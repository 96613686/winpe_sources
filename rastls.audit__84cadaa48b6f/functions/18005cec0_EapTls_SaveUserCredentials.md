# EapTls_SaveUserCredentials

- ea: `0x18005cec0`
- end: `0x18005d0c3`
- name: `EapTls_SaveUserCredentials`
- size: `515`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hSourceHandle, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005a5ec`

## callees

- `0x180005010`
- `0x18005cec0`
- `0x180068830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d053`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d00e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d00e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cf94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cfa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cf94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cfa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d095`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005cfd7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005cfd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cf53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cf53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d0a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d0a4`

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
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v7);
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
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
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
0x18005cec0  mov     [rsp+arg_8], rbx
0x18005cec5  mov     [rsp+arg_10], rsi
0x18005ceca  push    rdi
0x18005cecb  sub     rsp, 40h
0x18005cecf  mov     [rsp+48h+TargetHandle], 0
0x18005ced8  mov     r10d, r9d
0x18005cedb  mov     r9d, edx
0x18005cede  mov     rbx, r8
0x18005cee1  mov     rsi, rcx
0x18005cee4  test    rcx, rcx
0x18005cee7  jnz     short loc_18005CEF3
0x18005cee9  mov     ebx, 0Dh
0x18005ceee  jmp     loc_18005D0B0
0x18005cef3  cmp     r9d, 48h ; 'H'
0x18005cef7  jnb     short loc_18005CF23
0x18005cef9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cf00  lea     rax, WPP_GLOBAL_Control
0x18005cf07  cmp     rcx, rax
0x18005cf0a  jz      short loc_18005CEE9
0x18005cf0c  mov     edx, 0F1h
0x18005cf11  mov     rcx, [rcx+10h]
0x18005cf15  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005cf1c  call    WPP_SF_d
0x18005cf21  jmp     short loc_18005CEE9
0x18005cf23  test    rbx, rbx
0x18005cf26  jz      short loc_18005CEE9
0x18005cf28  cmp     r10d, 14h
0x18005cf2c  jnb     short loc_18005CF4B
0x18005cf2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cf35  lea     rax, WPP_GLOBAL_Control
0x18005cf3c  cmp     rcx, rax
0x18005cf3f  jz      short loc_18005CEE9
0x18005cf41  mov     edx, 0F2h
0x18005cf46  mov     r9d, r10d
0x18005cf49  jmp     short loc_18005CF11
0x18005cf4b  mov     edx, 28h ; '('; uBytes
0x18005cf50  lea     ecx, [rdx+18h]; uFlags
0x18005cf53  call    cs:__imp_LocalAlloc
0x18005cf5a  nop     dword ptr [rax+rax+00h]
0x18005cf5f  mov     rdi, rax
0x18005cf62  test    rax, rax
0x18005cf65  jnz     short loc_18005CF6F
0x18005cf67  lea     ebx, [rax+8]
0x18005cf6a  jmp     loc_18005D0B0
0x18005cf6f  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18005cf76  mov     [rax+8], rsi
0x18005cf7a  mov     [rax+10h], rbx
0x18005cf7e  mov     rax, [rsp+48h+arg_28]
0x18005cf83  movups  xmm0, xmmword ptr [rax]
0x18005cf86  movdqu  xmmword ptr [rdi+18h], xmm0
0x18005cf8b  mov     [rsp+48h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x18005cf94  call    cs:__imp_GetCurrentProcess
0x18005cf9b  nop     dword ptr [rax+rax+00h]
0x18005cfa0  mov     rbx, rax
0x18005cfa3  call    cs:__imp_GetCurrentProcess
0x18005cfaa  nop     dword ptr [rax+rax+00h]
0x18005cfaf  mov     rdx, [rsp+48h+hSourceHandle]; hSourceHandle
0x18005cfb4  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x18005cfb9  mov     [rsp+48h+dwOptions], 2; dwOptions
0x18005cfc1  mov     rcx, rax; hSourceProcessHandle
0x18005cfc4  mov     [rsp+48h+bInheritHandle], 1; bInheritHandle
0x18005cfcc  mov     r8, rbx; hTargetProcessHandle
0x18005cfcf  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18005cfd7  call    cs:__imp_DuplicateHandle
0x18005cfde  nop     dword ptr [rax+rax+00h]
0x18005cfe3  test    eax, eax
0x18005cfe5  jz      short loc_18005D053
0x18005cfe7  mov     rax, [rsp+48h+TargetHandle]
0x18005cfec  lea     r8, ?SaveCertCredsThread@@YAKPEAX@Z; lpStartAddress
0x18005cff3  mov     qword ptr [rsp+48h+bInheritHandle], 0; lpThreadId
0x18005cffc  mov     r9, rdi; lpParameter
0x18005cfff  xor     edx, edx; dwStackSize
0x18005d001  mov     [rdi], rax
0x18005d004  xor     ecx, ecx; lpThreadAttributes
0x18005d006  mov     [rsp+48h+dwDesiredAccess], 0; dwCreationFlags
0x18005d00e  call    cs:__imp_CreateThread
0x18005d015  nop     dword ptr [rax+rax+00h]
0x18005d01a  test    rax, rax
0x18005d01d  jnz     short loc_18005D047
0x18005d01f  call    cs:__imp_GetLastError
0x18005d026  nop     dword ptr [rax+rax+00h]
0x18005d02b  mov     ebx, eax
0x18005d02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d034  lea     rax, WPP_GLOBAL_Control
0x18005d03b  cmp     rcx, rax
0x18005d03e  jz      short loc_18005D08C
0x18005d040  mov     edx, 0F4h
0x18005d045  jmp     short loc_18005D079
0x18005d047  xor     ebx, ebx
0x18005d049  mov     rdx, rax; void *
0x18005d04c  call    ?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z; CWorkerThreadState::SetThreadHandle(void *)
0x18005d051  jmp     short loc_18005D0B0
0x18005d053  call    cs:__imp_GetLastError
0x18005d05a  nop     dword ptr [rax+rax+00h]
0x18005d05f  mov     ebx, eax
0x18005d061  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d068  lea     rax, WPP_GLOBAL_Control
0x18005d06f  cmp     rcx, rax
0x18005d072  jz      short loc_18005D08C
0x18005d074  mov     edx, 0F3h
0x18005d079  mov     rcx, [rcx+10h]
0x18005d07d  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005d084  mov     r9d, ebx
0x18005d087  call    WPP_SF_d
0x18005d08c  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18005d090  jz      short loc_18005D0A1
0x18005d092  mov     rcx, [rdi]; hObject
0x18005d095  call    cs:__imp_CloseHandle
0x18005d09c  nop     dword ptr [rax+rax+00h]
0x18005d0a1  mov     rcx, rdi; hMem
0x18005d0a4  call    cs:__imp_LocalFree
0x18005d0ab  nop     dword ptr [rax+rax+00h]
0x18005d0b0  mov     rsi, [rsp+48h+arg_10]
0x18005d0b5  mov     eax, ebx
0x18005d0b7  mov     rbx, [rsp+48h+arg_8]
0x18005d0bc  add     rsp, 40h
0x18005d0c0  pop     rdi
0x18005d0c1  retn
```
