# CThreadContext::ImpersonateUser(void *)

- ea: `0x180003cd0`
- end: `0x180003d98`
- name: `?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z`
- size: `200`
- prototype: `int __fastcall(void **this, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fed8`
- `0x180018a3c`

## callees

- `0x180003cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003ce5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003ce5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003cfd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003cfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d6e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180003d3c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180003d3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CThreadContext::ImpersonateUser(void **this, void *a2)
{
  HANDLE CurrentThread; // rax
  int result; // eax
  bool v6; // sf
  signed int LastError; // eax
  signed int v8; // ebx
  void *v9; // rcx

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, this + 1) )
    goto LABEL_18;
  result = GetLastError();
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( !v6 )
    return -2147467259;
  if ( result == -2147023888 )
  {
LABEL_18:
    if ( ImpersonateLoggedOnUser(a2) )
    {
      *(_DWORD *)this = 1;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v9 = this[1];
      if ( v8 >= 0 )
        v8 = -2147467259;
      if ( v9 )
      {
        CloseHandle(v9);
        this[1] = 0;
      }
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003cd0  mov     [rsp+arg_0], rbx
0x180003cd5  mov     [rsp+arg_8], rsi
0x180003cda  push    rdi
0x180003cdb  sub     rsp, 20h
0x180003cdf  mov     rbx, rdx
0x180003ce2  mov     rdi, rcx
0x180003ce5  call    cs:__imp_GetCurrentThread
0x180003ceb  lea     r9, [rdi+8]; TokenHandle
0x180003cef  mov     edx, 2000Ch; DesiredAccess
0x180003cf4  mov     rcx, rax; ThreadHandle
0x180003cf7  mov     r8d, 1; OpenAsSelf
0x180003cfd  call    cs:__imp_OpenThreadToken
0x180003d03  test    eax, eax
0x180003d05  jnz     short loc_180003D39
0x180003d07  call    cs:__imp_GetLastError
0x180003d0d  test    eax, eax
0x180003d0f  jle     short loc_180003D1B
0x180003d11  movzx   eax, ax
0x180003d14  or      eax, 80070000h
0x180003d19  test    eax, eax
0x180003d1b  js      short loc_180003D32
0x180003d1d  mov     eax, 80004005h
0x180003d22  mov     rbx, [rsp+28h+arg_0]
0x180003d27  mov     rsi, [rsp+28h+arg_8]
0x180003d2c  add     rsp, 20h
0x180003d30  pop     rdi
0x180003d31  retn
0x180003d32  cmp     eax, 800703F0h
0x180003d37  jnz     short loc_180003D88
0x180003d39  mov     rcx, rbx; hToken
0x180003d3c  call    cs:__imp_ImpersonateLoggedOnUser
0x180003d42  test    eax, eax
0x180003d44  jnz     short loc_180003D80
0x180003d46  call    cs:__imp_GetLastError
0x180003d4c  mov     ebx, eax
0x180003d4e  test    eax, eax
0x180003d50  jle     short loc_180003D5B
0x180003d52  movzx   ebx, ax
0x180003d55  or      ebx, 80070000h
0x180003d5b  mov     rcx, [rdi+8]; hObject
0x180003d5f  test    ebx, ebx
0x180003d61  mov     eax, 80004005h
0x180003d66  cmovns  ebx, eax
0x180003d69  test    rcx, rcx
0x180003d6c  jz      short loc_180003D7C
0x180003d6e  call    cs:__imp_CloseHandle
0x180003d74  mov     qword ptr [rdi+8], 0
0x180003d7c  mov     eax, ebx
0x180003d7e  jmp     short loc_180003D88
0x180003d80  mov     dword ptr [rdi], 1
0x180003d86  xor     eax, eax
0x180003d88  mov     rbx, [rsp+28h+arg_0]
0x180003d8d  mov     rsi, [rsp+28h+arg_8]
0x180003d92  add     rsp, 20h
0x180003d96  pop     rdi
0x180003d97  retn
```
