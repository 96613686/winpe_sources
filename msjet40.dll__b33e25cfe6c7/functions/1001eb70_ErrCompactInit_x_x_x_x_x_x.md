# ErrCompactInit(x,x,x,x,x,x)

- ea: `0x1001eb70`
- end: `0x1001f47c`
- name: `_ErrCompactInit@24`
- size: `2316`
- prototype: `int __fastcall(int, int, __int16 *, unsigned int, const unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x10025b10`

## callees

- `0x100129b0`
- `0x10016d00`
- `0x10016ed0`
- `0x10017010`
- `0x10017860`
- `0x1001a180`
- `0x1001ea70`
- `0x1001eb70`
- `0x10025760`
- `0x10025940`
- `0x1002a530`
- `0x1003a7f0`
- `0x100429d0`
- `0x10042ed0`
- `0x10042fb0`
- `0x10122f60`
- `0x101243f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ed6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ed87`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ed9f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f414`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f431`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f44e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ed6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ed87`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001ed9f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f414`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f431`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f44e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ed1e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001f217`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ed1e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001f217`

## pseudocode

```c
int __fastcall ErrCompactInit(int a1, int a2, __int16 *a3, unsigned int a4, const unsigned __int16 *a5, __int16 a6)
{
  const unsigned __int16 *v7; // esi
  void *v8; // ebx
  int result; // eax
  int DatabaseInfo; // edi
  char v11; // bl
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  BOOL v15; // ecx
  size_t v16; // edi
  unsigned __int16 *v17; // eax
  unsigned __int16 *v18; // edx
  int v19; // esi
  unsigned int v20; // ecx
  int v21; // eax
  char *v22; // edx
  char *v23; // ecx
  __int16 v24; // ax
  char *v25; // ecx
  unsigned int i; // edx
  unsigned __int16 v27; // ax
  int v28; // ecx
  unsigned int v29; // edx
  unsigned int v30; // eax
  int v31; // ebx
  _DWORD *v32; // ecx
  int v33; // eax
  _DWORD *v34; // esi
  int v35; // eax
  __int16 *v36; // ebx
  _WORD *v37; // eax
  __int16 v38; // ax
  __int16 v39; // di
  __int16 v40; // cx
  unsigned __int16 *v41; // edx
  int v42; // eax
  int v43; // eax
  int v44; // eax
  unsigned __int16 v45; // ax
  char *v46; // ecx
  _WORD *v47; // edx
  unsigned __int16 v48; // si
  unsigned __int16 v49; // ax
  __int16 v50; // ax
  __int16 *v51; // edx
  __int16 v52; // si
  __int16 v53; // ax
  void *v54; // ebx
  size_t v55; // esi
  unsigned int v56; // esi
  int v57; // edi
  int v58; // eax
  _DWORD *v59; // ebx
  _DWORD *v60; // esi
  int v61; // esi
  void *ObjectInfo; // eax
  int v63; // eax
  void *v64; // ebx
  int v65; // [esp-14h] [ebp-10A4h]
  int v66; // [esp-10h] [ebp-10A0h]
  _DWORD v67[4]; // [esp+10h] [ebp-1080h] BYREF
  unsigned int v68; // [esp+20h] [ebp-1070h]
  __int16 *v69; // [esp+24h] [ebp-106Ch]
  int v70; // [esp+28h] [ebp-1068h]
  int v71; // [esp+2Ch] [ebp-1064h] BYREF
  int v72; // [esp+30h] [ebp-1060h] BYREF
  unsigned int v73; // [esp+34h] [ebp-105Ch]
  unsigned int *v74; // [esp+38h] [ebp-1058h]
  void *v75; // [esp+3Ch] [ebp-1054h]
  unsigned int v76; // [esp+40h] [ebp-1050h]
  int v77; // [esp+44h] [ebp-104Ch] BYREF
  char *v78; // [esp+48h] [ebp-1048h]
  int v79; // [esp+4Ch] [ebp-1044h]
  void *Block; // [esp+50h] [ebp-1040h]
  unsigned int v81; // [esp+54h] [ebp-103Ch] BYREF
  int v82; // [esp+58h] [ebp-1038h]
  void *v83; // [esp+5Ch] [ebp-1034h]
  _BYTE v84[4096]; // [esp+60h] [ebp-1030h] BYREF
  _WORD v85[22]; // [esp+1060h] [ebp-30h] BYREF

  v82 = a1;
  v7 = a5;
  v8 = 0;
  v69 = a3;
  v68 = a4;
  Block = 0;
  v75 = 0;
  v70 = 0;
  v65 = *(_DWORD *)(a1 + 4);
  v73 = 0;
  v79 = v65;
  result = ErrOpenDatabase(v65, a2, a3, &v77, 73);
  v76 = result;
  if ( result < 0 )
    return result;
  v78 = 0;
  v74 = (unsigned int *)(a1 + 16);
  DatabaseInfo = ErrDispGetDatabaseInfo(v79, v77, a1 + 16, 4, 8);
  if ( DatabaseInfo < 0 )
    goto LABEL_28;
  v11 = a6;
  if ( (a6 & 0x1000) != 0 )
  {
    v12 = *v74;
    if ( *v74 > 0x20000 )
    {
      if ( v12 == 196608 )
        v11 = a6 | 0x40;
    }
    else if ( *v74 == 0x20000 )
    {
      v11 = a6 | 0x20;
    }
    else
    {
      v13 = v12 - 0x10000;
      if ( v13 )
      {
        if ( v13 == 1 )
          v11 = a6 | 0x10;
      }
      else
      {
        v11 = a6 | 0x18;
      }
    }
  }
  if ( (v11 & 3) != 0 )
  {
    v14 = *v74 < 0x20000
        ? ErrSecValidateAccess(L"Tables", L"MSysObjects", 0, 0, 0x40000, v74)
        : ErrSecValidateAccess(L"Databases", L"MSysDb", 0, 0, 0x40000, v74);
    DatabaseInfo = v14;
    if ( v14 < 0 )
      goto LABEL_27;
  }
  if ( (v11 & 1) != 0 )
  {
    v15 = 1;
  }
  else
  {
    v15 = 0;
    if ( (v11 & 2) == 0 )
      v15 = v76 == 1208;
  }
  v76 = v15;
  if ( (v11 & 0x10) != 0 )
  {
    v73 = v15 | ((v11 & 8 | 0x10u) >> 2);
    v76 = v73;
  }
  if ( a5 )
  {
    v16 = 2 * wcslen(a5) + 44;
    v81 = v16;
    v17 = (unsigned __int16 *)_malloc(v16);
    v18 = v17;
    v78 = (char *)v17;
    if ( !v17 )
    {
      DatabaseInfo = -1011;
LABEL_27:
      v8 = 0;
LABEL_28:
      v19 = v82;
LABEL_29:
      ErrDispCloseDatabase(v79, v77, 0);
      if ( Block != v78 && Block )
        _free(Block);
      if ( v75 && v70 )
        _free(v75);
      if ( v8 )
      {
        if ( v8 != (void *)(v19 + 2522) )
          _free(v8);
      }
      return DatabaseInfo;
    }
    v83 = v17;
    v20 = v16 >> 1;
    if ( v16 >> 1 <= 1 )
    {
LABEL_45:
      if ( !v20 )
        goto LABEL_48;
    }
    else
    {
      v78 = (char *)v17;
      v81 = v16;
      v83 = v17;
      while ( 1 )
      {
        v21 = *v7;
        if ( !(_WORD)v21 || v21 == 59 )
          break;
        *v18 = v21;
        --v20;
        ++v18;
        ++v7;
        v78 = (char *)v18;
        if ( v20 <= 1 )
          goto LABEL_45;
      }
    }
    *v18 = 0;
  }
  else
  {
    v81 = 32512;
    v78 = (char *)(v82 + 2522);
    v83 = (void *)(v82 + 2522);
  }
LABEL_48:
  DatabaseInfo = ErrDispGetDatabaseInfo(v79, v77, &v71, 4, 18);
  v81 >>= 1;
  WCSCPY2(v81 - ((v78 - (_BYTE *)v83) >> 1));
  Block = &v78[2 * wcslen((const unsigned __int16 *)v78)];
  DecodeUintW(v71 & 0xFFFEFF, 10);
  v22 = (char *)Block;
  v23 = (char *)Block;
  Block = (char *)Block + 2;
  do
  {
    v24 = *(_WORD *)v23;
    v23 += 2;
  }
  while ( v24 );
  v25 = &v22[2 * ((v23 - (_BYTE *)Block) >> 1)];
  if ( v7 )
  {
    for ( i = v81 - ((v25 - (_BYTE *)v83) >> 1); *v7; v25 += 2 )
    {
      if ( i <= 1 )
        break;
      v27 = *v7;
      --i;
      ++v7;
      *(_WORD *)v25 = v27;
    }
  }
  if ( v81 != (v25 - (_BYTE *)v83) >> 1 )
    *(_WORD *)v25 = 0;
  v78 = (char *)v83;
  Block = v83;
  v81 = (unsigned int)v83;
  if ( (v11 & 0x38) != 0
    || (v11 & 0x40) != 0
    || (v28 = wcslen((const unsigned __int16 *)v83), v28 < 7)
    || v28 > 7 && *((_WORD *)v83 + 7) != 59
    || WCSNICMP(7) && WCSNICMP(7) )
  {
    DatabaseInfo = ErrGenIISAMConnectString(&v81);
    Block = (void *)v81;
  }
  if ( DatabaseInfo < 0 )
    goto LABEL_111;
  v29 = v73;
  v30 = *v74;
  if ( *v74 > 0x10001 )
  {
    if ( (v73 & 4) != 0 || (v11 & 0x20) != 0 && v30 >= 0x30000 || (v11 & 0x40) != 0 && v30 >= 0x40000 )
    {
      v8 = v83;
      DatabaseInfo = -1067;
      goto LABEL_28;
    }
    v31 = 0;
  }
  else
  {
    v31 = 2 * (v30 == 0x10000) + 4;
  }
  v32 = (_DWORD *)v82;
  v33 = 6;
  *(_DWORD *)(v82 + 2336) = v31;
  v34 = v32 + 587;
  v32[585] = v29;
  v74 = (unsigned int *)(v31 & 4);
  if ( (v31 & 4) == 0 )
    v33 = 9;
  v32[586] = v33;
  v35 = ErrDispGetDatabaseInfo(v79, v77, v32 + 587, 4, 13);
  DatabaseInfo = v35;
  if ( v35 == -1003 )
  {
    *v34 = 0;
    goto LABEL_80;
  }
  if ( v35 < 0 )
  {
LABEL_111:
    v8 = v83;
    goto LABEL_28;
  }
  if ( *v34 )
    v76 |= 0x80u;
LABEL_80:
  v36 = v69;
  if ( v69 )
  {
    v38 = *v69;
    v39 = 0;
    v85[0] = 0;
    if ( v38 )
    {
      v40 = v38;
      while ( 1 )
      {
        v41 = (unsigned __int16 *)++v36;
        if ( v40 == 59 && wcslen(v41) >= 3 )
        {
          v42 = *v41;
          if ( v42 == 80 || v42 == 112 )
          {
            v43 = v41[1];
            if ( v43 == 87 || v43 == 119 )
            {
              v44 = v41[2];
              if ( v44 == 68 || v44 == 100 )
                break;
            }
          }
        }
        v40 = *v36;
        if ( !*v36 )
          goto LABEL_106;
      }
      v45 = v41[3];
      v46 = (char *)v85;
      v47 = v41 + 3;
      if ( v45 )
      {
        v48 = v45;
        while ( v48 != 61 )
        {
          v49 = v47[1];
          ++v47;
          v48 = v49;
          if ( !v49 )
            goto LABEL_106;
        }
        if ( *v47 )
        {
          v50 = v47[1];
          v51 = v47 + 1;
          if ( v50 )
          {
            v52 = v50;
            while ( v52 != 59 )
            {
              if ( (int)((v46 - (char *)v85) & 0xFFFFFFFE) >= 40 )
              {
                DatabaseInfo = -1905;
                goto LABEL_111;
              }
              v53 = *v51++;
              *(_WORD *)v46 = v53;
              v46 += 2;
              v52 = *v51;
              if ( !*v51 )
                break;
            }
          }
          *(_WORD *)v46 = 0;
          v39 = v85[0];
        }
      }
    }
LABEL_106:
    v54 = Block;
    v55 = 52;
    if ( Block )
      v55 = 2 * wcslen((const unsigned __int16 *)Block) + 52;
    v37 = _malloc(v55);
    v75 = v37;
    if ( !v37 )
    {
      v8 = v83;
      DatabaseInfo = -1011;
      goto LABEL_28;
    }
    v56 = v55 >> 1;
    *v37 = 0;
    v70 = 1;
    if ( v54 )
    {
      WCSCPY2(v56);
      v37 = v75;
    }
    if ( v39 )
    {
      WCSCAT2(v37, L";Pwd=", v56);
      WCSCAT2(v75, v85, v56);
      v37 = v75;
    }
  }
  else
  {
    v37 = Block;
    v75 = Block;
  }
  v57 = v79;
  v58 = ErrCreateDatabase(v79, v68, v37, &v72, v76);
  if ( v58 < 0 )
  {
    v19 = v82;
    v8 = v83;
    DatabaseInfo = -1201;
    if ( v58 == -1202 )
      v58 = -1201;
    *(_DWORD *)(v82 + 24) = v58;
    goto LABEL_29;
  }
  v59 = (_DWORD *)v82;
  v60 = (_DWORD *)(v82 + 20);
  DatabaseInfo = ErrDispGetDatabaseInfo(v57, v72, v82 + 20, 4, 8);
  if ( DatabaseInfo >= 0 && *v60 < v59[4] )
  {
    DatabaseInfo = -1067;
LABEL_127:
    ErrDispCloseDatabase(v79, v72, 0);
    v8 = v83;
    goto LABEL_28;
  }
  v61 = v79;
  if ( v74 && (v73 & 4) == 0 )
    DatabaseInfo = ErrSecGiveDefPermissions(v79, L";", v72, 7);
  if ( DatabaseInfo < 0 )
    goto LABEL_127;
  v59[2] = v77;
  v66 = v72;
  v59[3] = v72;
  ErrDispGetDatabaseInfo(v61, v66, &v71, 4, 18);
  v59[7] = (unsigned __int16)v71;
  v67[3] = v59 + 10;
  v67[0] = 48;
  ObjectInfo = (void *)ErrDispGetObjectInfo(v61, v77, 0, 0, 0, v67, 1);
  if ( (int)ObjectInfo < 0 && ObjectInfo != (void *)-1211 )
  {
    ErrGetErrorText((int)v59, ObjectInfo, (int)v84);
    v63 = ErrCompactLogError(v84, L"MSysObjects", 0);
    if ( v63 < 0 )
      v59[591] = v63;
    v59[589] = 1;
  }
  v64 = v83;
  if ( Block != v83 && Block )
    _free(Block);
  if ( v75 && v70 )
    _free(v75);
  if ( v64 && v64 != (void *)(v82 + 2522) )
    _free(v64);
  return 0;
}

