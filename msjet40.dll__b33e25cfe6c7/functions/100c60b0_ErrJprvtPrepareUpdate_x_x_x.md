# ErrJprvtPrepareUpdate(x,x,x)

- ea: `0x100c60b0`
- end: `0x100c652e`
- name: `_ErrJprvtPrepareUpdate@12`
- size: `1150`
- prototype: ``
- caller_count: `7`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100ac913`
- `0x100acde0`
- `0x100ad370`
- `0x100ad870`
- `0x100adb60`
- `0x100c60b0`
- `0x100c8b90`

## callees

- `0x10043660`
- `0x10043e90`
- `0x100ad249`
- `0x100ad315`
- `0x100ad937`
- `0x100c32f0`
- `0x100c5707`
- `0x100c5dee`
- `0x100c5ed2`
- `0x100c5fd3`
- `0x100c60b0`
- `0x100d9d64`
- `0x100da399`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c62a5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c64a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c62a5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c64a4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c6202`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c6202`

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
  UnsyncPrvtc(0, a2);
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
0x100c60b0  mov     edi, edi
0x100c60b2  push    ebp
0x100c60b3  mov     ebp, esp
0x100c60b5  and     esp, 0FFFFFFF8h
0x100c60b8  sub     esp, 24h
0x100c60bb  push    ebx
0x100c60bc  push    esi
0x100c60bd  push    edi
0x100c60be  mov     edi, [ebp+arg_4]
0x100c60c1  mov     ebx, [edi+1Ch]
0x100c60c4  mov     esi, [edi]
0x100c60c6  mov     [esp+30h+var_C], ebx
0x100c60ca  mov     [esp+30h+var_20], esi
0x100c60ce  mov     eax, [ebx+104h]
0x100c60d4  mov     [esp+30h+var_4], eax
0x100c60d8  xor     eax, eax
0x100c60da  test    dword ptr [ebx+1Ch], 1000h
0x100c60e1  mov     [esp+30h+Block], eax
0x100c60e5  mov     [esp+30h+var_1C], eax
0x100c60e9  mov     [esp+30h+var_8], eax
0x100c60ed  jz      short loc_100C60F9
0x100c60ef  mov     eax, 0FFFFFBD7h
0x100c60f4  jmp     loc_100C6525
0x100c60f9  mov     eax, [esi+2Ch]
0x100c60fc  and     eax, 3
0x100c60ff  cmp     al, 3
0x100c6101  jnz     loc_100C6520
0x100c6107  cmp     [ebp+arg_8], 3
0x100c610b  jz      short loc_100C6130
0x100c610d  cmp     dword ptr [edi+10h], 0Ah
0x100c6111  jz      short loc_100C6130
0x100c6113  push    3
0x100c6115  push    edi
0x100c6116  push    [ebp+arg_0]
0x100c6119  call    _ErrJprvtPrepareUpdate@12; ErrJprvtPrepareUpdate(x,x,x)
0x100c611e  mov     esi, eax
0x100c6120  mov     [esp+30h+var_1C], esi
0x100c6124  test    esi, esi
0x100c6126  js      loc_100C6525
0x100c612c  mov     esi, [esp+30h+var_20]
0x100c6130  mov     eax, edi
0x100c6132  xor     edx, edx
0x100c6134  sub     eax, [edi]
0x100c6136  push    24h ; '$'
0x100c6138  sub     eax, 54h ; 'T'
0x100c613b  pop     ecx
0x100c613c  div     ecx
0x100c613e  lea     ecx, [edi+14h]
0x100c6141  mov     [ebx+8Ch], eax
0x100c6147  cmp     dword ptr [ecx], 0FFFFFFFFh
0x100c614a  mov     [esp+30h+var_18], eax
0x100c614e  jnz     short loc_100C6162
0x100c6150  mov     edx, [edi+4]
0x100c6153  push    ecx
0x100c6154  push    dword ptr [esi+490h]
0x100c615a  mov     ecx, [ebp+arg_0]
0x100c615d  call    _ErrIrowOfRecid@16; ErrIrowOfRecid(x,x,x,x)
0x100c6162  mov     eax, [ebp+arg_8]
0x100c6165  xor     ecx, ecx
0x100c6167  push    2
0x100c6169  pop     edx
0x100c616a  sub     eax, ecx
0x100c616c  jz      loc_100C62D8
0x100c6172  sub     eax, edx
0x100c6174  jz      short loc_100C61D4
0x100c6176  sub     eax, 1
0x100c6179  jz      short loc_100C618A
0x100c617b  sub     eax, 1
0x100c617e  jz      short loc_100C61D4
0x100c6180  mov     eax, 0FFFFFC15h
0x100c6185  jmp     loc_100C6525
0x100c618a  mov     edx, edi
0x100c618c  call    _UnsyncPrvtc@8; UnsyncPrvtc(x,x)
0x100c6191  cmp     dword ptr [edi+4], 0FFFFFFFFh
0x100c6195  jz      short loc_100C61B3
0x100c6197  push    3
0x100c6199  push    dword ptr [edi+4]
0x100c619c  push    [ebp+arg_0]
0x100c619f  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c61a4  mov     esi, eax
0x100c61a6  mov     [esp+30h+var_1C], esi
0x100c61aa  test    esi, esi
0x100c61ac  jns     short loc_100C61B3
0x100c61ae  jmp     loc_100C6525
0x100c61b3  and     dword ptr [edi+8], 0FFFFFFFCh
0x100c61b7  mov     ecx, ebx
0x100c61b9  push    0Ah
0x100c61bb  pop     edx
0x100c61bc  mov     byte ptr [edi+19h], 0
0x100c61c0  call    RVTSetUpdcolFlags
0x100c61c5  mov     eax, [esp+30h+var_20]
0x100c61c9  lea     esi, [eax+4ACh]
0x100c61cf  jmp     loc_100C642D
0x100c61d4  cmp     [edi+0Ch], edx
0x100c61d7  jz      short loc_100C61E3
0x100c61d9  mov     eax, 0FFFFF9BDh
0x100c61de  jmp     loc_100C6525
0x100c61e3  cmp     [ebx+104h], ecx
0x100c61e9  jz      short loc_100C61F6
0x100c61eb  push    1
0x100c61ed  xor     edx, edx
0x100c61ef  mov     ecx, ebx
0x100c61f1  call    _FCEnable@12; FCEnable(x,x,x)
0x100c61f6  add     esi, 4ACh
0x100c61fc  mov     [esp+30h+var_14], esi
0x100c6200  push    dword ptr [esi]; Size
0x100c6202  call    ds:__imp__malloc
0x100c6208  mov     edx, eax
0x100c620a  mov     [esp+34h+Block], edx
0x100c620e  pop     ecx
0x100c620f  test    edx, edx
0x100c6211  jz      loc_100C6429
0x100c6217  push    dword ptr [esi]; Size
0x100c6219  mov     ecx, ebx
0x100c621b  push    edx; void *
0x100c621c  mov     edx, [esp+38h+var_20]
0x100c6220  call    _ErrRVTSyncAllBM@16; ErrRVTSyncAllBM(x,x,x,x)
0x100c6225  mov     [esp+30h+var_1C], eax
0x100c6229  test    eax, eax
0x100c622b  js      loc_100C6429
0x100c6231  cmp     eax, 6A3h
0x100c6236  jz      short loc_100C62B3
0x100c6238  mov     eax, [esp+30h+var_20]
0x100c623c  test    byte ptr [eax+2Ch], 8
0x100c6240  jz      short loc_100C6283
0x100c6242  xor     eax, eax
0x100c6244  cmp     [ebx+100h], ax
0x100c624b  jbe     short loc_100C6258
0x100c624d  push    [esp+30h+Block]
0x100c6251  mov     edx, edi
0x100c6253  call    PartiallyUnsyncPrvtc
0x100c6258  lea     eax, [esp+30h+var_8]
0x100c625c  mov     edx, edi
0x100c625e  push    eax
0x100c625f  push    1
0x100c6261  mov     ecx, ebx
0x100c6263  call    _ErrRVTCompUpdateCS@16; ErrRVTCompUpdateCS(x,x,x,x)
0x100c6268  mov     esi, [esp+30h+var_14]
0x100c626c  mov     [esp+30h+var_1C], eax
0x100c6270  test    eax, eax
0x100c6272  js      loc_100C6429
0x100c6278  cmp     eax, 64Ah
0x100c627d  jz      short loc_100C62B3
0x100c627f  mov     eax, [esp+30h+var_20]
0x100c6283  push    [ebp+arg_8]
0x100c6286  mov     ecx, [ebp+arg_0]
0x100c6289  mov     edx, ebx
0x100c628b  push    eax
0x100c628c  call    ErrRVTPrepReplaceBTs
0x100c6291  mov     esi, [esp+30h+var_14]
0x100c6295  mov     [esp+30h+var_1C], eax
0x100c6299  test    eax, eax
0x100c629b  js      loc_100C6429
0x100c62a1  push    [esp+30h+Block]; Block
0x100c62a5  call    ds:__imp__free
0x100c62ab  pop     ecx
0x100c62ac  mov     eax, esi
0x100c62ae  jmp     loc_100C638D
0x100c62b3  cmp     dword ptr [ebx+104h], 0
0x100c62ba  jz      short loc_100C62C7
0x100c62bc  mov     edx, [esp+30h+var_20]
0x100c62c0  mov     ecx, ebx
0x100c62c2  call    _FCEjectCurrentRow@8; FCEjectCurrentRow(x,x)
0x100c62c7  mov     esi, [esp+30h+var_14]
0x100c62cb  mov     [esp+30h+var_1C], 0FFFFF9B5h
0x100c62d3  jmp     loc_100C6429
0x100c62d8  test    dword ptr [ebx+1Ch], 800h
0x100c62df  jz      short loc_100C62EB
0x100c62e1  mov     eax, 0FFFFFAE0h
0x100c62e6  jmp     loc_100C6525
0x100c62eb  cmp     [ebx+104h], ecx
0x100c62f1  jz      short loc_100C62FE
0x100c62f3  push    1
0x100c62f5  xor     edx, edx
0x100c62f7  mov     ecx, ebx
0x100c62f9  call    _FCEnable@12; FCEnable(x,x,x)
0x100c62fe  mov     ecx, [esp+30h+var_20]
0x100c6302  add     esi, 4ACh
0x100c6308  mov     eax, [esi]
0x100c630a  test    eax, eax
0x100c630c  jle     short loc_100C6347
0x100c630e  mov     edx, [ecx+4A8h]
0x100c6314  lea     eax, [edx+eax*4]
0x100c6317  mov     [esp+30h+var_14], eax
0x100c631b  mov     eax, [edx]
0x100c631d  cmp     edx, [esp+30h+var_14]
0x100c6321  jnb     short loc_100C6347
0x100c6323  mov     ebx, [esp+30h+var_14]
0x100c6327  mov     edi, [esp+30h+var_18]
0x100c632b  mov     eax, [eax+0E4h]
0x100c6331  add     edx, 4
0x100c6334  mov     byte ptr [eax+edi*8], 3
0x100c6338  cmp     edx, ebx
0x100c633a  jnb     short loc_100C6340
0x100c633c  mov     eax, [edx]
0x100c633e  jmp     short loc_100C632B
0x100c6340  mov     edi, [ebp+arg_4]
0x100c6343  mov     ebx, [esp+30h+var_C]
0x100c6347  cmp     dword ptr [esi], 1
0x100c634a  mov     eax, esi
0x100c634c  jnz     short loc_100C638D
0x100c634e  mov     eax, [ecx+4A8h]
0x100c6354  push    0
0x100c6356  mov     eax, [eax]
0x100c6358  mov     ecx, [eax+0E4h]
0x100c635e  mov     [esp+34h+var_14], ecx
0x100c6362  mov     ecx, [esp+34h+var_18]
0x100c6366  push    dword ptr [eax+ecx*4+28h]
0x100c636a  push    [ebp+arg_0]
0x100c636d  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c6372  mov     [esp+30h+var_1C], eax
0x100c6376  test    eax, eax
0x100c6378  js      loc_100C6429
0x100c637e  mov     eax, [esp+30h+var_14]
0x100c6382  mov     ecx, [esp+30h+var_18]
0x100c6386  or      dword ptr [eax+ecx*8+4], 1
0x100c638b  mov     eax, esi
0x100c638d  mov     esi, eax
0x100c638f  mov     eax, [ebp+arg_8]
0x100c6392  mov     [edi+10h], eax
0x100c6395  mov     edx, [esi]
0x100c6397  test    edx, edx
0x100c6399  jle     short loc_100C63DF
0x100c639b  mov     eax, [esp+30h+var_20]
0x100c639f  mov     ecx, [eax+4A8h]
0x100c63a5  lea     eax, [ecx+edx*4]
0x100c63a8  mov     edx, [ecx]
0x100c63aa  mov     [esp+30h+Block], eax
0x100c63ae  cmp     ecx, eax
0x100c63b0  jnb     short loc_100C63DF
0x100c63b2  mov     edi, [esp+30h+var_18]
0x100c63b6  mov     ebx, eax
0x100c63b8  mov     eax, [edx+0E4h]
0x100c63be  add     ecx, 4
0x100c63c1  and     dword ptr [eax+edi*8+4], 0FFFFFFC1h
0x100c63c6  mov     dword ptr [edx+0D8h], 0
0x100c63d0  cmp     ecx, ebx
0x100c63d2  jnb     short loc_100C63D8
0x100c63d4  mov     edx, [ecx]
0x100c63d6  jmp     short loc_100C63B8
0x100c63d8  mov     edi, [ebp+arg_4]
0x100c63db  mov     ebx, [esp+30h+var_C]
0x100c63df  mov     edx, [ebp+arg_8]
0x100c63e2  mov     ecx, ebx
0x100c63e4  call    RVTSetUpdcolFlags
0x100c63e9  and     dword ptr [edi+8], 0FFFFFFFEh
0x100c63ed  cmp     dword ptr [edi+4], 0FFFFFFFFh
0x100c63f1  mov     al, [edi+18h]
0x100c63f4  mov     [edi+19h], al
0x100c63f7  jz      loc_100C651C
0x100c63fd  mov     eax, [ebp+arg_8]
0x100c6400  cmp     eax, 4
0x100c6403  push    2
0x100c6405  pop     ecx
0x100c6406  cmovz   eax, ecx
0x100c6409  push    eax
0x100c640a  push    dword ptr [edi+4]
0x100c640d  push    [ebp+arg_0]
0x100c6410  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c6415  mov     [esp+30h+var_1C], eax
0x100c6419  mov     [esp+30h+Block], 0
0x100c6421  test    eax, eax
0x100c6423  jns     loc_100C64D7
0x100c6429  mov     eax, [esp+30h+var_20]
0x100c642d  mov     ecx, [esi]
0x100c642f  test    ecx, ecx
0x100c6431  jle     short loc_100C6481
0x100c6433  mov     eax, [eax+4A8h]
0x100c6439  mov     [esp+30h+var_14], eax
0x100c643d  lea     edx, [eax+ecx*4]
0x100c6440  mov     ecx, [eax]
0x100c6442  mov     [esp+30h+var_4], edx
0x100c6446  cmp     eax, edx
0x100c6448  jnb     short loc_100C6481
0x100c644a  mov     edi, eax
0x100c644c  mov     ebx, edx
0x100c644e  mov     eax, [esp+30h+var_18]
0x100c6452  mov     esi, [ecx+0E4h]
0x100c6458  push    3
0x100c645a  push    dword ptr [ecx+eax*4+28h]
0x100c645e  push    [ebp+arg_0]
0x100c6461  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100c6466  mov     eax, [esp+30h+var_18]
0x100c646a  add     edi, 4
0x100c646d  and     dword ptr [esi+eax*8+4], 0FFFFFFC0h
0x100c6472  cmp     edi, ebx
0x100c6474  jnb     short loc_100C647A
0x100c6476  mov     ecx, [edi]
0x100c6478  jmp     short loc_100C6452
0x100c647a  mov     edi, [ebp+arg_4]
0x100c647d  mov     ebx, [esp+30h+var_C]
0x100c6481  mov     eax, [esp+30h+var_20]
0x100c6485  test    byte ptr [eax+2Ch], 8
0x100c6489  jz      short loc_100C649B
0x100c648b  cmp     [esp+30h+var_8], 0
0x100c6490  jz      short loc_100C649B
0x100c6492  mov     edx, edi
0x100c6494  mov     ecx, ebx
0x100c6496  call    _RVTCancelLastChecksum@8; RVTCancelLastChecksum(x,x)
0x100c649b  mov     eax, [esp+30h+Block]
  ... truncated ...
```
