# ErrGetLinkColIdxInfo

- ea: `0x1002c8f0`
- end: `0x1002ce5a`
- name: `ErrGetLinkColIdxInfo`
- size: `1386`
- prototype: `int __fastcall(int, int, int, int, int, int, unsigned int, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x10013500`
- `0x10015e50`
- `0x1002b920`
- `0x1002e750`

## callees

- `0x1002a7d0`
- `0x1002a840`
- `0x1002c7b0`
- `0x1002c8f0`
- `0x1003a840`
- `0x1003e930`
- `0x1003e9b0`
- `0x1003ea00`
- `0x10042b60`
- `0x10042f50`
- `0x100430d0`
- `0x100433f0`
- `0x100439d0`
- `0x10044240`
- `0x10044a70`
- `0x10045280`
- `0x100454a0`
- `0x10123110`
- `0x10123130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002cdba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002cdba`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002cd82`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002cd82`

## pseudocode

```c
int __fastcall ErrGetLinkColIdxInfo(int a1, int a2, int a3, int a4, int a5, int a6, unsigned int a7, int a8)
{
  int v9; // eax
  int v11; // eax
  char *v12; // ebx
  int result; // eax
  __int64 v14; // xmm0_8
  int TableColumnInfo; // edi
  int v16; // ecx
  unsigned int v17; // eax
  int v18; // eax
  int ObjidFromName; // eax
  char *v20; // eax
  int v21; // ecx
  int IndexInfo; // eax
  int ColumnInfo; // eax
  _DWORD *v24; // edi
  _DWORD *v25; // eax
  void *v26; // ebx
  char *v27; // eax
  int v28; // ecx
  int v29; // ecx
  int v30; // [esp-14h] [ebp-57Ch]
  int v31; // [esp-4h] [ebp-56Ch]
  _DWORD v32[4]; // [esp+10h] [ebp-558h] BYREF
  __int64 v33; // [esp+20h] [ebp-548h]
  int v34; // [esp+2Ch] [ebp-53Ch] BYREF
  char *v35; // [esp+30h] [ebp-538h]
  int v36; // [esp+34h] [ebp-534h]
  int v37; // [esp+38h] [ebp-530h]
  _WORD *i; // [esp+3Ch] [ebp-52Ch] BYREF
  int v39; // [esp+40h] [ebp-528h]
  int v40; // [esp+44h] [ebp-524h] BYREF
  int v41; // [esp+48h] [ebp-520h] BYREF
  int v42; // [esp+4Ch] [ebp-51Ch] BYREF
  char v43[4]; // [esp+50h] [ebp-518h] BYREF
  int v44; // [esp+54h] [ebp-514h]
  _WORD v45[304]; // [esp+68h] [ebp-500h] BYREF
  _WORD v46[264]; // [esp+2C8h] [ebp-2A0h] BYREF
  _WORD Src[70]; // [esp+4D8h] [ebp-90h] BYREF

  v39 = a5;
  v36 = a4;
  v9 = isibHead;
  v40 = -1;
  v41 = -1;
  for ( i = 0; v9 != -1; v9 = dword_1016EB88[26 * v9] )
  {
    if ( rgsib[26 * v9] == a1 )
      break;
  }
  if ( v9 >= 0 )
  {
    _mm_lfence();
    v11 = dword_1016EB44[26 * v9];
  }
  else
  {
    v11 = -1;
  }
  v12 = (char *)rgtib + 2316 * v11;
  v35 = v12;
  result = ErrGetObjInfoId(6, a3, &v40, 0);
  if ( result >= 0 )
  {
    v14 = *((_QWORD *)v12 + 283);
    v37 = *((_DWORD *)v12 + 568);
    v30 = v40;
    *((_DWORD *)v12 + 566) = a1;
    *((_DWORD *)v12 + 567) = a2;
    v33 = v14;
    v42 = 522;
    TableColumnInfo = ErrDispGetTableColumnInfo(a1, v30, L"Database", v43, 24, 0);
    if ( TableColumnInfo >= 0 )
    {
      TableColumnInfo = ErrDispRetrieveColumn(a1, v40, v44, v46, v42, &v42, 0, 0);
      if ( TableColumnInfo >= 0 )
      {
        v17 = v42 & 0xFFFFFFFE;
        if ( (v42 & 0xFFFFFFFE) >= 0x20A )
          goto LABEL_59;
        v42 = 604;
        *(_WORD *)((char *)v46 + v17) = 0;
        TableColumnInfo = ErrDispGetTableColumnInfo(a1, v40, L"Connect", v43, 24, 0);
        if ( TableColumnInfo >= 0 )
        {
          v18 = ErrDispRetrieveColumn(a1, v40, v44, v45, v42, &v42, 0, 0);
          TableColumnInfo = v18;
          if ( v18 >= 0 )
          {
            if ( v18 != 1004 )
            {
              if ( (v42 & 0xFFFFFFFE) >= 0x25C )
                goto LABEL_59;
              *(_WORD *)((char *)v45 + (v42 & 0xFFFFFFFE)) = 0;
              i = v45;
            }
            v42 = 130;
            TableColumnInfo = ErrGetSysField(L"ForeignName", Src, &v42);
            if ( TableColumnInfo >= 0 )
            {
              if ( (v42 & 0xFFFFFFFE) < 0x82 )
              {
                v31 = v40;
                *(_WORD *)((char *)Src + (v42 & 0xFFFFFFFE)) = 0;
                ErrDispCloseTable(a1, v31);
                TableColumnInfo = ErrTryOpenDatabase(a1, v46, i, &v41, 0, 0);
                if ( TableColumnInfo >= 0 )
                {
                  if ( IsJetIsam(a1, v41) )
                  {
                    ObjidFromName = ErrDispGetObjidFromName(a1, v41, L"Tables", Src, &v34);
                    TableColumnInfo = ObjidFromName;
                    if ( ObjidFromName == -1305 )
                    {
                      ClearErrorInfo(a1);
                      UtilSetErrorInfoReal(a1, 0, Src, 0, -8003, 0, 0, 0);
LABEL_22:
                      ErrDispCloseDatabase(a1, v41, 0);
                      v20 = v35;
                      v21 = v37;
                      *((_QWORD *)v35 + 283) = v33;
                      *((_DWORD *)v20 + 568) = v21;
                      return TableColumnInfo;
                    }
                    if ( ObjidFromName < 0 )
                      goto LABEL_22;
                    TableColumnInfo = ErrSecGetAccess(a1, v41, v34, 0, 0, 0, &i, 0);
                    if ( TableColumnInfo < 0 )
                      goto LABEL_22;
                    if ( ((unsigned __int8)i & 0xFC) == 0 )
                    {
                      UtilSetErrorInfoReal(a1, Src, 0, 0, -8118, 0, 0, 0);
LABEL_27:
                      TableColumnInfo = -1907;
                      goto LABEL_22;
                    }
                    if ( a7 == 3 && ((unsigned __int8)i & 8) == 0 )
                    {
                      UtilSetErrorInfoReal(a1, Src, 0, 0, -8170, 0, 0, 0);
                      goto LABEL_27;
                    }
                  }
                  v32[3] = v39;
                  v32[0] = a6;
                  if ( a8 )
                  {
                    IndexInfo = ErrDispGetIndexInfo(a1, v41, Src, v36, v32, a7);
                    TableColumnInfo = IndexInfo;
                    if ( IndexInfo == -1034 || IndexInfo == -1035 || IndexInfo == -1052 )
                      UtilSetErrorInfoReal(a1, 0, Src, 0, -8003, 0, 0, 0);
                    if ( TableColumnInfo < 0 )
                      goto LABEL_22;
                    if ( a7 >= 2 )
                      goto LABEL_38;
                  }
                  else
                  {
                    ColumnInfo = ErrDispGetColumnInfo(a1, v41, Src, v36, v32, a7);
                    TableColumnInfo = ColumnInfo;
                    if ( ColumnInfo == -1034 || ColumnInfo == -1035 || ColumnInfo == -1052 )
                      UtilSetErrorInfoReal(a1, 0, Src, 0, -8003, 0, 0, 0);
                    if ( TableColumnInfo < 0 )
                      goto LABEL_22;
                    if ( a7 != 1 && a7 != 2 && a7 != 8 && a7 != 7 )
                    {
LABEL_38:
                      ErrDispCloseDatabase(a1, v41, 0);
                      goto LABEL_54;
                    }
                  }
                  v24 = (_DWORD *)(v39 + 4);
                  if ( v39 != -4 )
                  {
                    v25 = _malloc(8u);
                    v26 = v25;
                    if ( !v25 )
                    {
                      TableColumnInfo = -1011;
                      goto LABEL_22;
                    }
                    *v25 = v41;
                    v25[1] = *v24;
                    TableColumnInfo = ErrAllocateTableid(0);
                    if ( TableColumnInfo < 0 )
                    {
                      _free(v26);
                      goto LABEL_22;
                    }
                    ErrUpdateTableid(*(_DWORD *)(v39 + 4), v26, &vtfndefLinfoDisp);
                  }
LABEL_54:
                  v27 = v35;
                  v28 = v37;
                  *((_QWORD *)v35 + 283) = v33;
                  *((_DWORD *)v27 + 568) = v28;
                  return 0;
                }
LABEL_56:
                v29 = v37;
                *((_QWORD *)v12 + 283) = v33;
                *((_DWORD *)v12 + 568) = v29;
                return TableColumnInfo;
              }
LABEL_59:
              __report_rangecheckfailure(v16);
            }
          }
        }
      }
    }
    ErrDispCloseTable(a1, v40);
    goto LABEL_56;
  }
  return result;
}

```

