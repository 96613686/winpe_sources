# SaveCompiledQuery(x,x,x,x,x,x)

- ea: `0x100abd6f`
- end: `0x100ac254`
- name: `_SaveCompiledQuery@24`
- size: `1253`
- prototype: `int __thiscall(Session *, int, int, int, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1009feb0`
- `0x100ac25a`

## callees

- `0x1002a600`
- `0x1002a7f0`
- `0x10032020`
- `0x1003e6a0`
- `0x1003e820`
- `0x1003eef0`
- `0x10042fb0`
- `0x10043660`
- `0x10043840`
- `0x100440c0`
- `0x100448f0`
- `0x10044c00`
- `0x10044e00`
- `0x10045f7b`
- `0x100ab471`
- `0x100abd6f`
- `0x100c9832`
- `0x100c9899`
- `0x100c990a`
- `0x100f0bf4`
- `0x10122152`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac21d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac22d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac21d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100ac22d`

## string_xrefs

- `0x100abf19`: `DateUpdate`
- `0x100ac0e3`: `DateUpdate`
- `0x100ac1d2`: `DateUpdate`

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
      if ( HIBYTE(v41[2]) != LOBYTE(dword_1016EB00[26 * IsibOfSesid]) || LOWORD(v41[2]) != v13 )
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
        HIBYTE(v41[2]) = dword_1016EB00[26 * v16];
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
0x100abd6f  mov     edi, edi
0x100abd71  push    ebp
0x100abd72  mov     ebp, esp
0x100abd74  sub     esp, 0BCh
0x100abd7a  mov     eax, ___security_cookie
0x100abd7f  xor     eax, ebp
0x100abd81  mov     [ebp+var_4], eax
0x100abd84  mov     eax, [ebp+arg_0]
0x100abd87  push    ebx
0x100abd88  push    esi
0x100abd89  push    edi
0x100abd8a  mov     edi, [ebp+arg_4]
0x100abd8d  mov     ebx, ecx
0x100abd8f  xor     esi, esi
0x100abd91  mov     [ebp+var_84], edx
0x100abd97  push    ebx
0x100abd98  mov     [ebp+var_80], eax
0x100abd9b  mov     [ebp+var_9C], edi
0x100abda1  mov     [ebp+Block], esi
0x100abda4  mov     [ebp+var_7C], esi
0x100abda7  mov     [ebp+var_6C], 0FFFFFFFFh
0x100abdae  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x100abdb3  test    byte ptr [edi+4Ch], 4
0x100abdb7  mov     [ebp+var_8C], eax
0x100abdbd  mov     eax, [ebp+arg_8]
0x100abdc0  mov     [ebp+var_64], 0FFFFFFFFh
0x100abdc7  jz      short loc_100ABDD7
0x100abdc9  and     eax, 0FFFFFFEFh
0x100abdcc  test    [ebp+arg_8], 2000h
0x100abdd3  cmovz   eax, [ebp+arg_8]
0x100abdd7  push    [ebp+arg_C]
0x100abdda  mov     edx, [ebp+var_84]
0x100abde0  mov     ecx, ebx
0x100abde2  push    eax
0x100abde3  push    [ebp+var_80]
0x100abde6  call    _QotOfQuery@20; QotOfQuery(x,x,x,x,x)
0x100abdeb  mov     [ebp+var_98], eax
0x100abdf1  cmp     eax, 0FFFFFFFFh
0x100abdf4  jz      loc_100AC243
0x100abdfa  test    dword ptr [edi+1Ch], 201h
0x100abe01  jnz     loc_100AC243
0x100abe07  mov     ecx, [ebp+var_8C]
0x100abe0d  call    _GetEbVersionC@4; GetEbVersionC(x)
0x100abe12  mov     ecx, 106h
0x100abe17  cmp     ax, cx
0x100abe1a  jz      short loc_100ABE3D
0x100abe1c  mov     ecx, 1002h
0x100abe21  cmp     ax, cx
0x100abe24  jz      short loc_100ABE3D
0x100abe26  push    [ebp+var_80]
0x100abe29  mov     edx, ebx
0x100abe2b  mov     ecx, edi
0x100abe2d  push    [ebp+var_84]
0x100abe33  call    _ErrRefreshQueryObjectProperties@16; ErrRefreshQueryObjectProperties(x,x,x,x)
0x100abe38  jmp     loc_100AC243
0x100abe3d  push    3
0x100abe3f  lea     eax, [ebp+var_6C]
0x100abe42  mov     [ebp+var_B8], 4
0x100abe4c  mov     [ebp+var_AC], eax
0x100abe52  lea     eax, [ebp+var_B8]
0x100abe58  push    eax
0x100abe59  push    [ebp+var_80]
0x100abe5c  push    offset _wszTcObject; "Tables"
0x100abe61  push    0
0x100abe63  push    [ebp+var_84]
0x100abe69  push    ebx
0x100abe6a  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x100abe6f  test    eax, eax
0x100abe71  js      loc_100AC243
0x100abe77  mov     edx, [ebp+var_6C]
0x100abe7a  lea     eax, [ebp+var_78]
0x100abe7d  push    eax
0x100abe7e  lea     eax, [ebp+var_74]
0x100abe81  mov     [ebp+var_78], 2
0x100abe88  push    eax
0x100abe89  push    offset _wszSoObjectTypeColumn; "Type"
0x100abe8e  mov     ecx, ebx
0x100abe90  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x100abe95  test    eax, eax
0x100abe97  js      loc_100AC234
0x100abe9d  cmp     [ebp+var_74], 5
0x100abea2  jz      short loc_100ABEB8
0x100abea4  cmp     [ebp+var_74], 6
0x100abea9  jz      short loc_100ABEB8
0x100abeab  push    4
0x100abead  pop     eax
0x100abeae  cmp     [ebp+var_74], ax
0x100abeb2  jnz     loc_100AC234
0x100abeb8  mov     eax, [edi+0Ch]
0x100abebb  lea     edx, [ebp+var_7C]
0x100abebe  sub     eax, edi
0x100abec0  sub     eax, 17h
0x100abec3  push    ecx; int
0x100abec4  mov     [ebp+var_8C], eax
0x100abeca  lea     ecx, [eax+64h]; Size
0x100abecd  call    _ErrUtilAllocSeg@12; ErrUtilAllocSeg(x,x,x)
0x100abed2  test    eax, eax
0x100abed4  js      loc_100AC224
0x100abeda  push    [ebp+var_8C]
0x100abee0  mov     ecx, [ebp+var_7C]
0x100abee3  lea     eax, [edi+18h]
0x100abee6  push    eax
0x100abee7  call    _CbCompress@16; CbCompress(x,x,x,x)
0x100abeec  xor     edx, edx
0x100abeee  mov     [ebp+var_88], eax
0x100abef4  inc     edx
0x100abef5  mov     ecx, ebx
0x100abef7  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x100abefc  test    eax, eax
0x100abefe  js      loc_100AC224
0x100abf04  mov     edx, [ebp+var_6C]
0x100abf07  lea     eax, [ebp+var_78]
0x100abf0a  push    eax
0x100abf0b  lea     eax, [ebp+var_A8]
0x100abf11  mov     [ebp+var_78], 8
0x100abf18  push    eax
0x100abf19  push    offset _wszSoDateUpdateColumn; "DateUpdate"
0x100abf1e  mov     ecx, ebx
0x100abf20  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x100abf25  test    eax, eax
0x100abf27  js      loc_100AC209
0x100abf2d  push    0
0x100abf2f  push    18h
0x100abf31  lea     eax, [ebp+var_68]
0x100abf34  push    eax
0x100abf35  push    offset _wszSoLvColumn; "Lv"
0x100abf3a  push    [ebp+var_6C]
0x100abf3d  push    ebx
0x100abf3e  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100abf43  test    eax, eax
0x100abf45  js      loc_100AC209
0x100abf4b  push    0
0x100abf4d  push    0
0x100abf4f  lea     eax, [ebp+var_78]
0x100abf52  push    eax
0x100abf53  push    44h ; 'D'
0x100abf55  lea     eax, [ebp+var_50]
0x100abf58  push    eax
0x100abf59  push    [ebp+var_64]
0x100abf5c  push    [ebp+var_6C]
0x100abf5f  push    ebx
0x100abf60  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x100abf65  test    eax, eax
0x100abf67  js      loc_100AC209
0x100abf6d  mov     ecx, [edi+2Ch]
0x100abf70  call    _GetEbVersionC@4; GetEbVersionC(x)
0x100abf75  cmp     [ebp+var_78], 44h ; 'D'
0x100abf79  movzx   esi, ax
0x100abf7c  mov     [ebp+var_94], esi
0x100abf82  jb      short loc_100ABFC8
0x100abf84  cmp     [ebp+var_50], 0FFFFFFFFh
0x100abf88  jnz     short loc_100ABFC8
0x100abf8a  cmp     [ebp+var_4C], 17E678A5h
0x100abf91  jnz     short loc_100ABFC8
0x100abf93  cmp     [ebp+var_46], 0
0x100abf97  jnz     short loc_100ABFC8
0x100abf99  mov     ecx, ebx
0x100abf9b  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100abfa0  imul    ecx, eax, 68h ; 'h'
0x100abfa3  mov     al, [ebp+var_45]
0x100abfa6  cmp     al, byte ptr dword_1016EB00[ecx]
0x100abfac  jnz     short loc_100ABFC8
0x100abfae  cmp     [ebp+var_48], si
0x100abfb2  jnz     short loc_100ABFC8
0x100abfb4  mov     esi, [ebp+Size]
0x100abfb7  mov     [ebp+var_90], esi
0x100abfbd  cmp     [ebp+var_78], esi
0x100abfc0  jz      short loc_100AC00D
0x100abfc2  mov     esi, [ebp+var_94]
0x100abfc8  push    44h ; 'D'; Size
0x100abfca  lea     eax, [ebp+var_50]
0x100abfcd  push    0; Val
0x100abfcf  push    eax; void *
0x100abfd0  call    _memset
0x100abfd5  add     esp, 0Ch
0x100abfd8  mov     [ebp+var_50], 0FFFFFFFFh
0x100abfdf  mov     ecx, ebx
0x100abfe1  mov     [ebp+var_4C], 17E678A5h
0x100abfe8  mov     [ebp+var_46], 0
0x100abfec  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100abff1  imul    eax, 68h ; 'h'
0x100abff4  push    44h ; 'D'
0x100abff6  mov     [ebp+var_48], si
0x100abffa  pop     esi
0x100abffb  mov     [ebp+var_90], esi
0x100ac001  mov     [ebp+Size], esi
0x100ac004  mov     al, byte ptr dword_1016EB00[eax]
0x100ac00a  mov     [ebp+var_45], al
0x100ac00d  mov     ecx, [ebp+var_98]
0x100ac013  mov     eax, ecx
0x100ac015  sub     eax, 0
0x100ac018  jz      short loc_100AC028
0x100ac01a  sub     eax, 1
0x100ac01d  jz      short loc_100AC028
0x100ac01f  sub     eax, 1
0x100ac022  jnz     loc_100AC10D
0x100ac028  mov     eax, ecx
0x100ac02a  add     eax, eax
0x100ac02c  cmp     [ebp+eax*8+var_40], 0
0x100ac031  jnz     short loc_100ABFC2
0x100ac033  mov     edx, [ebp+var_88]
0x100ac039  mov     ecx, [ebp+var_8C]
0x100ac03f  mov     [ebp+eax*8+var_40], esi
0x100ac043  mov     [ebp+eax*8+var_3C], edx
0x100ac047  mov     [ebp+eax*8+var_38], ecx
0x100ac04b  mov     [ebp+eax*8+var_34], edi
0x100ac04f  mov     esi, [ebp+Size]
0x100ac052  mov     [ebp+var_90], esi
0x100ac058  mov     eax, [edi+4Ch]
0x100ac05b  and     eax, 4
0x100ac05e  shr     eax, 2
0x100ac061  mov     [ebp+var_44], eax
0x100ac064  cmp     esi, 44h ; 'D'
0x100ac067  jnz     loc_100AC118
0x100ac06d  push    [ebp+var_80]
0x100ac070  lea     eax, [edx+44h]
0x100ac073  mov     ecx, edi
0x100ac075  push    [ebp+var_84]
0x100ac07b  mov     edx, ebx
0x100ac07d  mov     [ebp+Size], eax
0x100ac080  call    _ErrRefreshQueryObjectProperties@16; ErrRefreshQueryObjectProperties(x,x,x,x)
0x100ac085  push    2
0x100ac087  push    [ebp+var_6C]
0x100ac08a  push    ebx
0x100ac08b  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100ac090  test    eax, eax
0x100ac092  js      loc_100AC206
0x100ac098  push    0
0x100ac09a  push    0
0x100ac09c  push    esi
0x100ac09d  lea     eax, [ebp+var_50]
0x100ac0a0  push    eax
0x100ac0a1  push    [ebp+var_64]
0x100ac0a4  push    [ebp+var_6C]
0x100ac0a7  push    ebx
0x100ac0a8  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100ac0ad  test    eax, eax
0x100ac0af  js      loc_100AC206
0x100ac0b5  mov     eax, [ebp+var_88]
0x100ac0bb  push    0
0x100ac0bd  push    1
0x100ac0bf  push    eax
0x100ac0c0  push    [ebp+var_7C]
0x100ac0c3  push    [ebp+var_64]
0x100ac0c6  push    [ebp+var_6C]
0x100ac0c9  push    ebx
0x100ac0ca  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100ac0cf  test    eax, eax
0x100ac0d1  js      loc_100AC206
0x100ac0d7  mov     edx, [ebp+var_6C]
0x100ac0da  lea     eax, [ebp+var_A8]
0x100ac0e0  push    8
0x100ac0e2  push    eax
0x100ac0e3  push    offset _wszSoDateUpdateColumn; "DateUpdate"
0x100ac0e8  mov     ecx, ebx
0x100ac0ea  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
0x100ac0ef  test    eax, eax
0x100ac0f1  js      loc_100AC206
0x100ac0f7  xor     eax, eax
0x100ac0f9  push    eax
0x100ac0fa  push    eax
0x100ac0fb  push    eax
0x100ac0fc  push    [ebp+var_6C]
0x100ac0ff  push    ebx
0x100ac100  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x100ac105  mov     esi, [ebp+Block]
0x100ac108  jmp     loc_100AC1F0
0x100ac10d  mov     edx, [ebp+var_88]
0x100ac113  jmp     loc_100AC058
0x100ac118  lea     eax, [edx+esi]
0x100ac11b  mov     [ebp+Size], eax
0x100ac11e  cmp     eax, esi
0x100ac120  jb      loc_100AC206
0x100ac126  push    ecx; int
0x100ac127  lea     edx, [ebp+Block]
0x100ac12a  mov     ecx, esi; Size
0x100ac12c  call    _ErrUtilAllocSeg@12; ErrUtilAllocSeg(x,x,x)
0x100ac131  test    eax, eax
0x100ac133  js      loc_100AC206
0x100ac139  push    0
0x100ac13b  push    0
0x100ac13d  lea     eax, [ebp+var_78]
0x100ac140  push    eax
0x100ac141  push    esi
0x100ac142  mov     esi, [ebp+Block]
0x100ac145  push    esi
0x100ac146  push    [ebp+var_64]
0x100ac149  push    [ebp+var_6C]
0x100ac14c  push    ebx
0x100ac14d  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x100ac152  test    eax, eax
0x100ac154  js      loc_100AC209
0x100ac15a  mov     edi, [ebp+Block]
0x100ac15d  lea     esi, [ebp+var_50]
0x100ac160  push    11h
0x100ac162  pop     ecx
0x100ac163  push    [ebp+var_80]
0x100ac166  rep movsd
0x100ac168  push    [ebp+var_84]
0x100ac16e  mov     ecx, [ebp+var_9C]
  ... truncated ...
```
