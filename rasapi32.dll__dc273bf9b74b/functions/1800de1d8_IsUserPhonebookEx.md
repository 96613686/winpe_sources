# IsUserPhonebookEx

- ea: `0x1800de1d8`
- end: `0x1800de233`
- name: `IsUserPhonebookEx`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800de184`

## callees

- `0x18000d88c`
- `0x1800de1d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800de212`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800de212`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800de1eb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800de1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de1fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de21c`

## pseudocode

```c
DWORD __fastcall IsUserPhonebookEx(void *a1, const WCHAR *a2)
{
  int v4; // ebx

  if ( !a1 || !a2 )
    return 87;
  if ( !ImpersonateLoggedOnUser(a1) )
    return GetLastError();
  v4 = (unsigned int)IsPersonalPhonebook(a2) == 0 ? 0x57 : 0;
  if ( !RevertToSelf() )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x1800de1d8  push    rbx
0x1800de1da  sub     rsp, 20h
0x1800de1de  mov     rbx, rdx
0x1800de1e1  test    rcx, rcx
0x1800de1e4  jz      short loc_1800DE228
0x1800de1e6  test    rdx, rdx
0x1800de1e9  jz      short loc_1800DE228
0x1800de1eb  call    cs:__imp_ImpersonateLoggedOnUser
0x1800de1f1  test    eax, eax
0x1800de1f3  jnz     short loc_1800DE201
0x1800de1f5  add     rsp, 20h
0x1800de1f9  pop     rbx
0x1800de1fa  jmp     cs:__imp_GetLastError
0x1800de201  mov     rcx, rbx; lpString2
0x1800de204  call    IsPersonalPhonebook
0x1800de209  neg     eax
0x1800de20b  sbb     ebx, ebx
0x1800de20d  not     ebx
0x1800de20f  and     ebx, 57h
0x1800de212  call    cs:__imp_RevertToSelf
0x1800de218  test    eax, eax
0x1800de21a  jnz     short loc_1800DE224
0x1800de21c  call    cs:__imp_GetLastError
0x1800de222  mov     ebx, eax
0x1800de224  mov     eax, ebx
0x1800de226  jmp     short loc_1800DE22D
0x1800de228  mov     eax, 57h ; 'W'
0x1800de22d  add     rsp, 20h
0x1800de231  pop     rbx
0x1800de232  retn
```
