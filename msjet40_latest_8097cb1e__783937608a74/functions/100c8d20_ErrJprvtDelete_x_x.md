# ErrJprvtDelete(x,x)

- ea: `0x100c8d20`
- end: `0x100c90c6`
- name: `_ErrJprvtDelete@8`
- size: `934`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10043d40`
- `0x10044020`
- `0x100ad3d9`
- `0x100c206c`
- `0x100c3251`
- `0x100c32e7`
- `0x100c3480`
- `0x100c5897`
- `0x100c6163`
- `0x100c61bd`
- `0x100c6240`
- `0x100c8d20`
- `0x100d9c3c`
- `0x100d9ef4`
- `0x100f1ca5`
- `0x100f1cfb`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c8f75`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c90a5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c8f75`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100c90a5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c8de8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100c8de8`

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
0x100c8d20  mov     edi, edi
0x100c8d22  push    ebp
0x100c8d23  mov     ebp, esp
0x100c8d25  sub     esp, 24h
0x100c8d28  push    ebx
0x100c8d29  mov     ebx, [ebp+arg_4]
0x100c8d2c  xor     edx, edx
0x100c8d2e  push    esi
0x100c8d2f  push    edi
0x100c8d30  mov     eax, ebx
0x100c8d32  mov     ecx, [ebx]
0x100c8d34  sub     eax, ecx
0x100c8d36  sub     eax, 54h ; 'T'
0x100c8d39  mov     edi, [ebx+1Ch]
0x100c8d3c  push    24h ; '$'
0x100c8d3e  pop     esi
0x100c8d3f  div     esi
0x100c8d41  mov     [ebp+var_4], ecx
0x100c8d44  mov     edx, eax
0x100c8d46  xor     eax, eax
0x100c8d48  mov     [ebp+var_20], eax
0x100c8d4b  mov     esi, eax
0x100c8d4d  test    dword ptr [edi+1Ch], 1000h
0x100c8d54  mov     [ebp+var_1C], edx
0x100c8d57  mov     [ebp+var_C], eax
0x100c8d5a  mov     [ebp+var_18], eax
0x100c8d5d  mov     [ebp+var_10], eax
0x100c8d60  mov     [ebp+var_8], eax
0x100c8d63  jz      short loc_100C8D6F
0x100c8d65  mov     eax, 0FFFFFBD7h
0x100c8d6a  jmp     loc_100C90BF
0x100c8d6f  mov     eax, [ecx+2Ch]
0x100c8d72  and     eax, 3
0x100c8d75  cmp     al, 3
0x100c8d77  jnz     loc_100C90BA
0x100c8d7d  cmp     dword ptr [ebx+0Ch], 2
0x100c8d81  jz      short loc_100C8D8D
0x100c8d83  mov     eax, 0FFFFF9BDh
0x100c8d88  jmp     loc_100C90BF
0x100c8d8d  mov     [edi+8Ch], edx
0x100c8d93  cmp     dword ptr [ebx+10h], 0Ah
0x100c8d97  jz      short loc_100C8DAE
0x100c8d99  push    3
0x100c8d9b  push    ebx
0x100c8d9c  push    [ebp+arg_0]
0x100c8d9f  call    _ErrJprvtPrepareUpdate@12; ErrJprvtPrepareUpdate(x,x,x)
0x100c8da4  mov     esi, eax
0x100c8da6  test    esi, esi
0x100c8da8  js      loc_100C90BF
0x100c8dae  cmp     dword ptr [edi+104h], 0
0x100c8db5  jz      short loc_100C8DDF
0x100c8db7  lea     eax, [ebp+var_18]
0x100c8dba  mov     ecx, edi
0x100c8dbc  push    eax
0x100c8dbd  lea     edx, [ebp+var_C]
0x100c8dc0  call    _ErrCheckFCRange@12; ErrCheckFCRange(x,x,x)
0x100c8dc5  cmp     [ebp+var_C], 0
0x100c8dc9  jz      short loc_100C8DDF
0x100c8dcb  cmp     dword ptr [edi+104h], 0
0x100c8dd2  jz      short loc_100C8DDF
0x100c8dd4  push    1
0x100c8dd6  xor     edx, edx
0x100c8dd8  mov     ecx, edi
0x100c8dda  call    _FCEnable@12; FCEnable(x,x,x)
0x100c8ddf  mov     eax, [ebp+var_4]
0x100c8de2  push    dword ptr [eax+4ACh]; Size
0x100c8de8  call    ds:__imp__malloc
0x100c8dee  pop     ecx
0x100c8def  mov     ecx, eax
0x100c8df1  mov     [ebp+Block], ecx
0x100c8df4  test    ecx, ecx
0x100c8df6  jz      loc_100C8F7C
0x100c8dfc  mov     eax, [ebp+var_4]
0x100c8dff  mov     edx, eax
0x100c8e01  push    dword ptr [eax+4ACh]; Size
0x100c8e07  push    ecx; void *
0x100c8e08  mov     ecx, edi
0x100c8e0a  call    _ErrRVTSyncAllBM@16; ErrRVTSyncAllBM(x,x,x,x)
0x100c8e0f  mov     esi, eax
0x100c8e11  test    esi, esi
0x100c8e13  js      loc_100C8F72
0x100c8e19  cmp     esi, 6A3h
0x100c8e1f  jnz     short loc_100C8E2B
0x100c8e21  mov     esi, 0FFFFFC07h
0x100c8e26  jmp     loc_100C8F72
0x100c8e2b  mov     eax, [ebp+var_4]
0x100c8e2e  test    byte ptr [eax+2Ch], 8
0x100c8e32  jz      short loc_100C8E8E
0x100c8e34  xor     eax, eax
0x100c8e36  cmp     [edi+100h], ax
0x100c8e3d  jbe     short loc_100C8E49
0x100c8e3f  push    [ebp+Block]
0x100c8e42  mov     edx, ebx
0x100c8e44  call    PartiallyUnsyncPrvtc
0x100c8e49  mov     ecx, [ebp+arg_0]
0x100c8e4c  push    ebx
0x100c8e4d  call    ForceCorrectIIsamCS
0x100c8e52  xor     eax, eax
0x100c8e54  mov     edx, ebx
0x100c8e56  push    eax
0x100c8e57  push    eax
0x100c8e58  mov     ecx, edi
0x100c8e5a  call    _ErrRVTCompUpdateCS@16; ErrRVTCompUpdateCS(x,x,x,x)
0x100c8e5f  mov     esi, eax
0x100c8e61  test    esi, esi
0x100c8e63  js      loc_100C8F72
0x100c8e69  cmp     esi, 64Ah
0x100c8e6f  jnz     short loc_100C8E8E
0x100c8e71  cmp     dword ptr [edi+104h], 0
0x100c8e78  jz      short loc_100C8E84
0x100c8e7a  mov     edx, [ebp+var_4]
0x100c8e7d  mov     ecx, edi
0x100c8e7f  call    _FCEjectCurrentRow@8; FCEjectCurrentRow(x,x)
0x100c8e84  mov     esi, 0FFFFF9B5h
0x100c8e89  jmp     loc_100C8F72
0x100c8e8e  xor     edx, edx
0x100c8e90  mov     ecx, edi
0x100c8e92  inc     edx
0x100c8e93  call    _ErrRVTTransaction@8; ErrRVTTransaction(x,x)
0x100c8e98  mov     esi, eax
0x100c8e9a  test    esi, esi
0x100c8e9c  js      loc_100C8F72
0x100c8ea2  mov     eax, [ebp+var_4]
0x100c8ea5  mov     ecx, [eax+4ACh]
0x100c8eab  mov     esi, [eax+4A8h]
0x100c8eb1  dec     ecx
0x100c8eb2  mov     [ebp+var_24], esi
0x100c8eb5  lea     ecx, [esi+ecx*4]
0x100c8eb8  jmp     short loc_100C8F20
0x100c8eba  mov     ecx, [ecx]
0x100c8ebc  cmp     dword ptr [ecx+0F0h], 0
0x100c8ec3  jnz     short loc_100C8F1A
0x100c8ec5  mov     eax, [ecx+0A0h]
0x100c8ecb  test    al, al
0x100c8ecd  js      short loc_100C8F1A
0x100c8ecf  test    byte ptr [ecx+110h], 80h
0x100c8ed6  jz      short loc_100C8F1A
0x100c8ed8  test    al, 4
0x100c8eda  jnz     short loc_100C8F1A
0x100c8edc  mov     eax, [ecx+0E4h]
0x100c8ee2  mov     edx, [ebp+var_1C]
0x100c8ee5  cmp     byte ptr [eax+edx*8], 2
0x100c8ee9  jnz     short loc_100C8F1A
0x100c8eeb  push    dword ptr [ecx+edx*4+28h]
0x100c8eef  push    [ebp+arg_0]
0x100c8ef2  call    _ErrDispDelete@8; ErrDispDelete(x,x)
0x100c8ef7  xor     esi, esi
0x100c8ef9  cmp     eax, 0FFFFFC07h
0x100c8efe  cmovnz  esi, eax
0x100c8f01  test    esi, esi
0x100c8f03  js      short loc_100C8F68
0x100c8f05  mov     eax, [ebp+var_10]
0x100c8f08  cmp     esi, 659h
0x100c8f0e  mov     esi, [ebp+var_24]
0x100c8f11  push    1
0x100c8f13  pop     ecx
0x100c8f14  cmovz   eax, ecx
0x100c8f17  mov     [ebp+var_10], eax
0x100c8f1a  mov     ecx, [ebp+var_18]
0x100c8f1d  sub     ecx, 4
0x100c8f20  mov     [ebp+var_18], ecx
0x100c8f23  cmp     ecx, esi
0x100c8f25  jnb     short loc_100C8EBA
0x100c8f27  cmp     [ebp+var_C], 0
0x100c8f2b  jz      loc_100C8FB5
0x100c8f31  mov     edx, [ebx+4]
0x100c8f34  mov     ecx, edi
0x100c8f36  call    _ErrFCKillRow@8; ErrFCKillRow(x,x)
0x100c8f3b  mov     esi, eax
0x100c8f3d  test    esi, esi
0x100c8f3f  jns     short loc_100C8F9F
0x100c8f41  cmp     esi, 0FFFFFBF7h
0x100c8f47  jz      short loc_100C8F61
0x100c8f49  cmp     esi, 0FFFFFC0Dh
0x100c8f4f  jz      short loc_100C8F61
0x100c8f51  cmp     esi, 0FFFFFC0Ah
0x100c8f57  jz      short loc_100C8F61
0x100c8f59  cmp     esi, 0FFFFF8F0h
0x100c8f5f  jnz     short loc_100C8F68
0x100c8f61  mov     ecx, edi
0x100c8f63  call    _ErrFCDestroy@4; ErrFCDestroy(x)
0x100c8f68  push    3
0x100c8f6a  pop     edx
0x100c8f6b  mov     ecx, edi
0x100c8f6d  call    _ErrRVTTransaction@8; ErrRVTTransaction(x,x)
0x100c8f72  push    [ebp+Block]; Block
0x100c8f75  call    ds:__imp__free
0x100c8f7b  pop     ecx
0x100c8f7c  cmp     [ebp+var_C], 0
0x100c8f80  jz      short loc_100C8F98
0x100c8f82  cmp     dword ptr [edi+104h], 0
0x100c8f89  jz      short loc_100C8F98
0x100c8f8b  xor     eax, eax
0x100c8f8d  mov     ecx, edi
0x100c8f8f  inc     eax
0x100c8f90  push    eax
0x100c8f91  mov     edx, eax
0x100c8f93  call    _FCEnable@12; FCEnable(x,x,x)
0x100c8f98  mov     eax, esi
0x100c8f9a  jmp     loc_100C90BF
0x100c8f9f  cmp     dword ptr [edi+104h], 0
0x100c8fa6  jz      short loc_100C8FB5
0x100c8fa8  xor     eax, eax
0x100c8faa  mov     ecx, edi
0x100c8fac  inc     eax
0x100c8fad  push    eax
0x100c8fae  mov     edx, eax
0x100c8fb0  call    _FCEnable@12; FCEnable(x,x,x)
0x100c8fb5  mov     eax, [ebp+var_4]
0x100c8fb8  cmp     dword ptr [eax+490h], 0
0x100c8fbf  jz      short loc_100C8FDC
0x100c8fc1  lea     eax, [ebp+var_24]
0x100c8fc4  push    eax
0x100c8fc5  push    4
0x100c8fc7  lea     eax, [ebp+var_20]
0x100c8fca  push    eax
0x100c8fcb  push    dword ptr [ebx+4]
0x100c8fce  push    [ebp+arg_0]
0x100c8fd1  call    _ErrDispGetBookmark@20; ErrDispGetBookmark(x,x,x,x,x)
0x100c8fd6  mov     esi, eax
0x100c8fd8  test    esi, esi
0x100c8fda  js      short loc_100C8F68
0x100c8fdc  push    dword ptr [ebx+4]
0x100c8fdf  push    [ebp+arg_0]
0x100c8fe2  call    _ErrDispDelete@8; ErrDispDelete(x,x)
0x100c8fe7  mov     esi, eax
0x100c8fe9  test    esi, esi
0x100c8feb  js      loc_100C8F68
0x100c8ff1  mov     ecx, [ebp+var_1C]
0x100c8ff4  or      edx, 0FFFFFFFFh
0x100c8ff7  mov     esi, [ebp+var_4]
0x100c8ffa  cmp     ecx, 1Eh
0x100c8ffd  jge     short loc_100C9009
0x100c8fff  imul    eax, ecx, 24h ; '$'
0x100c9002  inc     ecx
0x100c9003  mov     [eax+esi+68h], edx
0x100c9007  jmp     short loc_100C8FFA
0x100c9009  mov     eax, [esi+490h]
0x100c900f  test    eax, eax
0x100c9011  jz      short loc_100C904A
0x100c9013  mov     ecx, [ebp+var_20]
0x100c9016  add     eax, 10h
0x100c9019  mov     [ebp+var_8], 0
0x100c9020  jmp     short loc_100C902A
0x100c9022  cmp     [eax+4], edx
0x100c9025  jz      short loc_100C9043
0x100c9027  add     eax, 8
0x100c902a  cmp     [eax+4], ecx
0x100c902d  jb      short loc_100C9022
0x100c902f  cmp     [eax+4], edx
0x100c9032  jz      short loc_100C9043
0x100c9034  cmp     [eax+4], ecx
0x100c9037  jz      short loc_100C904A
0x100c9039  dec     dword ptr [eax]
0x100c903b  lea     eax, [eax+8]
0x100c903e  cmp     [eax+4], edx
0x100c9041  jnz     short loc_100C9039
0x100c9043  mov     [ebp+var_8], 1
0x100c904a  mov     eax, [esi+490h]
0x100c9050  test    eax, eax
0x100c9052  jz      short loc_100C9079
0x100c9054  cmp     [ebp+var_8], 0
0x100c9058  jnz     short loc_100C9079
0x100c905a  push    eax
0x100c905b  call    _SBFree@4; SBFree(x)
0x100c9060  call    _SBInit@0; SBInit()
0x100c9065  mov     [esi+490h], eax
0x100c906b  test    eax, eax
0x100c906d  jnz     short loc_100C9079
0x100c906f  mov     esi, 0FFFFFC0Dh
0x100c9074  jmp     loc_100C8F68
0x100c9079  push    2
0x100c907b  pop     edx
0x100c907c  mov     ecx, edi
0x100c907e  call    _ErrRVTTransaction@8; ErrRVTTransaction(x,x)
0x100c9083  mov     esi, eax
0x100c9085  test    esi, esi
0x100c9087  js      loc_100C8F68
0x100c908d  mov     cl, [ebx+18h]
0x100c9090  push    [ebp+Block]; Block
0x100c9093  or      dword ptr [ebx+8], 1
0x100c9097  mov     byte ptr [ebx+19h], 0
0x100c909b  mov     dword ptr [ebx+0Ch], 3
0x100c90a2  mov     [ebx+1Bh], cl
0x100c90a5  call    ds:__imp__free
0x100c90ab  mov     eax, [ebp+var_10]
0x100c90ae  neg     eax
0x100c90b0  pop     ecx
0x100c90b1  sbb     eax, eax
0x100c90b3  and     eax, 659h
0x100c90b8  jmp     short loc_100C90BF
0x100c90ba  mov     eax, 0FFFFF8EFh
0x100c90bf  pop     edi
0x100c90c0  pop     esi
0x100c90c1  pop     ebx
0x100c90c2  leave
0x100c90c3  retn    8
```
