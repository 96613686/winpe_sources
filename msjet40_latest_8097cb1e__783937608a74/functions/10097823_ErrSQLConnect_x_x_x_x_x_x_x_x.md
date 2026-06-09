# ErrSQLConnect(x,x,x,x,x,x,x,x)

- ea: `0x10097823`
- end: `0x10097bd6`
- name: `_ErrSQLConnect@32`
- size: `947`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10097d27`
- `0x10097f04`
- `0x100982ca`

## callees

- `0x10050190`
- `0x10096c58`
- `0x10097015`
- `0x100975fa`
- `0x10097823`
- `0x100a4694`
- `0x100a6506`
- `0x10123110`
- `0x10123130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097a84`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097aa5`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097ac6`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097b47`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097b68`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097a84`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097aa5`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097ac6`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097b47`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x10097b68`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097a92`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097ab3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097ad4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097b55`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097b76`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097a92`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097ab3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097ad4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097b55`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x10097b76`

## string_xrefs

- `0x10097a8a`: `odbcjt16.dll`
- `0x10097aab`: `odbcjt32.dll`
- `0x10097acc`: `simba.dll`

## pseudocode

```c
int __fastcall ErrSQLConnect(wchar_t *a1, _DWORD *a2, int a3, int a4, unsigned int a5, int a6, int a7, int a8)
{
  int result; // eax
  int v10; // eax
  int v11; // edi
  _WORD *i; // ecx
  int v13; // ecx
  unsigned int v14; // eax
  const wchar_t *v15; // eax
  const wchar_t *v16; // eax
  const wchar_t *v17; // eax
  unsigned int v18; // eax
  const wchar_t *v19; // eax
  const wchar_t *v20; // eax
  unsigned int v21; // eax
  wchar_t *SubStr; // [esp+6Ch] [ebp-FCh]
  wchar_t *SubStra; // [esp+6Ch] [ebp-FCh]
  wchar_t *SubStrb; // [esp+6Ch] [ebp-FCh]
  char v25; // [esp+70h] [ebp-F8h]
  char v26; // [esp+70h] [ebp-F8h]
  char v27; // [esp+70h] [ebp-F8h]
  __int16 v28; // [esp+74h] [ebp-F4h]
  __int16 v29; // [esp+74h] [ebp-F4h]
  __int16 v30; // [esp+74h] [ebp-F4h]
  int v31; // [esp+78h] [ebp-F0h]
  int v32; // [esp+78h] [ebp-F0h]
  int v33; // [esp+78h] [ebp-F0h]
  _DWORD *v34; // [esp+7Ch] [ebp-ECh]
  long double v35; // [esp+80h] [ebp-E8h] BYREF
  wchar_t *v36; // [esp+88h] [ebp-E0h]
  unsigned __int16 v37; // [esp+8Ch] [ebp-DCh] BYREF
  void *v38; // [esp+90h] [ebp-D8h] BYREF
  __int16 v39; // [esp+94h] [ebp-D4h] BYREF
  _WORD v40[102]; // [esp+98h] [ebp-D0h] BYREF

  v34 = a2;
  HIDWORD(v35) = a3;
  *a2 = 0;
  v37 = 0;
  v36 = a1;
  LODWORD(v35) = a4;
  if ( FShareConnection(a5, a6, a2, a8) )
    return 0;
  result = ErrSQLAllocConnect(a1, &v38);
  if ( result >= 0 )
  {
    pfnSQLSetConnectAttr(pfnSQLSetConnectAttr, v38, 30002, L"Microsoft Jet", -3);
    ErrSQLCheckError(0, a1);
    pfnSQLDriverConnect(pfnSQLDriverConnect, v38, HIDWORD(v35), LODWORD(v35), -3, a5, a6, &v37, a7);
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
    if ( v37 > 0x1FAu )
    {
      for ( i = (_WORD *)(a5 + 1012); (unsigned int)(i - 1) >= a5 && *(i - 1) != 59; --i )
        ;
      *i = 0;
    }
    SubStr = v36;
    pfnSQLGetInfo(pfnSQLGetInfo, v38, 9, (char *)&v35 + 4, 2, &v39);
    v11 = ErrSQLCheckError(0, SubStr);
    if ( v11 < 0 )
    {
LABEL_18:
      pfnSQLDisconnect(pfnSQLDisconnect, v38);
LABEL_19:
      pfnSQLFreeConnect(pfnSQLFreeConnect, v38);
      return v11;
    }
    if ( v39 != 2 )
    {
      v11 = -7701;
      goto LABEL_18;
    }
    if ( SWORD2(v35) < 1 )
    {
      v11 = -7702;
      goto LABEL_18;
    }
    if ( !*(_DWORD *)&wODBCISAMAttach )
    {
      SubStra = v36;
      pfnSQLGetInfo(pfnSQLGetInfo, v38, 6, v40, 200, &v39);
      if ( (int)ErrSQLCheckError(0, SubStra) >= 0 )
      {
        v14 = v39 & 0xFFFFFFFE;
        if ( v14 >= 0xC8 )
          goto LABEL_38;
        *(_WORD *)((char *)v40 + v14) = 0;
        v15 = (const wchar_t *)__o((wchar_t)v40, v25, v28, v31, (wchar_t)v34, v35);
        if ( !_wcsstr(v15, L"odbcjt16.dll") )
        {
          v16 = (const wchar_t *)__o((wchar_t)v40, v26, v29, v32, (wchar_t)v34, v35);
          if ( !_wcsstr(v16, L"odbcjt32.dll") )
          {
            v17 = (const wchar_t *)__o((wchar_t)v40, v26, v29, v32, (wchar_t)v34, v35);
            if ( !_wcsstr(v17, L"simba.dll") )
              goto LABEL_34;
          }
        }
        SubStrb = v36;
        pfnSQLGetInfo(pfnSQLGetInfo, v38, 17, v40, 200, &v39);
        if ( (int)ErrSQLCheckError(0, SubStrb) < 0 )
          goto LABEL_34;
        v18 = v39 & 0xFFFFFFFE;
        if ( v18 >= 0xC8 )
LABEL_38:
          __report_rangecheckfailure(v13);
        *(_WORD *)((char *)v40 + v18) = 0;
        v19 = (const wchar_t *)__o((wchar_t)v40, v26, v29, v32, (wchar_t)v34, v35);
        if ( !_wcsstr(v19, L"excel") )
        {
          v20 = (const wchar_t *)__o((wchar_t)v40, v27, v30, v33, (wchar_t)v34, v35);
          if ( !_wcsstr(v20, L"text") )
          {
            v11 = -2034;
            goto LABEL_18;
          }
        }
      }
    }
LABEL_34:
    v21 = LODWORD(v35);
    if ( a5 )
      v21 = a5;
    v11 = ErrRmtRegisterConn(v21, a8);
    if ( v11 >= 0 )
    {
      *v34 = PconnOfHdbc(v38) + 24;
      return 0;
    }
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x10097823  mov     edi, edi
0x10097825  push    ebp
0x10097826  mov     ebp, esp
0x10097828  sub     esp, 0ECh
0x1009782e  mov     eax, ___security_cookie
0x10097833  xor     eax, ebp
0x10097835  mov     [ebp+var_4], eax
0x10097838  mov     eax, [ebp+arg_4]
0x1009783b  push    ebx
0x1009783c  mov     ebx, [ebp+arg_8]
0x1009783f  push    esi
0x10097840  push    edi
0x10097841  push    [ebp+arg_14]
0x10097844  mov     edi, ecx
0x10097846  mov     [ebp+var_EC], edx
0x1009784c  mov     ecx, [ebp+arg_0]
0x1009784f  push    edx
0x10097850  push    [ebp+arg_C]
0x10097853  mov     [ebp+var_E4], ecx
0x10097859  xor     ecx, ecx
0x1009785b  mov     [edx], ecx
0x1009785d  mov     edx, eax
0x1009785f  mov     [ebp+var_DC], cx
0x10097866  mov     ecx, edi
0x10097868  push    ebx
0x10097869  mov     [ebp+var_E0], edi
0x1009786f  mov     [ebp+var_E8], eax
0x10097875  call    FShareConnection
0x1009787a  test    eax, eax
0x1009787c  jz      short loc_10097885
0x1009787e  xor     eax, eax
0x10097880  jmp     loc_100979E8
0x10097885  lea     edx, [ebp+var_D8]
0x1009788b  mov     ecx, edi
0x1009788d  call    _ErrSQLAllocConnect@8; ErrSQLAllocConnect(x,x)
0x10097892  test    eax, eax
0x10097894  js      loc_100979E8
0x1009789a  mov     esi, _pfnSQLSetConnectAttr
0x100978a0  mov     ecx, esi
0x100978a2  push    edi
0x100978a3  push    0
0x100978a5  push    0FFFFFFFDh
0x100978a7  push    offset aMicrosoftJet; "Microsoft Jet"
0x100978ac  push    7532h; unsigned int
0x100978b1  push    [ebp+var_D8]; void *
0x100978b7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100978bd  call    esi ; _pfnSQLSetConnectAttr
0x100978bf  mov     edx, [ebp+var_D8]
0x100978c5  mov     ecx, eax
0x100978c7  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x100978cc  mov     esi, _pfnSQLDriverConnect
0x100978d2  lea     eax, [ebp+var_DC]
0x100978d8  push    edi
0x100978d9  push    0
0x100978db  push    [ebp+arg_10]
0x100978de  mov     ecx, esi
0x100978e0  push    eax
0x100978e1  push    [ebp+arg_C]
0x100978e4  push    ebx
0x100978e5  push    0FFFFFFFDh
0x100978e7  push    [ebp+var_E8]
0x100978ed  push    [ebp+var_E4]; unsigned int
0x100978f3  push    [ebp+var_D8]; void *
0x100978f9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100978ff  call    esi ; _pfnSQLDriverConnect
0x10097901  mov     edx, [ebp+var_D8]
0x10097907  mov     ecx, eax
0x10097909  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x1009790e  mov     edi, eax
0x10097910  test    edi, edi
0x10097912  jns     short loc_1009793A
0x10097914  cmp     edi, 0FFFFF9BDh
0x1009791a  jnz     short loc_10097926
0x1009791c  mov     edi, 0FFFFFBDFh
0x10097921  jmp     loc_100979D0
0x10097926  cmp     edi, 0FFFFF817h
0x1009792c  jnz     loc_100979D0
0x10097932  add     edi, 18h
0x10097935  jmp     loc_100979D0
0x1009793a  movsx   eax, [ebp+var_DC]
0x10097941  mov     ecx, 1FAh
0x10097946  cmp     ax, cx
0x10097949  jbe     short loc_10097969
0x1009794b  lea     ecx, [ebx+3F4h]
0x10097951  jmp     short loc_1009795D
0x10097953  cmp     word ptr [ecx-2], 3Bh ; ';'
0x10097958  jz      short loc_10097964
0x1009795a  add     ecx, 0FFFFFFFEh
0x1009795d  lea     eax, [ecx-2]
0x10097960  cmp     eax, ebx
0x10097962  jnb     short loc_10097953
0x10097964  xor     eax, eax
0x10097966  mov     [ecx], ax
0x10097969  push    [ebp+var_E0]
0x1009796f  mov     edi, [ebp+var_D8]
0x10097975  lea     eax, [ebp+var_D4]
0x1009797b  mov     esi, _pfnSQLGetInfo
0x10097981  mov     ecx, esi
0x10097983  push    0
0x10097985  push    eax
0x10097986  push    2
0x10097988  lea     eax, [ebp+var_E4]
0x1009798e  push    eax
0x1009798f  push    9; unsigned int
0x10097991  push    edi; void *
0x10097992  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10097998  call    esi ; _pfnSQLGetInfo
0x1009799a  mov     edx, edi
0x1009799c  mov     ecx, eax
0x1009799e  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x100979a3  mov     edi, eax
0x100979a5  test    edi, edi
0x100979a7  js      short loc_100979BA
0x100979a9  push    2
0x100979ab  pop     eax
0x100979ac  cmp     [ebp+var_D4], ax
0x100979b3  jz      short loc_100979F9
0x100979b5  mov     edi, 0FFFFE1EBh
0x100979ba  push    [ebp+var_D8]; void *
0x100979c0  mov     esi, _pfnSQLDisconnect
0x100979c6  mov     ecx, esi
0x100979c8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100979ce  call    esi ; _pfnSQLDisconnect
0x100979d0  push    [ebp+var_D8]; void *
0x100979d6  mov     esi, _pfnSQLFreeConnect
0x100979dc  mov     ecx, esi
0x100979de  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100979e4  call    esi ; _pfnSQLFreeConnect
0x100979e6  mov     eax, edi
0x100979e8  mov     ecx, [ebp+var_4]
0x100979eb  pop     edi
0x100979ec  pop     esi
0x100979ed  xor     ecx, ebp; StackCookie
0x100979ef  pop     ebx
0x100979f0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100979f5  leave
0x100979f6  retn    18h
0x100979f9  cmp     word ptr [ebp+var_E4], 1
0x10097a01  jge     short loc_10097A0A
0x10097a03  mov     edi, 0FFFFE1EAh
0x10097a08  jmp     short loc_100979BA
0x10097a0a  cmp     _wODBCISAMAttach, 0
0x10097a11  jnz     loc_10097B8C
0x10097a17  push    [ebp+var_E0]
0x10097a1d  mov     edi, [ebp+var_D8]
0x10097a23  lea     eax, [ebp+var_D4]
0x10097a29  mov     esi, _pfnSQLGetInfo
0x10097a2f  mov     ecx, esi
0x10097a31  push    0
0x10097a33  push    eax
0x10097a34  push    0C8h
0x10097a39  lea     eax, [ebp+var_D0]
0x10097a3f  push    eax
0x10097a40  push    6; unsigned int
0x10097a42  push    edi; void *
0x10097a43  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10097a49  call    esi ; _pfnSQLGetInfo
0x10097a4b  mov     edx, edi
0x10097a4d  mov     ecx, eax
0x10097a4f  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x10097a54  test    eax, eax
0x10097a56  js      loc_10097B8C
0x10097a5c  movsx   eax, [ebp+var_D4]
0x10097a63  mov     esi, 0C8h
0x10097a68  and     eax, 0FFFFFFFEh
0x10097a6b  cmp     eax, esi
0x10097a6d  jnb     loc_10097BD1
0x10097a73  xor     ecx, ecx
0x10097a75  mov     [ebp+eax+var_D0], cx
0x10097a7d  lea     eax, [ebp+var_D0]
0x10097a83  push    eax
0x10097a84  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x10097a8a  mov     [esp+0FCh+SubStr], offset aOdbcjt16Dll; "odbcjt16.dll"
0x10097a91  push    eax; Str
0x10097a92  call    ds:__imp__wcsstr
0x10097a98  pop     ecx
0x10097a99  pop     ecx
0x10097a9a  test    eax, eax
0x10097a9c  jnz     short loc_10097AE4
0x10097a9e  lea     eax, [ebp+var_D0]
0x10097aa4  push    eax
0x10097aa5  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x10097aab  mov     [esp+0FCh+SubStr], offset aOdbcjt32Dll; "odbcjt32.dll"
0x10097ab2  push    eax; Str
0x10097ab3  call    ds:__imp__wcsstr
0x10097ab9  pop     ecx
0x10097aba  pop     ecx
0x10097abb  test    eax, eax
0x10097abd  jnz     short loc_10097AE4
0x10097abf  lea     eax, [ebp+var_D0]
0x10097ac5  push    eax
0x10097ac6  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x10097acc  mov     [esp+0FCh+SubStr], offset aSimbaDll; "simba.dll"
0x10097ad3  push    eax; Str
0x10097ad4  call    ds:__imp__wcsstr
0x10097ada  pop     ecx
0x10097adb  pop     ecx
0x10097adc  test    eax, eax
0x10097ade  jz      loc_10097B8C
0x10097ae4  push    [ebp+var_E0]
0x10097aea  mov     edi, [ebp+var_D8]
0x10097af0  lea     eax, [ebp+var_D4]
0x10097af6  push    0
0x10097af8  push    eax
0x10097af9  push    esi
0x10097afa  mov     esi, _pfnSQLGetInfo
0x10097b00  lea     eax, [ebp+var_D0]
0x10097b06  push    eax
0x10097b07  push    11h; unsigned int
0x10097b09  push    edi; void *
0x10097b0a  mov     ecx, esi
0x10097b0c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10097b12  call    esi ; _pfnSQLGetInfo
0x10097b14  mov     edx, edi
0x10097b16  mov     ecx, eax
0x10097b18  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x10097b1d  test    eax, eax
0x10097b1f  js      short loc_10097B8C
0x10097b21  movsx   eax, [ebp+var_D4]
0x10097b28  and     eax, 0FFFFFFFEh
0x10097b2b  cmp     eax, 0C8h
0x10097b30  jnb     loc_10097BD1
0x10097b36  xor     ecx, ecx
0x10097b38  mov     [ebp+eax+var_D0], cx
0x10097b40  lea     eax, [ebp+var_D0]
0x10097b46  push    eax
0x10097b47  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x10097b4d  mov     [esp+0FCh+SubStr], offset aExcel; "excel"
0x10097b54  push    eax; Str
0x10097b55  call    ds:__imp__wcsstr
0x10097b5b  pop     ecx
0x10097b5c  pop     ecx
0x10097b5d  test    eax, eax
0x10097b5f  jnz     short loc_10097B8C
0x10097b61  lea     eax, [ebp+var_D0]
0x10097b67  push    eax
0x10097b68  call    ds:__imp___o__wcslwr; __o(wchar_t,char,short,long,wchar_t,long double)
0x10097b6e  mov     [esp+0FCh+SubStr], offset aText; "text"
0x10097b75  push    eax; Str
0x10097b76  call    ds:__imp__wcsstr
0x10097b7c  pop     ecx
0x10097b7d  pop     ecx
0x10097b7e  test    eax, eax
0x10097b80  jnz     short loc_10097B8C
0x10097b82  mov     edi, 0FFFFF80Eh
0x10097b87  jmp     loc_100979BA
0x10097b8c  push    [ebp+arg_14]
0x10097b8f  mov     eax, [ebp+var_E8]
0x10097b95  test    ebx, ebx
0x10097b97  mov     edx, [ebp+var_D8]
0x10097b9d  mov     ecx, [ebp+var_E0]
0x10097ba3  cmovnz  eax, ebx
0x10097ba6  push    eax
0x10097ba7  call    ErrRmtRegisterConn
0x10097bac  mov     edi, eax
0x10097bae  test    edi, edi
0x10097bb0  js      loc_100979BA
0x10097bb6  mov     ecx, [ebp+var_D8]
0x10097bbc  call    PconnOfHdbc
0x10097bc1  mov     ecx, [ebp+var_EC]
0x10097bc7  add     eax, 18h
0x10097bca  mov     [ecx], eax
0x10097bcc  jmp     loc_1009787E
0x10097bd1  call    ___report_rangecheckfailure
```
