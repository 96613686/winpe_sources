# Microsoft.Crm.Asynchronous.YammerPostOperation::<CreateHttpRequestExecutor>b__31_0

- ea: `0xa2b0`
- end: `0xa412`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::<CreateHttpRequestExecutor>b__31_0`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x96c0`
- `0xa2b0`

## string_xrefs

- `0xa2d2`: `PostJsonPlugin exception: {0}\n {1}\n {2}\n {3}\n`

## pseudocode

```c

```

## disassembly

```asm
0xa2b0  ldc.i4   0x1F4
0xa2b5  stloc.0
0xa2b6  ldarg.0
0xa2b7  ldarg.1
0xa2b8  ldarg.2
0xa2b9  ldarg.3
0xa2ba  ldarg.s  4
0xa2bc  ldarg.s  5
0xa2be  ldarg.s  6
0xa2c0  ldarg.s  7
0xa2c2  ldloca.s 0
0xa2c4  call     instance string Microsoft.Crm.Asynchronous.YammerPostOperation::PostJson(class [System]System.Uri fullUrl, string accessToken, string method, string contentType, string accept, string json, valuetype [mscorlib]System.TimeSpan connectionTimeout, [out] valuetype [System]System.Net.HttpStatusCode& statusCode)
0xa2c9  stloc.1
0xa2ca  leave.s  loc_A321
0xa2cc  stloc.2
0xa2cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa2d2  ldstr    aPostjsonplugin// "PostJsonPlugin exception: {0}\n {1}\n {"...
0xa2d7  ldc.i4.4
0xa2d8  newarr   [mscorlib]System.Object
0xa2dd  dup
0xa2de  ldc.i4.0
0xa2df  ldloc.2
0xa2e0  stelem.ref
0xa2e1  dup
0xa2e2  ldc.i4.1
0xa2e3  ldloc.2
0xa2e4  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0xa2e9  stelem.ref
0xa2ea  dup
0xa2eb  ldc.i4.2
0xa2ec  ldloc.2
0xa2ed  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa2f2  stelem.ref
0xa2f3  dup
0xa2f4  ldc.i4.3
0xa2f5  ldloc.2
0xa2f6  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xa2fb  stelem.ref
0xa2fc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa301  stloc.1
0xa302  ldloc.2
0xa303  ldarg.0
0xa304  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0xa309  ldc.i4.s 0x14
0xa30b  ldstr    a0_1// "{0}"
0xa310  ldc.i4.1
0xa311  newarr   [mscorlib]System.Object
0xa316  dup
0xa317  ldc.i4.0
0xa318  ldloc.1
0xa319  stelem.ref
0xa31a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa31f  leave.s  loc_A321
0xa321  ldloc.0
0xa322  stloc.3
0xa323  ldloc.3
0xa324  ldc.i4   0x198
0xa329  bgt.s    loc_A37D
0xa32b  ldloc.3
0xa32c  ldc.i4   0xC8
0xa331  sub
0xa332  switch   loc_A410, loc_A410, loc_A410, loc_A3FB, loc_A410
0xa34b  ldloc.3
0xa34c  ldc.i4   0x190
0xa351  sub
0xa352  switch   loc_A3BC, loc_A3D1, loc_A3FB, loc_A3E6, loc_A3FB, loc_A3FB, loc_A3FB, loc_A3FB, loc_A3FB
0xa37b  br.s     loc_A3FB
0xa37d  ldloc.3
0xa37e  ldc.i4   0x1AD
0xa383  beq.s    loc_A3A7
0xa385  ldloc.3
0xa386  ldc.i4   0x1F4
0xa38b  sub
0xa38c  switch   loc_A3FB, loc_A3FB, loc_A3FB, loc_A3FB, loc_A3FB
0xa3a5  br.s     loc_A3FB
0xa3a7  ldc.i4   0x8005F103
0xa3ac  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xa3b1  ldc.i4   0x8005F103
0xa3b6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa3bb  throw
0xa3bc  ldc.i4   0x8005F100
0xa3c1  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xa3c6  ldc.i4   0x8005F100
0xa3cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa3d0  throw
0xa3d1  ldc.i4   0x8005F101
0xa3d6  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xa3db  ldc.i4   0x8005F101
0xa3e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa3e5  throw
0xa3e6  ldc.i4   0x8005F102
0xa3eb  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xa3f0  ldc.i4   0x8005F102
0xa3f5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa3fa  throw
0xa3fb  ldc.i4   0x8005F104
0xa400  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xa405  ldc.i4   0x8005F104
0xa40a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa40f  throw
0xa410  ldloc.1
0xa411  ret
```
