# EfsResolveProcessInfo

- ea: `0x18000c108`
- end: `0x18000c25d`
- name: `EfsResolveProcessInfo`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a60`

## callees

- `0x18000c108`
- `0x18000c264`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c20e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c20e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c23f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c23f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c22b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c22b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c13a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c13a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c170`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c170`
- `ext-ms-win-security-efs-l1-1-0!EfsPlatform_GetCallerID` at `0x18000c1d7`
- `ext-ms-win-security-efs-l1-1-0!EfsPlatform_GetCallerID` at `0x18000c1d7`

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
0x18000c108  push    rbp
0x18000c10a  push    rbx
0x18000c10b  push    rsi
0x18000c10c  push    rdi
0x18000c10d  push    r12
0x18000c10f  push    r14
0x18000c111  push    r15
0x18000c113  mov     rbp, rsp
0x18000c116  sub     rsp, 20h
0x18000c11a  mov     [rbp+arg_0], 0
0x18000c121  mov     rdi, r9
0x18000c124  mov     [rbp+lpMem], 0
0x18000c12c  mov     rsi, r8
0x18000c12f  mov     r12d, edx
0x18000c132  mov     r15, rcx
0x18000c135  test    rcx, rcx
0x18000c138  jnz     short loc_18000C149
0x18000c13a  call    cs:__imp_GetCurrentProcess
0x18000c141  nop     dword ptr [rax+rax+00h]
0x18000c146  mov     r15, rax
0x18000c149  mov     [rbp+TokenHandle], 0
0x18000c151  test    rsi, rsi
0x18000c154  jz      short loc_18000C15A
0x18000c156  xor     eax, eax
0x18000c158  mov     [rsi], eax
0x18000c15a  test    rdi, rdi
0x18000c15d  jz      short loc_18000C164
0x18000c15f  xor     eax, eax
0x18000c161  mov     [rdi], rax
0x18000c164  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000c168  mov     edx, 8; DesiredAccess
0x18000c16d  mov     rcx, r15; ProcessHandle
0x18000c170  call    cs:__imp_OpenProcessToken
0x18000c177  nop     dword ptr [rax+rax+00h]
0x18000c17c  test    eax, eax
0x18000c17e  jnz     short loc_18000C19D
0x18000c180  call    cs:__imp_GetLastError
0x18000c187  nop     dword ptr [rax+rax+00h]
0x18000c18c  mov     ebx, eax
0x18000c18e  test    eax, eax
0x18000c190  jle     short loc_18000C205
0x18000c192  movzx   ebx, ax
0x18000c195  or      ebx, 80070000h
0x18000c19b  jmp     short loc_18000C205
0x18000c19d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000c1a1  lea     rdx, [rbp+arg_0]; int *
0x18000c1a5  call    ?CheckIsLowILToken@CEfsTokenManager@@SAKPEAXPEAH@Z; CEfsTokenManager::CheckIsLowILToken(void *,int *)
0x18000c1aa  mov     ebx, eax
0x18000c1ac  test    eax, eax
0x18000c1ae  jle     short loc_18000C1B9
0x18000c1b0  movzx   ebx, ax
0x18000c1b3  or      ebx, 80070000h
0x18000c1b9  test    ebx, ebx
0x18000c1bb  js      short loc_18000C205
0x18000c1bd  mov     r14d, [rbp+arg_0]
0x18000c1c1  test    rdi, rdi
0x18000c1c4  jz      short loc_18000C1E9
0x18000c1c6  test    r14d, r14d
0x18000c1c9  jnz     short loc_18000C1D0
0x18000c1cb  test    r12d, r12d
0x18000c1ce  jnz     short loc_18000C1E9
0x18000c1d0  lea     rdx, [rbp+lpMem]
0x18000c1d4  mov     rcx, r15
0x18000c1d7  call    cs:__imp_EfsPlatform_GetCallerID
0x18000c1de  nop     dword ptr [rax+rax+00h]
0x18000c1e3  mov     ebx, eax
0x18000c1e5  test    eax, eax
0x18000c1e7  js      short loc_18000C205
0x18000c1e9  test    rsi, rsi
0x18000c1ec  jz      short loc_18000C1F1
0x18000c1ee  mov     [rsi], r14d
0x18000c1f1  test    rdi, rdi
0x18000c1f4  jz      short loc_18000C205
0x18000c1f6  mov     rcx, [rbp+lpMem]
0x18000c1fa  mov     [rdi], rcx
0x18000c1fd  mov     [rbp+lpMem], 0
0x18000c205  mov     rcx, [rbp+TokenHandle]; hObject
0x18000c209  test    rcx, rcx
0x18000c20c  jz      short loc_18000C222
0x18000c20e  call    cs:__imp_CloseHandle
0x18000c215  nop     dword ptr [rax+rax+00h]
0x18000c21a  mov     [rbp+TokenHandle], 0
0x18000c222  mov     rdi, [rbp+lpMem]
0x18000c226  test    rdi, rdi
0x18000c229  jz      short loc_18000C24B
0x18000c22b  call    cs:__imp_GetProcessHeap
0x18000c232  nop     dword ptr [rax+rax+00h]
0x18000c237  mov     r8, rdi; lpMem
0x18000c23a  xor     edx, edx; dwFlags
0x18000c23c  mov     rcx, rax; hHeap
0x18000c23f  call    cs:__imp_HeapFree
0x18000c246  nop     dword ptr [rax+rax+00h]
0x18000c24b  mov     eax, ebx
0x18000c24d  add     rsp, 20h
0x18000c251  pop     r15
0x18000c253  pop     r14
0x18000c255  pop     r12
0x18000c257  pop     rdi
0x18000c258  pop     rsi
0x18000c259  pop     rbx
0x18000c25a  pop     rbp
0x18000c25b  retn
```
