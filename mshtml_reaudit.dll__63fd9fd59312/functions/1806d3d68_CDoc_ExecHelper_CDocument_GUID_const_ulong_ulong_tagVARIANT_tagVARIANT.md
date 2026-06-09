# CDoc::ExecHelper(CDocument *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x1806d3d68`
- end: `0x1806dad38`
- name: `?ExecHelper@CDoc@@QEAAJPEAVCDocument@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z`
- size: `28624`
- prototype: `__int64 __fastcall(CDoc *__hidden this, struct CDocument *, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *, VARIANTARG *)`
- caller_count: `10`
- callee_count: `395`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180438bd0`
- `0x1806d3d30`
- `0x1806d3d68`
- `0x1808793d0`
- `0x180889d30`
- `0x18096f950`
- `0x180983630`
- `0x180d13150`
- `0x180e38cf0`
- `0x181024940`

## callees

- `0x180007698`
- `0x1800076b0`
- `0x180008450`
- `0x18000b364`
- `0x18000e08c`
- `0x180010118`
- `0x180012c04`
- `0x180023974`
- `0x18002586c`
- `0x180055f44`
- `0x18007237c`
- `0x1800766e0`
- `0x180077680`
- `0x1800c3950`
- `0x1800c8054`
- `0x1800c86b8`
- `0x1800c8c14`
- `0x1800c8ebc`
- `0x1800c9360`
- `0x1800cafdc`
- `0x1800d6a2c`
- `0x1800d7ea4`
- `0x1800da290`
- `0x1800e2b60`
- `0x1800e2fb8`
- `0x1800e4c70`
- `0x1800f3c4c`
- `0x1800f5454`
- `0x180101ca0`
- `0x18011d004`
- `0x18011f0ac`
- `0x180120b40`
- `0x180121390`
- `0x1801216bc`
- `0x180144d1c`
- `0x180146f6c`
- `0x180154a54`
- `0x180168c80`
- `0x1801711a0`
- `0x1801752ac`
- `0x18019b014`
- `0x18019b034`
- `0x1801a194c`
- `0x1801af6e0`
- `0x1801b0510`
- `0x1801bf588`
- `0x1801c0000`
- `0x1801cd614`
- `0x1801dfa54`
- `0x180217830`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1806d504e`
- `msvcrt!_ultow_s` at `0x1806d504e`
- `msvcrt!wcsrchr` at `0x1806d4c41`
- `msvcrt!wcsrchr` at `0x1806d4c41`
- `KERNEL32!CreateFileW` at `0x1806d4cbd`
- `KERNEL32!CreateFileW` at `0x1806d4cbd`
- `KERNEL32!CloseHandle` at `0x1806d4ccf`
- `KERNEL32!CloseHandle` at `0x1806d4ccf`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806d4c13`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806d4c13`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d4baf`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d4bdf`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d4baf`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d4bdf`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d4c1f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d4c29`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d4c1f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d4c29`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1806d5054`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1806d5054`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d61b8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d6890`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d9f93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806da0d9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806da9a2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d61b8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d6890`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d9f93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806da0d9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806da9a2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1806d61c2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1806d61c2`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x1806d9c42`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x1806d9c42`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806d988f`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806d9b02`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806d988f`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806d9b02`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806d9ca3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806d9ca3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d50f5`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d5125`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d50f5`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d5125`
- `WININET!InternetSetOptionW` at `0x1806d9599`
- `WININET!InternetSetOptionW` at `0x1806d9599`
- `urlmon!__imp_GetMinLayoutWidthFromCVList` at `0x1806d8d99`
- `urlmon!__imp_GetMinLayoutWidthFromCVList` at `0x1806d8d99`
- `ieapfltr!GetUrlBlockClient` at `0x1806d7d6c`
- `ieapfltr!GetUrlBlockClient` at `0x1806d7d6c`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d61f9`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d75c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d7a06`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d8474`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d86a6`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d9c5b`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d61f9`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d75c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d7a06`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d8474`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d86a6`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d9c5b`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d495c`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d7a70`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d7dcd`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d495c`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d7a70`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d7dcd`
- `OLEAUT32!__imp_VariantInit` at `0x1806d56f4`
- `OLEAUT32!__imp_VariantInit` at `0x1806d69fb`
- `OLEAUT32!__imp_VariantInit` at `0x1806d8460`
- `OLEAUT32!__imp_VariantInit` at `0x1806d85a8`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9998`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9aac`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9ab9`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9ac3`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9cbd`
- `OLEAUT32!__imp_VariantInit` at `0x1806da357`
- `OLEAUT32!__imp_VariantInit` at `0x1806da5f2`
- `OLEAUT32!__imp_VariantInit` at `0x1806d56f4`
- `OLEAUT32!__imp_VariantInit` at `0x1806d69fb`
- `OLEAUT32!__imp_VariantInit` at `0x1806d8460`
- `OLEAUT32!__imp_VariantInit` at `0x1806d85a8`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9998`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9aac`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9ab9`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9ac3`
- `OLEAUT32!__imp_VariantInit` at `0x1806d9cbd`
- `OLEAUT32!__imp_VariantInit` at `0x1806da357`
- `OLEAUT32!__imp_VariantInit` at `0x1806da5f2`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4292`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4364`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4383`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4b3f`
- `OLEAUT32!__imp_VariantClear` at `0x1806d9b78`
- `OLEAUT32!__imp_VariantClear` at `0x1806d9b85`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4292`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4364`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4383`
- `OLEAUT32!__imp_VariantClear` at `0x1806d4b3f`
- `OLEAUT32!__imp_VariantClear` at `0x1806d9b78`
- `OLEAUT32!__imp_VariantClear` at `0x1806d9b85`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1806d9c02`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1806d9c02`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d6f0c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d89ab`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d6f0c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d89ab`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d6f47`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d89c6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d9845`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d6f47`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d89c6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d9845`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1806d6f2f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1806d6f2f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d8582`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d89e8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d9824`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d9c1b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d8582`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d89e8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d9824`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d9c1b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806d8a19`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806d9cac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806d8a19`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806d9cac`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d6fdd`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d95fb`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d961b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d9adc`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d9b20`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d9b4b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d6fdd`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d95fb`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d961b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d9adc`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d9b20`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d9b4b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da390`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da3ae`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da3c7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da3e0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da390`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da3ae`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da3c7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806da3e0`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d6f5d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d6f73`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d6f5d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d6f73`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806d8558`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806da36f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806d8558`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806da36f`
- `OLEAUT32!__imp_OleTranslateColor` at `0x1806da4b0`
- `OLEAUT32!__imp_OleTranslateColor` at `0x1806da4b0`

## string_xrefs

- `0x1806d4b8b`: `CLSID\{25336920-03F9-11CF-8FD0-00AA00686F13}`
- `0x1806d4c6e`: `\readme.htm`

## pseudocode

