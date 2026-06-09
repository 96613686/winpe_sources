# Microsoft.Crm.Common.Application.Platform.Email::AddPartyToHeader

- ea: `0x3d30`
- end: `0x3e25`
- name: `Microsoft.Crm.Common.Application.Platform.Email::AddPartyToHeader`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3ad0`

## callees

- `0x3d30`

## pseudocode

```c

```

## disassembly

```asm
0x3d30  ldarg.1
0x3d31  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x3d36  ldc.i4.0
0x3d37  cgt
0x3d39  ldstr    aAnEmptyPartyCo// "An empty party collection was passed to"...
0x3d3e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x3d43  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3d48  stloc.0
0x3d49  ldloc.0
0x3d4a  ldstr    aB// "<b>"
0x3d4f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d54  pop
0x3d55  ldloc.0
0x3d56  ldarg.0
0x3d57  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3d5c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d61  pop
0x3d62  ldloc.0
0x3d63  ldstr    aB_0// "</b> "
0x3d68  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d6d  pop
0x3d6e  ldc.i4.0
0x3d6f  stloc.1
0x3d70  br       loc_3E06
0x3d75  ldloc.1
0x3d76  brfalse.s loc_3D84
0x3d78  ldloc.0
0x3d79  ldstr    asc_9C44// "; "
0x3d7e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d83  pop
0x3d84  ldarg.1
0x3d85  ldloc.1
0x3d86  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x3d8b  stloc.2
0x3d8c  ldsfld   string [mscorlib]System.String::Empty
0x3d91  stloc.3
0x3d92  ldloc.2
0x3d93  ldstr    aPartyidname// "partyidname"
0x3d98  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3d9d  brfalse.s loc_3DB2
0x3d9f  ldloc.2
0x3da0  ldstr    aPartyidname// "partyidname"
0x3da5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3daa  castclass [mscorlib]System.String
0x3daf  stloc.3
0x3db0  br.s     loc_3DF5
0x3db2  ldloc.2
0x3db3  ldstr    aAddressused// "addressused"
0x3db8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3dbd  brfalse.s loc_3DD9
0x3dbf  ldloc.2
0x3dc0  ldstr    aAddressused// "addressused"
0x3dc5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3dca  isinst   [mscorlib]System.String
0x3dcf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3dd4  ldc.i4.0
0x3dd5  cgt.un
0x3dd7  br.s     loc_3DDA
0x3dd9  ldc.i4.0
0x3dda  ldstr    aPartyWithoutAn// "Party without an id also does not have "...
0x3ddf  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x3de4  ldloc.2
0x3de5  ldstr    aAddressused// "addressused"
0x3dea  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3def  castclass [mscorlib]System.String
0x3df4  stloc.3
0x3df5  ldloc.0
0x3df6  ldloc.3
0x3df7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3dfc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3e01  pop
0x3e02  ldloc.1
0x3e03  ldc.i4.1
0x3e04  add
0x3e05  stloc.1
0x3e06  ldloc.1
0x3e07  ldarg.1
0x3e08  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x3e0d  blt      loc_3D75
0x3e12  ldloc.0
0x3e13  ldstr    aBr// "<br>"
0x3e18  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3e1d  pop
0x3e1e  ldloc.0
0x3e1f  callvirt instance string [mscorlib]System.Object::ToString()
0x3e24  ret
```
