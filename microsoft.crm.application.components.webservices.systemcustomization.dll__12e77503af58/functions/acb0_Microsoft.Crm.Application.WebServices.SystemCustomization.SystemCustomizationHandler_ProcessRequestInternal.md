# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::ProcessRequestInternal

- ea: `0xacb0`
- end: `0xad74`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::ProcessRequestInternal`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0xacb0`
- `0xad80`
- `0xad90`
- `0xada0`
- `0xadc0`
- `0xae00`
- `0xae30`

## string_xrefs

- `0xad0a`: `CreateEntity`
- `0xad2f`: `UpdateEntity`

## pseudocode

```c

```

## disassembly

```asm
0xacb0  ldsfld   string [mscorlib]System.String::Empty
0xacb5  stloc.0
0xacb6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::.ctor()
0xacbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::ValidateToken()
0xacc0  ldarg.1
0xacc1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xacc6  ldstr    aOperation// "operation"
0xaccb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xacd0  stloc.1
0xacd1  ldloc.1
0xacd2  ldstr    aPublishallcust// "PublishAllCustomizations"
0xacd7  ldc.i4.5
0xacd8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xacdd  brfalse.s loc_ACEB
0xacdf  ldarg.0
0xace0  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::PublishAllCustomizations()
0xace5  stloc.0
0xace6  br       loc_AD72
0xaceb  ldloc.1
0xacec  ldstr    aPublishcustomi// "PublishCustomizations"
0xacf1  ldc.i4.5
0xacf2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xacf7  brfalse.s loc_AD09
0xacf9  ldarg.0
0xacfa  ldarg.0
0xacfb  ldarg.1
0xacfc  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::GetData(class [System.Web]System.Web.HttpRequest request)
0xad01  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::PublishCustomizations(class [System.Xml]System.Xml.XmlNode data)
0xad06  stloc.0
0xad07  br.s     loc_AD72
0xad09  ldloc.1
0xad0a  ldstr    aCreateentity// "CreateEntity"
0xad0f  ldc.i4.5
0xad10  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xad15  brfalse.s loc_AD2E
0xad17  ldarg.0
0xad18  ldarg.0
0xad19  ldarg.1
0xad1a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::GetSolutionId(class [System.Web]System.Web.HttpRequest request)
0xad1f  ldarg.0
0xad20  ldarg.1
0xad21  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::GetData(class [System.Web]System.Web.HttpRequest request)
0xad26  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::CreateEntity(valuetype [mscorlib]System.Guid solutionId, class [System.Xml]System.Xml.XmlNode data)
0xad2b  stloc.0
0xad2c  br.s     loc_AD72
0xad2e  ldloc.1
0xad2f  ldstr    aUpdateentity// "UpdateEntity"
0xad34  ldc.i4.5
0xad35  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xad3a  brfalse.s loc_AD53
0xad3c  ldarg.0
0xad3d  ldarg.0
0xad3e  ldarg.1
0xad3f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::GetSolutionId(class [System.Web]System.Web.HttpRequest request)
0xad44  ldarg.0
0xad45  ldarg.1
0xad46  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::GetData(class [System.Web]System.Web.HttpRequest request)
0xad4b  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::UpdateEntity(valuetype [mscorlib]System.Guid solutionId, class [System.Xml]System.Xml.XmlNode data)
0xad50  stloc.0
0xad51  br.s     loc_AD72
0xad53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad58  ldstr    aSystemcustomiz_5// "SystemCustomizationHandler, invalid ope"...
0xad5d  ldc.i4.1
0xad5e  newarr   [mscorlib]System.Object
0xad63  dup
0xad64  ldc.i4.0
0xad65  ldloc.1
0xad66  stelem.ref
0xad67  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xad6c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xad71  throw
0xad72  ldloc.0
0xad73  ret
```
