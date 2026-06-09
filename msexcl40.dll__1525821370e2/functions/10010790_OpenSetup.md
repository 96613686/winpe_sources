# OpenSetup

- ea: `0x10010790`
- end: `0x10010ffd`
- name: `OpenSetup`
- size: `2157`
- prototype: `int __fastcall(int, unsigned int, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, installer_update`

## callers

- `0x10011280`

## callees

- `0x10006400`
- `0x10007320`
- `0x100094b0`
- `0x1000dcc0`
- `0x1000df70`
- `0x1000e440`
- `0x1000f470`
- `0x100102c0`
- `0x10010790`
- `0x1002580a`
- `0x10025ab7`
- `0x10025e72`
- `0x10025f86`
- `0x10026030`
- `0x100260bc`
- `0x1002eb45`
- `0x10033c94`
- `0x10033ce9`
- `0x10035510`
- `0x1003669c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10010dd2`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10010dd2`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x10010989`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x10010989`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x10010974`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x10010974`

## pseudocode

```c
int __fastcall OpenSetup(int a1, unsigned int a2, int a3)
{
  unsigned int v3; // esi
  int v5; // edi
  int v6; // ecx
  int v7; // eax
  bool v8; // sf
  void *v9; // esi
  size_t v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int16 v14; // di
  size_t v15; // esi
  void *v16; // eax
  int v17; // edi
  const CHAR *v18; // eax
  _WORD *v19; // esi
  int v20; // ecx
  int v22; // ecx
  int v23; // eax
  wchar_t *v24; // esi
  int v25; // edx
  unsigned __int16 *v26; // ecx
  unsigned __int16 *v27; // eax
  int v28; // esi
  _DWORD *i; // esi
  _DWORD **v30; // esi
  _DWORD **v31; // esi
  _DWORD *v32; // ecx
  _DWORD *j; // edx
  _DWORD *v35; // ecx
  _DWORD *v36; // esi
  int v37; // ecx
  int v38; // ecx
  UINT v39; // [esp-4h] [ebp-148h]
  void *Src; // [esp+10h] [ebp-134h] BYREF
  int v41; // [esp+14h] [ebp-130h]
  int v42; // [esp+18h] [ebp-12Ch] BYREF
  int *v43; // [esp+1Ch] [ebp-128h]
  int v44; // [esp+20h] [ebp-124h]
  int cbMultiByte; // [esp+24h] [ebp-120h] BYREF
  unsigned int v46; // [esp+28h] [ebp-11Ch]
  int v47; // [esp+2Ch] [ebp-118h] BYREF
  void *v48; // [esp+30h] [ebp-114h] BYREF
  __int16 v49; // [esp+34h] [ebp-110h] BYREF
  __int16 v50; // [esp+36h] [ebp-10Eh]
  wchar_t Ext[32]; // [esp+38h] [ebp-10Ch] BYREF
  wchar_t Filename[32]; // [esp+78h] [ebp-CCh] BYREF
  unsigned __int16 v53[66]; // [esp+B8h] [ebp-8Ch] BYREF

  v3 = a2;
  v43 = 0;
  v46 = a2;
  v44 = 0;
  v53[0] = 0;
  if ( ExcelReadRecordHeader(a1, &v49) )
    goto LABEL_116;
  if ( v49 != 9 )
  {
    if ( v49 == 521 )
      goto LABEL_9;
    if ( v49 != 1033 && v49 != 2057 )
    {
LABEL_116:
      v5 = -10;
      goto LABEL_117;
    }
  }
  if ( v49 != 1033 && v49 != 2057 )
  {
    v5 = -13;
    goto LABEL_117;
  }
LABEL_9:
  v5 = ExcelReadTotalRecord(a1, &v49, &v48);
  if ( v5 )
    goto LABEL_117;
  ParseBOFRecord(v48, a1 + 4, &v47, &cbMultiByte, &v42);
  v6 = *(_DWORD *)(a1 + 4);
  if ( v6 < 8 )
  {
    if ( v6 < 5 )
    {
      v3 &= ~0x800u;
      v46 = v3;
      *(_DWORD *)(a1 + 56) = v3;
    }
  }
  else if ( cbMultiByte < 2407 )
  {
    v5 = -13;
    goto LABEL_117;
  }
  if ( v47 == 32 )
  {
    v5 = -24;
    goto LABEL_117;
  }
  *(_DWORD *)(a1 + 8) = ExcelPTGSize();
  *(_DWORD *)(a1 + 12) = dword_10001C90;
  v7 = MemAllocate(2092);
  if ( !v7 )
  {
    *(_DWORD *)(a1 + 16) = 0;
LABEL_19:
    v5 = -2;
    goto LABEL_117;
  }
  *(_DWORD *)(a1 + 16) = v7;
  v47 = a1 + 16;
  *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                       + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                       - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
  v5 = ExcelReadRecordHeader(a1, &v49);
  v8 = v5 < 0;
  if ( !v5 )
  {
    v41 = 255;
    v47 = a1 + 16;
    v42 = 430;
    while ( 1 )
    {
      if ( v49 == 47 )
      {
        v5 = -12;
        goto LABEL_117;
      }
      if ( v49 == 66 )
      {
        v5 = ExcelReadTotalRecord(a1, &v49, &v48);
        v8 = v5 < 0;
        if ( v5 )
          break;
        v39 = *(__int16 *)v48;
        *(_DWORD *)(a1 + 28) = v39;
        if ( IsValidCodePage(v39) )
          *(_DWORD *)(a1 + 24) = *(_DWORD *)(a1 + 28);
        else
          *(_DWORD *)(a1 + 24) = GetACP();
        goto LABEL_86;
      }
      if ( ((v3 >> 12) & (v49 == (__int16)v41)) != 0 )
      {
        v9 = (void *)MemAllocate(1026);
        if ( !v9 )
          goto LABEL_19;
        v5 = ExcelReadTotalRecord(a1, &v49, &Src);
        if ( v5 )
        {
          MemFree(v9);
LABEL_87:
          v8 = v5 < 0;
          break;
        }
        LOWORD(v10) = v50;
        if ( (unsigned __int16)v50 >= 0x402u )
        {
          LOWORD(v10) = 1026;
          v50 = 1026;
        }
        v10 = (__int16)v10;
        if ( (unsigned int)(__int16)v10 > 0x402 )
          v10 = 1026;
        memcpy(v9, Src, v10);
        v11 = v47;
        *(_DWORD *)(a1 + 72) = v9;
        v3 = v46;
        v47 = v11;
      }
      else
      {
        if ( ((v3 >> 13) & (v49 == (__int16)v42)) == 0 )
        {
          v13 = *(_DWORD *)(a1 + 4);
          if ( v13 >= 8 && v49 == 23 )
          {
            if ( (v3 & 0x2000) != 0 )
            {
              v5 = ExcelReadTotalRecord(a1, &v49, &v48);
              v8 = v5 < 0;
              if ( v5 )
                break;
              v14 = v50;
              v15 = v50;
              v16 = (void *)MemAllocate(v50);
              *(_DWORD *)(a1 + 80) = v16;
              if ( !v16 )
                goto LABEL_19;
              memcpy(v16, v48, v15);
              cbMultiByte = 0;
              if ( !FSafeProductU(&cbMultiByte)
                || !FSafeSumU(&cbMultiByte)
                || (unsigned int)cbMultiByte > 0x7FFF
                || v14 < 0
                || v15 < cbMultiByte )
              {
                goto LABEL_116;
              }
              v3 = v46;
              goto LABEL_86;
            }
LABEL_72:
            if ( v49 == 133 )
            {
              v5 = ExcelReadTotalRecord(a1, &v49, &v48);
              v8 = v5 < 0;
              if ( v5 )
                break;
              cbMultiByte = *((unsigned __int8 *)v48 + 6);
              v17 = MemAllocate(2 * cbMultiByte + 62);
              if ( !v17 )
                goto LABEL_19;
              v18 = (const CHAR *)v48;
              v19 = (_WORD *)(v17 + 56);
              v20 = *(_DWORD *)v48;
              *(_DWORD *)(v17 + 8) = *(_DWORD *)v48;
              *(_DWORD *)(v17 + 4) = v20;
              *(_DWORD *)(v17 + 12) = *(_DWORD *)(a1 + 88);
              *(_DWORD *)(v17 + 32) = *((__int16 *)v18 + 2);
              ExcelExtractString(
                *(_DWORD *)(a1 + 4),
                *(_DWORD *)(a1 + 24),
                (__m128i *)(v17 + 56),
                2 * cbMultiByte,
                v18 + 7,
                cbMultiByte);
              while ( *v19++ )
                ;
              if ( (unsigned int)(((int)v19 - v17 - 58) >> 1) > 0x1F )
                *(_WORD *)(v17 + 118) = 0;
              v3 = v46;
              if ( v43 )
                *v43 = v17;
              else
                *(_DWORD *)(a1 + 64) = v17;
              v43 = (int *)v17;
              goto LABEL_86;
            }
          }
          else
          {
            if ( v49 == 10
              || v49 == 56
              || v49 == 516
              || v49 == 638
              || v49 == 515
              || v49 == 189
              || v49 == 190
              || v49 == 513
              || v49 == 517
              || v49 == 214
              || v49 == 253
              || v49 == 518
              || v49 == 1030
              || v49 == 6
              || v49 == 519
              || v49 == 545
              || v49 == 1212 )
            {
              goto LABEL_87;
            }
            if ( v13 >= 5 )
              goto LABEL_72;
          }
          v22 = *(_DWORD *)(a1 + 40);
          if ( v22 )
            *(_DWORD *)(v22 + 8) = **(_DWORD **)(v22 + 8);
          else
            BFSetFilePosition(*(int **)(a1 + 20), 1, v50);
          goto LABEL_86;
        }
        v5 = ExcelReadTotalRecord(a1, &v49, &v48);
        v8 = v5 < 0;
        if ( v5 )
          break;
        if ( v50 != 4 )
        {
          v12 = v44;
LABEL_42:
          v44 = v12 + 1;
          goto LABEL_86;
        }
        v12 = v44;
        if ( (*(_DWORD *)v48 & 0xFFFF0000) != 0x4010000 )
          goto LABEL_42;
        *(_DWORD *)(a1 + 76) = v44;
        v44 = v12 + 1;
      }
LABEL_86:
      *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                           + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                           - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
      v5 = ExcelReadRecordHeader(a1, &v49);
      if ( v5 )
        goto LABEL_87;
    }
  }
  if ( v8 )
    goto LABEL_117;
  if ( *(int *)(a1 + 4) <= 4 )
  {
    if ( !v53[0] )
      __wsplitpath_s((const wchar_t *)(a1 + 132), 0, 0, 0, 0, Filename, 0x1Fu, Ext, 0x1Fu);
    v23 = 2147483646;
    v24 = Filename;
    v25 = 63;
    v26 = v53;
    do
    {
      if ( !v23 )
        break;
      if ( !*v24 )
        break;
      *v26++ = *v24++;
      --v23;
      --v25;
    }
    while ( v25 );
    v27 = v26 - 1;
    if ( v25 )
      v27 = v26;
    *v27 = 0;
    v53[31] = 0;
    v28 = MemAllocate(2 * wcslen(v53) + 62);
    if ( !v28 )
    {
      v5 = -2;
      goto LABEL_117;
    }
    WCSCPY2(wcslen(v53) + 1);
    *(_DWORD *)(a1 + 64) = v28;
  }
  for ( i = *(_DWORD **)(a1 + 64); i; i = (_DWORD *)*i )
  {
    v5 = OpenFilePlySetup(v46);
    if ( v5 )
      goto LABEL_117;
  }
  if ( (v46 & 0x800) == 0 )
    return 0;
  v30 = (_DWORD **)(a1 + 40);
  v5 = ExcelMILoad(a1 + 40);
  if ( !v5 )
  {
    if ( !*(_DWORD *)(a1 + 48) )
      goto LABEL_113;
    BFCloseStream(*(_DWORD *)(a1 + 20));
    v5 = BFOpenStream(v46);
    if ( !v5 )
    {
      v31 = (_DWORD **)*v30;
      *(_DWORD *)(a1 + 40) = 0;
      v5 = ExcelMILoad(a1 + 52);
      *(_DWORD *)(a1 + 40) = v31;
      if ( !v5 )
      {
        BFCloseStream(*(_DWORD *)(a1 + 20));
        v5 = BFOpenStream(v46);
        if ( !v5 )
        {
          v30 = (_DWORD **)(a1 + 40);
LABEL_113:
          v32 = *(_DWORD **)(a1 + 64);
          for ( j = (_DWORD *)**v30; v32; j = (_DWORD *)*j )
          {
            v32[1] = j[1];
            v32[5] = j;
            v32 = (_DWORD *)*v32;
          }
          return 0;
        }
      }
    }
  }
LABEL_117:
  BFCloseFile(*(_DWORD *)(a1 + 20));
  v35 = *(_DWORD **)(a1 + 64);
  if ( v35 )
  {
    do
    {
      v36 = (_DWORD *)*v35;
      MemFree(v35);
      v35 = v36;
    }
    while ( v36 );
  }
  if ( *(_DWORD *)(a1 + 16) )
    TextStorageDestroy();
  v37 = *(_DWORD *)(a1 + 72);
  if ( v37 )
    MemFree(v37);
  v38 = *(_DWORD *)(a1 + 80);
  if ( v38 )
    MemFree(v38);
  MemFree(a1);
  return v5;
}

