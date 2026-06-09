# Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::CopyExceptionDetails

- ea: `0x12d80`
- end: `0x12ee0`
- name: `Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::CopyExceptionDetails`
- size: `352`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x12d00`
- `0x12d20`

## callees

- `0x12d80`

## string_xrefs

- `0x12e51`: `PluginTrace`
- `0x12e71`: `Plugin Trace:`

## pseudocode

```c

```

## disassembly

```asm
0x12d80  ldarg.1
0x12d81  ldstr    aEx// "ex"
0x12d86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12d8b  ldarg.0
0x12d8c  ldarg.1
0x12d8d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x12d92  stfld    string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorMessage
0x12d97  ldarg.0
0x12d98  ldarg.1
0x12d99  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12d9e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::XmlCharacterAllowedList(string)
0x12da3  stfld    string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_friendlyMessage
0x12da8  ldarg.0
0x12da9  ldarg.2
0x12daa  stfld    int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorCode
0x12daf  ldarg.1
0x12db0  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmExceptionHandler::RetrieveCrmException(class [mscorlib]System.Exception)
0x12db5  stloc.0
0x12db6  ldloc.0
0x12db7  brfalse.s loc_12DFC
0x12db9  ldarg.0
0x12dba  ldloc.0
0x12dbb  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x12dc0  stfld    int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorCode
0x12dc5  ldloc.0
0x12dc6  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.FaultHelper::ConvertToFault(class [mscorlib]System.Exception)
0x12dcb  stloc.2
0x12dcc  ldloc.2
0x12dcd  brfalse.s loc_12DDB
0x12dcf  ldarg.0
0x12dd0  ldloc.2
0x12dd1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x12dd6  stfld    string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorMessage
0x12ddb  leave.s  loc_12E4B
0x12ddd  stloc.3
0x12dde  ldarg.0
0x12ddf  ldarg.0
0x12de0  ldfld    string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorMessage
0x12de5  call     string [mscorlib]System.Environment::get_NewLine()
0x12dea  ldloc.3
0x12deb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x12df0  call     string [mscorlib]System.String::Concat(string, string, string)
0x12df5  stfld    string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorMessage
0x12dfa  leave.s  loc_12E4B
0x12dfc  ldarg.1
0x12dfd  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.PluginExecutionExceptionHandler::RetrieveInvalidPluginExecutionException(class [mscorlib]System.Exception)
0x12e02  brfalse.s loc_12E11
0x12e04  ldarg.0
0x12e05  ldc.i4   0x80040265
0x12e0a  stfld    int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorCode
0x12e0f  br.s     loc_12E4B
0x12e11  ldarg.1
0x12e12  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x12e17  stloc.s  4
0x12e19  ldloc.s  4
0x12e1b  brfalse.s loc_12E2D
0x12e1d  ldarg.0
0x12e1e  ldloc.s  4
0x12e20  ldarg.2
0x12e21  call     int32 [Microsoft.Crm]Microsoft.Crm.SoapUtility::ParseErrorCodeFromSoapException(class [System.Web.Services]System.Web.Services.Protocols.SoapException, int32)
0x12e26  stfld    int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorCode
0x12e2b  br.s     loc_12E4B
0x12e2d  ldarg.1
0x12e2e  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x12e33  stloc.s  5
0x12e35  ldloc.s  5
0x12e37  brfalse.s loc_12E4B
0x12e39  ldarg.0
0x12e3a  ldloc.s  5
0x12e3c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x12e41  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x12e46  stfld    int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorCode
0x12e4b  ldarg.1
0x12e4c  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x12e51  ldstr    aPlugintrace// "PluginTrace"
0x12e56  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x12e5b  isinst   [mscorlib]System.String
0x12e60  stloc.1
0x12e61  ldloc.1
0x12e62  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12e67  brtrue.s loc_12EDF
0x12e69  ldc.i4.7
0x12e6a  newarr   [mscorlib]System.String
0x12e6f  dup
0x12e70  ldc.i4.0
0x12e71  ldstr    aPluginTrace// "Plugin Trace:"
0x12e76  stelem.ref
0x12e77  dup
0x12e78  ldc.i4.1
0x12e79  call     string [mscorlib]System.Environment::get_NewLine()
0x12e7e  stelem.ref
0x12e7f  dup
0x12e80  ldc.i4.2
0x12e81  call     string [mscorlib]System.Environment::get_NewLine()
0x12e86  stelem.ref
0x12e87  dup
0x12e88  ldc.i4.3
0x12e89  ldloc.1
0x12e8a  stelem.ref
0x12e8b  dup
0x12e8c  ldc.i4.4
0x12e8d  call     string [mscorlib]System.Environment::get_NewLine()
0x12e92  stelem.ref
0x12e93  dup
0x12e94  ldc.i4.5
0x12e95  call     string [mscorlib]System.Environment::get_NewLine()
0x12e9a  stelem.ref
0x12e9b  dup
0x12e9c  ldc.i4.6
0x12e9d  call     string [mscorlib]System.Environment::get_NewLine()
0x12ea2  stelem.ref
0x12ea3  call     string [mscorlib]System.String::Concat(string[])
0x12ea8  stloc.1
0x12ea9  ldarg.0
0x12eaa  ldc.i4.5
0x12eab  newarr   [mscorlib]System.String
0x12eb0  dup
0x12eb1  ldc.i4.0
0x12eb2  ldloc.1
0x12eb3  stelem.ref
0x12eb4  dup
0x12eb5  ldc.i4.1
0x12eb6  ldstr    aErrorMessage// "Error Message:"
0x12ebb  stelem.ref
0x12ebc  dup
0x12ebd  ldc.i4.2
0x12ebe  call     string [mscorlib]System.Environment::get_NewLine()
0x12ec3  stelem.ref
0x12ec4  dup
0x12ec5  ldc.i4.3
0x12ec6  call     string [mscorlib]System.Environment::get_NewLine()
0x12ecb  stelem.ref
0x12ecc  dup
0x12ecd  ldc.i4.4
0x12ece  ldarg.0
0x12ecf  ldfld    string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorMessage
0x12ed4  stelem.ref
0x12ed5  call     string [mscorlib]System.String::Concat(string[])
0x12eda  stfld    string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::_errorMessage
0x12edf  ret
```
