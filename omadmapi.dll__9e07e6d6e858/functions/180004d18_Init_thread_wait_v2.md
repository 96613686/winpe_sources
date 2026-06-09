# _Init_thread_wait_v2

- ea: `0x180004d18`
- end: `0x180004d76`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c64`

## callees

- `0x180004d18`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004d5e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004d5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d4a`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180032AA0 )
  {
    qword_180032AA0(&qword_180032A68, &stru_180032A78, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_180032A78);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_180032A78);
  }
}

```

## disassembly

```asm
0x180004d18  sub     rsp, 28h
0x180004d1c  mov     rax, cs:qword_180032AA0
0x180004d23  test    rax, rax
0x180004d26  jz      short loc_180004D43
0x180004d28  or      r8d, 0FFFFFFFFh
0x180004d2c  lea     rdx, stru_180032A78
0x180004d33  lea     rcx, qword_180032A68
0x180004d3a  add     rsp, 28h
0x180004d3e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004d43  lea     rcx, stru_180032A78; lpCriticalSection
0x180004d4a  call    cs:__imp_LeaveCriticalSection
0x180004d50  mov     rcx, cs:hHandle; hHandle
0x180004d57  xor     r8d, r8d; bAlertable
0x180004d5a  lea     edx, [r8+64h]; dwMilliseconds
0x180004d5e  call    cs:__imp_WaitForSingleObjectEx
0x180004d64  lea     rcx, stru_180032A78
0x180004d6b  add     rsp, 28h
0x180004d6f  jmp     cs:__imp_EnterCriticalSection
```
