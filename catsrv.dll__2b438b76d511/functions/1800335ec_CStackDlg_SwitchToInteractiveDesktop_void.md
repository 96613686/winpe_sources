# CStackDlg::SwitchToInteractiveDesktop(void)

- ea: `0x1800335ec`
- end: `0x180033784`
- name: `?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ`
- size: `408`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033234`

## callees

- `0x1800335ec`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033659`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003366c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033659`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003366c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800336a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033714`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800336a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033714`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033602`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033615`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033615`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003364a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003364a`

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
  v4 = (*(__int64 (**)(void))(qword_180073338 + 72))();
  *((_QWORD *)this + 5) = v4;
  if ( !v4 )
    return 0;
  v5 = *(__int64 (__fastcall **)(_QWORD))(qword_180073338 + 104);
  CurrentThreadId = GetCurrentThreadId();
  v7 = v5(CurrentThreadId);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    return 0;
  v8 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, __int64))(qword_180073338 + 88))(L"winsta0", 0, 895);
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64))(qword_180073338 + 80))(v8) )
    return 0;
  v9 = *(__int64 (__fastcall **)(_QWORD))(qword_180073338 + 104);
  v10 = GetCurrentThreadId();
  v11 = v9(v10);
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 0;
  v12 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, _QWORD, __int64))(qword_180073338 + 120))(
          L"default",
          0,
          0,
          386);
  *((_QWORD *)this + 4) = v12;
  if ( !v12 )
    return 0;
  return (*(unsigned int (__fastcall **)(__int64))(qword_180073338 + 112))(v12) != 0;
}

```

## disassembly

```asm
0x1800335ec  mov     [rsp+arg_0], rbx
0x1800335f1  push    rdi
0x1800335f2  sub     rsp, 30h
0x1800335f6  mov     rdi, rcx
0x1800335f9  mov     [rsp+38h+TokenHandle], 0
0x180033602  call    cs:__imp_GetCurrentProcess
0x180033608  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003360d  mov     edx, 8; DesiredAccess
0x180033612  mov     rcx, rax; ProcessHandle
0x180033615  call    cs:__imp_OpenProcessToken
0x18003361b  test    eax, eax
0x18003361d  jz      short loc_18003365F
0x18003361f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180033624  lea     rax, [rsp+38h+arg_10]
0x180033629  mov     r9d, 4; TokenInformationLength
0x18003362f  mov     [rsp+38h+TokenInformation], 0
0x180033637  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18003363c  mov     [rsp+38h+arg_10], r9d
0x180033641  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180033646  lea     edx, [r9+8]; TokenInformationClass
0x18003364a  call    cs:__imp_GetTokenInformation
0x180033650  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180033655  test    eax, eax
0x180033657  jnz     short loc_18003366C
0x180033659  call    cs:__imp_CloseHandle
0x18003365f  xor     eax, eax
0x180033661  mov     rbx, [rsp+38h+arg_0]
0x180033666  add     rsp, 30h
0x18003366a  pop     rdi
0x18003366b  retn
0x18003366c  call    cs:__imp_CloseHandle
0x180033672  cmp     [rsp+38h+TokenInformation], 0
0x180033677  mov     [rsp+38h+TokenHandle], 0
0x180033680  jz      short loc_18003365F
0x180033682  mov     rax, cs:qword_180073338
0x180033689  mov     rax, [rax+48h]
0x18003368d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033692  mov     [rdi+28h], rax
0x180033696  test    rax, rax
0x180033699  jz      short loc_18003365F
0x18003369b  mov     rax, cs:qword_180073338
0x1800336a2  mov     rbx, [rax+68h]
0x1800336a6  call    cs:__imp_GetCurrentThreadId
0x1800336ac  mov     ecx, eax
0x1800336ae  mov     rax, rbx
0x1800336b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336b6  mov     [rdi+10h], rax
0x1800336ba  test    rax, rax
0x1800336bd  jz      short loc_18003365F
0x1800336bf  mov     rax, cs:qword_180073338
0x1800336c6  lea     rcx, aWinsta0; "winsta0"
0x1800336cd  xor     edx, edx
0x1800336cf  mov     r8d, 37Fh
0x1800336d5  mov     rax, [rax+58h]
0x1800336d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336de  mov     [rdi+30h], rax
0x1800336e2  mov     rdx, rax
0x1800336e5  test    rax, rax
0x1800336e8  jz      loc_18003365F
0x1800336ee  mov     rcx, cs:qword_180073338
0x1800336f5  mov     rax, [rcx+50h]
0x1800336f9  mov     rcx, rdx
0x1800336fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033701  test    eax, eax
0x180033703  jz      loc_18003365F
0x180033709  mov     rax, cs:qword_180073338
0x180033710  mov     rbx, [rax+68h]
0x180033714  call    cs:__imp_GetCurrentThreadId
0x18003371a  mov     ecx, eax
0x18003371c  mov     rax, rbx
0x18003371f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033724  mov     [rdi+18h], rax
0x180033728  test    rax, rax
0x18003372b  jz      loc_18003365F
0x180033731  mov     rax, cs:qword_180073338
0x180033738  lea     rcx, aDefault; "default"
0x18003373f  mov     r9d, 182h
0x180033745  xor     r8d, r8d
0x180033748  xor     edx, edx
0x18003374a  mov     rax, [rax+78h]
0x18003374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033753  mov     [rdi+20h], rax
0x180033757  mov     rdx, rax
0x18003375a  test    rax, rax
0x18003375d  jz      loc_18003365F
0x180033763  mov     rcx, cs:qword_180073338
0x18003376a  mov     rax, [rcx+70h]
0x18003376e  mov     rcx, rdx
0x180033771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033776  xor     ecx, ecx
0x180033778  test    eax, eax
0x18003377a  setnz   cl
0x18003377d  mov     eax, ecx
0x18003377f  jmp     loc_180033661
```
