# Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::CopyExceptionDetails

- ea: `0x9540`
- end: `0x9648`
- name: `Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::CopyExceptionDetails`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x94c0`
- `0x94e0`

## callees

- `0x9540`

## string_xrefs

- `0x9577`: `PluginTrace`
- `0x9597`: `Plugin Trace:`

## pseudocode

```c

```

## disassembly

```asm
0x9540  ldarg.1
0x9541  ldstr    aEx// "ex"
0x9546  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x954b  ldarg.0
0x954c  ldarg.1
0x954d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x9552  stfld    string Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_errorMessage
0x9557  ldarg.0
0x9558  ldarg.1
0x9559  callvirt instance string [mscorlib]System.Exception::get_Message()
0x955e  stfld    string Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_friendlyMessage
0x9563  ldarg.0
0x9564  ldarg.2
0x9565  stfld    int32 Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_errorCode
0x956a  ldarg.0
0x956b  ldarg.1
0x956c  stfld    class [mscorlib]System.Exception Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_fullExceptionDetail
0x9571  ldarg.1
0x9572  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x9577  ldstr    aPlugintrace// "PluginTrace"
0x957c  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x9581  isinst   [mscorlib]System.String
0x9586  stloc.0
0x9587  ldloc.0
0x9588  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x958d  brtrue.s loc_9605
0x958f  ldc.i4.7
0x9590  newarr   [mscorlib]System.String
0x9595  dup
0x9596  ldc.i4.0
0x9597  ldstr    aPluginTrace// "Plugin Trace:"
0x959c  stelem.ref
0x959d  dup
0x959e  ldc.i4.1
0x959f  call     string [mscorlib]System.Environment::get_NewLine()
0x95a4  stelem.ref
0x95a5  dup
0x95a6  ldc.i4.2
0x95a7  call     string [mscorlib]System.Environment::get_NewLine()
0x95ac  stelem.ref
0x95ad  dup
0x95ae  ldc.i4.3
0x95af  ldloc.0
0x95b0  stelem.ref
0x95b1  dup
0x95b2  ldc.i4.4
0x95b3  call     string [mscorlib]System.Environment::get_NewLine()
0x95b8  stelem.ref
0x95b9  dup
0x95ba  ldc.i4.5
0x95bb  call     string [mscorlib]System.Environment::get_NewLine()
0x95c0  stelem.ref
0x95c1  dup
0x95c2  ldc.i4.6
0x95c3  call     string [mscorlib]System.Environment::get_NewLine()
0x95c8  stelem.ref
0x95c9  call     string [mscorlib]System.String::Concat(string[])
0x95ce  stloc.0
0x95cf  ldarg.0
0x95d0  ldc.i4.5
0x95d1  newarr   [mscorlib]System.String
0x95d6  dup
0x95d7  ldc.i4.0
0x95d8  ldloc.0
0x95d9  stelem.ref
0x95da  dup
0x95db  ldc.i4.1
0x95dc  ldstr    aErrorMessage// "Error Message:"
0x95e1  stelem.ref
0x95e2  dup
0x95e3  ldc.i4.2
0x95e4  call     string [mscorlib]System.Environment::get_NewLine()
0x95e9  stelem.ref
0x95ea  dup
0x95eb  ldc.i4.3
0x95ec  call     string [mscorlib]System.Environment::get_NewLine()
0x95f1  stelem.ref
0x95f2  dup
0x95f3  ldc.i4.4
0x95f4  ldarg.0
0x95f5  ldfld    string Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_errorMessage
0x95fa  stelem.ref
0x95fb  call     string [mscorlib]System.String::Concat(string[])
0x9600  stfld    string Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_errorMessage
0x9605  ldarg.1
0x9606  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmExceptionHandler::RetrieveCrmException(class [mscorlib]System.Exception)
0x960b  stloc.1
0x960c  ldloc.1
0x960d  brfalse.s loc_961C
0x960f  ldarg.0
0x9610  ldloc.1
0x9611  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x9616  stfld    int32 Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_errorCode
0x961b  ret
0x961c  ldarg.1
0x961d  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.PluginExecutionExceptionHandler::RetrieveInvalidPluginExecutionException(class [mscorlib]System.Exception)
0x9622  brfalse.s loc_9630
0x9624  ldarg.0
0x9625  ldc.i4   0x80040265
0x962a  stfld    int32 Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_errorCode
0x962f  ret
0x9630  ldarg.1
0x9631  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x9636  stloc.2
0x9637  ldloc.2
0x9638  brfalse.s loc_9647
0x963a  ldarg.0
0x963b  ldloc.2
0x963c  ldarg.2
0x963d  call     int32 [Microsoft.Crm]Microsoft.Crm.SoapUtility::ParseErrorCodeFromSoapException(class [System.Web.Services]System.Web.Services.Protocols.SoapException, int32)
0x9642  stfld    int32 Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::_errorCode
0x9647  ret
```
