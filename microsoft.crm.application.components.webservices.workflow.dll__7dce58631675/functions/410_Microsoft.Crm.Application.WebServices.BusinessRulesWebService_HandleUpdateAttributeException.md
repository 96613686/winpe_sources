# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::HandleUpdateAttributeException

- ea: `0x410`
- end: `0x54c`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::HandleUpdateAttributeException`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x260`
- `0x2d0`

## callees

- `0x410`
- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldarg.1
0x411  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x416  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x41b  stloc.0
0x41c  ldloc.0
0x41d  brfalse.s loc_43E
0x41f  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.Utils.ErrorCode
0x424  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x429  ldloc.0
0x42a  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x42f  box      [mscorlib]System.Int32
0x434  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x439  ldc.i4.0
0x43a  ceq
0x43c  br.s     loc_43F
0x43e  ldc.i4.1
0x43f  stloc.1
0x440  ldarg.0
0x441  ldarg.2
0x442  call     instance string Microsoft.Crm.Application.WebServices.BusinessRulesWebService::GetAttributeName(valuetype [mscorlib]System.Guid attributeId)
0x447  stloc.2
0x448  ldloc.1
0x449  brtrue.s loc_45D
0x44b  ldarg.1
0x44c  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x451  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x456  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x45b  br.s     loc_47B
0x45d  ldc.i4   0x80060424
0x462  ldc.i4.1
0x463  newarr   [mscorlib]System.Object
0x468  dup
0x469  ldc.i4.0
0x46a  ldloc.2
0x46b  stelem.ref
0x46c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x471  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x476  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47b  stloc.3
0x47c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x481  stloc.s  5
0x483  ldloc.s  5
0x485  ldstr    aError// "_error"
0x48a  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper::.ctor()
0x48f  stloc.s  6
0x491  ldloc.s  6
0x493  ldloc.3
0x494  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x499  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper::ErrorCode
0x49e  ldloc.s  6
0x4a0  ldloc.3
0x4a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Code()
0x4a6  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper::Code
0x4ab  ldloc.s  6
0x4ad  ldloc.3
0x4ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayTitle()
0x4b3  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper::Title
0x4b8  ldloc.s  6
0x4ba  ldloc.3
0x4bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Description()
0x4c0  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper::Description
0x4c5  ldloc.s  6
0x4c7  ldloc.3
0x4c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_SerializedException()
0x4cd  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper::SerializedException
0x4d2  ldloc.s  6
0x4d4  ldloc.1
0x4d5  brtrue.s loc_4F9
0x4d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4dc  ldloc.3
0x4dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayText()
0x4e2  ldloc.0
0x4e3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x4e8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::get_Values()
0x4ed  call     T0x2B000005
0x4f2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4f7  br.s     loc_513
0x4f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fe  ldloc.3
0x4ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayText()
0x504  ldc.i4.1
0x505  newarr   [mscorlib]System.Object
0x50a  dup
0x50b  ldc.i4.0
0x50c  ldloc.2
0x50d  stelem.ref
0x50e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x513  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper::DisplayText
0x518  ldloc.s  6
0x51a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x51f  ldloc.s  5
0x521  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::.ctor()
0x526  dup
0x527  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ExceptionJsonWrapper
0x52c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x531  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x536  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJSObject(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>)
0x53b  stloc.s  4
0x53d  ldarg.0
0x53e  ldloc.s  4
0x540  ldarg.1
0x541  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x546  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x54b  throw
```
