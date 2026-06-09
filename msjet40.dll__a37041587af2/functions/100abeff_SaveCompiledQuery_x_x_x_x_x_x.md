# SaveCompiledQuery(x,x,x,x,x,x)

- ea: `0x100abeff`
- end: `0x100ac3e4`
- name: `_SaveCompiledQuery@24`
- size: `1253`
- prototype: `void __fastcall(Session *, int, int, int, unsigned int, char)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x100a0040`
- `0x100ac3ea`

## callees

- `0x1002a7d0`
- `0x1002a9c0`
- `0x100321c0`
- `0x1003e830`
- `0x1003e9b0`
- `0x1003f080`
- `0x10043140`
- `0x100437f0`
- `0x100439d0`
- `0x10044240`
- `0x10044a70`
- `0x10044d80`
- `0x10044f80`
- `0x100460fb`
- `0x100ab601`
- `0x100abeff`
- `0x100c99c2`
- `0x100c9a29`
- `0x100c9a9a`
- `0x100f0d84`
- `0x10122302`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac3ad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac3bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac3ad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac3bd`

## string_xrefs

- `0x100ac0a9`: `DateUpdate`
- `0x100ac273`: `DateUpdate`
- `0x100ac362`: `DateUpdate`

## pseudocode

```c
void __fastcall SaveCompiledQuery(Session *a1, int a2, int a3, int a4, unsigned int a5, char a6)
{
  void *v7; // esi
  int ItibOfSesid; // eax
  bool v9; // zf
  unsigned int v10; // eax
  __int16 EbVersionC; // ax
  int v12; // ecx
  unsigned __int16 v13; // si
  int IsibOfSesid; // eax
  size_t v15; // esi
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // edx
  int v20; // eax
  int v21; // eax
  size_t v22; // [esp-10h] [ebp-D8h]
  int v23; // [esp-4h] [ebp-CCh]
  _DWORD v24[4]; // [esp+10h] [ebp-B8h] BYREF
  _BYTE v25[12]; // [esp+20h] [ebp-A8h] BYREF
  int v26; // [esp+2Ch] [ebp-9Ch]
  unsigned int v27; // [esp+30h] [ebp-98h]
  int v28; // [esp+34h] [ebp-94h]
  int v29; // [esp+38h] [ebp-90h]
  int v30; // [esp+3Ch] [ebp-8Ch]
  int v31; // [esp+40h] [ebp-88h]
  int v32; // [esp+44h] [ebp-84h]
  int v33; // [esp+48h] [ebp-80h]
  void *v34; // [esp+4Ch] [ebp-7Ch]
  unsigned int v35; // [esp+50h] [ebp-78h] BYREF
  __int16 v36; // [esp+54h] [ebp-74h] BYREF
  void *Block; // [esp+58h] [ebp-70h]
  int v38; // [esp+5Ch] [ebp-6Ch] BYREF
  _BYTE v39[4]; // [esp+60h] [ebp-68h] BYREF
  int v40; // [esp+64h] [ebp-64h]
  _DWORD v41[19]; // [esp+78h] [ebp-50h] BYREF

  v7 = 0;
  v32 = a2;
  v33 = a3;
  v26 = a4;
  Block = 0;
  v34 = 0;
  v38 = -1;
  ItibOfSesid = UtilGetItibOfSesid(a1);
  v9 = (*(_BYTE *)(a4 + 76) & 4) == 0;
  v30 = ItibOfSesid;
  v10 = a5;
  v40 = -1;
  if ( !v9 )
  {
    v10 = a5 & 0xFFFFFFEF;
    if ( (a5 & 0x2000) == 0 )
      v10 = a5;
  }
  v27 = QotOfQuery(v33, v10, a6);
  if ( v27 != -1 && (*(_DWORD *)(a4 + 28) & 0x201) == 0 )
  {
    EbVersionC = GetEbVersionC(v30);
    if ( EbVersionC != 262 && EbVersionC != 4098 )
    {
      ErrRefreshQueryObjectProperties(v32, v33);
      return;
    }
    v24[0] = 4;
    v24[3] = &v38;
    if ( (int)ErrDispGetObjectInfo(a1, v32, 0, L"Tables", v33, v24, 3) >= 0 )
    {
      v35 = 2;
      if ( (int)ErrGetSysField(L"Type", &v36, &v35) < 0 || v36 != 5 && v36 != 6 && v36 != 4 )
      {
LABEL_55:
        if ( v38 != -1 )
          ErrDispCloseTable(a1, v38);
        return;
      }
      v30 = *(_DWORD *)(a4 + 12) - a4 - 23;
      if ( ErrUtilAllocSeg(v30 + 100, v12) < 0 || (v31 = CbCompress(a4 + 24, v30), ErrQjetBeginTransaction(a1, 1) < 0) )
      {
LABEL_53:
        if ( v34 )
          _free(v34);
        goto LABEL_55;
      }
      v35 = 8;
      if ( (int)ErrGetSysField(L"DateUpdate", v25, &v35) < 0
        || (int)ErrDispGetTableColumnInfo(a1, v38, L"Lv", v39, 24, 0) < 0
        || (int)ErrDispRetrieveColumn(a1, v38, v40, v41, 68, &v35, 0, 0) < 0 )
      {
        goto LABEL_50;
      }
      v13 = GetEbVersionC(*(_DWORD *)(a4 + 44));
      v28 = v13;
      if ( v35 < 0x44 )
        goto LABEL_27;
      if ( v41[0] != -1 )
        goto LABEL_27;
      if ( v41[1] != 400980133 )
        goto LABEL_27;
      if ( BYTE2(v41[2]) )
        goto LABEL_27;
      IsibOfSesid = UtilGetIsibOfSesid(a1);
      if ( HIBYTE(v41[2]) != LOBYTE(dword_1016EBA0[26 * IsibOfSesid]) || LOWORD(v41[2]) != v13 )
        goto LABEL_27;
      v15 = v41[16];
      v29 = v41[16];
      if ( v35 == v41[16] )
        goto LABEL_28;
      while ( 1 )
      {
        v13 = v28;
LABEL_27:
        memset(v41, 0, 0x44u);
        v41[0] = -1;
        v41[1] = 400980133;
        BYTE2(v41[2]) = 0;
        v16 = UtilGetIsibOfSesid(a1);
        LOWORD(v41[2]) = v13;
        v15 = 68;
        v29 = 68;
        v41[16] = 68;
        HIBYTE(v41[2]) = dword_1016EBA0[26 * v16];
LABEL_28:
        v17 = v27;
        if ( v27 > 2 )
          break;
        v18 = 2 * v27;
        if ( !v41[4 * v27 + 4] )
        {
          v19 = v31;
          v17 = v30;
          v41[4 * v27 + 4] = v15;
          v41[2 * v18 + 5] = v19;
          v41[2 * v18 + 6] = v17;
          v41[2 * v18 + 7] = a4;
          v15 = v41[16];
          v29 = v41[16];
          goto LABEL_31;
        }
      }
      v19 = v31;
LABEL_31:
      v41[3] = (*(_DWORD *)(a4 + 76) & 4u) >> 2;
      if ( v15 == 68 )
      {
        v41[16] = v19 + 68;
        ErrRefreshQueryObjectProperties(v32, v33);
        if ( (int)ErrDispPrepareUpdate2(a1, v38, 2) >= 0
          && (int)ErrDispSetColumn(a1, v38, v40, v41, 68, 0, 0) >= 0
          && (int)ErrDispSetColumn(a1, v38, v40, v34, v31, 1, 0) >= 0
          && (int)ErrSetSysField(L"DateUpdate", v25, 8) >= 0 )
        {
          v20 = ErrDispUpdate(a1, v38, 0, 0, 0);
          v7 = Block;
LABEL_46:
          if ( v20 >= 0 && (int)ErrQjetCommitTransaction(1) >= 0 )
          {
LABEL_51:
            if ( v7 )
              _free(v7);
            goto LABEL_53;
          }
LABEL_50:
          ErrQjetRollback(a1, 1);
          ClearErrorInfo(a1);
          goto LABEL_51;
        }
      }
      else
      {
        v41[16] = v19 + v15;
        if ( v19 + v15 >= v15 && ErrUtilAllocSeg(v15, v17) >= 0 )
        {
          v22 = v15;
          v7 = Block;
          if ( (int)ErrDispRetrieveColumn(a1, v38, v40, Block, v22, &v35, 0, 0) < 0 )
            goto LABEL_50;
          v23 = v33;
          qmemcpy(Block, v41, 0x44u);
          ErrRefreshQueryObjectProperties(v32, v23);
          v21 = ErrDispPrepareUpdate2(a1, v38, 2);
          v7 = Block;
          if ( v21 < 0
            || (int)ErrDispSetColumn(a1, v38, v40, Block, v29, 0, 0) < 0
            || (int)ErrDispSetColumn(a1, v38, v40, v34, v31, 1, 0) < 0
            || (int)ErrSetSysField(L"DateUpdate", v25, 8) < 0 )
          {
            goto LABEL_50;
          }
          v20 = ErrDispUpdate(a1, v38, 0, 0, 0);
          goto LABEL_46;
        }
      }
      v7 = Block;
      goto LABEL_50;
    }
  }
}

