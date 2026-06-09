# ErrREPOpenTable(x,x,x,x,x)

- ea: `0x10117862`
- end: `0x10117dfc`
- name: `_ErrREPOpenTable@20`
- size: `1434`
- prototype: `int __thiscall(int, int, void *Src, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x10042c00`
- `0x10043090`

## callees

- `0x1003e870`
- `0x10042ed0`
- `0x10043840`
- `0x10043da0`
- `0x100440c0`
- `0x10044460`
- `0x10044b20`
- `0x10044b90`
- `0x100451a0`
- `0x10117862`
- `0x101183c0`
- `0x101185da`
- `0x101187f2`
- `0x1011b238`
- `0x1011b410`
- `0x1011c800`
- `0x1011cda3`
- `0x1011ce1c`
- `0x1011dee6`
- `0x1011df12`
- `0x1011df91`
- `0x1011e129`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10117c83`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10117c83`

## string_xrefs

- `0x101179fe`: `SideTable`

## pseudocode

```c
int __fastcall ErrREPOpenTable(int a1, int a2, int *a3, unsigned __int16 *Src, int a5)
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
  unsigned __int16 *v15; // ecx
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
      dword_10131564[25 * *v34] = v8[17] | 0x2000;
      dword_10131530[25 * *v23] = v8[4];
      v24 = &rgreptinfo[25 * *v23];
      *v24++ = *v8;
      *v24++ = v8[1];
      *v24 = v8[2];
      v24[1] = v8[3];
      dword_10131538[25 * *v23] = v8[6];
      dword_1013153C[25 * *v23] = v8[7];
      dword_10131534[25 * *v23] = v8[5];
      v25 = v34;
      dword_10131540[25 * *v23] = v8[8];
      dword_10131568[25 * *v23] = v8[18];
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
        v15 = Src;
        do
          v16 = *v15++;
        while ( v16 != (_WORD)v37 );
        TableGuid = ErrDispMakeKey(a1, v30, Src, 2 * (v15 - (Src + 1)), 1);
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
        dword_10131564[25 * *v17] = v8[17] | 0x2000;
        dword_10131530[25 * *v17] = v8[4];
        dword_10131580[25 * *v17] |= 1u;
        v18 = *v17;
        v8[24] |= 1u;
        v8[20] = v18;
        dword_10131564[25 * *v17] &= ~0x10000u;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10117862  mov     edi, edi
0x10117864  push    ebp
0x10117865  mov     ebp, esp
0x10117867  and     esp, 0FFFFFFF8h
0x1011786a  sub     esp, 84h
0x10117870  mov     eax, ___security_cookie
0x10117875  xor     eax, esp
0x10117877  mov     [esp+84h+var_4], eax
0x1011787e  mov     eax, [ebp+arg_0]
0x10117881  push    ebx
0x10117882  mov     [esp+88h+var_68], eax
0x10117886  push    esi
0x10117887  mov     eax, [eax]
0x10117889  mov     esi, ecx
0x1011788b  mov     ecx, _rgrepdbinfo[edx*4]
0x10117892  imul    ebx, eax, 64h ; 'd'
0x10117895  push    edi
0x10117896  mov     edi, [ebp+Src]
0x10117899  mov     [esp+90h+var_84], edx
0x1011789d  mov     [esp+90h+var_7C], edi
0x101178a1  add     ebx, offset _rgreptinfo
0x101178a7  mov     [esp+90h+var_78], 0FFFFFFFFh
0x101178af  mov     [esp+90h+var_80], eax
0x101178b3  mov     [esp+90h+var_6C], ecx
0x101178b7  test    ecx, ecx
0x101178b9  jz      loc_10117DD8
0x101178bf  mov     [ebx+10h], edx
0x101178c2  mov     eax, [ecx+0E8h]
0x101178c8  mov     [ebx+48h], eax
0x101178cb  xor     eax, eax
0x101178cd  mov     ecx, [ecx+0E4h]
0x101178d3  and     dword ptr [ebx+60h], 0FFFFFFFEh
0x101178d7  and     ecx, 0FFFDFFFFh
0x101178dd  mov     [ebx+4Ch], eax
0x101178e0  mov     [esp+90h+var_5C], eax
0x101178e4  mov     [ebx+58h], eax
0x101178e7  mov     [ebx+34h], eax
0x101178ea  mov     eax, [esp+90h+var_6C]
0x101178ee  mov     [ebx+44h], ecx
0x101178f1  mov     dword ptr [ebx+54h], 0FFFFFFFFh
0x101178f8  mov     dword ptr [ebx+50h], 0FFFFFFFFh
0x101178ff  mov     eax, [eax+0E4h]
0x10117905  mov     [esp+90h+var_74], eax
0x10117909  test    al, 20h
0x1011790b  jnz     loc_10117DD8
0x10117911  xor     eax, eax
0x10117913  inc     eax
0x10117914  test    [esp+90h+var_74], 8000h
0x1011791c  mov     [esp+90h+var_70], eax
0x10117920  jz      short loc_10117927
0x10117922  or      ecx, eax
0x10117924  mov     [ebx+44h], ecx
0x10117927  test    cl, 1
0x1011792a  jz      loc_10117DD8
0x10117930  mov     eax, [ebp+arg_8]
0x10117933  and     eax, 80000004h
0x10117938  mov     [esp+90h+var_64], eax
0x1011793c  jnz     short loc_10117977
0x1011793e  mov     ecx, edi
0x10117940  call    _FTableRepSystem@4; FTableRepSystem(x)
0x10117945  test    eax, eax
0x10117947  jz      short loc_10117973
0x10117949  mov     eax, [esp+90h+var_6C]
0x1011794d  test    byte ptr [eax+0E4h], 10h
0x10117954  jnz     short loc_10117973
0x10117956  xor     eax, eax
0x10117958  push    eax; int
0x10117959  push    eax; int
0x1011795a  push    eax; int
0x1011795b  push    0FFFFDDD9h; int
0x10117960  push    eax; void *
0x10117961  push    eax; void *
0x10117962  push    edi; Src
0x10117963  push    esi; int
0x10117964  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10117969  mov     eax, 0FFFFB137h
0x1011796e  jmp     loc_10117DDA
0x10117973  mov     edx, [esp+90h+var_84]
0x10117977  lea     eax, [esp+90h+var_58]
0x1011797b  mov     ecx, esi
0x1011797d  push    eax; int
0x1011797e  lea     eax, [esp+94h+var_74]
0x10117982  push    eax; int
0x10117983  push    edi; Src
0x10117984  push    offset _wszTcObject; "Tables"
0x10117989  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x1011798e  test    eax, eax
0x10117990  js      loc_10117DDA
0x10117996  cmp     [esp+90h+var_74], 0
0x1011799b  jnz     loc_10117ADB
0x101179a1  mov     ecx, edi
0x101179a3  call    _FTableRepSystem@4; FTableRepSystem(x)
0x101179a8  test    eax, eax
0x101179aa  jnz     loc_10117DD8
0x101179b0  mov     ecx, edi
0x101179b2  call    _FTableNonRep@4; FTableNonRep(x)
0x101179b7  test    eax, eax
0x101179b9  jnz     loc_10117DD8
0x101179bf  mov     edi, [esp+90h+var_6C]
0x101179c3  test    dword ptr [edi+0E4h], 80000h
0x101179cd  jnz     loc_10117DD8
0x101179d3  mov     edx, [esp+90h+var_84]
0x101179d7  mov     ecx, esi
0x101179d9  call    _ErrOpenOptConflictTables@8; ErrOpenOptConflictTables(x,x)
0x101179de  test    eax, eax
0x101179e0  js      loc_10117DDA
0x101179e6  push    0
0x101179e8  lea     eax, [esp+94h+var_78]
0x101179ec  push    eax
0x101179ed  push    dword ptr [edi+14h]
0x101179f0  push    esi
0x101179f1  call    _ErrDispDupCursor@16; ErrDispDupCursor(x,x,x,x)
0x101179f6  test    eax, eax
0x101179f8  js      loc_10117DDA
0x101179fe  push    offset _WZSideTable; "SideTable"
0x10117a03  push    [esp+94h+var_78]
0x10117a07  push    esi
0x10117a08  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10117a0d  mov     edi, eax
0x10117a0f  test    edi, edi
0x10117a11  js      short loc_10117A52
0x10117a13  mov     edx, [esp+90h+var_7C]
0x10117a17  mov     ecx, edx
0x10117a19  lea     edi, [ecx+2]
0x10117a1c  mov     ax, [ecx]
0x10117a1f  add     ecx, 2
0x10117a22  cmp     ax, word ptr [esp+90h+var_5C]
0x10117a27  jnz     short loc_10117A1C
0x10117a29  sub     ecx, edi
0x10117a2b  sar     ecx, 1
0x10117a2d  push    1
0x10117a2f  lea     eax, [ecx+ecx]
0x10117a32  push    eax
0x10117a33  push    edx
0x10117a34  push    [esp+9Ch+var_78]
0x10117a38  push    esi
0x10117a39  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x10117a3e  mov     edi, eax
0x10117a40  test    edi, edi
0x10117a42  js      short loc_10117A52
0x10117a44  push    1
0x10117a46  push    [esp+94h+var_78]
0x10117a4a  push    esi
0x10117a4b  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x10117a50  mov     edi, eax
0x10117a52  push    [esp+90h+var_78]
0x10117a56  push    esi
0x10117a57  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10117a5c  mov     [esp+90h+var_78], 0FFFFFFFFh
0x10117a64  cmp     edi, 0FFFFF9BFh
0x10117a6a  jz      loc_10117DD8
0x10117a70  test    edi, edi
0x10117a72  jns     short loc_10117A7B
0x10117a74  mov     eax, edi
0x10117a76  jmp     loc_10117DDA
0x10117a7b  mov     edi, [esp+90h+var_68]
0x10117a7f  push    offset _vtfndefRepSideTable
0x10117a84  push    [esp+94h+var_80]
0x10117a88  push    edi
0x10117a89  push    esi
0x10117a8a  call    _ErrAllocateTableidForVSesid@16; ErrAllocateTableidForVSesid(x,x,x,x)
0x10117a8f  test    eax, eax
0x10117a91  js      loc_10117DDA
0x10117a97  imul    eax, [edi], 64h ; 'd'
0x10117a9a  mov     ecx, [ebx+44h]
0x10117a9d  or      ecx, 2000h
0x10117aa3  mov     dword_10131564[eax], ecx
0x10117aa9  imul    ecx, [edi], 64h ; 'd'
0x10117aac  mov     eax, [ebx+10h]
0x10117aaf  mov     dword_10131530[ecx], eax
0x10117ab5  xor     ecx, ecx
0x10117ab7  imul    eax, [edi], 64h ; 'd'
0x10117aba  inc     ecx
0x10117abb  or      dword_10131580[eax], ecx
0x10117ac1  mov     eax, [edi]
0x10117ac3  or      [ebx+60h], ecx
0x10117ac6  mov     [ebx+50h], eax
0x10117ac9  imul    eax, [edi], 64h ; 'd'
0x10117acc  and     dword_10131564[eax], 0FFFEFFFFh
0x10117ad6  jmp     loc_10117DD8
0x10117adb  mov     edi, [esp+90h+var_80]
0x10117adf  lea     eax, [esp+90h+var_3C]
0x10117ae3  push    1
0x10117ae5  push    38h ; '8'
0x10117ae7  push    eax
0x10117ae8  push    0
0x10117aea  push    edi
0x10117aeb  push    esi
0x10117aec  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117af1  test    eax, eax
0x10117af3  js      loc_10117DDA
0x10117af9  lea     eax, [esp+90h+var_3C]
0x10117afd  push    eax
0x10117afe  push    edi
0x10117aff  push    esi
0x10117b00  call    _ErrCountLvCols@12; ErrCountLvCols(x,x,x)
0x10117b05  mov     edi, eax
0x10117b07  test    edi, edi
0x10117b09  js      loc_10117CB6
0x10117b0f  cmp     [esp+90h+var_64], 0
0x10117b14  jnz     short loc_10117B3F
0x10117b16  mov     eax, [ebx+44h]
0x10117b19  and     al, 90h
0x10117b1b  cmp     al, 80h
0x10117b1d  jnz     short loc_10117B3F
0x10117b1f  xor     eax, eax
0x10117b21  push    eax; int
0x10117b22  push    eax; int
0x10117b23  push    eax; int
0x10117b24  push    0FFFFE016h; int
0x10117b29  push    eax; void *
0x10117b2a  push    eax; void *
0x10117b2b  push    [esp+0A8h+var_7C]; Src
0x10117b2f  push    esi; int
0x10117b30  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10117b35  mov     edi, 0FFFFF88Dh
0x10117b3a  jmp     loc_10117CB6
0x10117b3f  mov     edi, [esp+90h+var_7C]
0x10117b43  lea     eax, [esp+90h+var_74]
0x10117b47  or      dword ptr [ebx+44h], 8
0x10117b4b  push    eax; int
0x10117b4c  push    edi; Src
0x10117b4d  push    offset _wszTcObject; "Tables"
0x10117b52  push    [esp+9Ch+var_84]; int
0x10117b56  push    esi; int
0x10117b57  call    _ErrFColumnLevelTracking@20; ErrFColumnLevelTracking(x,x,x,x,x)
0x10117b5c  test    eax, eax
0x10117b5e  js      loc_10117DDA
0x10117b64  cmp     [esp+90h+var_74], 0
0x10117b69  jz      short loc_10117B72
0x10117b6b  or      dword ptr [ebx+44h], 20000h
0x10117b72  push    ebx
0x10117b73  push    edi
0x10117b74  push    [esp+98h+var_84]
0x10117b78  push    esi
0x10117b79  call    _ErrRepGetTableGuid@16; ErrRepGetTableGuid(x,x,x,x)
0x10117b7e  mov     edi, eax
0x10117b80  test    edi, edi
0x10117b82  js      loc_10117CB6
0x10117b88  push    0
0x10117b8a  push    18h
0x10117b8c  lea     eax, [esp+98h+var_54]
0x10117b90  push    eax
0x10117b91  push    offset _WZGeneration; "s_Generation"
0x10117b96  push    [esp+0A0h+var_80]
0x10117b9a  push    esi
0x10117b9b  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117ba0  mov     edi, eax
0x10117ba2  test    edi, edi
0x10117ba4  js      loc_10117CB6
0x10117baa  mov     eax, [esp+90h+var_50]
0x10117bae  push    0
0x10117bb0  push    18h
0x10117bb2  mov     [ebx+20h], eax
0x10117bb5  lea     eax, [esp+98h+var_54]
0x10117bb9  push    eax
0x10117bba  push    offset _WZLineage; "s_Lineage"
0x10117bbf  push    [esp+0A0h+var_80]
0x10117bc3  push    esi
0x10117bc4  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117bc9  mov     edi, eax
0x10117bcb  test    edi, edi
0x10117bcd  js      loc_10117CB6
0x10117bd3  test    dword ptr [ebx+44h], 20000h
0x10117bda  mov     eax, [esp+90h+var_50]
0x10117bde  mov     [ebx+18h], eax
0x10117be1  jz      short loc_10117C01
0x10117be3  push    [esp+90h+var_7C]
0x10117be7  mov     edx, [esp+94h+var_84]
0x10117beb  mov     ecx, esi
0x10117bed  push    ebx
0x10117bee  push    [esp+98h+var_80]
0x10117bf2  call    _ErrGetTblColLvlInfo@20; ErrGetTblColLvlInfo(x,x,x,x,x)
0x10117bf7  mov     edi, eax
0x10117bf9  test    edi, edi
0x10117bfb  js      loc_10117CB6
0x10117c01  push    8
0x10117c03  push    4
0x10117c05  lea     eax, [esp+98h+var_60]
0x10117c09  push    eax
0x10117c0a  push    [esp+9Ch+var_84]
0x10117c0e  push    esi
0x10117c0f  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x10117c14  mov     edi, eax
0x10117c16  test    edi, edi
0x10117c18  js      loc_10117CB6
0x10117c1e  push    8
0x10117c20  push    4
0x10117c22  lea     eax, [esp+98h+var_60]
0x10117c26  push    eax
0x10117c27  push    [esp+9Ch+var_84]
0x10117c2b  push    esi
0x10117c2c  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x10117c31  mov     edi, eax
0x10117c33  test    edi, edi
0x10117c35  js      short loc_10117CB6
0x10117c37  cmp     [esp+90h+var_60], 30000h
0x10117c3f  jbe     short loc_10117C6F
0x10117c41  cmp     [esp+90h+var_74], 0
0x10117c46  jz      short loc_10117C6F
  ... truncated ...
```
