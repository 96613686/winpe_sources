# Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::ImportUnmanagedAppModule

- ea: `0x28040`
- end: `0x286ff`
- name: `Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::ImportUnmanagedAppModule`
- size: `1727`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x27fa0`

## callees

- `0x28040`
- `0x28700`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x28462`: `componentstate`
- `0x28479`: `componentstate`
- `0x284d3`: `componentstate`
- `0x2804d`: `AppModulesInstaller.ImportUnmanagedAppModule(): START`
- `0x28065`: `Unmanaged solution expects full app module xml.`
- `0x280b7`: `AppModulesInstaller.ImportUnmanagedAppModule(): {0}`
- `0x28155`: `AppModulesInstaller.ImportUnmanagedAppModule(): No Sitemap, Exception: {0}`
- `0x281c3`: `AppModulesInstaller.ImportUnmanagedAppModule(): Existing AppModules [count:{0}]`
- `0x28238`: `AppModulesInstaller.ImportUnmanagedAppModule(): AppModule with clientType OUTLOOK already exists.`
- `0x282b4`: `AppModulesInstaller.ImportUnmanagedAppModule(): AppModule with [appmoduleid:{0}] exists.`
- `0x2830e`: `AppModulesInstaller.ImportUnmanagedAppModule(): Active AppModule exists with [appmoduleid:{0}] [appmoduleidunique:{1}].`
- `0x2839e`: `AppModulesInstaller.ImportUnmanagedAppModule(): Published version didnt exists, Deleted AppModule with [appmoduleid:{0}] [appmoduleidunique:{1}].`
- `0x28431`: `AppModulesInstaller.ImportUnmanagedAppModule(): Updating existing AppModule entity.`
- `0x2844e`: `AppModulesInstaller.ImportUnmanagedAppModule(): Updating existing AppModule entity.`
- `0x284bf`: `AppModulesInstaller.ImportUnmanagedAppModule(): Updating existing AppModule entity.`
- `0x28502`: `AppModulesInstaller.ImportUnmanagedAppModule(): UnPublished AppModule with [UniqueName:{0}] Collection size : {1]`
- `0x28562`: `AppModulesInstaller.ImportUnmanagedAppModule(): Create AppModuleComponents for AppModule with [UniqueName:{0}] and [appmoduleid:{1}]`
- `0x28655`: `welcomepageid`
- `0x28668`: `welcomepageid`
- `0x286de`: `AppModulesInstaller.ImportUnmanagedAppModule(): END`

## pseudocode

```c

```

## disassembly

