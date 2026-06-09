# CDoc::ExecHelper(CDocument *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x1806d4ea8`
- end: `0x1806dc070`
- name: `?ExecHelper@CDoc@@QEAAJPEAVCDocument@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z`
- size: `29128`
- prototype: `__int64 __fastcall(CInPlace **this, struct CDocument *, struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *, VARIANTARG *)`
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
  int Text; // esi
  struct CDocument *v15; // rbx
  CInPlace *v16; // rax
  __int64 v17; // rax
  struct IUnknown *v18; // rcx
  void *v19; // r8
  unsigned int v20; // r13d
  CElement *v21; // rcx
  struct CMarkup *MarkupPtr; // rax
  __int64 v23; // rax
  int v24; // eax
  signed int v25; // edi
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  struct CMarkup *v31; // rbx
  unsigned int v32; // ebx
  int v33; // eax
  CMarkup *v34; // rax
  COmWindowProxy *v35; // rax
  int v36; // eax
  CInPlace **v37; // rbx
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
  LONG HWND; // eax
  const unsigned __int16 *v50; // r8
  unsigned int v51; // ebx
  CInPlace *v52; // rcx
  CInPlace *v53; // rcx
  int v54; // eax
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
  struct CMarkup **v67; // rbx
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
  int v80; // r8d
  __int128 v81; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  struct IDispatch *v83; // rdi
  const unsigned __int16 *v84; // rbx
  CElement *v85; // rax
  struct CMarkup *v86; // rax
  int v87; // eax
  unsigned int v88; // ecx
  CInPlace *v89; // r10
  CInPlace *v90; // rcx
  __int64 v91; // rcx
  VARIANTARG *p_pvarg; // rcx
  LSTATUS v93; // ebx
  wchar_t *v94; // rax
  __int64 v95; // rax
  HANDLE FileW; // rax
  int v97; // eax
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
  SIZE_T v109; // rax
  CInPlace *v110; // rcx
  CInPlace *v111; // rax
  unsigned int v112; // ecx
  unsigned __int8 v113; // al
  struct CBase *v114; // rax
  CImplAry *v115; // rcx
  char *v116; // r8
  __int64 v117; // rdx
  const WCHAR *v118; // r12
  unsigned int v119; // r15d
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
  unsigned int v152; // edx
  CInPlace *v153; // rax
  HWND v154; // rbx
  CInPlace *v155; // rax
  HWND v156; // rax
  CWindowBarProp *v157; // rax
  struct CTreeNode *v158; // rax
  __int64 v159; // r8
  CWindowBarProp *v160; // rax
  struct CTreeNode *v161; // rax
  CElement *v162; // rax
  CMarkup *v163; // rsi
  CCollectionCache *v164; // rax
  VARIANTARG *v165; // rbx
  __int64 v166; // rdx
  struct CElement *v167; // rdx
  __int64 v168; // rcx
  CMarkup *v169; // rcx
  int v170; // ebx
  CInPlace *v171; // rcx
  __int64 (__fastcall ***v172)(_QWORD, GUID *, BSTR *); // rcx
  int v173; // eax
  CMarkup *v174; // rax
  struct CGlyph *GlyphTable; // rax
  int v176; // edx
  CPeerFactoryUrl *v177; // rcx
  unsigned __int16 *Url; // rax
  CMarkup *v179; // rax
  CScriptCollection *ScriptCollection; // rax
  LONG v181; // esi
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
  CTreeNode **TopLayoutElement; // rax
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
  CTitleElement **v227; // rax
  CTitleElement *v228; // rdx
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
  int v251; // eax
  struct IUnknown *v252; // rcx
  int v253; // eax
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
  const OLECHAR **v264; // rax
  CMarkup *v265; // rax
  CMarkup *v266; // rbx
  CMarkup *v267; // rax
  struct CMarkup *v268; // rbx
  __int64 v269; // rsi
  bool v270; // bl
  BYTE v271; // r8
  CMarkup *v272; // rax
  struct CMarkupStyleState *StyleState; // rax
  __int64 v274; // rdx
  void *v275; // r8
  CMarkup *v276; // rbx
  CStr *v277; // rax
  CStr *v278; // rax
  CDispSurface *v279; // rax
  struct IDispRenderTarget *v280; // rax
  struct tagVARIANT *v281; // rcx
  signed __int64 v282; // rax
  int v283; // edx
  int v284; // r8d
  struct CMarkupStyleState *v285; // rax
  struct IUnknown *v286; // rdx
  SAFEARRAY *v287; // rbx
  signed int v288; // edx
  SAFEARRAY *v289; // rbx
  LONG v290; // eax
  LONG v291; // ecx
  HRESULT Element; // eax
  __int64 *v293; // rax
  struct IUnknown *punkVal; // rcx
  const struct CDispNode *v295; // rdx
  struct CRect *v296; // r8
  struct IUnknown *v297; // rcx
  struct CDocument *v298; // r8
  struct CElement *v299; // rdx
  CMarkup *v300; // rbx
  int v301; // eax
  int v302; // esi
  int v303; // edi
  unsigned int v304; // eax
  HMENU EncodingMenu; // rax
  CMarkup *v306; // rax
  const WCHAR *v307; // rbx
  struct CMarkup *v308; // rax
  CMarkup *v309; // rax
  unsigned int v310; // eax
  struct CElement *v311; // rdx
  unsigned int v312; // ebx
  int v313; // eax
  COmWindowProxy *v314; // rcx
  CMarkup **v315; // rax
  __int64 v316; // r8
  struct CMarkup *v317; // rax
  struct CElement *v318; // rax
  int DefaultBlockTag; // eax
  const OLECHAR *v320; // rcx
  BOOL v321; // ebx
  CInPlace *v322; // rcx
  CElement *v323; // rcx
  CMarkup *v324; // rax
  CMarkup *v325; // rax
  struct COmWindowProxy *v326; // rsi
  LONG lVal; // ecx
  __int64 v328; // rbx
  struct GWND *Gwnd; // rax
  struct CElement *v330; // rdx
  int v331; // ecx
  HMENU DocDirMenu; // rax
  LONG v333; // eax
  int v334; // esi
  bool v335; // al
  __int16 *v336; // rdx
  bool v337; // al
  __int16 *v338; // rcx
  __int16 v339; // cx
  HMENU FontSizeMenu; // rax
  LONG v341; // eax
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, BSTR *); // rcx
  CDocument *v343; // rdi
  struct INamedPropertyBag *v344; // rbx
  struct CMarkup *v345; // rax
  CMarkup *v346; // rax
  struct CElement *v347; // rax
  COmWindowProxy *v348; // rcx
  CDocument *v349; // rax
  BSTR v350; // rax
  struct CMarkup *v351; // rax
  struct IDispRenderTarget *v352; // rax
  LONG v353; // eax
  ReadingMode::CTextClusterDetector *v354; // rax
  ReadingMode::CTextClusterDetector *v355; // rax
  ReadingMode::CTextClusterDetector *v356; // rbx
  CInputManager *v357; // rax
  CDeferredActionHandler *v358; // rax
  struct CMarkup *v359; // rax
  CInPlace *v360; // rbx
  int CodePageCore; // r8d
  int v362; // esi
  BSTR v363; // rcx
  bool IsEnterpriseMode; // bl
  CMarkup *v365; // rax
  CMarkupVersion *v366; // rax
  SHORT v367; // ax
  bool v368; // zf
  struct CMarkup *v369; // rax
  struct CMarkup *v370; // rbx
  CInPlace *v371; // rcx
  CInputManager *v372; // rax
  CDeferredActionHandler *v373; // rax
  CInputManager *v374; // rax
  CDeferredActionHandler *v375; // rax
  CInputManager *v376; // rax
  CDeferredActionHandler *v377; // rax
  CInputManager *v378; // rax
  CDeferredActionHandler *v379; // rax
  CInputManager *v380; // rax
  CDeferredActionHandler *v381; // rax
  SHORT v382; // cx
  int v383; // eax
  CVirtualTabStorageEntry *v384; // rcx
  struct CMarkup *v385; // rax
  CPreloadManager *v386; // rax
  struct IDispSystem *DispSystem; // rax
  LONG v388; // eax
  LONG v389; // ecx
  unsigned int Lo; // r9d
  CInPlace **v391; // rax
  LONG DebugState; // eax
  struct THREADSTATEUI *ThreadStateUI; // rax
  struct CMarkup *v394; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdx
  LONG v396; // r8d
  struct CMarkup *v397; // rax
  int v398; // ecx
  SAFEARRAY *Vector; // rax
  __int64 i; // r13
  char v401; // r8
  _QWORD *v402; // rbx
  COptionsHolder *v403; // rax
  CHtmCtx *v404; // rax
  const wchar_t *OriginalUrlContext; // rax
  const OLECHAR *v406; // rcx
  unsigned __int64 v407; // rdi
  size_t v408; // r8
  int v409; // eax
  BSTR v410; // rcx
  _QWORD *v411; // rax
  char v412; // dl
  _QWORD *v413; // rcx
  struct CSecurityContext *v414; // rax
  _QWORD *v415; // rcx
  _QWORD *v416; // rcx
  SAFEARRAY *v417; // rcx
  int v418; // eax
  struct CView *View; // rax
  struct CView *v420; // rdi
  int v421; // ebx
  const struct CDispNode *v422; // rdx
  struct CRect *v423; // r8
  const struct CDispNode *v424; // rdx
  struct CRect *v425; // r8
  struct CView *v426; // rax
  struct CView *v427; // rax
  bool IsMobileOptimizedSite; // al
  struct CView *v429; // rax
  SAFEARRAY *v430; // rcx
  SAFEARRAY *v431; // rcx
  CView *v432; // rax
  CFullScreenState *v433; // rax
  __int16 v434; // cx
  struct IUnknown *v435; // rcx
  CElement *v436; // rcx
  struct IUnknown *v437; // rcx
  CFullScreenState *v438; // rax
  int *v439; // rax
  CRootTracker *RootTracker; // rax
  CDCompLayerManager *v441; // rbx
  struct IDispLayer *v442; // rdi
  __int64 (__fastcall *v443)(struct IDispLayer *, GUID *, struct CHtmParseCtx *); // rbx
  __int64 *v444; // rax
  struct CHtmParseCtx *HpxEmbed; // rax
  struct IDispRenderTarget *v446; // rax
  CAPProcessor *v447; // rcx
  CWindow *v448; // rax
  CWindow *v449; // rbx
  CMarkup *v450; // rdi
  struct COmWindowProxy *v451; // rax
  unsigned __int64 v452; // rdx
  __int64 v453; // r9
  _QWORD *ThreadLocalStoragePointer; // rax
  bool v455; // zf
  struct CView *v456; // rax
  CViewportController *v457; // rcx
  _QWORD *v458; // rax
  unsigned int VirtualTabID; // eax
  unsigned int v460; // edx
  struct CView *v461; // rax
  CViewportController *v462; // rcx
  CInPlace *v463; // rax
  LONG v464; // ecx
  const struct CMarkup *v465; // rax
  CTextScalingSettings *TextScalingSettings; // rax
  const struct CDispNode *v467; // rdx
  struct CRect *v468; // r8
  SAFEARRAY *v469; // rcx
  SAFEARRAY *v470; // rcx
  struct CMarkup *v471; // rax
  COmWindowProxy *v472; // rcx
  unsigned int (__fastcall ***v473)(_QWORD, GUID *, void **, __int64); // rcx
  CInPlace *v474; // rcx
  struct CMarkup *v475; // rbx
  SAFEARRAY *v476; // rcx
  SAFEARRAY *v477; // rcx
  unsigned int v478; // eax
  _DWORD *v479; // rbx
  HRESULT v480; // eax
  BSTR v481; // rcx
  struct CMarkup *v482; // rbx
  LONG v483; // ecx
  int v484; // ecx
  CMarkup *v485; // rax
  const struct CMarkupVersion *v486; // rax
  CMarkup *v487; // rax
  const struct CMarkupVersion *v488; // rax
  __int64 v489; // rdx
  _QWORD *v490; // rax
  SAFEARRAY *v491; // rcx
  SAFEARRAY *v492; // rcx
  SAFEARRAY *v493; // rcx
  SAFEARRAY *v494; // rax
  SAFEARRAY *v495; // rbx
  BSTR v496; // rax
  LPCWSTR v497; // rdx
  CMarkup *v498; // rax
  LONG v499; // edx
  CMarkupVersion *v500; // rax
  bool IsNativeQuirksLayoutEmulation; // al
  SHORT v502; // cx
  CDCompVideoBackedLayer *v503; // rax
  __int64 (__fastcall ***v504)(_QWORD, GUID *, VARIANTARG *, __int64); // rcx
  const unsigned __int16 *v505; // rdx
  int v506; // ecx
  int iVal; // ebx
  LONG v508; // eax
  int v509; // eax
  unsigned int v510; // esi
  const struct CMarkup *v511; // rax
  const unsigned __int16 *UrlRaw; // rax
  const WCHAR *v513; // rcx
  SAFEARRAY *parray; // rax
  const unsigned __int16 *bstrVal; // r8
  unsigned int v516; // ebx
  struct CMarkup *v517; // rax
  int IsActiveXFilteringEnabled; // eax
  int v519; // r8d
  struct IUnknown *v520; // rcx
  struct ILayoutServices *v521; // rax
  __int64 v522; // rcx
  OLECHAR *j; // rax
  CDispNodeReader *v524; // rax
  CDispScroller *v525; // rax
  float TotalZoomFactor; // xmm0_4
  double v527; // xmm6_8
  CDispTopLevelScroller *v528; // rax
  const struct CDispNode *v529; // rdx
  struct CRect *v530; // r8
  SAFEARRAY *v531; // rax
  SAFEARRAY *v532; // rcx
  SAFEARRAY *v533; // rcx
  SAFEARRAY *v534; // rcx
  int v535; // ebx
  OLE_COLOR *v536; // rcx
  LONG v537; // ebx
  CMarkup *v538; // rax
  LONG v539; // ebx
  CMarkup *v540; // rax
  struct CMarkup *RootMarkup; // rax
  struct CMarkup *v542; // rax
  struct CMarkup *v543; // rax
  __int64 v544; // rbx
  unsigned int v545; // esi
  __int64 v546; // r8
  int v547; // edx
  struct CMarkup *v548; // rax
  struct CMarkup *v549; // rax
  struct IBindCtx *v550; // rdx
  void (__fastcall ***v551)(_QWORD, GUID *, struct CHtmParseCtx *); // rdi
  void (__fastcall *v552)(_QWORD, GUID *, struct CHtmParseCtx *); // rbx
  struct CHtmParseCtx *v553; // rax
  int v554; // eax
  unsigned int CodePageFromMenuID; // esi
  int IsCpAutoDetect; // eax
  CInPlace *v557; // rcx
  int v558; // ebx
  HWND v559; // rax
  CElement *v560; // rcx
  CMarkup *v561; // rax
  CMarkup *FrameOrPrimaryMarkup; // rax
  CMarkup *v563; // r13
  CWindowBarProp *v564; // rdi
  struct CSecurityContext *v565; // rax
  struct COmWindowProxy *v566; // rdi
  int CPSrc; // ebx
  int CodePage; // eax
  int v569; // ebx
  CWindowBarProp *v570; // rax
  CTreeNode *v571; // rbx
  struct CMarkup *v572; // rax
  struct CTreeNode *NodeInMarkup; // rax
  struct CElement *ElementClient; // rax
  struct CDocument *v575; // rbx
  CMarkup *v576; // rax
  unsigned int v577; // edi
  struct CMarkupEditContext *EditContext; // rax
  struct _GUID *v579; // rsi
  struct CMarkupEditContext *v580; // rbx
  CEntity *FocusedEntity; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-138h]
  BSTR bstrString; // [rsp+E0h] [rbp-80h] BYREF
  LONG plLbound[2]; // [rsp+E8h] [rbp-78h] BYREF
  CDocument *v585; // [rsp+F0h] [rbp-70h] BYREF
  unsigned int pvData; // [rsp+F8h] [rbp-68h] BYREF
  void *ppvData; // [rsp+100h] [rbp-60h] BYREF
  VARTYPE pvt[2]; // [rsp+108h] [rbp-58h] BYREF
  unsigned int v589; // [rsp+10Ch] [rbp-54h]
  LONG rgIndices[2]; // [rsp+110h] [rbp-50h] BYREF
  struct _GUID *v591; // [rsp+118h] [rbp-48h]
  LPCWSTR pszSubKey; // [rsp+120h] [rbp-40h] BYREF
  struct IUnknown *v593; // [rsp+128h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+130h] [rbp-30h] BYREF
  VARIANTARG pv; // [rsp+148h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+160h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+168h] [rbp+8h] BYREF
  CElement *v598[5]; // [rsp+170h] [rbp+10h] BYREF
  char v599; // [rsp+198h] [rbp+38h]
  int v600; // [rsp+19Ch] [rbp+3Ch]
  CIPrintCollection *v601; // [rsp+1A0h] [rbp+40h]
  __int64 v602; // [rsp+1A8h] [rbp+48h]
  __int64 v603; // [rsp+1B0h] [rbp+50h]
  size_t BufferCount; // [rsp+1C0h] [rbp+60h] BYREF
  wchar_t *Buffer; // [rsp+1C8h] [rbp+68h] BYREF
  __int128 v606; // [rsp+1D0h] [rbp+70h] BYREF
  VARIANTARG *v607; // [rsp+1E0h] [rbp+80h]
  __int128 v608; // [rsp+1E8h] [rbp+88h] BYREF
  __int128 *v609; // [rsp+1F8h] [rbp+98h]
  int v610; // [rsp+200h] [rbp+A0h] BYREF
  __int64 *v611[2]; // [rsp+208h] [rbp+A8h] BYREF
  CScriptCollection *v612; // [rsp+218h] [rbp+B8h]
  VARIANTARG String1; // [rsp+220h] [rbp+C0h] BYREF
  VARIANTARG v614; // [rsp+240h] [rbp+E0h] BYREF
  _BYTE v615[32]; // [rsp+260h] [rbp+100h] BYREF
  _WORD Data[264]; // [rsp+280h] [rbp+120h] BYREF
  OLECHAR psz[2088]; // [rsp+490h] [rbp+330h] BYREF

  v7 = a6;
  v9 = a7;
  v589 = a4;
  *(_QWORD *)&v614.vt = a6;
  *(_QWORD *)&String1.vt = a7;
  v12 = a2;
  v591 = a3;
  v585 = a2;
  if ( !CBase::IsCmdGroupSupported(a3) )
    return 2147746052LL;
  CDoc::CLock::CLock((CDoc::CLock *)v611, (struct CDoc *)this, 0);
  v609 = 0;
  v607 = 0;
  v593 = 0;
  Text = -2147221248;
  v608 = 0;
  v606 = 0;
  if ( !a3 )
  {
    Text = CDoc::BrowserDocumentServerExec((CDoc *)this, v12, a4, a5, a6, a7);
    if ( Text != -2147221248 )
      goto LABEL_1657;
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
      v593 = v18;
    }
    else
    {
      v16 = this[103];
      if ( !v16 )
      {
        if ( v612 )
          CScriptCollection::Release(v612);
        Text = -2147418113;
        goto LABEL_15;
      }
      v12 = *(struct CDocument **)(*((_QWORD *)v16 + 15) + 120LL);
      v585 = v12;
    }
    plLbound[0] = CBase::IDMFromCmdID(a3, v589);
    v20 = plLbound[0];
    if ( (unsigned int)(plLbound[0] - 3700) <= 0x20 )
    {
      v21 = this[544];
      if ( !v21 || (MarkupPtr = CElement::GetMarkupPtr(v21)) == 0 )
      {
        v23 = *((_QWORD *)v12 + 7);
        MarkupPtr = v23 ? *(struct CMarkup **)(v23 + 104) : (struct CMarkup *)*((_QWORD *)v12 + 6);
        if ( !MarkupPtr )
          goto LABEL_1657;
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
        v357 = CDoc::InputManager((CDoc *)this);
        v358 = CInputManager::DeferredActionHandler(v357);
        NormZoomPercent = CDeferredActionHandler::RegisterVTabNavigate(v358);
        goto LABEL_940;
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
                        v40 = v585;
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
                            v74 = *((_QWORD *)v585 + 7);
                            if ( v74 )
                              v31 = *(struct CMarkup **)(v74 + 104);
                            else
                              v31 = (struct CMarkup *)*((_QWORD *)v585 + 6);
LABEL_170:
                            if ( *((_QWORD *)v31 + 18) )
                              v31 = (struct CMarkup *)*((_QWORD *)v31 + 18);
                            if ( (*((_DWORD *)v31 + 187) & 0x4000000) != 0 )
                            {
                              v76 = (COptionsHolder *)MemoryProtection::HeapAlloc<1>(
                                                        (MemoryProtection *)g_hProcessHeap,
                                                        0x80u);
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
                                    *(_OWORD *)v615 = v81;
                                    *(_QWORD *)&v615[16] = pRecInfo;
                                    COptionsHolder::put_execArg(
                                      (struct COptionsHolder *)((char *)v75 + 48),
                                      (struct tagVARIANT *)v615);
                                    Text = GetFindText(&bstrString);
                                    if ( !Text )
                                    {
                                      BASICPROPPARAMS::SetStringProperty(
                                        (BASICPROPPARAMS *)qword_1811F5878,
                                        bstrString,
                                        (__int64)v75,
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
                                        memset(&v614, 0, sizeof(v614));
                                        if ( !v89
                                          || (*((_DWORD *)this + 1215) & 0x400000) != 0
                                          || (Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v89 + 32LL))(
                                                       v89,
                                                       &CGID_DocHostCommandHandler,
                                                       42,
                                                       v88,
                                                       &pv,
                                                       &v614)) != 0 )
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
                                                       &v614);
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
                    v34 = CDocument::Markup(v585);
                    v35 = CMarkup::Window(v34);
                    v36 = COmWindowProxy::Fire_onbeforeunload(v35, 1);
                    Text = 0;
                    if ( !a7 )
                      goto LABEL_1656;
                    a7->vt = 11;
                    a7->iVal = -(v36 != 0);
LABEL_1655:
                    if ( !v7 )
                      goto LABEL_1657;
LABEL_1656:
                    CDoc::DeferUpdateUI((CDoc *)this);
                    goto LABEL_1657;
                  }
LABEL_1456:
                  v506 = *((_DWORD *)this + 1217);
                  if ( (v506 & 0x800) != 0 )
                    goto LABEL_231;
                  iVal = 0;
                  v508 = *((_DWORD *)this + 1215);
                  plLbound[0] = v508;
                  if ( v589 == 93 && (v508 & 1) == 0
                    || v589 == 15038
                    || (v506 & 0x80u) != 0
                    || (unsigned __int8)IEConfiguration_GetBool(268435481) )
                  {
                    a5 = 0;
                    if ( !a6 || a6->vt != 2 )
                      goto LABEL_1469;
                    a6->iVal &= ~1u;
                  }
                  else if ( !a6 )
                  {
                    goto LABEL_1469;
                  }
                  if ( a6->vt == 2 )
                    iVal = a6->iVal;
LABEL_1469:
                  v509 = iVal | 1;
                  if ( a5 != 2 )
                    v509 = iVal;
                  v510 = v509 | 0x1000000;
                  if ( v20 != 15038 )
                    v510 = v509;
                  if ( (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  {
                    v511 = CDoc::PrimaryMarkup((CDoc *)this);
                    UrlRaw = CMarkup::GetUrlRaw(v511);
                    v513 = L"about:blank";
                    if ( UrlRaw )
                      v513 = UrlRaw;
                    if ( *v513 && !wcscmp_0(v513, L"outday://") )
                      *((_DWORD *)this + 1215) |= 0x400000u;
                  }
                  if ( v20 == 27 )
                  {
                    if ( a6 && (a6->vt & 0x6000) == 0x6000 )
                    {
                      parray = a6->parray;
LABEL_1486:
                      if ( a6->vt == 8 )
                      {
                        bstrVal = a6->bstrVal;
LABEL_1489:
                        v516 = a5;
                        Text = CDoc::PrintHandler((CDoc *)this, v585, bstrVal, 0, v510, parray, a5, a6, a7, 0);
                        if ( Text )
                          goto LABEL_1657;
                        if ( (*((char *)this + 4868) < 0 || (unsigned __int8)IEConfiguration_GetBool(268435481))
                          && v20 != 15038 )
                        {
                          ++*((_DWORD *)this + 1237);
                        }
                        *((_DWORD *)this + 1215) ^= (*((_DWORD *)this + 1215) ^ plLbound[0]) & 0x400000;
LABEL_1590:
                        if ( v20 >= 0xE19 )
                        {
                          if ( v20 <= 0xE73 )
                          {
                            CodePageFromMenuID = GetCodePageFromMenuID(v20);
                            *(_QWORD *)&v614.vt = GetThreadStateUI();
                            if ( CodePageFromMenuID == -1 )
                            {
                              if ( v20 != 3699
                                || (IsCpAutoDetect = CDoc::IsCpAutoDetect((CDoc *)this),
                                    CDoc::SetCpAutoDetect((CDoc *)this, IsCpAutoDetect == 0),
                                    !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this))
                                || !(unsigned int)CMLang::IsMLangAvailable((CMLang *)&g_MLang) )
                              {
LABEL_1608:
                                ++*(_DWORD *)(*(_QWORD *)&v614.vt + 604LL);
                                goto LABEL_53;
                              }
                              CodePageFromMenuID = 50001;
                              if ( g_cpDefault == 932 )
                                CodePageFromMenuID = 50932;
                            }
                            v557 = this[12];
                            if ( v557 )
                            {
                              v558 = (_DWORD)this[556] & 0x40000000;
                              v559 = CInPlace::_hwnd_Get(v557);
                              if ( !(unsigned int)CMLang::ValidateCodePage(
                                                    (CMLang *)&g_MLang,
                                                    g_cpDefault,
                                                    CodePageFromMenuID,
                                                    v559,
                                                    1,
                                                    v558) )
                              {
                                v560 = this[544];
                                v561 = v560 ? CElement::GetMarkupPtr(v560) : CDocument::Markup(v585);
                                FrameOrPrimaryMarkup = CMarkup::GetFrameOrPrimaryMarkup(v561);
                                v563 = FrameOrPrimaryMarkup;
                                if ( FrameOrPrimaryMarkup )
                                {
                                  v564 = CMarkup::Root(FrameOrPrimaryMarkup);
                                  CNotification::CNotification((CNotification *)v598);
                                  v565 = CWindowBarProp::SecurityContext(v564);
                                  CNotification::Initialize(
                                    (__int64)v598,
                                    59,
                                    v564,
                                    (__int64)v565,
                                    CodePageFromMenuID,
                                    0);
                                  if ( !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this)
                                    && !(unsigned int)CMarkup::HaveCodePageMetaTag(v563) )
                                  {
                                    CDoc::SaveDefaultCodepage((CDoc *)this, CodePageFromMenuID);
                                  }
                                  CDoc::BroadcastNotify((CDoc *)this, v598);
                                  CMarkup::BubbleDownCodePage(v563, CodePageFromMenuID);
                                  v566 = CMarkup::Window(v563);
                                  CPSrc = CMarkup::GetCPSrc((__int64)v563);
                                  CodePage = CMarkup::GetCodePage(v563);
                                  COmWindowProxy::ExecRefresh((__int64)v566, 5, CodePage, CPSrc);
                                }
                              }
                            }
                            goto LABEL_1608;
                          }
                          a5 = v516;
                        }
                        goto LABEL_1610;
                      }
LABEL_1488:
                      bstrVal = 0;
                      goto LABEL_1489;
                    }
                  }
                  else
                  {
                    parray = 0;
                    if ( v20 != 15038 )
                      goto LABEL_1488;
                  }
                  parray = 0;
                  if ( !a6 )
                    goto LABEL_1488;
                  goto LABEL_1486;
                }
                v51 = 3;
                goto LABEL_104;
              }
              if ( plLbound[0] != 71 )
              {
                switch ( plLbound[0] )
                {
                  case 93:
                    goto LABEL_1456;
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
                        McGenEventWrite_EventWriteTransfer(
                          (REGHANDLE *)&BERP_IE_Context,
                          (const EVENT_DESCRIPTOR *)MSHTML_PRINTPREVIEW_START,
                          0,
                          1u,
                          (PEVENT_DATA_DESCRIPTOR)&v614);
                      if ( a6 && a6->vt == 8 )
                        v50 = a6->bstrVal;
                      else
                        v50 = 0;
                      Text = CDoc::PrintHandler((CDoc *)this, v585, v50, 0, 0, 0, a5, a6, a7, 1);
                      if ( (Microsoft_IEEnableBits & 0x10000) != 0 )
                        McGenEventWrite_EventWriteTransfer(
                          (REGHANDLE *)&BERP_IE_Context,
                          (const EVENT_DESCRIPTOR *)MSHTML_PRINTPREVIEW_STOP,
                          0,
                          1u,
                          (PEVENT_DATA_DESCRIPTOR)&v614);
                      goto LABEL_1652;
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
LABEL_1657:
                  CDoc::CLock::~CLock(v611);
                  return (unsigned int)Text;
                }
                v43 = this[540];
                if ( v43 && a5 != 2 && (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v43 + 32LL))(
                           v43,
                           &CGID_DocHostCommandHandler,
                           v589,
                           a5,
                           a6,
                           a7);
                if ( Text < 0 )
                {
                  CDoc::EnsureBackupUIHandler((CDoc *)this);
                  v44 = this[539];
                  if ( !v44 )
                    goto LABEL_1588;
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
                    goto LABEL_1657;
                  }
                  v45 = this[103];
                  v46 = this[51];
                  pv.vt = 13;
                  v47 = this[50];
                  v48 = *(_QWORD *)(*((_QWORD *)v45 + 15) + 120LL);
                  HWND = CServer::GetHWND((CServer *)this);
                  pv.llVal = (LONGLONG)SetPrintCommandParameters(
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
                                         (__int64)&pvarg,
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
LABEL_1610:
                if ( Text != -2147221248 )
                  goto LABEL_1644;
                if ( v20 != 15031 || !(unsigned __int8)IEConfiguration_GetBool(268435481) )
                {
                  *((_QWORD *)&v608 + 1) = v591;
                  v609 = &v606;
                  *(_QWORD *)&v606 = __PAIR64__(a5, v589);
                  LODWORD(v608) = 0;
                  *((_QWORD *)&v606 + 1) = v7;
                  v607 = a7;
                  if ( this[544] )
                  {
                    if ( ((_DWORD)this[608] & 0x40000) != 0 )
                    {
                      v569 = 1;
                      CDoc::BeginUserInitiatedAction((CDoc *)this, 1);
                    }
                    else
                    {
                      v569 = 0;
                    }
                    Text = CDoc::RouteCTElement((CDoc *)this, this[544], (struct CDoc::CTArg *)&v608, v585);
                    if ( v569 )
                      CDoc::EndUserInitiatedAction((CDoc *)this);
                    if ( Text != -2147221248 )
                      goto LABEL_1644;
                  }
                  if ( CDoc::GetActiveElement((CDoc *)this) )
                  {
                    v570 = CDoc::GetActiveElement((CDoc *)this);
                    v571 = CWindowBarProp::SecurityContext(v570);
                    v572 = CDocument::Markup(v585);
                    NodeInMarkup = CTreeNode::GetNodeInMarkup(v571, v572);
                    if ( NodeInMarkup )
                    {
                      ElementClient = (struct CElement *)SP<Tree::CIE9DocumentLayout>::operator->((__int64)NodeInMarkup);
                      v575 = v585;
                    }
                    else
                    {
                      v575 = v585;
                      v576 = CDocument::Markup(v585);
                      ElementClient = CMarkup::GetElementClient(v576);
                    }
                    if ( ElementClient )
                    {
                      Text = CDoc::RouteCTElement((CDoc *)this, ElementClient, (struct CDoc::CTArg *)&v608, v575);
                      if ( Text != -2147221248 )
                      {
                        v577 = a5;
LABEL_1646:
                        if ( v20 == 15 && !CDoc::HasSelection((CDoc *)this) )
                        {
                          v455 = Text == 0;
                          if ( Text < 0 )
                            goto LABEL_1653;
                          goto LABEL_1649;
                        }
LABEL_1652:
                        v455 = Text == 0;
LABEL_1653:
                        if ( !v455 )
                          goto LABEL_1657;
                        goto LABEL_1654;
                      }
                    }
                  }
                }
LABEL_441:
                v198 = this[126];
                if ( (!v198 || !*((_BYTE *)v198 + 38) || !*((_DWORD *)this + 1231))
                  && (int)CServer::State((__int64)this) >= 3
                  && (*((char *)this + 4868) >= 0 || v20 != 2315) )
                {
                  v199 = v593;
                  *(_QWORD *)&String1.vt = 0;
                  if ( v593 )
                    goto LABEL_1630;
                  SelectionMarkup = CDoc::GetSelectionMarkup((CDoc *)this, (struct CMarkup **)&v593);
                  v199 = v593;
                  if ( !v593 )
                  {
                    if ( CDoc::GetActiveElement((CDoc *)this) )
                    {
                      v201 = CDoc::GetActiveElement((CDoc *)this);
                      v199 = (struct IUnknown *)CElement::GetMarkupPtr(v201);
                      v593 = v199;
                    }
                    else
                    {
                      v199 = v593;
                    }
                  }
                  if ( SelectionMarkup >= 0 && v199 )
                  {
LABEL_1630:
                    Text = CMarkup::EnsureEditRouter((CMarkup *)v199, (struct CEditRouter **)&String1);
                    if ( Text >= 0 )
                    {
                      CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&v614);
                      EditContext = CMarkup::GetEditContext((CMarkup *)v593);
                      v579 = v591;
                      v580 = EditContext;
                      if ( v591 && _(v591, &CGID_MSHTML) )
                      {
                        if ( v20 - 15 <= 1 )
                        {
                          v25 = 0;
LABEL_1638:
                          *((_DWORD *)v580 + 10) &= ~0x800u;
                          *((_DWORD *)v580 + 10) |= v25 << 11;
                          if ( v25 )
                            CDoc::CDOMTextInputScope::Init((CDoc::CDOMTextInputScope *)&v614, (struct CDoc *)this, 2);
                          *((_DWORD *)v580 + 10) |= 0x400u;
                          goto LABEL_1641;
                        }
                        if ( v20 == 26 || v20 - 2500 <= 1 )
                          goto LABEL_1638;
                      }
LABEL_1641:
                      v577 = a5;
                      Text = CEditRouter::ExecEditCommand(
                               *(CEditRouter **)&String1.vt,
                               v579,
                               v589,
                               a5,
                               v7,
                               a7,
                               v593,
                               (struct CMarkup *)v593,
                               (struct CDoc *)this);
                      if ( v580 == CMarkup::GetEditContext((CMarkup *)v593) )
                        *((_DWORD *)v580 + 10) &= 0xFFFFF3FF;
                      CDoc::CDOMTextInputScope::~CDOMTextInputScope((CDoc::CDOMTextInputScope *)&v614);
LABEL_1645:
                      if ( Text == -2147221248 )
                      {
LABEL_1649:
                        if ( CDoc::EntityHasFocus((CDoc *)this) )
                        {
                          FocusedEntity = CDoc::GetFocusedEntity((CDoc *)this);
                          if ( FocusedEntity )
                            Text = CEntity::Exec(FocusedEntity, v591, v589, v577, v7, a7);
                        }
                        goto LABEL_1652;
                      }
                      goto LABEL_1646;
                    }
                  }
                }
LABEL_1644:
                v577 = a5;
                goto LABEL_1645;
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
                           v589,
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
                    v368 = (unsigned int)CTQueryStatus(
                                           *((struct IUnknown **)v59 + 10),
                                           0,
                                           1u,
                                           (struct _tagOLECMD *const)&ppvData,
                                           0) == 0;
                    v61 = bstrString;
                    if ( v368 && HIDWORD(ppvData) == 3 )
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
                  v62 = *((_QWORD *)v585 + 7);
                  if ( v62 )
                    v63 = *(struct CMarkup **)(v62 + 104);
                  else
                    v63 = (struct CMarkup *)*((_QWORD *)v585 + 6);
                  Text = CDoc::PromptSave((CDoc *)this, v63, 1, v60, v61);
                }
