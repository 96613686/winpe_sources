# _Init_thread_wait_v2

- ea: `0x18000246c`
- end: `0x1800024ca`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023b8`

## callees

- `0x18000246c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000249e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000249e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800024b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800024b2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18001F318 )
  {
    qword_18001F318(&qword_18001F2E0, &CriticalSection, 0xFFFFFFFFLL);
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
0x18000246c  sub     rsp, 28h
0x180002470  mov     rax, cs:qword_18001F318
0x180002477  test    rax, rax
0x18000247a  jz      short loc_180002497
0x18000247c  or      r8d, 0FFFFFFFFh
0x180002480  lea     rdx, CriticalSection
0x180002487  lea     rcx, qword_18001F2E0
0x18000248e  add     rsp, 28h
0x180002492  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002497  lea     rcx, CriticalSection; lpCriticalSection
0x18000249e  call    cs:__imp_LeaveCriticalSection
0x1800024a4  mov     rcx, cs:hHandle; hHandle
0x1800024ab  xor     r8d, r8d; bAlertable
0x1800024ae  lea     edx, [r8+64h]; dwMilliseconds
0x1800024b2  call    cs:__imp_WaitForSingleObjectEx
0x1800024b8  lea     rcx, CriticalSection
0x1800024bf  add     rsp, 28h
0x1800024c3  jmp     cs:__imp_EnterCriticalSection
```