```asm
0x28040  ldarg.0
0x28041  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28046  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2804b  ldc.i4.s 0x47
0x2804d  ldstr    aAppmodulesinst_1// "AppModulesInstaller.ImportUnmanagedAppM"...
0x28052  ldc.i4.0
0x28053  newarr   [mscorlib]System.Object
0x28058  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2805d  ldarg.1
0x2805e  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::ImportingFullAppModule(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x28063  brtrue.s loc_28070
0x28065  ldstr    aUnmanagedSolut// "Unmanaged solution expects full app mod"...
0x2806a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x2806f  throw
0x28070  ldarg.0
0x28071  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleXmlParser Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModuleXmlParser
0x28076  ldarg.1
0x28077  ldarg.2
0x28078  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleXmlParser::GenerateAppModuleDefinition(class [System.Xml]System.Xml.XmlNode, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x2807d  stloc.0
0x2807e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28083  ldstr    aImportitemProc_0// "ImportItem: Processing app module with "...
0x28088  ldc.i4.1
0x28089  newarr   [mscorlib]System.Object
0x2808e  dup
0x2808f  ldc.i4.0
0x28090  ldloc.0
0x28091  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x28096  stelem.ref
0x28097  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2809c  stloc.1
0x2809d  ldarg.0
0x2809e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_tracer
0x280a3  ldloc.1
0x280a4  ldc.i4.1
0x280a5  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x280aa  ldarg.0
0x280ab  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x280b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x280b5  ldc.i4.s 0x47
0x280b7  ldstr    aAppmodulesinst_2// "AppModulesInstaller.ImportUnmanagedAppM"...
0x280bc  ldc.i4.1
0x280bd  newarr   [mscorlib]System.Object
0x280c2  dup
0x280c3  ldc.i4.0
0x280c4  ldloc.1
0x280c5  stelem.ref
0x280c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x280cb  ldc.i4.s 0x50
0x280cd  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x280d2  ldarg.1
0x280d3  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x280d8  ldloc.0
0x280d9  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x280de  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x280e3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x280e8  ldarg.0
0x280e9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x280ee  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x280f3  ldarg.0
0x280f4  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleValidator Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModuleValidator
0x280f9  ldloc.0
0x280fa  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleValidator::Validate(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition)
0x280ff  ldarg.0
0x28100  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x28105  ldloc.0
0x28106  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleComponentDefinition> [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_AppModuleComponents()
0x2810b  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::IsSiteMapPresent(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleComponentDefinition>)
0x28110  brtrue.s loc_28172
0x28112  ldstr    aAppModuleWithU// "App module with unique name {0} does no"...
0x28117  ldloc.0
0x28118  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x2811d  call     string [mscorlib]System.String::Format(string, object)
0x28122  stloc.s  7
0x28124  ldc.i4   0x8005011C
0x28129  ldc.i4.0
0x2812a  newarr   [mscorlib]System.Object
0x2812f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x28134  stloc.s  8
0x28136  ldarg.0
0x28137  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_tracer
0x2813c  ldloc.s  7
0x2813e  ldloc.s  8
0x28140  ldc.i4.1
0x28141  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x28146  ldloc.s  8
0x28148  ldarg.0
0x28149  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x2814e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28153  ldc.i4.s 0x47
0x28155  ldstr    aAppmodulesinst_3// "AppModulesInstaller.ImportUnmanagedAppM"...
0x2815a  ldc.i4.1
0x2815b  newarr   [mscorlib]System.Object
0x28160  dup
0x28161  ldc.i4.0
0x28162  ldloc.s  8
0x28164  stelem.ref
0x28165  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2816a  ldloc.s  7
0x2816c  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x28171  throw
0x28172  ldarg.0
0x28173  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28178  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2817d  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModule::.ctor(valuetype [mscorlib]System.Guid)
0x28182  stloc.2
0x28183  ldloc.0
0x28184  ldloc.2
0x28185  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::PopulateAppModuleEntity(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModule)
0x2818a  ldarg.0
0x2818b  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x28190  ldloc.0
0x28191  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x28196  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::RetrieveUnpublishedAppModule(string)
0x2819b  stloc.3
0x2819c  ldarg.0
0x2819d  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModuleService
0x281a2  ldarg.0
0x281a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x281a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService::getExistingOutlookAppModule(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x281ad  stloc.s  4
0x281af  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x281b4  stloc.s  5
0x281b6  ldarg.0
0x281b7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x281bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x281c1  ldc.i4.s 0x47
0x281c3  ldstr    aAppmodulesinst_4// "AppModulesInstaller.ImportUnmanagedAppM"...
0x281c8  ldc.i4.1
0x281c9  newarr   [mscorlib]System.Object
0x281ce  dup
0x281cf  ldc.i4.0
0x281d0  ldloc.3
0x281d1  brtrue.s loc_281DF
0x281d3  ldloca.s 9
0x281d5  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x281db  ldloc.s  9
0x281dd  br.s     loc_281EA
0x281df  ldloc.3
0x281e0  call     instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x281e5  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x281ea  box      valuetype [mscorlib]System.Nullable`1<int32>
0x281ef  stelem.ref
0x281f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x281f5  ldloc.3
0x281f6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x281fb  brtrue   loc_2828F
0x28200  ldloc.0
0x28201  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_ClientType()
0x28206  ldc.i4.8
0x28207  bne.un.s loc_28260
0x28209  ldloc.s  4
0x2820b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x28210  ldc.i4.0
0x28211  ble.s    loc_28260
0x28213  ldc.i4   0x80050127
0x28218  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x2821d  ldc.i4   0x80050127
0x28222  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x28227  stloc.s  0xA
0x28229  ldloc.s  0xA
0x2822b  ldarg.0
0x2822c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28231  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28236  ldc.i4.s 0x47
0x28238  ldstr    aAppmodulesinst_5// "AppModulesInstaller.ImportUnmanagedAppM"...
0x2823d  ldc.i4.0
0x2823e  newarr   [mscorlib]System.Object
0x28243  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28248  ldarg.0
0x28249  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_tracer
0x2824e  ldloc.s  0xA
0x28250  callvirt instance string [mscorlib]System.Exception::get_Message()
0x28255  ldloc.s  0xA
0x28257  ldc.i4.1
0x28258  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x2825d  ldloc.s  0xA
0x2825f  throw
0x28260  ldloc.2
0x28261  ldstr    aAppmoduleid// "appmoduleid"
0x28266  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2826b  dup
0x2826c  stloc.s  5
0x2826e  box      [mscorlib]System.Guid
0x28273  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x28278  ldarg.0
0x28279  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x2827e  ldloc.2
0x2827f  ldarg.0
0x28280  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28285  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::CreateAppModule(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2828a  br       loc_284E3
0x2828f  ldloc.3
0x28290  ldc.i4.0
0x28291  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x28296  ldstr    aAppmoduleid// "appmoduleid"
0x2829b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x282a0  unbox.any [mscorlib]System.Guid
0x282a5  stloc.s  5
0x282a7  ldarg.0
0x282a8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x282ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x282b2  ldc.i4.s 0x47
0x282b4  ldstr    aAppmodulesinst_6// "AppModulesInstaller.ImportUnmanagedAppM"...
0x282b9  ldc.i4.1
0x282ba  newarr   [mscorlib]System.Object
0x282bf  dup
0x282c0  ldc.i4.0
0x282c1  ldloc.s  5
0x282c3  box      [mscorlib]System.Guid
0x282c8  stelem.ref
0x282c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x282ce  ldarg.0
0x282cf  ldloc.0
0x282d0  ldloc.3
0x282d1  ldc.i4.0
0x282d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x282d7  ldloc.s  4
0x282d9  call     instance void Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::ValidateOutlookAppModuleUpdate(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition appModuleToImport, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingAppModule, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection presentOutlookAppModules)
0x282de  ldarg.0
0x282df  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x282e4  ldloc.3
0x282e5  ldc.i4.0
0x282e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x282eb  ldstr    aAppmoduleid// "appmoduleid"
0x282f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x282f5  unbox.any [mscorlib]System.Guid
0x282fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::TryRetrieveAppModule(valuetype [mscorlib]System.Guid)
0x282ff  stloc.s  0xB
0x28301  ldarg.0
0x28302  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28307  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2830c  ldc.i4.s 0x47
0x2830e  ldstr    aAppmodulesinst_7// "AppModulesInstaller.ImportUnmanagedAppM"...
0x28313  ldc.i4.2
0x28314  newarr   [mscorlib]System.Object
0x28319  dup
0x2831a  ldc.i4.0
0x2831b  ldloc.s  0xB
0x2831d  brtrue.s loc_28322
0x2831f  ldnull
0x28320  br.s     loc_2832E
0x28322  ldloc.s  0xB
0x28324  ldstr    aAppmoduleid// "appmoduleid"
0x28329  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x2832e  stelem.ref
0x2832f  dup
0x28330  ldc.i4.1
0x28331  ldloc.s  0xB
0x28333  brtrue.s loc_28338
0x28335  ldnull
0x28336  br.s     loc_28344
0x28338  ldloc.s  0xB
0x2833a  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x2833f  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x28344  stelem.ref
0x28345  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2834a  ldloc.s  0xB
0x2834c  brtrue   loc_28400
0x28351  ldloc.3
0x28352  ldc.i4.0
0x28353  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x28358  ldstr    aAppmoduleid// "appmoduleid"
0x2835d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x28362  unbox.any [mscorlib]System.Guid
0x28367  ldstr    aAppmodule// "AppModule"
0x2836c  ldarg.0
0x2836d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28372  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28377  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x2837c  stloc.s  0xC
0x2837e  ldarg.0
0x2837f  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModuleService
0x28384  ldloc.s  0xC
0x28386  ldarg.0
0x28387  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x2838c  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService::DeleteInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x28391  ldarg.0
0x28392  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28397  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2839c  ldc.i4.s 0x47
0x2839e  ldstr    aAppmodulesinst_8// "AppModulesInstaller.ImportUnmanagedAppM"...
0x283a3  ldc.i4.2
0x283a4  newarr   [mscorlib]System.Object
0x283a9  dup
0x283aa  ldc.i4.0
0x283ab  ldloc.s  0xB
0x283ad  brtrue.s loc_283B2
0x283af  ldnull
0x283b0  br.s     loc_283BE
0x283b2  ldloc.s  0xB
0x283b4  ldstr    aAppmoduleid// "appmoduleid"
0x283b9  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x283be  stelem.ref
0x283bf  dup
0x283c0  ldc.i4.1
0x283c1  ldloc.s  0xB
0x283c3  brtrue.s loc_283C8
0x283c5  ldnull
0x283c6  br.s     loc_283D4
  ... truncated ...
```
