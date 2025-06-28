- map(): This method is primarily used for element-wise transformations on a Series (a single column). It's useful for simple operations like squaring numbers, modifying strings, or substituting values based on a dictionary or another Series. map() is generally faster for these specific tasks.

- apply(): This method offers more flexibility and can be used on both Series and DataFrames. When used on a Series, it works similarly to map(). However, its true power lies in its ability to apply functions along rows or columns of a DataFrame (using the axis parameter). This makes apply() suitable for tasks like calculating the mean of each column or performing more complex functions involving multiple columns. While potentially slightly slower than map() for single-column operations on a Series, it excels in versatility.
  Applies a function column-wise or row-wise
  df['Description'] = df.apply(
  lambda row: f"{row['Gender']} scored {row['Score']}", axis=1
  )
  df['Score_Status'] = df['Score'].apply(lambda x: 'Pass' if x >= 80 else 'Fail')

- applymap() – Operates on individual elements (cell level)
  ex: df.applymap(lambda x: x.strip() if isinstance(x, str) else x)
