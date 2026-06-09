# CXMLTag::GetValue(tagPROPVARIANT * *)

- ea: `0x18000fb70`
- end: `0x18000ff4a`
- name: `?GetValue@CXMLTag@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `986`
- prototype: `signed int __fastcall(const void **this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000eac8`
- `0x18000fab0`
- `0x18000fb70`
- `0x180011204`
- `0x180014130`
- `0x180021a2c`
- `0x180021bc8`
- `0x180023388`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000fdd3`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000fdd3`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000fcdc`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000fd0a`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000fcdc`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000fd0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe75`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000fe58`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000fe58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fec2`
- `OLEAUT32!__imp_VarR8FromStr` at `0x18000fdbc`
- `OLEAUT32!__imp_VarR8FromStr` at `0x18000fdbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000fd25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000fd4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000fd25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000fd4b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000fd70`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000fd70`

## string_xrefs

- `0x18000fc65`: `[HTML] CXMLTag::GetValue, unknown data type: %d\n`
- `0x18000fbb3`: `onecoreuap\base\appmodel\search\filters\html\nlhtml\xmltag.cxx`
- `0x18000fc71`: `onecoreuap\base\appmodel\search\filters\html\nlhtml\xmltag.cxx`
- `0x18000fba7`: `[HTML] CXMLTag::GetValue, unknown value of _eState: %d\n`

## pseudocode

```c
signed int __fastcall CXMLTag::GetValue(const void **this, struct tagPROPVARIANT **a2)
{
  const wchar_t *v2; // r9
  signed int result; // eax
  struct tagPROPVARIANT *v6; // rax
  struct tagPROPVARIANT *v7; // rbx
  unsigned int *v8; // r9
  const wchar_t *v9; // r9
  int v10; // edi
  unsigned int v11; // r14d
  LPVOID v12; // rax
  void *v13; // rsi
  wchar_t *Buffer; // rax
  int v15; // eax
  CXMLTag *v16; // rcx
  CXMLTag *v17; // rcx
  unsigned int *v18; // rax
  __int64 v19; // rcx
  LCID v20; // edx
  unsigned int v21; // esi
  __int64 v22; // rax
  int cbMultiByte; // ebp
  CHAR *v24; // rax
  CHAR *lpMultiByteStr; // rdx
  int v26; // eax
  unsigned int v27; // eax
  unsigned __int64 v28; // rax
  __int64 v29; // rsi
  void *v30; // rax
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-48h] BYREF

  v2 = (const wchar_t *)*((unsigned int *)this + 62);
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == 1 )
      return -2147215614;
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\xmltag.cxx",
      (const wchar_t *)0xF2,
      (unsigned int)L"[HTML] CXMLTag::GetValue, unknown value of _eState: %d\n",
      v2);
    return -2147467259;
  }
  result = CPropertyTag::ReadProperty((CPropertyTag *)this);
  if ( result < 0 )
    return result;
  v6 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  v8 = (unsigned int *)this[18];
  if ( v8 )
    v9 = (const wchar_t *)v8[44];
  else
    v9 = (const wchar_t *)*((unsigned int *)this + 228);
  if ( !(_DWORD)v9 )
  {
    v6->vt = 31;
    v27 = *((_DWORD *)this + 196);
    if ( v27 + 1 >= v27 )
    {
      v28 = 2LL * (v27 + 1);
      if ( v28 <= 0xFFFFFFFF )
      {
        v29 = (unsigned int)v28;
        v30 = CoTaskMemAlloc((unsigned int)v28);
        v7->hVal.QuadPart = (LONGLONG)v30;
        if ( v30 )
        {
          memcpy_0(v30, this[33], v29 - 2);
          *(_WORD *)(v7->hVal.QuadPart + 2LL * *((unsigned int *)this + 196)) = 0;
          goto LABEL_48;
        }
        goto LABEL_45;
      }
    }
    return -2147024362;
  }
  if ( (_DWORD)v9 != 1 )
  {
    switch ( (_DWORD)v9 )
    {
      case 2:
        v6->vt = 11;
        v6->iVal = -((unsigned int)_o__wtoi(this[33]) != 0);
        goto LABEL_48;
      case 3:
        v6->vt = 5;
        v18 = (unsigned int *)this[1];
        v19 = v18[1392];
        if ( (_DWORD)v19 == -1 || !v18[1396] )
          v20 = v18[1393];
        else
          v20 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v18 + 697) + 8 * v19) + 12LL);
        VarR8FromStr((LPCOLESTR)this[33], v20, 0, &v7->dblVal);
        goto LABEL_48;
      case 4:
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        CXMLTag::ParseDateISO8601ToSystemTime(v17, (wchar_t *)this[33], &SystemTime);
        break;
      case 5:
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        CXMLTag::ParseDateTimeISO8601ToSystemTime(v16, (wchar_t *)this[33], &SystemTime);
        break;
      case 6:
        v6->vt = 3;
        v6->lVal = _o__wtol(this[33]);
        goto LABEL_48;
      case 7:
        v15 = _o__wtol(this[33]);
        v7->vt = 64;
        v7->hVal.QuadPart = 60000 * v15;
        goto LABEL_48;
      case 8:
        v6->vt = 31;
        v11 = 2 * *((_DWORD *)this + 259) + 2;
        v12 = CoTaskMemAlloc(v11);
        v7->hVal.QuadPart = (LONGLONG)v12;
        v13 = v12;
        if ( v12 )
        {
          Buffer = CLMString::GetBuffer((CLMString *)(this + 127), 0);
          memcpy_0(v13, Buffer, v11);
LABEL_48:
          *a2 = v7;
          result = 268042;
          *((_DWORD *)this + 196) = 0;
          *((_DWORD *)this + 62) = 1;
          return result;
        }
LABEL_45:
        v10 = -2147024882;
        goto LABEL_46;
      default:
        SearchIndexerDebug::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\xmltag.cxx",
          (const wchar_t *)0xDE,
          (unsigned int)L"[HTML] CXMLTag::GetValue, unknown data type: %d\n",
          v9);
        v10 = -2147467259;
LABEL_46:
        CoTaskMemFree(v7);
        return v10;
    }
    v7->vt = 64;
    SystemTimeToFileTime(&SystemTime, &v7->filetime);
    goto LABEL_48;
  }
  v6->vt = 30;
  v21 = *((_DWORD *)this + 196);
  v22 = v21 + 1;
  if ( (unsigned int)v22 < v21 || (unsigned __int64)(3 * v22) > 0xFFFFFFFF )
    return -2147024362;
  cbMultiByte = 3 * v22;
  v24 = (CHAR *)CoTaskMemAlloc((unsigned int)(3 * v22));
  v7->hVal.QuadPart = (LONGLONG)v24;
  lpMultiByteStr = v24;
  if ( !v24 )
    goto LABEL_45;
  v26 = 0;
  if ( !v21
    || (v26 = WideCharToMultiByte(
                *((_DWORD *)this[1] + 1266),
                0,
                (LPCWCH)this[33],
                v21,
                lpMultiByteStr,
                cbMultiByte,
                0,
                0)) != 0 )
  {
    *(_BYTE *)(v26 + v7->hVal.QuadPart) = 0;
    goto LABEL_48;
  }
  CoTaskMemFree(v7->puuid);
  CoTaskMemFree(v7);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fb70  mov     [rsp+arg_10], rbx
0x18000fb75  push    rbp
0x18000fb76  push    rsi
0x18000fb77  push    rdi
0x18000fb78  push    r14
0x18000fb7a  push    r15
0x18000fb7c  sub     rsp, 60h
0x18000fb80  mov     rax, cs:__security_cookie
0x18000fb87  xor     rax, rsp
0x18000fb8a  mov     [rsp+88h+var_38], rax
0x18000fb8f  mov     r9d, [rcx+0F8h]; wchar_t *
0x18000fb96  mov     r15, rdx
0x18000fb99  mov     rdi, rcx
0x18000fb9c  test    r9d, r9d
0x18000fb9f  jz      short loc_18000FBD3
0x18000fba1  cmp     r9d, 1
0x18000fba5  jz      short loc_18000FBC9
0x18000fba7  lea     r8, aHtmlCxmltagGet; "[HTML] CXMLTag::GetValue, unknown value"...
0x18000fbae  mov     edx, 0F2h; wchar_t *
0x18000fbb3  lea     rcx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000fbba  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000fbbf  mov     eax, 80004005h
0x18000fbc4  jmp     loc_18000FF29
0x18000fbc9  mov     eax, 80041702h
0x18000fbce  jmp     loc_18000FF29
0x18000fbd3  call    ?ReadProperty@CPropertyTag@@IEAAJXZ; CPropertyTag::ReadProperty(void)
0x18000fbd8  test    eax, eax
0x18000fbda  js      loc_18000FF29
0x18000fbe0  mov     ecx, 18h; cb
0x18000fbe5  call    cs:__imp_CoTaskMemAlloc
0x18000fbeb  mov     rbx, rax
0x18000fbee  test    rax, rax
0x18000fbf1  jnz     short loc_18000FBFD
0x18000fbf3  mov     eax, 8007000Eh
0x18000fbf8  jmp     loc_18000FF29
0x18000fbfd  mov     r9, [rdi+90h]
0x18000fc04  test    r9, r9
0x18000fc07  jz      short loc_18000FC12
0x18000fc09  mov     r9d, [r9+0B0h]
0x18000fc10  jmp     short loc_18000FC19
0x18000fc12  mov     r9d, [rdi+390h]; wchar_t *
0x18000fc19  mov     ecx, r9d
0x18000fc1c  test    r9d, r9d
0x18000fc1f  jz      loc_18000FE9D
0x18000fc25  sub     ecx, 1
0x18000fc28  jz      loc_18000FDE7
0x18000fc2e  sub     ecx, 1
0x18000fc31  jz      loc_18000FDC7
0x18000fc37  sub     ecx, 1
0x18000fc3a  jz      loc_18000FD7B
0x18000fc40  sub     ecx, 1
0x18000fc43  jz      loc_18000FD3E
0x18000fc49  sub     ecx, 1
0x18000fc4c  jz      loc_18000FD18
0x18000fc52  sub     ecx, 1
0x18000fc55  jz      loc_18000FCFE
0x18000fc5b  sub     ecx, 1
0x18000fc5e  jz      short loc_18000FCD5
0x18000fc60  cmp     ecx, 1
0x18000fc63  jz      short loc_18000FC87
0x18000fc65  lea     r8, aHtmlCxmltagGet_0; "[HTML] CXMLTag::GetValue, unknown data "...
0x18000fc6c  mov     edx, 0DEh; wchar_t *
0x18000fc71  lea     rcx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000fc78  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000fc7d  mov     edi, 80004005h
0x18000fc82  jmp     loc_18000FED6
0x18000fc87  mov     word ptr [rax], 1Fh
0x18000fc8c  lea     rbp, [rdi+3F8h]
0x18000fc93  mov     eax, [rbp+14h]
0x18000fc96  lea     eax, ds:2[rax*2]
0x18000fc9d  mov     ecx, eax; cb
0x18000fc9f  mov     r14d, eax
0x18000fca2  call    cs:__imp_CoTaskMemAlloc
0x18000fca8  mov     [rbx+8], rax
0x18000fcac  mov     rsi, rax
0x18000fcaf  test    rax, rax
0x18000fcb2  jz      loc_18000FED1
0x18000fcb8  xor     edx, edx; int
0x18000fcba  mov     rcx, rbp; this
0x18000fcbd  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18000fcc2  mov     rdx, rax; Src
0x18000fcc5  mov     r8d, r14d; Size
0x18000fcc8  mov     rcx, rsi; void *
0x18000fccb  call    memcpy_0
0x18000fcd0  jmp     loc_18000FF06
0x18000fcd5  mov     rcx, [rdi+108h]
0x18000fcdc  call    cs:__imp__o__wtol
0x18000fce2  imul    eax, 0EA60h
0x18000fce8  mov     word ptr [rbx], 40h ; '@'
0x18000fced  cdqe
0x18000fcef  mov     [rbx+8], eax
0x18000fcf2  shr     rax, 20h
0x18000fcf6  mov     [rbx+0Ch], eax
0x18000fcf9  jmp     loc_18000FF06
0x18000fcfe  mov     word ptr [rax], 3
0x18000fd03  mov     rcx, [rdi+108h]
0x18000fd0a  call    cs:__imp__o__wtol
0x18000fd10  mov     [rbx+8], eax
0x18000fd13  jmp     loc_18000FF06
0x18000fd18  xorps   xmm0, xmm0
0x18000fd1b  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x18000fd20  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x18000fd25  call    cs:__imp_GetSystemTime
0x18000fd2b  mov     rdx, [rdi+108h]; wchar_t *
0x18000fd32  lea     r8, [rsp+88h+SystemTime]; struct _SYSTEMTIME *
0x18000fd37  call    ?ParseDateTimeISO8601ToSystemTime@CXMLTag@@AEAA_NPEA_WPEAU_SYSTEMTIME@@@Z; CXMLTag::ParseDateTimeISO8601ToSystemTime(wchar_t *,_SYSTEMTIME *)
0x18000fd3c  jmp     short loc_18000FD62
0x18000fd3e  xorps   xmm0, xmm0
0x18000fd41  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x18000fd46  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x18000fd4b  call    cs:__imp_GetSystemTime
0x18000fd51  mov     rdx, [rdi+108h]; wchar_t *
0x18000fd58  lea     r8, [rsp+88h+SystemTime]; struct _SYSTEMTIME *
0x18000fd5d  call    ?ParseDateISO8601ToSystemTime@CXMLTag@@AEAA_NPEA_WPEAU_SYSTEMTIME@@@Z; CXMLTag::ParseDateISO8601ToSystemTime(wchar_t *,_SYSTEMTIME *)
0x18000fd62  lea     rdx, [rbx+8]; lpFileTime
0x18000fd66  mov     word ptr [rbx], 40h ; '@'
0x18000fd6b  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x18000fd70  call    cs:__imp_SystemTimeToFileTime
0x18000fd76  jmp     loc_18000FF06
0x18000fd7b  mov     word ptr [rax], 5
0x18000fd80  mov     rax, [rdi+8]
0x18000fd84  mov     ecx, [rax+15C0h]
0x18000fd8a  cmp     ecx, 0FFFFFFFFh
0x18000fd8d  jz      short loc_18000FDA8
0x18000fd8f  cmp     dword ptr [rax+15D0h], 0
0x18000fd96  jz      short loc_18000FDA8
0x18000fd98  mov     rax, [rax+15C8h]
0x18000fd9f  mov     rcx, [rax+rcx*8]
0x18000fda3  mov     edx, [rcx+0Ch]
0x18000fda6  jmp     short loc_18000FDAE
0x18000fda8  mov     edx, [rax+15C4h]; lcid
0x18000fdae  mov     rcx, [rdi+108h]; strIn
0x18000fdb5  lea     r9, [rbx+8]; pdblOut
0x18000fdb9  xor     r8d, r8d; dwFlags
0x18000fdbc  call    cs:__imp_VarR8FromStr
0x18000fdc2  jmp     loc_18000FF06
0x18000fdc7  mov     word ptr [rax], 0Bh
0x18000fdcc  mov     rcx, [rdi+108h]
0x18000fdd3  call    cs:__imp__o__wtoi
0x18000fdd9  neg     eax
0x18000fddb  sbb     cx, cx
0x18000fdde  mov     [rbx+8], cx
0x18000fde2  jmp     loc_18000FF06
0x18000fde7  mov     word ptr [rax], 1Eh
0x18000fdec  mov     esi, [rdi+310h]
0x18000fdf2  lea     eax, [rsi+1]
0x18000fdf5  cmp     eax, esi
0x18000fdf7  jb      loc_18000FF24
0x18000fdfd  lea     rdx, [rax+rax*2]
0x18000fe01  mov     ecx, 0FFFFFFFFh
0x18000fe06  cmp     rdx, rcx
0x18000fe09  ja      loc_18000FF24
0x18000fe0f  mov     ecx, edx; cb
0x18000fe11  mov     ebp, edx
0x18000fe13  call    cs:__imp_CoTaskMemAlloc
0x18000fe19  mov     [rbx+8], rax
0x18000fe1d  mov     rdx, rax
0x18000fe20  test    rax, rax
0x18000fe23  jz      loc_18000FED1
0x18000fe29  xor     eax, eax
0x18000fe2b  test    esi, esi
0x18000fe2d  jz      short loc_18000FE90
0x18000fe2f  mov     rcx, [rdi+8]
0x18000fe33  mov     r9d, esi; cchWideChar
0x18000fe36  mov     r8, [rdi+108h]; lpWideCharStr
0x18000fe3d  mov     [rsp+88h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18000fe42  mov     [rsp+88h+lpDefaultChar], rax; lpDefaultChar
0x18000fe47  mov     ecx, [rcx+13C8h]; CodePage
0x18000fe4d  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x18000fe51  mov     [rsp+88h+lpMultiByteStr], rdx; lpMultiByteStr
0x18000fe56  xor     edx, edx; dwFlags
0x18000fe58  call    cs:__imp_WideCharToMultiByte
0x18000fe5e  test    eax, eax
0x18000fe60  jnz     short loc_18000FE90
0x18000fe62  mov     rcx, [rbx+8]; pv
0x18000fe66  call    cs:__imp_CoTaskMemFree
0x18000fe6c  mov     rcx, rbx; pv
0x18000fe6f  call    cs:__imp_CoTaskMemFree
0x18000fe75  call    cs:__imp_GetLastError
0x18000fe7b  test    eax, eax
0x18000fe7d  jle     loc_18000FF29
0x18000fe83  movzx   eax, ax
0x18000fe86  or      eax, 80070000h
0x18000fe8b  jmp     loc_18000FF29
0x18000fe90  movsxd  rcx, eax
0x18000fe93  mov     rax, [rbx+8]
0x18000fe97  mov     byte ptr [rcx+rax], 0
0x18000fe9b  jmp     short loc_18000FF06
0x18000fe9d  mov     word ptr [rax], 1Fh
0x18000fea2  mov     eax, [rdi+310h]
0x18000fea8  lea     ecx, [rax+1]
0x18000feab  cmp     ecx, eax
0x18000fead  jb      short loc_18000FF24
0x18000feaf  mov     eax, ecx
0x18000feb1  mov     ecx, 0FFFFFFFFh
0x18000feb6  add     rax, rax
0x18000feb9  cmp     rax, rcx
0x18000febc  ja      short loc_18000FF24
0x18000febe  mov     ecx, eax; cb
0x18000fec0  mov     esi, eax
0x18000fec2  call    cs:__imp_CoTaskMemAlloc
0x18000fec8  mov     [rbx+8], rax
0x18000fecc  test    rax, rax
0x18000fecf  jnz     short loc_18000FEE3
0x18000fed1  mov     edi, 8007000Eh
0x18000fed6  mov     rcx, rbx; pv
0x18000fed9  call    cs:__imp_CoTaskMemFree
0x18000fedf  mov     eax, edi
0x18000fee1  jmp     short loc_18000FF29
0x18000fee3  mov     rdx, [rdi+108h]; Src
0x18000feea  lea     r8, [rsi-2]; Size
0x18000feee  mov     rcx, rax; void *
0x18000fef1  call    memcpy_0
0x18000fef6  mov     edx, [rdi+310h]
0x18000fefc  xor     eax, eax
0x18000fefe  mov     rcx, [rbx+8]
0x18000ff02  mov     [rcx+rdx*2], ax
0x18000ff06  mov     [r15], rbx
0x18000ff09  mov     eax, 4170Ah
0x18000ff0e  mov     dword ptr [rdi+310h], 0
0x18000ff18  mov     dword ptr [rdi+0F8h], 1
0x18000ff22  jmp     short loc_18000FF29
0x18000ff24  mov     eax, 80070216h
0x18000ff29  mov     rcx, [rsp+88h+var_38]
0x18000ff2e  xor     rcx, rsp; StackCookie
0x18000ff31  call    __security_check_cookie
0x18000ff36  mov     rbx, [rsp+88h+arg_10]
0x18000ff3e  add     rsp, 60h
0x18000ff42  pop     r15
0x18000ff44  pop     r14
0x18000ff46  pop     rdi
0x18000ff47  pop     rsi
0x18000ff48  pop     rbp
0x18000ff49  retn
```
