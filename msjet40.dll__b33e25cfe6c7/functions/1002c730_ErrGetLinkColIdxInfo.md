# ErrGetLinkColIdxInfo

- ea: `0x1002c730`
- end: `0x1002cc9a`
- name: `ErrGetLinkColIdxInfo`
- size: `1386`
- prototype: `int __thiscall(int, int, int, int, int, int, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x100133c0`
- `0x10015d10`
- `0x1002b760`
- `0x1002e5b0`

## callees

- `0x1002a600`
- `0x1002a670`
- `0x1002c5f0`
- `0x1002c730`
- `0x1003a6c0`
- `0x1003e7a0`
- `0x1003e820`
- `0x1003e870`
- `0x100429d0`
- `0x10042dc0`
- `0x10042f40`
- `0x10043260`
- `0x10043840`
- `0x100440c0`
- `0x100448f0`
- `0x10045100`
- `0x10045320`
- `0x10122f60`
- `0x10122f80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002cbfa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002cbfa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002cbc2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002cbc2`

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
  unsigned int v16; // eax
  int v17; // eax
  int ObjidFromName; // eax
  char *v19; // eax
  int v20; // ecx
  int IndexInfo; // eax
  int ColumnInfo; // eax
  _DWORD *v23; // edi
  _DWORD *v24; // eax
  void *v25; // ebx
  char *v26; // eax
  int v27; // ecx
  int v28; // ecx
  int v29; // [esp-14h] [ebp-57Ch]
  int v30; // [esp-4h] [ebp-56Ch]
  _DWORD v31[4]; // [esp+10h] [ebp-558h] BYREF
  __int64 v32; // [esp+20h] [ebp-548h]
  int v33; // [esp+2Ch] [ebp-53Ch] BYREF
  char *v34; // [esp+30h] [ebp-538h]
  int v35; // [esp+34h] [ebp-534h]
  int v36; // [esp+38h] [ebp-530h]
  _WORD *i; // [esp+3Ch] [ebp-52Ch] BYREF
  int v38; // [esp+40h] [ebp-528h]
  int v39; // [esp+44h] [ebp-524h] BYREF
  int v40; // [esp+48h] [ebp-520h] BYREF
  int v41; // [esp+4Ch] [ebp-51Ch] BYREF
  char v42[4]; // [esp+50h] [ebp-518h] BYREF
  int v43; // [esp+54h] [ebp-514h]
  _WORD v44[304]; // [esp+68h] [ebp-500h] BYREF
  _WORD v45[264]; // [esp+2C8h] [ebp-2A0h] BYREF
  unsigned __int16 Src[70]; // [esp+4D8h] [ebp-90h] BYREF

  v38 = a5;
  v35 = a4;
  v9 = isibHead;
  v39 = -1;
  v40 = -1;
  for ( i = 0; v9 != -1; v9 = dword_1016EAE8[26 * v9] )
  {
    if ( rgsib[26 * v9] == a1 )
      break;
  }
  if ( v9 >= 0 )
  {
    _mm_lfence();
    v11 = dword_1016EAA4[26 * v9];
  }
  else
  {
    v11 = -1;
  }
  v12 = (char *)rgtib + 2316 * v11;
  v34 = v12;
  result = ErrGetObjInfoId(6, a3, &v39, 0);
  if ( result >= 0 )
  {
    v14 = *((_QWORD *)v12 + 283);
    v36 = *((_DWORD *)v12 + 568);
    v29 = v39;
    *((_DWORD *)v12 + 566) = a1;
    *((_DWORD *)v12 + 567) = a2;
    v32 = v14;
    v41 = 522;
    TableColumnInfo = ErrDispGetTableColumnInfo(a1, v29, L"Database", v42, 24, 0);
    if ( TableColumnInfo >= 0 )
    {
      TableColumnInfo = ErrDispRetrieveColumn(a1, v39, v43, v45, v41, &v41, 0, 0);
      if ( TableColumnInfo >= 0 )
      {
        v16 = v41 & 0xFFFFFFFE;
        if ( (v41 & 0xFFFFFFFE) >= 0x20A )
          goto LABEL_59;
        v41 = 604;
        *(_WORD *)((char *)v45 + v16) = 0;
        TableColumnInfo = ErrDispGetTableColumnInfo(a1, v39, L"Connect", v42, 24, 0);
        if ( TableColumnInfo >= 0 )
        {
          v17 = ErrDispRetrieveColumn(a1, v39, v43, v44, v41, &v41, 0, 0);
          TableColumnInfo = v17;
          if ( v17 >= 0 )
          {
            if ( v17 != 1004 )
            {
              if ( (v41 & 0xFFFFFFFE) >= 0x25C )
                goto LABEL_59;
              *(_WORD *)((char *)v44 + (v41 & 0xFFFFFFFE)) = 0;
              i = v44;
            }
            v41 = 130;
            TableColumnInfo = ErrGetSysField(L"ForeignName", Src, &v41);
            if ( TableColumnInfo >= 0 )
            {
              if ( (v41 & 0xFFFFFFFE) < 0x82 )
              {
                v30 = v39;
                *(unsigned __int16 *)((char *)Src + (v41 & 0xFFFFFFFE)) = 0;
                ErrDispCloseTable(a1, v30);
                TableColumnInfo = ErrTryOpenDatabase(a1, v45, i, &v40, 0, 0);
                if ( TableColumnInfo >= 0 )
                {
                  if ( IsJetIsam(a1, v40) )
                  {
                    ObjidFromName = ErrDispGetObjidFromName(a1, v40, L"Tables", Src, &v33);
                    TableColumnInfo = ObjidFromName;
                    if ( ObjidFromName == -1305 )
                    {
                      ClearErrorInfo(a1);
                      UtilSetErrorInfoReal(a1, 0, Src, 0, -8003, 0, 0, 0);
LABEL_22:
                      ErrDispCloseDatabase(a1, v40, 0);
                      v19 = v34;
                      v20 = v36;
                      *((_QWORD *)v34 + 283) = v32;
                      *((_DWORD *)v19 + 568) = v20;
                      return TableColumnInfo;
                    }
                    if ( ObjidFromName < 0 )
                      goto LABEL_22;
                    TableColumnInfo = ErrSecGetAccess(a1, v40, v33, 0, 0, 0, &i, 0);
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
                  v31[3] = v38;
                  v31[0] = a6;
                  if ( a8 )
                  {
                    IndexInfo = ErrDispGetIndexInfo(a1, v40, Src, v35, v31, a7);
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
                    ColumnInfo = ErrDispGetColumnInfo(a1, v40, Src, v35, v31, a7);
                    TableColumnInfo = ColumnInfo;
                    if ( ColumnInfo == -1034 || ColumnInfo == -1035 || ColumnInfo == -1052 )
                      UtilSetErrorInfoReal(a1, 0, Src, 0, -8003, 0, 0, 0);
                    if ( TableColumnInfo < 0 )
                      goto LABEL_22;
                    if ( a7 != 1 && a7 != 2 && a7 != 8 && a7 != 7 )
                    {
LABEL_38:
                      ErrDispCloseDatabase(a1, v40, 0);
                      goto LABEL_54;
                    }
                  }
                  v23 = (_DWORD *)(v38 + 4);
                  if ( v38 != -4 )
                  {
                    v24 = _malloc(8u);
                    v25 = v24;
                    if ( !v24 )
                    {
                      TableColumnInfo = -1011;
                      goto LABEL_22;
                    }
                    *v24 = v40;
                    v24[1] = *v23;
                    TableColumnInfo = ErrAllocateTableid(0);
                    if ( TableColumnInfo < 0 )
                    {
                      _free(v25);
                      goto LABEL_22;
                    }
                    ErrUpdateTableid(*(_DWORD *)(v38 + 4), v25, &vtfndefLinfoDisp);
                  }
LABEL_54:
                  v26 = v34;
                  v27 = v36;
                  *((_QWORD *)v34 + 283) = v32;
                  *((_DWORD *)v26 + 568) = v27;
                  return 0;
                }
LABEL_56:
                v28 = v36;
                *((_QWORD *)v12 + 283) = v32;
                *((_DWORD *)v12 + 568) = v28;
                return TableColumnInfo;
              }
LABEL_59:
              __report_rangecheckfailure();
            }
          }
        }
      }
    }
    ErrDispCloseTable(a1, v39);
    goto LABEL_56;
  }
  return result;
}

