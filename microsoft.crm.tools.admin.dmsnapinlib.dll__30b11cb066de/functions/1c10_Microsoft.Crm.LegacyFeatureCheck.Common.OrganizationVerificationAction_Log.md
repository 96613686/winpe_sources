# Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::Log

- ea: `0x1c10`
- end: `0x1c4b`
- name: `Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::Log`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1be0`
- `0x1bf0`
- `0x1c00`

## callees

- `0xb00`
- `0xb20`
- `0xb40`
- `0xb60`
- `0xb70`
- `0xf20`

## pseudocode

```c

```

## disassembly

```asm
0x1c10  ldarg.1
0x1c11  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> Microsoft.Crm.LegacyFeatureCheck.Organization::get_VerificationResults()
0x1c16  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.VerificationResult::.ctor()
0x1c1b  dup
0x1c1c  ldarg.2
0x1c1d  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.VerificationResult::set_Severity(valuetype [System]System.Diagnostics.TraceLevel value)
0x1c22  dup
0x1c23  ldarg.3
0x1c24  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.VerificationResult::set_Component(valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName value)
0x1c29  dup
0x1c2a  ldarg.s  4
0x1c2c  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.VerificationResult::set_ComponentId(valuetype [mscorlib]System.Guid value)
0x1c31  dup
0x1c32  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c37  ldarg.s  5
0x1c39  ldarg.s  6
0x1c3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c40  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.VerificationResult::set_Message(string value)
0x1c45  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::Add(var<u1>)
0x1c4a  ret
```
