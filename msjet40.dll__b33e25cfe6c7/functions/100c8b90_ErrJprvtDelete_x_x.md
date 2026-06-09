# ErrJprvtDelete(x,x)

- ea: `0x100c8b90`
- end: `0x100c8f36`
- name: `_ErrJprvtDelete@8`
- size: `934`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10043bb0`
- `0x10043e90`
- `0x100ad249`
- `0x100c1edc`
- `0x100c30c1`
- `0x100c3157`
- `0x100c32f0`
- `0x100c5707`
- `0x100c5fd3`
- `0x100c602d`
- `0x100c60b0`
- `0x100c8b90`
- `0x100d9aac`
- `0x100d9d64`
- `0x100f1b15`
- `0x100f1b6b`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c8de5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c8f15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c8de5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c8f15`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c8c58`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c8c58`

## pseudocode

```c
int __stdcall ErrJprvtDelete(int a1, int a2)
{
  int v2; // ecx
  int v3; // edi
  unsigned int v4; // eax
  int Bookmark; // esi
  bool v6; // zf
  int result; // eax
  void *v8; // ecx
  int v9; // eax
  int updated; // eax
  unsigned int v11; // esi
  int v12; // ecx
  _DWORD *i; // ecx
  int v14; // ecx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // ecx
  int v20; // esi
  int v21; // eax
  int v22; // eax
  _DWORD *v23; // eax
  int v24; // eax
  int v25; // eax
  char v26; // cl
  void *v27; // [esp-4h] [ebp-34h]
  unsigned int v28; // [esp+Ch] [ebp-24h] BYREF
  unsigned int v29; // [esp+10h] [ebp-20h] BYREF
  unsigned int v30; // [esp+14h] [ebp-1Ch]
  _DWORD *v31; // [esp+18h] [ebp-18h] BYREF
  void *Block; // [esp+1Ch] [ebp-14h]
  int v33; // [esp+20h] [ebp-10h]
  int v34; // [esp+24h] [ebp-Ch]
  int v35; // [esp+28h] [ebp-8h]
  int v36; // [esp+2Ch] [ebp-4h]

  v2 = *(_DWORD *)a2;
  v3 = *(_DWORD *)(a2 + 28);
  v4 = (a2 - *(_DWORD *)a2 - 84) / 0x24u;
  v36 = *(_DWORD *)a2;
  v29 = 0;
  Bookmark = 0;
  v6 = (*(_DWORD *)(v3 + 28) & 0x1000) == 0;
  v30 = v4;
  v34 = 0;
  v31 = 0;
  v33 = 0;
  v35 = 0;
  if ( !v6 )
    return -1065;
  if ( (*(_BYTE *)(v2 + 44) & 3) != 3 )
    return -1809;
  if ( *(_DWORD *)(a2 + 12) != 2 )
    return -1603;
  *(_DWORD *)(v3 + 140) = v4;
  if ( *(_DWORD *)(a2 + 16) == 10 || (result = ErrJprvtPrepareUpdate(a1, (int *)a2, 3), Bookmark = result, result >= 0) )
  {
    if ( *(_DWORD *)(v3 + 260) )
    {
      ErrCheckFCRange(&v31);
      if ( v34 )
      {
        if ( *(_DWORD *)(v3 + 260) )
          FCEnable(1);
      }
    }
    v8 = _malloc(*(_DWORD *)(v36 + 1196));
    Block = v8;
    if ( !v8 )
      goto LABEL_48;
    v9 = ErrRVTSyncAllBM(v8, *(_DWORD *)(v36 + 1196));
    Bookmark = v9;
    if ( v9 < 0 )
      goto LABEL_47;
    if ( v9 == 1699 )
    {
      Bookmark = -1017;
      goto LABEL_47;
    }
    if ( (*(_BYTE *)(v36 + 44) & 8) != 0 )
    {
      if ( *(_WORD *)(v3 + 256) )
        PartiallyUnsyncPrvtc(Block);
      ForceCorrectIIsamCS(a2);
      updated = ErrRVTCompUpdateCS(0, 0);
      Bookmark = updated;
      if ( updated < 0 )
        goto LABEL_47;
      if ( updated == 1610 )
      {
        if ( *(_DWORD *)(v3 + 260) )
          FCEjectCurrentRow(v3, v36);
        Bookmark = -1611;
        goto LABEL_47;
      }
    }
    Bookmark = ErrRVTTransaction(v3, 1);
    if ( Bookmark < 0 )
    {
LABEL_47:
      _free(Block);
LABEL_48:
      if ( v34 )
      {
        if ( *(_DWORD *)(v3 + 260) )
          FCEnable(1);
      }
      return Bookmark;
    }
    v11 = *(_DWORD *)(v36 + 1192);
    v12 = *(_DWORD *)(v36 + 1196) - 1;
    v28 = v11;
    for ( i = (_DWORD *)(v11 + 4 * v12); ; i = v31 - 1 )
    {
      v31 = i;
      if ( (unsigned int)i < v11 )
        break;
      v14 = *i;
      if ( !*(_DWORD *)(v14 + 240) )
      {
        v15 = *(_DWORD *)(v14 + 160);
        if ( (v15 & 0x80u) == 0
          && *(char *)(v14 + 272) < 0
          && (v15 & 4) == 0
          && *(_BYTE *)(*(_DWORD *)(v14 + 228) + 8 * v30) == 2 )
        {
          v16 = ErrDispDelete(a1, *(_DWORD *)(v14 + 4 * v30 + 40));
          Bookmark = 0;
          if ( v16 != -1017 )
            Bookmark = v16;
          if ( Bookmark < 0 )
            goto LABEL_46;
          v17 = v33;
          v6 = Bookmark == 1625;
          v11 = v28;
          if ( v6 )
            v17 = 1;
          v33 = v17;
        }
      }
    }
    if ( v34 )
    {
      v18 = ErrFCKillRow(v3, *(_DWORD *)(a2 + 4));
      Bookmark = v18;
      if ( v18 < 0 )
      {
        if ( v18 == -1033 || v18 == -1011 || v18 == -1014 || v18 == -1808 )
          ErrFCDestroy(v3);
        goto LABEL_46;
      }
      if ( *(_DWORD *)(v3 + 260) )
        FCEnable(1);
    }
    if ( !*(_DWORD *)(v36 + 1168)
      || (Bookmark = ErrDispGetBookmark(a1, *(_DWORD *)(a2 + 4), &v29, 4, &v28), Bookmark >= 0) )
    {
      Bookmark = ErrDispDelete(a1, *(_DWORD *)(a2 + 4));
      if ( Bookmark >= 0 )
      {
        v19 = v30;
        v20 = v36;
        while ( v19 < 30 )
        {
          v21 = 36 * v19++;
          *(_DWORD *)(v21 + v20 + 104) = -1;
        }
        v22 = *(_DWORD *)(v20 + 1168);
        if ( v22 )
        {
          v23 = (_DWORD *)(v22 + 16);
          v35 = 0;
          while ( v23[1] < v29 )
          {
            if ( v23[1] == -1 )
              goto LABEL_68;
            v23 += 2;
          }
          if ( v23[1] != -1 )
          {
            if ( v23[1] == v29 )
              goto LABEL_69;
            do
            {
              --*v23;
              v23 += 2;
            }
            while ( v23[1] != -1 );
          }
LABEL_68:
          v35 = 1;
        }
LABEL_69:
        v24 = *(_DWORD *)(v20 + 1168);
        if ( !v24 || v35 || (SBFree(v24), v25 = SBInit(), (*(_DWORD *)(v20 + 1168) = v25) != 0) )
        {
          Bookmark = ErrRVTTransaction(v3, 2);
          if ( Bookmark >= 0 )
          {
            v26 = *(_BYTE *)(a2 + 24);
            v27 = Block;
            *(_DWORD *)(a2 + 8) |= 1u;
            *(_BYTE *)(a2 + 25) = 0;
            *(_DWORD *)(a2 + 12) = 3;
            *(_BYTE *)(a2 + 27) = v26;
            _free(v27);
            return v33 != 0 ? 0x659 : 0;
          }
        }
        else
        {
          Bookmark = -1011;
        }
      }
    }
LABEL_46:
    ErrRVTTransaction(v3, 3);
    goto LABEL_47;
  }
  return result;
}

```

