# Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::PopulateServiceAccountMailbox

- ea: `0x126010`
- end: `0x1261ff`
- name: `Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::PopulateServiceAccountMailbox`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x19b90`
- `0x126010`

## string_xrefs

- `0x126144`: `incomingpassword`
- `0x126118`: `incomingusername`
- `0x12612e`: `incomingusername`
- `0x1261ed`: `incomingemaildeliverymethod`
- `0x1260b1`: `enabledforincomingemail`
- `0x1261ba`: `testemailconfigurationscheduled`
- `0x12617d`: `postponetestemailconfigurationuntil`
- `0x12605f`: `isserviceaccount`
- `0x126021`: `EmailConnector.EmailServerProfile.ServiceAccountName`

## pseudocode

```c

```

## disassembly

```asm
0x126010  ldarg.2
0x126011  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x126016  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x12601b  stloc.0
0x12601c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x126021  ldstr    aEmailconnector// "EmailConnector.EmailServerProfile.Servi"...
0x126026  ldloc.0
0x126027  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x12602c  ldc.i4.1
0x12602d  newarr   [mscorlib]System.Object
0x126032  dup
0x126033  ldc.i4.0
0x126034  ldarg.1
0x126035  ldstr    aName// "name"
0x12603a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x12603f  stelem.ref
0x126040  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x126045  stloc.1
0x126046  ldarg.2
0x126047  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12604c  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Mailbox::.ctor(valuetype [mscorlib]System.Guid)
0x126051  stloc.2
0x126052  ldloc.2
0x126053  ldstr    aName// "name"
0x126058  ldloc.1
0x126059  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x12605e  ldloc.2
0x12605f  ldstr    aIsserviceaccou// "isserviceaccount"
0x126064  ldc.i4.1
0x126065  box      [mscorlib]System.Boolean
0x12606a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x12606f  ldloc.2
0x126070  ldstr    aEmailserverpro_1// "emailserverprofile"
0x126075  ldarg.1
0x126076  ldstr    aEmailserverpro_0// "emailserverprofileid"
0x12607b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x126080  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x126085  ldloc.2
0x126086  ldstr    aOrganizationid_1// "organizationid"
0x12608b  ldarg.2
0x12608c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x126091  box      [mscorlib]System.Guid
0x126096  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x12609b  ldloc.2
0x12609c  ldstr    aMailboxid// "mailboxid"
0x1260a1  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1260a6  box      [mscorlib]System.Guid
0x1260ab  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1260b0  ldloc.2
0x1260b1  ldstr    aEnabledforinco// "enabledforincomingemail"
0x1260b6  ldc.i4.1
0x1260b7  box      [mscorlib]System.Boolean
0x1260bc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1260c1  ldloc.2
0x1260c2  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x1260c7  ldc.i4.0
0x1260c8  box      [mscorlib]System.Boolean
0x1260cd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1260d2  ldloc.2
0x1260d3  ldstr    aOwnerid// "ownerid"
0x1260d8  ldarg.1
0x1260d9  ldstr    aOwnerid// "ownerid"
0x1260de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x1260e3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1260e8  ldloc.2
0x1260e9  ldstr    aOwningbusiness// "owningbusinessunit"
0x1260ee  ldarg.1
0x1260ef  ldstr    aOwningbusiness// "owningbusinessunit"
0x1260f4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x1260f9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1260fe  ldarg.1
0x1260ff  ldstr    aServertype// "servertype"
0x126104  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x126109  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType
0x12610e  ldc.i4.2
0x12610f  bne.un.s loc_126153
0x126111  ldloc.2
0x126112  ldstr    aEmailaddress// "emailaddress"
0x126117  ldarg.1
0x126118  ldstr    aIncominguserna// "incomingusername"
0x12611d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x126122  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x126127  ldloc.2
0x126128  ldstr    aUsername// "username"
0x12612d  ldarg.1
0x12612e  ldstr    aIncominguserna// "incomingusername"
0x126133  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x126138  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x12613d  ldloc.2
0x12613e  ldstr    aPassword// "password"
0x126143  ldarg.1
0x126144  ldstr    aIncomingpasswo// "incomingpassword"
0x126149  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x12614e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x126153  ldarg.1
0x126154  ldstr    aServertype// "servertype"
0x126159  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x12615e  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType
0x126163  ldc.i4.3
0x126164  bne.un.s loc_12617C
0x126166  ldloc.2
0x126167  ldstr    aEmailaddress// "emailaddress"
0x12616c  ldarg.1
0x12616d  ldstr    aOwneremailaddr// "owneremailaddress"
0x126172  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x126177  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x12617c  ldloc.2
0x12617d  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x126182  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::MaxValue
0x126187  ldc.i4.1
0x126188  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x12618d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x126192  ldloc.2
0x126193  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x126198  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::MaxValue
0x12619d  ldc.i4.1
0x12619e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x1261a3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1261a8  ldloc.2
0x1261a9  ldstr    aIsforwardmailb// "isforwardmailbox"
0x1261ae  ldc.i4.1
0x1261af  box      [mscorlib]System.Boolean
0x1261b4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1261b9  ldloc.2
0x1261ba  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x1261bf  ldc.i4.0
0x1261c0  box      [mscorlib]System.Boolean
0x1261c5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1261ca  ldloc.2
0x1261cb  ldstr    aActdeliverymet// "actdeliverymethod"
0x1261d0  ldc.i4.2
0x1261d1  box      [mscorlib]System.Int32
0x1261d6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1261db  ldloc.2
0x1261dc  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x1261e1  ldc.i4.0
0x1261e2  box      [mscorlib]System.Int32
0x1261e7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1261ec  ldloc.2
0x1261ed  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x1261f2  ldc.i4.0
0x1261f3  box      [mscorlib]System.Int32
0x1261f8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1261fd  ldloc.2
0x1261fe  ret
```
