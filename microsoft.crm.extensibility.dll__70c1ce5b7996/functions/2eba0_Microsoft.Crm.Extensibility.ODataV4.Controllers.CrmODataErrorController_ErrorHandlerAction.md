# Microsoft.Crm.Extensibility.ODataV4.Controllers.CrmODataErrorController::ErrorHandlerAction

- ea: `0x2eba0`
- end: `0x2ec46`
- name: `Microsoft.Crm.Extensibility.ODataV4.Controllers.CrmODataErrorController::ErrorHandlerAction`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2eba0`
- `0x2ec50`
- `0x2ec80`

## string_xrefs

- `0x2ec12`: `Bad Request for path {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2eba0  ldarg.0
0x2eba1  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.ODataV4.Controllers.CrmODataErrorController::GetExceptionFromRequestProperties()
0x2eba6  dup
0x2eba7  brtrue.s loc_2EBB0
0x2eba9  pop
0x2ebaa  ldarg.0
0x2ebab  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.ODataV4.Controllers.CrmODataErrorController::GetExceptionFromPathSegment()
0x2ebb0  stloc.0
0x2ebb1  ldloc.0
0x2ebb2  brfalse.s loc_2EC06
0x2ebb4  ldloc.0
0x2ebb5  callvirt instance valuetype [System]System.Net.HttpStatusCode [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::get_StatusCode()
0x2ebba  stloc.1
0x2ebbb  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x2ebc0  dup
0x2ebc1  ldloc.0
0x2ebc2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ebc7  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x2ebcc  dup
0x2ebcd  ldloc.0
0x2ebce  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x2ebd3  brtrue.s loc_2EBD8
0x2ebd5  ldloc.0
0x2ebd6  br.s     loc_2EBDE
0x2ebd8  ldloc.0
0x2ebd9  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x2ebde  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataInnerError::.ctor(class [mscorlib]System.Exception)
0x2ebe3  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_InnerError(class [Microsoft.OData.Core]Microsoft.OData.ODataInnerError)
0x2ebe8  dup
0x2ebe9  ldstr    a0x0X// "0x{0:x}"
0x2ebee  ldloc.0
0x2ebef  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x2ebf4  box      [mscorlib]System.Int32
0x2ebf9  call     string [mscorlib]System.String::Format(string, object)
0x2ebfe  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x2ec03  stloc.2
0x2ec04  br.s     loc_2EC3D
0x2ec06  ldc.i4   0x190
0x2ec0b  stloc.1
0x2ec0c  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x2ec11  dup
0x2ec12  ldstr    aBadRequestForP// "Bad Request for path {1}"
0x2ec17  ldarg.0
0x2ec18  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x2ec1d  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x2ec22  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::get_Path()
0x2ec27  call     string [mscorlib]System.String::Format(string, object)
0x2ec2c  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_Message(string)
0x2ec31  dup
0x2ec32  ldstr    asc_39E2A// ""
0x2ec37  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x2ec3c  stloc.2
0x2ec3d  ldarg.0
0x2ec3e  ldloc.1
0x2ec3f  ldloc.2
0x2ec40  callvirt T0x2B00010F
0x2ec45  ret
```
