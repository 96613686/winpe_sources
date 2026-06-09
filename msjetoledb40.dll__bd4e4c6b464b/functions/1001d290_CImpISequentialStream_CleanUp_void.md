# CImpISequentialStream::CleanUp(void)

- ea: `0x1001d290`
- end: `0x1001d3a8`
- name: `?CleanUp@CImpISequentialStream@@UAEXXZ`
- size: `280`
- prototype: `void __thiscall(CImpISequentialStream *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1001d290`

## import_xrefs

- `msjet40!__imp__JetUpdate@20` at `0x1001d2c7`
- `msjet40!__imp__JetUpdate@20` at `0x1001d2c7`

## pseudocode

```c
void __thiscall CImpISequentialStream::CleanUp(CImpISequentialStream *this)
{
  int v2; // eax
  int v3; // eax
  _DWORD *v4; // edi
  unsigned int v5; // ebx
  int v6; // ecx
  int v7; // eax
  _DWORD *v8; // eax
  _DWORD *v9; // eax
  _BYTE pvBookmark[4]; // [esp+4h] [ebp-8h] BYREF
  unsigned int pcbActual; // [esp+8h] [ebp-4h] BYREF

  v2 = *((_DWORD *)this + 3);
  if ( (*(_BYTE *)(v2 + 96) & 0x10) != 0 && !*((_DWORD *)this + 10) )
  {
    JetUpdate(*(_DWORD *)(*(_DWORD *)(v2 + 56) + 16), *((_DWORD *)this + 5), pvBookmark, 4u, &pcbActual);
    v3 = *((_DWORD *)this + 3);
    v4 = *(_DWORD **)(v3 + 104);
    v5 = *(_DWORD *)(v3 + 224);
    v6 = v4[6];
    if ( v5 > v6 + 8 * v4[5] - 1
      || (*(_BYTE *)(((v5 - v6) >> 3) + v4[4]) & *((_BYTE *)&Bitmap::ThisBit + ((v5 - v6) & 7))) != 0 )
    {
      v7 = 0;
    }
    else
    {
      v7 = v4[2] + v5 * *v4;
    }
    *(_DWORD *)(v7 + 4) = 8;
    v8 = (_DWORD *)*((_DWORD *)this + 3);
    v8[55] = -1;
    v8[57] = 0;
    v8[56] = 0;
    v8[58] = -1;
    v8[59] = 1;
  }
  v9 = (_DWORD *)*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 10) == 1 )
  {
    v9[55] = -1;
    v9[57] = 0;
    v9[56] = 0;
    v9[58] = -1;
LABEL_11:
    v9[59] = 1;
    v9 = (_DWORD *)*((_DWORD *)this + 3);
    goto LABEL_12;
  }
  if ( !v9[59] )
    goto LABEL_11;
LABEL_12:
  v9[54] = 0;
}

```

## disassembly

```asm
0x1001d290  mov     edi, edi
0x1001d292  push    ebp
0x1001d293  mov     ebp, esp
0x1001d295  sub     esp, 8
0x1001d298  push    esi
0x1001d299  mov     esi, ecx
0x1001d29b  mov     eax, [esi+0Ch]
0x1001d29e  test    byte ptr [eax+60h], 10h
0x1001d2a2  jz      loc_1001D350
0x1001d2a8  cmp     dword ptr [esi+28h], 0
0x1001d2ac  jnz     loc_1001D350
0x1001d2b2  mov     eax, [eax+38h]
0x1001d2b5  lea     ecx, [ebp+pcbActual]
0x1001d2b8  push    ebx
0x1001d2b9  push    edi
0x1001d2ba  push    ecx; pcbActual
0x1001d2bb  push    4; cbBookmark
0x1001d2bd  lea     ecx, [ebp+pvBookmark]
0x1001d2c0  push    ecx; pvBookmark
0x1001d2c1  push    dword ptr [esi+14h]; tableid
0x1001d2c4  push    dword ptr [eax+10h]; sesid
0x1001d2c7  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x1001d2cd  mov     eax, [esi+0Ch]
0x1001d2d0  mov     edi, [eax+68h]
0x1001d2d3  mov     ebx, [eax+0E0h]
0x1001d2d9  mov     eax, [edi+14h]
0x1001d2dc  mov     ecx, [edi+18h]
0x1001d2df  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1001d2e6  add     eax, ecx
0x1001d2e8  cmp     ebx, eax
0x1001d2ea  ja      short loc_1001D310
0x1001d2ec  mov     eax, [edi+10h]
0x1001d2ef  mov     edx, ebx
0x1001d2f1  sub     edx, ecx
0x1001d2f3  mov     ecx, edx
0x1001d2f5  and     edx, 7
0x1001d2f8  shr     ecx, 3
0x1001d2fb  mov     al, [ecx+eax]
0x1001d2fe  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1001d304  jnz     short loc_1001D310
0x1001d306  mov     eax, [edi]
0x1001d308  imul    eax, ebx
0x1001d30b  add     eax, [edi+8]
0x1001d30e  jmp     short loc_1001D312
0x1001d310  xor     eax, eax
0x1001d312  mov     dword ptr [eax+4], 8
0x1001d319  mov     eax, [esi+0Ch]
0x1001d31c  pop     edi
0x1001d31d  pop     ebx
0x1001d31e  mov     dword ptr [eax+0DCh], 0FFFFFFFFh
0x1001d328  mov     dword ptr [eax+0E4h], 0
0x1001d332  mov     dword ptr [eax+0E0h], 0
0x1001d33c  mov     dword ptr [eax+0E8h], 0FFFFFFFFh
0x1001d346  mov     dword ptr [eax+0ECh], 1
0x1001d350  cmp     dword ptr [esi+28h], 1
0x1001d354  mov     eax, [esi+0Ch]
0x1001d357  jnz     short loc_1001D383
0x1001d359  mov     dword ptr [eax+0DCh], 0FFFFFFFFh
0x1001d363  mov     dword ptr [eax+0E4h], 0
0x1001d36d  mov     dword ptr [eax+0E0h], 0
0x1001d377  mov     dword ptr [eax+0E8h], 0FFFFFFFFh
0x1001d381  jmp     short loc_1001D38C
0x1001d383  cmp     dword ptr [eax+0ECh], 0
0x1001d38a  jnz     short loc_1001D399
0x1001d38c  mov     dword ptr [eax+0ECh], 1
0x1001d396  mov     eax, [esi+0Ch]
0x1001d399  mov     dword ptr [eax+0D8h], 0
0x1001d3a3  pop     esi
0x1001d3a4  mov     esp, ebp
0x1001d3a6  pop     ebp
0x1001d3a7  retn
```
