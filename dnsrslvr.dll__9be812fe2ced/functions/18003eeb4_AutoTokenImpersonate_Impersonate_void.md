# AutoTokenImpersonate::Impersonate(void *)

- ea: `0x18003eeb4`
- end: `0x18003efb1`
- name: `?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(AutoTokenImpersonate *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f3c0`

## callees

- `0x18003eeb4`
- `0x180046ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ef91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ef91`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003eefa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003eefa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003eee1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003eee1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003ef3e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003ef3e`

## pseudocode

```c
__int64 __fastcall AutoTokenImpersonate::Impersonate(AutoTokenImpersonate *this, void *a2)
{
  HANDLE CurrentThread; // rax
  signed int v4; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    if ( RevertToSelf() )
    {
      v5 = 0;
      *(_QWORD *)this = TokenHandle;
      TokenHandle = 0;
      *((_DWORD *)this + 2) = 1;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147418113;
    }
  }
  else if ( GetLastError() == 1008 )
  {
    v5 = 0;
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147418113;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003eeb4  mov     [rsp+arg_8], rbx
0x18003eeb9  push    rdi
0x18003eeba  sub     rsp, 40h
0x18003eebe  mov     rax, cs:__security_cookie
0x18003eec5  xor     rax, rsp
0x18003eec8  mov     [rsp+48h+var_18], rax
0x18003eecd  mov     rdi, rcx
0x18003eed0  mov     [rsp+48h+var_24], 0
0x18003eed8  mov     [rsp+48h+TokenHandle], 0
0x18003eee1  call    cs:__imp_GetCurrentThread
0x18003eee7  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18003eeec  mov     edx, 2000Eh; DesiredAccess
0x18003eef1  mov     rcx, rax; ThreadHandle
0x18003eef4  mov     r8d, 1; OpenAsSelf
0x18003eefa  call    cs:__imp_OpenThreadToken
0x18003ef00  test    eax, eax
0x18003ef02  jnz     short loc_18003EF3E
0x18003ef04  call    cs:__imp_GetLastError
0x18003ef0a  cmp     eax, 3F0h
0x18003ef0f  jz      short loc_18003EF3A
0x18003ef11  call    cs:__imp_GetLastError
0x18003ef17  mov     ebx, eax
0x18003ef19  test    eax, eax
0x18003ef1b  jle     short loc_18003EF26
0x18003ef1d  movzx   ebx, ax
0x18003ef20  or      ebx, 80070000h
0x18003ef26  test    ebx, ebx
0x18003ef28  mov     [rsp+48h+var_24], 184h
0x18003ef30  mov     eax, 8000FFFFh
0x18003ef35  cmovns  ebx, eax
0x18003ef38  jmp     short loc_18003EF87
0x18003ef3a  xor     ebx, ebx
0x18003ef3c  jmp     short loc_18003EF87
0x18003ef3e  call    cs:__imp_RevertToSelf
0x18003ef44  test    eax, eax
0x18003ef46  jnz     short loc_18003EF71
0x18003ef48  call    cs:__imp_GetLastError
0x18003ef4e  mov     ebx, eax
0x18003ef50  test    eax, eax
0x18003ef52  jle     short loc_18003EF5D
0x18003ef54  movzx   ebx, ax
0x18003ef57  or      ebx, 80070000h
0x18003ef5d  test    ebx, ebx
0x18003ef5f  mov     [rsp+48h+var_24], 197h
0x18003ef67  mov     eax, 8000FFFFh
0x18003ef6c  cmovns  ebx, eax
0x18003ef6f  jmp     short loc_18003EF87
0x18003ef71  mov     rcx, [rsp+48h+TokenHandle]
0x18003ef76  xor     ebx, ebx
0x18003ef78  mov     [rdi], rcx
0x18003ef7b  mov     [rsp+48h+TokenHandle], rbx
0x18003ef80  mov     dword ptr [rdi+8], 1
0x18003ef87  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18003ef8c  test    rcx, rcx
0x18003ef8f  jz      short loc_18003EF97
0x18003ef91  call    cs:__imp_CloseHandle
0x18003ef97  mov     eax, ebx
0x18003ef99  mov     rcx, [rsp+48h+var_18]
0x18003ef9e  xor     rcx, rsp; StackCookie
0x18003efa1  call    __security_check_cookie
0x18003efa6  mov     rbx, [rsp+48h+arg_8]
0x18003efab  add     rsp, 40h
0x18003efaf  pop     rdi
0x18003efb0  retn
```
