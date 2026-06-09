# CBody::SaveAsStationery(tagVARIANT const *,tagVARIANT *)

- ea: `0x18007d36c`
- end: `0x18007db29`
- name: `?SaveAsStationery@CBody@@AEAAJPEBUtagVARIANT@@PEAU2@@Z`
- size: `1981`
- prototype: `__int64 __fastcall(CBody *__hidden this, const struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023d04`

## callees

- `0x180004f40`
- `0x1800055bc`
- `0x180005748`
- `0x18000910c`
- `0x180015858`
- `0x180020d88`
- `0x180021140`
- `0x18002a0d8`
- `0x18004bba4`
- `0x180052178`
- `0x180073e84`
- `0x180074638`
- `0x180074be4`
- `0x18007d36c`
- `0x1800cb9a8`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cca90`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!MessageBoxInstW` at `0x18007d8e7`
- `MSOERT2!MessageBoxInstW` at `0x18007d9bc`
- `MSOERT2!MessageBoxInstW` at `0x18007d8e7`
- `MSOERT2!MessageBoxInstW` at `0x18007d9bc`
- `MSOERT2!ReplaceCharsW` at `0x18007d4af`
- `MSOERT2!ReplaceCharsW` at `0x18007d4af`
- `MSOERT2!WriteStreamToFileW` at `0x18007d912`
- `MSOERT2!WriteStreamToFileW` at `0x18007da96`
- `MSOERT2!WriteStreamToFileW` at `0x18007d912`
- `MSOERT2!WriteStreamToFileW` at `0x18007da96`
- `MSOERT2!HrGetStyleSheet` at `0x18007d5f3`
- `MSOERT2!HrGetStyleSheet` at `0x18007d5f3`
- `SHLWAPI!PathFileExistsW` at `0x18007d83c`
- `SHLWAPI!PathFileExistsW` at `0x18007d83c`
- `USER32!MessageBoxW` at `0x18007d896`
- `USER32!MessageBoxW` at `0x18007d96e`
- `USER32!LoadStringW` at `0x18007d49e`
- `USER32!LoadStringW` at `0x18007d4ce`
- `USER32!LoadStringW` at `0x18007d863`
- `USER32!LoadStringW` at `0x18007d49e`
- `USER32!LoadStringW` at `0x18007d4ce`
- `USER32!LoadStringW` at `0x18007d863`
- `USER32!LoadStringW` at `0x18007d8ce`
- `USER32!LoadStringW` at `0x18007d9a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18007dab8`
- `OLEAUT32!__imp_SysAllocString` at `0x18007dab8`
- `OLEAUT32!__imp_SysFreeString` at `0x18007d712`
- `OLEAUT32!__imp_SysFreeString` at `0x18007dadb`
- `OLEAUT32!__imp_SysFreeString` at `0x18007d712`
- `OLEAUT32!__imp_SysFreeString` at `0x18007dadb`

## pseudocode

