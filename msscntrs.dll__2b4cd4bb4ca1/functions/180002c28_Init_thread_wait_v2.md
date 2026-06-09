# _Init_thread_wait_v2

- ea: `0x180002c28`
- end: `0x180002c86`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b74`

## callees

- `0x180002c28`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c7f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002c6e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002c6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c5a`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180021DD0 )
  {
    qword_180021DD0(&qword_180021D98, &stru_180021DA8, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_180021DA8);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_180021DA8);
  }
}

```

## disassembly

```asm
0x180002c28  sub     rsp, 28h
0x180002c2c  mov     rax, cs:qword_180021DD0
0x180002c33  test    rax, rax
0x180002c36  jz      short loc_180002C53
0x180002c38  or      r8d, 0FFFFFFFFh
0x180002c3c  lea     rdx, stru_180021DA8
0x180002c43  lea     rcx, qword_180021D98
0x180002c4a  add     rsp, 28h
0x180002c4e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002c53  lea     rcx, stru_180021DA8; lpCriticalSection
0x180002c5a  call    cs:__imp_LeaveCriticalSection
0x180002c60  mov     rcx, cs:hHandle; hHandle
0x180002c67  xor     r8d, r8d; bAlertable
0x180002c6a  lea     edx, [r8+64h]; dwMilliseconds
0x180002c6e  call    cs:__imp_WaitForSingleObjectEx
0x180002c74  lea     rcx, stru_180021DA8
0x180002c7b  add     rsp, 28h
0x180002c7f  jmp     cs:__imp_EnterCriticalSection
```