```

## disassembly

```asm
0x10010790  mov     edi, edi
0x10010792  push    ebp
0x10010793  mov     ebp, esp
0x10010795  sub     esp, 138h
0x1001079b  mov     eax, ___security_cookie
0x100107a0  xor     eax, ebp
0x100107a2  mov     [ebp+var_8], eax
0x100107a5  push    ebx
0x100107a6  push    esi
0x100107a7  mov     esi, edx
0x100107a9  mov     [ebp+var_128], 0
0x100107b3  xor     eax, eax
0x100107b5  mov     [ebp+var_11C], esi
0x100107bb  push    edi
0x100107bc  lea     edx, [ebp+var_110]
0x100107c2  mov     [ebp+var_124], 0
0x100107cc  mov     ebx, ecx
0x100107ce  mov     [ebp+var_8C], ax
0x100107d5  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x100107da  test    eax, eax
0x100107dc  jnz     loc_10010F98
0x100107e2  mov     ax, [ebp+var_110]
0x100107e9  mov     ecx, 209h
0x100107ee  mov     edx, 409h
0x100107f3  mov     edi, 809h
0x100107f8  cmp     ax, 9
0x100107fc  jz      short loc_10010811
0x100107fe  cmp     ax, cx
0x10010801  jz      short loc_1001082A
0x10010803  cmp     ax, dx
0x10010806  jz      short loc_10010811
0x10010808  cmp     ax, di
0x1001080b  jnz     loc_10010F98
0x10010811  cmp     ax, cx
0x10010814  jz      short loc_1001082A
0x10010816  cmp     ax, dx
0x10010819  jz      short loc_1001082A
0x1001081b  cmp     ax, di
0x1001081e  jz      short loc_1001082A
0x10010820  mov     edi, 0FFFFFFF3h
0x10010825  jmp     loc_10010F9D
0x1001082a  lea     eax, [ebp+var_114]
0x10010830  mov     ecx, ebx
0x10010832  push    eax
0x10010833  lea     edx, [ebp+var_110]
0x10010839  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x1001083e  mov     edi, eax
0x10010840  test    edi, edi
0x10010842  jnz     loc_10010F9D
0x10010848  movsx   edx, [ebp+var_110]
0x1001084f  lea     eax, [ebp+var_12C]
0x10010855  push    eax
0x10010856  lea     eax, [ebp+cbMultiByte]
0x1001085c  mov     ecx, ebx
0x1001085e  push    eax
0x1001085f  lea     eax, [ebp+var_118]
0x10010865  push    eax
0x10010866  lea     edi, [ebx+4]
0x10010869  push    edi
0x1001086a  push    [ebp+var_114]
0x10010870  call    ParseBOFRecord
0x10010875  mov     ecx, [edi]
0x10010877  cmp     ecx, 8
0x1001087a  jl      short loc_10010892
0x1001087c  cmp     [ebp+cbMultiByte], 967h
0x10010886  jge     short loc_100108A6
0x10010888  mov     edi, 0FFFFFFF3h
0x1001088d  jmp     loc_10010F9D
0x10010892  cmp     ecx, 5
0x10010895  jge     short loc_100108A6
0x10010897  and     esi, 0FFFFF7FFh
0x1001089d  mov     [ebp+var_11C], esi
0x100108a3  mov     [ebx+38h], esi
0x100108a6  cmp     [ebp+var_118], 20h ; ' '
0x100108ad  jnz     short loc_100108B9
0x100108af  mov     edi, 0FFFFFFE8h
0x100108b4  jmp     loc_10010F9D
0x100108b9  call    _ExcelPTGSize@4; ExcelPTGSize(x)
0x100108be  mov     ecx, 82Ch
0x100108c3  mov     [ebx+8], eax
0x100108c6  mov     dword ptr [ebx+0Ch], offset dword_10001C90
0x100108cd  call    _MemAllocate@4; MemAllocate(x)
0x100108d2  test    eax, eax
0x100108d4  jnz     short loc_100108E3
0x100108d6  mov     [ebx+10h], eax
0x100108d9  mov     edi, 0FFFFFFFEh
0x100108de  jmp     loc_10010F9D
0x100108e3  mov     [ebx+10h], eax
0x100108e6  lea     ecx, [ebx+10h]
0x100108e9  mov     [ebp+var_118], ecx
0x100108ef  lea     edx, [ebp+var_110]
0x100108f5  mov     ecx, [ebx+14h]
0x100108f8  mov     eax, [ecx+54h]
0x100108fb  sub     eax, [ecx+4]
0x100108fe  add     eax, [ecx+8]
0x10010901  mov     ecx, ebx
0x10010903  mov     [ebx+58h], eax
0x10010906  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x1001090b  mov     edi, eax
0x1001090d  test    edi, edi
0x1001090f  jnz     loc_10010D97
0x10010915  lea     eax, [ebx+10h]
0x10010918  mov     [ebp+var_130], 0FFh
0x10010922  mov     [ebp+var_118], eax
0x10010928  mov     [ebp+var_12C], 1AEh
0x10010932  mov     dx, [ebp+var_110]
0x10010939  cmp     dx, 2Fh ; '/'
0x1001093d  jz      loc_10010E65
0x10010943  cmp     dx, 42h ; 'B'
0x10010947  jnz     short loc_10010997
0x10010949  lea     eax, [ebp+var_114]
0x1001094f  mov     ecx, ebx
0x10010951  push    eax
0x10010952  lea     edx, [ebp+var_110]
0x10010958  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x1001095d  mov     edi, eax
0x1001095f  test    edi, edi
0x10010961  jnz     loc_10010D97
0x10010967  mov     eax, [ebp+var_114]
0x1001096d  movsx   eax, word ptr [eax]
0x10010970  push    eax; CodePage
0x10010971  mov     [ebx+1Ch], eax
0x10010974  call    ds:__imp__IsValidCodePage@4; IsValidCodePage(x)
0x1001097a  test    eax, eax
0x1001097c  jz      short loc_10010989
0x1001097e  mov     eax, [ebx+1Ch]
0x10010981  mov     [ebx+18h], eax
0x10010984  jmp     loc_10010D6F
0x10010989  call    ds:__imp__GetACP@0; GetACP()
0x1001098f  mov     [ebx+18h], eax
0x10010992  jmp     loc_10010D6F
0x10010997  mov     ecx, esi
0x10010999  xor     eax, eax
0x1001099b  shr     ecx, 0Ch
0x1001099e  cmp     dx, word ptr [ebp+var_130]
0x100109a5  setz    al
0x100109a8  test    eax, ecx
0x100109aa  jz      short loc_10010A2B
0x100109ac  mov     ecx, 402h
0x100109b1  call    _MemAllocate@4; MemAllocate(x)
0x100109b6  mov     esi, eax
0x100109b8  test    esi, esi
0x100109ba  jz      loc_100108D9
0x100109c0  lea     eax, [ebp+Src]
0x100109c6  mov     ecx, ebx
0x100109c8  push    eax
0x100109c9  lea     edx, [ebp+var_110]
0x100109cf  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x100109d4  mov     edi, eax
0x100109d6  test    edi, edi
0x100109d8  jnz     loc_10010E59
0x100109de  mov     ax, [ebp+var_10E]
0x100109e5  mov     ecx, 402h
0x100109ea  cmp     ax, cx
0x100109ed  jb      short loc_100109F8
0x100109ef  mov     eax, ecx
0x100109f1  mov     [ebp+var_10E], ax
0x100109f8  cwde
0x100109f9  cmp     eax, 402h
0x100109fe  cmova   eax, ecx
0x10010a01  push    eax; Size
0x10010a02  push    [ebp+Src]; Src
0x10010a08  push    esi; void *
0x10010a09  call    _memcpy
0x10010a0e  mov     eax, [ebp+var_118]
0x10010a14  add     esp, 0Ch
0x10010a17  mov     [ebx+48h], esi
0x10010a1a  mov     esi, [ebp+var_11C]
0x10010a20  mov     [ebp+var_118], eax
0x10010a26  jmp     loc_10010D6F
0x10010a2b  mov     ecx, esi
0x10010a2d  xor     eax, eax
0x10010a2f  shr     ecx, 0Dh
0x10010a32  cmp     dx, word ptr [ebp+var_12C]
0x10010a39  setz    al
0x10010a3c  test    eax, ecx
0x10010a3e  jz      short loc_10010AA3
0x10010a40  lea     eax, [ebp+var_114]
0x10010a46  mov     ecx, ebx
0x10010a48  push    eax
0x10010a49  lea     edx, [ebp+var_110]
0x10010a4f  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x10010a54  mov     edi, eax
0x10010a56  test    edi, edi
0x10010a58  jnz     loc_10010D97
0x10010a5e  cmp     [ebp+var_10E], 4
0x10010a66  jnz     short loc_10010A91
0x10010a68  mov     eax, [ebp+var_114]
0x10010a6e  mov     eax, [eax]
0x10010a70  and     eax, 0FFFF0000h
0x10010a75  cmp     eax, 4010000h
0x10010a7a  mov     eax, [ebp+var_124]
0x10010a80  jnz     short loc_10010A97
0x10010a82  mov     [ebx+4Ch], eax
0x10010a85  inc     eax
0x10010a86  mov     [ebp+var_124], eax
0x10010a8c  jmp     loc_10010D6F
0x10010a91  mov     eax, [ebp+var_124]
0x10010a97  inc     eax
0x10010a98  mov     [ebp+var_124], eax
0x10010a9e  jmp     loc_10010D6F
0x10010aa3  mov     eax, [ebx+4]
0x10010aa6  cmp     eax, 8
0x10010aa9  jl      loc_10010B8B
0x10010aaf  cmp     dx, 17h
0x10010ab3  jnz     loc_10010B8B
0x10010ab9  test    esi, 2000h
0x10010abf  jz      loc_10010C76
0x10010ac5  lea     eax, [ebp+var_114]
0x10010acb  mov     ecx, ebx
0x10010acd  push    eax
0x10010ace  lea     edx, [ebp+var_110]
0x10010ad4  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x10010ad9  mov     edi, eax
0x10010adb  test    edi, edi
0x10010add  jnz     loc_10010D97
0x10010ae3  mov     di, [ebp+var_10E]
0x10010aea  movsx   esi, di
0x10010aed  mov     ecx, esi
0x10010aef  call    _MemAllocate@4; MemAllocate(x)
0x10010af4  mov     [ebx+50h], eax
0x10010af7  test    eax, eax
0x10010af9  jz      loc_100108D9
0x10010aff  push    esi; Size
0x10010b00  push    [ebp+var_114]; Src
0x10010b06  push    eax; void *
0x10010b07  call    _memcpy
0x10010b0c  add     esp, 0Ch
0x10010b0f  mov     [ebp+cbMultiByte], 0
0x10010b19  lea     eax, [ebp+cbMultiByte]
0x10010b1f  push    eax
0x10010b20  mov     eax, [ebx+50h]
0x10010b23  movsx   ecx, word ptr [eax]
0x10010b26  call    _FSafeProductU@12; FSafeProductU(x,x,x)
0x10010b2b  test    eax, eax
0x10010b2d  jz      loc_10010F98
0x10010b33  mov     edx, [ebp+cbMultiByte]
0x10010b39  lea     eax, [ebp+cbMultiByte]
0x10010b3f  push    eax
0x10010b40  mov     ecx, 2
0x10010b45  call    _FSafeSumU@12; FSafeSumU(x,x,x)
0x10010b4a  test    eax, eax
0x10010b4c  jz      loc_10010F98
0x10010b52  mov     eax, [ebp+var_118]
0x10010b58  mov     [ebp+var_118], eax
0x10010b5e  mov     eax, [ebp+cbMultiByte]
0x10010b64  cmp     eax, 7FFFh
0x10010b69  ja      loc_10010F98
0x10010b6f  test    di, di
0x10010b72  js      loc_10010F98
0x10010b78  cmp     esi, eax
0x10010b7a  jb      loc_10010F98
0x10010b80  mov     esi, [ebp+var_11C]
0x10010b86  jmp     loc_10010D6F
0x10010b8b  cmp     dx, 0Ah
0x10010b8f  jz      loc_10010D95
0x10010b95  cmp     dx, 38h ; '8'
0x10010b99  jz      loc_10010D95
0x10010b9f  mov     ecx, 204h
0x10010ba4  cmp     dx, cx
0x10010ba7  jz      loc_10010D95
0x10010bad  mov     ecx, 27Eh
0x10010bb2  cmp     dx, cx
0x10010bb5  jz      loc_10010D95
0x10010bbb  mov     ecx, 203h
0x10010bc0  cmp     dx, cx
0x10010bc3  jz      loc_10010D95
0x10010bc9  mov     ecx, 0BDh
0x10010bce  cmp     dx, cx
0x10010bd1  jz      loc_10010D95
0x10010bd7  mov     ecx, 0BEh
0x10010bdc  cmp     dx, cx
0x10010bdf  jz      loc_10010D95
0x10010be5  mov     ecx, 201h
0x10010bea  cmp     dx, cx
0x10010bed  jz      loc_10010D95
0x10010bf3  mov     ecx, 205h
0x10010bf8  cmp     dx, cx
0x10010bfb  jz      loc_10010D95
0x10010c01  mov     ecx, 0D6h
0x10010c06  cmp     dx, cx
0x10010c09  jz      loc_10010D95
0x10010c0f  mov     ecx, 0FDh
0x10010c14  cmp     dx, cx
0x10010c17  jz      loc_10010D95
0x10010c1d  mov     ecx, 206h
0x10010c22  cmp     dx, cx
0x10010c25  jz      loc_10010D95
0x10010c2b  mov     ecx, 406h
0x10010c30  cmp     dx, cx
0x10010c33  jz      loc_10010D95
0x10010c39  cmp     dx, 6
0x10010c3d  jz      loc_10010D95
0x10010c43  mov     ecx, 207h
0x10010c48  cmp     dx, cx
0x10010c4b  jz      loc_10010D95
0x10010c51  mov     ecx, 221h
0x10010c56  cmp     dx, cx
0x10010c59  jz      loc_10010D95
0x10010c5f  mov     ecx, 4BCh
  ... truncated ...
```
