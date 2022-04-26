<script>
  import { FeedbackStore } from "../stores";

  $: count = $FeedbackStore.length;
  $: average =
    $FeedbackStore.reduce((a, { rating }) => a + rating, 0) /
    $FeedbackStore.length;
</script>

<div class="feedback-stats">
  <h1>{count} Reviews</h1>
  <h4>Ratings average: {average}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
