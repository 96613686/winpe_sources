# CodeFromRgbQ(x)

- ea: `0x10009892`
- end: `0x10009938`
- name: `_CodeFromRgbQ@4`
- size: `166`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x10009940`
- `0x10009bd0`
- `0x10009e60`
- `0x1000a0f0`
- `0x1000a1d0`
- `0x1000a2b0`
- `0x1000a390`
- `0x1000a470`
- `0x1000a4e0`

## callees

- `0x10009869`

## pseudocode

```c
unsigned __int8 *__thiscall CodeFromRgbQ(unsigned __int8 *this, unsigned __int8 *a2)
{
  unsigned __int8 v3; // bh
  unsigned __int8 v4; // bl
  unsigned __int8 v5; // al
  unsigned __int8 *result; // eax
  int v7; // edx
  int v8; // [esp+Ch] [ebp-Ch]
  unsigned __int8 v9; // [esp+17h] [ebp-1h]

  v9 = ((int (*)(void))YFromRgbQ)();
  *a2 = v9;
  v3 = YFromRgbQ(this + 4);
  a2[1] = v3;
  v4 = YFromRgbQ(this + 8);
  a2[2] = v4;
  v5 = YFromRgbQ(this + 12);
  a2[3] = v5;
  v8 = v9 + v3 + v4 + v5;
  result = a2;
  v7 = this[14];
  a2[4] = (*this + this[4] + this[8] + this[12] - v8 + 4) >> 3;
  a2[5] = (this[2] + this[6] + this[10] + v7 - v8 + 4) >> 3;
  return result;
}

```

## disassembly

```asm
0x10009892  mov     edi, edi
0x10009894  push    ebp
0x10009895  mov     ebp, esp
0x10009897  sub     esp, 0Ch
0x1000989a  push    ebx
0x1000989b  push    esi
0x1000989c  push    edi
0x1000989d  mov     esi, ecx
0x1000989f  call    _YFromRgbQ@4; YFromRgbQ(x)
0x100098a4  mov     edi, [ebp+arg_0]
0x100098a7  lea     ecx, [esi+4]
0x100098aa  mov     [ebp+var_1], al
0x100098ad  mov     [edi], al
0x100098af  call    _YFromRgbQ@4; YFromRgbQ(x)
0x100098b4  mov     bh, al
0x100098b6  lea     ecx, [esi+8]
0x100098b9  mov     [edi+1], bh
0x100098bc  call    _YFromRgbQ@4; YFromRgbQ(x)
0x100098c1  mov     bl, al
0x100098c3  lea     ecx, [esi+0Ch]
0x100098c6  mov     eax, edi
0x100098c8  mov     [eax+2], bl
0x100098cb  call    _YFromRgbQ@4; YFromRgbQ(x)
0x100098d0  mov     ecx, edi
0x100098d2  movzx   edx, al
0x100098d5  mov     [ecx+3], al
0x100098d8  movzx   ecx, byte ptr [esi+0Ch]
0x100098dc  movzx   eax, bl
0x100098df  add     edx, eax
0x100098e1  movzx   eax, bh
0x100098e4  add     edx, eax
0x100098e6  mov     ebx, esi
0x100098e8  movzx   eax, [ebp+var_1]
0x100098ec  add     edx, eax
0x100098ee  movzx   eax, byte ptr [esi+8]
0x100098f2  add     ecx, eax
0x100098f4  mov     [ebp+var_C], edx
0x100098f7  movzx   eax, byte ptr [ebx+4]
0x100098fb  add     ecx, eax
0x100098fd  movzx   eax, byte ptr [ebx]
0x10009900  add     ecx, eax
0x10009902  mov     eax, edi
0x10009904  sub     ecx, edx
0x10009906  movzx   edx, byte ptr [ebx+0Eh]
0x1000990a  add     ecx, 4
0x1000990d  sar     ecx, 3
0x10009910  mov     [eax+4], cl
0x10009913  movzx   ecx, byte ptr [ebx+0Ah]
0x10009917  add     edx, ecx
0x10009919  movzx   ecx, byte ptr [ebx+6]
0x1000991d  add     edx, ecx
0x1000991f  movzx   ecx, byte ptr [ebx+2]
0x10009923  add     edx, ecx
0x10009925  sub     edx, [ebp+var_C]
0x10009928  pop     edi
0x10009929  add     edx, 4
0x1000992c  sar     edx, 3
0x1000992f  pop     esi
0x10009930  mov     [eax+5], dl
0x10009933  pop     ebx
0x10009934  leave
0x10009935  retn    4
```
