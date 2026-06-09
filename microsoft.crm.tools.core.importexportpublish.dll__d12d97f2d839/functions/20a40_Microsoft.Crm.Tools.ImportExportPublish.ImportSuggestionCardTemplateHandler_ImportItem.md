# Microsoft.Crm.Tools.ImportExportPublish.ImportSuggestionCardTemplateHandler::ImportItem

- ea: `0x20a40`
- end: `0x20b18`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSuggestionCardTemplateHandler::ImportItem`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x20a40`
- `0x35e50`
- `0x46410`
- `0x464d0`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x20a46`: `/ImportExportXml/SuggestionCardTemplates`
- `0x20a5d`: `SuggestionCardTemplate`
- `0x20a9d`: `SuggestionCardTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x20a40  ldarg.0
0x20a41  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_doc
0x20a46  ldstr    aImportexportxm_34// "/ImportExportXml/SuggestionCardTemplate"...
0x20a4b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x20a50  stloc.0
0x20a51  ldloc.0
0x20a52  brtrue.s loc_20A55
0x20a54  ret
0x20a55  nop
0x20a56  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.SuggestionCardTemplateService::.ctor()
0x20a5b  stloc.1
0x20a5c  ldloc.0
0x20a5d  ldstr    aSuggestioncard// "SuggestionCardTemplate"
0x20a62  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x20a67  stloc.2
0x20a68  ldloc.2
0x20a69  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x20a6e  stloc.3
0x20a6f  br.s     loc_20AB7
0x20a71  ldloc.3
0x20a72  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x20a77  castclass [System.Xml]System.Xml.XmlNode
0x20a7c  stloc.s  4
0x20a7e  ldarg.0
0x20a7f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x20a84  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x20a89  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.SuggestionCardTemplate::.ctor(valuetype [mscorlib]System.Guid)
0x20a8e  stloc.s  5
0x20a90  ldarg.0
0x20a91  ldloc.s  4
0x20a93  ldloc.s  5
0x20a95  ldc.i4.1
0x20a96  newarr   [mscorlib]System.String
0x20a9b  dup
0x20a9c  ldc.i4.0
0x20a9d  ldstr    aSuggestioncard// "SuggestionCardTemplate"
0x20aa2  stelem.ref
0x20aa3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::InitializeEntity(class [System.Xml]System.Xml.XmlNode entityNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, string[] excludedNodes)
0x20aa8  ldarg.0
0x20aa9  ldloc.1
0x20aaa  ldloc.s  5
0x20aac  ldarg.0
0x20aad  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x20ab2  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::EnsureEntityExisted(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20ab7  ldloc.3
0x20ab8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20abd  brtrue.s loc_20A71
0x20abf  leave.s  loc_20AD5
0x20ac1  ldloc.3
0x20ac2  isinst   [mscorlib]System.IDisposable
0x20ac7  stloc.s  6
0x20ac9  ldloc.s  6
0x20acb  brfalse.s loc_20AD4
0x20acd  ldloc.s  6
0x20acf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20ad4  endfinally
0x20ad5  leave.s  loc_20AE1
0x20ad7  ldloc.2
0x20ad8  brfalse.s loc_20AE0
0x20ada  ldloc.2
0x20adb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20ae0  endfinally
0x20ae1  ldarg.0
0x20ae2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x20ae7  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::SuggestionCardTemplateImportSuccessMessage
0x20aec  ldc.i4.1
0x20aed  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x20af2  leave.s  loc_20B17
0x20af4  stloc.s  7
0x20af6  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::SuggestionCardTemplateImportErrorMessage
0x20afb  stloc.s  8
0x20afd  ldarg.0
0x20afe  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x20b03  ldloc.s  8
0x20b05  ldloc.s  7
0x20b07  ldc.i4.1
0x20b08  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x20b0d  ldloc.s  8
0x20b0f  ldloc.s  7
0x20b11  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportGenericEntitiesException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x20b16  throw
0x20b17  ret
```
