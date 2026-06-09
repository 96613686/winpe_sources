# Microsoft.Crm.CrmLive.Provisioning.SyncCompanyAction::SyncObject

- ea: `0xedc0`
- end: `0xf0b8`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncCompanyAction::SyncObject`
- size: `760`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0xb540`
- `0xb600`
- `0xb660`
- `0xb6c0`
- `0xbc60`
- `0xedc0`
- `0xf0c0`
- `0xf0e0`
- `0xf2b0`
- `0x30cd0`
- `0x30cf0`
- `0x30d30`

## string_xrefs

- `0xf077`: `CrmScaleGroupProvisioningService`

## pseudocode

```c

```

## disassembly

```asm
0xedc0  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xedc5  stloc.0
0xedc6  ldloc.0
0xedc7  ldarg.1
0xedc8  stfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem <>c__DisplayClass0_0::item
0xedcd  ldloc.0
0xedce  ldloc.0
0xedcf  ldfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem <>c__DisplayClass0_0::item
0xedd4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0xedd9  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::organizationId
0xedde  newobj   instance void <>c__DisplayClass0_1::.ctor()
0xede3  stloc.1
0xede4  ldloc.1
0xede5  ldloc.0
0xede6  stfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xedeb  ldloc.1
0xedec  ldstr    aSyncdataexecut// "SyncDataExecutor"
0xedf1  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::.ctor(string)
0xedf6  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext <>c__DisplayClass0_1::context
0xedfb  newobj   instance void <>c__DisplayClass0_2::.ctor()
0xee00  stloc.2
0xee01  ldloc.2
0xee02  ldloc.1
0xee03  stfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xee08  ldloc.2
0xee09  ldarg.2
0xee0a  ldloc.2
0xee0b  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xee10  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xee15  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::organizationId
0xee1a  call     class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company Microsoft.Crm.CrmLive.Provisioning.SyncCompanyAction::GetCompany(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record, valuetype [mscorlib]System.Guid organizationId)
0xee1f  stfld    class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company <>c__DisplayClass0_2::company
0xee24  ldloc.2
0xee25  ldfld    class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company <>c__DisplayClass0_2::company
0xee2a  callvirt instance bool [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_Deleted()
0xee2f  stloc.3
0xee30  ldloc.2
0xee31  ldfld    class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company <>c__DisplayClass0_2::company
0xee36  callvirt instance bool [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_Deleted()
0xee3b  brtrue.s loc_EE87
0xee3d  ldloc.2
0xee3e  ldfld    class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company <>c__DisplayClass0_2::company
0xee43  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company::get_AssignedPlan()
0xee48  brfalse.s loc_EE5C
0xee4a  ldloc.2
0xee4b  ldfld    class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company <>c__DisplayClass0_2::company
0xee50  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company::get_AssignedPlan()
0xee55  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan::get_Value()
0xee5a  brtrue.s loc_EE61
0xee5c  leave    loc_F0B7
0xee61  ldloc.2
0xee62  ldfld    class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company <>c__DisplayClass0_2::company
0xee67  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company::get_AssignedPlan()
0xee6c  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan::get_Value()
0xee71  ldloc.2
0xee72  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xee77  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xee7c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::organizationId
0xee81  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncCompanyAction::ShouldOrgBeDeleted(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan[] assignedPlans, valuetype [mscorlib]System.Guid organizationId)
0xee86  stloc.3
0xee87  ldloc.2
0xee88  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xee8d  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xee92  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::organizationId
0xee97  ldloc.2
0xee98  ldfld    class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company <>c__DisplayClass0_2::company
0xee9d  ldloc.3
0xee9e  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.AssignedPlanStateData::.ctor(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company company, bool isDelete)
0xeea3  stloc.s  4
0xeea5  ldloc.s  4
0xeea7  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ICompanyHandler> Microsoft.Crm.CrmLive.Provisioning.SyncCompanyAction::BuildHandlers(class Microsoft.Crm.CrmLive.Provisioning.AssignedPlanStateData assignedPlanState)
0xeeac  stloc.s  5
0xeeae  ldloc.3
0xeeaf  brfalse.s loc_EEC9
0xeeb1  ldloc.s  5
0xeeb3  ldloc.2
0xeeb4  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xeeb9  ldftn    instance void <>c__DisplayClass0_1::<SyncObject>b__0(class Microsoft.Crm.CrmLive.Provisioning.ICompanyHandler handler)
0xeebf  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.CrmLive.Provisioning.ICompanyHandler>::.ctor(object, native int)
0xeec4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ICompanyHandler>::ForEach(class [mscorlib]System.Action`1<var<u1>>)
0xeec9  ldloc.2
0xeeca  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.CompanyHandlerContext::.ctor()
0xeecf  stfld    class Microsoft.Crm.CrmLive.Provisioning.CompanyHandlerContext <>c__DisplayClass0_2::handlerContext
0xeed4  ldloc.s  5
0xeed6  ldloc.2
0xeed7  ldftn    instance void <>c__DisplayClass0_2::<SyncObject>b__1(class Microsoft.Crm.CrmLive.Provisioning.ICompanyHandler handler)
0xeedd  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.CrmLive.Provisioning.ICompanyHandler>::.ctor(object, native int)
0xeee2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ICompanyHandler>::ForEach(class [mscorlib]System.Action`1<var<u1>>)
0xeee7  ldloc.3
0xeee8  brtrue.s loc_EF29
0xeeea  ldloc.s  4
0xeeec  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans Microsoft.Crm.CrmLive.Provisioning.AssignedPlanStateData::get_PreviousAssignedAndSubscribedPlan()
0xeef1  ldloc.s  4
0xeef3  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan> Microsoft.Crm.CrmLive.Provisioning.AssignedPlanStateData::get_NewPlansRaw()
0xeef8  call     T0x2B000056
0xeefd  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans::SetAssignedPlans(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan[])
0xef02  ldloc.2
0xef03  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xef08  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xef0d  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::organizationId
0xef12  ldloc.2
0xef13  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xef18  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext <>c__DisplayClass0_1::context
0xef1d  ldloc.s  4
0xef1f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans Microsoft.Crm.CrmLive.Provisioning.AssignedPlanStateData::get_PreviousAssignedAndSubscribedPlan()
0xef24  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CompanyState::SetPreviousAssignedAndSubscribedPlans(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans)
0xef29  ldloc.s  4
0xef2b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan> Microsoft.Crm.CrmLive.Provisioning.AssignedPlanStateData::get_ChangedPlansCollapsed()
0xef30  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan>::get_Count()
0xef35  ldc.i4.0
0xef36  ble      loc_F0A1
0xef3b  ldc.i4.0
0xef3c  stloc.s  6
0xef3e  ldc.i4.0
0xef3f  stloc.s  7
0xef41  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xef46  ldstr    aMsonlinestorag// "MSOnlineStorageCapability"
0xef4b  ldc.i4.0
0xef4c  callvirt T0x2B000011
0xef51  stloc.s  8
0xef53  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xef58  ldstr    aMsonlineinstan// "MSOnlineInstanceCapability"
0xef5d  ldc.i4.0
0xef5e  callvirt T0x2B000011
0xef63  stloc.s  9
0xef65  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xef6a  ldstr    aMsonlinetestin// "MSOnlineTestInstanceCapability"
0xef6f  ldc.i4.0
0xef70  callvirt T0x2B000011
0xef75  stloc.s  0xA
0xef77  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xef7c  stloc.s  0xB
0xef7e  ldloc.s  4
0xef80  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan> Microsoft.Crm.CrmLive.Provisioning.AssignedPlanStateData::get_ChangedPlansCollapsed()
0xef85  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan>::GetEnumerator()
0xef8a  stloc.s  0xC
0xef8c  br       loc_F01F
0xef91  ldloc.s  0xC
0xef93  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan>::get_Current()
0xef98  stloc.s  0xD
0xef9a  ldloc.s  0xD
0xef9c  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xefa1  callvirt instance class [System.Xml]System.Xml.XmlElement [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue::get_Capability()
0xefa6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xefab  ldstr    aPlan// "Plan"
0xefb0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xefb5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xefba  stloc.s  0xE
0xefbc  ldloc.s  0xE
0xefbe  ldloc.s  8
0xefc0  ldc.i4.5
0xefc1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xefc6  brtrue.s loc_F01F
0xefc8  ldloc.s  0xE
0xefca  ldloc.s  9
0xefcc  ldc.i4.5
0xefcd  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xefd2  brtrue.s loc_F01F
0xefd4  ldloc.s  0xE
0xefd6  ldloc.s  0xA
0xefd8  ldc.i4.5
0xefd9  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xefde  brtrue.s loc_F01F
0xefe0  ldloc.s  7
0xefe2  brfalse.s loc_EFEC
0xefe4  ldloc.s  0xB
0xefe6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xefeb  pop
0xefec  ldloc.s  0xB
0xefee  ldstr    aNoHandlersFoun// "No Handlers Found For {0} Capability"
0xeff3  ldloc.s  0xD
0xeff5  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xeffa  callvirt instance class [System.Xml]System.Xml.XmlElement [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue::get_Capability()
0xefff  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xf004  ldstr    aPlan// "Plan"
0xf009  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xf00e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xf013  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xf018  pop
0xf019  ldc.i4.1
0xf01a  stloc.s  6
0xf01c  ldc.i4.1
0xf01d  stloc.s  7
0xf01f  ldloc.s  0xC
0xf021  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf026  brtrue   loc_EF91
0xf02b  leave.s  loc_F039
0xf02d  ldloc.s  0xC
0xf02f  brfalse.s loc_F038
0xf031  ldloc.s  0xC
0xf033  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf038  endfinally
0xf039  ldloc.s  6
0xf03b  brfalse.s loc_F0A1
0xf03d  ldloc.s  0xB
0xf03f  callvirt instance string [mscorlib]System.Object::ToString()
0xf044  stloc.s  0xF
0xf046  ldnull
0xf047  ldloc.2
0xf048  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xf04d  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xf052  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::organizationId
0xf057  ldc.i4.s 0xA
0xf059  ldstr    a0// "{0}"
0xf05e  ldc.i4.1
0xf05f  newarr   [mscorlib]System.Object
0xf064  dup
0xf065  ldc.i4.0
0xf066  ldloc.s  0xF
0xf068  stelem.ref
0xf069  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf06e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::NewEventLog()
0xf073  stloc.s  0x10
0xf075  ldloc.s  0x10
0xf077  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0xf07c  ldc.i4.1
0xf07d  ldc.i4   0xC000460B
0xf082  conv.u8
0xf083  ldc.i4.1
0xf084  newarr   [mscorlib]System.Object
0xf089  dup
0xf08a  ldc.i4.0
0xf08b  ldloc.s  0xF
0xf08d  stelem.ref
0xf08e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xf093  leave.s  loc_F0B7
0xf095  ldloc.s  0x10
0xf097  brfalse.s loc_F0A0
0xf099  ldloc.s  0x10
0xf09b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf0a0  endfinally
0xf0a1  leave.s  loc_F0B7
0xf0a3  ldloc.1
0xf0a4  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext <>c__DisplayClass0_1::context
0xf0a9  brfalse.s loc_F0B6
0xf0ab  ldloc.1
0xf0ac  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext <>c__DisplayClass0_1::context
0xf0b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf0b6  endfinally
0xf0b7  ret
```