```c
__int64 __fastcall CBody::SaveAsStationery(CBody *this, const struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  const WCHAR *bstrVal; // rdi
  __int64 result; // rax
  unsigned __int64 v8; // rbx
  __int64 nFileExtension; // rcx
  unsigned __int64 v10; // rcx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // r12
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // r8
  char *v17; // r14
  unsigned __int16 *v18; // r8
  int v19; // ebx
  __int64 v20; // r8
  WCHAR *v21; // rdx
  BSTR v22; // rax
  int v23; // ecx
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  struct IStream *v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h] BYREF
  char *v28; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v30; // [rsp+90h] [rbp-70h]
  struct tagOFNW v31; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v33[206]; // [rsp+152h] [rbp+52h] BYREF
  WCHAR pszPath[264]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v35; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v36[526]; // [rsp+432h] [rbp+332h] BYREF
  unsigned __int16 v37; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v38[526]; // [rsp+642h] [rbp+542h] BYREF
  unsigned __int16 v39; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v40[526]; // [rsp+852h] [rbp+752h] BYREF
  unsigned __int16 v41[512]; // [rsp+A60h] [rbp+960h] BYREF
  WCHAR v42[512]; // [rsp+E60h] [rbp+D60h] BYREF
  WCHAR v43[512]; // [rsp+1260h] [rbp+1160h] BYREF
  unsigned __int16 v44[264]; // [rsp+1660h] [rbp+1560h] BYREF
  unsigned __int16 v45[776]; // [rsp+1870h] [rbp+1770h] BYREF

  bstrString = 0;
  v27 = 0;
  v25 = 0;
  v28 = 0;
  memset_0(v45, 0, 0x608u);
  memset_0(v43, 0, sizeof(v43));
  memset_0(v38, 0, 0x206u);
  memset_0(v40, 0, 0x206u);
  memset_0(&v31, 0, sizeof(v31));
  memset_0(v36, 0, 0x206u);
  memset_0(v42, 0, sizeof(v42));
  memset_0(v33, 0, 0xC6u);
  memset_0(v41, 0, sizeof(v41));
  v37 = 0;
  v39 = 0;
  v35 = 0;
  bstrVal = 0;
  Buffer = 0;
  LoadStringW(g_hLocRes, 0x4F8u, &Buffer, 100);
  ReplaceCharsW(&Buffer, 124);
  LoadStringW(g_hLocRes, 0x4F7u, v42, 512);
  if ( a2 && a2->vt == 8 )
    bstrVal = a2->bstrVal;
  v31.hwndOwner = (HWND)*((_QWORD *)this + 13);
  v31.lStructSize = 152;
  v31.lpstrFilter = &Buffer;
  v31.lpstrFile = &v35;
  v31.lpstrTitle = v42;
  v31.nFilterIndex = 1;
  v31.nMaxFile = 260;
  v31.lpstrInitialDir = bstrVal;
  v31.Flags = 2062;
  if ( !GetSaveFileNameW(&v31) || !v35 )
    return 2148275971LL;
  result = StringCchCopyW(&v39, 0x104u, &v35);
  if ( (int)result < 0 )
    return result;
  v8 = 2LL * v31.nFileOffset;
  if ( v8 >= 0x208 )
    goto LABEL_62;
  nFileExtension = v31.nFileExtension;
  *(_WORD *)&v40[2 * v31.nFileOffset - 2] = 0;
  if ( (_WORD)nFileExtension && pszPath[nFileExtension + 263] == 46 )
  {
    v10 = 2 * nFileExtension - 2;
    if ( v10 < 0x208 )
    {
      *(_WORD *)&v36[v10 - 2] = 0;
      goto LABEL_12;
    }
LABEL_62:
    _report_rangecheckfailure();
  }
LABEL_12:
  if ( (int)MimeOleCreateVirtualStream(&v27) < 0 )
    return 2147942414LL;
  v11 = *((_QWORD *)this + 37);
  v12 = (const unsigned __int16 *)&v36[v8 - 2];
  v26 = 0;
  if ( v11 )
  {
    bstrString = 0;
    if ( !(unsigned int)HrGetStyleSheet(v11, &v26) )
    {
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 208LL))(v26, &bstrString);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
  }
  v13 = v27;
  (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v27 + 32LL))(v27, L"<HTML>\r\n", 16);
  v14 = -1;
  if ( (int)StringCchPrintfW(
              v41,
              0x200u,
              L"<META HTTP-EQUIV=\"Content-Type\" CONTENT=\"text/html;charset=%s\">\r\n",
              L"Unicode") >= 0 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v41[v15] );
    (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v13 + 32LL))(
      v13,
      v41,
      (unsigned int)(2 * v15),
      0);
  }
  if ( bstrString )
  {
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v13 + 32LL))(
      v13,
      L"<HEAD>\r\n<STYLE>\r\n",
      34);
    v16 = -1;
    do
      ++v16;
    while ( bstrString[v16] );
    (*(void (__fastcall **)(__int64, BSTR, _QWORD, _QWORD))(*(_QWORD *)v13 + 32LL))(
      v13,
      bstrString,
      (unsigned int)(2 * v16),
      0);
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v13 + 32LL))(
      v13,
      L"</STYLE>\r\n</HEAD>\r\n",
      38);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
  }
  if ( (unsigned int)GetBackgroundImage(*((struct IHTMLDocument2 **)this + 37), &bstrString) )
    goto LABEL_44;
  if ( (unsigned int)HrOpenUrlViaCache(bstrString, &v25) )
    HrFindUrlInMsg(*((struct IMimeMessage **)this + 35), bstrString, 1u, &v25);
  if ( !v25 )
  {
LABEL_44:
    if ( v37 )
    {
      StringCchPrintfW(pszPath, 0x104u, L"<BODY BACKGROUND=\"%s\">\r\n&nbsp;\r\n", &v37);
      do
        ++v14;
      while ( pszPath[v14] );
      v20 = (unsigned int)(2 * v14);
      v21 = pszPath;
    }
    else
    {
      if ( (unsigned int)MessageBoxInstW(
                           g_hLocRes,
                           *((_QWORD *)this + 13),
                           1271,
                           1274,
                           0,
                           308,
                           LoadStringW,
                           MessageBoxW,
                           0,
                           0,
                           0,
                           0) != 6 )
      {
        v19 = -2146691325;
        goto LABEL_59;
      }
      v20 = 28;
      v21 = L"<BODY>\r\n&nbsp;";
    }
    (*(void (__fastcall **)(__int64, WCHAR *, __int64, _QWORD))(*(_QWORD *)v13 + 32LL))(v13, v21, v20, 0);
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v13 + 32LL))(v13, L"</BODY>\r\n", 18);
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v13 + 32LL))(
      v13,
      L"</HTML>\r\n",
      18,
      0);
    v19 = StringCchCopyW(pszPath, 0x104u, &v39);
    if ( v19 >= 0 )
    {
      v19 = StringCchCatW(pszPath, 0x104u, v12);
      if ( v19 >= 0 )
      {
        v19 = StringCchCatW(pszPath, 0x104u, L".htm");
        if ( v19 >= 0 )
        {
          v19 = WriteStreamToFileW(v13, pszPath, 2, 0x40000000);
          if ( v19 >= 0 )
          {
            if ( a3 )
            {
              a3->vt = 8;
              a3->llVal = 0;
              v22 = SysAllocString(pszPath);
              v23 = v19;
              a3->llVal = (LONGLONG)v22;
              if ( !v22 )
                v23 = -2147024882;
              v19 = v23;
            }
          }
        }
      }
    }
    goto LABEL_59;
  }
  StringCchCopyW(&v37, 0x104u, v12);
  if ( !(unsigned int)HrSniffStreamFileExt(v25, &v28) )
  {
    STRW::STRW((STRW *)&v29, v44, 0x104u);
    v17 = v28;
    if ( STRW::AppendA_CP((STRW *)&v29, v28, 0) >= 0 )
    {
      v18 = (unsigned __int16 *)&cchOriginalDestLength;
      if ( v29 )
        v18 = v30;
      StringCchCatW(&v37, 0x104u, v18);
    }
    if ( v17 )
      ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v17);
    STRW::~STRW((STRW *)&v29);
  }
  StringCchCopyW(pszPath, 0x104u, &v39);
  StringCchCatW(pszPath, 0x104u, &v37);
  if ( !PathFileExistsW(pszPath) )
  {
LABEL_43:
    WriteStreamToFileW(v25, pszPath, 2, 0x40000000);
    ((void (__fastcall *)(struct IStream *))v25->lpVtbl->Release)(v25);
    goto LABEL_44;
  }
  if ( LoadStringW(g_hLocRes, 0x4F9u, v43, 512) )
  {
    StringCchPrintfW(v45, 0x304u, v43, pszPath);
    if ( (unsigned int)MessageBoxInstW(
                         g_hLocRes,
                         *((_QWORD *)this + 13),
                         1271,
                         v45,
                         0,
                         308,
                         LoadStringW,
                         MessageBoxW,
                         0,
                         0,
                         0,
                         0) != 6 )
    {
      v19 = 0;
      goto LABEL_59;
    }
    goto LABEL_43;
  }
  v19 = -2147024882;
LABEL_59:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  OE_SafeReleaseAndNullPtr<IStream>(&v27);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18007d36c  mov     [rsp-8+arg_18], rbx
0x18007d371  push    rbp
0x18007d372  push    rsi
0x18007d373  push    rdi
0x18007d374  push    r12
0x18007d376  push    r13
0x18007d378  push    r14
0x18007d37a  push    r15
0x18007d37c  lea     rbp, [rsp-1D90h]
0x18007d384  mov     eax, 1E90h
0x18007d389  call    _alloca_probe
0x18007d38e  sub     rsp, rax
0x18007d391  mov     rax, cs:__security_cookie
0x18007d398  xor     rax, rsp
0x18007d39b  mov     [rbp+1DC0h+var_40], rax
0x18007d3a2  xor     r13d, r13d
0x18007d3a5  mov     r15, r8
0x18007d3a8  mov     rbx, rdx
0x18007d3ab  mov     [rsp+1EC0h+bstrString], r13
0x18007d3b0  mov     rsi, rcx
0x18007d3b3  mov     [rsp+1EC0h+var_1E48], r13
0x18007d3b8  xor     edx, edx; Val
0x18007d3ba  mov     [rsp+1EC0h+var_1E58], r13
0x18007d3bf  mov     r8d, 608h; Size
0x18007d3c5  mov     [rbp+1DC0h+var_1E40], r13
0x18007d3c9  lea     rcx, [rbp+1DC0h+var_650]; void *
0x18007d3d0  call    memset_0
0x18007d3d5  mov     r14d, 400h
0x18007d3db  lea     rcx, [rbp+1DC0h+var_C60]; void *
0x18007d3e2  mov     r8d, r14d; Size
0x18007d3e5  xor     edx, edx; Val
0x18007d3e7  call    memset_0
0x18007d3ec  mov     edi, 206h
0x18007d3f1  lea     rcx, [rbp+1DC0h+var_187E]; void *
0x18007d3f8  mov     r8d, edi; Size
0x18007d3fb  xor     edx, edx; Val
0x18007d3fd  call    memset_0
0x18007d402  mov     r8d, edi; Size
0x18007d405  lea     rcx, [rbp+1DC0h+var_166E]; void *
0x18007d40c  xor     edx, edx; Val
0x18007d40e  call    memset_0
0x18007d413  mov     r12d, 98h
0x18007d419  lea     rcx, [rbp+1DC0h+var_1E10]; void *
0x18007d41d  mov     r8d, r12d; Size
0x18007d420  xor     edx, edx; Val
0x18007d422  call    memset_0
0x18007d427  mov     r8d, edi; Size
0x18007d42a  lea     rcx, [rbp+1DC0h+var_1A8E]; void *
0x18007d431  xor     edx, edx; Val
0x18007d433  call    memset_0
0x18007d438  mov     r8d, r14d; Size
0x18007d43b  lea     rcx, [rbp+1DC0h+var_1060]; void *
0x18007d442  xor     edx, edx; Val
0x18007d444  call    memset_0
0x18007d449  xor     edx, edx; Val
0x18007d44b  lea     r8d, [r12+2Eh]; Size
0x18007d450  lea     rcx, [rbp+1DC0h+var_1D6E]; void *
0x18007d454  call    memset_0
0x18007d459  mov     r8d, r14d; Size
0x18007d45c  lea     rcx, [rbp+1DC0h+var_1460]; void *
0x18007d463  xor     edx, edx; Val
0x18007d465  call    memset_0
0x18007d46a  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007d471  lea     r9d, [r13+64h]; cchBufferMax
0x18007d475  lea     r8, [rbp+1DC0h+Buffer]; lpBuffer
0x18007d479  mov     [rbp+1DC0h+var_1880], r13w
0x18007d481  mov     edx, 4F8h; uID
0x18007d486  mov     [rbp+1DC0h+var_1670], r13w
0x18007d48e  mov     [rbp+1DC0h+var_1A90], r13w
0x18007d496  mov     edi, r13d
0x18007d499  mov     [rbp+1DC0h+Buffer], r13w
0x18007d49e  call    cs:__imp_LoadStringW
0x18007d4a4  xor     r8d, r8d
0x18007d4a7  lea     edx, [r13+7Ch]
0x18007d4ab  lea     rcx, [rbp+1DC0h+Buffer]
0x18007d4af  call    cs:__imp_ReplaceCharsW
0x18007d4b5  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007d4bc  lea     r8, [rbp+1DC0h+var_1060]; lpBuffer
0x18007d4c3  mov     r9d, 200h; cchBufferMax
0x18007d4c9  mov     edx, 4F7h; uID
0x18007d4ce  call    cs:__imp_LoadStringW
0x18007d4d4  lea     eax, [r13+8]
0x18007d4d8  test    rbx, rbx
0x18007d4db  jz      short loc_18007D4E6
0x18007d4dd  cmp     [rbx], ax
0x18007d4e0  jnz     short loc_18007D4E6
0x18007d4e2  mov     rdi, [rbx+8]
0x18007d4e6  mov     rax, [rsi+68h]
0x18007d4ea  lea     rcx, [rbp+1DC0h+var_1E10]; LPOPENFILENAMEW
0x18007d4ee  mov     [rbp+1DC0h+var_1E10.hwndOwner], rax
0x18007d4f2  mov     r14d, 104h
0x18007d4f8  lea     rax, [rbp+1DC0h+Buffer]
0x18007d4fc  mov     [rbp+1DC0h+var_1E10.lStructSize], r12d
0x18007d500  mov     [rbp+1DC0h+var_1E10.lpstrFilter], rax
0x18007d504  lea     rax, [rbp+1DC0h+var_1A90]
0x18007d50b  mov     [rbp+1DC0h+var_1E10.lpstrFile], rax
0x18007d50f  lea     rax, [rbp+1DC0h+var_1060]
0x18007d516  mov     [rbp+1DC0h+var_1E10.lpstrTitle], rax
0x18007d51a  mov     [rbp+1DC0h+var_1E10.nFilterIndex], 1
0x18007d521  mov     [rbp+1DC0h+var_1E10.nMaxFile], r14d
0x18007d525  mov     [rbp+1DC0h+var_1E10.lpstrInitialDir], rdi
0x18007d529  mov     [rbp+1DC0h+var_1E10.Flags], 80Eh
0x18007d530  call    GetSaveFileNameW
0x18007d535  test    eax, eax
0x18007d537  jz      loc_18007DAFA
0x18007d53d  cmp     [rbp+1DC0h+var_1A90], r13w
0x18007d545  jz      loc_18007DAFA
0x18007d54b  lea     r8, [rbp+1DC0h+var_1A90]; unsigned __int16 *
0x18007d552  mov     edx, r14d; unsigned __int64
0x18007d555  lea     rcx, [rbp+1DC0h+var_1670]; unsigned __int16 *
0x18007d55c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007d561  test    eax, eax
0x18007d563  js      loc_18007DAFF
0x18007d569  movzx   eax, [rbp+1DC0h+var_1E10.nFileOffset]
0x18007d56d  mov     edx, 208h
0x18007d572  lea     rbx, [rax+rax]
0x18007d576  cmp     rbx, rdx
0x18007d579  jnb     loc_18007DAF4
0x18007d57f  movzx   ecx, [rbp+1DC0h+var_1E10.nFileExtension]
0x18007d583  mov     [rbp+rbx+1DC0h+var_1670], r13w
0x18007d58c  test    cx, cx
0x18007d58f  jz      short loc_18007D5B6
0x18007d591  cmp     [rbp+rcx*2+1DC0h+var_1A92], 2Eh ; '.'
0x18007d59a  jnz     short loc_18007D5B6
0x18007d59c  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x18007d5a4  cmp     rcx, rdx
0x18007d5a7  jnb     loc_18007DAF4
0x18007d5ad  mov     [rbp+rcx+1DC0h+var_1A90], r13w
0x18007d5b6  lea     rcx, [rsp+1EC0h+var_1E48]
0x18007d5bb  call    MimeOleCreateVirtualStream
0x18007d5c0  test    eax, eax
0x18007d5c2  jns     short loc_18007D5CE
0x18007d5c4  mov     eax, 8007000Eh
0x18007d5c9  jmp     loc_18007DAFF
0x18007d5ce  mov     rcx, [rsi+128h]
0x18007d5d5  lea     r12, [rbp+1DC0h+var_1A90]
0x18007d5dc  add     r12, rbx
0x18007d5df  mov     [rsp+1EC0h+var_1E50], r13
0x18007d5e4  test    rcx, rcx
0x18007d5e7  jz      short loc_18007D627
0x18007d5e9  lea     rdx, [rsp+1EC0h+var_1E50]
0x18007d5ee  mov     [rsp+1EC0h+bstrString], r13
0x18007d5f3  call    cs:__imp_HrGetStyleSheet
0x18007d5f9  test    eax, eax
0x18007d5fb  jnz     short loc_18007D627
0x18007d5fd  mov     rcx, [rsp+1EC0h+var_1E50]
0x18007d602  lea     rdx, [rsp+1EC0h+bstrString]
0x18007d607  mov     rax, [rcx]
0x18007d60a  mov     rax, [rax+0D0h]
0x18007d611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d616  mov     rcx, [rsp+1EC0h+var_1E50]
0x18007d61b  mov     rax, [rcx]
0x18007d61e  mov     rax, [rax+10h]
0x18007d622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d627  mov     rdi, [rsp+1EC0h+var_1E48]
0x18007d62c  lea     rdx, c_wszHtml_HtmlOpenCR; "<HTML>\r\n"
0x18007d633  xor     r9d, r9d
0x18007d636  mov     rcx, rdi
0x18007d639  mov     rax, [rdi]
0x18007d63c  lea     r8d, [r9+10h]
0x18007d640  mov     rax, [rax+20h]
0x18007d644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d649  lea     r9, aUnicode; "Unicode"
0x18007d650  mov     edx, 200h; unsigned __int64
0x18007d655  lea     r8, c_wszHtml_MetaTagf; "<META HTTP-EQUIV=\"Content-Type\" CONTE"...
0x18007d65c  lea     rcx, [rbp+1DC0h+var_1460]; unsigned __int16 *
0x18007d663  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007d668  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007d66c  test    eax, eax
0x18007d66e  js      short loc_18007D6A0
0x18007d670  lea     rax, [rbp+1DC0h+var_1460]
0x18007d677  mov     r8, rbx
0x18007d67a  inc     r8
0x18007d67d  cmp     [rax+r8*2], r13w
0x18007d682  jnz     short loc_18007D67A
0x18007d684  mov     rax, [rdi]
0x18007d687  lea     rdx, [rbp+1DC0h+var_1460]
0x18007d68e  add     r8d, r8d
0x18007d691  xor     r9d, r9d
0x18007d694  mov     rcx, rdi
0x18007d697  mov     rax, [rax+20h]
0x18007d69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6a0  cmp     [rsp+1EC0h+bstrString], r13
0x18007d6a5  jz      short loc_18007D71D
0x18007d6a7  mov     rax, [rdi]
0x18007d6aa  lea     rdx, c_wszHtml_HeadOpenCR; "<HEAD>\r\n<STYLE>\r\n"
0x18007d6b1  xor     r9d, r9d
0x18007d6b4  mov     rcx, rdi
0x18007d6b7  mov     rax, [rax+20h]
0x18007d6bb  lea     r8d, [r9+22h]
0x18007d6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6c4  mov     rdx, [rsp+1EC0h+bstrString]
0x18007d6c9  mov     r8, rbx
0x18007d6cc  inc     r8
0x18007d6cf  cmp     [rdx+r8*2], r13w
0x18007d6d4  jnz     short loc_18007D6CC
0x18007d6d6  mov     rax, [rdi]
0x18007d6d9  add     r8d, r8d
0x18007d6dc  xor     r9d, r9d
0x18007d6df  mov     rcx, rdi
0x18007d6e2  mov     rax, [rax+20h]
0x18007d6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6eb  mov     rax, [rdi]
0x18007d6ee  lea     rdx, c_wszHtml_HeadCloseCR; "</STYLE>\r\n</HEAD>\r\n"
0x18007d6f5  xor     r9d, r9d
0x18007d6f8  mov     rcx, rdi
0x18007d6fb  mov     rax, [rax+20h]
0x18007d6ff  lea     r8d, [r9+26h]
0x18007d703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d708  mov     rcx, [rsp+1EC0h+bstrString]; bstrString
0x18007d70d  test    rcx, rcx
0x18007d710  jz      short loc_18007D71D
0x18007d712  call    cs:__imp_SysFreeString
0x18007d718  mov     [rsp+1EC0h+bstrString], r13
0x18007d71d  mov     rcx, [rsi+128h]; struct IHTMLDocument2 *
0x18007d724  lea     rdx, [rsp+1EC0h+bstrString]; unsigned __int16 **
0x18007d729  call    ?GetBackgroundImage@@YAJPEAUIHTMLDocument2@@PEAPEAG@Z; GetBackgroundImage(IHTMLDocument2 *,ushort * *)
0x18007d72e  test    eax, eax
0x18007d730  jnz     loc_18007D929
0x18007d736  mov     rcx, [rsp+1EC0h+bstrString]; unsigned __int16 *
0x18007d73b  lea     rdx, [rsp+1EC0h+var_1E58]; struct IStream **
0x18007d740  call    ?HrOpenUrlViaCache@@YAJPEBGPEAPEAUIStream@@@Z; HrOpenUrlViaCache(ushort const *,IStream * *)
0x18007d745  test    eax, eax
0x18007d747  jz      short loc_18007D765
0x18007d749  mov     rdx, [rsp+1EC0h+bstrString]; unsigned __int16 *
0x18007d74e  lea     r9, [rsp+1EC0h+var_1E58]; struct IStream **
0x18007d753  mov     rcx, [rsi+118h]; struct IMimeMessage *
0x18007d75a  mov     r8d, 1; unsigned int
0x18007d760  call    ?HrFindUrlInMsg@@YAJPEAUIMimeMessage@@PEAGKPEAPEAUIStream@@@Z; HrFindUrlInMsg(IMimeMessage *,ushort *,ulong,IStream * *)
0x18007d765  cmp     [rsp+1EC0h+var_1E58], r13
0x18007d76a  jz      loc_18007D929
0x18007d770  mov     r8, r12; unsigned __int16 *
0x18007d773  lea     rcx, [rbp+1DC0h+var_1880]; unsigned __int16 *
0x18007d77a  mov     rdx, r14; unsigned __int64
0x18007d77d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007d782  mov     rcx, [rsp+1EC0h+var_1E58]; struct IStream *
0x18007d787  lea     rdx, [rbp+1DC0h+var_1E40]; char **
0x18007d78b  call    ?HrSniffStreamFileExt@@YAJPEAUIStream@@PEAPEAD@Z; HrSniffStreamFileExt(IStream *,char * *)
0x18007d790  test    eax, eax
0x18007d792  jnz     short loc_18007D809
0x18007d794  mov     r8d, r14d; unsigned int
0x18007d797  lea     rdx, [rbp+1DC0h+var_860]; unsigned __int16 *
0x18007d79e  lea     rcx, [rbp+1DC0h+var_1E38]; this
0x18007d7a2  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007d7a7  mov     r14, [rbp+1DC0h+var_1E40]
0x18007d7ab  lea     rcx, [rbp+1DC0h+var_1E38]; this
0x18007d7af  mov     rdx, r14; char *
0x18007d7b2  xor     r8d, r8d; unsigned int
0x18007d7b5  call    ?AppendA_CP@STRW@@QEAAJPEBDI@Z; STRW::AppendA_CP(char const *,uint)
0x18007d7ba  test    eax, eax
0x18007d7bc  js      short loc_18007D7DF
0x18007d7be  cmp     [rbp+1DC0h+var_1E38], r13d
0x18007d7c2  lea     r8, cchOriginalDestLength
0x18007d7c9  mov     edx, 104h; unsigned __int64
0x18007d7ce  lea     rcx, [rbp+1DC0h+var_1880]; unsigned __int16 *
0x18007d7d5  cmovnz  r8, [rbp+1DC0h+var_1E30]; unsigned __int16 *
0x18007d7da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007d7df  test    r14, r14
0x18007d7e2  jz      short loc_18007D7FA
0x18007d7e4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007d7eb  mov     rdx, r14
0x18007d7ee  mov     rax, [rcx]
0x18007d7f1  mov     rax, [rax+28h]
0x18007d7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7fa  lea     rcx, [rbp+1DC0h+var_1E38]; this
0x18007d7fe  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18007d803  mov     r14d, 104h
0x18007d809  lea     r8, [rbp+1DC0h+var_1670]; unsigned __int16 *
0x18007d810  mov     rdx, r14; unsigned __int64
0x18007d813  lea     rcx, [rbp+1DC0h+pszPath]; unsigned __int16 *
0x18007d81a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007d81f  lea     r8, [rbp+1DC0h+var_1880]; unsigned __int16 *
0x18007d826  mov     rdx, r14; unsigned __int64
0x18007d829  lea     rcx, [rbp+1DC0h+pszPath]; unsigned __int16 *
0x18007d830  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007d835  lea     rcx, [rbp+1DC0h+pszPath]; pszPath
0x18007d83c  call    cs:__imp_PathFileExistsW
0x18007d842  test    eax, eax
0x18007d844  jz      loc_18007D8FA
0x18007d84a  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007d851  lea     r8, [rbp+1DC0h+var_C60]; lpBuffer
0x18007d858  mov     r9d, 200h; cchBufferMax
0x18007d85e  mov     edx, 4F9h; uID
0x18007d863  call    cs:__imp_LoadStringW
0x18007d869  test    eax, eax
0x18007d86b  jnz     short loc_18007D877
0x18007d86d  mov     ebx, 8007000Eh
0x18007d872  jmp     loc_18007DAD1
0x18007d877  lea     r9, [rbp+1DC0h+pszPath]
0x18007d87e  mov     edx, 304h; unsigned __int64
0x18007d883  lea     r8, [rbp+1DC0h+var_C60]; unsigned __int16 *
0x18007d88a  lea     rcx, [rbp+1DC0h+var_650]; unsigned __int16 *
0x18007d891  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007d896  mov     rax, cs:__imp_MessageBoxW
0x18007d89d  lea     r9, [rbp+1DC0h+var_650]
0x18007d8a4  mov     rdx, [rsi+68h]
0x18007d8a8  mov     r8d, 4F7h
0x18007d8ae  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x18007d8b5  mov     [rsp+1EC0h+var_1E68], r13d
0x18007d8ba  mov     [rsp+1EC0h+var_1E70], r13
  ... truncated ...
```
