# Microsoft.Crm.ObjectModel.SystemFormService::Update_1

- ea: `0x108550`
- end: `0x1088d4`
- name: `Microsoft.Crm.ObjectModel.SystemFormService::Update_1`
- size: `900`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x108540`

## callees

- `0xfff50`
- `0x107e30`
- `0x108430`
- `0x108550`
- `0x1088e0`
- `0x1089c0`
- `0x1099f0`
- `0x109c20`
- `0x109ee0`
- `0x109f70`
- `0x10a770`
- `0x10aa70`
- `0x133490`
- `0x133940`

## string_xrefs

- `0x10874a`: `componentstate`
- `0x10880f`: `formxml`
- `0x108802`: `formjson`
- `0x108826`: `formjson`
- `0x108774`: `updateForCustomizableSystemForm`
- `0x108839`: `updateForCustomizableSystemForm`

## pseudocode

```c

```

## disassembly

```asm
0x108550  ldarg.1
0x108551  ldstr    aEntity_0// "entity"
0x108556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10855b  ldarg.2
0x10855c  ldstr    aContext// "context"
0x108561  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x108566  ldarg.0
0x108567  ldarg.1
0x108568  ldarg.2
0x108569  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.SystemFormService::GetPreImage(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10856e  stloc.0
0x10856f  ldloc.0
0x108570  ldstr    aType// "type"
0x108575  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10857a  unbox.any [mscorlib]System.Int32
0x10857f  brfalse.s loc_108596
0x108581  ldloc.0
0x108582  ldstr    aType// "type"
0x108587  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10858c  unbox.any [mscorlib]System.Int32
0x108591  ldc.i4.8
0x108592  ceq
0x108594  br.s     loc_108597
0x108596  ldc.i4.1
0x108597  stloc.1
0x108598  ldarg.1
0x108599  ldstr    aObjecttypecode// "objecttypecode"
0x10859e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1085a3  brtrue.s loc_1085BB
0x1085a5  ldarg.1
0x1085a6  ldstr    aObjecttypecode// "objecttypecode"
0x1085ab  ldloc.0
0x1085ac  ldstr    aObjecttypecode// "objecttypecode"
0x1085b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1085b6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1085bb  ldarg.1
0x1085bc  ldloc.0
0x1085bd  ldarg.2
0x1085be  ldarg.3
0x1085bf  newobj   instance void Microsoft.Crm.ObjectModel.FormValidationContext::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x1085c4  stloc.2
0x1085c5  ldarg.0
0x1085c6  ldloc.2
0x1085c7  call     instance void Microsoft.Crm.ObjectModel.SystemFormService::Validate(class Microsoft.Crm.ObjectModel.FormValidationContext validationContext)
0x1085cc  ldarg.2
0x1085cd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1085d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::StartTransaction()
0x1085d7  ldarg.0
0x1085d8  ldarg.1
0x1085d9  ldarg.2
0x1085da  call     instance void Microsoft.Crm.ObjectModel.SystemFormService::ExecutePreUpdateManagedPropertyHandler(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1085df  ldarg.1
0x1085e0  ldstr    aFormactivation// "formactivationstate"
0x1085e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1085ea  brfalse  loc_1086F6
0x1085ef  ldarg.1
0x1085f0  ldstr    aFormactivation// "formactivationstate"
0x1085f5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1085fa  unbox.any [mscorlib]System.Int32
0x1085ff  brtrue.s loc_108633
0x108601  ldloc.0
0x108602  ldstr    aType// "type"
0x108607  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10860c  unbox.any [mscorlib]System.Int32
0x108611  ldc.i4.2
0x108612  beq.s    loc_108633
0x108614  ldc.i4   0x8004F660
0x108619  ldc.i4.1
0x10861a  newarr   [mscorlib]System.Object
0x10861f  dup
0x108620  ldc.i4.0
0x108621  ldarg.1
0x108622  ldstr    aFormactivation// "formactivationstate"
0x108627  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10862c  stelem.ref
0x10862d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x108632  throw
0x108633  ldarg.1
0x108634  ldstr    aFormactivation// "formactivationstate"
0x108639  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10863e  unbox.any [mscorlib]System.Int32
0x108643  brtrue   loc_1086F6
0x108648  ldarg.0
0x108649  ldarg.1
0x10864a  ldstr    aObjecttypecode// "objecttypecode"
0x10864f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x108654  unbox.any [mscorlib]System.Int32
0x108659  ldc.i4.2
0x10865a  ldarg.1
0x10865b  ldstr    aFormid// "formid"
0x108660  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x108665  unbox.any [mscorlib]System.Guid
0x10866a  ldarg.2
0x10866b  call     instance bool Microsoft.Crm.ObjectModel.SystemFormService::HaveOtherActiveForm(int32 objectTypeCode, int32 formType, valuetype [mscorlib]System.Guid formToExclude, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x108670  brtrue   loc_1086F6
0x108675  ldarg.2
0x108676  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x10867b  brtrue.s loc_10868A
0x10867d  ldarg.2
0x10867e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x108683  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x108688  brfalse.s loc_1086E5
0x10868a  ldarg.1
0x10868b  ldstr    aFormactivation// "formactivationstate"
0x108690  ldc.i4.1
0x108691  box      [mscorlib]System.Int32
0x108696  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x10869b  ldarg.2
0x10869c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1086a1  ldc.i4.s 0x38
0x1086a3  ldstr    aSolutionOperat// "Solution Operation with formId: {0}, Ob"...
0x1086a8  ldc.i4.2
0x1086a9  newarr   [mscorlib]System.Object
0x1086ae  dup
0x1086af  ldc.i4.0
0x1086b0  ldarg.1
0x1086b1  ldstr    aFormid// "formid"
0x1086b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1086bb  unbox.any [mscorlib]System.Guid
0x1086c0  box      [mscorlib]System.Guid
0x1086c5  stelem.ref
0x1086c6  dup
0x1086c7  ldc.i4.1
0x1086c8  ldarg.1
0x1086c9  ldstr    aObjecttypecode// "objecttypecode"
0x1086ce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1086d3  unbox.any [mscorlib]System.Int32
0x1086d8  box      [mscorlib]System.Int32
0x1086dd  stelem.ref
0x1086de  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1086e3  br.s     loc_1086F6
0x1086e5  ldc.i4   0x8004F661
0x1086ea  ldc.i4.0
0x1086eb  newarr   [mscorlib]System.Object
0x1086f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1086f5  throw
0x1086f6  ldarg.1
0x1086f7  call     string Microsoft.Crm.ObjectModel.FormLabelHelper::GetEntityFormXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x1086fc  stloc.3
0x1086fd  ldarg.s  4
0x1086ff  brtrue   loc_1087B8
0x108704  ldloc.0
0x108705  ldarg.2
0x108706  call     void Microsoft.Crm.ObjectModel.SystemFormService::DeleteUnpublishedLabels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10870b  ldloc.3
0x10870c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x108711  brtrue   loc_1087B8
0x108716  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x10871b  pop
0x10871c  ldloc.3
0x10871d  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x108722  ldstr    aLabels_2// "//labels"
0x108727  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x10872c  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x108731  ldc.i4.0
0x108732  ble      loc_1087B8
0x108737  ldarg.2
0x108738  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoDisablePublishOnCreateModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10873d  stloc.s  5
0x10873f  ldarg.0
0x108740  ldloc.0
0x108741  ldarg.2
0x108742  call     instance string Microsoft.Crm.ObjectModel.SystemFormService::GetPreImageFormXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x108747  stloc.s  6
0x108749  ldloc.0
0x10874a  ldstr    aComponentstate_0// "componentstate"
0x10874f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x108754  unbox.any [mscorlib]System.Int32
0x108759  ldc.i4.2
0x10875a  ceq
0x10875c  stloc.s  7
0x10875e  ldloc.0
0x10875f  ldstr    aType// "type"
0x108764  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x108769  unbox.any [mscorlib]System.Int32
0x10876e  brtrue.s loc_108773
0x108770  ldc.i4.1
0x108771  stloc.s  7
0x108773  ldarg.2
0x108774  ldstr    aUpdateforcusto// "updateForCustomizableSystemForm"
0x108779  ldloc.1
0x10877a  box      [mscorlib]System.Boolean
0x10877f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x108784  stloc.s  8
0x108786  ldarg.1
0x108787  ldc.i4.0
0x108788  ldloc.s  6
0x10878a  ldloc.s  7
0x10878c  ldarg.2
0x10878d  ldloca.s 9
0x10878f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x108795  ldloc.s  9
0x108797  call     void Microsoft.Crm.ObjectModel.FormLabelHelper::ExtractAndSaveFormLabels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, bool isCreate, string oldEntityFormXml, bool extractUnchangedLabels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] valuetype [mscorlib]System.Nullable`1<int32> langCode)
0x10879c  leave.s  loc_1087AA
0x10879e  ldloc.s  8
0x1087a0  brfalse.s loc_1087A9
0x1087a2  ldloc.s  8
0x1087a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1087a9  endfinally
0x1087aa  leave.s  loc_1087B8
0x1087ac  ldloc.s  5
0x1087ae  brfalse.s loc_1087B7
0x1087b0  ldloc.s  5
0x1087b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1087b7  endfinally
0x1087b8  ldarg.1
0x1087b9  ldstr    aObjecttypecode// "objecttypecode"
0x1087be  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1087c3  brfalse.s loc_1087D1
0x1087c5  ldarg.1
0x1087c6  ldstr    aObjecttypecode// "objecttypecode"
0x1087cb  ldnull
0x1087cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1087d1  ldarg.1
0x1087d2  ldstr    aIsdefault// "isdefault"
0x1087d7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1087dc  brtrue.s loc_1087F7
0x1087de  ldarg.1
0x1087df  ldstr    aIsdefault// "isdefault"
0x1087e4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1087e9  unbox.any [mscorlib]System.Boolean
0x1087ee  brfalse.s loc_1087F7
0x1087f0  ldarg.0
0x1087f1  ldarg.2
0x1087f2  call     instance void Microsoft.Crm.ObjectModel.SystemFormService::ResetDefaultDashboard(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1087f7  ldarg.1
0x1087f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x1087fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x108802  ldstr    aFormjson// "formjson"
0x108807  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x10880c  brfalse.s loc_108838
0x10880e  ldarg.1
0x10880f  ldstr    aFormxml// "formxml"
0x108814  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x108819  castclass [mscorlib]System.String
0x10881e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x108823  brtrue.s loc_108838
0x108825  ldarg.1
0x108826  ldstr    aFormjson// "formjson"
0x10882b  ldarg.0
0x10882c  ldarg.1
0x10882d  ldarg.2
0x10882e  call     instance string Microsoft.Crm.ObjectModel.SystemFormService::GetFormJson(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x108833  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x108838  ldarg.2
0x108839  ldstr    aUpdateforcusto// "updateForCustomizableSystemForm"
0x10883e  ldloc.1
0x10883f  box      [mscorlib]System.Boolean
0x108844  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x108849  stloc.s  8
0x10884b  ldarg.0
0x10884c  ldarg.1
0x10884d  ldarg.2
0x10884e  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x108853  leave.s  loc_108861
0x108855  ldloc.s  8
0x108857  brfalse.s loc_108860
0x108859  ldloc.s  8
0x10885b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x108860  endfinally
0x108861  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x108866  ldarg.2
0x108867  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x10886c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x108871  ldarg.2
0x108872  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x108877  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_IsProtected()
0x10887c  stloc.s  4
0x10887e  ldarg.0
0x10887f  ldarg.1
0x108880  ldloc.s  4
0x108882  ldc.i4.0
0x108883  ldarg.2
0x108884  call     instance void Microsoft.Crm.ObjectModel.SystemFormService::UpdateRibbonCustomizations(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, bool isProtectedSolution, bool isCreateOperation, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x108889  ldarg.0
0x10888a  ldarg.1
0x10888b  ldloc.0
0x10888c  ldarg.2
0x10888d  call     instance void Microsoft.Crm.ObjectModel.SystemFormService::RemoveUnchangedMUI(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entityNew, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entityPre, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x108892  ldloc.3
0x108893  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x108898  brtrue.s loc_1088BD
0x10889a  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x10889f  pop
0x1088a0  ldloc.3
0x1088a1  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x1088a6  ldstr    aDisplayconditi_1// "//DisplayConditions"
0x1088ab  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1088b0  brfalse.s loc_1088BD
0x1088b2  ldarg.2
0x1088b3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1088b8  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataTimeStampUtility::TryRegisterEventForInsertMetadataTimestamp(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x1088bd  ldarg.2
0x1088be  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x1088c3  leave.s  loc_1088D3
0x1088c5  pop
0x1088c6  ldarg.2
0x1088c7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1088cc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::RollbackTransaction()
0x1088d1  rethrow
  ... truncated ...
```
