# CDoc::ExecHelper(CDocument *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x1806d4ea8`
- end: `0x1806dc070`
- name: `?ExecHelper@CDoc@@QEAAJPEAVCDocument@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z`
- size: `29128`
- prototype: `__int64 __fastcall(CDoc *__hidden this, struct CDocument *, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *, VARIANTARG *)`
- caller_count: `10`
- callee_count: `395`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e6c24`
- `0x1806d4e70`
- `0x1806d4ea8`
- `0x18087fff0`
- `0x180891370`
- `0x18097d820`
- `0x180991c10`
- `0x180d34f50`
- `0x180e5db60`
- `0x181052af0`

## callees

- `0x18000dc74`
- `0x180012430`
- `0x180013efc`
- `0x18002f6d0`
- `0x180037c84`
- `0x1800501fc`
- `0x18005d0e4`
- `0x18005db70`
- `0x180066940`
- `0x18006b354`
- `0x1800895bc`
- `0x18008a2c8`
- `0x1800a89a0`
- `0x1800aa864`
- `0x1800b6ce0`
- `0x1800bb020`
- `0x1800bbf30`
- `0x1800c5000`
- `0x1800e5024`
- `0x1800e7a2c`
- `0x1800e7b18`
- `0x1800e7be0`
- `0x1800ea428`
- `0x18011853c`
- `0x18011a7c4`
- `0x1801296e4`
- `0x1801297b8`
- `0x18012b1f0`
- `0x18012ba30`
- `0x18012bd68`
- `0x180133b3c`
- `0x180137368`
- `0x1801393a8`
- `0x180148494`
- `0x180149610`
- `0x18014b724`
- `0x18014e21c`
- `0x180155b88`
- `0x18015a55c`
- `0x18016666c`
- `0x1801c0790`
- `0x1801dc4a4`
- `0x1801e9400`
- `0x1801f1900`
- `0x1801f5a74`
- `0x18021b2c4`
- `0x18025f724`
- `0x18025f744`
- `0x180265374`
- `0x18026a150`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1806d61dc`
- `msvcrt!_ultow_s` at `0x1806d61dc`
- `msvcrt!wcsrchr` at `0x1806d5dbd`
- `msvcrt!wcsrchr` at `0x1806d5dbd`
- `KERNEL32!CreateFileW` at `0x1806d5e3f`
- `KERNEL32!CreateFileW` at `0x1806d5e3f`
- `KERNEL32!CloseHandle` at `0x1806d5e57`
- `KERNEL32!CloseHandle` at `0x1806d5e57`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806d5d7d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806d5d7d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d5d0d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d5d43`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d5d0d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806d5d43`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d5d8f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d5d9f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d5d8f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806d5d9f`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1806d61e8`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1806d61e8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d7368`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d7a56`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806db283`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806db3cf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806dbcd2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d7368`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806d7a56`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806db283`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806db3cf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806dbcd2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1806d7378`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1806d7378`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x1806daf14`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x1806daf14`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806dab0f`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806dadaa`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806dab0f`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1806dadaa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806daf81`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1806daf81`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d6293`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d62c9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d6293`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1806d62c9`
- `WININET!InternetSetOptionW` at `0x1806da7fb`
- `WININET!InternetSetOptionW` at `0x1806da7fb`
- `urlmon!__imp_GetMinLayoutWidthFromCVList` at `0x1806d9ff5`
- `urlmon!__imp_GetMinLayoutWidthFromCVList` at `0x1806d9ff5`
- `ieapfltr!GetUrlBlockClient` at `0x1806d8f78`
- `ieapfltr!GetUrlBlockClient` at `0x1806d8f78`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d73b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d87be`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d8c02`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d9696`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d98e0`
- `OLEAUT32!__imp_SysAllocString` at `0x1806daf33`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d73b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d87be`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d8c02`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d9696`
- `OLEAUT32!__imp_SysAllocString` at `0x1806d98e0`
- `OLEAUT32!__imp_SysAllocString` at `0x1806daf33`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d5aae`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d8c72`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d8fdf`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d5aae`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d8c72`
- `OLEAUT32!__imp_SysFreeString` at `0x1806d8fdf`
- `OLEAUT32!__imp_VariantInit` at `0x1806d689e`
- `OLEAUT32!__imp_VariantInit` at `0x1806d7bc7`
- `OLEAUT32!__imp_VariantInit` at `0x1806d967c`
- `OLEAUT32!__imp_VariantInit` at `0x1806d97dc`
- `OLEAUT32!__imp_VariantInit` at `0x1806dac1e`
- `OLEAUT32!__imp_VariantInit` at `0x1806dad38`
- `OLEAUT32!__imp_VariantInit` at `0x1806dad4b`
- `OLEAUT32!__imp_VariantInit` at `0x1806dad5b`
- `OLEAUT32!__imp_VariantInit` at `0x1806dafa7`
- `OLEAUT32!__imp_VariantInit` at `0x1806db653`
- `OLEAUT32!__imp_VariantInit` at `0x1806db91c`
- `OLEAUT32!__imp_VariantInit` at `0x1806d689e`
- `OLEAUT32!__imp_VariantInit` at `0x1806d7bc7`
- `OLEAUT32!__imp_VariantInit` at `0x1806d967c`
- `OLEAUT32!__imp_VariantInit` at `0x1806d97dc`
- `OLEAUT32!__imp_VariantInit` at `0x1806dac1e`
- `OLEAUT32!__imp_VariantInit` at `0x1806dad38`
- `OLEAUT32!__imp_VariantInit` at `0x1806dad4b`
- `OLEAUT32!__imp_VariantInit` at `0x1806dad5b`
- `OLEAUT32!__imp_VariantInit` at `0x1806dafa7`
- `OLEAUT32!__imp_VariantInit` at `0x1806db653`
- `OLEAUT32!__imp_VariantInit` at `0x1806db91c`
- `OLEAUT32!__imp_VariantClear` at `0x1806d53d2`
- `OLEAUT32!__imp_VariantClear` at `0x1806d54aa`
- `OLEAUT32!__imp_VariantClear` at `0x1806d54cf`
- `OLEAUT32!__imp_VariantClear` at `0x1806d5c97`
- `OLEAUT32!__imp_VariantClear` at `0x1806dae32`
- `OLEAUT32!__imp_VariantClear` at `0x1806dae45`
- `OLEAUT32!__imp_VariantClear` at `0x1806d53d2`
- `OLEAUT32!__imp_VariantClear` at `0x1806d54aa`
- `OLEAUT32!__imp_VariantClear` at `0x1806d54cf`
- `OLEAUT32!__imp_VariantClear` at `0x1806d5c97`
- `OLEAUT32!__imp_VariantClear` at `0x1806dae32`
- `OLEAUT32!__imp_VariantClear` at `0x1806dae45`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1806daec8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1806daec8`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d80de`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d9bef`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d80de`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806d9bef`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d8125`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d9c10`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806daabf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d8125`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806d9c10`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806daabf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1806d8107`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1806d8107`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d97b0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d9c38`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806daa98`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806daee7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d97b0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806d9c38`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806daa98`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806daee7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806d9c6f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806daf90`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806d9c6f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806daf90`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d81cd`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806da863`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806da889`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806dad7a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806dadce`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806dadff`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806d81cd`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806da863`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806da889`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806dad7a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806dadce`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1806dadff`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db69c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db6c0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db6df`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db6fe`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db69c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db6c0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db6df`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1806db6fe`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d8141`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d815d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d8141`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1806d815d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806d9780`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806db671`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806d9780`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1806db671`
- `OLEAUT32!__imp_OleTranslateColor` at `0x1806db7d4`
- `OLEAUT32!__imp_OleTranslateColor` at `0x1806db7d4`

## string_xrefs

- `0x1806d5ce9`: `CLSID\{25336920-03F9-11CF-8FD0-00AA00686F13}`
- `0x1806d5df0`: `\readme.htm`

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
  __int64 v164; // rdx
  VARIANTARG *v165; // rbx
  __int64 v166; // rdx
  struct CElement *v167; // rdx
  __int64 v168; // rcx
  CMarkup *v169; // rcx
  int v170; // ebx
  CInPlace *v171; // rcx
  __int64 (__fastcall ***v172)(_QWORD, GUID *, BSTR *); // rcx
  HRESULT v173; // eax
  CMarkup *v174; // rax
  struct CGlyph *GlyphTable; // rax
  int v176; // edx
  CPeerFactoryUrl *v177; // rcx
  unsigned __int16 *Url; // rax
  CMarkup *v179; // rax
  CScriptCollection *ScriptCollection; // rax
  LONG lVal; // esi
  int v182; // ebx
  struct CElement *v183; // rax
  __int64 v184; // rcx
  CMarkup *v185; // rax
  CDwnDoc *DwnDoc; // rax
  CMarkup *v187; // rax
  CMarkup *v188; // rax
  CMarkup *v189; // rbx
  BOOL v190; // ecx
  struct CElement *ElementTopHelper; // rax
  CElement *TopLayoutElement; // rax
  struct CElement *v193; // rax
  BYTE bVal; // al
  int v195; // ecx
  int v196; // eax
  unsigned int v197; // ecx
  CInPlace *v198; // rax
  struct IUnknown *v199; // rax
  int SelectionMarkup; // ebx
  CElement *v201; // rax
  int v202; // ebx
  int v203; // ebx
  CMarkup *v204; // rax
  CMarkup *v205; // rax
  struct CGlyph *v206; // rax
  CElement *v207; // rcx
  CMarkup *v208; // rax
  CMarkup *v209; // rax
  struct CMarkup *v210; // rbx
  struct CSecurityContext *v211; // rax
  struct IUnknown *v212; // rcx
  unsigned __int16 *v213; // rbx
  struct CMarkup *v214; // rax
  struct CParentUndoUnit *v215; // rbx
  CMarkup *v216; // rbx
  COptionsHolder *v217; // rax
  struct CSecurityContext *v218; // rax
  CIPrintCollection *v219; // rbx
  LONG v220; // ecx
  int v221; // ecx
  CIPrintCollection *v222; // rax
  __int64 v223; // rcx
  __int64 v224; // rdx
  __int64 v225; // rdi
  CMarkup *v226; // rdi
  struct CMarkupTopElemCache *v227; // rax
  __int64 v228; // rdx
  CIPrintCollection *v229; // rbx
  CElement *v230; // rax
  struct CMarkup *v231; // rax
  CElement *v232; // rax
  CTreePos *v233; // rcx
  __int64 v234; // rcx
  __int64 LookasidePtr2; // rax
  void *v236; // rcx
  CIPrintCollection *v237; // rax
  __int64 v238; // rcx
  __int64 v239; // rdx
  struct CWindow *v240; // rax
  struct IUnknown *v241; // rcx
  CAutoRange *v242; // rsi
  int v243; // ecx
  unsigned int v244; // eax
  int v245; // eax
  CMarkup *v246; // rax
  CMarkup *v247; // rbx
  struct CMarkupEditContext *v248; // rax
  CMarkup *v249; // rbx
  CInPlace *v250; // rcx
  HRESULT v251; // eax
  struct IUnknown *v252; // rcx
  HRESULT v253; // eax
  CDocument *v254; // rbx
  struct CWindow *v255; // rax
  __int64 v256; // rbx
  CMarkup *v257; // rbx
  int v258; // eax
  int v259; // ecx
  int NormZoomPercent; // eax
  CMarkup *v261; // rax
  CMarkup *v262; // rbx
  CStr *v263; // rax
  CStr *v264; // rax
  CMarkup *v265; // rax
  CMarkup *v266; // rbx
  CMarkup *v267; // rax
  struct CMarkup *v268; // rbx
  __int64 v269; // rsi
  bool v270; // bl
  __int64 v271; // rdx
  BYTE v272; // r8
  CMarkup *v273; // rax
  struct CMarkupStyleState *StyleState; // rax
  CMarkup *v275; // rbx
  CStr *v276; // rax
  CStr *v277; // rax
  CDispSurface *v278; // rax
  struct IDispRenderTarget *v279; // rax
  struct tagVARIANT *v280; // rcx
  signed __int64 v281; // rax
  int v282; // edx
  int v283; // r8d
  struct CMarkupStyleState *v284; // rax
  struct IUnknown *v285; // rdx
  SAFEARRAY *v286; // rbx
  signed int v287; // edx
  SAFEARRAY *v288; // rbx
  LONG v289; // eax
  LONG v290; // ecx
  HRESULT Element; // eax
  struct IUnknown **v292; // rax
  struct IUnknown *punkVal; // rcx
  const struct CDispNode *v294; // rdx
  struct CRect *v295; // r8
  struct IUnknown *v296; // rcx
  struct CDocument *v297; // r8
  struct CElement *v298; // rdx
  CMarkup *v299; // rbx
  int v300; // eax
  int v301; // esi
  int v302; // edi
  unsigned int v303; // eax
  HMENU EncodingMenu; // rax
  CMarkup *v305; // rax
  const WCHAR *v306; // rbx
  struct CMarkup *v307; // rax
  CMarkup *v308; // rax
  unsigned int v309; // eax
  struct CElement *v310; // rdx
  unsigned int v311; // ebx
  int v312; // eax
  COmWindowProxy *v313; // rcx
  CMarkup *v314; // rax
  __int64 v315; // r8
  struct CMarkup *v316; // rax
  struct CElement *v317; // rax
  int DefaultBlockTag; // eax
  const OLECHAR *v319; // rcx
  BOOL v320; // ebx
  CInPlace *v321; // rcx
  CElement *v322; // rcx
  CMarkup *v323; // rax
  CMarkup *v324; // rax
  struct GWND *Gwnd; // rax
  struct CElement *v326; // rdx
  int v327; // ecx
  HMENU DocDirMenu; // rax
  LONG v329; // eax
  int v330; // esi
  bool v331; // al
  __int16 *v332; // rdx
  bool v333; // al
  __int16 *v334; // rcx
  __int16 v335; // cx
  HMENU FontSizeMenu; // rax
  LONG v337; // eax
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, BSTR *); // rcx
  CDocument *v339; // rdi
  struct INamedPropertyBag *v340; // rbx
  struct CMarkup *v341; // rax
  CMarkup *v342; // rax
  struct CElement *v343; // rax
  COmWindowProxy *v344; // rcx
  CDocument *v345; // rax
  BSTR v346; // rax
  struct CMarkup *v347; // rax
  struct IDispRenderTarget *v348; // rax
  LONG v349; // eax
  ReadingMode::CTextClusterDetector *v350; // rax
  ReadingMode::CTextClusterDetector *v351; // rax
  ReadingMode::CTextClusterDetector *v352; // rbx
  CInputManager *v353; // rax
  CDeferredActionHandler *v354; // rax
  struct CMarkup *v355; // rax
  CInPlace *v356; // rbx
  __int64 CodePageCore; // r8
  unsigned int v358; // esi
  BSTR v359; // rcx
  bool IsEnterpriseMode; // bl
  CMarkup *v361; // rax
  CMarkupVersion *v362; // rax
  SHORT v363; // ax
  bool v364; // zf
  struct CMarkup *v365; // rax
  struct CMarkup *v366; // rbx
  CInPlace *v367; // rcx
  CInputManager *v368; // rax
  CDeferredActionHandler *v369; // rax
  CInputManager *v370; // rax
  CDeferredActionHandler *v371; // rax
  CInputManager *v372; // rax
  CDeferredActionHandler *v373; // rax
  CInputManager *v374; // rax
  CDeferredActionHandler *v375; // rax
  CInputManager *v376; // rax
  CDeferredActionHandler *v377; // rax
  SHORT v378; // cx
  int v379; // eax
  CVirtualTabStorageEntry *v380; // rcx
  struct CMarkup *v381; // rax
  CPreloadManager *v382; // rax
  struct IDispSystem *DispSystem; // rax
  LONG v384; // eax
  LONG v385; // ecx
  unsigned int Lo; // r9d
  char *v387; // rax
  LONG DebugState; // eax
  struct THREADSTATEUI *ThreadStateUI; // rax
  struct CMarkup *v390; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdx
  LONG v392; // r8d
  struct CMarkup *v393; // rax
  int v394; // ecx
  SAFEARRAY *Vector; // rax
  __int64 i; // r13
  char v397; // r8
  _QWORD *v398; // rbx
  COptionsHolder *v399; // rax
  CHtmCtx *v400; // rax
  const wchar_t *OriginalUrlContext; // rax
  const OLECHAR *v402; // rcx
  unsigned __int64 v403; // rdi
  size_t v404; // r8
  int v405; // eax
  BSTR v406; // rcx
  _QWORD *v407; // rax
  char v408; // dl
  _QWORD *v409; // rcx
  struct CSecurityContext *v410; // rax
  _QWORD *v411; // rcx
  _QWORD *v412; // rcx
  SAFEARRAY *v413; // rcx
  int v414; // eax
  struct CView *View; // rax
  struct CView *v416; // rdi
  int v417; // ebx
  const struct CDispNode *v418; // rdx
  struct CRect *v419; // r8
  const struct CDispNode *v420; // rdx
  struct CRect *v421; // r8
  struct CView *v422; // rax
  struct CView *v423; // rax
  bool IsMobileOptimizedSite; // al
  struct CView *v425; // rax
  SAFEARRAY *v426; // rcx
  SAFEARRAY *v427; // rcx
  CView *v428; // rax
  CFullScreenState *v429; // rax
  __int16 v430; // cx
  struct IUnknown *v431; // rcx
  CElement *v432; // rcx
  struct IUnknown *v433; // rcx
  CFullScreenState *v434; // rax
  int *v435; // rax
  CRootTracker *RootTracker; // rax
  CDCompLayerManager *v437; // rbx
  struct IDispLayer *v438; // rdi
  __int64 (__fastcall *v439)(struct IDispLayer *, GUID *, struct CHtmParseCtx *); // rbx
  CHtmRootParseCtxRouter *v440; // rax
  struct CHtmParseCtx *HpxEmbed; // rax
  struct IDispRenderTarget *v442; // rax
  CAPProcessor *v443; // rcx
  CWindow *v444; // rax
  CWindow *v445; // rbx
  CMarkup *v446; // rdi
  struct COmWindowProxy *v447; // rax
  __int64 v448; // rdx
  __int64 v449; // r9
  _QWORD *ThreadLocalStoragePointer; // rax
  bool v451; // zf
  struct CView *v452; // rax
  CViewportController *v453; // rcx
  _QWORD *v454; // rax
  unsigned int VirtualTabID; // eax
  struct CView *v456; // rax
  CViewportController *v457; // rcx
  CInPlace *v458; // rax
  LONG v459; // ecx
  const struct CMarkup *v460; // rax
  CTextScalingSettings *TextScalingSettings; // rax
  const struct CDispNode *v462; // rdx
  struct CRect *v463; // r8
  SAFEARRAY *v464; // rcx
  SAFEARRAY *v465; // rcx
  struct CMarkup *v466; // rax
  COmWindowProxy *v467; // rcx
  unsigned int (__fastcall ***v468)(_QWORD, GUID *, void **, __int64); // rcx
  CInPlace *v469; // rcx
  struct CMarkup *v470; // rbx
  SAFEARRAY *v471; // rcx
  SAFEARRAY *v472; // rcx
  unsigned int v473; // eax
  _DWORD *v474; // rbx
  HRESULT v475; // eax
  BSTR v476; // rcx
  struct CMarkup *v477; // rbx
  LONG v478; // ecx
  int v479; // ecx
  CMarkup *v480; // rax
  const struct CMarkupVersion *v481; // rax
  CMarkup *v482; // rax
  const struct CMarkupVersion *v483; // rax
  __int64 v484; // rdx
  _QWORD *v485; // rax
  SAFEARRAY *v486; // rcx
  SAFEARRAY *v487; // rcx
  SAFEARRAY *v488; // rcx
  SAFEARRAY *v489; // rax
  SAFEARRAY *v490; // rbx
  BSTR v491; // rax
  LPCWSTR v492; // rdx
  CMarkup *v493; // rax
  LONG v494; // edx
  CMarkupVersion *v495; // rax
  bool IsNativeQuirksLayoutEmulation; // al
  SHORT v497; // cx
  CDCompVideoBackedLayer *v498; // rax
  __int64 (__fastcall ***v499)(_QWORD, GUID *, VARIANTARG *, __int64); // rcx
  const unsigned __int16 *v500; // rdx
  int v501; // ecx
  int iVal; // ebx
  LONG v503; // eax
  int v504; // eax
  unsigned int v505; // esi
  const struct CMarkup *v506; // rax
  const unsigned __int16 *UrlRaw; // rax
  const WCHAR *v508; // rcx
  SAFEARRAY *parray; // rax
  const unsigned __int16 *bstrVal; // r8
  unsigned int v511; // ebx
  struct CMarkup *v512; // rax
  int IsActiveXFilteringEnabled; // eax
  int v514; // r8d
  struct IUnknown *v515; // rcx
  struct ILayoutServices *v516; // rax
  __int64 v517; // rcx
  OLECHAR *j; // rax
  CDispNodeReader *v519; // rax
  CDispScroller *v520; // rax
  CDispTopLevelScroller *v521; // rax
  const struct CDispNode *v522; // rdx
  struct CRect *v523; // r8
  SAFEARRAY *v524; // rax
  SAFEARRAY *v525; // rcx
  SAFEARRAY *v526; // rcx
  SAFEARRAY *v527; // rcx
  int v528; // ebx
  OLE_COLOR *v529; // rcx
  LONG v530; // ebx
  CMarkup *v531; // rax
  LONG v532; // ebx
  CMarkup *v533; // rax
  struct CMarkup *RootMarkup; // rax
  struct CMarkup *v535; // rax
  struct CMarkup *v536; // rax
  struct CMarkup *v537; // rbx
  unsigned int v538; // esi
  __int64 v539; // r8
  __int64 v540; // rdx
  struct CMarkup *v541; // rax
  struct CMarkup *v542; // rax
  struct IBindCtx *v543; // rdx
  void (__fastcall ***v544)(_QWORD, GUID *, struct CHtmParseCtx *); // rdi
  void (__fastcall *v545)(_QWORD, GUID *, struct CHtmParseCtx *); // rbx
  struct CHtmParseCtx *v546; // rax
  HRESULT v547; // eax
  unsigned int CodePageFromMenuID; // esi
  int IsCpAutoDetect; // eax
  CInPlace *v550; // rcx
  int v551; // ebx
  HWND v552; // rax
  CElement *v553; // rcx
  CMarkup *v554; // rax
  CMarkup *FrameOrPrimaryMarkup; // rax
  CMarkup *v556; // r13
  CWindowBarProp *v557; // rdi
  struct CSecurityContext *v558; // rax
  struct COmWindowProxy *v559; // rdi
  unsigned int CPSrc; // ebx
  unsigned int CodePage; // eax
  int v562; // ebx
  CWindowBarProp *v563; // rax
  CTreeNode *v564; // rbx
  struct CMarkup *v565; // rax
  struct CTreeNode *NodeInMarkup; // rax
  struct CElement *ElementClient; // rax
  struct CDocument *v568; // rbx
  CMarkup *v569; // rax
  unsigned int v570; // edi
  struct CMarkupEditContext *EditContext; // rax
  struct _GUID *v572; // rsi
  struct CMarkupEditContext *v573; // rbx
  CEntity *FocusedEntity; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-138h]
  BSTR bstrString; // [rsp+E0h] [rbp-80h] BYREF
  LONG plLbound[2]; // [rsp+E8h] [rbp-78h] BYREF
  CDocument *v578; // [rsp+F0h] [rbp-70h] BYREF
  unsigned int pvData; // [rsp+F8h] [rbp-68h] BYREF
  void *ppvData; // [rsp+100h] [rbp-60h] BYREF
  VARTYPE pvt[2]; // [rsp+108h] [rbp-58h] BYREF
  unsigned int v582; // [rsp+10Ch] [rbp-54h]
  LONG rgIndices[2]; // [rsp+110h] [rbp-50h] BYREF
  struct _GUID *v584; // [rsp+118h] [rbp-48h]
  LPCWSTR pszSubKey; // [rsp+120h] [rbp-40h] BYREF
  struct IUnknown *v586; // [rsp+128h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+130h] [rbp-30h] BYREF
  VARIANTARG pv; // [rsp+148h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+160h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+168h] [rbp+8h] BYREF
  int v591; // [rsp+170h] [rbp+10h] BYREF
  __int64 v592; // [rsp+178h] [rbp+18h]
  __int64 v593; // [rsp+188h] [rbp+28h]
  char v594; // [rsp+198h] [rbp+38h]
  int v595; // [rsp+19Ch] [rbp+3Ch]
  CIPrintCollection *v596; // [rsp+1A0h] [rbp+40h]
  __int64 v597; // [rsp+1A8h] [rbp+48h]
  __int64 v598; // [rsp+1B0h] [rbp+50h]
  size_t BufferCount; // [rsp+1C0h] [rbp+60h] BYREF
  wchar_t *Buffer; // [rsp+1C8h] [rbp+68h] BYREF
  __int128 v601; // [rsp+1D0h] [rbp+70h] BYREF
  VARIANTARG *v602; // [rsp+1E0h] [rbp+80h]
  __int128 v603; // [rsp+1E8h] [rbp+88h] BYREF
  __int128 *v604; // [rsp+1F8h] [rbp+98h]
  int v605; // [rsp+200h] [rbp+A0h] BYREF
  _BYTE v606[16]; // [rsp+208h] [rbp+A8h] BYREF
  CScriptCollection *v607; // [rsp+218h] [rbp+B8h]
  VARIANTARG String1; // [rsp+220h] [rbp+C0h] BYREF
  VARIANTARG v609; // [rsp+240h] [rbp+E0h] BYREF
  _BYTE v610[32]; // [rsp+260h] [rbp+100h] BYREF
  OLECHAR Data[264]; // [rsp+280h] [rbp+120h] BYREF
  OLECHAR psz[2088]; // [rsp+490h] [rbp+330h] BYREF

  v7 = a6;
  v9 = a7;
  v582 = a4;
  *(_QWORD *)&v609.vt = a6;
  *(_QWORD *)&String1.vt = a7;
  v12 = a2;
  v584 = a3;
  v578 = a2;
  if ( !(unsigned int)CBase::IsCmdGroupSupported(a3) )
    return 2147746052LL;
  CDoc::CLock::CLock((CDoc::CLock *)v606, (struct CDoc *)this, 0);
  v604 = 0;
  v602 = 0;
  v586 = 0;
  Text = -2147221248;
  v603 = 0;
  v601 = 0;
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
      v586 = v18;
    }
    else
    {
      v16 = this[103];
      if ( !v16 )
      {
        if ( v607 )
          CScriptCollection::Release(v607);
        Text = -2147418113;
        goto LABEL_15;
      }
      v12 = *(struct CDocument **)(*((_QWORD *)v16 + 15) + 120LL);
      v578 = v12;
    }
    plLbound[0] = CBase::IDMFromCmdID(a3, v582);
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
        v353 = CDoc::InputManager((CDoc *)this);
        v354 = CInputManager::DeferredActionHandler(v353);
        NormZoomPercent = CDeferredActionHandler::RegisterVTabNavigate(v354);
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
                        v40 = v578;
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
                            v74 = *((_QWORD *)v578 + 7);
                            if ( v74 )
                              v31 = *(struct CMarkup **)(v74 + 104);
                            else
                              v31 = (struct CMarkup *)*((_QWORD *)v578 + 6);
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
                                    if ( v20 == dword_18158CE40[4 * v79] )
                                      break;
                                    ++v79;
                                  }
                                  while ( v79 < 9 );
                                  *(_QWORD *)&String1.vt = 16LL * (int)v79;
                                  v80 = *(_DWORD *)&algn_18158CE44[*(_QWORD *)&String1.vt];
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
                                    *(_OWORD *)v610 = v81;
                                    *(_QWORD *)&v610[16] = pRecInfo;
                                    COptionsHolder::put_execArg(
                                      (struct COptionsHolder *)((char *)v75 + 48),
                                      (struct tagVARIANT *)v610);
                                    Text = GetFindText(&bstrString);
                                    if ( !Text )
                                    {
                                      BASICPROPPARAMS::SetStringProperty(
                                        (BASICPROPPARAMS *)qword_1811F5878,
                                        bstrString,
                                        v75,
                                        (struct COptionsHolder *)((char *)v75 + 24),
                                        0);
                                      SysFreeString(bstrString);
                                      bstrString = 0;
                                      if ( v20 == 2121 )
                                      {
                                        v83 = (struct IDispatch *)ppvData;
                                        v84 = *(const unsigned __int16 **)&algn_18158CE44[*(_QWORD *)&String1.vt + 4];
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
                                        memset(&v609, 0, sizeof(v609));
                                        if ( !v89
                                          || (*((_DWORD *)this + 1215) & 0x400000) != 0
                                          || (Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v89 + 32LL))(
                                                       v89,
                                                       &CGID_DocHostCommandHandler,
                                                       42,
                                                       v88,
                                                       &pv,
                                                       &v609)) != 0 )
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
                                                       &v609);
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
                    v34 = CDocument::Markup(v578);
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
                  v501 = *((_DWORD *)this + 1217);
                  if ( (v501 & 0x800) != 0 )
                    goto LABEL_231;
                  iVal = 0;
                  v503 = *((_DWORD *)this + 1215);
                  plLbound[0] = v503;
                  if ( v582 == 93 && (v503 & 1) == 0
                    || v582 == 15038
                    || (v501 & 0x80u) != 0
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
                  v504 = iVal | 1;
                  if ( a5 != 2 )
                    v504 = iVal;
                  v505 = v504 | 0x1000000;
                  if ( v20 != 15038 )
                    v505 = v504;
                  if ( (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  {
                    v506 = CDoc::PrimaryMarkup((CDoc *)this);
                    UrlRaw = CMarkup::GetUrlRaw(v506);
                    v508 = L"about:blank";
                    if ( UrlRaw )
                      v508 = UrlRaw;
                    if ( *v508 && !wcscmp_0(v508, L"outday://") )
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
                        v511 = a5;
                        Text = CDoc::PrintHandler((CDoc *)this, v578, bstrVal, 0, v505, parray, a5, a6, a7, 0);
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
                            *(_QWORD *)&v609.vt = GetThreadStateUI();
                            if ( CodePageFromMenuID == -1 )
                            {
                              if ( v20 != 3699
                                || (IsCpAutoDetect = CDoc::IsCpAutoDetect((CDoc *)this),
                                    CDoc::SetCpAutoDetect((CDoc *)this, IsCpAutoDetect == 0),
                                    !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this))
                                || !(unsigned int)CMLang::IsMLangAvailable((CMLang *)&g_MLang) )
                              {
LABEL_1601:
                                ++*(_DWORD *)(*(_QWORD *)&v609.vt + 604LL);
                                goto LABEL_53;
                              }
                              CodePageFromMenuID = 50001;
                              if ( g_cpDefault == 932 )
                                CodePageFromMenuID = 50932;
                            }
                            v550 = this[12];
                            if ( v550 )
                            {
                              v551 = (_DWORD)this[556] & 0x40000000;
                              v552 = CInPlace::_hwnd_Get(v550);
                              if ( !(unsigned int)CMLang::ValidateCodePage(
                                                    (CMLang *)&g_MLang,
                                                    g_cpDefault,
                                                    CodePageFromMenuID,
                                                    v552,
                                                    1,
                                                    v551) )
                              {
                                v553 = this[544];
                                v554 = v553 ? CElement::GetMarkupPtr(v553) : CDocument::Markup(v578);
                                FrameOrPrimaryMarkup = CMarkup::GetFrameOrPrimaryMarkup(v554, 1);
                                v556 = FrameOrPrimaryMarkup;
                                if ( FrameOrPrimaryMarkup )
                                {
                                  v557 = CMarkup::Root(FrameOrPrimaryMarkup);
                                  CNotification::CNotification((CNotification *)&v591);
                                  v558 = CWindowBarProp::SecurityContext(v557);
                                  CNotification::Initialize(&v591, 59, v557, v558, CodePageFromMenuID, 0);
                                  if ( !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this)
                                    && !(unsigned int)CMarkup::HaveCodePageMetaTag(v556) )
                                  {
                                    CDoc::SaveDefaultCodepage((CDoc *)this, CodePageFromMenuID);
                                  }
                                  CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
                                  CMarkup::BubbleDownCodePage(v556, CodePageFromMenuID);
                                  v559 = CMarkup::Window(v556);
                                  CPSrc = CMarkup::GetCPSrc(v556);
                                  CodePage = CMarkup::GetCodePage(v556);
                                  COmWindowProxy::ExecRefresh(v559, 5, CodePage, CPSrc);
                                }
                              }
                            }
                            goto LABEL_1601;
                          }
                          a5 = v511;
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
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, MSHTML_PRINTPREVIEW_START, 0, 1, &v609);
                      if ( a6 && a6->vt == 8 )
                        v50 = a6->bstrVal;
                      else
                        v50 = 0;
                      Text = CDoc::PrintHandler((CDoc *)this, v578, v50, 0, 0, 0, a5, a6, a7, 1);
                      if ( (Microsoft_IEEnableBits & 0x10000) != 0 )
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, MSHTML_PRINTPREVIEW_STOP, 0, 1, &v609);
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
                  CDoc::CLock::~CLock((CDoc::CLock *)v606);
                  return (unsigned int)Text;
                }
                v43 = this[540];
                if ( v43 && a5 != 2 && (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v43 + 32LL))(
                           v43,
                           &CGID_DocHostCommandHandler,
                           v582,
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
                  *((_QWORD *)&v603 + 1) = v584;
                  v604 = &v601;
                  *(_QWORD *)&v601 = __PAIR64__(a5, v582);
                  LODWORD(v603) = 0;
                  *((_QWORD *)&v601 + 1) = v7;
                  v602 = a7;
                  if ( this[544] )
                  {
                    if ( ((_DWORD)this[608] & 0x40000) != 0 )
                    {
                      v562 = 1;
                      CDoc::BeginUserInitiatedAction((CDoc *)this, 1);
                    }
                    else
                    {
                      v562 = 0;
                    }
                    Text = CDoc::RouteCTElement((CDoc *)this, this[544], (struct CDoc::CTArg *)&v603, v578);
                    if ( v562 )
                      CDoc::EndUserInitiatedAction((CDoc *)this);
                    if ( Text != -2147221248 )
                      goto LABEL_1637;
                  }
                  if ( CDoc::GetActiveElement((CDoc *)this) )
                  {
                    v563 = CDoc::GetActiveElement((CDoc *)this);
                    v564 = CWindowBarProp::SecurityContext(v563);
                    v565 = CDocument::Markup(v578);
                    NodeInMarkup = CTreeNode::GetNodeInMarkup(v564, v565);
                    if ( NodeInMarkup )
                    {
                      ElementClient = (struct CElement *)SP<Tree::CIE9DocumentLayout>::operator->(NodeInMarkup);
                      v568 = v578;
                    }
                    else
                    {
                      v568 = v578;
                      v569 = CDocument::Markup(v578);
                      ElementClient = CMarkup::GetElementClient(v569);
                    }
                    if ( ElementClient )
                    {
                      Text = CDoc::RouteCTElement((CDoc *)this, ElementClient, (struct CDoc::CTArg *)&v603, v568);
                      if ( Text != -2147221248 )
                      {
                        v570 = a5;
LABEL_1639:
                        if ( v20 == 15 && !(unsigned int)CDoc::HasSelection((CDoc *)this) )
                        {
                          v451 = Text == 0;
                          if ( Text < 0 )
                            goto LABEL_1646;
                          goto LABEL_1642;
                        }
LABEL_1645:
                        v451 = Text == 0;
LABEL_1646:
                        if ( !v451 )
                          goto LABEL_1650;
                        goto LABEL_1647;
                      }
                    }
                  }
                }
LABEL_441:
                v198 = this[126];
                if ( (!v198 || !*((_BYTE *)v198 + 38) || !*((_DWORD *)this + 1231))
                  && (int)CServer::State(this) >= 3
                  && (*((char *)this + 4868) >= 0 || v20 != 2315) )
                {
                  v199 = v586;
                  *(_QWORD *)&String1.vt = 0;
                  if ( v586 )
                    goto LABEL_1623;
                  SelectionMarkup = CDoc::GetSelectionMarkup((CDoc *)this, (struct CMarkup **)&v586);
                  v199 = v586;
                  if ( !v586 )
                  {
                    if ( CDoc::GetActiveElement((CDoc *)this) )
                    {
                      v201 = CDoc::GetActiveElement((CDoc *)this);
                      v199 = (struct IUnknown *)CElement::GetMarkupPtr(v201);
                      v586 = v199;
                    }
                    else
                    {
                      v199 = v586;
                    }
                  }
                  if ( SelectionMarkup >= 0 && v199 )
                  {
LABEL_1623:
                    Text = CMarkup::EnsureEditRouter((CMarkup *)v199, (struct CEditRouter **)&String1);
                    if ( Text >= 0 )
                    {
                      CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&v609);
                      EditContext = CMarkup::GetEditContext((CMarkup *)v586);
                      v572 = v584;
                      v573 = EditContext;
                      if ( v584 && (unsigned __int8)_(v584, &CGID_MSHTML) )
                      {
                        if ( v20 - 15 <= 1 )
                        {
                          v25 = 0;
LABEL_1631:
                          *((_DWORD *)v573 + 10) &= ~0x800u;
                          *((_DWORD *)v573 + 10) |= v25 << 11;
                          if ( v25 )
                            CDoc::CDOMTextInputScope::Init((CDoc::CDOMTextInputScope *)&v609, (struct CDoc *)this, 2);
                          *((_DWORD *)v573 + 10) |= 0x400u;
                          goto LABEL_1634;
                        }
                        if ( v20 == 26 || v20 - 2500 <= 1 )
                          goto LABEL_1631;
                      }
LABEL_1634:
                      v570 = a5;
                      Text = CEditRouter::ExecEditCommand(
                               *(CEditRouter **)&String1.vt,
                               v572,
                               v582,
                               a5,
                               v7,
                               a7,
                               v586,
                               (struct CMarkup *)v586,
                               (struct CDoc *)this);
                      if ( v573 == CMarkup::GetEditContext((CMarkup *)v586) )
                        *((_DWORD *)v573 + 10) &= 0xFFFFF3FF;
                      CDoc::CDOMTextInputScope::~CDOMTextInputScope((CDoc::CDOMTextInputScope *)&v609);
LABEL_1638:
                      if ( Text == -2147221248 )
                      {
LABEL_1642:
                        if ( CDoc::EntityHasFocus((CDoc *)this) )
                        {
                          FocusedEntity = CDoc::GetFocusedEntity((CDoc *)this);
                          if ( FocusedEntity )
                            Text = CEntity::Exec(FocusedEntity, v584, v582, v570, v7, a7);
                        }
                        goto LABEL_1645;
                      }
                      goto LABEL_1639;
                    }
                  }
                }
LABEL_1637:
                v570 = a5;
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
                           v582,
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
                    v364 = (unsigned int)CTQueryStatus(
                                           *((struct IUnknown **)v59 + 10),
                                           0,
                                           1u,
                                           (struct _tagOLECMD *const)&ppvData,
                                           0) == 0;
                    v61 = bstrString;
                    if ( v364 && HIDWORD(ppvData) == 3 )
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
                  v62 = *((_QWORD *)v578 + 7);
                  if ( v62 )
                    v63 = *(struct CMarkup **)(v62 + 104);
                  else
                    v63 = (struct CMarkup *)*((_QWORD *)v578 + 6);
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
                         v584,
                         v582,
                         a5,
                         a6,
                         a7);
                goto LABEL_118;
              }
LABEL_1653:
              _report_securityfailure(1, v27);
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
                    v64 = CDocument::Markup(v578);
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
                inserted = CDoc::SetDesignMode((CDoc *)this, v578, v72);
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
                      v106 = (wchar_t *)&Source;
                      v364 = *((_BYTE *)v105 + 56) == 0;
                      Buffer = 0;
                      if ( v364 )
                        v106 = L"\\Scripts";
                      LODWORD(v578) = 12;
                      ppvData = v106;
                      v107 = -1;
                      do
                        ++v107;
                      while ( *(_WORD *)(*((_QWORD *)v105 + 184) + 2 * v107) );
                      if ( (int)UIntAdd(0xCu, v107, (unsigned int *)&v578) < 0 )
                        goto LABEL_273;
                      if ( (int)UIntAdd((unsigned int)v578, 0xEu, (unsigned int *)&v578) < 0 )
                        goto LABEL_273;
                      v108 = -1;
                      do
                        ++v108;
                      while ( *((_WORD *)ppvData + v108) );
                      if ( (int)UIntAdd((unsigned int)v578, v108, (unsigned int *)&v578) < 0 )
                        goto LABEL_273;
                      v109 = 2LL * (unsigned int)v578;
                      if ( !is_mul_ok((unsigned int)v578, 2u) )
                        v109 = -1;
                      pszSubKey = (LPCWSTR)operator new[](v109, (const struct MemoryProtection::leaf_t *)&leaf);
                      if ( pszSubKey )
                      {
                        v110 = this[126];
                        BufferCount = 0;
                        StringCchPrintfExW(
                          (wchar_t *)pszSubKey,
                          (unsigned int)v578,
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
                                if ( (int)StringCchPrintfW((unsigned __int16 *)v610, 0x10u, L"%d", v124) >= 0 )
                                {
                                  SetBinaryExt(
                                    SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizeExt[0],
                                    2,
                                    (unsigned int)v610,
                                    (unsigned int)&pvData,
                                    4);
                                  if ( LOBYTE(pvt[0]) )
                                    SetBinaryExt(
                                      SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizePrivateExt[0],
                                      2,
                                      (unsigned int)v610,
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
                          v7 = *(VARIANTARG **)&v609.vt;
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
              COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v610);
              v136 = v582;
              *(_QWORD *)v610 = v584;
              *(_DWORD *)&v610[8] = v582;
              CNotification::CNotification((CNotification *)&v591);
              v137 = CDoc::PrimaryRoot((CDoc *)this);
              CNotification::Command((CNotification *)&v591, v137, v610, 0);
              CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
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
            CDoc::ShowMessage((CDoc *)this, &v605, 0, 0, 0x5EDu, lpcbData, 0, 10570, 1001, &Source, &Source);
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
                       v584,
                       v582,
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
                       v584,
                       v582,
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
          v145 = *((_QWORD *)v578 + 7);
          if ( v145 )
            v141 = *(struct CMarkup **)(v145 + 104);
          else
            v141 = (struct CMarkup *)*((_QWORD *)v578 + 6);
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
                  memset(&v609, 0, sizeof(v609));
                  VariantInit(&v609);
                  v165 = 0;
                  pvData = ConvertSBCMDID(plLbound[0]);
                  plLbound[0] = 0;
                  if ( v20 == 2135 )
                  {
                    v609.vt = 3;
                    v609.lVal = 1;
LABEL_361:
                    v165 = &v609;
LABEL_362:
                    v171 = this[12];
                    if ( v171 )
                    {
                      v172 = (__int64 (__fastcall ***)(_QWORD, GUID *, BSTR *))*((_QWORD *)v171 + 10);
                      bstrString = 0;
                      if ( v172 )
                      {
                        v173 = (**v172)(v172, &IID_IOleCommandTarget, &bstrString);
                        v166 = 0;
                        Text = v173;
                        if ( !v173 )
                        {
                          Text = (*(__int64 (__fastcall **)(BSTR, const GUID *, _QWORD, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)bstrString + 32LL))(
                                   bstrString,
                                   &CGID_Explorer,
                                   pvData,
                                   (unsigned int)plLbound[0],
                                   v165,
                                   0);
                          (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                        }
                      }
                      else
                      {
                        Text = -2147467259;
                      }
                    }
                    if ( v609.vt == 13 && v609.llVal )
                      (*(void (__fastcall **)(LONGLONG, __int64))(*v609.pllVal + 16))(v609.llVal, v166);
                    goto LABEL_230;
                  }
                  if ( v20 != 2266 )
                  {
                    v609.vt = 3;
                    v170 = 6;
                    if ( v20 != 2130 )
                      v170 = 1;
                    v609.lVal = v170 | 0x20000;
                    goto LABEL_361;
                  }
                  v167 = this[544];
                  bstrString = 0;
                  Text = GetExecDocument((struct CDocument **)&bstrString, v167, v578);
                  if ( Text < 0 )
                    goto LABEL_1650;
                  if ( bstrString )
                  {
                    v168 = *((_QWORD *)bstrString + 7);
                    if ( v168 )
                      v169 = *(CMarkup **)(v168 + 104);
                    else
                      v169 = (CMarkup *)*((_QWORD *)bstrString + 6);
                    if ( !(unsigned int)CMarkup::IsPrimaryMarkup(v169) )
                    {
                      v609.vt = 13;
                      Text = CDocument::QueryInterface((CDocument *)bstrString, &IID_IUnknown, &v609.byref);
                      if ( Text )
                        goto LABEL_1650;
                      v165 = &v609;
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
                      _report_securityfailure(1, v164);
                    Text = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(**(_QWORD **)&String1.vt + 368LL))(
                             *(_QWORD *)&String1.vt,
                             v584,
                             v582,
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
                  v146 = *((_QWORD *)v578 + 7);
                  if ( v146 )
                    v147 = *(CMarkup **)(v146 + 104);
                  else
                    v147 = (CMarkup *)*((_QWORD *)v578 + 6);
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
                v149 = v578;
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
            v320 = 0;
            if ( plLbound[0] == 2300 && a6 && a6->vt == 3 )
              v320 = (a6->lVal & 0x7FF0000) != 0;
            v321 = this[540];
            if ( v321 )
              Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v321 + 32LL))(
                       v321,
                       &CGID_DocHostCommandHandler,
                       (unsigned int)plLbound[0],
                       a5,
                       a6,
                       a7);
            if ( Text >= 0 )
              goto LABEL_1582;
            if ( ((plLbound[0] - 6041) & 0xFFFFFFFD) != 0 && !v320 )
            {
              v322 = this[544];
              v323 = v322 ? CElement::GetMarkupPtr(v322) : CDocument::Markup(v578);
              if ( v323 )
              {
                v324 = CMarkup::GetFrameOrPrimaryMarkup(v323, 1);
                if ( v324 )
                  CMarkup::Window(v324);
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
                  CNotification::CNotification((CNotification *)&v591);
                  v364 = ((_DWORD)this[608] & 0x80000) == 0;
                  *((_DWORD *)this + 1215) ^= ((unsigned __int8)*((_DWORD *)this + 1215)
                                             ^ (unsigned __int8)(16 * lVal))
                                            & 0x10;
                  if ( !v364 )
                  {
                    v182 = *((_DWORD *)this + 45);
                    v183 = CDoc::PrimaryRoot((CDoc *)this);
                    CNotification::EnableInteraction1((CNotification *)&v591, v183, 0);
                    CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
                    if ( !v182 )
                    {
                      if ( *((_DWORD *)this + 45) )
                        *((_DWORD *)this + 45) = 0;
                    }
                  }
                  v184 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + (unsigned int)tls_index)
                                               + 16LL)
                                   + 208LL);
                  if ( v184 )
                    CImgAnim::SetAnimState(v184, this, lVal == 0);
                }
                goto LABEL_53;
              }
              goto LABEL_131;
            case 2310:
              v179 = CDoc::PrimaryMarkup((CDoc *)this);
              ScriptCollection = CMarkup::GetScriptCollection(v179, 1);
              if ( ScriptCollection )
              {
                inserted = CScriptCollection::ViewSourceInDebugger(ScriptCollection, 0, 0);
                goto LABEL_306;
              }
              break;
            case 2311:
              v177 = this[809];
              if ( v177 && CPeerFactoryUrl::GetUrl(v177) )
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
              *(GUID *)&v609.vt = CGID_MSHTML;
              CDoc::Exec((CDoc *)this, (const struct _GUID *)&v609, 0x90Eu, 0, a6, 0);
              goto LABEL_53;
            case 2317:
              v176 = 0;
LABEL_380:
              inserted = CDoc::OnSettingsChange((CDoc *)this, v176, 0);
              goto LABEL_306;
            default:
              if ( (unsigned int)(plLbound[0] - 2320) > 1 )
                goto LABEL_231;
LABEL_376:
              CVariant::CVariant((CVariant *)&pvarg);
              v174 = CDocument::Markup(v578);
              GlyphTable = CMarkup::GetGlyphTable(v174);
              if ( a6 )
              {
                if ( a6->vt != 11 )
                {
LABEL_378:
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_231;
                }
                v202 = a6->iVal != 0;
LABEL_477:
                if ( !v202 && (plLbound[0] == 2327 || plLbound[0] == 2320) )
                  v20 = 2336;
                v204 = CDocument::Markup(v578);
                Text = CMarkup::EnsureGlyphTableExistsAndExecute(v204, v584, v20, a5, v7, a7);
                if ( !Text )
                {
                  if ( v20 != 2336 )
                  {
                    if ( ((((v205 = CDocument::Markup(v578), v206 = CMarkup::GetGlyphTable(v205), v20 == 2327)
                         || v20 == 2321)
                        && (*(_DWORD *)v206 ^= (*(_DWORD *)v206 ^ v202) & 1, v20 == 2327)
                        || v20 == 2322)
                       && (*(_DWORD *)v206 ^= (*(_DWORD *)v206 ^ (2 * v202)) & 2, v20 == 2327)
                       || v20 == 2323)
                      && (*(_DWORD *)v206 &= ~8u, *(_DWORD *)v206 |= 8 * v202, v20 == 2327)
                      || v20 == 2324 )
                    {
                      *(_DWORD *)v206 &= ~4u;
                      *(_DWORD *)v206 |= 4 * v202;
                      if ( v20 == 2327 )
                        goto LABEL_1659;
                    }
                    if ( v20 == 2325 )
                    {
LABEL_1659:
                      *(_DWORD *)v206 &= ~0x10u;
                      *(_DWORD *)v206 |= 16 * v202;
                      if ( v20 == 2327 )
                        goto LABEL_1658;
                    }
                    if ( v20 == 2320 )
                    {
LABEL_1658:
                      *(_DWORD *)v206 &= ~0x40u;
                      *(_DWORD *)v206 |= v202 << 6;
                      if ( v20 == 2327 )
                        goto LABEL_1657;
                    }
                    if ( v20 == 2326 )
                    {
LABEL_1657:
                      *(_DWORD *)v206 ^= (*(_DWORD *)v206 ^ (32 * v202)) & 0x20;
                      if ( v20 == 2327 )
                        goto LABEL_499;
                    }
                    if ( v20 == 2340 )
LABEL_499:
                      *(_DWORD *)v206 ^= (*(_DWORD *)v206 ^ (v202 << 7)) & 0x80;
                  }
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_1582;
                }
                goto LABEL_378;
              }
              if ( GlyphTable )
              {
                v202 = 0;
                if ( plLbound[0] != 2320 )
                {
                  if ( plLbound[0] == 2321 )
                  {
                    v203 = *(_DWORD *)GlyphTable;
                  }
                  else if ( plLbound[0] == 2322 )
                  {
                    v203 = *(_DWORD *)GlyphTable >> 1;
                  }
                  else if ( plLbound[0] == 2323 )
                  {
                    v203 = *(_DWORD *)GlyphTable >> 3;
                  }
                  else if ( plLbound[0] == 2324 )
                  {
                    v203 = *(_DWORD *)GlyphTable >> 2;
                  }
                  else if ( plLbound[0] == 2325 )
                  {
                    v203 = *(_DWORD *)GlyphTable >> 4;
                  }
                  else
                  {
                    if ( plLbound[0] != 2326 )
                    {
                      if ( plLbound[0] == 2327 )
                      {
                        LOBYTE(v202) = *(_BYTE *)GlyphTable != 0xFF;
                      }
                      else if ( plLbound[0] == 2340 )
                      {
                        v202 = (*(_DWORD *)GlyphTable & 0x80) == 0;
                      }
LABEL_472:
                      pvarg.vt = 11;
                      if ( !v202 )
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
                    v203 = *(_DWORD *)GlyphTable >> 5;
                  }
                  v202 = (v203 & 1) == 0;
                  goto LABEL_472;
                }
                if ( (*(_BYTE *)GlyphTable & 0x40) != 0 )
                  goto LABEL_472;
              }
              v202 = 1;
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
              v187 = CDocument::Markup(v578);
              inserted = CMarkup::EnsureGlyphTableExistsAndExecute(v187, v584, plLbound[0], a5, a6, a7);
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
              v185 = CDocument::Markup(v578);
              DwnDoc = CMarkup::GetDwnDoc(v185);
              a7->vt = 3;
              if ( DwnDoc )
                LODWORD(DwnDoc) = CDwnDoc::GetBytesRead(DwnDoc);
              a7->lVal = (int)DwnDoc;
              goto LABEL_231;
            }
            goto LABEL_330;
          }
LABEL_420:
          v188 = CDocument::Markup(v578);
          v189 = v188;
          if ( a6 && a6->vt == 11 )
            v190 = a6->bVal != 0;
          else
            v190 = !CMarkup::IsShowZeroBorderAtDesignTime(v188);
          if ( plLbound[0] == 2328 )
          {
            CMarkup::SetShowZeroBorderAtDesignTime(v189, v190);
            CNotification::CNotification((CNotification *)&v591);
            ElementTopHelper = CMarkup::GetElementTopHelper(v189);
            CNotification::ZeroGrayChange((CNotification *)&v591, ElementTopHelper);
            CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
            CDoc::Invalidate((CDoc *)this);
          }
          else
          {
            *((_DWORD *)this + 1216) &= ~0x10u;
            *((_DWORD *)this + 1216) |= 16 * v190;
          }
          Text = 0;
          *((_DWORD *)this[126] + 23) = *CDoc::_dwMiscFlags((CDoc *)this);
          TopLayoutElement = CMarkup::GetTopLayoutElement(v189);
          if ( TopLayoutElement )
            CElement::ResizeElement(TopLayoutElement, 0x800000u);
          COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v610);
          *(_QWORD *)v610 = v584;
          *(_DWORD *)&v610[8] = v582;
          CNotification::CNotification((CNotification *)&v591);
          if ( v20 == 2328 )
            v193 = CMarkup::Root(v189);
          else
            v193 = CDoc::PrimaryRoot((CDoc *)this);
          CNotification::Command((CNotification *)&v591, v193, v610, 0);
          CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
          goto LABEL_1647;
        }
        if ( a6 && a6->vt == 11 )
        {
          bVal = a6->bVal;
          v195 = *((_DWORD *)this + 1428);
          if ( plLbound[0] == 2332 )
          {
            v196 = bVal != 0 ? 0x100 : 0;
            v197 = v195 & 0xFFFFFEFF;
          }
          else if ( plLbound[0] == 2333 )
          {
            v196 = bVal != 0 ? 0x200 : 0;
            v197 = v195 & 0xFFFFFDFF;
          }
          else
          {
            v196 = bVal != 0 ? 0x400 : 0;
            v197 = v195 & 0xFFFFFBFF;
          }
          *((_DWORD *)this + 1428) = v197 | v196;
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
                         v578,
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
                      v296 = (struct IUnknown *)bstrString;
                      a7->vt = 8;
                      Text = CDiagnosticsDom::GetDiagnosticsUniqueId(v296, &a7->bstrVal);
                    }
                    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                  }
                  else if ( a7 )
                  {
                    a7->vt = 3;
                    a7->lVal = 1;
                  }
                }
                CDispClient::AdjustContentSize((CDispClient *)&ppvData, v294, v295);
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
                        v216 = CDocument::Markup(v578);
                        v217 = CMarkup::Window(v216);
                        v218 = COptionsHolder::SecurityContext(v217);
                        inserted = ShowModalDialogHelper(
                                     v216,
                                     a6->bstrVal,
                                     (struct IDispatch *)(((unsigned __int64)v218 + 48) & -(__int64)(v218 != 0)),
                                     0,
                                     0,
                                     0x4000010u);
                        goto LABEL_306;
                      }
                      break;
                    case 2350:
                    case 2351:
                      *(_QWORD *)&String1.vt = 0;
                      v215 = CBase::OpenParentUnit((CBase *)this, (struct CBase *)this, 0x8D6u, 0);
                      Text = GetExecDocument((struct CDocument **)&String1, this[544], v578);
                      if ( Text >= 0 )
                        Text = CDocument::SetDocDirection(
                                 *(CDocument **)&String1.vt,
                                 (unsigned int)(plLbound[0] != 2350) + 1);
                      CBase::CloseParentUnit((CBase *)this, v215, Text);
                      goto LABEL_231;
                    case 2370:
                      if ( a6 )
                      {
                        if ( a6->vt == 8 )
                        {
                          v213 = a6->bstrVal;
                          if ( v213 )
                          {
                            v214 = CDocument::Markup(v578);
                            inserted = CDoc::SavePretransformedSource((CDoc *)this, v214, v213);
                            goto LABEL_306;
                          }
                        }
                      }
                      break;
                    case 2371:
LABEL_514:
                      v207 = this[544];
                      if ( v207 )
                        v208 = CElement::GetMarkupPtr(v207);
                      else
                        v208 = CDocument::Markup(v578);
                      if ( !v208
                        || (v209 = CMarkup::GetFrameOrPrimaryMarkup(v208, 1), (v210 = v209) == 0)
                        || (unsigned int)CMarkup::IsImageFile(v209) )
                      {
                        Text = 0;
                        goto LABEL_1582;
                      }
                      if ( plLbound[0] != 2139
                        || !(unsigned int)CMarkup::IsPrimaryMarkup(v210)
                        || !(unsigned int)CDoc::IsAggregatedByXMLMime((CDoc *)this) )
                      {
                        Text = CDoc::GetViewSourceFileName((CDoc *)this, psz, 0x823u, v210);
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
                      v211 = CDOMStringMap::SecurityContext((CDOMStringMap *)this);
                      if ( (**(unsigned int (__fastcall ***)(struct CSecurityContext *, GUID *, BSTR *))v211)(
                             v211,
                             &IID_IOleCommandTarget,
                             &bstrString)
                        || !bstrString )
                      {
                        goto LABEL_231;
                      }
                      (*(void (__fastcall **)(BSTR, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)bstrString + 32LL))(
                        bstrString,
                        v584,
                        v582,
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
              v219 = 0;
              v220 = a6->lVal;
              plLbound[0] = 0;
              if ( v220 )
              {
                v221 = v220 - 1;
                if ( v221 )
                {
                  if ( v221 == 1 )
                  {
                    v222 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                    if ( v222 )
                    {
                      v223 = *((_QWORD *)v578 + 7);
                      v224 = v223 ? *(_QWORD *)(v223 + 104) : *((_QWORD *)v578 + 6);
                      v219 = CIPrintCollection::CIPrintCollection(v222, *(struct CSecurityContext **)(v224 + 320));
                      if ( v219 )
                      {
                        v225 = *((_QWORD *)v578 + 7);
                        if ( v225 )
                          v226 = *(CMarkup **)(v225 + 104);
                        else
                          v226 = (CMarkup *)*((_QWORD *)v578 + 6);
                        if ( v226 )
                        {
                          v227 = CMarkup::EnsureTopElems(v226);
                          if ( v227 )
                          {
                            v228 = *((_QWORD *)v227 + 4);
                            if ( v228 )
                            {
                              if ( *(_WORD *)(v228 + 56) == 47 )
                              {
                                v592 = *(_QWORD *)(v228 + 48);
                                v597 = 0;
                                v598 = 0;
                                v594 = 0;
                                v591 = 88;
                                v596 = v219;
                                v595 = 18436;
                                v593 = 0;
                                CNotification::SetElement((CNotification *)&v591, (struct CElement *)v228);
                                CMarkup::Notify(v226, (struct CNotification *)&v591, 0);
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
                  v242 = (CIPrintCollection *)((char *)v219 + 48);
                  if ( !(unsigned int)CIPrintCollection::get_length((CIPrintCollection *)((char *)v219 + 48), plLbound)
                    && plLbound[0] > 0 )
                  {
                    COMRect::AddRef((CIPrintCollection *)((char *)v219 + 48));
                    a7->vt = 13;
                    a7->llVal = (unsigned __int64)v242 & -(__int64)(v219 != 0);
                  }
                  CAutoRange::Release(v242);
                  Text = 0;
                  goto LABEL_1649;
                }
                if ( !CDoc::GetActiveElement((CDoc *)this) )
                  goto LABEL_600;
                v229 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                if ( !v229 )
                  goto LABEL_895;
                v230 = CDoc::GetActiveElement((CDoc *)this);
                v231 = CElement::GetMarkupPtr(v230);
                v219 = CIPrintCollection::CIPrintCollection(v229, *((struct CSecurityContext **)v231 + 40));
                if ( !v219 )
                  goto LABEL_895;
                v232 = CDoc::GetActiveElement((CDoc *)this);
                v233 = (CTreePos *)*((_QWORD *)CElement::GetMarkupPtr(v232) + 68);
                v234 = v233 ? *(_QWORD *)CTreePos::Branch(v233) : 0LL;
                if ( (*(_DWORD *)(v234 + 60) & 0x200) == 0 )
                  goto LABEL_600;
                LookasidePtr2 = CElement::GetLookasidePtr2(v234, 0);
                if ( *(_WORD *)(LookasidePtr2 + 56) != 46 && *(_WORD *)(LookasidePtr2 + 56) != 60 )
                  goto LABEL_600;
                bstrString = 0;
                if ( !(unsigned int)CFrameContentHelper::GetPrintObject(
                                      (CFrameContentHelper *)(LookasidePtr2 + 96),
                                      (struct IPrint **)&bstrString) )
                {
                  *(_QWORD *)&String1.vt = bstrString;
                  if ( !(unsigned int)CImplAry::AppendIndirect<8>((char *)v219 + 56, &String1, 0) )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&String1.vt + 8LL))(*(_QWORD *)&String1.vt);
                }
                v236 = bstrString;
              }
              else
              {
                v237 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                if ( !v237 )
                  goto LABEL_895;
                v238 = *((_QWORD *)v578 + 7);
                v239 = v238 ? *(_QWORD *)(v238 + 104) : *((_QWORD *)v578 + 6);
                v219 = CIPrintCollection::CIPrintCollection(v237, *(struct CSecurityContext **)(v239 + 320));
                if ( !v219 )
                  goto LABEL_895;
                v240 = CDocument::Window(v578);
                if ( !v240 )
                  goto LABEL_600;
                v241 = (struct IUnknown *)*((_QWORD *)v240 + 43);
                if ( !v241 )
                  goto LABEL_600;
                bstrString = 0;
                ppvData = 0;
                if ( !(unsigned int)GetWebOCDocument(v241, (struct IDispatch **)&bstrString) )
                  (**(void (__fastcall ***)(BSTR, GUID *, void **))bstrString)(bstrString, &IID_IPrint, &ppvData);
                if ( ppvData )
                {
                  *(_QWORD *)&String1.vt = ppvData;
                  if ( !(unsigned int)CImplAry::AppendIndirect<8>((char *)v219 + 56, &String1, 0) )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&String1.vt + 8LL))(*(_QWORD *)&String1.vt);
                }
                if ( bstrString )
                  (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                v236 = ppvData;
              }
              if ( v236 )
                (*(void (__fastcall **)(void *))(*(_QWORD *)v236 + 16LL))(v236);
              goto LABEL_600;
            }
            if ( plLbound[0] == 2405 )
            {
              v256 = *((_QWORD *)v578 + 7);
              if ( v256 )
                v257 = *(CMarkup **)(v256 + 104);
              else
                v257 = (CMarkup *)*((_QWORD *)v578 + 6);
              if ( a6 && a6->vt == 11 )
              {
                v258 = *((_DWORD *)v257 + 187);
                v259 = -(a6->bVal != 0);
              }
              else
              {
                v258 = *((_DWORD *)v257 + 187);
                LOWORD(v259) = ~(_WORD)v258;
              }
              *((_DWORD *)v257 + 187) = v258 & 0xFFFFBFFF | v259 & 0x4000;
              if ( v257 == CDoc::PrimaryMarkup((CDoc *)this) )
                CDoc::ForceRelayout((CDoc *)this, 0);
              else
                CMarkup::ForceRelayout(v257, 0);
              goto LABEL_53;
            }
            if ( plLbound[0] == 2408 )
            {
              if ( a6 && a6->vt == 3 )
              {
                if ( *((char *)this + 4868) >= 0 && !(unsigned __int8)IEConfiguration_GetBool(268435481) )
                {
                  v250 = this[8];
                  Text = 0;
                  if ( v250 )
                  {
                    bstrString = 0;
                    v251 = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, BSTR *))v250)(
                             v250,
                             &IID_IOleCommandTarget,
                             &bstrString);
                    v252 = (struct IUnknown *)bstrString;
                    Text = v251;
                    if ( !v251 && bstrString )
                    {
                      v253 = (*(__int64 (__fastcall **)(BSTR, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, _QWORD))(*(_QWORD *)bstrString + 32LL))(
                               bstrString,
                               &CGID_DocHostCommandHandler,
                               (unsigned int)(v251 + 48),
                               0,
                               a6,
                               0);
                      v252 = (struct IUnknown *)bstrString;
                      Text = v253;
                    }
                    ReleaseInterface(v252);
                  }
                }
                if ( !a6->lVal )
                {
                  v364 = (*((_DWORD *)this + 1237))-- == 1;
                  if ( v364 && (*((_DWORD *)this + 1217) & 0x4000) != 0 )
                  {
                    v254 = v578;
                    if ( v578 )
                    {
                      if ( CDocument::Window(v578) )
                      {
                        *((_DWORD *)this + 1217) &= ~0x4000u;
                        v255 = CDocument::Window(v254);
                        CWindow::close((struct CWindow *)((char *)v255 + 48));
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
                  v246 = CDocument::Markup(v578);
                  v247 = v246;
                  if ( a6 && a6->vt == 11 )
                  {
                    v25 = a6->bVal != 0;
                  }
                  else if ( (unsigned int)CMarkup::HasEditContext(v246)
                         && (*((_BYTE *)CMarkup::GetEditContext(v247) + 40) & 2) != 0 )
                  {
                    v25 = 0;
                  }
                  if ( CMarkup::EnsureEditContext(v247) )
                  {
                    v248 = CMarkup::GetEditContext(v247);
                    *((_DWORD *)v248 + 10) &= ~2u;
                    *((_DWORD *)v248 + 10) |= 2 * v25;
                  }
                  goto LABEL_53;
                case 2423:
                  *((_DWORD *)this + 1217) = *((_DWORD *)this + 1217) & 0xFEFFFFFF
                                           | ~*((_DWORD *)this + 1217) & 0x1000000;
                  goto LABEL_53;
                case 2425:
                  if ( a6 && a6->vt == 11 )
                    v245 = a6->bVal != 0;
                  else
                    v245 = ((*((_DWORD *)this + 1217) >> 25) & 1) == 0;
                  *((_DWORD *)this + 1217) &= ~0x2000000u;
                  *((_DWORD *)this + 1217) |= v245 << 25;
                  goto LABEL_53;
              }
              if ( plLbound[0] != 2430 )
                goto LABEL_231;
              if ( a6 && a6->vt == 11 )
              {
                v243 = a6->bVal != 0 ? 0x4000000 : 0;
                v244 = *((_DWORD *)this + 1217) & 0xFBFFFFFF;
                goto LABEL_614;
              }
LABEL_131:
              Text = -2147024809;
              goto LABEL_1650;
            }
            v249 = CDocument::Markup(v578);
            if ( !(unsigned int)CMarkup::IsConnectedToPrimaryMarkup(v249) )
            {
              CMarkup::TearDownMarkup(v249, 1, 0);
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
              v273 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&String1.vt = v273;
              if ( !v273 || !a6 || a6->vt != 8 )
                goto LABEL_1647;
              if ( CMarkup::GetStyleState(v273) )
              {
                StyleState = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                CStr::~CStr((struct CMarkupStyleState *)((char *)StyleState + 8));
                v275 = *(CMarkup **)&String1.vt;
                v276 = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                if ( !(unsigned int)CStr::IsNull(v276) )
                {
                  v277 = CMarkup::GetStyleState(v275);
                  if ( (unsigned int)CStr::IsNull(v277) )
                    goto LABEL_1647;
                  v278 = CMarkup::GetStyleState(v275);
                  v279 = CDispSurface::UseRenderTarget(v278);
                  v280 = a6;
                  v281 = v279 - (struct IDispRenderTarget *)a6;
                  do
                  {
                    v282 = *(unsigned __int16 *)((char *)&v280->vt + v281);
                    v283 = v280->vt - v282;
                    if ( v283 )
                      break;
                    v280 = (struct tagVARIANT *)((char *)v280 + 2);
                  }
                  while ( v282 );
                  if ( !v283 )
                    goto LABEL_1647;
                }
                v284 = CMarkup::GetStyleState(v275);
                inserted = CStr::SetBSTR((struct CMarkupStyleState *)((char *)v284 + 8), a6->bstrVal);
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
                v272 = a6->bVal;
                if ( (v272 == 0) == (((*((_DWORD *)this + 1215) >> 17) & 1) == 0) )
                  goto LABEL_1647;
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | (v272 != 0 ? 0x20000 : 0);
              }
              else
              {
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | ~*((_DWORD *)this + 1215) & 0x20000;
              }
              CDoc::NotifySelection(this, 17, 0);
              goto LABEL_1647;
            case 2437:
              Text = 0;
              v267 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v609.vt = v267;
              v268 = v267;
              if ( !v267 || !a6 || a6->vt != 11 )
                goto LABEL_1647;
              if ( CMarkup::GetStyleState(v267) )
              {
                CMarkup::CLock::CLock((CMarkup::CLock *)&String1, v268);
                v269 = *(_QWORD *)&v609.vt;
                v270 = a6->bVal != 0;
                *((_BYTE *)CMarkup::GetStyleState(*(CMarkup **)&v609.vt) + 24) = v270;
                if ( *(__int64 (__fastcall **)())(*(_QWORD *)v269 + 984LL) != _vtguard )
                  _report_securityfailure(1, v271);
                Text = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v269 + 224LL))(v269, 3);
                CMarkup::CLock::~CLock((CMarkup::CLock *)&String1);
                goto LABEL_231;
              }
              break;
            case 2438:
              Text = 0;
              v265 = CDoc::PrimaryMarkup((CDoc *)this);
              v266 = v265;
              if ( !v265 || a7->vt != 11 )
                goto LABEL_1647;
              a7->iVal = 0;
              if ( CMarkup::GetStyleState(v265) )
              {
                if ( *((_BYTE *)CMarkup::GetStyleState(v266) + 24) )
                  a7->iVal = -1;
                goto LABEL_1648;
              }
              goto LABEL_895;
            case 2439:
              Text = 0;
              v261 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v609.vt = v261;
              if ( !v261 )
                goto LABEL_1647;
              a7->llVal = 0;
              if ( !CMarkup::GetStyleState(v261) )
              {
                Text = -2147024882;
                goto LABEL_1581;
              }
              if ( a7->vt != 8 )
                goto LABEL_1647;
              v262 = *(CMarkup **)&v609.vt;
              v263 = CMarkup::GetStyleState(*(CMarkup **)&v609.vt);
              if ( (unsigned int)CStr::IsNull(v263) )
                goto LABEL_1648;
              v264 = CMarkup::GetStyleState(v262);
              Text = CStr::AllocBSTR(v264, &a7->bstrVal);
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
            v286 = a6->parray;
            *(_QWORD *)&v609.vt = v286;
            if ( v286 && SafeArrayGetDim(v286) == 1 )
            {
              plLbound[0] = 0;
              pvData = 0;
              pvt[0] = 0;
              Text = SafeArrayGetLBound(v286, 1u, plLbound);
              if ( !Text )
              {
                Text = SafeArrayGetUBound(v286, 1u, (LONG *)&pvData);
                if ( !Text )
                {
                  Text = SafeArrayGetVartype(v286, pvt);
                  if ( !Text )
                    Text = SafeArrayGetVartype(v286, pvt);
                }
              }
              if ( plLbound[0] || (v287 = pvData, pvData > 3) || pvt[0] != 8 )
              {
                Text = -2147024809;
              }
              else
              {
                v288 = *(SAFEARRAY **)&v609.vt;
                v289 = 0;
                v290 = 0;
                memset(v610, 0, sizeof(v610));
                rgIndices[0] = 0;
                do
                {
                  if ( !Text )
                  {
                    Element = SafeArrayGetElement(v288, rgIndices, &v610[8 * v290]);
                    v287 = pvData;
                    Text = Element;
                    v289 = rgIndices[0];
                  }
                  rgIndices[0] = ++v289;
                  v290 = v289;
                }
                while ( v289 <= v287 );
                if ( !Text )
                {
                  v292 = (struct IUnknown **)TSmartPointer<ID3D11Device>::operator&(&bstrString);
                  Text = CDoc::InitializeDiagnosticsMode(
                           (CDoc *)this,
                           *(const unsigned __int16 **)v610,
                           *(const unsigned __int16 **)&v610[8],
                           *(const unsigned __int16 **)&v610[16],
                           *(const unsigned __int16 **)&v610[24],
                           v292);
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
              v285 = a6->punkVal;
              if ( v285 )
              {
                if ( a7 )
                {
                  plLbound[0] = 0;
                  Text = CDebugCallbackNotificationHandlers::AddCallbackNotificationHandler(
                           (CDebugCallbackNotificationHandlers *)(this + 812),
                           v285,
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
                v313 = this[103];
                if ( v313 )
                {
                  v314 = COmWindowProxy::Markup(v313);
                  Text = CMarkup::GetFrameZone(v314, a7, 0);
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
              v308 = CDoc::PrimaryMarkup((CDoc *)this);
              v309 = CMarkup::GetCodePage(v308);
              v310 = this[544];
              v311 = v309;
              plLbound[0] = 0;
              *(_QWORD *)&String1.vt = 0;
              Text = GetExecDocument((struct CDocument **)&String1, v310, v578);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
              v98 = Text < 0;
              if ( !Text )
              {
                v312 = CDoc::IsCpAutoDetect((CDoc *)this);
                Text = ShowMimeCSetMenu(this[126], (int *)&pvData, v311, a6->lVal, plLbound[0], v312);
                if ( !Text )
                {
                  v20 = pvData;
                  if ( pvData - 3609 > 0x5A )
                  {
                    if ( pvData - 2350 <= 1 )
                      CDoc::ExecHelper((CDoc *)this, v578, &CGID_MSHTML, pvData, 0, 0, 0);
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
                  v306 = a6->bstrVal;
                  if ( v306 )
                  {
                    v307 = CDocument::Markup(v578);
                    inserted = CDoc::SetUrl((CDoc *)this, v307, v306, 0);
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
              v305 = CDoc::PrimaryMarkup((CDoc *)this);
              NormZoomPercent = CMarkup::GetCodePage(v305);
              if ( plLbound[0] == 6034 )
                NormZoomPercent = WindowsCodePageFromCodePage(NormZoomPercent);
              a7->vt = 3;
              break;
            case 6036:
              if ( !a7 )
                goto LABEL_756;
              v297 = v578;
              a7->vt = 37;
              v298 = this[544];
              plLbound[0] = 0;
              bstrString = 0;
              Text = GetExecDocument((struct CDocument **)&bstrString, v298, v297);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection((CDocument *)bstrString, plLbound);
              v98 = Text < 0;
              if ( !Text )
              {
                v299 = CDocument::Markup((CDocument *)bstrString);
                v300 = CDoc::IsCpAutoDetect((CDoc *)this);
                v301 = plLbound[0];
                v302 = v300;
                v303 = CMarkup::GetCodePage(v299);
                EncodingMenu = GetEncodingMenu(this[126], v303, v301, v302);
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
              v511 = a5;
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
        v315 = 3;
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
                CNotification::CNotification((CNotification *)&v591);
                v316 = CDoc::PrimaryMarkup((CDoc *)this);
                v317 = CMarkup::GetElementTopHelper(v316);
                CNotification::EditModeChange((CNotification *)&v591, v317, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
              }
            }
            if ( a7 )
            {
              a7->vt = 8;
              DefaultBlockTag = CDoc::GetDefaultBlockTag(this, v27, v315, v26);
              v319 = L"DIV";
              if ( DefaultBlockTag != 34 )
                v319 = L"P";
              a7->llVal = (LONGLONG)SysAllocString(v319);
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
              *(_OWORD *)&v609.vt = 0;
              CNotification::CNotification((CNotification *)&v591);
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
              v339 = v578;
              v340 = (struct INamedPropertyBag *)bstrString;
              v341 = CDocument::Markup(v578);
              Text = CDoc::PersistFavoritesData((CDoc *)this, v341, v340, L"DEFAULT");
              if ( Text )
              {
                ReleaseInterface((struct IUnknown *)bstrString);
                goto LABEL_230;
              }
              *(_QWORD *)&v609.vt = bstrString;
              v609.llVal = (LONGLONG)SysAllocString(L"DOC");
              if ( v609.llVal )
              {
                v342 = CDocument::Markup(v339);
                v343 = CMarkup::Root(v342);
                CNotification::FavoritesSave((CNotification *)&v591, v343, &v609, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
                ClearInterface<INamedPropertyBag *>(&v609);
                SysFreeString(v609.bstrVal);
                goto LABEL_1647;
              }
              ReleaseInterface((struct IUnknown *)bstrString);
              goto LABEL_895;
            case 6051:
              Text = 0;
              if ( a7 )
              {
                v333 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v334 = (__int16 *)this + 2861;
                if ( !v333 )
                  v334 = (__int16 *)(this + 715);
                v335 = *v334;
                a7->vt = 3;
                FontSizeMenu = GetFontSizeMenu(v335);
                v337 = HandleToLong(FontSizeMenu);
                a7->lVal = v337;
                LOBYTE(Text) = v337 == 0;
                goto LABEL_231;
              }
              goto LABEL_756;
            case 6052:
              if ( a6 )
              {
                plLbound[0] = 0;
                v331 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v332 = (__int16 *)this + 2861;
                if ( !v331 )
                  v332 = (__int16 *)(this + 715);
                Text = ShowFontSizeMenu(plLbound, *v332, a6->lVal);
                if ( !Text )
                {
                  if ( (unsigned int)(plLbound[0] - 2141) <= 4 )
                    CDoc::ExecHelper((CDoc *)this, v578, &CGID_MSHTML, plLbound[0], 0, 0, 0);
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
            v326 = this[544];
            plLbound[0] = 0;
            *(_QWORD *)&String1.vt = 0;
            if ( GetExecDocument((struct CDocument **)&String1, v326, v578) >= 0 )
              CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
            v327 = plLbound[0];
            a7->vt = 3;
            DocDirMenu = CreateDocDirMenu(v327, 0);
            v329 = HandleToLong(DocDirMenu);
            a7->lVal = v329;
            v330 = -2147221247;
LABEL_1318:
            Text = v329 == 0 ? v330 : 0;
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
        v344 = this[103];
        if ( !v344 )
          goto LABEL_350;
        *(_QWORD *)&String1.vt = 0;
        v345 = COmWindowProxy::Document(v344);
        Text = CDocument::ExtractContent(v345, (struct IReadingModeExtractedContent **)&String1);
        if ( Text < 0 )
          goto LABEL_1581;
        v346 = *(BSTR *)&String1.vt;
        a7->vt = 13;
LABEL_902:
        a7->llVal = (LONGLONG)v346;
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
          v350 = (ReadingMode::CTextClusterDetector *)operator new[](
                                                        0x40u,
                                                        (const struct MemoryProtection::leaf_t *)0x8FC);
          if ( v350 )
          {
            v351 = (ReadingMode::CTextClusterDetector *)ReadingMode::CTextClusterDetector::CTextClusterDetector(
                                                          v350,
                                                          (struct CDoc *)this);
            v352 = v351;
            if ( v351 )
            {
              a7->lVal = ReadingMode::CTextClusterDetector::LengthOfArticleBody(v351);
              ReadingMode::CTextClusterDetector::`scalar deleting destructor'(v352, 1u);
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
          v347 = CDoc::PrimaryMarkup((CDoc *)this);
          CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v347);
          if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
          {
            v348 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
            Text = CPreloadManager::SuspendDuringPrerender(v348, 4);
          }
          CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
        }
        goto LABEL_231;
      }
      if ( !a7 || !a6 || a6->vt != 19 )
        goto LABEL_131;
      a7->vt = 19;
      v349 = CDoc::CheckBFCacheCandidacy(this, a6->cyVal.Lo, 2139, 0xFFFFFFFFLL);
