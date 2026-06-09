# Microsoft.Crm.Setup.Common.UrlAccessValidator::ProcessWebException

- ea: `0x4180`
- end: `0x4205`
- name: `Microsoft.Crm.Setup.Common.UrlAccessValidator::ProcessWebException`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4070`

## callees

- `0x2cd0`
- `0x4180`
- `0x4210`

## string_xrefs

- `0x41d8`: `UrlAccessValidator.Failure.UrlAccess`

## pseudocode

```c

```

## disassembly

```asm
0x4180  ldsfld   string [mscorlib]System.String::Empty
0x4185  stloc.0
0x4186  ldarg.1
0x4187  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x418c  isinst   [System]System.Net.HttpWebResponse
0x4191  stloc.1
0x4192  ldloc.1
0x4193  brtrue.s loc_41B6
0x4195  ldarg.1
0x4196  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x419b  isinst   [System]System.Net.WebException
0x41a0  stloc.3
0x41a1  ldloc.3
0x41a2  brfalse.s loc_41B6
0x41a4  ldloc.3
0x41a5  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x41aa  isinst   [System]System.Net.HttpWebResponse
0x41af  stloc.1
0x41b0  ldloc.1
0x41b1  brfalse.s loc_41B6
0x41b3  ldloc.3
0x41b4  starg.s  1
0x41b6  ldc.i4.1
0x41b7  stloc.2
0x41b8  ldloc.1
0x41b9  brfalse.s loc_41D6
0x41bb  ldloc.1
0x41bc  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x41c1  stloc.s  4
0x41c3  ldloc.s  4
0x41c5  ldc.i4   0x1F6
0x41ca  bne.un.s loc_41CE
0x41cc  ldc.i4.2
0x41cd  stloc.2
0x41ce  ldloc.1
0x41cf  ldloc.2
0x41d0  call     string Microsoft.Crm.Setup.Common.UrlAccessValidator::GetCustomError(class [System]System.Net.HttpWebResponse httpWebResponse, valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult errorLevelForLogging)
0x41d5  stloc.0
0x41d6  ldloc.2
0x41d7  ldarg.0
0x41d8  ldstr    aUrlaccessvalid_1// "UrlAccessValidator.Failure.UrlAccess"
0x41dd  ldc.i4.3
0x41de  newarr   [mscorlib]System.Object
0x41e3  dup
0x41e4  ldc.i4.0
0x41e5  ldarg.0
0x41e6  ldfld    class [System]System.Uri Microsoft.Crm.Setup.Common.UrlAccessValidator::_urlBase
0x41eb  stelem.ref
0x41ec  dup
0x41ed  ldc.i4.1
0x41ee  ldarg.0
0x41ef  ldarg.1
0x41f0  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x41f5  stelem.ref
0x41f6  dup
0x41f7  ldc.i4.2
0x41f8  ldloc.0
0x41f9  stelem.ref
0x41fa  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x41ff  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x4204  ret
```
