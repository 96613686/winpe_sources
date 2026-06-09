# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::StripQuote

- ea: `0x2e0`
- end: `0x31d`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::StripQuote`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x120`

## callees

- `0x2e0`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  ldarg.0
0x2e1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2e6  brtrue.s loc_31B
0x2e8  ldarg.0
0x2e9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2ee  ldc.i4.1
0x2ef  ble.s    loc_31B
0x2f1  ldarg.0
0x2f2  ldstr    asc_319C// "\""
0x2f7  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x2fc  brfalse.s loc_31B
0x2fe  ldarg.0
0x2ff  ldstr    asc_319C// "\""
0x304  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x309  brfalse.s loc_31B
0x30b  ldarg.0
0x30c  ldc.i4.1
0x30d  ldarg.0
0x30e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x313  ldc.i4.2
0x314  sub
0x315  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x31a  ret
0x31b  ldarg.0
0x31c  ret
```
