# IndexPage::Compress(Bitmap &,ulong)

- ea: `0x10033400`
- end: `0x100336da`
- name: `?Compress@IndexPage@@AAEKAAVBitmap@@K@Z`
- size: `730`
- prototype: `unsigned int __thiscall(IndexPage *__hidden this, struct Bitmap *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10011f50`
- `0x10032460`

## callees

- `0x1000f790`
- `0x1000f930`
- `0x1000f990`
- `0x10033400`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x10033532`
- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x10033532`

## pseudocode

```c
unsigned int __thiscall IndexPage::Compress(IndexPage *this, struct Bitmap *a2, unsigned int a3)
{
  _BYTE *v3; // ebx
  unsigned int v4; // ecx
  int v5; // eax
  unsigned int v6; // ecx
  unsigned __int8 v7; // al
  int v9; // eax
  _BYTE *v10; // ecx
  _BYTE *i; // esi
  unsigned int v12; // ebx
  unsigned __int16 v13; // si
  unsigned int One; // eax
  unsigned int v15; // ecx
  int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // esi
  unsigned int v19; // esi
  unsigned int v20; // edx
  int v21; // ecx
  void *v22; // esi
  bool v23; // cf
  unsigned int v24; // edx
  unsigned int v25; // eax
  int v26; // edx
  unsigned int v27; // eax
  unsigned __int8 v28; // dl
  unsigned int v29; // ecx
  void *v30; // ebx
  unsigned int v31; // edi
  void *v33; // [esp+Ch] [ebp-24h]
  unsigned __int16 v34; // [esp+Ch] [ebp-24h]
  int v35; // [esp+10h] [ebp-20h]
  unsigned int OneInclusive; // [esp+14h] [ebp-1Ch]
  unsigned int v37; // [esp+18h] [ebp-18h]
  int v38; // [esp+1Ch] [ebp-14h]
  char *v39; // [esp+20h] [ebp-10h]
  void *v40; // [esp+24h] [ebp-Ch]
  int v41; // [esp+28h] [ebp-8h]
  void *Block; // [esp+2Ch] [ebp-4h]

  v38 = *((_DWORD *)this + 1);
  v3 = (_BYTE *)(v38 + 248);
  v35 = v38 + 248;
  v4 = a3 - *((_DWORD *)a2 + 2);
  v5 = v4 & 7;
  v6 = v4 >> 3;
  v7 = *(_BYTE *)(*(_DWORD *)a2 + v6) & byte_10003908[v5];
  if ( v7 )
  {
LABEL_4:
    v9 = *((_DWORD *)a2 + 2) + (unsigned __int8)byte_10003708[v7] + 8 * v6;
  }
  else
  {
    while ( v6-- )
    {
      v7 = *(_BYTE *)(v6 + *(_DWORD *)a2);
      if ( v7 )
        goto LABEL_4;
    }
    v9 = -1;
  }
  v10 = &v3[v9];
  v41 = 1;
  for ( i = &v3[a3]; v10 < i; ++v3 )
  {
    if ( *v3 != *v10 )
      break;
    ++v10;
  }
  v12 = (unsigned int)&v3[-v38 - 248];
  if ( v12 > Bitmap::NextOneInclusive(a2, *((_DWORD *)a2 + 2)) - 2 )
    v12 = Bitmap::NextOneInclusive(a2, *((_DWORD *)a2 + 2)) - 2;
  if ( v12 == (unsigned __int8)v12 )
  {
    v13 = v12;
    *(_BYTE *)(v38 + 20) = v12;
    if ( !v12 )
      return a3;
  }
  else
  {
    v12 = 255;
    *(_BYTE *)(v38 + 20) = -1;
    v13 = 255;
  }
  OneInclusive = Bitmap::NextOneInclusive(a2, *((_DWORD *)a2 + 2));
  One = Bitmap::NextOne(a2, OneInclusive);
  v15 = OneInclusive;
  v16 = One;
  v37 = One;
  v39 = (char *)(OneInclusive + v35);
  if ( One == -1 )
  {
    v22 = v33;
    v30 = v33;
  }
  else
  {
    v34 = v13;
    Block = (void *)v13;
    v40 = (void *)v13;
    while ( 1 )
    {
      v17 = v12 + v15;
      v18 = v16 - v17;
      *(_WORD *)(v38 + 2) += v34;
      _memcpy(v39, (const void *)(v17 + v38 + 248), v16 - v17);
      v39 += v18;
      v19 = *((_DWORD *)a2 + 1);
      v20 = v37 - *((_DWORD *)a2 + 2);
      if ( v20 < 8 * v19 )
      {
        v23 = v20 >> 3 < v19;
        v22 = Block;
        if ( v23 )
          *(_BYTE *)(*(_DWORD *)a2 + (v20 >> 3)) &= ~*((_BYTE *)&Bitmap::ThisBit + (v20 & 7));
        v21 = v41;
      }
      else
      {
        v21 = v41;
        if ( v41 >= 8 )
        {
          v22 = Block;
        }
        else
        {
          v22 = 0;
          v21 = 8;
          v41 = 8;
          Block = 0;
          v40 = 0;
        }
      }
      v24 = (unsigned int)&v39[-v35 - *((_DWORD *)a2 + 2)];
      if ( v24 < 8 * *((_DWORD *)a2 + 1) )
      {
        if ( v24 >> 3 < *((_DWORD *)a2 + 1) )
          *(_BYTE *)(*(_DWORD *)a2 + (v24 >> 3)) |= *((_BYTE *)&Bitmap::ThisBit + (v24 & 7));
      }
      else if ( v21 < 8 )
      {
        v22 = 0;
        v41 = 8;
        Block = 0;
        v40 = 0;
      }
      v25 = v37 - *((_DWORD *)a2 + 2);
      v26 = v25 & 7;
      v27 = v25 >> 3;
      v28 = *(_BYTE *)(*(_DWORD *)a2 + v27) & byte_100036F0[v26];
      if ( !v28 )
        break;
LABEL_32:
      v15 = v37;
      v16 = *((_DWORD *)a2 + 2) + (unsigned __int8)byte_10003808[v28] + 8 * v27;
      v37 = v16;
      if ( v16 == -1 )
        goto LABEL_33;
    }
    v29 = *((_DWORD *)a2 + 1);
    while ( ++v27 < v29 )
    {
      _mm_lfence();
      v28 = *(_BYTE *)(v27 + *(_DWORD *)a2);
      v29 = *((_DWORD *)a2 + 1);
      if ( v28 )
        goto LABEL_32;
    }
LABEL_33:
    v30 = v40;
  }
  v31 = Bitmap::PreviousOne(a2, *((_DWORD *)a2 + 2) - 1 + 8 * *((_DWORD *)a2 + 1) - *(unsigned __int16 *)(v38 + 2));
  if ( (v41 & 0xFFFFFFFE) != 0 )
  {
    if ( v22 )
      operator delete[](v22);
    if ( v30 )
      operator delete[](v30);
  }
  return v31;
}

```

