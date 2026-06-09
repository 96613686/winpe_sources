# Microsoft.Crm.Sdk.ServiceDescription::LoadConfiguration

- ea: `0x88e0`
- end: `0x89b4`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadConfiguration`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8850`

## callees

- `0x88e0`
- `0x89c0`
- `0x8a40`
- `0x8b80`
- `0x8bf0`

## string_xrefs

- `0x8928`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0x895d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x8935`: `Microsoft.Crm.Sdk.Crm2006.Request,Microsoft.Crm.WebServices`
- `0x8940`: `Microsoft.Crm.Sdk.Crm2006.Response,Microsoft.Crm.WebServices`
- `0x894b`: `Microsoft.Crm.WebServices.CallerId,Microsoft.Crm.WebServices`
- `0x896a`: `Microsoft.Crm.Sdk.Crm2007.Request,Microsoft.Crm.WebServices`
- `0x8975`: `Microsoft.Crm.Sdk.Crm2007.Response,Microsoft.Crm.WebServices`
- `0x8980`: `Microsoft.Crm.Sdk.CrmAuthenticationToken,Microsoft.Crm.Sdk`
- `0x898b`: `Microsoft.Crm.Sdk.CorrelationToken,Microsoft.Crm.Sdk`
- `0x8996`: `Microsoft.Crm.Sdk.CallerOriginToken,Microsoft.Crm.Sdk`
- `0x89a2`: `Unsupported namespace for ServiceDescription.`

## pseudocode

```c

```

## disassembly

```asm
0x88e0  ldarg.0
0x88e1  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeHandlers()
0x88e6  ldarg.1
0x88e7  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageTypeCollection [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagesType::get_SdkMessageCollection()
0x88ec  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x88f1  stloc.0
0x88f2  br.s     loc_8907
0x88f4  ldloc.0
0x88f5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x88fa  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType
0x88ff  stloc.1
0x8900  ldarg.0
0x8901  ldloc.1
0x8902  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadMessage(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType message)
0x8907  ldloc.0
0x8908  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x890d  brtrue.s loc_88F4
0x890f  leave.s  loc_8922
0x8911  ldloc.0
0x8912  isinst   [mscorlib]System.IDisposable
0x8917  stloc.2
0x8918  ldloc.2
0x8919  brfalse.s loc_8921
0x891b  ldloc.2
0x891c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8921  endfinally
0x8922  ldarg.0
0x8923  ldfld    string Microsoft.Crm.Sdk.ServiceDescription::_targetNamespace
0x8928  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0x892d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8932  brfalse.s loc_8957
0x8934  ldarg.0
0x8935  ldstr    aMicrosoftCrmSd_11// "Microsoft.Crm.Sdk.Crm2006.Request,Micro"...
0x893a  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x893f  ldarg.0
0x8940  ldstr    aMicrosoftCrmSd_12// "Microsoft.Crm.Sdk.Crm2006.Response,Micr"...
0x8945  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x894a  ldarg.0
0x894b  ldstr    aMicrosoftCrmWe// "Microsoft.Crm.WebServices.CallerId,Micr"...
0x8950  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x8955  br.s     loc_89AD
0x8957  ldarg.0
0x8958  ldfld    string Microsoft.Crm.Sdk.ServiceDescription::_targetNamespace
0x895d  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x8962  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8967  brfalse.s loc_89A2
0x8969  ldarg.0
0x896a  ldstr    aMicrosoftCrmSd_13// "Microsoft.Crm.Sdk.Crm2007.Request,Micro"...
0x896f  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x8974  ldarg.0
0x8975  ldstr    aMicrosoftCrmSd_14// "Microsoft.Crm.Sdk.Crm2007.Response,Micr"...
0x897a  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x897f  ldarg.0
0x8980  ldstr    aMicrosoftCrmSd_15// "Microsoft.Crm.Sdk.CrmAuthenticationToke"...
0x8985  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x898a  ldarg.0
0x898b  ldstr    aMicrosoftCrmSd_16// "Microsoft.Crm.Sdk.CorrelationToken,Micr"...
0x8990  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x8995  ldarg.0
0x8996  ldstr    aMicrosoftCrmSd_17// "Microsoft.Crm.Sdk.CallerOriginToken,Mic"...
0x899b  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport(string exportTypeName)
0x89a0  br.s     loc_89AD
0x89a2  ldstr    aUnsupportedNam// "Unsupported namespace for ServiceDescri"...
0x89a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x89ac  throw
0x89ad  ldarg.0
0x89ae  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadExtraEntities()
0x89b3  ret
```
