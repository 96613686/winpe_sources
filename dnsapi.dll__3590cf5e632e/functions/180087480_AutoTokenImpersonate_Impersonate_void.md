# AutoTokenImpersonate::Impersonate(void *)

- ea: `0x180087480`
- end: `0x1800875a8`
- name: `?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z`
- size: `296`
- prototype: `__int64 __fastcall(AutoTokenImpersonate *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c9f20`

## callees

- `0x180087480`
- `0x18008b5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800874dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800874ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800874dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800874ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087532`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087581`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800874cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800874cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800874ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800874ad`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087522`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087522`

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
0x180087480  mov     [rsp+arg_8], rbx
0x180087485  push    rdi
0x180087486  sub     rsp, 40h
0x18008748a  mov     rax, cs:__security_cookie
0x180087491  xor     rax, rsp
0x180087494  mov     [rsp+48h+var_18], rax
0x180087499  mov     rdi, rcx
0x18008749c  mov     [rsp+48h+var_24], 0
0x1800874a4  mov     [rsp+48h+TokenHandle], 0
0x1800874ad  call    cs:__imp_GetCurrentThread
0x1800874b4  nop     dword ptr [rax+rax+00h]
0x1800874b9  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800874be  mov     edx, 2000Eh; DesiredAccess
0x1800874c3  mov     rcx, rax; ThreadHandle
0x1800874c6  mov     r8d, 1; OpenAsSelf
0x1800874cc  call    cs:__imp_OpenThreadToken
0x1800874d3  nop     dword ptr [rax+rax+00h]
0x1800874d8  test    eax, eax
0x1800874da  jnz     short loc_180087522
0x1800874dc  call    cs:__imp_GetLastError
0x1800874e3  nop     dword ptr [rax+rax+00h]
0x1800874e8  cmp     eax, 3F0h
0x1800874ed  jz      short loc_18008751E
0x1800874ef  call    cs:__imp_GetLastError
0x1800874f6  nop     dword ptr [rax+rax+00h]
0x1800874fb  mov     ebx, eax
0x1800874fd  test    eax, eax
0x1800874ff  jle     short loc_18008750A
0x180087501  movzx   ebx, ax
0x180087504  or      ebx, 80070000h
0x18008750a  test    ebx, ebx
0x18008750c  mov     [rsp+48h+var_24], 184h
0x180087514  mov     eax, 8000FFFFh
0x180087519  cmovns  ebx, eax
0x18008751c  jmp     short loc_180087577
0x18008751e  xor     ebx, ebx
0x180087520  jmp     short loc_180087577
0x180087522  call    cs:__imp_RevertToSelf
0x180087529  nop     dword ptr [rax+rax+00h]
0x18008752e  test    eax, eax
0x180087530  jnz     short loc_180087561
0x180087532  call    cs:__imp_GetLastError
0x180087539  nop     dword ptr [rax+rax+00h]
0x18008753e  mov     ebx, eax
0x180087540  test    eax, eax
0x180087542  jle     short loc_18008754D
0x180087544  movzx   ebx, ax
0x180087547  or      ebx, 80070000h
0x18008754d  test    ebx, ebx
0x18008754f  mov     [rsp+48h+var_24], 197h
0x180087557  mov     eax, 8000FFFFh
0x18008755c  cmovns  ebx, eax
0x18008755f  jmp     short loc_180087577
0x180087561  mov     rcx, [rsp+48h+TokenHandle]
0x180087566  xor     ebx, ebx
0x180087568  mov     [rdi], rcx
0x18008756b  mov     [rsp+48h+TokenHandle], rbx
0x180087570  mov     dword ptr [rdi+8], 1
0x180087577  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18008757c  test    rcx, rcx
0x18008757f  jz      short loc_18008758D
0x180087581  call    cs:__imp_CloseHandle
0x180087588  nop     dword ptr [rax+rax+00h]
0x18008758d  mov     eax, ebx
0x18008758f  mov     rcx, [rsp+48h+var_18]
0x180087594  xor     rcx, rsp; StackCookie
0x180087597  call    __security_check_cookie
0x18008759c  mov     rbx, [rsp+48h+arg_8]
0x1800875a1  add     rsp, 40h
0x1800875a5  pop     rdi
0x1800875a6  retn
```