## disassembly

```asm
0x10033400  mov     edi, edi
0x10033402  push    ebp
0x10033403  mov     ebp, esp
0x10033405  sub     esp, 24h
0x10033408  mov     eax, [ecx+4]
0x1003340b  push    ebx
0x1003340c  mov     [ebp+var_14], eax
0x1003340f  add     eax, 0F8h
0x10033414  push    esi
0x10033415  mov     esi, [ebp+arg_4]
0x10033418  mov     ebx, eax
0x1003341a  mov     [ebp+var_20], eax
0x1003341d  mov     eax, esi
0x1003341f  push    edi
0x10033420  mov     edi, [ebp+arg_0]
0x10033423  sub     eax, [edi+8]
0x10033426  mov     edx, [edi]
0x10033428  mov     ecx, eax
0x1003342a  and     eax, 7
0x1003342d  shr     ecx, 3
0x10033430  mov     al, ds:byte_10003908[eax]
0x10033436  and     al, [edx+ecx]
0x10033439  jnz     short loc_1003344E
0x1003343b  nop     dword ptr [eax+eax+00h]
0x10033440  mov     eax, ecx
0x10033442  dec     ecx
0x10033443  test    eax, eax
0x10033445  jz      short loc_100334B8
0x10033447  mov     al, [ecx+edx]
0x1003344a  test    al, al
0x1003344c  jz      short loc_10033440
0x1003344e  movzx   eax, al
0x10033451  movzx   eax, ds:byte_10003708[eax]
0x10033458  add     eax, [edi+8]
0x1003345b  lea     eax, [eax+ecx*8]
0x1003345e  lea     ecx, [eax+ebx]
0x10033461  mov     [ebp+var_8], 1
0x10033468  add     esi, ebx
0x1003346a  cmp     ecx, esi
0x1003346c  jnb     short loc_1003347C
0x1003346e  mov     edi, edi
0x10033470  mov     al, [ebx]
0x10033472  cmp     al, [ecx]
0x10033474  jnz     short loc_1003347C
0x10033476  inc     ecx
0x10033477  inc     ebx
0x10033478  cmp     ecx, esi
0x1003347a  jb      short loc_10033470
0x1003347c  mov     esi, [ebp+var_14]
0x1003347f  mov     ecx, edi; this
0x10033481  mov     edx, [edi+8]; unsigned int
0x10033484  sub     ebx, esi
0x10033486  sub     ebx, 0F8h
0x1003348c  call    ?NextOneInclusive@Bitmap@@QBIKK@Z; Bitmap::NextOneInclusive(ulong)
0x10033491  sub     eax, 2
0x10033494  cmp     ebx, eax
0x10033496  jbe     short loc_100334A5
0x10033498  mov     edx, [edi+8]; unsigned int
0x1003349b  mov     ecx, edi; this
0x1003349d  call    ?NextOneInclusive@Bitmap@@QBIKK@Z; Bitmap::NextOneInclusive(ulong)
0x100334a2  lea     ebx, [eax-2]
0x100334a5  movzx   eax, bl
0x100334a8  cmp     ebx, eax
0x100334aa  jz      short loc_100334BD
0x100334ac  mov     ebx, 0FFh
0x100334b1  mov     [esi+14h], bl
0x100334b4  mov     esi, ebx
0x100334b6  jmp     short loc_100334CD
0x100334b8  or      eax, 0FFFFFFFFh
0x100334bb  jmp     short loc_1003345E
0x100334bd  mov     eax, [ebp+var_14]
0x100334c0  mov     esi, ebx
0x100334c2  mov     [eax+14h], bl
0x100334c5  test    ebx, ebx
0x100334c7  jz      loc_100336CE
0x100334cd  mov     edx, [edi+8]; unsigned int
0x100334d0  mov     ecx, edi; this
0x100334d2  call    ?NextOneInclusive@Bitmap@@QBIKK@Z; Bitmap::NextOneInclusive(ulong)
0x100334d7  mov     edx, eax; unsigned int
0x100334d9  mov     [ebp+var_1C], eax
0x100334dc  mov     ecx, edi; this
0x100334de  call    ?NextOne@Bitmap@@QBIKK@Z; Bitmap::NextOne(ulong)
0x100334e3  mov     ecx, [ebp+var_1C]
0x100334e6  mov     edx, eax
0x100334e8  mov     eax, [ebp+var_20]
0x100334eb  add     eax, ecx
0x100334ed  mov     [ebp+var_18], edx
0x100334f0  mov     [ebp+var_10], eax
0x100334f3  cmp     edx, 0FFFFFFFFh
0x100334f6  jz      loc_1003367C
0x100334fc  movzx   eax, si
0x100334ff  mov     [ebp+var_24], eax
0x10033502  mov     eax, [ebp+var_24]
0x10033505  mov     [ebp+Block], eax
0x10033508  mov     eax, [ebp+var_24]
0x1003350b  mov     [ebp+var_C], eax
0x1003350e  mov     edi, edi
0x10033510  mov     esi, edx
0x10033512  add     ecx, ebx
0x10033514  mov     edx, [ebp+var_14]
0x10033517  sub     esi, ecx
0x10033519  push    esi; Size
0x1003351a  mov     ax, [edx+2]
0x1003351e  add     ax, word ptr [ebp+var_24]
0x10033522  mov     [edx+2], ax
0x10033526  lea     eax, [edx+0F8h]
0x1003352c  add     eax, ecx
0x1003352e  push    eax; Src
0x1003352f  push    [ebp+var_10]; void *
0x10033532  call    ds:__imp__memcpy
0x10033538  add     [ebp+var_10], esi
0x1003353b  add     esp, 0Ch
0x1003353e  mov     esi, [edi+4]
0x10033541  mov     edx, [ebp+var_18]
0x10033544  sub     edx, [edi+8]
0x10033547  lea     eax, ds:0[esi*8]
0x1003354e  cmp     edx, eax
0x10033550  jb      short loc_10033598
0x10033552  mov     ecx, [ebp+var_8]
0x10033555  cmp     ecx, 8
0x10033558  jge     loc_10033604
0x1003355e  test    ecx, 0FFFFFFFEh
0x10033564  jz      short loc_10033586
0x10033566  mov     eax, [ebp+Block]
0x10033569  test    eax, eax
0x1003356b  jz      short loc_10033576
0x1003356d  push    eax; Block
0x1003356e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10033573  add     esp, 4
0x10033576  mov     eax, [ebp+var_C]
0x10033579  test    eax, eax
0x1003357b  jz      short loc_10033586
0x1003357d  push    eax; Block
0x1003357e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10033583  add     esp, 4
0x10033586  xor     esi, esi
0x10033588  mov     ecx, 8
0x1003358d  mov     [ebp+var_8], ecx
0x10033590  mov     [ebp+Block], esi
0x10033593  mov     [ebp+var_C], esi
0x10033596  jmp     short loc_100335B6
0x10033598  mov     ecx, edx
0x1003359a  shr     ecx, 3
0x1003359d  cmp     ecx, esi
0x1003359f  mov     esi, [ebp+Block]
0x100335a2  jnb     short loc_100335B3
0x100335a4  add     ecx, [edi]
0x100335a6  and     edx, 7
0x100335a9  mov     al, ds:?ThisBit@Bitmap@@1QBEB[edx]; uchar const * const Bitmap::ThisBit
0x100335af  not     al
0x100335b1  and     [ecx], al
0x100335b3  mov     ecx, [ebp+var_8]
0x100335b6  mov     edx, [ebp+var_10]
0x100335b9  sub     edx, [ebp+var_20]
0x100335bc  mov     eax, [edi+4]
0x100335bf  sub     edx, [edi+8]
0x100335c2  shl     eax, 3
0x100335c5  cmp     edx, eax
0x100335c7  jb      short loc_10033609
0x100335c9  cmp     ecx, 8
0x100335cc  jge     short loc_10033620
0x100335ce  test    ecx, 0FFFFFFFEh
0x100335d4  jz      short loc_100335F3
0x100335d6  test    esi, esi
0x100335d8  jz      short loc_100335E3
0x100335da  push    esi; Block
0x100335db  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100335e0  add     esp, 4
0x100335e3  mov     eax, [ebp+var_C]
0x100335e6  test    eax, eax
0x100335e8  jz      short loc_100335F3
0x100335ea  push    eax; Block
0x100335eb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100335f0  add     esp, 4
0x100335f3  xor     esi, esi
0x100335f5  mov     [ebp+var_8], 8
0x100335fc  mov     [ebp+Block], esi
0x100335ff  mov     [ebp+var_C], esi
0x10033602  jmp     short loc_10033620
0x10033604  mov     esi, [ebp+Block]
0x10033607  jmp     short loc_100335B6
0x10033609  mov     ecx, edx
0x1003360b  shr     ecx, 3
0x1003360e  cmp     ecx, [edi+4]
0x10033611  jnb     short loc_10033620
0x10033613  add     ecx, [edi]
0x10033615  and     edx, 7
0x10033618  mov     al, ds:?ThisBit@Bitmap@@1QBEB[edx]; uchar const * const Bitmap::ThisBit
0x1003361e  or      [ecx], al
0x10033620  mov     edx, [ebp+var_18]
0x10033623  mov     ecx, [edi]
0x10033625  mov     [ebp+var_1C], edx
0x10033628  sub     edx, [edi+8]
0x1003362b  mov     eax, edx
0x1003362d  and     edx, 7
0x10033630  shr     eax, 3
0x10033633  mov     dl, ds:byte_100036F0[edx]
0x10033639  and     dl, [ecx+eax]
0x1003363c  jnz     short loc_10033658
0x1003363e  mov     ecx, [edi+4]
0x10033641  mov     [ebp+var_18], ecx
0x10033644  inc     eax
0x10033645  cmp     eax, ecx
0x10033647  jnb     short loc_10033677
0x10033649  lfence
0x1003364c  mov     ecx, [edi]
0x1003364e  mov     dl, [eax+ecx]
0x10033651  mov     ecx, [ebp+var_18]
0x10033654  test    dl, dl
0x10033656  jz      short loc_10033644
0x10033658  movzx   ecx, dl
0x1003365b  movzx   ecx, ds:byte_10003808[ecx]
0x10033662  lea     edx, [ecx+eax*8]
0x10033665  mov     ecx, [ebp+var_1C]
0x10033668  add     edx, [edi+8]
0x1003366b  mov     [ebp+var_18], edx
0x1003366e  cmp     edx, 0FFFFFFFFh
0x10033671  jnz     loc_10033510
0x10033677  mov     ebx, [ebp+var_C]
0x1003367a  jmp     short loc_10033682
0x1003367c  mov     esi, [ebp+var_24]
0x1003367f  mov     ebx, [ebp+var_24]
0x10033682  mov     eax, [ebp+var_14]
0x10033685  mov     ecx, edi; this
0x10033687  mov     edx, [edi+4]
0x1003368a  shl     edx, 3
0x1003368d  movzx   eax, word ptr [eax+2]
0x10033691  sub     edx, eax
0x10033693  mov     eax, [edi+8]
0x10033696  dec     eax
0x10033697  add     edx, eax; unsigned int
0x10033699  call    ?PreviousOne@Bitmap@@QBIKK@Z; Bitmap::PreviousOne(ulong)
0x1003369e  test    [ebp+var_8], 0FFFFFFFEh
0x100336a5  mov     edi, eax
0x100336a7  jz      short loc_100336C3
0x100336a9  test    esi, esi
0x100336ab  jz      short loc_100336B6
0x100336ad  push    esi; Block
0x100336ae  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100336b3  add     esp, 4
0x100336b6  test    ebx, ebx
0x100336b8  jz      short loc_100336C3
0x100336ba  push    ebx; Block
0x100336bb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100336c0  add     esp, 4
0x100336c3  mov     eax, edi
0x100336c5  pop     edi
0x100336c6  pop     esi
0x100336c7  pop     ebx
0x100336c8  mov     esp, ebp
0x100336ca  pop     ebp
0x100336cb  retn    8
0x100336ce  mov     eax, [ebp+arg_4]
0x100336d1  pop     edi
0x100336d2  pop     esi
0x100336d3  pop     ebx
0x100336d4  mov     esp, ebp
0x100336d6  pop     ebp
0x100336d7  retn    8
```
