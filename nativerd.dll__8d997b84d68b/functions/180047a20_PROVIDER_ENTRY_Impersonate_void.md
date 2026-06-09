# PROVIDER_ENTRY::Impersonate(void)

- ea: `0x180047a20`
- end: `0x180047a63`
- name: `?Impersonate@PROVIDER_ENTRY@@QEAAJXZ`
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

- `0x180047a20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a39`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047a2f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047a2f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047a54`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047a54`

## pseudocode

```c
signed int __fastcall PROVIDER_ENTRY::Impersonate(PROVIDER_ENTRY *this)
{
  void *v1; // rdx
  BOOL v2; // eax
  signed int result; // eax

  v1 = (void *)*((_QWORD *)this + 2);
  if ( v1 )
  {
    v2 = SetThreadToken(0, v1);
  }
  else
  {
    if ( !*((_QWORD *)this + 3) )
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
0x180047a20  sub     rsp, 28h
0x180047a24  mov     rdx, [rcx+10h]; Token
0x180047a28  test    rdx, rdx
0x180047a2b  jz      short loc_180047A4D
0x180047a2d  xor     ecx, ecx; Thread
0x180047a2f  call    cs:__imp_SetThreadToken
0x180047a35  test    eax, eax
0x180047a37  jnz     short loc_180047A5C
0x180047a39  call    cs:__imp_GetLastError
0x180047a3f  test    eax, eax
0x180047a41  jle     short loc_180047A5E
0x180047a43  movzx   eax, ax
0x180047a46  or      eax, 80070000h
0x180047a4b  jmp     short loc_180047A5E
0x180047a4d  cmp     qword ptr [rcx+18h], 0
0x180047a52  jz      short loc_180047A5C
0x180047a54  call    cs:__imp_RevertToSelf
0x180047a5a  jmp     short loc_180047A35
0x180047a5c  xor     eax, eax
0x180047a5e  add     rsp, 28h
0x180047a62  retn
```
