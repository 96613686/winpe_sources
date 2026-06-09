# EnableFlushTimer

- ea: `0x180003f54`
- end: `0x180003fa5`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800040d0`
- `0x180004120`

## callees

- `0x180003f54`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180003f8d`
- `KERNEL32!SetThreadpoolTimer` at `0x180003f8d`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18000A720 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180003f54  sub     rsp, 28h
0x180003f58  test    rcx, rcx
0x180003f5b  jz      short loc_180003FA0
0x180003f5d  mov     eax, cs:dword_18000A720
0x180003f63  test    eax, eax
0x180003f65  jnz     short loc_180003FA0
0x180003f67  mov     eax, edx
0x180003f69  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180003f70  mov     rdx, rax
0x180003f73  shr     rdx, 20h
0x180003f77  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180003f7b  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180003f7f  mov     r9d, 1388h; msWindowLength
0x180003f85  xor     r8d, r8d; msPeriod
0x180003f88  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180003f8d  call    cs:__imp_SetThreadpoolTimer
0x180003f93  jmp     short loc_180003FA0
0x180003f95  mov     eax, 1
0x180003f9a  xchg    eax, cs:dword_18000A720
0x180003fa0  add     rsp, 28h
0x180003fa4  retn
0x1800052b6  push    rbp
0x1800052b8  sub     rsp, 20h
0x1800052bc  mov     rbp, rdx
0x1800052bf  mov     rax, [rcx]
0x1800052c2  xor     ecx, ecx
0x1800052c4  cmp     dword ptr [rax], 0C000000Dh
0x1800052ca  setz    cl
0x1800052cd  mov     eax, ecx
0x1800052cf  add     rsp, 20h
0x1800052d3  pop     rbp
0x1800052d4  retn
```
