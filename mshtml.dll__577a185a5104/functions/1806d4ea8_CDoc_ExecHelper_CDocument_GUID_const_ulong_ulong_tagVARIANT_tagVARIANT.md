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
  __int64 v19; // r8
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
  int v172; // eax
  CMarkup *v173; // rax
  struct CGlyph *GlyphTable; // rax
  int v175; // edx
  CPeerFactoryUrl *v176; // rcx
  unsigned __int16 *Url; // rax
  CMarkup *v178; // rax
  CScriptCollection *ScriptCollection; // rax
  LONG v180; // esi
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
  int v250; // eax
  struct IUnknown *v251; // rcx
  int v252; // eax
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
  struct COmWindowProxy *v323; // rsi
  LONG lVal; // ecx
  __int64 v325; // rbx
  struct GWND *Gwnd; // rax
  struct CElement *v327; // rdx
  int v328; // ecx
  HMENU DocDirMenu; // rax
  LONG v330; // eax
  int v331; // esi
  bool v332; // al
  __int16 *v333; // rdx
  bool v334; // al
  __int16 *v335; // rcx
  __int16 v336; // cx
  HMENU FontSizeMenu; // rax
  LONG v338; // eax
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, BSTR *); // rcx
  CDocument *v340; // rdi
  struct INamedPropertyBag *v341; // rbx
  struct CMarkup *v342; // rax
  CMarkup *v343; // rax
  struct CElement *v344; // rax
  COmWindowProxy *v345; // rcx
  CDocument *v346; // rax
  BSTR v347; // rax
  struct CMarkup *v348; // rax
  struct IDispRenderTarget *v349; // rax
  LONG v350; // eax
  ReadingMode::CTextClusterDetector *v351; // rax
  ReadingMode::CTextClusterDetector *v352; // rax
  ReadingMode::CTextClusterDetector *v353; // rbx
  CInputManager *v354; // rax
  CDeferredActionHandler *v355; // rax
  struct CMarkup *v356; // rax
  CInPlace *v357; // rbx
  __int64 CodePageCore; // r8
  unsigned int v359; // esi
  BSTR v360; // rcx
  bool IsEnterpriseMode; // bl
  CMarkup *v362; // rax
  CMarkupVersion *v363; // rax
  SHORT v364; // ax
  bool v365; // zf
  struct CMarkup *v366; // rax
  struct CMarkup *v367; // rbx
  CInPlace *v368; // rcx
  CInputManager *v369; // rax
  CDeferredActionHandler *v370; // rax
  CInputManager *v371; // rax
  CDeferredActionHandler *v372; // rax
  CInputManager *v373; // rax
  CDeferredActionHandler *v374; // rax
  CInputManager *v375; // rax
  CDeferredActionHandler *v376; // rax
  CInputManager *v377; // rax
  CDeferredActionHandler *v378; // rax
  SHORT v379; // cx
  int v380; // eax
  CVirtualTabStorageEntry *v381; // rcx
  struct CMarkup *v382; // rax
  CPreloadManager *v383; // rax
  struct IDispSystem *DispSystem; // rax
  LONG v385; // eax
  LONG v386; // ecx
  unsigned int Lo; // r9d
  CInPlace **v388; // rax
  LONG DebugState; // eax
  struct THREADSTATEUI *ThreadStateUI; // rax
  struct CMarkup *v391; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdx
  LONG v393; // r8d
  struct CMarkup *v394; // rax
  int v395; // ecx
  SAFEARRAY *Vector; // rax
  __int64 i; // r13
  char v398; // r8
  _QWORD *v399; // rbx
  COptionsHolder *v400; // rax
  CHtmCtx *v401; // rax
  const wchar_t *OriginalUrlContext; // rax
  const OLECHAR *v403; // rcx
  unsigned __int64 v404; // rdi
  size_t v405; // r8
  int v406; // eax
  BSTR v407; // rcx
  _QWORD *v408; // rax
  char v409; // dl
  _QWORD *v410; // rcx
  struct CSecurityContext *v411; // rax
  _QWORD *v412; // rcx
  _QWORD *v413; // rcx
  SAFEARRAY *v414; // rcx
  int v415; // eax
  struct CView *View; // rax
  struct CView *v417; // rdi
  int v418; // ebx
  const struct CDispNode *v419; // rdx
  struct CRect *v420; // r8
  const struct CDispNode *v421; // rdx
  struct CRect *v422; // r8
  struct CView *v423; // rax
  struct CView *v424; // rax
  bool IsMobileOptimizedSite; // al
  struct CView *v426; // rax
  SAFEARRAY *v427; // rcx
  SAFEARRAY *v428; // rcx
  CView *v429; // rax
  CFullScreenState *v430; // rax
  __int16 v431; // cx
  struct IUnknown *v432; // rcx
  CElement *v433; // rcx
  struct IUnknown *v434; // rcx
  CFullScreenState *v435; // rax
  int *v436; // rax
  CRootTracker *RootTracker; // rax
  CDCompLayerManager *v438; // rbx
  struct IDispLayer *v439; // rdi
  __int64 (__fastcall *v440)(struct IDispLayer *, GUID *, struct CHtmParseCtx *); // rbx
  CHtmRootParseCtxRouter *v441; // rax
  struct CHtmParseCtx *HpxEmbed; // rax
  struct IDispRenderTarget *v443; // rax
  CAPProcessor *v444; // rcx
  CWindow *v445; // rax
  CWindow *v446; // rbx
  CMarkup *v447; // rdi
  struct COmWindowProxy *v448; // rax
  __int64 v449; // rdx
  __int64 v450; // r9
  _QWORD *ThreadLocalStoragePointer; // rax
  bool v452; // zf
  struct CView *v453; // rax
  CViewportController *v454; // rcx
  _QWORD *v455; // rax
  unsigned int VirtualTabID; // eax
  struct CView *v457; // rax
  CViewportController *v458; // rcx
  CInPlace *v459; // rax
  LONG v460; // ecx
  const struct CMarkup *v461; // rax
  CTextScalingSettings *TextScalingSettings; // rax
  const struct CDispNode *v463; // rdx
  struct CRect *v464; // r8
  SAFEARRAY *v465; // rcx
  SAFEARRAY *v466; // rcx
  struct CMarkup *v467; // rax
  COmWindowProxy *v468; // rcx
  unsigned int (__fastcall ***v469)(_QWORD, GUID *, void **, __int64); // rcx
  CInPlace *v470; // rcx
  struct CMarkup *v471; // rbx
  SAFEARRAY *v472; // rcx
  SAFEARRAY *v473; // rcx
  unsigned int v474; // eax
  _DWORD *v475; // rbx
  HRESULT v476; // eax
  BSTR v477; // rcx
  struct CMarkup *v478; // rbx
  LONG v479; // ecx
  int v480; // ecx
  CMarkup *v481; // rax
  const struct CMarkupVersion *v482; // rax
  CMarkup *v483; // rax
  const struct CMarkupVersion *v484; // rax
  __int64 v485; // rdx
  _QWORD *v486; // rax
  SAFEARRAY *v487; // rcx
  SAFEARRAY *v488; // rcx
  SAFEARRAY *v489; // rcx
  SAFEARRAY *v490; // rax
  SAFEARRAY *v491; // rbx
  BSTR v492; // rax
  LPCWSTR v493; // rdx
  CMarkup *v494; // rax
  LONG v495; // edx
  CMarkupVersion *v496; // rax
  bool IsNativeQuirksLayoutEmulation; // al
  SHORT v498; // cx
  CDCompVideoBackedLayer *v499; // rax
  __int64 (__fastcall ***v500)(_QWORD, GUID *, VARIANTARG *, __int64); // rcx
  const unsigned __int16 *v501; // rdx
  int v502; // ecx
  int iVal; // ebx
  LONG v504; // eax
  int v505; // eax
  unsigned int v506; // esi
  const struct CMarkup *v507; // rax
  const unsigned __int16 *UrlRaw; // rax
  const WCHAR *v509; // rcx
  SAFEARRAY *parray; // rax
  const unsigned __int16 *bstrVal; // r8
  unsigned int v512; // ebx
  struct CMarkup *v513; // rax
  int IsActiveXFilteringEnabled; // eax
  int v515; // r8d
  struct IUnknown *v516; // rcx
  struct ILayoutServices *v517; // rax
  __int64 v518; // rcx
  OLECHAR *j; // rax
  CDispNodeReader *v520; // rax
  CDispScroller *v521; // rax
  CDispTopLevelScroller *v522; // rax
  const struct CDispNode *v523; // rdx
  struct CRect *v524; // r8
  SAFEARRAY *v525; // rax
  SAFEARRAY *v526; // rcx
  SAFEARRAY *v527; // rcx
  SAFEARRAY *v528; // rcx
  int v529; // ebx
  OLE_COLOR *v530; // rcx
  LONG v531; // ebx
  CMarkup *v532; // rax
  LONG v533; // ebx
  CMarkup *v534; // rax
  struct CMarkup *RootMarkup; // rax
  struct CMarkup *v536; // rax
  struct CMarkup *v537; // rax
  struct CMarkup *v538; // rbx
  unsigned int v539; // esi
  __int64 v540; // r8
  __int64 v541; // rdx
  struct CMarkup *v542; // rax
  struct CMarkup *v543; // rax
  struct IBindCtx *v544; // rdx
  void (__fastcall ***v545)(_QWORD, GUID *, struct CHtmParseCtx *); // rdi
  void (__fastcall *v546)(_QWORD, GUID *, struct CHtmParseCtx *); // rbx
  struct CHtmParseCtx *v547; // rax
  int v548; // eax
  unsigned int CodePageFromMenuID; // esi
  int IsCpAutoDetect; // eax
  CInPlace *v551; // rcx
  int v552; // ebx
  HWND v553; // rax
  CElement *v554; // rcx
  CMarkup *v555; // rax
  CMarkup *FrameOrPrimaryMarkup; // rax
  CMarkup *v557; // r13
  CWindowBarProp *v558; // rdi
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
        v354 = CDoc::InputManager((CDoc *)this);
        v355 = CInputManager::DeferredActionHandler(v354);
        NormZoomPercent = CDeferredActionHandler::RegisterVTabNavigate(v355);
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
                  v502 = *((_DWORD *)this + 1217);
                  if ( (v502 & 0x800) != 0 )
                    goto LABEL_231;
                  iVal = 0;
                  v504 = *((_DWORD *)this + 1215);
                  plLbound[0] = v504;
                  if ( v582 == 93 && (v504 & 1) == 0
                    || v582 == 15038
                    || (v502 & 0x80u) != 0
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
                  v505 = iVal | 1;
                  if ( a5 != 2 )
                    v505 = iVal;
                  v506 = v505 | 0x1000000;
                  if ( v20 != 15038 )
                    v506 = v505;
                  if ( (*((_DWORD *)this + 1215) & 0x400000) == 0 )
                  {
                    v507 = CDoc::PrimaryMarkup((CDoc *)this);
                    UrlRaw = CMarkup::GetUrlRaw(v507);
                    v509 = L"about:blank";
                    if ( UrlRaw )
                      v509 = UrlRaw;
                    if ( *v509 && !wcscmp_0(v509, L"outday://") )
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
                        v512 = a5;
                        Text = CDoc::PrintHandler((CDoc *)this, v578, bstrVal, 0, v506, parray, a5, a6, a7, 0);
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
                            *(_QWORD *)&v609.vt = GetThreadStateUI();
                            if ( CodePageFromMenuID == -1 )
                            {
                              if ( v20 != 3699
                                || (IsCpAutoDetect = CDoc::IsCpAutoDetect((CDoc *)this),
                                    CDoc::SetCpAutoDetect((CDoc *)this, IsCpAutoDetect == 0),
                                    !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this))
                                || !(unsigned int)CMLang::IsMLangAvailable((CMLang *)&g_MLang) )
                              {
LABEL_1608:
                                ++*(_DWORD *)(*(_QWORD *)&v609.vt + 604LL);
                                goto LABEL_53;
                              }
                              CodePageFromMenuID = 50001;
                              if ( g_cpDefault == 932 )
                                CodePageFromMenuID = 50932;
                            }
                            v551 = this[12];
                            if ( v551 )
                            {
                              v552 = (_DWORD)this[556] & 0x40000000;
                              v553 = CInPlace::_hwnd_Get(v551);
                              if ( !(unsigned int)CMLang::ValidateCodePage(
                                                    (CMLang *)&g_MLang,
                                                    g_cpDefault,
                                                    CodePageFromMenuID,
                                                    v553,
                                                    1,
                                                    v552) )
                              {
                                v554 = this[544];
                                v555 = v554 ? CElement::GetMarkupPtr(v554) : CDocument::Markup(v578);
                                FrameOrPrimaryMarkup = CMarkup::GetFrameOrPrimaryMarkup(v555, 1);
                                v557 = FrameOrPrimaryMarkup;
                                if ( FrameOrPrimaryMarkup )
                                {
                                  v558 = CMarkup::Root(FrameOrPrimaryMarkup);
                                  CNotification::CNotification((CNotification *)&v591);
                                  CWindowBarProp::SecurityContext(v558);
                                  CNotification::Initialize(&v591, 59, v558);
                                  if ( !(unsigned int)CDoc::IsCpAutoDetect((CDoc *)this)
                                    && !(unsigned int)CMarkup::HaveCodePageMetaTag(v557) )
                                  {
                                    CDoc::SaveDefaultCodepage((CDoc *)this, CodePageFromMenuID);
                                  }
                                  CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
                                  CMarkup::BubbleDownCodePage(v557, CodePageFromMenuID);
                                  v559 = CMarkup::Window(v557);
                                  CPSrc = CMarkup::GetCPSrc(v557);
                                  CodePage = CMarkup::GetCodePage(v557);
                                  COmWindowProxy::ExecRefresh(v559, 5, CodePage, CPSrc);
                                }
                              }
                            }
                            goto LABEL_1608;
                          }
                          a5 = v512;
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
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, MSHTML_PRINTPREVIEW_START, 0, 1, &v609);
                      if ( a6 && a6->vt == 8 )
                        v50 = a6->bstrVal;
                      else
                        v50 = 0;
                      Text = CDoc::PrintHandler((CDoc *)this, v578, v50, 0, 0, 0, a5, a6, a7, 1);
                      if ( (Microsoft_IEEnableBits & 0x10000) != 0 )
                        McGenEventWrite_EventWriteTransfer(&BERP_IE_Context, MSHTML_PRINTPREVIEW_STOP, 0, 1, &v609);
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
                  HWND = (unsigned int)CServer::GetHWND((CServer *)this);
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
                      goto LABEL_1644;
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
LABEL_1646:
                        if ( v20 == 15 && !(unsigned int)CDoc::HasSelection((CDoc *)this) )
                        {
                          v452 = Text == 0;
                          if ( Text < 0 )
                            goto LABEL_1653;
                          goto LABEL_1649;
                        }
