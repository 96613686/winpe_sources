# EnableFlushTimer

- ea: `0x180046bf0`
- end: `0x180046c41`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180046e20`
- `0x180046e70`

## callees

- `0x180046bf0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046c29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046c29`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180061938 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180046bf0  sub     rsp, 28h
0x180046bf4  test    rcx, rcx
0x180046bf7  jz      short loc_180046C3C
0x180046bf9  mov     eax, cs:dword_180061938
0x180046bff  test    eax, eax
0x180046c01  jnz     short loc_180046C3C
0x180046c03  mov     eax, edx
0x180046c05  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180046c0c  mov     rdx, rax
0x180046c0f  shr     rdx, 20h
0x180046c13  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180046c17  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180046c1b  mov     r9d, 1388h; msWindowLength
0x180046c21  xor     r8d, r8d; msPeriod
0x180046c24  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180046c29  call    cs:__imp_SetThreadpoolTimer
0x180046c2f  jmp     short loc_180046C3C
0x180046c31  mov     eax, 1
0x180046c36  xchg    eax, cs:dword_180061938
0x180046c3c  add     rsp, 28h
0x180046c40  retn
0x180048015  push    rbp
0x180048017  sub     rsp, 20h
0x18004801b  mov     rbp, rdx
0x18004801e  mov     rax, [rcx]
0x180048021  xor     ecx, ecx
0x180048023  cmp     dword ptr [rax], 0C000000Dh
0x180048029  setz    cl
0x18004802c  mov     eax, ecx
0x18004802e  add     rsp, 20h
0x180048032  pop     rbp
0x180048033  retn
```
