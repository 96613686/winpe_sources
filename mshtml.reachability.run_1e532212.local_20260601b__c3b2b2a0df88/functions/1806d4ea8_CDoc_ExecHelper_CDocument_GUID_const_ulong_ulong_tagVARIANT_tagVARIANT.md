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
  unsigned int v19; // eax
  __int64 v20; // r8
  LONGLONG llVal; // rdx
  unsigned int v22; // r13d
  CElement *v23; // rcx
  struct CMarkup *MarkupPtr; // rax
  __int64 v25; // rax
  HRESULT v26; // eax
  ULONG v27; // edi
  __int64 v28; // r9
  __int64 v29; // rax
  struct CMarkup *v30; // rbx
  unsigned int v31; // ebx
  HRESULT v32; // eax
  CMarkup *v33; // rax
  COmWindowProxy *v34; // rax
  int v35; // eax
  CBase **v36; // rbx
  CElement *v37; // rcx
  CMarkup *v38; // rax
  struct CDocument *v39; // rsi
  CBase *ActiveElement; // rax
  int v41; // r8d
  CInPlace *v42; // rcx
  CInPlace *v43; // rcx
  CInPlace *v44; // rax
  CInPlace *v45; // rbx
  CInPlace *v46; // rdi
  __int64 v47; // rsi
  HWND HWND; // rax
  const unsigned __int16 *v49; // r8
  unsigned int v50; // ebx
  CInPlace *v51; // rcx
  CInPlace *v52; // rcx
  HRESULT v53; // eax
  HRESULT v54; // eax
  void *v55; // rcx
  struct CElement *v56; // rax
  CInPlace *v57; // rcx
  CInPlace *v58; // rcx
  int v59; // esi
  unsigned __int16 *v60; // rax
  __int64 v61; // rcx
  struct CMarkup *v62; // rdx
  CMarkup *v63; // rsi
  COptionsHolder *v64; // rax
  COptionsHolder *v65; // rax
  CWindow *v66; // rbx
  COptionsHolder *v67; // rax
  struct CSecurityContext *v68; // rax
  int v69; // r8d
  int inserted; // eax
  enum _htmlDesignMode v71; // r8d
  CElement *v72; // rcx
  __int64 v73; // rbx
  struct COptionsHolder *v74; // rbx
  COptionsHolder *v75; // rax
  __int64 v76; // rdx
  COptionsHolder *v77; // rax
  unsigned int v78; // edx
  unsigned int v79; // r8d
  __int128 v80; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  struct IDispatch *v82; // rdi
  const unsigned __int16 *v83; // rbx
  CElement *v84; // rax
  struct CMarkup *v85; // rax
  HRESULT v86; // eax
  unsigned int v87; // ecx
  CInPlace *v88; // r10
  CInPlace *v89; // rcx
  __int64 v90; // rcx
  VARIANTARG *p_pvarg; // rcx
  LSTATUS v92; // ebx
  wchar_t *v93; // rax
  __int64 v94; // rax
  HANDLE FileW; // rax
  HRESULT v96; // eax
  bool v97; // sf
  CElement *v98; // rax
  CElement *v99; // rax
  CMarkup *WindowedMarkupContext; // rax
  BSTR v101; // rdi
  signed __int16 v102; // r13
  __int16 BaselineFontPrivate; // ax
  CInPlace *v104; // rax
  wchar_t *v105; // rcx
  __int64 v106; // rdx
  __int64 v107; // rdx
  unsigned __int64 v108; // rax
  CInPlace *v109; // rcx
  CInPlace *v110; // rax
  unsigned int v111; // ecx
  unsigned __int8 v112; // al
  struct CBase *v113; // rax
  CImplAry *v114; // rcx
  int v115; // edx
  const WCHAR *v116; // r12
  unsigned int v117; // r15d
  char *v118; // r8
  unsigned int v119; // ecx
  unsigned __int8 v120; // al
  unsigned __int8 v121; // al
  int v122; // eax
  __int64 v123; // r9
  CInPlace *v124; // rax
  unsigned int v125; // ecx
  unsigned __int8 v126; // al
  int v127; // r13d
  struct CBase *v128; // rdi
  LONG v129; // r12d
  unsigned int v130; // eax
  unsigned __int8 v131; // al
  CElement *v132; // rax
  CMarkup *v133; // rax
  __int64 v134; // rdx
  unsigned int v135; // ebx
  struct CElement *v136; // rax
  CInPlace *v137; // rcx
  struct IUnknown *v138; // rcx
  __int64 v139; // rax
  struct CMarkup *v140; // rax
  CInPlace *v141; // rcx
  CElement *v142; // rcx
  struct CElement *v143; // rax
  __int64 v144; // rax
  __int64 v145; // rbx
  CMarkup *v146; // rbx
  struct CMarkupEditContext *v147; // rax
  CDocument *v148; // rax
  __int64 v149; // rcx
  CMarkup *v150; // rcx
  int v151; // edx
  CInPlace *v152; // rax
  HWND v153; // rbx
  CInPlace *v154; // rax
  HWND v155; // rax
  CWindowBarProp *v156; // rax
  struct CTreeNode *v157; // rax
  CWindowBarProp *v158; // rax
  struct CTreeNode *v159; // rax
  CElement *v160; // rax
  CMarkup *v161; // rsi
  CCollectionCache *v162; // rax
  VARIANTARG *v163; // rbx
  struct CElement *v164; // rdx
  __int64 v165; // rcx
  CMarkup *v166; // rcx
  int v167; // ebx
  CInPlace *v168; // rcx
  __int64 (__fastcall ***v169)(_QWORD, GUID *, BSTR *); // rcx
  HRESULT v170; // eax
  CMarkup *v171; // rax
  struct CGlyph *GlyphTable; // rax
  int v173; // edx
  CPeerFactoryUrl *v174; // rcx
  unsigned __int16 *Url; // rax
  CMarkup *v176; // rax
  CScriptCollection *ScriptCollection; // rax
  LONG lVal; // esi
  int v179; // ebx
  struct CElement *v180; // rax
  __int64 v181; // rcx
  CMarkup *v182; // rax
  CDwnDoc *DwnDoc; // rax
  CMarkup *v184; // rax
  CMarkup *v185; // rax
  CMarkup *v186; // rbx
  BOOL v187; // ecx
  struct CElement *ElementTopHelper; // rax
  CElement *TopLayoutElement; // rax
  struct CElement *v190; // rax
  BYTE bVal; // al
  int v192; // ecx
  int v193; // eax
  unsigned int v194; // ecx
  CInPlace *v195; // rax
  struct IUnknown *v196; // rax
  int SelectionMarkup; // ebx
  CElement *v198; // rax
  int v199; // ebx
  int v200; // ebx
  CMarkup *v201; // rax
  CMarkup *v202; // rax
  struct CGlyph *v203; // rax
  CElement *v204; // rcx
  CMarkup *v205; // rax
  CMarkup *v206; // rax
  struct CMarkup *v207; // rbx
  struct CSecurityContext *v208; // rax
  struct IUnknown *v209; // rcx
  __int64 v210; // rdx
  __int64 v211; // r8
  __int64 v212; // r9
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
  BYTE v271; // r8
  CMarkup *v272; // rax
  struct CMarkupStyleState *StyleState; // rax
  CMarkup *v274; // rbx
  CStr *v275; // rax
  CStr *v276; // rax
  CDispSurface *v277; // rax
  struct IDispRenderTarget *v278; // rax
  struct tagVARIANT *v279; // rcx
  signed __int64 v280; // rax
  int v281; // edx
  int v282; // r8d
  struct CMarkupStyleState *v283; // rax
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
  struct CMarkup *v313; // rax
  struct CElement *v314; // rax
  int DefaultBlockTag; // eax
  const OLECHAR *v316; // rcx
  BOOL v317; // ebx
  CInPlace *v318; // rcx
  CElement *v319; // rcx
  CMarkup *v320; // rax
  CMarkup *v321; // rax
  struct GWND *Gwnd; // rax
  struct CElement *v323; // rdx
  int v324; // ecx
  HMENU DocDirMenu; // rax
  LONG v326; // eax
  int v327; // esi
  bool v328; // al
  __int16 *v329; // rdx
  bool v330; // al
  __int16 *v331; // rcx
  __int16 v332; // cx
  HMENU FontSizeMenu; // rax
  LONG v334; // eax
  __int64 (__fastcall ***v335)(_QWORD, GUID *, BSTR *); // rcx
  CDocument *v336; // rdi
  struct INamedPropertyBag *v337; // rbx
  struct CMarkup *v338; // rax
  CMarkup *v339; // rax
  struct CElement *v340; // rax
  COmWindowProxy *v341; // rcx
  CDocument *v342; // rax
  BSTR v343; // rax
  struct CMarkup *v344; // rax
  struct IDispRenderTarget *v345; // rax
  LONG v346; // eax
  ReadingMode::CTextClusterDetector *v347; // rax
  ReadingMode::CTextClusterDetector *v348; // rax
  ReadingMode::CTextClusterDetector *v349; // rbx
  CInputManager *v350; // rax
  CDeferredActionHandler *v351; // rax
  struct CMarkup *v352; // rax
  CInPlace *v353; // rbx
  __int64 CodePageCore; // r8
  unsigned int v355; // esi
  BSTR v356; // rcx
  bool IsEnterpriseMode; // bl
  CMarkup *v358; // rax
  CMarkupVersion *v359; // rax
  SHORT v360; // ax
  bool v361; // zf
  struct CMarkup *v362; // rax
  struct CMarkup *v363; // rbx
  CInPlace *v364; // rcx
  CInputManager *v365; // rax
  CDeferredActionHandler *v366; // rax
  CInputManager *v367; // rax
  CDeferredActionHandler *v368; // rax
  CInputManager *v369; // rax
  CDeferredActionHandler *v370; // rax
  CInputManager *v371; // rax
  CDeferredActionHandler *v372; // rax
  CInputManager *v373; // rax
  CDeferredActionHandler *v374; // rax
  SHORT v375; // cx
  int v376; // eax
  CVirtualTabStorageEntry *v377; // rcx
  struct CMarkup *v378; // rax
  CPreloadManager *v379; // rax
  struct IDispSystem *DispSystem; // rax
  LONG v381; // eax
  LONG v382; // ecx
  unsigned int Lo; // r9d
  char *v384; // rax
  LONG DebugState; // eax
  struct THREADSTATEUI *ThreadStateUI; // rax
  struct CMarkup *v387; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdx
  LONG v389; // r8d
  struct CMarkup *v390; // rax
  int v391; // ecx
  SAFEARRAY *Vector; // rax
  __int64 i; // r13
  char v394; // r8
  _QWORD *v395; // rbx
  COptionsHolder *v396; // rax
  CHtmCtx *v397; // rax
  const wchar_t *OriginalUrlContext; // rax
  const OLECHAR *v399; // rcx
  unsigned __int64 v400; // rdi
  size_t v401; // r8
  int v402; // eax
  BSTR v403; // rcx
  _QWORD *v404; // rax
  char v405; // dl
  _QWORD *v406; // rcx
  struct CSecurityContext *v407; // rax
  _QWORD *v408; // rcx
  _QWORD *v409; // rcx
  SAFEARRAY *v410; // rcx
  int v411; // eax
  struct CView *View; // rax
  struct CView *v413; // rdi
  int v414; // ebx
  const struct CDispNode *v415; // rdx
  struct CRect *v416; // r8
  const struct CDispNode *v417; // rdx
  struct CRect *v418; // r8
  struct CView *v419; // rax
  struct CView *v420; // rax
  bool IsMobileOptimizedSite; // al
  struct CView *v422; // rax
  SAFEARRAY *v423; // rcx
  SAFEARRAY *v424; // rcx
  CView *v425; // rax
  CFullScreenState *v426; // rax
  __int16 v427; // cx
  struct IUnknown *v428; // rcx
  CElement *v429; // rcx
  struct IUnknown *v430; // rcx
  CFullScreenState *v431; // rax
  int *v432; // rax
  CRootTracker *RootTracker; // rax
  CDCompLayerManager *v434; // rbx
  struct IDispLayer *v435; // rdi
  __int64 (__fastcall *v436)(struct IDispLayer *, GUID *, struct CHtmParseCtx *); // rbx
  CHtmRootParseCtxRouter *v437; // rax
  struct CHtmParseCtx *HpxEmbed; // rax
  struct IDispRenderTarget *v439; // rax
  CAPProcessor *v440; // rcx
  CWindow *v441; // rax
  CWindow *v442; // rbx
  CMarkup *v443; // rdi
  struct COmWindowProxy *v444; // rax
  __int64 v445; // rdx
  __int64 v446; // r9
  _QWORD *ThreadLocalStoragePointer; // rax
  bool v448; // zf
  struct CView *v449; // rax
  CViewportController *v450; // rcx
  _QWORD *v451; // rax
  unsigned int VirtualTabID; // eax
  struct CView *v453; // rax
  CViewportController *v454; // rcx
  CInPlace *v455; // rax
  LONG v456; // ecx
  const struct CMarkup *v457; // rax
  CTextScalingSettings *TextScalingSettings; // rax
  const struct CDispNode *v459; // rdx
  struct CRect *v460; // r8
  SAFEARRAY *v461; // rcx
  SAFEARRAY *v462; // rcx
  struct CMarkup *v463; // rax
  COmWindowProxy *v464; // rcx
  unsigned int (__fastcall ***v465)(_QWORD, GUID *, void **, __int64); // rcx
  CInPlace *v466; // rcx
  struct CMarkup *v467; // rbx
  SAFEARRAY *v468; // rcx
  SAFEARRAY *v469; // rcx
  unsigned int v470; // eax
  _DWORD *v471; // rbx
  HRESULT v472; // eax
  BSTR v473; // rcx
  struct CMarkup *v474; // rbx
  LONG v475; // ecx
  int v476; // ecx
  CMarkup *v477; // rax
  const struct CMarkupVersion *v478; // rax
  CMarkup *v479; // rax
  const struct CMarkupVersion *v480; // rax
  __int64 v481; // rdx
  _QWORD *v482; // rax
  SAFEARRAY *v483; // rcx
  SAFEARRAY *v484; // rcx
  SAFEARRAY *v485; // rcx
  SAFEARRAY *v486; // rax
  SAFEARRAY *v487; // rbx
  BSTR v488; // rax
  LPCWSTR v489; // rdx
  CMarkup *v490; // rax
  LONG v491; // edx
  CMarkupVersion *v492; // rax
  bool IsNativeQuirksLayoutEmulation; // al
  SHORT v494; // cx
  CDCompVideoBackedLayer *v495; // rax
  __int64 (__fastcall ***v496)(_QWORD, GUID *, VARIANTARG *, __int64); // rcx
  const unsigned __int16 *v497; // rdx
  int v498; // ecx
  int iVal; // ebx
  LONG v500; // eax
  int v501; // eax
  unsigned int v502; // esi
  const struct CMarkup *v503; // rax
  const unsigned __int16 *UrlRaw; // rax
  const WCHAR *v505; // rcx
  SAFEARRAY *parray; // rax
  const unsigned __int16 *bstrVal; // r8
  unsigned int v508; // ebx
  struct CMarkup *v509; // rax
  int IsActiveXFilteringEnabled; // eax
  int v511; // r8d
  struct IUnknown *v512; // rcx
  struct ILayoutServices *v513; // rax
  __int64 v514; // rcx
  OLECHAR *j; // rax
  CDispNodeReader *v516; // rax
  CDispScroller *v517; // rax
  CDispTopLevelScroller *v518; // rax
  const struct CDispNode *v519; // rdx
  struct CRect *v520; // r8
  SAFEARRAY *v521; // rax
  SAFEARRAY *v522; // rcx
  SAFEARRAY *v523; // rcx
  SAFEARRAY *v524; // rcx
  int v525; // ebx
  OLE_COLOR *v526; // rcx
  LONG v527; // ebx
  CMarkup *v528; // rax
  LONG v529; // ebx
  CMarkup *v530; // rax
  struct CMarkup *RootMarkup; // rax
  struct CMarkup *v532; // rax
  struct CMarkup *v533; // rax
  struct CMarkup *v534; // rbx
  unsigned int v535; // esi
  __int64 v536; // r8
  __int64 v537; // rdx
  struct CMarkup *v538; // rax
  struct CMarkup *v539; // rax
  struct IBindCtx *v540; // rdx
  void (__fastcall ***v541)(_QWORD, GUID *, struct CHtmParseCtx *); // rdi
  void (__fastcall *v542)(_QWORD, GUID *, struct CHtmParseCtx *); // rbx
  struct CHtmParseCtx *v543; // rax
  HRESULT v544; // eax
  unsigned int CodePageFromMenuID; // esi
  int IsCpAutoDetect; // eax
  CInPlace *v547; // rcx
  int v548; // ebx
  HWND v549; // rax
  CElement *v550; // rcx
  CMarkup *v551; // rax
  CMarkup *FrameOrPrimaryMarkup; // rax
  CMarkup *v553; // r13
  CWindowBarProp *v554; // rdi
  struct CSecurityContext *v555; // rax
  struct COmWindowProxy *v556; // rdi
  unsigned int CPSrc; // ebx
  unsigned int CodePage; // eax
  int v559; // ebx
  CWindowBarProp *v560; // rax
  CTreeNode *v561; // rbx
  struct CMarkup *v562; // rax
  struct CTreeNode *NodeInMarkup; // rax
  struct CElement *ElementClient; // rax
  struct CDocument *v565; // rbx
  CMarkup *v566; // rax
  unsigned int v567; // edi
  struct CMarkupEditContext *EditContext; // rax
  struct _GUID *v569; // rsi
  struct CMarkupEditContext *v570; // rbx
  CEntity *FocusedEntity; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-138h]
  BSTR bstrString; // [rsp+E0h] [rbp-80h] BYREF
  LONG plLbound[2]; // [rsp+E8h] [rbp-78h] BYREF
  CDocument *v575; // [rsp+F0h] [rbp-70h] BYREF
  unsigned int pvData; // [rsp+F8h] [rbp-68h] BYREF
  void *ppvData; // [rsp+100h] [rbp-60h] BYREF
  VARTYPE pvt[2]; // [rsp+108h] [rbp-58h] BYREF
  unsigned int v579; // [rsp+10Ch] [rbp-54h]
  LONG rgIndices[2]; // [rsp+110h] [rbp-50h] BYREF
  struct _GUID *v581; // [rsp+118h] [rbp-48h]
  LPCWSTR pszSubKey; // [rsp+120h] [rbp-40h] BYREF
  struct IUnknown *v583; // [rsp+128h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+130h] [rbp-30h] BYREF
  VARIANTARG pv; // [rsp+148h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+160h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+168h] [rbp+8h] BYREF
  int v588; // [rsp+170h] [rbp+10h] BYREF
  __int64 v589; // [rsp+178h] [rbp+18h]
  __int64 v590; // [rsp+188h] [rbp+28h]
  char v591; // [rsp+198h] [rbp+38h]
  int v592; // [rsp+19Ch] [rbp+3Ch]
  CIPrintCollection *v593; // [rsp+1A0h] [rbp+40h]
  __int64 v594; // [rsp+1A8h] [rbp+48h]
  __int64 v595; // [rsp+1B0h] [rbp+50h]
  size_t BufferCount; // [rsp+1C0h] [rbp+60h] BYREF
  wchar_t *Buffer; // [rsp+1C8h] [rbp+68h] BYREF
  __int128 v598; // [rsp+1D0h] [rbp+70h] BYREF
  VARIANTARG *v599; // [rsp+1E0h] [rbp+80h]
  __int128 v600; // [rsp+1E8h] [rbp+88h] BYREF
  __int128 *v601; // [rsp+1F8h] [rbp+98h]
  int v602; // [rsp+200h] [rbp+A0h] BYREF
  _BYTE v603[16]; // [rsp+208h] [rbp+A8h] BYREF
  CScriptCollection *v604; // [rsp+218h] [rbp+B8h]
  VARIANTARG String1; // [rsp+220h] [rbp+C0h] BYREF
  VARIANTARG v606; // [rsp+240h] [rbp+E0h] BYREF
  _BYTE v607[32]; // [rsp+260h] [rbp+100h] BYREF
  OLECHAR Data[264]; // [rsp+280h] [rbp+120h] BYREF
  OLECHAR psz[2088]; // [rsp+490h] [rbp+330h] BYREF

  v7 = a6;
  v9 = a7;
  v579 = a4;
  *(_QWORD *)&v606.vt = a6;
  *(_QWORD *)&String1.vt = a7;
  v12 = a2;
  v581 = a3;
  v575 = a2;
  if ( !(unsigned int)CBase::IsCmdGroupSupported(a3) )
    return 2147746052LL;
  CDoc::CLock::CLock((CDoc::CLock *)v603, (struct CDoc *)this, 0);
  v601 = 0;
  v599 = 0;
  v583 = 0;
  Text = -2147221248;
  v600 = 0;
  v598 = 0;
  if ( !a3 )
  {
    Text = CDoc::BrowserDocumentServerExec((CDoc *)this, v12, a4, a5, a6, a7);
    if ( Text != -2147221248 )
      goto LABEL_1652;
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
      v583 = v18;
    }
    else
    {
      v16 = this[103];
      if ( !v16 )
      {
        if ( v604 )
          CScriptCollection::Release(v604);
        Text = -2147418113;
        goto LABEL_15;
      }
      v12 = *(struct CDocument **)(*((_QWORD *)v16 + 15) + 120LL);
      v575 = v12;
    }
    v19 = CBase::IDMFromCmdID(a3, v579);
    llVal = 32;
    plLbound[0] = v19;
    v22 = v19;
    if ( v19 - 3700 <= 0x20 )
    {
      v23 = this[544];
      if ( !v23 || (MarkupPtr = CElement::GetMarkupPtr(v23)) == 0 )
      {
        v25 = *((_QWORD *)v12 + 7);
        MarkupPtr = v25 ? *(struct CMarkup **)(v25 + 104) : (struct CMarkup *)*((_QWORD *)v12 + 6);
        if ( !MarkupPtr )
          goto LABEL_1652;
      }
      v26 = CDoc::OnContextMenuExt((CDoc *)this, MarkupPtr, v22, a6);
      goto LABEL_28;
    }
    v27 = 1;
    v28 = 0xFFFFFFFFLL;
    if ( v19 <= 0x17BA )
    {
      if ( v19 == 6074 )
      {
        if ( !a7 )
          goto LABEL_131;
        a7->vt = 19;
        v350 = CDoc::InputManager((CDoc *)this);
        v351 = CInputManager::DeferredActionHandler(v350);
        NormZoomPercent = CDeferredActionHandler::RegisterVTabNavigate(v351);
        goto LABEL_935;
      }
      llVal = 2300;
      v20 = 2139;
      if ( v19 <= 0x924 )
      {
        v28 = 2322;
        if ( v19 == 2340 )
          goto LABEL_376;
        if ( v19 <= 0x8D5 )
        {
          if ( v19 != 2261 )
          {
            if ( v19 <= 0x7DB )
            {
              if ( v19 == 2011 )
              {
                v41 = 0;
                goto LABEL_140;
              }
              if ( v19 <= 0x46 )
              {
                if ( v19 != 70 )
                {
                  if ( v19 != 27 )
                  {
                    if ( v19 == 28 )
                    {
                      v36 = this + 544;
                      v37 = this[544];
                      if ( v37 )
                      {
                        v38 = CElement::GetMarkupPtr(v37);
                        v39 = CMarkup::Document(v38);
                      }
                      else
                      {
                        v39 = v575;
                      }
                      if ( !*v36 || !(unsigned int)CBase::HasPages(*v36) )
                      {
                        if ( !*v36
                          && CDoc::GetActiveElement((CDoc *)this)
                          && (ActiveElement = CDoc::GetActiveElement((CDoc *)this),
                              (unsigned int)CBase::HasPages(ActiveElement)) )
                        {
                          v36 = this + 113;
                        }
                        else
                        {
                          v27 = 0;
                          v36 = 0;
                        }
                      }
                      CDoc::ShowPropertyDialog((CDoc *)this, v39, v27, v36);
                      goto LABEL_53;
                    }
                    if ( v19 == 29 )
                    {
                      v31 = *((_DWORD *)this + 1219);
                      *((_DWORD *)this + 1219) = v31 | 0x400;
                      v32 = CDoc::EditRedo((CDoc *)this);
LABEL_55:
                      Text = v32;
                      *((_DWORD *)this + 1219) ^= ((unsigned __int16)*((_DWORD *)this + 1219)
                                                 ^ (unsigned __int16)((unsigned __int8)(v31 >> 10) << 10))
                                                & 0x400;
                      goto LABEL_231;
                    }
                    if ( v19 != 37 )
                    {
                      if ( v19 != 43 )
                      {
                        if ( v19 == 47 )
                        {
                          if ( (unsigned int)CDoc::DesignMode((CDoc *)this) )
                            *((_DWORD *)this + 1216) |= 0x10000000u;
                          goto LABEL_53;
                        }
                        if ( v19 != 67 )
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
                          v29 = *((_QWORD *)v15 + 7);
                          if ( v29 )
                            v30 = *(struct CMarkup **)(v29 + 104);
                          else
                            v30 = (struct CMarkup *)*((_QWORD *)v15 + 6);
                          goto LABEL_170;
                        }
                        v72 = this[544];
                        if ( !v72 )
                        {
                          if ( !CDoc::GetActiveElement((CDoc *)this) )
                          {
                            v73 = *((_QWORD *)v575 + 7);
                            if ( v73 )
                              v30 = *(struct CMarkup **)(v73 + 104);
                            else
                              v30 = (struct CMarkup *)*((_QWORD *)v575 + 6);
LABEL_170:
                            if ( *((_QWORD *)v30 + 18) )
                              v30 = (struct CMarkup *)*((_QWORD *)v30 + 18);
                            if ( (*((_DWORD *)v30 + 187) & 0x4000000) != 0 )
                            {
                              v75 = (COptionsHolder *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 128);
                              if ( v75 )
                              {
                                if ( (*((_DWORD *)v30 + 187) & 0x4000000) != 0 )
                                  v76 = *((_QWORD *)v30 + 44);
                                else
                                  v76 = 0;
                                v77 = COptionsHolder::COptionsHolder(v75, *(struct CWindow **)(v76 + 120));
                                v74 = v77;
                                if ( v77 )
                                {
                                  v78 = 0;
                                  *(_QWORD *)plLbound = v77;
                                  do
                                  {
                                    if ( v22 == dword_18158CE40[4 * v78] )
                                      break;
                                    ++v78;
                                  }
                                  while ( v78 < 9 );
                                  *(_QWORD *)&String1.vt = 16LL * (int)v78;
                                  v79 = *(_DWORD *)&algn_18158CE44[*(_QWORD *)&String1.vt];
                                  if ( v79 )
                                    *(_QWORD *)rgIndices = CBase::OpenParentUnit(
                                                             (CBase *)this,
                                                             (struct CBase *)this,
                                                             v79,
                                                             0);
                                  Text = COptionsHolder::PrivateQueryInterface(v74, &IID_IHTMLOptionsHolder, &ppvData);
                                  if ( !Text )
                                  {
                                    if ( a6 )
                                    {
                                      v80 = *(_OWORD *)&a6->vt;
                                      pRecInfo = a6->pRecInfo;
                                    }
                                    else
                                    {
                                      v80 = *(_OWORD *)&pvarg.vt;
                                      pRecInfo = pvarg.pRecInfo;
                                    }
                                    *(_OWORD *)v607 = v80;
                                    *(_QWORD *)&v607[16] = pRecInfo;
                                    COptionsHolder::put_execArg(
                                      (struct COptionsHolder *)((char *)v74 + 48),
                                      (struct tagVARIANT *)v607);
                                    Text = GetFindText(&bstrString);
                                    if ( !Text )
                                    {
                                      BASICPROPPARAMS::SetStringProperty(
                                        (BASICPROPPARAMS *)qword_1811F5878,
                                        bstrString,
                                        v74,
                                        (struct COptionsHolder *)((char *)v74 + 24),
                                        0);
                                      SysFreeString(bstrString);
                                      bstrString = 0;
                                      if ( v22 == 2121 )
                                      {
                                        v82 = (struct IDispatch *)ppvData;
                                        v83 = *(const unsigned __int16 **)&algn_18158CE44[*(_QWORD *)&String1.vt + 4];
                                        v84 = CDoc::GetActiveElement((CDoc *)this);
                                        v85 = CElement::GetMarkupPtr(v84);
                                        v86 = ShowModalDialogHelper(
                                                v85,
                                                v83,
                                                v82,
                                                *(struct COptionsHolder **)plLbound,
                                                0,
                                                0x2000000u);
                                        v74 = *(struct COptionsHolder **)plLbound;
                                        Text = v86;
                                        v27 = 1;
                                      }
                                      else
                                      {
                                        if ( v22 != 67 || (v87 = 1, !g_fBidiSupport) )
                                          v87 = 0;
                                        v88 = this[540];
                                        pvData = v87;
                                        *(_QWORD *)&pv.vt = 9;
                                        *(_OWORD *)&pv.decVal.Lo32 = (unsigned __int64)ppvData;
                                        memset(&v606, 0, sizeof(v606));
                                        if ( !v88
                                          || (*((_DWORD *)this + 1215) & 0x400000) != 0
                                          || (Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v88 + 32LL))(
                                                       v88,
                                                       &CGID_DocHostCommandHandler,
                                                       42,
                                                       v87,
                                                       &pv,
                                                       &v606)) != 0 )
                                        {
                                          CDoc::EnsureBackupUIHandler((CDoc *)this);
                                          v89 = this[539];
                                          if ( v89 )
                                          {
                                            *(_QWORD *)plLbound = 0;
                                            Text = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, LONG *))v89)(
                                                     v89,
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
                                                       &v606);
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
                                v74 = 0;
                              }
                              Text = -2147024882;
                            }
                            else
                            {
                              v74 = 0;
                            }
LABEL_203:
                            v90 = ((unsigned __int64)v74 + 48) & -(__int64)(v74 != 0);
                            if ( v90 )
                              (*(void (__fastcall **)(__int64, LONGLONG, __int64, __int64))(*(_QWORD *)v90 + 16LL))(
                                v90,
                                llVal,
                                v20,
                                v28);
                            if ( ppvData )
                              (*(void (__fastcall **)(void *, LONGLONG, __int64, __int64))(*(_QWORD *)ppvData + 16LL))(
                                ppvData,
                                llVal,
                                v20,
                                v28);
                            if ( *(_QWORD *)rgIndices )
                              CBase::CloseParentUnit((CBase *)this, *(struct CParentUndoUnit **)rgIndices, Text);
                            p_pvarg = &pvarg;
                            goto LABEL_210;
                          }
                          v72 = CDoc::GetActiveElement((CDoc *)this);
                        }
                        v30 = CElement::GetMarkupPtr(v72);
                        goto LABEL_170;
                      }
                      v31 = *((_DWORD *)this + 1219);
                      *((_DWORD *)this + 1219) = v31 | 0x400;
                      v32 = CDoc::EditUndo((CDoc *)this);
                      goto LABEL_55;
                    }
                    v33 = CDocument::Markup(v575);
                    v34 = CMarkup::Window(v33);
                    v35 = COmWindowProxy::Fire_onbeforeunload(v34, 1);
                    Text = 0;
                    if ( !a7 )
                      goto LABEL_1651;
                    a7->vt = 11;
                    a7->iVal = -(v35 != 0);
LABEL_1650:
                    if ( !v7 )
                      goto LABEL_1652;
LABEL_1651:
                    CDoc::DeferUpdateUI((CDoc *)this);
                    goto LABEL_1652;
                  }
LABEL_1451:
                  v498 = *((_DWORD *)this + 1217);
                  if ( (v498 & 0x800) != 0 )
                    goto LABEL_231;
                  iVal = 0;
                  v500 = *((_DWORD *)this + 1215);
                  plLbound[0] = v500;
                  if ( v579 == 93 && (v500 & 1) == 0
                    || v579 == 15038
                    || (v498 & 0x80u) != 0
                    || (unsigned __int8)IEConfiguration_GetBool(268435481, v579, v20, v28) )
                  {
                    a5 = 0;
                    if ( !a6 || a6->vt != 2 )
                      goto LABEL_1464;
                    a6->iVal &= ~1u;
                  }
                  else if ( !a6 )
                  {
                    goto LABEL_1464;
                  }
                  if ( a6->vt == 2 )
                    iVal = a6->iVal;
LABEL_1464:
                  v501 = iVal | 1;
                  if ( a5 != 2 )
                    v501 = iVal;
                  v502 = v501 | 0x1000000;
                  if ( v22 != 15038 )
                    v502 = v501;
                  if ( (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  {
                    v503 = CDoc::PrimaryMarkup((CDoc *)this);
                    UrlRaw = CMarkup::GetUrlRaw(v503);
                    v505 = L"about:blank";
                    if ( UrlRaw )
                      v505 = UrlRaw;
                    if ( *v505 && !wcscmp_0(v505, L"outday://") )
                      *((_DWORD *)this + 1215) |= 0x400000u;
                  }
                  if ( v22 == 27 )
                  {
                    if ( a6 && (a6->vt & 0x6000) == 0x6000 )
                    {
                      parray = a6->parray;
LABEL_1481:
                      if ( a6->vt == 8 )
                      {
                        bstrVal = a6->bstrVal;
LABEL_1484:
                        v508 = a5;
                        Text = CDoc::PrintHandler((CDoc *)this, v575, bstrVal, 0, v502, parray, a5, a6, a7, 0);
                        if ( Text )
                          goto LABEL_1652;
                        if ( (*((char *)this + 4868) < 0
                           || (unsigned __int8)IEConfiguration_GetBool(268435481, llVal, v20, v28))
                          && v22 != 15038 )
                        {
                          ++*((_DWORD *)this + 1237);
                        }
                        *((_DWORD *)this + 1215) ^= (*((_DWORD *)this + 1215) ^ plLbound[0]) & 0x400000;
LABEL_1585:
                        if ( v22 >= 0xE19 )
                        {
                          if ( v22 <= 0xE73 )
                          {
                            CodePageFromMenuID = GetCodePageFromMenuID(v22);
                            *(_QWORD *)&v606.vt = GetThreadStateUI();
                            if ( CodePageFromMenuID == -1 )
                            {
                              if ( v22 != 3699
                                || (IsCpAutoDetect = CDoc::IsCpAutoDetect((CDoc *)this),
                                    CDoc::SetCpAutoDetect((CDoc *)this, IsCpAutoDetect == 0),
                                    !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this))
                                || !(unsigned int)CMLang::IsMLangAvailable((CMLang *)&g_MLang) )
                              {
LABEL_1603:
                                ++*(_DWORD *)(*(_QWORD *)&v606.vt + 604LL);
                                goto LABEL_53;
                              }
                              CodePageFromMenuID = 50001;
                              if ( g_cpDefault == 932 )
                                CodePageFromMenuID = 50932;
                            }
                            v547 = this[12];
                            if ( v547 )
                            {
                              v548 = (_DWORD)this[556] & 0x40000000;
                              v549 = CInPlace::_hwnd_Get(v547);
                              if ( !(unsigned int)CMLang::ValidateCodePage(
                                                    (CMLang *)&g_MLang,
                                                    g_cpDefault,
                                                    CodePageFromMenuID,
                                                    v549,
                                                    1,
                                                    v548) )
                              {
                                v550 = this[544];
                                v551 = v550 ? CElement::GetMarkupPtr(v550) : CDocument::Markup(v575);
                                FrameOrPrimaryMarkup = CMarkup::GetFrameOrPrimaryMarkup(v551, 1);
                                v553 = FrameOrPrimaryMarkup;
                                if ( FrameOrPrimaryMarkup )
                                {
                                  v554 = CMarkup::Root(FrameOrPrimaryMarkup);
                                  CNotification::CNotification((CNotification *)&v588);
                                  v555 = CWindowBarProp::SecurityContext(v554);
                                  CNotification::Initialize(&v588, 59, v554, v555, CodePageFromMenuID, 0);
                                  if ( !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this)
                                    && !(unsigned int)CMarkup::HaveCodePageMetaTag(v553) )
                                  {
                                    CDoc::SaveDefaultCodepage((CDoc *)this, CodePageFromMenuID);
                                  }
                                  CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v588);
                                  CMarkup::BubbleDownCodePage(v553, CodePageFromMenuID);
                                  v556 = CMarkup::Window(v553);
                                  CPSrc = CMarkup::GetCPSrc(v553);
                                  CodePage = CMarkup::GetCodePage(v553);
                                  COmWindowProxy::ExecRefresh(v556, 5, CodePage, CPSrc);
                                }
                              }
                            }
                            goto LABEL_1603;
                          }
                          a5 = v508;
                        }
                        goto LABEL_1605;
                      }
LABEL_1483:
                      bstrVal = 0;
                      goto LABEL_1484;
                    }
                  }
                  else
                  {
                    parray = 0;
                    if ( v22 != 15038 )
                      goto LABEL_1483;
                  }
                  parray = 0;
                  if ( !a6 )
                    goto LABEL_1483;
                  goto LABEL_1481;
                }
                v50 = 3;
                goto LABEL_104;
              }
              if ( v19 != 71 )
              {
                switch ( v19 )
                {
                  case 0x5Du:
                    goto LABEL_1451;
                  case 0x7D0u:
                  case 0x7D1u:
                    if ( v19 == 2000 )
                      v50 = 1;
                    else
                      v50 = 2;
LABEL_104:
                    v51 = this[12];
                    llVal = 0;
                    if ( v51 )
                      v52 = (CInPlace *)*((_QWORD *)v51 + 10);
                    else
                      v52 = this[8];
                    bstrString = 0;
                    if ( !v52 )
                    {
                      Text = -2147467259;
                      goto LABEL_231;
                    }
                    v53 = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, BSTR *, __int64))v52)(
                            v52,
                            &IID_IOleCommandTarget,
                            &bstrString,
                            2322);
                    llVal = 0;
                    Text = v53;
                    if ( v53 )
                      goto LABEL_231;
                    v54 = (*(__int64 (__fastcall **)(BSTR, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)bstrString
                                                                                                  + 32LL))(
                            bstrString,
                            0,
                            v50,
                            0,
                            0,
                            0);
                    v55 = bstrString;
                    Text = v54;
LABEL_111:
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v55 + 16LL))(v55);
                    goto LABEL_231;
                  case 0x7D3u:
                    if ( (*((_DWORD *)this + 1217) & 0x800) == 0 )
                    {
                      if ( (Microsoft_IEEnableBits & 0x10000) != 0 )
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, MSHTML_PRINTPREVIEW_START, 0, 1, &v606);
                      if ( a6 && a6->vt == 8 )
                        v49 = a6->bstrVal;
                      else
                        v49 = 0;
                      Text = CDoc::PrintHandler((CDoc *)this, v575, v49, 0, 0, 0, a5, a6, a7, 1);
                      if ( (Microsoft_IEEnableBits & 0x10000) != 0 )
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, MSHTML_PRINTPREVIEW_STOP, 0, 1, &v606);
                      goto LABEL_1647;
                    }
                    goto LABEL_231;
                }
                if ( v19 != 2004 )
                {
                  if ( v19 != 2010 )
                    goto LABEL_231;
                  v41 = 1;
LABEL_140:
                  v26 = CDoc::DelegateShowPrintingDialog((CDoc *)this, a6, v41);
LABEL_28:
                  Text = v26;
LABEL_1652:
                  CDoc::CLock::~CLock((CDoc::CLock *)v603);
                  return (unsigned int)Text;
                }
                v42 = this[540];
                if ( v42 )
                {
                  llVal = a5;
                  if ( a5 != 2 && (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                    Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v42 + 32LL))(
                             v42,
                             &CGID_DocHostCommandHandler,
                             v579,
                             a5,
                             a6,
                             a7);
                }
                if ( Text < 0 )
                {
                  CDoc::EnsureBackupUIHandler((CDoc *)this);
                  v43 = this[539];
                  if ( !v43 )
                    goto LABEL_1583;
                  bstrString = 0;
                  memset(&pv, 0, sizeof(pv));
                  memset(&pvarg, 0, sizeof(pvarg));
                  Text = (**(__int64 (__fastcall ***)(CInPlace *, GUID *, BSTR *))v43)(
                           v43,
                           &IID_IOleCommandTarget,
                           &bstrString);
                  if ( Text )
                  {
                    VariantClear(&pvarg);
                    goto LABEL_1652;
                  }
                  v44 = this[103];
                  v45 = this[51];
                  pv.vt = 13;
                  v46 = this[50];
                  v47 = *(_QWORD *)(*((_QWORD *)v44 + 15) + 120LL);
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
                               v47,
                               &pvarg,
                               v46,
                               v45,
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
                  v27 = 1;
                  if ( Text == 1 )
                    Text = -2147221245;
                  goto LABEL_231;
                }
