# Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::ImportManagedAppModule

- ea: `0x28840`
- end: `0x28f30`
- name: `Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::ImportManagedAppModule`
- size: `1776`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x27fa0`

## callees

- `0x28700`
- `0x28840`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x2898c`: `componentstate`
- `0x2884d`: `AppModulesInstaller.ImportManagedAppModule(): START`
- `0x288a4`: `AppModulesInstaller.ImportManagedAppModule(): {0}`
- `0x288f9`: `AppModulesInstaller.ImportManagedAppModule(): AppMdoule validated.`
- `0x28934`: `AppModulesInstaller.ImportManagedAppModule(): Number of AppModules with [uniquename:{0}] is [{1}]`
- `0x289b0`: `AppModulesInstaller.ImportManagedAppModule(): UnPublished AppModules with [uniquename:{0}] exists : [{1}]`
- `0x28a9a`: `AppModulesInstaller.ImportManagedAppModule(): Cannot Import appmodule with clientType Outlook.`
- `0x28af4`: `AppModulesInstaller.ImportManagedAppModule(): [appModuleId:{0}]`
- `0x28b3b`: `AppModulesInstaller.ImportManagedAppModule(): [appModuleId:{0}] [appModuleStates:{1}]`
- `0x28b87`: `AppModulesInstaller.ImportManagedAppModule(): [appModuleId:{0}] [isExistingSolution:{1}]`
- `0x28c89`: `AppModulesInstaller.ImportManagedAppModule(): Generated descriptor for AppModule [appmoduleid:{0}]`
- `0x28e69`: `AppModulesInstaller.ImportManagedAppModule(): Generated descriptor for AppModule [appmoduleid:{0}]`
- `0x28cb4`: `Full app module xml is expected to create an app module.`
- `0x28cdf`: `AppModulesInstaller.ImportManagedAppModule(): AppModule imported with [appmoduleid:{0}]`
- `0x28d35`: `AppModulesInstaller.ImportManagedAppModule(): [lastManagedAppModuleDefinition==null:{0}]`
- `0x28dd8`: `AppModulesInstaller.ImportManagedAppModule(): [customizationDiff==null:{0}]`
- `0x28e15`: `AppModulesInstaller.ImportManagedAppModule(): Installed Customization for AppMdoule with [aoomoduleid:{0}]`
- `0x28f1d`: `AppModulesInstaller.ImportManagedAppModule(): END`

## pseudocode

```c

```

## disassembly

