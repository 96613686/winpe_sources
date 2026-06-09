# CscUtil_SetThreadPriorityTrace(void *,int,int)

- ea: `0x180018c90`
- end: `0x180018dbb`
- name: `?CscUtil_SetThreadPriorityTrace@@YAJPEAXHH@Z`
- size: `299`
- prototype: `__int64 __fastcall(HANDLE hThread, int nPriority, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800189a0`

## callees

- `0x180018c90`
- `0x18002f10c`
- `0x180069038`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180018ce0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180018ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d81`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018d23`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018d79`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018d23`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180018d79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018d70`

## pseudocode

```c
__int64 __fastcall CscUtil_SetThreadPriorityTrace(HANDLE hThread, int nPriority, int a3)
{
  unsigned int Error; // ebp
  char v7; // r14
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  __int64 CurrentThreadId; // r9
  char v12; // al
  HANDLE v13; // rax
  int v14; // ebx
  DWORD v15; // eax
  int v16; // [rsp+28h] [rbp-30h]

  Error = 0;
  v7 = 89;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    CurrentThreadId = GetCurrentThreadId();
    v12 = 89;
    if ( !a3 )
      v12 = 78;
    WPP_SF_DDc(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      WPP_7967f24143133d59f1b33f7a742017bc_Traceguids,
      CurrentThreadId,
      ThreadPriority,
      v12);
  }
  if ( !SetThreadPriority(hThread, nPriority) )
    Error = ResultFromLastError();
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v13 = GetCurrentThread();
    v14 = GetThreadPriority(v13);
    v15 = GetCurrentThreadId();
    if ( !a3 )
      v7 = 78;
    LOBYTE(v16) = v7;
    WPP_SF_DDc(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids, v15, v14, v16);
  }
  return Error;
}

```

## disassembly

```asm
0x180018c90  push    rbx
0x180018c92  push    rbp
0x180018c93  push    r13
0x180018c95  push    r14
0x180018c97  push    r15
0x180018c99  sub     rsp, 30h
0x180018c9d  mov     [rsp+58h+arg_0], rsi
0x180018ca2  mov     r15d, r8d
0x180018ca5  mov     [rsp+58h+arg_8], rdi
0x180018caa  mov     rsi, rcx
0x180018cad  mov     [rsp+58h+arg_10], r12
0x180018cb2  mov     edi, edx
0x180018cb4  xor     ebp, ebp
0x180018cb6  mov     rax, cs:WPP_GLOBAL_Control
0x180018cbd  lea     r12, WPP_GLOBAL_Control
0x180018cc4  mov     r14d, 59h ; 'Y'
0x180018cca  mov     r13d, 4Eh ; 'N'
0x180018cd0  cmp     rax, r12
0x180018cd3  jz      short loc_180018CDB
0x180018cd5  test    byte ptr [rax+1Ch], 20h
0x180018cd9  jnz     short loc_180018D1A
0x180018cdb  mov     edx, edi; nPriority
0x180018cdd  mov     rcx, rsi; hThread
0x180018ce0  call    cs:__imp_SetThreadPriority
0x180018ce6  mov     rdi, [rsp+58h+arg_8]
0x180018ceb  mov     rsi, [rsp+58h+arg_0]
0x180018cf0  test    eax, eax
0x180018cf2  jz      short loc_180018D67
0x180018cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cfb  cmp     rcx, r12
0x180018cfe  mov     r12, [rsp+58h+arg_10]
0x180018d03  jz      short loc_180018D0B
0x180018d05  test    byte ptr [rcx+1Ch], 20h
0x180018d09  jnz     short loc_180018D70
0x180018d0b  mov     eax, ebp
0x180018d0d  add     rsp, 30h
0x180018d11  pop     r15
0x180018d13  pop     r14
0x180018d15  pop     r13
0x180018d17  pop     rbp
0x180018d18  pop     rbx
0x180018d19  retn
0x180018d1a  call    cs:__imp_GetCurrentThread
0x180018d20  mov     rcx, rax; hThread
0x180018d23  call    cs:__imp_GetThreadPriority
0x180018d29  mov     ebx, eax
0x180018d2b  call    cs:__imp_GetCurrentThreadId
0x180018d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d38  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018d3f  mov     r9d, eax
0x180018d42  test    r15d, r15d
0x180018d45  mov     eax, r14d
0x180018d48  mov     edx, 6Bh ; 'k'
0x180018d4d  cmovz   eax, r13d
0x180018d51  mov     rcx, [rcx+10h]
0x180018d55  mov     byte ptr [rsp+58h+var_30], al
0x180018d59  mov     [rsp+58h+var_38], ebx
0x180018d5d  call    WPP_SF_DDc
0x180018d62  jmp     loc_180018CDB
0x180018d67  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180018d6c  mov     ebp, eax
0x180018d6e  jmp     short loc_180018CF4
0x180018d70  call    cs:__imp_GetCurrentThread
0x180018d76  mov     rcx, rax; hThread
0x180018d79  call    cs:__imp_GetThreadPriority
0x180018d7f  mov     ebx, eax
0x180018d81  call    cs:__imp_GetCurrentThreadId
0x180018d87  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d8e  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180018d95  test    r15d, r15d
0x180018d98  mov     edx, 6Ch ; 'l'
0x180018d9d  mov     r9d, eax
0x180018da0  cmovz   r14d, r13d
0x180018da4  mov     rcx, [rcx+10h]
0x180018da8  mov     byte ptr [rsp+58h+var_30], r14b
0x180018dad  mov     [rsp+58h+var_38], ebx
0x180018db1  call    WPP_SF_DDc
0x180018db6  jmp     loc_180018D0B
```
