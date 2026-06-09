# _Init_thread_wait_v2

- ea: `0x1800029f8`
- end: `0x180002a56`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002944`

## callees

- `0x1800029f8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a4f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002a3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a2a`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18001B6B0 )
  {
    qword_18001B6B0(&qword_18001B678, &stru_18001B688, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_18001B688);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_18001B688);
  }
}

```

## disassembly

```asm
0x1800029f8  sub     rsp, 28h
0x1800029fc  mov     rax, cs:qword_18001B6B0
0x180002a03  test    rax, rax
0x180002a06  jz      short loc_180002A23
0x180002a08  or      r8d, 0FFFFFFFFh
0x180002a0c  lea     rdx, stru_18001B688
0x180002a13  lea     rcx, qword_18001B678
0x180002a1a  add     rsp, 28h
0x180002a1e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002a23  lea     rcx, stru_18001B688; lpCriticalSection
0x180002a2a  call    cs:__imp_LeaveCriticalSection
0x180002a30  mov     rcx, cs:hHandle; hHandle
0x180002a37  xor     r8d, r8d; bAlertable
0x180002a3a  lea     edx, [r8+64h]; dwMilliseconds
0x180002a3e  call    cs:__imp_WaitForSingleObjectEx
0x180002a44  lea     rcx, stru_18001B688
0x180002a4b  add     rsp, 28h
0x180002a4f  jmp     cs:__imp_EnterCriticalSection
```
