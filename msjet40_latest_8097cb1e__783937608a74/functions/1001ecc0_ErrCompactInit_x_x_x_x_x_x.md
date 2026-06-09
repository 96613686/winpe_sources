# ErrCompactInit(x,x,x,x,x,x)

- ea: `0x1001ecc0`
- end: `0x1001f5cc`
- name: `_ErrCompactInit@24`
- size: `2316`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x10025c70`

## callees

- `0x10012af0`
- `0x10016e40`
- `0x10017010`
- `0x10017150`
- `0x100179a0`
- `0x1001a2c0`
- `0x1001ebc0`
- `0x1001ecc0`
- `0x100258c0`
- `0x10025aa0`
- `0x1002a700`
- `0x1003a970`
- `0x10042b60`
- `0x10043060`
- `0x10043140`
- `0x10123110`
- `0x101245a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001eeba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001eed7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001eeef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f564`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f581`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f59e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001eeba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001eed7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001eeef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f564`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f581`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001f59e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ee6e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001f367`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ee6e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001f367`

## pseudocode

```c
int __fastcall ErrCompactInit(
        int a1,
        wchar_t *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        __int16 a6)
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
  char *v17; // eax
  char *v18; // edx
  int v19; // esi
  unsigned int v20; // ecx
  int v21; // eax
  char *v22; // edx
  char *v23; // ecx
  __int16 v24; // ax
  char *v25; // ecx
  unsigned int i; // edx
  unsigned __int16 v27; // ax
  int v28; // eax
  int v29; // ecx
  unsigned int v30; // edx
  unsigned int v31; // eax
  int v32; // ebx
  _DWORD *v33; // ecx
  int v34; // eax
  _DWORD *v35; // esi
  int v36; // eax
  unsigned __int16 *v37; // ebx
  _WORD *v38; // eax
  unsigned __int16 v39; // ax
  __int16 v40; // di
  unsigned __int16 v41; // cx
  unsigned __int16 *v42; // edx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  unsigned __int16 v46; // ax
  char *v47; // ecx
  _WORD *v48; // edx
  unsigned __int16 v49; // si
  unsigned __int16 v50; // ax
  __int16 v51; // ax
  __int16 *v52; // edx
  __int16 v53; // si
  __int16 v54; // ax
  _WORD *v55; // ebx
  size_t v56; // esi
  unsigned int v57; // esi
  int v58; // edi
  int v59; // eax
  _DWORD *v60; // ebx
  _DWORD *v61; // esi
  int v62; // esi
  int ObjectInfo; // eax
  int v64; // eax
  void *v65; // ebx
  int v66; // [esp-14h] [ebp-10A4h]
  int v67; // [esp-10h] [ebp-10A0h]
  _DWORD v68[4]; // [esp+10h] [ebp-1080h] BYREF
  unsigned int v69; // [esp+20h] [ebp-1070h]
  unsigned __int16 *v70; // [esp+24h] [ebp-106Ch]
  int v71; // [esp+28h] [ebp-1068h]
  int v72; // [esp+2Ch] [ebp-1064h] BYREF
  int v73; // [esp+30h] [ebp-1060h] BYREF
  unsigned int v74; // [esp+34h] [ebp-105Ch]
  unsigned int *v75; // [esp+38h] [ebp-1058h]
  void *v76; // [esp+3Ch] [ebp-1054h]
  unsigned int v77; // [esp+40h] [ebp-1050h]
  int v78; // [esp+44h] [ebp-104Ch] BYREF
  char *v79; // [esp+48h] [ebp-1048h]
  int v80; // [esp+4Ch] [ebp-1044h]
  void *Block; // [esp+50h] [ebp-1040h]
  unsigned int v82; // [esp+54h] [ebp-103Ch] BYREF
  int v83; // [esp+58h] [ebp-1038h]
  void *v84; // [esp+5Ch] [ebp-1034h]
  _BYTE v85[4096]; // [esp+60h] [ebp-1030h] BYREF
  _WORD v86[22]; // [esp+1060h] [ebp-30h] BYREF

  v83 = a1;
  v7 = a5;
  v8 = 0;
  v70 = a3;
  v69 = a4;
  Block = 0;
  v76 = 0;
  v71 = 0;
  v66 = *(_DWORD *)(a1 + 4);
  v74 = 0;
  v80 = v66;
  result = ErrOpenDatabase(v66, a2, a3, (int)&v78, 73);
  v77 = result;
  if ( result < 0 )
    return result;
  v79 = 0;
  v75 = (unsigned int *)(a1 + 16);
  DatabaseInfo = ErrDispGetDatabaseInfo(v80, v78, a1 + 16, 4, 8);
  if ( DatabaseInfo < 0 )
    goto LABEL_28;
  v11 = a6;
  if ( (a6 & 0x1000) != 0 )
  {
    v12 = *v75;
    if ( *v75 > 0x20000 )
    {
      if ( v12 == 196608 )
        v11 = a6 | 0x40;
    }
    else if ( *v75 == 0x20000 )
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
    v14 = *v75 < 0x20000
        ? ErrSecValidateAccess(L"Tables", L"MSysObjects", 0, 0, 0x40000, v75)
        : ErrSecValidateAccess(L"Databases", L"MSysDb", 0, 0, 0x40000, v75);
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
      v15 = v77 == 1208;
  }
  v77 = v15;
  if ( (v11 & 0x10) != 0 )
  {
    v74 = v15 | ((v11 & 8 | 0x10u) >> 2);
    v77 = v74;
  }
  if ( !a5 )
  {
    v82 = 32512;
    v79 = (char *)(v83 + 2522);
    v84 = (void *)(v83 + 2522);
    goto LABEL_48;
  }
  v16 = 2 * wcslen(a5) + 44;
  v82 = v16;
  v17 = (char *)_malloc(v16);
  v18 = v17;
  v79 = v17;
  if ( !v17 )
  {
    DatabaseInfo = -1011;
LABEL_27:
    v8 = 0;
LABEL_28:
    v19 = v83;
LABEL_29:
    ErrDispCloseDatabase(v80, v78, 0);
    if ( Block != v79 && Block )
      _free(Block);
    if ( v76 && v71 )
      _free(v76);
    if ( v8 )
    {
      if ( v8 != (void *)(v19 + 2522) )
        _free(v8);
    }
    return DatabaseInfo;
  }
  v84 = v17;
  v20 = v16 >> 1;
  if ( v16 >> 1 > 1 )
  {
    v79 = v17;
    v82 = v16;
    v84 = v17;
    do
    {
      v21 = *v7;
      if ( !(_WORD)v21 || v21 == 59 )
        goto LABEL_46;
      *(_WORD *)v18 = v21;
      --v20;
      v18 += 2;
      ++v7;
      v79 = v18;
    }
    while ( v20 > 1 );
  }
  if ( v20 )
LABEL_46:
    *(_WORD *)v18 = 0;
LABEL_48:
  DatabaseInfo = ErrDispGetDatabaseInfo(v80, v78, &v72, 4, 18);
  v82 >>= 1;
  WCSCPY2(v79, L";LCID=", v82 - ((v79 - (_BYTE *)v84) >> 1));
  Block = &v79[2 * wcslen((const unsigned __int16 *)v79)];
  DecodeUintW(v72 & 0xFFFEFF, 10);
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
    for ( i = v82 - ((v25 - (_BYTE *)v84) >> 1); *v7; v25 += 2 )
    {
      if ( i <= 1 )
        break;
      v27 = *v7;
      --i;
      ++v7;
      *(_WORD *)v25 = v27;
    }
  }
  if ( v82 != (v25 - (_BYTE *)v84) >> 1 )
    *(_WORD *)v25 = 0;
  v79 = (char *)v84;
  Block = v84;
  v82 = (unsigned int)v84;
  if ( (v11 & 0x38) != 0 )
  {
    DatabaseInfo = ErrGenIISAMConnectString((__int16 *)v84, L"Jet 2.x", &v82);
    Block = (void *)v82;
  }
  else
  {
    if ( (v11 & 0x40) != 0 )
    {
      v28 = ErrGenIISAMConnectString((__int16 *)v84, L"Jet 3.x", &v82);
    }
    else
    {
      v29 = wcslen((const unsigned __int16 *)v84);
      if ( v29 >= 7 && (v29 <= 7 || *((_WORD *)v84 + 7) == 59) && (!WCSNICMP(7) || !WCSNICMP(7)) )
        goto LABEL_67;
      v28 = ErrGenIISAMConnectString((__int16 *)v84, &dword_100086F8, &v82);
    }
    DatabaseInfo = v28;
    Block = (void *)v82;
  }
LABEL_67:
  if ( DatabaseInfo < 0 )
    goto LABEL_114;
  v30 = v74;
  v31 = *v75;
  if ( *v75 > 0x10001 )
  {
    if ( (v74 & 4) != 0 || (v11 & 0x20) != 0 && v31 >= 0x30000 || (v11 & 0x40) != 0 && v31 >= 0x40000 )
    {
      v8 = v84;
      DatabaseInfo = -1067;
      goto LABEL_28;
    }
    v32 = 0;
  }
  else
  {
    v32 = 2 * (v31 == 0x10000) + 4;
  }
  v33 = (_DWORD *)v83;
  v34 = 6;
  *(_DWORD *)(v83 + 2336) = v32;
  v35 = v33 + 587;
  v33[585] = v30;
  v75 = (unsigned int *)(v32 & 4);
  if ( (v32 & 4) == 0 )
    v34 = 9;
  v33[586] = v34;
  v36 = ErrDispGetDatabaseInfo(v80, v78, v33 + 587, 4, 13);
  DatabaseInfo = v36;
  if ( v36 == -1003 )
  {
    *v35 = 0;
    goto LABEL_83;
  }
  if ( v36 < 0 )
  {
LABEL_114:
    v8 = v84;
    goto LABEL_28;
  }
  if ( *v35 )
    v77 |= 0x80u;
LABEL_83:
  v37 = v70;
  if ( v70 )
  {
    v39 = *v70;
    v40 = 0;
    v86[0] = 0;
    if ( v39 )
    {
      v41 = v39;
      while ( 1 )
      {
        v42 = ++v37;
        if ( v41 == 59 && wcslen(v42) >= 3 )
        {
          v43 = *v42;
          if ( v43 == 80 || v43 == 112 )
          {
            v44 = v42[1];
            if ( v44 == 87 || v44 == 119 )
            {
              v45 = v42[2];
              if ( v45 == 68 || v45 == 100 )
                break;
            }
          }
        }
        v41 = *v37;
        if ( !*v37 )
          goto LABEL_109;
      }
      v46 = v42[3];
      v47 = (char *)v86;
      v48 = v42 + 3;
      if ( v46 )
      {
        v49 = v46;
        while ( v49 != 61 )
        {
          v50 = v48[1];
          ++v48;
          v49 = v50;
          if ( !v50 )
            goto LABEL_109;
        }
        if ( *v48 )
        {
          v51 = v48[1];
          v52 = v48 + 1;
          if ( v51 )
          {
            v53 = v51;
            while ( v53 != 59 )
            {
              if ( (int)((v47 - (char *)v86) & 0xFFFFFFFE) >= 40 )
              {
                DatabaseInfo = -1905;
                goto LABEL_114;
              }
              v54 = *v52++;
              *(_WORD *)v47 = v54;
              v47 += 2;
              v53 = *v52;
              if ( !*v52 )
                break;
            }
          }
          *(_WORD *)v47 = 0;
          v40 = v86[0];
        }
      }
    }
LABEL_109:
    v55 = Block;
    v56 = 52;
    if ( Block )
      v56 = 2 * wcslen((const unsigned __int16 *)Block) + 52;
    v38 = _malloc(v56);
    v76 = v38;
    if ( !v38 )
    {
      v8 = v84;
      DatabaseInfo = -1011;
      goto LABEL_28;
    }
    v57 = v56 >> 1;
    *v38 = 0;
    v71 = 1;
    if ( v55 )
    {
      WCSCPY2(v38, v55, v57);
      v38 = v76;
    }
    if ( v40 )
    {
      WCSCAT2(v38, L";Pwd=", v57);
      WCSCAT2(v76, v86, v57);
      v38 = v76;
    }
  }
  else
  {
    v38 = Block;
    v76 = Block;
  }
  v58 = v80;
  v59 = ErrCreateDatabase(v80, v69, v38, &v73, v77);
  if ( v59 < 0 )
  {
    v19 = v83;
    v8 = v84;
    DatabaseInfo = -1201;
    if ( v59 == -1202 )
      v59 = -1201;
    *(_DWORD *)(v83 + 24) = v59;
    goto LABEL_29;
  }
  v60 = (_DWORD *)v83;
  v61 = (_DWORD *)(v83 + 20);
  DatabaseInfo = ErrDispGetDatabaseInfo(v58, v73, v83 + 20, 4, 8);
  if ( DatabaseInfo >= 0 && *v61 < v60[4] )
  {
    DatabaseInfo = -1067;
LABEL_130:
    ErrDispCloseDatabase(v80, v73, 0);
    v8 = v84;
    goto LABEL_28;
  }
  v62 = v80;
  if ( v75 && (v74 & 4) == 0 )
    DatabaseInfo = ErrSecGiveDefPermissions(v80, L";", v73, 7);
  if ( DatabaseInfo < 0 )
    goto LABEL_130;
  v60[2] = v78;
  v67 = v73;
  v60[3] = v73;
  ErrDispGetDatabaseInfo(v62, v67, &v72, 4, 18);
  v60[7] = (unsigned __int16)v72;
  v68[3] = v60 + 10;
  v68[0] = 48;
  ObjectInfo = ErrDispGetObjectInfo(v62, v78, 0, 0, 0, v68, 1);
  if ( ObjectInfo < 0 && ObjectInfo != -1211 )
  {
    ErrGetErrorText(v85);
    v64 = ErrCompactLogError(v85, L"MSysObjects", 0);
    if ( v64 < 0 )
      v60[591] = v64;
    v60[589] = 1;
  }
  v65 = v84;
  if ( Block != v84 && Block )
    _free(Block);
  if ( v76 && v71 )
    _free(v76);
  if ( v65 && v65 != (void *)(v83 + 2522) )
    _free(v65);
  return 0;
}

```

