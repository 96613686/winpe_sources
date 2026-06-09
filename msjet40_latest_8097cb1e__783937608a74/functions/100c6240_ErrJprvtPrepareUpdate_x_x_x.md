# ErrJprvtPrepareUpdate(x,x,x)

- ea: `0x100c6240`
- end: `0x100c66be`
- name: `_ErrJprvtPrepareUpdate@12`
- size: `1150`
- prototype: ``
- caller_count: `7`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100acaa3`
- `0x100acf70`
- `0x100ad500`
- `0x100ada00`
- `0x100adcf0`
- `0x100c6240`
- `0x100c8d20`

## callees

- `0x100437f0`
- `0x10044020`
- `0x100ad3d9`
- `0x100ad4a5`
- `0x100adac7`
- `0x100c3480`
- `0x100c5897`
- `0x100c5f7e`
- `0x100c6062`
- `0x100c6163`
- `0x100c6240`
- `0x100d9ef4`
- `0x100da529`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c6435`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c6634`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c6435`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c6634`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c6392`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c6392`

## pseudocode

```c
int __stdcall ErrJprvtPrepareUpdate(int a1, int *a2, int a3)
{
  int *v3; // edi
  int v4; // ebx
  int v5; // esi
  bool v6; // zf
  int result; // eax
  unsigned int v8; // eax
  int v9; // eax
  size_t *v10; // esi
  void *v11; // eax
  int v12; // eax
  int v13; // eax
  int updated; // eax
  size_t *v15; // eax
  int *v16; // edx
  int v17; // eax
  int v18; // eax
  int *v19; // ecx
  int *v20; // eax
  int v21; // edx
  int v22; // eax
  int *v23; // eax
  int *v24; // edx
  int v25; // ecx
  int *v26; // edi
  unsigned int v27; // ebx
  unsigned int v28; // eax
  int v29; // esi
  int v30; // [esp+10h] [ebp-20h]
  int v31; // [esp+14h] [ebp-1Ch]
  unsigned int v32; // [esp+18h] [ebp-18h]
  int *v33; // [esp+1Ch] [ebp-14h]
  int v34; // [esp+1Ch] [ebp-14h]
  void *Block; // [esp+20h] [ebp-10h]
  int v36; // [esp+24h] [ebp-Ch]
  int v37; // [esp+28h] [ebp-8h] BYREF
  int *v38; // [esp+2Ch] [ebp-4h] BYREF

  v3 = a2;
  v4 = a2[7];
  v5 = *a2;
  v36 = v4;
  v30 = *a2;
  v38 = *(int **)(v4 + 260);
  v6 = (*(_DWORD *)(v4 + 28) & 0x1000) == 0;
  Block = 0;
  v31 = 0;
  v37 = 0;
  if ( !v6 )
    return -1065;
  if ( (*(_BYTE *)(v5 + 44) & 3) != 3 )
    return -1809;
  if ( a3 != 3 && a2[4] != 10 )
  {
    result = ErrJprvtPrepareUpdate(a1, a2, 3);
    v31 = result;
    if ( result < 0 )
      return result;
    v5 = v30;
  }
  v8 = ((unsigned int)a2 - *a2 - 84) / 0x24;
  *(_DWORD *)(v4 + 140) = v8;
  v32 = v8;
  if ( a2[5] == -1 )
    ErrIrowOfRecid(*(_DWORD *)(v5 + 1168), a2 + 5);
  if ( !a3 )
  {
    if ( (*(_DWORD *)(v4 + 28) & 0x800) != 0 )
      return -1312;
    if ( *(_DWORD *)(v4 + 260) )
      FCEnable(1);
    v10 = (size_t *)(v5 + 1196);
    if ( (int)*v10 > 0 )
    {
      v16 = *(int **)(v30 + 1192);
      v33 = &v16[*v10];
      v17 = *v16;
      if ( v16 < v33 )
      {
        while ( 1 )
        {
          ++v16;
          *(_BYTE *)(*(_DWORD *)(v17 + 228) + 8 * v32) = 3;
          if ( v16 >= v33 )
            break;
          v17 = *v16;
        }
        v3 = a2;
      }
    }
    v15 = v10;
    if ( *v10 != 1 )
    {
LABEL_48:
      v10 = v15;
      v3[4] = a3;
      if ( (int)*v15 > 0 )
      {
        v19 = *(int **)(v30 + 1192);
        v20 = &v19[*v15];
        v21 = *v19;
        if ( v19 < v20 )
        {
          while ( 1 )
          {
            ++v19;
            *(_DWORD *)(*(_DWORD *)(v21 + 228) + 8 * v32 + 4) &= 0xFFFFFFC1;
            *(_DWORD *)(v21 + 216) = 0;
            if ( v19 >= v20 )
              break;
            v21 = *v19;
          }
          v3 = a2;
        }
      }
      RVTSetUpdcolFlags(v4, a3);
      v3[2] &= ~1u;
      v6 = v3[1] == -1;
      *((_BYTE *)v3 + 25) = *((_BYTE *)v3 + 24);
      if ( !v6 )
      {
        v22 = a3;
        if ( a3 == 4 )
          v22 = 2;
        v31 = ErrDispPrepareUpdate2(a1, v3[1], v22);
        Block = 0;
        if ( v31 < 0 )
          goto LABEL_57;
        v6 = v38 == 0;
        v3[2] |= 2u;
        if ( !v6 && a3 )
        {
          ErrDispGetBookmark(a1, v3[1], &v38, 4, &v37);
          *(_DWORD *)(v4 + 148) = v38;
        }
      }
      return 0;
    }
    v18 = **(_DWORD **)(v30 + 1192);
    v34 = *(_DWORD *)(v18 + 228);
    v31 = ErrDispPrepareUpdate2(a1, *(_DWORD *)(v18 + 4 * v32 + 40), 0);
    if ( v31 >= 0 )
    {
      *(_DWORD *)(v34 + 8 * v32 + 4) |= 1u;
      v15 = v10;
      goto LABEL_48;
    }
LABEL_57:
    v9 = v30;
    goto LABEL_58;
  }
  if ( a3 == 2 )
  {
LABEL_18:
    if ( a2[3] != 2 )
      return -1603;
    if ( *(_DWORD *)(v4 + 260) )
      FCEnable(1);
    v10 = (size_t *)(v5 + 1196);
    v11 = _malloc(*v10);
    Block = v11;
    if ( !v11 )
      goto LABEL_57;
    v12 = ErrRVTSyncAllBM(v11, *v10);
    v31 = v12;
    if ( v12 < 0 )
      goto LABEL_57;
    if ( v12 != 1699 )
    {
      v13 = v30;
      if ( (*(_BYTE *)(v30 + 44) & 8) == 0 )
        goto LABEL_31;
      if ( *(_WORD *)(v4 + 256) )
        PartiallyUnsyncPrvtc(Block);
      updated = ErrRVTCompUpdateCS(1, &v37);
      v31 = updated;
      if ( updated < 0 )
        goto LABEL_57;
      if ( updated != 1610 )
      {
        v13 = v30;
LABEL_31:
        v31 = ErrRVTPrepReplaceBTs(v13, a3);
        if ( v31 >= 0 )
        {
          _free(Block);
          v15 = v10;
          goto LABEL_48;
        }
        goto LABEL_57;
      }
    }
    if ( *(_DWORD *)(v4 + 260) )
      FCEjectCurrentRow(v4, v30);
    v31 = -1611;
    goto LABEL_57;
  }
  if ( a3 != 3 )
  {
    if ( a3 != 4 )
      return -1003;
    goto LABEL_18;
  }
  UnsyncPrvtc();
  if ( a2[1] != -1 )
  {
    result = ErrDispPrepareUpdate2(a1, a2[1], 3);
    v31 = result;
    if ( result < 0 )
      return result;
  }
  a2[2] &= 0xFFFFFFFC;
  *((_BYTE *)a2 + 25) = 0;
  RVTSetUpdcolFlags(v4, 10);
  v9 = v30;
  v10 = (size_t *)(v30 + 1196);
LABEL_58:
  if ( (int)*v10 > 0 )
  {
    v23 = *(int **)(v9 + 1192);
    v24 = &v23[*v10];
    v25 = *v23;
    v38 = v24;
    if ( v23 < v24 )
    {
      v26 = v23;
      v27 = (unsigned int)v24;
      v28 = v32;
      while ( 1 )
      {
        v29 = *(_DWORD *)(v25 + 228);
        ErrDispPrepareUpdate2(a1, *(_DWORD *)(v25 + 4 * v28 + 40), 3);
        v28 = v32;
        ++v26;
        *(_DWORD *)(v29 + 8 * v32 + 4) &= 0xFFFFFFC0;
        if ( (unsigned int)v26 >= v27 )
          break;
        v25 = *v26;
      }
      v3 = a2;
      v4 = v36;
    }
  }
  if ( (*(_BYTE *)(v30 + 44) & 8) != 0 && v37 )
    RVTCancelLastChecksum(v4, v3);
  if ( Block )
    _free(Block);
  if ( *(_DWORD *)(v4 + 260) )
    FCEnable(1);
  result = v31;
  *(_DWORD *)(v4 + 148) = 0;
  v3[4] = 10;
  return result;
}

