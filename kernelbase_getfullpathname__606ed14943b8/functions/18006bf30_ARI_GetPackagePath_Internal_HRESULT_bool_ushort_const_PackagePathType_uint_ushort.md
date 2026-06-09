# ARI::GetPackagePath_Internal_HRESULT(bool,ushort const *,PackagePathType,uint *,ushort *)

- ea: `0x18006bf30`
- end: `0x18006d440`
- name: `?GetPackagePath_Internal_HRESULT@ARI@@YAJ_NPEBGW4PackagePathType@@PEAIPEAG@Z`
- size: `5392`
- prototype: `int __high(bool, const unsigned __int16 *, enum PackagePathType, unsigned int *, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x18006b820`
- `0x18006ba60`
- `0x18006bac0`
- `0x18006bb14`
- `0x18006be40`
- `0x18006bea0`
- `0x18006befc`

## callees

- `0x180008cb0`
- `0x1800090b0`
- `0x180009e40`
- `0x18000a2b0`
- `0x18000a690`
- `0x18000a9c4`
- `0x18000b014`
- `0x18000cda0`
- `0x18001b080`
- `0x18005997c`
- `0x18005aa70`
- `0x18005b2c4`
- `0x18006a430`
- `0x18006bf30`
- `0x1800d0c28`
- `0x1801369c9`
- `0x18015b710`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006c43e`
- `ntdll!RtlFreeHeap` at `0x18006d222`
- `ntdll!RtlFreeHeap` at `0x18006d2df`
- `ntdll!RtlFreeHeap` at `0x18006d36f`
- `ntdll!RtlFreeHeap` at `0x18006c43e`
- `ntdll!RtlFreeHeap` at `0x18006d222`
- `ntdll!RtlFreeHeap` at `0x18006d2df`
- `ntdll!RtlFreeHeap` at `0x18006d36f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006c7eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006ccec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006ced9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006d0ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006c7eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006ccec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006ced9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18006d0ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006c629`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006cb2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006c629`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006cb2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18006c4e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18006c9e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18006c4e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18006c9e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18006bf96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18006bf96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c50d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c653`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c731`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c7aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c88e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006ca12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cb58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cc36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cc66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006ccaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cd8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cf7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cfd8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006d165`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006d1c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c50d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c653`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c731`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c7aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006c88e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006ca12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cb58`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cc36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cc66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006ccaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cd8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cf7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006cfd8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006d165`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006d1c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006bfc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006c35c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d246`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d303`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d393`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d3d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006bfc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006c35c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d246`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d303`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d393`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006d3d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c338`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c3b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c41f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c716`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c78f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c838`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c94e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cc1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cc94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cd36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cf29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d10d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d205`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d298`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d2c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d352`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c338`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c3b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c41f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c716`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c78f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c838`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006c94e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cc1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cc94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cd36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006cf29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d10d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d205`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d298`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d2c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18006d352`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006c6b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006cbb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006c6b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006cbb7`

## string_xrefs

