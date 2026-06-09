# _Init_thread_wait_v2

- ea: `0x14000246c`
- end: `0x1400024ca`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023b8`

## callees

- `0x14000246c`
- `0x140010010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x1400024b2`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400024b2`
- `KERNEL32!EnterCriticalSection` at `0x1400024c3`
- `KERNEL32!LeaveCriticalSection` at `0x14000249e`
- `KERNEL32!LeaveCriticalSection` at `0x14000249e`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_140016550 )
  {
    qword_140016550(&qword_140016518, &CriticalSection, 0xFFFFFFFFLL);
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
0x14000246c  sub     rsp, 28h
0x140002470  mov     rax, cs:qword_140016550
0x140002477  test    rax, rax
0x14000247a  jz      short loc_140002497
0x14000247c  or      r8d, 0FFFFFFFFh
0x140002480  lea     rdx, CriticalSection
0x140002487  lea     rcx, qword_140016518
0x14000248e  add     rsp, 28h
0x140002492  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140002497  lea     rcx, CriticalSection; lpCriticalSection
0x14000249e  call    cs:__imp_LeaveCriticalSection
0x1400024a4  mov     rcx, cs:hHandle; hHandle
0x1400024ab  xor     r8d, r8d; bAlertable
0x1400024ae  lea     edx, [r8+64h]; dwMilliseconds
0x1400024b2  call    cs:__imp_WaitForSingleObjectEx
0x1400024b8  lea     rcx, CriticalSection
0x1400024bf  add     rsp, 28h
0x1400024c3  jmp     cs:__imp_EnterCriticalSection
```