```

## disassembly

```asm
0x100abeff  mov     edi, edi
0x100abf01  push    ebp
0x100abf02  mov     ebp, esp
0x100abf04  sub     esp, 0BCh
0x100abf0a  mov     eax, ___security_cookie
0x100abf0f  xor     eax, ebp
0x100abf11  mov     [ebp+var_4], eax
0x100abf14  mov     eax, [ebp+arg_0]
0x100abf17  push    ebx
0x100abf18  push    esi
0x100abf19  push    edi
0x100abf1a  mov     edi, [ebp+arg_4]
0x100abf1d  mov     ebx, ecx
0x100abf1f  xor     esi, esi
0x100abf21  mov     [ebp+var_84], edx
0x100abf27  push    ebx
0x100abf28  mov     [ebp+var_80], eax
0x100abf2b  mov     [ebp+var_9C], edi
0x100abf31  mov     [ebp+Block], esi
0x100abf34  mov     [ebp+var_7C], esi
0x100abf37  mov     [ebp+var_6C], 0FFFFFFFFh
0x100abf3e  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x100abf43  test    byte ptr [edi+4Ch], 4
0x100abf47  mov     [ebp+var_8C], eax
0x100abf4d  mov     eax, [ebp+arg_8]
0x100abf50  mov     [ebp+var_64], 0FFFFFFFFh
0x100abf57  jz      short loc_100ABF67
0x100abf59  and     eax, 0FFFFFFEFh
0x100abf5c  test    [ebp+arg_8], 2000h
0x100abf63  cmovz   eax, [ebp+arg_8]
0x100abf67  push    [ebp+arg_C]
0x100abf6a  mov     edx, [ebp+var_84]
0x100abf70  mov     ecx, ebx
0x100abf72  push    eax
0x100abf73  push    [ebp+var_80]
0x100abf76  call    _QotOfQuery@20; QotOfQuery(x,x,x,x,x)
0x100abf7b  mov     [ebp+var_98], eax
0x100abf81  cmp     eax, 0FFFFFFFFh
0x100abf84  jz      loc_100AC3D3
0x100abf8a  test    dword ptr [edi+1Ch], 201h
0x100abf91  jnz     loc_100AC3D3
0x100abf97  mov     ecx, [ebp+var_8C]
0x100abf9d  call    _GetEbVersionC@4; GetEbVersionC(x)
0x100abfa2  mov     ecx, 106h
0x100abfa7  cmp     ax, cx
0x100abfaa  jz      short loc_100ABFCD
0x100abfac  mov     ecx, 1002h
0x100abfb1  cmp     ax, cx
0x100abfb4  jz      short loc_100ABFCD
0x100abfb6  push    [ebp+var_80]
0x100abfb9  mov     edx, ebx
0x100abfbb  mov     ecx, edi
0x100abfbd  push    [ebp+var_84]
0x100abfc3  call    _ErrRefreshQueryObjectProperties@16; ErrRefreshQueryObjectProperties(x,x,x,x)
0x100abfc8  jmp     loc_100AC3D3
0x100abfcd  push    3
0x100abfcf  lea     eax, [ebp+var_6C]
0x100abfd2  mov     [ebp+var_B8], 4
0x100abfdc  mov     [ebp+var_AC], eax
0x100abfe2  lea     eax, [ebp+var_B8]
0x100abfe8  push    eax
0x100abfe9  push    [ebp+var_80]
0x100abfec  push    offset _wszTcObject; "Tables"
0x100abff1  push    0
0x100abff3  push    [ebp+var_84]
0x100abff9  push    ebx
0x100abffa  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x100abfff  test    eax, eax
0x100ac001  js      loc_100AC3D3
0x100ac007  mov     edx, [ebp+var_6C]
0x100ac00a  lea     eax, [ebp+var_78]
0x100ac00d  push    eax
0x100ac00e  lea     eax, [ebp+var_74]
0x100ac011  mov     [ebp+var_78], 2
0x100ac018  push    eax
0x100ac019  push    offset _wszSoObjectTypeColumn; "Type"
0x100ac01e  mov     ecx, ebx
0x100ac020  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x100ac025  test    eax, eax
0x100ac027  js      loc_100AC3C4
0x100ac02d  cmp     [ebp+var_74], 5
0x100ac032  jz      short loc_100AC048
0x100ac034  cmp     [ebp+var_74], 6
0x100ac039  jz      short loc_100AC048
0x100ac03b  push    4
0x100ac03d  pop     eax
0x100ac03e  cmp     [ebp+var_74], ax
0x100ac042  jnz     loc_100AC3C4
0x100ac048  mov     eax, [edi+0Ch]
0x100ac04b  lea     edx, [ebp+var_7C]
0x100ac04e  sub     eax, edi
0x100ac050  sub     eax, 17h
0x100ac053  push    ecx; int
0x100ac054  mov     [ebp+var_8C], eax
0x100ac05a  lea     ecx, [eax+64h]; Size
0x100ac05d  call    _ErrUtilAllocSeg@12; ErrUtilAllocSeg(x,x,x)
0x100ac062  test    eax, eax
0x100ac064  js      loc_100AC3B4
0x100ac06a  push    [ebp+var_8C]
0x100ac070  mov     ecx, [ebp+var_7C]
0x100ac073  lea     eax, [edi+18h]
0x100ac076  push    eax
0x100ac077  call    _CbCompress@16; CbCompress(x,x,x,x)
0x100ac07c  xor     edx, edx
0x100ac07e  mov     [ebp+var_88], eax
0x100ac084  inc     edx
0x100ac085  mov     ecx, ebx
0x100ac087  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x100ac08c  test    eax, eax
0x100ac08e  js      loc_100AC3B4
0x100ac094  mov     edx, [ebp+var_6C]
0x100ac097  lea     eax, [ebp+var_78]
0x100ac09a  push    eax
0x100ac09b  lea     eax, [ebp+var_A8]
0x100ac0a1  mov     [ebp+var_78], 8
0x100ac0a8  push    eax
0x100ac0a9  push    offset _wszSoDateUpdateColumn; "DateUpdate"
0x100ac0ae  mov     ecx, ebx
0x100ac0b0  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x100ac0b5  test    eax, eax
0x100ac0b7  js      loc_100AC399
0x100ac0bd  push    0
0x100ac0bf  push    18h
0x100ac0c1  lea     eax, [ebp+var_68]
0x100ac0c4  push    eax
0x100ac0c5  push    offset _wszSoLvColumn; "Lv"
0x100ac0ca  push    [ebp+var_6C]
0x100ac0cd  push    ebx
0x100ac0ce  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100ac0d3  test    eax, eax
0x100ac0d5  js      loc_100AC399
0x100ac0db  push    0
0x100ac0dd  push    0
0x100ac0df  lea     eax, [ebp+var_78]
0x100ac0e2  push    eax
0x100ac0e3  push    44h ; 'D'
0x100ac0e5  lea     eax, [ebp+var_50]
0x100ac0e8  push    eax
0x100ac0e9  push    [ebp+var_64]
0x100ac0ec  push    [ebp+var_6C]
0x100ac0ef  push    ebx
0x100ac0f0  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x100ac0f5  test    eax, eax
0x100ac0f7  js      loc_100AC399
0x100ac0fd  mov     ecx, [edi+2Ch]
0x100ac100  call    _GetEbVersionC@4; GetEbVersionC(x)
0x100ac105  cmp     [ebp+var_78], 44h ; 'D'
0x100ac109  movzx   esi, ax
0x100ac10c  mov     [ebp+var_94], esi
0x100ac112  jb      short loc_100AC158
0x100ac114  cmp     [ebp+var_50], 0FFFFFFFFh
0x100ac118  jnz     short loc_100AC158
0x100ac11a  cmp     [ebp+var_4C], 17E678A5h
0x100ac121  jnz     short loc_100AC158
0x100ac123  cmp     [ebp+var_46], 0
0x100ac127  jnz     short loc_100AC158
0x100ac129  mov     ecx, ebx
0x100ac12b  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100ac130  imul    ecx, eax, 68h ; 'h'
0x100ac133  mov     al, [ebp+var_45]
0x100ac136  cmp     al, byte ptr dword_1016EBA0[ecx]
0x100ac13c  jnz     short loc_100AC158
0x100ac13e  cmp     [ebp+var_48], si
0x100ac142  jnz     short loc_100AC158
0x100ac144  mov     esi, [ebp+Size]
0x100ac147  mov     [ebp+var_90], esi
0x100ac14d  cmp     [ebp+var_78], esi
0x100ac150  jz      short loc_100AC19D
0x100ac152  mov     esi, [ebp+var_94]
0x100ac158  push    44h ; 'D'; Size
0x100ac15a  lea     eax, [ebp+var_50]
0x100ac15d  push    0; Val
0x100ac15f  push    eax; void *
0x100ac160  call    _memset
0x100ac165  add     esp, 0Ch
0x100ac168  mov     [ebp+var_50], 0FFFFFFFFh
0x100ac16f  mov     ecx, ebx
0x100ac171  mov     [ebp+var_4C], 17E678A5h
0x100ac178  mov     [ebp+var_46], 0
0x100ac17c  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100ac181  imul    eax, 68h ; 'h'
0x100ac184  push    44h ; 'D'
0x100ac186  mov     [ebp+var_48], si
0x100ac18a  pop     esi
0x100ac18b  mov     [ebp+var_90], esi
0x100ac191  mov     [ebp+Size], esi
0x100ac194  mov     al, byte ptr dword_1016EBA0[eax]
0x100ac19a  mov     [ebp+var_45], al
0x100ac19d  mov     ecx, [ebp+var_98]
0x100ac1a3  mov     eax, ecx
0x100ac1a5  sub     eax, 0
0x100ac1a8  jz      short loc_100AC1B8
0x100ac1aa  sub     eax, 1
0x100ac1ad  jz      short loc_100AC1B8
0x100ac1af  sub     eax, 1
0x100ac1b2  jnz     loc_100AC29D
0x100ac1b8  mov     eax, ecx
0x100ac1ba  add     eax, eax
0x100ac1bc  cmp     [ebp+eax*8+var_40], 0
0x100ac1c1  jnz     short loc_100AC152
0x100ac1c3  mov     edx, [ebp+var_88]
0x100ac1c9  mov     ecx, [ebp+var_8C]
0x100ac1cf  mov     [ebp+eax*8+var_40], esi
0x100ac1d3  mov     [ebp+eax*8+var_3C], edx
0x100ac1d7  mov     [ebp+eax*8+var_38], ecx
0x100ac1db  mov     [ebp+eax*8+var_34], edi
0x100ac1df  mov     esi, [ebp+Size]
0x100ac1e2  mov     [ebp+var_90], esi
0x100ac1e8  mov     eax, [edi+4Ch]
0x100ac1eb  and     eax, 4
0x100ac1ee  shr     eax, 2
0x100ac1f1  mov     [ebp+var_44], eax
0x100ac1f4  cmp     esi, 44h ; 'D'
0x100ac1f7  jnz     loc_100AC2A8
0x100ac1fd  push    [ebp+var_80]
0x100ac200  lea     eax, [edx+44h]
0x100ac203  mov     ecx, edi
0x100ac205  push    [ebp+var_84]
0x100ac20b  mov     edx, ebx
0x100ac20d  mov     [ebp+Size], eax
0x100ac210  call    _ErrRefreshQueryObjectProperties@16; ErrRefreshQueryObjectProperties(x,x,x,x)
0x100ac215  push    2
0x100ac217  push    [ebp+var_6C]
0x100ac21a  push    ebx
0x100ac21b  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100ac220  test    eax, eax
0x100ac222  js      loc_100AC396
0x100ac228  push    0
0x100ac22a  push    0
0x100ac22c  push    esi
0x100ac22d  lea     eax, [ebp+var_50]
0x100ac230  push    eax
0x100ac231  push    [ebp+var_64]
0x100ac234  push    [ebp+var_6C]
0x100ac237  push    ebx
0x100ac238  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100ac23d  test    eax, eax
0x100ac23f  js      loc_100AC396
0x100ac245  mov     eax, [ebp+var_88]
0x100ac24b  push    0
0x100ac24d  push    1
0x100ac24f  push    eax
0x100ac250  push    [ebp+var_7C]
0x100ac253  push    [ebp+var_64]
0x100ac256  push    [ebp+var_6C]
0x100ac259  push    ebx
0x100ac25a  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100ac25f  test    eax, eax
0x100ac261  js      loc_100AC396
0x100ac267  mov     edx, [ebp+var_6C]
0x100ac26a  lea     eax, [ebp+var_A8]
0x100ac270  push    8
0x100ac272  push    eax
0x100ac273  push    offset _wszSoDateUpdateColumn; "DateUpdate"
0x100ac278  mov     ecx, ebx
0x100ac27a  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
0x100ac27f  test    eax, eax
0x100ac281  js      loc_100AC396
0x100ac287  xor     eax, eax
0x100ac289  push    eax
0x100ac28a  push    eax
0x100ac28b  push    eax
0x100ac28c  push    [ebp+var_6C]
0x100ac28f  push    ebx
0x100ac290  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x100ac295  mov     esi, [ebp+Block]
0x100ac298  jmp     loc_100AC380
0x100ac29d  mov     edx, [ebp+var_88]
0x100ac2a3  jmp     loc_100AC1E8
0x100ac2a8  lea     eax, [edx+esi]
0x100ac2ab  mov     [ebp+Size], eax
0x100ac2ae  cmp     eax, esi
0x100ac2b0  jb      loc_100AC396
0x100ac2b6  push    ecx; int
0x100ac2b7  lea     edx, [ebp+Block]
0x100ac2ba  mov     ecx, esi; Size
0x100ac2bc  call    _ErrUtilAllocSeg@12; ErrUtilAllocSeg(x,x,x)
0x100ac2c1  test    eax, eax
0x100ac2c3  js      loc_100AC396
0x100ac2c9  push    0
0x100ac2cb  push    0
0x100ac2cd  lea     eax, [ebp+var_78]
0x100ac2d0  push    eax
0x100ac2d1  push    esi
0x100ac2d2  mov     esi, [ebp+Block]
0x100ac2d5  push    esi
0x100ac2d6  push    [ebp+var_64]
0x100ac2d9  push    [ebp+var_6C]
0x100ac2dc  push    ebx
0x100ac2dd  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x100ac2e2  test    eax, eax
0x100ac2e4  js      loc_100AC399
0x100ac2ea  mov     edi, [ebp+Block]
0x100ac2ed  lea     esi, [ebp+var_50]
0x100ac2f0  push    11h
0x100ac2f2  pop     ecx
0x100ac2f3  push    [ebp+var_80]
0x100ac2f6  rep movsd
0x100ac2f8  push    [ebp+var_84]
0x100ac2fe  mov     ecx, [ebp+var_9C]
  ... truncated ...
```
