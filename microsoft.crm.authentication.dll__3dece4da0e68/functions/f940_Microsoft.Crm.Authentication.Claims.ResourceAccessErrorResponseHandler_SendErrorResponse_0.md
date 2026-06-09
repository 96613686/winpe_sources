# Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendErrorResponse_0

- ea: `0xf940`
- end: `0xf9e2`
- name: `Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendErrorResponse_0`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xec70`
- `0xf930`

## callees

- `0xf780`
- `0xf940`
- `0xfbd0`

## pseudocode

```c

```

## disassembly

```asm
0xf940  ldarg.1
0xf941  ldstr    aErrorcode// "errorCode"
0xf946  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xf94b  ldarg.0
0xf94c  ldstr    aContext// "context"
0xf951  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf956  ldc.i4   0x191
0xf95b  stloc.0
0xf95c  ldarg.1
0xf95d  ldstr    aInvalidRequest// "invalid_request"
0xf962  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf967  brfalse.s loc_F96F
0xf969  ldc.i4   0x190
0xf96e  stloc.0
0xf96f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf974  stloc.1
0xf975  ldloc.1
0xf976  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf97b  ldstr    a01_1// "{0}={1}"
0xf980  ldc.i4.2
0xf981  newarr   [mscorlib]System.Object
0xf986  dup
0xf987  ldc.i4.0
0xf988  ldstr    aError// "error"
0xf98d  stelem.ref
0xf98e  dup
0xf98f  ldc.i4.1
0xf990  ldarg.1
0xf991  stelem.ref
0xf992  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf997  pop
0xf998  ldarg.2
0xf999  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xf99e  brtrue.s loc_F9C3
0xf9a0  ldloc.1
0xf9a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf9a6  ldstr    a01_2// ", {0}={1}"
0xf9ab  ldc.i4.2
0xf9ac  newarr   [mscorlib]System.Object
0xf9b1  dup
0xf9b2  ldc.i4.0
0xf9b3  ldstr    aErrorDescripti// "error_description"
0xf9b8  stelem.ref
0xf9b9  dup
0xf9ba  ldc.i4.1
0xf9bb  ldarg.2
0xf9bc  stelem.ref
0xf9bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf9c2  pop
0xf9c3  ldarg.3
0xf9c4  brfalse.s loc_F9D4
0xf9c6  ldarg.0
0xf9c7  ldloc.0
0xf9c8  ldloc.1
0xf9c9  callvirt instance string [mscorlib]System.Object::ToString()
0xf9ce  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendAuthRequiredResponse(class [System.Web]System.Web.HttpContext context, valuetype [System]System.Net.HttpStatusCode statusCode, string additionalContext)
0xf9d3  ret
0xf9d4  ldarg.0
0xf9d5  ldloc.0
0xf9d6  ldloc.1
0xf9d7  callvirt instance string [mscorlib]System.Object::ToString()
0xf9dc  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendResponse(class [System.Web]System.Web.HttpContext context, valuetype [System]System.Net.HttpStatusCode statusCode, string responseDescription)
0xf9e1  ret
```
