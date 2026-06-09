# CFrameWebOC::Navigate(ulong,IBindCtx *,IBindStatusCallback *,IHlink *)

- ea: `0x180b5bfb0`
- end: `0x180b5c597`
- name: `?Navigate@CFrameWebOC@@QEAAJKPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlink@@@Z`
- size: `1511`
- prototype: `__int64 __fastcall(CFrameWebOC *__hidden this, unsigned int, struct IBindCtx *, struct IBindStatusCallback *, struct IHlink *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005e648`
- `0x1800ea428`
- `0x1805f8990`
- `0x18071f204`
- `0x180b5bfb0`
- `0x1810f650a`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180b5c2a3`
- `msvcrt!memcpy_s` at `0x180b5c2a3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNIW` at `0x180b5c35c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNIW` at `0x180b5c35c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180b5c337`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180b5c337`
- `iertutil!CreateUri` at `0x180b5c197`
- `iertutil!CreateUri` at `0x180b5c197`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c39a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c3ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c509`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c519`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c529`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c39a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c3ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c509`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c519`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b5c529`
- `ole32!CreateBindCtx` at `0x180b5c149`
- `ole32!CreateBindCtx` at `0x180b5c149`
- `urlmon!ReleaseBindInfo` at `0x180b5c4ba`
- `urlmon!ReleaseBindInfo` at `0x180b5c4ba`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c11e`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c1b1`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c1c8`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c3bb`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c41f`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c11e`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c1b1`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c1c8`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c3bb`
- `OLEAUT32!__imp_SysAllocString` at `0x180b5c41f`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c4aa`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c538`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c547`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c556`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c565`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c4aa`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c538`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c547`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c556`
- `OLEAUT32!__imp_SysFreeString` at `0x180b5c565`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180b5c496`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180b5c496`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180b5c281`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180b5c281`

## pseudocode

