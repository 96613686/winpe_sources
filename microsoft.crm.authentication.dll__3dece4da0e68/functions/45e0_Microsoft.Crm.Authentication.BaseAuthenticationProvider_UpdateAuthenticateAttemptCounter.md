# Microsoft.Crm.Authentication.BaseAuthenticationProvider::UpdateAuthenticateAttemptCounter

- ea: `0x45e0`
- end: `0x45ed`
- name: `Microsoft.Crm.Authentication.BaseAuthenticationProvider::UpdateAuthenticateAttemptCounter`
- size: `13`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2cc0`
- `0x6530`
- `0xc910`

## pseudocode

```c

```

## disassembly

```asm
0x45e0  ldarg.0
0x45e1  ldflda   int32 Microsoft.Crm.Authentication.BaseAuthenticationProvider::_attempts
0x45e6  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x45eb  pop
0x45ec  ret
```