LABEL_137:
                if ( Text == 1 )
                  Text = -2147221245;
                goto LABEL_231;
              }
              if ( *(void (**)())(*(_QWORD *)CDoc::GetActiveElement((CDoc *)this) + 1624LL) == _vtguard )
              {
                v56 = CDoc::GetActiveElement((CDoc *)this);
                Text = (*(__int64 (__fastcall **)(struct CElement *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v56 + 368LL))(
                         v56,
                         v591,
                         v589,
                         a5,
                         a6,
                         a7);
                goto LABEL_118;
              }
LABEL_1660:
              _report_securityfailure(1u);
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
                    v64 = CDocument::Markup(v585);
                    if ( CMarkup::HasWindow(v64) )
                    {
                      v65 = CMarkup::Window(v64);
                      if ( *((_QWORD *)COptionsHolder::SecurityContext(v65) + 14) )
                      {
                        v66 = CMarkup::Window(v64);
                        v67 = (struct CMarkup **)COptionsHolder::SecurityContext(v66);
                        v68 = CMarkup::Window(v64);
                        v69 = COptionsHolder::SecurityContext(v68);
                        CWindow::ReleaseMarkupPending(v67, *((struct CMarkup **)v69 + 14));
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
                inserted = CDoc::SetDesignMode((CDoc *)this, v585, v72);
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
                      v368 = *((_BYTE *)v105 + 56) == 0;
                      Buffer = 0;
                      if ( v368 )
                        v106 = L"\\Scripts";
                      LODWORD(v585) = 12;
                      ppvData = v106;
                      v107 = -1;
                      do
                        ++v107;
                      while ( *(_WORD *)(*((_QWORD *)v105 + 184) + 2 * v107) );
                      if ( (int)UIntAdd(0xCu, v107, (unsigned int *)&v585) < 0 )
                        goto LABEL_273;
                      if ( (int)UIntAdd((unsigned int)v585, 14, (unsigned int *)&v585) < 0 )
                        goto LABEL_273;
                      v108 = -1;
                      do
                        ++v108;
                      while ( *((_WORD *)ppvData + v108) );
                      if ( (int)UIntAdd((unsigned int)v585, v108, (unsigned int *)&v585) < 0 )
                        goto LABEL_273;
                      v109 = 2LL * (unsigned int)v585;
                      if ( !is_mul_ok((unsigned int)v585, 2u) )
                        v109 = -1;
                      pszSubKey = (LPCWSTR)operator new[](v109, (const struct MemoryProtection::leaf_t *)&leaf);
                      if ( pszSubKey )
                      {
                        v110 = this[126];
                        BufferCount = 0;
                        StringCchPrintfExW(
                          (wchar_t *)pszSubKey,
                          (unsigned int)v585,
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
                          plLbound[0] = (unsigned __int8)RegistryAppropriateSidFromSid(v113);
                        }
                        v114 = CListenerDispatch::GetThis((CInPlace *)((char *)this[126] + 112));
                        v115 = (CInPlace *)((char *)this[126] + 112);
                        ppvData = v114;
                        rgIndices[0] = CImplAry::Size(v115);
                        v117 = (unsigned int)rgIndices[0];
                        if ( rgIndices[0] > 0 )
                        {
                          v118 = pszSubKey;
                          v119 = plLbound[0];
                          v116 = (char *)ppvData;
                          do
                          {
                            v120 = *(_DWORD *)(*(_QWORD *)v116 + 8LL);
                            if ( !*((_BYTE *)this[126] + 56) )
                            {
                              v121 = DefaultSidForCodePage(v120);
                              v122 = RegistryAppropriateSidFromSid(v121);
                              LODWORD(v117) = rgIndices[0];
                              v116 = (char *)ppvData;
                              v120 = v122;
                            }
                            if ( v120 == v119 )
                            {
                              *(_WORD *)(*(_QWORD *)v116 + 2LL) = v103;
                              _ultow_s(v120, Buffer, BufferCount, 10);
                              v123 = IsProtectedModeProcess();
                              v124 = 3;
                              if ( v123 )
                              {
                                SHSetValueW(HKEY_CURRENT_USER, v118, L"IEFontSize", 3u, &pvData, 4u);
                                if ( LOBYTE(pvt[0]) )
                                  SHSetValueW(HKEY_CURRENT_USER, v118, L"IEFontSizePrivate", 3u, &pvData, 4u);
                              }
                              else
                              {
                                if ( v119 - 3 <= 0x25 )
                                  v124 = v119;
                                if ( (int)StringCchPrintfW((unsigned __int16 *)v615, 0x10u, L"%d", v124) >= 0 )
                                {
                                  SetBinaryExt(
                                    SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizeExt[0],
                                    2,
                                    (unsigned int)v615,
                                    (unsigned int)&pvData,
                                    4);
                                  if ( LOBYTE(pvt[0]) )
                                    SetBinaryExt(
                                      SettingStore::IEVALUE_Trident_OptionSetting_Scripts_IEFontSizePrivateExt[0],
                                      2,
                                      (unsigned int)v615,
                                      (unsigned int)&pvData,
                                      4);
                                }
                              }
                              LODWORD(v117) = rgIndices[0];
                              v116 = (char *)ppvData;
                            }
                            v116 += 8;
                            v117 = (unsigned int)(v117 - 1);
                            ppvData = v116;
                            rgIndices[0] = v117;
                          }
                          while ( (int)v117 > 0 );
                          v7 = *(VARIANTARG **)&v614.vt;
                          v9 = *(VARIANTARG **)&String1.vt;
                          v102 = bstrString;
                        }
                        Free_progressEventParams((void *)pszSubKey, v117, v116);
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
                      plLbound[0] = (unsigned __int8)RegistryAppropriateSidFromSid(v127);
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
                          v131 = (unsigned __int8)RegistryAppropriateSidFromSid(v132);
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
              CMarkup::EnsureFormatCacheChange(v134);
              CDoc::ForceRelayout((CDoc *)this, 0);
              v135 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL);
              ++*(_DWORD *)(v135 + 604);
              COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v615);
              v136 = v589;
              *(_QWORD *)v615 = v591;
              *(_DWORD *)&v615[8] = v589;
              CNotification::CNotification((CNotification *)v598);
              v137 = CDoc::PrimaryRoot((CDoc *)this);
              CNotification::Command((CNotification *)v598, v137, v615, 0);
              CDoc::BroadcastNotify((CDoc *)this, v598);
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
              Text = StringCchCatNW(Data, 260, L"\\readme.htm", 259 - v95);
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
                          0);
LABEL_229:
                  Text = v97;
                }
