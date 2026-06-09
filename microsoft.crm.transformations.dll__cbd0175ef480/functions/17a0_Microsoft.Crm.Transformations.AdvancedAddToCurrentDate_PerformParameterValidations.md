# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::PerformParameterValidations

- ea: `0x17a0`
- end: `0x1951`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::PerformParameterValidations`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1300`

## callees

- `0x17a0`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  ldarg.1
0x17a1  ldc.i4.0
0x17a2  ldelem.ref
0x17a3  brfalse.s loc_17D0
0x17a5  ldarg.1
0x17a6  ldc.i4.0
0x17a7  ldelem.ref
0x17a8  isinst   [mscorlib]System.Int32
0x17ad  brtrue.s loc_17D0
0x17af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17b4  ldstr    aInvalidInputTr// "Invalid input transformation parameter "...
0x17b9  ldc.i4.1
0x17ba  newarr   [mscorlib]System.Object
0x17bf  dup
0x17c0  ldc.i4.0
0x17c1  ldarg.1
0x17c2  ldc.i4.0
0x17c3  ldelem.ref
0x17c4  stelem.ref
0x17c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17ca  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x17cf  throw
0x17d0  ldarg.1
0x17d1  ldc.i4.1
0x17d2  ldelem.ref
0x17d3  brfalse.s loc_1800
0x17d5  ldarg.1
0x17d6  ldc.i4.1
0x17d7  ldelem.ref
0x17d8  isinst   [mscorlib]System.Int32
0x17dd  brtrue.s loc_1800
0x17df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17e4  ldstr    aInvalidInputTr_0// "Invalid input transformation parameter "...
0x17e9  ldc.i4.1
0x17ea  newarr   [mscorlib]System.Object
0x17ef  dup
0x17f0  ldc.i4.0
0x17f1  ldarg.1
0x17f2  ldc.i4.1
0x17f3  ldelem.ref
0x17f4  stelem.ref
0x17f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17fa  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x17ff  throw
0x1800  ldarg.1
0x1801  ldc.i4.2
0x1802  ldelem.ref
0x1803  brfalse.s loc_1830
0x1805  ldarg.1
0x1806  ldc.i4.2
0x1807  ldelem.ref
0x1808  isinst   [mscorlib]System.Int32
0x180d  brtrue.s loc_1830
0x180f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1814  ldstr    aInvalidInputTr_1// "Invalid input transformation parameter "...
0x1819  ldc.i4.1
0x181a  newarr   [mscorlib]System.Object
0x181f  dup
0x1820  ldc.i4.0
0x1821  ldarg.1
0x1822  ldc.i4.2
0x1823  ldelem.ref
0x1824  stelem.ref
0x1825  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x182a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x182f  throw
0x1830  ldarg.1
0x1831  ldc.i4.3
0x1832  ldelem.ref
0x1833  brfalse.s loc_1860
0x1835  ldarg.1
0x1836  ldc.i4.3
0x1837  ldelem.ref
0x1838  isinst   [mscorlib]System.Int32
0x183d  brtrue.s loc_1860
0x183f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1844  ldstr    aInvalidInputTr_2// "Invalid input transformation parameter "...
0x1849  ldc.i4.1
0x184a  newarr   [mscorlib]System.Object
0x184f  dup
0x1850  ldc.i4.0
0x1851  ldarg.1
0x1852  ldc.i4.3
0x1853  ldelem.ref
0x1854  stelem.ref
0x1855  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x185a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x185f  throw
0x1860  ldarg.1
0x1861  ldc.i4.4
0x1862  ldelem.ref
0x1863  brfalse.s loc_1890
0x1865  ldarg.1
0x1866  ldc.i4.4
0x1867  ldelem.ref
0x1868  isinst   [mscorlib]System.Int32
0x186d  brtrue.s loc_1890
0x186f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1874  ldstr    aInvalidInputTr_3// "Invalid input transformation parameter "...
0x1879  ldc.i4.1
0x187a  newarr   [mscorlib]System.Object
0x187f  dup
0x1880  ldc.i4.0
0x1881  ldarg.1
0x1882  ldc.i4.4
0x1883  ldelem.ref
0x1884  stelem.ref
0x1885  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x188a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x188f  throw
0x1890  ldarg.1
0x1891  ldc.i4.5
0x1892  ldelem.ref
0x1893  brfalse.s loc_18C0
0x1895  ldarg.1
0x1896  ldc.i4.5
0x1897  ldelem.ref
0x1898  isinst   [mscorlib]System.Int32
0x189d  brtrue.s loc_18C0
0x189f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18a4  ldstr    aInvalidInputTr_4// "Invalid input transformation parameter "...
0x18a9  ldc.i4.1
0x18aa  newarr   [mscorlib]System.Object
0x18af  dup
0x18b0  ldc.i4.0
0x18b1  ldarg.1
0x18b2  ldc.i4.5
0x18b3  ldelem.ref
0x18b4  stelem.ref
0x18b5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18ba  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x18bf  throw
0x18c0  ldarg.1
0x18c1  ldc.i4.6
0x18c2  ldelem.ref
0x18c3  brfalse.s loc_18F0
0x18c5  ldarg.1
0x18c6  ldc.i4.6
0x18c7  ldelem.ref
0x18c8  isinst   [mscorlib]System.Int32
0x18cd  brtrue.s loc_18F0
0x18cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18d4  ldstr    aInvalidInputTr_5// "Invalid input transformation parameter "...
0x18d9  ldc.i4.1
0x18da  newarr   [mscorlib]System.Object
0x18df  dup
0x18e0  ldc.i4.0
0x18e1  ldarg.1
0x18e2  ldc.i4.6
0x18e3  ldelem.ref
0x18e4  stelem.ref
0x18e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18ea  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x18ef  throw
0x18f0  ldarg.1
0x18f1  ldc.i4.7
0x18f2  ldelem.ref
0x18f3  brfalse.s loc_1920
0x18f5  ldarg.1
0x18f6  ldc.i4.7
0x18f7  ldelem.ref
0x18f8  isinst   [mscorlib]System.Int32
0x18fd  brtrue.s loc_1920
0x18ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1904  ldstr    aInvalidInputTr_6// "Invalid input transformation parameter "...
0x1909  ldc.i4.1
0x190a  newarr   [mscorlib]System.Object
0x190f  dup
0x1910  ldc.i4.0
0x1911  ldarg.1
0x1912  ldc.i4.7
0x1913  ldelem.ref
0x1914  stelem.ref
0x1915  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x191a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x191f  throw
0x1920  ldarg.1
0x1921  ldc.i4.8
0x1922  ldelem.ref
0x1923  brfalse.s loc_1950
0x1925  ldarg.1
0x1926  ldc.i4.8
0x1927  ldelem.ref
0x1928  isinst   [mscorlib]System.Int32
0x192d  brtrue.s loc_1950
0x192f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1934  ldstr    aInvalidInputTr_7// "Invalid input transformation parameter "...
0x1939  ldc.i4.1
0x193a  newarr   [mscorlib]System.Object
0x193f  dup
0x1940  ldc.i4.0
0x1941  ldarg.1
0x1942  ldc.i4.8
0x1943  ldelem.ref
0x1944  stelem.ref
0x1945  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x194a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x194f  throw
0x1950  ret
```