LABEL_922:
      a7->lVal = v349;
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
            v368 = CDoc::InputManager((CDoc *)this);
            v369 = CInputManager::DeferredActionHandler(v368);
            CDeferredActionHandler::AgreeToVTabNavigate(v369, 0);
            goto LABEL_53;
          case 0x17BC:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v370 = CDoc::InputManager((CDoc *)this);
            v371 = CInputManager::DeferredActionHandler(v370);
            CDeferredActionHandler::OnVTabNavigateComplete(v371, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BD:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v372 = CDoc::InputManager((CDoc *)this);
            v373 = CInputManager::DeferredActionHandler(v372);
            CDeferredActionHandler::CancelSpecificVTabNavigate(v373, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BE:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v374 = CDoc::InputManager((CDoc *)this);
            v375 = CInputManager::DeferredActionHandler(v374);
            inserted = CDeferredActionHandler::ValidateVTabNavigate(v375, a6->cyVal.Lo);
            goto LABEL_306;
          case 0x17BF:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v376 = CDoc::InputManager((CDoc *)this);
            v377 = CInputManager::DeferredActionHandler(v376);
            CDeferredActionHandler::OnBeforeUnloadAgreed(v377, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17C0:
            if ( !a6 || a6->vt != 11 )
              goto LABEL_231;
            v378 = a6->iVal;
            Text = 0;
            if ( !v378 && ((_DWORD)this[609] & 0x200000) != 0 )
              goto LABEL_350;
            *((_DWORD *)this + 1219) &= ~0x100000u;
            v379 = 0;
            if ( v378 == -1 )
              v379 = 0x100000;
            *((_DWORD *)this + 1219) |= v379;
            goto LABEL_230;
          case 0x17C1:
            Text = -2147467259;
            v365 = CDoc::PrimaryMarkup((CDoc *)this);
            v366 = v365;
            if ( !v365 || !(unsigned int)BindCtx_ContainsObject(*((_QWORD *)v365 + 183), L"IE_FLAG_HAS_SCROLL_POSITION") )
              goto LABEL_1650;
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v366 + 183) + 96LL))(
              *((_QWORD *)v366 + 183),
              L"IE_FLAG_HAS_SCROLL_POSITION");
            goto LABEL_53;
          case 0x17C2:
            CDoc::ReleaseOffscreenBuffers((CDoc *)this);
            goto LABEL_53;
          case 0x17C3:
            v367 = this[876];
            if ( v367 )
            {
              (*(void (__fastcall **)(CInPlace *, __int64, __int64, __int64))(*(_QWORD *)v367 + 16LL))(
                v367,
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
            v363 = ((_BYTE)this[441] & 4) != 0;
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
            v384 = plLbound[0];
            goto LABEL_1533;
          case 0x17C7:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v385 = a6->lVal;
            plLbound[0] = 0;
            Text = ValidateD3DRequestedFeatureLevel(v385, (enum D3D_REQUESTED_FEATURE_LEVEL *)plLbound);
            if ( Text )
              goto LABEL_231;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                  + 16LL)
                      + 1132LL) = plLbound[0];
            goto LABEL_1647;
          case 0x17C8:
            if ( !a6 )
              goto LABEL_131;
            v364 = a6->vt == 19;
            goto LABEL_964;
          case 0x17C9:
            if ( !a7 )
              goto LABEL_131;
            IsEnterpriseMode = 0;
            if ( CDoc::PrimaryMarkup((CDoc *)this) )
            {
              v361 = CDoc::PrimaryMarkup((CDoc *)this);
              v362 = CMarkup::MarkupVersion(v361);
              IsEnterpriseMode = CMarkupVersion::IsEnterpriseMode(v362);
            }
            a7->vt = 11;
            v363 = !IsEnterpriseMode - 1;
