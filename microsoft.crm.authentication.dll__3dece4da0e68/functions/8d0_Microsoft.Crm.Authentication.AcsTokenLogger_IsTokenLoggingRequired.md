# Microsoft.Crm.Authentication.AcsTokenLogger::IsTokenLoggingRequired

- ea: `0x8d0`
- end: `0x8e4`
- name: `Microsoft.Crm.Authentication.AcsTokenLogger::IsTokenLoggingRequired`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x31b0`

## callees

- `0x8d0`
- `0x940`
- `0x960`

## pseudocode

```c

```

## disassembly

```asm
0x8d0  ldarg.0
0x8d1  ldc.i4.1
0x8d2  bne.un.s loc_8E2
0x8d4  call     bool Microsoft.Crm.Authentication.AcsTokenLogger::IsAcsAuditingEnabled()
0x8d9  brfalse.s loc_8E2
0x8db  ldarg.1
0x8dc  call     bool Microsoft.Crm.Authentication.AcsTokenLogger::IsAcsToken(class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal)
0x8e1  ret
0x8e2  ldc.i4.0
0x8e3  ret
```
