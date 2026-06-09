# Microsoft.Crm.Common.Repository::CloneArray

- ea: `0x18e0`
- end: `0x195b`
- name: `Microsoft.Crm.Common.Repository::CloneArray`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18e0`

## pseudocode

```c

```

## disassembly

```asm
0x18e0  ldtoken  mvar<u1>
0x18e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ea  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0x18ef  stloc.0
0x18f0  ldarg.0
0x18f1  ldlen
0x18f2  conv.i4
0x18f3  newarr   mvar<u1>
0x18f8  stloc.1
0x18f9  ldc.i4.0
0x18fa  stloc.2
0x18fb  br.s     loc_1953
0x18fd  ldarg.0
0x18fe  ldloc.2
0x18ff  ldelem   mvar<u1>
0x1904  stloc.3
0x1905  call     T0x2B000009
0x190a  stloc.s  4
0x190c  ldloc.0
0x190d  stloc.s  5
0x190f  ldc.i4.0
0x1910  stloc.s  6
0x1912  br.s     loc_193E
0x1914  ldloc.s  5
0x1916  ldloc.s  6
0x1918  ldelem.ref
0x1919  stloc.s  7
0x191b  ldloc.s  7
0x191d  ldloc.s  4
0x191f  box      mvar<u1>
0x1924  ldloc.s  7
0x1926  ldloc.3
0x1927  box      mvar<u1>
0x192c  ldnull
0x192d  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x1932  ldnull
0x1933  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x1938  ldloc.s  6
0x193a  ldc.i4.1
0x193b  add
0x193c  stloc.s  6
0x193e  ldloc.s  6
0x1940  ldloc.s  5
0x1942  ldlen
0x1943  conv.i4
0x1944  blt.s    loc_1914
0x1946  ldloc.1
0x1947  ldloc.2
0x1948  ldloc.s  4
0x194a  stelem   mvar<u1>
0x194f  ldloc.2
0x1950  ldc.i4.1
0x1951  add
0x1952  stloc.2
0x1953  ldloc.2
0x1954  ldarg.0
0x1955  ldlen
0x1956  conv.i4
0x1957  blt.s    loc_18FD
0x1959  ldloc.1
0x195a  ret
```
