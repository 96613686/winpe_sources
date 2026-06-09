# Microsoft.Crm.ObjectModel.AppModuleService::populateDescriptorAppInfo

- ea: `0x900e0`
- end: `0x9040b`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::populateDescriptorAppInfo`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8ff50`

## callees

- `0x900e0`
- `0x90410`

## string_xrefs

- `0x902f6`: `welcomepageid`
- `0x9030b`: `welcomepageid`
- `0x90388`: `welcomepageid`
- `0x903bd`: `welcomepageid`
- `0x900ef`: `AppModuleService.populateDescriptorAppInfo(): appModule is null : {0}`
- `0x90114`: `AppModuleService.populateDescriptorAppInfo(): appModuleDescriptor is null : {0}`
- `0x90139`: `AppModuleService.populateDescriptorAppInfo(): [appComponentState:{0}]`
- `0x90360`: `AppModuleService.populateDescriptorAppInfo(): [{0}:{1}]`
- `0x903b0`: `AppModuleService.populateDescriptorAppInfo(): [{0}:{1}]`
- `0x903e3`: `AppModuleService.populateDescriptorAppInfo(): Error While populating descriptor for appModule with [appModuleId:{0}], exception {1}`

## pseudocode

```c

```

## disassembly

```asm
0x900e0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x900e5  stloc.0
0x900e6  ldarg.s  4
0x900e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x900ed  ldc.i4.s 0x47
0x900ef  ldstr    aAppmoduleservi_15// "AppModuleService.populateDescriptorAppI"...
0x900f4  ldc.i4.1
0x900f5  newarr   [mscorlib]System.Object
0x900fa  dup
0x900fb  ldc.i4.0
0x900fc  ldarg.1
0x900fd  ldnull
0x900fe  ceq
0x90100  box      [mscorlib]System.Boolean
0x90105  stelem.ref
0x90106  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9010b  ldarg.s  4
0x9010d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x90112  ldc.i4.s 0x47
0x90114  ldstr    aAppmoduleservi_16// "AppModuleService.populateDescriptorAppI"...
0x90119  ldc.i4.1
0x9011a  newarr   [mscorlib]System.Object
0x9011f  dup
0x90120  ldc.i4.0
0x90121  ldarg.2
0x90122  ldnull
0x90123  ceq
0x90125  box      [mscorlib]System.Boolean
0x9012a  stelem.ref
0x9012b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90130  ldarg.s  4
0x90132  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x90137  ldc.i4.s 0x47
0x90139  ldstr    aAppmoduleservi_17// "AppModuleService.populateDescriptorAppI"...
0x9013e  ldc.i4.1
0x9013f  newarr   [mscorlib]System.Object
0x90144  dup
0x90145  ldc.i4.0
0x90146  ldarg.3
0x90147  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x9014c  stelem.ref
0x9014d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90152  ldarg.2
0x90153  brtrue.s loc_9015C
0x90155  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor::.ctor()
0x9015a  starg.s  2
0x9015c  ldarg.2
0x9015d  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor::get_appInfo()
0x90162  stloc.1
0x90163  ldarg.1
0x90164  ldstr    aAppmoduleid// "appmoduleid"
0x90169  ldloca.s 0
0x9016b  callvirt T0x2B0000EF
0x90170  pop
0x90171  ldloc.1
0x90172  ldarg.1
0x90173  ldstr    aAppmoduleid// "appmoduleid"
0x90178  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9017d  brtrue.s loc_90187
0x9017f  ldloc.1
0x90180  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_AppId()
0x90185  br.s     loc_90197
0x90187  ldarg.1
0x90188  ldstr    aAppmoduleid// "appmoduleid"
0x9018d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90192  callvirt instance string [mscorlib]System.Object::ToString()
0x90197  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_AppId(string)
0x9019c  ldloc.1
0x9019d  ldarg.1
0x9019e  ldstr    aName// "name"
0x901a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x901a8  brtrue.s loc_901B2
0x901aa  ldloc.1
0x901ab  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_Title()
0x901b0  br.s     loc_901C2
0x901b2  ldarg.1
0x901b3  ldstr    aName// "name"
0x901b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x901bd  callvirt instance string [mscorlib]System.Object::ToString()
0x901c2  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_Title(string)
0x901c7  ldloc.1
0x901c8  ldarg.1
0x901c9  ldstr    aUniquename// "uniquename"
0x901ce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x901d3  brtrue.s loc_901DD
0x901d5  ldloc.1
0x901d6  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_UniqueName()
0x901db  br.s     loc_901ED
0x901dd  ldarg.1
0x901de  ldstr    aUniquename// "uniquename"
0x901e3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x901e8  callvirt instance string [mscorlib]System.Object::ToString()
0x901ed  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_UniqueName(string)
0x901f2  ldloc.1
0x901f3  ldarg.1
0x901f4  ldstr    aUrl// "url"
0x901f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x901fe  brtrue.s loc_90208
0x90200  ldloc.1
0x90201  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_AppUrl()
0x90206  br.s     loc_90218
0x90208  ldarg.1
0x90209  ldstr    aUrl// "url"
0x9020e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90213  callvirt instance string [mscorlib]System.Object::ToString()
0x90218  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_AppUrl(string)
0x9021d  ldloc.1
0x9021e  ldarg.1
0x9021f  ldstr    aClienttype// "clienttype"
0x90224  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90229  brtrue.s loc_90233
0x9022b  ldloc.1
0x9022c  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_ClientType()
0x90231  br.s     loc_90243
0x90233  ldarg.1
0x90234  ldstr    aClienttype// "clienttype"
0x90239  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9023e  unbox.any [mscorlib]System.Int32
0x90243  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_ClientType(int32)
0x90248  ldloc.1
0x90249  ldarg.1
0x9024a  ldstr    aDescription// "description"
0x9024f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90254  brtrue.s loc_9025E
0x90256  ldloc.1
0x90257  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_Description()
0x9025c  br.s     loc_9026E
0x9025e  ldarg.1
0x9025f  ldstr    aDescription// "description"
0x90264  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90269  callvirt instance string [mscorlib]System.Object::ToString()
0x9026e  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_Description(string)
0x90273  ldloc.1
0x90274  ldarg.1
0x90275  ldstr    aSolutionid// "solutionid"
0x9027a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9027f  brtrue.s loc_90289
0x90281  ldloc.1
0x90282  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_SolutionId()
0x90287  br.s     loc_90299
0x90289  ldarg.1
0x9028a  ldstr    aSolutionid// "solutionid"
0x9028f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90294  callvirt instance string [mscorlib]System.Object::ToString()
0x90299  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_SolutionId(string)
0x9029e  ldloc.1
0x9029f  ldarg.1
0x902a0  ldstr    aVersionnumber// "versionnumber"
0x902a5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x902aa  brtrue.s loc_902B4
0x902ac  ldloc.1
0x902ad  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_VersionNumber()
0x902b2  br.s     loc_902C4
0x902b4  ldarg.1
0x902b5  ldstr    aVersionnumber// "versionnumber"
0x902ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x902bf  callvirt instance string [mscorlib]System.Object::ToString()
0x902c4  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_VersionNumber(string)
0x902c9  ldloc.1
0x902ca  ldarg.1
0x902cb  ldstr    aWebresourceid// "webresourceid"
0x902d0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x902d5  brtrue.s loc_902DF
0x902d7  ldloc.1
0x902d8  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_webResourceId()
0x902dd  br.s     loc_902EF
0x902df  ldarg.1
0x902e0  ldstr    aWebresourceid// "webresourceid"
0x902e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x902ea  callvirt instance string [mscorlib]System.Object::ToString()
0x902ef  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_webResourceId(string)
0x902f4  ldloc.1
0x902f5  ldarg.1
0x902f6  ldstr    aWelcomepageid// "welcomepageid"
0x902fb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90300  brtrue.s loc_9030A
0x90302  ldloc.1
0x90303  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::get_welcomePageId()
0x90308  br.s     loc_9031A
0x9030a  ldarg.1
0x9030b  ldstr    aWelcomepageid// "welcomepageid"
0x90310  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x90315  callvirt instance string [mscorlib]System.Object::ToString()
0x9031a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_welcomePageId(string)
0x9031f  ldloc.1
0x90320  ldarg.3
0x90321  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_Status(int32)
0x90326  ldloc.1
0x90327  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppComponentInfo>::.ctor()
0x9032c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInformation::set_Components(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppComponentInfo>)
0x90331  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x90336  stloc.2
0x90337  ldarg.1
0x90338  ldstr    aWebresourceid// "webresourceid"
0x9033d  ldloca.s 2
0x9033f  callvirt T0x2B0000EF
0x90344  brfalse.s loc_90357
0x90346  ldarg.2
0x90347  ldarg.0
0x90348  ldloc.2
0x90349  ldarg.s  4
0x9034b  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation Microsoft.Crm.ObjectModel.AppModuleService::getWebResourceInformation(valuetype [mscorlib]System.Guid webresourceId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x90350  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor::set_webResourceInfo(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation)
0x90355  br.s     loc_90381
0x90357  ldarg.s  4
0x90359  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9035e  ldc.i4.s 0x47
0x90360  ldstr    aAppmoduleservi_18// "AppModuleService.populateDescriptorAppI"...
0x90365  ldc.i4.2
0x90366  newarr   [mscorlib]System.Object
0x9036b  dup
0x9036c  ldc.i4.0
0x9036d  ldstr    aWebresourceid// "webresourceid"
0x90372  stelem.ref
0x90373  dup
0x90374  ldc.i4.1
0x90375  ldloc.2
0x90376  box      [mscorlib]System.Guid
0x9037b  stelem.ref
0x9037c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90381  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x90386  stloc.3
0x90387  ldarg.1
0x90388  ldstr    aWelcomepageid// "welcomepageid"
0x9038d  ldloca.s 3
0x9038f  callvirt T0x2B0000EF
0x90394  brfalse.s loc_903A7
0x90396  ldarg.2
0x90397  ldarg.0
0x90398  ldloc.3
0x90399  ldarg.s  4
0x9039b  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation Microsoft.Crm.ObjectModel.AppModuleService::getWebResourceInformation(valuetype [mscorlib]System.Guid webresourceId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x903a0  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor::set_welcomePageInfo(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation)
0x903a5  br.s     loc_903D1
0x903a7  ldarg.s  4
0x903a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x903ae  ldc.i4.s 0x47
0x903b0  ldstr    aAppmoduleservi_18// "AppModuleService.populateDescriptorAppI"...
0x903b5  ldc.i4.2
0x903b6  newarr   [mscorlib]System.Object
0x903bb  dup
0x903bc  ldc.i4.0
0x903bd  ldstr    aWelcomepageid// "welcomepageid"
0x903c2  stelem.ref
0x903c3  dup
0x903c4  ldc.i4.1
0x903c5  ldloc.3
0x903c6  box      [mscorlib]System.Guid
0x903cb  stelem.ref
0x903cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x903d1  ldarg.2
0x903d2  stloc.s  4
0x903d4  leave.s  loc_90408
0x903d6  stloc.s  5
0x903d8  ldloc.s  5
0x903da  ldarg.s  4
0x903dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x903e1  ldc.i4.s 0x47
0x903e3  ldstr    aAppmoduleservi_19// "AppModuleService.populateDescriptorAppI"...
0x903e8  ldc.i4.2
0x903e9  newarr   [mscorlib]System.Object
0x903ee  dup
0x903ef  ldc.i4.0
0x903f0  ldloc.0
0x903f1  box      [mscorlib]System.Guid
0x903f6  stelem.ref
0x903f7  dup
0x903f8  ldc.i4.1
0x903f9  ldloc.s  5
0x903fb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x90400  stelem.ref
0x90401  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90406  rethrow
0x90408  ldloc.s  4
0x9040a  ret
```
