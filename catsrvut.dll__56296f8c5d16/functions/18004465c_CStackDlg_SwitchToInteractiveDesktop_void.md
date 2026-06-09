# CStackDlg::SwitchToInteractiveDesktop(void)

- ea: `0x18004465c`
- end: `0x1800447f4`
- name: `?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ`
- size: `408`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800442a0`

## callees

- `0x18004465c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800446c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800446dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800446c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800446dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044716`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044784`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044716`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044784`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180044685`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180044685`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800446ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800446ba`

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
  v4 = (*(__int64 (**)(void))(qword_1800733F0 + 72))();
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
    return 0;
  v5 = *(__int64 (__fastcall **)(_QWORD))(qword_1800733F0 + 104);
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5(CurrentThreadId);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    return 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, __int64))(qword_1800733F0 + 88))(L"winsta0", 0, 895);
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64))(qword_1800733F0 + 80))(v8) )
    return 0;
  v9 = *(__int64 (__fastcall **)(_QWORD))(qword_1800733F0 + 104);
  v10 = GetCurrentThreadId();
  v11 = v9(v10);
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 0;
  v12 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, _QWORD, __int64))(qword_1800733F0 + 120))(
          L"default",
          0,
          0,
          386);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
    return 0;
  return (*(unsigned int (__fastcall **)(__int64))(qword_1800733F0 + 112))(v12) != 0;
}

```

## disassembly

```asm
0x18004465c  mov     [rsp+arg_0], rbx
0x180044661  push    rdi
0x180044662  sub     rsp, 30h
0x180044666  mov     rdi, rcx
0x180044669  mov     [rsp+38h+TokenHandle], 0
0x180044672  call    cs:__imp_GetCurrentProcess
0x180044678  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18004467d  mov     edx, 8; DesiredAccess
0x180044682  mov     rcx, rax; ProcessHandle
0x180044685  call    cs:__imp_OpenProcessToken
0x18004468b  test    eax, eax
0x18004468d  jz      short loc_1800446CF
0x18004468f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180044694  lea     rax, [rsp+38h+arg_10]
0x180044699  mov     r9d, 4; TokenInformationLength
0x18004469f  mov     [rsp+38h+TokenInformation], 0
0x1800446a7  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800446ac  mov     [rsp+38h+arg_10], r9d
0x1800446b1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800446b6  lea     edx, [r9+8]; TokenInformationClass
0x1800446ba  call    cs:__imp_GetTokenInformation
0x1800446c0  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800446c5  test    eax, eax
0x1800446c7  jnz     short loc_1800446DC
0x1800446c9  call    cs:__imp_CloseHandle
0x1800446cf  xor     eax, eax
0x1800446d1  mov     rbx, [rsp+38h+arg_0]
0x1800446d6  add     rsp, 30h
0x1800446da  pop     rdi
0x1800446db  retn
0x1800446dc  call    cs:__imp_CloseHandle
0x1800446e2  cmp     [rsp+38h+TokenInformation], 0
0x1800446e7  mov     [rsp+38h+TokenHandle], 0
0x1800446f0  jz      short loc_1800446CF
0x1800446f2  mov     rax, cs:qword_1800733F0
0x1800446f9  mov     rax, [rax+48h]
0x1800446fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044702  mov     [rdi+28h], rax
0x180044706  test    rax, rax
0x180044709  jz      short loc_1800446CF
0x18004470b  mov     rax, cs:qword_1800733F0
0x180044712  mov     rbx, [rax+68h]
0x180044716  call    cs:__imp_GetCurrentThreadId
0x18004471c  mov     ecx, eax
0x18004471e  mov     rax, rbx
0x180044721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044726  mov     [rdi+10h], rax
0x18004472a  test    rax, rax
0x18004472d  jz      short loc_1800446CF
0x18004472f  mov     rax, cs:qword_1800733F0
0x180044736  lea     rcx, aWinsta0; "winsta0"
0x18004473d  xor     edx, edx
0x18004473f  mov     r8d, 37Fh
0x180044745  mov     rax, [rax+58h]
0x180044749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004474e  mov     [rdi+30h], rax
0x180044752  mov     rdx, rax
0x180044755  test    rax, rax
0x180044758  jz      loc_1800446CF
0x18004475e  mov     rcx, cs:qword_1800733F0
0x180044765  mov     rax, [rcx+50h]
0x180044769  mov     rcx, rdx
0x18004476c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044771  test    eax, eax
0x180044773  jz      loc_1800446CF
0x180044779  mov     rax, cs:qword_1800733F0
0x180044780  mov     rbx, [rax+68h]
0x180044784  call    cs:__imp_GetCurrentThreadId
0x18004478a  mov     ecx, eax
0x18004478c  mov     rax, rbx
0x18004478f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044794  mov     [rdi+18h], rax
0x180044798  test    rax, rax
0x18004479b  jz      loc_1800446CF
0x1800447a1  mov     rax, cs:qword_1800733F0
0x1800447a8  lea     rcx, aDefault; "default"
0x1800447af  mov     r9d, 182h
0x1800447b5  xor     r8d, r8d
0x1800447b8  xor     edx, edx
0x1800447ba  mov     rax, [rax+78h]
0x1800447be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447c3  mov     [rdi+20h], rax
0x1800447c7  mov     rdx, rax
0x1800447ca  test    rax, rax
0x1800447cd  jz      loc_1800446CF
0x1800447d3  mov     rcx, cs:qword_1800733F0
0x1800447da  mov     rax, [rcx+70h]
0x1800447de  mov     rcx, rdx
0x1800447e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447e6  xor     ecx, ecx
0x1800447e8  test    eax, eax
0x1800447ea  setnz   cl
0x1800447ed  mov     eax, ecx
0x1800447ef  jmp     loc_1800446D1
```
