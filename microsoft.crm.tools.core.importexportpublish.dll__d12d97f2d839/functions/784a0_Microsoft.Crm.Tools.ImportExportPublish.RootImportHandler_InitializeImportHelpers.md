# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeImportHelpers

- ea: `0x784a0`
- end: `0x792b3`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeImportHelpers`
- size: `3603`
- prototype: ``
- caller_count: `2`
- callee_count: `119`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x793b0`
- `0x7a6c0`

## callees

- `0x18fe0`
- `0x1e4b0`
- `0x1e6e0`
- `0x1e720`
- `0x1eba0`
- `0x1ef90`
- `0x1efa0`
- `0x1f0a0`
- `0x1fb10`
- `0x1fb40`
- `0x1ff10`
- `0x1ff20`
- `0x207b0`
- `0x208c0`
- `0x20a20`
- `0x20a30`
- `0x2b2a0`
- `0x2b2e0`
- `0x3d0b0`
- `0x3d0e0`
- `0x3d130`
- `0x3d160`
- `0x3d1a0`
- `0x3d7c0`
- `0x3d870`
- `0x3e9b0`
- `0x3e9d0`
- `0x3ec80`
- `0x3ed00`
- `0x3f3f0`
- `0x3f460`
- `0x3fb30`
- `0x3fb70`
- `0x40640`
- `0x40650`
- `0x40750`
- `0x407a0`
- `0x41050`
- `0x41080`
- `0x413c0`
- `0x47290`
- `0x472d0`
- `0x47cb0`
- `0x47d20`
- `0x4d720`
- `0x4d760`
- `0x4e300`
- `0x50300`
- `0x50370`
- `0x50500`

## string_xrefs

- `0x78b02`: `PluginAssembly`
- `0x78b50`: `PluginType`
- `0x788db`: `isvconfig`
- `0x78b27`: `PluginTypes`
- `0x78b4b`: `PluginTypes`
- `0x78ad9`: `PluginAssemblies`
- `0x78afd`: `PluginAssemblies`
- `0x78b07`: `pluginassembly`
- `0x78b55`: `plugintype`

## pseudocode

```c

```

## disassembly

