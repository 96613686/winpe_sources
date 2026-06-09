# Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateNonce

- ea: `0x95c0`
- end: `0x97b3`
- name: `Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateNonce`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x9290`
- `0x93f0`

## callees

- `0x7780`
- `0x95c0`
- `0x9a50`

## string_xrefs

- `0x961b`: `NonceValidator.ValidateNonce The 'nonce' found in the  token did not match the expected nonce.\nexpected: '{0}'\nfound in token: '{1}'!`

## pseudocode

```c

```

## disassembly

```asm
0x95c0  ldarg.1
0x95c1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x95c6  brfalse.s loc_95E4
0x95c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95cd  ldstr    aNoncevalidator_4// "NonceValidator.ValidateNonce The requir"...
0x95d2  ldc.i4.0
0x95d3  newarr   [mscorlib]System.Object
0x95d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x95dd  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x95e2  ldc.i4.0
0x95e3  ret
0x95e4  ldarg.2
0x95e5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x95ea  brfalse.s loc_9608
0x95ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95f1  ldstr    aNoncevalidator_5// "NonceValidator.ValidateNonce The nonce "...
0x95f6  ldc.i4.0
0x95f7  newarr   [mscorlib]System.Object
0x95fc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9601  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x9606  ldc.i4.0
0x9607  ret
0x9608  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0x960d  ldarg.2
0x960e  ldarg.1
0x960f  callvirt instance bool [mscorlib]System.StringComparer::Equals(string, string)
0x9614  brtrue.s loc_963A
0x9616  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x961b  ldstr    aNoncevalidator_6// "NonceValidator.ValidateNonce The 'nonce"...
0x9620  ldc.i4.2
0x9621  newarr   [mscorlib]System.Object
0x9626  dup
0x9627  ldc.i4.0
0x9628  ldarg.1
0x9629  stelem.ref
0x962a  dup
0x962b  ldc.i4.1
0x962c  ldarg.2
0x962d  stelem.ref
0x962e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9633  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x9638  ldc.i4.0
0x9639  ret
0x963a  ldarg.2
0x963b  ldc.i4.s 0x2E
0x963d  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x9642  stloc.2
0x9643  ldloc.2
0x9644  ldc.i4.m1
0x9645  bne.un.s loc_9667
0x9647  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x964c  ldstr    aNoncevalidator_7// "NonceValidator.ValidateNonce The 'nonce"...
0x9651  ldc.i4.1
0x9652  newarr   [mscorlib]System.Object
0x9657  dup
0x9658  ldc.i4.0
0x9659  ldarg.1
0x965a  stelem.ref
0x965b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9660  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x9665  ldc.i4.0
0x9666  ret
0x9667  ldarg.2
0x9668  ldc.i4.0
0x9669  ldloc.2
0x966a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x966f  stloc.3
0x9670  ldloc.3
0x9671  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9676  call     int64 [mscorlib]System.Convert::ToInt64(string, class [mscorlib]System.IFormatProvider)
0x967b  stloc.1
0x967c  leave.s  loc_96B8
0x967e  stloc.s  5
0x9680  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9685  ldstr    aNoncevalidator_8// "NonceValidator.ValidateNonce The 'nonce"...
0x968a  ldc.i4.2
0x968b  newarr   [mscorlib]System.Object
0x9690  dup
0x9691  ldc.i4.0
0x9692  ldc.i4.2
0x9693  newarr   [mscorlib]System.Object
0x9698  dup
0x9699  ldc.i4.0
0x969a  ldloc.3
0x969b  stelem.ref
0x969c  dup
0x969d  ldc.i4.1
0x969e  ldarg.1
0x969f  stelem.ref
0x96a0  stelem.ref
0x96a1  dup
0x96a2  ldc.i4.1
0x96a3  ldloc.s  5
0x96a5  stelem.ref
0x96a6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x96ab  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x96b0  ldc.i4.0
0x96b1  stloc.s  6
0x96b3  leave    loc_97B0
0x96b8  ldloc.1
0x96b9  ldc.i4.0
0x96ba  conv.i8
0x96bb  bgt.s    loc_96E1
0x96bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x96c2  ldstr    aNoncevalidator_8// "NonceValidator.ValidateNonce The 'nonce"...
0x96c7  ldc.i4.2
0x96c8  newarr   [mscorlib]System.Object
0x96cd  dup
0x96ce  ldc.i4.0
0x96cf  ldloc.3
0x96d0  stelem.ref
0x96d1  dup
0x96d2  ldc.i4.1
0x96d3  ldarg.1
0x96d4  stelem.ref
0x96d5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x96da  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x96df  ldc.i4.0
0x96e0  ret
0x96e1  nop
0x96e2  ldloc.1
0x96e3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromBinary(int64)
0x96e8  stloc.0
0x96e9  leave.s  loc_9753
0x96eb  stloc.s  7
0x96ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x96f2  ldstr    aNoncevalidator_9// "NonceValidator.ValidateNonce The 'nonce"...
0x96f7  ldc.i4.4
0x96f8  newarr   [mscorlib]System.Object
0x96fd  dup
0x96fe  ldc.i4.0
0x96ff  ldloc.3
0x9700  stelem.ref
0x9701  dup
0x9702  ldc.i4.1
0x9703  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x9708  stloc.s  8
0x970a  ldloca.s 8
0x970c  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x9711  stloc.s  9
0x9713  ldloca.s 9
0x9715  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x971a  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x971f  stelem.ref
0x9720  dup
0x9721  ldc.i4.2
0x9722  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x9727  stloc.s  8
0x9729  ldloca.s 8
0x972b  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x9730  stloc.s  9
0x9732  ldloca.s 9
0x9734  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9739  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x973e  stelem.ref
0x973f  dup
0x9740  ldc.i4.3
0x9741  ldloc.s  7
0x9743  stelem.ref
0x9744  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9749  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x974e  ldc.i4.0
0x974f  stloc.s  6
0x9751  leave.s  loc_97B0
0x9753  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x9758  stloc.s  4
0x975a  ldloc.0
0x975b  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Authentication.Claims.NonceSessionSettings::get_NonceLifetime()
0x9760  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x9765  ldloc.s  4
0x9767  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x976c  brfalse.s loc_97AE
0x976e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9773  ldstr    aNoncevalidator_10// "NonceValidator.ValidateNonce The 'nonce"...
0x9778  ldc.i4.4
0x9779  newarr   [mscorlib]System.Object
0x977e  dup
0x977f  ldc.i4.0
0x9780  ldarg.1
0x9781  stelem.ref
0x9782  dup
0x9783  ldc.i4.1
0x9784  ldloc.0
0x9785  box      [mscorlib]System.DateTime
0x978a  stelem.ref
0x978b  dup
0x978c  ldc.i4.2
0x978d  ldloc.s  4
0x978f  box      [mscorlib]System.DateTime
0x9794  stelem.ref
0x9795  dup
0x9796  ldc.i4.3
0x9797  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Authentication.Claims.NonceSessionSettings::get_NonceLifetime()
0x979c  box      [mscorlib]System.TimeSpan
0x97a1  stelem.ref
0x97a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x97a7  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x97ac  ldc.i4.0
0x97ad  ret
0x97ae  ldc.i4.1
0x97af  ret
0x97b0  ldloc.s  6
0x97b2  ret
```
