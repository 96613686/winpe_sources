# _AfxOleMakeSymbolTable(_AFX_OLESYMBOLTABLE &,_GUID const &,wchar_t const *,wchar_t const *,wchar_t const *,int,wchar_t const *,wchar_t const *)

- ea: `0x18026f028`
- end: `0x18026f4a5`
- name: `?_AfxOleMakeSymbolTable@@YAHAEAV_AFX_OLESYMBOLTABLE@@AEBU_GUID@@PEB_W22H22@Z`
- size: `1149`
- prototype: `int __fastcall(_AFX_OLESYMBOLTABLE *refTable, const _GUID *clsid, const wchar_t *lpszClassName, const wchar_t *lpszShortTypeName, const wchar_t *lpszLongTypeName, int nIconIndex, const wchar_t *lpszFilterName, const wchar_t *lpszFilterExt)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18026f500`
- `0x18026f660`

## callees

- `0x180002b60`
- `0x180002e40`
- `0x180003450`
- `0x18000dc50`
- `0x18000e0e0`
- `0x180012d20`
- `0x180012eb0`
- `0x180139860`
- `0x1801d5b60`
- `0x180233590`
- `0x18026efd8`
- `0x18026f028`
- `0x180270350`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!wcschr` at `0x18026f26d`
- `VCRUNTIME140!wcschr` at `0x18026f2ef`
- `VCRUNTIME140!wcschr` at `0x18026f36c`
- `VCRUNTIME140!wcschr` at `0x18026f26d`
- `VCRUNTIME140!wcschr` at `0x18026f2ef`
- `VCRUNTIME140!wcschr` at `0x18026f36c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026f21b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026f242`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026f21b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026f242`
- `USER32!DestroyIcon` at `0x18026f1a5`
- `USER32!DestroyIcon` at `0x18026f1a5`
- `ole32!CoTaskMemFree` at `0x18026f093`
- `ole32!CoTaskMemFree` at `0x18026f093`
- `ole32!StringFromCLSID` at `0x18026f059`
- `ole32!StringFromCLSID` at `0x18026f059`
- `SHELL32!ExtractIconW` at `0x18026f197`
- `SHELL32!ExtractIconW` at `0x18026f197`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall _AfxOleMakeSymbolTable(
        _AFX_OLESYMBOLTABLE *refTable,
        const _GUID *clsid,
        const wchar_t *lpszClassName,
        const wchar_t *lpszShortTypeName,
        wchar_t *lpszLongTypeName,
        UINT nIconIndex,
        wchar_t *lpszFilterName,
        wchar_t *lpszFilterExt)
{
  wchar_t *v11; // rbx
  AFX_MODULE_STATE *ModuleState; // rax
  wchar_t *m_pszData; // rbx
  AFX_MODULE_STATE *v14; // rax
  UINT v15; // edi
  AFX_MODULE_STATE *v16; // rax
  HICON IconW; // rax
  int v18; // eax
  int v19; // eax
  wchar_t *v20; // rbx
  wchar_t *v21; // rax
  __int64 v22; // rax
  wchar_t *v23; // rdx
  wchar_t *v24; // rbx
  wchar_t *v25; // rax
  __int64 v26; // rax
  wchar_t *v27; // rdx
  wchar_t *v28; // rbx
  wchar_t *v29; // rax
  __int64 v30; // rax
  const ATL::CSimpleStringT<wchar_t,0> *v31; // rax
  wchar_t *v32; // rdx
  wchar_t *v33; // rbx
  wchar_t *v34; // rdx
  wchar_t *v35; // rdx
  wchar_t *v36; // rdx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strFileExtension; // [rsp+20h] [rbp-30h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strPathNameQuoted; // [rsp+28h] [rbp-28h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strIconIndex; // [rsp+30h] [rbp-20h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strPathName; // [rsp+38h] [rbp-18h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > result; // [rsp+40h] [rbp-10h] BYREF
  wchar_t *lpOleStr; // [rsp+48h] [rbp-8h] BYREF

  if ( StringFromCLSID(clsid, &lpOleStr) < 0 )
    return 0;
  v11 = lpOleStr;
  if ( !lpOleStr )
    return 0;
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 0, lpOleStr);
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 1, lpszClassName);
  CoTaskMemFree(v11);
  strPathName.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  ModuleState = AfxGetModuleState();
  AfxGetModuleFileName(ModuleState->m_hCurrentInstanceHandle, &strPathName);
  strPathNameQuoted.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(&strPathNameQuoted, "\"");
  m_pszData = strPathName.m_pszData;
  ATL::CSimpleStringT<wchar_t,1>::Append(
    &strPathNameQuoted,
    strPathName.m_pszData,
    *((_DWORD *)strPathName.m_pszData - 4));
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&strPathNameQuoted, "\"");
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 2, strPathNameQuoted.m_pszData);
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 3, lpszShortTypeName);
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 4, lpszLongTypeName);
  v14 = AfxGetModuleState();
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 5, v14->m_lpszCurrentAppName);
  strIconIndex.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  v15 = nIconIndex;
  if ( nIconIndex )
  {
    v16 = AfxGetModuleState();
    IconW = ExtractIconW(v16->m_hCurrentInstanceHandle, m_pszData, nIconIndex);
    if ( IconW )
      DestroyIcon(IconW);
    else
      v15 = 0;
  }
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(&strIconIndex, L"%d", v15);
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 6, strIconIndex.m_pszData);
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 7, lpszFilterName);
  strFileExtension.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  if ( lpszFilterExt && *lpszFilterExt )
  {
    v18 = wcslen(lpszFilterExt);
    ATL::CSimpleStringT<wchar_t,1>::SetString(&strFileExtension, lpszFilterExt, v18);
  }
  else
  {
    if ( lpszFilterName )
      v19 = wcslen(lpszFilterName);
    else
      v19 = 0;
    ATL::CSimpleStringT<wchar_t,1>::SetString(&strFileExtension, lpszFilterName, v19);
    v20 = strFileExtension.m_pszData;
    if ( *((int *)strFileExtension.m_pszData - 4) <= 0 )
      goto LABEL_28;
    v21 = wcschr(strFileExtension.m_pszData, 0x28u);
    if ( !v21 )
      goto LABEL_28;
    v22 = v21 - v20;
    if ( (_DWORD)v22 == -1 )
      goto LABEL_28;
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
      &strFileExtension,
      &result,
      v22 + 1,
      *((_DWORD *)v20 - 4) - (v22 + 1));
    ATL::CSimpleStringT<wchar_t,1>::operator=(&strFileExtension, (const ATL::CSimpleStringT<wchar_t,0> *)&result);
    v23 = result.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)result.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
    v24 = strFileExtension.m_pszData;
    if ( *((int *)strFileExtension.m_pszData - 4) <= 0 )
      goto LABEL_28;
    v25 = wcschr(strFileExtension.m_pszData, 0x2Eu);
    if ( !v25 )
      goto LABEL_28;
    v26 = v25 - v24;
    if ( (_DWORD)v26 == -1 )
      goto LABEL_28;
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
      &strFileExtension,
      &result,
      v26,
      *((_DWORD *)v24 - 4) - v26);
    ATL::CSimpleStringT<wchar_t,1>::operator=(&strFileExtension, (const ATL::CSimpleStringT<wchar_t,0> *)&result);
    v27 = result.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)result.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
    v28 = strFileExtension.m_pszData;
    if ( *((int *)strFileExtension.m_pszData - 4) <= 0
      || (v29 = wcschr(strFileExtension.m_pszData, 0x29u)) == 0
      || (v30 = v29 - v28, (_DWORD)v30 == -1) )
    {
LABEL_28:
      ATL::CSimpleStringT<wchar_t,1>::Empty(&strFileExtension);
    }
    else
    {
      v31 = (const ATL::CSimpleStringT<wchar_t,0> *)ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Left(
                                                      &strFileExtension,
                                                      &result,
                                                      v30);
      ATL::CSimpleStringT<wchar_t,1>::operator=(&strFileExtension, v31);
      v32 = result.m_pszData - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)result.m_pszData - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v32 + 8LL))(*(_QWORD *)v32);
    }
  }
  v33 = strFileExtension.m_pszData;
  _AFX_OLESYMBOLTABLE::SetAt(refTable, 8, strFileExtension.m_pszData);
  if ( _InterlockedDecrement((volatile signed __int32 *)v33 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v33 - 3) + 8LL))(*((_QWORD *)v33 - 3));
  v34 = strIconIndex.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strIconIndex.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 8LL))(*(_QWORD *)v34);
  v35 = strPathNameQuoted.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strPathNameQuoted.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 8LL))(*(_QWORD *)v35);
  v36 = strPathName.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strPathName.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v36 + 8LL))(*(_QWORD *)v36);
  return 1;
}