LABEL_1605:
                if ( Text != -2147221248 )
                  goto LABEL_1639;
                if ( v22 != 15031 || !(unsigned __int8)IEConfiguration_GetBool(268435481, llVal, v20, v28) )
                {
                  *((_QWORD *)&v600 + 1) = v581;
                  v601 = &v598;
                  *(_QWORD *)&v598 = __PAIR64__(a5, v579);
                  LODWORD(v600) = 0;
                  *((_QWORD *)&v598 + 1) = v7;
                  v599 = a7;
                  if ( this[544] )
                  {
                    if ( ((_DWORD)this[608] & 0x40000) != 0 )
                    {
                      v559 = 1;
                      CDoc::BeginUserInitiatedAction((CDoc *)this, 1);
                    }
                    else
                    {
                      v559 = 0;
                    }
                    Text = CDoc::RouteCTElement((CDoc *)this, this[544], (struct CDoc::CTArg *)&v600, v575);
                    if ( v559 )
                      CDoc::EndUserInitiatedAction((CDoc *)this);
                    if ( Text != -2147221248 )
                      goto LABEL_1639;
                  }
                  if ( CDoc::GetActiveElement((CDoc *)this) )
                  {
                    v560 = CDoc::GetActiveElement((CDoc *)this);
                    v561 = CWindowBarProp::SecurityContext(v560);
                    v562 = CDocument::Markup(v575);
                    NodeInMarkup = CTreeNode::GetNodeInMarkup(v561, v562);
                    if ( NodeInMarkup )
                    {
                      ElementClient = (struct CElement *)SP<Tree::CIE9DocumentLayout>::operator->(NodeInMarkup);
                      v565 = v575;
                    }
                    else
                    {
                      v565 = v575;
                      v566 = CDocument::Markup(v575);
                      ElementClient = CMarkup::GetElementClient(v566);
                    }
                    if ( ElementClient )
                    {
                      Text = CDoc::RouteCTElement((CDoc *)this, ElementClient, (struct CDoc::CTArg *)&v600, v565);
                      if ( Text != -2147221248 )
                      {
                        v567 = a5;
LABEL_1641:
                        if ( v22 == 15 && !(unsigned int)CDoc::HasSelection((CDoc *)this) )
                        {
                          v448 = Text == 0;
                          if ( Text < 0 )
                            goto LABEL_1648;
                          goto LABEL_1644;
                        }
LABEL_1647:
                        v448 = Text == 0;
LABEL_1648:
                        if ( !v448 )
                          goto LABEL_1652;
                        goto LABEL_1649;
                      }
                    }
                  }
                }