```asm
0x784a0  ldarg.3
0x784a1  ldstr    aInitializeimpo// "InitializeImportHelpers"
0x784a6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x784ab  stloc.0
0x784ac  ldarg.0
0x784ad  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x784b2  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x784b7  ldarg.0
0x784b8  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x784bd  ldarg.0
0x784be  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x784c3  ldarg.0
0x784c4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x784c9  ldarg.0
0x784ca  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x784cf  ldarg.s  4
0x784d1  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportStagingStartHandler::.ctor(class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer importTracer, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ICustomizationSqlLockManager lockManager)
0x784d6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x784db  pop
0x784dc  ldarg.0
0x784dd  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_Setup()
0x784e2  brtrue.s loc_7852D
0x784e4  ldarg.0
0x784e5  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x784ea  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument)
0x784ef  brfalse.s loc_7852D
0x784f1  ldarg.0
0x784f2  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x784f7  ldarg.0
0x784f8  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x784fd  ldarg.0
0x784fe  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::pinpointDocument
0x78503  ldarg.0
0x78504  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::compatibilityXml
0x78509  ldarg.0
0x7850a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7850f  ldarg.0
0x78510  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x78515  ldarg.0
0x78516  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::locLabelHelper
0x7851b  ldarg.1
0x7851c  ldarg.0
0x7851d  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::holdingSolution
0x78522  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlDocument pinpointDocument, string compatibilityXml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper locLabelHelper, valuetype [mscorlib]System.Guid solutionId, bool holdingSolution)
0x78527  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7852c  pop
0x7852d  ldarg.0
0x7852e  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78533  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportOptionSetsHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument)
0x78538  brfalse.s loc_78576
0x7853a  ldarg.0
0x7853b  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x78540  ldarg.0
0x78541  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78546  ldarg.2
0x78547  ldarg.0
0x78548  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7854d  ldarg.0
0x7854e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x78553  ldarg.0
0x78554  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::locLabelHelper
0x78559  ldarg.0
0x7855a  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_optionSetsNameToIdMapping
0x7855f  ldarg.0
0x78560  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x78565  ldarg.0
0x78566  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7856b  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOptionSetsHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper locLabelHelper, class [mscorlib]System.Collections.Hashtable optionSetsNameToIdMapping, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent)
0x78570  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x78575  pop
0x78576  ldarg.0
0x78577  ldarg.2
0x78578  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntityHandlers(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x7857d  ldarg.0
0x7857e  ldc.i4.1
0x7857f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntitySubHandlers(valuetype SubHandlerType subHandlerType)
0x78584  ldarg.0
0x78585  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7858a  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportXml::IsRelationshipToBeImported()
0x7858f  brfalse.s loc_785CE
0x78591  ldarg.0
0x78592  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78597  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportEntityRelationshipHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument)
0x7859c  brfalse.s loc_785CE
0x7859e  ldarg.0
0x7859f  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x785a4  ldarg.0
0x785a5  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x785aa  ldarg.2
0x785ab  ldarg.0
0x785ac  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x785b1  ldarg.0
0x785b2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x785b7  ldarg.0
0x785b8  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x785bd  ldarg.0
0x785be  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::locLabelHelper
0x785c3  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityRelationshipHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper helper, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocLabelHelper labelHelper)
0x785c8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x785cd  pop
0x785ce  ldarg.0
0x785cf  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x785d4  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SystemSolutionUpdate()
0x785d9  brtrue.s loc_785F8
0x785db  ldarg.0
0x785dc  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x785e1  ldarg.0
0x785e2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x785e7  ldarg.0
0x785e8  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x785ed  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportFlushCacheHandler::.ctor(class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper helper, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x785f2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x785f7  pop
0x785f8  ldarg.0
0x785f9  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x785fe  ldarg.0
0x785ff  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78604  ldarg.2
0x78605  ldarg.0
0x78606  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_newEntities
0x7860b  ldarg.0
0x7860c  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x78611  ldarg.0
0x78612  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x78617  ldarg.0
0x78618  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7861d  ldarg.0
0x7861e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x78623  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [mscorlib]System.Collections.Generic.List`1<string> newEntities, bool isInternal, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x78628  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7862d  pop
0x7862e  ldarg.0
0x7862f  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x78634  ldarg.0
0x78635  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x7863a  ldarg.2
0x7863b  ldarg.0
0x7863c  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x78641  ldarg.0
0x78642  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x78647  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportStagingEndHandler::.ctor(class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer importTracer, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, bool isInternalSolution, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7864c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x78651  pop
0x78652  ldarg.0
0x78653  ldarg.2
0x78654  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeCalculatedFieldHandlers(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x78659  ldarg.0
0x7865a  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7865f  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportWebResourcesHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument)
0x78664  brfalse.s loc_7869B
0x78666  ldarg.0
0x78667  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x7866c  ldarg.0
0x7866d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78672  ldarg.0
0x78673  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x78678  ldarg.0
0x78679  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x7867e  ldarg.0
0x7867f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x78684  ldarg.0
0x78685  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7868a  ldarg.0
0x7868b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_importFileSet
0x78690  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportWebResourcesHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet filesToImport)
0x78695  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7869a  pop
0x7869b  ldarg.0
0x7869c  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x786a1  brtrue.s loc_786AB
0x786a3  ldarg.0
0x786a4  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsFirstPartySolution()
0x786a9  brfalse.s loc_786DA
0x786ab  ldarg.0
0x786ac  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x786b1  ldarg.0
0x786b2  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x786b7  ldarg.0
0x786b8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x786bd  ldarg.0
0x786be  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x786c3  ldarg.0
0x786c4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x786c9  ldarg.0
0x786ca  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_importFileSet
0x786cf  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportStoredProceduresHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet filesToImport)
0x786d4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x786d9  pop
0x786da  ldarg.0
0x786db  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x786e0  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlsHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument)
0x786e5  brfalse.s loc_78722
0x786e7  ldarg.0
0x786e8  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x786ed  ldarg.0
0x786ee  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x786f3  ldarg.0
0x786f4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x786f9  ldarg.0
0x786fa  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x786ff  ldarg.0
0x78700  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x78705  ldarg.0
0x78706  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7870b  ldarg.0
0x7870c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_importFileSet
0x78711  ldarg.0
0x78712  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileContents
0x78717  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlsHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet filesToImport, class [Microsoft.Crm]Microsoft.Crm.CrmUnzip customizationFileContents)
0x7871c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x78721  pop
0x78722  ldarg.0
0x78723  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78728  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument)
0x7872d  brfalse.s loc_78764
0x7872f  ldarg.0
0x78730  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x78735  ldarg.0
0x78736  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7873b  ldarg.0
0x7873c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x78741  ldarg.0
0x78742  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x78747  ldarg.0
0x78748  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importHelper
0x7874d  ldarg.0
0x7874e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x78753  ldarg.0
0x78754  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::entitiesWithRibbon
0x78759  call     class Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler::CreateRibbonsHandler(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> entitiesWithRibbon)
0x7875e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x78763  pop
0x78764  ldarg.0
0x78765  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7876a  ldstr    aApplicationfil// "ApplicationFiles"
0x7876f  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportApplicationFilesHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument, string collectionElementName)
0x78774  brfalse.s loc_78799
0x78776  ldarg.0
0x78777  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x7877c  ldarg.0
0x7877d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78782  ldarg.0
0x78783  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x78788  ldarg.0
0x78789  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::tracer
0x7878e  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportApplicationFilesHandler::.ctor(class [System.Xml]System.Xml.XmlDocument doc, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x78793  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x78798  pop
0x78799  ldarg.0
0x7879a  ldc.i4   0x200
0x7879f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntitySubHandlers(valuetype SubHandlerType subHandlerType)
0x787a4  ldarg.0
0x787a5  ldc.i4   0x80
0x787aa  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntitySubHandlers(valuetype SubHandlerType subHandlerType)
0x787af  ldarg.0
0x787b0  ldc.i4.s 0x1A
0x787b2  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntitySubHandlers(valuetype SubHandlerType subHandlerType)
0x787b7  ldarg.0
0x787b8  ldc.i4.s 0x40
0x787ba  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntitySubHandlers(valuetype SubHandlerType subHandlerType)
0x787bf  ldarg.0
0x787c0  ldc.i4   0x100
0x787c5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntitySubHandlers(valuetype SubHandlerType subHandlerType)
0x787ca  ldarg.0
0x787cb  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x787d0  brtrue.s loc_787DA
0x787d2  ldarg.0
0x787d3  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsFirstPartySolution()
0x787d8  brfalse.s loc_787E5
0x787da  ldarg.0
0x787db  ldc.i4   0x400
0x787e0  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeEntitySubHandlers(valuetype SubHandlerType subHandlerType)
0x787e5  ldarg.0
0x787e6  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x787eb  brtrue.s loc_78826
0x787ed  ldarg.0
0x787ee  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_Setup()
0x787f3  brtrue.s loc_78802
0x787f5  ldarg.0
0x787f6  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x787fb  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SystemSolutionUpdate()
0x78800  brfalse.s loc_78843
0x78802  ldarg.0
0x78803  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x78808  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x7880d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x78812  call     bool [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::IsOptInSolution(valuetype [mscorlib]System.Guid)
0x78817  brtrue.s loc_78843
0x78819  ldarg.0
0x7881a  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7881f  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportComplexControlHandler::HasNodesToBeImported(class [System.Xml]System.Xml.XmlDocument importDocument)
0x78824  brfalse.s loc_78843
0x78826  ldarg.0
0x78827  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::handlers
0x7882c  ldarg.0
0x7882d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x78832  ldarg.0
0x78833  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x78838  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportComplexControlHandler::.ctor(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7883d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
  ... truncated ...
```
