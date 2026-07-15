<script>
    import { ScatterChartComponent, BubbleChartComponent } from "@visuallyjs/browser-ui-svelte";
    import { charts } from "./examples";
</script>

<div class="vjs-scatter-bubble-chart">
    {#each charts as chart}
        <div class="vjs-chart-example">
            <div class="vjs-chart-example-title">{chart.desc}</div>
            {#if chart.comments}
                <div class="vjs-chart-example-comments">{chart.comments}</div>
            {/if}
            {#if chart.type === 'scatter'}
                <ScatterChartComponent className="vjs-chart-example-container" options={chart.options.config} url={chart.options.url}/>
            {:else if chart.type === 'bubble'}
                <BubbleChartComponent className="vjs-chart-example-container" options={chart.options.config} url={chart.options.url} />
            {/if}
        </div>
    {/each}
</div>
