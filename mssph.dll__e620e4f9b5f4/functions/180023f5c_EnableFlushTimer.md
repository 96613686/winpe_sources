# EnableFlushTimer

- ea: `0x180023f5c`
- end: `0x180023fad`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180024110`
- `0x180024160`

## callees

- `0x180023f5c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023f95`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023f95`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180036600 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180023f5c  sub     rsp, 28h
0x180023f60  test    rcx, rcx
0x180023f63  jz      short loc_180023FA8
0x180023f65  mov     eax, cs:dword_180036600
0x180023f6b  test    eax, eax
0x180023f6d  jnz     short loc_180023FA8
0x180023f6f  mov     eax, edx
0x180023f71  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180023f78  mov     rdx, rax
0x180023f7b  shr     rdx, 20h
0x180023f7f  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180023f83  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180023f87  mov     r9d, 1388h; msWindowLength
0x180023f8d  xor     r8d, r8d; msPeriod
0x180023f90  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180023f95  call    cs:__imp_SetThreadpoolTimer
0x180023f9b  jmp     short loc_180023FA8
0x180023f9d  mov     eax, 1
0x180023fa2  xchg    eax, cs:dword_180036600
0x180023fa8  add     rsp, 28h
0x180023fac  retn
0x180026b86  push    rbp
0x180026b88  sub     rsp, 20h
0x180026b8c  mov     rbp, rdx
0x180026b8f  mov     rax, [rcx]
0x180026b92  xor     ecx, ecx
0x180026b94  cmp     dword ptr [rax], 0C000000Dh
0x180026b9a  setz    cl
0x180026b9d  mov     eax, ecx
0x180026b9f  add     rsp, 20h
0x180026ba3  pop     rbp
0x180026ba4  retn
```