```c
__int64 __fastcall CDoc::ExecHelper(
        CInPlace **this,
        struct CDocument *a2,
        struct _GUID *a3,
        unsigned int a4,
        unsigned int a5,
        struct tagVARIANT *a6,
        VARIANTARG *a7)
{
  VARIANTARG *v7; // r15
  VARIANTARG *v9; // r12
  struct CDocument *v12; // rdi
  HRESULT Text; // esi
  struct CDocument *v15; // rbx
  CInPlace *v16; // rax
  __int64 v17; // rax
  struct IUnknown *v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r13d
  CElement *v21; // rcx
  struct CMarkup *MarkupPtr; // rax
  __int64 v23; // rax
  HRESULT v24; // eax
  ULONG v25; // edi
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  struct CMarkup *v31; // rbx
  unsigned int v32; // ebx
  HRESULT v33; // eax
  CMarkup *v34; // rax
  COmWindowProxy *v35; // rax
  int v36; // eax
  CBase **v37; // rbx
  CElement *v38; // rcx
  CMarkup *v39; // rax
  struct CDocument *v40; // rsi
  CBase *ActiveElement; // rax
  int v42; // r8d
  CInPlace *v43; // rcx
  CInPlace *v44; // rcx
  CInPlace *v45; // rax
  CInPlace *v46; // rbx
  CInPlace *v47; // rdi
  __int64 v48; // rsi
  HWND HWND; // rax
  const unsigned __int16 *v50; // r8
  unsigned int v51; // ebx
  CInPlace *v52; // rcx
  CInPlace *v53; // rcx
  HRESULT v54; // eax
  void *v55; // rcx
  struct CElement *v56; // rax
  CInPlace *v57; // rcx
  unsigned int v58; // edx
  CInPlace *v59; // rcx
  int v60; // esi
  unsigned __int16 *v61; // rax
  __int64 v62; // rcx
  struct CMarkup *v63; // rdx
  CMarkup *v64; // rsi
  COptionsHolder *v65; // rax
  COptionsHolder *v66; // rax
  CWindow *v67; // rbx
  COptionsHolder *v68; // rax
  struct CSecurityContext *v69; // rax
  int v70; // r8d
  int inserted; // eax
  enum _htmlDesignMode v72; // r8d
  CElement *v73; // rcx
  __int64 v74; // rbx
  struct COptionsHolder *v75; // rbx
  COptionsHolder *v76; // rax
  __int64 v77; // rdx
  COptionsHolder *v78; // rax
  unsigned int v79; // edx
  unsigned int v80; // r8d
  __int128 v81; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  struct IDispatch *v83; // rdi
  const unsigned __int16 *v84; // rbx
  CElement *v85; // rax
  struct CMarkup *v86; // rax
  HRESULT v87; // eax
  unsigned int v88; // ecx
  CInPlace *v89; // r10
  CInPlace *v90; // rcx
  __int64 v91; // rcx
  VARIANTARG *p_pvarg; // rcx
  LSTATUS v93; // ebx
  wchar_t *v94; // rax
  __int64 v95; // rax
  HANDLE FileW; // rax
  HRESULT v97; // eax
  bool v98; // sf
  CElement *v99; // rax
  CElement *v100; // rax
  CMarkup *WindowedMarkupContext; // rax
  BSTR v102; // rdi
  signed __int16 v103; // r13
  __int16 BaselineFontPrivate; // ax
  CInPlace *v105; // rax
  wchar_t *v106; // rcx
  __int64 v107; // rdx
  __int64 v108; // rdx
  unsigned __int64 v109; // rax
  CInPlace *v110; // rcx
  CInPlace *v111; // rax
  unsigned int v112; // ecx
  unsigned __int8 v113; // al
  struct CBase *v114; // rax
  CImplAry *v115; // rcx
  int v116; // edx
  const WCHAR *v117; // r12
  unsigned int v118; // r15d
  char *v119; // r8
  unsigned int v120; // ecx
  unsigned __int8 v121; // al
  unsigned __int8 v122; // al
  int v123; // eax
  __int64 v124; // r9
  CInPlace *v125; // rax
  unsigned int v126; // ecx
  unsigned __int8 v127; // al
  int v128; // r13d
  struct CBase *v129; // rdi
  LONG v130; // r12d
  unsigned int v131; // eax
  unsigned __int8 v132; // al
  CElement *v133; // rax
  CMarkup *v134; // rax
  __int64 v135; // rdx
  unsigned int v136; // ebx
  struct CElement *v137; // rax
  CInPlace *v138; // rcx
  struct IUnknown *v139; // rcx
  __int64 v140; // rax
  struct CMarkup *v141; // rax
  CInPlace *v142; // rcx
  CElement *v143; // rcx
  struct CElement *v144; // rax
  __int64 v145; // rax
  __int64 v146; // rbx
  CMarkup *v147; // rbx
  struct CMarkupEditContext *v148; // rax
  CDocument *v149; // rax
  __int64 v150; // rcx
  CMarkup *v151; // rcx
  int v152; // edx
  CInPlace *v153; // rax
  HWND v154; // rbx
  CInPlace *v155; // rax
  HWND v156; // rax
  CWindowBarProp *v157; // rax
  struct CTreeNode *v158; // rax
  CWindowBarProp *v159; // rax
  struct CTreeNode *v160; // rax
  CElement *v161; // rax
  CMarkup *v162; // rsi
  CCollectionCache *v163; // rax
  VARIANTARG *v164; // rbx
  __int64 v165; // rdx
  struct CElement *v166; // rdx
  __int64 v167; // rcx
  CMarkup *v168; // rcx
  int v169; // ebx
  CInPlace *v170; // rcx
  __int64 (__fastcall ***v171)(_QWORD, GUID *, BSTR *); // rcx
  HRESULT v172; // eax
  CMarkup *v173; // rax
  struct CGlyph *GlyphTable; // rax
  int v175; // edx
  CPeerFactoryUrl *v176; // rcx
  unsigned __int16 *Url; // rax
  CMarkup *v178; // rax
  CScriptCollection *ScriptCollection; // rax
  LONG lVal; // esi
  int v181; // ebx
  struct CElement *v182; // rax
  __int64 v183; // rcx
  CMarkup *v184; // rax
  CDwnDoc *DwnDoc; // rax
  CMarkup *v186; // rax
  CMarkup *v187; // rax
  CMarkup *v188; // rbx
  BOOL v189; // ecx
  struct CElement *ElementTopHelper; // rax
  CElement *TopLayoutElement; // rax
  struct CElement *v192; // rax
  BYTE bVal; // al
  int v194; // ecx
  int v195; // eax
  unsigned int v196; // ecx
  CInPlace *v197; // rax
  struct IUnknown *v198; // rax
  int SelectionMarkup; // ebx
  CElement *v200; // rax
  int v201; // ebx
  int v202; // ebx
  CMarkup *v203; // rax
  CMarkup *v204; // rax
  struct CGlyph *v205; // rax
  CElement *v206; // rcx
  CMarkup *v207; // rax
  CMarkup *v208; // rax
  struct CMarkup *v209; // rbx
  struct CSecurityContext *v210; // rax
  struct IUnknown *v211; // rcx
  unsigned __int16 *v212; // rbx
  struct CMarkup *v213; // rax
  struct CParentUndoUnit *v214; // rbx
  CMarkup *v215; // rbx
  COptionsHolder *v216; // rax
  struct CSecurityContext *v217; // rax
  CIPrintCollection *v218; // rbx
  LONG v219; // ecx
  int v220; // ecx
  CIPrintCollection *v221; // rax
  __int64 v222; // rcx
  __int64 v223; // rdx
  __int64 v224; // rdi
  CMarkup *v225; // rdi
  struct CMarkupTopElemCache *v226; // rax
  __int64 v227; // rdx
  CIPrintCollection *v228; // rbx
  CElement *v229; // rax
  struct CMarkup *v230; // rax
  CElement *v231; // rax
  CTreePos *v232; // rcx
  __int64 v233; // rcx
  __int64 LookasidePtr2; // rax
  void *v235; // rcx
  CIPrintCollection *v236; // rax
  __int64 v237; // rcx
  __int64 v238; // rdx
  struct CWindow *v239; // rax
  struct IUnknown *v240; // rcx
  CAutoRange *v241; // rsi
  int v242; // ecx
  unsigned int v243; // eax
  int v244; // eax
  CMarkup *v245; // rax
  CMarkup *v246; // rbx
  struct CMarkupEditContext *v247; // rax
  CMarkup *v248; // rbx
  CInPlace *v249; // rcx
  HRESULT v250; // eax
  struct IUnknown *v251; // rcx
  HRESULT v252; // eax
  CDocument *v253; // rbx
  struct CWindow *v254; // rax
  __int64 v255; // rbx
  CMarkup *v256; // rbx
  int v257; // eax
  int v258; // ecx
  int NormZoomPercent; // eax
  CMarkup *v260; // rax
  CMarkup *v261; // rbx
  CStr *v262; // rax
  CStr *v263; // rax
  CMarkup *v264; // rax
  CMarkup *v265; // rbx
  CMarkup *v266; // rax
  struct CMarkup *v267; // rbx
  __int64 v268; // rsi
  bool v269; // bl
  BYTE v270; // r8
  CMarkup *v271; // rax
  struct CMarkupStyleState *StyleState; // rax
  CMarkup *v273; // rbx
  CStr *v274; // rax
  CStr *v275; // rax
  CDispSurface *v276; // rax
  struct IDispRenderTarget *v277; // rax
  struct tagVARIANT *v278; // rcx
  signed __int64 v279; // rax
  int v280; // edx
  int v281; // r8d
  struct CMarkupStyleState *v282; // rax
  struct IUnknown *v283; // rdx
  SAFEARRAY *v284; // rbx
  signed int v285; // edx
  SAFEARRAY *v286; // rbx
  LONG v287; // eax
  LONG v288; // ecx
  HRESULT Element; // eax
  struct IUnknown **v290; // rax
  struct IUnknown *punkVal; // rcx
  const struct CDispNode *v292; // rdx
  struct CRect *v293; // r8
  struct IUnknown *v294; // rcx
  struct CDocument *v295; // r8
  struct CElement *v296; // rdx
  CMarkup *v297; // rbx
  int v298; // eax
  int v299; // esi
  int v300; // edi
  unsigned int v301; // eax
  HMENU EncodingMenu; // rax
  CMarkup *v303; // rax
  const WCHAR *v304; // rbx
  struct CMarkup *v305; // rax
  CMarkup *v306; // rax
  unsigned int v307; // eax
  struct CElement *v308; // rdx
  unsigned int v309; // ebx
  int v310; // eax
  COmWindowProxy *v311; // rcx
  CMarkup *v312; // rax
  __int64 v313; // r8
  struct CMarkup *v314; // rax
  struct CElement *v315; // rax
  int DefaultBlockTag; // eax
  const OLECHAR *v317; // rcx
  BOOL v318; // ebx
  CInPlace *v319; // rcx
  CElement *v320; // rcx
  CMarkup *v321; // rax
  CMarkup *v322; // rax
  struct GWND *Gwnd; // rax
  struct CElement *v324; // rdx
  int v325; // ecx
  HMENU DocDirMenu; // rax
  LONG v327; // eax
  int v328; // esi
  bool v329; // al
  __int16 *v330; // rdx
  bool v331; // al
  __int16 *v332; // rcx
  __int16 v333; // cx
  HMENU FontSizeMenu; // rax
  LONG v335; // eax
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, BSTR *); // rcx
  CDocument *v337; // rdi
  struct INamedPropertyBag *v338; // rbx
  struct CMarkup *v339; // rax
  CMarkup *v340; // rax
  struct CElement *v341; // rax
  COmWindowProxy *v342; // rcx
  CDocument *v343; // rax
  BSTR v344; // rax
  struct CMarkup *v345; // rax
  struct IDispRenderTarget *v346; // rax
  LONG v347; // eax
  ReadingMode::CTextClusterDetector *v348; // rax
  ReadingMode::CTextClusterDetector *v349; // rax
  ReadingMode::CTextClusterDetector *v350; // rbx
  CInputManager *v351; // rax
  CDeferredActionHandler *v352; // rax
  struct CMarkup *v353; // rax
  CInPlace *v354; // rbx
  __int64 CodePageCore; // r8
  unsigned int v356; // esi
  BSTR v357; // rcx
  bool IsEnterpriseMode; // bl
  CMarkup *v359; // rax
  CMarkupVersion *v360; // rax
  SHORT v361; // ax
  bool v362; // zf
  struct CMarkup *v363; // rax
  struct CMarkup *v364; // rbx
  CInPlace *v365; // rcx
  CInputManager *v366; // rax
  CDeferredActionHandler *v367; // rax
  CInputManager *v368; // rax
  CDeferredActionHandler *v369; // rax
  CInputManager *v370; // rax
  CDeferredActionHandler *v371; // rax
  CInputManager *v372; // rax
  CDeferredActionHandler *v373; // rax
  CInputManager *v374; // rax
  CDeferredActionHandler *v375; // rax
  SHORT v376; // cx
  int v377; // eax
  CVirtualTabStorageEntry *v378; // rcx
  struct CMarkup *v379; // rax
  CPreloadManager *v380; // rax
  struct IDispSystem *DispSystem; // rax
  LONG v382; // eax
  LONG v383; // ecx
  unsigned int Lo; // r9d
  char *v385; // rax
  LONG DebugState; // eax
  struct THREADSTATEUI *ThreadStateUI; // rax
  struct CMarkup *v388; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdx
  LONG v390; // r8d
  struct CMarkup *v391; // rax
  int v392; // ecx
  SAFEARRAY *Vector; // rax
  __int64 i; // r13
  char v395; // r8
  _QWORD *v396; // rbx
  COptionsHolder *v397; // rax
  CHtmCtx *v398; // rax
  const wchar_t *OriginalUrlContext; // rax
  const OLECHAR *v400; // rcx
  unsigned __int64 v401; // rdi
  size_t v402; // r8
  int v403; // eax
  BSTR v404; // rcx
  _QWORD *v405; // rax
  char v406; // dl
  _QWORD *v407; // rcx
  struct CSecurityContext *v408; // rax
  _QWORD *v409; // rcx
  _QWORD *v410; // rcx
  SAFEARRAY *v411; // rcx
  int v412; // eax
  struct CView *View; // rax
  struct CView *v414; // rdi
  int v415; // ebx
  const struct CDispNode *v416; // rdx
  struct CRect *v417; // r8
  const struct CDispNode *v418; // rdx
  struct CRect *v419; // r8
  struct CView *v420; // rax
  struct CView *v421; // rax
  bool IsMobileOptimizedSite; // al
  struct CView *v423; // rax
  SAFEARRAY *v424; // rcx
  SAFEARRAY *v425; // rcx
  CView *v426; // rax
  CFullScreenState *v427; // rax
  __int16 v428; // cx
  struct IUnknown *v429; // rcx
  CElement *v430; // rcx
  struct IUnknown *v431; // rcx
  CFullScreenState *v432; // rax
  int *v433; // rax
  CRootTracker *RootTracker; // rax
  CDCompLayerManager *v435; // rbx
  struct IDispLayer *v436; // rdi
  __int64 (__fastcall *v437)(struct IDispLayer *, GUID *, struct CHtmParseCtx *); // rbx
  CHtmRootParseCtxRouter *v438; // rax
  struct CHtmParseCtx *HpxEmbed; // rax
  struct IDispRenderTarget *v440; // rax
  CAPProcessor *v441; // rcx
  CWindow *v442; // rax
  CWindow *v443; // rbx
  CMarkup *v444; // rdi
  unsigned int v445; // eax
  __int64 v446; // rdx
  __int64 v447; // r9
  _QWORD *ThreadLocalStoragePointer; // rax
  bool v449; // zf
  struct CView *v450; // rax
  CViewportController *v451; // rcx
  _QWORD *v452; // rax
  unsigned int VirtualTabID; // eax
  struct CView *v454; // rax
  CViewportController *v455; // rcx
  CInPlace *v456; // rax
  LONG v457; // ecx
  const struct CMarkup *v458; // rax
  CTextScalingSettings *TextScalingSettings; // rax
  const struct CDispNode *v460; // rdx
  struct CRect *v461; // r8
  SAFEARRAY *v462; // rcx
  SAFEARRAY *v463; // rcx
  struct CMarkup *v464; // rax
  COmWindowProxy *v465; // rcx
  unsigned int (__fastcall ***v466)(_QWORD, GUID *, void **, __int64); // rcx
  CInPlace *v467; // rcx
  struct CMarkup *v468; // rbx
  SAFEARRAY *v469; // rcx
  SAFEARRAY *v470; // rcx
  unsigned int v471; // eax
  _DWORD *v472; // rbx
  HRESULT v473; // eax
  BSTR v474; // rcx
  struct CMarkup *v475; // rbx
  LONG v476; // ecx
  int v477; // ecx
  CMarkup *v478; // rax
  const struct CMarkupVersion *v479; // rax
  CMarkup *v480; // rax
  const struct CMarkupVersion *v481; // rax
  __int64 v482; // rdx
  _QWORD *v483; // rax
  SAFEARRAY *v484; // rcx
  SAFEARRAY *v485; // rcx
  SAFEARRAY *v486; // rcx
  SAFEARRAY *v487; // rax
  SAFEARRAY *v488; // rbx
  BSTR v489; // rax
  LPCWSTR v490; // rdx
  CMarkup *v491; // rax
  LONG v492; // edx
  CMarkupVersion *v493; // rax
  bool IsNativeQuirksLayoutEmulation; // al
  SHORT v495; // cx
  CDCompVideoBackedLayer *v496; // rax
  __int64 (__fastcall ***v497)(_QWORD, GUID *, VARIANTARG *, __int64); // rcx
  const unsigned __int16 *v498; // rdx
  int v499; // ecx
  int iVal; // ebx
  LONG v501; // eax
  int v502; // eax
  unsigned int v503; // esi
  const struct CMarkup *v504; // rax
  const unsigned __int16 *UrlRaw; // rax
  const WCHAR *v506; // rcx
  SAFEARRAY *parray; // rax
  const unsigned __int16 *bstrVal; // r8
  unsigned int v509; // ebx
  struct CMarkup *v510; // rax
  int IsActiveXFilteringEnabled; // eax
  int v512; // r8d
  struct IUnknown *v513; // rcx
  struct ILayoutServices *v514; // rax
  __int64 v515; // rcx
  OLECHAR *j; // rax
  CDispNodeReader *v517; // rax
  CDispScroller *v518; // rax
  CDispTopLevelScroller *v519; // rax
  const struct CDispNode *v520; // rdx
  struct CRect *v521; // r8
  SAFEARRAY *v522; // rax
  SAFEARRAY *v523; // rcx
  SAFEARRAY *v524; // rcx
  SAFEARRAY *v525; // rcx
  int v526; // ebx
  OLE_COLOR *v527; // rcx
  LONG v528; // ebx
  CMarkup *v529; // rax
  LONG v530; // ebx
  CMarkup *v531; // rax
  struct CMarkup *RootMarkup; // rax
  struct CMarkup *v533; // rax
  struct CMarkup *v534; // rax
  struct CMarkup *v535; // rbx
  unsigned int v536; // esi
  __int64 v537; // r8
  __int64 v538; // rdx
  struct CMarkup *v539; // rax
  struct CMarkup *v540; // rax
  struct IBindCtx *v541; // rdx
  void (__fastcall ***v542)(_QWORD, GUID *, struct CHtmParseCtx *); // rdi
  void (__fastcall *v543)(_QWORD, GUID *, struct CHtmParseCtx *); // rbx
  struct CHtmParseCtx *v544; // rax
  HRESULT v545; // eax
  unsigned int CodePageFromMenuID; // esi
  int IsCpAutoDetect; // eax
  CInPlace *v548; // rcx
  int v549; // ebx
  HWND v550; // rax
  CElement *v551; // rcx
  CMarkup *v552; // rax
  CMarkup *FrameOrPrimaryMarkup; // rax
  CMarkup *v554; // r13
  CWindowBarProp *v555; // rdi
  struct CSecurityContext *v556; // rax
  struct COmWindowProxy *v557; // rdi
  unsigned int CPSrc; // ebx
  unsigned int CodePage; // eax
  int v560; // ebx
  CWindowBarProp *v561; // rax
  CTreeNode *v562; // rbx
  struct CMarkup *v563; // rax
  struct CTreeNode *NodeInMarkup; // rax
  struct CElement *ElementClient; // rax
  struct CDocument *v566; // rbx
  CMarkup *v567; // rax
  unsigned int v568; // edi
  struct CMarkupEditContext *EditContext; // rax
  struct _GUID *v570; // rsi
  struct CMarkupEditContext *v571; // rbx
  CEntity *FocusedEntity; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-138h]
  BSTR bstrString; // [rsp+E0h] [rbp-80h] BYREF
  LONG plLbound[2]; // [rsp+E8h] [rbp-78h] BYREF
  CDocument *v576; // [rsp+F0h] [rbp-70h] BYREF
  unsigned int pvData; // [rsp+F8h] [rbp-68h] BYREF
  void *ppvData; // [rsp+100h] [rbp-60h] BYREF
  VARTYPE pvt[2]; // [rsp+108h] [rbp-58h] BYREF
  unsigned int v580; // [rsp+10Ch] [rbp-54h]
  LONG rgIndices[2]; // [rsp+110h] [rbp-50h] BYREF
  struct _GUID *v582; // [rsp+118h] [rbp-48h]
  LPCWSTR pszSubKey; // [rsp+120h] [rbp-40h] BYREF
  struct IUnknown *v584; // [rsp+128h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+130h] [rbp-30h] BYREF
  VARIANTARG pv; // [rsp+148h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+160h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+168h] [rbp+8h] BYREF
  int v589; // [rsp+170h] [rbp+10h] BYREF
  __int64 v590; // [rsp+178h] [rbp+18h]
  __int64 v591; // [rsp+188h] [rbp+28h]
  char v592; // [rsp+198h] [rbp+38h]
  int v593; // [rsp+19Ch] [rbp+3Ch]
  CIPrintCollection *v594; // [rsp+1A0h] [rbp+40h]
  __int64 v595; // [rsp+1A8h] [rbp+48h]
  __int64 v596; // [rsp+1B0h] [rbp+50h]
  size_t BufferCount; // [rsp+1C0h] [rbp+60h] BYREF
  wchar_t *Buffer; // [rsp+1C8h] [rbp+68h] BYREF
  __int128 v599; // [rsp+1D0h] [rbp+70h] BYREF
  VARIANTARG *v600; // [rsp+1E0h] [rbp+80h]
  __int128 v601; // [rsp+1E8h] [rbp+88h] BYREF
  __int128 *v602; // [rsp+1F8h] [rbp+98h]
  int v603; // [rsp+200h] [rbp+A0h] BYREF
  _BYTE v604[16]; // [rsp+208h] [rbp+A8h] BYREF
  CScriptCollection *v605; // [rsp+218h] [rbp+B8h]
  VARIANTARG String1; // [rsp+220h] [rbp+C0h] BYREF
  VARIANTARG v607; // [rsp+240h] [rbp+E0h] BYREF
  _BYTE v608[32]; // [rsp+260h] [rbp+100h] BYREF
  OLECHAR Data[264]; // [rsp+280h] [rbp+120h] BYREF
  OLECHAR psz[2088]; // [rsp+490h] [rbp+330h] BYREF

  v7 = a6;
  v9 = a7;
  v580 = a4;
  *(_QWORD *)&v607.vt = a6;
  *(_QWORD *)&String1.vt = a7;
  v12 = a2;
  v582 = a3;
  v576 = a2;
  if ( !(unsigned int)CBase::IsCmdGroupSupported(a3) )
    return 2147746052LL;
  CDoc::CLock::CLock((CDoc::CLock *)v604, (struct CDoc *)this, 0);
  v602 = 0;
  v600 = 0;
  v584 = 0;
  Text = -2147221248;
  v601 = 0;
  v599 = 0;
  if ( !a3 )
  {
    Text = CDoc::BrowserDocumentServerExec((CDoc *)this, v12, a4, a5, a6, a7);
    if ( Text != -2147221248 )
      goto LABEL_1650;
  }
  if ( a5 != 3 )
  {
    v15 = v12;
    if ( v12 )
    {
      v17 = *((_QWORD *)v12 + 7);
      if ( v17 )
        v18 = *(struct IUnknown **)(v17 + 104);
      else
        v18 = (struct IUnknown *)*((_QWORD *)v12 + 6);
      v584 = v18;
    }
    else
    {
      v16 = this[103];
      if ( !v16 )
      {
        if ( v605 )
          CScriptCollection::Release(v605);
        Text = -2147418113;
        goto LABEL_15;
      }
      v12 = *(struct CDocument **)(*((_QWORD *)v16 + 15) + 120LL);
      v576 = v12;
    }
    plLbound[0] = CBase::IDMFromCmdID(a3, v580);
    v20 = plLbound[0];
    if ( (unsigned int)(plLbound[0] - 3700) <= 0x20 )
    {
      v21 = this[544];
      if ( !v21 || (MarkupPtr = CElement::GetMarkupPtr(v21)) == 0 )
      {
        v23 = *((_QWORD *)v12 + 7);
        MarkupPtr = v23 ? *(struct CMarkup **)(v23 + 104) : (struct CMarkup *)*((_QWORD *)v12 + 6);
        if ( !MarkupPtr )
          goto LABEL_1650;
      }
      v24 = CDoc::OnContextMenuExt((CDoc *)this, MarkupPtr, plLbound[0], a6);
      goto LABEL_28;
    }
    v25 = 1;
    v26 = 0xFFFFFFFFLL;
    if ( plLbound[0] <= 0x17BAu )
    {
      if ( plLbound[0] == 6074 )
      {
        if ( !a7 )
          goto LABEL_131;
        a7->vt = 19;
        v351 = CDoc::InputManager((CDoc *)this);
        v352 = CInputManager::DeferredActionHandler(v351);
        NormZoomPercent = CDeferredActionHandler::RegisterVTabNavigate(v352);
        goto LABEL_933;
      }
      v27 = 2300;
      v28 = 2139;
      if ( plLbound[0] <= 0x924u )
      {
        v29 = 2322;
        if ( plLbound[0] == 2340 )
          goto LABEL_376;
        if ( plLbound[0] <= 0x8D5u )
        {
          if ( plLbound[0] != 2261 )
          {
            if ( plLbound[0] <= 0x7DBu )
            {
              if ( plLbound[0] == 2011 )
              {
                v42 = 0;
                goto LABEL_140;
              }
              if ( plLbound[0] <= 0x46u )
              {
                if ( plLbound[0] != 70 )
                {
                  if ( plLbound[0] != 27 )
                  {
                    if ( plLbound[0] == 28 )
                    {
                      v37 = this + 544;
                      v38 = this[544];
                      if ( v38 )
                      {
                        v39 = CElement::GetMarkupPtr(v38);
                        v40 = CMarkup::Document(v39);
                      }
                      else
                      {
                        v40 = v576;
                      }
                      if ( !*v37 || !(unsigned int)CBase::HasPages(*v37) )
                      {
                        if ( !*v37
                          && CDoc::GetActiveElement((CDoc *)this)
                          && (ActiveElement = CDoc::GetActiveElement((CDoc *)this),
                              (unsigned int)CBase::HasPages(ActiveElement)) )
                        {
                          v37 = this + 113;
                        }
                        else
                        {
                          v25 = 0;
                          v37 = 0;
                        }
                      }
                      CDoc::ShowPropertyDialog((CDoc *)this, v40, v25, v37);
                      goto LABEL_53;
                    }
                    if ( plLbound[0] == 29 )
                    {
                      v32 = *((_DWORD *)this + 1219);
                      *((_DWORD *)this + 1219) = v32 | 0x400;
                      v33 = CDoc::EditRedo((CDoc *)this);
LABEL_55:
                      Text = v33;
                      *((_DWORD *)this + 1219) ^= ((unsigned __int16)*((_DWORD *)this + 1219)
                                                 ^ (unsigned __int16)((unsigned __int8)(v32 >> 10) << 10))
                                                & 0x400;
                      goto LABEL_231;
                    }
                    if ( plLbound[0] != 37 )
                    {
                      if ( plLbound[0] != 43 )
                      {
                        if ( plLbound[0] == 47 )
                        {
                          if ( (unsigned int)CDoc::DesignMode((CDoc *)this) )
                            *((_DWORD *)this + 1216) |= 0x10000000u;
                          goto LABEL_53;
                        }
                        if ( plLbound[0] != 67 )
                          goto LABEL_231;
LABEL_46:
                        if ( *((int *)this + 1214) < 0 || a5 == 2 )
                          goto LABEL_231;
                        Text = 0;
                        ppvData = 0;
                        *(_QWORD *)rgIndices = 0;
                        bstrString = 0;
                        memset(&pvarg, 0, sizeof(pvarg));
                        pvarg.vt = 1;
                        if ( v15 )
                        {
                          v30 = *((_QWORD *)v15 + 7);
                          if ( v30 )
                            v31 = *(struct CMarkup **)(v30 + 104);
                          else
                            v31 = (struct CMarkup *)*((_QWORD *)v15 + 6);
                          goto LABEL_170;
                        }
                        v73 = this[544];
                        if ( !v73 )
                        {
                          if ( !CDoc::GetActiveElement((CDoc *)this) )
                          {
                            v74 = *((_QWORD *)v576 + 7);
                            if ( v74 )
                              v31 = *(struct CMarkup **)(v74 + 104);
                            else
                              v31 = (struct CMarkup *)*((_QWORD *)v576 + 6);
LABEL_170:
                            if ( *((_QWORD *)v31 + 18) )
                              v31 = (struct CMarkup *)*((_QWORD *)v31 + 18);
                            if ( (*((_DWORD *)v31 + 187) & 0x4000000) != 0 )
                            {
                              v76 = (COptionsHolder *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 128);
                              if ( v76 )
                              {
                                if ( (*((_DWORD *)v31 + 187) & 0x4000000) != 0 )
                                  v77 = *((_QWORD *)v31 + 44);
                                else
                                  v77 = 0;
                                v78 = COptionsHolder::COptionsHolder(v76, *(struct CWindow **)(v77 + 120));
                                v75 = v78;
                                if ( v78 )
                                {
                                  v79 = 0;
                                  *(_QWORD *)plLbound = v78;
                                  do
                                  {
                                    if ( v20 == dword_181559E20[4 * v79] )
                                      break;
                                    ++v79;
                                  }
                                  while ( v79 < 9 );
                                  *(_QWORD *)&String1.vt = 16LL * (int)v79;
                                  v80 = *(_DWORD *)&algn_181559E24[*(_QWORD *)&String1.vt];
                                  if ( v80 )
                                    *(_QWORD *)rgIndices = CBase::OpenParentUnit(
                                                             (CBase *)this,
                                                             (struct CBase *)this,
                                                             v80,
                                                             0);
                                  Text = COptionsHolder::PrivateQueryInterface(v75, &IID_IHTMLOptionsHolder, &ppvData);
                                  if ( !Text )
                                  {
                                    if ( a6 )
                                    {
                                      v81 = *(_OWORD *)&a6->vt;
                                      pRecInfo = a6->pRecInfo;
                                    }
                                    else
                                    {
                                      v81 = *(_OWORD *)&pvarg.vt;
                                      pRecInfo = pvarg.pRecInfo;
                                    }
                                    *(_OWORD *)v608 = v81;
                                    *(_QWORD *)&v608[16] = pRecInfo;
                                    COptionsHolder::put_execArg(
                                      (struct COptionsHolder *)((char *)v75 + 48),
                                      (struct tagVARIANT *)v608);
                                    Text = GetFindText(&bstrString);
                                    if ( !Text )
                                    {
                                      BASICPROPPARAMS::SetStringProperty(
                                        (BASICPROPPARAMS *)&unk_1811C2858,
                                        bstrString,
                                        v75,
                                        (struct COptionsHolder *)((char *)v75 + 24),
                                        0);
                                      SysFreeString(bstrString);
                                      bstrString = 0;
                                      if ( v20 == 2121 )
                                      {
                                        v83 = (struct IDispatch *)ppvData;
                                        v84 = *(const unsigned __int16 **)&algn_181559E24[*(_QWORD *)&String1.vt + 4];
                                        v85 = CDoc::GetActiveElement((CDoc *)this);
                                        v86 = CElement::GetMarkupPtr(v85);
                                        v87 = ShowModalDialogHelper(
                                                v86,
                                                v84,
                                                v83,
                                                *(struct COptionsHolder **)plLbound,
                                                0,
                                                0x2000000u);
                                        v75 = *(struct COptionsHolder **)plLbound;
                                        Text = v87;
                                        v25 = 1;
                                      }
                                      else
                                      {
                                        if ( v20 != 67 || (v88 = 1, !g_fBidiSupport) )
                                          v88 = 0;
                                        v89 = this[540];
                                        pvData = v88;
                                        *(_QWORD *)&pv.vt = 9;
                                        *(_OWORD *)&pv.decVal.Lo32 = (unsigned __int64)ppvData;
                                        memset(&v607, 0, sizeof(v607));
                                        if ( !v89
                                          || (*((_DWORD *)this + 1215) & 0x400000) != 0
                                          || (Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v89 + 32LL))(
                                                       v89,
                                                       &CGID_DocHostCommandHandler,
                                                       42,
                                                       v88,
                                                       &pv,
                                                       &v607)) != 0 )
                                        {
                                          CDoc::EnsureBackupUIHandler((CDoc *)this);
                                          v90 = this[539];
                                          if ( v90 )
                                          {
                                            *(_QWORD *)plLbound = 0;
                                            Text = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, LONG *))v90)(
                                                     v90,
                                                     &IID_IOleCommandTarget,
                                                     plLbound);
                                            if ( !Text )
                                            {
                                              Text = (*(__int64 (__fastcall **)(_QWORD, const GUID *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))(**(_QWORD **)plLbound + 32LL))(
                                                       *(_QWORD *)plLbound,
                                                       &CGID_DocHostCommandHandler,
                                                       42,
                                                       pvData,
                                                       &pv,
                                                       &v607);
                                              if ( *(_QWORD *)plLbound )
                                                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plLbound + 16LL))(*(_QWORD *)plLbound);
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                  goto LABEL_203;
                                }
                              }
                              else
                              {
                                v75 = 0;
                              }
                              Text = -2147024882;
                            }
                            else
                            {
                              v75 = 0;
                            }
LABEL_203:
                            v91 = ((unsigned __int64)v75 + 48) & -(__int64)(v75 != 0);
                            if ( v91 )
                              (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v91 + 16LL))(
                                v91,
                                v27,
                                v28,
                                v29);
                            if ( ppvData )
                              (*(void (__fastcall **)(void *, __int64, __int64, __int64))(*(_QWORD *)ppvData + 16LL))(
                                ppvData,
                                v27,
                                v28,
                                v29);
                            if ( *(_QWORD *)rgIndices )
                              CBase::CloseParentUnit((CBase *)this, *(struct CParentUndoUnit **)rgIndices, Text);
                            p_pvarg = &pvarg;
                            goto LABEL_210;
                          }
                          v73 = CDoc::GetActiveElement((CDoc *)this);
                        }
                        v31 = CElement::GetMarkupPtr(v73);
                        goto LABEL_170;
                      }
                      v32 = *((_DWORD *)this + 1219);
                      *((_DWORD *)this + 1219) = v32 | 0x400;
                      v33 = CDoc::EditUndo((CDoc *)this);
                      goto LABEL_55;
                    }
                    v34 = CDocument::Markup(v576);
                    v35 = CMarkup::Window(v34);
                    v36 = COmWindowProxy::Fire_onbeforeunload(v35, 1);
                    Text = 0;
                    if ( !a7 )
                      goto LABEL_1649;
                    a7->vt = 11;
                    a7->iVal = -(v36 != 0);
LABEL_1648:
                    if ( !v7 )
                      goto LABEL_1650;
LABEL_1649:
                    CDoc::DeferUpdateUI((CDoc *)this);
                    goto LABEL_1650;
                  }
LABEL_1449:
                  v499 = *((_DWORD *)this + 1217);
                  if ( (v499 & 0x800) != 0 )
                    goto LABEL_231;
                  iVal = 0;
                  v501 = *((_DWORD *)this + 1215);
                  plLbound[0] = v501;
                  if ( v580 == 93 && (v501 & 1) == 0
                    || v580 == 15038
                    || (v499 & 0x80u) != 0
                    || (unsigned __int8)IEConfiguration_GetBool(268435481) )
                  {
                    a5 = 0;
                    if ( !a6 || a6->vt != 2 )
                      goto LABEL_1462;
                    a6->iVal &= ~1u;
                  }
                  else if ( !a6 )
                  {
                    goto LABEL_1462;
                  }
                  if ( a6->vt == 2 )
                    iVal = a6->iVal;
LABEL_1462:
                  v502 = iVal | 1;
                  if ( a5 != 2 )
                    v502 = iVal;
                  v503 = v502 | 0x1000000;
                  if ( v20 != 15038 )
                    v503 = v502;
                  if ( (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  {
                    v504 = CDoc::PrimaryMarkup((CDoc *)this);
                    UrlRaw = CMarkup::GetUrlRaw(v504);
                    v506 = L"about:blank";
                    if ( UrlRaw )
                      v506 = UrlRaw;
                    if ( *v506 && !wcscmp_0(v506, L"outday://") )
                      *((_DWORD *)this + 1215) |= 0x400000u;
                  }
                  if ( v20 == 27 )
                  {
                    if ( a6 && (a6->vt & 0x6000) == 0x6000 )
                    {
                      parray = a6->parray;
LABEL_1479:
                      if ( a6->vt == 8 )
                      {
                        bstrVal = a6->bstrVal;
LABEL_1482:
                        v509 = a5;
                        Text = CDoc::PrintHandler((CDoc *)this, v576, bstrVal, 0, v503, parray, a5, a6, a7, 0);
                        if ( Text )
                          goto LABEL_1650;
                        if ( (*((char *)this + 4868) < 0 || (unsigned __int8)IEConfiguration_GetBool(268435481))
                          && v20 != 15038 )
                        {
                          ++*((_DWORD *)this + 1237);
                        }
                        *((_DWORD *)this + 1215) ^= (*((_DWORD *)this + 1215) ^ plLbound[0]) & 0x400000;
LABEL_1583:
                        if ( v20 >= 0xE19 )
                        {
                          if ( v20 <= 0xE73 )
                          {
                            CodePageFromMenuID = GetCodePageFromMenuID(v20);
                            *(_QWORD *)&v607.vt = GetThreadStateUI();
                            if ( CodePageFromMenuID == -1 )
                            {
                              if ( v20 != 3699
                                || (IsCpAutoDetect = CDoc::IsCpAutoDetect((CDoc *)this),
                                    CDoc::SetCpAutoDetect((CDoc *)this, IsCpAutoDetect == 0),
                                    !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this))
                                || !(unsigned int)CMLang::IsMLangAvailable((CMLang *)&g_MLang) )
                              {
LABEL_1601:
                                ++*(_DWORD *)(*(_QWORD *)&v607.vt + 604LL);
                                goto LABEL_53;
                              }
                              CodePageFromMenuID = 50001;
                              if ( g_cpDefault == 932 )
                                CodePageFromMenuID = 50932;
                            }
                            v548 = this[12];
                            if ( v548 )
                            {
                              v549 = (_DWORD)this[556] & 0x40000000;
                              v550 = CInPlace::_hwnd_Get(v548);
                              if ( !(unsigned int)CMLang::ValidateCodePage(
                                                    (CMLang *)&g_MLang,
                                                    g_cpDefault,
                                                    CodePageFromMenuID,
                                                    v550,
                                                    1,
                                                    v549) )
                              {
                                v551 = this[544];
                                v552 = v551 ? CElement::GetMarkupPtr(v551) : CDocument::Markup(v576);
                                FrameOrPrimaryMarkup = CMarkup::GetFrameOrPrimaryMarkup(v552, 1);
                                v554 = FrameOrPrimaryMarkup;
                                if ( FrameOrPrimaryMarkup )
                                {
                                  v555 = CMarkup::Root(FrameOrPrimaryMarkup);
                                  CNotification::CNotification((CNotification *)&v589);
                                  v556 = CWindowBarProp::SecurityContext(v555);
                                  CNotification::Initialize(&v589, 59, v555, v556, CodePageFromMenuID, 0);
                                  if ( !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this)
                                    && !(unsigned int)CMarkup::HaveCodePageMetaTag(v554) )
                                  {
                                    CDoc::SaveDefaultCodepage((CDoc *)this, CodePageFromMenuID);
                                  }
                                  CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v589);
                                  CMarkup::BubbleDownCodePage(v554, CodePageFromMenuID);
                                  v557 = CMarkup::Window(v554);
                                  CPSrc = CMarkup::GetCPSrc(v554);
                                  CodePage = CMarkup::GetCodePage(v554);
                                  COmWindowProxy::ExecRefresh(v557, 5, CodePage, CPSrc);
                                }
                              }
                            }
                            goto LABEL_1601;
                          }
                          a5 = v509;
                        }
                        goto LABEL_1603;
                      }
LABEL_1481:
                      bstrVal = 0;
                      goto LABEL_1482;
                    }
                  }
                  else
                  {
                    parray = 0;
                    if ( v20 != 15038 )
                      goto LABEL_1481;
                  }
                  parray = 0;
                  if ( !a6 )
                    goto LABEL_1481;
                  goto LABEL_1479;
                }
                v51 = 3;
                goto LABEL_104;
              }
              if ( plLbound[0] != 71 )
              {
                switch ( plLbound[0] )
                {
                  case 93:
                    goto LABEL_1449;
                  case 2000:
                  case 2001:
                    if ( plLbound[0] == 2000 )
                      v51 = 1;
                    else
                      v51 = 2;
LABEL_104:
                    v52 = this[12];
                    if ( v52 )
                      v53 = (CInPlace *)*((_QWORD *)v52 + 10);
                    else
                      v53 = this[8];
                    bstrString = 0;
                    if ( !v53 )
                    {
                      Text = -2147467259;
                      goto LABEL_231;
                    }
                    Text = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, BSTR *, __int64))v53)(
                             v53,
                             &IID_IOleCommandTarget,
                             &bstrString,
                             2322);
                    if ( Text )
                      goto LABEL_231;
                    v54 = (*(__int64 (__fastcall **)(BSTR, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)bstrString
                                                                                                  + 32LL))(
                            bstrString,
                            0,
                            v51,
                            0,
                            0,
                            0);
                    v55 = bstrString;
                    Text = v54;
LABEL_111:
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v55 + 16LL))(v55);
                    goto LABEL_231;
                  case 2003:
                    if ( (*((_DWORD *)this + 1217) & 0x800) == 0 )
                    {
                      if ( (Microsoft_IEEnableBits & 0x10000) != 0 )
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, &MSHTML_PRINTPREVIEW_START, 0, 1, &v607);
                      if ( a6 && a6->vt == 8 )
                        v50 = a6->bstrVal;
                      else
                        v50 = 0;
                      Text = CDoc::PrintHandler((CDoc *)this, v576, v50, 0, 0, 0, a5, a6, a7, 1);
                      if ( (Microsoft_IEEnableBits & 0x10000) != 0 )
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, &MSHTML_PRINTPREVIEW_STOP, 0, 1, &v607);
                      goto LABEL_1645;
                    }
                    goto LABEL_231;
                }
                if ( plLbound[0] != 2004 )
                {
                  if ( plLbound[0] != 2010 )
                    goto LABEL_231;
                  v42 = 1;
LABEL_140:
                  v24 = CDoc::DelegateShowPrintingDialog((CDoc *)this, a6, v42);
LABEL_28:
                  Text = v24;
LABEL_1650:
                  CDoc::CLock::~CLock((CDoc::CLock *)v604);
                  return (unsigned int)Text;
                }
                v43 = this[540];
                if ( v43 && a5 != 2 && (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v43 + 32LL))(
                           v43,
                           &CGID_DocHostCommandHandler,
                           v580,
                           a5,
                           a6,
                           a7);
                if ( Text < 0 )
                {
                  CDoc::EnsureBackupUIHandler((CDoc *)this);
                  v44 = this[539];
                  if ( !v44 )
                    goto LABEL_1581;
                  bstrString = 0;
                  memset(&pv, 0, sizeof(pv));
                  memset(&pvarg, 0, sizeof(pvarg));
                  Text = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, BSTR *))v44)(
                           v44,
                           &IID_IOleCommandTarget,
                           &bstrString);
                  if ( Text )
                  {
                    VariantClear(&pvarg);
                    goto LABEL_1650;
                  }
                  v45 = this[103];
                  v46 = this[51];
                  pv.vt = 13;
                  v47 = this[50];
                  v48 = *(_QWORD *)(*((_QWORD *)v45 + 15) + 120LL);
                  HWND = CServer::GetHWND((CServer *)this);
                  pv.llVal = SetPrintCommandParameters(
                               HWND,
                               0,
                               0,
                               0,
                               0,
                               0,
                               0,
                               0,
                               0,
                               v48,
                               &pvarg,
                               v47,
                               v46,
                               0,
                               0,
                               0,
                               0,
                               0);
                  Text = (*(__int64 (__fastcall **)(BSTR, const GUID *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))(*(_QWORD *)bstrString + 32LL))(
                           bstrString,
                           &CGID_DocHostCommandHandler,
                           2298,
                           a5,
                           &pv,
                           a7);
                  VariantClear(&pv);
                  if ( bstrString )
                    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                  VariantClear(&pvarg);
                  v25 = 1;
                  if ( Text == 1 )
                    Text = -2147221245;
                  goto LABEL_231;
                }
LABEL_1603:
                if ( Text != -2147221248 )
                  goto LABEL_1637;
                if ( v20 != 15031 || !(unsigned __int8)IEConfiguration_GetBool(268435481) )
                {
                  *((_QWORD *)&v601 + 1) = v582;
                  v602 = &v599;
                  *(_QWORD *)&v599 = __PAIR64__(a5, v580);
                  LODWORD(v601) = 0;
                  *((_QWORD *)&v599 + 1) = v7;
                  v600 = a7;
                  if ( this[544] )
                  {
                    if ( ((_DWORD)this[608] & 0x40000) != 0 )
                    {
                      v560 = 1;
                      CDoc::BeginUserInitiatedAction((CDoc *)this, 1);
                    }
                    else
                    {
                      v560 = 0;
                    }
                    Text = CDoc::RouteCTElement((CDoc *)this, this[544], (struct CDoc::CTArg *)&v601, v576);
                    if ( v560 )
                      CDoc::EndUserInitiatedAction((CDoc *)this);
                    if ( Text != -2147221248 )
                      goto LABEL_1637;
                  }
                  if ( CDoc::GetActiveElement((CDoc *)this) )
                  {
                    v561 = CDoc::GetActiveElement((CDoc *)this);
                    v562 = CWindowBarProp::SecurityContext(v561);
                    v563 = CDocument::Markup(v576);
                    NodeInMarkup = CTreeNode::GetNodeInMarkup(v562, v563);
                    if ( NodeInMarkup )
                    {
                      ElementClient = (struct CElement *)SP<Tree::CIE9DocumentLayout>::operator->(NodeInMarkup);
                      v566 = v576;
                    }
                    else
                    {
                      v566 = v576;
                      v567 = CDocument::Markup(v576);
                      ElementClient = CMarkup::GetElementClient(v567);
                    }
                    if ( ElementClient )
                    {
                      Text = CDoc::RouteCTElement((CDoc *)this, ElementClient, (struct CDoc::CTArg *)&v601, v566);
                      if ( Text != -2147221248 )
                      {
                        v568 = a5;
LABEL_1639:
                        if ( v20 == 15 && !(unsigned int)CDoc::HasSelection((CDoc *)this) )
                        {
                          v449 = Text == 0;
                          if ( Text < 0 )
                            goto LABEL_1646;
                          goto LABEL_1642;
                        }
LABEL_1645:
                        v449 = Text == 0;
LABEL_1646:
                        if ( !v449 )
                          goto LABEL_1650;
                        goto LABEL_1647;
                      }
                    }
                  }
                }
LABEL_441:
                v197 = this[126];
                if ( (!v197 || !*((_BYTE *)v197 + 38) || !*((_DWORD *)this + 1231))
                  && (int)CServer::State(this) >= 3
                  && (*((char *)this + 4868) >= 0 || v20 != 2315) )
                {
                  v198 = v584;
                  *(_QWORD *)&String1.vt = 0;
                  if ( v584 )
                    goto LABEL_1623;
                  SelectionMarkup = CDoc::GetSelectionMarkup((CDoc *)this, (struct CMarkup **)&v584);
                  v198 = v584;
                  if ( !v584 )
                  {
                    if ( CDoc::GetActiveElement((CDoc *)this) )
                    {
                      v200 = CDoc::GetActiveElement((CDoc *)this);
                      v198 = (struct IUnknown *)CElement::GetMarkupPtr(v200);
                      v584 = v198;
                    }
                    else
                    {
                      v198 = v584;
                    }
                  }
                  if ( SelectionMarkup >= 0 && v198 )
                  {
LABEL_1623:
                    Text = CMarkup::EnsureEditRouter((CMarkup *)v198, (struct CEditRouter **)&String1);
                    if ( Text >= 0 )
                    {
                      CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&v607);
                      EditContext = CMarkup::GetEditContext((CMarkup *)v584);
                      v570 = v582;
                      v571 = EditContext;
                      if ( v582 && (unsigned __int8)_(v582, &CGID_MSHTML) )
                      {
                        if ( v20 - 15 <= 1 )
                        {
                          v25 = 0;
LABEL_1631:
                          *((_DWORD *)v571 + 10) &= ~0x800u;
                          *((_DWORD *)v571 + 10) |= v25 << 11;
                          if ( v25 )
                            CDoc::CDOMTextInputScope::Init((CDoc::CDOMTextInputScope *)&v607, (struct CDoc *)this, 2);
                          *((_DWORD *)v571 + 10) |= 0x400u;
                          goto LABEL_1634;
                        }
                        if ( v20 == 26 || v20 - 2500 <= 1 )
                          goto LABEL_1631;
                      }
LABEL_1634:
                      v568 = a5;
                      Text = CEditRouter::ExecEditCommand(
                               *(CEditRouter **)&String1.vt,
                               v570,
                               v580,
                               a5,
                               v7,
                               a7,
                               v584,
                               (struct CMarkup *)v584,
                               (struct CDoc *)this);
                      if ( v571 == CMarkup::GetEditContext((CMarkup *)v584) )
                        *((_DWORD *)v571 + 10) &= 0xFFFFF3FF;
                      CDoc::CDOMTextInputScope::~CDOMTextInputScope((CDoc::CDOMTextInputScope *)&v607);
LABEL_1638:
                      if ( Text == -2147221248 )
                      {
LABEL_1642:
                        if ( CDoc::EntityHasFocus((CDoc *)this) )
                        {
                          FocusedEntity = CDoc::GetFocusedEntity((CDoc *)this);
                          if ( FocusedEntity )
                            Text = CEntity::Exec(FocusedEntity, v582, v580, v568, v7, a7);
                        }
                        goto LABEL_1645;
                      }
                      goto LABEL_1639;
                    }
                  }
                }
LABEL_1637:
                v568 = a5;
                goto LABEL_1638;
              }
              if ( *((_WORD *)CDoc::GetActiveElement((CDoc *)this) + 28) != 60
                && *((_WORD *)CDoc::GetActiveElement((CDoc *)this) + 28) != 46
                && (*((_WORD *)CDoc::GetActiveElement((CDoc *)this) + 28) != 86
                 || (*((_BYTE *)CDoc::GetActiveElement((CDoc *)this) + 432) & 1) == 0) )
              {
LABEL_118:
                if ( Text != -2147221248 )
                  goto LABEL_137;
                v57 = this[540];
                v58 = a5;
                if ( v57 && a5 != 2 )
                {
                  Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v57 + 32LL))(
                           v57,
                           &CGID_DocHostCommandHandler,
                           v580,
                           a5,
                           a6,
                           a7);
                  if ( Text >= 0 )
                    goto LABEL_137;
                  v58 = a5;
                }
                v59 = this[12];
                if ( v59 )
                {
                  bstrString = 0;
                  v60 = 1;
                  if ( a6 && a6->vt == 8 )
                    bstrString = a6->bstrVal;
                  if ( v58 == 2 )
                  {
                    ppvData = (void *)46;
                    v362 = (unsigned int)CTQueryStatus(
                                           *((struct IUnknown **)v59 + 10),
                                           0,
                                           1u,
                                           (struct _tagOLECMD *const)&ppvData,
                                           0) == 0;
                    v61 = bstrString;
                    if ( v362 && HIDWORD(ppvData) == 3 )
                    {
                      v60 = 0;
                      if ( !bstrString )
                        goto LABEL_131;
                    }
                  }
                  else
                  {
                    v61 = bstrString;
                  }
                  v62 = *((_QWORD *)v576 + 7);
                  if ( v62 )
                    v63 = *(struct CMarkup **)(v62 + 104);
                  else
                    v63 = (struct CMarkup *)*((_QWORD *)v576 + 6);
                  Text = CDoc::PromptSave((CDoc *)this, v63, 1, v60, v61);
                }
LABEL_137:
                if ( Text == 1 )
                  Text = -2147221245;
                goto LABEL_231;
              }
              if ( *(__int64 (__fastcall **)())(*(_QWORD *)CDoc::GetActiveElement((CDoc *)this) + 1624LL) == _vtguard )
              {
                v56 = CDoc::GetActiveElement((CDoc *)this);
                Text = (*(__int64 (__fastcall **)(struct CElement *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v56 + 368LL))(
                         v56,
                         v582,
                         v580,
                         a5,
                         a6,
                         a7);
                goto LABEL_118;
              }
LABEL_1653:
              _report_securityfailure(1);
            }
            if ( plLbound[0] <= 0x85Bu )
            {
              if ( plLbound[0] != 2139 )
              {
                switch ( plLbound[0] )
                {
                  case 2121:
                    goto LABEL_46;
                  case 2126:
                    v72 = htmlDesignModeOff;
                    break;
                  case 2127:
                    v72 = htmlDesignModeOn;
                    break;
                  case 2130:
                  case 2131:
                  case 2135:
                    goto LABEL_345;
                  case 2138:
                    v64 = CDocument::Markup(v576);
                    if ( CMarkup::HasWindow(v64) )
                    {
                      v65 = CMarkup::Window(v64);
                      if ( *((_QWORD *)COptionsHolder::SecurityContext(v65) + 14) )
                      {
                        v66 = CMarkup::Window(v64);
                        v67 = COptionsHolder::SecurityContext(v66);
                        v68 = CMarkup::Window(v64);
                        v69 = COptionsHolder::SecurityContext(v68);
                        CWindow::ReleaseMarkupPending(v67, *((struct CMarkup **)v69 + 14), 1);
                        goto LABEL_53;
                      }
                    }
                    if ( !a6 || a6->vt != 11 || (v70 = 0, v25 = 1, a6->iVal != -1) )
                      v70 = 1;
                    inserted = CMarkup::ExecStop(v64, 1, v70, 1);
                    goto LABEL_306;
                  default:
                    goto LABEL_231;
                }
                inserted = CDoc::SetDesignMode((CDoc *)this, v576, v72);
                goto LABEL_306;
              }
              goto LABEL_514;
            }
            if ( plLbound[0] == 2141
              || plLbound[0] == 2142
              || plLbound[0] == 2143
              || plLbound[0] == 2144
              || plLbound[0] == 2145 )
            {
              if ( CDoc::GetActiveElement((CDoc *)this) )
              {
                v99 = CDoc::GetActiveElement((CDoc *)this);
                if ( CElement::GetWindowedMarkupContext(v99) )
                {
                  v100 = CDoc::GetActiveElement((CDoc *)this);
                  WindowedMarkupContext = CElement::GetWindowedMarkupContext(v100);
                  bstrString = (BSTR)CMarkup::GetCodepageSettings(WindowedMarkupContext);
                  v102 = bstrString;
                  if ( bstrString )
                  {
                    v103 = LOWORD(plLbound[0]) - 2141;
                    LOBYTE(pvt[0]) = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                    if ( LOBYTE(pvt[0]) )
                      BaselineFontPrivate = CDoc::GetBaselineFontPrivate((CDoc *)this);
                    else
                      BaselineFontPrivate = CDoc::GetBaselineFont((CDoc *)this);
                    if ( BaselineFontPrivate != v103 )
                    {
                      v105 = this[126];
                      v106 = (wchar_t *)&LocaleName;
                      v362 = *((_BYTE *)v105 + 56) == 0;
                      Buffer = 0;
                      if ( v362 )
                        v106 = L"\\Scripts";
                      LODWORD(v576) = 12;
                      ppvData = v106;
                      v107 = -1;
                      do
                        ++v107;
                      while ( *(_WORD *)(*((_QWORD *)v105 + 184) + 2 * v107) );
                      if ( (int)UIntAdd(0xCu, v107, (unsigned int *)&v576) < 0 )
                        goto LABEL_273;
                      if ( (int)UIntAdd((unsigned int)v576, 0xEu, (unsigned int *)&v576) < 0 )
                        goto LABEL_273;
                      v108 = -1;
                      do
                        ++v108;
                      while ( *((_WORD *)ppvData + v108) );
                      if ( (int)UIntAdd((unsigned int)v576, v108, (unsigned int *)&v576) < 0 )
                        goto LABEL_273;
                      v109 = 2LL * (unsigned int)v576;
                      if ( !is_mul_ok((unsigned int)v576, 2u) )
                        v109 = -1;
                      pszSubKey = (LPCWSTR)operator new[](v109, (const struct MemoryProtection::leaf_t *)&leaf);
                      if ( pszSubKey )
                      {
                        v110 = this[126];
                        BufferCount = 0;
                        StringCchPrintfExW(
                          (wchar_t *)pszSubKey,
                          (unsigned int)v576,
                          &Buffer,
                          &BufferCount,
                          0,
                          L"%s%s%s\\",
                          *((_QWORD *)v110 + 184),
                          L"\\International",
                          ppvData);
                        v102 = bstrString;
                        pvData = v103;
                        v111 = this[126];
                        v112 = *((_DWORD *)bstrString + 2);
                        plLbound[0] = v112;
                        if ( !*((_BYTE *)v111 + 56) )
                        {
                          v113 = DefaultSidForCodePage(v112);
                          plLbound[0] = RegistryAppropriateSidFromSid(v113);
                        }
                        v114 = CListenerDispatch::GetThis((CInPlace *)((char *)this[126] + 112));
                        v115 = (CInPlace *)((char *)this[126] + 112);
                        ppvData = v114;
                        rgIndices[0] = CImplAry::Size(v115);
                        v116 = rgIndices[0];
                        if ( rgIndices[0] > 0 )
                        {
                          v117 = pszSubKey;
                          v118 = plLbound[0];
                          v119 = (char *)ppvData;
                          do
                          {
                            v120 = *(_DWORD *)(*(_QWORD *)v119 + 8LL);
                            if ( !*((_BYTE *)this[126] + 56) )
                            {
                              v121 = DefaultSidForCodePage(v120);
                              v122 = RegistryAppropriateSidFromSid(v121);
                              v116 = rgIndices[0];
                              v119 = (char *)ppvData;
                              v120 = v122;
                            }
                            if ( v120 == v118 )
                            {
                              *(_WORD *)(*(_QWORD *)v119 + 2LL) = v103;
                              _ultow_s(v120, Buffer, BufferCount, 10);
                              v123 = IsProtectedModeProcess();
                              v124 = 3;
                              if ( v123 )
                              {
                                SHSetValueW(HKEY_CURRENT_USER, v117, L"IEFontSize", 3u, &pvData, 4u);
                                if ( LOBYTE(pvt[0]) )
                                  SHSetValueW(HKEY_CURRENT_USER, v117, L"IEFontSizePrivate", 3u, &pvData, 4u);
                              }
                              else
                              {
                                if ( v118 - 3 <= 0x25 )
                                  v124 = v118;
                                if ( (int)StringCchPrintfW((unsigned __int16 *)v608, 0x10u, L"%d", v124) >= 0 )
                                {
                                  SetBinaryExt(
                                    (_DWORD)SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizeExt,
                                    2,
                                    (unsigned int)v608,
                                    (unsigned int)&pvData,
                                    4);
                                  if ( LOBYTE(pvt[0]) )
                                    SetBinaryExt(
                                      (_DWORD)SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizePrivateExt,
                                      2,
                                      (unsigned int)v608,
                                      (unsigned int)&pvData,
                                      4);
                                }
                              }
                              v116 = rgIndices[0];
                              v119 = (char *)ppvData;
                            }
                            v119 += 8;
                            --v116;
                            ppvData = v119;
                            rgIndices[0] = v116;
                          }
                          while ( v116 > 0 );
                          v7 = *(VARIANTARG **)&v607.vt;
                          v9 = *(VARIANTARG **)&String1.vt;
                          v102 = bstrString;
                        }
                        Free_progressEventParams((void *)pszSubKey);
                      }
                      else
                      {
LABEL_273:
                        v102 = bstrString;
                      }
                    }
                    v102[1] = v103;
                    *((_WORD *)this + 2860) = v103;
                    v102[2] = v103;
                    *((_DWORD *)this + 1217) |= 0x80000000;
                    v125 = this[126];
                    *((_WORD *)this + 2861) = v103;
                    v126 = *((_DWORD *)v102 + 2);
                    plLbound[0] = v126;
                    if ( !*((_BYTE *)v125 + 56) )
                    {
                      v127 = DefaultSidForCodePage(v126);
                      plLbound[0] = RegistryAppropriateSidFromSid(v127);
                    }
                    v128 = CImplAry::Size((CInPlace *)((char *)this[126] + 112));
                    v129 = CListenerDispatch::GetThis((CInPlace *)((char *)this[126] + 112));
                    if ( v128 > 0 )
                    {
                      v130 = plLbound[0];
                      do
                      {
                        v131 = *(_DWORD *)(*(_QWORD *)v129 + 8LL);
                        if ( !*((_BYTE *)this[126] + 56) )
                        {
                          v132 = DefaultSidForCodePage(v131);
                          v131 = RegistryAppropriateSidFromSid(v132);
                        }
                        if ( v130 == v131 )
                        {
                          *(_WORD *)(*(_QWORD *)v129 + 2LL) = *((_WORD *)this + 2860);
                          *(_WORD *)(*(_QWORD *)v129 + 4LL) = *((_WORD *)this + 2861);
                        }
                        --v128;
                        v129 = (struct CBase *)((char *)v129 + 8);
                      }
                      while ( v128 > 0 );
                      v9 = *(VARIANTARG **)&String1.vt;
                    }
                  }
                }
              }
              v133 = CDoc::GetActiveElement((CDoc *)this);
              v134 = CElement::GetMarkupPtr(v133);
              CMarkup::EnsureFormatCacheChange(v134, 0x80u);
              CDoc::ForceRelayout((CDoc *)this, 0);
              v135 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL);
              ++*(_DWORD *)(v135 + 604);
              COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v608);
              v136 = v580;
              *(_QWORD *)v608 = v582;
              *(_DWORD *)&v608[8] = v580;
              CNotification::CNotification((CNotification *)&v589);
              v137 = CDoc::PrimaryRoot((CDoc *)this);
              CNotification::Command((CNotification *)&v589, v137, v608, 0);
              CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v589);
              v138 = this[12];
              if ( v138 )
                v139 = (struct IUnknown *)*((_QWORD *)v138 + 10);
              else
                v139 = (struct IUnknown *)this[8];
              CTExec(v139, &CGID_ExplorerBarDoc, v136, 0, 0, 0);
              goto LABEL_53;
            }
            if ( plLbound[0] != 2221 )
            {
              if ( plLbound[0] != 2222 )
                goto LABEL_231;
              hKey = 0;
              cbData = 0;
              if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID\\{25336920-03F9-11CF-8FD0-00AA00686F13}", 0, 1u, &hKey) )
                goto LABEL_231;
              bstrString = 0;
              v93 = RegOpenKeyExW(hKey, L"InprocServer32", 0, 1u, (PHKEY)&bstrString);
              if ( !v93 )
              {
                cbData = 520;
                v93 = RegQueryValueExW((HKEY)bstrString, 0, 0, 0, (LPBYTE)Data, &cbData);
                RegCloseKey((HKEY)bstrString);
              }
              RegCloseKey(hKey);
              if ( v93 )
                goto LABEL_231;
              v94 = wcsrchr(Data, 0x5Cu);
              if ( v94 )
                *v94 = 0;
              v95 = -1;
              do
                ++v95;
              while ( Data[v95] );
              Text = StringCchCatNW(Data, 0x104u, L"\\readme.htm", 259 - v95);
              if ( Text >= 0 )
              {
                FileW = CreateFileW(Data, 0x80000000, 1u, 0, 3u, 0x80u, 0);
                if ( FileW != (HANDLE)-1LL )
                {
                  CloseHandle(FileW);
                  v97 = CDoc::FollowHyperlink(
                          (CDoc *)this,
                          Data,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0);
LABEL_229:
                  Text = v97;
                }
LABEL_230:
                v25 = 1;
                goto LABEL_231;
              }
LABEL_1580:
              v25 = 1;
              goto LABEL_1581;
            }
            LODWORD(lpcbData) = 11;
            CDoc::ShowMessage((CDoc *)this, &v603, 0, 0, 0x5EDu, lpcbData, 0, 10570, 1001, &LocaleName, &LocaleName);
LABEL_53:
            Text = 0;
            goto LABEL_1647;
          }
          if ( v15 )
          {
            v140 = *((_QWORD *)v15 + 7);
            if ( v140 )
              v141 = *(struct CMarkup **)(v140 + 104);
            else
              v141 = (struct CMarkup *)*((_QWORD *)v15 + 6);
          }
          else
          {
            v142 = this[544];
            if ( v142 )
            {
              if ( *(__int64 (__fastcall **)())(*(_QWORD *)v142 + 1624LL) != _vtguard )
                goto LABEL_1653;
              Text = (*(__int64 (__fastcall **)(CInPlace *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v142 + 368LL))(
                       v142,
                       v582,
                       v580,
                       a5,
                       a6,
                       a7);
              if ( !Text )
                goto LABEL_231;
              v143 = this[544];
            }
            else
            {
              if ( !CDoc::GetActiveElement((CDoc *)this) )
                goto LABEL_302;
              if ( *(__int64 (__fastcall **)())(*(_QWORD *)CDoc::GetActiveElement((CDoc *)this) + 1624LL) != _vtguard )
                goto LABEL_1653;
              v144 = CDoc::GetActiveElement((CDoc *)this);
              Text = (*(__int64 (__fastcall **)(struct CElement *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v144 + 368LL))(
                       v144,
                       v582,
                       v580,
                       a5,
                       a6,
                       a7);
              if ( !Text )
                goto LABEL_231;
              v143 = CDoc::GetActiveElement((CDoc *)this);
            }
            v141 = CElement::GetMarkupPtr(v143);
          }
          if ( v141 )
          {
LABEL_305:
            inserted = CDoc::AddToFavorites((CDoc *)this, v141);
            goto LABEL_306;
          }
LABEL_302:
          v145 = *((_QWORD *)v576 + 7);
          if ( v145 )
            v141 = *(struct CMarkup **)(v145 + 104);
          else
            v141 = (struct CMarkup *)*((_QWORD *)v576 + 6);
          goto LABEL_305;
        }
        if ( plLbound[0] <= 0x912u )
        {
          if ( plLbound[0] == 2322 )
            goto LABEL_376;
          if ( plLbound[0] <= 0x8FCu )
          {
            if ( plLbound[0] != 2300 )
            {
              switch ( plLbound[0] )
              {
                case 2266:
LABEL_345:
                  memset(&v607, 0, sizeof(v607));
                  VariantInit(&v607);
                  v164 = 0;
                  pvData = ConvertSBCMDID(plLbound[0]);
                  plLbound[0] = 0;
                  if ( v20 == 2135 )
                  {
                    v607.vt = 3;
                    v607.lVal = 1;
LABEL_361:
                    v164 = &v607;
LABEL_362:
                    v170 = this[12];
                    if ( v170 )
                    {
                      v171 = (__int64 (__fastcall ***)(_QWORD, GUID *, BSTR *))*((_QWORD *)v170 + 10);
                      bstrString = 0;
                      if ( v171 )
                      {
                        v172 = (**v171)(v171, &IID_IOleCommandTarget, &bstrString);
                        v165 = 0;
                        Text = v172;
                        if ( !v172 )
                        {
                          Text = (*(__int64 (__fastcall **)(BSTR, const GUID *, _QWORD, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)bstrString + 32LL))(
                                   bstrString,
                                   &CGID_Explorer,
                                   pvData,
                                   (unsigned int)plLbound[0],
                                   v164,
                                   0);
                          (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                        }
                      }
                      else
                      {
                        Text = -2147467259;
                      }
                    }
                    if ( v607.vt == 13 && v607.llVal )
                      (*(void (__fastcall **)(LONGLONG, __int64))(*v607.pllVal + 16))(v607.llVal, v165);
                    goto LABEL_230;
                  }
                  if ( v20 != 2266 )
                  {
                    v607.vt = 3;
                    v169 = 6;
                    if ( v20 != 2130 )
                      v169 = 1;
                    v607.lVal = v169 | 0x20000;
                    goto LABEL_361;
                  }
                  v166 = this[544];
                  bstrString = 0;
                  Text = GetExecDocument((struct CDocument **)&bstrString, v166, v576);
                  if ( Text < 0 )
                    goto LABEL_1650;
                  if ( bstrString )
                  {
                    v167 = *((_QWORD *)bstrString + 7);
                    if ( v167 )
                      v168 = *(CMarkup **)(v167 + 104);
                    else
                      v168 = (CMarkup *)*((_QWORD *)bstrString + 6);
                    if ( !(unsigned int)CMarkup::IsPrimaryMarkup(v168) )
                    {
                      v607.vt = 13;
                      Text = CDocument::QueryInterface((CDocument *)bstrString, &IID_IUnknown, &v607.byref);
                      if ( Text )
                        goto LABEL_1650;
                      v164 = &v607;
                    }
                    plLbound[0] = 1;
                    goto LABEL_362;
                  }
LABEL_350:
                  Text = -2147467259;
                  goto LABEL_1650;
                case 2270:
                  if ( !this[544] )
                  {
                    *(_QWORD *)&String1.vt = 0;
                    v161 = CDoc::GetActiveElement((CDoc *)this);
                    v162 = CElement::GetMarkupPtr(v161);
                    if ( (unsigned int)CMarkup::EnsureCollectionCache(v162, 4) )
                      goto LABEL_344;
                    v163 = CMarkup::CollectionCache(v162);
                    if ( (unsigned int)CCollectionCache::GetElementAtIndex(v163, 4, 0, (struct CElement **)&String1) )
                      goto LABEL_344;
                    if ( *(__int64 (__fastcall **)())(**(_QWORD **)&String1.vt + 1624LL) != _vtguard )
                      _report_securityfailure(1);
                    Text = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(**(_QWORD **)&String1.vt + 368LL))(
                             *(_QWORD *)&String1.vt,
                             v582,
                             v580,
                             a5,
                             a6,
                             a7);
                    if ( Text )
LABEL_344:
                      Text = -2147221248;
                  }
                  goto LABEL_231;
                case 2280:
                  v153 = CDoc::InPlace((CDoc *)this);
                  v154 = CInPlace::_hwnd_Get(v153);
                  v155 = CDoc::InPlace((CDoc *)this);
                  v156 = CInPlace::_hwnd_Get(v155);
                  CMessage::CMessage((CMessage *)Data, v156, 0x7Bu, (unsigned __int64)v154, 0xFFFFFFFFLL);
                  v157 = CDoc::GetActiveElement((CDoc *)this);
                  v158 = CWindowBarProp::SecurityContext(v157);
                  Text = CMessage::SetNodeHit((CMessage *)Data, v158);
                  if ( Text )
                  {
                    CMessage::~CMessage((CMessage *)Data);
                    goto LABEL_1650;
                  }
                  v159 = CDoc::GetActiveElement((CDoc *)this);
                  v160 = CWindowBarProp::SecurityContext(v159);
                  Text = CDoc::PumpMessage((CDoc *)this, (struct CMessage *)Data, v160, 0);
                  CMessage::~CMessage((CMessage *)Data);
                  goto LABEL_231;
                case 2282:
                case 2283:
                  if ( (*((_DWORD *)this + 1215) & 0x40000000) != 0 )
                  {
                    inserted = CDoc::FollowHistory((CDoc *)this, plLbound[0] == 2283);
                  }
                  else
                  {
                    v152 = -1;
                    if ( plLbound[0] != 2282 )
                      v152 = 1;
                    inserted = CDoc::Travel((CDoc *)this, v152);
                  }
                  goto LABEL_306;
              }
              if ( plLbound[0] != 2295 )
              {
                if ( plLbound[0] != 2296 )
                  goto LABEL_231;
                if ( a6 && a6->vt == 11 )
                {
                  v146 = *((_QWORD *)v576 + 7);
                  if ( v146 )
                    v147 = *(CMarkup **)(v146 + 104);
                  else
                    v147 = (CMarkup *)*((_QWORD *)v576 + 6);
                  CMarkup::SetPrintTemplate(v147, a6->bVal != 0);
                  v148 = CMarkup::EnsureEditContext(v147);
                  if ( v148 )
                    *((_DWORD *)v148 + 10) |= 0x80u;
                  goto LABEL_53;
                }
                goto LABEL_131;
              }
              if ( a7 )
              {
                v149 = v576;
                Text = 0;
                a7->vt = 11;
                v150 = *((_QWORD *)v149 + 7);
                if ( v150 )
                  v151 = *(CMarkup **)(v150 + 104);
                else
                  v151 = (CMarkup *)*((_QWORD *)v149 + 6);
                a7->iVal = -((unsigned int)CMarkup::IsPrintTemplate(v151) != 0);
                goto LABEL_1648;
              }
LABEL_330:
              Text = -2147467261;
              goto LABEL_1650;
            }
LABEL_835:
            v318 = 0;
            if ( plLbound[0] == 2300 && a6 && a6->vt == 3 )
              v318 = (a6->lVal & 0x7FF0000) != 0;
            v319 = this[540];
            if ( v319 )
              Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v319 + 32LL))(
                       v319,
                       &CGID_DocHostCommandHandler,
                       (unsigned int)plLbound[0],
                       a5,
                       a6,
                       a7);
            if ( Text >= 0 )
              goto LABEL_1582;
            if ( ((plLbound[0] - 6041) & 0xFFFFFFFD) != 0 && !v318 )
            {
              v320 = this[544];
              v321 = v320 ? CElement::GetMarkupPtr(v320) : CDocument::Markup(v576);
              if ( v321 )
              {
                v322 = CMarkup::GetFrameOrPrimaryMarkup(v321, 1);
                if ( v322 )
                  CMarkup::Window(v322);
              }
            }
            Gwnd = GetGwnd();
            inserted = _GWPostMethodCallEx(Gwnd, 0, 0);
            goto LABEL_306;
          }
          switch ( plLbound[0] )
          {
            case 2302:
              if ( a6 && a6->vt == 3 )
              {
                lVal = a6->lVal;
                if ( ((*((_DWORD *)this + 1215) >> 4) & 1) != (lVal != 0) )
                {
                  CNotification::CNotification((CNotification *)&v589);
                  v362 = ((_DWORD)this[608] & 0x80000) == 0;
                  *((_DWORD *)this + 1215) ^= ((unsigned __int8)*((_DWORD *)this + 1215)
                                             ^ (unsigned __int8)(16 * lVal))
                                            & 0x10;
                  if ( !v362 )
                  {
                    v181 = *((_DWORD *)this + 45);
                    v182 = CDoc::PrimaryRoot((CDoc *)this);
                    CNotification::EnableInteraction1((CNotification *)&v589, v182, 0);
                    CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v589);
                    if ( !v181 )
                    {
                      if ( *((_DWORD *)this + 45) )
                        *((_DWORD *)this + 45) = 0;
                    }
                  }
                  v183 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + (unsigned int)tls_index)
                                               + 16LL)
                                   + 208LL);
                  if ( v183 )
                    CImgAnim::SetAnimState(v183, this, lVal == 0);
                }
                goto LABEL_53;
              }
              goto LABEL_131;
            case 2310:
              v178 = CDoc::PrimaryMarkup((CDoc *)this);
              ScriptCollection = CMarkup::GetScriptCollection(v178, 1);
              if ( ScriptCollection )
              {
                inserted = CScriptCollection::ViewSourceInDebugger(ScriptCollection, 0, 0);
                goto LABEL_306;
              }
              break;
            case 2311:
              v176 = this[809];
              if ( v176 && CPeerFactoryUrl::GetUrl(v176) )
              {
                Url = CPeerFactoryUrl::GetUrl(this[809]);
                inserted = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)Url + 32LL))(Url);
                goto LABEL_306;
              }
              break;
            case 2316:
              if ( !a6 || a6->vt != 11 )
                goto LABEL_131;
              *((_DWORD *)this + 1217) = *((_DWORD *)this + 1217) & 0xFFFFFEFF | (a6->iVal != 0 ? 0x100 : 0);
              *(GUID *)&v607.vt = CGID_MSHTML;
              CDoc::Exec((CDoc *)this, (const struct _GUID *)&v607, 0x90Eu, 0, a6, 0);
              goto LABEL_53;
            case 2317:
              v175 = 0;
LABEL_380:
              inserted = CDoc::OnSettingsChange((CDoc *)this, v175, 0);
              goto LABEL_306;
            default:
              if ( (unsigned int)(plLbound[0] - 2320) > 1 )
                goto LABEL_231;
LABEL_376:
              CVariant::CVariant((CVariant *)&pvarg);
              v173 = CDocument::Markup(v576);
              GlyphTable = CMarkup::GetGlyphTable(v173);
              if ( a6 )
              {
                if ( a6->vt != 11 )
                {
LABEL_378:
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_231;
                }
                v201 = a6->iVal != 0;
LABEL_477:
                if ( !v201 && (plLbound[0] == 2327 || plLbound[0] == 2320) )
                  v20 = 2336;
                v203 = CDocument::Markup(v576);
                Text = CMarkup::EnsureGlyphTableExistsAndExecute(v203, v582, v20, a5, v7, a7);
                if ( !Text )
                {
                  if ( v20 != 2336 )
                  {
                    if ( ((((v204 = CDocument::Markup(v576), v205 = CMarkup::GetGlyphTable(v204), v20 == 2327)
                         || v20 == 2321)
                        && (*(_DWORD *)v205 ^= (*(_DWORD *)v205 ^ v201) & 1, v20 == 2327)
                        || v20 == 2322)
                       && (*(_DWORD *)v205 ^= (*(_DWORD *)v205 ^ (2 * v201)) & 2, v20 == 2327)
                       || v20 == 2323)
                      && (*(_DWORD *)v205 &= ~8u, *(_DWORD *)v205 |= 8 * v201, v20 == 2327)
                      || v20 == 2324 )
                    {
                      *(_DWORD *)v205 &= ~4u;
                      *(_DWORD *)v205 |= 4 * v201;
                      if ( v20 == 2327 )
                        goto LABEL_1659;
                    }
                    if ( v20 == 2325 )
                    {
LABEL_1659:
                      *(_DWORD *)v205 &= ~0x10u;
                      *(_DWORD *)v205 |= 16 * v201;
                      if ( v20 == 2327 )
                        goto LABEL_1658;
                    }
                    if ( v20 == 2320 )
                    {
LABEL_1658:
                      *(_DWORD *)v205 &= ~0x40u;
                      *(_DWORD *)v205 |= v201 << 6;
                      if ( v20 == 2327 )
                        goto LABEL_1657;
                    }
                    if ( v20 == 2326 )
                    {
LABEL_1657:
                      *(_DWORD *)v205 ^= (*(_DWORD *)v205 ^ (32 * v201)) & 0x20;
                      if ( v20 == 2327 )
                        goto LABEL_499;
                    }
                    if ( v20 == 2340 )
LABEL_499:
                      *(_DWORD *)v205 ^= (*(_DWORD *)v205 ^ (v201 << 7)) & 0x80;
                  }
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_1582;
                }
                goto LABEL_378;
              }
              if ( GlyphTable )
              {
                v201 = 0;
                if ( plLbound[0] != 2320 )
                {
                  if ( plLbound[0] == 2321 )
                  {
                    v202 = *(_DWORD *)GlyphTable;
                  }
                  else if ( plLbound[0] == 2322 )
                  {
                    v202 = *(_DWORD *)GlyphTable >> 1;
                  }
                  else if ( plLbound[0] == 2323 )
                  {
                    v202 = *(_DWORD *)GlyphTable >> 3;
                  }
                  else if ( plLbound[0] == 2324 )
                  {
                    v202 = *(_DWORD *)GlyphTable >> 2;
                  }
                  else if ( plLbound[0] == 2325 )
                  {
                    v202 = *(_DWORD *)GlyphTable >> 4;
                  }
                  else
                  {
                    if ( plLbound[0] != 2326 )
                    {
                      if ( plLbound[0] == 2327 )
                      {
                        LOBYTE(v201) = *(_BYTE *)GlyphTable != 0xFF;
                      }
                      else if ( plLbound[0] == 2340 )
                      {
                        v201 = (*(_DWORD *)GlyphTable & 0x80) == 0;
                      }
LABEL_472:
                      pvarg.vt = 11;
                      if ( !v201 )
                      {
                        pvarg.iVal = 0;
LABEL_476:
                        v7 = &pvarg;
                        v25 = 1;
                        goto LABEL_477;
                      }
LABEL_475:
                      pvarg.iVal = -1;
                      goto LABEL_476;
                    }
                    v202 = *(_DWORD *)GlyphTable >> 5;
                  }
                  v201 = (v202 & 1) == 0;
                  goto LABEL_472;
                }
                if ( (*(_BYTE *)GlyphTable & 0x40) != 0 )
                  goto LABEL_472;
              }
              v201 = 1;
              pvarg.vt = 11;
              goto LABEL_475;
          }
          Text = -2147418113;
          goto LABEL_231;
        }
        if ( plLbound[0] > 0x91Cu )
        {
          if ( plLbound[0] != 2333 && plLbound[0] != 2334 )
          {
            if ( plLbound[0] != 2335 )
            {
              if ( plLbound[0] != 2336 && (plLbound[0] != 2337 && (unsigned int)(plLbound[0] - 2338) > 1 || !a6->llVal) )
                goto LABEL_231;
              v186 = CDocument::Markup(v576);
              inserted = CMarkup::EnsureGlyphTableExistsAndExecute(v186, v582, plLbound[0], a5, a6, a7);
              goto LABEL_306;
            }
            goto LABEL_420;
          }
        }
        else if ( plLbound[0] != 2332 )
        {
          if ( plLbound[0] == 2323
            || plLbound[0] == 2324
            || plLbound[0] == 2325
            || plLbound[0] == 2326
            || plLbound[0] == 2327 )
          {
            goto LABEL_376;
          }
          if ( plLbound[0] != 2328 )
          {
            if ( plLbound[0] != 2331 )
              goto LABEL_231;
            if ( a7 )
            {
              v184 = CDocument::Markup(v576);
              DwnDoc = CMarkup::GetDwnDoc(v184);
              a7->vt = 3;
              if ( DwnDoc )
                LODWORD(DwnDoc) = CDwnDoc::GetBytesRead(DwnDoc);
              a7->lVal = (int)DwnDoc;
              goto LABEL_231;
            }
            goto LABEL_330;
          }
LABEL_420:
          v187 = CDocument::Markup(v576);
          v188 = v187;
          if ( a6 && a6->vt == 11 )
            v189 = a6->bVal != 0;
          else
            v189 = !CMarkup::IsShowZeroBorderAtDesignTime(v187);
          if ( plLbound[0] == 2328 )
          {
            CMarkup::SetShowZeroBorderAtDesignTime(v188, v189);
            CNotification::CNotification((CNotification *)&v589);
            ElementTopHelper = CMarkup::GetElementTopHelper(v188);
            CNotification::ZeroGrayChange((CNotification *)&v589, ElementTopHelper);
            CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v589);
            CDoc::Invalidate((CDoc *)this);
          }
          else
          {
            *((_DWORD *)this + 1216) &= ~0x10u;
            *((_DWORD *)this + 1216) |= 16 * v189;
          }
          Text = 0;
          *((_DWORD *)this[126] + 23) = *CDoc::_dwMiscFlags((CDoc *)this);
          TopLayoutElement = CMarkup::GetTopLayoutElement(v188);
          if ( TopLayoutElement )
            CElement::ResizeElement(TopLayoutElement, 0x800000u);
          COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v608);
          *(_QWORD *)v608 = v582;
          *(_DWORD *)&v608[8] = v580;
          CNotification::CNotification((CNotification *)&v589);
          if ( v20 == 2328 )
            v192 = CMarkup::Root(v188);
          else
            v192 = CDoc::PrimaryRoot((CDoc *)this);
          CNotification::Command((CNotification *)&v589, v192, v608, 0);
          CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v589);
          goto LABEL_1647;
        }
        if ( a6 && a6->vt == 11 )
        {
          bVal = a6->bVal;
          v194 = *((_DWORD *)this + 1428);
          if ( plLbound[0] == 2332 )
          {
            v195 = bVal != 0 ? 0x100 : 0;
            v196 = v194 & 0xFFFFFEFF;
          }
          else if ( plLbound[0] == 2333 )
          {
            v195 = bVal != 0 ? 0x200 : 0;
            v196 = v194 & 0xFFFFFDFF;
          }
          else
          {
            v195 = bVal != 0 ? 0x400 : 0;
            v196 = v194 & 0xFFFFFBFF;
          }
          *((_DWORD *)this + 1428) = v196 | v195;
          Text = 0;
          *((_DWORD *)this[126] + 23) = *CDoc::_dwMiscFlags((CDoc *)this);
          goto LABEL_441;
        }
        goto LABEL_231;
      }
      if ( plLbound[0] <= 0xF40u )
      {
        if ( plLbound[0] == 3904 )
        {
          if ( a6 )
          {
            if ( a6->vt == 3 )
            {
              Text = 0;
              if ( this[12] )
              {
                CPoint::CPoint((CPoint *)&ppvData, a6->iVal, (__int16)HIWORD(a6->lVal));
                CInPlace::ScreenToClient(this[12], 0xFFFFFF00, (struct tagPOINT *)&ppvData);
                bstrString = 0;
                Text = CDocument::ElementFromPoint(
                         v576,
                         (float)(int)ppvData,
                         (float)SHIDWORD(ppvData),
                         0,
                         0,
                         0,
                         (struct IHTMLElement **)&bstrString);
                if ( Text >= 0 )
                {
                  if ( bstrString )
                  {
                    Text = DevToolbarHelper::InspectElement((struct IUnknown *)bstrString);
                    if ( Text && a7 )
                    {
                      v294 = (struct IUnknown *)bstrString;
                      a7->vt = 8;
                      Text = CDiagnosticsDom::GetDiagnosticsUniqueId(v294, &a7->bstrVal);
                    }
                    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                  }
                  else if ( a7 )
                  {
                    a7->vt = 3;
                    a7->lVal = 1;
                  }
                }
                CDispClient::AdjustContentSize((CDispClient *)&ppvData, v292, v293);
              }
            }
          }
          goto LABEL_231;
        }
        if ( plLbound[0] <= 0x97Fu )
        {
          if ( plLbound[0] != 2431 )
          {
            if ( plLbound[0] <= 0x963u )
            {
              if ( plLbound[0] != 2403 )
              {
                if ( plLbound[0] == 2341 )
                {
                  *((_DWORD *)this + 1215) |= 0x4000u;
                  goto LABEL_53;
                }
                if ( plLbound[0] != 2342 )
                {
                  switch ( plLbound[0] )
                  {
                    case 2343:
                      if ( a6 && a6->vt == 8 )
                      {
                        v215 = CDocument::Markup(v576);
                        v216 = CMarkup::Window(v215);
                        v217 = COptionsHolder::SecurityContext(v216);
                        inserted = ShowModalDialogHelper(
                                     v215,
                                     a6->bstrVal,
                                     (struct IDispatch *)(((unsigned __int64)v217 + 48) & -(__int64)(v217 != 0)),
                                     0,
                                     0,
                                     0x4000010u);
                        goto LABEL_306;
                      }
                      break;
                    case 2350:
                    case 2351:
                      *(_QWORD *)&String1.vt = 0;
                      v214 = CBase::OpenParentUnit((CBase *)this, (struct CBase *)this, 0x8D6u, 0);
                      Text = GetExecDocument((struct CDocument **)&String1, this[544], v576);
                      if ( Text >= 0 )
                        Text = CDocument::SetDocDirection(
                                 *(CDocument **)&String1.vt,
                                 (unsigned int)(plLbound[0] != 2350) + 1);
                      CBase::CloseParentUnit((CBase *)this, v214, Text);
                      goto LABEL_231;
                    case 2370:
                      if ( a6 )
                      {
                        if ( a6->vt == 8 )
                        {
                          v212 = a6->bstrVal;
                          if ( v212 )
                          {
                            v213 = CDocument::Markup(v576);
                            inserted = CDoc::SavePretransformedSource((CDoc *)this, v213, v212);
                            goto LABEL_306;
                          }
                        }
                      }
                      break;
                    case 2371:
LABEL_514:
                      v206 = this[544];
                      if ( v206 )
                        v207 = CElement::GetMarkupPtr(v206);
                      else
                        v207 = CDocument::Markup(v576);
                      if ( !v207
                        || (v208 = CMarkup::GetFrameOrPrimaryMarkup(v207, 1), (v209 = v208) == 0)
                        || (unsigned int)CMarkup::IsImageFile(v208) )
                      {
                        Text = 0;
                        goto LABEL_1582;
                      }
                      if ( plLbound[0] != 2139
                        || !(unsigned int)CMarkup::IsPrimaryMarkup(v209)
                        || !(unsigned int)CDoc::IsAggregatedByXMLMime((CDoc *)this) )
                      {
                        Text = CDoc::GetViewSourceFileName((CDoc *)this, psz, 0x823u, v209);
                        if ( Text < 0 )
                          goto LABEL_1581;
                        if ( (unsigned int)IsDefaultViewSourceEditor()
                          && (unsigned __int8)IEConfiguration_GetBool(268435500)
                          && !IsDualEngineProcess() )
                        {
                          Text = 0;
                          if ( (unsigned int)DevToolbarHelper::ViewSource(psz) && a7 )
                          {
                            a7->vt = 8;
                            a7->llVal = (LONGLONG)SysAllocString(psz);
                          }
                        }
                        else
                        {
                          CDoc::InvokeEditor((CDoc *)this, psz);
                        }
                        goto LABEL_1582;
                      }
                      bstrString = 0;
                      v210 = CDOMStringMap::SecurityContext((CDOMStringMap *)this);
                      if ( (**(unsigned int (__fastcall ***)(struct CSecurityContext *, GUID *, BSTR *))v210)(
                             v210,
                             &IID_IOleCommandTarget,
                             &bstrString)
                        || !bstrString )
                      {
                        goto LABEL_231;
                      }
                      (*(void (__fastcall **)(BSTR, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)bstrString + 32LL))(
                        bstrString,
                        v582,
                        v580,
                        a5,
                        a6,
                        a7);
                      goto LABEL_526;
                    default:
                      goto LABEL_231;
                  }
LABEL_756:
                  Text = -2147024809;
                  goto LABEL_231;
                }
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_131;
                inserted = CDoc::SetDirtyFlag((CDoc *)this, a6->bVal != 0);
LABEL_306:
                Text = inserted;
                goto LABEL_231;
              }
              if ( !a7 || !a6 )
                goto LABEL_330;
              if ( a6->vt != 3 )
                goto LABEL_131;
              a7->vt = 1;
              v218 = 0;
              v219 = a6->lVal;
              plLbound[0] = 0;
              if ( v219 )
              {
                v220 = v219 - 1;
                if ( v220 )
                {
                  if ( v220 == 1 )
                  {
                    v221 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                    if ( v221 )
                    {
                      v222 = *((_QWORD *)v576 + 7);
                      v223 = v222 ? *(_QWORD *)(v222 + 104) : *((_QWORD *)v576 + 6);
                      v218 = CIPrintCollection::CIPrintCollection(v221, *(struct CSecurityContext **)(v223 + 320));
                      if ( v218 )
                      {
                        v224 = *((_QWORD *)v576 + 7);
                        if ( v224 )
                          v225 = *(CMarkup **)(v224 + 104);
                        else
                          v225 = (CMarkup *)*((_QWORD *)v576 + 6);
                        if ( v225 )
                        {
                          v226 = CMarkup::EnsureTopElems(v225);
                          if ( v226 )
                          {
                            v227 = *((_QWORD *)v226 + 4);
                            if ( v227 )
                            {
                              if ( *(_WORD *)(v227 + 56) == 47 )
                              {
                                v590 = *(_QWORD *)(v227 + 48);
                                v595 = 0;
                                v596 = 0;
                                v592 = 0;
                                v589 = 88;
                                v594 = v218;
                                v593 = 18436;
                                v591 = 0;
                                CNotification::SetElement((CNotification *)&v589, (struct CElement *)v227);
                                CMarkup::Notify(v225, (struct CNotification *)&v589, 0);
                              }
                            }
                          }
                        }
                        goto LABEL_600;
                      }
                    }
LABEL_895:
                    Text = -2147024882;
                    goto LABEL_1650;
                  }
LABEL_600:
                  v241 = (CIPrintCollection *)((char *)v218 + 48);
                  if ( !(unsigned int)CIPrintCollection::get_length((CIPrintCollection *)((char *)v218 + 48), plLbound)
                    && plLbound[0] > 0 )
                  {
                    COMRect::AddRef((CIPrintCollection *)((char *)v218 + 48));
                    a7->vt = 13;
                    a7->llVal = (unsigned __int64)v241 & -(__int64)(v218 != 0);
                  }
                  CAutoRange::Release(v241);
                  Text = 0;
                  goto LABEL_1649;
                }
                if ( !CDoc::GetActiveElement((CDoc *)this) )
                  goto LABEL_600;
                v228 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                if ( !v228 )
                  goto LABEL_895;
                v229 = CDoc::GetActiveElement((CDoc *)this);
                v230 = CElement::GetMarkupPtr(v229);
                v218 = CIPrintCollection::CIPrintCollection(v228, *((struct CSecurityContext **)v230 + 40));
                if ( !v218 )
                  goto LABEL_895;
                v231 = CDoc::GetActiveElement((CDoc *)this);
                v232 = (CTreePos *)*((_QWORD *)CElement::GetMarkupPtr(v231) + 68);
                v233 = v232 ? *(_QWORD *)CTreePos::Branch(v232) : 0LL;
                if ( (*(_DWORD *)(v233 + 60) & 0x200) == 0 )
                  goto LABEL_600;
                LookasidePtr2 = CElement::GetLookasidePtr2(v233, 0);
                if ( *(_WORD *)(LookasidePtr2 + 56) != 46 && *(_WORD *)(LookasidePtr2 + 56) != 60 )
                  goto LABEL_600;
                bstrString = 0;
                if ( !(unsigned int)CFrameContentHelper::GetPrintObject(
                                      (CFrameContentHelper *)(LookasidePtr2 + 96),
                                      (struct IPrint **)&bstrString) )
                {
                  *(_QWORD *)&String1.vt = bstrString;
                  if ( !(unsigned int)CImplAry::AppendIndirect<8>((char *)v218 + 56, &String1, 0) )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&String1.vt + 8LL))(*(_QWORD *)&String1.vt);
                }
                v235 = bstrString;
              }
              else
              {
                v236 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                if ( !v236 )
                  goto LABEL_895;
                v237 = *((_QWORD *)v576 + 7);
                v238 = v237 ? *(_QWORD *)(v237 + 104) : *((_QWORD *)v576 + 6);
                v218 = CIPrintCollection::CIPrintCollection(v236, *(struct CSecurityContext **)(v238 + 320));
                if ( !v218 )
                  goto LABEL_895;
                v239 = CDocument::Window(v576);
                if ( !v239 )
                  goto LABEL_600;
                v240 = (struct IUnknown *)*((_QWORD *)v239 + 43);
                if ( !v240 )
                  goto LABEL_600;
                bstrString = 0;
                ppvData = 0;
                if ( !(unsigned int)GetWebOCDocument(v240, (struct IDispatch **)&bstrString) )
                  (**(void (__fastcall ***)(BSTR, GUID *, void **))bstrString)(bstrString, &IID_IPrint, &ppvData);
                if ( ppvData )
                {
                  *(_QWORD *)&String1.vt = ppvData;
                  if ( !(unsigned int)CImplAry::AppendIndirect<8>((char *)v218 + 56, &String1, 0) )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&String1.vt + 8LL))(*(_QWORD *)&String1.vt);
                }
                if ( bstrString )
                  (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                v235 = ppvData;
              }
              if ( v235 )
                (*(void (__fastcall **)(void *))(*(_QWORD *)v235 + 16LL))(v235);
              goto LABEL_600;
            }
            if ( plLbound[0] == 2405 )
            {
              v255 = *((_QWORD *)v576 + 7);
              if ( v255 )
                v256 = *(CMarkup **)(v255 + 104);
              else
                v256 = (CMarkup *)*((_QWORD *)v576 + 6);
              if ( a6 && a6->vt == 11 )
              {
                v257 = *((_DWORD *)v256 + 187);
                v258 = -(a6->bVal != 0);
              }
              else
              {
                v257 = *((_DWORD *)v256 + 187);
                LOWORD(v258) = ~(_WORD)v257;
              }
              *((_DWORD *)v256 + 187) = v257 & 0xFFFFBFFF | v258 & 0x4000;
              if ( v256 == CDoc::PrimaryMarkup((CDoc *)this) )
                CDoc::ForceRelayout((CDoc *)this, 0);
              else
                CMarkup::ForceRelayout(v256, 0);
              goto LABEL_53;
            }
            if ( plLbound[0] == 2408 )
            {
              if ( a6 && a6->vt == 3 )
              {
                if ( *((char *)this + 4868) >= 0 && !(unsigned __int8)IEConfiguration_GetBool(268435481) )
                {
                  v249 = this[8];
                  Text = 0;
                  if ( v249 )
                  {
                    bstrString = 0;
                    v250 = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, BSTR *))v249)(
                             v249,
                             &IID_IOleCommandTarget,
                             &bstrString);
                    v251 = (struct IUnknown *)bstrString;
                    Text = v250;
                    if ( !v250 && bstrString )
                    {
                      v252 = (*(__int64 (__fastcall **)(BSTR, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, _QWORD))(*(_QWORD *)bstrString + 32LL))(
                               bstrString,
                               &CGID_DocHostCommandHandler,
                               (unsigned int)(v250 + 48),
                               0,
                               a6,
                               0);
                      v251 = (struct IUnknown *)bstrString;
                      Text = v252;
                    }
                    ReleaseInterface(v251);
                  }
                }
                if ( !a6->lVal )
                {
                  v362 = (*((_DWORD *)this + 1237))-- == 1;
                  if ( v362 && (*((_DWORD *)this + 1217) & 0x4000) != 0 )
                  {
                    v253 = v576;
                    if ( v576 )
                    {
                      if ( CDocument::Window(v576) )
                      {
                        *((_DWORD *)this + 1217) &= ~0x4000u;
                        v254 = CDocument::Window(v253);
                        CWindow::close((struct CWindow *)((char *)v254 + 48));
                      }
                    }
                  }
                }
                goto LABEL_231;
              }
              goto LABEL_756;
            }
            if ( plLbound[0] != 2411 )
            {
              switch ( plLbound[0] )
              {
                case 2420:
                  v245 = CDocument::Markup(v576);
                  v246 = v245;
                  if ( a6 && a6->vt == 11 )
                  {
                    v25 = a6->bVal != 0;
                  }
                  else if ( (unsigned int)CMarkup::HasEditContext(v245)
                         && (*((_BYTE *)CMarkup::GetEditContext(v246) + 40) & 2) != 0 )
                  {
                    v25 = 0;
                  }
                  if ( CMarkup::EnsureEditContext(v246) )
                  {
                    v247 = CMarkup::GetEditContext(v246);
                    *((_DWORD *)v247 + 10) &= ~2u;
                    *((_DWORD *)v247 + 10) |= 2 * v25;
                  }
                  goto LABEL_53;
                case 2423:
                  *((_DWORD *)this + 1217) = *((_DWORD *)this + 1217) & 0xFEFFFFFF
                                           | ~*((_DWORD *)this + 1217) & 0x1000000;
                  goto LABEL_53;
                case 2425:
                  if ( a6 && a6->vt == 11 )
                    v244 = a6->bVal != 0;
                  else
                    v244 = ((*((_DWORD *)this + 1217) >> 25) & 1) == 0;
                  *((_DWORD *)this + 1217) &= ~0x2000000u;
                  *((_DWORD *)this + 1217) |= v244 << 25;
                  goto LABEL_53;
              }
              if ( plLbound[0] != 2430 )
                goto LABEL_231;
              if ( a6 && a6->vt == 11 )
              {
                v242 = a6->bVal != 0 ? 0x4000000 : 0;
                v243 = *((_DWORD *)this + 1217) & 0xFBFFFFFF;
                goto LABEL_614;
              }
LABEL_131:
              Text = -2147024809;
              goto LABEL_1650;
            }
            v248 = CDocument::Markup(v576);
            if ( !(unsigned int)CMarkup::IsConnectedToPrimaryMarkup(v248) )
            {
              CMarkup::TearDownMarkup(v248, 1, 0);
              goto LABEL_53;
            }
LABEL_630:
            Text = -2147418113;
            goto LABEL_1650;
          }
          if ( !a7 )
            goto LABEL_131;
          VariantInit(a7);
          a7->vt = 19;
          NormZoomPercent = *((_DWORD *)this + 1245);
          goto LABEL_933;
        }
        if ( plLbound[0] <= 0x988u )
        {
          switch ( plLbound[0] )
          {
            case 2440:
              Text = 0;
              v271 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&String1.vt = v271;
              if ( !v271 || !a6 || a6->vt != 8 )
                goto LABEL_1647;
              if ( CMarkup::GetStyleState(v271) )
              {
                StyleState = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                CStr::~CStr((struct CMarkupStyleState *)((char *)StyleState + 8));
                v273 = *(CMarkup **)&String1.vt;
                v274 = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                if ( !(unsigned int)CStr::IsNull(v274) )
                {
                  v275 = CMarkup::GetStyleState(v273);
                  if ( (unsigned int)CStr::IsNull(v275) )
                    goto LABEL_1647;
                  v276 = CMarkup::GetStyleState(v273);
                  v277 = CDispSurface::UseRenderTarget(v276);
                  v278 = a6;
                  v279 = v277 - (struct IDispRenderTarget *)a6;
                  do
                  {
                    v280 = *(unsigned __int16 *)((char *)&v278->vt + v279);
                    v281 = v278->vt - v280;
                    if ( v281 )
                      break;
                    v278 = (struct tagVARIANT *)((char *)v278 + 2);
                  }
                  while ( v280 );
                  if ( !v281 )
                    goto LABEL_1647;
                }
                v282 = CMarkup::GetStyleState(v273);
                inserted = CStr::SetBSTR((struct CMarkupStyleState *)((char *)v282 + 8), a6->bstrVal);
                goto LABEL_306;
              }
              break;
            case 2432:
              CDoc::BeginUserInitiatedAction((CDoc *)this, 0);
              goto LABEL_53;
            case 2433:
              CDoc::EndUserInitiatedAction((CDoc *)this);
              goto LABEL_53;
            case 2434:
              Text = -2147024809;
              if ( !a6 || a6->vt != 21 )
                goto LABEL_1650;
              this[625] = (CInPlace *)a6->llVal;
              goto LABEL_53;
            case 2436:
              Text = 0;
              if ( a6 )
              {
                if ( a6->vt != 11 )
                  goto LABEL_131;
                v270 = a6->bVal;
                if ( (v270 == 0) == (((*((_DWORD *)this + 1215) >> 17) & 1) == 0) )
                  goto LABEL_1647;
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | (v270 != 0 ? 0x20000 : 0);
              }
              else
              {
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | ~*((_DWORD *)this + 1215) & 0x20000;
              }
              CDoc::NotifySelection(this, 17, 0);
              goto LABEL_1647;
            case 2437:
              Text = 0;
              v266 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v607.vt = v266;
              v267 = v266;
              if ( !v266 || !a6 || a6->vt != 11 )
                goto LABEL_1647;
              if ( CMarkup::GetStyleState(v266) )
              {
                CMarkup::CLock::CLock((CMarkup::CLock *)&String1, v267);
                v268 = *(_QWORD *)&v607.vt;
                v269 = a6->bVal != 0;
                *((_BYTE *)CMarkup::GetStyleState(*(CMarkup **)&v607.vt) + 24) = v269;
                if ( *(__int64 (__fastcall **)())(*(_QWORD *)v268 + 984LL) != _vtguard )
                  _report_securityfailure(1);
                Text = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v268 + 224LL))(v268, 3);
                CMarkup::CLock::~CLock((CMarkup::CLock *)&String1);
                goto LABEL_231;
              }
              break;
            case 2438:
              Text = 0;
              v264 = CDoc::PrimaryMarkup((CDoc *)this);
              v265 = v264;
              if ( !v264 || a7->vt != 11 )
                goto LABEL_1647;
              a7->iVal = 0;
              if ( CMarkup::GetStyleState(v264) )
              {
                if ( *((_BYTE *)CMarkup::GetStyleState(v265) + 24) )
                  a7->iVal = -1;
                goto LABEL_1648;
              }
              goto LABEL_895;
            case 2439:
              Text = 0;
              v260 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v607.vt = v260;
              if ( !v260 )
                goto LABEL_1647;
              a7->llVal = 0;
              if ( !CMarkup::GetStyleState(v260) )
              {
                Text = -2147024882;
                goto LABEL_1581;
              }
              if ( a7->vt != 8 )
                goto LABEL_1647;
              v261 = *(CMarkup **)&v607.vt;
              v262 = CMarkup::GetStyleState(*(CMarkup **)&v607.vt);
              if ( (unsigned int)CStr::IsNull(v262) )
                goto LABEL_1648;
              v263 = CMarkup::GetStyleState(v261);
              Text = CStr::AllocBSTR(v263, &a7->bstrVal);
              if ( Text < 0 )
              {
                a7->llVal = 0;
                goto LABEL_1581;
              }
              goto LABEL_1603;
            default:
              goto LABEL_231;
          }
LABEL_1404:
          Text = -2147024882;
          goto LABEL_231;
        }
        switch ( plLbound[0] )
        {
          case 3733:
            if ( a7 )
            {
              if ( !this[126] )
              {
                Text = -2147221247;
                goto LABEL_1650;
              }
              a7->vt = 3;
              Text = 0;
              a7->lVal = *((_DWORD *)this[126] + 33);
              goto LABEL_1648;
            }
            goto LABEL_131;
          case 3800:
            if ( !a6 )
              goto LABEL_756;
            if ( a6->vt == 13 )
            {
              punkVal = a6->punkVal;
              if ( punkVal )
              {
                if ( a7 )
                {
                  v97 = DevToolbarHelper::AddConsoleMessageReceiver(punkVal, a7);
                  goto LABEL_229;
                }
              }
            }
            break;
          case 3801:
            if ( a6 && a6->vt == 19 )
            {
              inserted = DevToolbarHelper::RemoveConsoleMessageReceiver(a6->cyVal.Lo);
              goto LABEL_306;
            }
            goto LABEL_756;
          case 3802:
            Text = -2147024809;
            if ( !a6 || a6->vt != 8200 )
              goto LABEL_1650;
            CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
            v284 = a6->parray;
            *(_QWORD *)&v607.vt = v284;
            if ( v284 && SafeArrayGetDim(v284) == 1 )
            {
              plLbound[0] = 0;
              pvData = 0;
              pvt[0] = 0;
              Text = SafeArrayGetLBound(v284, 1u, plLbound);
              if ( !Text )
              {
                Text = SafeArrayGetUBound(v284, 1u, (LONG *)&pvData);
                if ( !Text )
                {
                  Text = SafeArrayGetVartype(v284, pvt);
                  if ( !Text )
                    Text = SafeArrayGetVartype(v284, pvt);
                }
              }
              if ( plLbound[0] || (v285 = pvData, pvData > 3) || pvt[0] != 8 )
              {
                Text = -2147024809;
              }
              else
              {
                v286 = *(SAFEARRAY **)&v607.vt;
                v287 = 0;
                v288 = 0;
                memset(v608, 0, sizeof(v608));
                rgIndices[0] = 0;
                do
                {
                  if ( !Text )
                  {
                    Element = SafeArrayGetElement(v286, rgIndices, &v608[8 * v288]);
                    v285 = pvData;
                    Text = Element;
                    v287 = rgIndices[0];
                  }
                  rgIndices[0] = ++v287;
                  v288 = v287;
                }
                while ( v287 <= v285 );
                if ( !Text )
                {
                  v290 = (struct IUnknown **)TSmartPointer<ID3D11Device>::operator&(&bstrString);
                  Text = CDoc::InitializeDiagnosticsMode(
                           (CDoc *)this,
                           *(const unsigned __int16 **)v608,
                           *(const unsigned __int16 **)&v608[8],
                           *(const unsigned __int16 **)&v608[16],
                           *(const unsigned __int16 **)&v608[24],
                           v290);
                  if ( !Text )
                  {
                    if ( a7 )
                    {
                      a7->vt = 13;
                      a7->llVal = TSmartPointer<IUnknown>::Extract(&bstrString);
                    }
                  }
                }
              }
            }
            TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&bstrString);
            goto LABEL_231;
          case 3803:
            Text = -2147024809;
            if ( !a7 )
              goto LABEL_1650;
            *(_QWORD *)&String1.vt = 0;
            Text = CDoc::CreateServiceW(
                     (CDoc *)this,
                     (const struct _GUID *)&SID_GetScriptEngine,
                     &GUID_bb1a2ae1_a4f9_11cf_8f20_00805f2cd064,
                     (void **)&String1);
            if ( Text )
              goto LABEL_231;
            a7->llVal = *(_QWORD *)&String1.vt;
            a7->vt = 13;
            goto LABEL_1648;
          case 3804:
            if ( !a6 )
              goto LABEL_756;
            if ( a6->vt == 13 )
            {
              v283 = a6->punkVal;
              if ( v283 )
              {
                if ( a7 )
                {
                  plLbound[0] = 0;
                  Text = CDebugCallbackNotificationHandlers::AddCallbackNotificationHandler(
                           (CDebugCallbackNotificationHandlers *)(this + 812),
                           v283,
                           (unsigned int *)plLbound);
                  a7->vt = 19;
                  a7->lVal = plLbound[0];
                  goto LABEL_230;
                }
              }
            }
            break;
          case 3805:
            if ( a6 && a6->vt == 19 )
            {
              CDebugCallbackNotificationHandlers::RemoveCallbackNotificationHandler(
                (CDebugCallbackNotificationHandlers *)(this + 812),
                a6->cyVal.Lo);
              goto LABEL_53;
            }
            goto LABEL_131;
          default:
            goto LABEL_231;
        }
LABEL_755:
        v25 = 1;
        goto LABEL_756;
      }
      if ( plLbound[0] <= 0x17A1u )
      {
        if ( plLbound[0] == 6049 )
        {
          if ( !a6 || a6->vt != 11 )
            goto LABEL_131;
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL)
                   + 578LL) = a6->iVal != 0;
          goto LABEL_53;
        }
        if ( plLbound[0] <= 0x1795u )
        {
          switch ( plLbound[0] )
          {
            case 6037:
              if ( a7 )
              {
                v311 = this[103];
                if ( v311 )
                {
                  v312 = COmWindowProxy::Markup(v311);
                  Text = CMarkup::GetFrameZone(v312, a7, 0);
                }
                if ( Text || !this[103] )
                {
                  a7->vt = 0;
                  goto LABEL_231;
                }
                goto LABEL_1648;
              }
              goto LABEL_330;
            case 6021:
              if ( !a6 )
                goto LABEL_231;
              pvData = 0;
              v306 = CDoc::PrimaryMarkup((CDoc *)this);
              v307 = CMarkup::GetCodePage(v306);
              v308 = this[544];
              v309 = v307;
              plLbound[0] = 0;
              *(_QWORD *)&String1.vt = 0;
              Text = GetExecDocument((struct CDocument **)&String1, v308, v576);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
              v98 = Text < 0;
              if ( !Text )
              {
                v310 = CDoc::IsCpAutoDetect((CDoc *)this);
                Text = ShowMimeCSetMenu(this[126], (int *)&pvData, v309, a6->lVal, plLbound[0], v310);
                if ( !Text )
                {
                  v20 = pvData;
                  if ( pvData - 3609 > 0x5A )
                  {
                    if ( pvData - 2350 <= 1 )
                      CDoc::ExecHelper((CDoc *)this, v576, &CGID_MSHTML, pvData, 0, 0, 0);
                    goto LABEL_1647;
                  }
                  goto LABEL_1582;
                }
                goto LABEL_231;
              }
              goto LABEL_232;
            case 6028:
              if ( !a6 || a6->vt != 13 )
                goto LABEL_131;
              CDoc::SetPicsCommandTarget((CDoc *)this, (struct IOleCommandTarget *)a6->llVal);
              goto LABEL_53;
            case 6032:
              if ( a6 )
              {
                if ( a6->vt == 8 )
                {
                  v304 = a6->bstrVal;
                  if ( v304 )
                  {
                    v305 = CDocument::Markup(v576);
                    inserted = CDoc::SetUrl((CDoc *)this, v305, v304, 0);
                    goto LABEL_306;
                  }
                }
              }
              goto LABEL_756;
            case 6033:
              if ( !a7 )
                goto LABEL_131;
              a7->vt = 3;
              NormZoomPercent = (*((_DWORD *)this + 1214) >> 3) & 1;
              break;
            case 6034:
            case 6035:
              if ( !a7 )
              {
                Text = 1;
                goto LABEL_1650;
              }
              v303 = CDoc::PrimaryMarkup((CDoc *)this);
              NormZoomPercent = CMarkup::GetCodePage(v303);
              if ( plLbound[0] == 6034 )
                NormZoomPercent = WindowsCodePageFromCodePage(NormZoomPercent);
              a7->vt = 3;
              break;
            case 6036:
              if ( !a7 )
                goto LABEL_756;
              v295 = v576;
              a7->vt = 37;
              v296 = this[544];
              plLbound[0] = 0;
              bstrString = 0;
              Text = GetExecDocument((struct CDocument **)&bstrString, v296, v295);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection((CDocument *)bstrString, plLbound);
              v98 = Text < 0;
              if ( !Text )
              {
                v297 = CDocument::Markup((CDocument *)bstrString);
                v298 = CDoc::IsCpAutoDetect((CDoc *)this);
                v299 = plLbound[0];
                v300 = v298;
                v301 = CMarkup::GetCodePage(v297);
                EncodingMenu = GetEncodingMenu(this[126], v301, v299, v300);
                a7->llVal = (LONGLONG)EncodingMenu;
                if ( !EncodingMenu )
                {
                  v25 = 1;
                  Text = 1;
                  goto LABEL_231;
                }
                goto LABEL_934;
              }
LABEL_232:
              if ( v98 )
              {
LABEL_1581:
                if ( Text != -2147221248 )
                  goto LABEL_1650;
              }
LABEL_1582:
              v509 = a5;
              goto LABEL_1583;
            default:
              goto LABEL_231;
          }
LABEL_933:
          a7->lVal = NormZoomPercent;
          goto LABEL_934;
        }
        if ( plLbound[0] == 6038 )
          goto LABEL_53;
        v313 = 3;
        switch ( plLbound[0] )
        {
          case 6041:
          case 6042:
          case 6043:
          case 6044:
            goto LABEL_835;
          case 6046:
            if ( a6 )
            {
              Text = CDoc::SetupDefaultBlockTag((CDoc *)this, a6);
              if ( !Text )
              {
                CNotification::CNotification((CNotification *)&v589);
                v314 = CDoc::PrimaryMarkup((CDoc *)this);
                v315 = CMarkup::GetElementTopHelper(v314);
                CNotification::EditModeChange((CNotification *)&v589, v315, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v589);
              }
            }
            if ( a7 )
            {
              a7->vt = 8;
              DefaultBlockTag = CDoc::GetDefaultBlockTag(this, v27, v313, v26);
              v317 = L"DIV";
              if ( DefaultBlockTag != 34 )
                v317 = L"P";
              a7->llVal = (LONGLONG)SysAllocString(v317);
              Text = 0;
            }
            goto LABEL_231;
          case 6048:
            if ( !a6 )
              goto LABEL_756;
            if ( a6->vt == 13 )
            {
              v97 = CDoc::SetDownloadNotify((CDoc *)this, a6->punkVal);
              goto LABEL_229;
            }
            goto LABEL_755;
        }
        goto LABEL_231;
      }
      if ( plLbound[0] <= 0x17ADu )
      {
        if ( plLbound[0] != 6061 )
        {
          switch ( plLbound[0] )
          {
            case 6050:
              bstrString = 0;
              *(_OWORD *)&v607.vt = 0;
              CNotification::CNotification((CNotification *)&v589);
              if ( !a6 )
                goto LABEL_131;
              if ( a6->vt != 13 )
                goto LABEL_131;
              llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, BSTR *))a6->llVal;
              if ( !llVal )
                goto LABEL_131;
              Text = (**llVal)(llVal, &IID_INamedPropertyBag, &bstrString);
              if ( Text )
                goto LABEL_230;
              v337 = v576;
              v338 = (struct INamedPropertyBag *)bstrString;
              v339 = CDocument::Markup(v576);
              Text = CDoc::PersistFavoritesData((CDoc *)this, v339, v338, L"DEFAULT");
              if ( Text )
              {
                ReleaseInterface((struct IUnknown *)bstrString);
                goto LABEL_230;
              }
              *(_QWORD *)&v607.vt = bstrString;
              v607.llVal = (LONGLONG)SysAllocString(L"DOC");
              if ( v607.llVal )
              {
                v340 = CDocument::Markup(v337);
                v341 = CMarkup::Root(v340);
                CNotification::FavoritesSave((CNotification *)&v589, v341, &v607, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v589);
                ClearInterface<INamedPropertyBag *>(&v607);
                SysFreeString(v607.bstrVal);
                goto LABEL_1647;
              }
              ReleaseInterface((struct IUnknown *)bstrString);
              goto LABEL_895;
            case 6051:
              Text = 0;
              if ( a7 )
              {
                v331 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v332 = (__int16 *)this + 2861;
                if ( !v331 )
                  v332 = (__int16 *)(this + 715);
                v333 = *v332;
                a7->vt = 3;
                FontSizeMenu = GetFontSizeMenu(v333);
                v335 = HandleToLong(FontSizeMenu);
                a7->lVal = v335;
                LOBYTE(Text) = v335 == 0;
                goto LABEL_231;
              }
              goto LABEL_756;
            case 6052:
              if ( a6 )
              {
                plLbound[0] = 0;
                v329 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v330 = (__int16 *)this + 2861;
                if ( !v329 )
                  v330 = (__int16 *)(this + 715);
                Text = ShowFontSizeMenu(plLbound, *v330, a6->lVal);
                if ( !Text )
                {
                  if ( (unsigned int)(plLbound[0] - 2141) <= 4 )
                    CDoc::ExecHelper((CDoc *)this, v576, &CGID_MSHTML, plLbound[0], 0, 0, 0);
                  goto LABEL_1647;
                }
              }
              goto LABEL_231;
          }
          if ( plLbound[0] != 6053 )
          {
            if ( plLbound[0] != 6054 )
            {
              if ( plLbound[0] != 6055 )
              {
                if ( plLbound[0] == 6057 )
                  *((_DWORD *)this + 1217) |= 0x10000u;
                goto LABEL_231;
              }
              if ( a6 && a6->vt == 37 && a7 && a7->vt == 3 )
              {
                inserted = CDoc::InsertMenuExt((CDoc *)this, (HMENU)a6->llVal, a7->lVal);
                goto LABEL_306;
              }
              goto LABEL_756;
            }
            if ( !a7 )
              goto LABEL_756;
            v324 = this[544];
            plLbound[0] = 0;
            *(_QWORD *)&String1.vt = 0;
            if ( GetExecDocument((struct CDocument **)&String1, v324, v576) >= 0 )
              CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
            v325 = plLbound[0];
            a7->vt = 3;
            DocDirMenu = CreateDocDirMenu(v325, 0);
            v327 = HandleToLong(DocDirMenu);
            a7->lVal = v327;
            v328 = -2147221247;
LABEL_1318:
            Text = v327 == 0 ? v328 : 0;
            goto LABEL_231;
          }
          if ( !a6 )
            goto LABEL_131;
          memset(&pv, 0, sizeof(pv));
          Text = CVariant::CoerceVariantArg((CVariant *)&pv, a6, 0xDu);
          if ( Text >= 0 )
            Text = CDoc::SaveSnapshotHelper((CDoc *)this, pv.punkVal, 1);
LABEL_876:
          p_pvarg = &pv;
LABEL_210:
          VariantClear(p_pvarg);
          goto LABEL_231;
        }
        if ( a6 || !a7 )
          goto LABEL_756;
        v342 = this[103];
        if ( !v342 )
          goto LABEL_350;
        *(_QWORD *)&String1.vt = 0;
        v343 = COmWindowProxy::Document(v342);
        Text = CDocument::ExtractContent(v343, (struct IReadingModeExtractedContent **)&String1);
        if ( Text < 0 )
          goto LABEL_1581;
        v344 = *(BSTR *)&String1.vt;
        a7->vt = 13;
LABEL_902:
        a7->llVal = (LONGLONG)v344;
        goto LABEL_1645;
      }
      switch ( plLbound[0] )
      {
        case 6062:
          Text = 0;
          if ( a6 || !a7 )
            goto LABEL_131;
          a7->vt = 3;
          a7->lVal = 0;
          v348 = (ReadingMode::CTextClusterDetector *)operator new[](
                                                        0x40u,
                                                        (const struct MemoryProtection::leaf_t *)0x8FC);
          if ( v348 )
          {
            v349 = (ReadingMode::CTextClusterDetector *)ReadingMode::CTextClusterDetector::CTextClusterDetector(
                                                          v348,
                                                          (struct CDoc *)this);
            v350 = v349;
            if ( v349 )
            {
              a7->lVal = ReadingMode::CTextClusterDetector::LengthOfArticleBody(v349);
              ReadingMode::CTextClusterDetector::`scalar deleting destructor'(v350, 1u);
              goto LABEL_1650;
            }
          }
          goto LABEL_895;
        case 6065:
          if ( CDoc::UseLayerManager((CDoc *)this) )
            CView::QueueFlushBatch((CView *)(this + 283));
          goto LABEL_53;
        case 6070:
          CDoc::SetPrerenderVisibility((CDoc *)this, a5 != 0);
          goto LABEL_53;
      }
      if ( plLbound[0] != 6071 )
      {
        if ( plLbound[0] == 6072 )
        {
          if ( a6 && a6->vt == 19 )
            Text = CDoc::AttemptBFCacheNavigation((CDoc *)this, a5, a6->cyVal.Lo);
          else
            Text = -2147024809;
          if ( a7 )
          {
            a7->vt = 3;
            a7->lVal = Text;
          }
        }
        else if ( plLbound[0] == 6073 )
        {
          Text = -2147024882;
          v345 = CDoc::PrimaryMarkup((CDoc *)this);
          CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v345);
          if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
          {
            v346 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
            Text = CPreloadManager::SuspendDuringPrerender(v346, 4);
          }
          CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
        }
        goto LABEL_231;
      }
      if ( !a7 || !a6 || a6->vt != 19 )
        goto LABEL_131;
      a7->vt = 19;
      v347 = CDoc::CheckBFCacheCandidacy(this, a6->cyVal.Lo, 2139, 0xFFFFFFFFLL);
