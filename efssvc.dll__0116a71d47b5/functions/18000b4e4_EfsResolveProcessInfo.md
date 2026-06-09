# EfsResolveProcessInfo

- ea: `0x18000b4e4`
- end: `0x18000b60e`
- name: `EfsResolveProcessInfo`
- size: `298`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, int, int *, LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003854`

## callees

- `0x18000b4e4`
- `0x18000b614`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b516`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b516`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b546`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b546`
- `ext-ms-win-security-efs-l1-1-0!EfsPlatform_GetCallerID` at `0x18000b5a1`
- `ext-ms-win-security-efs-l1-1-0!EfsPlatform_GetCallerID` at `0x18000b5a1`

## pseudocode

```c
__int64 __fastcall EfsResolveProcessInfo(HANDLE ProcessHandle, int a2, int *a3, LPVOID *a4)
{
  HANDLE CurrentProcess; // r15
  signed int LastError; // eax
  signed int CallerID; // ebx
  int v10; // eax
  int v11; // r14d
  void *v12; // rdi
  HANDLE ProcessHeap; // rax
  int v15; // [rsp+60h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+50h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+58h] BYREF

  v15 = 0;
  lpMem = 0;
  CurrentProcess = ProcessHandle;
  if ( !ProcessHandle )
    CurrentProcess = GetCurrentProcess();
  TokenHandle = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v10 = CEfsTokenManager::CheckIsLowILToken(TokenHandle, &v15);
    CallerID = v10;
    if ( v10 > 0 )
      CallerID = (unsigned __int16)v10 | 0x80070000;
    if ( CallerID >= 0 )
    {
      if ( (v11 = v15, !a4) || !v15 && a2 || (CallerID = EfsPlatform_GetCallerID(CurrentProcess, &lpMem), CallerID >= 0) )
      {
        if ( a3 )
          *a3 = v11;
        if ( a4 )
        {
          *a4 = lpMem;
          lpMem = 0;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    CallerID = LastError;
    if ( LastError > 0 )
      CallerID = (unsigned __int16)LastError | 0x80070000;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  v12 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
  }
  return (unsigned int)CallerID;
}

```

## disassembly

```asm
0x18000b4e4  push    rbp
0x18000b4e6  push    rbx
0x18000b4e7  push    rsi
0x18000b4e8  push    rdi
0x18000b4e9  push    r12
0x18000b4eb  push    r14
0x18000b4ed  push    r15
0x18000b4ef  mov     rbp, rsp
0x18000b4f2  sub     rsp, 20h
0x18000b4f6  mov     [rbp+arg_0], 0
0x18000b4fd  mov     rdi, r9
0x18000b500  mov     [rbp+lpMem], 0
0x18000b508  mov     rsi, r8
0x18000b50b  mov     r12d, edx
0x18000b50e  mov     r15, rcx
0x18000b511  test    rcx, rcx
0x18000b514  jnz     short loc_18000B51F
0x18000b516  call    cs:__imp_GetCurrentProcess
0x18000b51c  mov     r15, rax
0x18000b51f  mov     [rbp+TokenHandle], 0
0x18000b527  test    rsi, rsi
0x18000b52a  jz      short loc_18000B530
0x18000b52c  xor     eax, eax
0x18000b52e  mov     [rsi], eax
0x18000b530  test    rdi, rdi
0x18000b533  jz      short loc_18000B53A
0x18000b535  xor     eax, eax
0x18000b537  mov     [rdi], rax
0x18000b53a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000b53e  mov     edx, 8; DesiredAccess
0x18000b543  mov     rcx, r15; ProcessHandle
0x18000b546  call    cs:__imp_OpenProcessToken
0x18000b54c  test    eax, eax
0x18000b54e  jnz     short loc_18000B567
0x18000b550  call    cs:__imp_GetLastError
0x18000b556  mov     ebx, eax
0x18000b558  test    eax, eax
0x18000b55a  jle     short loc_18000B5C9
0x18000b55c  movzx   ebx, ax
0x18000b55f  or      ebx, 80070000h
0x18000b565  jmp     short loc_18000B5C9
0x18000b567  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000b56b  lea     rdx, [rbp+arg_0]; int *
0x18000b56f  call    ?CheckIsLowILToken@CEfsTokenManager@@SAKPEAXPEAH@Z; CEfsTokenManager::CheckIsLowILToken(void *,int *)
0x18000b574  mov     ebx, eax
0x18000b576  test    eax, eax
0x18000b578  jle     short loc_18000B583
0x18000b57a  movzx   ebx, ax
0x18000b57d  or      ebx, 80070000h
0x18000b583  test    ebx, ebx
0x18000b585  js      short loc_18000B5C9
0x18000b587  mov     r14d, [rbp+arg_0]
0x18000b58b  test    rdi, rdi
0x18000b58e  jz      short loc_18000B5AD
0x18000b590  test    r14d, r14d
0x18000b593  jnz     short loc_18000B59A
0x18000b595  test    r12d, r12d
0x18000b598  jnz     short loc_18000B5AD
0x18000b59a  lea     rdx, [rbp+lpMem]
0x18000b59e  mov     rcx, r15
0x18000b5a1  call    cs:__imp_EfsPlatform_GetCallerID
0x18000b5a7  mov     ebx, eax
0x18000b5a9  test    eax, eax
0x18000b5ab  js      short loc_18000B5C9
0x18000b5ad  test    rsi, rsi
0x18000b5b0  jz      short loc_18000B5B5
0x18000b5b2  mov     [rsi], r14d
0x18000b5b5  test    rdi, rdi
0x18000b5b8  jz      short loc_18000B5C9
0x18000b5ba  mov     rcx, [rbp+lpMem]
0x18000b5be  mov     [rdi], rcx
0x18000b5c1  mov     [rbp+lpMem], 0
0x18000b5c9  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b5cd  test    rcx, rcx
0x18000b5d0  jz      short loc_18000B5E0
0x18000b5d2  call    cs:__imp_CloseHandle
0x18000b5d8  mov     [rbp+TokenHandle], 0
0x18000b5e0  mov     rdi, [rbp+lpMem]
0x18000b5e4  test    rdi, rdi
0x18000b5e7  jz      short loc_18000B5FD
0x18000b5e9  call    cs:__imp_GetProcessHeap
0x18000b5ef  mov     r8, rdi; lpMem
0x18000b5f2  xor     edx, edx; dwFlags
0x18000b5f4  mov     rcx, rax; hHeap
0x18000b5f7  call    cs:__imp_HeapFree
0x18000b5fd  mov     eax, ebx
0x18000b5ff  add     rsp, 20h
0x18000b603  pop     r15
0x18000b605  pop     r14
0x18000b607  pop     r12
0x18000b609  pop     rdi
0x18000b60a  pop     rsi
0x18000b60b  pop     rbx
0x18000b60c  pop     rbp
0x18000b60d  retn
```
