# EnableFlushTimer

- ea: `0x18001e6d4`
- end: `0x18001e725`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e850`
- `0x18001e8a0`

## callees

- `0x18001e6d4`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001e70d`
- `KERNEL32!SetThreadpoolTimer` at `0x18001e70d`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18002FEA4 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18001e6d4  sub     rsp, 28h
0x18001e6d8  test    rcx, rcx
0x18001e6db  jz      short loc_18001E720
0x18001e6dd  mov     eax, cs:dword_18002FEA4
0x18001e6e3  test    eax, eax
0x18001e6e5  jnz     short loc_18001E720
0x18001e6e7  mov     eax, edx
0x18001e6e9  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18001e6f0  mov     rdx, rax
0x18001e6f3  shr     rdx, 20h
0x18001e6f7  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18001e6fb  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18001e6ff  mov     r9d, 1388h; msWindowLength
0x18001e705  xor     r8d, r8d; msPeriod
0x18001e708  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001e70d  call    cs:__imp_SetThreadpoolTimer
0x18001e713  jmp     short loc_18001E720
0x18001e715  mov     eax, 1
0x18001e71a  xchg    eax, cs:dword_18002FEA4
0x18001e720  add     rsp, 28h
0x18001e724  retn
0x180020934  push    rbp
0x180020936  sub     rsp, 20h
0x18002093a  mov     rbp, rdx
0x18002093d  mov     rax, [rcx]
0x180020940  xor     ecx, ecx
0x180020942  cmp     dword ptr [rax], 0C000000Dh
0x180020948  setz    cl
0x18002094b  mov     eax, ecx
0x18002094d  add     rsp, 20h
0x180020951  pop     rbp
0x180020952  retn
```
