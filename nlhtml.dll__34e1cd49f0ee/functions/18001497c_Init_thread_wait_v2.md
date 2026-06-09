# _Init_thread_wait_v2

- ea: `0x18001497c`
- end: `0x1800149da`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800148c8`

## callees

- `0x18001497c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800149c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800149c2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18003DF90 )
  {
    qword_18003DF90(&qword_18003DF58, &CriticalSection, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&CriticalSection);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x18001497c  sub     rsp, 28h
0x180014980  mov     rax, cs:qword_18003DF90
0x180014987  test    rax, rax
0x18001498a  jz      short loc_1800149A7
0x18001498c  or      r8d, 0FFFFFFFFh
0x180014990  lea     rdx, CriticalSection
0x180014997  lea     rcx, qword_18003DF58
0x18001499e  add     rsp, 28h
0x1800149a2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800149a7  lea     rcx, CriticalSection; lpCriticalSection
0x1800149ae  call    cs:__imp_LeaveCriticalSection
0x1800149b4  mov     rcx, cs:hHandle; hHandle
0x1800149bb  xor     r8d, r8d; bAlertable
0x1800149be  lea     edx, [r8+64h]; dwMilliseconds
0x1800149c2  call    cs:__imp_WaitForSingleObjectEx
0x1800149c8  lea     rcx, CriticalSection
0x1800149cf  add     rsp, 28h
0x1800149d3  jmp     cs:__imp_EnterCriticalSection
```
