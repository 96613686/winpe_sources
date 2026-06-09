# ErrSQLConnect(x,x,x,x,x,x,x,x)

- ea: `0x10097693`
- end: `0x10097a46`
- name: `_ErrSQLConnect@32`
- size: `947`
- prototype: `int __fastcall(wchar_t *, _DWORD *, int, int, unsigned int, int, int, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10097b97`
- `0x10097d74`
- `0x1009813a`

## callees

- `0x10050000`
- `0x10096ac8`
- `0x10096e85`
- `0x1009746a`
- `0x10097693`
- `0x100a4504`
- `0x100a6376`
- `0x10122f60`
- `0x10122f80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x100978f4`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097915`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097936`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x100979b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x100979d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x100978f4`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097915`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097936`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x100979b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x100979d8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097902`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097923`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097944`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x100979c5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x100979e6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097902`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097923`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097944`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x100979c5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x100979e6`

## string_xrefs

- `0x100978fa`: `odbcjt16.dll`
- `0x1009791b`: `odbcjt32.dll`
- `0x1009793c`: `simba.dll`

## pseudocode

```c
int __fastcall ErrSQLConnect(wchar_t *a1, _DWORD *a2, int a3, int a4, unsigned int a5, int a6, int a7, int a8)
{
  int result; // eax
  int v10; // eax
  int v11; // edi
  _WORD *i; // ecx
  unsigned int v13; // eax
  const wchar_t *v14; // eax
  const wchar_t *v15; // eax
  const wchar_t *v16; // eax
  unsigned int v17; // eax
  const wchar_t *v18; // eax
  const wchar_t *v19; // eax
  unsigned int v20; // eax
  wchar_t *SubStr; // [esp+6Ch] [ebp-FCh]
  wchar_t *SubStra; // [esp+6Ch] [ebp-FCh]
  wchar_t *SubStrb; // [esp+6Ch] [ebp-FCh]
  char v24; // [esp+70h] [ebp-F8h]
  char v25; // [esp+70h] [ebp-F8h]
  char v26; // [esp+70h] [ebp-F8h]
  __int16 v27; // [esp+74h] [ebp-F4h]
  __int16 v28; // [esp+74h] [ebp-F4h]
  __int16 v29; // [esp+74h] [ebp-F4h]
  int v30; // [esp+78h] [ebp-F0h]
  int v31; // [esp+78h] [ebp-F0h]
  int v32; // [esp+78h] [ebp-F0h]
  _DWORD *v33; // [esp+7Ch] [ebp-ECh]
  long double v34; // [esp+80h] [ebp-E8h] BYREF
  wchar_t *v35; // [esp+88h] [ebp-E0h]
  unsigned __int16 v36; // [esp+8Ch] [ebp-DCh] BYREF
  void *v37; // [esp+90h] [ebp-D8h] BYREF
  __int16 v38; // [esp+94h] [ebp-D4h] BYREF
  _WORD v39[102]; // [esp+98h] [ebp-D0h] BYREF

  v33 = a2;
  HIDWORD(v34) = a3;
  *a2 = 0;
  v36 = 0;
  v35 = a1;
  LODWORD(v34) = a4;
  if ( FShareConnection(a5, a6, a2, a8) )
    return 0;
  result = ErrSQLAllocConnect(a1, &v37);
  if ( result >= 0 )
  {
    pfnSQLSetConnectAttr(pfnSQLSetConnectAttr, v37, 30002, L"Microsoft Jet", -3);
    ErrSQLCheckError(0, a1);
    pfnSQLDriverConnect(pfnSQLDriverConnect, v37, HIDWORD(v34), LODWORD(v34), -3, a5, a6, &v36, a7);
    v10 = ErrSQLCheckError(0, a1);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( v10 == -1603 )
      {
        v11 = -1057;
      }
      else if ( v10 == -2025 )
      {
        v11 = -2001;
      }
      goto LABEL_19;
    }
    if ( v36 > 0x1FAu )
    {
      for ( i = (_WORD *)(a5 + 1012); (unsigned int)(i - 1) >= a5 && *(i - 1) != 59; --i )
        ;
      *i = 0;
    }
    SubStr = v35;
    pfnSQLGetInfo(pfnSQLGetInfo, v37, 9, (char *)&v34 + 4, 2, &v38);
    v11 = ErrSQLCheckError(0, SubStr);
    if ( v11 < 0 )
    {
LABEL_18:
      pfnSQLDisconnect(pfnSQLDisconnect, v37);
LABEL_19:
      pfnSQLFreeConnect(pfnSQLFreeConnect, v37);
      return v11;
    }
    if ( v38 != 2 )
    {
      v11 = -7701;
      goto LABEL_18;
    }
    if ( SWORD2(v34) < 1 )
    {
      v11 = -7702;
      goto LABEL_18;
    }
    if ( !*(_DWORD *)&wODBCISAMAttach )
    {
      SubStra = v35;
      pfnSQLGetInfo(pfnSQLGetInfo, v37, 6, v39, 200, &v38);
      if ( (int)ErrSQLCheckError(0, SubStra) >= 0 )
      {
        v13 = v38 & 0xFFFFFFFE;
        if ( v13 >= 0xC8 )
          goto LABEL_38;
        *(_WORD *)((char *)v39 + v13) = 0;
        v14 = (const wchar_t *)__o((wchar_t)v39, v24, v27, v30, (wchar_t)v33, v34);
        if ( !_wcsstr(v14, L"odbcjt16.dll") )
        {
          v15 = (const wchar_t *)__o((wchar_t)v39, v25, v28, v31, (wchar_t)v33, v34);
          if ( !_wcsstr(v15, L"odbcjt32.dll") )
          {
            v16 = (const wchar_t *)__o((wchar_t)v39, v25, v28, v31, (wchar_t)v33, v34);
            if ( !_wcsstr(v16, L"simba.dll") )
              goto LABEL_34;
          }
        }
        SubStrb = v35;
        pfnSQLGetInfo(pfnSQLGetInfo, v37, 17, v39, 200, &v38);
        if ( (int)ErrSQLCheckError(0, SubStrb) < 0 )
          goto LABEL_34;
        v17 = v38 & 0xFFFFFFFE;
        if ( v17 >= 0xC8 )
LABEL_38:
          __report_rangecheckfailure();
        *(_WORD *)((char *)v39 + v17) = 0;
        v18 = (const wchar_t *)__o((wchar_t)v39, v25, v28, v31, (wchar_t)v33, v34);
        if ( !_wcsstr(v18, L"excel") )
        {
          v19 = (const wchar_t *)__o((wchar_t)v39, v26, v29, v32, (wchar_t)v33, v34);
          if ( !_wcsstr(v19, L"text") )
          {
            v11 = -2034;
            goto LABEL_18;
          }
        }
      }
    }
LABEL_34:
    v20 = LODWORD(v34);
    if ( a5 )
      v20 = a5;
    v11 = ErrRmtRegisterConn(v20, a8);
    if ( v11 >= 0 )
    {
      *v33 = PconnOfHdbc(v37) + 24;
      return 0;
    }
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x10097693  mov     edi, edi
0x10097695  push    ebp
0x10097696  mov     ebp, esp
0x10097698  sub     esp, 0ECh
0x1009769e  mov     eax, ___security_cookie
0x100976a3  xor     eax, ebp
0x100976a5  mov     [ebp+var_4], eax
0x100976a8  mov     eax, [ebp+arg_4]
0x100976ab  push    ebx
0x100976ac  mov     ebx, [ebp+arg_8]
0x100976af  push    esi
0x100976b0  push    edi
0x100976b1  push    [ebp+arg_14]
0x100976b4  mov     edi, ecx
0x100976b6  mov     [ebp+var_EC], edx
0x100976bc  mov     ecx, [ebp+arg_0]
0x100976bf  push    edx
0x100976c0  push    [ebp+arg_C]
0x100976c3  mov     [ebp+var_E4], ecx
0x100976c9  xor     ecx, ecx
0x100976cb  mov     [edx], ecx
0x100976cd  mov     edx, eax
0x100976cf  mov     [ebp+var_DC], cx
0x100976d6  mov     ecx, edi
0x100976d8  push    ebx
0x100976d9  mov     [ebp+var_E0], edi
0x100976df  mov     [ebp+var_E8], eax
0x100976e5  call    FShareConnection
0x100976ea  test    eax, eax
0x100976ec  jz      short loc_100976F5
0x100976ee  xor     eax, eax
0x100976f0  jmp     loc_10097858
0x100976f5  lea     edx, [ebp+var_D8]
0x100976fb  mov     ecx, edi
0x100976fd  call    _ErrSQLAllocConnect@8; ErrSQLAllocConnect(x,x)
0x10097702  test    eax, eax
0x10097704  js      loc_10097858
0x1009770a  mov     esi, _pfnSQLSetConnectAttr
0x10097710  mov     ecx, esi
0x10097712  push    edi
0x10097713  push    0
0x10097715  push    0FFFFFFFDh
0x10097717  push    offset aMicrosoftJet; "Microsoft Jet"
0x1009771c  push    7532h; unsigned int
0x10097721  push    [ebp+var_D8]; void *
0x10097727  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1009772d  call    esi ; _pfnSQLSetConnectAttr
0x1009772f  mov     edx, [ebp+var_D8]
0x10097735  mov     ecx, eax
0x10097737  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x1009773c  mov     esi, _pfnSQLDriverConnect
0x10097742  lea     eax, [ebp+var_DC]
0x10097748  push    edi
0x10097749  push    0
0x1009774b  push    [ebp+arg_10]
0x1009774e  mov     ecx, esi
0x10097750  push    eax
0x10097751  push    [ebp+arg_C]
0x10097754  push    ebx
0x10097755  push    0FFFFFFFDh
0x10097757  push    [ebp+var_E8]
0x1009775d  push    [ebp+var_E4]; unsigned int
0x10097763  push    [ebp+var_D8]; void *
0x10097769  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1009776f  call    esi ; _pfnSQLDriverConnect
0x10097771  mov     edx, [ebp+var_D8]
0x10097777  mov     ecx, eax
0x10097779  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x1009777e  mov     edi, eax
0x10097780  test    edi, edi
0x10097782  jns     short loc_100977AA
0x10097784  cmp     edi, 0FFFFF9BDh
0x1009778a  jnz     short loc_10097796
0x1009778c  mov     edi, 0FFFFFBDFh
0x10097791  jmp     loc_10097840
0x10097796  cmp     edi, 0FFFFF817h
0x1009779c  jnz     loc_10097840
0x100977a2  add     edi, 18h
0x100977a5  jmp     loc_10097840
0x100977aa  movsx   eax, [ebp+var_DC]
0x100977b1  mov     ecx, 1FAh
0x100977b6  cmp     ax, cx
0x100977b9  jbe     short loc_100977D9
0x100977bb  lea     ecx, [ebx+3F4h]
0x100977c1  jmp     short loc_100977CD
0x100977c3  cmp     word ptr [ecx-2], 3Bh ; ';'
0x100977c8  jz      short loc_100977D4
0x100977ca  add     ecx, 0FFFFFFFEh
0x100977cd  lea     eax, [ecx-2]
0x100977d0  cmp     eax, ebx
0x100977d2  jnb     short loc_100977C3
0x100977d4  xor     eax, eax
0x100977d6  mov     [ecx], ax
0x100977d9  push    [ebp+var_E0]
0x100977df  mov     edi, [ebp+var_D8]
0x100977e5  lea     eax, [ebp+var_D4]
0x100977eb  mov     esi, _pfnSQLGetInfo
0x100977f1  mov     ecx, esi
0x100977f3  push    0
0x100977f5  push    eax
0x100977f6  push    2
0x100977f8  lea     eax, [ebp+var_E4]
0x100977fe  push    eax
0x100977ff  push    9; unsigned int
0x10097801  push    edi; void *
0x10097802  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10097808  call    esi ; _pfnSQLGetInfo
0x1009780a  mov     edx, edi
0x1009780c  mov     ecx, eax
0x1009780e  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x10097813  mov     edi, eax
0x10097815  test    edi, edi
0x10097817  js      short loc_1009782A
0x10097819  push    2
0x1009781b  pop     eax
0x1009781c  cmp     [ebp+var_D4], ax
0x10097823  jz      short loc_10097869
0x10097825  mov     edi, 0FFFFE1EBh
0x1009782a  push    [ebp+var_D8]; void *
0x10097830  mov     esi, _pfnSQLDisconnect
0x10097836  mov     ecx, esi
0x10097838  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1009783e  call    esi ; _pfnSQLDisconnect
0x10097840  push    [ebp+var_D8]; void *
0x10097846  mov     esi, _pfnSQLFreeConnect
0x1009784c  mov     ecx, esi
0x1009784e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10097854  call    esi ; _pfnSQLFreeConnect
0x10097856  mov     eax, edi
0x10097858  mov     ecx, [ebp+var_4]
0x1009785b  pop     edi
0x1009785c  pop     esi
0x1009785d  xor     ecx, ebp; StackCookie
0x1009785f  pop     ebx
0x10097860  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10097865  leave
0x10097866  retn    18h
0x10097869  cmp     word ptr [ebp+var_E4], 1
0x10097871  jge     short loc_1009787A
0x10097873  mov     edi, 0FFFFE1EAh
0x10097878  jmp     short loc_1009782A
0x1009787a  cmp     _wODBCISAMAttach, 0
0x10097881  jnz     loc_100979FC
0x10097887  push    [ebp+var_E0]
0x1009788d  mov     edi, [ebp+var_D8]
0x10097893  lea     eax, [ebp+var_D4]
0x10097899  mov     esi, _pfnSQLGetInfo
0x1009789f  mov     ecx, esi
0x100978a1  push    0
0x100978a3  push    eax
0x100978a4  push    0C8h
0x100978a9  lea     eax, [ebp+var_D0]
0x100978af  push    eax
0x100978b0  push    6; unsigned int
0x100978b2  push    edi; void *
0x100978b3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100978b9  call    esi ; _pfnSQLGetInfo
0x100978bb  mov     edx, edi
0x100978bd  mov     ecx, eax
0x100978bf  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x100978c4  test    eax, eax
0x100978c6  js      loc_100979FC
0x100978cc  movsx   eax, [ebp+var_D4]
0x100978d3  mov     esi, 0C8h
0x100978d8  and     eax, 0FFFFFFFEh
0x100978db  cmp     eax, esi
0x100978dd  jnb     loc_10097A41
0x100978e3  xor     ecx, ecx
0x100978e5  mov     [ebp+eax+var_D0], cx
0x100978ed  lea     eax, [ebp+var_D0]
0x100978f3  push    eax
0x100978f4  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x100978fa  mov     [esp+0FCh+SubStr], offset aOdbcjt16Dll; "odbcjt16.dll"
0x10097901  push    eax; Str
0x10097902  call    ds:__imp__wcsstr
0x10097908  pop     ecx
0x10097909  pop     ecx
0x1009790a  test    eax, eax
0x1009790c  jnz     short loc_10097954
0x1009790e  lea     eax, [ebp+var_D0]
0x10097914  push    eax
0x10097915  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x1009791b  mov     [esp+0FCh+SubStr], offset aOdbcjt32Dll; "odbcjt32.dll"
0x10097922  push    eax; Str
0x10097923  call    ds:__imp__wcsstr
0x10097929  pop     ecx
0x1009792a  pop     ecx
0x1009792b  test    eax, eax
0x1009792d  jnz     short loc_10097954
0x1009792f  lea     eax, [ebp+var_D0]
0x10097935  push    eax
0x10097936  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x1009793c  mov     [esp+0FCh+SubStr], offset aSimbaDll; "simba.dll"
0x10097943  push    eax; Str
0x10097944  call    ds:__imp__wcsstr
0x1009794a  pop     ecx
0x1009794b  pop     ecx
0x1009794c  test    eax, eax
0x1009794e  jz      loc_100979FC
0x10097954  push    [ebp+var_E0]
0x1009795a  mov     edi, [ebp+var_D8]
0x10097960  lea     eax, [ebp+var_D4]
0x10097966  push    0
0x10097968  push    eax
0x10097969  push    esi
0x1009796a  mov     esi, _pfnSQLGetInfo
0x10097970  lea     eax, [ebp+var_D0]
0x10097976  push    eax
0x10097977  push    11h; unsigned int
0x10097979  push    edi; void *
0x1009797a  mov     ecx, esi
0x1009797c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10097982  call    esi ; _pfnSQLGetInfo
0x10097984  mov     edx, edi
0x10097986  mov     ecx, eax
0x10097988  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x1009798d  test    eax, eax
0x1009798f  js      short loc_100979FC
0x10097991  movsx   eax, [ebp+var_D4]
0x10097998  and     eax, 0FFFFFFFEh
0x1009799b  cmp     eax, 0C8h
0x100979a0  jnb     loc_10097A41
0x100979a6  xor     ecx, ecx
0x100979a8  mov     [ebp+eax+var_D0], cx
0x100979b0  lea     eax, [ebp+var_D0]
0x100979b6  push    eax
0x100979b7  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x100979bd  mov     [esp+0FCh+SubStr], offset aExcel; "excel"
0x100979c4  push    eax; Str
0x100979c5  call    ds:__imp__wcsstr
0x100979cb  pop     ecx
0x100979cc  pop     ecx
0x100979cd  test    eax, eax
0x100979cf  jnz     short loc_100979FC
0x100979d1  lea     eax, [ebp+var_D0]
0x100979d7  push    eax
0x100979d8  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x100979de  mov     [esp+0FCh+SubStr], offset aText; "text"
0x100979e5  push    eax; Str
0x100979e6  call    ds:__imp__wcsstr
0x100979ec  pop     ecx
0x100979ed  pop     ecx
0x100979ee  test    eax, eax
0x100979f0  jnz     short loc_100979FC
0x100979f2  mov     edi, 0FFFFF80Eh
0x100979f7  jmp     loc_1009782A
0x100979fc  push    [ebp+arg_14]
0x100979ff  mov     eax, [ebp+var_E8]
0x10097a05  test    ebx, ebx
0x10097a07  mov     edx, [ebp+var_D8]
0x10097a0d  mov     ecx, [ebp+var_E0]
0x10097a13  cmovnz  eax, ebx
0x10097a16  push    eax
0x10097a17  call    ErrRmtRegisterConn
0x10097a1c  mov     edi, eax
0x10097a1e  test    edi, edi
0x10097a20  js      loc_1009782A
0x10097a26  mov     ecx, [ebp+var_D8]
0x10097a2c  call    PconnOfHdbc
0x10097a31  mov     ecx, [ebp+var_EC]
0x10097a37  add     eax, 18h
0x10097a3a  mov     [ecx], eax
0x10097a3c  jmp     loc_100976EE
0x10097a41  call    ___report_rangecheckfailure
```