LABEL_1652:
                        v452 = Text == 0;
LABEL_1653:
                        if ( !v452 )
                          goto LABEL_1657;
                        goto LABEL_1654;
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
                  v198 = v586;
                  *(_QWORD *)&String1.vt = 0;
                  if ( v586 )
                    goto LABEL_1630;
                  SelectionMarkup = CDoc::GetSelectionMarkup((CDoc *)this, (struct CMarkup **)&v586);
                  v198 = v586;
                  if ( !v586 )
                  {
                    if ( CDoc::GetActiveElement((CDoc *)this) )
                    {
                      v200 = CDoc::GetActiveElement((CDoc *)this);
                      v198 = (struct IUnknown *)CElement::GetMarkupPtr(v200);
                      v586 = v198;
                    }
                    else
                    {
                      v198 = v586;
                    }
                  }
                  if ( SelectionMarkup >= 0 && v198 )
                  {
LABEL_1630:
                    Text = CMarkup::EnsureEditRouter((CMarkup *)v198, (struct CEditRouter **)&String1);
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
LABEL_1638:
                          *((_DWORD *)v573 + 10) &= ~0x800u;
                          *((_DWORD *)v573 + 10) |= v25 << 11;
                          if ( v25 )
                            CDoc::CDOMTextInputScope::Init((CDoc::CDOMTextInputScope *)&v609, (struct CDoc *)this, 2);
                          *((_DWORD *)v573 + 10) |= 0x400u;
                          goto LABEL_1641;
                        }
                        if ( v20 == 26 || v20 - 2500 <= 1 )
                          goto LABEL_1638;
                      }
LABEL_1641:
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
LABEL_1645:
                      if ( Text == -2147221248 )
                      {
LABEL_1649:
                        if ( CDoc::EntityHasFocus((CDoc *)this) )
                        {
                          FocusedEntity = CDoc::GetFocusedEntity((CDoc *)this);
                          if ( FocusedEntity )
                            Text = CEntity::Exec(FocusedEntity, v584, v582, v570, v7, a7);
                        }
                        goto LABEL_1652;
                      }
                      goto LABEL_1646;
                    }
                  }
                }
