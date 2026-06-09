# Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException

- ea: `0x15490`
- end: `0x15574`
- name: `Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x155a0`

## callees

- `0x15420`
- `0x15490`
- `0x23640`

## string_xrefs

- `0x15496`: `PluginTrace`
- `0x15567`: `PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x15490  ldarg.0
0x15491  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x15496  ldstr    aPlugintrace// "PluginTrace"
0x1549b  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x154a0  isinst   [mscorlib]System.String
0x154a5  stloc.0
0x154a6  ldarg.0
0x154a7  stloc.1
0x154a8  ldloc.1
0x154a9  isinst   [mscorlib]System.Reflection.TargetInvocationException
0x154ae  stloc.2
0x154af  ldloc.2
0x154b0  brfalse.s loc_154BD
0x154b2  ldloc.2
0x154b3  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x154b8  ldnull
0x154b9  cgt.un
0x154bb  br.s     loc_154BE
0x154bd  ldc.i4.0
0x154be  ldarg.2
0x154bf  and
0x154c0  brfalse.s loc_154C9
0x154c2  ldloc.1
0x154c3  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x154c8  stloc.1
0x154c9  ldloc.1
0x154ca  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmExceptionHandler::RetrieveCrmException(class [mscorlib]System.Exception)
0x154cf  stloc.3
0x154d0  ldloc.1
0x154d1  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.PluginExecutionExceptionHandler::RetrieveInvalidPluginExecutionException(class [mscorlib]System.Exception)
0x154d6  stloc.s  4
0x154d8  ldloc.1
0x154d9  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.FaultHelper::GetOrganizationServiceFault(class [mscorlib]System.Exception)
0x154de  stloc.s  5
0x154e0  ldloc.s  4
0x154e2  brtrue.s loc_15540
0x154e4  ldloc.3
0x154e5  brtrue.s loc_15540
0x154e7  ldloc.s  5
0x154e9  brtrue.s loc_15540
0x154eb  ldloc.1
0x154ec  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x154f1  stloc.s  6
0x154f3  ldloc.s  6
0x154f5  brfalse.s loc_15540
0x154f7  ldloc.0
0x154f8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x154fd  brfalse.s loc_15507
0x154ff  ldloc.s  6
0x15501  call     string Microsoft.Crm.PluginExceptionConvertor::ExtractPluginTraceFromSoapException(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception)
0x15506  stloc.0
0x15507  ldloc.s  6
0x15509  call     int32 Microsoft.Crm.SoapUtility::ParseErrorCodeFromSoapException(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception)
0x1550e  stloc.s  7
0x15510  ldloc.s  7
0x15512  ldc.i4   0x80040265
0x15517  bne.un.s loc_1552A
0x15519  ldloc.s  6
0x1551b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExtractErrorMessageFromSoapException(class [System.Web.Services]System.Web.Services.Protocols.SoapException)
0x15520  ldloc.s  6
0x15522  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.InvalidPluginExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x15527  stloc.1
0x15528  br.s     loc_15540
0x1552a  ldarg.1
0x1552b  brtrue.s loc_15540
0x1552d  ldloc.s  7
0x1552f  ldc.i4.1
0x15530  newarr   [mscorlib]System.Object
0x15535  dup
0x15536  ldc.i4.0
0x15537  ldloc.s  6
0x15539  stelem.ref
0x1553a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1553f  stloc.1
0x15540  ldloc.s  5
0x15542  brfalse.s loc_15559
0x15544  ldloc.0
0x15545  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1554a  brfalse.s loc_15559
0x1554c  ldloc.s  5
0x1554e  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x15553  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x15558  stloc.0
0x15559  ldloc.0
0x1555a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1555f  brtrue.s loc_15572
0x15561  ldloc.1
0x15562  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x15567  ldstr    aPlugintrace// "PluginTrace"
0x1556c  ldloc.0
0x1556d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x15572  ldloc.1
0x15573  ret
```
