# Microsoft.Crm.Sandbox.SandboxHost::get_MaxWorkerCallRetry

- ea: `0x4210`
- end: `0x423f`
- name: `Microsoft.Crm.Sandbox.SandboxHost::get_MaxWorkerCallRetry`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4130`
- `0xba70`
- `0xbf70`

## pseudocode

```c

```

## disassembly

```asm
0x4210  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4215  ldstr    a01// "{0}{1}"
0x421a  ldc.i4.2
0x421b  newarr   [mscorlib]System.Object
0x4220  dup
0x4221  ldc.i4.0
0x4222  ldc.i4.2
0x4223  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x4228  stelem.ref
0x4229  dup
0x422a  ldc.i4.1
0x422b  ldc.i4.s 0x1E
0x422d  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxProperty
0x4232  stelem.ref
0x4233  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4238  ldc.i4.1
0x4239  call     int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetValueFromRegkeyOrgDefault(string, int32)
0x423e  ret
```