LABEL_441:
                v195 = this[126];
                if ( (!v195 || !*((_BYTE *)v195 + 38) || !*((_DWORD *)this + 1231))
                  && (int)CServer::State(this) >= 3
                  && (*((char *)this + 4868) >= 0 || v22 != 2315) )
                {
                  v196 = v583;
                  *(_QWORD *)&String1.vt = 0;
                  if ( v583 )
                    goto LABEL_1625;
                  SelectionMarkup = CDoc::GetSelectionMarkup((CDoc *)this, (struct CMarkup **)&v583);
                  v196 = v583;
                  if ( !v583 )
                  {
                    if ( CDoc::GetActiveElement((CDoc *)this) )
                    {
                      v198 = CDoc::GetActiveElement((CDoc *)this);
                      v196 = (struct IUnknown *)CElement::GetMarkupPtr(v198);
                      v583 = v196;
                    }
                    else
                    {
                      v196 = v583;
                    }
                  }
                  if ( SelectionMarkup >= 0 && v196 )
                  {
LABEL_1625:
                    Text = CMarkup::EnsureEditRouter((CMarkup *)v196, (struct CEditRouter **)&String1);
                    if ( Text >= 0 )
                    {
                      CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&v606);
                      EditContext = CMarkup::GetEditContext((CMarkup *)v583);
                      v569 = v581;
                      v570 = EditContext;
                      if ( v581 && (unsigned __int8)_(v581, &CGID_MSHTML) )
                      {
                        if ( v22 - 15 <= 1 )
                        {
                          v27 = 0;
LABEL_1633:
                          *((_DWORD *)v570 + 10) &= ~0x800u;
                          *((_DWORD *)v570 + 10) |= v27 << 11;
                          if ( v27 )
                            CDoc::CDOMTextInputScope::Init((CDoc::CDOMTextInputScope *)&v606, (struct CDoc *)this, 2);
                          *((_DWORD *)v570 + 10) |= 0x400u;
                          goto LABEL_1636;
                        }
                        if ( v22 == 26 || v22 - 2500 <= 1 )
                          goto LABEL_1633;
                      }
LABEL_1636:
                      v567 = a5;
                      Text = CEditRouter::ExecEditCommand(
                               *(CEditRouter **)&String1.vt,
                               v569,
                               v579,
                               a5,
                               v7,
                               a7,
                               v583,
                               (struct CMarkup *)v583,
                               (struct CDoc *)this);
                      if ( v570 == CMarkup::GetEditContext((CMarkup *)v583) )
                        *((_DWORD *)v570 + 10) &= 0xFFFFF3FF;
                      CDoc::CDOMTextInputScope::~CDOMTextInputScope((CDoc::CDOMTextInputScope *)&v606);
LABEL_1640:
                      if ( Text == -2147221248 )
                      {
LABEL_1644:
                        if ( CDoc::EntityHasFocus((CDoc *)this) )
                        {
                          FocusedEntity = CDoc::GetFocusedEntity((CDoc *)this);
                          if ( FocusedEntity )
                            Text = CEntity::Exec(FocusedEntity, v581, v579, v567, v7, a7);
                        }
                        goto LABEL_1647;
                      }
                      goto LABEL_1641;
                    }
                  }
                }
LABEL_1639:
                v567 = a5;
                goto LABEL_1640;
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
                llVal = a5;
                if ( v57 && a5 != 2 )
                {
                  Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v57 + 32LL))(
                           v57,
                           &CGID_DocHostCommandHandler,
                           v579,
                           a5,
                           a6,
                           a7);
                  if ( Text >= 0 )
                    goto LABEL_137;
                  llVal = a5;
                }
                v58 = this[12];
                if ( v58 )
                {
                  bstrString = 0;
                  v59 = 1;
                  if ( a6 && a6->vt == 8 )
                    bstrString = a6->bstrVal;
                  if ( (_DWORD)llVal == 2 )
                  {
                    ppvData = (void *)46;
                    v361 = (unsigned int)CTQueryStatus(
                                           *((struct IUnknown **)v58 + 10),
                                           0,
                                           1u,
                                           (struct _tagOLECMD *const)&ppvData,
                                           0) == 0;
                    v60 = bstrString;
                    if ( v361 && HIDWORD(ppvData) == 3 )
                    {
                      v59 = 0;
                      if ( !bstrString )
                        goto LABEL_131;
                    }
                  }
                  else
                  {
                    v60 = bstrString;
                  }
                  v61 = *((_QWORD *)v575 + 7);
                  if ( v61 )
                    v62 = *(struct CMarkup **)(v61 + 104);
                  else
                    v62 = (struct CMarkup *)*((_QWORD *)v575 + 6);
                  Text = CDoc::PromptSave((CDoc *)this, v62, 1, v59, v60);
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
                         v581,
                         v579,
                         a5,
                         a6,
                         a7);
                goto LABEL_118;
              }
LABEL_1655:
              _report_securityfailure(1);
            }
            if ( v19 <= 0x85B )
            {
              if ( v19 != 2139 )
              {
                switch ( v19 )
                {
                  case 0x849u:
                    goto LABEL_46;
                  case 0x84Eu:
                    v71 = htmlDesignModeOff;
                    break;
                  case 0x84Fu:
                    v71 = htmlDesignModeOn;
                    break;
                  case 0x852u:
                  case 0x853u:
                  case 0x857u:
                    goto LABEL_345;
                  case 0x85Au:
                    v63 = CDocument::Markup(v575);
                    if ( CMarkup::HasWindow(v63) )
                    {
                      v64 = CMarkup::Window(v63);
                      if ( *((_QWORD *)COptionsHolder::SecurityContext(v64) + 14) )
                      {
                        v65 = CMarkup::Window(v63);
                        v66 = COptionsHolder::SecurityContext(v65);
                        v67 = CMarkup::Window(v63);
                        v68 = COptionsHolder::SecurityContext(v67);
                        CWindow::ReleaseMarkupPending(v66, *((struct CMarkup **)v68 + 14), 1);
                        goto LABEL_53;
                      }
                    }
                    if ( !a6 || a6->vt != 11 || (v69 = 0, v27 = 1, a6->iVal != -1) )
                      v69 = 1;
                    inserted = CMarkup::ExecStop(v63, 1, v69, 1);
                    goto LABEL_306;
                  default:
                    goto LABEL_231;
                }
                inserted = CDoc::SetDesignMode((CDoc *)this, v575, v71);
                goto LABEL_306;
              }
              goto LABEL_514;
            }
            if ( v19 == 2141 || v19 == 2142 || v19 == 2143 || v19 == 2144 || v19 == 2145 )
            {
              if ( CDoc::GetActiveElement((CDoc *)this) )
              {
                v98 = CDoc::GetActiveElement((CDoc *)this);
                if ( CElement::GetWindowedMarkupContext(v98) )
                {
                  v99 = CDoc::GetActiveElement((CDoc *)this);
                  WindowedMarkupContext = CElement::GetWindowedMarkupContext(v99);
                  bstrString = (BSTR)CMarkup::GetCodepageSettings(WindowedMarkupContext);
                  v101 = bstrString;
                  if ( bstrString )
                  {
                    v102 = v22 - 2141;
                    LOBYTE(pvt[0]) = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                    if ( LOBYTE(pvt[0]) )
                      BaselineFontPrivate = CDoc::GetBaselineFontPrivate((CDoc *)this);
                    else
                      BaselineFontPrivate = CDoc::GetBaselineFont((CDoc *)this);
                    if ( BaselineFontPrivate != v102 )
                    {
                      v104 = this[126];
                      v105 = (wchar_t *)&Source;
                      v361 = *((_BYTE *)v104 + 56) == 0;
                      Buffer = 0;
                      if ( v361 )
                        v105 = L"\\Scripts";
                      LODWORD(v575) = 12;
                      ppvData = v105;
                      v106 = -1;
                      do
                        ++v106;
                      while ( *(_WORD *)(*((_QWORD *)v104 + 184) + 2 * v106) );
                      if ( (int)UIntAdd(0xCu, v106, (unsigned int *)&v575) < 0 )
                        goto LABEL_273;
                      if ( (int)UIntAdd((unsigned int)v575, 0xEu, (unsigned int *)&v575) < 0 )
                        goto LABEL_273;
                      v107 = -1;
                      do
                        ++v107;
                      while ( *((_WORD *)ppvData + v107) );
                      if ( (int)UIntAdd((unsigned int)v575, v107, (unsigned int *)&v575) < 0 )
                        goto LABEL_273;
                      v108 = 2LL * (unsigned int)v575;
                      if ( !is_mul_ok((unsigned int)v575, 2u) )
                        v108 = -1;
                      pszSubKey = (LPCWSTR)operator new[](v108, (const struct MemoryProtection::leaf_t *)&leaf);
                      if ( pszSubKey )
                      {
                        v109 = this[126];
                        BufferCount = 0;
                        StringCchPrintfExW(
                          (wchar_t *)pszSubKey,
                          (unsigned int)v575,
                          &Buffer,
                          &BufferCount,
                          0,
                          L"%s%s%s\\",
                          *((_QWORD *)v109 + 184),
                          L"\\International",
                          ppvData);
                        v101 = bstrString;
                        pvData = v102;
                        v110 = this[126];
                        v111 = *((_DWORD *)bstrString + 2);
                        plLbound[0] = v111;
                        if ( !*((_BYTE *)v110 + 56) )
                        {
                          v112 = DefaultSidForCodePage(v111);
                          plLbound[0] = RegistryAppropriateSidFromSid(v112);
                        }
                        v113 = CListenerDispatch::GetThis((CInPlace *)((char *)this[126] + 112));
                        v114 = (CInPlace *)((char *)this[126] + 112);
                        ppvData = v113;
                        rgIndices[0] = CImplAry::Size(v114);
                        v115 = rgIndices[0];
                        if ( rgIndices[0] > 0 )
                        {
                          v116 = pszSubKey;
                          v117 = plLbound[0];
                          v118 = (char *)ppvData;
                          do
                          {
                            v119 = *(_DWORD *)(*(_QWORD *)v118 + 8LL);
                            if ( !*((_BYTE *)this[126] + 56) )
                            {
                              v120 = DefaultSidForCodePage(v119);
                              v121 = RegistryAppropriateSidFromSid(v120);
                              v115 = rgIndices[0];
                              v118 = (char *)ppvData;
                              v119 = v121;
                            }
                            if ( v119 == v117 )
                            {
                              *(_WORD *)(*(_QWORD *)v118 + 2LL) = v102;
                              _ultow_s(v119, Buffer, BufferCount, 10);
                              v122 = IsProtectedModeProcess();
                              v123 = 3;
                              if ( v122 )
                              {
                                SHSetValueW(HKEY_CURRENT_USER, v116, L"IEFontSize", 3u, &pvData, 4u);
                                if ( LOBYTE(pvt[0]) )
                                  SHSetValueW(HKEY_CURRENT_USER, v116, L"IEFontSizePrivate", 3u, &pvData, 4u);
                              }
                              else
                              {
                                if ( v117 - 3 <= 0x25 )
                                  v123 = v117;
                                if ( (int)StringCchPrintfW((unsigned __int16 *)v607, 0x10u, L"%d", v123) >= 0 )
                                {
                                  SetBinaryExt(
                                    SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizeExt[0],
                                    2,
                                    (unsigned int)v607,
                                    (unsigned int)&pvData,
                                    4);
                                  if ( LOBYTE(pvt[0]) )
                                    SetBinaryExt(
                                      SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizePrivateExt[0],
                                      2,
                                      (unsigned int)v607,
                                      (unsigned int)&pvData,
                                      4);
                                }
                              }
                              v115 = rgIndices[0];
                              v118 = (char *)ppvData;
                            }
                            v118 += 8;
                            --v115;
                            ppvData = v118;
                            rgIndices[0] = v115;
                          }
                          while ( v115 > 0 );
                          v7 = *(VARIANTARG **)&v606.vt;
                          v9 = *(VARIANTARG **)&String1.vt;
                          v101 = bstrString;
                        }
                        Free_progressEventParams((void *)pszSubKey);
                      }
                      else
                      {
LABEL_273:
                        v101 = bstrString;
                      }
                    }
                    v101[1] = v102;
                    *((_WORD *)this + 2860) = v102;
                    v101[2] = v102;
                    *((_DWORD *)this + 1217) |= 0x80000000;
                    v124 = this[126];
                    *((_WORD *)this + 2861) = v102;
                    v125 = *((_DWORD *)v101 + 2);
                    plLbound[0] = v125;
                    if ( !*((_BYTE *)v124 + 56) )
                    {
                      v126 = DefaultSidForCodePage(v125);
                      plLbound[0] = RegistryAppropriateSidFromSid(v126);
                    }
                    v127 = CImplAry::Size((CInPlace *)((char *)this[126] + 112));
                    v128 = CListenerDispatch::GetThis((CInPlace *)((char *)this[126] + 112));
                    if ( v127 > 0 )
                    {
                      v129 = plLbound[0];
                      do
                      {
                        v130 = *(_DWORD *)(*(_QWORD *)v128 + 8LL);
                        if ( !*((_BYTE *)this[126] + 56) )
                        {
                          v131 = DefaultSidForCodePage(v130);
                          v130 = RegistryAppropriateSidFromSid(v131);
                        }
                        if ( v129 == v130 )
                        {
                          *(_WORD *)(*(_QWORD *)v128 + 2LL) = *((_WORD *)this + 2860);
                          *(_WORD *)(*(_QWORD *)v128 + 4LL) = *((_WORD *)this + 2861);
                        }
                        --v127;
                        v128 = (struct CBase *)((char *)v128 + 8);
                      }
                      while ( v127 > 0 );
                      v9 = *(VARIANTARG **)&String1.vt;
                    }
                  }
                }
              }
              v132 = CDoc::GetActiveElement((CDoc *)this);
              v133 = CElement::GetMarkupPtr(v132);
              CMarkup::EnsureFormatCacheChange(v133, 0x80u);
              CDoc::ForceRelayout((CDoc *)this, 0);
              v134 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL);
              ++*(_DWORD *)(v134 + 604);
              COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v607);
              v135 = v579;
              *(_QWORD *)v607 = v581;
              *(_DWORD *)&v607[8] = v579;
              CNotification::CNotification((CNotification *)&v588);
              v136 = CDoc::PrimaryRoot((CDoc *)this);
              CNotification::Command((CNotification *)&v588, v136, v607, 0);
              CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v588);
              v137 = this[12];
              if ( v137 )
                v138 = (struct IUnknown *)*((_QWORD *)v137 + 10);
              else
                v138 = (struct IUnknown *)this[8];
              CTExec(v138, &CGID_ExplorerBarDoc, v135, 0, 0, 0);
              goto LABEL_53;
            }
            if ( v19 != 2221 )
            {
              if ( v19 != 2222 )
                goto LABEL_231;
              hKey = 0;
              cbData = 0;
              if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID\\{25336920-03F9-11CF-8FD0-00AA00686F13}", 0, 1u, &hKey) )
                goto LABEL_231;
              bstrString = 0;
              v92 = RegOpenKeyExW(hKey, L"InprocServer32", 0, 1u, (PHKEY)&bstrString);
              if ( !v92 )
              {
                cbData = 520;
                v92 = RegQueryValueExW((HKEY)bstrString, 0, 0, 0, (LPBYTE)Data, &cbData);
                RegCloseKey((HKEY)bstrString);
              }
              RegCloseKey(hKey);
              if ( v92 )
                goto LABEL_231;
              v93 = wcsrchr(Data, 0x5Cu);
              if ( v93 )
                *v93 = 0;
              v94 = -1;
              do
                ++v94;
              while ( Data[v94] );
              Text = StringCchCatNW(Data, 0x104u, L"\\readme.htm", 259 - v94);
              if ( Text >= 0 )
              {
                FileW = CreateFileW(Data, 0x80000000, 1u, 0, 3u, 0x80u, 0);
                if ( FileW != (HANDLE)-1LL )
                {
                  CloseHandle(FileW);
                  v96 = CDoc::FollowHyperlink(
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
                  Text = v96;
                }
LABEL_230:
                v27 = 1;
                goto LABEL_231;
              }
LABEL_1582:
              v27 = 1;
              goto LABEL_1583;
            }
            LODWORD(lpcbData) = 11;
            CDoc::ShowMessage((CDoc *)this, &v602, 0, 0, 0x5EDu, lpcbData, 0, 10570, 1001, &Source, &Source);
LABEL_53:
            Text = 0;
            goto LABEL_1649;
          }
          if ( v15 )
          {
            v139 = *((_QWORD *)v15 + 7);
            if ( v139 )
              v140 = *(struct CMarkup **)(v139 + 104);
            else
              v140 = (struct CMarkup *)*((_QWORD *)v15 + 6);
          }
          else
          {
            v141 = this[544];
            if ( v141 )
            {
              if ( *(__int64 (__fastcall **)())(*(_QWORD *)v141 + 1624LL) != _vtguard )
                goto LABEL_1655;
              Text = (*(__int64 (__fastcall **)(CInPlace *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v141 + 368LL))(
                       v141,
                       v581,
                       v579,
                       a5,
                       a6,
                       a7);
              if ( !Text )
                goto LABEL_231;
              v142 = this[544];
            }
            else
            {
              if ( !CDoc::GetActiveElement((CDoc *)this) )
                goto LABEL_302;
              if ( *(__int64 (__fastcall **)())(*(_QWORD *)CDoc::GetActiveElement((CDoc *)this) + 1624LL) != _vtguard )
                goto LABEL_1655;
              v143 = CDoc::GetActiveElement((CDoc *)this);
              Text = (*(__int64 (__fastcall **)(struct CElement *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v143 + 368LL))(
                       v143,
                       v581,
                       v579,
                       a5,
                       a6,
                       a7);
              if ( !Text )
                goto LABEL_231;
              v142 = CDoc::GetActiveElement((CDoc *)this);
            }
            v140 = CElement::GetMarkupPtr(v142);
          }
          if ( v140 )
          {
LABEL_305:
            inserted = CDoc::AddToFavorites((CDoc *)this, v140);
            goto LABEL_306;
          }
LABEL_302:
          v144 = *((_QWORD *)v575 + 7);
          if ( v144 )
            v140 = *(struct CMarkup **)(v144 + 104);
          else
            v140 = (struct CMarkup *)*((_QWORD *)v575 + 6);
          goto LABEL_305;
        }
        if ( v19 <= 0x912 )
        {
          if ( v19 == 2322 )
            goto LABEL_376;
          if ( v19 <= 0x8FC )
          {
            if ( v19 != 2300 )
            {
              switch ( v19 )
              {
                case 0x8DAu:
LABEL_345:
                  memset(&v606, 0, sizeof(v606));
                  VariantInit(&v606);
                  v163 = 0;
                  pvData = ConvertSBCMDID(v22);
                  plLbound[0] = 0;
                  if ( v22 == 2135 )
                  {
                    v606.vt = 3;
                    v606.lVal = 1;
LABEL_361:
                    v163 = &v606;
LABEL_362:
                    v168 = this[12];
                    if ( v168 )
                    {
                      v169 = (__int64 (__fastcall ***)(_QWORD, GUID *, BSTR *))*((_QWORD *)v168 + 10);
                      bstrString = 0;
                      if ( v169 )
                      {
                        v170 = (**v169)(v169, &IID_IOleCommandTarget, &bstrString);
                        llVal = 0;
                        Text = v170;
                        if ( !v170 )
                        {
                          Text = (*(__int64 (__fastcall **)(BSTR, const GUID *, _QWORD, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)bstrString + 32LL))(
                                   bstrString,
                                   &CGID_Explorer,
                                   pvData,
                                   (unsigned int)plLbound[0],
                                   v163,
                                   0);
                          (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                        }
                      }
                      else
                      {
                        Text = -2147467259;
                      }
                    }
                    if ( v606.vt == 13 && v606.llVal )
                      (*(void (__fastcall **)(LONGLONG, LONGLONG))(*v606.pllVal + 16))(v606.llVal, llVal);
                    goto LABEL_230;
                  }
                  if ( v22 != 2266 )
                  {
                    v606.vt = 3;
                    v167 = 6;
                    if ( v22 != 2130 )
                      v167 = 1;
                    v606.lVal = v167 | 0x20000;
                    goto LABEL_361;
                  }
                  v164 = this[544];
                  bstrString = 0;
                  Text = GetExecDocument((struct CDocument **)&bstrString, v164, v575);
                  if ( Text < 0 )
                    goto LABEL_1652;
                  if ( bstrString )
                  {
                    v165 = *((_QWORD *)bstrString + 7);
                    if ( v165 )
                      v166 = *(CMarkup **)(v165 + 104);
                    else
                      v166 = (CMarkup *)*((_QWORD *)bstrString + 6);
                    if ( !(unsigned int)CMarkup::IsPrimaryMarkup(v166) )
                    {
                      v606.vt = 13;
                      Text = CDocument::QueryInterface((CDocument *)bstrString, &IID_IUnknown, &v606.byref);
                      if ( Text )
                        goto LABEL_1652;
                      v163 = &v606;
                    }
                    plLbound[0] = 1;
                    goto LABEL_362;
                  }
LABEL_350:
                  Text = -2147467259;
                  goto LABEL_1652;
                case 0x8DEu:
                  if ( !this[544] )
                  {
                    *(_QWORD *)&String1.vt = 0;
                    v160 = CDoc::GetActiveElement((CDoc *)this);
                    v161 = CElement::GetMarkupPtr(v160);
                    if ( (unsigned int)CMarkup::EnsureCollectionCache(v161, 4) )
                      goto LABEL_344;
                    v162 = CMarkup::CollectionCache(v161);
                    if ( (unsigned int)CCollectionCache::GetElementAtIndex(v162, 4, 0, (struct CElement **)&String1) )
                      goto LABEL_344;
                    if ( *(__int64 (__fastcall **)())(**(_QWORD **)&String1.vt + 1624LL) != _vtguard )
                      _report_securityfailure(1);
                    Text = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(**(_QWORD **)&String1.vt + 368LL))(
                             *(_QWORD *)&String1.vt,
                             v581,
                             v579,
                             a5,
                             a6,
                             a7);
                    if ( Text )
LABEL_344:
                      Text = -2147221248;
                  }
                  goto LABEL_231;
                case 0x8E8u:
                  v152 = CDoc::InPlace((CDoc *)this);
                  v153 = CInPlace::_hwnd_Get(v152);
                  v154 = CDoc::InPlace((CDoc *)this);
                  v155 = CInPlace::_hwnd_Get(v154);
                  CMessage::CMessage((CMessage *)Data, v155, 0x7Bu, (unsigned __int64)v153, 0xFFFFFFFFLL);
                  v156 = CDoc::GetActiveElement((CDoc *)this);
                  v157 = CWindowBarProp::SecurityContext(v156);
                  Text = CMessage::SetNodeHit((CMessage *)Data, v157);
                  if ( Text )
                  {
                    CMessage::~CMessage((CMessage *)Data);
                    goto LABEL_1652;
                  }
                  v158 = CDoc::GetActiveElement((CDoc *)this);
                  v159 = CWindowBarProp::SecurityContext(v158);
                  Text = CDoc::PumpMessage((CDoc *)this, (struct CMessage *)Data, v159, 0);
                  CMessage::~CMessage((CMessage *)Data);
                  goto LABEL_231;
                case 0x8EAu:
                case 0x8EBu:
                  if ( (*((_DWORD *)this + 1215) & 0x40000000) != 0 )
                  {
                    inserted = CDoc::FollowHistory((CDoc *)this, v19 == 2283);
                  }
                  else
                  {
                    v151 = -1;
                    if ( v19 != 2282 )
                      v151 = 1;
                    inserted = CDoc::Travel((CDoc *)this, v151);
                  }
                  goto LABEL_306;
              }
              if ( v19 != 2295 )
              {
                if ( v19 != 2296 )
                  goto LABEL_231;
                if ( a6 && a6->vt == 11 )
                {
                  v145 = *((_QWORD *)v575 + 7);
                  if ( v145 )
                    v146 = *(CMarkup **)(v145 + 104);
                  else
                    v146 = (CMarkup *)*((_QWORD *)v575 + 6);
                  CMarkup::SetPrintTemplate(v146, a6->bVal != 0);
                  v147 = CMarkup::EnsureEditContext(v146);
                  if ( v147 )
                    *((_DWORD *)v147 + 10) |= 0x80u;
                  goto LABEL_53;
                }
                goto LABEL_131;
              }
              if ( a7 )
              {
                v148 = v575;
                Text = 0;
                a7->vt = 11;
                v149 = *((_QWORD *)v148 + 7);
                if ( v149 )
                  v150 = *(CMarkup **)(v149 + 104);
                else
                  v150 = (CMarkup *)*((_QWORD *)v148 + 6);
                a7->iVal = -((unsigned int)CMarkup::IsPrintTemplate(v150) != 0);
                goto LABEL_1650;
              }
LABEL_330:
              Text = -2147467261;
              goto LABEL_1652;
            }
            v20 = 3;
LABEL_837:
            v317 = 0;
            if ( v19 == 2300 && a6 && a6->vt == 3 )
              v317 = (a6->lVal & 0x7FF0000) != 0;
            v318 = this[540];
            if ( v318 )
              Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v318 + 32LL))(
                       v318,
                       &CGID_DocHostCommandHandler,
                       v19,
                       a5,
                       a6,
                       a7);
            if ( Text >= 0 )
              goto LABEL_1584;
            if ( ((v22 - 6041) & 0xFFFFFFFD) != 0 && !v317 )
            {
              v319 = this[544];
              v320 = v319 ? CElement::GetMarkupPtr(v319) : CDocument::Markup(v575);
              if ( v320 )
              {
                v321 = CMarkup::GetFrameOrPrimaryMarkup(v320, 1);
                if ( v321 )
                  CMarkup::Window(v321);
              }
            }
            Gwnd = GetGwnd();
            inserted = _GWPostMethodCallEx(Gwnd, 0, 0);
            goto LABEL_306;
          }
          switch ( v19 )
          {
            case 0x8FEu:
              if ( a6 && a6->vt == 3 )
              {
                lVal = a6->lVal;
                if ( ((*((_DWORD *)this + 1215) >> 4) & 1) != (lVal != 0) )
                {
                  CNotification::CNotification((CNotification *)&v588);
                  v361 = ((_DWORD)this[608] & 0x80000) == 0;
                  *((_DWORD *)this + 1215) ^= ((unsigned __int8)*((_DWORD *)this + 1215)
                                             ^ (unsigned __int8)(16 * lVal))
                                            & 0x10;
                  if ( !v361 )
                  {
                    v179 = *((_DWORD *)this + 45);
                    v180 = CDoc::PrimaryRoot((CDoc *)this);
                    CNotification::EnableInteraction1((CNotification *)&v588, v180, 0);
                    CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v588);
                    if ( !v179 )
                    {
                      if ( *((_DWORD *)this + 45) )
                        *((_DWORD *)this + 45) = 0;
                    }
                  }
                  v181 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + (unsigned int)tls_index)
                                               + 16LL)
                                   + 208LL);
                  if ( v181 )
                    CImgAnim::SetAnimState(v181, this, lVal == 0);
                }
                goto LABEL_53;
              }
              goto LABEL_131;
            case 0x906u:
              v176 = CDoc::PrimaryMarkup((CDoc *)this);
              ScriptCollection = CMarkup::GetScriptCollection(v176, 1);
              if ( ScriptCollection )
              {
                inserted = CScriptCollection::ViewSourceInDebugger(ScriptCollection, 0, 0);
                goto LABEL_306;
              }
              break;
            case 0x907u:
              v174 = this[809];
              if ( v174 && CPeerFactoryUrl::GetUrl(v174) )
              {
                Url = CPeerFactoryUrl::GetUrl(this[809]);
                inserted = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)Url + 32LL))(Url);
                goto LABEL_306;
              }
              break;
            case 0x90Cu:
              if ( !a6 || a6->vt != 11 )
                goto LABEL_131;
              *((_DWORD *)this + 1217) = *((_DWORD *)this + 1217) & 0xFFFFFEFF | (a6->iVal != 0 ? 0x100 : 0);
              *(GUID *)&v606.vt = CGID_MSHTML;
              CDoc::Exec((CDoc *)this, (const struct _GUID *)&v606, 0x90Eu, 0, a6, 0);
              goto LABEL_53;
            case 0x90Du:
              v173 = 0;
