# CContentDirectoryFolder::_GetPidlFromCdsObjectId(ushort const *,_ITEMID_CHILD * *)

- ea: `0x180018b94`
- end: `0x18001928f`
- name: `?_GetPidlFromCdsObjectId@CContentDirectoryFolder@@AEAAJPEBGPEAPEAU_ITEMID_CHILD@@@Z`
- size: `1787`
- prototype: `__int64 __fastcall(CContentDirectoryFolder *__hidden this, const unsigned __int16 *, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x180016af0`

## callees

- `0x1800097c0`
- `0x18000ab30`
- `0x18000ab48`
- `0x18000bc18`
- `0x18000bca4`
- `0x180011930`
- `0x1800140e4`
- `0x180014a00`
- `0x180014b90`
- `0x180015204`
- `0x180017a8c`
- `0x180017fcc`
- `0x1800185f4`
- `0x180018b94`
- `0x1800198d4`
- `0x18002cba0`
- `0x18002cbe0`
- `0x18002f378`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018d3d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018d53`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018d3d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018d53`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180018cd4`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180018cd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180018d68`
- `OLEAUT32!__imp_SysFreeString` at `0x180018d68`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180018e00`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180018e00`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180018da5`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180018da5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180018de2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180018de2`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CContentDirectoryFolder::_GetPidlFromCdsObjectId(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        struct _ITEMID_CHILD **a3)
{
  unsigned int v6; // r12d
  HRESULT CDSHandler; // edi
  HSTRING v8; // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 i; // rbx
  LPITEMIDLIST *v12; // rax
  struct CContentDirectory *v13; // r14
  const unsigned __int16 *v14; // rax
  UINT32 v15; // edi
  const WCHAR *v16; // rax
  const WCHAR *v17; // r13
  struct IPropertyStore *v18; // r14
  const WCHAR *v19; // rcx
  char *v20; // r8
  int v21; // eax
  int v22; // edx
  int v23; // eax
  const WCHAR *v24; // rbx
  char *v25; // rax
  signed __int64 v26; // r8
  int v27; // ecx
  int v28; // edx
  int v29; // eax
  int v30; // ecx
  __int64 v31; // r8
  struct CContentDirectory *v32; // rax
  struct _ITEMID_CHILD **v33; // r14
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  struct CContentDirectory *v36; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpStringSource; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v38; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v39; // [rsp+70h] [rbp-90h] BYREF
  char *v40; // [rsp+78h] [rbp-88h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *Str; // [rsp+88h] [rbp-78h] BYREF
  struct _ITEMID_CHILD **v43; // [rsp+90h] [rbp-70h]
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  PROPERTYKEY v45; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR ppszExt; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  int v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v53; // [rsp+F8h] [rbp-8h]
  __int64 v54; // [rsp+100h] [rbp+0h]
  int v55; // [rsp+108h] [rbp+8h]
  WCHAR pszPath[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v57[520]; // [rsp+320h] [rbp+220h] BYREF

  v43 = a3;
  v6 = 0;
  v51 = 0;
  v38 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  string = 0;
  *a3 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids, a2);
  }
  CDSHandler = CCDSResultsParser::UnescapeObjectID(a2, &string);
  if ( CDSHandler < 0 )
  {
    CDSHandler = -2147023693;
    goto LABEL_83;
  }
  v8 = string;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !(unsigned int)CContentDirectoryFolder::_BrowseCdsObject(
                        this,
                        this,
                        StringRawBuffer,
                        0,
                        96,
                        &v47,
                        0,
                        1,
                        &v38,
                        &v41) )
  {
    v10 = v48;
    if ( v48 )
    {
      *a3 = *(struct _ITEMID_CHILD **)ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(&v47);
      for ( i = 1; i < v10; ++i )
      {
        v12 = (LPITEMIDLIST *)ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(&v47);
        ILFree(*v12);
      }
      goto LABEL_83;
    }
  }
  v36 = 0;
  CDSHandler = CContentDirectoryFolder::_GetCDSHandler((CContentDirectoryFolder *)this, this[12], &v36);
  if ( CDSHandler < 0 )
    goto LABEL_81;
  Str = 0;
  v13 = v36;
  CDSHandler = (*(__int64 (__fastcall **)(struct CContentDirectory *, wchar_t **))(*(_QWORD *)v36 + 32LL))(v36, &Str);
  if ( CDSHandler < 0 )
    goto LABEL_81;
  if ( !wcsstr(Str, L"dc:title") && !wcsstr(Str, L"*") )
    CDSHandler = -2147467263;
  SysFreeString(Str);
  if ( CDSHandler < 0 )
    goto LABEL_81;
  v14 = WindowsGetStringRawBuffer(v8, 0);
  CDSHandler = StringCchCopyW(pszPath, 0x104u, v14);
  if ( CDSHandler < 0 )
    goto LABEL_81;
  CDSHandler = PathCchRemoveExtension(pszPath, 0x104u);
  if ( CDSHandler < 0 )
    goto LABEL_81;
  CDSHandler = StringCchPrintfW(v57, 0x208u, L"dc:title = \"%ws\"", pszPath);
  if ( CDSHandler < 0 )
    goto LABEL_81;
  ppszExt = 0;
  v15 = WindowsGetStringLen(v8) + 1;
  v16 = WindowsGetStringRawBuffer(v8, 0);
  CDSHandler = PathCchFindExtension(v16, v15, &ppszExt);
  if ( CDSHandler < 0 )
    goto LABEL_81;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v41 = 0;
  v17 = &String1;
  CDSHandler = (*(__int64 (__fastcall **)(struct CContentDirectory *, unsigned __int16 *, const wchar_t *, const WCHAR *, _DWORD, _DWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)v13 + 24LL))(
                 v13,
                 v57,
                 L"*",
                 &String1,
                 0,
                 0,
                 &v41,
                 &v38,
                 &v52);
  if ( CDSHandler < 0 )
    goto LABEL_80;
  if ( !v38 )
  {
    CDSHandler = -2147023693;
    goto LABEL_80;
  }
  if ( v38 > 1
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids);
  }
  while ( 1 )
  {
    if ( CDSHandler < 0 || v6 >= v53 )
    {
      v33 = v43;
      goto LABEL_78;
    }
    v18 = *(struct IPropertyStore **)ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(&v52);
    CPropertyStoreHelper::CPropertyStoreHelper((CPropertyStoreHelper *)&v35, v18);
    lpStringSource = 0;
    v40 = 0;
    v39 = 0;
    v45 = PKEY_FileExtension;
    CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v35, &v45, &v39);
    v19 = &String1;
    if ( v39 )
      v19 = v39;
    v20 = (char *)((char *)ppszExt - (char *)v19);
    do
    {
      v21 = *(unsigned __int16 *)&v20[(_QWORD)v19];
      v22 = *v19 - v21;
      if ( v22 )
        break;
      ++v19;
    }
    while ( v21 );
    if ( v22 )
    {
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v39);
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v40);
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpStringSource);
      if ( v35 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        v35 = 0;
      }
      goto LABEL_76;
    }
    v45.fmtid = (GUID)PKEY_ParentID;
    v45.pid = 5;
    v23 = CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v35, &v45, &v40);
    v24 = (const WCHAR *)v40;
    if ( v23 < 0 )
      break;
    v25 = (char *)this[12];
    if ( v25 )
    {
      v26 = v40 - v25;
      do
      {
        v27 = *(unsigned __int16 *)&v25[v26];
        v28 = *(unsigned __int16 *)v25 - v27;
        if ( v28 )
          break;
        v25 += 2;
      }
      while ( v27 );
      if ( v28 )
      {
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v39);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v40);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpStringSource);
        if ( v35 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          v35 = 0;
        }
        goto LABEL_76;
      }
      break;
    }
    v29 = *(unsigned __int16 *)v40;
    v30 = 48 - v29;
    if ( v29 == 48 )
      v30 = -*((unsigned __int16 *)v40 + 1);
    if ( !v30 )
      break;
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v39);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v40);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpStringSource);
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
    }
