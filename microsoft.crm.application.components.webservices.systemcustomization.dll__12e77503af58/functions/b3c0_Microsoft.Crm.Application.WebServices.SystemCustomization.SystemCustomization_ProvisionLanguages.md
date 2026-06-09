# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::ProvisionLanguages

- ea: `0xb3c0`
- end: `0xb409`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::ProvisionLanguages`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb310`

## callees

- `0x9150`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0xb3c0  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetExtendedTimeout()
0xb3c5  ldc.i4   0x3E8
0xb3ca  div
0xb3cb  stloc.0
0xb3cc  ldloc.0
0xb3cd  ldc.i4   0x4B0
0xb3d2  bgt.s    loc_B3DB
0xb3d4  ldc.i4   0x4B0
0xb3d9  br.s     loc_B3DC
0xb3db  ldloc.0
0xb3dc  stloc.0
0xb3dd  ldloc.0
0xb3de  ldarg.0
0xb3df  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web.Services]System.Web.Services.WebService::get_Server()
0xb3e4  callvirt instance int32 [System.Web]System.Web.HttpServerUtility::get_ScriptTimeout()
0xb3e9  ble.s    loc_B3F7
0xb3eb  ldarg.0
0xb3ec  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web.Services]System.Web.Services.WebService::get_Server()
0xb3f1  ldloc.0
0xb3f2  callvirt instance void [System.Web]System.Web.HttpServerUtility::set_ScriptTimeout(int32)
0xb3f7  ldarg.1
0xb3f8  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.LangProvisioning::Execute(class [System.Xml]System.Xml.XmlNode data)
0xb3fd  leave.s  loc_B408
0xb3ff  stloc.1
0xb400  ldarg.0
0xb401  ldloc.1
0xb402  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb407  throw
0xb408  ret
```