```

## disassembly

```asm
0x1001eb70  mov     edi, edi
0x1001eb72  push    ebp
0x1001eb73  mov     ebp, esp
0x1001eb75  mov     eax, 1084h
0x1001eb7a  call    __chkstk
0x1001eb7f  mov     eax, ___security_cookie
0x1001eb84  xor     eax, ebp
0x1001eb86  mov     [ebp+var_4], eax
0x1001eb89  push    ebx
0x1001eb8a  push    esi
0x1001eb8b  push    edi
0x1001eb8c  mov     edi, ecx
0x1001eb8e  mov     [ebp+var_1038], edi
0x1001eb94  mov     eax, [ebp+arg_0]
0x1001eb97  mov     esi, [ebp+arg_8]
0x1001eb9a  xor     ebx, ebx
0x1001eb9c  push    49h ; 'I'
0x1001eb9e  mov     [ebp+var_106C], eax
0x1001eba4  mov     ecx, [ebp+arg_4]
0x1001eba7  lea     eax, [ebp+var_104C]
0x1001ebad  push    eax
0x1001ebae  mov     eax, [ebp+var_106C]
0x1001ebb4  mov     [ebp+var_1070], ecx
0x1001ebba  xor     ecx, ecx
0x1001ebbc  push    eax
0x1001ebbd  mov     [ebp+Block], ecx
0x1001ebc3  mov     [ebp+var_1054], ecx
0x1001ebc9  mov     [ebp+var_1068], ecx
0x1001ebcf  mov     ecx, [edi+4]
0x1001ebd2  push    edx
0x1001ebd3  push    ecx
0x1001ebd4  mov     [ebp+var_105C], ebx
0x1001ebda  mov     [ebp+var_1044], ecx
0x1001ebe0  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x1001ebe5  mov     [ebp+var_1050], eax
0x1001ebeb  test    eax, eax
0x1001ebed  js      loc_1001EDAA
0x1001ebf3  push    8
0x1001ebf5  push    4
0x1001ebf7  lea     eax, [edi+10h]
0x1001ebfa  mov     [ebp+var_1048], ebx
0x1001ec00  push    eax
0x1001ec01  push    [ebp+var_104C]
0x1001ec07  mov     [ebp+var_1058], eax
0x1001ec0d  push    [ebp+var_1044]
0x1001ec13  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1001ec18  mov     edi, eax
0x1001ec1a  test    edi, edi
0x1001ec1c  js      loc_1001ED3E
0x1001ec22  mov     ebx, [ebp+arg_C]
0x1001ec25  mov     ecx, [ebp+var_1058]
0x1001ec2b  test    ebx, 1000h
0x1001ec31  jz      short loc_1001EC63
0x1001ec33  mov     eax, [ecx]
0x1001ec35  cmp     eax, 20000h
0x1001ec3a  ja      short loc_1001EC59
0x1001ec3c  jz      short loc_1001EC54
0x1001ec3e  sub     eax, 10000h
0x1001ec43  jz      short loc_1001EC4F
0x1001ec45  sub     eax, 1
0x1001ec48  jnz     short loc_1001EC63
0x1001ec4a  or      ebx, 10h
0x1001ec4d  jmp     short loc_1001EC63
0x1001ec4f  or      ebx, 18h
0x1001ec52  jmp     short loc_1001EC63
0x1001ec54  or      ebx, 20h
0x1001ec57  jmp     short loc_1001EC63
0x1001ec59  cmp     eax, 30000h
0x1001ec5e  jnz     short loc_1001EC63
0x1001ec60  or      ebx, 40h
0x1001ec63  test    bl, 3
0x1001ec66  jz      short loc_1001ECAB
0x1001ec68  cmp     dword ptr [ecx], 20000h
0x1001ec6e  mov     edx, [ebp+var_104C]
0x1001ec74  push    ecx
0x1001ec75  mov     ecx, [ebp+var_1044]
0x1001ec7b  push    40000h
0x1001ec80  push    0
0x1001ec82  push    0
0x1001ec84  jb      short loc_1001EC92
0x1001ec86  push    offset _wszDbObject; "MSysDb"
0x1001ec8b  push    offset _wszDcObject; "Databases"
0x1001ec90  jmp     short loc_1001EC9C
0x1001ec92  push    offset _wszSoTable; "MSysObjects"
0x1001ec97  push    offset _wszTcObject; "Tables"
0x1001ec9c  call    _ErrSecValidateAccess@32; ErrSecValidateAccess(x,x,x,x,x,x,x,x)
0x1001eca1  mov     edi, eax
0x1001eca3  test    edi, edi
0x1001eca5  js      loc_1001ED3C
0x1001ecab  test    bl, 1
0x1001ecae  jz      short loc_1001ECB7
0x1001ecb0  mov     ecx, 1
0x1001ecb5  jmp     short loc_1001ECD0
0x1001ecb7  xor     ecx, ecx
0x1001ecb9  test    bl, 2
0x1001ecbc  jnz     short loc_1001ECD0
0x1001ecbe  cmp     [ebp+var_1050], 4B8h
0x1001ecc8  mov     eax, 1
0x1001eccd  cmovz   ecx, eax
0x1001ecd0  mov     [ebp+var_1050], ecx
0x1001ecd6  test    bl, 10h
0x1001ecd9  jz      short loc_1001ECF4
0x1001ecdb  mov     eax, ebx
0x1001ecdd  and     eax, 8
0x1001ece0  or      eax, 10h
0x1001ece3  shr     eax, 2
0x1001ece6  or      eax, ecx
0x1001ece8  mov     [ebp+var_105C], eax
0x1001ecee  mov     [ebp+var_1050], eax
0x1001ecf4  test    esi, esi
0x1001ecf6  jz      loc_1001EE0D
0x1001ecfc  mov     ecx, esi
0x1001ecfe  lea     edx, [ecx+2]
0x1001ed01  mov     ax, [ecx]
0x1001ed04  add     ecx, 2
0x1001ed07  test    ax, ax
0x1001ed0a  jnz     short loc_1001ED01
0x1001ed0c  sub     ecx, edx
0x1001ed0e  sar     ecx, 1
0x1001ed10  lea     edi, ds:2Ch[ecx*2]
0x1001ed17  push    edi; Size
0x1001ed18  mov     [ebp+var_103C], edi
0x1001ed1e  call    ds:__imp__malloc
0x1001ed24  mov     edx, eax
0x1001ed26  add     esp, 4
0x1001ed29  mov     [ebp+var_1048], edx
0x1001ed2f  test    edx, edx
0x1001ed31  jnz     loc_1001EDBD
0x1001ed37  mov     edi, 0FFFFFC0Dh
0x1001ed3c  xor     ebx, ebx
0x1001ed3e  mov     esi, [ebp+var_1038]
0x1001ed44  push    0
0x1001ed46  push    [ebp+var_104C]
0x1001ed4c  push    [ebp+var_1044]
0x1001ed52  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001ed57  mov     eax, [ebp+Block]
0x1001ed5d  cmp     eax, [ebp+var_1048]
0x1001ed63  jz      short loc_1001ED73
0x1001ed65  test    eax, eax
0x1001ed67  jz      short loc_1001ED73
0x1001ed69  push    eax; Block
0x1001ed6a  call    ds:__imp__free
0x1001ed70  add     esp, 4
0x1001ed73  mov     eax, [ebp+var_1054]
0x1001ed79  test    eax, eax
0x1001ed7b  jz      short loc_1001ED90
0x1001ed7d  cmp     [ebp+var_1068], 0
0x1001ed84  jz      short loc_1001ED90
0x1001ed86  push    eax; Block
0x1001ed87  call    ds:__imp__free
0x1001ed8d  add     esp, 4
0x1001ed90  test    ebx, ebx
0x1001ed92  jz      short loc_1001EDA8
0x1001ed94  lea     eax, [esi+9DAh]
0x1001ed9a  cmp     ebx, eax
0x1001ed9c  jz      short loc_1001EDA8
0x1001ed9e  push    ebx; Block
0x1001ed9f  call    ds:__imp__free
0x1001eda5  add     esp, 4
0x1001eda8  mov     eax, edi
0x1001edaa  pop     edi
0x1001edab  pop     esi
0x1001edac  pop     ebx
0x1001edad  mov     ecx, [ebp+var_4]
0x1001edb0  xor     ecx, ebp; StackCookie
0x1001edb2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001edb7  mov     esp, ebp
0x1001edb9  pop     ebp
0x1001edba  retn    10h
0x1001edbd  mov     ecx, edi
0x1001edbf  mov     [ebp+var_1034], edx
0x1001edc5  shr     ecx, 1
0x1001edc7  mov     eax, edx
0x1001edc9  cmp     ecx, 1
0x1001edcc  jbe     short loc_1001EE02
0x1001edce  mov     [ebp+var_1048], edx
0x1001edd4  mov     [ebp+var_103C], edi
0x1001edda  mov     [ebp+var_1034], eax
0x1001ede0  movzx   eax, word ptr [esi]
0x1001ede3  test    ax, ax
0x1001ede6  jz      short loc_1001EE06
0x1001ede8  cmp     eax, 3Bh ; ';'
0x1001edeb  jz      short loc_1001EE06
0x1001eded  mov     [edx], ax
0x1001edf0  dec     ecx
0x1001edf1  add     edx, 2
0x1001edf4  add     esi, 2
0x1001edf7  mov     [ebp+var_1048], edx
0x1001edfd  cmp     ecx, 1
0x1001ee00  ja      short loc_1001EDE0
0x1001ee02  test    ecx, ecx
0x1001ee04  jz      short loc_1001EE2E
0x1001ee06  xor     eax, eax
0x1001ee08  mov     [edx], ax
0x1001ee0b  jmp     short loc_1001EE2E
0x1001ee0d  mov     eax, [ebp+var_1038]
0x1001ee13  add     eax, 9DAh
0x1001ee18  mov     [ebp+var_103C], 7F00h
0x1001ee22  mov     [ebp+var_1048], eax
0x1001ee28  mov     [ebp+var_1034], eax
0x1001ee2e  push    12h
0x1001ee30  push    4
0x1001ee32  lea     eax, [ebp+var_1064]
0x1001ee38  push    eax
0x1001ee39  push    [ebp+var_104C]
0x1001ee3f  push    [ebp+var_1044]
0x1001ee45  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1001ee4a  mov     ecx, [ebp+var_1048]
0x1001ee50  mov     edi, eax
0x1001ee52  mov     eax, [ebp+var_103C]
0x1001ee58  mov     edx, offset _wszLocale; ";LCID="
0x1001ee5d  sub     ecx, [ebp+var_1034]
0x1001ee63  shr     eax, 1
0x1001ee65  sar     ecx, 1
0x1001ee67  mov     [ebp+var_103C], eax
0x1001ee6d  sub     eax, ecx
0x1001ee6f  mov     ecx, [ebp+var_1048]
0x1001ee75  push    eax
0x1001ee76  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ee7b  mov     ecx, [ebp+var_1048]
0x1001ee81  lea     edx, [ecx+2]
0x1001ee84  mov     ax, [ecx]
0x1001ee87  add     ecx, 2
0x1001ee8a  test    ax, ax
0x1001ee8d  jnz     short loc_1001EE84
0x1001ee8f  mov     eax, [ebp+var_1048]
0x1001ee95  sub     ecx, edx
0x1001ee97  mov     edx, [ebp+var_103C]
0x1001ee9d  sar     ecx, 1
0x1001ee9f  push    0Ah
0x1001eea1  lea     ecx, [eax+ecx*2]
0x1001eea4  mov     eax, [ebp+var_1064]
0x1001eeaa  and     eax, 0FFFEFFh
0x1001eeaf  mov     [ebp+Block], ecx
0x1001eeb5  push    eax
0x1001eeb6  mov     eax, ecx
0x1001eeb8  sub     eax, [ebp+var_1034]
0x1001eebe  sar     eax, 1
0x1001eec0  sub     edx, eax
0x1001eec2  call    _DecodeUintW@16; DecodeUintW(x,x,x,x)
0x1001eec7  mov     edx, [ebp+Block]
0x1001eecd  mov     ecx, edx
0x1001eecf  lea     eax, [ecx+2]
0x1001eed2  mov     [ebp+Block], eax
0x1001eed8  nop     dword ptr [eax+eax+00000000h]
0x1001eee0  mov     ax, [ecx]
0x1001eee3  add     ecx, 2
0x1001eee6  test    ax, ax
0x1001eee9  jnz     short loc_1001EEE0
0x1001eeeb  sub     ecx, [ebp+Block]
0x1001eef1  sar     ecx, 1
0x1001eef3  lea     ecx, [edx+ecx*2]
0x1001eef6  test    esi, esi
0x1001eef8  jz      short loc_1001EF2A
0x1001eefa  mov     edx, [ebp+var_103C]
0x1001ef00  mov     eax, ecx
0x1001ef02  sub     eax, [ebp+var_1034]
0x1001ef08  sar     eax, 1
0x1001ef0a  sub     edx, eax
0x1001ef0c  cmp     word ptr [esi], 0
0x1001ef10  jz      short loc_1001EF2A
0x1001ef12  cmp     edx, 1
0x1001ef15  jbe     short loc_1001EF2A
0x1001ef17  mov     ax, [esi]
0x1001ef1a  dec     edx
0x1001ef1b  add     esi, 2
0x1001ef1e  mov     [ecx], ax
0x1001ef21  add     ecx, 2
0x1001ef24  cmp     word ptr [esi], 0
0x1001ef28  jnz     short loc_1001EF12
0x1001ef2a  mov     edx, [ebp+var_103C]
0x1001ef30  mov     eax, ecx
0x1001ef32  sub     eax, [ebp+var_1034]
0x1001ef38  sar     eax, 1
0x1001ef3a  sub     edx, eax
0x1001ef3c  jz      short loc_1001EF43
0x1001ef3e  xor     eax, eax
0x1001ef40  mov     [ecx], ax
0x1001ef43  mov     eax, [ebp+var_1034]
0x1001ef49  mov     esi, ebx
0x1001ef4b  mov     ecx, eax
0x1001ef4d  mov     [ebp+var_1048], eax
0x1001ef53  and     esi, 40h
0x1001ef56  mov     [ebp+Block], ecx
0x1001ef5c  mov     [ebp+var_103C], ecx
0x1001ef62  test    bl, 38h
0x1001ef65  jz      short loc_1001EF8D
0x1001ef67  lea     ecx, [ebp+var_103C]
0x1001ef6d  mov     edx, offset aJet2X; "Jet 2.x"
0x1001ef72  push    ecx
0x1001ef73  mov     ecx, eax
0x1001ef75  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x1001ef7a  mov     edi, eax
0x1001ef7c  mov     eax, [ebp+var_103C]
0x1001ef82  mov     [ebp+Block], eax
0x1001ef88  jmp     loc_1001F01A
0x1001ef8d  test    esi, esi
0x1001ef8f  jz      short loc_1001EFA1
0x1001ef91  lea     ecx, [ebp+var_103C]
0x1001ef97  mov     edx, offset aJet3X; "Jet 3.x"
  ... truncated ...
```
