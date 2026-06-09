# PerfpUpdateSection

- ea: `0x180011bd8`
- end: `0x180011c73`
- name: `PerfpUpdateSection`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180011d10`

## pseudocode

```c
__int64 __fastcall PerfpUpdateSection(__int64 a1)
{
  __int64 result; // rax

  *(_QWORD *)(*(_QWORD *)(a1 + 432) + 64LL) = *(_QWORD *)(a1 + 440);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 72LL) = *(_DWORD *)(a1 + 448);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 76LL) = *(_DWORD *)(a1 + 452);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 80LL) = *(_DWORD *)(a1 + 456);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 84LL) = *(_DWORD *)(a1 + 460);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 88LL) = *(_DWORD *)(a1 + 464);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 92LL) = *(_DWORD *)(a1 + 468);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 96LL) = *(_DWORD *)(a1 + 472);
  result = *(unsigned int *)(a1 + 476);
  *(_DWORD *)(*(_QWORD *)(a1 + 432) + 100LL) = result;
  return result;
}

```

## disassembly

```asm
0x180011bd8  mov     rdx, [rcx+1B0h]
0x180011bdf  mov     r8, rcx
0x180011be2  mov     rax, [rcx+1B8h]
0x180011be9  mov     [rdx+40h], rax
0x180011bed  mov     rdx, [rcx+1B0h]
0x180011bf4  mov     eax, [rcx+1C0h]
0x180011bfa  mov     [rdx+48h], eax
0x180011bfd  mov     rdx, [rcx+1B0h]
0x180011c04  mov     eax, [rcx+1C4h]
0x180011c0a  mov     [rdx+4Ch], eax
0x180011c0d  mov     eax, [rcx+1C8h]
0x180011c13  mov     rdx, [rcx+1B0h]
0x180011c1a  mov     [rdx+50h], eax
0x180011c1d  mov     rcx, [rcx+1B0h]
0x180011c24  mov     eax, [r8+1CCh]
0x180011c2b  mov     [rcx+54h], eax
0x180011c2e  mov     rcx, [r8+1B0h]
0x180011c35  mov     eax, [r8+1D0h]
0x180011c3c  mov     [rcx+58h], eax
0x180011c3f  mov     rcx, [r8+1B0h]
0x180011c46  mov     eax, [r8+1D4h]
0x180011c4d  mov     [rcx+5Ch], eax
0x180011c50  mov     rcx, [r8+1B0h]
0x180011c57  mov     eax, [r8+1D8h]
0x180011c5e  mov     [rcx+60h], eax
0x180011c61  mov     rcx, [r8+1B0h]
0x180011c68  mov     eax, [r8+1DCh]
0x180011c6f  mov     [rcx+64h], eax
0x180011c72  retn
```
