# LongBinaryILockBytes::CleanUp(void)

- ea: `0x1001c8c0`
- end: `0x1001c9ef`
- name: `?CleanUp@LongBinaryILockBytes@@UAEXXZ`
- size: `303`
- prototype: `void __thiscall(LongBinaryILockBytes *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1001c6d0`
- `0x1001c8c0`

## import_xrefs

- `msjet40!__imp__JetUpdate@20` at `0x1001c90e`
- `msjet40!__imp__JetUpdate@20` at `0x1001c90e`

## pseudocode

```c
void __thiscall LongBinaryILockBytes::CleanUp(LongBinaryILockBytes *this)
{
  int v2; // ecx
  int v3; // eax
  int v4; // eax
  _DWORD *v5; // esi
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // eax
  _DWORD *v9; // eax
  _DWORD *v10; // eax
  _BYTE pvBookmark[4]; // [esp+8h] [ebp-8h] BYREF
  unsigned int pcbActual; // [esp+Ch] [ebp-4h] BYREF

  v2 = *((_DWORD *)this + 4);
  if ( v2 )
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v2 + 8))(*(_DWORD *)(*(_DWORD *)v2 + 8), v2);
  v3 = *((_DWORD *)this + 3);
  if ( (*(_BYTE *)(v3 + 96) & 0x10) != 0 && !*((_DWORD *)this + 6) )
  {
    JetUpdate(*(_DWORD *)(*(_DWORD *)(v3 + 56) + 16), *((_DWORD *)this + 5), pvBookmark, 4u, &pcbActual);
    v4 = *((_DWORD *)this + 3);
    v5 = *(_DWORD **)(v4 + 104);
    v6 = *(_DWORD *)(v4 + 224);
    v7 = v5[6];
    if ( v6 > v7 + 8 * v5[5] - 1
      || (*(_BYTE *)(((v6 - v7) >> 3) + v5[4]) & *((_BYTE *)&Bitmap::ThisBit + ((v6 - v7) & 7))) != 0 )
    {
      v8 = 0;
    }
    else
    {
      v8 = v5[2] + v6 * *v5;
    }
    *(_DWORD *)(v8 + 4) = 8;
    v9 = (_DWORD *)*((_DWORD *)this + 3);
    v9[55] = -1;
    v9[57] = 0;
    v9[56] = 0;
    v9[58] = -1;
    v9[59] = 1;
  }
  v10 = (_DWORD *)*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 6) == 1 )
  {
    v10[55] = -1;
    v10[57] = 0;
    v10[56] = 0;
    v10[58] = -1;
LABEL_13:
    v10[59] = 1;
    v10 = (_DWORD *)*((_DWORD *)this + 3);
    goto LABEL_14;
  }
  if ( !v10[59] )
    goto LABEL_13;
LABEL_14:
  v10[54] = 0;
}

```

## disassembly

```asm
0x1001c8c0  mov     edi, edi
0x1001c8c2  push    ebp
0x1001c8c3  mov     ebp, esp
0x1001c8c5  sub     esp, 8
0x1001c8c8  push    esi
0x1001c8c9  push    edi
0x1001c8ca  mov     edi, ecx
0x1001c8cc  mov     ecx, [edi+10h]
0x1001c8cf  test    ecx, ecx
0x1001c8d1  jz      short loc_1001C8E3
0x1001c8d3  mov     eax, [ecx]
0x1001c8d5  push    ecx
0x1001c8d6  mov     esi, [eax+8]
0x1001c8d9  mov     ecx, esi
0x1001c8db  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001c8e1  call    esi
0x1001c8e3  mov     eax, [edi+0Ch]
0x1001c8e6  test    byte ptr [eax+60h], 10h
0x1001c8ea  jz      loc_1001C996
0x1001c8f0  cmp     dword ptr [edi+18h], 0
0x1001c8f4  jnz     loc_1001C996
0x1001c8fa  mov     eax, [eax+38h]
0x1001c8fd  lea     ecx, [ebp+pcbActual]
0x1001c900  push    ebx
0x1001c901  push    ecx; pcbActual
0x1001c902  push    4; cbBookmark
0x1001c904  lea     ecx, [ebp+pvBookmark]
0x1001c907  push    ecx; pvBookmark
0x1001c908  push    dword ptr [edi+14h]; tableid
0x1001c90b  push    dword ptr [eax+10h]; sesid
0x1001c90e  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x1001c914  mov     eax, [edi+0Ch]
0x1001c917  mov     esi, [eax+68h]
0x1001c91a  mov     ebx, [eax+0E0h]
0x1001c920  mov     eax, [esi+14h]
0x1001c923  mov     ecx, [esi+18h]
0x1001c926  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1001c92d  add     eax, ecx
0x1001c92f  cmp     ebx, eax
0x1001c931  ja      short loc_1001C957
0x1001c933  mov     eax, [esi+10h]
0x1001c936  mov     edx, ebx
0x1001c938  sub     edx, ecx
0x1001c93a  mov     ecx, edx
0x1001c93c  and     edx, 7
0x1001c93f  shr     ecx, 3
0x1001c942  mov     al, [ecx+eax]
0x1001c945  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1001c94b  jnz     short loc_1001C957
0x1001c94d  mov     eax, [esi]
0x1001c94f  imul    eax, ebx
0x1001c952  add     eax, [esi+8]
0x1001c955  jmp     short loc_1001C959
0x1001c957  xor     eax, eax
0x1001c959  mov     dword ptr [eax+4], 8
0x1001c960  mov     eax, [edi+0Ch]
0x1001c963  pop     ebx
0x1001c964  mov     dword ptr [eax+0DCh], 0FFFFFFFFh
0x1001c96e  mov     dword ptr [eax+0E4h], 0
0x1001c978  mov     dword ptr [eax+0E0h], 0
0x1001c982  mov     dword ptr [eax+0E8h], 0FFFFFFFFh
0x1001c98c  mov     dword ptr [eax+0ECh], 1
0x1001c996  cmp     dword ptr [edi+18h], 1
0x1001c99a  mov     eax, [edi+0Ch]
0x1001c99d  jnz     short loc_1001C9C9
0x1001c99f  mov     dword ptr [eax+0DCh], 0FFFFFFFFh
0x1001c9a9  mov     dword ptr [eax+0E4h], 0
0x1001c9b3  mov     dword ptr [eax+0E0h], 0
0x1001c9bd  mov     dword ptr [eax+0E8h], 0FFFFFFFFh
0x1001c9c7  jmp     short loc_1001C9D2
0x1001c9c9  cmp     dword ptr [eax+0ECh], 0
0x1001c9d0  jnz     short loc_1001C9DF
0x1001c9d2  mov     dword ptr [eax+0ECh], 1
0x1001c9dc  mov     eax, [edi+0Ch]
0x1001c9df  pop     edi
0x1001c9e0  mov     dword ptr [eax+0D8h], 0
0x1001c9ea  pop     esi
0x1001c9eb  mov     esp, ebp
0x1001c9ed  pop     ebp
0x1001c9ee  retn
```
