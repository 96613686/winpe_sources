# Microsoft.Crm.Application.Platform.SolutionAdapter::AddLinkToSystemFormThroughProcessTrigger

- ea: `0x6edd0`
- end: `0x6ee8a`
- name: `Microsoft.Crm.Application.Platform.SolutionAdapter::AddLinkToSystemFormThroughProcessTrigger`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x6eb80`

## callees

- `0x45620`
- `0x6a120`
- `0x6a2a0`
- `0x6e850`

## string_xrefs

- `0x6edfb`: `processid`
- `0x6ee08`: `processtriggerlink`
- `0x6ee52`: `systemformlink`

## pseudocode

```c

```

## disassembly

```asm
0x6edd0  ldc.i4.s 0x1D
0x6edd2  call     int32 Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32 componentTypeCode)
0x6edd7  ldarg.0
0x6edd8  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6eddd  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(int32 typeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ede2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x6ede7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x6edec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x6edf1  ldstr    aProcesstrigger// "processtrigger"
0x6edf6  ldstr    aWorkflowid// "workflowid"
0x6edfb  ldstr    aProcessid// "processid"
0x6ee00  ldc.i4.1
0x6ee01  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6ee06  stloc.0
0x6ee07  ldloc.0
0x6ee08  ldstr    aProcesstrigger_0// "processtriggerlink"
0x6ee0d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::set_Alias(string)
0x6ee12  ldloc.0
0x6ee13  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_Columns()
0x6ee18  ldstr    aFormid// "formid"
0x6ee1d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x6ee22  ldloc.0
0x6ee23  ldc.i4.1
0x6ee24  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::set_JoinOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6ee29  ldarg.1
0x6ee2a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkEntities()
0x6ee2f  ldloc.0
0x6ee30  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6ee35  pop
0x6ee36  ldstr    aProcesstrigger// "processtrigger"
0x6ee3b  ldstr    aSystemform// "systemform"
0x6ee40  ldstr    aFormid// "formid"
0x6ee45  ldstr    aFormid// "formid"
0x6ee4a  ldc.i4.1
0x6ee4b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6ee50  stloc.1
0x6ee51  ldloc.1
0x6ee52  ldstr    aSystemformlink// "systemformlink"
0x6ee57  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::set_Alias(string)
0x6ee5c  ldloc.1
0x6ee5d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_Columns()
0x6ee62  ldstr    aFormid// "formid"
0x6ee67  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x6ee6c  ldloc.1
0x6ee6d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_Columns()
0x6ee72  ldstr    aType// "type"
0x6ee77  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x6ee7c  ldloc.0
0x6ee7d  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkEntities()
0x6ee82  ldloc.1
0x6ee83  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6ee88  pop
0x6ee89  ret
```
