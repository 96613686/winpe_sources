# _Init_thread_wait_v2

- ea: `0x180001ce8`
- end: `0x180001d46`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c34`

## callees

- `0x180001ce8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001d2e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001d2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d3f`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1800283F0 )
  {
    qword_1800283F0(&qword_1800283B8, &CriticalSection, 0xFFFFFFFFLL);
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
0x180001ce8  sub     rsp, 28h
0x180001cec  mov     rax, cs:qword_1800283F0
0x180001cf3  test    rax, rax
0x180001cf6  jz      short loc_180001D13
0x180001cf8  or      r8d, 0FFFFFFFFh
0x180001cfc  lea     rdx, CriticalSection
0x180001d03  lea     rcx, qword_1800283B8
0x180001d0a  add     rsp, 28h
0x180001d0e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001d13  lea     rcx, CriticalSection; lpCriticalSection
0x180001d1a  call    cs:__imp_LeaveCriticalSection
0x180001d20  mov     rcx, cs:hHandle; hHandle
0x180001d27  xor     r8d, r8d; bAlertable
0x180001d2a  lea     edx, [r8+64h]; dwMilliseconds
0x180001d2e  call    cs:__imp_WaitForSingleObjectEx
0x180001d34  lea     rcx, CriticalSection
0x180001d3b  add     rsp, 28h
0x180001d3f  jmp     cs:__imp_EnterCriticalSection
```
