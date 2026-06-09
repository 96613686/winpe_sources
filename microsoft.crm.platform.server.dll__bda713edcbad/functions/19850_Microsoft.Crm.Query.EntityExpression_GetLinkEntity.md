# Microsoft.Crm.Query.EntityExpression::GetLinkEntity

- ea: `0x19850`
- end: `0x1992a`
- name: `Microsoft.Crm.Query.EntityExpression::GetLinkEntity`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x169a0`
- `0x87cc0`

## callees

- `0x184f0`
- `0x197f0`
- `0x19850`
- `0x88130`

## string_xrefs

- `0x198c4`: `There's more than one LinkEntity expressions with name={0}`
- `0x19904`: `Link entity with name or alias {0} is not found`

## pseudocode

```c

```

## disassembly

```asm
0x19850  newobj   instance void <>c__DisplayClass129_0::.ctor()
0x19855  stloc.0
0x19856  ldloc.0
0x19857  ldarg.1
0x19858  stfld    string <>c__DisplayClass129_0::linkEntityName
0x1985d  ldarg.0
0x1985e  ldloc.0
0x1985f  ldfld    string <>c__DisplayClass129_0::linkEntityName
0x19864  ldloca.s 1
0x19866  call     instance bool Microsoft.Crm.Query.EntityExpression::TryGetLinkEntityByTableAlias(string linkEntityName, [out] class Microsoft.Crm.Query.LinkEntityExpression& linkEntity)
0x1986b  brtrue   loc_198FC
0x19870  ldarg.0
0x19871  call     instance class Microsoft.Crm.Query.LinkEntityExpressionCollection Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x19876  call     T0x2B00002F
0x1987b  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>> <>c::<>9__129_0
0x19880  dup
0x19881  brtrue.s loc_1989A
0x19883  pop
0x19884  ldsfld   class <>c <>c::<>9
0x19889  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression> <>c::<GetLinkEntity>b__129_0(class Microsoft.Crm.Query.LinkEntityExpression exp)
0x1988f  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>>::.ctor(object, native int)
0x19894  dup
0x19895  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>> <>c::<>9__129_0
0x1989a  call     T0x2B000030
0x1989f  ldloc.0
0x198a0  ldftn    instance bool <>c__DisplayClass129_0::<GetLinkEntity>b__1(class Microsoft.Crm.Query.LinkEntityExpression entity)
0x198a6  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, bool>::.ctor(object, native int)
0x198ab  call     T0x2B000037
0x198b0  call     T0x2B000038
0x198b5  stloc.2
0x198b6  ldloc.2
0x198b7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LinkEntityExpression>::get_Count()
0x198bc  ldc.i4.1
0x198bd  ble.s    loc_198E8
0x198bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x198c4  ldstr    aThereSMoreThan// "There's more than one LinkEntity expres"...
0x198c9  ldc.i4.1
0x198ca  newarr   [mscorlib]System.Object
0x198cf  dup
0x198d0  ldc.i4.0
0x198d1  ldloc.0
0x198d2  ldfld    string <>c__DisplayClass129_0::linkEntityName
0x198d7  stelem.ref
0x198d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x198dd  ldc.i4   0x80041108
0x198e2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x198e7  throw
0x198e8  ldloc.2
0x198e9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LinkEntityExpression>::get_Count()
0x198ee  ldc.i4.0
0x198ef  bgt.s    loc_198F4
0x198f1  ldnull
0x198f2  br.s     loc_198FB
0x198f4  ldloc.2
0x198f5  ldc.i4.0
0x198f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x198fb  stloc.1
0x198fc  ldloc.1
0x198fd  brtrue.s loc_19928
0x198ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19904  ldstr    aLinkEntityWith// "Link entity with name or alias {0} is n"...
0x19909  ldc.i4.1
0x1990a  newarr   [mscorlib]System.Object
0x1990f  dup
0x19910  ldc.i4.0
0x19911  ldloc.0
0x19912  ldfld    string <>c__DisplayClass129_0::linkEntityName
0x19917  stelem.ref
0x19918  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1991d  ldc.i4   0x80041108
0x19922  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19927  throw
0x19928  ldloc.1
0x19929  ret
```
