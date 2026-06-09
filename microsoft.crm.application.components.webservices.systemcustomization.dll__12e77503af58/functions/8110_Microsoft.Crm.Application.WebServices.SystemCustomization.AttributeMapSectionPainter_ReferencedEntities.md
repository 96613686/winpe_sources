# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::ReferencedEntities

- ea: `0x8110`
- end: `0x81f7`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::ReferencedEntities`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x7e60`

## callees

- `0x8110`

## string_xrefs

- `0x8183`: `Referencing Privilege Denied : `

## pseudocode

```c

```

## disassembly

```asm
0x8110  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8115  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x811a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x811f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8124  stloc.0
0x8125  ldc.i4.1
0x8126  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0x812b  stloc.1
0x812c  ldloc.1
0x812d  ldstr    aReferencing// "referencing_"
0x8132  ldarg.0
0x8133  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_inputFileId
0x8138  call     string [mscorlib]System.String::Concat(string, string)
0x813d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8142  ldloc.1
0x8143  ldsfld   string [mscorlib]System.String::Empty
0x8148  ldsfld   string [mscorlib]System.String::Empty
0x814d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x8152  ldloc.1
0x8153  ldsfld   string [mscorlib]System.String::Empty
0x8158  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x815d  ldarg.0
0x815e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8163  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::GetAllowedReferencedEntities()
0x8168  stloc.2
0x8169  leave.s  loc_81AD
0x816b  stloc.3
0x816c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x8171  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x8176  ldstr    a0// "{0}"
0x817b  ldc.i4.1
0x817c  newarr   [mscorlib]System.Object
0x8181  dup
0x8182  ldc.i4.0
0x8183  ldstr    aReferencingPri// "Referencing Privilege Denied : "
0x8188  ldloc.3
0x8189  callvirt instance string [mscorlib]System.Object::ToString()
0x818e  call     string [mscorlib]System.String::Concat(string, string)
0x8193  stelem.ref
0x8194  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8199  ldloc.3
0x819a  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x819f  ldc.i4   0x80040220
0x81a4  bne.un.s loc_81AB
0x81a6  ldloc.1
0x81a7  stloc.s  4
0x81a9  leave.s  loc_81F4
0x81ab  rethrow
0x81ad  ldloc.2
0x81ae  stloc.s  5
0x81b0  ldc.i4.0
0x81b1  stloc.s  6
0x81b3  br.s     loc_81EA
0x81b5  ldloc.s  5
0x81b7  ldloc.s  6
0x81b9  ldelem   [mscorlib]System.Guid
0x81be  stloc.s  7
0x81c0  ldloc.0
0x81c1  ldloc.s  7
0x81c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x81c8  stloc.s  8
0x81ca  ldloc.1
0x81cb  ldloc.s  8
0x81cd  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x81d2  ldc.i4.1
0x81d3  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x81d8  ldloc.s  8
0x81da  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x81df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x81e4  ldloc.s  6
0x81e6  ldc.i4.1
0x81e7  add
0x81e8  stloc.s  6
0x81ea  ldloc.s  6
0x81ec  ldloc.s  5
0x81ee  ldlen
0x81ef  conv.i4
0x81f0  blt.s    loc_81B5
0x81f2  ldloc.1
0x81f3  ret
0x81f4  ldloc.s  4
0x81f6  ret
```