LABEL_76:
    ++v6;
  }
  v45 = PKEY_ItemClass;
  CDSHandler = CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v35, &v45, &lpStringSource);
  if ( CDSHandler < 0 )
  {
LABEL_74:
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v39);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v40);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpStringSource);
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
    }
    goto LABEL_76;
  }
  v36 = 0;
  if ( CCDSResultsParser::IsContainerClass(lpStringSource) )
  {
    v31 = 1;
  }
  else
  {
    if ( !CCDSResultsParser::IsItemClass(lpStringSource) )
    {
      CDSHandler = -2147023693;
LABEL_73:
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v36);
      goto LABEL_74;
    }
    v31 = 2;
  }
  CDSHandler = CContentDirectoryFolder::_CreateItemFromPropertyStore(this, v18, v31, &v36);
  if ( CDSHandler < 0 )
    goto LABEL_73;
  v32 = v36;
  if ( !v36 )
    goto LABEL_73;
  v36 = 0;
  v33 = v43;
  *v43 = v32;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( v24 )
      v17 = v24;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids, v17);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v36);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v39);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v40);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpStringSource);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
LABEL_78:
  if ( !*v33 )
    CDSHandler = -2147023693;
LABEL_80:
  ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::~CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>(&v52);
  if ( CDSHandler < 0 )
  {
LABEL_81:
    if ( CDSHandler != -2147467263 )
      CDSHandler = -2147023693;
  }