```c
__int64 __fastcall CFrameWebOC::Navigate(
        CFrameWebOC *this,
        int a2,
        struct IBindCtx *a3,
        OLECHAR *a4,
        struct IHlink *a5)
{
  unsigned int v5; // ebx
  OLECHAR *v8; // r12
  unsigned __int16 *v9; // r13
  __int64 v10; // rsi
  OLECHAR *v11; // rdi
  struct IUnknown *v12; // rcx
  OLECHAR *v13; // rbx
  int v14; // edx
  int v15; // edi
  SAFEARRAY *v16; // r14
  SAFEARRAY *Vector; // rax
  int v18; // eax
  WCHAR *v19; // rbx
  const WCHAR *v20; // rdi
  PWSTR v21; // rax
  void *v22; // rsi
  const OLECHAR *v23; // rcx
  OLECHAR *v24; // rsi
  unsigned int v26; // [rsp+50h] [rbp-B8h]
  unsigned __int16 *v27; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v28; // [rsp+80h] [rbp-88h]
  OLECHAR *v29; // [rsp+88h] [rbp-80h] BYREF
  PCWSTR pszFirst; // [rsp+90h] [rbp-78h] BYREF
  LPBC ppbc; // [rsp+98h] [rbp-70h] BYREF
  int v32; // [rsp+A0h] [rbp-68h] BYREF
  struct IUnknown *v33; // [rsp+A8h] [rbp-60h] BYREF
  int v34; // [rsp+B0h] [rbp-58h] BYREF
  struct IUnknown *v35; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-48h] BYREF
  struct IUnknown *v37; // [rsp+C8h] [rbp-40h] BYREF
  IUri *ppURI; // [rsp+D0h] [rbp-38h] BYREF
  LPCWSTR pwzURI; // [rsp+D8h] [rbp-30h] BYREF
  OLECHAR *v40; // [rsp+E0h] [rbp-28h] BYREF
  OLECHAR *v41; // [rsp+E8h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+F0h] [rbp-18h]
  CFrameWebOC *v43; // [rsp+F8h] [rbp-10h]
  struct tagVARIANT v44; // [rsp+100h] [rbp-8h] BYREF
  struct tagVARIANT v45; // [rsp+118h] [rbp+10h] BYREF
  BINDINFO pbindinfo; // [rsp+138h] [rbp+30h] BYREF
  OLECHAR psz[264]; // [rsp+1B8h] [rbp+B0h] BYREF

  v5 = -2147467259;
  v43 = this;
  v37 = 0;
  v8 = 0;
  ppbc = 0;
  v9 = 0;
  pwzURI = 0;
  ppURI = 0;
  v27 = 0;
  v40 = 0;
  v41 = 0;
  if ( !a5 || (v10 = -1, a5 == (struct IHlink *)-1LL) )
  {
    v11 = 0;
    v24 = 0;
    goto LABEL_57;
  }
  ((void (__fastcall *)(struct IHlink *, OLECHAR **))a5->lpVtbl->GetTargetFrameName)(a5, &v41);
  v11 = 0;
  v5 = ((__int64 (__fastcall *)(struct IHlink *, __int64, struct IUnknown **, OLECHAR **))a5->lpVtbl->GetMonikerReference)(
         a5,
         1,
         &v37,
         &v40);
  if ( v5 )
    goto LABEL_55;
  if ( !a3 )
  {
    v5 = CreateBindCtx(0, &ppbc);
    if ( !v5 )
      goto LABEL_13;
LABEL_55:
    v24 = 0;
    goto LABEL_57;
  }
  v35 = 0;
  v33 = 0;
  ppbc = a3;
  ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
  ((void (__fastcall *)(LPBC, const wchar_t *, struct IUnknown **))ppbc->lpVtbl->GetObjectParam)(
    ppbc,
    L"__HTMLLOADOPTIONS",
    &v35);
  if ( !v35 )
  {
LABEL_10:
    v12 = v33;
    goto LABEL_11;
  }
  ((void (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v35->lpVtbl->QueryInterface)(
    v35,
    &IID_IHtmlLoadOptions,
    &v33);
  v12 = v33;
  if ( v33 )
  {
    v32 = 520;
    if ( !((unsigned int (__fastcall *)(struct IUnknown *, __int64, OLECHAR *, int *))v33->lpVtbl[1].QueryInterface)(
            v33,
            1,
            psz,
            &v32)
      && v32 )
    {
      v27 = SysAllocString(psz);
    }
    goto LABEL_10;
  }
LABEL_11:
  ReleaseInterface(v12);
  ReleaseInterface(v35);
LABEL_13:
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, LPBC, _QWORD, LPCWSTR *))v37->lpVtbl[6].Release)(
         v37,
         ppbc,
         0,
         &pwzURI);
  if ( v5 || (v5 = CreateUri(pwzURI, 0x3002B85u, 0, &ppURI)) != 0 )
  {
    v11 = v27;
    v24 = 0;
    goto LABEL_57;
  }
  v13 = SysAllocString(v41);
  bstrString = v13;
  v28 = SysAllocString(v40);
  v34 = 0;
  v14 = (4 * (a2 & 2)) | 0x2001;
  if ( a2 >= 0 )
    v14 = (4 * (a2 & 2)) | 1;
  v15 = v14 | 0x80;
  if ( (a2 & 0x200000) == 0 )
    v15 = v14;
  LODWORD(v29) = v15;
  memset_0(&pbindinfo.cbSize + 1, 0, 0x7Cu);
  pbindinfo.cbSize = 128;
  v16 = 0;
  v36 = 0;
  memset(&v45, 0, sizeof(v45));
  memset(&v44, 0, sizeof(v44));
  if ( !a4 )
    goto LABEL_44;
  if ( (*(int (__fastcall **)(OLECHAR *, int *, BINDINFO *))(*(_QWORD *)a4 + 64LL))(a4, &v34, &pbindinfo) >= 0
    && pbindinfo.stgmedData.tymed == 1 )
  {
    if ( pbindinfo.stgmedData.hBitmap )
    {
      if ( pbindinfo.cbstgmedData )
      {
        Vector = SafeArrayCreateVector(0x11u, 0, pbindinfo.cbstgmedData);
        v16 = Vector;
        if ( Vector )
        {
          memcpy_s(Vector->pvData, pbindinfo.cbstgmedData, pbindinfo.stgmedData.hBitmap, pbindinfo.cbstgmedData);
          v45.llVal = (LONGLONG)v16;
          v45.vt = 8209;
        }
      }
    }
  }
  v18 = (**(__int64 (__fastcall ***)(OLECHAR *, GUID *, __int64 *))a4)(a4, &IID_IHttpNegotiate, &v36);
  a4 = 0;
  if ( v18 < 0 )
    goto LABEL_44;
  pszFirst = 0;
  if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, PCWSTR *))(*(_QWORD *)v36 + 24LL))(
         v36,
         0,
         0,
         0,
         &pszFirst) < 0 )
  {
    v23 = pszFirst;
LABEL_40:
    if ( v23 && *v23 )
    {
      v8 = SysAllocString(v23);
      v44.vt = 8;
      v44.llVal = (LONGLONG)v8;
    }
    goto LABEL_43;
  }
  v19 = (WCHAR *)pszFirst;
  if ( pszFirst )
  {
    do
      ++v10;
    while ( pszFirst[v10] );
    v20 = &pszFirst[v10];
    while ( v19 < v20 )
    {
      v21 = StrStrIW(v19, L"\r\n");
      if ( !v21 )
      {
        *v19 = 0;
        break;
      }
      v22 = v21 + 2;
      if ( !StrCmpNIW(v19, L"Accept-Language:", 16) )
      {
        memmove_0(v19, v22, 2 * (((char *)v20 - (_BYTE *)v22) >> 1) + 2);
        break;
      }
      v19 = (WCHAR *)v22;
    }
    v23 = pszFirst;
    if ( !*pszFirst )
    {
      CoTaskMemFree((LPVOID)pszFirst);
      v23 = 0;
      pszFirst = 0;
    }
    v15 = (int)v29;
    goto LABEL_40;
  }
LABEL_43:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  CoTaskMemFree((LPVOID)pszFirst);
  v13 = bstrString;
LABEL_44:
  if ( ppbc )
  {
    v29 = a4;
    if ( !(unsigned int)GetBindContextParam(ppbc, (struct CStr *)&v29, 0) )
      v9 = SysAllocString(v29);
    CStr::_Free((CStr *)&v29);
  }
  v24 = v28;
  v26 = v15;
  v11 = v27;
  v5 = CWindow::SuperNavigateInternal(
         *((CWindow **)v43 + 7),
         ppURI,
         v28,
         v27,
         v13,
         v9,
         &v45,
         (struct IStream *)a4,
         &v44,
         v26,
         (unsigned int)a4,
         (struct IBindCtx *)a4,
         (int *)a4);
  if ( v16 )
    SafeArrayDestroy(v16);
  if ( v8 )
    SysFreeString(v8);
  ReleaseBindInfo(&pbindinfo);
  v8 = bstrString;
LABEL_57:
  ReleaseInterface(v37);
  ReleaseInterface((struct IUnknown *)ppbc);
  ReleaseInterface((struct IUnknown *)ppURI);
  CoTaskMemFree((LPVOID)pwzURI);
  CoTaskMemFree(v40);
  CoTaskMemFree(v41);
  SysFreeString(v8);
  SysFreeString(v11);
  SysFreeString(v24);
  SysFreeString(v9);
  return v5;
}

```