- `0x18006c466`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c494`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c53f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c56e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c5e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c685`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c6ea`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c853`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c96d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c999`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006ca44`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006ca73`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006caeb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006cb8a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006cbef`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006cd51`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006ce28`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006ce54`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006ce95`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006cf44`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006d004`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006d02f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006d072`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006d128`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18006c524`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006c66a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006c6cf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006c804`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006ca29`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006cb6f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006cbd4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006cd05`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006cef2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006d0d3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006bfd7`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`
- `0x18006c120`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c150`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c1ba`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c1fe`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c239`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c266`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c314`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c397`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c3fe`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c8b8`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006c92c`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006cdb6`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006cfa9`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006d18f`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006d275`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006d329`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18006d3b7`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`

## pseudocode

```c
__int64 __fastcall ARI::GetPackagePath_Internal_HRESULT(
        char a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned int *a4,
        unsigned __int16 *a5)
{
  PVOID v8; // r14
  int v10; // ebx
  unsigned __int16 *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r10
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax
  void *v20; // rdx
  int v21; // eax
  int v22; // eax
  const unsigned __int16 *v23; // rbx
  unsigned __int16 *v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // rcx
  __int64 v29; // rcx
  int EffectiveLocationByUserAndPackage; // eax
  unsigned __int16 *v31; // rcx
  PVOID v32; // r8
  __int64 v33; // rdx
  unsigned __int64 v34; // rdi
  unsigned __int16 *v35; // rcx
  int v36; // eax
  unsigned __int16 *v37; // rcx
  bool v38; // si
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  void *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  PVOID v45; // rcx
  int Field_String; // eax
  unsigned __int16 *v47; // rcx
  void *v48; // rcx
  unsigned __int16 *v49; // rcx
  __int64 v50; // rdx
  unsigned __int64 v51; // rdi
  unsigned __int16 *v52; // rcx
  int v53; // eax
  unsigned __int16 *v54; // rcx
  bool v55; // si
  int v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rcx
  void *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  int v62; // eax
  unsigned __int16 *v63; // rcx
  void *v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rdi
  int v67; // eax
  unsigned __int64 v68; // r9
  __int64 v69; // rdx
  __int64 v70; // rcx
  int v71; // eax
  unsigned __int16 *v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // rdi
  int v76; // eax
  unsigned __int64 v77; // r9
  __int64 v78; // rdx
  int v79; // eax
  unsigned __int16 *v80; // rcx
  PVOID v81; // rcx
  __int64 v82; // rax
  unsigned __int64 v83; // rcx
  unsigned int v84; // eax
  unsigned __int16 *v85; // rcx
  __int64 v86; // rcx
  int v87; // eax
  int v88; // eax
  unsigned __int16 *v89; // rcx
  unsigned __int16 *v90; // rcx
  __int64 v91; // rcx
  unsigned __int16 *v92; // rcx
  bool *v93; // [rsp+20h] [rbp-E0h]
  int v94; // [rsp+20h] [rbp-E0h]
  int v95; // [rsp+20h] [rbp-E0h]
  int v96; // [rsp+20h] [rbp-E0h]
  int v97; // [rsp+20h] [rbp-E0h]
  int v98; // [rsp+20h] [rbp-E0h]
  int v99; // [rsp+20h] [rbp-E0h]
  int v100; // [rsp+20h] [rbp-E0h]
  int v101; // [rsp+20h] [rbp-E0h]
  int v102; // [rsp+20h] [rbp-E0h]
  int v103; // [rsp+20h] [rbp-E0h]
  int v104; // [rsp+20h] [rbp-E0h]
  int v105; // [rsp+20h] [rbp-E0h]
  int v106; // [rsp+20h] [rbp-E0h]
  int v107; // [rsp+20h] [rbp-E0h]
  char *v108; // [rsp+28h] [rbp-D8h]
  bool v109; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v110; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v111; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v112; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v114; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v115; // [rsp+70h] [rbp-90h] BYREF
  char v116; // [rsp+78h] [rbp-88h]
  void *v117; // [rsp+80h] [rbp-80h] BYREF
  void *v118; // [rsp+88h] [rbp-78h] BYREF
  void *v119; // [rsp+90h] [rbp-70h] BYREF
  __int64 v120; // [rsp+98h] [rbp-68h] BYREF
  __int128 v121; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v122[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v123; // [rsp+C0h] [rbp-40h] BYREF
  char *v124[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v125; // [rsp+E0h] [rbp-20h]
  __int64 v126; // [rsp+E8h] [rbp-18h]
  int v127; // [rsp+F0h] [rbp-10h]
  int v128; // [rsp+F4h] [rbp-Ch]
  __int64 v129; // [rsp+F8h] [rbp-8h]
  __int64 v130; // [rsp+100h] [rbp+0h]
  const unsigned __int16 *v131; // [rsp+108h] [rbp+8h]
  __int128 v132; // [rsp+110h] [rbp+10h]
  int v133; // [rsp+120h] [rbp+20h]
  __int64 v134; // [rsp+128h] [rbp+28h]
  __int64 v135; // [rsp+130h] [rbp+30h]
  unsigned __int64 v136; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v137; // [rsp+148h] [rbp+48h] BYREF
  __int64 v138; // [rsp+150h] [rbp+50h] BYREF
  __int64 v139; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 **v140; // [rsp+160h] [rbp+60h]
  unsigned __int16 *v141; // [rsp+168h] [rbp+68h] BYREF
  char v142; // [rsp+170h] [rbp+70h]
  unsigned __int16 **v143; // [rsp+178h] [rbp+78h]
  unsigned __int16 *v144; // [rsp+180h] [rbp+80h] BYREF
  char v145; // [rsp+188h] [rbp+88h]
  unsigned __int16 **v146; // [rsp+190h] [rbp+90h]
  unsigned __int16 *v147; // [rsp+198h] [rbp+98h] BYREF
  char v148; // [rsp+1A0h] [rbp+A0h]
  __int64 v149; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v150[512]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v151; // [rsp+3B8h] [rbp+2B8h]
  __int64 v152; // [rsp+3C0h] [rbp+2C0h]
  _BYTE *v153; // [rsp+3C8h] [rbp+2C8h]
  __int64 v154; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v155[512]; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v156; // [rsp+5D8h] [rbp+4D8h]
  __int64 v157; // [rsp+5E0h] [rbp+4E0h]
  _BYTE *v158; // [rsp+5E8h] [rbp+4E8h]
  wil::details::in1diag3 *retaddr; // [rsp+638h] [rbp+538h]

  v114 = (unsigned __int16 **)&v110;
  v8 = 0;
  v116 = 1;
  v110 = 0;
  v115 = 0;
  v10 = SRCacheManager_Open(0, &v115);
  if ( v116 )
  {
    v11 = *v114;
    *v114 = v115;
    if ( v11 )
      SRCacheManager_Close(v11);
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)(unsigned int)v10,
      (int)v93);
    v12 = 73;
LABEL_248:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
      (const char *)(unsigned int)v10,
      (int)v93);
    goto LABEL_249;
  }
  v123 = 0;
  v10 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v110,
          a2,
          &v123);
  if ( v10 < 0 )
  {
    v12 = 75;
    goto LABEL_248;
  }
  v13 = v123;
  if ( !v123 )
  {
    if ( !a2
      || (memset_0(&v149, 0, 0xF0u),
          LODWORD(v111) = 240,
          (unsigned int)ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
                          a2,
                          v14,
                          &v111,
                          &v149) == 87) )
    {
      v12 = 79;
LABEL_247:
      v10 = -2147024809;
      goto LABEL_248;
    }
    v15 = v110;
    v110 = 0;
    goto LABEL_243;
  }
  v16 = 0;
  switch ( a3 )
  {
    case 0:
      v16 = 256;
      goto LABEL_16;
    case 1:
      v16 = 768;
      goto LABEL_16;
    case 2:
    case 3:
    case 4:
    case 5:
LABEL_16:
      v125 = 0;
      *(_OWORD *)v124 = 0;
      v17 = v16 | 0x20;
      v126 = 0;
      v127 = 0;
      v18 = 0;
      v129 = 0;
      if ( !a1 )
        v17 = v16;
      v128 = 0;
      v130 = 0;
      v131 = 0;
      v132 = 0;
      v133 = 0;
      v134 = 0;
      v135 = 0;
      if ( !v17 )
        goto LABEL_24;
      v109 = 0;
      v93 = &v109;
      v19 = StateRepository::Cache::Entity::Package_NoThrow::Get(&v110, v123, v17, v124);
      v10 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v19,
          (int)&v109);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
