# UpdateWSProcessCounterBlock

- ea: `0x180003800`
- end: `0x1800038a8`
- name: `UpdateWSProcessCounterBlock`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002990`

## pseudocode

```c
__int64 __fastcall UpdateWSProcessCounterBlock(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  *(_DWORD *)(a1 + 4) += *(_DWORD *)(a2 + 128);
  v2 = (unsigned int)dword_180012AB4;
  *(_QWORD *)(a1 + 8) += (*(_QWORD *)(a2 + 48) + *(_QWORD *)(a2 + 40)) / (__int64)(unsigned int)dword_180012AB4;
  *(_QWORD *)(a1 + 16) += *(_QWORD *)(a2 + 40) / v2;
  *(_QWORD *)(a1 + 24) += *(_QWORD *)(a2 + 48) / v2;
  *(_QWORD *)(a1 + 32) += *(_QWORD *)(a2 + 112);
  *(_QWORD *)(a1 + 40) += *(_QWORD *)(a2 + 120);
  *(_QWORD *)(a1 + 48) += *(_QWORD *)(a2 + 136);
  *(_QWORD *)(a1 + 56) += *(_QWORD *)(a2 + 144);
  *(_QWORD *)(a1 + 64) += *(_QWORD *)(a2 + 192);
  *(_QWORD *)(a1 + 72) += *(_QWORD *)(a2 + 184);
  *(_QWORD *)(a1 + 80) += *(_QWORD *)(a2 + 200);
  *(_DWORD *)(a1 + 88) += *(_DWORD *)(a2 + 4);
  *(_DWORD *)(a1 + 112) += *(_DWORD *)(a2 + 160);
  *(_DWORD *)(a1 + 116) += *(_DWORD *)(a2 + 176);
  result = *(unsigned int *)(a2 + 96);
  *(_DWORD *)(a1 + 120) += result;
  return result;
}

```

## disassembly

```asm
0x180003800  mov     eax, [rdx+80h]
0x180003806  mov     r9, rdx
0x180003809  add     [rcx+4], eax
0x18000380c  mov     rax, [rdx+28h]
0x180003810  add     rax, [rdx+30h]
0x180003814  mov     r8d, cs:dword_180012AB4
0x18000381b  cqo
0x18000381d  idiv    r8
0x180003820  add     [rcx+8], rax
0x180003824  mov     rax, [r9+28h]
0x180003828  cqo
0x18000382a  idiv    r8
0x18000382d  add     [rcx+10h], rax
0x180003831  mov     rax, [r9+30h]
0x180003835  cqo
0x180003837  idiv    r8
0x18000383a  add     [rcx+18h], rax
0x18000383e  mov     rax, [r9+70h]
0x180003842  add     [rcx+20h], rax
0x180003846  mov     rax, [r9+78h]
0x18000384a  add     [rcx+28h], rax
0x18000384e  mov     rax, [r9+88h]
0x180003855  add     [rcx+30h], rax
0x180003859  mov     rax, [r9+90h]
0x180003860  add     [rcx+38h], rax
0x180003864  mov     rax, [r9+0C0h]
0x18000386b  add     [rcx+40h], rax
0x18000386f  mov     rax, [r9+0B8h]
0x180003876  add     [rcx+48h], rax
0x18000387a  mov     rax, [r9+0C8h]
0x180003881  add     [rcx+50h], rax
0x180003885  mov     eax, [r9+4]
0x180003889  add     [rcx+58h], eax
0x18000388c  mov     eax, [r9+0A0h]
0x180003893  add     [rcx+70h], eax
0x180003896  mov     eax, [r9+0B0h]
0x18000389d  add     [rcx+74h], eax
0x1800038a0  mov     eax, [r9+60h]
0x1800038a4  add     [rcx+78h], eax
0x1800038a7  retn
```