## disassembly

```asm
0x1002c8f0  mov     edi, edi
0x1002c8f2  push    ebp
0x1002c8f3  mov     ebp, esp
0x1002c8f5  sub     esp, 55Ch
0x1002c8fb  mov     eax, ___security_cookie
0x1002c900  xor     eax, ebp
0x1002c902  mov     [ebp+var_4], eax
0x1002c905  mov     eax, [ebp+arg_8]
0x1002c908  push    ebx
0x1002c909  mov     [ebp+var_528], eax
0x1002c90f  mov     eax, [ebp+arg_4]
0x1002c912  push    esi
0x1002c913  mov     [ebp+var_534], eax
0x1002c919  mov     esi, ecx
0x1002c91b  mov     eax, _isibHead
0x1002c920  mov     [ebp+var_524], 0FFFFFFFFh
0x1002c92a  mov     [ebp+var_520], 0FFFFFFFFh
0x1002c934  mov     [ebp+var_52C], 0
0x1002c93e  push    edi
0x1002c93f  mov     edi, edx
0x1002c941  mov     edx, [ebp+arg_0]
0x1002c944  cmp     eax, 0FFFFFFFFh
0x1002c947  jz      short loc_1002C966
0x1002c949  nop     dword ptr [eax+00000000h]
0x1002c950  imul    ecx, eax, 68h ; 'h'
0x1002c953  cmp     _rgsib[ecx], esi
0x1002c959  jz      short loc_1002C966
0x1002c95b  mov     eax, dword_1016EB88[ecx]
0x1002c961  cmp     eax, 0FFFFFFFFh
0x1002c964  jnz     short loc_1002C950
0x1002c966  test    eax, eax
0x1002c968  jns     short loc_1002C96F
0x1002c96a  or      eax, 0FFFFFFFFh
0x1002c96d  jmp     short loc_1002C97B
0x1002c96f  imul    eax, 68h ; 'h'
0x1002c972  lfence
0x1002c975  mov     eax, dword_1016EB44[eax]
0x1002c97b  imul    ebx, eax, 90Ch
0x1002c981  mov     ecx, esi
0x1002c983  push    0
0x1002c985  lea     eax, [ebp+var_524]
0x1002c98b  push    eax
0x1002c98c  push    edx
0x1002c98d  add     ebx, _rgtib
0x1002c993  mov     edx, edi
0x1002c995  push    6
0x1002c997  mov     [ebp+var_538], ebx
0x1002c99d  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x1002c9a2  test    eax, eax
0x1002c9a4  js      loc_1002CE42
0x1002c9aa  mov     eax, [ebx+8E0h]
0x1002c9b0  movq    xmm0, qword ptr [ebx+8D8h]
0x1002c9b8  push    0
0x1002c9ba  push    18h
0x1002c9bc  mov     [ebp+var_530], eax
0x1002c9c2  lea     eax, [ebp+var_518]
0x1002c9c8  push    eax
0x1002c9c9  push    offset _wszSoDatabaseColumn; "Database"
0x1002c9ce  push    [ebp+var_524]
0x1002c9d4  mov     [ebx+8D8h], esi
0x1002c9da  mov     [ebx+8DCh], edi
0x1002c9e0  push    esi
0x1002c9e1  movq    [ebp+var_548], xmm0
0x1002c9e9  mov     [ebp+var_51C], 20Ah
0x1002c9f3  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002c9f8  mov     edi, eax
0x1002c9fa  test    edi, edi
0x1002c9fc  js      loc_1002CE18
0x1002ca02  push    0
0x1002ca04  push    0
0x1002ca06  lea     eax, [ebp+var_51C]
0x1002ca0c  push    eax
0x1002ca0d  push    [ebp+var_51C]
0x1002ca13  lea     eax, [ebp+var_2A0]
0x1002ca19  push    eax
0x1002ca1a  push    [ebp+var_514]
0x1002ca20  push    [ebp+var_524]
0x1002ca26  push    esi
0x1002ca27  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002ca2c  mov     edi, eax
0x1002ca2e  test    edi, edi
0x1002ca30  js      loc_1002CE18
0x1002ca36  mov     eax, [ebp+var_51C]
0x1002ca3c  and     eax, 0FFFFFFFEh
0x1002ca3f  cmp     eax, 20Ah
0x1002ca44  jnb     loc_1002CE55
0x1002ca4a  xor     ecx, ecx
0x1002ca4c  mov     [ebp+var_51C], 25Ch
0x1002ca56  push    ecx
0x1002ca57  push    18h
0x1002ca59  mov     [ebp+eax+var_2A0], cx
0x1002ca61  lea     eax, [ebp+var_518]
0x1002ca67  push    eax
0x1002ca68  push    offset _wszSoConnectColumn; "Connect"
0x1002ca6d  push    [ebp+var_524]
0x1002ca73  push    esi
0x1002ca74  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002ca79  mov     edi, eax
0x1002ca7b  test    edi, edi
0x1002ca7d  js      loc_1002CE18
0x1002ca83  push    0
0x1002ca85  push    0
0x1002ca87  lea     eax, [ebp+var_51C]
0x1002ca8d  push    eax
0x1002ca8e  push    [ebp+var_51C]
0x1002ca94  lea     eax, [ebp+var_500]
0x1002ca9a  push    eax
0x1002ca9b  push    [ebp+var_514]
0x1002caa1  push    [ebp+var_524]
0x1002caa7  push    esi
0x1002caa8  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002caad  mov     edi, eax
0x1002caaf  test    edi, edi
0x1002cab1  js      loc_1002CE18
0x1002cab7  cmp     edi, 3ECh
0x1002cabd  jz      short loc_1002CAE9
0x1002cabf  mov     eax, [ebp+var_51C]
0x1002cac5  and     eax, 0FFFFFFFEh
0x1002cac8  cmp     eax, 25Ch
0x1002cacd  jnb     loc_1002CE55
0x1002cad3  xor     ecx, ecx
0x1002cad5  mov     [ebp+eax+var_500], cx
0x1002cadd  lea     eax, [ebp+var_500]
0x1002cae3  mov     [ebp+var_52C], eax
0x1002cae9  mov     edx, [ebp+var_524]
0x1002caef  lea     eax, [ebp+var_51C]
0x1002caf5  push    eax
0x1002caf6  lea     eax, [ebp+Src]
0x1002cafc  mov     [ebp+var_51C], 82h
0x1002cb06  push    eax
0x1002cb07  push    offset _wszSoForeignNameColumn; "ForeignName"
0x1002cb0c  mov     ecx, esi
0x1002cb0e  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x1002cb13  mov     edi, eax
0x1002cb15  test    edi, edi
0x1002cb17  js      loc_1002CE18
0x1002cb1d  mov     eax, [ebp+var_51C]
0x1002cb23  and     eax, 0FFFFFFFEh
0x1002cb26  cmp     eax, 82h
0x1002cb2b  jnb     loc_1002CE55
0x1002cb31  push    [ebp+var_524]
0x1002cb37  xor     ecx, ecx
0x1002cb39  push    esi
0x1002cb3a  mov     [ebp+eax+Src], cx
0x1002cb42  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1002cb47  push    0
0x1002cb49  push    0
0x1002cb4b  lea     eax, [ebp+var_520]
0x1002cb51  mov     ecx, esi
0x1002cb53  push    eax
0x1002cb54  push    [ebp+var_52C]
0x1002cb5a  lea     edx, [ebp+var_2A0]
0x1002cb60  call    _ErrTryOpenDatabase@24; ErrTryOpenDatabase(x,x,x,x,x,x)
0x1002cb65  mov     edi, eax
0x1002cb67  test    edi, edi
0x1002cb69  js      loc_1002CE24
0x1002cb6f  mov     edx, [ebp+var_520]
0x1002cb75  mov     ecx, esi
0x1002cb77  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1002cb7c  mov     ebx, [ebp+arg_10]
0x1002cb7f  test    eax, eax
0x1002cb81  jz      loc_1002CC78
0x1002cb87  lea     eax, [ebp+var_53C]
0x1002cb8d  push    eax
0x1002cb8e  lea     eax, [ebp+Src]
0x1002cb94  push    eax
0x1002cb95  push    offset _wszTcObject; "Tables"
0x1002cb9a  push    [ebp+var_520]
0x1002cba0  push    esi
0x1002cba1  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1002cba6  mov     edi, eax
0x1002cba8  cmp     edi, 0FFFFFAE7h
0x1002cbae  jnz     short loc_1002CC07
0x1002cbb0  push    esi
0x1002cbb1  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1002cbb6  push    0; int
0x1002cbb8  push    0; int
0x1002cbba  push    0; int
0x1002cbbc  push    0FFFFE0BDh; int
0x1002cbc1  push    0; void *
0x1002cbc3  lea     eax, [ebp+Src]
0x1002cbc9  push    eax; void *
0x1002cbca  push    0; Src
0x1002cbcc  push    esi; int
0x1002cbcd  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002cbd2  push    0
0x1002cbd4  push    [ebp+var_520]
0x1002cbda  push    esi
0x1002cbdb  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1002cbe0  mov     eax, [ebp+var_538]
0x1002cbe6  movq    xmm0, [ebp+var_548]
0x1002cbee  mov     ecx, [ebp+var_530]
0x1002cbf4  movq    qword ptr [eax+8D8h], xmm0
0x1002cbfc  mov     [eax+8E0h], ecx
0x1002cc02  jmp     loc_1002CE40
0x1002cc07  test    edi, edi
0x1002cc09  js      short loc_1002CBD2
0x1002cc0b  push    0
0x1002cc0d  lea     eax, [ebp+var_52C]
0x1002cc13  push    eax
0x1002cc14  push    0
0x1002cc16  push    0
0x1002cc18  push    0
0x1002cc1a  push    [ebp+var_53C]
0x1002cc20  push    [ebp+var_520]
0x1002cc26  push    esi
0x1002cc27  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x1002cc2c  mov     edi, eax
0x1002cc2e  test    edi, edi
0x1002cc30  js      short loc_1002CBD2
0x1002cc32  mov     eax, [ebp+var_52C]
0x1002cc38  test    al, 0FCh
0x1002cc3a  jnz     short loc_1002CC62
0x1002cc3c  push    0; int
0x1002cc3e  push    0; int
0x1002cc40  push    0; int
0x1002cc42  push    0FFFFE04Ah; int
0x1002cc47  push    0; void *
0x1002cc49  push    0; void *
0x1002cc4b  lea     eax, [ebp+Src]
0x1002cc51  push    eax; Src
0x1002cc52  push    esi; int
0x1002cc53  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002cc58  mov     edi, 0FFFFF88Dh
0x1002cc5d  jmp     loc_1002CBD2
0x1002cc62  cmp     ebx, 3
0x1002cc65  jnz     short loc_1002CC78
0x1002cc67  test    al, 8
0x1002cc69  jnz     short loc_1002CC78
0x1002cc6b  push    0
0x1002cc6d  push    0
0x1002cc6f  push    0
0x1002cc71  push    0FFFFE016h
0x1002cc76  jmp     short loc_1002CC47
0x1002cc78  cmp     [ebp+arg_14], 0
0x1002cc7c  mov     eax, [ebp+var_528]
0x1002cc82  mov     [ebp+var_54C], eax
0x1002cc88  mov     eax, [ebp+arg_C]
0x1002cc8b  push    ebx
0x1002cc8c  mov     [ebp+var_558], eax
0x1002cc92  lea     eax, [ebp+var_558]
0x1002cc98  push    eax
0x1002cc99  push    [ebp+var_534]
0x1002cc9f  lea     eax, [ebp+Src]
0x1002cca5  push    eax
0x1002cca6  push    [ebp+var_520]
0x1002ccac  push    esi
0x1002ccad  jz      short loc_1002CD0E
0x1002ccaf  call    _ErrDispGetIndexInfo@24; ErrDispGetIndexInfo(x,x,x,x,x,x)
0x1002ccb4  mov     edi, eax
0x1002ccb6  cmp     edi, 0FFFFFBF6h
0x1002ccbc  jz      short loc_1002CCCE
0x1002ccbe  cmp     edi, 0FFFFFBF5h
0x1002ccc4  jz      short loc_1002CCCE
0x1002ccc6  cmp     edi, 0FFFFFBE4h
0x1002cccc  jnz     short loc_1002CCEA
0x1002ccce  push    0; int
0x1002ccd0  push    0; int
0x1002ccd2  push    0; int
0x1002ccd4  push    0FFFFE0BDh; int
0x1002ccd9  push    0; void *
0x1002ccdb  lea     eax, [ebp+Src]
0x1002cce1  push    eax; void *
0x1002cce2  push    0; Src
0x1002cce4  push    esi; int
0x1002cce5  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002ccea  test    edi, edi
0x1002ccec  js      loc_1002CBD2
0x1002ccf2  test    ebx, ebx
0x1002ccf4  jz      short loc_1002CD71
0x1002ccf6  cmp     ebx, 1
0x1002ccf9  jz      short loc_1002CD71
0x1002ccfb  push    0
0x1002ccfd  push    [ebp+var_520]
0x1002cd03  push    esi
0x1002cd04  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1002cd09  jmp     loc_1002CDE1
0x1002cd0e  call    _ErrDispGetColumnInfo@24; ErrDispGetColumnInfo(x,x,x,x,x,x)
0x1002cd13  mov     edi, eax
0x1002cd15  cmp     edi, 0FFFFFBF6h
0x1002cd1b  jz      short loc_1002CD2D
0x1002cd1d  cmp     edi, 0FFFFFBF5h
0x1002cd23  jz      short loc_1002CD2D
0x1002cd25  cmp     edi, 0FFFFFBE4h
0x1002cd2b  jnz     short loc_1002CD49
0x1002cd2d  push    0; int
0x1002cd2f  push    0; int
0x1002cd31  push    0; int
0x1002cd33  push    0FFFFE0BDh; int
0x1002cd38  push    0; void *
0x1002cd3a  lea     eax, [ebp+Src]
0x1002cd40  push    eax; void *
0x1002cd41  push    0; Src
0x1002cd43  push    esi; int
0x1002cd44  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002cd49  test    edi, edi
0x1002cd4b  js      loc_1002CBD2
0x1002cd51  cmp     ebx, 1
0x1002cd54  jz      short loc_1002CD65
0x1002cd56  cmp     ebx, 2
  ... truncated ...
```