LABEL_83:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::~CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>(&v47);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v51);
  return (unsigned int)CDSHandler;
}

```

## disassembly

```asm
0x180018b94  mov     [rsp-8+arg_18], rbx
0x180018b99  push    rbp
0x180018b9a  push    rsi
0x180018b9b  push    rdi
0x180018b9c  push    r12
0x180018b9e  push    r13
0x180018ba0  push    r14
0x180018ba2  push    r15
0x180018ba4  lea     rbp, [rsp-640h]
0x180018bac  sub     rsp, 740h
0x180018bb3  mov     rax, cs:__security_cookie
0x180018bba  xor     rax, rsp
0x180018bbd  mov     [rbp+670h+var_40], rax
0x180018bc4  mov     r14, r8
0x180018bc7  mov     [rbp+670h+var_6E0], r8
0x180018bcb  mov     rbx, rdx
0x180018bce  mov     r15, rcx
0x180018bd1  xor     r12d, r12d
0x180018bd4  mov     [rbp+670h+var_688], r12
0x180018bd8  mov     [rsp+770h+var_708], r12d
0x180018bdd  mov     [rbp+670h+var_6A8], r12
0x180018be1  mov     [rbp+670h+var_6A0], r12
0x180018be5  mov     [rbp+670h+var_698], r12
0x180018be9  mov     [rbp+670h+var_690], r12d
0x180018bed  mov     [rbp+670h+string], r12
0x180018bf1  mov     [r8], r12
0x180018bf4  lea     rax, WPP_GLOBAL_Control
0x180018bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c02  cmp     rcx, rax
0x180018c05  jz      short loc_180018C2B
0x180018c07  test    byte ptr [rcx+1Ch], 40h
0x180018c0b  jz      short loc_180018C2B
0x180018c0d  cmp     byte ptr [rcx+19h], 4
0x180018c11  jb      short loc_180018C2B
0x180018c13  lea     edx, [r12+0Bh]
0x180018c18  mov     r9, rbx
0x180018c1b  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x180018c22  mov     rcx, [rcx+10h]
0x180018c26  call    WPP_SF_S
0x180018c2b  lea     rdx, [rbp+670h+string]; HSTRING *
0x180018c2f  mov     rcx, rbx; unsigned __int16 *
0x180018c32  call    ?UnescapeObjectID@CCDSResultsParser@@SAJPEBGPEAPEAUHSTRING__@@@Z; CCDSResultsParser::UnescapeObjectID(ushort const *,HSTRING__ * *)
0x180018c37  mov     edi, eax
0x180018c39  test    eax, eax
0x180018c3b  jns     short loc_180018C47
0x180018c3d  mov     edi, 800704B3h
0x180018c42  jmp     loc_180019246
0x180018c47  xor     edx, edx; length
0x180018c49  mov     rbx, [rbp+670h+string]
0x180018c4d  mov     rcx, rbx; string
0x180018c50  call    cs:__imp_WindowsGetStringRawBuffer
0x180018c56  lea     rcx, [rbp+670h+var_6F0]
0x180018c5a  mov     [rsp+770h+var_728], rcx
0x180018c5f  lea     rcx, [rsp+770h+var_708]
0x180018c64  mov     [rsp+770h+var_730], rcx
0x180018c69  mov     r13d, 1
0x180018c6f  mov     dword ptr [rsp+770h+var_738], r13d
0x180018c74  mov     dword ptr [rsp+770h+var_740], r12d
0x180018c79  lea     rcx, [rbp+670h+var_6A8]
0x180018c7d  mov     [rsp+770h+var_748], rcx
0x180018c82  mov     [rsp+770h+var_750], 60h ; '`'
0x180018c8a  xor     r9d, r9d
0x180018c8d  mov     r8, rax
0x180018c90  mov     rdx, r15
0x180018c93  mov     rcx, r15
0x180018c96  call    ?_BrowseCdsObject@CContentDirectoryFolder@@AEAAJ_KPEBG_NKAEAV?$CAtlArray@PEAU_ITEMID_CHILD@@V?$CElementTraits@PEAU_ITEMID_CHILD@@@ATL@@@ATL@@KKPEAK4@Z; CContentDirectoryFolder::_BrowseCdsObject(unsigned __int64,ushort const *,bool,ulong,ATL::CAtlArray<_ITEMID_CHILD *,ATL::CElementTraits<_ITEMID_CHILD *>> &,ulong,ulong,ulong *,ulong *)
0x180018c9b  test    eax, eax
0x180018c9d  jnz     short loc_180018CE7
0x180018c9f  mov     rsi, [rbp+670h+var_6A0]
0x180018ca3  test    rsi, rsi
0x180018ca6  jz      short loc_180018CE7
0x180018ca8  xor     edx, edx
0x180018caa  lea     rcx, [rbp+670h+var_6A8]
0x180018cae  call    ?GetAt@?$CAtlArray@PEAUIPropertyStore@@V?$CElementTraits@PEAUIPropertyStore@@@ATL@@@ATL@@QEAAAEAPEAUIPropertyStore@@_K@Z; ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(unsigned __int64)
0x180018cb3  mov     rcx, [rax]
0x180018cb6  mov     [r14], rcx
0x180018cb9  mov     ebx, r13d
0x180018cbc  cmp     rsi, r13
0x180018cbf  jbe     loc_180019246
0x180018cc5  mov     rdx, rbx
0x180018cc8  lea     rcx, [rbp+670h+var_6A8]
0x180018ccc  call    ?GetAt@?$CAtlArray@PEAUIPropertyStore@@V?$CElementTraits@PEAUIPropertyStore@@@ATL@@@ATL@@QEAAAEAPEAUIPropertyStore@@_K@Z; ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(unsigned __int64)
0x180018cd1  mov     rcx, [rax]; pidl
0x180018cd4  call    cs:__imp_ILFree
0x180018cda  add     rbx, r13
0x180018cdd  cmp     rbx, rsi
0x180018ce0  jb      short loc_180018CC5
0x180018ce2  jmp     loc_180019246
0x180018ce7  mov     [rsp+770h+var_718], r12
0x180018cec  lea     r8, [rsp+770h+var_718]; struct CContentDirectory **
0x180018cf1  mov     rdx, [r15+60h]; unsigned __int16 *
0x180018cf5  mov     rcx, r15; this
0x180018cf8  call    ?_GetCDSHandler@CContentDirectoryFolder@@AEAAJPEBGPEAPEAVCContentDirectory@@@Z; CContentDirectoryFolder::_GetCDSHandler(ushort const *,CContentDirectory * *)
0x180018cfd  mov     edi, eax
0x180018cff  mov     esi, 800704B3h
0x180018d04  test    eax, eax
0x180018d06  js      loc_18001923D
0x180018d0c  mov     [rbp+670h+Str], r12
0x180018d10  mov     r14, [rsp+770h+var_718]
0x180018d15  mov     rax, [r14]
0x180018d18  lea     rdx, [rbp+670h+Str]
0x180018d1c  mov     rcx, r14
0x180018d1f  mov     rax, [rax+20h]
0x180018d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d28  mov     edi, eax
0x180018d2a  test    eax, eax
0x180018d2c  js      loc_18001923D
0x180018d32  lea     rdx, aDcTitle; "dc:title"
0x180018d39  mov     rcx, [rbp+670h+Str]; Str
0x180018d3d  call    cs:__imp_wcsstr
0x180018d43  test    rax, rax
0x180018d46  jnz     short loc_180018D64
0x180018d48  lea     rdx, Src; "*"
0x180018d4f  mov     rcx, [rbp+670h+Str]; Str
0x180018d53  call    cs:__imp_wcsstr
0x180018d59  test    rax, rax
0x180018d5c  mov     eax, 80004001h
0x180018d61  cmovz   edi, eax
0x180018d64  mov     rcx, [rbp+670h+Str]; bstrString
0x180018d68  call    cs:__imp_SysFreeString
0x180018d6e  test    edi, edi
0x180018d70  js      loc_18001923D
0x180018d76  xor     edx, edx; length
0x180018d78  mov     rcx, rbx; string
0x180018d7b  call    cs:__imp_WindowsGetStringRawBuffer
0x180018d81  mov     r8, rax; unsigned __int16 *
0x180018d84  mov     edx, 104h; unsigned __int64
0x180018d89  lea     rcx, [rbp+670h+pszPath]; unsigned __int16 *
0x180018d8d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018d92  mov     edi, eax
0x180018d94  test    eax, eax
0x180018d96  js      loc_18001923D
0x180018d9c  mov     edx, 104h; cchPath
0x180018da1  lea     rcx, [rbp+670h+pszPath]; pszPath
0x180018da5  call    cs:__imp_PathCchRemoveExtension
0x180018dab  mov     edi, eax
0x180018dad  test    eax, eax
0x180018daf  js      loc_18001923D
0x180018db5  lea     r9, [rbp+670h+pszPath]
0x180018db9  lea     r8, aDcTitleWs; "dc:title = \"%ws\""
0x180018dc0  mov     edx, 208h; unsigned __int64
0x180018dc5  lea     rcx, [rbp+670h+var_450]; unsigned __int16 *
0x180018dcc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018dd1  mov     edi, eax
0x180018dd3  test    eax, eax
0x180018dd5  js      loc_18001923D
0x180018ddb  mov     [rbp+670h+ppszExt], r12
0x180018ddf  mov     rcx, rbx; string
0x180018de2  call    cs:__imp_WindowsGetStringLen
0x180018de8  lea     edi, [rax+r13]
0x180018dec  xor     edx, edx; length
0x180018dee  mov     rcx, rbx; string
0x180018df1  call    cs:__imp_WindowsGetStringRawBuffer
0x180018df7  lea     r8, [rbp+670h+ppszExt]; ppszExt
0x180018dfb  mov     edx, edi; cchPath
0x180018dfd  mov     rcx, rax; pszPath
0x180018e00  call    cs:__imp_PathCchFindExtension
0x180018e06  mov     edi, eax
0x180018e08  test    eax, eax
0x180018e0a  js      loc_18001923D
0x180018e10  mov     [rbp+670h+var_680], r12
0x180018e14  mov     [rbp+670h+var_678], r12
0x180018e18  mov     [rbp+670h+var_670], r12
0x180018e1c  mov     [rbp+670h+var_668], r12d
0x180018e20  mov     [rbp+670h+var_6F0], r12d
0x180018e24  mov     rax, [r14]
0x180018e27  lea     rcx, [rbp+670h+var_680]
0x180018e2b  mov     [rsp+770h+var_730], rcx
0x180018e30  lea     rcx, [rsp+770h+var_708]
0x180018e35  mov     [rsp+770h+var_738], rcx
0x180018e3a  lea     rcx, [rbp+670h+var_6F0]
0x180018e3e  mov     [rsp+770h+var_740], rcx
0x180018e43  mov     dword ptr [rsp+770h+var_748], r12d
0x180018e48  mov     [rsp+770h+var_750], r12d
0x180018e4d  lea     r13, String1
0x180018e54  mov     r9, r13
0x180018e57  lea     r8, Src; "*"
0x180018e5e  lea     rdx, [rbp+670h+var_450]
0x180018e65  mov     rcx, r14
0x180018e68  mov     rax, [rax+18h]
0x180018e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e71  mov     edi, eax
0x180018e73  test    eax, eax
0x180018e75  js      loc_180019230
0x180018e7b  mov     eax, [rsp+770h+var_708]
0x180018e7f  test    eax, eax
0x180018e81  jnz     short loc_180018E8A
0x180018e83  mov     edi, esi
0x180018e85  jmp     loc_180019230
0x180018e8a  cmp     eax, 1
0x180018e8d  jbe     short loc_180018EC3
0x180018e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e96  lea     rax, WPP_GLOBAL_Control
0x180018e9d  cmp     rcx, rax
0x180018ea0  jz      short loc_180018EC3
0x180018ea2  test    byte ptr [rcx+1Ch], 40h
0x180018ea6  jz      short loc_180018EC3
0x180018ea8  cmp     byte ptr [rcx+19h], 4
0x180018eac  jb      short loc_180018EC3
0x180018eae  mov     edx, 0Ch
0x180018eb3  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x180018eba  mov     rcx, [rcx+10h]
0x180018ebe  call    WPP_SF_
0x180018ec3  test    edi, edi
0x180018ec5  js      loc_180019223
0x180018ecb  mov     edx, r12d
0x180018ece  cmp     rdx, [rbp+670h+var_678]
0x180018ed2  jnb     loc_180019223
0x180018ed8  lea     rcx, [rbp+670h+var_680]
0x180018edc  call    ?GetAt@?$CAtlArray@PEAUIPropertyStore@@V?$CElementTraits@PEAUIPropertyStore@@@ATL@@@ATL@@QEAAAEAPEAUIPropertyStore@@_K@Z; ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(unsigned __int64)
0x180018ee1  mov     r14, [rax]
0x180018ee4  mov     rdx, r14; struct IPropertyStore *
0x180018ee7  lea     rcx, [rsp+770h+var_720]; this
0x180018eec  call    ??0CPropertyStoreHelper@@QEAA@PEAUIPropertyStore@@@Z; CPropertyStoreHelper::CPropertyStoreHelper(IPropertyStore *)
0x180018ef1  nop
0x180018ef2  mov     [rsp+770h+lpStringSource], 0
0x180018efb  mov     [rsp+770h+var_6F8], 0
0x180018f04  mov     [rsp+770h+var_700], 0
0x180018f0d  movups  xmm0, xmmword ptr cs:PKEY_FileExtension.fmtid.Data1
0x180018f14  movaps  [rbp+670h+var_6D0], xmm0
0x180018f18  mov     eax, cs:PKEY_FileExtension.pid
0x180018f1e  mov     [rbp+670h+var_6C0], eax
0x180018f21  lea     r8, [rsp+770h+var_700]
0x180018f26  lea     rdx, [rbp+670h+var_6D0]
0x180018f2a  lea     rcx, [rsp+770h+var_720]
0x180018f2f  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180018f34  mov     rcx, r13
0x180018f37  mov     rax, [rsp+770h+var_700]
0x180018f3c  test    rax, rax
0x180018f3f  cmovnz  rcx, rax
0x180018f43  mov     r8, [rbp+670h+ppszExt]
0x180018f47  sub     r8, rcx
0x180018f4a  movzx   edx, word ptr [rcx]
0x180018f4d  movzx   eax, word ptr [rcx+r8]
0x180018f52  sub     edx, eax
0x180018f54  jnz     short loc_180018F5E
0x180018f56  add     rcx, 2
0x180018f5a  test    eax, eax
0x180018f5c  jnz     short loc_180018F4A
0x180018f5e  test    edx, edx
0x180018f60  jz      short loc_180018FA7
0x180018f62  lea     rcx, [rsp+770h+var_700]
0x180018f67  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180018f6c  nop
0x180018f6d  lea     rcx, [rsp+770h+var_6F8]
0x180018f72  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180018f77  nop
0x180018f78  lea     rcx, [rsp+770h+lpStringSource]
0x180018f7d  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180018f82  nop
0x180018f83  mov     rcx, [rsp+770h+var_720]
0x180018f88  test    rcx, rcx
0x180018f8b  jz      short loc_180018FA2
0x180018f8d  mov     rax, [rcx]
0x180018f90  mov     rax, [rax+10h]
0x180018f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f99  mov     [rsp+770h+var_720], 0
0x180018fa2  jmp     loc_18001921B
0x180018fa7  movups  xmm0, cs:PKEY_ParentID
0x180018fae  movaps  [rbp+670h+var_6D0], xmm0
0x180018fb2  mov     eax, cs:dword_18003B9A8
0x180018fb8  mov     [rbp+670h+var_6C0], eax
0x180018fbb  lea     r8, [rsp+770h+var_6F8]
0x180018fc0  lea     rdx, [rbp+670h+var_6D0]
0x180018fc4  lea     rcx, [rsp+770h+var_720]
0x180018fc9  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180018fce  mov     rbx, [rsp+770h+var_6F8]
0x180018fd3  test    eax, eax
0x180018fd5  js      loc_1800190AB
0x180018fdb  mov     rax, [r15+60h]
0x180018fdf  test    rax, rax
0x180018fe2  jz      short loc_18001904B
0x180018fe4  mov     r8, rbx
0x180018fe7  sub     r8, rax
0x180018fea  movzx   edx, word ptr [rax]
0x180018fed  movzx   ecx, word ptr [rax+r8]
0x180018ff2  sub     edx, ecx
0x180018ff4  jnz     short loc_180018FFE
0x180018ff6  add     rax, 2
0x180018ffa  test    ecx, ecx
0x180018ffc  jnz     short loc_180018FEA
0x180018ffe  test    edx, edx
0x180019000  jz      loc_1800190AB
0x180019006  lea     rcx, [rsp+770h+var_700]
0x18001900b  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180019010  nop
0x180019011  lea     rcx, [rsp+770h+var_6F8]
0x180019016  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001901b  nop
0x18001901c  lea     rcx, [rsp+770h+lpStringSource]
0x180019021  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180019026  nop
0x180019027  mov     rcx, [rsp+770h+var_720]
0x18001902c  test    rcx, rcx
0x18001902f  jz      short loc_180019046
0x180019031  mov     rax, [rcx]
0x180019034  mov     rax, [rax+10h]
0x180019038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001903d  mov     [rsp+770h+var_720], 0
0x180019046  jmp     loc_18001921B
  ... truncated ...
```