```asm
0x28840  ldarg.0
0x28841  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28846  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2884b  ldc.i4.s 0x47
0x2884d  ldstr    aAppmodulesinst_15// "AppModulesInstaller.ImportManagedAppMod"...
0x28852  ldc.i4.0
0x28853  newarr   [mscorlib]System.Object
0x28858  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2885d  ldarg.0
0x2885e  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleXmlParser Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModuleXmlParser
0x28863  ldarg.1
0x28864  ldarg.2
0x28865  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleXmlParser::GenerateAppModuleDefinition(class [System.Xml]System.Xml.XmlNode, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x2886a  stloc.0
0x2886b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28870  ldstr    aImportitemProc_0// "ImportItem: Processing app module with "...
0x28875  ldc.i4.1
0x28876  newarr   [mscorlib]System.Object
0x2887b  dup
0x2887c  ldc.i4.0
0x2887d  ldloc.0
0x2887e  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x28883  stelem.ref
0x28884  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28889  stloc.1
0x2888a  ldarg.0
0x2888b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_tracer
0x28890  ldloc.1
0x28891  ldc.i4.1
0x28892  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x28897  ldarg.0
0x28898  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x2889d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x288a2  ldc.i4.s 0x47
0x288a4  ldstr    aAppmodulesinst_16// "AppModulesInstaller.ImportManagedAppMod"...
0x288a9  ldc.i4.1
0x288aa  newarr   [mscorlib]System.Object
0x288af  dup
0x288b0  ldc.i4.0
0x288b1  ldloc.1
0x288b2  stelem.ref
0x288b3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x288b8  ldc.i4.s 0x50
0x288ba  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x288bf  ldarg.1
0x288c0  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x288c5  ldloc.0
0x288c6  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x288cb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x288d0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x288d5  ldarg.0
0x288d6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x288db  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x288e0  ldarg.0
0x288e1  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleValidator Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModuleValidator
0x288e6  ldloc.0
0x288e7  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleValidator::Validate(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition)
0x288ec  ldarg.0
0x288ed  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x288f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x288f7  ldc.i4.s 0x47
0x288f9  ldstr    aAppmodulesinst_17// "AppModulesInstaller.ImportManagedAppMod"...
0x288fe  ldc.i4.0
0x288ff  newarr   [mscorlib]System.Object
0x28904  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28909  ldarg.0
0x2890a  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x2890f  ldloc.0
0x28910  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::ConvertSchemaNameToGuids(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition)
0x28915  ldarg.0
0x28916  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x2891b  ldloc.0
0x2891c  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x28921  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::RetrieveUnpublishedAppModule(string)
0x28926  stloc.2
0x28927  ldarg.0
0x28928  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x2892d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28932  ldc.i4.s 0x47
0x28934  ldstr    aAppmodulesinst_18// "AppModulesInstaller.ImportManagedAppMod"...
0x28939  ldc.i4.2
0x2893a  newarr   [mscorlib]System.Object
0x2893f  dup
0x28940  ldc.i4.0
0x28941  ldloc.0
0x28942  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x28947  stelem.ref
0x28948  dup
0x28949  ldc.i4.1
0x2894a  ldloc.2
0x2894b  brtrue.s loc_28959
0x2894d  ldloca.s 0xD
0x2894f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x28955  ldloc.s  0xD
0x28957  br.s     loc_28964
0x28959  ldloc.2
0x2895a  call     instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2895f  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x28964  box      valuetype [mscorlib]System.Nullable`1<int32>
0x28969  stelem.ref
0x2896a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2896f  ldloc.2
0x28970  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x28975  ldc.i4.0
0x28976  cgt
0x28978  ldc.i4.0
0x28979  ceq
0x2897b  stloc.3
0x2897c  ldloc.2
0x2897d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x28982  ldc.i4.0
0x28983  ble.s    loc_289A0
0x28985  ldloc.2
0x28986  ldc.i4.0
0x28987  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x2898c  ldstr    aComponentstate_0// "componentstate"
0x28991  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x28996  unbox.any [mscorlib]System.Int32
0x2899b  ldc.i4.1
0x2899c  ceq
0x2899e  br.s     loc_289A1
0x289a0  ldc.i4.0
0x289a1  stloc.s  4
0x289a3  ldarg.0
0x289a4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x289a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x289ae  ldc.i4.s 0x47
0x289b0  ldstr    aAppmodulesinst_19// "AppModulesInstaller.ImportManagedAppMod"...
0x289b5  ldc.i4.2
0x289b6  newarr   [mscorlib]System.Object
0x289bb  dup
0x289bc  ldc.i4.0
0x289bd  ldloc.0
0x289be  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_UniqueName()
0x289c3  stelem.ref
0x289c4  dup
0x289c5  ldc.i4.1
0x289c6  ldloc.s  4
0x289c8  box      [mscorlib]System.Boolean
0x289cd  stelem.ref
0x289ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x289d3  ldc.i4.0
0x289d4  stloc.s  5
0x289d6  ldnull
0x289d7  stloc.s  6
0x289d9  ldnull
0x289da  stloc.s  7
0x289dc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x289e1  stloc.s  8
0x289e3  ldarg.0
0x289e4  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModuleService
0x289e9  ldarg.0
0x289ea  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x289ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService::getExistingOutlookAppModule(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x289f4  stloc.s  9
0x289f6  ldloc.3
0x289f7  brtrue.s loc_28A62
0x289f9  ldarg.0
0x289fa  ldloc.0
0x289fb  ldloc.2
0x289fc  ldc.i4.0
0x289fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x28a02  ldloc.s  9
0x28a04  call     instance void Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::ValidateOutlookAppModuleUpdate(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition appModuleToImport, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingAppModule, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection presentOutlookAppModules)
0x28a09  ldloc.s  4
0x28a0b  brtrue.s loc_28A2E
0x28a0d  ldloc.2
0x28a0e  ldc.i4.0
0x28a0f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x28a14  stloc.s  7
0x28a16  ldloc.s  7
0x28a18  ldstr    aAppmoduleid// "appmoduleid"
0x28a1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x28a22  unbox.any [mscorlib]System.Guid
0x28a27  stloc.s  8
0x28a29  br       loc_28AC2
0x28a2e  ldloc.2
0x28a2f  ldc.i4.0
0x28a30  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x28a35  stloc.s  6
0x28a37  ldloc.s  6
0x28a39  ldstr    aAppmoduleid// "appmoduleid"
0x28a3e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x28a43  unbox.any [mscorlib]System.Guid
0x28a48  stloc.s  8
0x28a4a  ldarg.0
0x28a4b  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x28a50  ldloc.s  8
0x28a52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::TryRetrieveAppModule(valuetype [mscorlib]System.Guid)
0x28a57  stloc.s  7
0x28a59  ldloc.s  7
0x28a5b  brtrue.s loc_28AC2
0x28a5d  ldc.i4.1
0x28a5e  stloc.s  5
0x28a60  br.s     loc_28AC2
0x28a62  ldloc.0
0x28a63  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_ClientType()
0x28a68  ldc.i4.8
0x28a69  bne.un.s loc_28AC2
0x28a6b  ldloc.s  9
0x28a6d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x28a72  ldc.i4.0
0x28a73  ble.s    loc_28AC2
0x28a75  ldc.i4   0x80050127
0x28a7a  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x28a7f  ldc.i4   0x80050127
0x28a84  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x28a89  stloc.s  0xE
0x28a8b  ldloc.s  0xE
0x28a8d  ldarg.0
0x28a8e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28a93  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28a98  ldc.i4.s 0x47
0x28a9a  ldstr    aAppmodulesinst_20// "AppModulesInstaller.ImportManagedAppMod"...
0x28a9f  ldc.i4.0
0x28aa0  newarr   [mscorlib]System.Object
0x28aa5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28aaa  ldarg.0
0x28aab  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_tracer
0x28ab0  ldloc.s  0xE
0x28ab2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x28ab7  ldloc.s  0xE
0x28ab9  ldc.i4.1
0x28aba  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x28abf  ldloc.s  0xE
0x28ac1  throw
0x28ac2  ldloc.0
0x28ac3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_WelcomePageId()
0x28ac8  pop
0x28ac9  ldloc.0
0x28aca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_WelcomePageId()
0x28acf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28ad4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28ad9  brtrue.s loc_28ADE
0x28adb  ldc.i4.1
0x28adc  br.s     loc_28ADF
0x28ade  ldc.i4.0
0x28adf  stloc.s  0xA
0x28ae1  ldnull
0x28ae2  stloc.s  0xB
0x28ae4  ldc.i4.0
0x28ae5  stloc.s  0xC
0x28ae7  ldarg.0
0x28ae8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28aed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28af2  ldc.i4.s 0x47
0x28af4  ldstr    aAppmodulesinst_21// "AppModulesInstaller.ImportManagedAppMod"...
0x28af9  ldc.i4.1
0x28afa  newarr   [mscorlib]System.Object
0x28aff  dup
0x28b00  ldc.i4.0
0x28b01  ldloc.s  8
0x28b03  box      [mscorlib]System.Guid
0x28b08  stelem.ref
0x28b09  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28b0e  ldloc.s  8
0x28b10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28b15  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28b1a  brfalse  loc_28CA6
0x28b1f  ldarg.0
0x28b20  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_appModulesUtility
0x28b25  ldloc.s  8
0x28b27  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::RetrieveAppModuleStates(valuetype [mscorlib]System.Guid)
0x28b2c  stloc.s  0xB
0x28b2e  ldarg.0
0x28b2f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28b34  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28b39  ldc.i4.s 0x47
0x28b3b  ldstr    aAppmodulesinst_22// "AppModulesInstaller.ImportManagedAppMod"...
0x28b40  ldc.i4.2
0x28b41  newarr   [mscorlib]System.Object
0x28b46  dup
0x28b47  ldc.i4.0
0x28b48  ldloc.s  8
0x28b4a  box      [mscorlib]System.Guid
0x28b4f  stelem.ref
0x28b50  dup
0x28b51  ldc.i4.1
0x28b52  ldloc.s  0xB
0x28b54  stelem.ref
0x28b55  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28b5a  ldloc.s  0xB
0x28b5c  brfalse  loc_28CA6
0x28b61  ldloc.s  0xB
0x28b63  ldarg.0
0x28b64  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28b69  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x28b6e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x28b73  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::IsExistingSolution(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, valuetype [mscorlib]System.Guid)
0x28b78  stloc.s  0xC
0x28b7a  ldarg.0
0x28b7b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::_context
0x28b80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x28b85  ldc.i4.s 0x47
0x28b87  ldstr    aAppmodulesinst_23// "AppModulesInstaller.ImportManagedAppMod"...
0x28b8c  ldc.i4.2
0x28b8d  newarr   [mscorlib]System.Object
0x28b92  dup
0x28b93  ldc.i4.0
0x28b94  ldloc.s  8
  ... truncated ...
```
