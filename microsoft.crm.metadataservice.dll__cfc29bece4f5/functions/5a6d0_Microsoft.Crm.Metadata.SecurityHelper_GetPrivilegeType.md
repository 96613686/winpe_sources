# Microsoft.Crm.Metadata.SecurityHelper::GetPrivilegeType

- ea: `0x5a6d0`
- end: `0x5a782`
- name: `Microsoft.Crm.Metadata.SecurityHelper::GetPrivilegeType`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x77e90`

## callees

- `0x5a6d0`

## string_xrefs

- `0x5a73a`: `Unexpected Access Rights: {0}`
- `0x5a764`: `privilegeType`

## pseudocode

```c

```

## disassembly

```asm
0x5a6d0  ldc.i4.m1
0x5a6d1  stloc.0
0x5a6d2  ldarg.0
0x5a6d3  ldc.i4.s 0x20
0x5a6d5  bgt.s    loc_5A6FB
0x5a6d7  ldarg.0
0x5a6d8  ldc.i4.1
0x5a6d9  sub
0x5a6da  switch   loc_5A729, loc_5A731, loc_5A735, loc_5A715
0x5a6ef  ldarg.0
0x5a6f0  ldc.i4.s 0x10
0x5a6f2  beq.s    loc_5A719
0x5a6f4  ldarg.0
0x5a6f5  ldc.i4.s 0x20
0x5a6f7  beq.s    loc_5A721
0x5a6f9  br.s     loc_5A735
0x5a6fb  ldarg.0
0x5a6fc  ldc.i4   0x10000
0x5a701  beq.s    loc_5A725
0x5a703  ldarg.0
0x5a704  ldc.i4   0x40000
0x5a709  beq.s    loc_5A72D
0x5a70b  ldarg.0
0x5a70c  ldc.i4   0x80000
0x5a711  beq.s    loc_5A71D
0x5a713  br.s     loc_5A735
0x5a715  ldc.i4.6
0x5a716  stloc.0
0x5a717  br.s     loc_5A75E
0x5a719  ldc.i4.7
0x5a71a  stloc.0
0x5a71b  br.s     loc_5A75E
0x5a71d  ldc.i4.4
0x5a71e  stloc.0
0x5a71f  br.s     loc_5A75E
0x5a721  ldc.i4.0
0x5a722  stloc.0
0x5a723  br.s     loc_5A75E
0x5a725  ldc.i4.3
0x5a726  stloc.0
0x5a727  br.s     loc_5A75E
0x5a729  ldc.i4.1
0x5a72a  stloc.0
0x5a72b  br.s     loc_5A75E
0x5a72d  ldc.i4.5
0x5a72e  stloc.0
0x5a72f  br.s     loc_5A75E
0x5a731  ldc.i4.2
0x5a732  stloc.0
0x5a733  br.s     loc_5A75E
0x5a735  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a73a  ldstr    aUnexpectedAcce// "Unexpected Access Rights: {0}"
0x5a73f  ldc.i4.1
0x5a740  newarr   [mscorlib]System.Object
0x5a745  dup
0x5a746  ldc.i4.0
0x5a747  ldarg.0
0x5a748  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0x5a74d  stelem.ref
0x5a74e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a753  ldc.i4   0x80040203
0x5a758  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5a75d  throw
0x5a75e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x5a763  dup
0x5a764  ldstr    aPrivilegetype// "privilegeType"
0x5a769  ldloca.s 0
0x5a76b  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x5a771  callvirt instance string [mscorlib]System.Object::ToString()
0x5a776  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5a77b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x5a780  ldloc.0
0x5a781  ret
```
