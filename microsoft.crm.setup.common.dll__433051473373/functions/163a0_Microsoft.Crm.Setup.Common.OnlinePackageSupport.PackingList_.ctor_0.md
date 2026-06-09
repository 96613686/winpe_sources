# Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::.ctor_0

- ea: `0x163a0`
- end: `0x163fe`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::.ctor_0`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16390`

## callees

- `0x163a0`
- `0x16410`
- `0x16430`
- `0x16440`
- `0x16460`
- `0x16480`

## string_xrefs

- `0x163a7`: `primaryPackageDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0x163a0  ldarg.0
0x163a1  call     instance void [mscorlib]System.Object::.ctor()
0x163a6  ldarg.1
0x163a7  ldstr    aPrimarypackage// "primaryPackageDescriptor"
0x163ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x163b1  ldarg.0
0x163b2  ldarg.1
0x163b3  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::set_PrimaryPackageDescriptor(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor value)
0x163b8  ldarg.0
0x163b9  ldarg.2
0x163ba  dup
0x163bb  brtrue.s loc_163C4
0x163bd  pop
0x163be  ldc.i4.0
0x163bf  newarr   Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor
0x163c4  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::set_SecondaryPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor> value)
0x163c9  ldarg.0
0x163ca  ldarg.3
0x163cb  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::set_IsCompletePackage(bool value)
0x163d0  ldc.i4.1
0x163d1  ldarg.0
0x163d2  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_SecondaryPackages()
0x163d7  call     T0x2B00001F
0x163dc  add
0x163dd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor>::.ctor(int32)
0x163e2  stloc.0
0x163e3  ldloc.0
0x163e4  ldarg.1
0x163e5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor>::Add(var<u1>)
0x163ea  ldloc.0
0x163eb  ldarg.0
0x163ec  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor> Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_SecondaryPackages()
0x163f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x163f6  ldarg.0
0x163f7  ldloc.0
0x163f8  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::set_AllPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor> value)
0x163fd  ret
```