LABEL_961:
            a7->iVal = v363;
            goto LABEL_934;
          case 0x17CA:
            v380 = *(CVirtualTabStorageEntry **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + (unsigned int)tls_index)
                                                           + 16LL)
                                               + 728LL);
            if ( v380 && CVirtualTabStorageEntry::WasLastNavigationViaFlipAhead(v380) )
            {
              v381 = CDoc::PrimaryMarkup((CDoc *)this);
              CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v381);
              if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
              {
                v382 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                CPreloadManager::SetLastNavAsFlipAheadAndIssueRequestIfApplicable(v382);
              }
              CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
            }
            goto LABEL_53;
          case 0x17CB:
            if ( !a6 || a6->vt != 8 )
              goto LABEL_756;
            v355 = CDoc::PrimaryMarkup((CDoc *)this);
            if ( v355 && (*((_BYTE *)v355 + 248) = 1, (v356 = this[103]) != 0) )
            {
              CodePageCore = *((unsigned int *)v355 + 194);
              v358 = *((_DWORD *)v355 + 196);
              if ( !(_DWORD)CodePageCore )
                CodePageCore = CMarkup::GetCodePageCore(v355);
              Text = COmWindowProxy::ExecRefresh(v356, 3, CodePageCore, v358);
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
              v359 = bstrString;
              bstrString = 0;
              if ( v359 )
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)v359 + 16LL))(v359);
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
        v176 = 1;
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
                v416 = View;
                if ( !a7 || !View || !*((_BYTE *)View + 40) )
                  goto LABEL_1650;
                a7->vt = 3;
                v417 = *(unsigned __int16 *)CViewportController::GetLogicalViewportSize(*((_QWORD *)View + 4), &String1);
                a7->lVal = v417
                         | (*(unsigned __int16 *)(CViewportController::GetLogicalViewportSize(
                                                    *((_QWORD *)v416 + 4),
                                                    &v609)
                                                + 4) << 16);
                CDispClient::AdjustContentSize((CDispClient *)&v609, v418, v419);
                CDispClient::AdjustContentSize((CDispClient *)&String1, v420, v421);
                goto LABEL_934;
              case 0x1B77:
                Text = -2147467259;
                v423 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v423 || !*((_BYTE *)v423 + 40) )
                  goto LABEL_1650;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsMobileOptimizedSite(*((CViewportController **)v423 + 4));
                goto LABEL_1154;
              case 0x1B78:
                Text = -2147467259;
                v425 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v425 || !*((_BYTE *)v425 + 40) )
                  goto LABEL_1650;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsViewportWidthOrientationDependent(*((CViewportController **)v425
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
                v414 = CVersions::MapToDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
                goto LABEL_1118;
              case 0x1B7D:
                inserted = CDoc::SetAuthoringCallback((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7E:
                if ( !a6 || a6->vt != 9 )
                  goto LABEL_330;
                bstrString = 0;
                v431 = a6->punkVal;
                *(GUID *)&v609.vt = CLSID_CElement;
                Text = QIClassID(v431, (struct _GUID *)&v609, (void **)&bstrString);
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
                v432 = 0;
                bstrString = 0;
                if ( a6->vt == 9 )
                {
                  v433 = a6->punkVal;
                  *(GUID *)&v609.vt = CLSID_CElement;
                  Text = QIClassID(v433, (struct _GUID *)&v609, (void **)&bstrString);
                  if ( Text < 0 )
                    goto LABEL_1581;
                  v432 = (CElement *)bstrString;
                }
                if ( v432 )
                {
                  inserted = CElement::ExitFullScreen(v432);
                }
                else
                {
                  v434 = CDoc::FullScreenState((CDoc *)this);
                  inserted = CFullScreenState::ExitFullScreen(v434, 0);
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
                v426 = a6->parray;
                plLbound[0] = 0;
                SafeArrayGetUBound(v426, 1u, plLbound);
                if ( plLbound[0] != 2 )
                  goto LABEL_1650;
                v427 = a6->parray;
                *(_QWORD *)&String1.vt = 0;
                Text = SafeArrayAccessData(v427, (void **)&String1);
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
                v422 = CDoc::GetView((CDoc *)this);
                if ( !v422 || !*((_BYTE *)v422 + 40) )
                  goto LABEL_1650;
                CViewportController::SetUIOrientation(*((CViewportController **)v422 + 4), a6->iVal == 0xFFFF);
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
                v428 = CDoc::GetView((CDoc *)this);
                if ( !v428 )
                  goto LABEL_1650;
                CView::AllowGrippersForHost(v428, a6->iVal == 0);
                goto LABEL_53;
              case 0x1B87:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1650;
                if ( a6->vt != 8 )
                  goto LABEL_1650;
                Text = -2147418113;
                if ( !v578 )
                  goto LABEL_1650;
                inserted = CDoc::HandleFlashServicingRefresh((CDoc *)this, v578, a6->bstrVal);
                goto LABEL_306;
              case 0x1B88:
                Text = -2147024809;
                if ( !a7 )
                  goto LABEL_1650;
                a7->vt = 11;
                v429 = CDoc::FullScreenState((CDoc *)this);
                IsMobileOptimizedSite = CFullScreenState::IsInFullScreen(v429);
LABEL_1154:
                v430 = !IsMobileOptimizedSite;
                goto LABEL_1491;
              default:
                goto LABEL_231;
            }
            goto LABEL_306;
          }
          if ( a6 )
          {
            v364 = a6->vt == 11;
LABEL_964:
            if ( v364 )
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
                v392 = 0;
                if ( a6 && a6->vt == 3 )
                  v392 = a6->lVal;
                CDoc::SubmitForAntiPhishProcessing((CDoc *)this, 0, v392, 0);
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
          v393 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( !v393 )
            goto LABEL_350;
          *((_BYTE *)v393 + 97) |= 8u;
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
                Text = CDoc::ExecHelper((CDoc *)this, v578, &CGID_MSHTML, Lo + 2141, 2u, 0, 0);
                if ( Text )
                  goto LABEL_231;
              }
              if ( !a7 )
                goto LABEL_53;
              v364 = !FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
              v387 = (char *)this + 5722;
              if ( v364 )
                v387 = (char *)(this + 715);
              DebugState = *(__int16 *)v387;
              a7->vt = 3;
LABEL_1025:
              a7->lVal = DebugState;
              goto LABEL_53;
          }
          v390 = CDocument::Markup(v578);
          CDoc::WaitForRecalc((CDoc *)this, v390);
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
              v394 = 0;
              if ( a6->iVal == -1 )
                v394 = 512;
              *((_DWORD *)this + 1214) = (_DWORD)this[607] & 0xFFFFFDFF | v394;
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
        Text = CDoc::SaveToTempFileForPrint((CDoc *)this, v578, Data, 0x104u, 0, 0, 0);
        if ( Text < 0 )
          goto LABEL_1581;
        if ( !a7 )
          goto LABEL_756;
        VariantInit(a7);
        a7->vt = 8;
        v346 = SysAllocString(Data);
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
      v397 = rgIndices[0];
      v20 = plLbound[0];
      if ( (rgIndices[0] & 1) != 0 )
      {
        Text = 0;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v398 = ppvData;
          *(_WORD *)ppvData = 21;
          v398[1] = *((_QWORD *)CDoc::PrimaryMarkup((CDoc *)this) + 17);
        }
        v397 = rgIndices[0];
      }
      if ( (v397 & 2) != 0 )
      {
        v399 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( v399 )
        {
          v400 = COptionsHolder::SecurityContext(v399);
          *(_QWORD *)&v609.vt = v400;
          if ( v400 )
          {
            *(_QWORD *)&String1.vt = CHtmCtx::GetReferrerUrl(v400);
            OriginalUrlContext = CHtmCtx::GetOriginalUrlContext(*(CHtmCtx **)&v609.vt);
            v402 = *(const OLECHAR **)&String1.vt;
            v403 = -1;
            *(_QWORD *)&v609.vt = OriginalUrlContext;
            if ( *(_QWORD *)&String1.vt )
            {
              v404 = -1;
              do
                ++v404;
              while ( *(_WORD *)(*(_QWORD *)&String1.vt + 2 * v404) );
            }
            else
            {
              v404 = 0;
            }
            if ( OriginalUrlContext )
            {
              do
                ++v403;
              while ( OriginalUrlContext[v403] );
            }
            else
            {
              v403 = 0;
            }
            if ( v404 )
            {
              if ( v403 > v404 )
              {
                v405 = wcsncmp_0(*(const wchar_t **)&String1.vt, OriginalUrlContext, v404);
                v402 = *(const OLECHAR **)&String1.vt;
                if ( !v405 )
                  v402 = *(const OLECHAR **)&v609.vt;
              }
            }
            v406 = SysAllocString(v402);
            v25 = 1;
            if ( v406 )
            {
              v407 = ppvData;
              Text = 0;
              *((_WORD *)ppvData + 12) = 8;
              v407[4] = v406;
            }
          }
        }
      }
      v408 = rgIndices[0];
      if ( (rgIndices[0] & 4) != 0 )
      {
        v409 = ppvData;
        *(_QWORD *)&v609.vt = ppvData;
        *((_WORD *)ppvData + 24) = 21;
        if ( this[781] )
        {
          v410 = CHTMLDlg::SecurityContext(this[781]);
          v408 = rgIndices[0];
          *(_QWORD *)(*(_QWORD *)&v609.vt + 56LL) = v410;
        }
        else
        {
          v409[7] = 0;
        }
      }
      if ( (v408 & 8) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractVideoData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text < 0 )
        {
LABEL_1110:
          CMultimediaLog::StopUpdate((CMultimediaLog *)(this + 741));
          v413 = (SAFEARRAY *)pszSubKey;
          goto LABEL_1143;
        }
        v408 = rgIndices[0];
        if ( bstrString )
        {
          v411 = ppvData;
          Text = 0;
          *((_WORD *)ppvData + 36) = 8;
          v411[10] = bstrString;
        }
      }
      if ( (v408 & 0x10) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractImageData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text >= 0 )
        {
          if ( bstrString )
          {
            v412 = ppvData;
            Text = 0;
            *((_WORD *)ppvData + 48) = 8;
            v412[13] = bstrString;
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
              Text = CDoc::SerializePrintCommands((CDoc *)this, v578, a6, a7);
              v451 = Text == 0;
              goto LABEL_1646;
            }
            goto LABEL_231;
          }
          if ( plLbound[0] == 8000 )
          {
            if ( !a6 || a6->vt == 11 )
            {
              v449 = (unsigned int)tls_index;
              if ( a7 )
              {
                ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 11;
                a7->iVal = -(*(_BYTE *)(*(_QWORD *)(ThreadLocalStoragePointer[v449] + 16LL) + 1128LL) != 0);
              }
              if ( a6 )
                *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v449) + 16LL) + 1128LL) = a6->iVal == 0xFFFF;
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
                v444 = CDocument::Window(v578);
                v445 = v444;
                if ( v444 && (unsigned int)CWindow::IsPrimaryWindow(v444) )
                {
                  v446 = CDeviceRotationRate::SecurityContext(v445);
                  if ( v446 )
                  {
                    v447 = CMarkup::Window(v446);
                    CEventMgr::QueueAsyncEvent(
                      &s_propdescCIE9EventListorientationchange,
                      v447,
                      v446,
                      COmWindowProxy::Fire_orientationchange,
                      0,
                      AsyncEventMerge_Always,
                      0);
                  }
                  v448 = *((_QWORD *)v445 + 55);
                  if ( v448 )
                    CEventMgr::QueueAsyncEvent(
                      &s_propdescCIE9EventListMSOrientationChange,
                      v448,
                      v446,
                      CScreen::Fire_orientationchange,
                      0,
                      AsyncEventMerge_Always,
                      0);
                }
                goto LABEL_1647;
              case 8004:
                inserted = CDoc::GetContentLang((CDoc *)this, a7);
                break;
              case 8005:
                v443 = this[732];
                if ( v443 )
                {
                  CAPProcessor::Passivate(v443);
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
          v243 = 0;
          if ( a6->iVal == -1 )
            v243 = 32;
          v244 = *((_DWORD *)this + 1217) & 0xFFFFFFDF;
LABEL_614:
          *((_DWORD *)this + 1217) = v244 | v243;
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
            v437 = RootTracker;
            if ( RootTracker )
            {
              Text = CRootTracker::EnsureInitialized(RootTracker);
              if ( Text < 0 )
                goto LABEL_1581;
              CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
              v438 = CDCompLayerManager::UseRootLayer(v437);
              v439 = **(__int64 (__fastcall ***)(struct IDispLayer *, GUID *, struct CHtmParseCtx *))v438;
              v440 = (CHtmRootParseCtxRouter *)TSmartPointer<ID3D11Device>::operator&(&bstrString);
              HpxEmbed = CHtmRootParseCtxRouter::GetHpxEmbed(v440);
              Text = v439(v438, &GUID_cc1a2bea_d5e9_4161_9da7_9042b37549a7, HpxEmbed);
              if ( Text >= 0 )
              {
                v442 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                Text = (*(__int64 (__fastcall **)(struct IDispRenderTarget *, __int64, struct tagVARIANT *))(*(_QWORD *)v442 + 24LL))(
                         v442,
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
              v212 = (struct IUnknown *)bstrString;
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
            v212 = (struct IUnknown *)bstrString;
LABEL_527:
            ReleaseInterface(v212);
            goto LABEL_231;
          }
          goto LABEL_131;
        }
        if ( !a7 )
          goto LABEL_131;
        a7->vt = 4;
        v364 = !CView::HasStaticViewportSizeApplied((CView *)(this + 283));
        v435 = (int *)(this + 481);
        if ( v364 )
          v435 = (int *)this + 1019;
        NormZoomPercent = *v435;
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
              v464 = a6->parray;
              if ( v464 )
              {
                pvData = 0;
                pszSubKey = 0;
                *(_QWORD *)&String1.vt = 0;
                if ( !SafeArrayGetElement(v464, (LONG *)&pvData, &pszSubKey) )
                {
                  v465 = a6->parray;
                  ++pvData;
                  if ( !SafeArrayGetElement(v465, (LONG *)&pvData, &String1) )
                    CDoc::ReplacePrintHandles((CDoc *)this, (void *)pszSubKey, *(void **)&String1.vt);
                }
                goto LABEL_53;
              }
            }
            goto LABEL_131;
          }
          v329 = InternetSetOptionW(0, 0x2Au, 0, 0);
          v330 = -2147467259;
          goto LABEL_1318;
        }
        if ( g_fInHtmlHelp )
        {
          *((_DWORD *)this + 1217) |= 0x400u;
          v466 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( v466 )
          {
            if ( (*((_DWORD *)v466 + 187) & 0x4000000) != 0 )
            {
              v467 = (COmWindowProxy *)*((_QWORD *)v466 + 44);
              if ( v467 )
                COmWindowProxy::Fire_onafterprint(v467);
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
                  CDispClient::AdjustContentSize((CDispClient *)&bstrString, v462, v463);
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
                CDoc::HandleWebStorageEvent((CDoc *)this, v578, a6->cyVal.Lo);
                goto LABEL_1647;
              }
              goto LABEL_131;
            case 8008:
              Text = 0;
              if ( a6 && a6->vt == 19 )
              {
                v458 = this[126];
                if ( v458 )
                {
                  v459 = a6->lVal;
                  if ( *((_DWORD *)v458 + 384) == v459 )
                    goto LABEL_1647;
                  *((_DWORD *)v458 + 384) = v459;
                  v460 = CDocument::Markup(v578);
                  TextScalingSettings = CTextScalingSettings::GetTextScalingSettings(v460);
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
              v456 = CDoc::GetView((CDoc *)this);
              if ( v456 )
              {
                if ( *((_BYTE *)v456 + 40) )
                {
                  v457 = (CViewportController *)*((_QWORD *)v456 + 4);
                  if ( v457 )
                  {
                    Text = 0;
                    CViewportController::SetAccessibleZoom(v457, a6->iVal != 0);
                    goto LABEL_1647;
                  }
                }
              }
              goto LABEL_350;
            case 8010:
              v454 = NtCurrentTeb()->ThreadLocalStoragePointer;
              pvData = 0;
              bstrString = (BSTR)v454[(unsigned int)tls_index];
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
            v452 = CDoc::GetView((CDoc *)this);
            if ( v452 )
            {
              v453 = (CViewportController *)*((_QWORD *)v452 + 4);
              if ( v453 )
              {
                Text = 0;
                CViewportController::SetIsReadingView(v453, a6->iVal != 0);
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
            v468 = (unsigned int (__fastcall ***)(_QWORD, GUID *, void **, __int64))a6->llVal;
            if ( v468 )
            {
              ppvData = 0;
              if ( !(**v468)(v468, &IID_IHTMLWindow2, &ppvData, v26) )
              {
                v469 = this[642];
                bstrString = 0;
                if ( !(**(unsigned int (__fastcall ***)(CInPlace *, GUID *, BSTR *))v469)(
                        v469,
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
        v531 = CDocument::Markup(v578);
        v532 = 0;
        if ( a6 && a6->vt == 3 )
          v532 = a6->lVal;
        Text = 0;
        if ( !v531 )
          goto LABEL_1647;
        v533 = CMarkup::GetWindowedMarkupContext(v531);
        if ( !v533 )
          goto LABEL_1647;
        RootMarkup = CMarkup::GetRootMarkup(v533, 0);
        if ( !RootMarkup )
          goto LABEL_1647;
        *((_DWORD *)RootMarkup + 197) |= v532;
        *((_DWORD *)this + 1224) &= ~v532;
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
              v489 = SafeArrayCreate(0xCu, 1u, (SAFEARRAYBOUND *)&String1);
              v490 = v489;
              if ( v489 )
              {
                Text = SafeArrayAccessData(v489, &ppvData);
                if ( Text >= 0 )
                {
                  bstrString = 0;
                  Text = StringFromCLSID((const IID *const)pszSubKey + 52, &bstrString);
                  if ( Text >= 0 )
                  {
                    *(_WORD *)ppvData = 8;
                    v491 = SysAllocString(bstrString);
                    v492 = pszSubKey;
                    *((_QWORD *)ppvData + 1) = v491;
                    *((_WORD *)ppvData + 12) = 3;
                    *((_DWORD *)ppvData + 8) = *((_DWORD *)v492 + 212);
                    *((_WORD *)ppvData + 24) = 3;
                    *((_DWORD *)ppvData + 14) = *((_DWORD *)v492 + 213);
                    CoTaskMemFree(bstrString);
                  }
                  SafeArrayUnaccessData(v490);
                  if ( Text >= 0 )
                  {
                    VariantInit(a7);
                    a7->vt = 8204;
                    a7->llVal = (LONGLONG)v490;
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
              *(_OWORD *)&v609.vt = 0;
              memset(&pvarg, 0, sizeof(pvarg));
              memset(&String1, 0, sizeof(String1));
              memset(&pv, 0, sizeof(pv));
              VariantInit(&pvarg);
              VariantInit(&String1);
              VariantInit(&pv);
              v486 = a6->parray;
              rgIndices[0] = 0;
              Text = SafeArrayGetElement(v486, rgIndices, &pvarg);
              if ( Text >= 0 && pvarg.vt == 8 )
              {
                Text = CLSIDFromString(pvarg.bstrVal, (LPCLSID)&v609);
                if ( !Text )
                {
                  v487 = a6->parray;
                  rgIndices[0] = 1;
                  Text = SafeArrayGetElement(v487, rgIndices, &String1);
                  if ( Text >= 0 && String1.vt == 19 )
                  {
                    v488 = a6->parray;
                    rgIndices[0] = 2;
                    Text = SafeArrayGetElement(v488, rgIndices, &pv);
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
              v414 = CVersions::MapToNearestDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
              if ( v414 < 0 )
                goto LABEL_1650;
LABEL_1118:
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 740LL) = v414;
              goto LABEL_53;
            case 15009:
              Text = -2147024809;
              if ( !a6 || a6->vt != 3 || !a7 )
                goto LABEL_1650;
              VariantInit(a7);
              v478 = a6->lVal;
              if ( v478 )
              {
                v479 = v478 - 1;
                if ( v479 )
                {
                  if ( v479 != 1 )
                    goto LABEL_1650;
                  v480 = CDocument::Markup(v578);
                  a7->vt = 3;
                  v481 = CMarkup::MarkupVersion(v480);
                  v349 = CMarkupVersion::DocumentMode(v481);
                }
                else
                {
                  v482 = CDocument::Markup(v578);
                  a7->vt = 3;
                  v483 = CMarkup::MarkupVersion(v482);
                  v349 = CMarkupVersion::NativeDocumentMode(v483, 0, 0);
                }
              }
              else
              {
                v484 = (unsigned int)tls_index;
                v485 = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 3;
                v349 = *(_DWORD *)(*(_QWORD *)(v485[v484] + 16LL) + 740LL);
              }
              goto LABEL_922;
          }
          ppvData = GetThreadStateUI();
          *(_QWORD *)&v609.vt = CDoc::PrimaryMarkup((CDoc *)this);
          v470 = *(struct CMarkup **)&v609.vt;
          if ( !a6 )
          {
            Text = -2147024809;
            *(_QWORD *)&v609.vt = (char *)ppvData + 832;
            if ( (unsigned int)IsEqualGUID((char *)ppvData + 832, &GUID_NULL) )
              goto LABEL_1650;
            Text = 0;
            *(GUID *)*(_QWORD *)&v609.vt = GUID_NULL;
            *((_QWORD *)ppvData + 106) = 0;
            if ( !v470 || !(unsigned __int8)CMarkup::IsVersionedChangeEnabled(v470, 100000) )
            {
LABEL_1647:
              if ( !v9 )
                goto LABEL_1649;
              goto LABEL_1648;
            }
            CWorkerManager::StartProfilingAllWorkers(v470, 0);
            goto LABEL_231;
          }
          if ( a6->vt != 8204 )
            goto LABEL_231;
          v471 = a6->parray;
          if ( !v471 )
            goto LABEL_231;
          bstrString = 0;
          Text = SafeArrayAccessData(v471, (void **)&bstrString);
          if ( Text < 0 )
            goto LABEL_1581;
          v472 = a6->parray;
          pvData = 0;
          Text = SafeArrayGetUBound(v472, 1u, (LONG *)&pvData);
          if ( Text >= 0 )
          {
            v473 = pvData + 1;
            pvData = v473;
            if ( v473 == 3 )
            {
              if ( *bstrString == 8 && bstrString[12] == 3 && bstrString[24] == (_WORD)v473 )
              {
                v474 = ppvData;
                v475 = CLSIDFromString(*((LPCOLESTR *)bstrString + 1), (LPCLSID)ppvData + 52);
                v476 = bstrString;
                Text = v475;
                v474[212] = *((_DWORD *)bstrString + 8);
                v474[213] = *((_DWORD *)v476 + 14);
                if ( !v475 )
                {
                  v477 = *(struct CMarkup **)&v609.vt;
                  if ( *(_QWORD *)&v609.vt )
                  {
                    if ( (unsigned __int8)CMarkup::IsVersionedChangeEnabled(*(_QWORD *)&v609.vt, 100000) )
                      CWorkerManager::StartProfilingAllWorkers(v477, 1);
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
          v413 = a6->parray;
LABEL_1143:
          SafeArrayUnaccessData(v413);
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
            v499 = (__int64 (__fastcall ***)(_QWORD, GUID *, VARIANTARG *, __int64))a6->llVal;
            if ( !v499 )
              goto LABEL_131;
            *(_QWORD *)&String1.vt = 0;
            Text = (**v499)(v499, &IID_INavigateEventSink, &String1, 0xFFFFFFFFLL);
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
            inserted = CDoc::FireOnPopStateEvent((CDoc *)this, v578);
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
        v493 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( !a7 || !a6 || a6->vt != 3 )
          goto LABEL_1650;
        a7->vt = 11;
        Text = 0;
        v494 = a6->lVal;
        if ( v494 )
        {
          if ( v494 != 1 )
            goto LABEL_630;
          if ( !v493 )
          {
            v497 = 0;
            goto LABEL_1420;
          }
          v495 = CMarkup::MarkupVersion(v493);
          IsNativeQuirksLayoutEmulation = CMarkupVersion::IsNativeQuirksLayoutEmulation(v495);
        }
        else
        {
          if ( !v493 )
          {
            v497 = -(*(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                            + (unsigned int)tls_index)
                                          + 16LL)
                              + 587LL) != 0);
            goto LABEL_1420;
          }
          v498 = CMarkup::MarkupVersion(v493);
          IsNativeQuirksLayoutEmulation = CDCompVideoBackedLayer::IsRenderRequired(v498);
        }
        v497 = !IsNativeQuirksLayoutEmulation - 1;
LABEL_1420:
        a7->iVal = v497;
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
              v530 = a6->lVal;
              if ( !*((_BYTE *)this + 1016) || CColorValue::GetIntoABGR((CColorValue *)((char *)this + 1020)) != v530 )
              {
                *((_BYTE *)this + 1016) = 1;
                Text = 0;
                if ( !CServer::IsWebPlatformWindowless((CServer *)this) )
                  v530 |= 0xFF000000;
                CColorValue::SetFromABGR((CColorValue *)((char *)this + 1020), v530);
                CDoc::ForceRelayout((CDoc *)this, 1);
                CDoc::SignalDefaultBackgroundColorChanged((CDoc *)this, v530);
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
            v528 = (int)(float)(CColorValue::GetAlpha((CColorValue *)((char *)this + 1020)) * 255.0);
            v384 = ((unsigned __int8)v528 << 24)
                 | CColorValue::GetColorRef((CColorValue *)((char *)this + 1020)) & 0xFFFFFF;
          }
          else
          {
            v529 = (OLE_COLOR *)this[126];
            if ( !v529 )
            {
              a7->lVal = -16777216;
              goto LABEL_231;
            }
            plLbound[0] = 0;
            Text = OleTranslateColor(*v529, 0, (COLORREF *)plLbound);
            if ( Text )
              goto LABEL_231;
            v384 = plLbound[0] | 0xFF000000;
          }
LABEL_1533:
          a7->lVal = v384;
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
            v514 = 1;
          }
          else
          {
            if ( a5 != 103 )
              goto LABEL_1650;
            v514 = 0;
          }
          inserted = CDoc::SetGeolocationUserConsent((CDoc *)this, a6->bstrVal, v514);
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
                v500 = 0;
              }
              else
              {
                if ( a6->vt != 8 )
                  goto LABEL_1650;
                v500 = a6->bstrVal;
              }
              inserted = CDoc::SetExtraHeaders((CDoc *)this, v500);
              break;
            default:
              goto LABEL_231;
          }
          goto LABEL_306;
        }
        if ( !a7 )
          goto LABEL_131;
        v512 = CDocument::GetWindowedMarkupContext(v578);
        IsActiveXFilteringEnabled = CMarkup::IsActiveXFilteringEnabled(v512);
        a7->vt = 11;
        v430 = IsActiveXFilteringEnabled != 1;
LABEL_1491:
        a7->iVal = v430 - 1;
        goto LABEL_934;
      }
      if ( !a6 || !a7 )
        goto LABEL_231;
      if ( a6->vt != 13 )
        goto LABEL_230;
      v515 = a6->punkVal;
      if ( !v515 )
        goto LABEL_230;
      *(_QWORD *)plLbound = 0;
      *(GUID *)&v609.vt = CLSID_CElement;
      Text = QIClassID(v515, (struct _GUID *)&v609, (void **)plLbound);
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
      CRect::CRect((CRect *)&v609);
      CRect::CRect((CRect *)&String1);
      Text = CElement::GetBoundingRect(*(CElement **)plLbound, (struct CRectF *)&String1, 0x4001u, 0);
      if ( Text >= 0
        && ((unsigned int)CElement::IsDeviceFixed(*(CElement **)plLbound)
         || (unsigned int)CElement::IsAncestorPositionFixed(*(CElement **)plLbound, 1))
        && CElement::IsStandardsMode(*(CElement **)plLbound) )
      {
        v516 = CElement::LayoutServices(*(CElement **)plLbound);
        if ( v516 )
        {
          v517 = *(_QWORD *)v516;
          bstrString = 0;
          LOBYTE(pvt[0]) = 0;
          (*(void (__fastcall **)(struct ILayoutServices *, _QWORD, BSTR *, VARTYPE *))(v517 + 432))(
            v516,
            *(_QWORD *)plLbound,
            &bstrString,
            pvt);
          for ( j = bstrString; j; bstrString = j )
          {
            v519 = CDispNode::NodeReader((CDispNode *)j);
            if ( CDispNodeReader::IsTopLevelScroller(v519) )
            {
              v520 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispScroller::GetTotalZoomFactor(v520);
              v521 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispTopLevelScroller::BaseOpticalZoomFactor(v521);
              CRectF::operator/=(&String1);
              break;
            }
            j = (OLECHAR *)CDispNode::GetParentNode((CDispNode *)bstrString);
          }
        }
      }
      CRect::SetRect((CRect *)&v609, (const struct D2D_RECT_F *)&String1, 0);
      if ( Text >= 0 )
      {
        VariantInit(a7);
        a7->vt = 8195;
        v524 = SafeArrayCreateVector(3u, 0, 4u);
        a7->llVal = (LONGLONG)v524;
        if ( v524 )
        {
          *(_DWORD *)pvt = 0;
          SafeArrayPutElement(v524, (LONG *)pvt, &v609);
          v525 = a7->parray;
          v25 = 1;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v525, (LONG *)pvt, &v609.decVal.Hi32);
          v526 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v526, (LONG *)pvt, &v609.decVal.8);
          v527 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v527, (LONG *)pvt, (char *)&v609.decVal.Lo64 + 4);
LABEL_1522:
          CDispClient::AdjustContentSize((CDispClient *)&String1, v522, v523);
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
        v543 = 0;
        if ( a6 )
        {
          if ( a6->vt == 13 )
          {
            v544 = (void (__fastcall ***)(_QWORD, GUID *, struct CHtmParseCtx *))a6->llVal;
            if ( v544 )
            {
              v545 = **v544;
              v546 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)&bstrString);
              v545(v544, &GUID_0000000e_0000_0000_c000_000000000046, v546);
              v543 = (struct IBindCtx *)bstrString;
            }
          }
          v25 = 1;
        }
        v547 = CFlipAheadManager::InvokeCachedTarget((CFlipAheadManager *)(this + 836), v543);
        v55 = bstrString;
        Text = v547;
LABEL_952:
        if ( !v55 )
          goto LABEL_231;
        goto LABEL_111;
      case 15202:
        v542 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v537 = v542;
        if ( v542 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v542) == 2 )
            goto LABEL_1647;
          plLbound[0] = CMarkup::GetDebugState(v537);
          v538 = plLbound[0];
          CMarkup::SetDebugState(v537, 2);
          v539 = 2;
          goto LABEL_1563;
        }
        break;
      case 15203:
        v541 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v537 = v541;
        if ( v541 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v541) != 2 )
            goto LABEL_1647;
          plLbound[0] = CMarkup::GetDebugState(v537);
          CMarkup::SetDebugState(v537, 1);
          Text = CDoc::DynamicDetachDebugger((CDoc *)this);
          if ( Text >= 0 )
            goto LABEL_1603;
          v540 = (unsigned int)plLbound[0];
          goto LABEL_1565;
        }
        break;
      case 15204:
        v536 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v537 = v536;
        if ( v536 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v536) )
            goto LABEL_1647;
          plLbound[0] = CMarkup::GetDebugState(v537);
          v538 = plLbound[0];
          CMarkup::SetDebugState(v537, 1);
          v539 = 1;
LABEL_1563:
          Text = CDoc::DynamicAttachDebugger(this, v538, v539);
          if ( Text >= 0 )
            goto LABEL_1603;
          v540 = (unsigned int)plLbound[0];
LABEL_1565:
          CMarkup::SetDebugState(v537, v540);
          goto LABEL_1581;
        }
        break;
      case 15205:
        VariantInit(a7);
        a7->vt = 3;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v535 = CDoc::PrimaryMarkup((CDoc *)this);
          DebugState = CMarkup::GetDebugState(v535);
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
  if ( v607 )
    CScriptCollection::Release(v607);
  Text = -2147467263;
LABEL_15:
  CServer::CLock::~CLock((CServer::CLock *)v606);
  return (unsigned int)Text;
}

```

## disassembly

```asm
0x1806d4ea8  push    rbp
0x1806d4eaa  push    rbx
0x1806d4eab  push    rsi
0x1806d4eac  push    rdi
0x1806d4ead  push    r12
0x1806d4eaf  push    r13
0x1806d4eb1  push    r14
0x1806d4eb3  push    r15
0x1806d4eb5  lea     rbp, [rsp-13A8h]
0x1806d4ebd  mov     eax, 1508h
0x1806d4ec2  call    _alloca_probe
0x1806d4ec7  sub     rsp, rax
0x1806d4eca  movaps  [rsp+1540h+var_50], xmm6
0x1806d4ed2  mov     rax, cs:__security_cookie
0x1806d4ed9  xor     rax, rsp
0x1806d4edc  mov     [rbp+13E0h+var_60], rax
0x1806d4ee3  mov     r15, [rbp+13E0h+arg_28]
0x1806d4eea  mov     ebx, r9d
0x1806d4eed  mov     r12, [rbp+13E0h+arg_30]
0x1806d4ef4  mov     r14, rcx
0x1806d4ef7  mov     rcx, r8; struct _GUID *
0x1806d4efa  mov     [rbp+13E0h+var_1434], ebx
0x1806d4efd  mov     qword ptr [rbp+13E0h+var_1300], r15
0x1806d4f04  mov     r13, r8
0x1806d4f07  mov     [rbp+13E0h+String1], r12
0x1806d4f0e  mov     rdi, rdx
0x1806d4f11  mov     [rbp+13E0h+var_1428], r8
0x1806d4f15  mov     [rbp+13E0h+var_1450], rdx
0x1806d4f19  call    ?IsCmdGroupSupported@CBase@@SAHPEBU_GUID@@@Z; CBase::IsCmdGroupSupported(_GUID const *)
0x1806d4f1e  test    eax, eax
0x1806d4f20  jnz     short loc_1806D4F2C
0x1806d4f22  mov     eax, 80040104h
0x1806d4f27  jmp     loc_1806DBF9B
0x1806d4f2c  xor     r8d, r8d; unsigned __int16
0x1806d4f2f  lea     rcx, [rbp+13E0h+var_1338]; this
0x1806d4f36  mov     rdx, r14; struct CDoc *
0x1806d4f39  call    ??0CLock@CDoc@@QEAA@PEAV1@G@Z; CDoc::CLock::CLock(CDoc *,ushort)
0x1806d4f3e  xor     eax, eax
0x1806d4f40  xor     edx, edx
0x1806d4f42  mov     [rbp+13E0h+var_1348], rax
0x1806d4f49  xorps   xmm0, xmm0
0x1806d4f4c  mov     [rbp+13E0h+var_1360], rax
0x1806d4f53  xorps   xmm1, xmm1
0x1806d4f56  mov     [rbp+13E0h+var_1418], rdx
0x1806d4f5a  mov     esi, 80040100h
0x1806d4f5f  movups  [rbp+13E0h+var_1358], xmm0
0x1806d4f66  movups  [rbp+13E0h+var_1370], xmm1
0x1806d4f6a  test    r13, r13
0x1806d4f6d  jnz     short loc_1806D4F9B
0x1806d4f6f  mov     r9d, [rbp+13E0h+arg_20]; unsigned int
0x1806d4f76  mov     r8d, ebx; unsigned int
0x1806d4f79  mov     [rsp+1540h+lpcbData], r12; struct tagVARIANT *
0x1806d4f7e  mov     rdx, rdi; struct CDocument *
0x1806d4f81  mov     rcx, r14; this
0x1806d4f84  mov     [rsp+1540h+phkResult], r15; struct tagVARIANT *
0x1806d4f89  call    ?BrowserDocumentServerExec@CDoc@@QEAAJPEAVCDocument@@KKPEAUtagVARIANT@@1@Z; CDoc::BrowserDocumentServerExec(CDocument *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x1806d4f8e  mov     esi, eax
0x1806d4f90  cmp     eax, 80040100h
0x1806d4f95  jnz     loc_1806DBF8D
0x1806d4f9b  cmp     [rbp+13E0h+arg_20], 3
0x1806d4fa2  jnz     short loc_1806D4FBC
0x1806d4fa4  mov     rcx, [rbp+13E0h+var_1328]; this
0x1806d4fab  test    rcx, rcx
0x1806d4fae  jz      short loc_1806D4FB5
0x1806d4fb0  call    ?Release@CScriptCollection@@UEAAKXZ; CScriptCollection::Release(void)
0x1806d4fb5  mov     esi, 80004001h
0x1806d4fba  jmp     short loc_1806D4FF4
0x1806d4fbc  mov     rbx, rdi
0x1806d4fbf  test    rdi, rdi
0x1806d4fc2  jnz     short loc_1806D5005
0x1806d4fc4  mov     rax, [r14+338h]
0x1806d4fcb  test    rax, rax
0x1806d4fce  jz      short loc_1806D4FDE
0x1806d4fd0  mov     rax, [rax+78h]
0x1806d4fd4  mov     rdi, [rax+78h]
0x1806d4fd8  mov     [rbp+13E0h+var_1450], rdi
0x1806d4fdc  jmp     short loc_1806D501C
0x1806d4fde  mov     rcx, [rbp+13E0h+var_1328]; this
0x1806d4fe5  test    rcx, rcx
0x1806d4fe8  jz      short loc_1806D4FEF
0x1806d4fea  call    ?Release@CScriptCollection@@UEAAKXZ; CScriptCollection::Release(void)
0x1806d4fef  mov     esi, 8000FFFFh
0x1806d4ff4  lea     rcx, [rbp+13E0h+var_1338]; this
0x1806d4ffb  call    ??1CLock@CServer@@QEAA@XZ; CServer::CLock::~CLock(void)
0x1806d5000  jmp     loc_1806DBF99
0x1806d5005  mov     rax, [rdi+38h]
0x1806d5009  test    rax, rax
0x1806d500c  jz      short loc_1806D5014
0x1806d500e  mov     rcx, [rax+68h]
0x1806d5012  jmp     short loc_1806D5018
0x1806d5014  mov     rcx, [rdi+30h]
0x1806d5018  mov     [rbp+13E0h+var_1418], rcx
0x1806d501c  mov     edx, [rbp+13E0h+var_1434]; unsigned int
0x1806d501f  mov     rcx, r13; struct _GUID *
0x1806d5022  call    ?IDMFromCmdID@CBase@@SAHPEBU_GUID@@K@Z; CBase::IDMFromCmdID(_GUID const *,ulong)
0x1806d5027  mov     edx, 20h ; ' '
0x1806d502c  mov     [rbp+13E0h+plLbound], eax
0x1806d502f  mov     r13d, eax
0x1806d5032  lea     ecx, [rax-0E74h]
0x1806d5038  cmp     ecx, edx
0x1806d503a  ja      short loc_1806D5086
0x1806d503c  mov     rcx, [r14+1100h]; this
0x1806d5043  test    rcx, rcx
0x1806d5046  jz      short loc_1806D5052
0x1806d5048  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x1806d504d  test    rax, rax
0x1806d5050  jnz     short loc_1806D506E
0x1806d5052  mov     rax, [rdi+38h]
0x1806d5056  test    rax, rax
0x1806d5059  jz      short loc_1806D5061
0x1806d505b  mov     rax, [rax+68h]
0x1806d505f  jmp     short loc_1806D5065
0x1806d5061  mov     rax, [rdi+30h]
0x1806d5065  test    rax, rax
0x1806d5068  jz      loc_1806DBF8D
0x1806d506e  mov     r9, r15; struct tagVARIANT *
0x1806d5071  mov     r8d, r13d; unsigned int
0x1806d5074  mov     rdx, rax; struct CMarkup *
0x1806d5077  mov     rcx, r14; this
0x1806d507a  call    ?OnContextMenuExt@CDoc@@QEAAJPEAVCMarkup@@IPEAUtagVARIANT@@@Z; CDoc::OnContextMenuExt(CMarkup *,uint,tagVARIANT *)
0x1806d507f  mov     esi, eax
0x1806d5081  jmp     loc_1806DBF8D
0x1806d5086  mov     edi, 1
0x1806d508b  mov     eax, 17BAh
0x1806d5090  mov     ecx, 400h
0x1806d5095  mov     r9d, 0FFFFFFFFh
0x1806d509b  lea     r10d, [rdi+1]
0x1806d509f  cmp     r13d, eax
0x1806d50a2  ja      loc_1806D8EC3
0x1806d50a8  jz      loc_1806D8E8B
0x1806d50ae  mov     edx, 8FCh; struct MemoryProtection::leaf_t *
0x1806d50b3  mov     r8d, 85Bh
0x1806d50b9  lea     eax, [rdx+28h]
0x1806d50bc  cmp     r13d, eax
0x1806d50bf  ja      loc_1806D71D9
0x1806d50c5  lea     r9d, [rdx+16h]
0x1806d50c9  jz      loc_1806D6A7C
0x1806d50cf  lea     eax, [rdx-27h]
0x1806d50d2  cmp     r13d, eax
0x1806d50d5  ja      loc_1806D65DD
0x1806d50db  jz      loc_1806D64B8
0x1806d50e1  lea     eax, [r8-80h]
0x1806d50e5  cmp     r13d, eax
0x1806d50e8  ja      loc_1806D580B
0x1806d50ee  jz      loc_1806D57F8
0x1806d50f4  cmp     r13d, 46h ; 'F'
0x1806d50f8  ja      loc_1806D52E0
0x1806d50fe  jz      loc_1806D55C1
0x1806d5104  mov     eax, r13d
0x1806d5107  sub     eax, 1Bh
0x1806d510a  jz      loc_1806DB248
0x1806d5110  sub     eax, edi
0x1806d5112  jz      loc_1806D525C
0x1806d5118  sub     eax, edi
0x1806d511a  jz      loc_1806D523D
0x1806d5120  sub     eax, 8
0x1806d5123  jz      loc_1806D51FB
0x1806d5129  sub     eax, 6
0x1806d512c  jz      loc_1806D51B9
0x1806d5132  sub     eax, 4
0x1806d5135  jz      short loc_1806D5199
0x1806d5137  cmp     eax, 14h
0x1806d513a  jnz     def_1806D8EF8; jumptable 00000001806D8EF8 default case
0x1806d5140  cmp     dword ptr [r14+12F8h], 0
0x1806d5148  jl      def_1806D8EF8; jumptable 00000001806D8EF8 default case
0x1806d514e  cmp     [rbp+13E0h+arg_20], r10d
0x1806d5155  jz      def_1806D8EF8; jumptable 00000001806D8EF8 default case
0x1806d515b  xor     esi, esi
0x1806d515d  xor     eax, eax
0x1806d515f  mov     qword ptr [rbp+13E0h+pvarg+10h], rax
0x1806d5163  xorps   xmm0, xmm0
0x1806d5166  mov     [rbp+13E0h+ppvData], rsi
0x1806d516a  mov     qword ptr [rbp+13E0h+rgIndices], rsi
0x1806d516e  mov     [rbp+13E0h+bstrString], rsi
0x1806d5172  movups  xmmword ptr [rbp+13E0h+pvarg], xmm0
0x1806d5176  mov     word ptr [rbp+13E0h+pvarg], di
0x1806d517a  test    rbx, rbx
0x1806d517d  jz      loc_1806D591F
0x1806d5183  mov     rax, [rbx+38h]
0x1806d5187  test    rax, rax
0x1806d518a  jz      loc_1806D5919
0x1806d5190  mov     rbx, [rax+68h]
0x1806d5194  jmp     loc_1806D5964
0x1806d5199  mov     rcx, r14; this
0x1806d519c  call    ?DesignMode@CDoc@@UEAAHXZ; CDoc::DesignMode(void)
0x1806d51a1  xor     r13d, r13d
0x1806d51a4  test    eax, eax
0x1806d51a6  jz      short loc_1806D51B1
0x1806d51a8  bts     dword ptr [r14+1300h], 1Ch
0x1806d51b1  mov     esi, r13d
0x1806d51b4  jmp     loc_1806DBF7B
0x1806d51b9  mov     ebx, [r14+130Ch]
0x1806d51c0  mov     eax, ebx
0x1806d51c2  or      eax, ecx
0x1806d51c4  mov     rcx, r14; this
0x1806d51c7  mov     [r14+130Ch], eax
0x1806d51ce  call    ?EditUndo@CDoc@@QEAAJXZ; CDoc::EditUndo(void)
0x1806d51d3  shr     ebx, 0Ah
0x1806d51d6  mov     esi, eax
0x1806d51d8  mov     eax, [r14+130Ch]
0x1806d51df  movzx   ecx, bl
0x1806d51e2  shl     ecx, 0Ah
0x1806d51e5  xor     ecx, eax
0x1806d51e7  and     ecx, 400h
0x1806d51ed  xor     ecx, eax
0x1806d51ef  mov     [r14+130Ch], ecx
0x1806d51f6  jmp     def_1806D8EF8; jumptable 00000001806D8EF8 default case
0x1806d51fb  mov     rcx, [rbp+13E0h+var_1450]; this
0x1806d51ff  call    ?Markup@CDocument@@QEBAPEAVCMarkup@@XZ; CDocument::Markup(void)
0x1806d5204  mov     rcx, rax; this
0x1806d5207  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x1806d520c  mov     dl, dil; bool
0x1806d520f  mov     rcx, rax; this
0x1806d5212  call    ?Fire_onbeforeunload@COmWindowProxy@@QEAAH_N@Z; COmWindowProxy::Fire_onbeforeunload(bool)
0x1806d5217  xor     r13d, r13d
0x1806d521a  mov     esi, r13d
0x1806d521d  test    r12, r12
0x1806d5220  jz      loc_1806DBF85
0x1806d5226  neg     eax
0x1806d5228  mov     word ptr [r12], 0Bh
0x1806d522f  sbb     ax, ax
0x1806d5232  mov     [r12+8], ax
0x1806d5238  jmp     loc_1806DBF80
0x1806d523d  mov     ebx, [r14+130Ch]
0x1806d5244  mov     eax, ebx
0x1806d5246  or      eax, ecx
0x1806d5248  mov     rcx, r14; this
0x1806d524b  mov     [r14+130Ch], eax
0x1806d5252  call    ?EditRedo@CDoc@@QEAAJXZ; CDoc::EditRedo(void)
0x1806d5257  jmp     loc_1806D51D3
0x1806d525c  lea     rbx, [r14+1100h]
0x1806d5263  xor     r13d, r13d
0x1806d5266  mov     rcx, [rbx]; this
0x1806d5269  test    rcx, rcx
0x1806d526c  jz      short loc_1806D5280
0x1806d526e  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x1806d5273  mov     rcx, rax; this
0x1806d5276  call    ?Document@CMarkup@@QEAAPEAVCDocument@@XZ; CMarkup::Document(void)
0x1806d527b  mov     rsi, rax
0x1806d527e  jmp     short loc_1806D5284
0x1806d5280  mov     rsi, [rbp+13E0h+var_1450]
0x1806d5284  mov     rcx, [rbx]; this
0x1806d5287  test    rcx, rcx
0x1806d528a  jz      short loc_1806D5295
0x1806d528c  call    ?HasPages@CBase@@QEAAHXZ; CBase::HasPages(void)
0x1806d5291  test    eax, eax
0x1806d5293  jnz     short loc_1806D52CA
0x1806d5295  cmp     [rbx], r13
0x1806d5298  jnz     short loc_1806D52C4
0x1806d529a  mov     rcx, r14; this
0x1806d529d  call    ?GetActiveElement@CDoc@@QEBAPEAVCElement@@XZ; CDoc::GetActiveElement(void)
0x1806d52a2  test    rax, rax
0x1806d52a5  jz      short loc_1806D52C4
0x1806d52a7  mov     rcx, r14; this
0x1806d52aa  call    ?GetActiveElement@CDoc@@QEBAPEAVCElement@@XZ; CDoc::GetActiveElement(void)
0x1806d52af  mov     rcx, rax; this
0x1806d52b2  call    ?HasPages@CBase@@QEAAHXZ; CBase::HasPages(void)
0x1806d52b7  test    eax, eax
0x1806d52b9  jz      short loc_1806D52C4
0x1806d52bb  lea     rbx, [r14+388h]
0x1806d52c2  jmp     short loc_1806D52CA
0x1806d52c4  mov     edi, r13d
0x1806d52c7  mov     rbx, r13
0x1806d52ca  mov     r9, rbx; struct CElement **
0x1806d52cd  mov     r8d, edi; cElements
0x1806d52d0  mov     rdx, rsi; struct CDocument *
0x1806d52d3  mov     rcx, r14; this
0x1806d52d6  call    ?ShowPropertyDialog@CDoc@@QEAAJPEAVCDocument@@HPEAPEAVCElement@@@Z; CDoc::ShowPropertyDialog(CDocument *,int,CElement * *)
0x1806d52db  jmp     loc_1806D51B1
0x1806d52e0  mov     eax, r13d
0x1806d52e3  sub     eax, 47h ; 'G'
0x1806d52e6  jz      loc_1806D5650
0x1806d52ec  sub     eax, 16h
0x1806d52ef  jz      loc_1806DB248
0x1806d52f5  sub     eax, 773h
0x1806d52fa  jz      loc_1806D55B3
0x1806d5300  sub     eax, edi
0x1806d5302  jz      loc_1806D55B3
0x1806d5308  sub     eax, r10d
0x1806d530b  jz      loc_1806D54EF
0x1806d5311  sub     eax, edi
0x1806d5313  jz      short loc_1806D532A
0x1806d5315  mov     ebx, 6
0x1806d531a  cmp     eax, ebx
0x1806d531c  jnz     def_1806D8EF8; jumptable 00000001806D8EF8 default case
0x1806d5322  mov     r8d, edi
0x1806d5325  jmp     loc_1806D57FB
0x1806d532a  mov     rcx, [r14+10E0h]
0x1806d5331  test    rcx, rcx
0x1806d5334  jz      short loc_1806D5374
0x1806d5336  mov     edx, [rbp+13E0h+arg_20]
0x1806d533c  cmp     edx, r10d
0x1806d533f  jz      short loc_1806D5374
0x1806d5341  test    dword ptr [r14+12FCh], 400000h
0x1806d534c  jnz     short loc_1806D5374
0x1806d534e  mov     rax, [rcx]
0x1806d5351  mov     r9d, edx
0x1806d5354  mov     r8d, [rbp+13E0h+var_1434]
0x1806d5358  lea     rdx, CGID_DocHostCommandHandler
0x1806d535f  mov     [rsp+1540h+lpcbData], r12
  ... truncated ...
```
