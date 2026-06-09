# Microsoft.Crm.LanguageUtility::IsValidMuiPackVersion

- ea: `0x20d10`
- end: `0x20e32`
- name: `Microsoft.Crm.LanguageUtility::IsValidMuiPackVersion`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x20e40`

## callees

- `0x20d10`

## string_xrefs

- `0x20db3`: `ProvisionLanguage: Major & Minor versions of the MUI pack '{0}' and of the installed CRM '{1}' do not match. They must be the same in order to be able to reprovision using the Mui pack. Reprovision will re-enable the installed MUI pack`
- `0x20df3`: `ProvisionLanguage: Major & Minor versions of the MUI pack '{0}', the installed MUI pack '{1}', and the installed CRM '{2}' do not match. They must be the same in order to be able to reprovision using the Mui pack. Reprovision will re-enable the installed MUI pack`

## pseudocode

```c

```

## disassembly

```asm
0x20d10  ldarg.3
0x20d11  ldstr    aOrganizationid_0// "organizationId"
0x20d16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20d1b  ldc.i4.0
0x20d1c  stloc.0
0x20d1d  ldnull
0x20d1e  stloc.1
0x20d1f  ldnull
0x20d20  stloc.2
0x20d21  ldnull
0x20d22  stloc.3
0x20d23  ldarg.0
0x20d24  ldloca.s 1
0x20d26  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0x20d2b  brfalse  loc_20E11
0x20d30  ldarg.1
0x20d31  ldloca.s 2
0x20d33  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0x20d38  brfalse  loc_20E11
0x20d3d  ldarg.2
0x20d3e  ldloca.s 3
0x20d40  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0x20d45  brfalse  loc_20E11
0x20d4a  ldloc.1
0x20d4b  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x20d50  ldloc.1
0x20d51  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x20d56  ldloc.1
0x20d57  callvirt instance int32 [mscorlib]System.Version::get_Build()
0x20d5c  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32)
0x20d61  stloc.s  4
0x20d63  ldloc.2
0x20d64  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x20d69  ldloc.2
0x20d6a  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x20d6f  ldloc.2
0x20d70  callvirt instance int32 [mscorlib]System.Version::get_Build()
0x20d75  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32)
0x20d7a  stloc.s  5
0x20d7c  ldloc.3
0x20d7d  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x20d82  ldloc.3
0x20d83  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x20d88  ldloc.3
0x20d89  callvirt instance int32 [mscorlib]System.Version::get_Build()
0x20d8e  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32)
0x20d93  stloc.s  6
0x20d95  ldloc.1
0x20d96  ldloc.2
0x20d97  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x20d9c  brfalse.s loc_20DCD
0x20d9e  ldloc.s  4
0x20da0  ldloc.s  6
0x20da2  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x20da7  brfalse.s loc_20DB0
0x20da9  ldc.i4.1
0x20daa  stloc.0
0x20dab  br       loc_20E30
0x20db0  ldarg.3
0x20db1  ldc.i4.s 0x18
0x20db3  ldstr    aProvisionlangu// "ProvisionLanguage: Major & Minor versio"...
0x20db8  ldc.i4.2
0x20db9  newarr   [mscorlib]System.Object
0x20dbe  dup
0x20dbf  ldc.i4.0
0x20dc0  ldloc.1
0x20dc1  stelem.ref
0x20dc2  dup
0x20dc3  ldc.i4.1
0x20dc4  ldloc.3
0x20dc5  stelem.ref
0x20dc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20dcb  br.s     loc_20E30
0x20dcd  ldloc.1
0x20dce  ldloc.2
0x20dcf  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x20dd4  brfalse.s loc_20E30
0x20dd6  ldloc.s  4
0x20dd8  ldloc.s  5
0x20dda  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x20ddf  brfalse.s loc_20DF0
0x20de1  ldloc.s  4
0x20de3  ldloc.s  6
0x20de5  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x20dea  brfalse.s loc_20DF0
0x20dec  ldc.i4.1
0x20ded  stloc.0
0x20dee  br.s     loc_20E30
0x20df0  ldarg.3
0x20df1  ldc.i4.s 0x18
0x20df3  ldstr    aProvisionlangu_0// "ProvisionLanguage: Major & Minor versio"...
0x20df8  ldc.i4.3
0x20df9  newarr   [mscorlib]System.Object
0x20dfe  dup
0x20dff  ldc.i4.0
0x20e00  ldloc.1
0x20e01  stelem.ref
0x20e02  dup
0x20e03  ldc.i4.1
0x20e04  ldloc.2
0x20e05  stelem.ref
0x20e06  dup
0x20e07  ldc.i4.2
0x20e08  ldloc.3
0x20e09  stelem.ref
0x20e0a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20e0f  br.s     loc_20E30
0x20e11  ldarg.3
0x20e12  ldc.i4.s 0x18
0x20e14  ldstr    aProvisionlangu_1// "ProvisionLanguage: FileVersion '{0}', D"...
0x20e19  ldc.i4.3
0x20e1a  newarr   [mscorlib]System.Object
0x20e1f  dup
0x20e20  ldc.i4.0
0x20e21  ldloc.1
0x20e22  stelem.ref
0x20e23  dup
0x20e24  ldc.i4.1
0x20e25  ldloc.2
0x20e26  stelem.ref
0x20e27  dup
0x20e28  ldc.i4.2
0x20e29  ldloc.3
0x20e2a  stelem.ref
0x20e2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20e30  ldloc.0
0x20e31  ret
```
