# Blog post proposal for your final project

Your final project is a **_technical blog post_** that uses a statistical model to answer an environmental data science question. The full description and rubric are on the [course website](https://eds-222-stats-f26.github.io/final-project.html).

This proposal is the second checkpoint for that project. Like all the final project checkpoints, it is ungraded. Its purpose is to move you from describing your data to planning your analysis, and to get feedback on your approach before you commit to it. Your exploratory analysis is the foundation for this proposal. If your question or data changed since then, that's ok!

Respond to the prompts below in a new Quarto document named `proposal.qmd`. Write in full sentences, and include any code you used. You may reuse text, code, and figures from `eda.qmd`, but revise them based on the feedback you received.

> [!IMPORTANT]
> As before, keep your data in your personal folder on Workbench _outside_ of this repo.

## 1. Your question and data

1. State your question in one sentence. If it changed since your exploratory analysis, briefly explain how and why.
2. In one paragraph, give the context for your question: why it matters, to whom, and what is already known about it. Cite at least **two sources** (these can be scientific literature, news articles, government reports, or any other reputable source).
3. Describe your data in a few sentences: the source, who collected it and how, what one row represents, and the response variable you're most interested in.
4. Include the one figure from your exploratory analysis (or create a new one) that best shows the relationship between your response and explanatory variables.

## 2. Causal relationships

1. Draw a directed acyclic graph (DAG) of the causal relationships you think connect your explanatory variable to your response. Include at least one other variable that affects your response, and at least one potential **confounder** (a variable that affects both your explanatory and response variables). You may draw it by hand and include a photo, or use a tool like `mermaid` (see below).t
2. Explain each arrow in your DAG in one sentence. Why do you think that causal relationship exists?
3. Which variables in your DAG are in your data? Which are not? How might the missing variables bias your results?

> [!TIP]
> Recall the Simpson's paradox example from this homework: the relationship between distance to the freeway and soil lead changed substantially once we accounted for area. A DAG is how you anticipate problems like that _before_ fitting your model.

> [!TIP]
> [Mermaid](https://quarto.org/docs/authoring/diagrams.html) is a tool for making diagrams that you can use in Quarto to make DAGs. Here's an example of a DAG where $x_1$ and $x_2$ have causal effects on $y$, and $x_2$ has an effect on $x_1$. In this example, $x_2$ is a _confounder_ of the relationship between $x_1$ and $y$.

```{mermaid}
flowchart LR
  x1 --> y
  x2 --> x1
  x2 --> y
```

## 3. Modeling considerations

1. Describe which variables you intend to include as predictors, and explain why you will use them in your model. Use your DAG to justify which variables you include and which you leave out. 
2. What is the _type_ of your response variable? Is it continuous or discrete? If it's continuous, is it bounded on the lower or upper end, like a strictly positive variable (0, Inf) or a proportion (0, 1)? If it's discrete, is it counts or categories? The _type_ of your response variable will guide your modeling choices later, after we cover generalized linear models.
3. State your _scientific_ hypothesis in plain language. Then state the _statistical_ null and alternative hypotheses in terms of a specific predictor variable's coefficient in your model.


## 4. Questions for feedback

What part of your analysis are you least sure about? What specific feedback would help you most?
