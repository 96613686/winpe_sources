# Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveProcessForEditorCommand::Execute

- ea: `0x949e0`
- end: `0x94ac7`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveProcessForEditorCommand::Execute`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x59710`
- `0x5e470`
- `0x90d80`
- `0xa7610`

## string_xrefs

- `0x94a5f`: `triggeroncreate`
- `0x94a68`: `triggerondelete`
- `0x94a71`: `triggeronupdateattributelist`

## pseudocode

```c

```

## disassembly

```asm
0x949e0  ldc.i4.s 0x15
0x949e2  newarr   [mscorlib]System.String
0x949e7  dup
0x949e8  ldc.i4.0
0x949e9  ldstr    aName// "name"
0x949ee  stelem.ref
0x949ef  dup
0x949f0  ldc.i4.1
0x949f1  ldstr    aDescription_0// "description"
0x949f6  stelem.ref
0x949f7  dup
0x949f8  ldc.i4.2
0x949f9  ldstr    aXaml// "xaml"
0x949fe  stelem.ref
0x949ff  dup
0x94a00  ldc.i4.3
0x94a01  ldstr    aCategory// "category"
0x94a06  stelem.ref
0x94a07  dup
0x94a08  ldc.i4.4
0x94a09  ldstr    aPrimaryentity// "primaryentity"
0x94a0e  stelem.ref
0x94a0f  dup
0x94a10  ldc.i4.5
0x94a11  ldstr    aType// "type"
0x94a16  stelem.ref
0x94a17  dup
0x94a18  ldc.i4.6
0x94a19  ldstr    aMode// "mode"
0x94a1e  stelem.ref
0x94a1f  dup
0x94a20  ldc.i4.7
0x94a21  ldstr    aStatecode// "statecode"
0x94a26  stelem.ref
0x94a27  dup
0x94a28  ldc.i4.8
0x94a29  ldstr    aIscustomizable// "iscustomizable"
0x94a2e  stelem.ref
0x94a2f  dup
0x94a30  ldc.i4.s 9
0x94a32  ldstr    aOwnerid// "ownerid"
0x94a37  stelem.ref
0x94a38  dup
0x94a39  ldc.i4.s 0xA
0x94a3b  ldstr    aDescription_0// "description"
0x94a40  stelem.ref
0x94a41  dup
0x94a42  ldc.i4.s 0xB
0x94a44  ldstr    aProcessroleass// "processroleassignment"
0x94a49  stelem.ref
0x94a4a  dup
0x94a4b  ldc.i4.s 0xC
0x94a4d  ldstr    aSubprocess// "subprocess"
0x94a52  stelem.ref
0x94a53  dup
0x94a54  ldc.i4.s 0xD
0x94a56  ldstr    aOndemand// "ondemand"
0x94a5b  stelem.ref
0x94a5c  dup
0x94a5d  ldc.i4.s 0xE
0x94a5f  ldstr    aTriggeroncreat// "triggeroncreate"
0x94a64  stelem.ref
0x94a65  dup
0x94a66  ldc.i4.s 0xF
0x94a68  ldstr    aTriggerondelet// "triggerondelete"
0x94a6d  stelem.ref
0x94a6e  dup
0x94a6f  ldc.i4.s 0x10
0x94a71  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x94a76  stelem.ref
0x94a77  dup
0x94a78  ldc.i4.s 0x11
0x94a7a  ldstr    aScope// "scope"
0x94a7f  stelem.ref
0x94a80  dup
0x94a81  ldc.i4.s 0x12
0x94a83  ldstr    aIstransacted// "istransacted"
0x94a88  stelem.ref
0x94a89  dup
0x94a8a  ldc.i4.s 0x13
0x94a8c  ldstr    aUniquename// "uniquename"
0x94a91  stelem.ref
0x94a92  dup
0x94a93  ldc.i4.s 0x14
0x94a95  ldstr    aSolutionid_0// "solutionid"
0x94a9a  stelem.ref
0x94a9b  stloc.0
0x94a9c  ldstr    aWorkflow// "workflow"
0x94aa1  ldarg.0
0x94aa2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveProcessForEditorCommand::_processId
0x94aa7  ldloc.0
0x94aa8  ldarg.0
0x94aa9  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x94aae  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x94ab3  stloc.1
0x94ab4  ldloc.1
0x94ab5  ldstr    aCategory// "category"
0x94aba  ldc.i4.m1
0x94abb  callvirt instance int32 Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsNumber(string name, int32 defaultValue)
0x94ac0  ldloc.1
0x94ac1  call     class Microsoft.Crm.Application.Platform.IProcessEntityProxy ProcessEntityProxyFacory::GetProxy(int32 category, class Microsoft.Crm.Application.Platform.Entity process)
0x94ac6  ret
```
