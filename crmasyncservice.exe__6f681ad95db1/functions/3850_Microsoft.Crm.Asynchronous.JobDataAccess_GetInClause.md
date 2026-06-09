# Microsoft.Crm.Asynchronous.JobDataAccess::GetInClause

- ea: `0x3850`
- end: `0x392b`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::GetInClause`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2b30`
- `0x3600`
- `0x3d60`

## callees

- `0x3850`

## pseudocode

```c

```

## disassembly

```asm
0x3850  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3855  stloc.0
0x3856  ldloc.0
0x3857  ldstr    asc_10D08// "("
0x385c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3861  pop
0x3862  ldloc.0
0x3863  ldstr    asc_10D0C// "'"
0x3868  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x386d  pop
0x386e  ldarg.1
0x386f  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3874  ldc.i4.0
0x3875  ble.s    loc_38F2
0x3877  ldloc.0
0x3878  ldarg.1
0x3879  ldc.i4.0
0x387a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x387f  stloc.1
0x3880  ldloca.s 1
0x3882  constrained. [mscorlib]System.Guid
0x3888  callvirt instance string [mscorlib]System.Object::ToString()
0x388d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3892  pop
0x3893  ldloc.0
0x3894  ldstr    asc_10D0C// "'"
0x3899  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x389e  pop
0x389f  ldc.i4.1
0x38a0  stloc.2
0x38a1  br.s     loc_38E7
0x38a3  ldloc.0
0x38a4  ldstr    asc_10D10// ","
0x38a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x38ae  pop
0x38af  ldloc.0
0x38b0  ldstr    asc_10D0C// "'"
0x38b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x38ba  pop
0x38bb  ldloc.0
0x38bc  ldarg.1
0x38bd  ldloc.2
0x38be  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x38c3  stloc.1
0x38c4  ldloca.s 1
0x38c6  constrained. [mscorlib]System.Guid
0x38cc  callvirt instance string [mscorlib]System.Object::ToString()
0x38d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x38d6  pop
0x38d7  ldloc.0
0x38d8  ldstr    asc_10D0C// "'"
0x38dd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x38e2  pop
0x38e3  ldloc.2
0x38e4  ldc.i4.1
0x38e5  add
0x38e6  stloc.2
0x38e7  ldloc.2
0x38e8  ldarg.1
0x38e9  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x38ee  blt.s    loc_38A3
0x38f0  br.s     loc_3918
0x38f2  ldloc.0
0x38f3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38f8  stloc.1
0x38f9  ldloca.s 1
0x38fb  constrained. [mscorlib]System.Guid
0x3901  callvirt instance string [mscorlib]System.Object::ToString()
0x3906  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x390b  pop
0x390c  ldloc.0
0x390d  ldstr    asc_10D0C// "'"
0x3912  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3917  pop
0x3918  ldloc.0
0x3919  ldstr    asc_CFB6// ")"
0x391e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3923  pop
0x3924  ldloc.0
0x3925  callvirt instance string [mscorlib]System.Object::ToString()
0x392a  ret
```
