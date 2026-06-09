# ErrREPOpenTable(x,x,x,x,x)

- ea: `0x10117a12`
- end: `0x10117fac`
- name: `_ErrREPOpenTable@20`
- size: `1434`
- prototype: `int __thiscall(int, int, void *Src, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x10042d90`
- `0x10043220`

## callees

- `0x1003ea00`
- `0x10043060`
- `0x100439d0`
- `0x10043f30`
- `0x10044240`
- `0x100445e0`
- `0x10044ca0`
- `0x10044d10`
- `0x10045320`
- `0x10117a12`
- `0x10118570`
- `0x1011878a`
- `0x101189a2`
- `0x1011b3e8`
- `0x1011b5c0`
- `0x1011c9b0`
- `0x1011cf53`
- `0x1011cfcc`
- `0x1011e094`
- `0x1011e0c0`
- `0x1011e13f`
- `0x1011e2d7`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10117e33`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10117e33`

## string_xrefs

- `0x10117bae`: `SideTable`

## pseudocode

```c
int __fastcall ErrREPOpenTable(int a1, int a2, int *a3, void *Src, int a5)
{
  int v5; // eax
  int v7; // ecx
  int *v8; // ebx
  int v9; // ecx
  unsigned int v10; // ecx
  int v11; // eax
  int result; // eax
  int v13; // edi
  int TableGuid; // edi
  char *v15; // ecx
  __int16 v16; // ax
  int *v17; // edi
  int v18; // eax
  bool v19; // zf
  int v20; // eax
  void *v21; // eax
  int v22; // eax
  int *v23; // edx
  int *v24; // edi
  int *v25; // ecx
  int v26; // eax
  int v27; // edx
  int v29; // [esp+10h] [ebp-80h]
  int v30; // [esp+18h] [ebp-78h] BYREF
  int v31; // [esp+1Ch] [ebp-74h] BYREF
  int v32; // [esp+20h] [ebp-70h]
  int v33; // [esp+24h] [ebp-6Ch]
  int *v34; // [esp+28h] [ebp-68h]
  int v35; // [esp+2Ch] [ebp-64h] BYREF
  unsigned int v36; // [esp+30h] [ebp-60h] BYREF
  int v37; // [esp+34h] [ebp-5Ch]
  int v38; // [esp+38h] [ebp-58h] BYREF
  char v39[4]; // [esp+3Ch] [ebp-54h] BYREF
  int v40; // [esp+40h] [ebp-50h]
  int v41[14]; // [esp+54h] [ebp-3Ch] BYREF

  v34 = a3;
  v5 = *a3;
  v7 = (int)*(&rgrepdbinfo + a2);
  v8 = &rgreptinfo[25 * *a3];
  v30 = -1;
  v29 = v5;
  v33 = v7;
  if ( !v7 )
    return 0;
  v8[4] = a2;
  v8[18] = *(_DWORD *)(v7 + 232);
  v9 = *(_DWORD *)(v7 + 228);
  v8[24] &= ~1u;
  v10 = v9 & 0xFFFDFFFF;
  v8[19] = 0;
  v37 = 0;
  v8[22] = 0;
  v8[13] = 0;
  v11 = v33;
  v8[17] = v10;
  v8[21] = -1;
  v8[20] = -1;
  v31 = *(_DWORD *)(v11 + 228);
  if ( (v31 & 0x20) != 0 )
    return 0;
  v32 = 1;
  if ( (v31 & 0x8000) != 0 )
  {
    v10 |= 1u;
    v8[17] = v10;
  }
  if ( (v10 & 1) == 0 )
    return 0;
  v35 = a5 & 0x80000004;
  if ( (a5 & 0x80000004) == 0 && FTableRepSystem(Src) && (*(_BYTE *)(v33 + 228) & 0x10) == 0 )
  {
    UtilSetErrorInfoReal(a1, Src, 0, 0, -8743, 0, 0, 0);
    return -20169;
  }
  result = ErrFObjectReplicable2((int)L"Tables", Src, (int)&v31, (int)&v38);
  if ( result < 0 )
    return result;
  if ( v31 )
  {
    result = ErrDispGetTableColumnInfo(a1, v29, 0, v41, 56, 1);
    if ( result < 0 )
      return result;
    TableGuid = ErrCountLvCols(a1, v29, v41);
    if ( TableGuid >= 0 )
    {
      if ( !v35 && (v8[17] & 0x90) == 0x80 )
      {
        UtilSetErrorInfoReal(a1, Src, 0, 0, -8170, 0, 0, 0);
        TableGuid = -1907;
        goto LABEL_51;
      }
      v8[17] |= 8u;
      result = ErrFColumnLevelTracking(a1, a2, (int)L"Tables", Src, (int)&v31);
      if ( result < 0 )
        return result;
      if ( v31 )
        v8[17] |= 0x20000u;
      TableGuid = ErrRepGetTableGuid(a1, a2, Src, v8);
      if ( TableGuid >= 0 )
      {
        TableGuid = ErrDispGetTableColumnInfo(a1, v29, L"s_Generation", v39, 24, 0);
        if ( TableGuid >= 0 )
        {
          v8[8] = v40;
          TableGuid = ErrDispGetTableColumnInfo(a1, v29, L"s_Lineage", v39, 24, 0);
          if ( TableGuid >= 0 )
          {
            v19 = (v8[17] & 0x20000) == 0;
            v8[6] = v40;
            if ( v19 || (TableGuid = ErrGetTblColLvlInfo(v29, v8, Src), TableGuid >= 0) )
            {
              TableGuid = ErrDispGetDatabaseInfo(a1, a2, &v36, 4, 8);
              if ( TableGuid >= 0 )
              {
                TableGuid = ErrDispGetDatabaseInfo(a1, a2, &v36, 4, 8);
                if ( TableGuid >= 0 )
                {
                  if ( v36 > 0x30000 && v31 )
                  {
                    TableGuid = ErrDispGetTableColumnInfo(a1, v29, L"s_ColLineage", v39, 24, 0);
                    if ( TableGuid < 0 )
                      goto LABEL_51;
                    v8[7] = v40;
                  }
                  else
                  {
                    v8[7] = -1;
                  }
                  v20 = *((unsigned __int16 *)v8 + 38);
                  if ( (_WORD)v20 )
                  {
                    v21 = _malloc(8 * v20);
                    v8[14] = (int)v21;
                    if ( !v21 )
                      return -1011;
                    TableGuid = ErrGetLvColGens(a1, (int)v21, (int)Src, v29, (int)v41);
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_51:
    ErrDispCloseTable(a1, v41[1]);
    if ( TableGuid < 0 )
      return TableGuid;
    if ( (a5 & 4) != 0 )
    {
      v22 = 0;
      v32 = 0;
    }
    else
    {
      if ( (v8[17] & 0x40) != 0 )
      {
        result = ErrFDBPartTableUpdatable(a1, a2, Src, (int)&v35);
        if ( result < 0 )
          return result;
        v19 = (v8[17] & 0x40) == 0;
        v32 = v35;
        if ( !v19 )
        {
          result = ErrREPOpenPartialsTable(v29, Src);
          if ( result < 0 )
            return result;
        }
      }
      v22 = v32;
    }
    SetPartTableidUpdatable(v29, v22);
    if ( (*(_BYTE *)(v33 + 228) & 0x10) == 0 )
    {
      result = ErrAllocateTableidForVSesid(a1, v34, v29, &vtfndefRepvt);
      if ( result < 0 )
        return result;
      v23 = v34;
      dword_10131604[25 * *v34] = v8[17] | 0x2000;
      dword_101315D0[25 * *v23] = v8[4];
      v24 = &rgreptinfo[25 * *v23];
      *v24++ = *v8;
      *v24++ = v8[1];
      *v24 = v8[2];
      v24[1] = v8[3];
      dword_101315D8[25 * *v23] = v8[6];
      dword_101315DC[25 * *v23] = v8[7];
      dword_101315D4[25 * *v23] = v8[5];
      v25 = v34;
      dword_101315E0[25 * *v23] = v8[8];
      dword_10131608[25 * *v23] = v8[18];
      v26 = *v23;
      v27 = v32;
      v8[20] = v26;
      SetPartTableidUpdatable(*v25, v27);
    }
    return 0;
  }
  if ( FTableRepSystem(Src) )
    return 0;
  if ( FTableNonRep(Src) )
    return 0;
  v13 = v33;
  if ( (*(_DWORD *)(v33 + 228) & 0x80000) != 0 )
    return 0;
  result = ErrOpenOptConflictTables(a1, a2);
  if ( result >= 0 )
  {
    result = ErrDispDupCursor(a1, *(_DWORD *)(v13 + 20), &v30, 0);
    if ( result >= 0 )
    {
      TableGuid = ErrDispSetCurrentIndex(a1, v30, L"SideTable");
      if ( TableGuid >= 0 )
      {
        v15 = (char *)Src;
        do
        {
          v16 = *(_WORD *)v15;
          v15 += 2;
        }
        while ( v16 != (_WORD)v37 );
        TableGuid = ErrDispMakeKey(a1, v30, Src, 2 * ((v15 - ((_BYTE *)Src + 2)) >> 1), 1);
        if ( TableGuid >= 0 )
          TableGuid = ErrDispSeek(a1, v30, 1);
      }
      ErrDispCloseTable(a1, v30);
      v30 = -1;
      if ( TableGuid == -1601 )
        return 0;
      if ( TableGuid < 0 )
        return TableGuid;
      v17 = v34;
      result = ErrAllocateTableidForVSesid(a1, v34, v29, &vtfndefRepSideTable);
      if ( result >= 0 )
      {
        dword_10131604[25 * *v17] = v8[17] | 0x2000;
        dword_101315D0[25 * *v17] = v8[4];
        dword_10131620[25 * *v17] |= 1u;
        v18 = *v17;
        v8[24] |= 1u;
        v8[20] = v18;
        dword_10131604[25 * *v17] &= ~0x10000u;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10117a12  mov     edi, edi
0x10117a14  push    ebp
0x10117a15  mov     ebp, esp
0x10117a17  and     esp, 0FFFFFFF8h
0x10117a1a  sub     esp, 84h
0x10117a20  mov     eax, ___security_cookie
0x10117a25  xor     eax, esp
0x10117a27  mov     [esp+84h+var_4], eax
0x10117a2e  mov     eax, [ebp+arg_0]
0x10117a31  push    ebx
0x10117a32  mov     [esp+88h+var_68], eax
0x10117a36  push    esi
0x10117a37  mov     eax, [eax]
0x10117a39  mov     esi, ecx
0x10117a3b  mov     ecx, _rgrepdbinfo[edx*4]
0x10117a42  imul    ebx, eax, 64h ; 'd'
0x10117a45  push    edi
0x10117a46  mov     edi, [ebp+Src]
0x10117a49  mov     [esp+90h+var_84], edx
0x10117a4d  mov     [esp+90h+var_7C], edi
0x10117a51  add     ebx, offset _rgreptinfo
0x10117a57  mov     [esp+90h+var_78], 0FFFFFFFFh
0x10117a5f  mov     [esp+90h+var_80], eax
0x10117a63  mov     [esp+90h+var_6C], ecx
0x10117a67  test    ecx, ecx
0x10117a69  jz      loc_10117F88
0x10117a6f  mov     [ebx+10h], edx
0x10117a72  mov     eax, [ecx+0E8h]
0x10117a78  mov     [ebx+48h], eax
0x10117a7b  xor     eax, eax
0x10117a7d  mov     ecx, [ecx+0E4h]
0x10117a83  and     dword ptr [ebx+60h], 0FFFFFFFEh
0x10117a87  and     ecx, 0FFFDFFFFh
0x10117a8d  mov     [ebx+4Ch], eax
0x10117a90  mov     [esp+90h+var_5C], eax
0x10117a94  mov     [ebx+58h], eax
0x10117a97  mov     [ebx+34h], eax
0x10117a9a  mov     eax, [esp+90h+var_6C]
0x10117a9e  mov     [ebx+44h], ecx
0x10117aa1  mov     dword ptr [ebx+54h], 0FFFFFFFFh
0x10117aa8  mov     dword ptr [ebx+50h], 0FFFFFFFFh
0x10117aaf  mov     eax, [eax+0E4h]
0x10117ab5  mov     [esp+90h+var_74], eax
0x10117ab9  test    al, 20h
0x10117abb  jnz     loc_10117F88
0x10117ac1  xor     eax, eax
0x10117ac3  inc     eax
0x10117ac4  test    [esp+90h+var_74], 8000h
0x10117acc  mov     [esp+90h+var_70], eax
0x10117ad0  jz      short loc_10117AD7
0x10117ad2  or      ecx, eax
0x10117ad4  mov     [ebx+44h], ecx
0x10117ad7  test    cl, 1
0x10117ada  jz      loc_10117F88
0x10117ae0  mov     eax, [ebp+arg_8]
0x10117ae3  and     eax, 80000004h
0x10117ae8  mov     [esp+90h+var_64], eax
0x10117aec  jnz     short loc_10117B27
0x10117aee  mov     ecx, edi
0x10117af0  call    _FTableRepSystem@4; FTableRepSystem(x)
0x10117af5  test    eax, eax
0x10117af7  jz      short loc_10117B23
0x10117af9  mov     eax, [esp+90h+var_6C]
0x10117afd  test    byte ptr [eax+0E4h], 10h
0x10117b04  jnz     short loc_10117B23
0x10117b06  xor     eax, eax
0x10117b08  push    eax; int
0x10117b09  push    eax; int
0x10117b0a  push    eax; int
0x10117b0b  push    0FFFFDDD9h; int
0x10117b10  push    eax; void *
0x10117b11  push    eax; void *
0x10117b12  push    edi; Src
0x10117b13  push    esi; int
0x10117b14  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10117b19  mov     eax, 0FFFFB137h
0x10117b1e  jmp     loc_10117F8A
0x10117b23  mov     edx, [esp+90h+var_84]
0x10117b27  lea     eax, [esp+90h+var_58]
0x10117b2b  mov     ecx, esi
0x10117b2d  push    eax; int
0x10117b2e  lea     eax, [esp+94h+var_74]
0x10117b32  push    eax; int
0x10117b33  push    edi; Src
0x10117b34  push    offset _wszTcObject; "Tables"
0x10117b39  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x10117b3e  test    eax, eax
0x10117b40  js      loc_10117F8A
0x10117b46  cmp     [esp+90h+var_74], 0
0x10117b4b  jnz     loc_10117C8B
0x10117b51  mov     ecx, edi
0x10117b53  call    _FTableRepSystem@4; FTableRepSystem(x)
0x10117b58  test    eax, eax
0x10117b5a  jnz     loc_10117F88
0x10117b60  mov     ecx, edi
0x10117b62  call    _FTableNonRep@4; FTableNonRep(x)
0x10117b67  test    eax, eax
0x10117b69  jnz     loc_10117F88
0x10117b6f  mov     edi, [esp+90h+var_6C]
0x10117b73  test    dword ptr [edi+0E4h], 80000h
0x10117b7d  jnz     loc_10117F88
0x10117b83  mov     edx, [esp+90h+var_84]
0x10117b87  mov     ecx, esi
0x10117b89  call    _ErrOpenOptConflictTables@8; ErrOpenOptConflictTables(x,x)
0x10117b8e  test    eax, eax
0x10117b90  js      loc_10117F8A
0x10117b96  push    0
0x10117b98  lea     eax, [esp+94h+var_78]
0x10117b9c  push    eax
0x10117b9d  push    dword ptr [edi+14h]
0x10117ba0  push    esi
0x10117ba1  call    _ErrDispDupCursor@16; ErrDispDupCursor(x,x,x,x)
0x10117ba6  test    eax, eax
0x10117ba8  js      loc_10117F8A
0x10117bae  push    offset _WZSideTable; "SideTable"
0x10117bb3  push    [esp+94h+var_78]
0x10117bb7  push    esi
0x10117bb8  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10117bbd  mov     edi, eax
0x10117bbf  test    edi, edi
0x10117bc1  js      short loc_10117C02
0x10117bc3  mov     edx, [esp+90h+var_7C]
0x10117bc7  mov     ecx, edx
0x10117bc9  lea     edi, [ecx+2]
0x10117bcc  mov     ax, [ecx]
0x10117bcf  add     ecx, 2
0x10117bd2  cmp     ax, word ptr [esp+90h+var_5C]
0x10117bd7  jnz     short loc_10117BCC
0x10117bd9  sub     ecx, edi
0x10117bdb  sar     ecx, 1
0x10117bdd  push    1
0x10117bdf  lea     eax, [ecx+ecx]
0x10117be2  push    eax
0x10117be3  push    edx
0x10117be4  push    [esp+9Ch+var_78]
0x10117be8  push    esi
0x10117be9  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x10117bee  mov     edi, eax
0x10117bf0  test    edi, edi
0x10117bf2  js      short loc_10117C02
0x10117bf4  push    1
0x10117bf6  push    [esp+94h+var_78]
0x10117bfa  push    esi
0x10117bfb  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x10117c00  mov     edi, eax
0x10117c02  push    [esp+90h+var_78]
0x10117c06  push    esi
0x10117c07  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10117c0c  mov     [esp+90h+var_78], 0FFFFFFFFh
0x10117c14  cmp     edi, 0FFFFF9BFh
0x10117c1a  jz      loc_10117F88
0x10117c20  test    edi, edi
0x10117c22  jns     short loc_10117C2B
0x10117c24  mov     eax, edi
0x10117c26  jmp     loc_10117F8A
0x10117c2b  mov     edi, [esp+90h+var_68]
0x10117c2f  push    offset _vtfndefRepSideTable
0x10117c34  push    [esp+94h+var_80]
0x10117c38  push    edi
0x10117c39  push    esi
0x10117c3a  call    _ErrAllocateTableidForVSesid@16; ErrAllocateTableidForVSesid(x,x,x,x)
0x10117c3f  test    eax, eax
0x10117c41  js      loc_10117F8A
0x10117c47  imul    eax, [edi], 64h ; 'd'
0x10117c4a  mov     ecx, [ebx+44h]
0x10117c4d  or      ecx, 2000h
0x10117c53  mov     dword_10131604[eax], ecx
0x10117c59  imul    ecx, [edi], 64h ; 'd'
0x10117c5c  mov     eax, [ebx+10h]
0x10117c5f  mov     dword_101315D0[ecx], eax
0x10117c65  xor     ecx, ecx
0x10117c67  imul    eax, [edi], 64h ; 'd'
0x10117c6a  inc     ecx
0x10117c6b  or      dword_10131620[eax], ecx
0x10117c71  mov     eax, [edi]
0x10117c73  or      [ebx+60h], ecx
0x10117c76  mov     [ebx+50h], eax
0x10117c79  imul    eax, [edi], 64h ; 'd'
0x10117c7c  and     dword_10131604[eax], 0FFFEFFFFh
0x10117c86  jmp     loc_10117F88
0x10117c8b  mov     edi, [esp+90h+var_80]
0x10117c8f  lea     eax, [esp+90h+var_3C]
0x10117c93  push    1
0x10117c95  push    38h ; '8'
0x10117c97  push    eax
0x10117c98  push    0
0x10117c9a  push    edi
0x10117c9b  push    esi
0x10117c9c  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117ca1  test    eax, eax
0x10117ca3  js      loc_10117F8A
0x10117ca9  lea     eax, [esp+90h+var_3C]
0x10117cad  push    eax
0x10117cae  push    edi
0x10117caf  push    esi
0x10117cb0  call    _ErrCountLvCols@12; ErrCountLvCols(x,x,x)
0x10117cb5  mov     edi, eax
0x10117cb7  test    edi, edi
0x10117cb9  js      loc_10117E66
0x10117cbf  cmp     [esp+90h+var_64], 0
0x10117cc4  jnz     short loc_10117CEF
0x10117cc6  mov     eax, [ebx+44h]
0x10117cc9  and     al, 90h
0x10117ccb  cmp     al, 80h
0x10117ccd  jnz     short loc_10117CEF
0x10117ccf  xor     eax, eax
0x10117cd1  push    eax; int
0x10117cd2  push    eax; int
0x10117cd3  push    eax; int
0x10117cd4  push    0FFFFE016h; int
0x10117cd9  push    eax; void *
0x10117cda  push    eax; void *
0x10117cdb  push    [esp+0A8h+var_7C]; Src
0x10117cdf  push    esi; int
0x10117ce0  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10117ce5  mov     edi, 0FFFFF88Dh
0x10117cea  jmp     loc_10117E66
0x10117cef  mov     edi, [esp+90h+var_7C]
0x10117cf3  lea     eax, [esp+90h+var_74]
0x10117cf7  or      dword ptr [ebx+44h], 8
0x10117cfb  push    eax; int
0x10117cfc  push    edi; Src
0x10117cfd  push    offset _wszTcObject; "Tables"
0x10117d02  push    [esp+9Ch+var_84]; int
0x10117d06  push    esi; int
0x10117d07  call    _ErrFColumnLevelTracking@20; ErrFColumnLevelTracking(x,x,x,x,x)
0x10117d0c  test    eax, eax
0x10117d0e  js      loc_10117F8A
0x10117d14  cmp     [esp+90h+var_74], 0
0x10117d19  jz      short loc_10117D22
0x10117d1b  or      dword ptr [ebx+44h], 20000h
0x10117d22  push    ebx
0x10117d23  push    edi
0x10117d24  push    [esp+98h+var_84]
0x10117d28  push    esi
0x10117d29  call    _ErrRepGetTableGuid@16; ErrRepGetTableGuid(x,x,x,x)
0x10117d2e  mov     edi, eax
0x10117d30  test    edi, edi
0x10117d32  js      loc_10117E66
0x10117d38  push    0
0x10117d3a  push    18h
0x10117d3c  lea     eax, [esp+98h+var_54]
0x10117d40  push    eax
0x10117d41  push    offset _WZGeneration; "s_Generation"
0x10117d46  push    [esp+0A0h+var_80]
0x10117d4a  push    esi
0x10117d4b  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117d50  mov     edi, eax
0x10117d52  test    edi, edi
0x10117d54  js      loc_10117E66
0x10117d5a  mov     eax, [esp+90h+var_50]
0x10117d5e  push    0
0x10117d60  push    18h
0x10117d62  mov     [ebx+20h], eax
0x10117d65  lea     eax, [esp+98h+var_54]
0x10117d69  push    eax
0x10117d6a  push    offset _WZLineage; "s_Lineage"
0x10117d6f  push    [esp+0A0h+var_80]
0x10117d73  push    esi
0x10117d74  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117d79  mov     edi, eax
0x10117d7b  test    edi, edi
0x10117d7d  js      loc_10117E66
0x10117d83  test    dword ptr [ebx+44h], 20000h
0x10117d8a  mov     eax, [esp+90h+var_50]
0x10117d8e  mov     [ebx+18h], eax
0x10117d91  jz      short loc_10117DB1
0x10117d93  push    [esp+90h+var_7C]
0x10117d97  mov     edx, [esp+94h+var_84]
0x10117d9b  mov     ecx, esi
0x10117d9d  push    ebx
0x10117d9e  push    [esp+98h+var_80]
0x10117da2  call    _ErrGetTblColLvlInfo@20; ErrGetTblColLvlInfo(x,x,x,x,x)
0x10117da7  mov     edi, eax
0x10117da9  test    edi, edi
0x10117dab  js      loc_10117E66
0x10117db1  push    8
0x10117db3  push    4
0x10117db5  lea     eax, [esp+98h+var_60]
0x10117db9  push    eax
0x10117dba  push    [esp+9Ch+var_84]
0x10117dbe  push    esi
0x10117dbf  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x10117dc4  mov     edi, eax
0x10117dc6  test    edi, edi
0x10117dc8  js      loc_10117E66
0x10117dce  push    8
0x10117dd0  push    4
0x10117dd2  lea     eax, [esp+98h+var_60]
0x10117dd6  push    eax
0x10117dd7  push    [esp+9Ch+var_84]
0x10117ddb  push    esi
0x10117ddc  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x10117de1  mov     edi, eax
0x10117de3  test    edi, edi
0x10117de5  js      short loc_10117E66
0x10117de7  cmp     [esp+90h+var_60], 30000h
0x10117def  jbe     short loc_10117E1F
0x10117df1  cmp     [esp+90h+var_74], 0
0x10117df6  jz      short loc_10117E1F
  ... truncated ...
```
