# JoltProperty::CopyPropertyFrom(DBInfoProps const *)

- ea: `0x1001f190`
- end: `0x1001f241`
- name: `?CopyPropertyFrom@JoltProperty@@UAEJPBUDBInfoProps@@@Z`
- size: `177`
- prototype: `int __thiscall(JoltProperty *__hidden this, const struct DBInfoProps *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1001f190`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x1001f204`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1001f204`
- `OLEAUT32!__imp__VariantClear@4` at `0x1001f1b3`
- `OLEAUT32!__imp__VariantClear@4` at `0x1001f1b3`

## pseudocode

```c
int __thiscall JoltProperty::CopyPropertyFrom(VARIANTARG *this, const struct DBInfoProps *a2)
{
  VARIANTARG *v3; // ebx
  int v4; // eax
  SHORT v5; // ax
  int result; // eax
  LONG v7; // eax
  BSTR v8; // eax

  v3 = this + 1;
  this->lVal = *(_DWORD *)a2;
  *(_DWORD *)&this[2].vt = *((_DWORD *)a2 + 5);
  this[2].lVal = 0;
  VariantClear(this + 1);
  v4 = *((unsigned __int16 *)a2 + 2);
  v3->vt = v4;
  switch ( v4 )
  {
    case 2:
    case 11:
      v5 = *((_WORD *)a2 + 4);
      this[2].decVal.Hi32 = (ULONG)a2;
      this[1].iVal = v5;
      result = 0;
      break;
    case 3:
      v7 = *((_DWORD *)a2 + 2);
      this[2].decVal.Hi32 = (ULONG)a2;
      this[1].lVal = v7;
      result = 0;
      break;
    case 8:
      if ( *((_DWORD *)a2 + 4) )
      {
        v8 = SysAllocString(*((const OLECHAR **)a2 + 4));
        this[1].lVal = (LONG)v8;
        if ( v8 )
          goto LABEL_9;
        result = -2147024882;
      }
      else
      {
        this[2].decVal.Hi32 = (ULONG)a2;
        result = 0;
        this[1].lVal = 0;
      }
      break;
    case 12:
      v3->vt = 0;
      goto LABEL_9;
    default:
LABEL_9:
      this[2].decVal.Hi32 = (ULONG)a2;
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1001f190  mov     edi, edi
0x1001f192  push    ebp
0x1001f193  mov     ebp, esp
0x1001f195  push    ebx
0x1001f196  push    esi
0x1001f197  mov     esi, ecx
0x1001f199  push    edi
0x1001f19a  mov     edi, [ebp+arg_0]
0x1001f19d  lea     ebx, [esi+10h]
0x1001f1a0  push    ebx; pvarg
0x1001f1a1  mov     eax, [edi]
0x1001f1a3  mov     [esi+8], eax
0x1001f1a6  mov     eax, [edi+14h]
0x1001f1a9  mov     [esi+20h], eax
0x1001f1ac  mov     dword ptr [esi+28h], 0
0x1001f1b3  call    ds:__imp__VariantClear@4; VariantClear(x)
0x1001f1b9  movzx   eax, word ptr [edi+4]
0x1001f1bd  mov     [ebx], ax
0x1001f1c0  add     eax, 0FFFFFFFEh; switch 11 cases
0x1001f1c3  cmp     eax, 0Ah
0x1001f1c6  ja      short def_1001F1CF; jumptable 1001F1CF default case, cases 4-7,9,10
0x1001f1c8  movzx   eax, ds:byte_1001F258[eax]
0x1001f1cf  jmp     ds:jpt_1001F1CF[eax*4]; switch jump
0x1001f1d6  mov     ax, [edi+8]; jumptable 1001F1CF cases 2,11
0x1001f1da  mov     [esi+24h], edi
0x1001f1dd  pop     edi
0x1001f1de  mov     [esi+18h], ax
0x1001f1e2  xor     eax, eax
0x1001f1e4  pop     esi
0x1001f1e5  pop     ebx
0x1001f1e6  pop     ebp
0x1001f1e7  retn    4
0x1001f1ea  mov     eax, [edi+8]; jumptable 1001F1CF case 3
0x1001f1ed  mov     [esi+24h], edi
0x1001f1f0  pop     edi
0x1001f1f1  mov     [esi+18h], eax
0x1001f1f4  xor     eax, eax
0x1001f1f6  pop     esi
0x1001f1f7  pop     ebx
0x1001f1f8  pop     ebp
0x1001f1f9  retn    4
0x1001f1fc  mov     eax, [edi+10h]; jumptable 1001F1CF case 8
0x1001f1ff  test    eax, eax
0x1001f201  jz      short loc_1001F21D
0x1001f203  push    eax; psz
0x1001f204  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1001f20a  mov     [esi+18h], eax
0x1001f20d  test    eax, eax
0x1001f20f  jnz     short def_1001F1CF; jumptable 1001F1CF default case, cases 4-7,9,10
0x1001f211  pop     edi
0x1001f212  pop     esi
0x1001f213  mov     eax, 8007000Eh
0x1001f218  pop     ebx
0x1001f219  pop     ebp
0x1001f21a  retn    4
0x1001f21d  mov     [esi+24h], edi
0x1001f220  xor     eax, eax
0x1001f222  pop     edi
0x1001f223  mov     dword ptr [esi+18h], 0
0x1001f22a  pop     esi
0x1001f22b  pop     ebx
0x1001f22c  pop     ebp
0x1001f22d  retn    4
0x1001f230  xor     eax, eax; jumptable 1001F1CF case 12
0x1001f232  mov     [ebx], ax
0x1001f235  mov     [esi+24h], edi; jumptable 1001F1CF default case, cases 4-7,9,10
0x1001f238  xor     eax, eax
0x1001f23a  pop     edi
0x1001f23b  pop     esi
0x1001f23c  pop     ebx
0x1001f23d  pop     ebp
0x1001f23e  retn    4
```