LABEL_922:
      a7->lVal = v347;
      Text = 0;
      goto LABEL_1649;
    }
    if ( plLbound[0] <= 0x1B53u )
    {
      if ( plLbound[0] != 6995 )
      {
        switch ( plLbound[0] )
        {
          case 0x17BB:
            v366 = CDoc::InputManager((CDoc *)this);
            v367 = CInputManager::DeferredActionHandler(v366);
            CDeferredActionHandler::AgreeToVTabNavigate(v367, 0);
            goto LABEL_53;
          case 0x17BC:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v368 = CDoc::InputManager((CDoc *)this);
            v369 = CInputManager::DeferredActionHandler(v368);
            CDeferredActionHandler::OnVTabNavigateComplete(v369, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BD:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v370 = CDoc::InputManager((CDoc *)this);
            v371 = CInputManager::DeferredActionHandler(v370);
            CDeferredActionHandler::CancelSpecificVTabNavigate(v371, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BE:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v372 = CDoc::InputManager((CDoc *)this);
            v373 = CInputManager::DeferredActionHandler(v372);
            inserted = CDeferredActionHandler::ValidateVTabNavigate(v373, a6->cyVal.Lo);
            goto LABEL_306;
          case 0x17BF:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v374 = CDoc::InputManager((CDoc *)this);
            v375 = CInputManager::DeferredActionHandler(v374);
            CDeferredActionHandler::OnBeforeUnloadAgreed(v375, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17C0:
            if ( !a6 || a6->vt != 11 )
              goto LABEL_231;
            v376 = a6->iVal;
            Text = 0;
            if ( !v376 && ((_DWORD)this[609] & 0x200000) != 0 )
              goto LABEL_350;
            *((_DWORD *)this + 1219) &= ~0x100000u;
            v377 = 0;
            if ( v376 == -1 )
              v377 = 0x100000;
            *((_DWORD *)this + 1219) |= v377;
            goto LABEL_230;
          case 0x17C1:
            Text = -2147467259;
            v363 = CDoc::PrimaryMarkup((CDoc *)this);
            v364 = v363;
            if ( !v363 || !(unsigned int)BindCtx_ContainsObject(*((_QWORD *)v363 + 183), L"IE_FLAG_HAS_SCROLL_POSITION") )
              goto LABEL_1650;
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v364 + 183) + 96LL))(
              *((_QWORD *)v364 + 183),
              L"IE_FLAG_HAS_SCROLL_POSITION");
            goto LABEL_53;
          case 0x17C2:
            CDoc::ReleaseOffscreenBuffers((CDoc *)this);
            goto LABEL_53;
          case 0x17C3:
            v365 = this[876];
            if ( v365 )
            {
              (*(void (__fastcall **)(CInPlace *, __int64, __int64, __int64))(*(_QWORD *)v365 + 16LL))(
                v365,
                32,
                v19,
                0xFFFFFFFFLL);
              this[876] = 0;
            }
            goto LABEL_53;
          case 0x17C4:
            if ( !a7 )
              goto LABEL_131;
            a7->vt = 11;
            v361 = ((_BYTE)this[441] & 4) != 0;
            goto LABEL_961;
          case 0x17C5:
            inserted = CDoc::GetVisibilityState((CDoc *)this, a7);
            goto LABEL_306;
          case 0x17C6:
            if ( !a7 )
              goto LABEL_756;
            a7->vt = 3;
            plLbound[0] = 0;
            DispSystem = GetDispSystem();
            Text = (*(__int64 (__fastcall **)(struct IDispSystem *, LONG *))(*(_QWORD *)DispSystem + 736LL))(
                     DispSystem,
                     plLbound);
            if ( Text )
              goto LABEL_231;
            v382 = plLbound[0];
            goto LABEL_1533;
          case 0x17C7:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v383 = a6->lVal;
            plLbound[0] = 0;
            Text = ValidateD3DRequestedFeatureLevel(v383, (enum D3D_REQUESTED_FEATURE_LEVEL *)plLbound);
            if ( Text )
              goto LABEL_231;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                  + 16LL)
                      + 1132LL) = plLbound[0];
            goto LABEL_1647;
          case 0x17C8:
            if ( !a6 )
              goto LABEL_131;
            v362 = a6->vt == 19;
            goto LABEL_964;
          case 0x17C9:
            if ( !a7 )
              goto LABEL_131;
            IsEnterpriseMode = 0;
            if ( CDoc::PrimaryMarkup((CDoc *)this) )
            {
              v359 = CDoc::PrimaryMarkup((CDoc *)this);
              v360 = CMarkup::MarkupVersion(v359);
              IsEnterpriseMode = CMarkupVersion::IsEnterpriseMode(v360);
            }
            a7->vt = 11;
            v361 = !IsEnterpriseMode - 1;
LABEL_961:
            a7->iVal = v361;
            goto LABEL_934;
          case 0x17CA:
            v378 = *(CVirtualTabStorageEntry **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + (unsigned int)tls_index)
                                                           + 16LL)
                                               + 728LL);
            if ( v378 && CVirtualTabStorageEntry::WasLastNavigationViaFlipAhead(v378) )
            {
              v379 = CDoc::PrimaryMarkup((CDoc *)this);
              CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v379);
              if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
              {
                v380 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                CPreloadManager::SetLastNavAsFlipAheadAndIssueRequestIfApplicable(v380);
              }
              CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
            }
            goto LABEL_53;
          case 0x17CB:
            if ( !a6 || a6->vt != 8 )
              goto LABEL_756;
            v353 = CDoc::PrimaryMarkup((CDoc *)this);
            if ( v353 && (*((_BYTE *)v353 + 248) = 1, (v354 = this[103]) != 0) )
            {
              CodePageCore = *((unsigned int *)v353 + 194);
              v356 = *((_DWORD *)v353 + 196);
              if ( !(_DWORD)CodePageCore )
                CodePageCore = CMarkup::GetCodePageCore(v353);
              Text = COmWindowProxy::ExecRefresh(v354, 3, CodePageCore, v356);
            }
            else
            {
              Text = -2147467259;
            }
            ppvData = 0;
            if ( (int)GetUrlBlockClient(&ppvData) >= 0 )
            {
              bstrString = 0;
              if ( (**(int (__fastcall ***)(void *, GUID *, BSTR *))ppvData)(
                     ppvData,
                     &GUID_0e6c4fe4_75d0_4bf5_84bb_7c28415787c0,
                     &bstrString) >= 0 )
                (*(void (__fastcall **)(BSTR, LONGLONG))(*(_QWORD *)bstrString + 48LL))(bstrString, a6->llVal);
              v357 = bstrString;
              bstrString = 0;
              if ( v357 )
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)v357 + 16LL))(v357);
            }
            SysFreeString(a6->bstrVal);
            v55 = ppvData;
            ppvData = 0;
            a6->llVal = 0;
            goto LABEL_952;
          default:
            goto LABEL_231;
        }
      }
      inserted = CDoc::GetDisabledRenderingMode((CDoc *)this, a7);
      goto LABEL_306;
    }
    if ( plLbound[0] <= 0x1BDCu )
    {
      if ( plLbound[0] == 7132 )
      {
        v175 = 1;
        goto LABEL_380;
      }
      if ( plLbound[0] > 0x1B75u )
      {
        if ( plLbound[0] > 0x1BBCu )
        {
          if ( plLbound[0] != 7101 )
            goto LABEL_231;
          if ( a6 && a6->vt == 11 )
          {
            *((_DWORD *)this + 1216) = (_DWORD)this[608] & 0x7FFFFFFF | (a6->iVal << 31);
            goto LABEL_53;
          }
        }
        else
        {
          if ( plLbound[0] != 7100 )
          {
            switch ( plLbound[0] )
            {
              case 0x1B76:
                Text = -2147467259;
                View = CDoc::GetView((CDoc *)this);
                v414 = View;
                if ( !a7 || !View || !*((_BYTE *)View + 40) )
                  goto LABEL_1650;
                a7->vt = 3;
                v415 = *(unsigned __int16 *)CViewportController::GetLogicalViewportSize(*((_QWORD *)View + 4), &String1);
                a7->lVal = v415
                         | (*(unsigned __int16 *)(CViewportController::GetLogicalViewportSize(
                                                    *((_QWORD *)v414 + 4),
                                                    &v607)
                                                + 4) << 16);
                CDispClient::AdjustContentSize((CDispClient *)&v607, v416, v417);
                CDispClient::AdjustContentSize((CDispClient *)&String1, v418, v419);
                goto LABEL_934;
              case 0x1B77:
                Text = -2147467259;
                v421 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v421 || !*((_BYTE *)v421 + 40) )
                  goto LABEL_1650;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsMobileOptimizedSite(*((CViewportController **)v421 + 4));
                goto LABEL_1154;
              case 0x1B78:
                Text = -2147467259;
                v423 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v423 || !*((_BYTE *)v423 + 40) )
                  goto LABEL_1650;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsViewportWidthOrientationDependent(*((CViewportController **)v423
                                                                                                 + 4));
                goto LABEL_1154;
              case 0x1B79:
                inserted = CDoc::SetViewStateMediaQuery((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7A:
                inserted = CDoc::GetUserVisibility((CDoc *)this, a7);
                goto LABEL_306;
              case 0x1B7B:
                inserted = CDoc::SetUserVisibility((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7C:
                Text = -2147024809;
                if ( !a6 || a6->vt != 3 )
                  goto LABEL_1650;
                v412 = CVersions::MapToDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
                goto LABEL_1118;
              case 0x1B7D:
                inserted = CDoc::SetAuthoringCallback((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7E:
                if ( !a6 || a6->vt != 9 )
                  goto LABEL_330;
                bstrString = 0;
                v429 = a6->punkVal;
                *(GUID *)&v607.vt = CLSID_CElement;
                Text = QIClassID(v429, (struct _GUID *)&v607, (void **)&bstrString);
                if ( Text < 0 )
                  goto LABEL_1581;
                inserted = CElement::EnterFullScreen((CElement *)bstrString);
                goto LABEL_306;
              case 0x1B7F:
                if ( !a6 || ((a6->vt - 1) & 0xFFF7) != 0 )
                {
                  Text = -2147467261;
                  bstrString = 0;
                  goto LABEL_1650;
                }
                v430 = 0;
                bstrString = 0;
                if ( a6->vt == 9 )
                {
                  v431 = a6->punkVal;
                  *(GUID *)&v607.vt = CLSID_CElement;
                  Text = QIClassID(v431, (struct _GUID *)&v607, (void **)&bstrString);
                  if ( Text < 0 )
                    goto LABEL_1581;
                  v430 = (CElement *)bstrString;
                }
                if ( v430 )
                {
                  inserted = CElement::ExitFullScreen(v430);
                }
                else
                {
                  v432 = CDoc::FullScreenState((CDoc *)this);
                  inserted = CFullScreenState::ExitFullScreen(v432, 0);
                }
                break;
              case 0x1B80:
                inserted = CDoc::PrepareForSetVisible((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B81:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1650;
                if ( a6->vt != 8204 )
                  goto LABEL_1650;
                if ( SafeArrayGetDim(a6->parray) != 1 )
                  goto LABEL_1650;
                v424 = a6->parray;
                plLbound[0] = 0;
                SafeArrayGetUBound(v424, 1u, plLbound);
                if ( plLbound[0] != 2 )
                  goto LABEL_1650;
                v425 = a6->parray;
                *(_QWORD *)&String1.vt = 0;
                Text = SafeArrayAccessData(v425, (void **)&String1);
                if ( Text < 0 )
                  goto LABEL_1581;
                Text = CDoc::SetMediaConsent(
                         (CDoc *)this,
                         *(const unsigned __int16 **)(*(_QWORD *)&String1.vt + 8LL),
                         *(_DWORD *)(*(_QWORD *)&String1.vt + 32LL),
                         *(_DWORD *)(*(_QWORD *)&String1.vt + 56LL));
                goto LABEL_1142;
              case 0x1B82:
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_131;
                Text = -2147467259;
                v420 = CDoc::GetView((CDoc *)this);
                if ( !v420 || !*((_BYTE *)v420 + 40) )
                  goto LABEL_1650;
                CViewportController::SetUIOrientation(*((CViewportController **)v420 + 4), a6->iVal == 0xFFFF);
                goto LABEL_53;
              case 0x1B83:
                Text = -2147024809;
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_1650;
                v97 = CDoc::ForcePaint((CDoc *)this, a6->iVal == 0xFFFF, 0);
                goto LABEL_229;
              case 0x1B84:
                inserted = CDoc::WaitForDCompFlush((CDoc *)this);
                goto LABEL_306;
              case 0x1B86:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1650;
                if ( a6->vt != 11 )
                  goto LABEL_1650;
                Text = -2147467259;
                v426 = CDoc::GetView((CDoc *)this);
                if ( !v426 )
                  goto LABEL_1650;
                CView::AllowGrippersForHost(v426, a6->iVal == 0);
                goto LABEL_53;
              case 0x1B87:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1650;
                if ( a6->vt != 8 )
                  goto LABEL_1650;
                Text = -2147418113;
                if ( !v576 )
                  goto LABEL_1650;
                inserted = CDoc::HandleFlashServicingRefresh((CDoc *)this, v576, a6->bstrVal);
                goto LABEL_306;
              case 0x1B88:
                Text = -2147024809;
                if ( !a7 )
                  goto LABEL_1650;
                a7->vt = 11;
                v427 = CDoc::FullScreenState((CDoc *)this);
                IsMobileOptimizedSite = CFullScreenState::IsInFullScreen(v427);
LABEL_1154:
                v428 = !IsMobileOptimizedSite;
                goto LABEL_1491;
              default:
                goto LABEL_231;
            }
            goto LABEL_306;
          }
          if ( a6 )
          {
            v362 = a6->vt == 11;
LABEL_964:
            if ( v362 )
              goto LABEL_53;
          }
        }
        goto LABEL_131;
      }
      if ( plLbound[0] == 7029 )
        goto LABEL_131;
      if ( plLbound[0] <= 0x1B60u )
      {
        if ( plLbound[0] == 7008 )
        {
          inserted = CDoc::SetPhishingFilterDialogAsShown((CDoc *)this);
          goto LABEL_306;
        }
        if ( plLbound[0] > 0x1B59u )
        {
          if ( plLbound[0] != 7003 )
          {
            switch ( plLbound[0] )
            {
              case 7004:
                v390 = 0;
                if ( a6 && a6->vt == 3 )
                  v390 = a6->lVal;
                CDoc::SubmitForAntiPhishProcessing((CDoc *)this, 0, v390, 0);
                goto LABEL_53;
              case 7005:
                inserted = CDoc::NotifyMarkupsModelessEnable((CDoc *)this);
                break;
              case 7007:
                p_llVal = 0;
                if ( a6 && a6->vt == 11 )
                  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a6->llVal;
                inserted = CDoc::SubmitPhishingFilterReport((CDoc *)this, (__int16 *)p_llVal);
                break;
              default:
                goto LABEL_231;
            }
            goto LABEL_306;
          }
          v391 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( !v391 )
            goto LABEL_350;
          *((_BYTE *)v391 + 97) |= 8u;
          goto LABEL_53;
        }
        if ( plLbound[0] != 7001 )
        {
          switch ( plLbound[0] )
          {
            case 6996:
              inserted = CDoc::SetDisabledRenderingMode((CDoc *)this, a6);
              goto LABEL_306;
            case 6997:
              g_fOverrideScrollbarSizes = 1;
              ThreadStateUI = GetThreadStateUI();
              InitSystemMetricValues(ThreadStateUI);
              OnSettingsChangeAllDocs(1, 0x1B55u);
              break;
            case 6998:
              goto LABEL_53;
            case 6999:
              break;
            default:
              if ( a6 && a6->vt == 3 )
              {
                Lo = a6->cyVal.Lo;
                if ( Lo > 4 )
                  goto LABEL_131;
                Text = CDoc::ExecHelper((CDoc *)this, v576, &CGID_MSHTML, Lo + 2141, 2u, 0, 0);
                if ( Text )
                  goto LABEL_231;
              }
              if ( !a7 )
                goto LABEL_53;
              v362 = !FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
              v385 = (char *)this + 5722;
              if ( v362 )
                v385 = (char *)(this + 715);
              DebugState = *(__int16 *)v385;
              a7->vt = 3;
LABEL_1025:
              a7->lVal = DebugState;
              goto LABEL_53;
          }
          v388 = CDocument::Markup(v576);
          CDoc::WaitForRecalc((CDoc *)this, v388);
          goto LABEL_53;
        }
        if ( !a7 )
          goto LABEL_330;
        a7->vt = 3;
        a7->lVal = 0x40000;
LABEL_934:
        Text = 0;
        goto LABEL_1648;
      }
      if ( plLbound[0] != 7011 )
      {
        switch ( plLbound[0] )
        {
          case 7014:
            inserted = PassThroughTechnique::GetConstantBuffer(this, a6, a7, 0xFFFFFFFFLL);
            goto LABEL_306;
          case 7017:
            inserted = CDoc::GetHighContrastMode((CDoc *)this, a7);
            goto LABEL_306;
          case 7018:
            inserted = CDoc::SetHighContrastMode((CDoc *)this, a6);
            goto LABEL_306;
          case 7020:
            CDoc::CompatViewRefresh((CDoc *)this, 0);
            goto LABEL_53;
          case 7021:
            if ( a6 && a6->vt == 11 )
            {
              v392 = 0;
              if ( a6->iVal == -1 )
                v392 = 512;
              *((_DWORD *)this + 1214) = (_DWORD)this[607] & 0xFFFFFDFF | v392;
              goto LABEL_230;
            }
            goto LABEL_756;
          case 7024:
            inserted = CDoc::GetSuspendLevel((CDoc *)this, a7);
            goto LABEL_306;
          case 7025:
            inserted = CDoc::SetSuspendLevel((CDoc *)this, a6);
            goto LABEL_306;
        }
        if ( plLbound[0] != 7026 )
          goto LABEL_231;
        Text = CDoc::SaveToTempFileForPrint((CDoc *)this, v576, Data, 0x104u, 0, 0, 0);
        if ( Text < 0 )
          goto LABEL_1581;
        if ( !a7 )
          goto LABEL_756;
        VariantInit(a7);
        a7->vt = 8;
        v344 = SysAllocString(Data);
        goto LABEL_902;
      }
      if ( !a6 || a6->vt != 19 || !a7 )
        goto LABEL_756;
      rgIndices[0] = a6->lVal;
      Vector = SafeArrayCreateVector(0xCu, 0, 6u);
      pszSubKey = &Vector->cDims;
      a7->llVal = (LONGLONG)Vector;
      a7->vt = 8204;
      if ( !Vector )
        goto LABEL_895;
      ppvData = 0;
      Text = SafeArrayAccessData(Vector, &ppvData);
      if ( Text < 0 )
        goto LABEL_1581;
      for ( i = 0; i != 6; ++i )
        VariantInit((VARIANTARG *)ppvData + i);
      v395 = rgIndices[0];
      v20 = plLbound[0];
      if ( (rgIndices[0] & 1) != 0 )
      {
        Text = 0;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v396 = ppvData;
          *(_WORD *)ppvData = 21;
          v396[1] = *((_QWORD *)CDoc::PrimaryMarkup((CDoc *)this) + 17);
        }
        v395 = rgIndices[0];
      }
      if ( (v395 & 2) != 0 )
      {
        v397 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( v397 )
        {
          v398 = COptionsHolder::SecurityContext(v397);
          *(_QWORD *)&v607.vt = v398;
          if ( v398 )
          {
            *(_QWORD *)&String1.vt = CHtmCtx::GetReferrerUrl(v398);
            OriginalUrlContext = CHtmCtx::GetOriginalUrlContext(*(CHtmCtx **)&v607.vt);
            v400 = *(const OLECHAR **)&String1.vt;
            v401 = -1;
            *(_QWORD *)&v607.vt = OriginalUrlContext;
            if ( *(_QWORD *)&String1.vt )
            {
              v402 = -1;
              do
                ++v402;
              while ( *(_WORD *)(*(_QWORD *)&String1.vt + 2 * v402) );
            }
            else
            {
              v402 = 0;
            }
            if ( OriginalUrlContext )
            {
              do
                ++v401;
              while ( OriginalUrlContext[v401] );
            }
            else
            {
              v401 = 0;
            }
            if ( v402 )
            {
              if ( v401 > v402 )
              {
                v403 = wcsncmp_0(*(const wchar_t **)&String1.vt, OriginalUrlContext, v402);
                v400 = *(const OLECHAR **)&String1.vt;
                if ( !v403 )
                  v400 = *(const OLECHAR **)&v607.vt;
              }
            }
            v404 = SysAllocString(v400);
            v25 = 1;
            if ( v404 )
            {
              v405 = ppvData;
              Text = 0;
              *((_WORD *)ppvData + 12) = 8;
              v405[4] = v404;
            }
          }
        }
      }
      v406 = rgIndices[0];
      if ( (rgIndices[0] & 4) != 0 )
      {
        v407 = ppvData;
        *(_QWORD *)&v607.vt = ppvData;
        *((_WORD *)ppvData + 24) = 21;
        if ( this[781] )
        {
          v408 = CHTMLDlg::SecurityContext(this[781]);
          v406 = rgIndices[0];
          *(_QWORD *)(*(_QWORD *)&v607.vt + 56LL) = v408;
        }
        else
        {
          v407[7] = 0;
        }
      }
      if ( (v406 & 8) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractVideoData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text < 0 )
        {
LABEL_1110:
          CMultimediaLog::StopUpdate((CMultimediaLog *)(this + 741));
          v411 = (SAFEARRAY *)pszSubKey;
          goto LABEL_1143;
        }
        v406 = rgIndices[0];
        if ( bstrString )
        {
          v409 = ppvData;
          Text = 0;
          *((_WORD *)ppvData + 36) = 8;
          v409[10] = bstrString;
        }
      }
      if ( (v406 & 0x10) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractImageData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text >= 0 )
        {
          if ( bstrString )
          {
            v410 = ppvData;
            Text = 0;
            *((_WORD *)ppvData + 48) = 8;
            v410[13] = bstrString;
          }
        }
      }
      goto LABEL_1110;
    }
    if ( plLbound[0] <= 0x3A9Cu )
    {
      if ( plLbound[0] == 15004 )
      {
        inserted = CDoc::OnGetUserInitFlags((CDoc *)this, a6, a7);
        goto LABEL_306;
      }
      if ( plLbound[0] <= 0x1F46u )
      {
        if ( plLbound[0] == 8006 )
        {
          inserted = CDoc::NotifyViewStateChanged((CDoc *)this);
          goto LABEL_306;
        }
        if ( plLbound[0] > 0x1BF1u )
        {
          if ( plLbound[0] == 7700 )
          {
            if ( (*((_DWORD *)this + 1217) & 0x800) == 0 )
            {
              Text = CDoc::SerializePrintCommands((CDoc *)this, v576, a6, a7);
              v449 = Text == 0;
              goto LABEL_1646;
            }
            goto LABEL_231;
          }
          if ( plLbound[0] == 8000 )
          {
            if ( !a6 || a6->vt == 11 )
            {
              v447 = (unsigned int)tls_index;
              if ( a7 )
              {
                ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 11;
                a7->iVal = -(*(_BYTE *)(*(_QWORD *)(ThreadLocalStoragePointer[v447] + 16LL) + 1128LL) != 0);
              }
              if ( a6 )
                *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v447) + 16LL) + 1128LL) = a6->iVal == 0xFFFF;
              goto LABEL_53;
            }
            goto LABEL_131;
          }
          if ( plLbound[0] != 8001 )
          {
            switch ( plLbound[0] )
            {
              case 8002:
                inserted = CDoc::_TogglePerfWidgetVisibility((CDoc *)this);
                break;
              case 8003:
                Text = 0;
                v442 = CDocument::Window(v576);
                v443 = v442;
                if ( v442 && (unsigned int)CWindow::IsPrimaryWindow(v442) )
                {
                  v444 = CDeviceRotationRate::SecurityContext(v443);
                  if ( v444 )
                  {
                    v445 = (unsigned int)CMarkup::Window(v444);
                    CEventMgr::QueueAsyncEvent(
                      (unsigned int)&s_propdescCIE9EventListorientationchange,
                      v445,
                      (_DWORD)v444,
                      (unsigned int)COmWindowProxy::Fire_orientationchange,
                      0,
                      (__int64)AsyncEventMerge_Always,
                      0);
                  }
                  v446 = *((_QWORD *)v443 + 55);
                  if ( v446 )
                    CEventMgr::QueueAsyncEvent(
                      (unsigned int)&s_propdescCIE9EventListMSOrientationChange,
                      v446,
                      (_DWORD)v444,
                      (unsigned int)CScreen::Fire_orientationchange,
                      0,
                      (__int64)AsyncEventMerge_Always,
                      0);
                }
                goto LABEL_1647;
              case 8004:
                inserted = CDoc::GetContentLang((CDoc *)this, a7);
                break;
              case 8005:
                v441 = this[732];
                if ( v441 )
                {
                  CAPProcessor::Passivate(v441);
                  CAPProcessor::Release(this[732]);
                  this[732] = 0;
                }
                goto LABEL_53;
              default:
                goto LABEL_231;
            }
            goto LABEL_306;
          }
          if ( a6 && a6->vt != 11 )
            goto LABEL_131;
          if ( a7 )
          {
            a7->vt = 11;
            a7->iVal = -((*((_DWORD *)this + 1217) & 0x20) != 0);
          }
          if ( !a6 )
            goto LABEL_53;
          v242 = 0;
          if ( a6->iVal == -1 )
            v242 = 32;
          v243 = *((_DWORD *)this + 1217) & 0xFFFFFFDF;
LABEL_614:
          *((_DWORD *)this + 1217) = v243 | v242;
          goto LABEL_53;
        }
        switch ( plLbound[0] )
        {
          case 7153:
            CDoc::UpdateDefaultDpiScaling((CDoc *)this);
            goto LABEL_53;
          case 7133:
            Text = -2147024809;
            if ( !a6 || a6->vt != 13 )
              goto LABEL_1650;
            v97 = CIndependentHitTestManager::RegisterHostForIndependentHitTesting(
                    (CIndependentHitTestManager *)&g_IndependentHitTestManager,
                    (struct CDoc *)this,
                    a6->punkVal);
            goto LABEL_229;
          case 7134:
            Text = -2147024809;
            if ( !a6 || a6->vt != 13 )
              goto LABEL_1650;
            v97 = CIndependentHitTestManager::UnregisterHostForIndependentHitTesting(
                    (CIndependentHitTestManager *)&g_IndependentHitTestManager,
                    (struct CDoc *)this,
                    a6->punkVal);
            goto LABEL_229;
          case 7135:
            Text = -2147024809;
            if ( !a6 || a6->vt != 0x4000 )
              goto LABEL_1650;
            RootTracker = CRootTracker::GetRootTracker();
            v435 = RootTracker;
            if ( RootTracker )
            {
              Text = CRootTracker::EnsureInitialized(RootTracker);
              if ( Text < 0 )
                goto LABEL_1581;
              CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
              v436 = CDCompLayerManager::UseRootLayer(v435);
              v437 = **(__int64 (__fastcall ***)(struct IDispLayer *, GUID *, struct CHtmParseCtx *))v436;
              v438 = (CHtmRootParseCtxRouter *)TSmartPointer<ID3D11Device>::operator&(&bstrString);
              HpxEmbed = CHtmRootParseCtxRouter::GetHpxEmbed(v438);
              Text = v437(v436, &GUID_cc1a2bea_d5e9_4161_9da7_9042b37549a7, HpxEmbed);
              if ( Text >= 0 )
              {
                v440 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                Text = (*(__int64 (__fastcall **)(struct IDispRenderTarget *, __int64, struct tagVARIANT *))(*(_QWORD *)v440 + 24LL))(
                         v440,
                         3,
                         a6);
              }
              TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&bstrString);
              goto LABEL_230;
            }
            goto LABEL_1404;
          case 7136:
            Text = -2147024809;
            if ( a7 )
            {
              a7->vt = 11;
              a7->iVal = -((unsigned int)CDoc::IsJSDumpRequested((CDoc *)this) != 0);
              if ( !a6 )
              {
                Text = 0;
                goto LABEL_1650;
              }
            }
            else if ( !a6 )
            {
              goto LABEL_1650;
            }
            if ( a6->vt != 21 )
              goto LABEL_1650;
            inserted = CDoc::OnDumpHeap((CDoc *)this, 0, &a6->ullVal);
            goto LABEL_306;
          case 7140:
            inserted = CDoc::OnGetTrackingProtectionData((CDoc *)this);
            goto LABEL_306;
          case 7150:
            CDoc::UpdateEffectiveDpi((CDoc *)this);
            goto LABEL_53;
        }
        if ( plLbound[0] != 7151 )
        {
          if ( plLbound[0] != 7152 )
            goto LABEL_231;
          if ( a7 )
          {
            a7->lVal = 0;
            bstrString = 0;
            a7->vt = 23;
            Text = CDoc::GetPrimaryUri((CDoc *)this, (struct IUri **)&bstrString);
            if ( !Text )
            {
              v211 = (struct IUnknown *)bstrString;
              if ( !bstrString )
                goto LABEL_527;
              plLbound[0] = 0;
              Text = GetMinLayoutWidthFromCVList(bstrString, plLbound);
              if ( Text >= 0 )
              {
                Text = 0;
                a7->lVal = plLbound[0];
              }
            }
LABEL_526:
            v211 = (struct IUnknown *)bstrString;
LABEL_527:
            ReleaseInterface(v211);
            goto LABEL_231;
          }
          goto LABEL_131;
        }
        if ( !a7 )
          goto LABEL_131;
        a7->vt = 4;
        v362 = !CView::HasStaticViewportSizeApplied((CView *)(this + 283));
        v433 = (int *)(this + 481);
        if ( v362 )
          v433 = (int *)this + 1019;
        NormZoomPercent = *v433;
        goto LABEL_933;
      }
      if ( plLbound[0] > 0x3A98u )
      {
        if ( plLbound[0] != 15001 )
        {
          if ( plLbound[0] == 15002 )
          {
            if ( a6 && (a6->vt == 8212 || a6->vt == 8195) )
            {
              v462 = a6->parray;
              if ( v462 )
              {
                pvData = 0;
                pszSubKey = 0;
                *(_QWORD *)&String1.vt = 0;
                if ( !SafeArrayGetElement(v462, (LONG *)&pvData, &pszSubKey) )
                {
                  v463 = a6->parray;
                  ++pvData;
                  if ( !SafeArrayGetElement(v463, (LONG *)&pvData, &String1) )
                    CDoc::ReplacePrintHandles((CDoc *)this, (void *)pszSubKey, *(void **)&String1.vt);
                }
                goto LABEL_53;
              }
            }
            goto LABEL_131;
          }
          v327 = InternetSetOptionW(0, 0x2Au, 0, 0);
          v328 = -2147467259;
          goto LABEL_1318;
        }
        if ( g_fInHtmlHelp )
        {
          *((_DWORD *)this + 1217) |= 0x400u;
          v464 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( v464 )
          {
            if ( (*((_DWORD *)v464 + 187) & 0x4000000) != 0 )
            {
              v465 = (COmWindowProxy *)*((_QWORD *)v464 + 44);
              if ( v465 )
                COmWindowProxy::Fire_onafterprint(v465);
            }
          }
          *((_DWORD *)this + 1217) &= ~0x400u;
        }
      }
      else if ( plLbound[0] != 15000 )
      {
        if ( plLbound[0] > 0x1F4Cu )
        {
          switch ( plLbound[0] )
          {
            case 8015:
              if ( a7 )
              {
                Text = 0;
                a7->vt = 11;
                a7->iVal = 0;
                goto LABEL_1648;
              }
              break;
            case 8016:
              goto LABEL_231;
            case 8017:
              if ( a6 && a6->vt == 19 )
              {
                if ( (unsigned __int8)CDoc::IsHostBehaviorSupported<84>(this, 32, v19, 0xFFFFFFFFLL) )
                {
                  CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)&bstrString);
                  GetCachedPrimaryDisplaySize((struct CSize *)&bstrString);
                  HIDWORD(bstrString) = a6->lVal;
                  SetCachedPrimaryDisplaySize((const struct CSize *)&bstrString);
                  CDispClient::AdjustContentSize((CDispClient *)&bstrString, v460, v461);
                }
                goto LABEL_53;
              }
              break;
            case 8018:
              if ( !a6 || a6->vt != 11 )
                goto LABEL_131;
              FeatureControlHelper::SetStripDOMElements(
                (FeatureControlHelper *)&g_FeatureControlHelper,
                a6->iVal == 0xFFFF);
              goto LABEL_53;
            case 8019:
              if ( a6 && a6->vt == 11 )
              {
                FeatureControlHelper::SetDisableSpeculativeDownload(
                  (FeatureControlHelper *)&g_FeatureControlHelper,
                  a6->iVal == 0xFFFF);
                goto LABEL_53;
              }
              break;
            default:
              goto LABEL_231;
          }
        }
        else
        {
          switch ( plLbound[0] )
          {
            case 8012:
              Text = 0;
              CDoc::OfferImageResources((CDoc *)this);
              goto LABEL_1647;
            case 8007:
              if ( a6 && a6->vt == 3 )
              {
                Text = 0;
                CDoc::HandleWebStorageEvent((CDoc *)this, v576, a6->cyVal.Lo);
                goto LABEL_1647;
              }
              goto LABEL_131;
            case 8008:
              Text = 0;
              if ( a6 && a6->vt == 19 )
              {
                v456 = this[126];
                if ( v456 )
                {
                  v457 = a6->lVal;
                  if ( *((_DWORD *)v456 + 384) == v457 )
                    goto LABEL_1647;
                  *((_DWORD *)v456 + 384) = v457;
                  v458 = CDocument::Markup(v576);
                  TextScalingSettings = CTextScalingSettings::GetTextScalingSettings(v458);
                  CTextScalingSettings::Initialize(TextScalingSettings, (struct CDoc *)this);
                  inserted = CDoc::ForceRelayout((CDoc *)this, 0);
                  goto LABEL_306;
                }
                goto LABEL_350;
              }
              goto LABEL_756;
            case 8009:
              if ( !a6 || a6->vt != 11 )
                goto LABEL_131;
              v454 = CDoc::GetView((CDoc *)this);
              if ( v454 )
              {
                if ( *((_BYTE *)v454 + 40) )
                {
                  v455 = (CViewportController *)*((_QWORD *)v454 + 4);
                  if ( v455 )
                  {
                    Text = 0;
                    CViewportController::SetAccessibleZoom(v455, a6->iVal != 0);
                    goto LABEL_1647;
                  }
                }
              }
              goto LABEL_350;
            case 8010:
              v452 = NtCurrentTeb()->ThreadLocalStoragePointer;
              pvData = 0;
              bstrString = (BSTR)v452[(unsigned int)tls_index];
              if ( *(_QWORD *)(*((_QWORD *)bstrString + 2) + 728LL) )
              {
                if ( !(unsigned int)CDoc::GetVirtualTabID((CDoc *)this, &pvData) )
                {
                  VirtualTabID = CVirtualTabStorageEntry::GetVirtualTabID(*(CVirtualTabStorageEntry **)(*((_QWORD *)bstrString + 2) + 728LL));
                  if ( VirtualTabID != pvData
                    && CVirtualTabStorageEntry::IsStorageListHelperSet(*(CVirtualTabStorageEntry **)(*((_QWORD *)bstrString + 2) + 728LL)) )
                  {
                    CVirtualTabStorageEntry::Release(*(CVirtualTabStorageEntry **)(*((_QWORD *)bstrString + 2) + 728LL));
                    *(_QWORD *)(*((_QWORD *)bstrString + 2) + 728LL) = 0;
                  }
                }
                if ( pvData )
                {
                  CLockg_pVirtualTabStorage::CLockg_pVirtualTabStorage((CLockg_pVirtualTabStorage *)pvt, 0);
                  CVirtualTabStorage::AddVirtualTabStorageEntryToTLS(g_pVirtualTabStorage, (struct CDoc *)this);
                  CLockg_pVirtualTabStorage::~CLockg_pVirtualTabStorage((CLockg_pVirtualTabStorage *)pvt);
                }
              }
              goto LABEL_231;
          }
          if ( a6 && a6->vt == 11 )
          {
            v450 = CDoc::GetView((CDoc *)this);
            if ( v450 )
            {
              v451 = (CViewportController *)*((_QWORD *)v450 + 4);
              if ( v451 )
              {
                Text = 0;
                CViewportController::SetIsReadingView(v451, a6->iVal != 0);
                goto LABEL_1647;
              }
            }
            goto LABEL_350;
          }
        }
        goto LABEL_131;
      }
      if ( this[642] )
      {
        if ( a6 )
        {
          if ( a6->vt == 13 )
          {
            v466 = (unsigned int (__fastcall ***)(_QWORD, GUID *, void **, __int64))a6->llVal;
            if ( v466 )
            {
              ppvData = 0;
              if ( !(**v466)(v466, &IID_IHTMLWindow2, &ppvData, v26) )
              {
                v467 = this[642];
                bstrString = 0;
                if ( !(**(unsigned int (__fastcall ***)(CInPlace *, GUID *, BSTR *))v467)(
                        v467,
                        &IID_ITridentService2,
                        &bstrString) )
                {
                  (*(void (__fastcall **)(BSTR, void *, _QWORD))(*(_QWORD *)bstrString + 144LL))(
                    bstrString,
                    ppvData,
                    (unsigned int)(v20 != 15000) + 225);
                  (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                }
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppvData + 16LL))(ppvData);
              }
              goto LABEL_53;
            }
          }
        }
      }
      goto LABEL_131;
    }
    if ( plLbound[0] <= 0x3AFCu )
    {
      if ( plLbound[0] == 15100 )
      {
        v529 = CDocument::Markup(v576);
        v530 = 0;
        if ( a6 && a6->vt == 3 )
          v530 = a6->lVal;
        Text = 0;
        if ( !v529 )
          goto LABEL_1647;
        v531 = CMarkup::GetWindowedMarkupContext(v529);
        if ( !v531 )
          goto LABEL_1647;
        RootMarkup = CMarkup::GetRootMarkup(v531, 0);
        if ( !RootMarkup )
          goto LABEL_1647;
        *((_DWORD *)RootMarkup + 197) |= v530;
        *((_DWORD *)this + 1224) &= ~v530;
        inserted = CDoc::NotifyPageActionBlockedState((CDoc *)this, 1, 0);
        goto LABEL_306;
      }
      if ( plLbound[0] <= 0x3AB3u )
      {
        if ( plLbound[0] == 15027 )
        {
          Text = -2147024809;
          if ( !a7 )
            goto LABEL_1650;
          a7->vt = 3;
          NormZoomPercent = CZoomState::GetNormZoomPercent();
          goto LABEL_933;
        }
        if ( plLbound[0] <= 0x3AA3u )
        {
          switch ( plLbound[0] )
          {
            case 15011:
              Text = -2147024809;
              if ( !a7 )
                goto LABEL_1650;
              ppvData = 0;
              pszSubKey = (LPCWSTR)GetThreadStateUI();
              if ( (unsigned int)IsEqualGUID(pszSubKey + 416, &GUID_NULL) )
                goto LABEL_1650;
              *(_QWORD *)&String1.vt = 3;
              v487 = SafeArrayCreate(0xCu, 1u, (SAFEARRAYBOUND *)&String1);
              v488 = v487;
              if ( v487 )
              {
                Text = SafeArrayAccessData(v487, &ppvData);
                if ( Text >= 0 )
                {
                  bstrString = 0;
                  Text = StringFromCLSID((const IID *const)pszSubKey + 52, &bstrString);
                  if ( Text >= 0 )
                  {
                    *(_WORD *)ppvData = 8;
                    v489 = SysAllocString(bstrString);
                    v490 = pszSubKey;
                    *((_QWORD *)ppvData + 1) = v489;
                    *((_WORD *)ppvData + 12) = 3;
                    *((_DWORD *)ppvData + 8) = *((_DWORD *)v490 + 212);
                    *((_WORD *)ppvData + 24) = 3;
                    *((_DWORD *)ppvData + 14) = *((_DWORD *)v490 + 213);
                    CoTaskMemFree(bstrString);
                  }
                  SafeArrayUnaccessData(v488);
                  if ( Text >= 0 )
                  {
                    VariantInit(a7);
                    a7->vt = 8204;
                    a7->llVal = (LONGLONG)v488;
                    goto LABEL_1645;
                  }
                }
                goto LABEL_1581;
              }
              goto LABEL_1404;
            case 15005:
              inserted = CDoc::OnGetDocDlgFlags((CDoc *)this, a7);
              goto LABEL_306;
            case 15006:
              CDoc::OnWindowStateChanged((CDoc *)this, a5);
              goto LABEL_53;
            case 15007:
              if ( a6->vt != 8204 || !a6->llVal )
                goto LABEL_231;
              *(_OWORD *)&v607.vt = 0;
              memset(&pvarg, 0, sizeof(pvarg));
              memset(&String1, 0, sizeof(String1));
              memset(&pv, 0, sizeof(pv));
              VariantInit(&pvarg);
              VariantInit(&String1);
              VariantInit(&pv);
              v484 = a6->parray;
              rgIndices[0] = 0;
              Text = SafeArrayGetElement(v484, rgIndices, &pvarg);
              if ( Text >= 0 && pvarg.vt == 8 )
              {
                Text = CLSIDFromString(pvarg.bstrVal, (LPCLSID)&v607);
                if ( !Text )
                {
                  v485 = a6->parray;
                  rgIndices[0] = 1;
                  Text = SafeArrayGetElement(v485, rgIndices, &String1);
                  if ( Text >= 0 && String1.vt == 19 )
                  {
                    v486 = a6->parray;
                    rgIndices[0] = 2;
                    Text = SafeArrayGetElement(v486, rgIndices, &pv);
                    if ( Text >= 0 && pv.vt == 8 )
                      CClassTable::AssignInstallPkgInfo((CClassTable *)(this + 678), pv.bstrVal, String1.cyVal.Lo);
                  }
                }
              }
              VariantClear(&pvarg);
              VariantClear(&String1);
              goto LABEL_876;
            case 15008:
              Text = -2147024809;
              if ( !a6 )
                goto LABEL_1650;
              if ( a6->vt != 3 )
                goto LABEL_1650;
              v412 = CVersions::MapToNearestDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
              if ( v412 < 0 )
                goto LABEL_1650;
LABEL_1118:
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 740LL) = v412;
              goto LABEL_53;
            case 15009:
              Text = -2147024809;
              if ( !a6 || a6->vt != 3 || !a7 )
                goto LABEL_1650;
              VariantInit(a7);
              v476 = a6->lVal;
              if ( v476 )
              {
                v477 = v476 - 1;
                if ( v477 )
                {
                  if ( v477 != 1 )
                    goto LABEL_1650;
                  v478 = CDocument::Markup(v576);
                  a7->vt = 3;
                  v479 = CMarkup::MarkupVersion(v478);
                  v347 = CMarkupVersion::DocumentMode(v479);
                }
                else
                {
                  v480 = CDocument::Markup(v576);
                  a7->vt = 3;
                  v481 = CMarkup::MarkupVersion(v480);
                  v347 = CMarkupVersion::NativeDocumentMode(v481, 0, 0);
                }
              }
              else
              {
                v482 = (unsigned int)tls_index;
                v483 = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 3;
                v347 = *(_DWORD *)(*(_QWORD *)(v483[v482] + 16LL) + 740LL);
              }
              goto LABEL_922;
          }
          ppvData = GetThreadStateUI();
          *(_QWORD *)&v607.vt = CDoc::PrimaryMarkup((CDoc *)this);
          v468 = *(struct CMarkup **)&v607.vt;
          if ( !a6 )
          {
            Text = -2147024809;
            *(_QWORD *)&v607.vt = (char *)ppvData + 832;
            if ( (unsigned int)IsEqualGUID((char *)ppvData + 832, &GUID_NULL) )
              goto LABEL_1650;
            Text = 0;
            *(GUID *)*(_QWORD *)&v607.vt = GUID_NULL;
            *((_QWORD *)ppvData + 106) = 0;
            if ( !v468 || !(unsigned __int8)CMarkup::IsVersionedChangeEnabled(v468, 100000) )
            {
LABEL_1647:
              if ( !v9 )
                goto LABEL_1649;
              goto LABEL_1648;
            }
            CWorkerManager::StartProfilingAllWorkers(v468, 0);
            goto LABEL_231;
          }
          if ( a6->vt != 8204 )
            goto LABEL_231;
          v469 = a6->parray;
          if ( !v469 )
            goto LABEL_231;
          bstrString = 0;
          Text = SafeArrayAccessData(v469, (void **)&bstrString);
          if ( Text < 0 )
            goto LABEL_1581;
          v470 = a6->parray;
          pvData = 0;
          Text = SafeArrayGetUBound(v470, 1u, (LONG *)&pvData);
          if ( Text >= 0 )
          {
            v471 = pvData + 1;
            pvData = v471;
            if ( v471 == 3 )
            {
              if ( *bstrString == 8 && bstrString[12] == 3 && bstrString[24] == (_WORD)v471 )
              {
                v472 = ppvData;
                v473 = CLSIDFromString(*((LPCOLESTR *)bstrString + 1), (LPCLSID)ppvData + 52);
                v474 = bstrString;
                Text = v473;
                v472[212] = *((_DWORD *)bstrString + 8);
                v472[213] = *((_DWORD *)v474 + 14);
                if ( !v473 )
                {
                  v475 = *(struct CMarkup **)&v607.vt;
                  if ( *(_QWORD *)&v607.vt )
                  {
                    if ( (unsigned __int8)CMarkup::IsVersionedChangeEnabled(*(_QWORD *)&v607.vt, 100000) )
                      CWorkerManager::StartProfilingAllWorkers(v475, 1);
                  }
                }
              }
              else
              {
                Text = -2147024809;
              }
            }
          }
LABEL_1142:
          v411 = a6->parray;
LABEL_1143:
          SafeArrayUnaccessData(v411);
          goto LABEL_231;
        }
        switch ( plLbound[0] )
        {
          case 15012:
            goto LABEL_131;
          case 15013:
            if ( !a6 )
              goto LABEL_131;
            if ( a6->vt != 13 )
              goto LABEL_131;
            v497 = (__int64 (__fastcall ***)(_QWORD, GUID *, VARIANTARG *, __int64))a6->llVal;
            if ( !v497 )
              goto LABEL_131;
            *(_QWORD *)&String1.vt = 0;
            Text = (**v497)(v497, &IID_INavigateEventSink, &String1, 0xFFFFFFFFLL);
            if ( Text >= 0 )
            {
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 744LL) = *(_QWORD *)&String1.vt;
              goto LABEL_1645;
            }
            goto LABEL_1580;
          case 15016:
            goto LABEL_131;
          case 15017:
            inserted = CDoc::FireOnPopStateEvent((CDoc *)this, v576);
            goto LABEL_306;
          case 15024:
            Text = -2147024809;
            if ( !a6 || a6->vt != 11 )
              goto LABEL_1650;
            *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                 + 16LL)
                     + 587LL) = a6->iVal == 0xFFFF;
            goto LABEL_53;
        }
        if ( plLbound[0] != 15025 )
          goto LABEL_231;
        Text = -2147024809;
        v491 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( !a7 || !a6 || a6->vt != 3 )
          goto LABEL_1650;
        a7->vt = 11;
        Text = 0;
        v492 = a6->lVal;
        if ( v492 )
        {
          if ( v492 != 1 )
            goto LABEL_630;
          if ( !v491 )
          {
            v495 = 0;
            goto LABEL_1420;
          }
          v493 = CMarkup::MarkupVersion(v491);
          IsNativeQuirksLayoutEmulation = CMarkupVersion::IsNativeQuirksLayoutEmulation(v493);
        }
        else
        {
          if ( !v491 )
          {
            v495 = -(*(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                            + (unsigned int)tls_index)
                                          + 16LL)
                              + 587LL) != 0);
            goto LABEL_1420;
          }
          v496 = CMarkup::MarkupVersion(v491);
          IsNativeQuirksLayoutEmulation = CDCompVideoBackedLayer::IsRenderRequired(v496);
        }
        v495 = !IsNativeQuirksLayoutEmulation - 1;