LABEL_380:
              inserted = CDoc::OnSettingsChange((CDoc *)this, v173, 0);
              goto LABEL_306;
            default:
              if ( v19 - 2320 > 1 )
                goto LABEL_231;
LABEL_376:
              CVariant::CVariant((CVariant *)&pvarg);
              v171 = CDocument::Markup(v575);
              GlyphTable = CMarkup::GetGlyphTable(v171);
              if ( a6 )
              {
                if ( a6->vt != 11 )
                {
LABEL_378:
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_231;
                }
                v199 = a6->iVal != 0;
LABEL_477:
                if ( !v199 && (v22 == 2327 || v22 == 2320) )
                  v22 = 2336;
                v201 = CDocument::Markup(v575);
                Text = CMarkup::EnsureGlyphTableExistsAndExecute(v201, v581, v22, a5, v7, a7);
                if ( !Text )
                {
                  if ( v22 != 2336 )
                  {
                    if ( ((((v202 = CDocument::Markup(v575), v203 = CMarkup::GetGlyphTable(v202), v22 == 2327)
                         || v22 == 2321)
                        && (*(_DWORD *)v203 ^= (*(_DWORD *)v203 ^ v199) & 1, v22 == 2327)
                        || v22 == 2322)
                       && (*(_DWORD *)v203 ^= (*(_DWORD *)v203 ^ (2 * v199)) & 2, v22 == 2327)
                       || v22 == 2323)
                      && (*(_DWORD *)v203 &= ~8u, *(_DWORD *)v203 |= 8 * v199, v22 == 2327)
                      || v22 == 2324 )
                    {
                      *(_DWORD *)v203 &= ~4u;
                      *(_DWORD *)v203 |= 4 * v199;
                      if ( v22 == 2327 )
                        goto LABEL_1661;
                    }
                    if ( v22 == 2325 )
                    {
LABEL_1661:
                      *(_DWORD *)v203 &= ~0x10u;
                      *(_DWORD *)v203 |= 16 * v199;
                      if ( v22 == 2327 )
                        goto LABEL_1660;
                    }
                    if ( v22 == 2320 )
                    {
LABEL_1660:
                      *(_DWORD *)v203 &= ~0x40u;
                      *(_DWORD *)v203 |= v199 << 6;
                      if ( v22 == 2327 )
                        goto LABEL_1659;
                    }
                    if ( v22 == 2326 )
                    {
LABEL_1659:
                      *(_DWORD *)v203 ^= (*(_DWORD *)v203 ^ (32 * v199)) & 0x20;
                      if ( v22 == 2327 )
                        goto LABEL_499;
                    }
                    if ( v22 == 2340 )
LABEL_499:
                      *(_DWORD *)v203 ^= (*(_DWORD *)v203 ^ (v199 << 7)) & 0x80;
                  }
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_1584;
                }
                goto LABEL_378;
              }
              if ( GlyphTable )
              {
                v199 = 0;
                if ( v22 != 2320 )
                {
                  if ( v22 == 2321 )
                  {
                    v200 = *(_DWORD *)GlyphTable;
                  }
                  else if ( v22 == 2322 )
                  {
                    v200 = *(_DWORD *)GlyphTable >> 1;
                  }
                  else if ( v22 == 2323 )
                  {
                    v200 = *(_DWORD *)GlyphTable >> 3;
                  }
                  else if ( v22 == 2324 )
                  {
                    v200 = *(_DWORD *)GlyphTable >> 2;
                  }
                  else if ( v22 == 2325 )
                  {
                    v200 = *(_DWORD *)GlyphTable >> 4;
                  }
                  else
                  {
                    if ( v22 != 2326 )
                    {
                      if ( v22 == 2327 )
                      {
                        LOBYTE(v199) = *(_BYTE *)GlyphTable != 0xFF;
                      }
                      else if ( v22 == 2340 )
                      {
                        v199 = (*(_DWORD *)GlyphTable & 0x80) == 0;
                      }
LABEL_472:
                      pvarg.vt = 11;
                      if ( !v199 )
                      {
                        pvarg.iVal = 0;
LABEL_476:
                        v7 = &pvarg;
                        v27 = 1;
                        goto LABEL_477;
                      }
LABEL_475:
                      pvarg.iVal = -1;
                      goto LABEL_476;
                    }
                    v200 = *(_DWORD *)GlyphTable >> 5;
                  }
                  v199 = (v200 & 1) == 0;
                  goto LABEL_472;
                }
                if ( (*(_BYTE *)GlyphTable & 0x40) != 0 )
                  goto LABEL_472;
              }
              v199 = 1;
              pvarg.vt = 11;
              goto LABEL_475;
          }
          Text = -2147418113;
          goto LABEL_231;
        }
        llVal = 2332;
        v20 = 2333;
        if ( v19 > 0x91C )
        {
          if ( v19 != 2333 && v19 != 2334 )
          {
            if ( v19 != 2335 )
            {
              if ( v19 != 2336 && (v19 != 2337 && v19 - 2338 > 1 || !a6->llVal) )
                goto LABEL_231;
              v184 = CDocument::Markup(v575);
              inserted = CMarkup::EnsureGlyphTableExistsAndExecute(v184, v581, v22, a5, a6, a7);
              goto LABEL_306;
            }
            goto LABEL_420;
          }
        }
        else if ( v19 != 2332 )
        {
          if ( v19 == 2323 || v19 == 2324 || v19 == 2325 || v19 == 2326 || v19 == 2327 )
            goto LABEL_376;
          if ( v19 != 2328 )
          {
            if ( v19 != 2331 )
              goto LABEL_231;
            if ( a7 )
            {
              v182 = CDocument::Markup(v575);
              DwnDoc = CMarkup::GetDwnDoc(v182);
              a7->vt = 3;
              if ( DwnDoc )
                LODWORD(DwnDoc) = CDwnDoc::GetBytesRead(DwnDoc);
              a7->lVal = (int)DwnDoc;
              goto LABEL_231;
            }
            goto LABEL_330;
          }
LABEL_420:
          v185 = CDocument::Markup(v575);
          v186 = v185;
          if ( a6 && a6->vt == 11 )
            v187 = a6->bVal != 0;
          else
            v187 = !CMarkup::IsShowZeroBorderAtDesignTime(v185);
          if ( v22 == 2328 )
          {
            CMarkup::SetShowZeroBorderAtDesignTime(v186, v187);
            CNotification::CNotification((CNotification *)&v588);
            ElementTopHelper = CMarkup::GetElementTopHelper(v186);
            CNotification::ZeroGrayChange((CNotification *)&v588, ElementTopHelper);
            CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v588);
            CDoc::Invalidate((CDoc *)this);
          }
          else
          {
            *((_DWORD *)this + 1216) &= ~0x10u;
            *((_DWORD *)this + 1216) |= 16 * v187;
          }
          Text = 0;
          *((_DWORD *)this[126] + 23) = *CDoc::_dwMiscFlags((CDoc *)this);
          TopLayoutElement = CMarkup::GetTopLayoutElement(v186);
          if ( TopLayoutElement )
            CElement::ResizeElement(TopLayoutElement, 0x800000u);
          COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v607);
          *(_QWORD *)v607 = v581;
          *(_DWORD *)&v607[8] = v579;
          CNotification::CNotification((CNotification *)&v588);
          if ( v22 == 2328 )
            v190 = CMarkup::Root(v186);
          else
            v190 = CDoc::PrimaryRoot((CDoc *)this);
          CNotification::Command((CNotification *)&v588, v190, v607, 0);
          CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v588);
          goto LABEL_1649;
        }
        if ( a6 && a6->vt == 11 )
        {
          bVal = a6->bVal;
          v192 = *((_DWORD *)this + 1428);
          if ( v22 == 2332 )
          {
            v193 = bVal != 0 ? 0x100 : 0;
            v194 = v192 & 0xFFFFFEFF;
          }
          else if ( v22 == 2333 )
          {
            v193 = bVal != 0 ? 0x200 : 0;
            v194 = v192 & 0xFFFFFDFF;
          }
          else
          {
            v193 = bVal != 0 ? 0x400 : 0;
            v194 = v192 & 0xFFFFFBFF;
          }
          *((_DWORD *)this + 1428) = v194 | v193;
          Text = 0;
          *((_DWORD *)this[126] + 23) = *CDoc::_dwMiscFlags((CDoc *)this);
          goto LABEL_441;
        }
        goto LABEL_231;
      }
      if ( v19 <= 0xF40 )
      {
        if ( v19 == 3904 )
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
                         v575,
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
        if ( v19 <= 0x97F )
        {
          if ( v19 != 2431 )
          {
            if ( v19 <= 0x963 )
            {
              if ( v19 != 2403 )
              {
                if ( v19 == 2341 )
                {
                  *((_DWORD *)this + 1215) |= 0x4000u;
                  goto LABEL_53;
                }
                if ( v19 != 2342 )
                {
                  switch ( v19 )
                  {
                    case 0x927u:
                      if ( a6 && a6->vt == 8 )
                      {
                        v216 = CDocument::Markup(v575);
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
                    case 0x92Eu:
                    case 0x92Fu:
                      *(_QWORD *)&String1.vt = 0;
                      v215 = CBase::OpenParentUnit((CBase *)this, (struct CBase *)this, 0x8D6u, 0);
                      Text = GetExecDocument((struct CDocument **)&String1, this[544], v575);
                      if ( Text >= 0 )
                        Text = CDocument::SetDocDirection(*(CDocument **)&String1.vt, (unsigned int)(v22 != 2350) + 1);
                      CBase::CloseParentUnit((CBase *)this, v215, Text);
                      goto LABEL_231;
                    case 0x942u:
                      if ( a6 )
                      {
                        if ( a6->vt == 8 )
                        {
                          v213 = a6->bstrVal;
                          if ( v213 )
                          {
                            v214 = CDocument::Markup(v575);
                            inserted = CDoc::SavePretransformedSource((CDoc *)this, v214, v213);
                            goto LABEL_306;
                          }
                        }
                      }
                      break;
                    case 0x943u:
LABEL_514:
                      v204 = this[544];
                      if ( v204 )
                        v205 = CElement::GetMarkupPtr(v204);
                      else
                        v205 = CDocument::Markup(v575);
                      if ( !v205
                        || (v206 = CMarkup::GetFrameOrPrimaryMarkup(v205, 1), (v207 = v206) == 0)
                        || (unsigned int)CMarkup::IsImageFile(v206) )
                      {
                        Text = 0;
                        goto LABEL_1584;
                      }
                      if ( v22 != 2139
                        || !(unsigned int)CMarkup::IsPrimaryMarkup(v207)
                        || !(unsigned int)CDoc::IsAggregatedByXMLMime((CDoc *)this) )
                      {
                        Text = CDoc::GetViewSourceFileName((CDoc *)this, psz, 0x823u, v207);
                        if ( Text < 0 )
                          goto LABEL_1583;
                        if ( (unsigned int)IsDefaultViewSourceEditor()
                          && (unsigned __int8)IEConfiguration_GetBool(268435500, v210, v211, v212)
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
                        goto LABEL_1584;
                      }
                      bstrString = 0;
                      v208 = CDOMStringMap::SecurityContext((CDOMStringMap *)this);
                      if ( (**(unsigned int (__fastcall ***)(struct CSecurityContext *, GUID *, BSTR *))v208)(
                             v208,
                             &IID_IOleCommandTarget,
                             &bstrString)
                        || !bstrString )
                      {
                        goto LABEL_231;
                      }
                      (*(void (__fastcall **)(BSTR, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)bstrString + 32LL))(
                        bstrString,
                        v581,
                        v579,
                        a5,
                        a6,
                        a7);
                      goto LABEL_526;
                    default:
                      goto LABEL_231;
                  }
LABEL_757:
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
                      v223 = *((_QWORD *)v575 + 7);
                      v224 = v223 ? *(_QWORD *)(v223 + 104) : *((_QWORD *)v575 + 6);
                      v219 = CIPrintCollection::CIPrintCollection(v222, *(struct CSecurityContext **)(v224 + 320));
                      if ( v219 )
                      {
                        v225 = *((_QWORD *)v575 + 7);
                        if ( v225 )
                          v226 = *(CMarkup **)(v225 + 104);
                        else
                          v226 = (CMarkup *)*((_QWORD *)v575 + 6);
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
                                v589 = *(_QWORD *)(v228 + 48);
                                v594 = 0;
                                v595 = 0;
                                v591 = 0;
                                v588 = 88;
                                v593 = v219;
                                v592 = 18436;
                                v590 = 0;
                                CNotification::SetElement((CNotification *)&v588, (struct CElement *)v228);
                                CMarkup::Notify(v226, (struct CNotification *)&v588, 0);
                              }
                            }
                          }
                        }
                        goto LABEL_600;
                      }
                    }
LABEL_897:
                    Text = -2147024882;
                    goto LABEL_1652;
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
                  goto LABEL_1651;
                }
                if ( !CDoc::GetActiveElement((CDoc *)this) )
                  goto LABEL_600;
                v229 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                if ( !v229 )
                  goto LABEL_897;
                v230 = CDoc::GetActiveElement((CDoc *)this);
                v231 = CElement::GetMarkupPtr(v230);
                v219 = CIPrintCollection::CIPrintCollection(v229, *((struct CSecurityContext **)v231 + 40));
                if ( !v219 )
                  goto LABEL_897;
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
                  goto LABEL_897;
                v238 = *((_QWORD *)v575 + 7);
                v239 = v238 ? *(_QWORD *)(v238 + 104) : *((_QWORD *)v575 + 6);
                v219 = CIPrintCollection::CIPrintCollection(v237, *(struct CSecurityContext **)(v239 + 320));
                if ( !v219 )
                  goto LABEL_897;
                v240 = CDocument::Window(v575);
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
            if ( v19 == 2405 )
            {
              v256 = *((_QWORD *)v575 + 7);
              if ( v256 )
                v257 = *(CMarkup **)(v256 + 104);
              else
                v257 = (CMarkup *)*((_QWORD *)v575 + 6);
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
            if ( v19 == 2408 )
            {
              if ( a6 && a6->vt == 3 )
              {
                if ( *((char *)this + 4868) >= 0 )
                {
                  if ( !(unsigned __int8)IEConfiguration_GetBool(268435481, 2300, 2139, 0xFFFFFFFFLL) )
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
                  v28 = 0xFFFFFFFFLL;
                }
                if ( !a6->lVal )
                {
                  v361 = (*((_DWORD *)this + 1237))-- == 1;
                  if ( v361 )
                  {
                    llVal = 0x4000;
                    if ( (*((_DWORD *)this + 1217) & 0x4000) != 0 )
                    {
                      v254 = v575;
                      if ( v575 )
                      {
                        if ( CDocument::Window(v575) )
                        {
                          *((_DWORD *)this + 1217) &= ~0x4000u;
                          v255 = CDocument::Window(v254);
                          CWindow::close((struct CWindow *)((char *)v255 + 48));
                        }
                      }
                    }
                  }
                }
                goto LABEL_231;
              }
              goto LABEL_757;
            }
            if ( v19 != 2411 )
            {
              switch ( v19 )
              {
                case 0x974u:
                  v246 = CDocument::Markup(v575);
                  v247 = v246;
                  if ( a6 && a6->vt == 11 )
                  {
                    v27 = a6->bVal != 0;
                  }
                  else if ( (unsigned int)CMarkup::HasEditContext(v246)
                         && (*((_BYTE *)CMarkup::GetEditContext(v247) + 40) & 2) != 0 )
                  {
                    v27 = 0;
                  }
                  if ( CMarkup::EnsureEditContext(v247) )
                  {
                    v248 = CMarkup::GetEditContext(v247);
                    *((_DWORD *)v248 + 10) &= ~2u;
                    *((_DWORD *)v248 + 10) |= 2 * v27;
                  }
                  goto LABEL_53;
                case 0x977u:
                  *((_DWORD *)this + 1217) = *((_DWORD *)this + 1217) & 0xFEFFFFFF
                                           | ~*((_DWORD *)this + 1217) & 0x1000000;
                  goto LABEL_53;
                case 0x979u:
                  if ( a6 && a6->vt == 11 )
                    v245 = a6->bVal != 0;
                  else
                    v245 = ((*((_DWORD *)this + 1217) >> 25) & 1) == 0;
                  *((_DWORD *)this + 1217) &= ~0x2000000u;
                  *((_DWORD *)this + 1217) |= v245 << 25;
                  goto LABEL_53;
              }
              if ( v19 != 2430 )
                goto LABEL_231;
              if ( a6 && a6->vt == 11 )
              {
                v243 = a6->bVal != 0 ? 0x4000000 : 0;
                v244 = *((_DWORD *)this + 1217) & 0xFBFFFFFF;
                goto LABEL_614;
              }
LABEL_131:
              Text = -2147024809;
              goto LABEL_1652;
            }
            v249 = CDocument::Markup(v575);
            if ( !(unsigned int)CMarkup::IsConnectedToPrimaryMarkup(v249) )
            {
              CMarkup::TearDownMarkup(v249, 1, 0);
              goto LABEL_53;
            }
LABEL_630:
            Text = -2147418113;
            goto LABEL_1652;
          }
          if ( !a7 )
            goto LABEL_131;
          VariantInit(a7);
          a7->vt = 19;
          NormZoomPercent = *((_DWORD *)this + 1245);
          goto LABEL_935;
        }
        if ( v19 <= 0x988 )
        {
          switch ( v19 )
          {
            case 0x988u:
              Text = 0;
              v272 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&String1.vt = v272;
              if ( !v272 || !a6 || a6->vt != 8 )
                goto LABEL_1649;
              if ( CMarkup::GetStyleState(v272) )
              {
                StyleState = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                CStr::~CStr((struct CMarkupStyleState *)((char *)StyleState + 8));
                v274 = *(CMarkup **)&String1.vt;
                v275 = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                if ( !(unsigned int)CStr::IsNull(v275) )
                {
                  v276 = CMarkup::GetStyleState(v274);
                  if ( (unsigned int)CStr::IsNull(v276) )
                    goto LABEL_1649;
                  v277 = CMarkup::GetStyleState(v274);
                  v278 = CDispSurface::UseRenderTarget(v277);
                  v279 = a6;
                  v280 = v278 - (struct IDispRenderTarget *)a6;
                  do
                  {
                    v281 = *(unsigned __int16 *)((char *)&v279->vt + v280);
                    v282 = v279->vt - v281;
                    if ( v282 )
                      break;
                    v279 = (struct tagVARIANT *)((char *)v279 + 2);
                  }
                  while ( v281 );
                  if ( !v282 )
                    goto LABEL_1649;
                }
                v283 = CMarkup::GetStyleState(v274);
                inserted = CStr::SetBSTR((struct CMarkupStyleState *)((char *)v283 + 8), a6->bstrVal);
                goto LABEL_306;
              }
              break;
            case 0x980u:
              CDoc::BeginUserInitiatedAction((CDoc *)this, 0);
              goto LABEL_53;
            case 0x981u:
              CDoc::EndUserInitiatedAction((CDoc *)this);
              goto LABEL_53;
            case 0x982u:
              Text = -2147024809;
              if ( !a6 || a6->vt != 21 )
                goto LABEL_1652;
              this[625] = (CInPlace *)a6->llVal;
              goto LABEL_53;
            case 0x984u:
              Text = 0;
              if ( a6 )
              {
                if ( a6->vt != 11 )
                  goto LABEL_131;
                v271 = a6->bVal;
                if ( (v271 == 0) == (((*((_DWORD *)this + 1215) >> 17) & 1) == 0) )
                  goto LABEL_1649;
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | (v271 != 0 ? 0x20000 : 0);
              }
              else
              {
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | ~*((_DWORD *)this + 1215) & 0x20000;
              }
              CDoc::NotifySelection(this, 17, 0);
              goto LABEL_1649;
            case 0x985u:
              Text = 0;
              v267 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v606.vt = v267;
              v268 = v267;
              if ( !v267 || !a6 || a6->vt != 11 )
                goto LABEL_1649;
              if ( CMarkup::GetStyleState(v267) )
              {
                CMarkup::CLock::CLock((CMarkup::CLock *)&String1, v268);
                v269 = *(_QWORD *)&v606.vt;
                v270 = a6->bVal != 0;
                *((_BYTE *)CMarkup::GetStyleState(*(CMarkup **)&v606.vt) + 24) = v270;
                if ( *(__int64 (__fastcall **)())(*(_QWORD *)v269 + 984LL) != _vtguard )
                  _report_securityfailure(1);
                Text = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v269 + 224LL))(v269, 3);
                CMarkup::CLock::~CLock((CMarkup::CLock *)&String1);
                goto LABEL_231;
              }
              break;
            case 0x986u:
              Text = 0;
              v265 = CDoc::PrimaryMarkup((CDoc *)this);
              v266 = v265;
              if ( !v265 || a7->vt != 11 )
                goto LABEL_1649;
              a7->iVal = 0;
              if ( CMarkup::GetStyleState(v265) )
              {
                if ( *((_BYTE *)CMarkup::GetStyleState(v266) + 24) )
                  a7->iVal = -1;
                goto LABEL_1650;
              }
              goto LABEL_897;
            case 0x987u:
              Text = 0;
              v261 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v606.vt = v261;
              if ( !v261 )
                goto LABEL_1649;
              a7->llVal = 0;
              if ( !CMarkup::GetStyleState(v261) )
              {
                Text = -2147024882;
                goto LABEL_1583;
              }
              if ( a7->vt != 8 )
                goto LABEL_1649;
              v262 = *(CMarkup **)&v606.vt;
              v263 = CMarkup::GetStyleState(*(CMarkup **)&v606.vt);
              if ( (unsigned int)CStr::IsNull(v263) )
                goto LABEL_1650;
              v264 = CMarkup::GetStyleState(v262);
              Text = CStr::AllocBSTR(v264, &a7->bstrVal);
              if ( Text < 0 )
              {
                a7->llVal = 0;
                goto LABEL_1583;
              }
              goto LABEL_1605;
            default:
              goto LABEL_231;
          }
