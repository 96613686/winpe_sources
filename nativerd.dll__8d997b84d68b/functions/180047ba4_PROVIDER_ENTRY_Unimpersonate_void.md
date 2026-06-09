# PROVIDER_ENTRY::Unimpersonate(void)

- ea: `0x180047ba4`
- end: `0x180047be7`
- name: `?Unimpersonate@PROVIDER_ENTRY@@QEAAJXZ`
- size: `67`
- prototype: `__int64 __fastcall(PROVIDER_ENTRY *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180048360`
- `0x1800496e0`
- `0x18004a650`

## callees

- `0x180047ba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047bbd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047bb3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047bb3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047bd8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047bd8`

## pseudocode

```c
signed int __fastcall PROVIDER_ENTRY::Unimpersonate(PROVIDER_ENTRY *this)
{
  void *v1; // rdx
  BOOL v2; // eax
  signed int result; // eax

  v1 = (void *)*((_QWORD *)this + 3);
  if ( v1 )
  {
    v2 = SetThreadToken(0, v1);
  }
  else
  {
    if ( !*((_QWORD *)this + 2) )
      return 0;
    v2 = RevertToSelf();
  }
  if ( v2 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180047ba4  sub     rsp, 28h
0x180047ba8  mov     rdx, [rcx+18h]; Token
0x180047bac  test    rdx, rdx
0x180047baf  jz      short loc_180047BD1
0x180047bb1  xor     ecx, ecx; Thread
0x180047bb3  call    cs:__imp_SetThreadToken
0x180047bb9  test    eax, eax
0x180047bbb  jnz     short loc_180047BE0
0x180047bbd  call    cs:__imp_GetLastError
0x180047bc3  test    eax, eax
0x180047bc5  jle     short loc_180047BE2
0x180047bc7  movzx   eax, ax
0x180047bca  or      eax, 80070000h
0x180047bcf  jmp     short loc_180047BE2
0x180047bd1  cmp     qword ptr [rcx+10h], 0
0x180047bd6  jz      short loc_180047BE0
0x180047bd8  call    cs:__imp_RevertToSelf
0x180047bde  jmp     short loc_180047BB9
0x180047be0  xor     eax, eax
0x180047be2  add     rsp, 28h
0x180047be6  retn
```