LABEL_1644:
                v570 = a5;
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
                    v365 = (unsigned int)CTQueryStatus(
                                           *((struct IUnknown **)v59 + 10),
                                           0,
                                           1u,
                                           (struct _tagOLECMD *const)&ppvData,
                                           0) == 0;
                    v61 = bstrString;
                    if ( v365 && HIDWORD(ppvData) == 3 )
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
LABEL_1660:
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
                      v365 = *((_BYTE *)v105 + 56) == 0;
                      Buffer = 0;
                      if ( v365 )
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
LABEL_1587:
              v25 = 1;
              goto LABEL_1588;
            }
            LODWORD(lpcbData) = 11;
            CDoc::ShowMessage((CDoc *)this, &v605, 0, 0, 0x5EDu, lpcbData, 0, 10570, 1001, &Source, &Source);
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
              if ( *(__int64 (__fastcall **)())(*(_QWORD *)v142 + 1624LL) != _vtguard )
                goto LABEL_1660;
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
                goto LABEL_1660;
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
                  v164 = 0;
                  pvData = ConvertSBCMDID(plLbound[0]);
                  plLbound[0] = 0;
                  if ( v20 == 2135 )
                  {
                    v609.vt = 3;
                    v609.lVal = 1;
LABEL_361:
                    v164 = &v609;
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
                    if ( v609.vt == 13 && v609.llVal )
                      (*(void (__fastcall **)(LONGLONG, __int64))(*v609.pllVal + 16))(v609.llVal, v165);
                    goto LABEL_230;
                  }
                  if ( v20 != 2266 )
                  {
                    v609.vt = 3;
                    v169 = 6;
                    if ( v20 != 2130 )
                      v169 = 1;
                    v609.lVal = v169 | 0x20000;
                    goto LABEL_361;
                  }
                  v166 = this[544];
                  bstrString = 0;
                  Text = GetExecDocument((struct CDocument **)&bstrString, v166, v578);
                  if ( Text < 0 )
                    goto LABEL_1657;
                  if ( bstrString )
                  {
                    v167 = *((_QWORD *)bstrString + 7);
                    if ( v167 )
                      v168 = *(CMarkup **)(v167 + 104);
                    else
                      v168 = (CMarkup *)*((_QWORD *)bstrString + 6);
                    if ( !(unsigned int)CMarkup::IsPrimaryMarkup(v168) )
                    {
                      v609.vt = 13;
                      Text = CDocument::QueryInterface((CDocument *)bstrString, &IID_IUnknown, &v609.byref);
                      if ( Text )
                        goto LABEL_1657;
                      v164 = &v609;
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
                    goto LABEL_1657;
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
                goto LABEL_1655;
              }
LABEL_330:
              Text = -2147467261;
              goto LABEL_1657;
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
              goto LABEL_1589;
            if ( ((plLbound[0] - 6041) & 0xFFFFFFFD) == 0
              || v318
              || ((v320 = this[544]) == 0 ? (v321 = CDocument::Markup(v578)) : (v321 = CElement::GetMarkupPtr(v320)),
                  !v321
               || (v322 = CMarkup::GetFrameOrPrimaryMarkup(v321, 1)) == 0
               || (v323 = CMarkup::Window(v322)) == 0) )
            {
              v323 = this[103];
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
            v325 = lVal;
            Gwnd = GetGwnd();
            inserted = _GWPostMethodCallEx(
                         Gwnd,
                         (unsigned __int64)v323,
                         (__int64)COmWindowProxy::ExecRefreshCallback,
                         v325,
                         0,
                         0);
            goto LABEL_306;
          }
          switch ( plLbound[0] )
          {
            case 2302:
              if ( a6 && a6->vt == 3 )
              {
                v180 = a6->lVal;
                if ( ((*((_DWORD *)this + 1215) >> 4) & 1) != (v180 != 0) )
                {
                  CNotification::CNotification((CNotification *)&v591);
                  v365 = ((_DWORD)this[608] & 0x80000) == 0;
                  *((_DWORD *)this + 1215) ^= ((unsigned __int8)*((_DWORD *)this + 1215)
                                             ^ (unsigned __int8)(16 * v180))
                                            & 0x10;
                  if ( !v365 )
                  {
                    v181 = *((_DWORD *)this + 45);
                    v182 = CDoc::PrimaryRoot((CDoc *)this);
                    CNotification::EnableInteraction1((CNotification *)&v591, v182, 0);
                    CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
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
                    CImgAnim::SetAnimState(v183, this, v180 == 0);
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
              *(GUID *)&v609.vt = CGID_MSHTML;
              CDoc::Exec((CDoc *)this, (const struct _GUID *)&v609, 0x90Eu, 0, a6, 0);
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
              v173 = CDocument::Markup(v578);
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
                v203 = CDocument::Markup(v578);
                Text = CMarkup::EnsureGlyphTableExistsAndExecute(v203, v584, v20, a5, v7, a7);
                if ( !Text )
                {
                  if ( v20 != 2336 )
                  {
                    if ( ((((v204 = CDocument::Markup(v578), v205 = CMarkup::GetGlyphTable(v204), v20 == 2327)
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
                        goto LABEL_1666;
                    }
                    if ( v20 == 2325 )
                    {
LABEL_1666:
                      *(_DWORD *)v205 &= ~0x10u;
                      *(_DWORD *)v205 |= 16 * v201;
                      if ( v20 == 2327 )
                        goto LABEL_1665;
                    }
                    if ( v20 == 2320 )
                    {
LABEL_1665:
                      *(_DWORD *)v205 &= ~0x40u;
                      *(_DWORD *)v205 |= v201 << 6;
                      if ( v20 == 2327 )
                        goto LABEL_1664;
                    }
                    if ( v20 == 2326 )
                    {
LABEL_1664:
                      *(_DWORD *)v205 ^= (*(_DWORD *)v205 ^ (32 * v201)) & 0x20;
                      if ( v20 == 2327 )
                        goto LABEL_499;
                    }
                    if ( v20 == 2340 )
LABEL_499:
                      *(_DWORD *)v205 ^= (*(_DWORD *)v205 ^ (v201 << 7)) & 0x80;
                  }
                  CVariant::~CVariant(&pvarg);
                  goto LABEL_1589;
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
              v186 = CDocument::Markup(v578);
              inserted = CMarkup::EnsureGlyphTableExistsAndExecute(v186, v584, plLbound[0], a5, a6, a7);
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
              v184 = CDocument::Markup(v578);
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
          v187 = CDocument::Markup(v578);
          v188 = v187;
          if ( a6 && a6->vt == 11 )
            v189 = a6->bVal != 0;
          else
            v189 = !CMarkup::IsShowZeroBorderAtDesignTime(v187);
          if ( plLbound[0] == 2328 )
          {
            CMarkup::SetShowZeroBorderAtDesignTime(v188, v189);
            CNotification::CNotification((CNotification *)&v591);
            ElementTopHelper = CMarkup::GetElementTopHelper(v188);
            CNotification::ZeroGrayChange((CNotification *)&v591, ElementTopHelper);
            CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
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
          COnCommandExecParams::COnCommandExecParams((COnCommandExecParams *)v610);
          *(_QWORD *)v610 = v584;
          *(_DWORD *)&v610[8] = v582;
          CNotification::CNotification((CNotification *)&v591);
          if ( v20 == 2328 )
            v192 = CMarkup::Root(v188);
          else
            v192 = CDoc::PrimaryRoot((CDoc *)this);
          CNotification::Command((CNotification *)&v591, v192, v610, 0);
          CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
          goto LABEL_1654;
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
                        v215 = CDocument::Markup(v578);
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
                      Text = GetExecDocument((struct CDocument **)&String1, this[544], v578);
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
                            v213 = CDocument::Markup(v578);
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
                        v207 = CDocument::Markup(v578);
                      if ( !v207
                        || (v208 = CMarkup::GetFrameOrPrimaryMarkup(v207, 1), (v209 = v208) == 0)
                        || (unsigned int)CMarkup::IsImageFile(v208) )
                      {
                        Text = 0;
                        goto LABEL_1589;
                      }
                      if ( plLbound[0] != 2139
                        || !(unsigned int)CMarkup::IsPrimaryMarkup(v209)
                        || !(unsigned int)CDoc::IsAggregatedByXMLMime((CDoc *)this) )
                      {
                        Text = CDoc::GetViewSourceFileName((CDoc *)this, psz, 0x823u, v209);
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
                      v222 = *((_QWORD *)v578 + 7);
                      v223 = v222 ? *(_QWORD *)(v222 + 104) : *((_QWORD *)v578 + 6);
                      v218 = CIPrintCollection::CIPrintCollection(v221, *(struct CSecurityContext **)(v223 + 320));
                      if ( v218 )
                      {
                        v224 = *((_QWORD *)v578 + 7);
                        if ( v224 )
                          v225 = *(CMarkup **)(v224 + 104);
                        else
                          v225 = (CMarkup *)*((_QWORD *)v578 + 6);
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
                                v592 = *(_QWORD *)(v227 + 48);
                                v597 = 0;
                                v598 = 0;
                                v594 = 0;
                                v591 = 88;
                                v596 = v218;
                                v595 = 18436;
                                v593 = 0;
                                CNotification::SetElement((CNotification *)&v591, (struct CElement *)v227);
                                CMarkup::Notify(v225, (struct CNotification *)&v591, 0);
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
                  goto LABEL_1656;
                }
                if ( !CDoc::GetActiveElement((CDoc *)this) )
                  goto LABEL_600;
                v228 = (CIPrintCollection *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 80);
                if ( !v228 )
                  goto LABEL_902;
                v229 = CDoc::GetActiveElement((CDoc *)this);
                v230 = CElement::GetMarkupPtr(v229);
                v218 = CIPrintCollection::CIPrintCollection(v228, *((struct CSecurityContext **)v230 + 40));
                if ( !v218 )
                  goto LABEL_902;
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
                  goto LABEL_902;
                v237 = *((_QWORD *)v578 + 7);
                v238 = v237 ? *(_QWORD *)(v237 + 104) : *((_QWORD *)v578 + 6);
                v218 = CIPrintCollection::CIPrintCollection(v236, *(struct CSecurityContext **)(v238 + 320));
                if ( !v218 )
                  goto LABEL_902;
                v239 = CDocument::Window(v578);
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
              v255 = *((_QWORD *)v578 + 7);
              if ( v255 )
                v256 = *(CMarkup **)(v255 + 104);
              else
                v256 = (CMarkup *)*((_QWORD *)v578 + 6);
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
                  v365 = (*((_DWORD *)this + 1237))-- == 1;
                  if ( v365 && (*((_DWORD *)this + 1217) & 0x4000) != 0 )
                  {
                    v253 = v578;
                    if ( v578 )
                    {
                      if ( CDocument::Window(v578) )
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
                  v245 = CDocument::Markup(v578);
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
              goto LABEL_1657;
            }
            v248 = CDocument::Markup(v578);
            if ( !(unsigned int)CMarkup::IsConnectedToPrimaryMarkup(v248) )
            {
              CMarkup::TearDownMarkup(v248, 1, 0);
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
              v271 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&String1.vt = v271;
              if ( !v271 || !a6 || a6->vt != 8 )
                goto LABEL_1654;
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
                    goto LABEL_1654;
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
                    goto LABEL_1654;
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
                goto LABEL_1657;
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
                  goto LABEL_1654;
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | (v270 != 0 ? 0x20000 : 0);
              }
              else
              {
                *((_DWORD *)this + 1215) = *((_DWORD *)this + 1215) & 0xFFFDFFFF | ~*((_DWORD *)this + 1215) & 0x20000;
              }
              CDoc::NotifySelection(this, 17, 0, 0, 0);
              goto LABEL_1654;
            case 2437:
              Text = 0;
              v266 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v609.vt = v266;
              v267 = v266;
              if ( !v266 || !a6 || a6->vt != 11 )
                goto LABEL_1654;
              if ( CMarkup::GetStyleState(v266) )
              {
                CMarkup::CLock::CLock((CMarkup::CLock *)&String1, v267);
                v268 = *(_QWORD *)&v609.vt;
                v269 = a6->bVal != 0;
                *((_BYTE *)CMarkup::GetStyleState(*(CMarkup **)&v609.vt) + 24) = v269;
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
                goto LABEL_1654;
              a7->iVal = 0;
              if ( CMarkup::GetStyleState(v264) )
              {
                if ( *((_BYTE *)CMarkup::GetStyleState(v265) + 24) )
                  a7->iVal = -1;
                goto LABEL_1655;
              }
              goto LABEL_902;
            case 2439:
              Text = 0;
              v260 = CDoc::PrimaryMarkup((CDoc *)this);
              *(_QWORD *)&v609.vt = v260;
              if ( !v260 )
                goto LABEL_1654;
              a7->llVal = 0;
              if ( !CMarkup::GetStyleState(v260) )
              {
                Text = -2147024882;
                goto LABEL_1588;
              }
              if ( a7->vt != 8 )
                goto LABEL_1654;
              v261 = *(CMarkup **)&v609.vt;
              v262 = CMarkup::GetStyleState(*(CMarkup **)&v609.vt);
              if ( (unsigned int)CStr::IsNull(v262) )
                goto LABEL_1655;
              v263 = CMarkup::GetStyleState(v261);
              Text = CStr::AllocBSTR(v263, &a7->bstrVal);
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
            v284 = a6->parray;
            *(_QWORD *)&v609.vt = v284;
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
                v286 = *(SAFEARRAY **)&v609.vt;
                v287 = 0;
                v288 = 0;
                memset(v610, 0, sizeof(v610));
                rgIndices[0] = 0;
                do
                {
                  if ( !Text )
                  {
                    Element = SafeArrayGetElement(v286, rgIndices, &v610[8 * v288]);
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
                           *(const unsigned __int16 **)v610,
                           *(const unsigned __int16 **)&v610[8],
                           *(const unsigned __int16 **)&v610[16],
                           *(const unsigned __int16 **)&v610[24],
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
                goto LABEL_1655;
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
              Text = GetExecDocument((struct CDocument **)&String1, v308, v578);
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
                      CDoc::ExecHelper(this, v578, (struct _GUID *)&CGID_MSHTML, pvData, 0, 0, 0);
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
                  v304 = a6->bstrVal;
                  if ( v304 )
                  {
                    v305 = CDocument::Markup(v578);
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
                goto LABEL_1657;
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
              v295 = v578;
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
              v512 = a5;
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
                CNotification::CNotification((CNotification *)&v591);
                v314 = CDoc::PrimaryMarkup((CDoc *)this);
                v315 = CMarkup::GetElementTopHelper(v314);
                CNotification::EditModeChange((CNotification *)&v591, v315, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
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
              v340 = v578;
              v341 = (struct INamedPropertyBag *)bstrString;
              v342 = CDocument::Markup(v578);
              Text = CDoc::PersistFavoritesData((CDoc *)this, v342, v341, L"DEFAULT");
              if ( Text )
              {
                ReleaseInterface((struct IUnknown *)bstrString);
                goto LABEL_230;
              }
              *(_QWORD *)&v609.vt = bstrString;
              v609.llVal = (LONGLONG)SysAllocString(L"DOC");
              if ( v609.llVal )
              {
                v343 = CDocument::Markup(v340);
                v344 = CMarkup::Root(v343);
                CNotification::FavoritesSave((CNotification *)&v591, v344, &v609, 0);
                CDoc::BroadcastNotify((CDoc *)this, (struct CNotification *)&v591);
                ClearInterface<INamedPropertyBag *>(&v609);
                SysFreeString(v609.bstrVal);
                goto LABEL_1654;
              }
              ReleaseInterface((struct IUnknown *)bstrString);
              goto LABEL_902;
            case 6051:
              Text = 0;
              if ( a7 )
              {
                v334 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v335 = (__int16 *)this + 2861;
                if ( !v334 )
                  v335 = (__int16 *)(this + 715);
                v336 = *v335;
                a7->vt = 3;
                FontSizeMenu = GetFontSizeMenu(v336);
                v338 = HandleToLong(FontSizeMenu);
                a7->lVal = v338;
                LOBYTE(Text) = v338 == 0;
                goto LABEL_231;
              }
              goto LABEL_756;
            case 6052:
              if ( a6 )
              {
                plLbound[0] = 0;
                v332 = FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
                v333 = (__int16 *)this + 2861;
                if ( !v332 )
                  v333 = (__int16 *)(this + 715);
                Text = ShowFontSizeMenu(plLbound, *v333, a6->lVal);
                if ( !Text )
                {
                  if ( (unsigned int)(plLbound[0] - 2141) <= 4 )
                    CDoc::ExecHelper(this, v578, (struct _GUID *)&CGID_MSHTML, plLbound[0], 0, 0, 0);
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
                inserted = CDoc::InsertMenuExt((CDoc *)this, (HMENU)a6->llVal, a7->lVal);
                goto LABEL_306;
              }
              goto LABEL_756;
            }
            if ( !a7 )
              goto LABEL_756;
            v327 = this[544];
            plLbound[0] = 0;
            *(_QWORD *)&String1.vt = 0;
            if ( GetExecDocument((struct CDocument **)&String1, v327, v578) >= 0 )
              CDocument::GetDocDirection(*(CDocument **)&String1.vt, plLbound);
            v328 = plLbound[0];
            a7->vt = 3;
            DocDirMenu = CreateDocDirMenu(v328, 0);
            v330 = HandleToLong(DocDirMenu);
            a7->lVal = v330;
            v331 = -2147221247;
LABEL_1325:
            Text = v330 == 0 ? v331 : 0;
            goto LABEL_231;
          }
          if ( !a6 )
            goto LABEL_131;
          memset(&pv, 0, sizeof(pv));
          Text = CVariant::CoerceVariantArg((CVariant *)&pv, a6, 0xDu);
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
        v345 = this[103];
        if ( !v345 )
          goto LABEL_350;
        *(_QWORD *)&String1.vt = 0;
        v346 = COmWindowProxy::Document(v345);
        Text = CDocument::ExtractContent(v346, (struct IReadingModeExtractedContent **)&String1);
        if ( Text < 0 )
          goto LABEL_1588;
        v347 = *(BSTR *)&String1.vt;
        a7->vt = 13;
LABEL_909:
        a7->llVal = (LONGLONG)v347;
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
          v351 = (ReadingMode::CTextClusterDetector *)operator new[](
                                                        0x40u,
                                                        (const struct MemoryProtection::leaf_t *)0x8FC);
          if ( v351 )
          {
            v352 = (ReadingMode::CTextClusterDetector *)ReadingMode::CTextClusterDetector::CTextClusterDetector(
                                                          v351,
                                                          (struct CDoc *)this);
            v353 = v352;
            if ( v352 )
            {
              a7->lVal = ReadingMode::CTextClusterDetector::LengthOfArticleBody(v352);
              ReadingMode::CTextClusterDetector::`scalar deleting destructor'(v353, 1u);
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
          v348 = CDoc::PrimaryMarkup((CDoc *)this);
          CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v348);
          if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
          {
            v349 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
            Text = CPreloadManager::SuspendDuringPrerender(v349, 4);
          }
          CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
        }
        goto LABEL_231;
      }
      if ( !a7 || !a6 || a6->vt != 19 )
        goto LABEL_131;
      a7->vt = 19;
      v350 = CDoc::CheckBFCacheCandidacy(this, a6->cyVal.Lo, 2139, 0xFFFFFFFFLL);
LABEL_929:
      a7->lVal = v350;
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
            v369 = CDoc::InputManager((CDoc *)this);
            v370 = CInputManager::DeferredActionHandler(v369);
            CDeferredActionHandler::AgreeToVTabNavigate(v370, 0);
            goto LABEL_53;
          case 0x17BC:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v371 = CDoc::InputManager((CDoc *)this);
            v372 = CInputManager::DeferredActionHandler(v371);
            CDeferredActionHandler::OnVTabNavigateComplete(v372, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BD:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v373 = CDoc::InputManager((CDoc *)this);
            v374 = CInputManager::DeferredActionHandler(v373);
            CDeferredActionHandler::CancelSpecificVTabNavigate(v374, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17BE:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v375 = CDoc::InputManager((CDoc *)this);
            v376 = CInputManager::DeferredActionHandler(v375);
            inserted = CDeferredActionHandler::ValidateVTabNavigate(v376, a6->cyVal.Lo);
            goto LABEL_306;
          case 0x17BF:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_131;
            v377 = CDoc::InputManager((CDoc *)this);
            v378 = CInputManager::DeferredActionHandler(v377);
            CDeferredActionHandler::OnBeforeUnloadAgreed(v378, a6->cyVal.Lo);
            goto LABEL_53;
          case 0x17C0:
            if ( !a6 || a6->vt != 11 )
              goto LABEL_231;
            v379 = a6->iVal;
            Text = 0;
            if ( !v379 && ((_DWORD)this[609] & 0x200000) != 0 )
              goto LABEL_350;
            *((_DWORD *)this + 1219) &= ~0x100000u;
            v380 = 0;
            if ( v379 == -1 )
              v380 = 0x100000;
            *((_DWORD *)this + 1219) |= v380;
            goto LABEL_230;
          case 0x17C1:
            Text = -2147467259;
            v366 = CDoc::PrimaryMarkup((CDoc *)this);
            v367 = v366;
            if ( !v366 || !(unsigned int)BindCtx_ContainsObject(*((_QWORD *)v366 + 183), L"IE_FLAG_HAS_SCROLL_POSITION") )
              goto LABEL_1657;
            (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v367 + 183) + 96LL))(
              *((_QWORD *)v367 + 183),
              L"IE_FLAG_HAS_SCROLL_POSITION");
            goto LABEL_53;
          case 0x17C2:
            CDoc::ReleaseOffscreenBuffers((CDoc *)this);
            goto LABEL_53;
          case 0x17C3:
            v368 = this[876];
            if ( v368 )
            {
              (*(void (__fastcall **)(CInPlace *, __int64, __int64, __int64))(*(_QWORD *)v368 + 16LL))(
                v368,
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
            v364 = ((_BYTE)this[441] & 4) != 0;
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
            v385 = plLbound[0];
            goto LABEL_1540;
          case 0x17C7:
            if ( !a6 || a6->vt != 19 )
              goto LABEL_756;
            v386 = a6->lVal;
            plLbound[0] = 0;
            Text = ValidateD3DRequestedFeatureLevel(v386, (enum D3D_REQUESTED_FEATURE_LEVEL *)plLbound);
            if ( Text )
              goto LABEL_231;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                  + 16LL)
                      + 1132LL) = plLbound[0];
            goto LABEL_1654;
          case 0x17C8:
            if ( !a6 )
              goto LABEL_131;
            v365 = a6->vt == 19;
            goto LABEL_971;
          case 0x17C9:
            if ( !a7 )
              goto LABEL_131;
            IsEnterpriseMode = 0;
            if ( CDoc::PrimaryMarkup((CDoc *)this) )
            {
              v362 = CDoc::PrimaryMarkup((CDoc *)this);
              v363 = CMarkup::MarkupVersion(v362);
              IsEnterpriseMode = CMarkupVersion::IsEnterpriseMode(v363);
            }
            a7->vt = 11;
            v364 = !IsEnterpriseMode - 1;
LABEL_968:
            a7->iVal = v364;
            goto LABEL_941;
          case 0x17CA:
            v381 = *(CVirtualTabStorageEntry **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + (unsigned int)tls_index)
                                                           + 16LL)
                                               + 728LL);
            if ( v381 && CVirtualTabStorageEntry::WasLastNavigationViaFlipAhead(v381) )
            {
              v382 = CDoc::PrimaryMarkup((CDoc *)this);
              CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&bstrString, v382);
              if ( CDispSurface::UseRenderTarget((CDispSurface *)&bstrString) )
              {
                v383 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                CPreloadManager::SetLastNavAsFlipAheadAndIssueRequestIfApplicable(v383);
              }
              CPreloadManagerLock::~CPreloadManagerLock((CPreloadManagerLock *)&bstrString);
            }
            goto LABEL_53;
          case 0x17CB:
            if ( !a6 || a6->vt != 8 )
              goto LABEL_756;
            v356 = CDoc::PrimaryMarkup((CDoc *)this);
            if ( v356 && (*((_BYTE *)v356 + 248) = 1, (v357 = this[103]) != 0) )
            {
              CodePageCore = *((unsigned int *)v356 + 194);
              v359 = *((_DWORD *)v356 + 196);
              if ( !(_DWORD)CodePageCore )
                CodePageCore = CMarkup::GetCodePageCore(v356);
              Text = COmWindowProxy::ExecRefresh(v357, 3, CodePageCore, v359);
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
              v360 = bstrString;
              bstrString = 0;
              if ( v360 )
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)v360 + 16LL))(v360);
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
                v417 = View;
                if ( !a7 || !View || !*((_BYTE *)View + 40) )
                  goto LABEL_1657;
                a7->vt = 3;
                v418 = *(unsigned __int16 *)CViewportController::GetLogicalViewportSize(*((_QWORD *)View + 4), &String1);
                a7->lVal = v418
                         | (*(unsigned __int16 *)(CViewportController::GetLogicalViewportSize(
                                                    *((_QWORD *)v417 + 4),
                                                    &v609)
                                                + 4) << 16);
                CDispClient::AdjustContentSize((CDispClient *)&v609, v419, v420);
                CDispClient::AdjustContentSize((CDispClient *)&String1, v421, v422);
                goto LABEL_941;
              case 0x1B77:
                Text = -2147467259;
                v424 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v424 || !*((_BYTE *)v424 + 40) )
                  goto LABEL_1657;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsMobileOptimizedSite(*((CViewportController **)v424 + 4));
                goto LABEL_1161;
              case 0x1B78:
                Text = -2147467259;
                v426 = CDoc::GetView((CDoc *)this);
                if ( !a7 || !v426 || !*((_BYTE *)v426 + 40) )
                  goto LABEL_1657;
                a7->vt = 11;
                IsMobileOptimizedSite = CViewportController::IsViewportWidthOrientationDependent(*((CViewportController **)v426
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
                v415 = CVersions::MapToDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
                goto LABEL_1125;
              case 0x1B7D:
                inserted = CDoc::SetAuthoringCallback((CDoc *)this, a6);
                goto LABEL_306;
              case 0x1B7E:
                if ( !a6 || a6->vt != 9 )
                  goto LABEL_330;
                bstrString = 0;
                v432 = a6->punkVal;
                *(GUID *)&v609.vt = CLSID_CElement;
                Text = QIClassID(v432, (struct _GUID *)&v609, (void **)&bstrString);
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
                v433 = 0;
                bstrString = 0;
                if ( a6->vt == 9 )
                {
                  v434 = a6->punkVal;
                  *(GUID *)&v609.vt = CLSID_CElement;
                  Text = QIClassID(v434, (struct _GUID *)&v609, (void **)&bstrString);
                  if ( Text < 0 )
                    goto LABEL_1588;
                  v433 = (CElement *)bstrString;
                }
                if ( v433 )
                {
                  inserted = CElement::ExitFullScreen(v433);
                }
                else
                {
                  v435 = CDoc::FullScreenState((CDoc *)this);
                  inserted = CFullScreenState::ExitFullScreen(v435, 0);
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
                v427 = a6->parray;
                plLbound[0] = 0;
                SafeArrayGetUBound(v427, 1u, plLbound);
                if ( plLbound[0] != 2 )
                  goto LABEL_1657;
                v428 = a6->parray;
                *(_QWORD *)&String1.vt = 0;
                Text = SafeArrayAccessData(v428, (void **)&String1);
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
                v423 = CDoc::GetView((CDoc *)this);
                if ( !v423 || !*((_BYTE *)v423 + 40) )
                  goto LABEL_1657;
                CViewportController::SetUIOrientation(*((CViewportController **)v423 + 4), a6->iVal == 0xFFFF);
                goto LABEL_53;
              case 0x1B83:
                Text = -2147024809;
                if ( !a6 || a6->vt != 11 )
                  goto LABEL_1657;
                v97 = CDoc::ForcePaint((CDoc *)this, a6->iVal == 0xFFFF, 0);
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
                v429 = CDoc::GetView((CDoc *)this);
                if ( !v429 )
                  goto LABEL_1657;
                CView::AllowGrippersForHost(v429, a6->iVal == 0);
                goto LABEL_53;
              case 0x1B87:
                Text = -2147024809;
                if ( !a6 )
                  goto LABEL_1657;
                if ( a6->vt != 8 )
                  goto LABEL_1657;
                Text = -2147418113;
                if ( !v578 )
                  goto LABEL_1657;
                inserted = CDoc::HandleFlashServicingRefresh((CDoc *)this, v578, a6->bstrVal);
                goto LABEL_306;
              case 0x1B88:
                Text = -2147024809;
                if ( !a7 )
                  goto LABEL_1657;
                a7->vt = 11;
                v430 = CDoc::FullScreenState((CDoc *)this);
                IsMobileOptimizedSite = CFullScreenState::IsInFullScreen(v430);
LABEL_1161:
                v431 = !IsMobileOptimizedSite;
                goto LABEL_1498;
              default:
                goto LABEL_231;
            }
            goto LABEL_306;
          }
          if ( a6 )
          {
            v365 = a6->vt == 11;
LABEL_971:
            if ( v365 )
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
                v393 = 0;
                if ( a6 && a6->vt == 3 )
                  v393 = a6->lVal;
                CDoc::SubmitForAntiPhishProcessing(this, 0, v393, 0);
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
          v394 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( !v394 )
            goto LABEL_350;
          *((_BYTE *)v394 + 97) |= 8u;
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
                Text = CDoc::ExecHelper(this, v578, (struct _GUID *)&CGID_MSHTML, Lo + 2141, 2u, 0, 0);
                if ( Text )
                  goto LABEL_231;
              }
              if ( !a7 )
                goto LABEL_53;
              v365 = !FeatureControlHelper::PrivateFontSetting((FeatureControlHelper *)&g_FeatureControlHelper);
              v388 = (CInPlace **)((char *)this + 5722);
              if ( v365 )
                v388 = this + 715;
              DebugState = *(__int16 *)v388;
              a7->vt = 3;
LABEL_1032:
              a7->lVal = DebugState;
              goto LABEL_53;
          }
          v391 = CDocument::Markup(v578);
          CDoc::WaitForRecalc((CDoc *)this, v391);
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
            CDoc::CompatViewRefresh((CDoc *)this, 0);
            goto LABEL_53;
          case 7021:
            if ( a6 && a6->vt == 11 )
            {
              v395 = 0;
              if ( a6->iVal == -1 )
                v395 = 512;
              *((_DWORD *)this + 1214) = (_DWORD)this[607] & 0xFFFFFDFF | v395;
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
          goto LABEL_1588;
        if ( !a7 )
          goto LABEL_756;
        VariantInit(a7);
        a7->vt = 8;
        v347 = SysAllocString(Data);
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
      v398 = rgIndices[0];
      v20 = plLbound[0];
      if ( (rgIndices[0] & 1) != 0 )
      {
        Text = 0;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v399 = ppvData;
          *(_WORD *)ppvData = 21;
          v399[1] = *((_QWORD *)CDoc::PrimaryMarkup((CDoc *)this) + 17);
        }
        v398 = rgIndices[0];
      }
      if ( (v398 & 2) != 0 )
      {
        v400 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( v400 )
        {
          v401 = COptionsHolder::SecurityContext(v400);
          *(_QWORD *)&v609.vt = v401;
          if ( v401 )
          {
            *(_QWORD *)&String1.vt = CHtmCtx::GetReferrerUrl(v401);
            OriginalUrlContext = CHtmCtx::GetOriginalUrlContext(*(CHtmCtx **)&v609.vt);
            v403 = *(const OLECHAR **)&String1.vt;
            v404 = -1;
            *(_QWORD *)&v609.vt = OriginalUrlContext;
            if ( *(_QWORD *)&String1.vt )
            {
              v405 = -1;
              do
                ++v405;
              while ( *(_WORD *)(*(_QWORD *)&String1.vt + 2 * v405) );
            }
            else
            {
              v405 = 0;
            }
            if ( OriginalUrlContext )
            {
              do
                ++v404;
              while ( OriginalUrlContext[v404] );
            }
            else
            {
              v404 = 0;
            }
            if ( v405 )
            {
              if ( v404 > v405 )
              {
                v406 = wcsncmp_0(*(const wchar_t **)&String1.vt, OriginalUrlContext, v405);
                v403 = *(const OLECHAR **)&String1.vt;
                if ( !v406 )
                  v403 = *(const OLECHAR **)&v609.vt;
              }
            }
            v407 = SysAllocString(v403);
            v25 = 1;
            if ( v407 )
            {
              v408 = ppvData;
              Text = 0;
              *((_WORD *)ppvData + 12) = 8;
              v408[4] = v407;
            }
          }
        }
      }
      v409 = rgIndices[0];
      if ( (rgIndices[0] & 4) != 0 )
      {
        v410 = ppvData;
        *(_QWORD *)&v609.vt = ppvData;
        *((_WORD *)ppvData + 24) = 21;
        if ( this[781] )
        {
          v411 = CHTMLDlg::SecurityContext(this[781]);
          v409 = rgIndices[0];
          *(_QWORD *)(*(_QWORD *)&v609.vt + 56LL) = v411;
        }
        else
        {
          v410[7] = 0;
        }
      }
      if ( (v409 & 8) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractVideoData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text < 0 )
        {
LABEL_1117:
          CMultimediaLog::StopUpdate((CMultimediaLog *)(this + 741));
          v414 = (SAFEARRAY *)pszSubKey;
          goto LABEL_1150;
        }
        v409 = rgIndices[0];
        if ( bstrString )
        {
          v412 = ppvData;
          Text = 0;
          *((_WORD *)ppvData + 36) = 8;
          v412[10] = bstrString;
        }
      }
      if ( (v409 & 0x10) != 0 )
      {
        bstrString = 0;
        Text = CMultimediaLog::ExtractImageData((CMultimediaLog *)(this + 741), &bstrString);
        if ( Text >= 0 )
        {
          if ( bstrString )
          {
            v413 = ppvData;
            Text = 0;
            *((_WORD *)ppvData + 48) = 8;
            v413[13] = bstrString;
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
              Text = CDoc::SerializePrintCommands((CDoc *)this, v578, a6, a7);
              v452 = Text == 0;
              goto LABEL_1653;
            }
            goto LABEL_231;
          }
          if ( plLbound[0] == 8000 )
          {
            if ( !a6 || a6->vt == 11 )
            {
              v450 = (unsigned int)tls_index;
              if ( a7 )
              {
                ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 11;
                a7->iVal = -(*(_BYTE *)(*(_QWORD *)(ThreadLocalStoragePointer[v450] + 16LL) + 1128LL) != 0);
              }
              if ( a6 )
                *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v450) + 16LL) + 1128LL) = a6->iVal == 0xFFFF;
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
                v445 = CDocument::Window(v578);
                v446 = v445;
                if ( v445 && (unsigned int)CWindow::IsPrimaryWindow(v445) )
                {
                  v447 = CDeviceRotationRate::SecurityContext(v446);
                  if ( v447 )
                  {
                    v448 = CMarkup::Window(v447);
                    CEventMgr::QueueAsyncEvent(
                      &s_propdescCIE9EventListorientationchange,
                      v448,
                      v447,
                      COmWindowProxy::Fire_orientationchange,
                      0,
                      AsyncEventMerge_Always,
                      0);
                  }
                  v449 = *((_QWORD *)v446 + 55);
                  if ( v449 )
                    CEventMgr::QueueAsyncEvent(
                      &s_propdescCIE9EventListMSOrientationChange,
                      v449,
                      v447,
                      CScreen::Fire_orientationchange,
                      0,
                      AsyncEventMerge_Always,
                      0);
                }
                goto LABEL_1654;
              case 8004:
                inserted = CDoc::GetContentLang((CDoc *)this, a7);
                break;
              case 8005:
                v444 = this[732];
                if ( v444 )
                {
                  CAPProcessor::Passivate(v444);
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
            v438 = RootTracker;
            if ( RootTracker )
            {
              Text = CRootTracker::EnsureInitialized(RootTracker);
              if ( Text < 0 )
                goto LABEL_1588;
              CDXRelationship<CDXTexture>::CDXRelationship<CDXTexture>(&bstrString);
              v439 = CDCompLayerManager::UseRootLayer(v438);
              v440 = **(__int64 (__fastcall ***)(struct IDispLayer *, GUID *, struct CHtmParseCtx *))v439;
              v441 = (CHtmRootParseCtxRouter *)TSmartPointer<ID3D11Device>::operator&(&bstrString);
              HpxEmbed = CHtmRootParseCtxRouter::GetHpxEmbed(v441);
              Text = v440(v439, &GUID_cc1a2bea_d5e9_4161_9da7_9042b37549a7, HpxEmbed);
              if ( Text >= 0 )
              {
                v443 = CDispSurface::UseRenderTarget((CDispSurface *)&bstrString);
                Text = (*(__int64 (__fastcall **)(struct IDispRenderTarget *, __int64, struct tagVARIANT *))(*(_QWORD *)v443 + 24LL))(
                         v443,
                         3,
                         a6);
              }
              TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&bstrString);
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
        v365 = !CView::HasStaticViewportSizeApplied((CView *)(this + 283));
        v436 = (int *)(this + 481);
        if ( v365 )
          v436 = (int *)this + 1019;
        NormZoomPercent = *v436;
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
              v465 = a6->parray;
              if ( v465 )
              {
                pvData = 0;
                pszSubKey = 0;
                *(_QWORD *)&String1.vt = 0;
                if ( !SafeArrayGetElement(v465, (LONG *)&pvData, &pszSubKey) )
                {
                  v466 = a6->parray;
                  ++pvData;
                  if ( !SafeArrayGetElement(v466, (LONG *)&pvData, &String1) )
                    CDoc::ReplacePrintHandles((CDoc *)this, (void *)pszSubKey, *(void **)&String1.vt);
                }
                goto LABEL_53;
              }
            }
            goto LABEL_131;
          }
          v330 = InternetSetOptionW(0, 0x2Au, 0, 0);
          v331 = -2147467259;
          goto LABEL_1325;
        }
        if ( g_fInHtmlHelp )
        {
          *((_DWORD *)this + 1217) |= 0x400u;
          v467 = CDoc::PrimaryMarkup((CDoc *)this);
          if ( v467 )
          {
            if ( (*((_DWORD *)v467 + 187) & 0x4000000) != 0 )
            {
              v468 = (COmWindowProxy *)*((_QWORD *)v467 + 44);
              if ( v468 )
                COmWindowProxy::Fire_onafterprint(v468);
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
                  CDispClient::AdjustContentSize((CDispClient *)&bstrString, v463, v464);
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
                CDoc::HandleWebStorageEvent((CDoc *)this, v578, a6->cyVal.Lo);
                goto LABEL_1654;
              }
              goto LABEL_131;
            case 8008:
              Text = 0;
              if ( a6 && a6->vt == 19 )
              {
                v459 = this[126];
                if ( v459 )
                {
                  v460 = a6->lVal;
                  if ( *((_DWORD *)v459 + 384) == v460 )
                    goto LABEL_1654;
                  *((_DWORD *)v459 + 384) = v460;
                  v461 = CDocument::Markup(v578);
                  TextScalingSettings = CTextScalingSettings::GetTextScalingSettings(v461);
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
              v457 = CDoc::GetView((CDoc *)this);
              if ( v457 )
              {
                if ( *((_BYTE *)v457 + 40) )
                {
                  v458 = (CViewportController *)*((_QWORD *)v457 + 4);
                  if ( v458 )
                  {
                    Text = 0;
                    CViewportController::SetAccessibleZoom(v458, a6->iVal != 0);
                    goto LABEL_1654;
                  }
                }
              }
              goto LABEL_350;
            case 8010:
              v455 = NtCurrentTeb()->ThreadLocalStoragePointer;
              pvData = 0;
              bstrString = (BSTR)v455[(unsigned int)tls_index];
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
            v453 = CDoc::GetView((CDoc *)this);
            if ( v453 )
            {
              v454 = (CViewportController *)*((_QWORD *)v453 + 4);
              if ( v454 )
              {
                Text = 0;
                CViewportController::SetIsReadingView(v454, a6->iVal != 0);
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
            v469 = (unsigned int (__fastcall ***)(_QWORD, GUID *, void **, __int64))a6->llVal;
            if ( v469 )
            {
              ppvData = 0;
              if ( !(**v469)(v469, &IID_IHTMLWindow2, &ppvData, v26) )
              {
                v470 = this[642];
                bstrString = 0;
                if ( !(**(unsigned int (__fastcall ***)(CInPlace *, GUID *, BSTR *))v470)(
                        v470,
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
        v532 = CDocument::Markup(v578);
        v533 = 0;
        if ( a6 && a6->vt == 3 )
          v533 = a6->lVal;
        Text = 0;
        if ( !v532 )
          goto LABEL_1654;
        v534 = CMarkup::GetWindowedMarkupContext(v532);
        if ( !v534 )
          goto LABEL_1654;
        RootMarkup = CMarkup::GetRootMarkup(v534, 0);
        if ( !RootMarkup )
          goto LABEL_1654;
        *((_DWORD *)RootMarkup + 197) |= v533;
        *((_DWORD *)this + 1224) &= ~v533;
        inserted = CDoc::NotifyPageActionBlockedState((CDoc *)this, 1, 0);
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
              if ( (unsigned int)IsEqualGUID(pszSubKey + 416, &GUID_NULL) )
                goto LABEL_1657;
              *(_QWORD *)&String1.vt = 3;
              v490 = SafeArrayCreate(0xCu, 1u, (SAFEARRAYBOUND *)&String1);
              v491 = v490;
              if ( v490 )
              {
                Text = SafeArrayAccessData(v490, &ppvData);
                if ( Text >= 0 )
                {
                  bstrString = 0;
                  Text = StringFromCLSID((const IID *const)pszSubKey + 52, &bstrString);
                  if ( Text >= 0 )
                  {
                    *(_WORD *)ppvData = 8;
                    v492 = SysAllocString(bstrString);
                    v493 = pszSubKey;
                    *((_QWORD *)ppvData + 1) = v492;
                    *((_WORD *)ppvData + 12) = 3;
                    *((_DWORD *)ppvData + 8) = *((_DWORD *)v493 + 212);
                    *((_WORD *)ppvData + 24) = 3;
                    *((_DWORD *)ppvData + 14) = *((_DWORD *)v493 + 213);
                    CoTaskMemFree(bstrString);
                  }
                  SafeArrayUnaccessData(v491);
                  if ( Text >= 0 )
                  {
                    VariantInit(a7);
                    a7->vt = 8204;
                    a7->llVal = (LONGLONG)v491;
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
              *(_OWORD *)&v609.vt = 0;
              memset(&pvarg, 0, sizeof(pvarg));
              memset(&String1, 0, sizeof(String1));
              memset(&pv, 0, sizeof(pv));
              VariantInit(&pvarg);
              VariantInit(&String1);
              VariantInit(&pv);
              v487 = a6->parray;
              rgIndices[0] = 0;
              Text = SafeArrayGetElement(v487, rgIndices, &pvarg);
              if ( Text >= 0 && pvarg.vt == 8 )
              {
                Text = CLSIDFromString(pvarg.bstrVal, (LPCLSID)&v609);
                if ( !Text )
                {
                  v488 = a6->parray;
                  rgIndices[0] = 1;
                  Text = SafeArrayGetElement(v488, rgIndices, &String1);
                  if ( Text >= 0 && String1.vt == 19 )
                  {
                    v489 = a6->parray;
                    rgIndices[0] = 2;
                    Text = SafeArrayGetElement(v489, rgIndices, &pv);
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
              v415 = CVersions::MapToNearestDocumentMode(a6->cyVal.Lo, 32, v19, 0xFFFFFFFFLL);
              if ( v415 < 0 )
                goto LABEL_1657;
LABEL_1125:
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 16LL)
                        + 740LL) = v415;
              goto LABEL_53;
            case 15009:
              Text = -2147024809;
              if ( !a6 || a6->vt != 3 || !a7 )
                goto LABEL_1657;
              VariantInit(a7);
              v479 = a6->lVal;
              if ( v479 )
              {
                v480 = v479 - 1;
                if ( v480 )
                {
                  if ( v480 != 1 )
                    goto LABEL_1657;
                  v481 = CDocument::Markup(v578);
                  a7->vt = 3;
                  v482 = CMarkup::MarkupVersion(v481);
                  v350 = CMarkupVersion::DocumentMode(v482);
                }
                else
                {
                  v483 = CDocument::Markup(v578);
                  a7->vt = 3;
                  v484 = CMarkup::MarkupVersion(v483);
                  v350 = CMarkupVersion::NativeDocumentMode(v484, 0, 0);
                }
              }
              else
              {
                v485 = (unsigned int)tls_index;
                v486 = NtCurrentTeb()->ThreadLocalStoragePointer;
                a7->vt = 3;
                v350 = *(_DWORD *)(*(_QWORD *)(v486[v485] + 16LL) + 740LL);
              }
              goto LABEL_929;
          }
          ppvData = GetThreadStateUI();
          *(_QWORD *)&v609.vt = CDoc::PrimaryMarkup((CDoc *)this);
          v471 = *(struct CMarkup **)&v609.vt;
          if ( !a6 )
          {
            Text = -2147024809;
            *(_QWORD *)&v609.vt = (char *)ppvData + 832;
            if ( (unsigned int)IsEqualGUID((char *)ppvData + 832, &GUID_NULL) )
              goto LABEL_1657;
            Text = 0;
            *(GUID *)*(_QWORD *)&v609.vt = GUID_NULL;
            *((_QWORD *)ppvData + 106) = 0;
            if ( !v471 || !(unsigned __int8)CMarkup::IsVersionedChangeEnabled(v471, 100000) )
            {
LABEL_1654:
              if ( !v9 )
                goto LABEL_1656;
              goto LABEL_1655;
            }
            CWorkerManager::StartProfilingAllWorkers(v471, 0);
            goto LABEL_231;
          }
          if ( a6->vt != 8204 )
            goto LABEL_231;
          v472 = a6->parray;
          if ( !v472 )
            goto LABEL_231;
          bstrString = 0;
          Text = SafeArrayAccessData(v472, (void **)&bstrString);
          if ( Text < 0 )
            goto LABEL_1588;
          v473 = a6->parray;
          pvData = 0;
          Text = SafeArrayGetUBound(v473, 1u, (LONG *)&pvData);
          if ( Text >= 0 )
          {
            v474 = pvData + 1;
            pvData = v474;
            if ( v474 == 3 )
            {
              if ( *bstrString == 8 && bstrString[12] == 3 && bstrString[24] == (_WORD)v474 )
              {
                v475 = ppvData;
                v476 = CLSIDFromString(*((LPCOLESTR *)bstrString + 1), (LPCLSID)ppvData + 52);
                v477 = bstrString;
                Text = v476;
                v475[212] = *((_DWORD *)bstrString + 8);
                v475[213] = *((_DWORD *)v477 + 14);
                if ( !v476 )
                {
                  v478 = *(struct CMarkup **)&v609.vt;
                  if ( *(_QWORD *)&v609.vt )
                  {
                    if ( (unsigned __int8)CMarkup::IsVersionedChangeEnabled(*(_QWORD *)&v609.vt, 100000) )
                      CWorkerManager::StartProfilingAllWorkers(v478, 1);
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
          v414 = a6->parray;
LABEL_1150:
          SafeArrayUnaccessData(v414);
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
            v500 = (__int64 (__fastcall ***)(_QWORD, GUID *, VARIANTARG *, __int64))a6->llVal;
            if ( !v500 )
              goto LABEL_131;
            *(_QWORD *)&String1.vt = 0;
            Text = (**v500)(v500, &IID_INavigateEventSink, &String1, 0xFFFFFFFFLL);
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
            inserted = CDoc::FireOnPopStateEvent((CDoc *)this, v578);
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
        v494 = CDoc::PrimaryMarkup((CDoc *)this);
        if ( !a7 || !a6 || a6->vt != 3 )
          goto LABEL_1657;
        a7->vt = 11;
        Text = 0;
        v495 = a6->lVal;
        if ( v495 )
        {
          if ( v495 != 1 )
            goto LABEL_630;
          if ( !v494 )
          {
            v498 = 0;
            goto LABEL_1427;
          }
          v496 = CMarkup::MarkupVersion(v494);
          IsNativeQuirksLayoutEmulation = CMarkupVersion::IsNativeQuirksLayoutEmulation(v496);
        }
        else
        {
          if ( !v494 )
          {
            v498 = -(*(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                            + (unsigned int)tls_index)
                                          + 16LL)
                              + 587LL) != 0);
            goto LABEL_1427;
          }
          v499 = CMarkup::MarkupVersion(v494);
          IsNativeQuirksLayoutEmulation = CDCompVideoBackedLayer::IsRenderRequired(v499);
        }
        v498 = !IsNativeQuirksLayoutEmulation - 1;
LABEL_1427:
        a7->iVal = v498;
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
              v531 = a6->lVal;
              if ( !*((_BYTE *)this + 1016) || CColorValue::GetIntoABGR((CColorValue *)((char *)this + 1020)) != v531 )
              {
                *((_BYTE *)this + 1016) = 1;
                Text = 0;
                if ( !CServer::IsWebPlatformWindowless((CServer *)this) )
                  v531 |= 0xFF000000;
                CColorValue::SetFromABGR((CColorValue *)((char *)this + 1020), v531);
                CDoc::ForceRelayout((CDoc *)this, 1);
                CDoc::SignalDefaultBackgroundColorChanged((CDoc *)this, v531);
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
            v529 = (int)(float)(CColorValue::GetAlpha((CColorValue *)((char *)this + 1020)) * 255.0);
            v385 = ((unsigned __int8)v529 << 24)
                 | CColorValue::GetColorRef((CColorValue *)((char *)this + 1020)) & 0xFFFFFF;
          }
          else
          {
            v530 = (OLE_COLOR *)this[126];
            if ( !v530 )
            {
              a7->lVal = -16777216;
              goto LABEL_231;
            }
            plLbound[0] = 0;
            Text = OleTranslateColor(*v530, 0, (COLORREF *)plLbound);
            if ( Text )
              goto LABEL_231;
            v385 = plLbound[0] | 0xFF000000;
          }
LABEL_1540:
          a7->lVal = v385;
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
            v515 = 1;
          }
          else
          {
            if ( a5 != 103 )
              goto LABEL_1657;
            v515 = 0;
          }
          inserted = CDoc::SetGeolocationUserConsent((CDoc *)this, a6->bstrVal, v515);
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
                v501 = 0;
              }
              else
              {
                if ( a6->vt != 8 )
                  goto LABEL_1657;
                v501 = a6->bstrVal;
              }
              inserted = CDoc::SetExtraHeaders((CDoc *)this, v501);
              break;
            default:
              goto LABEL_231;
          }
          goto LABEL_306;
        }
        if ( !a7 )
          goto LABEL_131;
        v513 = CDocument::GetWindowedMarkupContext(v578);
        IsActiveXFilteringEnabled = CMarkup::IsActiveXFilteringEnabled(v513);
        a7->vt = 11;
        v431 = IsActiveXFilteringEnabled != 1;
LABEL_1498:
        a7->iVal = v431 - 1;
        goto LABEL_941;
      }
      if ( !a6 || !a7 )
        goto LABEL_231;
      if ( a6->vt != 13 )
        goto LABEL_230;
      v516 = a6->punkVal;
      if ( !v516 )
        goto LABEL_230;
      *(_QWORD *)plLbound = 0;
      *(GUID *)&v609.vt = CLSID_CElement;
      Text = QIClassID(v516, (struct _GUID *)&v609, (void **)plLbound);
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
      CRect::CRect((CRect *)&v609);
      CRect::CRect((CRect *)&String1);
      Text = CElement::GetBoundingRect(*(CElement **)plLbound, (struct CRectF *)&String1, 0x4001u, 0);
      if ( Text >= 0
        && ((unsigned int)CElement::IsDeviceFixed(*(CElement **)plLbound)
         || (unsigned int)CElement::IsAncestorPositionFixed(*(CElement **)plLbound, 1))
        && CElement::IsStandardsMode(*(CElement **)plLbound) )
      {
        v517 = CElement::LayoutServices(*(CElement **)plLbound);
        if ( v517 )
        {
          v518 = *(_QWORD *)v517;
          bstrString = 0;
          LOBYTE(pvt[0]) = 0;
          (*(void (__fastcall **)(struct ILayoutServices *, _QWORD, BSTR *, VARTYPE *))(v518 + 432))(
            v517,
            *(_QWORD *)plLbound,
            &bstrString,
            pvt);
          for ( j = bstrString; j; bstrString = j )
          {
            v520 = CDispNode::NodeReader((CDispNode *)j);
            if ( CDispNodeReader::IsTopLevelScroller(v520) )
            {
              v521 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispScroller::GetTotalZoomFactor(v521);
              v522 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)bstrString);
              CDispTopLevelScroller::BaseOpticalZoomFactor(v522);
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
        v525 = SafeArrayCreateVector(3u, 0, 4u);
        a7->llVal = (LONGLONG)v525;
        if ( v525 )
        {
          *(_DWORD *)pvt = 0;
          SafeArrayPutElement(v525, (LONG *)pvt, &v609);
          v526 = a7->parray;
          v25 = 1;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v526, (LONG *)pvt, &v609.decVal.Hi32);
          v527 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v527, (LONG *)pvt, &v609.decVal.8);
          v528 = a7->parray;
          ++*(_DWORD *)pvt;
          SafeArrayPutElement(v528, (LONG *)pvt, (char *)&v609.decVal.Lo64 + 4);
LABEL_1529:
          CDispClient::AdjustContentSize((CDispClient *)&String1, v523, v524);
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
        v544 = 0;
        if ( a6 )
        {
          if ( a6->vt == 13 )
          {
            v545 = (void (__fastcall ***)(_QWORD, GUID *, struct CHtmParseCtx *))a6->llVal;
            if ( v545 )
            {
              v546 = **v545;
              v547 = CHtmRootParseCtxRouter::GetHpxEmbed((CHtmRootParseCtxRouter *)&bstrString);
              v546(v545, &GUID_0000000e_0000_0000_c000_000000000046, v547);
              v544 = (struct IBindCtx *)bstrString;
            }
          }
          v25 = 1;
        }
        v548 = CFlipAheadManager::InvokeCachedTarget((CFlipAheadManager *)(this + 836), v544);
        v55 = bstrString;
        Text = v548;
LABEL_959:
        if ( !v55 )
          goto LABEL_231;
        goto LABEL_111;
      case 15202:
        v543 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v538 = v543;
        if ( v543 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v543) == 2 )
            goto LABEL_1654;
          plLbound[0] = CMarkup::GetDebugState(v538);
          v539 = plLbound[0];
          CMarkup::SetDebugState(v538, 2);
          v540 = 2;
          goto LABEL_1570;
        }
        break;
      case 15203:
        v542 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v538 = v542;
        if ( v542 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v542) != 2 )
            goto LABEL_1654;
          plLbound[0] = CMarkup::GetDebugState(v538);
          CMarkup::SetDebugState(v538, 1);
          Text = CDoc::DynamicDetachDebugger((CDoc *)this);
          if ( Text >= 0 )
            goto LABEL_1610;
          v541 = (unsigned int)plLbound[0];
          goto LABEL_1572;
        }
        break;
      case 15204:
        v537 = CDoc::PrimaryMarkup((CDoc *)this);
        Text = 0;
        v538 = v537;
        if ( v537 )
        {
          if ( (unsigned int)CMarkup::GetDebugState(v537) )
            goto LABEL_1654;
          plLbound[0] = CMarkup::GetDebugState(v538);
          v539 = plLbound[0];
          CMarkup::SetDebugState(v538, 1);
          v540 = 1;
LABEL_1570:
          Text = CDoc::DynamicAttachDebugger(this, v539, v540);
          if ( Text >= 0 )
            goto LABEL_1610;
          v541 = (unsigned int)plLbound[0];
LABEL_1572:
          CMarkup::SetDebugState(v538, v541);
          goto LABEL_1588;
        }
        break;
      case 15205:
        VariantInit(a7);
        a7->vt = 3;
        if ( CDoc::PrimaryMarkup((CDoc *)this) )
        {
          v536 = CDoc::PrimaryMarkup((CDoc *)this);
          DebugState = CMarkup::GetDebugState(v536);
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
