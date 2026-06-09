# sub_15CD5D0

- ea: `0x15cd5d0`
- end: `0x15cd612`
- name: `sub_15CD5D0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall sub_15CD5D0(_BYTE *a1, _BYTE *a2, _DWORD *a3, _DWORD *a4, __int64 a5, __int64 a6, __int64 a7)
{
  bool v7; // cf
  _DWORD *v8; // rax
  char v9; // bh
  _DWORD *v11; // [rsp+0h] [rbp-1C6h]
  _UNKNOWN *retaddr; // [rsp+1CEh] [rbp+8h]

  *a3 += (_DWORD)v8 + v7;
  a2[285213172] += v9;
  *v8 += (_DWORD)v8;
  v7 = __CFADD__((_DWORD)v8, *v8);
  *v8 += (_DWORD)v8;
  *v11 += (_DWORD)v8 + v7;
  *a1 += (_BYTE)a4;
  LOBYTE(v8) = *(_BYTE *)v8 + (_BYTE)v8;
  BYTE2(qword_321FFC0[8]) = BYTE1(v8);
  *((_BYTE *)v8 + 115) += BYTE1(v8);
  v7 = __CFADD__((_DWORD)v8, *v8);
  *v8 += (_DWORD)v8;
  *a3 += (_DWORD)v8 + v7;
  *((_BYTE *)v8 + 126) += (_BYTE)a3;
  v7 = __CFADD__((_DWORD)v8, *v8);
  *v8 += (_DWORD)v8;
  *a4 += (_DWORD)v8 + v7;
  v7 = __CFADD__((_DWORD)v8, *v8);
  *v8 += (_DWORD)v8;
  *(_DWORD *)":TransferVideoFrameInternal_::_1_::dtor$6\n" += (_DWORD)v8 + v7;
  *a2 += (_BYTE)a4;
  return MK_FP((_WORD)retaddr, retaddr)(a1, a2, a3);
}

```

## disassembly

```asm
0x15cd5d0  enter   1C6h, 0
0x15cd5d4  adc     [rdx], eax
0x15cd5d6  add     [rsi+110001F4h], bh
0x15cd5dc  add     [rax], eax
0x15cd5de  pop     rbx
0x15cd5df  add     [rax], eax
0x15cd5e1  adc     [rbx], eax
0x15cd5e3  add     [rdi], cl
0x15cd5e5  mov     esp, 11000122h
0x15cd5ea  add     al, [rax]
0x15cd5ec  mov     ebx, 1110001h
0x15cd5f2  add     byte ptr ds:dword_2110001[rbx], ah
0x15cd5f8  add     [rax+73h], ah
0x15cd5fb  add     [rax], eax
0x15cd5fd  adc     [rdx], eax
0x15cd5ff  add     [rax+7Eh], dl
0x15cd602  add     [rax], eax
0x15cd604  adc     [rcx], eax
0x15cd606  add     dh, bh
0x15cd608  add     [rax], eax
0x15cd60a  adc     [rbx], eax
0x15cd60c  add     [rsi], cl
0x15cd60e  retf    1
```