LABEL_1420:
        a7->iVal = v495;
        goto LABEL_1649;
      }
      if ( plLbound[0] > 0x3AC1u )
      {
        if ( plLbound[0] == 15042 )
          goto LABEL_350;
        if ( plLbound[0] == 15043 )
        {
          if ( a6 )
          {
            if ( a6->vt == 3 )
            {
              v528 = a6->lVal;
              if ( !*((_BYTE *)this + 1016) || CColorValue::GetIntoABGR((CColorValue *)((char *)this + 1020)) != v528 )
              {
                *((_BYTE *)this + 1016) = 1;
                Text = 0;
                if ( !CServer::IsWebPlatformWindowless((CServer *)this) )
                  v528 |= 0xFF000000;
                CColorValue::SetFromABGR((CColorValue *)((char *)this + 1020), v528);
                CDoc::ForceRelayout((CDoc *)this, 1);
                CDoc::SignalDefaultBackgroundColorChanged((CDoc *)this, v528);
              }
            }
          }
          goto LABEL_231;
        }
        if ( plLbound[0] != 15044 )
        {
          if ( plLbound[0] == 15045 )
            goto LABEL_53;
          goto LABEL_231;
        }
        if ( a7 )
        {
          Text = 0;
          a7->vt = 3;
          if ( *((_BYTE *)this + 1016) )
          {
            v526 = (int)(float)(CColorValue::GetAlpha((CColorValue *)((char *)this + 1020)) * 255.0);
            v382 = ((unsigned __int8)v526 << 24)
                 | CColorValue::GetColorRef((CColorValue *)((char *)this + 1020)) & 0xFFFFFF;
          }
          else
          {
            v527 = (OLE_COLOR *)this[126];
            if ( !v527 )
            {
              a7->lVal = -16777216;
              goto LABEL_231;
            }
            plLbound[0] = 0;
            Text = OleTranslateColor(*v527, 0, (COLORREF *)plLbound);
            if ( Text )
              goto LABEL_231;
            v382 = plLbound[0] | 0xFF000000;
          }
LABEL_1533:
          a7->lVal = v382;
          goto LABEL_1648;
        }
LABEL_231:
        v98 = Text < 0;
        goto LABEL_232;
      }
      if ( plLbound[0] == 15041 )
      {
        inserted = CDoc::UpdateFromRegistry((CDoc *)this, a6);
        goto LABEL_306;
      }
      if ( plLbound[0] != 15028 )
      {
        if ( plLbound[0] == 15029 )
        {
          Text = -2147024809;
          if ( !a6 || a6->vt != 8 )
            goto LABEL_1650;
          if ( a5 == 102 )
          {
            v512 = 1;
          }
          else
          {
            if ( a5 != 103 )
              goto LABEL_1650;
            v512 = 0;
          }
          inserted = CDoc::SetGeolocationUserConsent((CDoc *)this, a6->bstrVal, v512);
          goto LABEL_306;
        }
        if ( plLbound[0] != 15030 )
        {
          switch ( plLbound[0] )
          {
            case 15033:
              inserted = CDoc::ShareAppCacheEventDownwards((CDoc *)this, a6->bstrVal);
              break;
            case 15038:
              goto LABEL_1449;
            case 15039:
              Text = -2147024809;
              if ( !a6 )
                goto LABEL_1650;
              if ( a6->vt == 1 )
              {
                v498 = 0;
              }
              else
              {
                if ( a6->vt != 8 )
                  goto LABEL_1650;
                v498 = a6->bstrVal;
              }
              inserted = CDoc::SetExtraHeaders((CDoc *)this, v498);
              break;
            default:
              goto LABEL_231;
          }
          goto LABEL_306;
        }
        if ( !a7 )
          goto LABEL_131;
        v510 = CDocument::GetWindowedMarkupContext(v576);
        IsActiveXFilteringEnabled = CMarkup::IsActiveXFilteringEnabled(v510);
        a7->vt = 11;
        v428 = IsActiveXFilteringEnabled != 1;
LABEL_1491:
        a7->iVal = v428 - 1;
        goto LABEL_934;
      }
      if ( !a6 || !a7 )
        goto LABEL_231;
      if ( a6->vt != 13 )
        goto LABEL_230;
      v513 = a6->punkVal;
      if ( !v513 )
        goto LABEL_230;
      *(_QWORD *)plLbound = 0;
      *(GUID *)&v607.vt = CLSID_CElement;
      Text = QIClassID(v513, (struct _GUID *)&v607, (void **)plLbound);
      if ( Text < 0 )
        goto LABEL_1580;
      if ( !(unsigned int)CElement::IsInMarkup(*(CElement **)plLbound) )
      {
        Text = -2147418113;
        goto LABEL_230;
      }
      Text = CElement::EnsureRecalcNotify(*(CElement **)plLbound);
      if ( Text < 0 )
        goto LABEL_1580;
      CRect::CRect((CRect *)&v607);
      CRect::CRect((CRect *)&String1);
      Text = CElement::GetBoundingRect(*(CElement **)plLbound, (struct CRectF *)&String1, 0x4001u, 0);
      if ( Text >= 0
        && ((unsigned int)CElement::IsDeviceFixed(*(CElement **)plLbound)
         || (unsigned int)CElement::IsAncestorPositionFixed(*(CElement **)plLbound, 1))
        && CElement::IsStandardsMode(*(CElement **)plLbound) )
      {
        v514 = CElement::LayoutServices(*(CElement **)plLbound);
        if ( v514 )
        {
          v515 = *(_QWORD *)v514;
          bstrString = 0;
          LOBYTE(pvt[0]) = 0;
          (*(void (__fastcall **)(struct ILayoutServices *, _QWORD, BSTR *, VARTYPE *))(v515 + 432))(
            v514,
            *(_QWORD *)plLbound,
            &bstrString,
            pvt);
          for ( j = bstrString; j; bstrString = j )
          {
            v517 = CDispNode::NodeReader((CDispNode *)j);
            if ( CDispNodeReader::IsTopLevelScroller(v517) )
            {
              v518 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispScroller::GetTotalZoomFactor(v518);
              v519 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispTopLevelScroller::BaseOpticalZoomFactor(v519);
              CRectF::operator/=(&String1);
              break;
            }
            j = (OLECHAR *)CDispNode::GetParentNode((CDispNode *)bstrString);
          }
        }
      }
      CRect::SetRect((CRect *)&v607, (const struct D2D_RECT_F *)&String1, 0);
      if ( Text >= 0 )
      {
        VariantInit(a7);
        a7->vt = 8195;
        v522 = SafeArrayCreateVector(3u, 0, 4u);
        a7->llVal = (LONGLONG)v522;
        if ( v522 )
        {
          *(_DWORD *)pvt = 0;
          SafeArrayPutElement(v522, (LONG *)pvt, &v607);
          v523 = a7->parray;
          v25 = 1;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v523, (LONG *)pvt, &v607.decVal.Hi32);
          v524 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v524, (LONG *)pvt, &v607.decVal.8);
          v525 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v525, (LONG *)pvt, (char *)&v607.decVal.Lo64 + 4);
