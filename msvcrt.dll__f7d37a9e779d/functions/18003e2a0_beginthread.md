# _beginthread

- ea: `0x18003e2a0`
- end: `0x18003e3a2`
- name: `_beginthread`
- size: `258`
- prototype: `uintptr_t __cdecl(_beginthread_proc_type StartAddress, unsigned int StackSize, void *ArgList)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180007d70`
- `0x180007ea8`
- `0x180007f00`
- `0x18001d300`
- `0x18001d50c`
- `0x18002f050`
- `0x18003e048`
- `0x18003e0fc`
- `0x18003e2a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e35d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003e392`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003e392`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e34b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e34b`

## pseudocode

```c
uintptr_t __cdecl beginthread(_beginthread_proc_type StartAddress, unsigned int StackSize, void *ArgList)
{
  SIZE_T v3; // r14
  DWORD LastError; // ebx
  _QWORD *v7; // rdi
  __int64 v8; // rax
  HANDLE v9; // rax
  uintptr_t v10; // rbx
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  v3 = StackSize;
  ThreadId = 0;
  if ( !StartAddress )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  LastError = 0;
  CrtSetReportMode();
  v7 = (_QWORD *)calloc_crt(1, 736);
  if ( v7 )
  {
    v8 = getptd();
    initptd(v7, *(_QWORD *)(v8 + 192));
    v7[18] = StartAddress;
    v7[19] = ArgList;
    v9 = CreateThread(0, v3, threadstart, v7, 4u, &ThreadId);
    v7[1] = v9;
    v10 = (uintptr_t)v9;
    if ( v9 && ResumeThread(v9) != -1 )
      return v10;
    LastError = GetLastError();
  }
  free(v7);
  if ( LastError )
    dosmaperr(LastError);
  return -1;
}

```

## disassembly

```asm
0x18003e2a0  mov     [rsp+arg_8], rbx
0x18003e2a5  mov     [rsp+arg_10], rbp
0x18003e2aa  push    rsi
0x18003e2ab  push    rdi
0x18003e2ac  push    r14
0x18003e2ae  sub     rsp, 30h
0x18003e2b2  mov     r14d, edx
0x18003e2b5  mov     rbp, r8
0x18003e2b8  mov     [rsp+48h+ThreadId], 0
0x18003e2c0  mov     rsi, rcx
0x18003e2c3  test    rcx, rcx
0x18003e2c6  jnz     short loc_18003E2EC
0x18003e2c8  call    _errno
0x18003e2cd  xor     r9d, r9d; LineNo
0x18003e2d0  mov     [rsp+48h+Reserved], rsi; Reserved
0x18003e2d5  xor     r8d, r8d; FileName
0x18003e2d8  xor     edx, edx; FunctionName
0x18003e2da  xor     ecx, ecx; Expression
0x18003e2dc  mov     dword ptr [rax], 16h
0x18003e2e2  call    _invalid_parameter
0x18003e2e7  jmp     loc_18003E378
0x18003e2ec  xor     ebx, ebx
0x18003e2ee  call    _CrtSetReportMode
0x18003e2f3  mov     edx, 2E0h
0x18003e2f8  lea     ecx, [rbx+1]
0x18003e2fb  call    _calloc_crt
0x18003e300  mov     rdi, rax
0x18003e303  test    rax, rax
0x18003e306  jz      short loc_18003E365
0x18003e308  call    _getptd
0x18003e30d  mov     rcx, rdi
0x18003e310  mov     rdx, [rax+0C0h]
0x18003e317  call    _initptd
0x18003e31c  lea     rax, [rsp+48h+ThreadId]
0x18003e321  mov     [rdi+90h], rsi
0x18003e328  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18003e32d  lea     r8, _threadstart; lpStartAddress
0x18003e334  mov     rdx, r14; dwStackSize
0x18003e337  mov     dword ptr [rsp+48h+Reserved], 4; dwCreationFlags
0x18003e33f  mov     r9, rdi; lpParameter
0x18003e342  mov     [rdi+98h], rbp
0x18003e349  xor     ecx, ecx; lpThreadAttributes
0x18003e34b  call    cs:__imp_CreateThread
0x18003e351  mov     [rdi+8], rax
0x18003e355  mov     rbx, rax
0x18003e358  test    rax, rax
0x18003e35b  jnz     short loc_18003E38F
0x18003e35d  call    cs:__imp_GetLastError
0x18003e363  mov     ebx, eax
0x18003e365  mov     rcx, rdi; Block
0x18003e368  call    free
0x18003e36d  test    ebx, ebx
0x18003e36f  jz      short loc_18003E378
0x18003e371  mov     ecx, ebx
0x18003e373  call    _dosmaperr
0x18003e378  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e37c  mov     rbx, [rsp+48h+arg_8]
0x18003e381  mov     rbp, [rsp+48h+arg_10]
0x18003e386  add     rsp, 30h
0x18003e38a  pop     r14
0x18003e38c  pop     rdi
0x18003e38d  pop     rsi
0x18003e38e  retn
0x18003e38f  mov     rcx, rbx; hThread
0x18003e392  call    cs:__imp_ResumeThread
0x18003e398  cmp     eax, 0FFFFFFFFh
0x18003e39b  jz      short loc_18003E35D
0x18003e39d  mov     rax, rbx
0x18003e3a0  jmp     short loc_18003E37C
```
