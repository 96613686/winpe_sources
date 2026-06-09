# CscTpQueueWorkItem

- ea: `0x18001f140`
- end: `0x18001f29b`
- name: `CscTpQueueWorkItem`
- size: `347`
- prototype: `DWORD __fastcall(PTP_CALLBACK_ENVIRON pcbe, void *, void *, void *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014ad8`
- `0x18007770c`

## callees

- `0x18001f140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f24a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f24a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f290`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f199`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f199`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f279`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f279`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18001f1cb`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18001f1cb`
- `KERNEL32!GetCurrentProcess` at `0x18001f22d`
- `KERNEL32!GetCurrentProcess` at `0x18001f22d`
- `KERNEL32!LocalAlloc` at `0x18001f163`
- `KERNEL32!LocalAlloc` at `0x18001f163`
- `KERNEL32!LocalFree` at `0x18001f1ef`
- `KERNEL32!LocalFree` at `0x18001f1ef`
- `ADVAPI32!OpenProcessToken` at `0x18001f240`
- `ADVAPI32!OpenProcessToken` at `0x18001f240`
- `ADVAPI32!OpenThreadToken` at `0x18001f1b0`
- `ADVAPI32!OpenThreadToken` at `0x18001f1b0`

## pseudocode

```c
DWORD __fastcall CscTpQueueWorkItem(PTP_CALLBACK_ENVIRON pcbe, void *a2, void *a3, void *a4, int a5)
{
  void **v9; // rbx
  DWORD LastError; // edi
  HANDLE CurrentThread; // rax
  void *v12; // rcx
  DWORD result; // eax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF

  v9 = (void **)LocalAlloc(0x40u, 0x28u);
  if ( v9 )
  {
    LastError = 0;
LABEL_3:
    *(_DWORD *)v9 = a5;
    v9[2] = a2;
    v9[3] = a3;
    v9[4] = a4;
    if ( (a5 & 1) != 0 )
    {
      LastError = 0;
      v9[1] = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xCu, 1, v9 + 1) )
      {
        LastError = GetLastError();
        if ( LastError == 1008 )
        {
          TokenHandle = 0;
          CurrentProcess = GetCurrentProcess();
          if ( OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
          {
            LastError = 0;
            if ( !DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, v9 + 1) )
              LastError = GetLastError();
            CloseHandle(TokenHandle);
          }
          else
          {
            LastError = GetLastError();
          }
        }
      }
    }
    if ( !LastError )
    {
      if ( TrySubmitThreadpoolCallback(CscTppSimpleWorkItemCallback, v9, pcbe) )
        return LastError;
      LastError = GetLastError();
    }
    v12 = v9[1];
    if ( v12 )
      CloseHandle(v12);
    LocalFree(v9);
    return LastError;
  }
  result = GetLastError();
  LastError = result;
  if ( !result )
    goto LABEL_3;
  return result;
}

```

## disassembly

