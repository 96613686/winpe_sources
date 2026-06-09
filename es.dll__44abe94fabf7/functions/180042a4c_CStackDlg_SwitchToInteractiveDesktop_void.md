# CStackDlg::SwitchToInteractiveDesktop(void)

- ea: `0x180042a4c`
- end: `0x180042be4`
- name: `?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ`
- size: `408`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004269c`

## callees

- `0x180042a4c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042a62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042a62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042b06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042b74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042b06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042b74`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042a75`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042acc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042acc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180042aaa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180042aaa`

## pseudocode

```c
_BOOL8 __fastcall CStackDlg::SwitchToInteractiveDesktop(CStackDlg *this)
{
  HANDLE CurrentProcess; // rax
  __int64 v4; // rax
  __int64 (__fastcall *v5)(_QWORD); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 (__fastcall *v9)(_QWORD); // rbx
  DWORD v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  TokenInformation = 0;
  ReturnLength = 4;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    CloseHandle(TokenHandle);
    return 0;
  }
  CloseHandle(TokenHandle);
  TokenHandle = 0;
  if ( !TokenInformation )
    return 0;
  v4 = (*(__int64 (**)(void))(qword_1800642C0 + 72))();
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
    return 0;
  v5 = *(__int64 (__fastcall **)(_QWORD))(qword_1800642C0 + 104);
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5(CurrentThreadId);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    return 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, __int64))(qword_1800642C0 + 88))(L"winsta0", 0, 895);
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64))(qword_1800642C0 + 80))(v8) )
    return 0;
  v9 = *(__int64 (__fastcall **)(_QWORD))(qword_1800642C0 + 104);
  v10 = GetCurrentThreadId();
  v11 = v9(v10);
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 0;
  v12 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, _QWORD, __int64))(qword_1800642C0 + 120))(
          L"default",
          0,
          0,
          386);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
    return 0;
  return (*(unsigned int (__fastcall **)(__int64))(qword_1800642C0 + 112))(v12) != 0;
}

```

## disassembly

```asm
0x180042a4c  mov     [rsp+arg_0], rbx
0x180042a51  push    rdi
0x180042a52  sub     rsp, 30h
0x180042a56  mov     rdi, rcx
0x180042a59  mov     [rsp+38h+TokenHandle], 0
0x180042a62  call    cs:__imp_GetCurrentProcess
0x180042a68  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180042a6d  mov     edx, 8; DesiredAccess
0x180042a72  mov     rcx, rax; ProcessHandle
0x180042a75  call    cs:__imp_OpenProcessToken
0x180042a7b  test    eax, eax
0x180042a7d  jz      short loc_180042ABF
0x180042a7f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180042a84  lea     rax, [rsp+38h+arg_10]
0x180042a89  mov     r9d, 4; TokenInformationLength
0x180042a8f  mov     [rsp+38h+TokenInformation], 0
0x180042a97  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180042a9c  mov     [rsp+38h+arg_10], r9d
0x180042aa1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180042aa6  lea     edx, [r9+8]; TokenInformationClass
0x180042aaa  call    cs:__imp_GetTokenInformation
0x180042ab0  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180042ab5  test    eax, eax
0x180042ab7  jnz     short loc_180042ACC
0x180042ab9  call    cs:__imp_CloseHandle
0x180042abf  xor     eax, eax
0x180042ac1  mov     rbx, [rsp+38h+arg_0]
0x180042ac6  add     rsp, 30h
0x180042aca  pop     rdi
0x180042acb  retn
0x180042acc  call    cs:__imp_CloseHandle
0x180042ad2  cmp     [rsp+38h+TokenInformation], 0
0x180042ad7  mov     [rsp+38h+TokenHandle], 0
0x180042ae0  jz      short loc_180042ABF
0x180042ae2  mov     rax, cs:qword_1800642C0
0x180042ae9  mov     rax, [rax+48h]
0x180042aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042af2  mov     [rdi+28h], rax
0x180042af6  test    rax, rax
0x180042af9  jz      short loc_180042ABF
0x180042afb  mov     rax, cs:qword_1800642C0
0x180042b02  mov     rbx, [rax+68h]
0x180042b06  call    cs:__imp_GetCurrentThreadId
0x180042b0c  mov     ecx, eax
0x180042b0e  mov     rax, rbx
0x180042b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b16  mov     [rdi+10h], rax
0x180042b1a  test    rax, rax
0x180042b1d  jz      short loc_180042ABF
0x180042b1f  mov     rax, cs:qword_1800642C0
0x180042b26  lea     rcx, aWinsta0; "winsta0"
0x180042b2d  xor     edx, edx
0x180042b2f  mov     r8d, 37Fh
0x180042b35  mov     rax, [rax+58h]
0x180042b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b3e  mov     [rdi+30h], rax
0x180042b42  mov     rdx, rax
0x180042b45  test    rax, rax
0x180042b48  jz      loc_180042ABF
0x180042b4e  mov     rcx, cs:qword_1800642C0
0x180042b55  mov     rax, [rcx+50h]
0x180042b59  mov     rcx, rdx
0x180042b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b61  test    eax, eax
0x180042b63  jz      loc_180042ABF
0x180042b69  mov     rax, cs:qword_1800642C0
0x180042b70  mov     rbx, [rax+68h]
0x180042b74  call    cs:__imp_GetCurrentThreadId
0x180042b7a  mov     ecx, eax
0x180042b7c  mov     rax, rbx
0x180042b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b84  mov     [rdi+18h], rax
0x180042b88  test    rax, rax
0x180042b8b  jz      loc_180042ABF
0x180042b91  mov     rax, cs:qword_1800642C0
0x180042b98  lea     rcx, aDefault; "default"
0x180042b9f  mov     r9d, 182h
0x180042ba5  xor     r8d, r8d
0x180042ba8  xor     edx, edx
0x180042baa  mov     rax, [rax+78h]
0x180042bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bb3  mov     [rdi+20h], rax
0x180042bb7  mov     rdx, rax
0x180042bba  test    rax, rax
0x180042bbd  jz      loc_180042ABF
0x180042bc3  mov     rcx, cs:qword_1800642C0
0x180042bca  mov     rax, [rcx+70h]
0x180042bce  mov     rcx, rdx
0x180042bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bd6  xor     ecx, ecx
0x180042bd8  test    eax, eax
0x180042bda  setnz   cl
0x180042bdd  mov     eax, ecx
0x180042bdf  jmp     loc_180042AC1
```
