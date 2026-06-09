# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerCrmTraceListener::OnWriteToCrmTrace

- ea: `0xae0`
- end: `0xb01`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerCrmTraceListener::OnWriteToCrmTrace`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xae0  ldstr    a012// "[{0}][{1}] {2}"
0xae5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xaea  box      [mscorlib]System.DateTime
0xaef  ldarg.1
0xaf0  box      [System]System.Diagnostics.TraceLevel
0xaf5  ldarg.2
0xaf6  call     string [mscorlib]System.String::Format(string, object, object, object)
0xafb  call     void [mscorlib]System.Console::WriteLine(string)
0xb00  ret
```