```

## disassembly

```asm
0x100c6240  mov     edi, edi
0x100c6242  push    ebp
0x100c6243  mov     ebp, esp
0x100c6245  and     esp, 0FFFFFFF8h
0x100c6248  sub     esp, 24h
0x100c624b  push    ebx
0x100c624c  push    esi
0x100c624d  push    edi
0x100c624e  mov     edi, [ebp+arg_4]
0x100c6251  mov     ebx, [edi+1Ch]
0x100c6254  mov     esi, [edi]
0x100c6256  mov     [esp+30h+var_C], ebx
0x100c625a  mov     [esp+30h+var_20], esi
0x100c625e  mov     eax, [ebx+104h]
0x100c6264  mov     [esp+30h+var_4], eax
0x100c6268  xor     eax, eax
0x100c626a  test    dword ptr [ebx+1Ch], 1000h
0x100c6271  mov     [esp+30h+Block], eax
0x100c6275  mov     [esp+30h+var_1C], eax
0x100c6279  mov     [esp+30h+var_8], eax
0x100c627d  jz      short loc_100C6289
0x100c627f  mov     eax, 0FFFFFBD7h
0x100c6284  jmp     loc_100C66B5
0x100c6289  mov     eax, [esi+2Ch]
0x100c628c  and     eax, 3
0x100c628f  cmp     al, 3
0x100c6291  jnz     loc_100C66B0
0x100c6297  cmp     [ebp+arg_8], 3
0x100c629b  jz      short loc_100C62C0
0x100c629d  cmp     dword ptr [edi+10h], 0Ah
0x100c62a1  jz      short loc_100C62C0
0x100c62a3  push    3
0x100c62a5  push    edi
0x100c62a6  push    [ebp+arg_0]
0x100c62a9  call    _ErrJprvtPrepareUpdate@12; ErrJprvtPrepareUpdate(x,x,x)
0x100c62ae  mov     esi, eax
0x100c62b0  mov     [esp+30h+var_1C], esi
0x100c62b4  test    esi, esi
0x100c62b6  js      loc_100C66B5
0x100c62bc  mov     esi, [esp+30h+var_20]
0x100c62c0  mov     eax, edi
0x100c62c2  xor     edx, edx
0x100c62c4  sub     eax, [edi]
0x100c62c6  push    24h ; '$'
0x100c62c8  sub     eax, 54h ; 'T'
0x100c62cb  pop     ecx
0x100c62cc  div     ecx
0x100c62ce  lea     ecx, [edi+14h]
0x100c62d1  mov     [ebx+8Ch], eax
0x100c62d7  cmp     dword ptr [ecx], 0FFFFFFFFh
0x100c62da  mov     [esp+30h+var_18], eax
0x100c62de  jnz     short loc_100C62F2
0x100c62e0  mov     edx, [edi+4]
0x100c62e3  push    ecx
0x100c62e4  push    dword ptr [esi+490h]
0x100c62ea  mov     ecx, [ebp+arg_0]
0x100c62ed  call    _ErrIrowOfRecid@16; ErrIrowOfRecid(x,x,x,x)
0x100c62f2  mov     eax, [ebp+arg_8]
0x100c62f5  xor     ecx, ecx
0x100c62f7  push    2
0x100c62f9  pop     edx
0x100c62fa  sub     eax, ecx
0x100c62fc  jz      loc_100C6468
0x100c6302  sub     eax, edx
0x100c6304  jz      short loc_100C6364
0x100c6306  sub     eax, 1
0x100c6309  jz      short loc_100C631A
0x100c630b  sub     eax, 1
0x100c630e  jz      short loc_100C6364
0x100c6310  mov     eax, 0FFFFFC15h
0x100c6315  jmp     loc_100C66B5
0x100c631a  mov     edx, edi
0x100c631c  call    _UnsyncPrvtc@8; UnsyncPrvtc(x,x)
0x100c6321  cmp     dword ptr [edi+4], 0FFFFFFFFh
0x100c6325  jz      short loc_100C6343
0x100c6327  push    3
0x100c6329  push    dword ptr [edi+4]
0x100c632c  push    [ebp+arg_0]
0x100c632f  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c6334  mov     esi, eax
0x100c6336  mov     [esp+30h+var_1C], esi
0x100c633a  test    esi, esi
0x100c633c  jns     short loc_100C6343
0x100c633e  jmp     loc_100C66B5
0x100c6343  and     dword ptr [edi+8], 0FFFFFFFCh
0x100c6347  mov     ecx, ebx
0x100c6349  push    0Ah
0x100c634b  pop     edx
0x100c634c  mov     byte ptr [edi+19h], 0
0x100c6350  call    RVTSetUpdcolFlags
0x100c6355  mov     eax, [esp+30h+var_20]
0x100c6359  lea     esi, [eax+4ACh]
0x100c635f  jmp     loc_100C65BD
0x100c6364  cmp     [edi+0Ch], edx
0x100c6367  jz      short loc_100C6373
0x100c6369  mov     eax, 0FFFFF9BDh
0x100c636e  jmp     loc_100C66B5
0x100c6373  cmp     [ebx+104h], ecx
0x100c6379  jz      short loc_100C6386
0x100c637b  push    1
0x100c637d  xor     edx, edx
0x100c637f  mov     ecx, ebx
0x100c6381  call    _FCEnable@12; FCEnable(x,x,x)
0x100c6386  add     esi, 4ACh
0x100c638c  mov     [esp+30h+var_14], esi
0x100c6390  push    dword ptr [esi]; Size
0x100c6392  call    ds:__imp__malloc
0x100c6398  mov     edx, eax
0x100c639a  mov     [esp+34h+Block], edx
0x100c639e  pop     ecx
0x100c639f  test    edx, edx
0x100c63a1  jz      loc_100C65B9
0x100c63a7  push    dword ptr [esi]; Size
0x100c63a9  mov     ecx, ebx
0x100c63ab  push    edx; void *
0x100c63ac  mov     edx, [esp+38h+var_20]
0x100c63b0  call    _ErrRVTSyncAllBM@16; ErrRVTSyncAllBM(x,x,x,x)
0x100c63b5  mov     [esp+30h+var_1C], eax
0x100c63b9  test    eax, eax
0x100c63bb  js      loc_100C65B9
0x100c63c1  cmp     eax, 6A3h
0x100c63c6  jz      short loc_100C6443
0x100c63c8  mov     eax, [esp+30h+var_20]
0x100c63cc  test    byte ptr [eax+2Ch], 8
0x100c63d0  jz      short loc_100C6413
0x100c63d2  xor     eax, eax
0x100c63d4  cmp     [ebx+100h], ax
0x100c63db  jbe     short loc_100C63E8
0x100c63dd  push    [esp+30h+Block]
0x100c63e1  mov     edx, edi
0x100c63e3  call    PartiallyUnsyncPrvtc
0x100c63e8  lea     eax, [esp+30h+var_8]
0x100c63ec  mov     edx, edi
0x100c63ee  push    eax
0x100c63ef  push    1
0x100c63f1  mov     ecx, ebx
0x100c63f3  call    _ErrRVTCompUpdateCS@16; ErrRVTCompUpdateCS(x,x,x,x)
0x100c63f8  mov     esi, [esp+30h+var_14]
0x100c63fc  mov     [esp+30h+var_1C], eax
0x100c6400  test    eax, eax
0x100c6402  js      loc_100C65B9
0x100c6408  cmp     eax, 64Ah
0x100c640d  jz      short loc_100C6443
0x100c640f  mov     eax, [esp+30h+var_20]
0x100c6413  push    [ebp+arg_8]
0x100c6416  mov     ecx, [ebp+arg_0]
0x100c6419  mov     edx, ebx
0x100c641b  push    eax
0x100c641c  call    ErrRVTPrepReplaceBTs
0x100c6421  mov     esi, [esp+30h+var_14]
0x100c6425  mov     [esp+30h+var_1C], eax
0x100c6429  test    eax, eax
0x100c642b  js      loc_100C65B9
0x100c6431  push    [esp+30h+Block]; Block
0x100c6435  call    ds:__imp__free
0x100c643b  pop     ecx
0x100c643c  mov     eax, esi
0x100c643e  jmp     loc_100C651D
0x100c6443  cmp     dword ptr [ebx+104h], 0
0x100c644a  jz      short loc_100C6457
0x100c644c  mov     edx, [esp+30h+var_20]
0x100c6450  mov     ecx, ebx
0x100c6452  call    _FCEjectCurrentRow@8; FCEjectCurrentRow(x,x)
0x100c6457  mov     esi, [esp+30h+var_14]
0x100c645b  mov     [esp+30h+var_1C], 0FFFFF9B5h
0x100c6463  jmp     loc_100C65B9
0x100c6468  test    dword ptr [ebx+1Ch], 800h
0x100c646f  jz      short loc_100C647B
0x100c6471  mov     eax, 0FFFFFAE0h
0x100c6476  jmp     loc_100C66B5
0x100c647b  cmp     [ebx+104h], ecx
0x100c6481  jz      short loc_100C648E
0x100c6483  push    1
0x100c6485  xor     edx, edx
0x100c6487  mov     ecx, ebx
0x100c6489  call    _FCEnable@12; FCEnable(x,x,x)
0x100c648e  mov     ecx, [esp+30h+var_20]
0x100c6492  add     esi, 4ACh
0x100c6498  mov     eax, [esi]
0x100c649a  test    eax, eax
0x100c649c  jle     short loc_100C64D7
0x100c649e  mov     edx, [ecx+4A8h]
0x100c64a4  lea     eax, [edx+eax*4]
0x100c64a7  mov     [esp+30h+var_14], eax
0x100c64ab  mov     eax, [edx]
0x100c64ad  cmp     edx, [esp+30h+var_14]
0x100c64b1  jnb     short loc_100C64D7
0x100c64b3  mov     ebx, [esp+30h+var_14]
0x100c64b7  mov     edi, [esp+30h+var_18]
0x100c64bb  mov     eax, [eax+0E4h]
0x100c64c1  add     edx, 4
0x100c64c4  mov     byte ptr [eax+edi*8], 3
0x100c64c8  cmp     edx, ebx
0x100c64ca  jnb     short loc_100C64D0
0x100c64cc  mov     eax, [edx]
0x100c64ce  jmp     short loc_100C64BB
0x100c64d0  mov     edi, [ebp+arg_4]
0x100c64d3  mov     ebx, [esp+30h+var_C]
0x100c64d7  cmp     dword ptr [esi], 1
0x100c64da  mov     eax, esi
0x100c64dc  jnz     short loc_100C651D
0x100c64de  mov     eax, [ecx+4A8h]
0x100c64e4  push    0
0x100c64e6  mov     eax, [eax]
0x100c64e8  mov     ecx, [eax+0E4h]
0x100c64ee  mov     [esp+34h+var_14], ecx
0x100c64f2  mov     ecx, [esp+34h+var_18]
0x100c64f6  push    dword ptr [eax+ecx*4+28h]
0x100c64fa  push    [ebp+arg_0]
0x100c64fd  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c6502  mov     [esp+30h+var_1C], eax
0x100c6506  test    eax, eax
0x100c6508  js      loc_100C65B9
0x100c650e  mov     eax, [esp+30h+var_14]
0x100c6512  mov     ecx, [esp+30h+var_18]
0x100c6516  or      dword ptr [eax+ecx*8+4], 1
0x100c651b  mov     eax, esi
0x100c651d  mov     esi, eax
0x100c651f  mov     eax, [ebp+arg_8]
0x100c6522  mov     [edi+10h], eax
0x100c6525  mov     edx, [esi]
0x100c6527  test    edx, edx
0x100c6529  jle     short loc_100C656F
0x100c652b  mov     eax, [esp+30h+var_20]
0x100c652f  mov     ecx, [eax+4A8h]
0x100c6535  lea     eax, [ecx+edx*4]
0x100c6538  mov     edx, [ecx]
0x100c653a  mov     [esp+30h+Block], eax
0x100c653e  cmp     ecx, eax
0x100c6540  jnb     short loc_100C656F
0x100c6542  mov     edi, [esp+30h+var_18]
0x100c6546  mov     ebx, eax
0x100c6548  mov     eax, [edx+0E4h]
0x100c654e  add     ecx, 4
0x100c6551  and     dword ptr [eax+edi*8+4], 0FFFFFFC1h
0x100c6556  mov     dword ptr [edx+0D8h], 0
0x100c6560  cmp     ecx, ebx
0x100c6562  jnb     short loc_100C6568
0x100c6564  mov     edx, [ecx]
0x100c6566  jmp     short loc_100C6548
0x100c6568  mov     edi, [ebp+arg_4]
0x100c656b  mov     ebx, [esp+30h+var_C]
0x100c656f  mov     edx, [ebp+arg_8]
0x100c6572  mov     ecx, ebx
0x100c6574  call    RVTSetUpdcolFlags
0x100c6579  and     dword ptr [edi+8], 0FFFFFFFEh
0x100c657d  cmp     dword ptr [edi+4], 0FFFFFFFFh
0x100c6581  mov     al, [edi+18h]
0x100c6584  mov     [edi+19h], al
0x100c6587  jz      loc_100C66AC
0x100c658d  mov     eax, [ebp+arg_8]
0x100c6590  cmp     eax, 4
0x100c6593  push    2
0x100c6595  pop     ecx
0x100c6596  cmovz   eax, ecx
0x100c6599  push    eax
0x100c659a  push    dword ptr [edi+4]
0x100c659d  push    [ebp+arg_0]
0x100c65a0  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c65a5  mov     [esp+30h+var_1C], eax
0x100c65a9  mov     [esp+30h+Block], 0
0x100c65b1  test    eax, eax
0x100c65b3  jns     loc_100C6667
0x100c65b9  mov     eax, [esp+30h+var_20]
0x100c65bd  mov     ecx, [esi]
0x100c65bf  test    ecx, ecx
0x100c65c1  jle     short loc_100C6611
0x100c65c3  mov     eax, [eax+4A8h]
0x100c65c9  mov     [esp+30h+var_14], eax
0x100c65cd  lea     edx, [eax+ecx*4]
0x100c65d0  mov     ecx, [eax]
0x100c65d2  mov     [esp+30h+var_4], edx
0x100c65d6  cmp     eax, edx
0x100c65d8  jnb     short loc_100C6611
0x100c65da  mov     edi, eax
0x100c65dc  mov     ebx, edx
0x100c65de  mov     eax, [esp+30h+var_18]
0x100c65e2  mov     esi, [ecx+0E4h]
0x100c65e8  push    3
0x100c65ea  push    dword ptr [ecx+eax*4+28h]
0x100c65ee  push    [ebp+arg_0]
0x100c65f1  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c65f6  mov     eax, [esp+30h+var_18]
0x100c65fa  add     edi, 4
0x100c65fd  and     dword ptr [esi+eax*8+4], 0FFFFFFC0h
0x100c6602  cmp     edi, ebx
0x100c6604  jnb     short loc_100C660A
0x100c6606  mov     ecx, [edi]
0x100c6608  jmp     short loc_100C65E2
0x100c660a  mov     edi, [ebp+arg_4]
0x100c660d  mov     ebx, [esp+30h+var_C]
0x100c6611  mov     eax, [esp+30h+var_20]
0x100c6615  test    byte ptr [eax+2Ch], 8
0x100c6619  jz      short loc_100C662B
0x100c661b  cmp     [esp+30h+var_8], 0
0x100c6620  jz      short loc_100C662B
0x100c6622  mov     edx, edi
0x100c6624  mov     ecx, ebx
0x100c6626  call    _RVTCancelLastChecksum@8; RVTCancelLastChecksum(x,x)
0x100c662b  mov     eax, [esp+30h+Block]
  ... truncated ...
```
