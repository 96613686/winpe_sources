# IIS_CRYPTO_BASE::GetThreadImpersonationToken(void * *)

- ea: `0x180029f50`
- end: `0x180029fba`
- name: `?GetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAPEAX@Z`
- size: `106`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002a058`
- `0x18002a128`
- `0x18002a1f8`
- `0x18002a2b4`
- `0x18002a35c`
- `0x18002a418`

## callees

- `0x180029f50`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x180029f74`
- `ADVAPI32!OpenThreadToken` at `0x180029f74`
- `KERNEL32!GetCurrentThread` at `0x180029f5f`
- `KERNEL32!GetCurrentThread` at `0x180029f5f`
- `KERNEL32!GetLastError` at `0x180029f7e`
- `KERNEL32!GetLastError` at `0x180029f7e`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_BASE::GetThreadImpersonationToken(PHANDLE TokenHandle)
{
  unsigned int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 && LastError != 120 && LastError != 50 )
    {
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      else
        v2 = LastError;
    }
    *TokenHandle = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180029f50  mov     [rsp+arg_0], rbx
0x180029f55  push    rdi
0x180029f56  sub     rsp, 20h
0x180029f5a  mov     rdi, rcx
0x180029f5d  xor     ebx, ebx
0x180029f5f  call    cs:__imp_GetCurrentThread
0x180029f65  mov     r9, rdi; TokenHandle
0x180029f68  lea     r8d, [rbx+1]; OpenAsSelf
0x180029f6c  mov     rcx, rax; ThreadHandle
0x180029f6f  mov     edx, 0F01FFh; DesiredAccess
0x180029f74  call    cs:__imp_OpenThreadToken
0x180029f7a  test    eax, eax
0x180029f7c  jnz     short loc_180029FAD
0x180029f7e  call    cs:__imp_GetLastError
0x180029f84  cmp     eax, 3F0h
0x180029f89  jz      short loc_180029FA6
0x180029f8b  cmp     eax, 78h ; 'x'
0x180029f8e  jz      short loc_180029FA6
0x180029f90  cmp     eax, 32h ; '2'
0x180029f93  jz      short loc_180029FA6
0x180029f95  test    eax, eax
0x180029f97  jg      short loc_180029F9D
0x180029f99  mov     ebx, eax
0x180029f9b  jmp     short loc_180029FA6
0x180029f9d  movzx   ebx, ax
0x180029fa0  or      ebx, 80070000h
0x180029fa6  mov     qword ptr [rdi], 0
0x180029fad  mov     eax, ebx
0x180029faf  mov     rbx, [rsp+28h+arg_0]
0x180029fb4  add     rsp, 20h
0x180029fb8  pop     rdi
0x180029fb9  retn
```
