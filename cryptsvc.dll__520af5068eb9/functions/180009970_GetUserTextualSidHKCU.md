# GetUserTextualSidHKCU

- ea: `0x180009970`
- end: `0x180009a56`
- name: `GetUserTextualSidHKCU`
- size: `230`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009854`

## callees

- `0x180009970`
- `0x180016e40`
- `0x180017020`
- `0x1800173b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a15`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800099b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800099b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800099c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800099c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800099d9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800099d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009999`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009999`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a0d`

## pseudocode

```c
__int64 __fastcall GetUserTextualSidHKCU(STRSAFE_LPWSTR pszDest, unsigned int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  unsigned int TokenUserSidHKCU; // eax
  void *v8; // rsi
  unsigned int TextualSidHKCU; // edi
  DWORD LastError; // ebx
  PSID v11; // rbx
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF
  PSID pSid; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  pSid = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return 0;
  }
  TokenUserSidHKCU = GetTokenUserSidHKCU(TokenHandle, &pSid);
  v8 = TokenHandle;
  TextualSidHKCU = TokenUserSidHKCU;
  if ( TokenHandle )
  {
    LastError = GetLastError();
    CloseHandle(v8);
    SetLastError(LastError);
  }
  v11 = pSid;
  if ( TextualSidHKCU )
    TextualSidHKCU = GetTextualSidHKCU(pSid, pszDest, a2);
  if ( v11 )
    freeWithSavedLastError(v11);
  return TextualSidHKCU;
}

```

## disassembly

```asm
0x180009970  mov     rax, rsp
0x180009973  mov     [rax+8], rbx
0x180009977  mov     [rax+10h], rbp
0x18000997b  push    rsi
0x18000997c  push    rdi
0x18000997d  push    r14
0x18000997f  sub     rsp, 20h
0x180009983  mov     rbp, rdx
0x180009986  mov     qword ptr [rax+18h], 0
0x18000998e  mov     r14, rcx
0x180009991  mov     qword ptr [rax+20h], 0
0x180009999  call    cs:__imp_GetCurrentThread
0x18000999f  mov     ebx, 8
0x1800099a4  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800099a9  mov     rcx, rax; ThreadHandle
0x1800099ac  mov     edx, ebx; DesiredAccess
0x1800099ae  lea     r8d, [rbx-7]; OpenAsSelf
0x1800099b2  call    cs:__imp_OpenThreadToken
0x1800099b8  test    eax, eax
0x1800099ba  jnz     short loc_1800099E7
0x1800099bc  call    cs:__imp_GetLastError
0x1800099c2  cmp     eax, 3F0h
0x1800099c7  jnz     short loc_1800099E3
0x1800099c9  call    cs:__imp_GetCurrentProcess
0x1800099cf  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800099d4  mov     edx, ebx; DesiredAccess
0x1800099d6  mov     rcx, rax; ProcessHandle
0x1800099d9  call    cs:__imp_OpenProcessToken
0x1800099df  test    eax, eax
0x1800099e1  jnz     short loc_1800099E7
0x1800099e3  xor     eax, eax
0x1800099e5  jmp     short loc_180009A43
0x1800099e7  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800099ec  lea     rdx, [rsp+38h+pSid]
0x1800099f1  call    GetTokenUserSidHKCU
0x1800099f6  mov     rsi, [rsp+38h+TokenHandle]
0x1800099fb  mov     edi, eax
0x1800099fd  test    rsi, rsi
0x180009a00  jz      short loc_180009A1B
0x180009a02  call    cs:__imp_GetLastError
0x180009a08  mov     rcx, rsi; hObject
0x180009a0b  mov     ebx, eax
0x180009a0d  call    cs:__imp_CloseHandle
0x180009a13  mov     ecx, ebx; dwErrCode
0x180009a15  call    cs:__imp_SetLastError
0x180009a1b  mov     rbx, [rsp+38h+pSid]
0x180009a20  test    edi, edi
0x180009a22  jz      short loc_180009A34
0x180009a24  mov     r8, rbp
0x180009a27  mov     rdx, r14; pszDest
0x180009a2a  mov     rcx, rbx; pSid
0x180009a2d  call    GetTextualSidHKCU
0x180009a32  mov     edi, eax
0x180009a34  test    rbx, rbx
0x180009a37  jz      short loc_180009A41
0x180009a39  mov     rcx, rbx; hMem
0x180009a3c  call    freeWithSavedLastError
0x180009a41  mov     eax, edi
0x180009a43  mov     rbx, [rsp+38h+arg_0]
0x180009a48  mov     rbp, [rsp+38h+arg_8]
0x180009a4d  add     rsp, 20h
0x180009a51  pop     r14
0x180009a53  pop     rdi
0x180009a54  pop     rsi
0x180009a55  retn
```