## disassembly

```asm
0x100c8b90  mov     edi, edi
0x100c8b92  push    ebp
0x100c8b93  mov     ebp, esp
0x100c8b95  sub     esp, 24h
0x100c8b98  push    ebx
0x100c8b99  mov     ebx, [ebp+arg_4]
0x100c8b9c  xor     edx, edx
0x100c8b9e  push    esi
0x100c8b9f  push    edi
0x100c8ba0  mov     eax, ebx
0x100c8ba2  mov     ecx, [ebx]
0x100c8ba4  sub     eax, ecx
0x100c8ba6  sub     eax, 54h ; 'T'
0x100c8ba9  mov     edi, [ebx+1Ch]
0x100c8bac  push    24h ; '$'
0x100c8bae  pop     esi
0x100c8baf  div     esi
0x100c8bb1  mov     [ebp+var_4], ecx
0x100c8bb4  mov     edx, eax
0x100c8bb6  xor     eax, eax
0x100c8bb8  mov     [ebp+var_20], eax
0x100c8bbb  mov     esi, eax
0x100c8bbd  test    dword ptr [edi+1Ch], 1000h
0x100c8bc4  mov     [ebp+var_1C], edx
0x100c8bc7  mov     [ebp+var_C], eax
0x100c8bca  mov     [ebp+var_18], eax
0x100c8bcd  mov     [ebp+var_10], eax
0x100c8bd0  mov     [ebp+var_8], eax
0x100c8bd3  jz      short loc_100C8BDF
0x100c8bd5  mov     eax, 0FFFFFBD7h
0x100c8bda  jmp     loc_100C8F2F
0x100c8bdf  mov     eax, [ecx+2Ch]
0x100c8be2  and     eax, 3
0x100c8be5  cmp     al, 3
0x100c8be7  jnz     loc_100C8F2A
0x100c8bed  cmp     dword ptr [ebx+0Ch], 2
0x100c8bf1  jz      short loc_100C8BFD
0x100c8bf3  mov     eax, 0FFFFF9BDh
0x100c8bf8  jmp     loc_100C8F2F
0x100c8bfd  mov     [edi+8Ch], edx
0x100c8c03  cmp     dword ptr [ebx+10h], 0Ah
0x100c8c07  jz      short loc_100C8C1E
0x100c8c09  push    3
0x100c8c0b  push    ebx
0x100c8c0c  push    [ebp+arg_0]
0x100c8c0f  call    _ErrJprvtPrepareUpdate@12; ErrJprvtPrepareUpdate(x,x,x)
0x100c8c14  mov     esi, eax
0x100c8c16  test    esi, esi
0x100c8c18  js      loc_100C8F2F
0x100c8c1e  cmp     dword ptr [edi+104h], 0
0x100c8c25  jz      short loc_100C8C4F
0x100c8c27  lea     eax, [ebp+var_18]
0x100c8c2a  mov     ecx, edi
0x100c8c2c  push    eax
0x100c8c2d  lea     edx, [ebp+var_C]
0x100c8c30  call    _ErrCheckFCRange@12; ErrCheckFCRange(x,x,x)
0x100c8c35  cmp     [ebp+var_C], 0
0x100c8c39  jz      short loc_100C8C4F
0x100c8c3b  cmp     dword ptr [edi+104h], 0
0x100c8c42  jz      short loc_100C8C4F
0x100c8c44  push    1
0x100c8c46  xor     edx, edx
0x100c8c48  mov     ecx, edi
0x100c8c4a  call    _FCEnable@12; FCEnable(x,x,x)
0x100c8c4f  mov     eax, [ebp+var_4]
0x100c8c52  push    dword ptr [eax+4ACh]; Size
0x100c8c58  call    ds:__imp__malloc
0x100c8c5e  pop     ecx
0x100c8c5f  mov     ecx, eax
0x100c8c61  mov     [ebp+Block], ecx
0x100c8c64  test    ecx, ecx
0x100c8c66  jz      loc_100C8DEC
0x100c8c6c  mov     eax, [ebp+var_4]
0x100c8c6f  mov     edx, eax
0x100c8c71  push    dword ptr [eax+4ACh]; Size
0x100c8c77  push    ecx; void *
0x100c8c78  mov     ecx, edi
0x100c8c7a  call    _ErrRVTSyncAllBM@16; ErrRVTSyncAllBM(x,x,x,x)
0x100c8c7f  mov     esi, eax
0x100c8c81  test    esi, esi
0x100c8c83  js      loc_100C8DE2
0x100c8c89  cmp     esi, 6A3h
0x100c8c8f  jnz     short loc_100C8C9B
0x100c8c91  mov     esi, 0FFFFFC07h
0x100c8c96  jmp     loc_100C8DE2
0x100c8c9b  mov     eax, [ebp+var_4]
0x100c8c9e  test    byte ptr [eax+2Ch], 8
0x100c8ca2  jz      short loc_100C8CFE
0x100c8ca4  xor     eax, eax
0x100c8ca6  cmp     [edi+100h], ax
0x100c8cad  jbe     short loc_100C8CB9
0x100c8caf  push    [ebp+Block]
0x100c8cb2  mov     edx, ebx
0x100c8cb4  call    PartiallyUnsyncPrvtc
0x100c8cb9  mov     ecx, [ebp+arg_0]
0x100c8cbc  push    ebx
0x100c8cbd  call    ForceCorrectIIsamCS
0x100c8cc2  xor     eax, eax
0x100c8cc4  mov     edx, ebx
0x100c8cc6  push    eax
0x100c8cc7  push    eax
0x100c8cc8  mov     ecx, edi
0x100c8cca  call    _ErrRVTCompUpdateCS@16; ErrRVTCompUpdateCS(x,x,x,x)
0x100c8ccf  mov     esi, eax
0x100c8cd1  test    esi, esi
0x100c8cd3  js      loc_100C8DE2
0x100c8cd9  cmp     esi, 64Ah
0x100c8cdf  jnz     short loc_100C8CFE
0x100c8ce1  cmp     dword ptr [edi+104h], 0
0x100c8ce8  jz      short loc_100C8CF4
0x100c8cea  mov     edx, [ebp+var_4]
0x100c8ced  mov     ecx, edi
0x100c8cef  call    _FCEjectCurrentRow@8; FCEjectCurrentRow(x,x)
0x100c8cf4  mov     esi, 0FFFFF9B5h
0x100c8cf9  jmp     loc_100C8DE2
0x100c8cfe  xor     edx, edx
0x100c8d00  mov     ecx, edi
0x100c8d02  inc     edx
0x100c8d03  call    _ErrRVTTransaction@8; ErrRVTTransaction(x,x)
0x100c8d08  mov     esi, eax
0x100c8d0a  test    esi, esi
0x100c8d0c  js      loc_100C8DE2
0x100c8d12  mov     eax, [ebp+var_4]
0x100c8d15  mov     ecx, [eax+4ACh]
0x100c8d1b  mov     esi, [eax+4A8h]
0x100c8d21  dec     ecx
0x100c8d22  mov     [ebp+var_24], esi
0x100c8d25  lea     ecx, [esi+ecx*4]
0x100c8d28  jmp     short loc_100C8D90
0x100c8d2a  mov     ecx, [ecx]
0x100c8d2c  cmp     dword ptr [ecx+0F0h], 0
0x100c8d33  jnz     short loc_100C8D8A
0x100c8d35  mov     eax, [ecx+0A0h]
0x100c8d3b  test    al, al
0x100c8d3d  js      short loc_100C8D8A
0x100c8d3f  test    byte ptr [ecx+110h], 80h
0x100c8d46  jz      short loc_100C8D8A
0x100c8d48  test    al, 4
0x100c8d4a  jnz     short loc_100C8D8A
0x100c8d4c  mov     eax, [ecx+0E4h]
0x100c8d52  mov     edx, [ebp+var_1C]
0x100c8d55  cmp     byte ptr [eax+edx*8], 2
0x100c8d59  jnz     short loc_100C8D8A
0x100c8d5b  push    dword ptr [ecx+edx*4+28h]
0x100c8d5f  push    [ebp+arg_0]
0x100c8d62  call    _ErrDispDelete@8; ErrDispDelete(x,x)
0x100c8d67  xor     esi, esi
0x100c8d69  cmp     eax, 0FFFFFC07h
0x100c8d6e  cmovnz  esi, eax
0x100c8d71  test    esi, esi
0x100c8d73  js      short loc_100C8DD8
0x100c8d75  mov     eax, [ebp+var_10]
0x100c8d78  cmp     esi, 659h
0x100c8d7e  mov     esi, [ebp+var_24]
0x100c8d81  push    1
0x100c8d83  pop     ecx
0x100c8d84  cmovz   eax, ecx
0x100c8d87  mov     [ebp+var_10], eax
0x100c8d8a  mov     ecx, [ebp+var_18]
0x100c8d8d  sub     ecx, 4
0x100c8d90  mov     [ebp+var_18], ecx
0x100c8d93  cmp     ecx, esi
0x100c8d95  jnb     short loc_100C8D2A
0x100c8d97  cmp     [ebp+var_C], 0
0x100c8d9b  jz      loc_100C8E25
0x100c8da1  mov     edx, [ebx+4]
0x100c8da4  mov     ecx, edi
0x100c8da6  call    _ErrFCKillRow@8; ErrFCKillRow(x,x)
0x100c8dab  mov     esi, eax
0x100c8dad  test    esi, esi
0x100c8daf  jns     short loc_100C8E0F
0x100c8db1  cmp     esi, 0FFFFFBF7h
0x100c8db7  jz      short loc_100C8DD1
0x100c8db9  cmp     esi, 0FFFFFC0Dh
0x100c8dbf  jz      short loc_100C8DD1
0x100c8dc1  cmp     esi, 0FFFFFC0Ah
0x100c8dc7  jz      short loc_100C8DD1
0x100c8dc9  cmp     esi, 0FFFFF8F0h
0x100c8dcf  jnz     short loc_100C8DD8
0x100c8dd1  mov     ecx, edi
0x100c8dd3  call    _ErrFCDestroy@4; ErrFCDestroy(x)
0x100c8dd8  push    3
0x100c8dda  pop     edx
0x100c8ddb  mov     ecx, edi
0x100c8ddd  call    _ErrRVTTransaction@8; ErrRVTTransaction(x,x)
0x100c8de2  push    [ebp+Block]; Block
0x100c8de5  call    ds:__imp__free
0x100c8deb  pop     ecx
0x100c8dec  cmp     [ebp+var_C], 0
0x100c8df0  jz      short loc_100C8E08
0x100c8df2  cmp     dword ptr [edi+104h], 0
0x100c8df9  jz      short loc_100C8E08
0x100c8dfb  xor     eax, eax
0x100c8dfd  mov     ecx, edi
0x100c8dff  inc     eax
0x100c8e00  push    eax
0x100c8e01  mov     edx, eax
0x100c8e03  call    _FCEnable@12; FCEnable(x,x,x)
0x100c8e08  mov     eax, esi
0x100c8e0a  jmp     loc_100C8F2F
0x100c8e0f  cmp     dword ptr [edi+104h], 0
0x100c8e16  jz      short loc_100C8E25
0x100c8e18  xor     eax, eax
0x100c8e1a  mov     ecx, edi
0x100c8e1c  inc     eax
0x100c8e1d  push    eax
0x100c8e1e  mov     edx, eax
0x100c8e20  call    _FCEnable@12; FCEnable(x,x,x)
0x100c8e25  mov     eax, [ebp+var_4]
0x100c8e28  cmp     dword ptr [eax+490h], 0
0x100c8e2f  jz      short loc_100C8E4C
0x100c8e31  lea     eax, [ebp+var_24]
0x100c8e34  push    eax
0x100c8e35  push    4
0x100c8e37  lea     eax, [ebp+var_20]
0x100c8e3a  push    eax
0x100c8e3b  push    dword ptr [ebx+4]
0x100c8e3e  push    [ebp+arg_0]
0x100c8e41  call    _ErrDispGetBookmark@20; ErrDispGetBookmark(x,x,x,x,x)
0x100c8e46  mov     esi, eax
0x100c8e48  test    esi, esi
0x100c8e4a  js      short loc_100C8DD8
0x100c8e4c  push    dword ptr [ebx+4]
0x100c8e4f  push    [ebp+arg_0]
0x100c8e52  call    _ErrDispDelete@8; ErrDispDelete(x,x)
0x100c8e57  mov     esi, eax
0x100c8e59  test    esi, esi
0x100c8e5b  js      loc_100C8DD8
0x100c8e61  mov     ecx, [ebp+var_1C]
0x100c8e64  or      edx, 0FFFFFFFFh
0x100c8e67  mov     esi, [ebp+var_4]
0x100c8e6a  cmp     ecx, 1Eh
0x100c8e6d  jge     short loc_100C8E79
0x100c8e6f  imul    eax, ecx, 24h ; '$'
0x100c8e72  inc     ecx
0x100c8e73  mov     [eax+esi+68h], edx
0x100c8e77  jmp     short loc_100C8E6A
0x100c8e79  mov     eax, [esi+490h]
0x100c8e7f  test    eax, eax
0x100c8e81  jz      short loc_100C8EBA
0x100c8e83  mov     ecx, [ebp+var_20]
0x100c8e86  add     eax, 10h
0x100c8e89  mov     [ebp+var_8], 0
0x100c8e90  jmp     short loc_100C8E9A
0x100c8e92  cmp     [eax+4], edx
0x100c8e95  jz      short loc_100C8EB3
0x100c8e97  add     eax, 8
0x100c8e9a  cmp     [eax+4], ecx
0x100c8e9d  jb      short loc_100C8E92
0x100c8e9f  cmp     [eax+4], edx
0x100c8ea2  jz      short loc_100C8EB3
0x100c8ea4  cmp     [eax+4], ecx
0x100c8ea7  jz      short loc_100C8EBA
0x100c8ea9  dec     dword ptr [eax]
0x100c8eab  lea     eax, [eax+8]
0x100c8eae  cmp     [eax+4], edx
0x100c8eb1  jnz     short loc_100C8EA9
0x100c8eb3  mov     [ebp+var_8], 1
0x100c8eba  mov     eax, [esi+490h]
0x100c8ec0  test    eax, eax
0x100c8ec2  jz      short loc_100C8EE9
0x100c8ec4  cmp     [ebp+var_8], 0
0x100c8ec8  jnz     short loc_100C8EE9
0x100c8eca  push    eax
0x100c8ecb  call    _SBFree@4; SBFree(x)
0x100c8ed0  call    _SBInit@0; SBInit()
0x100c8ed5  mov     [esi+490h], eax
0x100c8edb  test    eax, eax
0x100c8edd  jnz     short loc_100C8EE9
0x100c8edf  mov     esi, 0FFFFFC0Dh
0x100c8ee4  jmp     loc_100C8DD8
0x100c8ee9  push    2
0x100c8eeb  pop     edx
0x100c8eec  mov     ecx, edi
0x100c8eee  call    _ErrRVTTransaction@8; ErrRVTTransaction(x,x)
0x100c8ef3  mov     esi, eax
0x100c8ef5  test    esi, esi
0x100c8ef7  js      loc_100C8DD8
0x100c8efd  mov     cl, [ebx+18h]
0x100c8f00  push    [ebp+Block]; Block
0x100c8f03  or      dword ptr [ebx+8], 1
0x100c8f07  mov     byte ptr [ebx+19h], 0
0x100c8f0b  mov     dword ptr [ebx+0Ch], 3
0x100c8f12  mov     [ebx+1Bh], cl
0x100c8f15  call    ds:__imp__free
0x100c8f1b  mov     eax, [ebp+var_10]
0x100c8f1e  neg     eax
0x100c8f20  pop     ecx
0x100c8f21  sbb     eax, eax
0x100c8f23  and     eax, 659h
0x100c8f28  jmp     short loc_100C8F2F
0x100c8f2a  mov     eax, 0FFFFF8EFh
0x100c8f2f  pop     edi
0x100c8f30  pop     esi
0x100c8f31  pop     ebx
0x100c8f32  leave
0x100c8f33  retn    8
```
