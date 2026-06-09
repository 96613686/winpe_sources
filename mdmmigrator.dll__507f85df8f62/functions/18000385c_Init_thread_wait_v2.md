# _Init_thread_wait_v2

- ea: `0x18000385c`
- end: `0x1800038ba`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037a8`

## callees

- `0x18000385c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000388e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000388e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800038b3`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18002B5F0 )
  {
    qword_18002B5F0(&qword_18002B5B8, &stru_18002B5C8, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_18002B5C8);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_18002B5C8);
  }
}

```

## disassembly

```asm
0x18000385c  sub     rsp, 28h
0x180003860  mov     rax, cs:qword_18002B5F0
0x180003867  test    rax, rax
0x18000386a  jz      short loc_180003887
0x18000386c  or      r8d, 0FFFFFFFFh
0x180003870  lea     rdx, stru_18002B5C8
0x180003877  lea     rcx, qword_18002B5B8
0x18000387e  add     rsp, 28h
0x180003882  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003887  lea     rcx, stru_18002B5C8; lpCriticalSection
0x18000388e  call    cs:__imp_LeaveCriticalSection
0x180003894  mov     rcx, cs:hHandle; hHandle
0x18000389b  xor     r8d, r8d; bAlertable
0x18000389e  lea     edx, [r8+64h]; dwMilliseconds
0x1800038a2  call    cs:__imp_WaitForSingleObjectEx
0x1800038a8  lea     rcx, stru_18002B5C8
0x1800038af  add     rsp, 28h
0x1800038b3  jmp     cs:__imp_EnterCriticalSection
```
