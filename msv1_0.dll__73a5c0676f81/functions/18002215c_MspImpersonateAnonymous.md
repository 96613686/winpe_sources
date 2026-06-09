# MspImpersonateAnonymous

- ea: `0x18002215c`
- end: `0x180022185`
- name: `MspImpersonateAnonymous`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032500`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022160`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022160`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18002216f`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18002216f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022166`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022166`

## pseudocode

```c
__int64 MspImpersonateAnonymous()
{
  HANDLE CurrentThread; // rax

  RevertToSelf();
  CurrentThread = GetCurrentThread();
  return !ImpersonateAnonymousToken(CurrentThread) ? 0xC000010D : 0;
}

```

## disassembly

```asm
0x18002215c  sub     rsp, 28h
0x180022160  call    cs:__imp_RevertToSelf
0x180022166  call    cs:__imp_GetCurrentThread
0x18002216c  mov     rcx, rax; ThreadHandle
0x18002216f  call    cs:__imp_ImpersonateAnonymousToken
0x180022175  neg     eax
0x180022177  sbb     eax, eax
0x180022179  not     eax
0x18002217b  and     eax, 0C000010Dh
0x180022180  add     rsp, 28h
0x180022184  retn
```
