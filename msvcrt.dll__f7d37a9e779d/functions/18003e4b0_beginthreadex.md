# _beginthreadex

- ea: `0x18003e4b0`
- end: `0x18003e5b1`
- name: `_beginthreadex`
- size: `257`
- prototype: `uintptr_t __cdecl(void *Security, unsigned int StackSize, _beginthreadex_proc_type StartAddress, void *ArgList, unsigned int InitFlag, unsigned int *ThrdAddr)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d70`
- `0x180007ea8`
- `0x180007f00`
- `0x18001d300`
- `0x18001d50c`
- `0x18002f050`
- `0x18003e048`
- `0x18003e0fc`
- `0x18003e4b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e587`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e57c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e57c`

## pseudocode

```c
uintptr_t __cdecl beginthreadex(
        void *Security,
        unsigned int StackSize,
        _beginthreadex_proc_type StartAddress,
        void *ArgList,
        unsigned int InitFlag,
        unsigned int *ThrdAddr)
{
  SIZE_T v6; // r14
  DWORD LastError; // ebx
  _QWORD *v11; // rdi
  __int64 v12; // rax
  unsigned int *v13; // rcx
  DWORD *lpThreadId; // r8
  DWORD v15; // eax
  bool v16; // zf
  uintptr_t result; // rax
  int v18; // [rsp+80h] [rbp+18h] BYREF

  v6 = StackSize;
  v18 = 0;
  if ( !StartAddress )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  LastError = 0;
  CrtSetReportMode();
  v11 = (_QWORD *)calloc_crt(1, 736);
  if ( !v11 )
    goto LABEL_8;
  v12 = getptd();
  initptd(v11, *(_QWORD *)(v12 + 192));
  v13 = ThrdAddr;
  lpThreadId = (DWORD *)&v18;
  v15 = InitFlag;
  v16 = ThrdAddr == 0;
  v11[18] = StartAddress;
  if ( !v16 )
    lpThreadId = v13;
  v11[19] = ArgList;
  v11[1] = -1;
  result = (uintptr_t)CreateThread((LPSECURITY_ATTRIBUTES)Security, v6, threadstartex, v11, v15, lpThreadId);
  if ( !result )
  {
    LastError = GetLastError();
LABEL_8:
    free(v11);
    if ( LastError )
      dosmaperr(LastError);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003e4b0  mov     rax, rsp
0x18003e4b3  push    rbx
0x18003e4b4  push    rbp
0x18003e4b5  push    rsi
0x18003e4b6  push    rdi
0x18003e4b7  push    r14
0x18003e4b9  push    r15
0x18003e4bb  sub     rsp, 38h
0x18003e4bf  mov     r14d, edx
0x18003e4c2  mov     rbp, r9
0x18003e4c5  mov     dword ptr [rax+18h], 0
0x18003e4cc  mov     rsi, r8
0x18003e4cf  mov     r15, rcx
0x18003e4d2  test    r8, r8
0x18003e4d5  jnz     short loc_18003E4FF
0x18003e4d7  call    _errno
0x18003e4dc  xor     r9d, r9d; LineNo
0x18003e4df  mov     [rsp+68h+Reserved], rsi; Reserved
0x18003e4e4  xor     r8d, r8d; FileName
0x18003e4e7  xor     edx, edx; FunctionName
0x18003e4e9  xor     ecx, ecx; Expression
0x18003e4eb  mov     dword ptr [rax], 16h
0x18003e4f1  call    _invalid_parameter
0x18003e4f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e4fa  jmp     loc_18003E5A4
0x18003e4ff  xor     ebx, ebx
0x18003e501  call    _CrtSetReportMode
0x18003e506  mov     edx, 2E0h
0x18003e50b  lea     ecx, [rbx+1]
0x18003e50e  call    _calloc_crt
0x18003e513  mov     rdi, rax
0x18003e516  test    rax, rax
0x18003e519  jz      short loc_18003E58F
0x18003e51b  call    _getptd
0x18003e520  mov     rcx, rdi
0x18003e523  mov     rdx, [rax+0C0h]
0x18003e52a  call    _initptd
0x18003e52f  mov     rcx, [rsp+68h+ThrdAddr]
0x18003e537  lea     r8, [rsp+68h+arg_10]
0x18003e53f  mov     eax, [rsp+68h+InitFlag]
0x18003e546  test    rcx, rcx
0x18003e549  mov     rdx, r14; dwStackSize
0x18003e54c  mov     [rdi+90h], rsi
0x18003e553  cmovnz  r8, rcx
0x18003e557  mov     [rdi+98h], rbp
0x18003e55e  mov     [rsp+68h+lpThreadId], r8; lpThreadId
0x18003e563  mov     r9, rdi; lpParameter
0x18003e566  lea     r8, _threadstartex; lpStartAddress
0x18003e56d  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18003e575  mov     rcx, r15; lpThreadAttributes
0x18003e578  mov     dword ptr [rsp+68h+Reserved], eax; dwCreationFlags
0x18003e57c  call    cs:__imp_CreateThread
0x18003e582  test    rax, rax
0x18003e585  jnz     short loc_18003E5A4
0x18003e587  call    cs:__imp_GetLastError
0x18003e58d  mov     ebx, eax
0x18003e58f  mov     rcx, rdi; Block
0x18003e592  call    free
0x18003e597  test    ebx, ebx
0x18003e599  jz      short loc_18003E5A2
0x18003e59b  mov     ecx, ebx
0x18003e59d  call    _dosmaperr
0x18003e5a2  xor     eax, eax
0x18003e5a4  add     rsp, 38h
0x18003e5a8  pop     r15
0x18003e5aa  pop     r14
0x18003e5ac  pop     rdi
0x18003e5ad  pop     rsi
0x18003e5ae  pop     rbp
0x18003e5af  pop     rbx
0x18003e5b0  retn
```
