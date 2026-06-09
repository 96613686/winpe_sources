# Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::execute

- ea: `0x205400`
- end: `0x20579d`
- name: `Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::execute`
- size: `925`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x6d5a0`
- `0x6d810`
- `0x6d8d0`
- `0x88510`
- `0x88530`
- `0x17c3c0`
- `0x17c910`
- `0x187bc0`
- `0x203ad0`
- `0x203b00`
- `0x203b50`
- `0x205400`

## string_xrefs

- `0x2055d2`: `DeleteDocument`
- `0x2056ab`: `DeleteDocument`
- `0x20573b`: `DeleteDocument`
- `0x205771`: `DeleteDocument`
- `0x205781`: `DeleteDocument`
- `0x2055dc`: `Cannot delete OneToc files`

## pseudocode

```c

```

## disassembly

```asm
0x205400  ldarg.0
0x205401  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x205406  ldstr    aContext// "context"
0x20540b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x205410  ldarg.0
0x205411  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::parentEntityReference
0x205416  ldstr    aParententityre// "parentEntityReference"
0x20541b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x205420  ldarg.0
0x205421  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::entities
0x205426  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x20542b  ldc.i4.0
0x20542c  cgt
0x20542e  ldstr    aEntitiesCollec// "entities collection is empty"
0x205433  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x205438  ldarg.0
0x205439  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::parentEntityReference
0x20543e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x205443  stloc.s  5
0x205445  ldloca.s 5
0x205447  constrained. [mscorlib]System.Guid
0x20544d  callvirt instance string [mscorlib]System.Object::ToString()
0x205452  ldloca.s 0
0x205454  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x205459  brtrue.s loc_205461
0x20545b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x205460  stloc.0
0x205461  ldloc.0
0x205462  ldstr    aRegardingobjec_0// "regardingobjectid"
0x205467  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20546c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x205471  stloc.1
0x205472  ldarg.0
0x205473  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::parentEntityReference
0x205478  ldarg.0
0x205479  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x20547e  call     int32 Microsoft.Crm.ObjectModel.SPUtility.SharePointSDKHelper::GetTypeCodeFromEntityReference(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference parentEntityReference, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x205483  stloc.2
0x205484  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x205489  stloc.3
0x20548a  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x20548f  stloc.s  4
0x205491  ldarg.0
0x205492  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::entities
0x205497  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x20549c  stloc.s  6
0x20549e  br       loc_2055E8
0x2054a3  ldloc.s  6
0x2054a5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2054aa  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2054af  stloc.s  7
0x2054b1  ldloc.s  7
0x2054b3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x2054b8  ldstr    aLocationid// "locationid"
0x2054bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x2054c2  brfalse  loc_2055E8
0x2054c7  ldloc.s  7
0x2054c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x2054ce  ldstr    aLocationid// "locationid"
0x2054d3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x2054d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x2054dd  callvirt instance string [mscorlib]System.Object::ToString()
0x2054e2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2054e7  brtrue   loc_2055E8
0x2054ec  ldloc.3
0x2054ed  ldloc.s  7
0x2054ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x2054f4  ldstr    aLocationid// "locationid"
0x2054f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x2054fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x205503  callvirt instance string [mscorlib]System.Object::ToString()
0x205508  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::ContainsKey(var<u1>)
0x20550d  brtrue.s loc_20554C
0x20550f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x205514  stloc.1
0x205515  ldloc.1
0x205516  ldloc.s  7
0x205518  ldarg.0
0x205519  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x20551e  call     string Microsoft.Crm.ObjectModel.SPUtility.SharePointSDKHelper::GetDocumentId(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x205523  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x205528  ldloc.3
0x205529  ldloc.s  7
0x20552b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x205530  ldstr    aLocationid// "locationid"
0x205535  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x20553a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x20553f  callvirt instance string [mscorlib]System.Object::ToString()
0x205544  ldloc.1
0x205545  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>, !!T0)
0x20554a  br.s     loc_205581
0x20554c  ldloc.3
0x20554d  ldloc.s  7
0x20554f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x205554  ldstr    aLocationid// "locationid"
0x205559  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x20555e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x205563  callvirt instance string [mscorlib]System.Object::ToString()
0x205568  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item(void)
0x20556d  stloc.1
0x20556e  ldloc.1
0x20556f  ldloc.s  7
0x205571  ldarg.0
0x205572  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x205577  call     string Microsoft.Crm.ObjectModel.SPUtility.SharePointSDKHelper::GetDocumentId(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20557c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x205581  ldloc.s  7
0x205583  ldstr    aFiletype// "filetype"
0x205588  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x20558d  brtrue.s loc_2055AD
0x20558f  ldloc.s  7
0x205591  ldstr    aFiletype// "filetype"
0x205596  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x20559b  callvirt instance string [mscorlib]System.Object::ToString()
0x2055a0  ldstr    aOnetoc2_0// "onetoc2"
0x2055a5  ldc.i4.3
0x2055a6  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2055ab  brfalse.s loc_2055CB
0x2055ad  ldloc.s  7
0x2055af  ldstr    aFiletype// "filetype"
0x2055b4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2055b9  callvirt instance string [mscorlib]System.Object::ToString()
0x2055be  ldstr    aOnetoc// "onetoc"
0x2055c3  ldc.i4.3
0x2055c4  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2055c9  brtrue.s loc_2055E8
0x2055cb  ldc.i4.0
0x2055cc  ldarg.0
0x2055cd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x2055d2  ldstr    aDeletedocument// "DeleteDocument"
0x2055d7  ldc.i4   0x800608B7
0x2055dc  ldstr    aCannotDeleteOn// "Cannot delete OneToc files"
0x2055e1  ldnull
0x2055e2  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x2055e7  throw
0x2055e8  ldloc.s  6
0x2055ea  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2055ef  brtrue   loc_2054A3
0x2055f4  leave.s  loc_20560B
0x2055f6  ldloc.s  6
0x2055f8  isinst   [mscorlib]System.IDisposable
0x2055fd  stloc.s  8
0x2055ff  ldloc.s  8
0x205601  brfalse.s loc_20560A
0x205603  ldloc.s  8
0x205605  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20560a  endfinally
0x20560b  nop
0x20560c  ldloc.3
0x20560d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Keys()
0x205612  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [mscorlib]System.Collections.Generic.List`1<string>>::GetEnumerator()
0x205617  stloc.s  9
0x205619  br       loc_2056EB
0x20561e  ldloca.s 9
0x205620  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Current()
0x205625  stloc.s  0xA
0x205627  ldloc.3
0x205628  ldloc.s  0xA
0x20562a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item(void)
0x20562f  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x205634  stloc.s  0xB
0x205636  ldloc.s  0xA
0x205638  ldloca.s 0xC
0x20563a  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x20563f  brtrue.s loc_205659
0x205641  ldc.i4   0x80060734
0x205646  ldstr    aCanTMapDocumen// "Can't map documents to their location."
0x20564b  ldc.i4.5
0x20564c  ldarg.0
0x20564d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x205652  ldc.i4.0
0x205653  ldnull
0x205654  call     void Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException(int32 serverErrorCode, string message, valuetype Microsoft.Crm.ObjectModel.ErrorSource errorSource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ErrorTelemetryEventType errorEventType, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x205659  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x20565e  pop
0x20565f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x205664  stloc.s  0xD
0x205666  ldloc.s  0xD
0x205668  ldstr    aRegardingobjid_0// "RegardingObjId"
0x20566d  ldloc.0
0x20566e  box      [mscorlib]System.Guid
0x205673  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x205678  ldloc.s  0xD
0x20567a  ldstr    aRegardingobjty_0// "RegardingObjType"
0x20567f  ldloc.2
0x205680  box      [mscorlib]System.Int32
0x205685  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x20568a  ldloc.s  0xD
0x20568c  ldstr    aLocationid_0// "LocationId"
0x205691  ldloc.s  0xC
0x205693  box      [mscorlib]System.Guid
0x205698  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x20569d  ldloc.s  0xD
0x20569f  ldstr    aDocumentids// "DocumentIds"
0x2056a4  ldloc.s  0xB
0x2056a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2056ab  ldstr    aDeletedocument// "DeleteDocument"
0x2056b0  ldarg.0
0x2056b1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x2056b6  ldloc.s  0xD
0x2056b8  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogInformation(string EventName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> EventParams)
0x2056bd  newobj   instance void Microsoft.Crm.ObjectModel.SharePointDataProcessorFactory::.ctor()
0x2056c2  ldc.i4.0
0x2056c3  call     instance class Microsoft.Crm.ObjectModel.SharePointDataProcessor Microsoft.Crm.ObjectModel.SharePointDataProcessorFactory::GetDataProcessor(valuetype Microsoft.Crm.ObjectModel.DataProcessorType type)
0x2056c8  stloc.s  0xE
0x2056ca  ldloc.s  0xE
0x2056cc  ldloc.s  0xB
0x2056ce  ldloc.0
0x2056cf  ldloc.2
0x2056d0  ldarg.0
0x2056d1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x2056d6  ldloc.s  0xC
0x2056d8  callvirt instance void Microsoft.Crm.ObjectModel.SharePointDataProcessor::DeleteSharePointDocument(string[] documentIds, valuetype [mscorlib]System.Guid regardingOId, int32 regardingOType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid locationId)
0x2056dd  leave.s  loc_2056EB
0x2056df  ldloc.s  0xE
0x2056e1  brfalse.s loc_2056EA
0x2056e3  ldloc.s  0xE
0x2056e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2056ea  endfinally
0x2056eb  ldloca.s 9
0x2056ed  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<string>>::MoveNext()
0x2056f2  brtrue   loc_20561E
0x2056f7  leave.s  loc_205707
0x2056f9  ldloca.s 9
0x2056fb  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<string>>
0x205701  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x205706  endfinally
0x205707  leave.s  loc_205764
0x205709  stloc.s  0xF
0x20570b  ldloc.s  0xF
0x20570d  ldarg.0
0x20570e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x205713  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x205718  ldc.i4.s 0x11
0x20571a  ldstr    aExceptionOccur_42// "Exception occured while Deleting ShareP"...
0x20571f  ldc.i4.1
0x205720  newarr   [mscorlib]System.Object
0x205725  dup
0x205726  ldc.i4.0
0x205727  ldloc.s  0xF
0x205729  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x20572e  stelem.ref
0x20572f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x205734  ldc.i4.0
0x205735  ldarg.0
0x205736  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x20573b  ldstr    aDeletedocument// "DeleteDocument"
0x205740  ldloc.s  0xF
0x205742  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x205747  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x20574c  ldstr    aExceptionOccur_42// "Exception occured while Deleting ShareP"...
0x205751  ldloc.s  0xF
0x205753  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x205758  call     string [mscorlib]System.String::Format(string, object)
0x20575d  ldnull
0x20575e  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x205763  throw
0x205764  ldloc.s  4
0x205766  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x20576b  ldarg.0
0x20576c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x205771  ldstr    aDeletedocument// "DeleteDocument"
0x205776  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogSharePointCommandInfo(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string commandName)
0x20577b  ldarg.0
0x20577c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SPCommands.DeleteDocument::context
0x205781  ldstr    aDeletedocument// "DeleteDocument"
0x205786  ldstr    aTotaltimetaken// "TotalTimeTaken"
0x20578b  ldloc.s  4
0x20578d  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x205792  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogTimeTakenInformation(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string CallingMethod, string EventName, int64 TimeTaken)
0x205797  call     class Microsoft.Crm.ObjectModel.SPUtility.SPVoid Microsoft.Crm.ObjectModel.SPUtility.SPVoid::get_empty()
0x20579c  ret
```