LABEL_230:
                v25 = 1;
                goto LABEL_231;
              }
LABEL_1587:
              v25 = 1;
              goto LABEL_1588;
            }
            LODWORD(lpcbData) = 11;
            CDoc::ShowMessage((CDoc *)this, &v610, 0, 0, 0x5EDu, lpcbData, 0, 10570, 1001, &Source, &Source);
LABEL_53:
            Text = 0;
            goto LABEL_1654;
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
              if ( *(void (**)())(*(_QWORD *)v142 + 1624LL) != _vtguard )
                goto LABEL_1660;
              Text = (*(__int64 (__fastcall **)(CInPlace *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v142 + 368LL))(
                       v142,
                       v591,
                       v589,
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
              if ( *(void (**)())(*(_QWORD *)CDoc::GetActiveElement((CDoc *)this) + 1624LL) != _vtguard )
                goto LABEL_1660;
              v144 = CDoc::GetActiveElement((CDoc *)this);
              Text = (*(__int64 (__fastcall **)(struct CElement *, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v144 + 368LL))(
                       v144,
                       v591,
                       v589,
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
          v145 = *((_QWORD *)v585 + 7);
          if ( v145 )
            v141 = *(struct CMarkup **)(v145 + 104);
          else
            v141 = (struct CMarkup *)*((_QWORD *)v585 + 6);
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
                  memset(&v614, 0, sizeof(v614));
                  VariantInit(&v614);
                  v165 = 0;
                  pvData = ConvertSBCMDID(plLbound[0]);
                  plLbound[0] = 0;
                  if ( v20 == 2135 )
                  {
                    v614.vt = 3;
                    v614.lVal = 1;
LABEL_361:
                    v165 = &v614;
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
                    if ( v614.vt == 13 && v614.llVal )
                      (*(void (__fastcall **)(LONGLONG, __int64))(*v614.pllVal + 16))(v614.llVal, v166);
                    goto LABEL_230;
                  }
                  if ( v20 != 2266 )
                  {
                    v614.vt = 3;
                    v170 = 6;
                    if ( v20 != 2130 )
                      v170 = 1;
                    v614.lVal = v170 | 0x20000;
                    goto LABEL_361;
                  }
                  v167 = this[544];
                  bstrString = 0;
                  Text = GetExecDocument((struct CDocument **)&bstrString, v167, v585);
                  if ( Text < 0 )
                    goto LABEL_1657;
                  if ( bstrString )
                  {
                    v168 = *((_QWORD *)bstrString + 7);
                    if ( v168 )
                      v169 = *(CMarkup **)(v168 + 104);
                    else
                      v169 = (CMarkup *)*((_QWORD *)bstrString + 6);
                    if ( !(unsigned int)CMarkup::IsPrimaryMarkup(v169) )
                    {
                      v614.vt = 13;
                      Text = CDocument::QueryInterface((CDocument *)bstrString, &IID_IUnknown, &v614.byref);
                      if ( Text )
                        goto LABEL_1657;
                      v165 = &v614;
                    }
                    plLbound[0] = 1;
                    goto LABEL_362;
                  }
LABEL_350:
                  Text = -2147467259;
                  goto LABEL_1657;
                case 2270:
                  if ( !this[544] )
                  {
                    *(_QWORD *)&String1.vt = 0;
                    v162 = CDoc::GetActiveElement((CDoc *)this);
                    v163 = CElement::GetMarkupPtr(v162);
                    if ( (unsigned int)CMarkup::EnsureCollectionCache(v163, 4) )
                      goto LABEL_344;
                    v164 = CMarkup::CollectionCache(v163);
                    if ( (unsigned int)CCollectionCache::GetElementAtIndex(v164, 4, 0, (struct CElement **)&String1) )
                      goto LABEL_344;
                    if ( *(void (**)())(**(_QWORD **)&String1.vt + 1624LL) != _vtguard )
                      _report_securityfailure(1u);
                    Text = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(**(_QWORD **)&String1.vt + 368LL))(
                             *(_QWORD *)&String1.vt,
                             v591,
                             v589,
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
                  CMessage::CMessage((CMessage *)Data, v156, 123, (__int64)v154, 0xFFFFFFFFLL);
                  v157 = CDoc::GetActiveElement((CDoc *)this);
                  v158 = CWindowBarProp::SecurityContext(v157);
                  Text = CMessage::SetNodeHit((struct CTreeNode **)Data, v158, v159);
                  if ( Text )
                  {
                    CMessage::~CMessage((struct CTreeNode **)Data);
                    goto LABEL_1657;
                  }
                  v160 = CDoc::GetActiveElement((CDoc *)this);
                  v161 = CWindowBarProp::SecurityContext(v160);
                  Text = CDoc::PumpMessage((CDoc *)this, (struct CMessage *)Data, v161, 0);
                  CMessage::~CMessage((struct CTreeNode **)Data);
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
                  v146 = *((_QWORD *)v585 + 7);
                  if ( v146 )
                    v147 = *(CMarkup **)(v146 + 104);
                  else
                    v147 = (CMarkup *)*((_QWORD *)v585 + 6);
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
                v149 = v585;
                Text = 0;
                a7->vt = 11;
                v150 = *((_QWORD *)v149 + 7);
                if ( v150 )
                  v151 = *(CMarkup **)(v150 + 104);
                else
                  v151 = (CMarkup *)*((_QWORD *)v149 + 6);
                a7->iVal = -((unsigned int)CMarkup::IsPrintTemplate(v151) != 0);
                goto LABEL_1655;
              }
LABEL_330:
              Text = -2147467261;
              goto LABEL_1657;
            }
LABEL_835:
            v321 = 0;
            if ( plLbound[0] == 2300 && a6 && a6->vt == 3 )
              v321 = (a6->lVal & 0x7FF0000) != 0;
            v322 = this[540];
            if ( v322 )
              Text = (*(__int64 (__fastcall **)(CInPlace *, const GUID *, _QWORD, _QWORD, struct tagVARIANT *, VARIANTARG *))(*(_QWORD *)v322 + 32LL))(
                       v322,
                       &CGID_DocHostCommandHandler,
                       (unsigned int)plLbound[0],
                       a5,
                       a6,
                       a7);
            if ( Text >= 0 )
              goto LABEL_1589;
            if ( ((plLbound[0] - 6041) & 0xFFFFFFFD) == 0
              || v321
              || ((v323 = this[544]) == 0 ? (v324 = CDocument::Markup(v585)) : (v324 = CElement::GetMarkupPtr(v323)),
                  !v324 || (v325 = CMarkup::GetFrameOrPrimaryMarkup(v324)) == 0 || (v326 = CMarkup::Window(v325)) == 0) )
            {
              v326 = this[103];
            }
            if ( plLbound[0] == 2300 )
            {
              if ( a6 && a6->vt == 3 )
                lVal = a6->lVal;
              else
                lVal = 0;
            }
            else
            {
              lVal = ((unsigned int)(plLbound[0] - 6043) > 1) + 8195;
            }
            v328 = lVal;
            Gwnd = GetGwnd();
            inserted = _GWPostMethodCallEx(
                         Gwnd,
                         (unsigned __int64)v326,
                         (__int64)COmWindowProxy::ExecRefreshCallback,
                         v328,
                         0,
                         0);
            goto LABEL_306;
          }
          switch ( plLbound[0] )
          {
            case 2302:
              if ( a6 && a6->vt == 3 )
              {
                v181 = a6->lVal;
                if ( ((*((_DWORD *)this + 1215) >> 4) & 1) != (v181 != 0) )
                {
                  CNotification::CNotification((CNotification *)v598);
                  v368 = ((_DWORD)this[608] & 0x80000) == 0;
                  *((_DWORD *)this + 1215) ^= ((unsigned __int8)*((_DWORD *)this + 1215)
                                             ^ (unsigned __int8)(16 * v181))
                                            & 0x10;
                  if ( !v368 )
                  {
                    v182 = *((_DWORD *)this + 45);
                    v183 = CDoc::PrimaryRoot((CDoc *)this);
                    CNotification::EnableInteraction1((CNotification *)v598, v183, 0);
                    CDoc::BroadcastNotify((CDoc *)this, v598);
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
                    CImgAnim::SetAnimState(v184, this, v181 == 0);
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
              *(GUID *)&v614.vt = CGID_MSHTML;
              CDoc::Exec((CDoc *)this, (const struct _GUID *)&v614, 0x90Eu, 0, a6, 0);
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
              v174 = CDocument::Markup(v585);
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
                v204 = CDocument::Markup(v585);
                Text = CMarkup::EnsureGlyphTableExistsAndExecute(v204, v591, v20, a5, v7, a7);
                if ( !Text )
                {
                  if ( v20 != 2336 )
                  {
                    if ( ((((v205 = CDocument::Markup(v585), v206 = CMarkup::GetGlyphTable(v205), v20 == 2327)
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
                        goto LABEL_1666;
                    }
                    if ( v20 == 2325 )
                    {
LABEL_1666:
                      *(_DWORD *)v206 &= ~0x10u;
                      *(_DWORD *)v206 |= 16 * v202;
                      if ( v20 == 2327 )
                        goto LABEL_1665;
                    }
                    if ( v20 == 2320 )
                    {
LABEL_1665:
                      *(_DWORD *)v206 &= ~0x40u;
                      *(_DWORD *)v206 |= v202 << 6;
                      if ( v20 == 2327 )
                        goto LABEL_1664;
                    }
                    if ( v20 == 2326 )
                    {
LABEL_1664:
                      *(_DWORD *)v206 ^= (*(_DWORD *)v206 ^ (32 * v202)) & 0x20;
                      if ( v20 == 2327 )
                        goto LABEL_499;
                    }
                    if ( v20 == 2340 )
LABEL_499:
                      *(_DWORD *)v206 ^= (*(_DWORD *)v206 ^ (v202 << 7)) & 0x80;
                  }
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_1589;
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
              v187 = CDocument::Markup(v585);
              inserted = CMarkup::EnsureGlyphTableExistsAndExecute(v187, v591, plLbound[0], a5, a6, a7);
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
              v185 = CDocument::Markup(v585);
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
          v188 = CDocument::Markup(v585);
          v189 = v188;
          if ( a6 && a6->vt == 11 )
            v190 = a6->bVal != 0;
          else
            v190 = !CMarkup::IsShowZeroBorderAtDesignTime(v188);
          if ( plLbound[0] == 2328 )
          {
            CMarkup::SetShowZeroBorderAtDesignTime(v189, v190);
            CNotification::CNotification((CNotification *)v598);
            ElementTopHelper = CMarkup::GetElementTopHelper(v189);
            CNotification::ZeroGrayChange((CNotification *)v598, ElementTopHelper);
            CDoc::BroadcastNotify((CDoc *)this, v598);
            CDoc::Invalidate((CDoc *)this);
          }
          else
          {
            *((_DWORD *)this + 1216) &= ~0x10u;
            *((_DWORD *)this + 1216) |= 16 * v190;
          }
          Text = 0;
          *((_DWORD *)this[126] + 23) = *CDoc::_dwMiscFlags((CDoc *)this);
          TopLayoutElement = (CTreeNode **)CMarkup::GetTopLayoutElement(v189);
          if ( TopLayoutElement )
            CElement::ResizeElement(TopLayoutElement, 0x800000);
          COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v615);
          *(_QWORD *)v615 = v591;
          *(_DWORD *)&v615[8] = v589;
          CNotification::CNotification((CNotification *)v598);
          if ( v20 == 2328 )
            v193 = CMarkup::Root(v189);
          else
            v193 = CDoc::PrimaryRoot((CDoc *)this);
          CNotification::Command((CNotification *)v598, v193, v615, 0);
          CDoc::BroadcastNotify((CDoc *)this, v598);
          goto LABEL_1654;
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
                         v585,
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
                      v297 = (struct IUnknown *)bstrString;
                      a7->vt = 8;
                      Text = CDiagnosticsDom::GetDiagnosticsUniqueId(v297, &a7->bstrVal);
                    }
                    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
                  }
                  else if ( a7 )
                  {
                    a7->vt = 3;
                    a7->lVal = 1;
                  }
                }
                CDispClient::AdjustContentSize((CDispClient *)&ppvData, v295, v296);
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
                        v216 = CDocument::Markup(v585);
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
                      v215 = CBase::OpenParentUnit((CBase *)this, (struct CBase *)this, 2262, 0);
                      Text = GetExecDocument((struct CDocument **)&String1, this[544], v585);
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
                            v214 = CDocument::Markup(v585);
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
                        v208 = CDocument::Markup(v585);
                      if ( !v208
                        || (v209 = CMarkup::GetFrameOrPrimaryMarkup(v208), (v210 = v209) == 0)
                        || (unsigned int)CMarkup::IsImageFile(v209) )
                      {
                        Text = 0;
                        goto LABEL_1589;
                      }
                      if ( plLbound[0] != 2139
                        || !(unsigned int)CMarkup::IsPrimaryMarkup(v210)
                        || !(unsigned int)CDoc::IsAggregatedByXMLMime((CDoc *)this) )
                      {
                        Text = CDoc::GetViewSourceFileName((CDoc *)this, psz, 2083, v210);
                        if ( Text < 0 )
                          goto LABEL_1588;
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
                        goto LABEL_1589;
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
                        v591,
                        v589,
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
                    v222 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(
                                                  (MemoryProtection *)g_hProcessHeap,
                                                  0x50u);
                    if ( v222 )
                    {
                      v223 = *((_QWORD *)v585 + 7);
                      v224 = v223 ? *(_QWORD *)(v223 + 104) : *((_QWORD *)v585 + 6);
                      v219 = CIPrintCollection::CIPrintCollection(v222, *(struct CSecurityContext **)(v224 + 320));
                      if ( v219 )
                      {
                        v225 = *((_QWORD *)v585 + 7);
                        if ( v225 )
                          v226 = *(CMarkup **)(v225 + 104);
                        else
                          v226 = (CMarkup *)*((_QWORD *)v585 + 6);
                        if ( v226 )
                        {
                          v227 = CMarkup::EnsureTopElems(v226);
                          if ( v227 )
                          {
                            v228 = v227[4];
                            if ( v228 )
                            {
                              if ( *((_WORD *)v228 + 28) == 47 )
                              {
                                v598[1] = *((CElement **)v228 + 6);
                                v602 = 0;
                                v603 = 0;
                                v599 = 0;
                                LODWORD(v598[0]) = 88;
                                v601 = v219;
                                v600 = 18436;
                                v598[3] = 0;
                                CNotification::SetElement((CNotification *)v598, v228);
                                CMarkup::Notify(v226, (struct CNotification *)v598, 0);
                              }
                            }
                          }
                        }
                        goto LABEL_600;
                      }
                    }
LABEL_902:
                    Text = -2147024882;
                    goto LABEL_1657;
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
                  goto LABEL_1656;
                }
                if ( !CDoc::GetActiveElement((CDoc *)this) )
                  goto LABEL_600;
                v229 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>((MemoryProtection *)g_hProcessHeap, 0x50u);
                if ( !v229 )
                  goto LABEL_902;
                v230 = CDoc::GetActiveElement((CDoc *)this);
                v231 = CElement::GetMarkupPtr(v230);
                v219 = CIPrintCollection::CIPrintCollection(v229, *((struct CSecurityContext **)v231 + 40));
                if ( !v219 )
                  goto LABEL_902;
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
                  if ( !(unsigned int)CImplAry::AppendIndirect<8>((__int64)v219 + 56, (__int64 *)&String1, 0) )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&String1.vt + 8LL))(*(_QWORD *)&String1.vt);
                }
                v236 = bstrString;
              }
              else
              {
                v237 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>((MemoryProtection *)g_hProcessHeap, 0x50u);
                if ( !v237 )
                  goto LABEL_902;
                v238 = *((_QWORD *)v585 + 7);
                v239 = v238 ? *(_QWORD *)(v238 + 104) : *((_QWORD *)v585 + 6);
                v219 = CIPrintCollection::CIPrintCollection(v237, *(struct CSecurityContext **)(v239 + 320));
                if ( !v219 )
                  goto LABEL_902;
                v240 = CDocument::Window(v585);
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
                  if ( !(unsigned int)CImplAry::AppendIndirect<8>((__int64)v219 + 56, (__int64 *)&String1, 0) )
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
              v256 = *((_QWORD *)v585 + 7);
              if ( v256 )
                v257 = *(CMarkup **)(v256 + 104);
              else
                v257 = (CMarkup *)*((_QWORD *)v585 + 6);
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
                CMarkup::ForceRelayout(v257);
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
                  v368 = (*((_DWORD *)this + 1237))-- == 1;
                  if ( v368 && (*((_DWORD *)this + 1217) & 0x4000) != 0 )
                  {
                    v254 = v585;
                    if ( v585 )
                    {
                      if ( CDocument::Window(v585) )
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
                  v246 = CDocument::Markup(v585);
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
              goto LABEL_1657;
            }
            v249 = CDocument::Markup(v585);
            if ( !CMarkup::IsConnectedToPrimaryMarkup(v249) )
            {
              CMarkup::TearDownMarkup(v249, 1, 0);
              goto LABEL_53;
            }
LABEL_630:
            Text = -2147418113;
            goto LABEL_1657;
          }
          if ( !a7 )
            goto LABEL_131;
          VariantInit(a7);
          a7->vt = 19;
          NormZoomPercent = *((_DWORD *)this + 1245);
          goto LABEL_940;
        }
        if ( plLbound[0] <= 0x988u )
        {
          switch ( plLbound[0] )
          {
            case 2440:
              Text = 0;
              v272 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&String1.vt = v272;
              if ( !v272 || !a6 || a6->vt != 8 )
                goto LABEL_1654;
              if ( CMarkup::GetStyleState(v272) )
              {
                StyleState = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                CStr::~CStr((struct CMarkupStyleState *)((char *)StyleState + 8), v274, v275);
                v276 = *(CMarkup **)&String1.vt;
                v277 = CMarkup::GetStyleState(*(CMarkup **)&String1.vt);
                if ( !CStr::IsNull(v277) )
                {
                  v278 = CMarkup::GetStyleState(v276);
                  if ( CStr::IsNull(v278) )
                    goto LABEL_1654;
                  v279 = CMarkup::GetStyleState(v276);
                  v280 = CDispSurface::UseRenderTarget(v279);
                  v281 = a6;
                  v282 = v280 - (struct IDispRenderTarget *)a6;
                  do
                  {
                    v283 = *(unsigned __int16 *)((char *)&v281->vt + v282);
                    v284 = v281->vt - v283;
                    if ( v284 )
                      break;
                    v281 = (struct tagVARIANT *)((char *)v281 + 2);
                  }
                  while ( v283 );
                  if ( !v284 )
                    goto LABEL_1654;
                }
                v285 = CMarkup::GetStyleState(v276);
                inserted = CStr::SetBSTR((struct CMarkupStyleState *)((char *)v285 + 8), a6->bstrVal);
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
                goto LABEL_1657;
              this[625] = (CInPlace *)a6->llVal;
              goto LABEL_53;
            case 2436:
              Text = 0;
              if ( a6 )
              {
                if ( a6->vt != 11 )
                  goto LABEL_131;
                v271 = a6->bVal;
                if ( (v271 == 0) == (((*((_DWORD *)this + 1215) >> 17) & 1) == 0) )
                  goto LABEL_1654;
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | (v271 != 0 ? 0x20000 : 0);
              }
              else
              {
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | ~*((_DWORD *)this + 1215) & 0x20000;
              }
              CDoc::NotifySelection((__int64)this, (const struct _GUID *)0x11, 0, 0, 0);
              goto LABEL_1654;
            case 2437:
              Text = 0;
              v267 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v614.vt = v267;
              v268 = v267;
              if ( !v267 || !a6 || a6->vt != 11 )
                goto LABEL_1654;
              if ( CMarkup::GetStyleState(v267) )
              {
                CMarkup::CLock::CLock((CMarkup::CLock *)&String1, v268);
                v269 = *(_QWORD *)&v614.vt;
                v270 = a6->bVal != 0;
                *((_BYTE *)CMarkup::GetStyleState(*(CMarkup **)&v614.vt) + 24) = v270;
                if ( *(void (**)())(*(_QWORD *)v269 + 984LL) != _vtguard )
                  _report_securityfailure(1u);
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
                goto LABEL_1654;
              a7->iVal = 0;
              if ( CMarkup::GetStyleState(v265) )
              {
                if ( *((_BYTE *)CMarkup::GetStyleState(v266) + 24) )
                  a7->iVal = -1;
                goto LABEL_1655;
              }
              goto LABEL_902;
            case 2439:
              Text = 0;
              v261 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v614.vt = v261;
              if ( !v261 )
                goto LABEL_1654;
              a7->llVal = 0;
              if ( !CMarkup::GetStyleState(v261) )
              {
                Text = -2147024882;
                goto LABEL_1588;
              }
              if ( a7->vt != 8 )
                goto LABEL_1654;
              v262 = *(CMarkup **)&v614.vt;
              v263 = CMarkup::GetStyleState(*(CMarkup **)&v614.vt);
              if ( CStr::IsNull(v263) )
                goto LABEL_1655;
              v264 = (const OLECHAR **)CMarkup::GetStyleState(v262);
              Text = CStr::AllocBSTR(v264, &a7->bstrVal);
              if ( Text < 0 )
              {
                a7->llVal = 0;
                goto LABEL_1588;
              }
              goto LABEL_1610;
            default:
              goto LABEL_231;
          }
LABEL_1411:
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
                goto LABEL_1657;
              }
              a7->vt = 3;
              Text = 0;
              a7->lVal = *((_DWORD *)this[126] + 33);
              goto LABEL_1655;
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
              goto LABEL_1657;
            CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
            v287 = a6->parray;
            *(_QWORD *)&v614.vt = v287;
            if ( v287 && SafeArrayGetDim(v287) == 1 )
            {
              plLbound[0] = 0;
              pvData = 0;
              pvt[0] = 0;
              Text = SafeArrayGetLBound(v287, 1u, plLbound);
              if ( !Text )
              {
                Text = SafeArrayGetUBound(v287, 1u, (LONG *)&pvData);
                if ( !Text )
                {
                  Text = SafeArrayGetVartype(v287, pvt);
                  if ( !Text )
                    Text = SafeArrayGetVartype(v287, pvt);
                }
              }
              if ( plLbound[0] || (v288 = pvData, pvData > 3) || pvt[0] != 8 )
              {
                Text = -2147024809;
              }
              else
              {
                v289 = *(SAFEARRAY **)&v614.vt;
                v290 = 0;
                v291 = 0;
                memset(v615, 0, sizeof(v615));
                rgIndices[0] = 0;
                do
                {
                  if ( !Text )
                  {
                    Element = SafeArrayGetElement(v289, rgIndices, &v615[8 * v291]);
                    v288 = pvData;
                    Text = Element;
                    v290 = rgIndices[0];
                  }
                  rgIndices[0] = ++v290;
                  v291 = v290;
                }
                while ( v290 <= v288 );
                if ( !Text )
                {
                  v293 = TSmartPointer<ID3D11Device>::operator&((__int64 *)&bstrString);
                  Text = CDoc::InitializeDiagnosticsMode(
                           (CDoc *)this,
                           *(WCHAR **)v615,
                           *(WCHAR **)&v615[8],
                           *(WCHAR **)&v615[16],
                           *(const unsigned __int16 **)&v615[24],
                           (struct IObjectWithSite **)v293);
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
            TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&bstrString);
            goto LABEL_231;
          case 3803:
            Text = -2147024809;
            if ( !a7 )
              goto LABEL_1657;
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
            goto LABEL_1655;
          case 3804:
            if ( !a6 )
              goto LABEL_756;
            if ( a6->vt == 13 )
            {
              v286 = a6->punkVal;
              if ( v286 )
              {
                if ( a7 )
                {
                  plLbound[0] = 0;
                  Text = CDebugCallbackNotificationHandlers::AddCallbackNotificationHandler(
                           (CDebugCallbackNotificationHandlers *)(this + 812),
                           v286,
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
                v314 = this[103];
                if ( v314 )
                {
                  v315 = (CMarkup **)COmWindowProxy::Markup(v314);
                  Text = CMarkup::GetFrameZone(v315, a7, 0);
                }
                if ( Text || !this[103] )
                {
                  a7->vt = 0;
                  goto LABEL_231;
                }
                goto LABEL_1655;
              }
              goto LABEL_330;
            case 6021:
              if ( !a6 )
                goto LABEL_231;
              pvData = 0;
              v309 = CDoc::PrimaryMarkup((CDoc *)this);
              v310 = CMarkup::GetCodePage(v309);
              v311 = this[544];
              v312 = v310;
              plLbound[0] = 0;
              *(_QWORD *)&String1.vt = 0;
              Text = GetExecDocument((struct CDocument **)&String1, v311, v585);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
              v98 = Text < 0;
              if ( !Text )
              {
                v313 = CDoc::IsCpAutoDetect((CDoc *)this);
                Text = ShowMimeCSetMenu(this[126], (int *)&pvData, v312, a6->lVal, plLbound[0], v313);
                if ( !Text )
                {
                  v20 = pvData;
                  if ( pvData - 3609 > 0x5A )
                  {
                    if ( pvData - 2350 <= 1 )
                      CDoc::ExecHelper(this, v585, (struct _GUID *)&CGID_MSHTML, pvData, 0, 0, 0);
                    goto LABEL_1654;
                  }
                  goto LABEL_1589;
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
                  v307 = a6->bstrVal;
                  if ( v307 )
                  {
                    v308 = CDocument::Markup(v585);
                    inserted = CDoc::SetUrl((CDoc *)this, v308, v307);
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
                goto LABEL_1657;
              }
              v306 = CDoc::PrimaryMarkup((CDoc *)this);
              NormZoomPercent = CMarkup::GetCodePage(v306);
              if ( plLbound[0] == 6034 )
                NormZoomPercent = WindowsCodePageFromCodePage(NormZoomPercent);
              a7->vt = 3;
              break;
            case 6036:
              if ( !a7 )
                goto LABEL_756;
              v298 = v585;
              a7->vt = 37;
              v299 = this[544];
              plLbound[0] = 0;
              bstrString = 0;
              Text = GetExecDocument((struct CDocument **)&bstrString, v299, v298);
              if ( Text >= 0 )
                Text = CDocument::GetDocDirection((CDocument *)bstrString, plLbound);
              v98 = Text < 0;
              if ( !Text )
              {
                v300 = CDocument::Markup((CDocument *)bstrString);
                v301 = CDoc::IsCpAutoDetect((CDoc *)this);
                v302 = plLbound[0];
                v303 = v301;
                v304 = CMarkup::GetCodePage(v300);
                EncodingMenu = GetEncodingMenu(this[126], v304, v302, v303);
                a7->llVal = (LONGLONG)EncodingMenu;
                if ( !EncodingMenu )
                {
                  v25 = 1;
                  Text = 1;
                  goto LABEL_231;
                }
                goto LABEL_941;
              }
LABEL_232:
              if ( v98 )
              {
LABEL_1588:
                if ( Text != -2147221248 )
                  goto LABEL_1657;
              }
LABEL_1589:
              v516 = a5;
              goto LABEL_1590;
            default:
              goto LABEL_231;
          }
LABEL_940:
          a7->lVal = NormZoomPercent;
          goto LABEL_941;
        }
        if ( plLbound[0] == 6038 )
          goto LABEL_53;
        v316 = 3;
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
                CNotification::CNotification((CNotification *)v598);
                v317 = CDoc::PrimaryMarkup((CDoc *)this);
                v318 = CMarkup::GetElementTopHelper(v317);
                CNotification::EditModeChange((CNotification *)v598, v318, 0);
                CDoc::BroadcastNotify((CDoc *)this, v598);
              }
            }
            if ( a7 )
            {
              a7->vt = 8;
              DefaultBlockTag = CDoc::GetDefaultBlockTag(this, v27, v316, v26);
              v320 = L"DIV";
              if ( DefaultBlockTag != 34 )
                v320 = L"P";
              a7->llVal = (LONGLONG)SysAllocString(v320);
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
              *(_OWORD *)&v614.vt = 0;
              CNotification::CNotification((CNotification *)v598);
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
              v343 = v585;
              v344 = (struct INamedPropertyBag *)bstrString;
              v345 = CDocument::Markup(v585);
              Text = CDoc::PersistFavoritesData((CDoc *)this, v345, v344, L"DEFAULT");
              if ( Text )
              {
                ReleaseInterface((struct IUnknown *)bstrString);
                goto LABEL_230;
              }
              *(_QWORD *)&v614.vt = bstrString;
              v614.llVal = (LONGLONG)SysAllocString(L"DOC");
              if ( v614.llVal )
              {
                v346 = CDocument::Markup(v343);
                v347 = CMarkup::Root(v346);
                CNotification::FavoritesSave((CNotification *)v598, v347, &v614, 0);
                CDoc::BroadcastNotify((CDoc *)this, v598);
                ClearInterface<INamedPropertyBag *>((__int64 *)&v614);
                SysFreeString(v614.bstrVal);
                goto LABEL_1654;
              }
              ReleaseInterface((struct IUnknown *)bstrString);
              goto LABEL_902;
            case 6051:
              Text = 0;
              if ( a7 )
              {
                v337 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v338 = (__int16 *)this + 2861;
                if ( !v337 )
                  v338 = (__int16 *)(this + 715);
                v339 = *v338;
                a7->vt = 3;
                FontSizeMenu = GetFontSizeMenu(v339);
                v341 = HandleToLong(FontSizeMenu);
                a7->lVal = v341;
                LOBYTE(Text) = v341 == 0;
                goto LABEL_231;
              }
              goto LABEL_756;
            case 6052:
              if ( a6 )
              {
                plLbound[0] = 0;
                v335 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v336 = (__int16 *)this + 2861;
                if ( !v335 )
                  v336 = (__int16 *)(this + 715);
                Text = ShowFontSizeMenu(plLbound, *v336, a6->lVal);
                if ( !Text )
                {
                  if ( (unsigned int)(plLbound[0] - 2141) <= 4 )
                    CDoc::ExecHelper(this, v585, (struct _GUID *)&CGID_MSHTML, plLbound[0], 0, 0, 0);
                  goto LABEL_1654;
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
                inserted = CDoc::InsertMenuExt((CDoc *)this, (HMENU)a6->llVal, a7->cyVal.Lo);
                goto LABEL_306;
              }
              goto LABEL_756;
            }
            if ( !a7 )
              goto LABEL_756;
            v330 = this[544];
            plLbound[0] = 0;
            *(_QWORD *)&String1.vt = 0;
            if ( GetExecDocument((struct CDocument **)&String1, v330, v585) >= 0 )
              CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
            v331 = plLbound[0];
            a7->vt = 3;
            DocDirMenu = CreateDocDirMenu(v331, 0);
            v333 = HandleToLong(DocDirMenu);
            a7->lVal = v333;
            v334 = -2147221247;
LABEL_1325:
            Text = v333 == 0 ? v334 : 0;
            goto LABEL_231;
          }
          if ( !a6 )
            goto LABEL_131;
          memset(&pv, 0, sizeof(pv));
          Text = CVariant::CoerceVariantArg(&pv, a6, 0xDu);
          if ( Text >= 0 )
            Text = CDoc::SaveSnapshotHelper((CDoc *)this, pv.punkVal, 1);
LABEL_883:
          p_pvarg = &pv;
LABEL_210:
          VariantClear(p_pvarg);
          goto LABEL_231;
        }
        if ( a6 || !a7 )
          goto LABEL_756;
        v348 = this[103];
        if ( !v348 )
          goto LABEL_350;
        *(_QWORD *)&String1.vt = 0;
        v349 = COmWindowProxy::Document(v348);
        Text = CDocument::ExtractContent(v349, (struct IReadingModeExtractedContent **)&String1);
        if ( Text < 0 )
          goto LABEL_1588;
        v350 = *(BSTR *)&String1.vt;
        a7->vt = 13;
LABEL_909:
        a7->llVal = (LONGLONG)v350;
        goto LABEL_1652;
      }
      switch ( plLbound[0] )
      {
        case 6062:
          Text = 0;
          if ( a6 || !a7 )
            goto LABEL_131;
          a7->vt = 3;
          a7->lVal = 0;
          v354 = (ReadingMode::CTextClusterDetector *)operator new[](
                                                        0x40u,
                                                        (const struct MemoryProtection::leaf_t *)0x8FC);
          if ( v354 )
          {
            v355 = (ReadingMode::CTextClusterDetector *)ReadingMode::CTextClusterDetector::CTextClusterDetector(
                                                          v354,
                                                          (struct CDoc *)this);
            v356 = v355;
            if ( v355 )
            {
              a7->lVal = ReadingMode::CTextClusterDetector::LengthOfArticleBody(v355);
              ReadingMode::CTextClusterDetector::`scalar deleting destructor'(v356, 1u);
              goto LABEL_1657;
            }
          }
          goto LABEL_902;
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
            Text = CDoc::AttemptBFCacheNavigation((struct IUnknown **)this, a5, a6->cyVal.Lo);
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
          v351 = CDoc::PrimaryMarkup((CDoc *)this);
          CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v351);
          if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
          {
            v352 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
            Text = CPreloadManager::SuspendDuringPrerender((__int64)v352, 4u);
          }
          CPreloadManagerLock::~CPreloadManagerLock((CPreloadManager **)&bstrString);
        }
        goto LABEL_231;
      }
      if ( !a7 || !a6 || a6->vt != 19 )
        goto LABEL_131;
      a7->vt = 19;
      v353 = CDoc::CheckBFCacheCandidacy((__int64)this, a6->cyVal.Lo);
LABEL_929:
      a7->lVal = v353;
      Text = 0;
      goto LABEL_1656;
    }
    if ( plLbound[0] <= 0x1B53u )
    {
      if ( plLbound[0] != 6995 )
      {
        switch ( plLbound[0] )
        {
          case 0x17BB:
            v372 = CDoc::InputManager((CDoc *)this);
            v373 = CInputManager::DeferredActionHandler(v372);
            CDeferredActionHandler::AgreeToVTabNavigate(v373, 0);
            goto LABEL_53;
          case 0x17BC:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v374 = CDoc::InputManager((CDoc *)this);
            v375 = CInputManager::DeferredActionHandler(v374);
            CDeferredActionHandler::OnVTabNavigateComplete(v375, a6->lVal);
            goto LABEL_53;
          case 0x17BD:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v376 = CDoc::InputManager((CDoc *)this);
            v377 = CInputManager::DeferredActionHandler(v376);
            CDeferredActionHandler::CancelSpecificVTabNavigate(v377, a6->lVal);
            goto LABEL_53;
          case 0x17BE:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v378 = CDoc::InputManager((CDoc *)this);
            v379 = CInputManager::DeferredActionHandler(v378);
            inserted = CDeferredActionHandler::ValidateVTabNavigate(v379, a6->lVal);
            goto LABEL_306;
          case 0x17BF:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v380 = CDoc::InputManager((CDoc *)this);
            v381 = CInputManager::DeferredActionHandler(v380);
            CDeferredActionHandler::OnBeforeUnloadAgreed(v381, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17C0:
            if ( !a6 || a6->vt != 11 )
              goto LABEL_231;
            v382 = a6->iVal;
            Text = 0;
            if ( !v382 && ((_DWORD)this[609] & 0x200000) != 0 )
              goto LABEL_350;
            *((_DWORD *)this + 1219) &= ~0x100000u;
            v383 = 0;
            if ( v382 == -1 )
              v383 = 0x100000;
            *((_DWORD *)this + 1219) |= v383;
            goto LABEL_230;
          case 0x17C1:
            Text = -2147467259;
            v369 = CDoc::PrimaryMarkup((CDoc *)this);
            v370 = v369;
            if ( !v369 || !(unsigned int)BindCtx_ContainsObject(*((_QWORD *)v369 + 183), L"IE_FLAG_HAS_SCROLL_POSITION") )
              goto LABEL_1657;
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v370 + 183) + 96LL))(
              *((_QWORD *)v370 + 183),
              L"IE_FLAG_HAS_SCROLL_POSITION");
            goto LABEL_53;
          case 0x17C2:
            CDoc::ReleaseOffscreenBuffers((CDoc *)this);
            goto LABEL_53;
          case 0x17C3:
            v371 = this[876];
            if ( v371 )
            {
              (*(void (__fastcall **)(CInPlace *, __int64, void *, __int64))(*(_QWORD *)v371 + 16LL))(
                v371,
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
            v367 = ((_BYTE)this[441] & 4) != 0;
            goto LABEL_968;
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
            v388 = plLbound[0];
            goto LABEL_1540;
          case 0x17C7:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v389 = a6->lVal;
            plLbound[0] = 0;
            Text = ValidateD3DRequestedFeatureLevel(v389, (enum D3D_REQUESTED_FEATURE_LEVEL *)plLbound);
            if ( Text )
              goto LABEL_231;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                  + 16LL)
                      + 1132LL) = plLbound[0];
            goto LABEL_1654;
          case 0x17C8:
            if ( !a6 )
              goto LABEL_131;
            v368 = a6->vt == 19;
            goto LABEL_971;
          case 0x17C9:
            if ( !a7 )
              goto LABEL_131;
            IsEnterpriseMode = 0;
            if ( CDoc::PrimaryMarkup((CDoc *)this) )
            {
              v365 = CDoc::PrimaryMarkup((CDoc *)this);
              v366 = CMarkup::MarkupVersion(v365);
              IsEnterpriseMode = CMarkupVersion::IsEnterpriseMode(v366);
            }
            a7->vt = 11;
            v367 = !IsEnterpriseMode - 1;
LABEL_968:
            a7->iVal = v367;
            goto LABEL_941;
          case 0x17CA:
            v384 = *(CVirtualTabStorageEntry **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + (unsigned int)tls_index)
                                                           + 16LL)
                                               + 728LL);
            if ( v384 && CVirtualTabStorageEntry::WasLastNavigationViaFlipAhead(v384) )
            {
              v385 = CDoc::PrimaryMarkup((CDoc *)this);
              CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v385);
              if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
              {
                v386 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                CPreloadManager::SetLastNavAsFlipAheadAndIssueRequestIfApplicable(v386);
              }
              CPreloadManagerLock::~CPreloadManagerLock((CPreloadManager **)&bstrString);
            }
            goto LABEL_53;
          case 0x17CB:
            if ( !a6 || a6->vt != 8 )
              goto LABEL_756;
            v359 = CDoc::PrimaryMarkup((CDoc *)this);
            if ( v359 && (*((_BYTE *)v359 + 248) = 1, (v360 = this[103]) != 0) )
            {
              CodePageCore = *((_DWORD *)v359 + 194);
              v362 = *((_DWORD *)v359 + 196);
              if ( !CodePageCore )
                CodePageCore = CMarkup::GetCodePageCore(v359);
              Text = COmWindowProxy::ExecRefresh((__int64)v360, 3, CodePageCore, v362);
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
              v363 = bstrString;
              bstrString = 0;
              if ( v363 )
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)v363 + 16LL))(v363);
            }
            SysFreeString(a6->bstrVal);
            v55 = ppvData;
            ppvData = 0;
            a6->llVal = 0;
            goto LABEL_959;
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
                v420 = View;
                if ( !a7 || !View || !*((_BYTE *)View + 40) )
                  goto LABEL_1657;
                a7->vt = 3;
                v421 = *(unsigned __int16 *)CViewportController::GetLogicalViewportSize(*((_QWORD *)View + 4), &String1);
                a7->lVal = v421
                         | (*(unsigned __int16 *)(CViewportController::GetLogicalViewportSize(
                                                    *((_QWORD *)v420 + 4),
                                                    &v614)
                                                + 4) << 16);
                CDispClient::AdjustContentSize((CDispClient *)&v614, v422, v423);
                CDispClient::AdjustContentSize((CDispClient *)&String1, v424, v425);
                goto LABEL_941;
              case 0x1B77:
                Text = -2147467259;
                v427 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v427 || !*((_BYTE *)v427 + 40) )
                  goto LABEL_1657;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsMobileOptimizedSite(*((CViewportController **)v427 + 4));
                goto LABEL_1161;
              case 0x1B78:
                Text = -2147467259;
                v429 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v429 || !*((_BYTE *)v429 + 40) )
                  goto LABEL_1657;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsViewportWidthOrientationDependent(*((CViewportController **)v429
                                                                                                 + 4));
                goto LABEL_1161;
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
                  goto LABEL_1657;
                v418 = CVersions::MapToDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
                goto LABEL_1125;
              case 0x1B7D:
                inserted = CDoc::SetAuthoringCallback((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7E:
                if ( !a6 || a6->vt != 9 )
                  goto LABEL_330;
                bstrString = 0;
                v435 = a6->punkVal;
                *(GUID *)&v614.vt = CLSID_CElement;
                Text = QIClassID(v435, (struct _GUID *)&v614, (void **)&bstrString);
                if ( Text < 0 )
                  goto LABEL_1588;
                inserted = CElement::EnterFullScreen((CElement *)bstrString);
                goto LABEL_306;
              case 0x1B7F:
                if ( !a6 || ((a6->vt - 1) & 0xFFF7) != 0 )
                {
                  Text = -2147467261;
                  bstrString = 0;
                  goto LABEL_1657;
                }
                v436 = 0;
                bstrString = 0;
                if ( a6->vt == 9 )
                {
                  v437 = a6->punkVal;
                  *(GUID *)&v614.vt = CLSID_CElement;
                  Text = QIClassID(v437, (struct _GUID *)&v614, (void **)&bstrString);
                  if ( Text < 0 )
                    goto LABEL_1588;
                  v436 = (CElement *)bstrString;
                }
                if ( v436 )
                {
                  inserted = CElement::ExitFullScreen(v436);
                }
                else
                {
                  v438 = CDoc::FullScreenState((CDoc *)this);
                  inserted = CFullScreenState::ExitFullScreen(v438, 0);
                }
                break;
              case 0x1B80:
                inserted = CDoc::PrepareForSetVisible((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B81:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1657;
                if ( a6->vt != 8204 )
                  goto LABEL_1657;
                if ( SafeArrayGetDim(a6->parray) != 1 )
                  goto LABEL_1657;
                v430 = a6->parray;
                plLbound[0] = 0;
                SafeArrayGetUBound(v430, 1u, plLbound);
                if ( plLbound[0] != 2 )
                  goto LABEL_1657;
                v431 = a6->parray;
                *(_QWORD *)&String1.vt = 0;
                Text = SafeArrayAccessData(v431, (void **)&String1);
                if ( Text < 0 )
                  goto LABEL_1588;
                Text = CDoc::SetMediaConsent(
                         (CDoc *)this,
                         *(const unsigned __int16 **)(*(_QWORD *)&String1.vt + 8LL),
                         *(_DWORD *)(*(_QWORD *)&String1.vt + 32LL),
                         *(_DWORD *)(*(_QWORD *)&String1.vt + 56LL));
                goto LABEL_1149;
              case 0x1B82:
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_131;
                Text = -2147467259;
                v426 = CDoc::GetView((CDoc *)this);
                if ( !v426 || !*((_BYTE *)v426 + 40) )
                  goto LABEL_1657;
                CViewportController::SetUIOrientation(*((CViewportController **)v426 + 4), a6->iVal == 0xFFFF);
                goto LABEL_53;
              case 0x1B83:
                Text = -2147024809;
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_1657;
                v97 = CDoc::ForcePaint((LARGE_INTEGER *)this, a6->iVal == 0xFFFF, 0);
                goto LABEL_229;
              case 0x1B84:
                inserted = CDoc::WaitForDCompFlush((CDoc *)this);
                goto LABEL_306;
              case 0x1B86:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1657;
                if ( a6->vt != 11 )
                  goto LABEL_1657;
                Text = -2147467259;
                v432 = CDoc::GetView((CDoc *)this);
                if ( !v432 )
                  goto LABEL_1657;
                CView::AllowGrippersForHost(v432, a6->iVal == 0);
                goto LABEL_53;
              case 0x1B87:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1657;
                if ( a6->vt != 8 )
                  goto LABEL_1657;
                Text = -2147418113;
                if ( !v585 )
                  goto LABEL_1657;
                inserted = CDoc::HandleFlashServicingRefresh((CDoc *)this, v585, a6->bstrVal);
                goto LABEL_306;
              case 0x1B88:
                Text = -2147024809;
                if ( !a7 )
                  goto LABEL_1657;
                a7->vt = 11;
                v433 = CDoc::FullScreenState((CDoc *)this);
                IsMobileOptimizedSite = CFullScreenState::IsInFullScreen(v433);
LABEL_1161:
                v434 = !IsMobileOptimizedSite;
                goto LABEL_1498;
              default:
                goto LABEL_231;
            }
            goto LABEL_306;
          }
          if ( a6 )
          {
            v368 = a6->vt == 11;
LABEL_971:
            if ( v368 )
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
                v396 = 0;
                if ( a6 && a6->vt == 3 )
                  v396 = a6->lVal;
                CDoc::SubmitForAntiPhishProcessing(this, 0, v396, 0);
                goto LABEL_53;
              case 7005:
                inserted = CDoc::NotifyMarkupsModelessEnable((CDoc *)this, 32, v19);
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
          v397 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( !v397 )
            goto LABEL_350;
          *((_BYTE *)v397 + 97) |= 8u;
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
              OnSettingsChangeAllDocs(1, 6997);
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
                Text = CDoc::ExecHelper(this, v585, (struct _GUID *)&CGID_MSHTML, Lo + 2141, 2u, 0, 0);
                if ( Text )
                  goto LABEL_231;
              }
              if ( !a7 )
                goto LABEL_53;
              v368 = !FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
              v391 = (CInPlace **)((char *)this + 5722);
              if ( v368 )
                v391 = this + 715;
              DebugState = *(__int16 *)v391;
              a7->vt = 3;
LABEL_1032:
              a7->lVal = DebugState;
              goto LABEL_53;
          }
          v394 = CDocument::Markup(v585);
          CDoc::WaitForRecalc((CDoc *)this, v394);
          goto LABEL_53;
        }
        if ( !a7 )
          goto LABEL_330;
        a7->vt = 3;
        a7->lVal = 0x40000;
LABEL_941:
        Text = 0;
        goto LABEL_1655;
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
            CDoc::CompatViewRefresh((void **)this, 0);
            goto LABEL_53;
          case 7021:
            if ( a6 && a6->vt == 11 )
            {
              v398 = 0;
              if ( a6->iVal == -1 )
                v398 = 512;
              *((_DWORD *)this + 1214) = (_DWORD)this[607] & 0xFFFFFDFF | v398;
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
        Text = CDoc::SaveToTempFileForPrint((CDoc *)this, v585, Data, 0x104u, 0, 0, 0);
        if ( Text < 0 )
          goto LABEL_1588;
        if ( !a7 )
          goto LABEL_756;
        VariantInit(a7);
        a7->vt = 8;
        v350 = SysAllocString(Data);
        goto LABEL_909;
      }
      if ( !a6 || a6->vt != 19 || !a7 )
        goto LABEL_756;
      rgIndices[0] = a6->lVal;
      Vector = SafeArrayCreateVector(0xCu, 0, 6u);
      pszSubKey = &Vector->cDims;
      a7->llVal = (LONGLONG)Vector;
      a7->vt = 8204;
      if ( !Vector )
        goto LABEL_902;
      ppvData = 0;
      Text = SafeArrayAccessData(Vector, &ppvData);
      if ( Text < 0 )
        goto LABEL_1588;
      for ( i = 0; i != 6; ++i )
        VariantInit((VARIANTARG *)ppvData + i);
      v401 = rgIndices[0];
      v20 = plLbound[0];
      if ( (rgIndices[0] & 1) != 0 )
      {
        Text = 0;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v402 = ppvData;
          *(_WORD *)ppvData = 21;
          v402[1] = *((_QWORD *)CDoc::PrimaryMarkup((CDoc *)this) + 17);
        }
        v401 = rgIndices[0];
      }
      if ( (v401 & 2) != 0 )
      {
        v403 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( v403 )
        {
          v404 = COptionsHolder::SecurityContext(v403);
          *(_QWORD *)&v614.vt = v404;
          if ( v404 )
          {
            *(_QWORD *)&String1.vt = CHtmCtx::GetReferrerUrl(v404);
            OriginalUrlContext = CHtmCtx::GetOriginalUrlContext(*(CHtmCtx **)&v614.vt);
            v406 = *(const OLECHAR **)&String1.vt;
            v407 = -1;
            *(_QWORD *)&v614.vt = OriginalUrlContext;
            if ( *(_QWORD *)&String1.vt )
            {
              v408 = -1;
              do
                ++v408;
              while ( *(_WORD *)(*(_QWORD *)&String1.vt + 2 * v408) );
            }
            else
            {
              v408 = 0;
            }
            if ( OriginalUrlContext )
            {
              do
                ++v407;
              while ( OriginalUrlContext[v407] );
            }
            else
            {
              v407 = 0;
            }
            if ( v408 )
            {
              if ( v407 > v408 )
              {
                v409 = wcsncmp_0(*(const wchar_t **)&String1.vt, OriginalUrlContext, v408);
                v406 = *(const OLECHAR **)&String1.vt;
                if ( !v409 )
                  v406 = *(const OLECHAR **)&v614.vt;
              }
            }
            v410 = SysAllocString(v406);
            v25 = 1;
            if ( v410 )
            {
              v411 = ppvData;
              Text = 0;
              *((_WORD *)ppvData + 12) = 8;
              v411[4] = v410;
            }
          }
        }
      }
      v412 = rgIndices[0];
      if ( (rgIndices[0] & 4) != 0 )
      {
        v413 = ppvData;
        *(_QWORD *)&v614.vt = ppvData;
        *((_WORD *)ppvData + 24) = 21;
        if ( this[781] )
        {
          v414 = CHTMLDlg::SecurityContext(this[781]);
          v412 = rgIndices[0];
          *(_QWORD *)(*(_QWORD *)&v614.vt + 56LL) = v414;
        }
        else
        {
          v413[7] = 0;
        }
      }
      if ( (v412 & 8) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractVideoData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text < 0 )
        {
LABEL_1117:
          CMultimediaLog::StopUpdate((CMultimediaLog *)(this + 741));
          v417 = (SAFEARRAY *)pszSubKey;
          goto LABEL_1150;
        }
        v412 = rgIndices[0];
        if ( bstrString )
        {
          v415 = ppvData;
          Text = 0;
          *((_WORD *)ppvData + 36) = 8;
          v415[10] = bstrString;
        }
      }
      if ( (v412 & 0x10) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractImageData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text >= 0 )
        {
          if ( bstrString )
          {
            v416 = ppvData;
            Text = 0;
            *((_WORD *)ppvData + 48) = 8;
            v416[13] = bstrString;
          }
        }
      }
      goto LABEL_1117;
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
              Text = CDoc::SerializePrintCommands((CDoc *)this, v585, a6, a7);
              v455 = Text == 0;
              goto LABEL_1653;
            }
            goto LABEL_231;
          }
          if ( plLbound[0] == 8000 )
          {
            if ( !a6 || a6->vt == 11 )
            {
              v453 = (unsigned int)tls_index;
              if ( a7 )
              {
                ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 11;
                a7->iVal = -(*(_BYTE *)(*(_QWORD *)(ThreadLocalStoragePointer[v453] + 16LL) + 1128LL) != 0);
              }
              if ( a6 )
                *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v453) + 16LL) + 1128LL) = a6->iVal == 0xFFFF;
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
                v448 = CDocument::Window(v585);
                v449 = v448;
                if ( v448 && CWindow::IsPrimaryWindow(v448) )
                {
                  v450 = CDeviceRotationRate::SecurityContext(v449);
                  if ( v450 )
                  {
                    v451 = CMarkup::Window(v450);
                    CEventMgr::QueueAsyncEvent(
                      (__int64)&s_propdescCIE9EventListorientationchange,
                      (unsigned __int64)v451,
                      (__int64)v450,
                      (__int64)COmWindowProxy::Fire_orientationchange,
                      0,
                      (__int64)AsyncEventMerge_Always,
                      0);
                  }
                  v452 = *((_QWORD *)v449 + 55);
                  if ( v452 )
                    CEventMgr::QueueAsyncEvent(
                      (__int64)&s_propdescCIE9EventListMSOrientationChange,
                      v452,
                      (__int64)v450,
                      (__int64)CScreen::Fire_orientationchange,
                      0,
                      (__int64)AsyncEventMerge_Always,
                      0);
                }
                goto LABEL_1654;
              case 8004:
                inserted = CDoc::GetContentLang((CDoc *)this, a7);
                break;
              case 8005:
                v447 = this[732];
                if ( v447 )
                {
                  CAPProcessor::Passivate(v447);
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
              goto LABEL_1657;
            v97 = CIndependentHitTestManager::RegisterHostForIndependentHitTesting(
                    (CIndependentHitTestManager *)&g_IndependentHitTestManager,
                    (struct CDoc *)this,
                    a6->punkVal);
            goto LABEL_229;
          case 7134:
            Text = -2147024809;
            if ( !a6 || a6->vt != 13 )
              goto LABEL_1657;
            v97 = CIndependentHitTestManager::UnregisterHostForIndependentHitTesting(
                    (CIndependentHitTestManager *)&g_IndependentHitTestManager,
                    (struct CDoc *)this,
                    a6->punkVal);
            goto LABEL_229;
          case 7135:
            Text = -2147024809;
            if ( !a6 || a6->vt != 0x4000 )
              goto LABEL_1657;
            RootTracker = CRootTracker::GetRootTracker();
            v441 = RootTracker;
            if ( RootTracker )
            {
              Text = CRootTracker::EnsureInitialized(RootTracker);
              if ( Text < 0 )
                goto LABEL_1588;
              CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
              v442 = CDCompLayerManager::UseRootLayer(v441);
              v443 = **(__int64 (__fastcall ***)(struct IDispLayer *, GUID *, struct CHtmParseCtx *))v442;
              v444 = TSmartPointer<ID3D11Device>::operator&((__int64 *)&bstrString);
              HpxEmbed = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)v444);
              Text = v443(v442, &GUID_cc1a2bea_d5e9_4161_9da7_9042b37549a7, HpxEmbed);
              if ( Text >= 0 )
              {
                v446 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                Text = (*(__int64 (__fastcall **)(struct IDispRenderTarget *, __int64, struct tagVARIANT *))(*(_QWORD *)v446 + 24LL))(
                         v446,
                         3,
                         a6);
              }
              TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&bstrString);
              goto LABEL_230;
            }
            goto LABEL_1411;
          case 7136:
            Text = -2147024809;
            if ( a7 )
            {
              a7->vt = 11;
              a7->iVal = -((unsigned int)CDoc::IsJSDumpRequested((CDoc *)this) != 0);
              if ( !a6 )
              {
                Text = 0;
                goto LABEL_1657;
              }
            }
            else if ( !a6 )
            {
              goto LABEL_1657;
            }
            if ( a6->vt != 21 )
              goto LABEL_1657;
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
        v368 = CView::HasStaticViewportSizeApplied((CView *)(this + 283)) == 0;
        v439 = (int *)(this + 481);
        if ( v368 )
          v439 = (int *)this + 1019;
        NormZoomPercent = *v439;
        goto LABEL_940;
      }
      if ( plLbound[0] > 0x3A98u )
      {
        if ( plLbound[0] != 15001 )
        {
          if ( plLbound[0] == 15002 )
          {
            if ( a6 && (a6->vt == 8212 || a6->vt == 8195) )
            {
              v469 = a6->parray;
              if ( v469 )
              {
                pvData = 0;
                pszSubKey = 0;
                *(_QWORD *)&String1.vt = 0;
                if ( !SafeArrayGetElement(v469, (LONG *)&pvData, &pszSubKey) )
                {
                  v470 = a6->parray;
                  ++pvData;
                  if ( !SafeArrayGetElement(v470, (LONG *)&pvData, &String1) )
                    CDoc::ReplacePrintHandles((CDoc *)this, (void *)pszSubKey, *(void **)&String1.vt);
                }
                goto LABEL_53;
              }
            }
            goto LABEL_131;
          }
          v333 = InternetSetOptionW(0, 0x2Au, 0, 0);
          v334 = -2147467259;
          goto LABEL_1325;
        }
        if ( g_fInHtmlHelp )
        {
          *((_DWORD *)this + 1217) |= 0x400u;
          v471 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( v471 )
          {
            if ( (*((_DWORD *)v471 + 187) & 0x4000000) != 0 )
            {
              v472 = (COmWindowProxy *)*((_QWORD *)v471 + 44);
              if ( v472 )
                COmWindowProxy::Fire_onafterprint(v472);
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
                goto LABEL_1655;
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
                  CDispClient::AdjustContentSize((CDispClient *)&bstrString, v467, v468);
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
              goto LABEL_1654;
            case 8007:
              if ( a6 && a6->vt == 3 )
              {
                Text = 0;
                CDoc::HandleWebStorageEvent((CDoc *)this, v585, a6->cyVal.Lo);
                goto LABEL_1654;
              }
              goto LABEL_131;
            case 8008:
              Text = 0;
              if ( a6 && a6->vt == 19 )
              {
                v463 = this[126];
                if ( v463 )
                {
                  v464 = a6->lVal;
                  if ( *((_DWORD *)v463 + 384) == v464 )
                    goto LABEL_1654;
                  *((_DWORD *)v463 + 384) = v464;
                  v465 = CDocument::Markup(v585);
                  TextScalingSettings = CTextScalingSettings::GetTextScalingSettings(v465);
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
              v461 = CDoc::GetView((CDoc *)this);
              if ( v461 )
              {
                if ( *((_BYTE *)v461 + 40) )
                {
                  v462 = (CViewportController *)*((_QWORD *)v461 + 4);
                  if ( v462 )
                  {
                    Text = 0;
                    CViewportController::SetAccessibleZoom(v462, a6->iVal != 0);
                    goto LABEL_1654;
                  }
                }
              }
              goto LABEL_350;
            case 8010:
              v458 = NtCurrentTeb()->ThreadLocalStoragePointer;
              pvData = 0;
              bstrString = (BSTR)v458[(unsigned int)tls_index];
              if ( *(_QWORD *)(*((_QWORD *)bstrString + 2) + 728LL) )
              {
                if ( !(unsigned int)CDoc::GetVirtualTabID((CDoc *)this, &pvData) )
                {
                  VirtualTabID = CVirtualTabStorageEntry::GetVirtualTabID(*(CVirtualTabStorageEntry **)(*((_QWORD *)bstrString + 2) + 728LL));
                  if ( VirtualTabID != pvData
                    && CVirtualTabStorageEntry::IsStorageListHelperSet(*(CVirtualTabStorageEntry **)(*((_QWORD *)bstrString + 2) + 728LL)) )
                  {
                    CVirtualTabStorageEntry::Release(
                      *(CVirtualTabStorageEntry **)(*((_QWORD *)bstrString + 2) + 728LL),
                      v460);
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
            v456 = CDoc::GetView((CDoc *)this);
            if ( v456 )
            {
              v457 = (CViewportController *)*((_QWORD *)v456 + 4);
              if ( v457 )
              {
                Text = 0;
                CViewportController::SetIsReadingView(v457, a6->iVal != 0);
                goto LABEL_1654;
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
            v473 = (unsigned int (__fastcall ***)(_QWORD, GUID *, void **, __int64))a6->llVal;
            if ( v473 )
            {
              ppvData = 0;
              if ( !(**v473)(v473, &IID_IHTMLWindow2, &ppvData, v26) )
              {
                v474 = this[642];
                bstrString = 0;
                if ( !(**(unsigned int (__fastcall ***)(CInPlace *, GUID *, BSTR *))v474)(
                        v474,
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
        v538 = CDocument::Markup(v585);
        v539 = 0;
        if ( a6 && a6->vt == 3 )
          v539 = a6->lVal;
        Text = 0;
        if ( !v538 )
          goto LABEL_1654;
        v540 = CMarkup::GetWindowedMarkupContext(v538);
        if ( !v540 )
          goto LABEL_1654;
        RootMarkup = CMarkup::GetRootMarkup(v540, 0);
        if ( !RootMarkup )
          goto LABEL_1654;
        *((_DWORD *)RootMarkup + 197) |= v539;
        *((_DWORD *)this + 1224) &= ~v539;
        inserted = CDoc::NotifyPageActionBlockedState((struct IUnknown **)this, 1, 0);
        goto LABEL_306;
      }
      if ( plLbound[0] <= 0x3AB3u )
      {
        if ( plLbound[0] == 15027 )
        {
          Text = -2147024809;
          if ( !a7 )
            goto LABEL_1657;
          a7->vt = 3;
          NormZoomPercent = CZoomState::GetNormZoomPercent();
          goto LABEL_940;
        }
        if ( plLbound[0] <= 0x3AA3u )
        {
          switch ( plLbound[0] )
          {
            case 15011:
              Text = -2147024809;
              if ( !a7 )
                goto LABEL_1657;
              ppvData = 0;
              pszSubKey = (LPCWSTR)GetThreadStateUI();
              if ( IsEqualGUID((_QWORD *)pszSubKey + 104, &GUID_NULL) )
                goto LABEL_1657;
              *(_QWORD *)&String1.vt = 3;
              v494 = SafeArrayCreate(0xCu, 1u, (SAFEARRAYBOUND *)&String1);
              v495 = v494;
              if ( v494 )
              {
                Text = SafeArrayAccessData(v494, &ppvData);
                if ( Text >= 0 )
                {
                  bstrString = 0;
                  Text = StringFromCLSID((const IID *const)pszSubKey + 52, &bstrString);
                  if ( Text >= 0 )
                  {
                    *(_WORD *)ppvData = 8;
                    v496 = SysAllocString(bstrString);
                    v497 = pszSubKey;
                    *((_QWORD *)ppvData + 1) = v496;
                    *((_WORD *)ppvData + 12) = 3;
                    *((_DWORD *)ppvData + 8) = *((_DWORD *)v497 + 212);
                    *((_WORD *)ppvData + 24) = 3;
                    *((_DWORD *)ppvData + 14) = *((_DWORD *)v497 + 213);
                    CoTaskMemFree(bstrString);
                  }
                  SafeArrayUnaccessData(v495);
                  if ( Text >= 0 )
                  {
                    VariantInit(a7);
                    a7->vt = 8204;
                    a7->llVal = (LONGLONG)v495;
                    goto LABEL_1652;
                  }
                }
                goto LABEL_1588;
              }
              goto LABEL_1411;
            case 15005:
              inserted = CDoc::OnGetDocDlgFlags((CDoc *)this, a7);
              goto LABEL_306;
            case 15006:
              CDoc::OnWindowStateChanged((CDoc *)this, a5);
              goto LABEL_53;
            case 15007:
              if ( a6->vt != 8204 || !a6->llVal )
                goto LABEL_231;
              *(_OWORD *)&v614.vt = 0;
              memset(&pvarg, 0, sizeof(pvarg));
              memset(&String1, 0, sizeof(String1));
              memset(&pv, 0, sizeof(pv));
              VariantInit(&pvarg);
              VariantInit(&String1);
              VariantInit(&pv);
              v491 = a6->parray;
              rgIndices[0] = 0;
              Text = SafeArrayGetElement(v491, rgIndices, &pvarg);
              if ( Text >= 0 && pvarg.vt == 8 )
              {
                Text = CLSIDFromString(pvarg.bstrVal, (LPCLSID)&v614);
                if ( !Text )
                {
                  v492 = a6->parray;
                  rgIndices[0] = 1;
                  Text = SafeArrayGetElement(v492, rgIndices, &String1);
                  if ( Text >= 0 && String1.vt == 19 )
                  {
                    v493 = a6->parray;
                    rgIndices[0] = 2;
                    Text = SafeArrayGetElement(v493, rgIndices, &pv);
                    if ( Text >= 0 && pv.vt == 8 )
                      CClassTable::AssignInstallPkgInfo((CClassTable *)(this + 678), pv.bstrVal, String1.cyVal.Lo);
                  }
                }
              }
              VariantClear(&pvarg);
              VariantClear(&String1);
              goto LABEL_883;
            case 15008:
              Text = -2147024809;
              if ( !a6 )
                goto LABEL_1657;
              if ( a6->vt != 3 )
                goto LABEL_1657;
              v418 = CVersions::MapToNearestDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
              if ( v418 < 0 )
                goto LABEL_1657;
LABEL_1125:
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 740LL) = v418;
              goto LABEL_53;
            case 15009:
              Text = -2147024809;
              if ( !a6 || a6->vt != 3 || !a7 )
                goto LABEL_1657;
              VariantInit(a7);
              v483 = a6->lVal;
              if ( v483 )
              {
                v484 = v483 - 1;
                if ( v484 )
                {
                  if ( v484 != 1 )
                    goto LABEL_1657;
                  v485 = CDocument::Markup(v585);
                  a7->vt = 3;
                  v486 = CMarkup::MarkupVersion(v485);
                  v353 = CMarkupVersion::DocumentMode((__int64)v486);
                }
                else
                {
                  v487 = CDocument::Markup(v585);
                  a7->vt = 3;
                  v488 = CMarkup::MarkupVersion(v487);
                  v353 = CMarkupVersion::NativeDocumentMode(v488, 0, 0);
                }
              }
              else
              {
                v489 = (unsigned int)tls_index;
                v490 = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 3;
                v353 = *(_DWORD *)(*(_QWORD *)(v490[v489] + 16LL) + 740LL);
              }
              goto LABEL_929;
          }
          ppvData = GetThreadStateUI();
          *(_QWORD *)&v614.vt = CDoc::PrimaryMarkup((CDoc *)this);
          v475 = *(struct CMarkup **)&v614.vt;
          if ( !a6 )
          {
            Text = -2147024809;
            *(_QWORD *)&v614.vt = (char *)ppvData + 832;
            if ( IsEqualGUID((_QWORD *)ppvData + 104, &GUID_NULL) )
              goto LABEL_1657;
            Text = 0;
            *(GUID *)*(_QWORD *)&v614.vt = GUID_NULL;
            *((_QWORD *)ppvData + 106) = 0;
            if ( !v475 || !CMarkup::IsVersionedChangeEnabled((__int64)v475, 100000) )
            {
LABEL_1654:
              if ( !v9 )
                goto LABEL_1656;
              goto LABEL_1655;
            }
            CWorkerManager::StartProfilingAllWorkers(v475, 0);
            goto LABEL_231;
          }
          if ( a6->vt != 8204 )
            goto LABEL_231;
          v476 = a6->parray;
          if ( !v476 )
            goto LABEL_231;
          bstrString = 0;
          Text = SafeArrayAccessData(v476, (void **)&bstrString);
          if ( Text < 0 )
            goto LABEL_1588;
          v477 = a6->parray;
          pvData = 0;
          Text = SafeArrayGetUBound(v477, 1u, (LONG *)&pvData);
          if ( Text >= 0 )
          {
            v478 = pvData + 1;
            pvData = v478;
            if ( v478 == 3 )
            {
              if ( *bstrString == 8 && bstrString[12] == 3 && bstrString[24] == (_WORD)v478 )
              {
                v479 = ppvData;
                v480 = CLSIDFromString(*((LPCOLESTR *)bstrString + 1), (LPCLSID)ppvData + 52);
                v481 = bstrString;
                Text = v480;
                v479[212] = *((_DWORD *)bstrString + 8);
                v479[213] = *((_DWORD *)v481 + 14);
                if ( !v480 )
                {
                  v482 = *(struct CMarkup **)&v614.vt;
                  if ( *(_QWORD *)&v614.vt )
                  {
                    if ( CMarkup::IsVersionedChangeEnabled(*(__int64 *)&v614.vt, 100000) )
                      CWorkerManager::StartProfilingAllWorkers(v482, 1);
                  }
                }
              }
              else
              {
                Text = -2147024809;
              }
            }
          }
LABEL_1149:
          v417 = a6->parray;
LABEL_1150:
          SafeArrayUnaccessData(v417);
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
            v504 = (__int64 (__fastcall ***)(_QWORD, GUID *, VARIANTARG *, __int64))a6->llVal;
            if ( !v504 )
              goto LABEL_131;
            *(_QWORD *)&String1.vt = 0;
            Text = (**v504)(v504, &IID_INavigateEventSink, &String1, 0xFFFFFFFFLL);
            if ( Text >= 0 )
            {
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 744LL) = *(_QWORD *)&String1.vt;
              goto LABEL_1652;
            }
            goto LABEL_1587;
          case 15016:
            goto LABEL_131;
          case 15017:
            inserted = CDoc::FireOnPopStateEvent((CDoc *)this, v585);
            goto LABEL_306;
          case 15024:
            Text = -2147024809;
            if ( !a6 || a6->vt != 11 )
              goto LABEL_1657;
            *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                 + 16LL)
                     + 587LL) = a6->iVal == 0xFFFF;
            goto LABEL_53;
        }
        if ( plLbound[0] != 15025 )
          goto LABEL_231;
        Text = -2147024809;
        v498 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( !a7 || !a6 || a6->vt != 3 )
          goto LABEL_1657;
        a7->vt = 11;
        Text = 0;
        v499 = a6->lVal;
        if ( v499 )
        {
          if ( v499 != 1 )
            goto LABEL_630;
          if ( !v498 )
          {
            v502 = 0;
            goto LABEL_1427;
          }
          v500 = CMarkup::MarkupVersion(v498);
          IsNativeQuirksLayoutEmulation = CMarkupVersion::IsNativeQuirksLayoutEmulation(v500);
        }
        else
        {
          if ( !v498 )
          {
            v502 = -(*(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                            + (unsigned int)tls_index)
                                          + 16LL)
                              + 587LL) != 0);
            goto LABEL_1427;
          }
          v503 = CMarkup::MarkupVersion(v498);
          IsNativeQuirksLayoutEmulation = CDCompVideoBackedLayer::IsRenderRequired(v503);
        }
        v502 = !IsNativeQuirksLayoutEmulation - 1;
LABEL_1427:
        a7->iVal = v502;
        goto LABEL_1656;
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
              v537 = a6->lVal;
              if ( !*((_BYTE *)this + 1016) || CColorValue::GetIntoABGR((CColorValue *)((char *)this + 1020)) != v537 )
              {
                *((_BYTE *)this + 1016) = 1;
                Text = 0;
                if ( !CServer::IsWebPlatformWindowless((CServer *)this) )
                  v537 |= 0xFF000000;
                CColorValue::SetFromABGR((CColorValue *)((char *)this + 1020), v537);
                CDoc::ForceRelayout((CDoc *)this, 1);
                CDoc::SignalDefaultBackgroundColorChanged((CDoc *)this, v537);
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
            v535 = (int)(float)(CColorValue::GetAlpha((CColorValue *)((char *)this + 1020)) * 255.0);
            v388 = ((unsigned __int8)v535 << 24)
                 | CColorValue::GetColorRef((CColorValue *)((char *)this + 1020)) & 0xFFFFFF;
          }
          else
          {
            v536 = (OLE_COLOR *)this[126];
            if ( !v536 )
            {
              a7->lVal = -16777216;
              goto LABEL_231;
            }
            plLbound[0] = 0;
            Text = OleTranslateColor(*v536, 0, (COLORREF *)plLbound);
            if ( Text )
              goto LABEL_231;
            v388 = plLbound[0] | 0xFF000000;
          }
LABEL_1540:
          a7->lVal = v388;
          goto LABEL_1655;
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
            goto LABEL_1657;
          if ( a5 == 102 )
          {
            v519 = 1;
          }
          else
          {
            if ( a5 != 103 )
              goto LABEL_1657;
            v519 = 0;
          }
          inserted = CDoc::SetGeolocationUserConsent((CDoc *)this, a6->bstrVal, v519);
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
              goto LABEL_1456;
            case 15039:
              Text = -2147024809;
              if ( !a6 )
                goto LABEL_1657;
              if ( a6->vt == 1 )
              {
                v505 = 0;
              }
              else
              {
                if ( a6->vt != 8 )
                  goto LABEL_1657;
                v505 = a6->bstrVal;
              }
              inserted = CDoc::SetExtraHeaders((CDoc *)this, v505);
              break;
            default:
              goto LABEL_231;
          }
          goto LABEL_306;
        }
        if ( !a7 )
          goto LABEL_131;
        v517 = CDocument::GetWindowedMarkupContext(v585);
        IsActiveXFilteringEnabled = CMarkup::IsActiveXFilteringEnabled((__int64)v517);
        a7->vt = 11;
        v434 = IsActiveXFilteringEnabled != 1;
LABEL_1498:
        a7->iVal = v434 - 1;
        goto LABEL_941;
      }
      if ( !a6 || !a7 )
        goto LABEL_231;
      if ( a6->vt != 13 )
        goto LABEL_230;
      v520 = a6->punkVal;
      if ( !v520 )
        goto LABEL_230;
      *(_QWORD *)plLbound = 0;
      *(GUID *)&v614.vt = CLSID_CElement;
      Text = QIClassID(v520, (struct _GUID *)&v614, (void **)plLbound);
      if ( Text < 0 )
        goto LABEL_1587;
      if ( !(unsigned int)CElement::IsInMarkup(*(CElement **)plLbound) )
      {
        Text = -2147418113;
        goto LABEL_230;
      }
      Text = CElement::EnsureRecalcNotify(*(CElement **)plLbound);
      if ( Text < 0 )
        goto LABEL_1587;
      CRect::CRect((CRect *)&v614);
      CRect::CRect((CRect *)&String1);
      Text = CElement::GetBoundingRect(*(CElement **)plLbound, (struct CRectF *)&String1, 16385, 0);
      if ( Text >= 0
        && (CElement::IsDeviceFixed(*(CTreeNode ***)plLbound)
         || (unsigned int)CElement::IsAncestorPositionFixed(*(CElement **)plLbound, 1))
        && CElement::IsStandardsMode(*(CElement **)plLbound) )
      {
        v521 = CElement::LayoutServices(*(CElement **)plLbound);
        if ( v521 )
        {
          v522 = *(_QWORD *)v521;
          bstrString = 0;
          LOBYTE(pvt[0]) = 0;
          (*(void (__fastcall **)(struct ILayoutServices *, _QWORD, BSTR *, VARTYPE *))(v522 + 432))(
            v521,
            *(_QWORD *)plLbound,
            &bstrString,
            pvt);
          for ( j = bstrString; j; bstrString = j )
          {
            v524 = CDispNode::NodeReader((CDispNode *)j);
            if ( CDispNodeReader::IsTopLevelScroller(v524) )
            {
              v525 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              TotalZoomFactor = CDispScroller::GetTotalZoomFactor(v525);
              HIDWORD(v527) = *(_DWORD *)&CLSID_CElement.Data2;
              v528 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              *(float *)&v527 = TotalZoomFactor / CDispTopLevelScroller::BaseOpticalZoomFactor(v528);
              CRectF::operator/=((__m128 *)&String1, v527);
              break;
            }
            j = (OLECHAR *)CDispNode::GetParentNode((CDispNode **)bstrString);
          }
        }
      }
      CRect::SetRect((CRect *)&v614, (const struct D2D_RECT_F *)&String1, 0);
      if ( Text >= 0 )
      {
        VariantInit(a7);
        a7->vt = 8195;
        v531 = SafeArrayCreateVector(3u, 0, 4u);
        a7->llVal = (LONGLONG)v531;
        if ( v531 )
        {
          *(_DWORD *)pvt = 0;
          SafeArrayPutElement(v531, (LONG *)pvt, &v614);
          v532 = a7->parray;
          v25 = 1;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v532, (LONG *)pvt, &v614.decVal.Hi32);
          v533 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v533, (LONG *)pvt, &v614.decVal.8);
          v534 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v534, (LONG *)pvt, (char *)&v614.decVal.Lo64 + 4);
LABEL_1529:
          CDispClient::AdjustContentSize((CDispClient *)&String1, v529, v530);
          goto LABEL_231;
        }
        Text = -2147024882;
      }
      v25 = 1;
      goto LABEL_1529;
    }
    switch ( plLbound[0] )
    {
      case 15200:
        bstrString = 0;
        v550 = 0;
        if ( a6 )
        {
          if ( a6->vt == 13 )
          {
            v551 = (void (__fastcall ***)(_QWORD, GUID *, struct CHtmParseCtx *))a6->llVal;
            if ( v551 )
            {
              v552 = **v551;
              v553 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)&bstrString);
              v552(v551, &GUID_0000000e_0000_0000_c000_000000000046, v553);
              v550 = (struct IBindCtx *)bstrString;
            }
          }
          v25 = 1;
        }
        v554 = CFlipAheadManager::InvokeCachedTarget((CFlipAheadManager *)(this + 836), v550);
        v55 = bstrString;
        Text = v554;
LABEL_959:
        if ( !v55 )
          goto LABEL_231;
        goto LABEL_111;
      case 15202:
        v549 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v544 = (__int64)v549;
        if ( v549 )
        {
          if ( (unsigned int)CMarkup::GetDebugState((__int64)v549) == 2 )
            goto LABEL_1654;
          plLbound[0] = CMarkup::GetDebugState(v544);
          v545 = plLbound[0];
          CMarkup::SetDebugState(v544, 2);
          v546 = 2;
          goto LABEL_1570;
        }
        break;
      case 15203:
        v548 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v544 = (__int64)v548;
        if ( v548 )
        {
          if ( (unsigned int)CMarkup::GetDebugState((__int64)v548) != 2 )
            goto LABEL_1654;
          plLbound[0] = CMarkup::GetDebugState(v544);
          CMarkup::SetDebugState(v544, 1);
          Text = CDoc::DynamicDetachDebugger((CDoc *)this);
          if ( Text >= 0 )
            goto LABEL_1610;
          v547 = plLbound[0];
          goto LABEL_1572;
        }
        break;
      case 15204:
        v543 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v544 = (__int64)v543;
        if ( v543 )
        {
          if ( (unsigned int)CMarkup::GetDebugState((__int64)v543) )
            goto LABEL_1654;
          plLbound[0] = CMarkup::GetDebugState(v544);
          v545 = plLbound[0];
          CMarkup::SetDebugState(v544, 1);
          v546 = 1;
LABEL_1570:
          Text = CDoc::DynamicAttachDebugger(this, v545, v546);
          if ( Text >= 0 )
            goto LABEL_1610;
          v547 = plLbound[0];
LABEL_1572:
          CMarkup::SetDebugState(v544, v547);
          goto LABEL_1588;
        }
        break;
      case 15205:
        VariantInit(a7);
        a7->vt = 3;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v542 = CDoc::PrimaryMarkup((CDoc *)this);
          DebugState = CMarkup::GetDebugState((__int64)v542);
        }
        else
        {
          DebugState = 0;
        }
        goto LABEL_1032;
      default:
        goto LABEL_231;
    }
    Text = -2147418113;
    goto LABEL_1588;
  }
  if ( v612 )
    CScriptCollection::Release(v612);
  Text = -2147467263;
LABEL_15:
  CServer::CLock::~CLock((CServer::CLock *)v611);
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
