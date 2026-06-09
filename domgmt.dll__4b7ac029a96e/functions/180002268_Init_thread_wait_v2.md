# _Init_thread_wait_v2

- ea: `0x180002268`
- end: `0x1800022c6`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021b4`

## callees

- `0x180002268`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800022ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800022ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000229a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000229a`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180018610 )
  {
    qword_180018610(&qword_1800185D8, &CriticalSection, 0xFFFFFFFFLL);
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
0x180002268  sub     rsp, 28h
0x18000226c  mov     rax, cs:qword_180018610
0x180002273  test    rax, rax
0x180002276  jz      short loc_180002293
0x180002278  or      r8d, 0FFFFFFFFh
0x18000227c  lea     rdx, CriticalSection
0x180002283  lea     rcx, qword_1800185D8
0x18000228a  add     rsp, 28h
0x18000228e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002293  lea     rcx, CriticalSection; lpCriticalSection
0x18000229a  call    cs:__imp_LeaveCriticalSection
0x1800022a0  mov     rcx, cs:hHandle; hHandle
0x1800022a7  xor     r8d, r8d; bAlertable
0x1800022aa  lea     edx, [r8+64h]; dwMilliseconds
0x1800022ae  call    cs:__imp_WaitForSingleObjectEx
0x1800022b4  lea     rcx, CriticalSection
0x1800022bb  add     rsp, 28h
0x1800022bf  jmp     cs:__imp_EnterCriticalSection
```
