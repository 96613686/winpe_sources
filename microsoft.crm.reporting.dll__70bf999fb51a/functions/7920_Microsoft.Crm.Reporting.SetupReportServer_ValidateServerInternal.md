# Microsoft.Crm.Reporting.SetupReportServer::ValidateServerInternal

- ea: `0x7920`
- end: `0x7975`
- name: `Microsoft.Crm.Reporting.SetupReportServer::ValidateServerInternal`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x75b0`
- `0x7910`

## callees

- `0x7920`
- `0x8340`
- `0x8370`
- `0x8410`

## string_xrefs

- `0x7963`: `Setup failed to validate specified SQL Server Reporting Services Server`

## pseudocode

```c

```

## disassembly

```asm
0x7920  ldarg.0
0x7921  call     instance void Microsoft.Crm.Reporting.SetupReportServer::ValidateRSUrl()
0x7926  leave.s  loc_792B
0x7928  pop
0x7929  leave.s  loc_792B
0x792b  nop
0x792c  ldarg.1
0x792d  brfalse.s loc_7935
0x792f  ldarg.0
0x7930  call     instance void Microsoft.Crm.Reporting.SetupReportServer::ValidateCallerPermission()
0x7935  ldarg.0
0x7936  call     instance void Microsoft.Crm.Reporting.SetupReportServer::ValidateSecureLevel()
0x793b  leave.s  loc_7974
0x793d  stloc.0
0x793e  ldloc.0
0x793f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x7944  ldstr    aMessage// "Message"
0x7949  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x794e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7953  ldloc.0
0x7954  ldc.i4   0x80048300
0x7959  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException::.ctor(string, class [mscorlib]System.Exception, int32)
0x795e  throw
0x795f  pop
0x7960  rethrow
0x7962  pop
0x7963  ldstr    aSetupFailedToV// "Setup failed to validate specified SQL "...
0x7968  ldc.i4   0x80048300
0x796d  ldc.i4.0
0x796e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException::.ctor(string, int32, bool)
0x7973  throw
0x7974  ret
```
