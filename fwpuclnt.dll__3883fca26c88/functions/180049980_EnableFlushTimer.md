# EnableFlushTimer

- ea: `0x180049980`
- end: `0x1800499d8`
- name: `EnableFlushTimer`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180049b50`

## callees

- `0x180049980`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800499b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800499b9`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18007C3C0 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180049980  sub     rsp, 28h
0x180049984  test    rcx, rcx
0x180049987  jz      short loc_1800499D2
0x180049989  mov     eax, cs:dword_18007C3C0
0x18004998f  test    eax, eax
0x180049991  jnz     short loc_1800499D2
0x180049993  mov     eax, edx
0x180049995  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18004999c  mov     rdx, rax
0x18004999f  shr     rdx, 20h
0x1800499a3  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800499a7  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800499ab  mov     r9d, 1388h; msWindowLength
0x1800499b1  xor     r8d, r8d; msPeriod
0x1800499b4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800499b9  call    cs:__imp_SetThreadpoolTimer
0x1800499c0  nop     dword ptr [rax+rax+00h]
0x1800499c5  jmp     short loc_1800499D2
0x1800499c7  mov     eax, 1
0x1800499cc  xchg    eax, cs:dword_18007C3C0
0x1800499d2  add     rsp, 28h
0x1800499d6  retn
0x18004a244  push    rbp
0x18004a246  sub     rsp, 20h
0x18004a24a  mov     rbp, rdx
0x18004a24d  mov     rax, [rcx]
0x18004a250  xor     ecx, ecx
0x18004a252  cmp     dword ptr [rax], 0C000000Dh
0x18004a258  setz    cl
0x18004a25b  mov     eax, ecx
0x18004a25d  add     rsp, 20h
0x18004a261  pop     rbp
0x18004a262  retn
```
