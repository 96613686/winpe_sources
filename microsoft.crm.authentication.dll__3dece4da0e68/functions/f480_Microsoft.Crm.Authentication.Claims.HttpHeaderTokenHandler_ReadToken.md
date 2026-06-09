# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::ReadToken

- ea: `0xf480`
- end: `0xf5f2`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::ReadToken`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x7670`
- `0xa440`
- `0xc6a0`
- `0xf480`
- `0xf650`

## string_xrefs

- `0xf582`: `HttpHeaderTokenHander - Re-loading service configuratoin\n`

## pseudocode

```c

```

## disassembly

```asm
0xf480  ldarg.1
0xf481  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xf486  brtrue   loc_F5EE
0xf48b  ldarg.1
0xf48c  ldstr    asc_21BC0// "<"
0xf491  ldc.i4.5
0xf492  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xf497  brfalse.s loc_F515
0xf499  ldarg.1
0xf49a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xf49f  stloc.0
0xf4a0  ldloc.0
0xf4a1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xf4a6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0xf4ab  ldc.i4.s 0x11
0xf4ad  bne.un.s loc_F4BC
0xf4af  ldloc.0
0xf4b0  ldloc.0
0xf4b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xf4b6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xf4bb  pop
0xf4bc  ldloc.0
0xf4bd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xf4c2  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string)
0xf4c7  stloc.1
0xf4c8  ldarg.0
0xf4c9  call     instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::get_IdentityConfiguration()
0xf4ce  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xf4d3  ldstr    asc_1DBD8// ""
0xf4d8  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xf4dd  ldloc.1
0xf4de  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::CanReadToken(class [System.Xml]System.Xml.XmlReader)
0xf4e3  brfalse.s loc_F506
0xf4e5  ldarg.0
0xf4e6  call     instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::get_IdentityConfiguration()
0xf4eb  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xf4f0  ldstr    asc_1DBD8// ""
0xf4f5  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xf4fa  ldloc.1
0xf4fb  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::ReadToken(class [System.Xml]System.Xml.XmlReader)
0xf500  stloc.2
0xf501  leave    loc_F5F0
0xf506  leave    loc_F5EE
0xf50b  ldloc.1
0xf50c  brfalse.s loc_F514
0xf50e  ldloc.1
0xf50f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf514  endfinally
0xf515  ldarg.0
0xf516  call     instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::get_IdentityConfiguration()
0xf51b  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xf520  ldstr    asc_1DBD8// ""
0xf525  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xf52a  ldtoken  [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken
0xf52f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf534  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0xf539  isinst   Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandler
0xf53e  stloc.3
0xf53f  ldarg.0
0xf540  ldfld    bool Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_loadCrmServiceConfiguration
0xf545  brfalse  loc_F5E3
0xf54a  ldloc.3
0xf54b  brtrue   loc_F5E3
0xf550  call     void Microsoft.Crm.Authentication.Claims.ClaimsUtility::InitializeApplication()
0xf555  ldarg.0
0xf556  ldfld    object Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_objectLock
0xf55b  stloc.s  5
0xf55d  ldc.i4.0
0xf55e  stloc.s  6
0xf560  ldloc.s  5
0xf562  ldloca.s 6
0xf564  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xf569  ldarg.0
0xf56a  call     class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::GetIdentityConfiguration()
0xf56f  stfld    class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::_identityConfiguration
0xf574  leave.s  loc_F582
0xf576  ldloc.s  6
0xf578  brfalse.s loc_F581
0xf57a  ldloc.s  5
0xf57c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xf581  endfinally
0xf582  ldstr    aHttpheadertoke_7// "HttpHeaderTokenHander - Re-loading serv"...
0xf587  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xf58c  stloc.s  4
0xf58e  ldloc.s  4
0xf590  ldstr    aHost0// "Host: {0}\n"
0xf595  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xf59a  call     string [Microsoft.Crm.Core]Microsoft.Crm.AuthenticationContextExtensions::CurrentHost(class [System.Web]System.Web.HttpContext)
0xf59f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xf5a4  pop
0xf5a5  ldc.i4.8
0xf5a6  ldc.i4   0x4339
0xf5ab  conv.i8
0xf5ac  ldloc.s  4
0xf5ae  callvirt instance string [mscorlib]System.Object::ToString()
0xf5b3  ldnull
0xf5b4  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0xf5b9  ldarg.0
0xf5ba  call     instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::get_IdentityConfiguration()
0xf5bf  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlerCollectionManager()
0xf5c4  ldstr    asc_1DBD8// ""
0xf5c9  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager::get_Item(string)
0xf5ce  ldtoken  [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken
0xf5d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf5d8  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0xf5dd  isinst   Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandler
0xf5e2  stloc.3
0xf5e3  ldloc.3
0xf5e4  brfalse.s loc_F5EE
0xf5e6  ldloc.3
0xf5e7  ldarg.1
0xf5e8  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::ReadToken(string)
0xf5ed  ret
0xf5ee  ldnull
0xf5ef  ret
0xf5f0  ldloc.2
0xf5f1  ret
```