LABEL_1522:
          CDispClient::AdjustContentSize((CDispClient *)&String1, v520, v521);
          goto LABEL_231;
        }
        Text = -2147024882;
      }
      v25 = 1;
      goto LABEL_1522;
    }
    switch ( plLbound[0] )
    {
      case 15200:
        bstrString = 0;
        v541 = 0;
        if ( a6 )
        {
          if ( a6->vt == 13 )
          {
            v542 = (void (__fastcall ***)(_QWORD, GUID *, struct CHtmParseCtx *))a6->llVal;
            if ( v542 )
            {
              v543 = **v542;
              v544 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)&bstrString);
              v543(v542, &GUID_0000000e_0000_0000_c000_000000000046, v544);
              v541 = (struct IBindCtx *)bstrString;
            }
          }
          v25 = 1;
        }
        v545 = CFlipAheadManager::InvokeCachedTarget((CFlipAheadManager *)(this + 836), v541);
        v55 = bstrString;
        Text = v545;
LABEL_952:
        if ( !v55 )
          goto LABEL_231;
        goto LABEL_111;
      case 15202:
        v540 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v535 = v540;
        if ( v540 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v540) == 2 )
            goto LABEL_1647;
          plLbound[0] = CMarkup::GetDebugState(v535);
          v536 = plLbound[0];
          CMarkup::SetDebugState(v535, 2);
          v537 = 2;
          goto LABEL_1563;
        }
        break;
      case 15203:
        v539 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v535 = v539;
        if ( v539 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v539) != 2 )
            goto LABEL_1647;
          plLbound[0] = CMarkup::GetDebugState(v535);
          CMarkup::SetDebugState(v535, 1);
          Text = CDoc::DynamicDetachDebugger((CDoc *)this);
          if ( Text >= 0 )
            goto LABEL_1603;
          v538 = (unsigned int)plLbound[0];
          goto LABEL_1565;
        }
        break;
      case 15204:
        v534 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v535 = v534;
        if ( v534 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v534) )
            goto LABEL_1647;
          plLbound[0] = CMarkup::GetDebugState(v535);
          v536 = plLbound[0];
          CMarkup::SetDebugState(v535, 1);
          v537 = 1;
