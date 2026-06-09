# _Init_thread_wait_v2

- ea: `0x180002d58`
- end: `0x180002db6`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ca4`

## callees

- `0x180002d58`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002daf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002d9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002d9e`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180020370 )
  {
    qword_180020370(&qword_180020338, &CriticalSection, 0xFFFFFFFFLL);
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
0x180002d58  sub     rsp, 28h
0x180002d5c  mov     rax, cs:qword_180020370
0x180002d63  test    rax, rax
0x180002d66  jz      short loc_180002D83
0x180002d68  or      r8d, 0FFFFFFFFh
0x180002d6c  lea     rdx, CriticalSection
0x180002d73  lea     rcx, qword_180020338
0x180002d7a  add     rsp, 28h
0x180002d7e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002d83  lea     rcx, CriticalSection; lpCriticalSection
0x180002d8a  call    cs:__imp_LeaveCriticalSection
0x180002d90  mov     rcx, cs:hHandle; hHandle
0x180002d97  xor     r8d, r8d; bAlertable
0x180002d9a  lea     edx, [r8+64h]; dwMilliseconds
0x180002d9e  call    cs:__imp_WaitForSingleObjectEx
0x180002da4  lea     rcx, CriticalSection
0x180002dab  add     rsp, 28h
0x180002daf  jmp     cs:__imp_EnterCriticalSection
```