LABEL_1406:
          Text = -2147024882;
          goto LABEL_231;
        }
        switch ( v19 )
        {
          case 0xE95u:
            if ( a7 )
            {
              if ( !this[126] )
              {
                Text = -2147221247;
                goto LABEL_1652;
              }
              a7->vt = 3;
              Text = 0;
              a7->lVal = *((_DWORD *)this[126] + 33);
              goto LABEL_1650;
            }
            goto LABEL_131;
          case 0xED8u:
            if ( !a6 )
              goto LABEL_757;
            if ( a6->vt == 13 )
            {
              punkVal = a6->punkVal;
              if ( punkVal )
              {
                if ( a7 )
                {
                  v96 = DevToolbarHelper::AddConsoleMessageReceiver(punkVal, a7);
                  goto LABEL_229;
                }
              }
            }
            break;
          case 0xED9u:
            if ( a6 && a6->vt == 19 )
            {
              inserted = DevToolbarHelper::RemoveConsoleMessageReceiver(a6->cyVal.Lo);
              goto LABEL_306;
            }
            goto LABEL_757;
          case 0xEDAu:
            Text = -2147024809;
            if ( !a6 || a6->vt != 8200 )
              goto LABEL_1652;
            CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
            v284 = a6->parray;
            *(_QWORD *)&v606.vt = v284;
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
                v286 = *(SAFEARRAY **)&v606.vt;
                v287 = 0;
                v288 = 0;
                memset(v607, 0, sizeof(v607));
                rgIndices[0] = 0;
                do
                {
                  if ( !Text )
                  {
                    Element = SafeArrayGetElement(v286, rgIndices, &v607[8 * v288]);
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
                           *(const unsigned __int16 **)v607,
                           *(const unsigned __int16 **)&v607[8],
                           *(const unsigned __int16 **)&v607[16],
                           *(const unsigned __int16 **)&v607[24],
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
          case 0xEDBu:
            Text = -2147024809;
            if ( !a7 )
              goto LABEL_1652;
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
            goto LABEL_1650;
          case 0xEDCu:
            if ( !a6 )
              goto LABEL_757;
            if ( a6->vt == 13 )
            {
              llVal = a6->llVal;
              if ( llVal )
              {
                if ( a7 )
                {
                  plLbound[0] = 0;
                  Text = CDebugCallbackNotificationHandlers::AddCallbackNotificationHandler(
                           (CDebugCallbackNotificationHandlers *)(this + 812),
                           (struct IUnknown *)llVal,
                           (unsigned int *)plLbound);
                  a7->vt = 19;
                  a7->lVal = plLbound[0];
                  goto LABEL_230;
                }
              }
            }
            break;
          case 0xEDDu:
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
LABEL_756:
        v27 = 1;
        goto LABEL_757;
      }
      if ( v19 <= 0x17A1 )
      {
        if ( v19 == 6049 )
        {
          if ( !a6 || a6->vt != 11 )
            goto LABEL_131;
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL)
                   + 578LL) = a6->iVal != 0;
          goto LABEL_53;
        }
        if ( v19 <= 0x1795 )
        {
          switch ( v19 )
          {
            case 0x1795u:
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
                goto LABEL_1650;
              }
              goto LABEL_330;
            case 0x1785u:
              if ( !a6 )
                goto LABEL_231;
              pvData = 0;
              v306 = CDoc::PrimaryMarkup((CDoc *)this);
              v307 = CMarkup::GetCodePage(v306);
              v308 = this[544];
              v309 = v307;
              plLbound[0] = 0;
              *(_QWORD *)&String1.vt = 0;
              Text = GetExecDocument((struct CDocument **)&String1, v308, v575);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
              v97 = Text < 0;
              if ( !Text )
              {
                v310 = CDoc::IsCpAutoDetect((CDoc *)this);
                Text = ShowMimeCSetMenu(this[126], (int *)&pvData, v309, a6->lVal, plLbound[0], v310);
                if ( !Text )
                {
                  v22 = pvData;
                  if ( pvData - 3609 > 0x5A )
                  {
                    if ( pvData - 2350 <= 1 )
                      CDoc::ExecHelper((CDoc *)this, v575, &CGID_MSHTML, pvData, 0, 0, 0);
                    goto LABEL_1649;
                  }
                  goto LABEL_1584;
                }
                goto LABEL_231;
              }
              goto LABEL_232;
            case 0x178Cu:
              if ( !a6 || a6->vt != 13 )
                goto LABEL_131;
              CDoc::SetPicsCommandTarget((CDoc *)this, (struct IOleCommandTarget *)a6->llVal);
              goto LABEL_53;
            case 0x1790u:
              if ( a6 )
              {
                if ( a6->vt == 8 )
                {
                  v304 = a6->bstrVal;
                  if ( v304 )
                  {
                    v305 = CDocument::Markup(v575);
                    inserted = CDoc::SetUrl((CDoc *)this, v305, v304, 0);
                    goto LABEL_306;
                  }
                }
              }
              goto LABEL_757;
            case 0x1791u:
              if ( !a7 )
                goto LABEL_131;
              a7->vt = 3;
              NormZoomPercent = (*((_DWORD *)this + 1214) >> 3) & 1;
              break;
            case 0x1792u:
            case 0x1793u:
              if ( !a7 )
              {
                Text = 1;
                goto LABEL_1652;
              }
              v303 = CDoc::PrimaryMarkup((CDoc *)this);
              NormZoomPercent = CMarkup::GetCodePage(v303);
              if ( v22 == 6034 )
                NormZoomPercent = WindowsCodePageFromCodePage(NormZoomPercent);
              a7->vt = 3;
              break;
            case 0x1794u:
              if ( !a7 )
                goto LABEL_757;
              v295 = v575;
              a7->vt = 37;
              v296 = this[544];
              plLbound[0] = 0;
              bstrString = 0;
              Text = GetExecDocument((struct CDocument **)&bstrString, v296, v295);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection((CDocument *)bstrString, plLbound);
              v97 = Text < 0;
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
                  v27 = 1;
                  Text = 1;
                  goto LABEL_231;
                }
                goto LABEL_936;
              }
LABEL_232:
              if ( v97 )
              {
LABEL_1583:
                if ( Text != -2147221248 )
                  goto LABEL_1652;
              }
LABEL_1584:
              v508 = a5;
              goto LABEL_1585;
            default:
              goto LABEL_231;
          }