LABEL_249:
        v29 = v110;
        v110 = 0;
        goto LABEL_250;
      }
      if ( !v109 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80070490LL,
          (int)&v109);
LABEL_242:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
        v15 = v110;
        v110 = 0;
LABEL_243:
        if ( v15 )
          SRCacheManager_Close(v15);
        return 2147943568LL;
      }
      v13 = v123;
      v18 = v128;
LABEL_24:
      v20 = 0;
      v119 = 0;
      if ( a1 && v18 != 2 )
      {
        v21 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
                (struct StateRepository::Cache::Manager_NoThrow *)&v110,
                0,
                (__int64 *)&v119);
        v10 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7F,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)(unsigned int)v21,
            (int)v93);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
          goto LABEL_249;
        }
        if ( !v119 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x80,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)0x80070490LL,
            (int)"Unknown user",
            v108);
          goto LABEL_242;
        }
        v109 = 0;
        v22 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
                (struct StateRepository::Cache::Manager_NoThrow *)&v110,
                (__int64)v119,
                (__int64)v124[0],
                &v109);
        v10 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x82,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)(unsigned int)v22,
            (int)v93);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
          goto LABEL_249;
        }
        if ( !v109 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)0x80070490LL,
            (int)"Package %I64X not registered to user %I64X",
            v124[0],
            v119);
          goto LABEL_242;
        }
        v13 = v123;
        v20 = v119;
      }
      break;
    default:
LABEL_246:
      v12 = 103;
      goto LABEL_247;
  }
  P = 0;
  v121 = 0;
  *(_OWORD *)v122 = 0;
  switch ( a3 )
  {
    case 0:
      v23 = v131;
      goto LABEL_215;
    case 1:
      v23 = (const unsigned __int16 *)v132;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::GetImpl'::`2'::impl) )
      {
        if ( (_QWORD)v132 )
          goto LABEL_215;
      }
      else
      {
        if ( (_QWORD)v132 )
          goto LABEL_215;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80073D5BLL,
          (int)v93);
      }
      v24 = v122[1];
      v122[1] = 0;
      if ( v24 )
        SRCache_Free(v24);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
      v25 = v110;
      v110 = 0;
      if ( v25 )
        SRCacheManager_Close(v25);
      return 2147958107LL;
    case 2:
      if ( v20 )
        goto LABEL_54;
      v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              0,
              (__int64 *)&v119);
      if ( v10 < 0 )
      {
        v27 = 159;
        goto LABEL_50;
      }
      v13 = v123;
      v20 = v119;
LABEL_54:
      EffectiveLocationByUserAndPackage = StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(
                                            (struct StateRepository::Cache::Manager_NoThrow *)&v110,
                                            (__int64)v20,
                                            v13);
      v10 = EffectiveLocationByUserAndPackage;
      if ( EffectiveLocationByUserAndPackage >= 0 )
      {
        v8 = P;
        v23 = (const unsigned __int16 *)P;
        goto LABEL_215;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
        (const char *)(unsigned int)EffectiveLocationByUserAndPackage,
        (int)v93);
      v31 = v122[1];
      v122[1] = 0;
      if ( v31 )
        SRCache_Free(v31);
      v32 = P;
      if ( P )
        goto LABEL_58;
      goto LABEL_52;
    case 3:
      if ( !v13 )
      {
        v10 = -2147024809;
        v33 = 225;
LABEL_105:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v99);
        v27 = 168;
        goto LABEL_50;
      }
      v136 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              0,
              v13,
              (__int64 *)&v136);
      if ( v10 < 0 )
      {
        v33 = 228;
        goto LABEL_105;
      }
      v34 = v136;
      if ( !v136 )
        goto LABEL_214;
      v114 = (unsigned __int16 **)&v111;
      v117 = 0;
      v111 = 0;
      v115 = 0;
      v116 = 1;
      v10 = SRCacheContext_Open(v110, L"PackageExternalLocation\\Data", 0, &v115);
      if ( v116 )
      {
        v35 = *v114;
        *v114 = v115;
        if ( v35 )
          SRCacheContext_Close(v35);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v94);
        goto LABEL_83;
      }
      if ( !v111 )
      {
        v10 = -2140733422;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)0x80670012LL,
          (int)v93);
        goto LABEL_83;
      }
      v149 = 0;
      memset_0(v150, 0, sizeof(v150));
      v151 = 0;
      v153 = v150;
      v152 = 256;
      v36 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v149, v34);
      v10 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v36,
          (int)v93);
        goto LABEL_81;
      }
      v114 = (unsigned __int16 **)&v117;
      v115 = 0;
      v116 = 1;
      v10 = SRCacheContext_OpenSubContext(v111, v153, 0, &v115);
      if ( v116 )
      {
        v37 = *v114;
        *v114 = v115;
        if ( v37 )
          SRCacheContext_Close(v37);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v96);
        goto LABEL_81;
      }
      v38 = v117 != 0;
      v39 = SRCacheContext_AddToCache(v111, L"PackageExternalLocation\\Data");
      v10 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v39,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v97);
LABEL_81:
        v40 = v149;
        v149 = 0;
        if ( v40 )
          SRCache_Free(v40);
