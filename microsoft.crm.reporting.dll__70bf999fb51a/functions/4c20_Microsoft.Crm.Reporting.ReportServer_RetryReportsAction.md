# Microsoft.Crm.Reporting.ReportServer::RetryReportsAction

- ea: `0x4c20`
- end: `0x4cd5`
- name: `Microsoft.Crm.Reporting.ReportServer::RetryReportsAction`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4a20`

## callees

- `0x4c20`

## string_xrefs

- `0x4c87`: `{0} failed. Attempt {1}. Retrying in {2} seconds.`

## pseudocode

```c

```

## disassembly

```asm
0x4c20  ldc.i4.4
0x4c21  stloc.0
0x4c22  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4c27  stloc.1
0x4c28  ldc.i4.1
0x4c29  stloc.2
0x4c2a  br       loc_4CCD
0x4c2f  nop
0x4c30  ldarg.1
0x4c31  callvirt instance void [mscorlib]System.Action::Invoke()
0x4c36  leave    loc_4CD4
0x4c3b  dup
0x4c3c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x4c41  ldstr    aErrorcode// "ErrorCode"
0x4c46  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4c4b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x4c50  ldstr    aRsitemnotfound// "rsItemNotFound"
0x4c55  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4c5a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4c5f  stloc.s  4
0x4c61  ldloca.s 4
0x4c63  ldloc.1
0x4c64  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x4c69  stloc.3
0x4c6a  brtrue.s loc_4C7E
0x4c6c  ldloca.s 3
0x4c6e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x4c73  ldc.r8   60.0
0x4c7c  ble.un.s loc_4C80
0x4c7e  rethrow
0x4c80  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4c85  ldc.i4.s 0x20
0x4c87  ldstr    a0FailedAttempt// "{0} failed. Attempt {1}. Retrying in {2"...
0x4c8c  ldc.i4.3
0x4c8d  newarr   [mscorlib]System.Object
0x4c92  dup
0x4c93  ldc.i4.0
0x4c94  ldarg.1
0x4c95  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x4c9a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x4c9f  stelem.ref
0x4ca0  dup
0x4ca1  ldc.i4.1
0x4ca2  ldloc.2
0x4ca3  box      [mscorlib]System.Int32
0x4ca8  stelem.ref
0x4ca9  dup
0x4caa  ldc.i4.2
0x4cab  ldloc.0
0x4cac  box      [mscorlib]System.Int32
0x4cb1  stelem.ref
0x4cb2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4cb7  ldloc.0
0x4cb8  conv.r8
0x4cb9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x4cbe  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x4cc3  ldloc.0
0x4cc4  ldc.i4.2
0x4cc5  mul
0x4cc6  stloc.0
0x4cc7  leave.s  loc_4CC9
0x4cc9  ldloc.2
0x4cca  ldc.i4.1
0x4ccb  add
0x4ccc  stloc.2
0x4ccd  ldloc.2
0x4cce  ldc.i4.4
0x4ccf  ble      loc_4C2F
0x4cd4  ret
```