## disassembly

```asm
0x1001ecc0  mov     edi, edi
0x1001ecc2  push    ebp
0x1001ecc3  mov     ebp, esp
0x1001ecc5  mov     eax, 1084h
0x1001ecca  call    __chkstk
0x1001eccf  mov     eax, ___security_cookie
0x1001ecd4  xor     eax, ebp
0x1001ecd6  mov     [ebp+var_4], eax
0x1001ecd9  push    ebx
0x1001ecda  push    esi
0x1001ecdb  push    edi
0x1001ecdc  mov     edi, ecx
0x1001ecde  mov     [ebp+var_1038], edi
0x1001ece4  mov     eax, [ebp+arg_0]
0x1001ece7  mov     esi, [ebp+arg_8]
0x1001ecea  xor     ebx, ebx
0x1001ecec  push    49h ; 'I'
0x1001ecee  mov     [ebp+var_106C], eax
0x1001ecf4  mov     ecx, [ebp+arg_4]
0x1001ecf7  lea     eax, [ebp+var_104C]
0x1001ecfd  push    eax
0x1001ecfe  mov     eax, [ebp+var_106C]
0x1001ed04  mov     [ebp+var_1070], ecx
0x1001ed0a  xor     ecx, ecx
0x1001ed0c  push    eax
0x1001ed0d  mov     [ebp+Block], ecx
0x1001ed13  mov     [ebp+var_1054], ecx
0x1001ed19  mov     [ebp+var_1068], ecx
0x1001ed1f  mov     ecx, [edi+4]
0x1001ed22  push    edx
0x1001ed23  push    ecx
0x1001ed24  mov     [ebp+var_105C], ebx
0x1001ed2a  mov     [ebp+var_1044], ecx
0x1001ed30  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x1001ed35  mov     [ebp+var_1050], eax
0x1001ed3b  test    eax, eax
0x1001ed3d  js      loc_1001EEFA
0x1001ed43  push    8
0x1001ed45  push    4
0x1001ed47  lea     eax, [edi+10h]
0x1001ed4a  mov     [ebp+var_1048], ebx
0x1001ed50  push    eax
0x1001ed51  push    [ebp+var_104C]
0x1001ed57  mov     [ebp+var_1058], eax
0x1001ed5d  push    [ebp+var_1044]
0x1001ed63  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1001ed68  mov     edi, eax
0x1001ed6a  test    edi, edi
0x1001ed6c  js      loc_1001EE8E
0x1001ed72  mov     ebx, [ebp+arg_C]
0x1001ed75  mov     ecx, [ebp+var_1058]
0x1001ed7b  test    ebx, 1000h
0x1001ed81  jz      short loc_1001EDB3
0x1001ed83  mov     eax, [ecx]
0x1001ed85  cmp     eax, 20000h
0x1001ed8a  ja      short loc_1001EDA9
0x1001ed8c  jz      short loc_1001EDA4
0x1001ed8e  sub     eax, 10000h
0x1001ed93  jz      short loc_1001ED9F
0x1001ed95  sub     eax, 1
0x1001ed98  jnz     short loc_1001EDB3
0x1001ed9a  or      ebx, 10h
0x1001ed9d  jmp     short loc_1001EDB3
0x1001ed9f  or      ebx, 18h
0x1001eda2  jmp     short loc_1001EDB3
0x1001eda4  or      ebx, 20h
0x1001eda7  jmp     short loc_1001EDB3
0x1001eda9  cmp     eax, 30000h
0x1001edae  jnz     short loc_1001EDB3
0x1001edb0  or      ebx, 40h
0x1001edb3  test    bl, 3
0x1001edb6  jz      short loc_1001EDFB
0x1001edb8  cmp     dword ptr [ecx], 20000h
0x1001edbe  mov     edx, [ebp+var_104C]
0x1001edc4  push    ecx
0x1001edc5  mov     ecx, [ebp+var_1044]
0x1001edcb  push    40000h
0x1001edd0  push    0
0x1001edd2  push    0
0x1001edd4  jb      short loc_1001EDE2
0x1001edd6  push    offset _wszDbObject; "MSysDb"
0x1001eddb  push    offset _wszDcObject; "Databases"
0x1001ede0  jmp     short loc_1001EDEC
0x1001ede2  push    offset _wszSoTable; "MSysObjects"
0x1001ede7  push    offset _wszTcObject; "Tables"
0x1001edec  call    _ErrSecValidateAccess@32; ErrSecValidateAccess(x,x,x,x,x,x,x,x)
0x1001edf1  mov     edi, eax
0x1001edf3  test    edi, edi
0x1001edf5  js      loc_1001EE8C
0x1001edfb  test    bl, 1
0x1001edfe  jz      short loc_1001EE07
0x1001ee00  mov     ecx, 1
0x1001ee05  jmp     short loc_1001EE20
0x1001ee07  xor     ecx, ecx
0x1001ee09  test    bl, 2
0x1001ee0c  jnz     short loc_1001EE20
0x1001ee0e  cmp     [ebp+var_1050], 4B8h
0x1001ee18  mov     eax, 1
0x1001ee1d  cmovz   ecx, eax
0x1001ee20  mov     [ebp+var_1050], ecx
0x1001ee26  test    bl, 10h
0x1001ee29  jz      short loc_1001EE44
0x1001ee2b  mov     eax, ebx
0x1001ee2d  and     eax, 8
0x1001ee30  or      eax, 10h
0x1001ee33  shr     eax, 2
0x1001ee36  or      eax, ecx
0x1001ee38  mov     [ebp+var_105C], eax
0x1001ee3e  mov     [ebp+var_1050], eax
0x1001ee44  test    esi, esi
0x1001ee46  jz      loc_1001EF5D
0x1001ee4c  mov     ecx, esi
0x1001ee4e  lea     edx, [ecx+2]
0x1001ee51  mov     ax, [ecx]
0x1001ee54  add     ecx, 2
0x1001ee57  test    ax, ax
0x1001ee5a  jnz     short loc_1001EE51
0x1001ee5c  sub     ecx, edx
0x1001ee5e  sar     ecx, 1
0x1001ee60  lea     edi, ds:2Ch[ecx*2]
0x1001ee67  push    edi; Size
0x1001ee68  mov     [ebp+var_103C], edi
0x1001ee6e  call    ds:__imp__malloc
0x1001ee74  mov     edx, eax
0x1001ee76  add     esp, 4
0x1001ee79  mov     [ebp+var_1048], edx
0x1001ee7f  test    edx, edx
0x1001ee81  jnz     loc_1001EF0D
0x1001ee87  mov     edi, 0FFFFFC0Dh
0x1001ee8c  xor     ebx, ebx
0x1001ee8e  mov     esi, [ebp+var_1038]
0x1001ee94  push    0
0x1001ee96  push    [ebp+var_104C]
0x1001ee9c  push    [ebp+var_1044]
0x1001eea2  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001eea7  mov     eax, [ebp+Block]
0x1001eead  cmp     eax, [ebp+var_1048]
0x1001eeb3  jz      short loc_1001EEC3
0x1001eeb5  test    eax, eax
0x1001eeb7  jz      short loc_1001EEC3
0x1001eeb9  push    eax; Block
0x1001eeba  call    ds:__imp__free
0x1001eec0  add     esp, 4
0x1001eec3  mov     eax, [ebp+var_1054]
0x1001eec9  test    eax, eax
0x1001eecb  jz      short loc_1001EEE0
0x1001eecd  cmp     [ebp+var_1068], 0
0x1001eed4  jz      short loc_1001EEE0
0x1001eed6  push    eax; Block
0x1001eed7  call    ds:__imp__free
0x1001eedd  add     esp, 4
0x1001eee0  test    ebx, ebx
0x1001eee2  jz      short loc_1001EEF8
0x1001eee4  lea     eax, [esi+9DAh]
0x1001eeea  cmp     ebx, eax
0x1001eeec  jz      short loc_1001EEF8
0x1001eeee  push    ebx; Block
0x1001eeef  call    ds:__imp__free
0x1001eef5  add     esp, 4
0x1001eef8  mov     eax, edi
0x1001eefa  pop     edi
0x1001eefb  pop     esi
0x1001eefc  pop     ebx
0x1001eefd  mov     ecx, [ebp+var_4]
0x1001ef00  xor     ecx, ebp; StackCookie
0x1001ef02  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ef07  mov     esp, ebp
0x1001ef09  pop     ebp
0x1001ef0a  retn    10h
0x1001ef0d  mov     ecx, edi
0x1001ef0f  mov     [ebp+var_1034], edx
0x1001ef15  shr     ecx, 1
0x1001ef17  mov     eax, edx
0x1001ef19  cmp     ecx, 1
0x1001ef1c  jbe     short loc_1001EF52
0x1001ef1e  mov     [ebp+var_1048], edx
0x1001ef24  mov     [ebp+var_103C], edi
0x1001ef2a  mov     [ebp+var_1034], eax
0x1001ef30  movzx   eax, word ptr [esi]
0x1001ef33  test    ax, ax
0x1001ef36  jz      short loc_1001EF56
0x1001ef38  cmp     eax, 3Bh ; ';'
0x1001ef3b  jz      short loc_1001EF56
0x1001ef3d  mov     [edx], ax
0x1001ef40  dec     ecx
0x1001ef41  add     edx, 2
0x1001ef44  add     esi, 2
0x1001ef47  mov     [ebp+var_1048], edx
0x1001ef4d  cmp     ecx, 1
0x1001ef50  ja      short loc_1001EF30
0x1001ef52  test    ecx, ecx
0x1001ef54  jz      short loc_1001EF7E
0x1001ef56  xor     eax, eax
0x1001ef58  mov     [edx], ax
0x1001ef5b  jmp     short loc_1001EF7E
0x1001ef5d  mov     eax, [ebp+var_1038]
0x1001ef63  add     eax, 9DAh
0x1001ef68  mov     [ebp+var_103C], 7F00h
0x1001ef72  mov     [ebp+var_1048], eax
0x1001ef78  mov     [ebp+var_1034], eax
0x1001ef7e  push    12h
0x1001ef80  push    4
0x1001ef82  lea     eax, [ebp+var_1064]
0x1001ef88  push    eax
0x1001ef89  push    [ebp+var_104C]
0x1001ef8f  push    [ebp+var_1044]
0x1001ef95  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1001ef9a  mov     ecx, [ebp+var_1048]
0x1001efa0  mov     edi, eax
0x1001efa2  mov     eax, [ebp+var_103C]
0x1001efa8  mov     edx, offset _wszLocale; ";LCID="
0x1001efad  sub     ecx, [ebp+var_1034]
0x1001efb3  shr     eax, 1
0x1001efb5  sar     ecx, 1
0x1001efb7  mov     [ebp+var_103C], eax
0x1001efbd  sub     eax, ecx
0x1001efbf  mov     ecx, [ebp+var_1048]
0x1001efc5  push    eax
0x1001efc6  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001efcb  mov     ecx, [ebp+var_1048]
0x1001efd1  lea     edx, [ecx+2]
0x1001efd4  mov     ax, [ecx]
0x1001efd7  add     ecx, 2
0x1001efda  test    ax, ax
0x1001efdd  jnz     short loc_1001EFD4
0x1001efdf  mov     eax, [ebp+var_1048]
0x1001efe5  sub     ecx, edx
0x1001efe7  mov     edx, [ebp+var_103C]
0x1001efed  sar     ecx, 1
0x1001efef  push    0Ah
0x1001eff1  lea     ecx, [eax+ecx*2]
0x1001eff4  mov     eax, [ebp+var_1064]
0x1001effa  and     eax, 0FFFEFFh
0x1001efff  mov     [ebp+Block], ecx
0x1001f005  push    eax
0x1001f006  mov     eax, ecx
0x1001f008  sub     eax, [ebp+var_1034]
0x1001f00e  sar     eax, 1
0x1001f010  sub     edx, eax
0x1001f012  call    _DecodeUintW@16; DecodeUintW(x,x,x,x)
0x1001f017  mov     edx, [ebp+Block]
0x1001f01d  mov     ecx, edx
0x1001f01f  lea     eax, [ecx+2]
0x1001f022  mov     [ebp+Block], eax
0x1001f028  nop     dword ptr [eax+eax+00000000h]
0x1001f030  mov     ax, [ecx]
0x1001f033  add     ecx, 2
0x1001f036  test    ax, ax
0x1001f039  jnz     short loc_1001F030
0x1001f03b  sub     ecx, [ebp+Block]
0x1001f041  sar     ecx, 1
0x1001f043  lea     ecx, [edx+ecx*2]
0x1001f046  test    esi, esi
0x1001f048  jz      short loc_1001F07A
0x1001f04a  mov     edx, [ebp+var_103C]
0x1001f050  mov     eax, ecx
0x1001f052  sub     eax, [ebp+var_1034]
0x1001f058  sar     eax, 1
0x1001f05a  sub     edx, eax
0x1001f05c  cmp     word ptr [esi], 0
0x1001f060  jz      short loc_1001F07A
0x1001f062  cmp     edx, 1
0x1001f065  jbe     short loc_1001F07A
0x1001f067  mov     ax, [esi]
0x1001f06a  dec     edx
0x1001f06b  add     esi, 2
0x1001f06e  mov     [ecx], ax
0x1001f071  add     ecx, 2
0x1001f074  cmp     word ptr [esi], 0
0x1001f078  jnz     short loc_1001F062
0x1001f07a  mov     edx, [ebp+var_103C]
0x1001f080  mov     eax, ecx
0x1001f082  sub     eax, [ebp+var_1034]
0x1001f088  sar     eax, 1
0x1001f08a  sub     edx, eax
0x1001f08c  jz      short loc_1001F093
0x1001f08e  xor     eax, eax
0x1001f090  mov     [ecx], ax
0x1001f093  mov     eax, [ebp+var_1034]
0x1001f099  mov     esi, ebx
0x1001f09b  mov     ecx, eax
0x1001f09d  mov     [ebp+var_1048], eax
0x1001f0a3  and     esi, 40h
0x1001f0a6  mov     [ebp+Block], ecx
0x1001f0ac  mov     [ebp+var_103C], ecx
0x1001f0b2  test    bl, 38h
0x1001f0b5  jz      short loc_1001F0DD
0x1001f0b7  lea     ecx, [ebp+var_103C]
0x1001f0bd  mov     edx, offset aJet2X; "Jet 2.x"
0x1001f0c2  push    ecx
0x1001f0c3  mov     ecx, eax
0x1001f0c5  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x1001f0ca  mov     edi, eax
0x1001f0cc  mov     eax, [ebp+var_103C]
0x1001f0d2  mov     [ebp+Block], eax
0x1001f0d8  jmp     loc_1001F16A
0x1001f0dd  test    esi, esi
0x1001f0df  jz      short loc_1001F0F1
0x1001f0e1  lea     ecx, [ebp+var_103C]
0x1001f0e7  mov     edx, offset aJet3X; "Jet 3.x"
  ... truncated ...
```
