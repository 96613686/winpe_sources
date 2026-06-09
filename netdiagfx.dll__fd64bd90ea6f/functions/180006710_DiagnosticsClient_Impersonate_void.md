# DiagnosticsClient::Impersonate(void)

- ea: `0x180006710`
- end: `0x180006726`
- name: `?Impersonate@DiagnosticsClient@@UEAAJXZ`
- size: `22`
- prototype: `__int64 __fastcall(DiagnosticsClient *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180004694`

## callees

- `0x180006710`

## import_xrefs

- `wdi!WdiImpersonateClient` at `0x18000671f`

## pseudocode

```c
__int64 __fastcall DiagnosticsClient::Impersonate(DiagnosticsClient *this)
{
  if ( *((_QWORD *)this + 1) )
    return WdiImpersonateClient();
  else
    return 2147942406LL;
}

```

## disassembly

```asm
0x180006710  mov     rcx, [rcx+8]
0x180006714  test    rcx, rcx
0x180006717  jnz     short loc_18000671F
0x180006719  mov     eax, 80070006h
0x18000671e  retn
0x18000671f  jmp     cs:__imp_WdiImpersonateClient
```
