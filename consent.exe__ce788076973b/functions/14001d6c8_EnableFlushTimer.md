# EnableFlushTimer

- ea: `0x14001d6c8`
- end: `0x14001d719`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d870`

## callees

- `0x14001d6c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001d701`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001d701`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_140029BF8 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x14001d6c8  sub     rsp, 28h
0x14001d6cc  test    rcx, rcx
0x14001d6cf  jz      short loc_14001D714
0x14001d6d1  mov     eax, cs:dword_140029BF8
0x14001d6d7  test    eax, eax
0x14001d6d9  jnz     short loc_14001D714
0x14001d6db  mov     eax, edx
0x14001d6dd  imul    rax, 0FFFFFFFFFFFFD8F0h
0x14001d6e4  mov     rdx, rax
0x14001d6e7  shr     rdx, 20h
0x14001d6eb  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x14001d6ef  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x14001d6f3  mov     r9d, 1388h; msWindowLength
0x14001d6f9  xor     r8d, r8d; msPeriod
0x14001d6fc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x14001d701  call    cs:__imp_SetThreadpoolTimer
0x14001d707  jmp     short loc_14001D714
0x14001d709  mov     eax, 1
0x14001d70e  xchg    eax, cs:dword_140029BF8
0x14001d714  add     rsp, 28h
0x14001d718  retn
0x14001e8a1  push    rbp
0x14001e8a3  sub     rsp, 20h
0x14001e8a7  mov     rbp, rdx
0x14001e8aa  mov     rax, [rcx]
0x14001e8ad  xor     ecx, ecx
0x14001e8af  cmp     dword ptr [rax], 0C000000Dh
0x14001e8b5  setz    cl
0x14001e8b8  mov     eax, ecx
0x14001e8ba  add     rsp, 20h
0x14001e8be  pop     rbp
0x14001e8bf  retn
```
