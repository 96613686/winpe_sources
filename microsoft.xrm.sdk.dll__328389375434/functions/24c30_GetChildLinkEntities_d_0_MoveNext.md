# <GetChildLinkEntities>d__0::MoveNext

- ea: `0x24c30`
- end: `0x24cf6`
- name: `<GetChildLinkEntities>d__0::MoveNext`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x93b0`
- `0x24c10`
- `0x24c30`
- `0x24d00`

## pseudocode

```c

```

## disassembly

```asm
0x24c30  ldarg.0
0x24c31  ldfld    int32 <GetChildLinkEntities>d__0::<>1__state
0x24c36  stloc.1
0x24c37  ldloc.1
0x24c38  switch   loc_24C50, loc_24C71, loc_24CC7
0x24c49  ldc.i4.0
0x24c4a  stloc.0
0x24c4b  leave    loc_24CF4
0x24c50  ldarg.0
0x24c51  ldc.i4.m1
0x24c52  stfld    int32 <GetChildLinkEntities>d__0::<>1__state
0x24c57  ldarg.0
0x24c58  ldarg.0
0x24c59  ldfld    class Microsoft.Xrm.Sdk.Query.LinkEntity <GetChildLinkEntities>d__0::link
0x24c5e  stfld    class Microsoft.Xrm.Sdk.Query.LinkEntity <GetChildLinkEntities>d__0::<>2__current
0x24c63  ldarg.0
0x24c64  ldc.i4.1
0x24c65  stfld    int32 <GetChildLinkEntities>d__0::<>1__state
0x24c6a  ldc.i4.1
0x24c6b  stloc.0
0x24c6c  leave    loc_24CF4
0x24c71  ldarg.0
0x24c72  ldc.i4.m1
0x24c73  stfld    int32 <GetChildLinkEntities>d__0::<>1__state
0x24c78  ldarg.0
0x24c79  ldarg.0
0x24c7a  ldfld    class Microsoft.Xrm.Sdk.Query.LinkEntity <GetChildLinkEntities>d__0::link
0x24c7f  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0x24c84  ldnull
0x24c85  ldftn    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Extensions.LinkEntityExtensions::GetChildLinkEntities(class Microsoft.Xrm.Sdk.Query.LinkEntity link)
0x24c8b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.Query.LinkEntity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Query.LinkEntity>>::.ctor(object, native int)
0x24c90  call     T0x2B000082
0x24c95  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Query.LinkEntity>::GetEnumerator()
0x24c9a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> <GetChildLinkEntities>d__0::<>7__wrap1
0x24c9f  ldarg.0
0x24ca0  ldc.i4.s 0xFD
0x24ca2  stfld    int32 <GetChildLinkEntities>d__0::<>1__state
0x24ca7  br.s     loc_24CCF
0x24ca9  ldarg.0
0x24caa  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> <GetChildLinkEntities>d__0::<>7__wrap1
0x24caf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Current()
0x24cb4  stloc.2
0x24cb5  ldarg.0
0x24cb6  ldloc.2
0x24cb7  stfld    class Microsoft.Xrm.Sdk.Query.LinkEntity <GetChildLinkEntities>d__0::<>2__current
0x24cbc  ldarg.0
0x24cbd  ldc.i4.2
0x24cbe  stfld    int32 <GetChildLinkEntities>d__0::<>1__state
0x24cc3  ldc.i4.1
0x24cc4  stloc.0
0x24cc5  leave.s  loc_24CF4
0x24cc7  ldarg.0
0x24cc8  ldc.i4.s 0xFD
0x24cca  stfld    int32 <GetChildLinkEntities>d__0::<>1__state
0x24ccf  ldarg.0
0x24cd0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> <GetChildLinkEntities>d__0::<>7__wrap1
0x24cd5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24cda  brtrue.s loc_24CA9
0x24cdc  ldarg.0
0x24cdd  call     instance void <GetChildLinkEntities>d__0::<>m__Finally1()
0x24ce2  ldarg.0
0x24ce3  ldnull
0x24ce4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> <GetChildLinkEntities>d__0::<>7__wrap1
0x24ce9  ldc.i4.0
0x24cea  stloc.0
0x24ceb  leave.s  loc_24CF4
0x24ced  ldarg.0
0x24cee  call     instance void <GetChildLinkEntities>d__0::System.IDisposable.Dispose()
0x24cf3  endfinally
0x24cf4  ldloc.0
0x24cf5  ret
```