## disassembly

```asm
0x180b5bfb0  mov     rax, rsp
0x180b5bfb3  mov     [rax+20h], r9
0x180b5bfb7  mov     [rax+18h], r8
0x180b5bfbb  mov     [rax+10h], edx
0x180b5bfbe  mov     [rax+8], rcx
0x180b5bfc2  push    rbp
0x180b5bfc3  push    rbx
0x180b5bfc4  push    rsi
0x180b5bfc5  push    rdi
0x180b5bfc6  push    r12
0x180b5bfc8  push    r13
0x180b5bfca  push    r14
0x180b5bfcc  push    r15
0x180b5bfce  lea     rbp, [rax-318h]
0x180b5bfd5  sub     rsp, 3D8h
0x180b5bfdc  mov     rax, cs:__security_cookie
0x180b5bfe3  xor     rax, rsp
0x180b5bfe6  mov     [rbp+310h+var_50], rax
0x180b5bfed  mov     rax, [rbp+310h+arg_0]
0x180b5bff4  mov     ebx, 80004005h
0x180b5bff9  mov     rdi, [rbp+310h+arg_20]
0x180b5c000  mov     r14, [rbp+310h+arg_10]
0x180b5c007  mov     r15, [rbp+310h+arg_18]
0x180b5c00e  mov     [rbp+310h+var_320], rax
0x180b5c012  xor     eax, eax
0x180b5c014  mov     [rbp+310h+var_350], rax
0x180b5c018  mov     r12d, eax
0x180b5c01b  mov     [rbp+310h+ppbc], rax
0x180b5c01f  mov     r13d, eax
0x180b5c022  mov     [rbp+310h+pwzURI], rax
0x180b5c026  mov     [rbp+310h+ppURI], rax
0x180b5c02a  mov     [rsp+410h+var_3A0], rax
0x180b5c02f  mov     [rbp+310h+var_338], rax
0x180b5c033  mov     [rbp+310h+var_330], rax
0x180b5c037  test    rdi, rdi
0x180b5c03a  jz      loc_180B5C4D5
0x180b5c040  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180b5c044  cmp     rdi, rsi
0x180b5c047  jz      loc_180B5C4D5
0x180b5c04d  mov     rax, [rdi]
0x180b5c050  lea     rdx, [rbp+310h+var_330]
0x180b5c054  mov     rcx, rdi
0x180b5c057  mov     rax, [rax+60h]
0x180b5c05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c060  mov     rax, [rdi]
0x180b5c063  lea     r9, [rbp+310h+var_338]
0x180b5c067  lea     r8, [rbp+310h+var_350]
0x180b5c06b  mov     rcx, rdi
0x180b5c06e  lea     edx, [rsi+2]
0x180b5c071  mov     rax, [rax+30h]
0x180b5c075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c07a  xor     edi, edi
0x180b5c07c  mov     ebx, eax
0x180b5c07e  test    eax, eax
0x180b5c080  jnz     loc_180B5C4DD
0x180b5c086  test    r14, r14
0x180b5c089  jz      loc_180B5C143
0x180b5c08f  mov     [rbp+310h+var_360], rdi
0x180b5c093  mov     rcx, r14
0x180b5c096  mov     [rbp+310h+var_370], rdi
0x180b5c09a  mov     [rbp+310h+ppbc], r14
0x180b5c09e  mov     rax, [r14]
0x180b5c0a1  mov     rax, [rax+8]
0x180b5c0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c0aa  mov     rcx, [rbp+310h+ppbc]
0x180b5c0ae  lea     r8, [rbp+310h+var_360]
0x180b5c0b2  lea     rdx, aHtmlloadoption; "__HTMLLOADOPTIONS"
0x180b5c0b9  mov     rax, [rcx]
0x180b5c0bc  mov     rax, [rax+50h]
0x180b5c0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c0c5  mov     rcx, [rbp+310h+var_360]
0x180b5c0c9  test    rcx, rcx
0x180b5c0cc  jz      short loc_180B5C12F
0x180b5c0ce  mov     rax, [rcx]
0x180b5c0d1  lea     r8, [rbp+310h+var_370]
0x180b5c0d5  lea     rdx, IID_IHtmlLoadOptions
0x180b5c0dc  mov     rax, [rax]
0x180b5c0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c0e4  mov     rcx, [rbp+310h+var_370]
0x180b5c0e8  test    rcx, rcx
0x180b5c0eb  jz      short loc_180B5C133
0x180b5c0ed  mov     [rbp+310h+var_378], 208h
0x180b5c0f4  lea     r9, [rbp+310h+var_378]
0x180b5c0f8  mov     rax, [rcx]
0x180b5c0fb  lea     r8, [rbp+310h+psz]
0x180b5c102  lea     edx, [rsi+2]
0x180b5c105  mov     rax, [rax+18h]
0x180b5c109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c10e  test    eax, eax
0x180b5c110  jnz     short loc_180B5C12F
0x180b5c112  cmp     [rbp+310h+var_378], edi
0x180b5c115  jz      short loc_180B5C12F
0x180b5c117  lea     rcx, [rbp+310h+psz]; psz
0x180b5c11e  call    cs:__imp_SysAllocString
0x180b5c125  nop     dword ptr [rax+rax+00h]
0x180b5c12a  mov     [rsp+410h+var_3A0], rax
0x180b5c12f  mov     rcx, [rbp+310h+var_370]; struct IUnknown *
0x180b5c133  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180b5c138  mov     rcx, [rbp+310h+var_360]; struct IUnknown *
0x180b5c13c  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180b5c141  jmp     short loc_180B5C15F
0x180b5c143  lea     rdx, [rbp+310h+ppbc]; ppbc
0x180b5c147  xor     ecx, ecx; reserved
0x180b5c149  call    cs:__imp_CreateBindCtx
0x180b5c150  nop     dword ptr [rax+rax+00h]
0x180b5c155  mov     ebx, eax
0x180b5c157  test    eax, eax
0x180b5c159  jnz     loc_180B5C4DD
0x180b5c15f  mov     rcx, [rbp+310h+var_350]
0x180b5c163  lea     r9, [rbp+310h+pwzURI]
0x180b5c167  mov     rdx, [rbp+310h+ppbc]
0x180b5c16b  xor     r8d, r8d
0x180b5c16e  mov     rax, [rcx]
0x180b5c171  mov     rax, [rax+0A0h]
0x180b5c178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c17d  mov     ebx, eax
0x180b5c17f  test    eax, eax
0x180b5c181  jnz     loc_180B5C4E2
0x180b5c187  mov     rcx, [rbp+310h+pwzURI]; pwzURI
0x180b5c18b  lea     r9, [rbp+310h+ppURI]; ppURI
0x180b5c18f  xor     r8d, r8d; dwReserved
0x180b5c192  mov     edx, 3002B85h; dwFlags
0x180b5c197  call    cs:__imp_CreateUri
0x180b5c19e  nop     dword ptr [rax+rax+00h]
0x180b5c1a3  mov     ebx, eax
0x180b5c1a5  test    eax, eax
0x180b5c1a7  jnz     loc_180B5C4E2
0x180b5c1ad  mov     rcx, [rbp+310h+var_330]; psz
0x180b5c1b1  call    cs:__imp_SysAllocString
0x180b5c1b8  nop     dword ptr [rax+rax+00h]
0x180b5c1bd  mov     rcx, [rbp+310h+var_338]; psz
0x180b5c1c1  mov     rbx, rax
0x180b5c1c4  mov     [rbp+310h+bstrString], rax
0x180b5c1c8  call    cs:__imp_SysAllocString
0x180b5c1cf  nop     dword ptr [rax+rax+00h]
0x180b5c1d4  mov     r8d, [rbp+310h+arg_8]
0x180b5c1db  mov     ecx, r8d
0x180b5c1de  and     ecx, 2
0x180b5c1e1  mov     [rsp+78h], rax
0x180b5c1e6  shl     ecx, 2
0x180b5c1e9  or      ecx, 1
0x180b5c1ec  mov     [rbp+310h+var_368], r12d
0x180b5c1f0  mov     edx, ecx
0x180b5c1f2  bts     edx, 0Dh
0x180b5c1f6  test    r8d, r8d
0x180b5c1f9  cmovns  edx, ecx
0x180b5c1fc  lea     rcx, [rbp+310h+pbindinfo+4]; void *
0x180b5c200  mov     edi, edx
0x180b5c202  bts     edi, 7
0x180b5c206  bt      r8d, 15h
0x180b5c20b  cmovnb  edi, edx
0x180b5c20e  xor     edx, edx; Val
0x180b5c210  mov     dword ptr [rbp+310h+var_390], edi
0x180b5c213  lea     r8d, [rdx+7Ch]; Size
0x180b5c217  call    memset_0
0x180b5c21c  xor     eax, eax
0x180b5c21e  mov     [rbp+310h+pbindinfo.cbSize], 80h
0x180b5c225  xor     r14d, r14d
0x180b5c228  mov     qword ptr [rbp+310h+var_300+10h], rax
0x180b5c22c  mov     qword ptr [rbp+310h+var_318+10h], rax
0x180b5c230  xorps   xmm0, xmm0
0x180b5c233  mov     [rbp+310h+var_358], rax
0x180b5c237  xorps   xmm1, xmm1
0x180b5c23a  movups  xmmword ptr [rbp+310h+var_300], xmm0
0x180b5c23e  movups  xmmword ptr [rbp+310h+var_318], xmm1
0x180b5c242  test    r15, r15
0x180b5c245  jz      loc_180B5C3FE
0x180b5c24b  mov     rax, [r15]
0x180b5c24e  lea     r8, [rbp+310h+pbindinfo]
0x180b5c252  lea     rdx, [rbp+310h+var_368]
0x180b5c256  mov     rcx, r15
0x180b5c259  mov     rax, [rax+40h]
0x180b5c25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c262  test    eax, eax
0x180b5c264  js      short loc_180B5C2BC
0x180b5c266  cmp     [rbp+310h+pbindinfo.stgmedData.tymed], 1
0x180b5c26a  jnz     short loc_180B5C2BC
0x180b5c26c  cmp     qword ptr [rbp+310h+pbindinfo.stgmedData.8], r12
0x180b5c270  jz      short loc_180B5C2BC
0x180b5c272  mov     r8d, [rbp+310h+pbindinfo.cbstgmedData]; cElements
0x180b5c276  test    r8d, r8d
0x180b5c279  jz      short loc_180B5C2BC
0x180b5c27b  lea     ecx, [r14+11h]; vt
0x180b5c27f  xor     edx, edx; lLbound
0x180b5c281  call    cs:__imp_SafeArrayCreateVector
0x180b5c288  nop     dword ptr [rax+rax+00h]
0x180b5c28d  mov     r14, rax
0x180b5c290  test    rax, rax
0x180b5c293  jz      short loc_180B5C2BC
0x180b5c295  mov     edx, [rbp+310h+pbindinfo.cbstgmedData]; DestinationSize
0x180b5c298  mov     r8, qword ptr [rbp+310h+pbindinfo.stgmedData.8]; Source
0x180b5c29c  mov     r9d, edx; SourceSize
0x180b5c29f  mov     rcx, [rax+10h]; Destination
0x180b5c2a3  call    cs:__imp_memcpy_s
0x180b5c2aa  nop     dword ptr [rax+rax+00h]
0x180b5c2af  mov     eax, 2011h
0x180b5c2b4  mov     qword ptr [rbp+310h+var_300+8], r14
0x180b5c2b8  mov     word ptr [rbp+310h+var_300], ax
0x180b5c2bc  mov     rax, [r15]
0x180b5c2bf  lea     r8, [rbp+310h+var_358]
0x180b5c2c3  lea     rdx, IID_IHttpNegotiate
0x180b5c2ca  mov     rcx, r15
0x180b5c2cd  mov     rax, [rax]
0x180b5c2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c2d5  xor     r15d, r15d
0x180b5c2d8  test    eax, eax
0x180b5c2da  js      loc_180B5C3FE
0x180b5c2e0  mov     rcx, [rbp+310h+var_358]
0x180b5c2e4  lea     rdx, [rbp+310h+pszFirst]
0x180b5c2e8  mov     [rbp+310h+pszFirst], r15
0x180b5c2ec  xor     r9d, r9d
0x180b5c2ef  mov     [rsp+410h+var_3F0], rdx
0x180b5c2f4  xor     r8d, r8d
0x180b5c2f7  xor     edx, edx
0x180b5c2f9  mov     rax, [rcx]
0x180b5c2fc  mov     rax, [rax+18h]
0x180b5c300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c305  test    eax, eax
0x180b5c307  js      loc_180B5C4CC
0x180b5c30d  mov     rbx, [rbp+310h+pszFirst]
0x180b5c311  test    rbx, rbx
0x180b5c314  jz      loc_180B5C3D7
0x180b5c31a  inc     rsi
0x180b5c31d  cmp     [rbx+rsi*2], r15w
0x180b5c322  jnz     short loc_180B5C31A
0x180b5c324  lea     rdi, [rbx+rsi*2]
0x180b5c328  cmp     rbx, rdi
0x180b5c32b  jnb     short loc_180B5C390
0x180b5c32d  lea     rdx, asc_18143B398; "\r\n"
0x180b5c334  mov     rcx, rbx; pszFirst
0x180b5c337  call    cs:__imp_StrStrIW
0x180b5c33e  nop     dword ptr [rax+rax+00h]
0x180b5c343  test    rax, rax
0x180b5c346  jz      short loc_180B5C38C
0x180b5c348  mov     r8d, 10h; nChar
0x180b5c34e  lea     rdx, aAcceptLanguage_2; "Accept-Language:"
0x180b5c355  mov     rcx, rbx; psz1
0x180b5c358  lea     rsi, [rax+4]
0x180b5c35c  call    cs:__imp_StrCmpNIW
0x180b5c363  nop     dword ptr [rax+rax+00h]
0x180b5c368  test    eax, eax
0x180b5c36a  jz      short loc_180B5C371
0x180b5c36c  mov     rbx, rsi
0x180b5c36f  jmp     short loc_180B5C328
0x180b5c371  sub     rdi, rsi
0x180b5c374  mov     rdx, rsi; Src
0x180b5c377  sar     rdi, 1
0x180b5c37a  mov     rcx, rbx; void *
0x180b5c37d  lea     r8, ds:2[rdi*2]; Size
0x180b5c385  call    memmove_0
0x180b5c38a  jmp     short loc_180B5C390
0x180b5c38c  mov     [rbx], r15w
0x180b5c390  mov     rcx, [rbp+310h+pszFirst]; pv
0x180b5c394  cmp     [rcx], r15w
0x180b5c398  jnz     short loc_180B5C3AD
0x180b5c39a  call    cs:__imp_CoTaskMemFree
0x180b5c3a1  nop     dword ptr [rax+rax+00h]
0x180b5c3a6  mov     rcx, r15; psz
0x180b5c3a9  mov     [rbp+310h+pszFirst], rcx
0x180b5c3ad  mov     edi, dword ptr [rbp+310h+var_390]
0x180b5c3b0  test    rcx, rcx
0x180b5c3b3  jz      short loc_180B5C3D7
0x180b5c3b5  cmp     [rcx], r15w
0x180b5c3b9  jz      short loc_180B5C3D7
0x180b5c3bb  call    cs:__imp_SysAllocString
0x180b5c3c2  nop     dword ptr [rax+rax+00h]
0x180b5c3c7  mov     r12, rax
0x180b5c3ca  mov     eax, 8
0x180b5c3cf  mov     word ptr [rbp+310h+var_318], ax
0x180b5c3d3  mov     qword ptr [rbp+310h+var_318+8], r12
0x180b5c3d7  mov     rdx, [rbp+310h+var_358]
0x180b5c3db  mov     rcx, [rdx]
0x180b5c3de  mov     rax, [rcx+10h]
0x180b5c3e2  mov     rcx, rdx
0x180b5c3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5c3ea  mov     rcx, [rbp+310h+pszFirst]; pv
0x180b5c3ee  call    cs:__imp_CoTaskMemFree
0x180b5c3f5  nop     dword ptr [rax+rax+00h]
0x180b5c3fa  mov     rbx, [rbp+310h+bstrString]
0x180b5c3fe  mov     rcx, [rbp+310h+ppbc]; struct IBindCtx *
0x180b5c402  test    rcx, rcx
0x180b5c405  jz      short loc_180B5C437
0x180b5c407  xor     r8d, r8d; unsigned __int16 *
0x180b5c40a  mov     [rbp+310h+var_390], r15
0x180b5c40e  lea     rdx, [rbp+310h+var_390]; struct CStr *
0x180b5c412  call    ?GetBindContextParam@@YAJPEAUIBindCtx@@PEAVCStr@@PEAG@Z; GetBindContextParam(IBindCtx *,CStr *,ushort *)
0x180b5c417  test    eax, eax
0x180b5c419  jnz     short loc_180B5C42E
0x180b5c41b  mov     rcx, [rbp+310h+var_390]; psz
0x180b5c41f  call    cs:__imp_SysAllocString
0x180b5c426  nop     dword ptr [rax+rax+00h]
0x180b5c42b  mov     r13, rax
0x180b5c42e  lea     rcx, [rbp+310h+var_390]; this
0x180b5c432  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180b5c437  mov     rcx, [rbp+310h+var_320]
0x180b5c43b  lea     rax, [rbp+310h+var_318]
0x180b5c43f  mov     rsi, [rsp+78h]
0x180b5c444  mov     rdx, [rbp+310h+ppURI]; struct IUri *
0x180b5c448  mov     r8, rsi; unsigned __int16 *
0x180b5c44b  mov     [rsp+60h], r15; int *
  ... truncated ...
```