LABEL_935:
          a7->lVal = NormZoomPercent;
          goto LABEL_936;
        }
        if ( v19 == 6038 )
          goto LABEL_53;
        v20 = 3;
        switch ( v19 )
        {
          case 0x1799u:
          case 0x179Au:
          case 0x179Bu:
          case 0x179Cu:
            goto LABEL_837;
          case 0x179Eu:
            if ( a6 )
            {
              Text = CDoc::SetupDefaultBlockTag((CDoc *)this, a6);
              if ( !Text )
              {
                CNotification::CNotification((CNotification *)&v588);
                v313 = CDoc::PrimaryMarkup((CDoc *)this);
                v314 = CMarkup::GetElementTopHelper(v313);
                CNotification::EditModeChange((CNotification *)&v588, v314, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v588);
              }
            }
            if ( a7 )
            {
              a7->vt = 8;
              DefaultBlockTag = CDoc::GetDefaultBlockTag(this, llVal, v20, v28);
              v316 = L"DIV";
              if ( DefaultBlockTag != 34 )
                v316 = L"P";
              a7->llVal = (LONGLONG)SysAllocString(v316);
              Text = 0;
            }
            goto LABEL_231;
          case 0x17A0u:
            if ( !a6 )
              goto LABEL_757;
            if ( a6->vt == 13 )
            {
              v96 = CDoc::SetDownloadNotify((CDoc *)this, a6->punkVal);
              goto LABEL_229;
            }
            goto LABEL_756;
        }
        goto LABEL_231;
      }
      if ( v19 <= 0x17AD )
      {
        if ( v19 != 6061 )
        {
          switch ( v19 )
          {
            case 0x17A2u:
              bstrString = 0;
              *(_OWORD *)&v606.vt = 0;
              CNotification::CNotification((CNotification *)&v588);
              if ( !a6 )
                goto LABEL_131;
              if ( a6->vt != 13 )
                goto LABEL_131;
              v335 = (__int64 (__fastcall ***)(_QWORD, GUID *, BSTR *))a6->llVal;
              if ( !v335 )
                goto LABEL_131;
              Text = (**v335)(v335, &IID_INamedPropertyBag, &bstrString);
              if ( Text )
                goto LABEL_230;
              v336 = v575;
              v337 = (struct INamedPropertyBag *)bstrString;
              v338 = CDocument::Markup(v575);
              Text = CDoc::PersistFavoritesData((CDoc *)this, v338, v337, L"DEFAULT");
              if ( Text )
              {
                ReleaseInterface((struct IUnknown *)bstrString);
                goto LABEL_230;
              }
              *(_QWORD *)&v606.vt = bstrString;
              v606.llVal = (LONGLONG)SysAllocString(L"DOC");
              if ( v606.llVal )
              {
                v339 = CDocument::Markup(v336);
                v340 = CMarkup::Root(v339);
                CNotification::FavoritesSave((CNotification *)&v588, v340, &v606, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v588);
                ClearInterface<INamedPropertyBag *>(&v606);
                SysFreeString(v606.bstrVal);
                goto LABEL_1649;
              }
              ReleaseInterface((struct IUnknown *)bstrString);
              goto LABEL_897;
            case 0x17A3u:
              Text = 0;
              if ( a7 )
              {
                v330 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v331 = (__int16 *)this + 2861;
                if ( !v330 )
                  v331 = (__int16 *)(this + 715);
                v332 = *v331;
                a7->vt = 3;
                FontSizeMenu = GetFontSizeMenu(v332);
                v334 = HandleToLong(FontSizeMenu);
                a7->lVal = v334;
                LOBYTE(Text) = v334 == 0;
                goto LABEL_231;
              }
              goto LABEL_757;
            case 0x17A4u:
              if ( a6 )
              {
                plLbound[0] = 0;
                v328 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v329 = (__int16 *)this + 2861;
                if ( !v328 )
                  v329 = (__int16 *)(this + 715);
                Text = ShowFontSizeMenu(plLbound, *v329, a6->lVal);
                if ( !Text )
                {
                  if ( (unsigned int)(plLbound[0] - 2141) <= 4 )
                    CDoc::ExecHelper((CDoc *)this, v575, &CGID_MSHTML, plLbound[0], 0, 0, 0);
                  goto LABEL_1649;
                }
              }
              goto LABEL_231;
          }
          if ( v19 != 6053 )
          {
            if ( v19 != 6054 )
            {
              if ( v19 != 6055 )
              {
                if ( v19 == 6057 )
                  *((_DWORD *)this + 1217) |= 0x10000u;
                goto LABEL_231;
              }
              if ( a6 && a6->vt == 37 && a7 && a7->vt == 3 )
              {
                inserted = CDoc::InsertMenuExt((CDoc *)this, (HMENU)a6->llVal, a7->lVal);
                goto LABEL_306;
              }
              goto LABEL_757;
            }
            if ( !a7 )
              goto LABEL_757;
            v323 = this[544];
            plLbound[0] = 0;
            *(_QWORD *)&String1.vt = 0;
            if ( GetExecDocument((struct CDocument **)&String1, v323, v575) >= 0 )
              CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
            v324 = plLbound[0];
            a7->vt = 3;
            DocDirMenu = CreateDocDirMenu(v324, 0);
            v326 = HandleToLong(DocDirMenu);
            a7->lVal = v326;
            v327 = -2147221247;
LABEL_1320:
            Text = v326 == 0 ? v327 : 0;
            goto LABEL_231;
          }
          if ( !a6 )
            goto LABEL_131;
          memset(&pv, 0, sizeof(pv));
          Text = CVariant::CoerceVariantArg((CVariant *)&pv, a6, 0xDu);
          if ( Text >= 0 )
            Text = CDoc::SaveSnapshotHelper((CDoc *)this, pv.punkVal, 1);
LABEL_878:
          p_pvarg = &pv;
LABEL_210:
          VariantClear(p_pvarg);
          goto LABEL_231;
        }
        if ( a6 || !a7 )
          goto LABEL_757;
        v341 = this[103];
        if ( !v341 )
          goto LABEL_350;
        *(_QWORD *)&String1.vt = 0;
        v342 = COmWindowProxy::Document(v341);
        Text = CDocument::ExtractContent(v342, (struct IReadingModeExtractedContent **)&String1);
        if ( Text < 0 )
          goto LABEL_1583;
        v343 = *(BSTR *)&String1.vt;
        a7->vt = 13;
LABEL_904:
        a7->llVal = (LONGLONG)v343;
        goto LABEL_1647;
      }
      switch ( v19 )
      {
        case 0x17AEu:
          Text = 0;
          if ( a6 || !a7 )
            goto LABEL_131;
          a7->vt = 3;
          a7->lVal = 0;
          v347 = (ReadingMode::CTextClusterDetector *)operator new[](
                                                        0x40u,
                                                        (const struct MemoryProtection::leaf_t *)0x8FC);
          if ( v347 )
          {
            v348 = (ReadingMode::CTextClusterDetector *)ReadingMode::CTextClusterDetector::CTextClusterDetector(
                                                          v347,
                                                          (struct CDoc *)this);
            v349 = v348;
            if ( v348 )
            {
              a7->lVal = ReadingMode::CTextClusterDetector::LengthOfArticleBody(v348);
              ReadingMode::CTextClusterDetector::`scalar deleting destructor'(v349, 1u);
              goto LABEL_1652;
            }
          }
          goto LABEL_897;
        case 0x17B1u:
          if ( CDoc::UseLayerManager((CDoc *)this) )
            CView::QueueFlushBatch((CView *)(this + 283));
          goto LABEL_53;
        case 0x17B6u:
          CDoc::SetPrerenderVisibility((CDoc *)this, a5 != 0);
          goto LABEL_53;
      }
      if ( v19 != 6071 )
      {
        if ( v19 == 6072 )
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
        else if ( v19 == 6073 )
        {
          Text = -2147024882;
          v344 = CDoc::PrimaryMarkup((CDoc *)this);
          CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v344);
          if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
          {
            v345 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
            Text = CPreloadManager::SuspendDuringPrerender(v345, 4);
          }
          CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
        }
        goto LABEL_231;
      }
      if ( !a7 || !a6 || a6->vt != 19 )
        goto LABEL_131;
      a7->vt = 19;
      v346 = CDoc::CheckBFCacheCandidacy(this, a6->cyVal.Lo, 2139, 0xFFFFFFFFLL);
LABEL_924:
      a7->lVal = v346;
      Text = 0;
      goto LABEL_1651;
    }
    if ( v19 <= 0x1B53 )
    {
      if ( v19 != 6995 )
      {
        switch ( v19 )
        {
          case 0x17BBu:
            v365 = CDoc::InputManager((CDoc *)this);
            v366 = CInputManager::DeferredActionHandler(v365);
            CDeferredActionHandler::AgreeToVTabNavigate(v366, 0);
            goto LABEL_53;
          case 0x17BCu:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v367 = CDoc::InputManager((CDoc *)this);
            v368 = CInputManager::DeferredActionHandler(v367);
            CDeferredActionHandler::OnVTabNavigateComplete(v368, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BDu:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v369 = CDoc::InputManager((CDoc *)this);
            v370 = CInputManager::DeferredActionHandler(v369);
            CDeferredActionHandler::CancelSpecificVTabNavigate(v370, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BEu:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_757;
            v371 = CDoc::InputManager((CDoc *)this);
            v372 = CInputManager::DeferredActionHandler(v371);
            inserted = CDeferredActionHandler::ValidateVTabNavigate(v372, a6->cyVal.Lo);
            goto LABEL_306;
          case 0x17BFu:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v373 = CDoc::InputManager((CDoc *)this);
            v374 = CInputManager::DeferredActionHandler(v373);
            CDeferredActionHandler::OnBeforeUnloadAgreed(v374, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17C0u:
            if ( !a6 || a6->vt != 11 )
              goto LABEL_231;
            v375 = a6->iVal;
            Text = 0;
            if ( !v375 && ((_DWORD)this[609] & 0x200000) != 0 )
              goto LABEL_350;
            *((_DWORD *)this + 1219) &= ~0x100000u;
            v376 = 0;
            llVal = 0x100000;
            if ( v375 == -1 )
              v376 = 0x100000;
            *((_DWORD *)this + 1219) |= v376;
            goto LABEL_230;
          case 0x17C1u:
            Text = -2147467259;
            v362 = CDoc::PrimaryMarkup((CDoc *)this);
            v363 = v362;
            if ( !v362 || !(unsigned int)BindCtx_ContainsObject(*((_QWORD *)v362 + 183), L"IE_FLAG_HAS_SCROLL_POSITION") )
              goto LABEL_1652;
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v363 + 183) + 96LL))(
              *((_QWORD *)v363 + 183),
              L"IE_FLAG_HAS_SCROLL_POSITION");
            goto LABEL_53;
          case 0x17C2u:
            CDoc::ReleaseOffscreenBuffers((CDoc *)this);
            goto LABEL_53;
          case 0x17C3u:
            v364 = this[876];
            if ( v364 )
            {
              (*(void (__fastcall **)(CInPlace *, __int64, __int64, __int64))(*(_QWORD *)v364 + 16LL))(
                v364,
                32,
                v20,
                0xFFFFFFFFLL);
              this[876] = 0;
            }
            goto LABEL_53;
          case 0x17C4u:
            if ( !a7 )
              goto LABEL_131;
            a7->vt = 11;
            v360 = ((_BYTE)this[441] & 4) != 0;
            goto LABEL_963;
          case 0x17C5u:
            inserted = CDoc::GetVisibilityState((CDoc *)this, a7);
            goto LABEL_306;
          case 0x17C6u:
            if ( !a7 )
              goto LABEL_757;
            a7->vt = 3;
            plLbound[0] = 0;
            DispSystem = GetDispSystem();
            Text = (*(__int64 (__fastcall **)(struct IDispSystem *, LONG *))(*(_QWORD *)DispSystem + 736LL))(
                     DispSystem,
                     plLbound);
            if ( Text )
              goto LABEL_231;
            v381 = plLbound[0];
            goto LABEL_1535;
          case 0x17C7u:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_757;
            v382 = a6->lVal;
            plLbound[0] = 0;
            Text = ValidateD3DRequestedFeatureLevel(v382, (enum D3D_REQUESTED_FEATURE_LEVEL *)plLbound);
            if ( Text )
              goto LABEL_231;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                  + 16LL)
                      + 1132LL) = plLbound[0];
            goto LABEL_1649;
          case 0x17C8u:
            if ( !a6 )
              goto LABEL_131;
            v361 = a6->vt == 19;
            goto LABEL_966;
          case 0x17C9u:
            if ( !a7 )
              goto LABEL_131;
            IsEnterpriseMode = 0;
            if ( CDoc::PrimaryMarkup((CDoc *)this) )
            {
              v358 = CDoc::PrimaryMarkup((CDoc *)this);
              v359 = CMarkup::MarkupVersion(v358);
              IsEnterpriseMode = CMarkupVersion::IsEnterpriseMode(v359);
            }
            a7->vt = 11;
            v360 = !IsEnterpriseMode - 1;
LABEL_963:
            a7->iVal = v360;
            goto LABEL_936;
          case 0x17CAu:
            v377 = *(CVirtualTabStorageEntry **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + (unsigned int)tls_index)
                                                           + 16LL)
                                               + 728LL);
            if ( v377 && CVirtualTabStorageEntry::WasLastNavigationViaFlipAhead(v377) )
            {
              v378 = CDoc::PrimaryMarkup((CDoc *)this);
              CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v378);
              if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
              {
                v379 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                CPreloadManager::SetLastNavAsFlipAheadAndIssueRequestIfApplicable(v379);
              }
              CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
            }
            goto LABEL_53;
          case 0x17CBu:
            if ( !a6 || a6->vt != 8 )
              goto LABEL_757;
            v352 = CDoc::PrimaryMarkup((CDoc *)this);
            if ( v352 && (*((_BYTE *)v352 + 248) = 1, (v353 = this[103]) != 0) )
            {
              CodePageCore = *((unsigned int *)v352 + 194);
              v355 = *((_DWORD *)v352 + 196);
              if ( !(_DWORD)CodePageCore )
                CodePageCore = CMarkup::GetCodePageCore(v352);
              Text = COmWindowProxy::ExecRefresh(v353, 3, CodePageCore, v355);
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
              v356 = bstrString;
              bstrString = 0;
              if ( v356 )
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)v356 + 16LL))(v356);
            }
            SysFreeString(a6->bstrVal);
            v55 = ppvData;
            ppvData = 0;
            a6->llVal = 0;
            goto LABEL_954;
          default:
            goto LABEL_231;
        }
      }
      inserted = CDoc::GetDisabledRenderingMode((CDoc *)this, a7);
      goto LABEL_306;
    }
    if ( v19 <= 0x1BDC )
    {
      if ( v19 == 7132 )
      {
        v173 = 1;
        goto LABEL_380;
      }
      if ( v19 > 0x1B75 )
      {
        if ( v19 > 0x1BBC )
        {
          if ( v19 != 7101 )
            goto LABEL_231;
          if ( a6 && a6->vt == 11 )
          {
            *((_DWORD *)this + 1216) = (_DWORD)this[608] & 0x7FFFFFFF | (a6->iVal << 31);
            goto LABEL_53;
          }
        }
        else
        {
          if ( v19 != 7100 )
          {
            switch ( v19 )
            {
              case 0x1B76u:
                Text = -2147467259;
                View = CDoc::GetView((CDoc *)this);
                v413 = View;
                if ( !a7 || !View || !*((_BYTE *)View + 40) )
                  goto LABEL_1652;
                a7->vt = 3;
                v414 = *(unsigned __int16 *)CViewportController::GetLogicalViewportSize(*((_QWORD *)View + 4), &String1);
                a7->lVal = v414
                         | (*(unsigned __int16 *)(CViewportController::GetLogicalViewportSize(
                                                    *((_QWORD *)v413 + 4),
                                                    &v606)
                                                + 4) << 16);
                CDispClient::AdjustContentSize((CDispClient *)&v606, v415, v416);
                CDispClient::AdjustContentSize((CDispClient *)&String1, v417, v418);
                goto LABEL_936;
              case 0x1B77u:
                Text = -2147467259;
                v420 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v420 || !*((_BYTE *)v420 + 40) )
                  goto LABEL_1652;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsMobileOptimizedSite(*((CViewportController **)v420 + 4));
                goto LABEL_1156;
              case 0x1B78u:
                Text = -2147467259;
                v422 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v422 || !*((_BYTE *)v422 + 40) )
                  goto LABEL_1652;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsViewportWidthOrientationDependent(*((CViewportController **)v422
                                                                                                 + 4));
                goto LABEL_1156;
              case 0x1B79u:
                inserted = CDoc::SetViewStateMediaQuery((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7Au:
                inserted = CDoc::GetUserVisibility((CDoc *)this, a7);
                goto LABEL_306;
              case 0x1B7Bu:
                inserted = CDoc::SetUserVisibility((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7Cu:
                Text = -2147024809;
                if ( !a6 || a6->vt != 3 )
                  goto LABEL_1652;
                v411 = CVersions::MapToDocumentMode(a6->cyVal.Lo, 32, v20, 0xFFFFFFFFLL);
                goto LABEL_1120;
              case 0x1B7Du:
                inserted = CDoc::SetAuthoringCallback((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7Eu:
                if ( !a6 || a6->vt != 9 )
                  goto LABEL_330;
                bstrString = 0;
                v428 = a6->punkVal;
                *(GUID *)&v606.vt = CLSID_CElement;
                Text = QIClassID(v428, (struct _GUID *)&v606, (void **)&bstrString);
                if ( Text < 0 )
                  goto LABEL_1583;
                inserted = CElement::EnterFullScreen((CElement *)bstrString);
                goto LABEL_306;
              case 0x1B7Fu:
                if ( !a6 || ((a6->vt - 1) & 0xFFF7) != 0 )
                {
                  Text = -2147467261;
                  bstrString = 0;
                  goto LABEL_1652;
                }
                v429 = 0;
                bstrString = 0;
                if ( a6->vt == 9 )
                {
                  v430 = a6->punkVal;
                  *(GUID *)&v606.vt = CLSID_CElement;
                  Text = QIClassID(v430, (struct _GUID *)&v606, (void **)&bstrString);
                  if ( Text < 0 )
                    goto LABEL_1583;
                  v429 = (CElement *)bstrString;
                }
                if ( v429 )
                {
                  inserted = CElement::ExitFullScreen(v429);
                }
                else
                {
                  v431 = CDoc::FullScreenState((CDoc *)this);
                  inserted = CFullScreenState::ExitFullScreen(v431, 0);
                }
                break;
              case 0x1B80u:
                inserted = CDoc::PrepareForSetVisible((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B81u:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1652;
                if ( a6->vt != 8204 )
                  goto LABEL_1652;
                if ( SafeArrayGetDim(a6->parray) != 1 )
                  goto LABEL_1652;
                v423 = a6->parray;
                plLbound[0] = 0;
                SafeArrayGetUBound(v423, 1u, plLbound);
                if ( plLbound[0] != 2 )
                  goto LABEL_1652;
                v424 = a6->parray;
                *(_QWORD *)&String1.vt = 0;
                Text = SafeArrayAccessData(v424, (void **)&String1);
                if ( Text < 0 )
                  goto LABEL_1583;
                Text = CDoc::SetMediaConsent(
                         (CDoc *)this,
                         *(const unsigned __int16 **)(*(_QWORD *)&String1.vt + 8LL),
                         *(_DWORD *)(*(_QWORD *)&String1.vt + 32LL),
                         *(_DWORD *)(*(_QWORD *)&String1.vt + 56LL));
                goto LABEL_1144;
              case 0x1B82u:
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_131;
                Text = -2147467259;
                v419 = CDoc::GetView((CDoc *)this);
                if ( !v419 || !*((_BYTE *)v419 + 40) )
                  goto LABEL_1652;
                CViewportController::SetUIOrientation(*((CViewportController **)v419 + 4), a6->iVal == 0xFFFF);
                goto LABEL_53;
              case 0x1B83u:
                Text = -2147024809;
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_1652;
                v96 = CDoc::ForcePaint((CDoc *)this, a6->iVal == 0xFFFF, 0);
                goto LABEL_229;
              case 0x1B84u:
                inserted = CDoc::WaitForDCompFlush((CDoc *)this);
                goto LABEL_306;
              case 0x1B86u:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1652;
                if ( a6->vt != 11 )
                  goto LABEL_1652;
                Text = -2147467259;
                v425 = CDoc::GetView((CDoc *)this);
                if ( !v425 )
                  goto LABEL_1652;
                CView::AllowGrippersForHost(v425, a6->iVal == 0);
                goto LABEL_53;
              case 0x1B87u:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1652;
                if ( a6->vt != 8 )
                  goto LABEL_1652;
                Text = -2147418113;
                if ( !v575 )
                  goto LABEL_1652;
                inserted = CDoc::HandleFlashServicingRefresh((CDoc *)this, v575, a6->bstrVal);
                goto LABEL_306;
              case 0x1B88u:
                Text = -2147024809;
                if ( !a7 )
                  goto LABEL_1652;
                a7->vt = 11;
                v426 = CDoc::FullScreenState((CDoc *)this);
                IsMobileOptimizedSite = CFullScreenState::IsInFullScreen(v426);
LABEL_1156:
                v427 = !IsMobileOptimizedSite;
                goto LABEL_1493;
              default:
                goto LABEL_231;
            }
            goto LABEL_306;
          }
          if ( a6 )
          {
            v361 = a6->vt == 11;
LABEL_966:
            if ( v361 )
              goto LABEL_53;
          }
        }
        goto LABEL_131;
      }
      if ( v19 == 7029 )
        goto LABEL_131;
      if ( v19 <= 0x1B60 )
      {
        if ( v19 == 7008 )
        {
          inserted = CDoc::SetPhishingFilterDialogAsShown((CDoc *)this);
          goto LABEL_306;
        }
        if ( v19 > 0x1B59 )
        {
          if ( v19 != 7003 )
          {
            switch ( v19 )
            {
              case 0x1B5Cu:
                v389 = 0;
                if ( a6 && a6->vt == 3 )
                  v389 = a6->lVal;
                CDoc::SubmitForAntiPhishProcessing((CDoc *)this, 0, v389, 0);
                goto LABEL_53;
              case 0x1B5Du:
                inserted = CDoc::NotifyMarkupsModelessEnable((CDoc *)this);
                break;
              case 0x1B5Fu:
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
          v390 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( !v390 )
            goto LABEL_350;
          *((_BYTE *)v390 + 97) |= 8u;
          goto LABEL_53;
        }
        if ( v19 != 7001 )
        {
          switch ( v19 )
          {
            case 0x1B54u:
              inserted = CDoc::SetDisabledRenderingMode((CDoc *)this, a6);
              goto LABEL_306;
            case 0x1B55u:
              g_fOverrideScrollbarSizes = 1;
              ThreadStateUI = GetThreadStateUI();
              InitSystemMetricValues(ThreadStateUI);
              OnSettingsChangeAllDocs(1, 0x1B55u);
              break;
            case 0x1B56u:
              goto LABEL_53;
            case 0x1B57u:
              break;
            default:
              if ( a6 && a6->vt == 3 )
              {
                Lo = a6->cyVal.Lo;
                if ( Lo > 4 )
                  goto LABEL_131;
                Text = CDoc::ExecHelper((CDoc *)this, v575, &CGID_MSHTML, Lo + 2141, 2u, 0, 0);
                if ( Text )
                  goto LABEL_231;
              }
              if ( !a7 )
                goto LABEL_53;
              v361 = !FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
              v384 = (char *)this + 5722;
              if ( v361 )
                v384 = (char *)(this + 715);
              DebugState = *(__int16 *)v384;
              a7->vt = 3;
LABEL_1027:
              a7->lVal = DebugState;
              goto LABEL_53;
          }
          v387 = CDocument::Markup(v575);
          CDoc::WaitForRecalc((CDoc *)this, v387);
          goto LABEL_53;
        }
        if ( !a7 )
          goto LABEL_330;
        a7->vt = 3;
        a7->lVal = 0x40000;
LABEL_936:
        Text = 0;
        goto LABEL_1650;
      }
      if ( v19 != 7011 )
      {
        switch ( v19 )
        {
          case 0x1B66u:
            inserted = PassThroughTechnique::GetConstantBuffer(this, a6, a7, 0xFFFFFFFFLL);
            goto LABEL_306;
          case 0x1B69u:
            inserted = CDoc::GetHighContrastMode((CDoc *)this, a7);
            goto LABEL_306;
          case 0x1B6Au:
            inserted = CDoc::SetHighContrastMode((CDoc *)this, a6);
            goto LABEL_306;
          case 0x1B6Cu:
            CDoc::CompatViewRefresh((CDoc *)this, 0);
            goto LABEL_53;
          case 0x1B6Du:
            if ( a6 && a6->vt == 11 )
            {
              v391 = 0;
              llVal = 512;
              if ( a6->iVal == -1 )
                v391 = 512;
              *((_DWORD *)this + 1214) = (_DWORD)this[607] & 0xFFFFFDFF | v391;
              goto LABEL_230;
            }
            goto LABEL_757;
          case 0x1B70u:
            inserted = CDoc::GetSuspendLevel((CDoc *)this, a7);
            goto LABEL_306;
          case 0x1B71u:
            inserted = CDoc::SetSuspendLevel((CDoc *)this, a6);
            goto LABEL_306;
        }
        if ( v19 != 7026 )
          goto LABEL_231;
        Text = CDoc::SaveToTempFileForPrint((CDoc *)this, v575, Data, 0x104u, 0, 0, 0);
        if ( Text < 0 )
          goto LABEL_1583;
        if ( !a7 )
          goto LABEL_757;
        VariantInit(a7);
        a7->vt = 8;
        v343 = SysAllocString(Data);
        goto LABEL_904;
      }
      if ( !a6 || a6->vt != 19 || !a7 )
        goto LABEL_757;
      rgIndices[0] = a6->lVal;
      Vector = SafeArrayCreateVector(0xCu, 0, 6u);
      pszSubKey = &Vector->cDims;
      a7->llVal = (LONGLONG)Vector;
      a7->vt = 8204;
      if ( !Vector )
        goto LABEL_897;
      ppvData = 0;
      Text = SafeArrayAccessData(Vector, &ppvData);
      if ( Text < 0 )
        goto LABEL_1583;
      for ( i = 0; i != 6; ++i )
        VariantInit((VARIANTARG *)ppvData + i);
      v394 = rgIndices[0];
      v22 = plLbound[0];
      if ( (rgIndices[0] & 1) != 0 )
      {
        Text = 0;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v395 = ppvData;
          *(_WORD *)ppvData = 21;
          v395[1] = *((_QWORD *)CDoc::PrimaryMarkup((CDoc *)this) + 17);
        }
        v394 = rgIndices[0];
      }
      if ( (v394 & 2) != 0 )
      {
        v396 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( v396 )
        {
          v397 = COptionsHolder::SecurityContext(v396);
          *(_QWORD *)&v606.vt = v397;
          if ( v397 )
          {
            *(_QWORD *)&String1.vt = CHtmCtx::GetReferrerUrl(v397);
            OriginalUrlContext = CHtmCtx::GetOriginalUrlContext(*(CHtmCtx **)&v606.vt);
            v399 = *(const OLECHAR **)&String1.vt;
            v400 = -1;
            *(_QWORD *)&v606.vt = OriginalUrlContext;
            if ( *(_QWORD *)&String1.vt )
            {
              v401 = -1;
              do
                ++v401;
              while ( *(_WORD *)(*(_QWORD *)&String1.vt + 2 * v401) );
            }
            else
            {
              v401 = 0;
            }
            if ( OriginalUrlContext )
            {
              do
                ++v400;
              while ( OriginalUrlContext[v400] );
            }
            else
            {
              v400 = 0;
            }
            if ( v401 )
            {
              if ( v400 > v401 )
              {
                v402 = wcsncmp_0(*(const wchar_t **)&String1.vt, OriginalUrlContext, v401);
                v399 = *(const OLECHAR **)&String1.vt;
                if ( !v402 )
                  v399 = *(const OLECHAR **)&v606.vt;
              }
            }
            v403 = SysAllocString(v399);
            v27 = 1;
            if ( v403 )
            {
              v404 = ppvData;
              Text = 0;
              *((_WORD *)ppvData + 12) = 8;
              v404[4] = v403;
            }
          }
        }
      }
      v405 = rgIndices[0];
      if ( (rgIndices[0] & 4) != 0 )
      {
        v406 = ppvData;
        *(_QWORD *)&v606.vt = ppvData;
        *((_WORD *)ppvData + 24) = 21;
        if ( this[781] )
        {
          v407 = CHTMLDlg::SecurityContext(this[781]);
          v405 = rgIndices[0];
          *(_QWORD *)(*(_QWORD *)&v606.vt + 56LL) = v407;
        }
        else
        {
          v406[7] = 0;
        }
      }
      if ( (v405 & 8) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractVideoData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text < 0 )
        {
LABEL_1112:
          CMultimediaLog::StopUpdate((CMultimediaLog *)(this + 741));
          v410 = (SAFEARRAY *)pszSubKey;
          goto LABEL_1145;
        }
        v405 = rgIndices[0];
        if ( bstrString )
        {
          v408 = ppvData;
          Text = 0;
          *((_WORD *)ppvData + 36) = 8;
          v408[10] = bstrString;
        }
      }
      if ( (v405 & 0x10) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractImageData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text >= 0 )
        {
          if ( bstrString )
          {
            v409 = ppvData;
            Text = 0;
            *((_WORD *)ppvData + 48) = 8;
            v409[13] = bstrString;
          }
        }
      }
      goto LABEL_1112;
    }
    if ( v19 <= 0x3A9C )
    {
      if ( v19 == 15004 )
      {
        inserted = CDoc::OnGetUserInitFlags((CDoc *)this, a6, a7);
        goto LABEL_306;
      }
      if ( v19 <= 0x1F46 )
      {
        if ( v19 == 8006 )
        {
          inserted = CDoc::NotifyViewStateChanged((CDoc *)this);
          goto LABEL_306;
        }
        if ( v19 > 0x1BF1 )
        {
          if ( v19 == 7700 )
          {
            if ( (*((_DWORD *)this + 1217) & 0x800) == 0 )
            {
              Text = CDoc::SerializePrintCommands((CDoc *)this, v575, a6, a7);
              v448 = Text == 0;
              goto LABEL_1648;
            }
            goto LABEL_231;
          }
          if ( v19 == 8000 )
          {
            if ( !a6 || a6->vt == 11 )
            {
              v446 = (unsigned int)tls_index;
              if ( a7 )
              {
                ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 11;
                a7->iVal = -(*(_BYTE *)(*(_QWORD *)(ThreadLocalStoragePointer[v446] + 16LL) + 1128LL) != 0);
              }
              if ( a6 )
                *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v446) + 16LL) + 1128LL) = a6->iVal == 0xFFFF;
              goto LABEL_53;
            }
            goto LABEL_131;
          }
          if ( v19 != 8001 )
          {
            switch ( v19 )
            {
              case 0x1F42u:
                inserted = CDoc::_TogglePerfWidgetVisibility((CDoc *)this);
                break;
              case 0x1F43u:
                Text = 0;
                v441 = CDocument::Window(v575);
                v442 = v441;
                if ( v441 && (unsigned int)CWindow::IsPrimaryWindow(v441) )
                {
                  v443 = CDeviceRotationRate::SecurityContext(v442);
                  if ( v443 )
                  {
                    v444 = CMarkup::Window(v443);
                    CEventMgr::QueueAsyncEvent(
                      &s_propdescCIE9EventListorientationchange,
                      v444,
                      v443,
                      COmWindowProxy::Fire_orientationchange,
                      0,
                      AsyncEventMerge_Always,
                      0);
                  }
                  v445 = *((_QWORD *)v442 + 55);
                  if ( v445 )
                    CEventMgr::QueueAsyncEvent(
                      &s_propdescCIE9EventListMSOrientationChange,
                      v445,
                      v443,
                      CScreen::Fire_orientationchange,
                      0,
                      AsyncEventMerge_Always,
                      0);
                }
                goto LABEL_1649;
              case 0x1F44u:
                inserted = CDoc::GetContentLang((CDoc *)this, a7);
                break;
              case 0x1F45u:
                v440 = this[732];
                if ( v440 )
                {
                  CAPProcessor::Passivate(v440);
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
        switch ( v19 )
        {
          case 0x1BF1u:
            CDoc::UpdateDefaultDpiScaling((CDoc *)this);
            goto LABEL_53;
          case 0x1BDDu:
            Text = -2147024809;
            if ( !a6 || a6->vt != 13 )
              goto LABEL_1652;
            v96 = CIndependentHitTestManager::RegisterHostForIndependentHitTesting(
                    (CIndependentHitTestManager *)&g_IndependentHitTestManager,
                    (struct CDoc *)this,
                    a6->punkVal);
            goto LABEL_229;
          case 0x1BDEu:
            Text = -2147024809;
            if ( !a6 || a6->vt != 13 )
              goto LABEL_1652;
            v96 = CIndependentHitTestManager::UnregisterHostForIndependentHitTesting(
                    (CIndependentHitTestManager *)&g_IndependentHitTestManager,
                    (struct CDoc *)this,
                    a6->punkVal);
            goto LABEL_229;
          case 0x1BDFu:
            Text = -2147024809;
            if ( !a6 || a6->vt != 0x4000 )
              goto LABEL_1652;
            RootTracker = CRootTracker::GetRootTracker();
            v434 = RootTracker;
            if ( RootTracker )
            {
              Text = CRootTracker::EnsureInitialized(RootTracker);
              if ( Text < 0 )
                goto LABEL_1583;
              CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
              v435 = CDCompLayerManager::UseRootLayer(v434);
              v436 = **(__int64 (__fastcall ***)(struct IDispLayer *, GUID *, struct CHtmParseCtx *))v435;
              v437 = (CHtmRootParseCtxRouter *)TSmartPointer<ID3D11Device>::operator&(&bstrString);
              HpxEmbed = CHtmRootParseCtxRouter::GetHpxEmbed(v437);
              Text = v436(v435, &GUID_cc1a2bea_d5e9_4161_9da7_9042b37549a7, HpxEmbed);
              if ( Text >= 0 )
              {
                v439 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                Text = (*(__int64 (__fastcall **)(struct IDispRenderTarget *, __int64, struct tagVARIANT *))(*(_QWORD *)v439 + 24LL))(
                         v439,
                         3,
                         a6);
              }
              TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&bstrString);
              goto LABEL_230;
            }
            goto LABEL_1406;
          case 0x1BE0u:
            Text = -2147024809;
            if ( a7 )
            {
              a7->vt = 11;
              a7->iVal = -((unsigned int)CDoc::IsJSDumpRequested((CDoc *)this) != 0);
              if ( !a6 )
              {
                Text = 0;
                goto LABEL_1652;
              }
            }
            else if ( !a6 )
            {
              goto LABEL_1652;
            }
            if ( a6->vt != 21 )
              goto LABEL_1652;
            inserted = CDoc::OnDumpHeap((CDoc *)this, 0, &a6->ullVal);
            goto LABEL_306;
        }
        v20 = 4;
        if ( v19 == 7140 )
        {
          inserted = CDoc::OnGetTrackingProtectionData((CDoc *)this);
          goto LABEL_306;
        }
        if ( v19 == 7150 )
        {
          CDoc::UpdateEffectiveDpi((CDoc *)this);
          goto LABEL_53;
        }
        if ( v19 != 7151 )
        {
          if ( v19 != 7152 )
            goto LABEL_231;
          if ( a7 )
          {
            a7->lVal = 0;
            bstrString = 0;
            a7->vt = 23;
            Text = CDoc::GetPrimaryUri((CDoc *)this, (struct IUri **)&bstrString);
            if ( !Text )
            {
              v209 = (struct IUnknown *)bstrString;
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
            v209 = (struct IUnknown *)bstrString;
LABEL_527:
            ReleaseInterface(v209);
            goto LABEL_231;
          }
          goto LABEL_131;
        }
        if ( !a7 )
          goto LABEL_131;
        a7->vt = 4;
        v361 = !CView::HasStaticViewportSizeApplied((CView *)(this + 283));
        v432 = (int *)(this + 481);
        if ( v361 )
          v432 = (int *)this + 1019;
        NormZoomPercent = *v432;
        goto LABEL_935;
      }
      if ( v19 > 0x3A98 )
      {
        if ( v19 != 15001 )
        {
          if ( v19 == 15002 )
          {
            if ( a6 && (a6->vt == 8212 || a6->vt == 8195) )
            {
              v461 = a6->parray;
              if ( v461 )
              {
                pvData = 0;
                pszSubKey = 0;
                *(_QWORD *)&String1.vt = 0;
                if ( !SafeArrayGetElement(v461, (LONG *)&pvData, &pszSubKey) )
                {
                  v462 = a6->parray;
                  ++pvData;
                  if ( !SafeArrayGetElement(v462, (LONG *)&pvData, &String1) )
                    CDoc::ReplacePrintHandles((CDoc *)this, (void *)pszSubKey, *(void **)&String1.vt);
                }
                goto LABEL_53;
              }
            }
            goto LABEL_131;
          }
          v326 = InternetSetOptionW(0, 0x2Au, 0, 0);
          v327 = -2147467259;
          goto LABEL_1320;
        }
        if ( g_fInHtmlHelp )
        {
          *((_DWORD *)this + 1217) |= 0x400u;
          v463 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( v463 )
          {
            if ( (*((_DWORD *)v463 + 187) & 0x4000000) != 0 )
            {
              v464 = (COmWindowProxy *)*((_QWORD *)v463 + 44);
              if ( v464 )
                COmWindowProxy::Fire_onafterprint(v464);
            }
          }
          *((_DWORD *)this + 1217) &= ~0x400u;
        }
      }
      else if ( v19 != 15000 )
      {
        if ( v19 > 0x1F4C )
        {
          switch ( v19 )
          {
            case 0x1F4Fu:
              if ( a7 )
              {
                Text = 0;
                a7->vt = 11;
                a7->iVal = 0;
                goto LABEL_1650;
              }
              break;
            case 0x1F50u:
              goto LABEL_231;
            case 0x1F51u:
              if ( a6 && a6->vt == 19 )
              {
                if ( (unsigned __int8)CDoc::IsHostBehaviorSupported<84>(this, 32, v20, 0xFFFFFFFFLL) )
                {
                  CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)&bstrString);
                  GetCachedPrimaryDisplaySize((struct CSize *)&bstrString);
                  HIDWORD(bstrString) = a6->lVal;
                  SetCachedPrimaryDisplaySize((const struct CSize *)&bstrString);
                  CDispClient::AdjustContentSize((CDispClient *)&bstrString, v459, v460);
                }
                goto LABEL_53;
              }
              break;
            case 0x1F52u:
              if ( !a6 || a6->vt != 11 )
                goto LABEL_131;
              FeatureControlHelper::SetStripDOMElements(
                (FeatureControlHelper *)&g_FeatureControlHelper,
                a6->iVal == 0xFFFF);
              goto LABEL_53;
            case 0x1F53u:
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
          switch ( v19 )
          {
            case 0x1F4Cu:
              Text = 0;
              CDoc::OfferImageResources((CDoc *)this);
              goto LABEL_1649;
            case 0x1F47u:
              if ( a6 && a6->vt == 3 )
              {
                Text = 0;
                CDoc::HandleWebStorageEvent((CDoc *)this, v575, a6->cyVal.Lo);
                goto LABEL_1649;
              }
              goto LABEL_131;
            case 0x1F48u:
              Text = 0;
              if ( a6 && a6->vt == 19 )
              {
                v455 = this[126];
                if ( v455 )
                {
                  v456 = a6->lVal;
                  if ( *((_DWORD *)v455 + 384) == v456 )
                    goto LABEL_1649;
                  *((_DWORD *)v455 + 384) = v456;
                  v457 = CDocument::Markup(v575);
                  TextScalingSettings = CTextScalingSettings::GetTextScalingSettings(v457);
                  CTextScalingSettings::Initialize(TextScalingSettings, (struct CDoc *)this);
                  inserted = CDoc::ForceRelayout((CDoc *)this, 0);
                  goto LABEL_306;
                }
                goto LABEL_350;
              }
              goto LABEL_757;
            case 0x1F49u:
              if ( !a6 || a6->vt != 11 )
                goto LABEL_131;
              v453 = CDoc::GetView((CDoc *)this);
              if ( v453 )
              {
                if ( *((_BYTE *)v453 + 40) )
                {
                  v454 = (CViewportController *)*((_QWORD *)v453 + 4);
                  if ( v454 )
                  {
                    Text = 0;
                    CViewportController::SetAccessibleZoom(v454, a6->iVal != 0);
                    goto LABEL_1649;
                  }
                }
              }
              goto LABEL_350;
            case 0x1F4Au:
              v451 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v28 = 16;
              pvData = 0;
              bstrString = (BSTR)v451[(unsigned int)tls_index];
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
            v449 = CDoc::GetView((CDoc *)this);
            if ( v449 )
            {
              v450 = (CViewportController *)*((_QWORD *)v449 + 4);
              if ( v450 )
              {
                Text = 0;
                CViewportController::SetIsReadingView(v450, a6->iVal != 0);
                goto LABEL_1649;
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
            v465 = (unsigned int (__fastcall ***)(_QWORD, GUID *, void **, __int64))a6->llVal;
            if ( v465 )
            {
              ppvData = 0;
              if ( !(**v465)(v465, &IID_IHTMLWindow2, &ppvData, v28) )
              {
                v466 = this[642];
                bstrString = 0;
                if ( !(**(unsigned int (__fastcall ***)(CInPlace *, GUID *, BSTR *))v466)(
                        v466,
                        &IID_ITridentService2,
                        &bstrString) )
                {
                  (*(void (__fastcall **)(BSTR, void *, _QWORD))(*(_QWORD *)bstrString + 144LL))(
                    bstrString,
                    ppvData,
                    (unsigned int)(v22 != 15000) + 225);
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
    if ( v19 <= 0x3AFC )
    {
      if ( v19 == 15100 )
      {
        v528 = CDocument::Markup(v575);
        v529 = 0;
        if ( a6 && a6->vt == 3 )
          v529 = a6->lVal;
        Text = 0;
        if ( !v528 )
          goto LABEL_1649;
        v530 = CMarkup::GetWindowedMarkupContext(v528);
        if ( !v530 )
          goto LABEL_1649;
        RootMarkup = CMarkup::GetRootMarkup(v530, 0);
        if ( !RootMarkup )
          goto LABEL_1649;
        *((_DWORD *)RootMarkup + 197) |= v529;
        *((_DWORD *)this + 1224) &= ~v529;
        inserted = CDoc::NotifyPageActionBlockedState((CDoc *)this, 1, 0);
        goto LABEL_306;
      }
      if ( v19 <= 0x3AB3 )
      {
        if ( v19 == 15027 )
        {
          Text = -2147024809;
          if ( !a7 )
            goto LABEL_1652;
          a7->vt = 3;
          NormZoomPercent = CZoomState::GetNormZoomPercent();
          goto LABEL_935;
        }
        if ( v19 <= 0x3AA3 )
        {
          switch ( v19 )
          {
            case 0x3AA3u:
              Text = -2147024809;
              if ( !a7 )
                goto LABEL_1652;
              ppvData = 0;
              pszSubKey = (LPCWSTR)GetThreadStateUI();
              if ( (unsigned int)IsEqualGUID(pszSubKey + 416, &GUID_NULL) )
                goto LABEL_1652;
              *(_QWORD *)&String1.vt = 3;
              v486 = SafeArrayCreate(0xCu, 1u, (SAFEARRAYBOUND *)&String1);
              v487 = v486;
              if ( v486 )
              {
                Text = SafeArrayAccessData(v486, &ppvData);
                if ( Text >= 0 )
                {
                  bstrString = 0;
                  Text = StringFromCLSID((const IID *const)pszSubKey + 52, &bstrString);
                  if ( Text >= 0 )
                  {
                    *(_WORD *)ppvData = 8;
                    v488 = SysAllocString(bstrString);
                    v489 = pszSubKey;
                    *((_QWORD *)ppvData + 1) = v488;
                    *((_WORD *)ppvData + 12) = 3;
                    *((_DWORD *)ppvData + 8) = *((_DWORD *)v489 + 212);
                    *((_WORD *)ppvData + 24) = 3;
                    *((_DWORD *)ppvData + 14) = *((_DWORD *)v489 + 213);
                    CoTaskMemFree(bstrString);
                  }
                  SafeArrayUnaccessData(v487);
                  if ( Text >= 0 )
                  {
                    VariantInit(a7);
                    a7->vt = 8204;
                    a7->llVal = (LONGLONG)v487;
                    goto LABEL_1647;
                  }
                }
                goto LABEL_1583;
              }
              goto LABEL_1406;
            case 0x3A9Du:
              inserted = CDoc::OnGetDocDlgFlags((CDoc *)this, a7);
              goto LABEL_306;
            case 0x3A9Eu:
              CDoc::OnWindowStateChanged((CDoc *)this, a5);
              goto LABEL_53;
            case 0x3A9Fu:
              if ( a6->vt != 8204 || !a6->llVal )
                goto LABEL_231;
              *(_OWORD *)&v606.vt = 0;
              memset(&pvarg, 0, sizeof(pvarg));
              memset(&String1, 0, sizeof(String1));
              memset(&pv, 0, sizeof(pv));
              VariantInit(&pvarg);
              VariantInit(&String1);
              VariantInit(&pv);
              v483 = a6->parray;
              rgIndices[0] = 0;
              Text = SafeArrayGetElement(v483, rgIndices, &pvarg);
              if ( Text >= 0 && pvarg.vt == 8 )
              {
                Text = CLSIDFromString(pvarg.bstrVal, (LPCLSID)&v606);
                if ( !Text )
                {
                  v484 = a6->parray;
                  rgIndices[0] = 1;
                  Text = SafeArrayGetElement(v484, rgIndices, &String1);
                  if ( Text >= 0 && String1.vt == 19 )
                  {
                    v485 = a6->parray;
                    rgIndices[0] = 2;
                    Text = SafeArrayGetElement(v485, rgIndices, &pv);
                    if ( Text >= 0 && pv.vt == 8 )
                      CClassTable::AssignInstallPkgInfo((CClassTable *)(this + 678), pv.bstrVal, String1.cyVal.Lo);
                  }
                }
              }
              VariantClear(&pvarg);
              VariantClear(&String1);
              goto LABEL_878;
            case 0x3AA0u:
              Text = -2147024809;
              if ( !a6 )
                goto LABEL_1652;
              if ( a6->vt != 3 )
                goto LABEL_1652;
              v411 = CVersions::MapToNearestDocumentMode(a6->cyVal.Lo, 32, v20, 0xFFFFFFFFLL);
              if ( v411 < 0 )
                goto LABEL_1652;
LABEL_1120:
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 740LL) = v411;
              goto LABEL_53;
            case 0x3AA1u:
              Text = -2147024809;
              if ( !a6 || a6->vt != 3 || !a7 )
                goto LABEL_1652;
              VariantInit(a7);
              v475 = a6->lVal;
              if ( v475 )
              {
                v476 = v475 - 1;
                if ( v476 )
                {
                  if ( v476 != 1 )
                    goto LABEL_1652;
                  v477 = CDocument::Markup(v575);
                  a7->vt = 3;
                  v478 = CMarkup::MarkupVersion(v477);
                  v346 = CMarkupVersion::DocumentMode(v478);
                }
                else
                {
                  v479 = CDocument::Markup(v575);
                  a7->vt = 3;
                  v480 = CMarkup::MarkupVersion(v479);
                  v346 = CMarkupVersion::NativeDocumentMode(v480, 0, 0);
                }
              }
              else
              {
                v481 = (unsigned int)tls_index;
                v482 = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 3;
                v346 = *(_DWORD *)(*(_QWORD *)(v482[v481] + 16LL) + 740LL);
              }
              goto LABEL_924;
          }
          ppvData = GetThreadStateUI();
          *(_QWORD *)&v606.vt = CDoc::PrimaryMarkup((CDoc *)this);
          v467 = *(struct CMarkup **)&v606.vt;
          if ( !a6 )
          {
            Text = -2147024809;
            *(_QWORD *)&v606.vt = (char *)ppvData + 832;
            if ( (unsigned int)IsEqualGUID((char *)ppvData + 832, &GUID_NULL) )
              goto LABEL_1652;
            Text = 0;
            *(GUID *)*(_QWORD *)&v606.vt = GUID_NULL;
            *((_QWORD *)ppvData + 106) = 0;
            if ( !v467 || !(unsigned __int8)CMarkup::IsVersionedChangeEnabled(v467, 100000) )
            {
LABEL_1649:
              if ( !v9 )
                goto LABEL_1651;
              goto LABEL_1650;
            }
            CWorkerManager::StartProfilingAllWorkers(v467, 0);
            goto LABEL_231;
          }
          if ( a6->vt != 8204 )
            goto LABEL_231;
          v468 = a6->parray;
          if ( !v468 )
            goto LABEL_231;
          bstrString = 0;
          Text = SafeArrayAccessData(v468, (void **)&bstrString);
          if ( Text < 0 )
            goto LABEL_1583;
          v469 = a6->parray;
          pvData = 0;
          Text = SafeArrayGetUBound(v469, 1u, (LONG *)&pvData);
          if ( Text >= 0 )
          {
            v470 = pvData + 1;
            pvData = v470;
            if ( v470 == 3 )
            {
              if ( *bstrString == 8 && bstrString[12] == 3 && bstrString[24] == (_WORD)v470 )
              {
                v471 = ppvData;
                v472 = CLSIDFromString(*((LPCOLESTR *)bstrString + 1), (LPCLSID)ppvData + 52);
                v473 = bstrString;
                Text = v472;
                v471[212] = *((_DWORD *)bstrString + 8);
                v471[213] = *((_DWORD *)v473 + 14);
                if ( !v472 )
                {
                  v474 = *(struct CMarkup **)&v606.vt;
                  if ( *(_QWORD *)&v606.vt )
                  {
                    if ( (unsigned __int8)CMarkup::IsVersionedChangeEnabled(*(_QWORD *)&v606.vt, 100000) )
                      CWorkerManager::StartProfilingAllWorkers(v474, 1);
                  }
                }
              }
              else
              {
                Text = -2147024809;
              }
            }
          }
LABEL_1144:
          v410 = a6->parray;
LABEL_1145:
          SafeArrayUnaccessData(v410);
          goto LABEL_231;
        }
        switch ( v19 )
        {
          case 0x3AA4u:
            goto LABEL_131;
          case 0x3AA5u:
            if ( !a6 )
              goto LABEL_131;
            if ( a6->vt != 13 )
              goto LABEL_131;
            v496 = (__int64 (__fastcall ***)(_QWORD, GUID *, VARIANTARG *, __int64))a6->llVal;
            if ( !v496 )
              goto LABEL_131;
            *(_QWORD *)&String1.vt = 0;
            Text = (**v496)(v496, &IID_INavigateEventSink, &String1, 0xFFFFFFFFLL);
            if ( Text >= 0 )
            {
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 744LL) = *(_QWORD *)&String1.vt;
              goto LABEL_1647;
            }
            goto LABEL_1582;
          case 0x3AA8u:
            goto LABEL_131;
          case 0x3AA9u:
            inserted = CDoc::FireOnPopStateEvent((CDoc *)this, v575);
            goto LABEL_306;
          case 0x3AB0u:
            Text = -2147024809;
            if ( !a6 || a6->vt != 11 )
              goto LABEL_1652;
            *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                 + 16LL)
                     + 587LL) = a6->iVal == 0xFFFF;
            goto LABEL_53;
        }
        if ( v19 != 15025 )
          goto LABEL_231;
        Text = -2147024809;
        v490 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( !a7 || !a6 || a6->vt != 3 )
          goto LABEL_1652;
        a7->vt = 11;
        Text = 0;
        v491 = a6->lVal;
        if ( v491 )
        {
          if ( v491 != 1 )
            goto LABEL_630;
          if ( !v490 )
          {
            v494 = 0;
            goto LABEL_1422;
          }
          v492 = CMarkup::MarkupVersion(v490);
          IsNativeQuirksLayoutEmulation = CMarkupVersion::IsNativeQuirksLayoutEmulation(v492);
        }
        else
        {
          if ( !v490 )
          {
            v494 = -(*(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                            + (unsigned int)tls_index)
                                          + 16LL)
                              + 587LL) != 0);
            goto LABEL_1422;
          }
          v495 = CMarkup::MarkupVersion(v490);
          IsNativeQuirksLayoutEmulation = CDCompVideoBackedLayer::IsRenderRequired(v495);
        }
        v494 = !IsNativeQuirksLayoutEmulation - 1;
LABEL_1422:
        a7->iVal = v494;
        goto LABEL_1651;
      }
      if ( v19 > 0x3AC1 )
      {
        if ( v19 == 15042 )
          goto LABEL_350;
        if ( v19 == 15043 )
        {
          if ( a6 )
          {
            if ( a6->vt == 3 )
            {
              v527 = a6->lVal;
              if ( !*((_BYTE *)this + 1016) || CColorValue::GetIntoABGR((CColorValue *)((char *)this + 1020)) != v527 )
              {
                *((_BYTE *)this + 1016) = 1;
                Text = 0;
                if ( !CServer::IsWebPlatformWindowless((CServer *)this) )
                  v527 |= 0xFF000000;
                CColorValue::SetFromABGR((CColorValue *)((char *)this + 1020), v527);
                CDoc::ForceRelayout((CDoc *)this, 1);
                CDoc::SignalDefaultBackgroundColorChanged((CDoc *)this, v527);
              }
            }
          }
          goto LABEL_231;
        }
        if ( v19 != 15044 )
        {
          if ( v19 == 15045 )
            goto LABEL_53;
          goto LABEL_231;
        }
        if ( a7 )
        {
          Text = 0;
          a7->vt = 3;
          if ( *((_BYTE *)this + 1016) )
          {
            v525 = (int)(float)(CColorValue::GetAlpha((CColorValue *)((char *)this + 1020)) * 255.0);
            v381 = ((unsigned __int8)v525 << 24)
                 | CColorValue::GetColorRef((CColorValue *)((char *)this + 1020)) & 0xFFFFFF;
          }
          else
          {
            v526 = (OLE_COLOR *)this[126];
            if ( !v526 )
            {
              a7->lVal = -16777216;
              goto LABEL_231;
            }
            plLbound[0] = 0;
            Text = OleTranslateColor(*v526, 0, (COLORREF *)plLbound);
            if ( Text )
              goto LABEL_231;
            v381 = plLbound[0] | 0xFF000000;
          }
LABEL_1535:
          a7->lVal = v381;
          goto LABEL_1650;
        }
LABEL_231:
        v97 = Text < 0;
        goto LABEL_232;
      }
      if ( v19 == 15041 )
      {
        inserted = CDoc::UpdateFromRegistry((CDoc *)this, a6);
        goto LABEL_306;
      }
      if ( v19 != 15028 )
      {
        if ( v19 == 15029 )
        {
          Text = -2147024809;
          if ( !a6 || a6->vt != 8 )
            goto LABEL_1652;
          if ( a5 == 102 )
          {
            v511 = 1;
          }
          else
          {
            if ( a5 != 103 )
              goto LABEL_1652;
            v511 = 0;
          }
          inserted = CDoc::SetGeolocationUserConsent((CDoc *)this, a6->bstrVal, v511);
          goto LABEL_306;
        }
        if ( v19 != 15030 )
        {
          switch ( v19 )
          {
            case 0x3AB9u:
              inserted = CDoc::ShareAppCacheEventDownwards((CDoc *)this, a6->bstrVal);
              break;
            case 0x3ABEu:
              goto LABEL_1451;
            case 0x3ABFu:
              Text = -2147024809;
              if ( !a6 )
                goto LABEL_1652;
              if ( a6->vt == 1 )
              {
                v497 = 0;
              }
              else
              {
                if ( a6->vt != 8 )
                  goto LABEL_1652;
                v497 = a6->bstrVal;
              }
              inserted = CDoc::SetExtraHeaders((CDoc *)this, v497);
              break;
            default:
              goto LABEL_231;
          }
          goto LABEL_306;
        }
        if ( !a7 )
          goto LABEL_131;
        v509 = CDocument::GetWindowedMarkupContext(v575);
        IsActiveXFilteringEnabled = CMarkup::IsActiveXFilteringEnabled(v509);
        a7->vt = 11;
        v427 = IsActiveXFilteringEnabled != 1;
LABEL_1493:
        a7->iVal = v427 - 1;
        goto LABEL_936;
      }
      if ( !a6 || !a7 )
        goto LABEL_231;
      if ( a6->vt != 13 )
        goto LABEL_230;
      v512 = a6->punkVal;
      if ( !v512 )
        goto LABEL_230;
      *(_QWORD *)plLbound = 0;
      *(GUID *)&v606.vt = CLSID_CElement;
      Text = QIClassID(v512, (struct _GUID *)&v606, (void **)plLbound);
      if ( Text < 0 )
        goto LABEL_1582;
      if ( !(unsigned int)CElement::IsInMarkup(*(CElement **)plLbound) )
      {
        Text = -2147418113;
        goto LABEL_230;
      }
      Text = CElement::EnsureRecalcNotify(*(CElement **)plLbound);
      if ( Text < 0 )
        goto LABEL_1582;
      CRect::CRect((CRect *)&v606);
      CRect::CRect((CRect *)&String1);
      Text = CElement::GetBoundingRect(*(CElement **)plLbound, (struct CRectF *)&String1, 0x4001u, 0);
      if ( Text >= 0
        && ((unsigned int)CElement::IsDeviceFixed(*(CElement **)plLbound)
         || (unsigned int)CElement::IsAncestorPositionFixed(*(CElement **)plLbound, 1))
        && CElement::IsStandardsMode(*(CElement **)plLbound) )
      {
        v513 = CElement::LayoutServices(*(CElement **)plLbound);
        if ( v513 )
        {
          v514 = *(_QWORD *)v513;
          bstrString = 0;
          LOBYTE(pvt[0]) = 0;
          (*(void (__fastcall **)(struct ILayoutServices *, _QWORD, BSTR *, VARTYPE *))(v514 + 432))(
            v513,
            *(_QWORD *)plLbound,
            &bstrString,
            pvt);
          for ( j = bstrString; j; bstrString = j )
          {
            v516 = CDispNode::NodeReader((CDispNode *)j);
            if ( CDispNodeReader::IsTopLevelScroller(v516) )
            {
              v517 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispScroller::GetTotalZoomFactor(v517);
              v518 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispTopLevelScroller::BaseOpticalZoomFactor(v518);
              CRectF::operator/=(&String1);
              break;
            }
            j = (OLECHAR *)CDispNode::GetParentNode((CDispNode *)bstrString);
          }
        }
      }
      CRect::SetRect((CRect *)&v606, (const struct D2D_RECT_F *)&String1, 0);
      if ( Text >= 0 )
      {
        VariantInit(a7);
        a7->vt = 8195;
        v521 = SafeArrayCreateVector(3u, 0, 4u);
        a7->llVal = (LONGLONG)v521;
        if ( v521 )
        {
          *(_DWORD *)pvt = 0;
          SafeArrayPutElement(v521, (LONG *)pvt, &v606);
          v522 = a7->parray;
          v27 = 1;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v522, (LONG *)pvt, &v606.decVal.Hi32);
          v523 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v523, (LONG *)pvt, &v606.decVal.8);
          v524 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v524, (LONG *)pvt, (char *)&v606.decVal.Lo64 + 4);
LABEL_1524:
          CDispClient::AdjustContentSize((CDispClient *)&String1, v519, v520);
          goto LABEL_231;
        }
        Text = -2147024882;
      }
      v27 = 1;
      goto LABEL_1524;
    }
    switch ( v19 )
    {
      case 0x3B60u:
        bstrString = 0;
        v540 = 0;
        if ( a6 )
        {
          if ( a6->vt == 13 )
          {
            v541 = (void (__fastcall ***)(_QWORD, GUID *, struct CHtmParseCtx *))a6->llVal;
            if ( v541 )
            {
              v542 = **v541;
              v543 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)&bstrString);
              v542(v541, &GUID_0000000e_0000_0000_c000_000000000046, v543);
              v540 = (struct IBindCtx *)bstrString;
            }
          }
          v27 = 1;
        }
        v544 = CFlipAheadManager::InvokeCachedTarget((CFlipAheadManager *)(this + 836), v540);
        v55 = bstrString;
        Text = v544;
LABEL_954:
        if ( !v55 )
          goto LABEL_231;
        goto LABEL_111;
      case 0x3B62u:
        v539 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v534 = v539;
        if ( v539 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v539) == 2 )
            goto LABEL_1649;
          plLbound[0] = CMarkup::GetDebugState(v534);
          v535 = plLbound[0];
          CMarkup::SetDebugState(v534, 2);
          v536 = 2;
          goto LABEL_1565;
        }
        break;
      case 0x3B63u:
        v538 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v534 = v538;
        if ( v538 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v538) != 2 )
            goto LABEL_1649;
          plLbound[0] = CMarkup::GetDebugState(v534);
          CMarkup::SetDebugState(v534, 1);
          Text = CDoc::DynamicDetachDebugger((CDoc *)this);
          if ( Text >= 0 )
            goto LABEL_1605;
          v537 = (unsigned int)plLbound[0];
          goto LABEL_1567;
        }
        break;
      case 0x3B64u:
        v533 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v534 = v533;
        if ( v533 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v533) )
            goto LABEL_1649;
          plLbound[0] = CMarkup::GetDebugState(v534);
          v535 = plLbound[0];
          CMarkup::SetDebugState(v534, 1);
          v536 = 1;
LABEL_1565:
          Text = CDoc::DynamicAttachDebugger(this, v535, v536);
          if ( Text >= 0 )
            goto LABEL_1605;
          v537 = (unsigned int)plLbound[0];
LABEL_1567:
          CMarkup::SetDebugState(v534, v537);
          goto LABEL_1583;
        }
        break;
      case 0x3B65u:
        VariantInit(a7);
        a7->vt = 3;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v532 = CDoc::PrimaryMarkup((CDoc *)this);
          DebugState = CMarkup::GetDebugState(v532);
        }
        else
        {
          DebugState = 0;
        }
        goto LABEL_1027;
      default:
        goto LABEL_231;
    }
    Text = -2147418113;
    goto LABEL_1583;
  }
  if ( v604 )
    CScriptCollection::Release(v604);
  Text = -2147467263;
LABEL_15:
  CServer::CLock::~CLock((CServer::CLock *)v603);
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