LABEL_83:
        v41 = v111;
        v111 = 0;
        if ( v41 )
          SRCacheContext_Close(v41);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v95);
        v42 = v117;
        v117 = 0;
        if ( v42 )
          SRCacheContext_Close(v42);
        if ( v10 < 0 )
        {
LABEL_104:
          v33 = 231;
          goto LABEL_105;
        }
        goto LABEL_214;
      }
      v43 = v149;
      v149 = 0;
      if ( v43 )
        SRCache_Free(v43);
      v44 = v111;
      v111 = 0;
      if ( v44 )
        SRCacheContext_Close(v44);
      v45 = v117;
      if ( !v38 )
      {
        v117 = 0;
        goto LABEL_212;
      }
      v116 = 1;
      v114 = &v122[1];
      v115 = 0;
      Field_String = SRCacheContext_GetField_String(v117, L"Path", &v115);
      v10 = Field_String;
      if ( Field_String >= 0 )
        v10 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_String,
          (int)v93);
      if ( v116 )
      {
        v47 = *v114;
        *v114 = v115;
        if ( v47 )
          SRCache_Free(v47);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x269,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v98);
        v48 = v117;
        v117 = 0;
        if ( v48 )
          SRCacheContext_Close(v48);
        goto LABEL_104;
      }
      v45 = v117;
      v117 = 0;
      *(_QWORD *)&v121 = v34;
      goto LABEL_212;
    case 4:
      if ( v20 )
        goto LABEL_114;
      v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              0,
              (__int64 *)&v119);
      if ( v10 < 0 )
      {
        v27 = 176;
        goto LABEL_50;
      }
      v20 = v119;
      if ( !v119 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80070490LL,
          (int)"Unknown user",
          v108);
        v49 = v122[1];
        v122[1] = 0;
        if ( v49 )
          SRCache_Free(v49);
        goto LABEL_242;
      }
      v13 = v123;
LABEL_114:
      if ( !v13 )
      {
        v10 = -2147024809;
        v50 = 225;
LABEL_159:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v50,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v105);
        v27 = 179;
        goto LABEL_50;
      }
      v137 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              (__int64)v20,
              v13,
              (__int64 *)&v137);
      if ( v10 < 0 )
      {
        v50 = 228;
        goto LABEL_159;
      }
      v51 = v137;
      if ( !v137 )
        goto LABEL_214;
      v114 = (unsigned __int16 **)&v112;
      v118 = 0;
      v112 = 0;
      v115 = 0;
      v116 = 1;
      v10 = SRCacheContext_Open(v110, L"PackageExternalLocation\\Data", 0, &v115);
      if ( v116 )
      {
        v52 = *v114;
        *v114 = v115;
        if ( v52 )
          SRCacheContext_Close(v52);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v100);
        goto LABEL_137;
      }
      if ( !v112 )
      {
        v10 = -2140733422;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)0x80670012LL,
          (int)v93);
        goto LABEL_137;
      }
      v154 = 0;
      memset_0(v155, 0, sizeof(v155));
      v156 = 0;
      v158 = v155;
      v157 = 256;
      v53 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v154, v51);
      v10 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v53,
          (int)v93);
        goto LABEL_135;
      }
      v114 = (unsigned __int16 **)&v118;
      v115 = 0;
      v116 = 1;
      v10 = SRCacheContext_OpenSubContext(v112, v158, 0, &v115);
      if ( v116 )
      {
        v54 = *v114;
        *v114 = v115;
        if ( v54 )
          SRCacheContext_Close(v54);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v102);
        goto LABEL_135;
      }
      v55 = v118 != 0;
      v56 = SRCacheContext_AddToCache(v112, L"PackageExternalLocation\\Data");
      v10 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v56,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v103);
LABEL_135:
        v57 = v154;
        v154 = 0;
        if ( v57 )
          SRCache_Free(v57);
LABEL_137:
        v58 = v112;
        v112 = 0;
        if ( v58 )
          SRCacheContext_Close(v58);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v101);
        v59 = v118;
        v118 = 0;
        if ( v59 )
          SRCacheContext_Close(v59);
        if ( v10 < 0 )
        {
LABEL_158:
          v50 = 231;
          goto LABEL_159;
        }
        goto LABEL_214;
      }
      v60 = v154;
      v154 = 0;
      if ( v60 )
        SRCache_Free(v60);
      v61 = v112;
      v112 = 0;
      if ( v61 )
        SRCacheContext_Close(v61);
      v45 = v118;
      if ( !v55 )
      {
        v118 = 0;
        goto LABEL_212;
      }
      v142 = 1;
      v140 = &v122[1];
      v141 = 0;
      v62 = SRCacheContext_GetField_String(v118, L"Path", &v141);
      v10 = v62;
      if ( v62 >= 0 )
        v10 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v62,
          (int)v93);
      if ( v142 )
      {
        v63 = *v140;
        *v140 = v141;
        if ( v63 )
          SRCache_Free(v63);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x269,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v104);
        v64 = v118;
        v118 = 0;
        if ( v64 )
          SRCacheContext_Close(v64);
        goto LABEL_158;
      }
      v45 = v118;
      v118 = 0;
      *(_QWORD *)&v121 = v51;
LABEL_212:
      if ( v45 )
        SRCacheContext_Close(v45);
LABEL_214:
      v23 = v122[1];
LABEL_215:
      if ( !v23 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80070490LL,
          (int)"Package %ls not found",
          (const char *)a2);
        v92 = v122[1];
        v122[1] = 0;
        if ( v92 )
          SRCache_Free(v92);
        if ( v8 )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v8);
        goto LABEL_242;
      }