LABEL_1563:
          Text = CDoc::DynamicAttachDebugger(this, v536, v537);
          if ( Text >= 0 )
            goto LABEL_1603;
          v538 = (unsigned int)plLbound[0];
LABEL_1565:
          CMarkup::SetDebugState(v535, v538);
          goto LABEL_1581;
        }
        break;
      case 15205:
        VariantInit(a7);
        a7->vt = 3;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v533 = CDoc::PrimaryMarkup((CDoc *)this);
          DebugState = CMarkup::GetDebugState(v533);
        }
        else
        {
          DebugState = 0;
        }
        goto LABEL_1025;
      default:
        goto LABEL_231;
    }
    Text = -2147418113;
    goto LABEL_1581;
  }
  if ( v605 )
    CScriptCollection::Release(v605);
  Text = -2147467263;
LABEL_15:
  CServer::CLock::~CLock((CServer::CLock *)v604);
  return (unsigned int)Text;
}

```

## disassembly

```asm
0x1806d3d68  push    rbp
0x1806d3d6a  push    rbx
0x1806d3d6b  push    rsi
0x1806d3d6c  push    rdi
0x1806d3d6d  push    r12
0x1806d3d6f  push    r13
0x1806d3d71  push    r14
0x1806d3d73  push    r15
0x1806d3d75  lea     rbp, [rsp-13A8h]
0x1806d3d7d  mov     eax, 1508h
0x1806d3d82  call    _alloca_probe
0x1806d3d87  sub     rsp, rax
0x1806d3d8a  movaps  [rsp+1540h+var_50], xmm6
0x1806d3d92  mov     rax, cs:__security_cookie
0x1806d3d99  xor     rax, rsp
0x1806d3d9c  mov     [rbp+13E0h+var_60], rax
0x1806d3da3  mov     r15, [rbp+13E0h+arg_28]
0x1806d3daa  mov     ebx, r9d
0x1806d3dad  mov     r12, [rbp+13E0h+arg_30]
0x1806d3db4  mov     r14, rcx
0x1806d3db7  mov     rcx, r8; struct _GUID *
0x1806d3dba  mov     [rbp+13E0h+var_1434], ebx
0x1806d3dbd  mov     qword ptr [rbp+13E0h+var_1300], r15
0x1806d3dc4  mov     r13, r8
0x1806d3dc7  mov     [rbp+13E0h+String1], r12
0x1806d3dce  mov     rdi, rdx
0x1806d3dd1  mov     [rbp+13E0h+var_1428], r8
0x1806d3dd5  mov     [rbp+13E0h+var_1450], rdx
0x1806d3dd9  call    ?IsCmdGroupSupported@CBase@@SAHPEBU_GUID@@@Z; CBase::IsCmdGroupSupported(_GUID const *)
0x1806d3dde  test    eax, eax
0x1806d3de0  jnz     short loc_1806D3DEC
0x1806d3de2  mov     eax, 80040104h
0x1806d3de7  jmp     loc_1806DAC65
0x1806d3dec  xor     r8d, r8d; unsigned __int16
0x1806d3def  lea     rcx, [rbp+13E0h+var_1338]; this
0x1806d3df6  mov     rdx, r14; struct CDoc *
0x1806d3df9  call    ??0CLock@CDoc@@QEAA@PEAV1@G@Z; CDoc::CLock::CLock(CDoc *,ushort)
0x1806d3dfe  xor     eax, eax
0x1806d3e00  xor     edx, edx
0x1806d3e02  mov     [rbp+13E0h+var_1348], rax
0x1806d3e09  xorps   xmm0, xmm0
0x1806d3e0c  mov     [rbp+13E0h+var_1360], rax
0x1806d3e13  xorps   xmm1, xmm1
0x1806d3e16  mov     [rbp+13E0h+var_1418], rdx
0x1806d3e1a  mov     esi, 80040100h
0x1806d3e1f  movups  [rbp+13E0h+var_1358], xmm0
0x1806d3e26  movups  [rbp+13E0h+var_1370], xmm1
0x1806d3e2a  test    r13, r13
0x1806d3e2d  jnz     short loc_1806D3E5B
0x1806d3e2f  mov     r9d, [rbp+13E0h+arg_20]; unsigned int
0x1806d3e36  mov     r8d, ebx; unsigned int
0x1806d3e39  mov     [rsp+1540h+lpcbData], r12; struct tagVARIANT *
0x1806d3e3e  mov     rdx, rdi; struct CDocument *
0x1806d3e41  mov     rcx, r14; this
0x1806d3e44  mov     [rsp+1540h+phkResult], r15; struct tagVARIANT *
0x1806d3e49  call    ?BrowserDocumentServerExec@CDoc@@QEAAJPEAVCDocument@@KKPEAUtagVARIANT@@1@Z; CDoc::BrowserDocumentServerExec(CDocument *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x1806d3e4e  mov     esi, eax
0x1806d3e50  cmp     eax, 80040100h
0x1806d3e55  jnz     loc_1806DAC57
0x1806d3e5b  cmp     [rbp+13E0h+arg_20], 3
0x1806d3e62  jnz     short loc_1806D3E7C
0x1806d3e64  mov     rcx, [rbp+13E0h+var_1328]; this
0x1806d3e6b  test    rcx, rcx
0x1806d3e6e  jz      short loc_1806D3E75
0x1806d3e70  call    ?Release@CScriptCollection@@UEAAKXZ; CScriptCollection::Release(void)
0x1806d3e75  mov     esi, 80004001h
0x1806d3e7a  jmp     short loc_1806D3EB4
0x1806d3e7c  mov     rbx, rdi
0x1806d3e7f  test    rdi, rdi
0x1806d3e82  jnz     short loc_1806D3EC5
0x1806d3e84  mov     rax, [r14+338h]
0x1806d3e8b  test    rax, rax
0x1806d3e8e  jz      short loc_1806D3E9E
0x1806d3e90  mov     rax, [rax+78h]
0x1806d3e94  mov     rdi, [rax+78h]
0x1806d3e98  mov     [rbp+13E0h+var_1450], rdi
0x1806d3e9c  jmp     short loc_1806D3EDC
0x1806d3e9e  mov     rcx, [rbp+13E0h+var_1328]; this
0x1806d3ea5  test    rcx, rcx
0x1806d3ea8  jz      short loc_1806D3EAF
0x1806d3eaa  call    ?Release@CScriptCollection@@UEAAKXZ; CScriptCollection::Release(void)
0x1806d3eaf  mov     esi, 8000FFFFh
0x1806d3eb4  lea     rcx, [rbp+13E0h+var_1338]; this
0x1806d3ebb  call    ??1CLock@CServer@@QEAA@XZ; CServer::CLock::~CLock(void)
0x1806d3ec0  jmp     loc_1806DAC63
0x1806d3ec5  mov     rax, [rdi+38h]
0x1806d3ec9  test    rax, rax
0x1806d3ecc  jz      short loc_1806D3ED4
0x1806d3ece  mov     rcx, [rax+68h]
0x1806d3ed2  jmp     short loc_1806D3ED8
0x1806d3ed4  mov     rcx, [rdi+30h]
0x1806d3ed8  mov     [rbp+13E0h+var_1418], rcx
0x1806d3edc  mov     edx, [rbp+13E0h+var_1434]; unsigned int
0x1806d3edf  mov     rcx, r13; struct _GUID *
0x1806d3ee2  call    ?IDMFromCmdID@CBase@@SAHPEBU_GUID@@K@Z; CBase::IDMFromCmdID(_GUID const *,ulong)
0x1806d3ee7  mov     edx, 20h ; ' '
0x1806d3eec  mov     [rbp+13E0h+plLbound], eax
0x1806d3eef  mov     r13d, eax
0x1806d3ef2  lea     ecx, [rax-0E74h]
0x1806d3ef8  cmp     ecx, edx
0x1806d3efa  ja      short loc_1806D3F46
0x1806d3efc  mov     rcx, [r14+1100h]; this
0x1806d3f03  test    rcx, rcx
0x1806d3f06  jz      short loc_1806D3F12
0x1806d3f08  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x1806d3f0d  test    rax, rax
0x1806d3f10  jnz     short loc_1806D3F2E
0x1806d3f12  mov     rax, [rdi+38h]
0x1806d3f16  test    rax, rax
0x1806d3f19  jz      short loc_1806D3F21
0x1806d3f1b  mov     rax, [rax+68h]
0x1806d3f1f  jmp     short loc_1806D3F25
0x1806d3f21  mov     rax, [rdi+30h]
0x1806d3f25  test    rax, rax
0x1806d3f28  jz      loc_1806DAC57
0x1806d3f2e  mov     r9, r15; struct tagVARIANT *
0x1806d3f31  mov     r8d, r13d; unsigned int
0x1806d3f34  mov     rdx, rax; struct CMarkup *
0x1806d3f37  mov     rcx, r14; this
0x1806d3f3a  call    ?OnContextMenuExt@CDoc@@QEAAJPEAVCMarkup@@IPEAUtagVARIANT@@@Z; CDoc::OnContextMenuExt(CMarkup *,uint,tagVARIANT *)
0x1806d3f3f  mov     esi, eax
0x1806d3f41  jmp     loc_1806DAC57
0x1806d3f46  mov     edi, 1
0x1806d3f4b  mov     eax, 17BAh
0x1806d3f50  mov     ecx, 400h
0x1806d3f55  mov     r9d, 0FFFFFFFFh
0x1806d3f5b  lea     r10d, [rdi+1]
0x1806d3f5f  cmp     r13d, eax
0x1806d3f62  ja      loc_1806D7CBB
0x1806d3f68  jz      loc_1806D7C83
0x1806d3f6e  mov     edx, 8FCh; struct MemoryProtection::leaf_t *
0x1806d3f73  mov     r8d, 85Bh
0x1806d3f79  lea     eax, [rdx+28h]
0x1806d3f7c  cmp     r13d, eax
0x1806d3f7f  ja      loc_1806D6029
0x1806d3f85  lea     r9d, [rdx+16h]
0x1806d3f89  jz      loc_1806D58CC
0x1806d3f8f  lea     eax, [rdx-27h]
0x1806d3f92  cmp     r13d, eax
0x1806d3f95  ja      loc_1806D5433
0x1806d3f9b  jz      loc_1806D530E
0x1806d3fa1  lea     eax, [r8-80h]
0x1806d3fa5  cmp     r13d, eax
0x1806d3fa8  ja      loc_1806D46B9
0x1806d3fae  jz      loc_1806D46A6
0x1806d3fb4  cmp     r13d, 46h ; 'F'
0x1806d3fb8  ja      loc_1806D41A0
0x1806d3fbe  jz      loc_1806D446F
0x1806d3fc4  mov     eax, r13d
0x1806d3fc7  sub     eax, 1Bh
0x1806d3fca  jz      loc_1806D9F58
0x1806d3fd0  sub     eax, edi
0x1806d3fd2  jz      loc_1806D411C
0x1806d3fd8  sub     eax, edi
0x1806d3fda  jz      loc_1806D40FD
0x1806d3fe0  sub     eax, 8
0x1806d3fe3  jz      loc_1806D40BB
0x1806d3fe9  sub     eax, 6
0x1806d3fec  jz      loc_1806D4079
0x1806d3ff2  sub     eax, 4
0x1806d3ff5  jz      short loc_1806D4059
0x1806d3ff7  cmp     eax, 14h
0x1806d3ffa  jnz     def_1806D7CF0; jumptable 00000001806D7CF0 default case
0x1806d4000  cmp     dword ptr [r14+12F8h], 0
0x1806d4008  jl      def_1806D7CF0; jumptable 00000001806D7CF0 default case
0x1806d400e  cmp     [rbp+13E0h+arg_20], r10d
0x1806d4015  jz      def_1806D7CF0; jumptable 00000001806D7CF0 default case
0x1806d401b  xor     esi, esi
0x1806d401d  xor     eax, eax
0x1806d401f  mov     qword ptr [rbp+13E0h+pvarg+10h], rax
0x1806d4023  xorps   xmm0, xmm0
0x1806d4026  mov     [rbp+13E0h+ppvData], rsi
0x1806d402a  mov     qword ptr [rbp+13E0h+rgIndices], rsi
0x1806d402e  mov     [rbp+13E0h+bstrString], rsi
0x1806d4032  movups  xmmword ptr [rbp+13E0h+pvarg], xmm0
0x1806d4036  mov     word ptr [rbp+13E0h+pvarg], di
0x1806d403a  test    rbx, rbx
0x1806d403d  jz      loc_1806D47CD
0x1806d4043  mov     rax, [rbx+38h]
0x1806d4047  test    rax, rax
0x1806d404a  jz      loc_1806D47C7
0x1806d4050  mov     rbx, [rax+68h]
0x1806d4054  jmp     loc_1806D4812
0x1806d4059  mov     rcx, r14; this
0x1806d405c  call    ?DesignMode@CDoc@@UEAAHXZ; CDoc::DesignMode(void)
0x1806d4061  xor     r13d, r13d
0x1806d4064  test    eax, eax
0x1806d4066  jz      short loc_1806D4071
0x1806d4068  bts     dword ptr [r14+1300h], 1Ch
0x1806d4071  mov     esi, r13d
0x1806d4074  jmp     loc_1806DAC45
0x1806d4079  mov     ebx, [r14+130Ch]
0x1806d4080  mov     eax, ebx
0x1806d4082  or      eax, ecx
0x1806d4084  mov     rcx, r14; this
0x1806d4087  mov     [r14+130Ch], eax
0x1806d408e  call    ?EditUndo@CDoc@@QEAAJXZ; CDoc::EditUndo(void)
0x1806d4093  shr     ebx, 0Ah
0x1806d4096  mov     esi, eax
0x1806d4098  mov     eax, [r14+130Ch]
0x1806d409f  movzx   ecx, bl
0x1806d40a2  shl     ecx, 0Ah
0x1806d40a5  xor     ecx, eax
0x1806d40a7  and     ecx, 400h
0x1806d40ad  xor     ecx, eax
0x1806d40af  mov     [r14+130Ch], ecx
0x1806d40b6  jmp     def_1806D7CF0; jumptable 00000001806D7CF0 default case
0x1806d40bb  mov     rcx, [rbp+13E0h+var_1450]; this
0x1806d40bf  call    ?Markup@CDocument@@QEBAPEAVCMarkup@@XZ; CDocument::Markup(void)
0x1806d40c4  mov     rcx, rax; this
0x1806d40c7  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x1806d40cc  mov     dl, dil; bool
0x1806d40cf  mov     rcx, rax; this
0x1806d40d2  call    ?Fire_onbeforeunload@COmWindowProxy@@QEAAH_N@Z; COmWindowProxy::Fire_onbeforeunload(bool)
0x1806d40d7  xor     r13d, r13d
0x1806d40da  mov     esi, r13d
0x1806d40dd  test    r12, r12
0x1806d40e0  jz      loc_1806DAC4F
0x1806d40e6  neg     eax
0x1806d40e8  mov     word ptr [r12], 0Bh
0x1806d40ef  sbb     ax, ax
0x1806d40f2  mov     [r12+8], ax
0x1806d40f8  jmp     loc_1806DAC4A
0x1806d40fd  mov     ebx, [r14+130Ch]
0x1806d4104  mov     eax, ebx
0x1806d4106  or      eax, ecx
0x1806d4108  mov     rcx, r14; this
0x1806d410b  mov     [r14+130Ch], eax
0x1806d4112  call    ?EditRedo@CDoc@@QEAAJXZ; CDoc::EditRedo(void)
0x1806d4117  jmp     loc_1806D4093
0x1806d411c  lea     rbx, [r14+1100h]
0x1806d4123  xor     r13d, r13d
0x1806d4126  mov     rcx, [rbx]; this
0x1806d4129  test    rcx, rcx
0x1806d412c  jz      short loc_1806D4140
0x1806d412e  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x1806d4133  mov     rcx, rax; this
0x1806d4136  call    ?Document@CMarkup@@QEAAPEAVCDocument@@XZ; CMarkup::Document(void)
0x1806d413b  mov     rsi, rax
0x1806d413e  jmp     short loc_1806D4144
0x1806d4140  mov     rsi, [rbp+13E0h+var_1450]
0x1806d4144  mov     rcx, [rbx]; this
0x1806d4147  test    rcx, rcx
0x1806d414a  jz      short loc_1806D4155
0x1806d414c  call    ?HasPages@CBase@@QEAAHXZ; CBase::HasPages(void)
0x1806d4151  test    eax, eax
0x1806d4153  jnz     short loc_1806D418A
0x1806d4155  cmp     [rbx], r13
0x1806d4158  jnz     short loc_1806D4184
0x1806d415a  mov     rcx, r14; this
0x1806d415d  call    ?GetActiveElement@CDoc@@QEBAPEAVCElement@@XZ; CDoc::GetActiveElement(void)
0x1806d4162  test    rax, rax
0x1806d4165  jz      short loc_1806D4184
0x1806d4167  mov     rcx, r14; this
0x1806d416a  call    ?GetActiveElement@CDoc@@QEBAPEAVCElement@@XZ; CDoc::GetActiveElement(void)
0x1806d416f  mov     rcx, rax; this
0x1806d4172  call    ?HasPages@CBase@@QEAAHXZ; CBase::HasPages(void)
0x1806d4177  test    eax, eax
0x1806d4179  jz      short loc_1806D4184
0x1806d417b  lea     rbx, [r14+388h]
0x1806d4182  jmp     short loc_1806D418A
0x1806d4184  mov     edi, r13d
0x1806d4187  mov     rbx, r13
0x1806d418a  mov     r9, rbx; struct CElement **
0x1806d418d  mov     r8d, edi; cElements
0x1806d4190  mov     rdx, rsi; struct CDocument *
0x1806d4193  mov     rcx, r14; this
0x1806d4196  call    ?ShowPropertyDialog@CDoc@@QEAAJPEAVCDocument@@HPEAPEAVCElement@@@Z; CDoc::ShowPropertyDialog(CDocument *,int,CElement * *)
0x1806d419b  jmp     loc_1806D4071
0x1806d41a0  mov     eax, r13d
0x1806d41a3  sub     eax, 47h ; 'G'
0x1806d41a6  jz      loc_1806D44FE
0x1806d41ac  sub     eax, 16h
0x1806d41af  jz      loc_1806D9F58
0x1806d41b5  sub     eax, 773h
0x1806d41ba  jz      loc_1806D4461
0x1806d41c0  sub     eax, edi
0x1806d41c2  jz      loc_1806D4461
0x1806d41c8  sub     eax, r10d
0x1806d41cb  jz      loc_1806D439D
0x1806d41d1  sub     eax, edi
0x1806d41d3  jz      short loc_1806D41EA
0x1806d41d5  mov     ebx, 6
0x1806d41da  cmp     eax, ebx
0x1806d41dc  jnz     def_1806D7CF0; jumptable 00000001806D7CF0 default case
0x1806d41e2  mov     r8d, edi
0x1806d41e5  jmp     loc_1806D46A9
0x1806d41ea  mov     rcx, [r14+10E0h]
0x1806d41f1  test    rcx, rcx
0x1806d41f4  jz      short loc_1806D4234
0x1806d41f6  mov     edx, [rbp+13E0h+arg_20]
0x1806d41fc  cmp     edx, r10d
0x1806d41ff  jz      short loc_1806D4234
0x1806d4201  test    dword ptr [r14+12FCh], 400000h
0x1806d420c  jnz     short loc_1806D4234
0x1806d420e  mov     rax, [rcx]
0x1806d4211  mov     r9d, edx
0x1806d4214  mov     r8d, [rbp+13E0h+var_1434]
0x1806d4218  lea     rdx, CGID_DocHostCommandHandler
0x1806d421f  mov     [rsp+1540h+lpcbData], r12
  ... truncated ...
```
