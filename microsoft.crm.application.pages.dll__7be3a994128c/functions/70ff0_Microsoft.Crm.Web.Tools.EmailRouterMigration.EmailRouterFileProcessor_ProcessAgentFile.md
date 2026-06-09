# Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::ProcessAgentFile

- ea: `0x70ff0`
- end: `0x711ea`
- name: `Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::ProcessAgentFile`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xdb070`

## callees

- `0x70870`
- `0x70ff0`
- `0x713b0`
- `0x71570`
- `0x71590`
- `0x71c40`
- `0x71e90`
- `0x10b250`

## string_xrefs

- `0x710ea`: `ProviderConfiguration`
- `0x71150`: `ProviderConfiguration`
- `0x710f7`: `ProviderConfiguration Node should be present within the configuration node`
- `0x71105`: `ProviderConfiguration Node should not be present within another providerConfiguration node`
- `0x7112e`: `Configuration`
- `0x7117a`: `Configuration`
- `0x711b2`: `Exception on reading the EmailAgent.xml file during migration process : {0}`
- `0x711cc`: `Microsoft.Crm.Tools.EmailAgent.xml`

## pseudocode

```c

```

## disassembly

```asm
0x70ff0  ldc.i4.0
0x70ff1  stloc.0
0x70ff2  ldc.i4.0
0x70ff3  stloc.1
0x70ff4  ldc.i4.1
0x70ff5  stloc.2
0x70ff6  ldc.i4.0
0x70ff7  stloc.3
0x70ff8  ldnull
0x70ff9  stloc.s  4
0x70ffb  ldnull
0x70ffc  stloc.s  5
0x70ffe  ldarg.1
0x70fff  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(class [mscorlib]System.IO.Stream)
0x71004  stloc.s  6
0x71006  br       loc_71188
0x7100b  ldloc.s  6
0x7100d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x71012  ldc.i4.1
0x71013  bne.un   loc_7113E
0x71018  ldloc.0
0x71019  ldloc.2
0x7101a  and
0x7101b  brfalse  loc_710E3
0x71020  ldloc.s  6
0x71022  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x71027  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7102c  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x71031  stloc.s  7
0x71033  ldnull
0x71034  stloc.s  8
0x71036  ldarg.0
0x71037  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ProcessProviderNode> Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::providerNodeHandler
0x7103c  ldloc.s  7
0x7103e  ldloca.s 8
0x71040  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ProcessProviderNode>::TryGetValue(var<u1>, !!T0)
0x71045  brfalse.s loc_7105C
0x71047  ldloc.s  8
0x71049  ldloc.s  5
0x7104b  ldloc.s  6
0x7104d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x71052  callvirt instance void ProcessProviderNode::Invoke(class Microsoft.Crm.Web.Tools.EmailRouterMigration.ProviderConfigurationData provider, string nodeData)
0x71057  br       loc_71188
0x7105c  ldloc.s  7
0x7105e  ldstr    aEmailaddress_0// "emailaddress"
0x71063  ldc.i4.5
0x71064  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x71069  brfalse.s loc_7108C
0x7106b  ldloc.s  6
0x7106d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x71072  stloc.s  9
0x71074  ldloc.s  5
0x71076  ldloc.s  9
0x71078  callvirt instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.ProviderConfigurationData::set_EmailAddress(string value)
0x7107d  ldarg.0
0x7107e  ldloc.s  9
0x71080  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::GetUserQueueIdsFromEmailAddress(string emailAddress)
0x71085  stloc.s  4
0x71087  br       loc_71188
0x7108c  ldloc.s  7
0x7108e  ldstr    aUserid_0// "userid"
0x71093  ldc.i4.5
0x71094  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x71099  brtrue.s loc_710AA
0x7109b  ldloc.s  7
0x7109d  ldstr    aQueueid// "queueid"
0x710a2  ldc.i4.5
0x710a3  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x710a8  brfalse.s loc_710BD
0x710aa  ldloc.s  4
0x710ac  ldloc.s  6
0x710ae  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x710b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x710b8  br       loc_71188
0x710bd  ldloc.s  7
0x710bf  ldstr    aCrmserverurl// "crmserverurl"
0x710c4  ldc.i4.5
0x710c5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x710ca  brfalse  loc_71188
0x710cf  ldc.i4.1
0x710d0  stloc.3
0x710d1  ldloc.s  6
0x710d3  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x710d8  call     bool Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::IsValidProviderForThisOrg(string url)
0x710dd  stloc.2
0x710de  br       loc_71188
0x710e3  ldloc.s  6
0x710e5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x710ea  ldstr    aProviderconfig// "ProviderConfiguration"
0x710ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x710f4  brfalse.s loc_71127
0x710f6  ldloc.1
0x710f7  ldstr    aProviderconfig_0// "ProviderConfiguration Node should be pr"...
0x710fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x71101  ldloc.0
0x71102  ldc.i4.0
0x71103  ceq
0x71105  ldstr    aProviderconfig_1// "ProviderConfiguration Node should not b"...
0x7110a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x7110f  ldc.i4.1
0x71110  stloc.0
0x71111  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x71116  stloc.s  4
0x71118  ldarg.0
0x71119  ldfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::encryptionKeyForEmailRouter
0x7111e  newobj   instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.ProviderConfigurationData::.ctor(class [mscorlib]System.Security.SecureString encryptionKey)
0x71123  stloc.s  5
0x71125  br.s     loc_71188
0x71127  ldloc.s  6
0x71129  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x7112e  ldstr    aConfiguration// "Configuration"
0x71133  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71138  brfalse.s loc_71188
0x7113a  ldc.i4.1
0x7113b  stloc.1
0x7113c  br.s     loc_71188
0x7113e  ldloc.s  6
0x71140  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x71145  ldc.i4.s 0xF
0x71147  bne.un.s loc_71188
0x71149  ldloc.s  6
0x7114b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x71150  ldstr    aProviderconfig// "ProviderConfiguration"
0x71155  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7115a  brfalse.s loc_71173
0x7115c  ldloc.3
0x7115d  ldloc.2
0x7115e  and
0x7115f  brfalse.s loc_7116B
0x71161  ldarg.0
0x71162  ldloc.s  5
0x71164  ldloc.s  4
0x71166  call     instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::PopulateUserToProviderMappingDataStructure(class Microsoft.Crm.Web.Tools.EmailRouterMigration.ProviderConfigurationData configurationData, class [mscorlib]System.Collections.Generic.List`1<string> userQueueIds)
0x7116b  ldc.i4.1
0x7116c  stloc.2
0x7116d  ldc.i4.0
0x7116e  stloc.3
0x7116f  ldc.i4.0
0x71170  stloc.0
0x71171  br.s     loc_71188
0x71173  ldloc.s  6
0x71175  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x7117a  ldstr    aConfiguration// "Configuration"
0x7117f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71184  brfalse.s loc_71188
0x71186  ldc.i4.0
0x71187  stloc.1
0x71188  ldloc.s  6
0x7118a  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x7118f  brtrue   loc_7100B
0x71194  leave.s  loc_711A2
0x71196  ldloc.s  6
0x71198  brfalse.s loc_711A1
0x7119a  ldloc.s  6
0x7119c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x711a1  endfinally
0x711a2  leave.s  loc_711E9
0x711a4  stloc.s  0xA
0x711a6  ldloc.s  0xA
0x711a8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x711ad  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x711b2  ldstr    aExceptionOnRea_1// "Exception on reading the EmailAgent.xml"...
0x711b7  ldc.i4.1
0x711b8  newarr   [mscorlib]System.Object
0x711bd  dup
0x711be  ldc.i4.0
0x711bf  ldloc.s  0xA
0x711c1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x711c6  stelem.ref
0x711c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x711cc  ldstr    aMicrosoftCrmTo_0// "Microsoft.Crm.Tools.EmailAgent.xml"
0x711d1  ldarg.0
0x711d2  call     instance int32 Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::get_CurrentRouterNumber()
0x711d7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EmailRouterMigration.EmailRouterMigrationUtility::ConstructErrorMessage(string, int32)
0x711dc  ldloc.s  0xA
0x711de  ldc.i4   0x8005F032
0x711e3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x711e8  throw
0x711e9  ret
```
