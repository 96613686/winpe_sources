# EapTls_SaveUserCredentials

- ea: `0x180059b60`
- end: `0x180059d2c`
- name: `EapTls_SaveUserCredentials`
- size: `460`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hSourceHandle, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180057408`

## callees

- `0x180004bd0`
- `0x180059b60`
- `0x180064cb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ccf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180059c96`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180059c96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059d0b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059c65`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059c65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180059bf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180059bf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059d14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059d14`

## pseudocode

```c
__int64 __fastcall EapTls_SaveUserCredentials(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        HANDLE hSourceHandle,
        _OWORD *a6)
{
  __int64 v7; // r9
  DWORD LastError; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v11; // rcx
  __int64 v12; // rdx
  char *v13; // rax
  HANDLE *v14; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v16; // rax
  HANDLE Thread; // rax
  CWorkerThreadState *v18; // rcx
  struct _EAPTLS_CONTROL_BLOCK *v19; // rcx
  __int64 v20; // rdx
  HANDLE TargetHandle; // [rsp+50h] [rbp+8h] BYREF

  TargetHandle = 0;
  v7 = a2;
  if ( !a1 )
    return 13;
  if ( a2 < 0x48 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      return 13;
    v12 = 241;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v7);
    return 13;
  }
  if ( !a3 )
    return 13;
  if ( a4 < 0x14 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      return 13;
    v12 = 242;
    v7 = a4;
    goto LABEL_6;
  }
  v13 = (char *)LocalAlloc(0x40u, 0x28u);
  v14 = (HANDLE *)v13;
  if ( !v13 )
    return 8;
  *(_QWORD *)v13 = -1;
  *((_QWORD *)v13 + 1) = a1;
  *((_QWORD *)v13 + 2) = a3;
  *(_OWORD *)(v13 + 24) = *a6;
  TargetHandle = (HANDLE)-1LL;
  CurrentProcess = GetCurrentProcess();
  v16 = GetCurrentProcess();
  if ( DuplicateHandle(v16, hSourceHandle, CurrentProcess, &TargetHandle, 0, 1, 2u) )
  {
    *v14 = TargetHandle;
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SaveCertCredsThread, v14, 0, 0);
    if ( Thread )
    {
      LastError = 0;
      CWorkerThreadState::SetThreadHandle(v18, Thread);
      return LastError;
    }
    LastError = GetLastError();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_21;
    v20 = 244;
    goto LABEL_20;
  }
  LastError = GetLastError();
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v20 = 243;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
  }
LABEL_21:
  if ( *v14 != (HANDLE)-1LL )
    CloseHandle(*v14);
  LocalFree(v14);
  return LastError;
}