```

## disassembly

```asm
0x18026f028  mov     [rsp-18h+arg_0], rbx
0x18026f02d  mov     [rsp-18h+arg_8], rsi
0x18026f032  mov     [rsp-18h+arg_10], rdi
0x18026f037  push    rbp
0x18026f038  push    r14
0x18026f03a  push    r15
0x18026f03c  mov     rbp, rsp
0x18026f03f  sub     rsp, 50h
0x18026f043  mov     rdi, lpszShortTypeName
0x18026f046  mov     r14, lpszClassName
0x18026f049  mov     rax, clsid
0x18026f04c  mov     rsi, refTable
0x18026f04f  xor     r15d, r15d
0x18026f052  lea     clsid, [rbp+lpOleStr]; lplpsz
0x18026f056  mov     refTable, rax; rclsid
0x18026f059  call    cs:__imp_StringFromCLSID
0x18026f05f  test    eax, eax
0x18026f061  js      loc_18026F489
0x18026f067  mov     rbx, [rbp+lpOleStr]
0x18026f06b  test    rbx, rbx
0x18026f06e  jz      loc_18026F489
0x18026f074  mov     lpszClassName, rbx; pstr
0x18026f077  xor     edx, edx; nIndex
0x18026f079  mov     refTable, rsi; this
0x18026f07c  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f081  mov     lpszClassName, r14; pstr
0x18026f084  lea     edx, [r15+1]; nIndex
0x18026f088  mov     refTable, rsi; this
0x18026f08b  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f090  mov     refTable, rbx; pv
0x18026f093  call    cs:__imp_CoTaskMemFree
0x18026f099  nop
0x18026f09a  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026f0a1  lea     r14, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18026f0a8  mov     refTable, r14
0x18026f0ab  mov     rax, [rax+18h]
0x18026f0af  call    cs:__guard_dispatch_icall_fptr
0x18026f0b5  add     rax, 18h
0x18026f0b9  mov     [rbp+strPathName.m_pszData], rax
0x18026f0bd  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18026f0c2  lea     clsid, [rbp+strPathName]; strFileName
0x18026f0c6  mov     refTable, [rax+10h]; hInst
0x18026f0ca  call    ?AfxGetModuleFileName@@YAXPEAUHINSTANCE__@@AEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z; AfxGetModuleFileName(HINSTANCE__ *,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18026f0cf  nop
0x18026f0d0  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026f0d7  mov     refTable, r14
0x18026f0da  mov     rax, [rax+18h]
0x18026f0de  call    cs:__guard_dispatch_icall_fptr
0x18026f0e4  add     rax, 18h
0x18026f0e8  mov     [rbp+strPathNameQuoted.m_pszData], rax
0x18026f0ec  lea     clsid, asc_18035B5E4; "\""
0x18026f0f3  lea     refTable, [rbp+strPathNameQuoted]; this
0x18026f0f7  call    ??4?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(char const *)
0x18026f0fc  mov     rbx, [rbp+strPathName.m_pszData]
0x18026f100  mov     r8d, [rbx-10h]; nLength
0x18026f104  mov     clsid, rbx; pszSrc
0x18026f107  lea     refTable, [rbp+strPathNameQuoted]; this
0x18026f10b  call    ?Append@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::Append(wchar_t const *,int)
0x18026f110  lea     clsid, asc_18035B5E4; "\""
0x18026f117  lea     refTable, [rbp+strPathNameQuoted]; this
0x18026f11b  call    ??Y?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x18026f120  mov     lpszClassName, [rbp+strPathNameQuoted.m_pszData]; pstr
0x18026f124  lea     edx, [r15+2]; nIndex
0x18026f128  mov     refTable, rsi; this
0x18026f12b  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f130  mov     lpszClassName, rdi; pstr
0x18026f133  lea     edx, [r15+3]; nIndex
0x18026f137  mov     refTable, rsi; this
0x18026f13a  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f13f  mov     lpszClassName, [rbp+pstr]; pstr
0x18026f143  lea     edx, [r15+4]; nIndex
0x18026f147  mov     refTable, rsi; this
0x18026f14a  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f14f  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18026f154  mov     lpszClassName, [rax+20h]; pstr
0x18026f158  lea     edx, [r15+5]; nIndex
0x18026f15c  mov     refTable, rsi; this
0x18026f15f  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f164  nop
0x18026f165  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026f16c  mov     refTable, r14
0x18026f16f  mov     rax, [rax+18h]
0x18026f173  call    cs:__guard_dispatch_icall_fptr
0x18026f179  add     rax, 18h
0x18026f17d  mov     [rbp+strIconIndex.m_pszData], rax
0x18026f181  mov     edi, [rbp+arg_28]
0x18026f184  test    edi, edi
0x18026f186  jz      short loc_18026F1B0
0x18026f188  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18026f18d  mov     r8d, edi; nIconIndex
0x18026f190  mov     clsid, rbx; pszExeFileName
0x18026f193  mov     refTable, [rax+10h]; hInst
0x18026f197  call    cs:__imp_ExtractIconW
0x18026f19d  test    rax, rax
0x18026f1a0  jz      short loc_18026F1AD
0x18026f1a2  mov     refTable, rax; hIcon
0x18026f1a5  call    cs:__imp_DestroyIcon
0x18026f1ab  jmp     short loc_18026F1B0
0x18026f1ad  mov     edi, r15d
0x18026f1b0  mov     r8d, edi
0x18026f1b3  lea     clsid, aD; "%d"
0x18026f1ba  lea     refTable, [rbp+strIconIndex]; this
0x18026f1be  call    ?Format@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x18026f1c3  mov     lpszClassName, [rbp+strIconIndex.m_pszData]; pstr
0x18026f1c7  mov     edx, 6; nIndex
0x18026f1cc  mov     refTable, rsi; this
0x18026f1cf  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f1d4  mov     rdi, [rbp+pszSrc]
0x18026f1d8  mov     lpszClassName, rdi; pstr
0x18026f1db  mov     edx, 7; nIndex
0x18026f1e0  mov     refTable, rsi; this
0x18026f1e3  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f1e8  nop
0x18026f1e9  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026f1f0  mov     refTable, r14
0x18026f1f3  mov     rax, [rax+18h]
0x18026f1f7  call    cs:__guard_dispatch_icall_fptr
0x18026f1fd  add     rax, 18h
0x18026f201  mov     [rbp+strFileExtension.m_pszData], rax
0x18026f205  or      r14d, 0FFFFFFFFh
0x18026f209  mov     rbx, [rbp+String]
0x18026f20d  test    rbx, rbx
0x18026f210  jz      short loc_18026F235
0x18026f212  cmp     [rbx], r15w
0x18026f216  jz      short loc_18026F235
0x18026f218  mov     refTable, rbx; String
0x18026f21b  call    cs:__imp_wcslen
0x18026f221  mov     r8d, eax; nLength
0x18026f224  mov     clsid, rbx; pszSrc
0x18026f227  lea     refTable, [rbp+strFileExtension]; this
0x18026f22b  call    ?SetString@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::SetString(wchar_t const *,int)
0x18026f230  jmp     loc_18026F3D2
0x18026f235  test    rdi, rdi
0x18026f238  jnz     short loc_18026F23F
0x18026f23a  mov     eax, r15d
0x18026f23d  jmp     short loc_18026F248
0x18026f23f  mov     refTable, rdi; String
0x18026f242  call    cs:__imp_wcslen
0x18026f248  mov     r8d, eax; nLength
0x18026f24b  mov     clsid, rdi; pszSrc
0x18026f24e  lea     refTable, [rbp+strFileExtension]; this
0x18026f252  call    ?SetString@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::SetString(wchar_t const *,int)
0x18026f257  mov     rbx, [rbp+strFileExtension.m_pszData]
0x18026f25b  cmp     [rbx-10h], r15d
0x18026f25f  jle     loc_18026F3C9
0x18026f265  mov     edx, 28h ; '('; Ch
0x18026f26a  mov     refTable, rbx; Str
0x18026f26d  call    cs:__imp_wcschr
0x18026f273  test    rax, rax
0x18026f276  jz      loc_18026F3C9
0x18026f27c  sub     rax, rbx
0x18026f27f  sar     rax, 1
0x18026f282  cmp     eax, r14d
0x18026f285  jz      loc_18026F3C9
0x18026f28b  lea     r8d, [rax+1]; iFirst
0x18026f28f  mov     r9d, [rbx-10h]
0x18026f293  sub     r9d, r8d; nCount
0x18026f296  lea     clsid, [rbp+result]; result
0x18026f29a  lea     refTable, [rbp+strFileExtension]; this
0x18026f29e  call    ?Mid@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(int,int)
0x18026f2a3  nop
0x18026f2a4  lea     clsid, [rbp+result]; strSrc
0x18026f2a8  lea     refTable, [rbp+strFileExtension]; this
0x18026f2ac  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x18026f2b1  nop
0x18026f2b2  mov     clsid, [rbp+result.m_pszData]
0x18026f2b6  add     clsid, 0FFFFFFFFFFFFFFE8h
0x18026f2ba  mov     eax, r14d
0x18026f2bd  lock xadd [clsid+10h], eax
0x18026f2c2  add     eax, r14d
0x18026f2c5  test    eax, eax
0x18026f2c7  jg      short loc_18026F2D9
0x18026f2c9  mov     refTable, [clsid]
0x18026f2cc  mov     rax, [refTable]
0x18026f2cf  mov     rax, [rax+8]
0x18026f2d3  call    cs:__guard_dispatch_icall_fptr
0x18026f2d9  mov     rbx, [rbp+strFileExtension.m_pszData]
0x18026f2dd  cmp     [rbx-10h], r15d
0x18026f2e1  jle     loc_18026F3C9
0x18026f2e7  mov     edx, 2Eh ; '.'; Ch
0x18026f2ec  mov     refTable, rbx; Str
0x18026f2ef  call    cs:__imp_wcschr
0x18026f2f5  test    rax, rax
0x18026f2f8  jz      loc_18026F3C9
0x18026f2fe  sub     rax, rbx
0x18026f301  sar     rax, 1
0x18026f304  cmp     eax, r14d
0x18026f307  jz      loc_18026F3C9
0x18026f30d  mov     r9d, [rbx-10h]
0x18026f311  sub     r9d, eax; nCount
0x18026f314  mov     r8d, eax; iFirst
0x18026f317  lea     clsid, [rbp+result]; result
0x18026f31b  lea     refTable, [rbp+strFileExtension]; this
0x18026f31f  call    ?Mid@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(int,int)
0x18026f324  nop
0x18026f325  lea     clsid, [rbp+result]; strSrc
0x18026f329  lea     refTable, [rbp+strFileExtension]; this
0x18026f32d  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x18026f332  nop
0x18026f333  mov     clsid, [rbp+result.m_pszData]
0x18026f337  add     clsid, 0FFFFFFFFFFFFFFE8h
0x18026f33b  mov     eax, r14d
0x18026f33e  lock xadd [clsid+10h], eax
0x18026f343  add     eax, r14d
0x18026f346  test    eax, eax
0x18026f348  jg      short loc_18026F35A
0x18026f34a  mov     refTable, [clsid]
0x18026f34d  mov     rax, [refTable]
0x18026f350  mov     rax, [rax+8]
0x18026f354  call    cs:__guard_dispatch_icall_fptr
0x18026f35a  mov     rbx, [rbp+strFileExtension.m_pszData]
0x18026f35e  cmp     [rbx-10h], r15d
0x18026f362  jle     short loc_18026F3C9
0x18026f364  mov     edx, 29h ; ')'; Ch
0x18026f369  mov     refTable, rbx; Str
0x18026f36c  call    cs:__imp_wcschr
0x18026f372  test    rax, rax
0x18026f375  jz      short loc_18026F3C9
0x18026f377  sub     rax, rbx
0x18026f37a  sar     rax, 1
0x18026f37d  cmp     eax, r14d
0x18026f380  jz      short loc_18026F3C9
0x18026f382  mov     r8d, eax; nCount
0x18026f385  lea     clsid, [rbp+result]; result
0x18026f389  lea     refTable, [rbp+strFileExtension]; this
0x18026f38d  call    ?Left@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Left(int)
0x18026f392  nop
0x18026f393  mov     clsid, rax; strSrc
0x18026f396  lea     refTable, [rbp+strFileExtension]; this
0x18026f39a  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x18026f39f  nop
0x18026f3a0  mov     clsid, [rbp+result.m_pszData]
0x18026f3a4  add     clsid, 0FFFFFFFFFFFFFFE8h
0x18026f3a8  mov     eax, r14d
0x18026f3ab  lock xadd [clsid+10h], eax
0x18026f3b0  add     eax, r14d
0x18026f3b3  test    eax, eax
0x18026f3b5  jg      short loc_18026F3D2
0x18026f3b7  mov     refTable, [clsid]
0x18026f3ba  mov     rax, [refTable]
0x18026f3bd  mov     rax, [rax+8]
0x18026f3c1  call    cs:__guard_dispatch_icall_fptr
0x18026f3c7  jmp     short loc_18026F3D2
0x18026f3c9  lea     refTable, [rbp+strFileExtension]; this
0x18026f3cd  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x18026f3d2  mov     rbx, [rbp+strFileExtension.m_pszData]
0x18026f3d6  mov     lpszClassName, rbx; pstr
0x18026f3d9  mov     edx, 8; nIndex
0x18026f3de  mov     refTable, rsi; this
0x18026f3e1  call    ?SetAt@_AFX_OLESYMBOLTABLE@@QEAAXHPEB_W@Z; _AFX_OLESYMBOLTABLE::SetAt(int,wchar_t const *)
0x18026f3e6  nop
0x18026f3e7  lea     clsid, [rbx-18h]
0x18026f3eb  mov     eax, r14d
0x18026f3ee  lock xadd [clsid+10h], eax
0x18026f3f3  add     eax, r14d
0x18026f3f6  test    eax, eax
0x18026f3f8  jg      short loc_18026F40B
0x18026f3fa  mov     refTable, [clsid]
0x18026f3fd  mov     rax, [refTable]
0x18026f400  mov     rax, [rax+8]
0x18026f404  call    cs:__guard_dispatch_icall_fptr
0x18026f40a  nop
0x18026f40b  mov     clsid, [rbp+strIconIndex.m_pszData]
0x18026f40f  add     clsid, 0FFFFFFFFFFFFFFE8h
0x18026f413  mov     eax, r14d
0x18026f416  lock xadd [clsid+10h], eax
0x18026f41b  add     eax, r14d
0x18026f41e  test    eax, eax
0x18026f420  jg      short loc_18026F433
0x18026f422  mov     refTable, [clsid]
0x18026f425  mov     rax, [refTable]
0x18026f428  mov     rax, [rax+8]
0x18026f42c  call    cs:__guard_dispatch_icall_fptr
0x18026f432  nop
0x18026f433  mov     clsid, [rbp+strPathNameQuoted.m_pszData]
0x18026f437  add     clsid, 0FFFFFFFFFFFFFFE8h
0x18026f43b  mov     eax, r14d
0x18026f43e  lock xadd [clsid+10h], eax
0x18026f443  add     eax, r14d
0x18026f446  test    eax, eax
0x18026f448  jg      short loc_18026F45B
0x18026f44a  mov     refTable, [clsid]
0x18026f44d  mov     rax, [refTable]
0x18026f450  mov     rax, [rax+8]
0x18026f454  call    cs:__guard_dispatch_icall_fptr
0x18026f45a  nop
0x18026f45b  mov     clsid, [rbp+strPathName.m_pszData]
0x18026f45f  add     clsid, 0FFFFFFFFFFFFFFE8h
0x18026f463  mov     ecx, r14d
0x18026f466  lock xadd [clsid+10h], ecx
0x18026f46b  add     ecx, r14d
0x18026f46e  test    ecx, ecx
0x18026f470  jg      short loc_18026F482
0x18026f472  mov     refTable, [clsid]
0x18026f475  mov     lpszClassName, [refTable]
0x18026f478  mov     rax, [lpszClassName+8]
0x18026f47c  call    cs:__guard_dispatch_icall_fptr
0x18026f482  mov     eax, 1
0x18026f487  jmp     short loc_18026F48B
0x18026f489  xor     eax, eax
  ... truncated ...
```
