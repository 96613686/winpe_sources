# Microsoft.Xrm.Sdk.OrganizationServiceFault::ToString

- ea: `0x3400`
- end: `0x354d`
- name: `Microsoft.Xrm.Sdk.OrganizationServiceFault::ToString`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x3290`
- `0x32b0`
- `0x32d0`
- `0x3310`
- `0x3400`
- `0x3550`
- `0x3570`
- `0x3590`
- `0x35b0`

## pseudocode

```c

```

## disassembly

```asm
0x3400  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3405  stloc.0
0x3406  ldarg.0
0x3407  stloc.1
0x3408  br       loc_3540
0x340d  ldloc.0
0x340e  ldstr    aExceptionDetai// "Exception details: "
0x3413  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3418  pop
0x3419  ldloc.0
0x341a  ldstr    aErrorcode0x// "ErrorCode: 0x"
0x341f  ldloc.1
0x3420  callvirt instance int32 Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x3425  stloc.3
0x3426  ldloca.s 3
0x3428  ldstr    aX// "X"
0x342d  call     instance string [mscorlib]System.Int32::ToString(string)
0x3432  call     string [mscorlib]System.String::Concat(string, string)
0x3437  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x343c  pop
0x343d  ldstr    aMessage// "Message: "
0x3442  ldloc.1
0x3443  callvirt instance string Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x3448  call     string [mscorlib]System.String::Concat(string, string)
0x344d  stloc.2
0x344e  ldloc.1
0x344f  callvirt instance string Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x3454  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3459  brtrue.s loc_346D
0x345b  ldloc.2
0x345c  ldstr    asc_25ECE// "; "
0x3461  ldloc.1
0x3462  callvirt instance string Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x3467  call     string [mscorlib]System.String::Concat(string, string, string)
0x346c  stloc.2
0x346d  ldloc.0
0x346e  ldloc.2
0x346f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3474  pop
0x3475  ldloc.1
0x3476  callvirt instance class Microsoft.Xrm.Sdk.ErrorDetailCollection Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x347b  brfalse.s loc_34B7
0x347d  ldloc.1
0x347e  callvirt instance class Microsoft.Xrm.Sdk.ErrorDetailCollection Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x3483  ldstr    aCallstack// "CallStack"
0x3488  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x348d  brfalse.s loc_34B7
0x348f  ldloc.0
0x3490  ldstr    aStacktrace// "StackTrace: "
0x3495  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x349a  pop
0x349b  ldloc.0
0x349c  ldloc.1
0x349d  callvirt instance class Microsoft.Xrm.Sdk.ErrorDetailCollection Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x34a2  ldstr    aCallstack// "CallStack"
0x34a7  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x34ac  isinst   [mscorlib]System.String
0x34b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x34b6  pop
0x34b7  ldloc.0
0x34b8  ldstr    aTimestamp// "TimeStamp: "
0x34bd  ldloc.1
0x34be  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Xrm.Sdk.BaseServiceFault::get_Timestamp()
0x34c3  stloc.s  4
0x34c5  ldloca.s 4
0x34c7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x34cc  stloc.s  4
0x34ce  ldloca.s 4
0x34d0  ldstr    aO// "o"
0x34d5  call     instance string [mscorlib]System.DateTime::ToString(string)
0x34da  call     string [mscorlib]System.String::Concat(string, string)
0x34df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x34e4  pop
0x34e5  ldloc.1
0x34e6  callvirt instance string Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x34eb  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x34f0  brtrue.s loc_3509
0x34f2  ldloc.0
0x34f3  ldstr    aOriginalexcept// "OriginalException: "
0x34f8  ldloc.1
0x34f9  callvirt instance string Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x34fe  call     string [mscorlib]System.String::Concat(string, string)
0x3503  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3508  pop
0x3509  ldloc.1
0x350a  callvirt instance string Microsoft.Xrm.Sdk.OrganizationServiceFault::get_ExceptionSource()
0x350f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3514  brtrue.s loc_352D
0x3516  ldloc.0
0x3517  ldstr    aExceptionsourc// "ExceptionSource: "
0x351c  ldloc.1
0x351d  callvirt instance string Microsoft.Xrm.Sdk.OrganizationServiceFault::get_ExceptionSource()
0x3522  call     string [mscorlib]System.String::Concat(string, string)
0x3527  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x352c  pop
0x352d  ldloc.0
0x352e  ldstr    asc_25F6A// "--"
0x3533  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3538  pop
0x3539  ldloc.1
0x353a  callvirt instance class Microsoft.Xrm.Sdk.OrganizationServiceFault Microsoft.Xrm.Sdk.OrganizationServiceFault::get_InnerFault()
0x353f  stloc.1
0x3540  ldloc.1
0x3541  brtrue   loc_340D
0x3546  ldloc.0
0x3547  callvirt instance string [mscorlib]System.Object::ToString()
0x354c  ret
```