```

## disassembly

```asm
0x1002c730  mov     edi, edi
0x1002c732  push    ebp
0x1002c733  mov     ebp, esp
0x1002c735  sub     esp, 55Ch
0x1002c73b  mov     eax, ___security_cookie
0x1002c740  xor     eax, ebp
0x1002c742  mov     [ebp+var_4], eax
0x1002c745  mov     eax, [ebp+arg_8]
0x1002c748  push    ebx
0x1002c749  mov     [ebp+var_528], eax
0x1002c74f  mov     eax, [ebp+arg_4]
0x1002c752  push    esi
0x1002c753  mov     [ebp+var_534], eax
0x1002c759  mov     esi, ecx
0x1002c75b  mov     eax, _isibHead
0x1002c760  mov     [ebp+var_524], 0FFFFFFFFh
0x1002c76a  mov     [ebp+var_520], 0FFFFFFFFh
0x1002c774  mov     [ebp+var_52C], 0
0x1002c77e  push    edi
0x1002c77f  mov     edi, edx
0x1002c781  mov     edx, [ebp+arg_0]
0x1002c784  cmp     eax, 0FFFFFFFFh
0x1002c787  jz      short loc_1002C7A6
0x1002c789  nop     dword ptr [eax+00000000h]
0x1002c790  imul    ecx, eax, 68h ; 'h'
0x1002c793  cmp     _rgsib[ecx], esi
0x1002c799  jz      short loc_1002C7A6
0x1002c79b  mov     eax, dword_1016EAE8[ecx]
0x1002c7a1  cmp     eax, 0FFFFFFFFh
0x1002c7a4  jnz     short loc_1002C790
0x1002c7a6  test    eax, eax
0x1002c7a8  jns     short loc_1002C7AF
0x1002c7aa  or      eax, 0FFFFFFFFh
0x1002c7ad  jmp     short loc_1002C7BB
0x1002c7af  imul    eax, 68h ; 'h'
0x1002c7b2  lfence
0x1002c7b5  mov     eax, dword_1016EAA4[eax]
0x1002c7bb  imul    ebx, eax, 90Ch
0x1002c7c1  mov     ecx, esi
0x1002c7c3  push    0
0x1002c7c5  lea     eax, [ebp+var_524]
0x1002c7cb  push    eax
0x1002c7cc  push    edx
0x1002c7cd  add     ebx, _rgtib
0x1002c7d3  mov     edx, edi
0x1002c7d5  push    6
0x1002c7d7  mov     [ebp+var_538], ebx
0x1002c7dd  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x1002c7e2  test    eax, eax
0x1002c7e4  js      loc_1002CC82
0x1002c7ea  mov     eax, [ebx+8E0h]
0x1002c7f0  movq    xmm0, qword ptr [ebx+8D8h]
0x1002c7f8  push    0
0x1002c7fa  push    18h
0x1002c7fc  mov     [ebp+var_530], eax
0x1002c802  lea     eax, [ebp+var_518]
0x1002c808  push    eax
0x1002c809  push    offset _wszSoDatabaseColumn; "Database"
0x1002c80e  push    [ebp+var_524]
0x1002c814  mov     [ebx+8D8h], esi
0x1002c81a  mov     [ebx+8DCh], edi
0x1002c820  push    esi
0x1002c821  movq    [ebp+var_548], xmm0
0x1002c829  mov     [ebp+var_51C], 20Ah
0x1002c833  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002c838  mov     edi, eax
0x1002c83a  test    edi, edi
0x1002c83c  js      loc_1002CC58
0x1002c842  push    0
0x1002c844  push    0
0x1002c846  lea     eax, [ebp+var_51C]
0x1002c84c  push    eax
0x1002c84d  push    [ebp+var_51C]
0x1002c853  lea     eax, [ebp+var_2A0]
0x1002c859  push    eax
0x1002c85a  push    [ebp+var_514]
0x1002c860  push    [ebp+var_524]
0x1002c866  push    esi
0x1002c867  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002c86c  mov     edi, eax
0x1002c86e  test    edi, edi
0x1002c870  js      loc_1002CC58
0x1002c876  mov     eax, [ebp+var_51C]
0x1002c87c  and     eax, 0FFFFFFFEh
0x1002c87f  cmp     eax, 20Ah
0x1002c884  jnb     loc_1002CC95
0x1002c88a  xor     ecx, ecx
0x1002c88c  mov     [ebp+var_51C], 25Ch
0x1002c896  push    ecx
0x1002c897  push    18h
0x1002c899  mov     [ebp+eax+var_2A0], cx
0x1002c8a1  lea     eax, [ebp+var_518]
0x1002c8a7  push    eax
0x1002c8a8  push    offset _wszSoConnectColumn; "Connect"
0x1002c8ad  push    [ebp+var_524]
0x1002c8b3  push    esi
0x1002c8b4  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002c8b9  mov     edi, eax
0x1002c8bb  test    edi, edi
0x1002c8bd  js      loc_1002CC58
0x1002c8c3  push    0
0x1002c8c5  push    0
0x1002c8c7  lea     eax, [ebp+var_51C]
0x1002c8cd  push    eax
0x1002c8ce  push    [ebp+var_51C]
0x1002c8d4  lea     eax, [ebp+var_500]
0x1002c8da  push    eax
0x1002c8db  push    [ebp+var_514]
0x1002c8e1  push    [ebp+var_524]
0x1002c8e7  push    esi
0x1002c8e8  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002c8ed  mov     edi, eax
0x1002c8ef  test    edi, edi
0x1002c8f1  js      loc_1002CC58
0x1002c8f7  cmp     edi, 3ECh
0x1002c8fd  jz      short loc_1002C929
0x1002c8ff  mov     eax, [ebp+var_51C]
0x1002c905  and     eax, 0FFFFFFFEh
0x1002c908  cmp     eax, 25Ch
0x1002c90d  jnb     loc_1002CC95
0x1002c913  xor     ecx, ecx
0x1002c915  mov     [ebp+eax+var_500], cx
0x1002c91d  lea     eax, [ebp+var_500]
0x1002c923  mov     [ebp+var_52C], eax
0x1002c929  mov     edx, [ebp+var_524]
0x1002c92f  lea     eax, [ebp+var_51C]
0x1002c935  push    eax
0x1002c936  lea     eax, [ebp+Src]
0x1002c93c  mov     [ebp+var_51C], 82h
0x1002c946  push    eax
0x1002c947  push    offset _wszSoForeignNameColumn; "ForeignName"
0x1002c94c  mov     ecx, esi
0x1002c94e  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x1002c953  mov     edi, eax
0x1002c955  test    edi, edi
0x1002c957  js      loc_1002CC58
0x1002c95d  mov     eax, [ebp+var_51C]
0x1002c963  and     eax, 0FFFFFFFEh
0x1002c966  cmp     eax, 82h
0x1002c96b  jnb     loc_1002CC95
0x1002c971  push    [ebp+var_524]
0x1002c977  xor     ecx, ecx
0x1002c979  push    esi
0x1002c97a  mov     [ebp+eax+Src], cx
0x1002c982  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1002c987  push    0
0x1002c989  push    0
0x1002c98b  lea     eax, [ebp+var_520]
0x1002c991  mov     ecx, esi
0x1002c993  push    eax
0x1002c994  push    [ebp+var_52C]
0x1002c99a  lea     edx, [ebp+var_2A0]
0x1002c9a0  call    _ErrTryOpenDatabase@24; ErrTryOpenDatabase(x,x,x,x,x,x)
0x1002c9a5  mov     edi, eax
0x1002c9a7  test    edi, edi
0x1002c9a9  js      loc_1002CC64
0x1002c9af  mov     edx, [ebp+var_520]
0x1002c9b5  mov     ecx, esi
0x1002c9b7  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1002c9bc  mov     ebx, [ebp+arg_10]
0x1002c9bf  test    eax, eax
0x1002c9c1  jz      loc_1002CAB8
0x1002c9c7  lea     eax, [ebp+var_53C]
0x1002c9cd  push    eax
0x1002c9ce  lea     eax, [ebp+Src]
0x1002c9d4  push    eax
0x1002c9d5  push    offset _wszTcObject; "Tables"
0x1002c9da  push    [ebp+var_520]
0x1002c9e0  push    esi
0x1002c9e1  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1002c9e6  mov     edi, eax
0x1002c9e8  cmp     edi, 0FFFFFAE7h
0x1002c9ee  jnz     short loc_1002CA47
0x1002c9f0  push    esi
0x1002c9f1  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1002c9f6  push    0; int
0x1002c9f8  push    0; int
0x1002c9fa  push    0; int
0x1002c9fc  push    0FFFFE0BDh; int
0x1002ca01  push    0; void *
0x1002ca03  lea     eax, [ebp+Src]
0x1002ca09  push    eax; void *
0x1002ca0a  push    0; Src
0x1002ca0c  push    esi; int
0x1002ca0d  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002ca12  push    0
0x1002ca14  push    [ebp+var_520]
0x1002ca1a  push    esi
0x1002ca1b  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1002ca20  mov     eax, [ebp+var_538]
0x1002ca26  movq    xmm0, [ebp+var_548]
0x1002ca2e  mov     ecx, [ebp+var_530]
0x1002ca34  movq    qword ptr [eax+8D8h], xmm0
0x1002ca3c  mov     [eax+8E0h], ecx
0x1002ca42  jmp     loc_1002CC80
0x1002ca47  test    edi, edi
0x1002ca49  js      short loc_1002CA12
0x1002ca4b  push    0
0x1002ca4d  lea     eax, [ebp+var_52C]
0x1002ca53  push    eax
0x1002ca54  push    0
0x1002ca56  push    0
0x1002ca58  push    0
0x1002ca5a  push    [ebp+var_53C]
0x1002ca60  push    [ebp+var_520]
0x1002ca66  push    esi
0x1002ca67  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x1002ca6c  mov     edi, eax
0x1002ca6e  test    edi, edi
0x1002ca70  js      short loc_1002CA12
0x1002ca72  mov     eax, [ebp+var_52C]
0x1002ca78  test    al, 0FCh
0x1002ca7a  jnz     short loc_1002CAA2
0x1002ca7c  push    0; int
0x1002ca7e  push    0; int
0x1002ca80  push    0; int
0x1002ca82  push    0FFFFE04Ah; int
0x1002ca87  push    0; void *
0x1002ca89  push    0; void *
0x1002ca8b  lea     eax, [ebp+Src]
0x1002ca91  push    eax; Src
0x1002ca92  push    esi; int
0x1002ca93  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002ca98  mov     edi, 0FFFFF88Dh
0x1002ca9d  jmp     loc_1002CA12
0x1002caa2  cmp     ebx, 3
0x1002caa5  jnz     short loc_1002CAB8
0x1002caa7  test    al, 8
0x1002caa9  jnz     short loc_1002CAB8
0x1002caab  push    0
0x1002caad  push    0
0x1002caaf  push    0
0x1002cab1  push    0FFFFE016h
0x1002cab6  jmp     short loc_1002CA87
0x1002cab8  cmp     [ebp+arg_14], 0
0x1002cabc  mov     eax, [ebp+var_528]
0x1002cac2  mov     [ebp+var_54C], eax
0x1002cac8  mov     eax, [ebp+arg_C]
0x1002cacb  push    ebx
0x1002cacc  mov     [ebp+var_558], eax
0x1002cad2  lea     eax, [ebp+var_558]
0x1002cad8  push    eax
0x1002cad9  push    [ebp+var_534]
0x1002cadf  lea     eax, [ebp+Src]
0x1002cae5  push    eax
0x1002cae6  push    [ebp+var_520]
0x1002caec  push    esi
0x1002caed  jz      short loc_1002CB4E
0x1002caef  call    _ErrDispGetIndexInfo@24; ErrDispGetIndexInfo(x,x,x,x,x,x)
0x1002caf4  mov     edi, eax
0x1002caf6  cmp     edi, 0FFFFFBF6h
0x1002cafc  jz      short loc_1002CB0E
0x1002cafe  cmp     edi, 0FFFFFBF5h
0x1002cb04  jz      short loc_1002CB0E
0x1002cb06  cmp     edi, 0FFFFFBE4h
0x1002cb0c  jnz     short loc_1002CB2A
0x1002cb0e  push    0; int
0x1002cb10  push    0; int
0x1002cb12  push    0; int
0x1002cb14  push    0FFFFE0BDh; int
0x1002cb19  push    0; void *
0x1002cb1b  lea     eax, [ebp+Src]
0x1002cb21  push    eax; void *
0x1002cb22  push    0; Src
0x1002cb24  push    esi; int
0x1002cb25  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002cb2a  test    edi, edi
0x1002cb2c  js      loc_1002CA12
0x1002cb32  test    ebx, ebx
0x1002cb34  jz      short loc_1002CBB1
0x1002cb36  cmp     ebx, 1
0x1002cb39  jz      short loc_1002CBB1
0x1002cb3b  push    0
0x1002cb3d  push    [ebp+var_520]
0x1002cb43  push    esi
0x1002cb44  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1002cb49  jmp     loc_1002CC21
0x1002cb4e  call    _ErrDispGetColumnInfo@24; ErrDispGetColumnInfo(x,x,x,x,x,x)
0x1002cb53  mov     edi, eax
0x1002cb55  cmp     edi, 0FFFFFBF6h
0x1002cb5b  jz      short loc_1002CB6D
0x1002cb5d  cmp     edi, 0FFFFFBF5h
0x1002cb63  jz      short loc_1002CB6D
0x1002cb65  cmp     edi, 0FFFFFBE4h
0x1002cb6b  jnz     short loc_1002CB89
0x1002cb6d  push    0; int
0x1002cb6f  push    0; int
0x1002cb71  push    0; int
0x1002cb73  push    0FFFFE0BDh; int
0x1002cb78  push    0; void *
0x1002cb7a  lea     eax, [ebp+Src]
0x1002cb80  push    eax; void *
0x1002cb81  push    0; Src
0x1002cb83  push    esi; int
0x1002cb84  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002cb89  test    edi, edi
0x1002cb8b  js      loc_1002CA12
0x1002cb91  cmp     ebx, 1
0x1002cb94  jz      short loc_1002CBA5
0x1002cb96  cmp     ebx, 2
  ... truncated ...
```
