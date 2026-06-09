# CStackDlg::SwitchToInteractiveDesktop(void)

- ea: `0x1400050bc`
- end: `0x140005254`
- name: `?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ`
- size: `408`
- prototype: `_BOOL8 __fastcall(CStackDlg *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004cfc`

## callees

- `0x1400050bc`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400050d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400050d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005176`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005176`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400050e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400050e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000513c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000513c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000511a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000511a`

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
  v4 = (*(__int64 (**)(void))(qword_1400107C8 + 72))();
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
    return 0;
  v5 = *(__int64 (__fastcall **)(_QWORD))(qword_1400107C8 + 104);
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5(CurrentThreadId);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    return 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, __int64))(qword_1400107C8 + 88))(L"winsta0", 0, 895);
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64))(qword_1400107C8 + 80))(v8) )
    return 0;
  v9 = *(__int64 (__fastcall **)(_QWORD))(qword_1400107C8 + 104);
  v10 = GetCurrentThreadId();
  v11 = v9(v10);
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 0;
  v12 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, _QWORD, __int64))(qword_1400107C8 + 120))(
          L"default",
          0,
          0,
          386);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
    return 0;
  return (*(unsigned int (__fastcall **)(__int64))(qword_1400107C8 + 112))(v12) != 0;
}

```

## disassembly

```asm
0x1400050bc  mov     [rsp+arg_0], rbx
0x1400050c1  push    rdi
0x1400050c2  sub     rsp, 30h
0x1400050c6  mov     rdi, rcx
0x1400050c9  mov     [rsp+38h+TokenHandle], 0
0x1400050d2  call    cs:__imp_GetCurrentProcess
0x1400050d8  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1400050dd  mov     edx, 8; DesiredAccess
0x1400050e2  mov     rcx, rax; ProcessHandle
0x1400050e5  call    cs:__imp_OpenProcessToken
0x1400050eb  test    eax, eax
0x1400050ed  jz      short loc_14000512F
0x1400050ef  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1400050f4  lea     rax, [rsp+38h+arg_10]
0x1400050f9  mov     r9d, 4; TokenInformationLength
0x1400050ff  mov     [rsp+38h+TokenInformation], 0
0x140005107  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x14000510c  mov     [rsp+38h+arg_10], r9d
0x140005111  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140005116  lea     edx, [r9+8]; TokenInformationClass
0x14000511a  call    cs:__imp_GetTokenInformation
0x140005120  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x140005125  test    eax, eax
0x140005127  jnz     short loc_14000513C
0x140005129  call    cs:__imp_CloseHandle
0x14000512f  xor     eax, eax
0x140005131  mov     rbx, [rsp+38h+arg_0]
0x140005136  add     rsp, 30h
0x14000513a  pop     rdi
0x14000513b  retn
0x14000513c  call    cs:__imp_CloseHandle
0x140005142  cmp     [rsp+38h+TokenInformation], 0
0x140005147  mov     [rsp+38h+TokenHandle], 0
0x140005150  jz      short loc_14000512F
0x140005152  mov     rax, cs:qword_1400107C8
0x140005159  mov     rax, [rax+48h]
0x14000515d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005162  mov     [rdi+28h], rax
0x140005166  test    rax, rax
0x140005169  jz      short loc_14000512F
0x14000516b  mov     rax, cs:qword_1400107C8
0x140005172  mov     rbx, [rax+68h]
0x140005176  call    cs:__imp_GetCurrentThreadId
0x14000517c  mov     ecx, eax
0x14000517e  mov     rax, rbx
0x140005181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005186  mov     [rdi+10h], rax
0x14000518a  test    rax, rax
0x14000518d  jz      short loc_14000512F
0x14000518f  mov     rax, cs:qword_1400107C8
0x140005196  lea     rcx, aWinsta0; "winsta0"
0x14000519d  xor     edx, edx
0x14000519f  mov     r8d, 37Fh
0x1400051a5  mov     rax, [rax+58h]
0x1400051a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051ae  mov     [rdi+30h], rax
0x1400051b2  mov     rdx, rax
0x1400051b5  test    rax, rax
0x1400051b8  jz      loc_14000512F
0x1400051be  mov     rcx, cs:qword_1400107C8
0x1400051c5  mov     rax, [rcx+50h]
0x1400051c9  mov     rcx, rdx
0x1400051cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051d1  test    eax, eax
0x1400051d3  jz      loc_14000512F
0x1400051d9  mov     rax, cs:qword_1400107C8
0x1400051e0  mov     rbx, [rax+68h]
0x1400051e4  call    cs:__imp_GetCurrentThreadId
0x1400051ea  mov     ecx, eax
0x1400051ec  mov     rax, rbx
0x1400051ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051f4  mov     [rdi+18h], rax
0x1400051f8  test    rax, rax
0x1400051fb  jz      loc_14000512F
0x140005201  mov     rax, cs:qword_1400107C8
0x140005208  lea     rcx, aDefault; "default"
0x14000520f  mov     r9d, 182h
0x140005215  xor     r8d, r8d
0x140005218  xor     edx, edx
0x14000521a  mov     rax, [rax+78h]
0x14000521e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005223  mov     [rdi+20h], rax
0x140005227  mov     rdx, rax
0x14000522a  test    rax, rax
0x14000522d  jz      loc_14000512F
0x140005233  mov     rcx, cs:qword_1400107C8
0x14000523a  mov     rax, [rcx+70h]
0x14000523e  mov     rcx, rdx
0x140005241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005246  xor     ecx, ecx
0x140005248  test    eax, eax
0x14000524a  setnz   cl
0x14000524d  mov     eax, ecx
0x14000524f  jmp     loc_140005131
```
