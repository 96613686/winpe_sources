# Microsoft.Crm.PackageDeployment.PDRootContextHelper::ReadStdinIfRedirected

- ea: `0x1e40`
- end: `0x1e54`
- name: `Microsoft.Crm.PackageDeployment.PDRootContextHelper::ReadStdinIfRedirected`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1e40`

## pseudocode

```c

```

## disassembly

```asm
0x1e40  call     bool [mscorlib]System.Console::get_IsInputRedirected()
0x1e45  brtrue.s loc_1E49
0x1e47  ldnull
0x1e48  ret
0x1e49  call     class [mscorlib]System.IO.TextReader [mscorlib]System.Console::get_In()
0x1e4e  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x1e53  ret
```