LABEL_216:
      v82 = -1;
      do
        ++v82;
      while ( v23[v82] );
      v83 = *a4;
      v84 = v82 + 1;
      *a4 = v84;
      if ( (unsigned int)v83 < v84 )
      {
        v85 = v122[1];
        v122[1] = 0;
        if ( v85 )
          SRCache_Free(v85);
        if ( v8 )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v8);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
        v86 = v110;
        v110 = 0;
        if ( v86 )
          SRCacheManager_Close(v86);
        return 2147942522LL;
      }
      v87 = RtlStringCchCopyW(a5, v83, v23);
      if ( v87 < 0 )
      {
        v88 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xE0,
                (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
                (const char *)(unsigned int)v87,
                (int)v93);
        v89 = v122[1];
        v10 = v88;
        v122[1] = 0;
        if ( v89 )
          SRCache_Free(v89);
        if ( v8 )
        {
          v32 = v8;
LABEL_58:
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v32);
        }
        goto LABEL_52;
      }
      v90 = v122[1];
      v122[1] = 0;
      if ( v90 )
        SRCache_Free(v90);
      if ( v8 )
        RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v8);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
      v91 = v110;
      v110 = 0;
      if ( v91 )
        SRCacheManager_Close(v91);
      return 0;
    case 5:
      if ( v20 )
        goto LABEL_166;
      v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              0,
              (__int64 *)&v119);
      if ( v10 < 0 )
      {
        v27 = 188;
        goto LABEL_50;
      }
      v20 = v119;
      if ( !v119 )
        goto LABEL_190;
      v13 = v123;
LABEL_166:
      v109 = 0;
      if ( !v13 )
      {
        v10 = -2147024809;
        v65 = 225;
LABEL_185:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v65,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v106);
        v27 = 194;
        goto LABEL_50;
      }
      v138 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              (__int64)v20,
              v13,
              &v138);
      if ( v10 < 0 )
      {
        v65 = 228;
        goto LABEL_185;
      }
      v66 = v138;
      if ( !v138 )
        goto LABEL_189;
      v120 = 0;
      v67 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              v138,
              (struct StateRepository::Cache::Context_NoThrow *)&v120,
              &v109);
      v10 = v67;
      if ( v67 < 0 )
      {
        v68 = (unsigned int)v67;
        v69 = 164;
LABEL_182:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v69,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)v68,
          (int)v93);
        v73 = v120;
        v120 = 0;
        if ( v73 )
          ((void (*)(void))SRCacheContext_Close)();
        v65 = 231;
        goto LABEL_185;
      }
      v70 = v120;
      if ( v109 )
      {
        v144 = 0;
        v143 = &v122[1];
        v145 = 1;
        v71 = SRCacheContext_GetField_String(v120, L"Path", &v144);
        v10 = v71;
        if ( v71 >= 0 )
          v10 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x246,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (const char *)(unsigned int)v71,
            (int)v93);
        if ( v145 )
        {
          v72 = *v143;
          *v143 = v144;
          if ( v72 )
            ((void (*)(void))SRCache_Free)();
        }
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x269,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
            (const char *)(unsigned int)v10,
            (int)v93);
          v68 = (unsigned int)v10;
          v69 = 169;
          goto LABEL_182;
        }
        v70 = v120;
        *(_QWORD *)&v121 = v66;
      }
      v120 = 0;
      if ( v70 )
        ((void (*)(void))SRCacheContext_Close)();
LABEL_189:
      v23 = v122[1];
      if ( v122[1] )
        goto LABEL_216;
LABEL_190:
      v109 = 0;
      if ( !v123 )
      {
        v10 = -2147024809;
        v74 = 225;
LABEL_209:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v74,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v107);
        v27 = 201;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          (int)v93);
        v28 = v122[1];
        v122[1] = 0;
        if ( v28 )
          SRCache_Free(v28);
LABEL_52:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v124);
        v29 = v110;
        v110 = 0;
LABEL_250:
        if ( v29 )
          SRCacheManager_Close(v29);
        return (unsigned int)v10;
      }
      v139 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              0,
              v123,
              &v139);
      if ( v10 < 0 )
      {
        v74 = 228;
        goto LABEL_209;
      }
      v75 = v139;
      if ( !v139 )
        goto LABEL_214;
      P = 0;
      v76 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v110,
              v139,
              (struct StateRepository::Cache::Context_NoThrow *)&P,
              &v109);
      v10 = v76;
      if ( v76 < 0 )
      {
        v77 = (unsigned int)v76;
        v78 = 164;
LABEL_206:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v78,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)v77,
          (int)v93);
        v81 = P;
        P = 0;
        if ( v81 )
          ((void (*)(void))SRCacheContext_Close)();
        v74 = 231;
        goto LABEL_209;
      }
      v45 = P;
      if ( v109 )
      {
        v147 = 0;
        v146 = &v122[1];
        v148 = 1;
        v79 = SRCacheContext_GetField_String(P, L"Path", &v147);
        v10 = v79;
        if ( v79 >= 0 )
          v10 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x246,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (const char *)(unsigned int)v79,
            (int)v93);
        if ( v148 )
        {
          v80 = *v146;
          *v146 = v147;
          if ( v80 )
            ((void (*)(void))SRCache_Free)();
        }
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x269,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
            (const char *)(unsigned int)v10,
            (int)v93);
          v77 = (unsigned int)v10;
          v78 = 169;
          goto LABEL_206;
        }
        v45 = P;
        *(_QWORD *)&v121 = v75;
      }
      P = 0;
      goto LABEL_212;
    default:
      goto LABEL_246;
  }
}

