MyTheories is a different implementation of the Theories runner in Junit4 which provides better reports.

See the following example:

```
@RunWith(MyTheories.class)
public class SampleTest {
    @DataPoint static int a = 1;
    @DataPoint static int b = 2;
    @DataPoint static int c = -1;

    @Theory
    public void $shouldBeGreaterThanZero(int param) {
        Assert.assertTrue(param > 0);
    }
}
```

After you run the above test, you will get the following test reports:
```
1shouldBeGreaterThanZero  passed
2shouldBeGreaterThanZero  passed
-1shouldBeGreaterThanZero failed
```

Note that the special character $ in test method name is replaced with corresponding DataPoint's string representation.