```asm
0x18001f140  push    rbx
0x18001f142  push    rbp
0x18001f143  push    rsi
0x18001f144  push    rdi
0x18001f145  push    r14
0x18001f147  push    r15
0x18001f149  sub     rsp, 48h
0x18001f14d  mov     r14, rdx
0x18001f150  mov     r15, rcx
0x18001f153  mov     edx, 28h ; '('; uBytes
0x18001f158  mov     ecx, 40h ; '@'; uFlags
0x18001f15d  mov     rsi, r9
0x18001f160  mov     rbp, r8
0x18001f163  call    cs:__imp_LocalAlloc
0x18001f169  mov     rbx, rax
0x18001f16c  test    rax, rax
0x18001f16f  jz      loc_18001F204
0x18001f175  xor     edi, edi
0x18001f177  mov     eax, [rsp+78h+arg_20]
0x18001f17e  mov     [rbx], eax
0x18001f180  mov     [rbx+10h], r14
0x18001f184  mov     [rbx+18h], rbp
0x18001f188  mov     [rbx+20h], rsi
0x18001f18c  test    al, 1
0x18001f18e  jz      short loc_18001F1BA
0x18001f190  lea     rsi, [rbx+8]
0x18001f194  xor     edi, edi
0x18001f196  mov     [rsi], rdi
0x18001f199  call    cs:__imp_GetCurrentThread
0x18001f19f  mov     r9, rsi; TokenHandle
0x18001f1a2  mov     edx, 0Ch; DesiredAccess
0x18001f1a7  mov     rcx, rax; ThreadHandle
0x18001f1aa  mov     r8d, 1; OpenAsSelf
0x18001f1b0  call    cs:__imp_OpenThreadToken
0x18001f1b6  test    eax, eax
0x18001f1b8  jz      short loc_18001F215
0x18001f1ba  test    edi, edi
0x18001f1bc  jnz     short loc_18001F1DD
0x18001f1be  mov     r8, r15; pcbe
0x18001f1c1  lea     rcx, ?CscTppSimpleWorkItemCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001f1c8  mov     rdx, rbx; pv
0x18001f1cb  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001f1d1  test    eax, eax
0x18001f1d3  jnz     short loc_18001F1F5
0x18001f1d5  call    cs:__imp_GetLastError
0x18001f1db  mov     edi, eax
0x18001f1dd  mov     rcx, [rbx+8]; hObject
0x18001f1e1  test    rcx, rcx
0x18001f1e4  jz      short loc_18001F1EC
0x18001f1e6  call    cs:__imp_CloseHandle
0x18001f1ec  mov     rcx, rbx; hMem
0x18001f1ef  call    cs:__imp_LocalFree
0x18001f1f5  mov     eax, edi
0x18001f1f7  add     rsp, 48h
0x18001f1fb  pop     r15
0x18001f1fd  pop     r14
0x18001f1ff  pop     rdi
0x18001f200  pop     rsi
0x18001f201  pop     rbp
0x18001f202  pop     rbx
0x18001f203  retn
0x18001f204  call    cs:__imp_GetLastError
0x18001f20a  mov     edi, eax
0x18001f20c  test    eax, eax
0x18001f20e  jnz     short loc_18001F1F7
0x18001f210  jmp     loc_18001F177
0x18001f215  call    cs:__imp_GetLastError
0x18001f21b  mov     edi, eax
0x18001f21d  cmp     eax, 3F0h
0x18001f222  jnz     short loc_18001F1BA
0x18001f224  mov     [rsp+78h+TokenHandle], 0
0x18001f22d  call    cs:__imp_GetCurrentProcess
0x18001f233  lea     r8, [rsp+78h+TokenHandle]; TokenHandle
0x18001f238  mov     edx, 2; DesiredAccess
0x18001f23d  mov     rcx, rax; ProcessHandle
0x18001f240  call    cs:__imp_OpenProcessToken
0x18001f246  test    eax, eax
0x18001f248  jnz     short loc_18001F257
0x18001f24a  call    cs:__imp_GetLastError
0x18001f250  mov     edi, eax
0x18001f252  jmp     loc_18001F1BA
0x18001f257  mov     rcx, [rsp+78h+TokenHandle]; hExistingToken
0x18001f25c  mov     r9d, 2; ImpersonationLevel
0x18001f262  mov     [rsp+78h+phNewToken], rsi; phNewToken
0x18001f267  xor     r8d, r8d; lpTokenAttributes
0x18001f26a  mov     edx, 0Ch; dwDesiredAccess
0x18001f26f  mov     [rsp+78h+TokenType], 2; TokenType
0x18001f277  xor     edi, edi
0x18001f279  call    cs:__imp_DuplicateTokenEx
0x18001f27f  test    eax, eax
0x18001f281  jnz     short loc_18001F28B
0x18001f283  call    cs:__imp_GetLastError
0x18001f289  mov     edi, eax
0x18001f28b  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18001f290  call    cs:__imp_CloseHandle
0x18001f296  jmp     loc_18001F1BA
```