```

## disassembly

```asm
0x180059b60  mov     [rsp+arg_8], rbx
0x180059b65  mov     [rsp+arg_10], rsi
0x180059b6a  push    rdi
0x180059b6b  sub     rsp, 40h
0x180059b6f  mov     [rsp+48h+TargetHandle], 0
0x180059b78  mov     r10d, r9d
0x180059b7b  mov     r9d, edx
0x180059b7e  mov     rbx, r8
0x180059b81  mov     rsi, rcx
0x180059b84  test    rcx, rcx
0x180059b87  jnz     short loc_180059B93
0x180059b89  mov     ebx, 0Dh
0x180059b8e  jmp     loc_180059D1A
0x180059b93  cmp     r9d, 48h ; 'H'
0x180059b97  jnb     short loc_180059BC3
0x180059b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180059ba0  lea     rax, WPP_GLOBAL_Control
0x180059ba7  cmp     rcx, rax
0x180059baa  jz      short loc_180059B89
0x180059bac  mov     edx, 0F1h
0x180059bb1  mov     rcx, [rcx+10h]
0x180059bb5  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180059bbc  call    WPP_SF_d
0x180059bc1  jmp     short loc_180059B89
0x180059bc3  test    rbx, rbx
0x180059bc6  jz      short loc_180059B89
0x180059bc8  cmp     r10d, 14h
0x180059bcc  jnb     short loc_180059BEB
0x180059bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180059bd5  lea     rax, WPP_GLOBAL_Control
0x180059bdc  cmp     rcx, rax
0x180059bdf  jz      short loc_180059B89
0x180059be1  mov     edx, 0F2h
0x180059be6  mov     r9d, r10d
0x180059be9  jmp     short loc_180059BB1
0x180059beb  mov     edx, 28h ; '('; uBytes
0x180059bf0  lea     ecx, [rdx+18h]; uFlags
0x180059bf3  call    cs:__imp_LocalAlloc
0x180059bf9  mov     rdi, rax
0x180059bfc  test    rax, rax
0x180059bff  jnz     short loc_180059C09
0x180059c01  lea     ebx, [rax+8]
0x180059c04  jmp     loc_180059D1A
0x180059c09  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x180059c10  mov     [rax+8], rsi
0x180059c14  mov     [rax+10h], rbx
0x180059c18  mov     rax, [rsp+48h+arg_28]
0x180059c1d  movups  xmm0, xmmword ptr [rax]
0x180059c20  movdqu  xmmword ptr [rdi+18h], xmm0
0x180059c25  mov     [rsp+48h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x180059c2e  call    cs:__imp_GetCurrentProcess
0x180059c34  mov     rbx, rax
0x180059c37  call    cs:__imp_GetCurrentProcess
0x180059c3d  mov     rdx, [rsp+48h+hSourceHandle]; hSourceHandle
0x180059c42  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x180059c47  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180059c4f  mov     rcx, rax; hSourceProcessHandle
0x180059c52  mov     [rsp+48h+bInheritHandle], 1; bInheritHandle
0x180059c5a  mov     r8, rbx; hTargetProcessHandle
0x180059c5d  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x180059c65  call    cs:__imp_DuplicateHandle
0x180059c6b  test    eax, eax
0x180059c6d  jz      short loc_180059CCF
0x180059c6f  mov     rax, [rsp+48h+TargetHandle]
0x180059c74  lea     r8, ?SaveCertCredsThread@@YAKPEAX@Z; lpStartAddress
0x180059c7b  mov     qword ptr [rsp+48h+bInheritHandle], 0; lpThreadId
0x180059c84  mov     r9, rdi; lpParameter
0x180059c87  xor     edx, edx; dwStackSize
0x180059c89  mov     [rdi], rax
0x180059c8c  xor     ecx, ecx; lpThreadAttributes
0x180059c8e  mov     [rsp+48h+dwDesiredAccess], 0; dwCreationFlags
0x180059c96  call    cs:__imp_CreateThread
0x180059c9c  test    rax, rax
0x180059c9f  jnz     short loc_180059CC3
0x180059ca1  call    cs:__imp_GetLastError
0x180059ca7  mov     ebx, eax
0x180059ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180059cb0  lea     rax, WPP_GLOBAL_Control
0x180059cb7  cmp     rcx, rax
0x180059cba  jz      short loc_180059D02
0x180059cbc  mov     edx, 0F4h
0x180059cc1  jmp     short loc_180059CEF
0x180059cc3  xor     ebx, ebx
0x180059cc5  mov     rdx, rax; void *
0x180059cc8  call    ?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z; CWorkerThreadState::SetThreadHandle(void *)
0x180059ccd  jmp     short loc_180059D1A
0x180059ccf  call    cs:__imp_GetLastError
0x180059cd5  mov     ebx, eax
0x180059cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180059cde  lea     rax, WPP_GLOBAL_Control
0x180059ce5  cmp     rcx, rax
0x180059ce8  jz      short loc_180059D02
0x180059cea  mov     edx, 0F3h
0x180059cef  mov     rcx, [rcx+10h]
0x180059cf3  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180059cfa  mov     r9d, ebx
0x180059cfd  call    WPP_SF_d
0x180059d02  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180059d06  jz      short loc_180059D11
0x180059d08  mov     rcx, [rdi]; hObject
0x180059d0b  call    cs:__imp_CloseHandle
0x180059d11  mov     rcx, rdi; hMem
0x180059d14  call    cs:__imp_LocalFree
0x180059d1a  mov     rsi, [rsp+48h+arg_10]
0x180059d1f  mov     eax, ebx
0x180059d21  mov     rbx, [rsp+48h+arg_8]
0x180059d26  add     rsp, 40h
0x180059d2a  pop     rdi
0x180059d2b  retn
```