```

## disassembly

```asm
0x18006bf30  mov     [rsp-8+arg_0], rbx
0x18006bf35  push    rbp
0x18006bf36  push    rsi
0x18006bf37  push    rdi
0x18006bf38  push    r12
0x18006bf3a  push    r13
0x18006bf3c  push    r14
0x18006bf3e  push    r15
0x18006bf40  lea     rbp, [rsp-500h]
0x18006bf48  sub     rsp, 600h
0x18006bf4f  mov     rax, cs:__security_cookie
0x18006bf56  xor     rax, rsp
0x18006bf59  mov     [rbp+530h+var_40], rax
0x18006bf60  mov     r13, [rbp+530h+arg_20]
0x18006bf67  lea     rax, [rsp+630h+var_5E8]
0x18006bf6c  mov     r15, rdx
0x18006bf6f  mov     [rsp+630h+var_5C8], rax
0x18006bf74  movzx   esi, cl
0x18006bf77  movsxd  rdi, r8d
0x18006bf7a  xor     r14d, r14d
0x18006bf7d  mov     [rsp+630h+var_5B8], 1
0x18006bf82  lea     rdx, [rsp+630h+var_5C0]
0x18006bf87  mov     [rsp+630h+var_5E8], r14
0x18006bf8c  xor     ecx, ecx
0x18006bf8e  mov     [rsp+630h+var_5C0], r14
0x18006bf93  mov     r12, r9
0x18006bf96  call    cs:__imp_SRCacheManager_Open
0x18006bf9d  nop     dword ptr [rax+rax+00h]
0x18006bfa2  mov     ebx, eax
0x18006bfa4  cmp     [rsp+630h+var_5B8], r14b
0x18006bfa9  jz      short loc_18006BFCC
0x18006bfab  mov     r8, [rsp+630h+var_5C8]
0x18006bfb0  mov     rdx, [rsp+630h+var_5C0]
0x18006bfb5  mov     rcx, [r8]
0x18006bfb8  mov     [r8], rdx
0x18006bfbb  test    rcx, rcx
0x18006bfbe  jz      short loc_18006BFCC
0x18006bfc0  call    cs:__imp_SRCacheManager_Close
0x18006bfc7  nop     dword ptr [rax+rax+00h]
0x18006bfcc  test    ebx, ebx
0x18006bfce  jns     short loc_18006BFF5
0x18006bfd0  mov     rcx, [rbp+538h]; this
0x18006bfd7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006bfde  mov     r9d, ebx; char *
0x18006bfe1  mov     edx, 0A5h; void *
0x18006bfe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bfeb  mov     edx, 49h ; 'I'
0x18006bff0  jmp     loc_18006D3B0
0x18006bff5  lea     r8, [rbp+530h+var_570]; __int64 *
0x18006bff9  mov     [rbp+530h+var_570], r14
0x18006bffd  mov     rdx, r15; unsigned __int16 *
0x18006c000  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18006c005  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18006c00a  mov     ebx, eax
0x18006c00c  test    eax, eax
0x18006c00e  jns     short loc_18006C01A
0x18006c010  mov     edx, 4Bh ; 'K'
0x18006c015  jmp     loc_18006D3B0
0x18006c01a  mov     r10, [rbp+530h+var_570]
0x18006c01e  test    r10, r10
0x18006c021  jnz     short loc_18006C076
0x18006c023  test    r15, r15
0x18006c026  jz      short loc_18006C06C
0x18006c028  xor     edx, edx; Val
0x18006c02a  lea     rcx, [rbp+530h+var_480]; void *
0x18006c031  mov     r8d, 0F0h; Size
0x18006c037  call    memset_0
0x18006c03c  lea     r9, [rbp+530h+var_480]
0x18006c043  mov     dword ptr [rsp+630h+var_5E0], 0F0h
0x18006c04b  lea     r8, [rsp+630h+var_5E0]
0x18006c050  mov     rcx, r15
0x18006c053  call    ?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)
0x18006c058  cmp     eax, 57h ; 'W'
0x18006c05b  jz      short loc_18006C06C
0x18006c05d  mov     rcx, [rsp+630h+var_5E8]
0x18006c062  mov     [rsp+630h+var_5E8], r14
0x18006c067  jmp     loc_18006D38E
0x18006c06c  mov     edx, 4Fh ; 'O'
0x18006c071  jmp     loc_18006D3AB
0x18006c076  cmp     edi, 5; switch 6 cases
0x18006c079  ja      def_18006C094; jumptable 000000018006C094 default case
0x18006c07f  lea     r8, __ImageBase
0x18006c086  mov     rdx, r14
0x18006c089  mov     ecx, ds:(jpt_18006C094 - 180000000h)[r8+rdi*4]
0x18006c091  add     rcx, r8
0x18006c094  jmp     rcx; switch jump
0x18006c09a  mov     edx, 100h; jumptable 000000018006C094 case 0
0x18006c09f  jmp     short loc_18006C0A6; jumptable 000000018006C094 cases 2-5
0x18006c0a1  mov     edx, 300h; jumptable 000000018006C094 case 1
0x18006c0a6  xorps   xmm0, xmm0; jumptable 000000018006C094 cases 2-5
0x18006c0a9  mov     [rbp+530h+var_550], r14
0x18006c0ad  mov     r8, rdx
0x18006c0b0  movdqa  xmmword ptr [rbp+530h+var_560], xmm0
0x18006c0b5  or      r8, 20h
0x18006c0b9  mov     [rbp+530h+var_548], r14
0x18006c0bd  test    sil, sil
0x18006c0c0  mov     [rbp+530h+var_540], r14d
0x18006c0c4  mov     eax, r14d
0x18006c0c7  mov     [rbp+530h+var_538], r14
0x18006c0cb  cmovz   r8, rdx
0x18006c0cf  mov     [rbp+530h+var_53C], eax
0x18006c0d2  mov     [rbp+530h+var_530], r14
0x18006c0d6  mov     [rbp+530h+var_528], r14
0x18006c0da  movdqa  [rbp+530h+var_520], xmm0
0x18006c0df  mov     [rbp+530h+var_510], r14d
0x18006c0e3  mov     [rbp+530h+var_508], r14
0x18006c0e7  mov     [rbp+530h+var_500], r14
0x18006c0eb  test    r8, r8
0x18006c0ee  jz      loc_18006C186
0x18006c0f4  mov     [rsp+630h+var_5F0], al
0x18006c0f8  lea     r9, [rbp+530h+var_560]
0x18006c0fc  lea     rax, [rsp+630h+var_5F0]
0x18006c101  mov     rdx, r10
0x18006c104  lea     rcx, [rsp+630h+var_5E8]
0x18006c109  mov     qword ptr [rsp+630h+var_610], rax; int
0x18006c10e  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18006c113  mov     ebx, eax
0x18006c115  test    eax, eax
0x18006c117  jns     short loc_18006C142
0x18006c119  mov     rcx, [rbp+538h]; this
0x18006c120  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c127  mov     r9d, eax; char *
0x18006c12a  mov     edx, 71h ; 'q'; void *
0x18006c12f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c134  lea     rcx, [rbp+530h+var_560]; this
0x18006c138  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006c13d  jmp     loc_18006D3C6
0x18006c142  cmp     [rsp+630h+var_5F0], r14b
0x18006c147  jnz     short loc_18006C17F
0x18006c149  mov     rcx, [rbp+538h]; this
0x18006c150  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c157  mov     r9d, 80070490h; char *
0x18006c15d  mov     edx, 72h ; 'r'; void *
0x18006c162  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c167  lea     rcx, [rbp+530h+var_560]; this
0x18006c16b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006c170  mov     rcx, [rsp+630h+var_5E8]
0x18006c175  mov     [rsp+630h+var_5E8], r14
0x18006c17a  jmp     loc_18006D38E
0x18006c17f  mov     r10, [rbp+530h+var_570]
0x18006c183  mov     eax, [rbp+530h+var_53C]
0x18006c186  mov     rdx, r14; void *
0x18006c189  mov     [rbp+530h+var_5A0], rdx
0x18006c18d  test    sil, sil
0x18006c190  jz      loc_18006C2AB
0x18006c196  cmp     eax, 2
0x18006c199  jz      loc_18006C2AB
0x18006c19f  lea     r8, [rbp+530h+var_5A0]; __int64 *
0x18006c1a3  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18006c1a8  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18006c1ad  mov     ebx, eax
0x18006c1af  test    eax, eax
0x18006c1b1  jns     short loc_18006C1DC
0x18006c1b3  mov     rcx, [rbp+538h]; this
0x18006c1ba  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c1c1  mov     r9d, eax; char *
0x18006c1c4  mov     edx, 7Fh; void *
0x18006c1c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c1ce  lea     rcx, [rbp+530h+var_560]; this
0x18006c1d2  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006c1d7  jmp     loc_18006D3C6
0x18006c1dc  mov     rdx, [rbp+530h+var_5A0]; __int64
0x18006c1e0  test    rdx, rdx
0x18006c1e3  jnz     short loc_18006C214
0x18006c1e5  mov     rcx, [rbp+538h]; this
0x18006c1ec  lea     rax, aUnknownUser; "Unknown user"
0x18006c1f3  mov     r9d, 80070490h; char *
0x18006c1f9  mov     qword ptr [rsp+630h+var_610], rax; int
0x18006c1fe  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c205  mov     edx, 80h; void *
0x18006c20a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006c20f  jmp     loc_18006C167
0x18006c214  mov     r8, [rbp+530h+var_560]; __int64
0x18006c218  lea     r9, [rsp+630h+var_5F0]; bool *
0x18006c21d  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18006c222  mov     [rsp+630h+var_5F0], r14b
0x18006c227  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x18006c22c  mov     ebx, eax
0x18006c22e  test    eax, eax
0x18006c230  jns     short loc_18006C25B
0x18006c232  mov     rcx, [rbp+538h]; this
0x18006c239  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c240  mov     r9d, eax; char *
0x18006c243  mov     edx, 82h; void *
0x18006c248  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c24d  lea     rcx, [rbp+530h+var_560]; this
0x18006c251  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006c256  jmp     loc_18006D3C6
0x18006c25b  cmp     [rsp+630h+var_5F0], r14b
0x18006c260  jnz     short loc_18006C2A3
0x18006c262  mov     rax, [rbp+530h+var_5A0]
0x18006c266  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c26d  mov     rcx, [rbp+538h]; this
0x18006c274  mov     r9d, 80070490h; char *
0x18006c27a  mov     [rsp+630h+var_600], rax
0x18006c27f  mov     edx, 83h; void *
0x18006c284  mov     rax, [rbp+530h+var_560]
0x18006c288  mov     [rsp+630h+var_608], rax; char *
0x18006c28d  lea     rax, aPackageI64xNot; "Package %I64X not registered to user %I"...
0x18006c294  mov     qword ptr [rsp+630h+var_610], rax; int
0x18006c299  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006c29e  jmp     loc_18006C167
0x18006c2a3  mov     r10, [rbp+530h+var_570]
0x18006c2a7  mov     rdx, [rbp+530h+var_5A0]; void *
0x18006c2ab  lea     r8, __ImageBase
0x18006c2b2  xor     esi, esi
0x18006c2b4  mov     ecx, ds:(jpt_18006C2D4 - 180000000h)[r8+rdi*4]; switch 6 cases
0x18006c2bc  xorps   xmm0, xmm0
0x18006c2bf  xorps   xmm1, xmm1
0x18006c2c2  mov     [rsp+630h+P], rsi
0x18006c2c7  add     rcx, r8
0x18006c2ca  movdqu  [rbp+530h+var_590], xmm0
0x18006c2cf  movdqu  xmmword ptr [rbp+530h+var_580], xmm1
0x18006c2d4  jmp     rcx; switch jump
0x18006c2da  mov     rbx, [rbp+530h+var_528]; jumptable 000000018006C2D4 case 0
0x18006c2de  jmp     loc_18006D1D0
0x18006c2e3  mov     rbx, qword ptr [rbp+530h+var_520]; jumptable 000000018006C2D4 case 1
0x18006c2e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError> `wil::Feature<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::GetImpl(void)'::`2'::impl
0x18006c2ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::__private_IsEnabled(void)
0x18006c2f3  test    al, al
0x18006c2f5  jz      short loc_18006C303
0x18006c2f7  cmp     qword ptr [rbp+530h+var_520], rsi
0x18006c2fb  jnz     loc_18006D1D0
0x18006c301  jmp     short loc_18006C32B
0x18006c303  cmp     qword ptr [rbp+530h+var_520], rsi
0x18006c307  jnz     loc_18006D1D0
0x18006c30d  mov     rcx, [rbp+538h]; this
0x18006c314  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c31b  mov     r9d, 80073D5Bh; char *
0x18006c321  mov     edx, 98h; void *
0x18006c326  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c32b  mov     rcx, [rbp+530h+var_580+8]
0x18006c32f  mov     [rbp+530h+var_580+8], rsi
0x18006c333  test    rcx, rcx
0x18006c336  jz      short loc_18006C344
0x18006c338  call    cs:__imp_SRCache_Free
0x18006c33f  nop     dword ptr [rax+rax+00h]
0x18006c344  lea     rcx, [rbp+530h+var_560]; this
0x18006c348  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006c34d  mov     rcx, [rsp+630h+var_5E8]
0x18006c352  mov     [rsp+630h+var_5E8], rsi
0x18006c357  test    rcx, rcx
0x18006c35a  jz      short loc_18006C368
0x18006c35c  call    cs:__imp_SRCacheManager_Close
0x18006c363  nop     dword ptr [rax+rax+00h]
0x18006c368  mov     eax, 80073D5Bh
0x18006c36d  jmp     loc_18006D3E3
0x18006c372  test    rdx, rdx; jumptable 000000018006C2D4 case 2
0x18006c375  jnz     short loc_18006C3DF
0x18006c377  lea     r8, [rbp+530h+var_5A0]; __int64 *
0x18006c37b  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18006c380  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18006c385  mov     ebx, eax
0x18006c387  test    eax, eax
0x18006c389  jns     short loc_18006C3D7
0x18006c38b  mov     edx, 9Fh; void *
0x18006c390  mov     rcx, [rbp+538h]; this
0x18006c397  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c39e  mov     r9d, ebx; char *
0x18006c3a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c3a6  mov     rcx, [rbp+530h+var_580+8]
0x18006c3aa  mov     [rbp+530h+var_580+8], rsi
0x18006c3ae  test    rcx, rcx
0x18006c3b1  jz      short loc_18006C3BF
0x18006c3b3  call    cs:__imp_SRCache_Free
0x18006c3ba  nop     dword ptr [rax+rax+00h]
0x18006c3bf  lea     rcx, [rbp+530h+var_560]; this
0x18006c3c3  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006c3c8  mov     rcx, [rsp+630h+var_5E8]
0x18006c3cd  mov     [rsp+630h+var_5E8], rsi
0x18006c3d2  jmp     loc_18006D3D0
0x18006c3d7  mov     r10, [rbp+530h+var_570]
0x18006c3db  mov     rdx, [rbp+530h+var_5A0]
0x18006c3df  lea     r9, [rsp+630h+P]
0x18006c3e4  mov     r8, r10
0x18006c3e7  lea     rcx, [rsp+630h+var_5E8]
0x18006c3ec  call    ?GetEffectiveLocationByUserAndPackage@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18006c3f1  mov     ebx, eax
0x18006c3f3  test    eax, eax
0x18006c3f5  jns     short loc_18006C44F
0x18006c3f7  mov     rcx, [rbp+538h]; this
0x18006c3fe  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18006c405  mov     r9d, eax; char *
0x18006c408  mov     edx, 0A1h; void *
0x18006c40d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c412  mov     rcx, [rbp+530h+var_580+8]
0x18006c416  mov     [rbp+530h+var_580+8], rsi
0x18006c41a  test    rcx, rcx
0x18006c41d  jz      short loc_18006C42B
0x18006c41f  call    cs:__imp_SRCache_Free
0x18006c426  nop     dword ptr [rax+rax+00h]
0x18006c42b  mov     r8, [rsp+630h+P]; P
0x18006c430  test    r8, r8
0x18006c433  jz      short loc_18006C3BF
0x18006c435  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18006c43c  xor     edx, edx; Flags
0x18006c43e  call    cs:__imp_RtlFreeHeap
0x18006c445  nop     dword ptr [rax+rax+00h]
0x18006c44a  jmp     loc_18006C3BF
0x18006c44f  mov     r14, [rsp+630h+P]
  ... truncated ...
```
