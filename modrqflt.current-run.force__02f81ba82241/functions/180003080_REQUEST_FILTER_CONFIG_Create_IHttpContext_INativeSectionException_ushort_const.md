# REQUEST_FILTER_CONFIG::Create(IHttpContext *,INativeSectionException * *,ushort const * *)

- ea: `0x180003080`
- end: `0x180005047`
- name: `?Create@REQUEST_FILTER_CONFIG@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@PEAPEBG@Z`
- size: `8135`
- prototype: `__int64 __fastcall(REQUEST_FILTER_CONFIG *__hidden this, struct IHttpContext *, struct INativeSectionException **, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800010c0`
- `0x180002ab0`

## callees

- `0x180003080`
- `0x180005050`
- `0x180005860`
- `0x180007bc0`
- `0x180008010`

## import_xrefs

- `msvcrt!wcscspn` at `0x18000420f`
- `msvcrt!wcscspn` at `0x18000420f`
- `msvcrt!_wcslwr` at `0x18000423d`
- `msvcrt!_wcslwr` at `0x18000455c`
- `msvcrt!_wcslwr` at `0x1800047eb`
- `msvcrt!_wcslwr` at `0x180004a7a`
- `msvcrt!_wcslwr` at `0x180004d09`
- `msvcrt!_wcslwr` at `0x18000423d`
- `msvcrt!_wcslwr` at `0x18000455c`
- `msvcrt!_wcslwr` at `0x1800047eb`
- `msvcrt!_wcslwr` at `0x180004a7a`
- `msvcrt!_wcslwr` at `0x180004d09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e98`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004f16`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004f23`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004f16`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004f23`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003ec6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f03`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f5e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003fb7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000400c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003ec6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f03`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f5e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003fb7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000400c`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180003785`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180003798`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004257`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004576`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004805`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004a94`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004d23`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180003785`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180003798`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004257`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004576`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004805`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004a94`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180004d23`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003ae5`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003e66`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003ae5`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003e66`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003aad`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003e0b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003aad`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003e0b`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180003eb3`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180003ee1`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180003eb3`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180003ee1`
- `iisutil!QueryLocalizedResourceString` at `0x1800042ee`
- `iisutil!QueryLocalizedResourceString` at `0x1800042ee`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003ea3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003ed1`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003ea3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003ed1`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180004f09`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180004f09`
- `iisutil!PuDbgPrint` at `0x180003305`
- `iisutil!PuDbgPrint` at `0x180003809`
- `iisutil!PuDbgPrint` at `0x18000385c`
- `iisutil!PuDbgPrint` at `0x180003b60`
- `iisutil!PuDbgPrint` at `0x180003bb3`
- `iisutil!PuDbgPrint` at `0x180003f54`
- `iisutil!PuDbgPrint` at `0x180003fad`
- `iisutil!PuDbgPrint` at `0x180004002`
- `iisutil!PuDbgPrint` at `0x180004350`
- `iisutil!PuDbgPrint` at `0x1800043a5`
- `iisutil!PuDbgPrint` at `0x1800045e6`
- `iisutil!PuDbgPrint` at `0x180004634`
- `iisutil!PuDbgPrint` at `0x180004875`
- `iisutil!PuDbgPrint` at `0x1800048c3`
- `iisutil!PuDbgPrint` at `0x180004b04`
- `iisutil!PuDbgPrint` at `0x180004b52`
- `iisutil!PuDbgPrint` at `0x180004d93`
- `iisutil!PuDbgPrint` at `0x180004de1`
- `iisutil!PuDbgPrint` at `0x180003305`
- `iisutil!PuDbgPrint` at `0x180003809`
- `iisutil!PuDbgPrint` at `0x18000385c`
- `iisutil!PuDbgPrint` at `0x180003b60`
- `iisutil!PuDbgPrint` at `0x180003bb3`
- `iisutil!PuDbgPrint` at `0x180003f54`
- `iisutil!PuDbgPrint` at `0x180003fad`
- `iisutil!PuDbgPrint` at `0x180004002`
- `iisutil!PuDbgPrint` at `0x180004350`
- `iisutil!PuDbgPrint` at `0x1800043a5`
- `iisutil!PuDbgPrint` at `0x1800045e6`
- `iisutil!PuDbgPrint` at `0x180004634`
- `iisutil!PuDbgPrint` at `0x180004875`
- `iisutil!PuDbgPrint` at `0x1800048c3`
- `iisutil!PuDbgPrint` at `0x180004b04`
- `iisutil!PuDbgPrint` at `0x180004b52`
- `iisutil!PuDbgPrint` at `0x180004d93`
- `iisutil!PuDbgPrint` at `0x180004de1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000419c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800044ea`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004779`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004a08`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004c97`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004ec4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004eff`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000419c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800044ea`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004779`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004a08`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004c97`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004ec4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004eff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004279`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000428f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000429f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004301`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000435a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800043af`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000459c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000463e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000482b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000487f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800048cd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004aba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004b0e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004b5c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d9d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004deb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004f82`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004279`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000428f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000429f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004301`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000435a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800043af`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000459c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000463e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000482b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000487f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800048cd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004aba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004b0e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004b5c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d9d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004deb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004f82`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004234`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004247`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004553`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004566`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800047e2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800047f5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004a71`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004a84`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004d00`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004d13`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004234`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004247`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004553`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004566`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800047e2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800047f5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004a71`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004a84`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004d00`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004d13`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004226`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004541`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800047d0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004a5f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004cee`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004226`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004541`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800047d0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004a5f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004cee`

## string_xrefs

- `0x1800031ca`: `removeServerHeader`
- `0x18000322a`: `fileExtensions`
- `0x180003146`: `system.webServer/security/requestFiltering`
- `0x1800032fe`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x1800037e0`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180003833`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180003b3e`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180003b8a`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180003f2b`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180003f84`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180003fdd`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004327`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004380`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x1800045c4`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004616`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004853`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x1800048a5`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004ae2`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004b34`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004d71`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x180004dc3`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\config.cxx`
- `0x1800032d9`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003506`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000353a`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000356e`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800035a2`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800035d6`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000360a`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000363e`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003672`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800036a6`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800036da`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800037d5`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003828`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003878`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800038ac`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800038e0`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003914`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003948`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000397c`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800039b0`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003b33`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003b7f`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003bcf`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003c66`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003cc6`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003d26`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003d74`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003dc9`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003f20`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003f79`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003fd2`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004074`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800040cd`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000411b`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004169`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000431c`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004375`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004417`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004465`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800044b3`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800045b9`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000460b`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800046a6`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800046f4`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004742`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004848`: `REQUEST_FILTER_CONFIG::Create`
- `0x18000489a`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004935`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004983`: `REQUEST_FILTER_CONFIG::Create`
- `0x1800049d1`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004ad7`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004b29`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004bc4`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004c12`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004c60`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004d66`: `REQUEST_FILTER_CONFIG::Create`
- `0x180004db8`: `REQUEST_FILTER_CONFIG::Create`
- `0x180003541`: `GetConfigSection failed on %S - 0x%08x.\n`
- `0x180003731`: `fileExtension`
- `0x18000383a`: `fileExtension`

## pseudocode

```c
__int64 __fastcall REQUEST_FILTER_CONFIG::Create(
        REQUEST_FILTER_CONFIG *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3,
        const unsigned __int16 **a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v7)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v10)(_QWORD); // rax
  __int64 v11; // r14
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rax
  int v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v24; // eax
  unsigned int i; // esi
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  unsigned int v36; // eax
  HLOCAL v37; // rax
  unsigned int j; // esi
  int v39; // eax
  int v40; // eax
  int v41; // eax
  STRA *v42; // rax
  STRA *v43; // rbx
  __int64 v44; // r14
  STRA *v45; // rcx
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  unsigned int k; // esi
  int v52; // eax
  int v53; // eax
  int v54; // eax
  const char *Str; // rax
  const char *v56; // rax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  unsigned int m; // esi
  int v62; // eax
  int v63; // eax
  size_t v64; // rbx
  wchar_t *v65; // rax
  const unsigned __int16 *v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  const char *v69; // rax
  int v70; // eax
  int v71; // eax
  int v72; // eax
  unsigned int n; // esi
  int v74; // eax
  int v75; // eax
  wchar_t *v76; // rax
  const unsigned __int16 *v77; // rax
  int v78; // eax
  int v79; // eax
  int v80; // eax
  unsigned int ii; // esi
  int v82; // eax
  int v83; // eax
  wchar_t *v84; // rax
  const unsigned __int16 *v85; // rax
  int v86; // eax
  int v87; // eax
  int v88; // eax
  unsigned int jj; // esi
  int v90; // eax
  int v91; // eax
  wchar_t *v92; // rax
  const unsigned __int16 *v93; // rax
  int v94; // eax
  int v95; // eax
  int v96; // eax
  unsigned int kk; // esi
  int v98; // eax
  int v99; // eax
  wchar_t *v100; // rax
  const unsigned __int16 *v101; // rax
  __int64 v102; // rax
  HLOCAL v103; // rax
  unsigned int mm; // esi
  STRU *v105; // rax
  STRU *v106; // rbx
  __int64 v107; // rcx
  FILTERING_RULE *v108; // rcx
  __int64 v109; // [rsp+40h] [rbp-79h] BYREF
  __int64 v110; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v111; // [rsp+50h] [rbp-69h] BYREF
  struct INativeConfigurationElement *v112; // [rsp+58h] [rbp-61h] BYREF
  int v113; // [rsp+60h] [rbp-59h] BYREF
  wchar_t *String; // [rsp+68h] [rbp-51h] BYREF
  __int64 v115; // [rsp+70h] [rbp-49h] BYREF
  __int64 v116; // [rsp+78h] [rbp-41h] BYREF
  const unsigned __int16 *v117; // [rsp+80h] [rbp-39h] BYREF
  __int64 v118; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v119[56]; // [rsp+90h] [rbp-29h] BYREF

  v4 = *(_QWORD *)a2;
  v118 = 0;
  v115 = 0;
  v110 = 0;
  v7 = *(__int64 (__fastcall **)(struct IHttpContext *))(v4 + 160);
  v116 = 0;
  v109 = 0;
  v112 = 0;
  v111 = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD))v7(a2);
  v11 = (**v10)(v10);
  v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v13 = (**v12)(v12, &IID_INativeConfigurationSystem, &v118);
  if ( v13 < 0 )
    goto LABEL_13;
  v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v118 + 24LL))(
          v118,
          L"system.webServer/security/requestFiltering",
          v11,
          &v115,
          a3,
          0);
  v13 = v14;
  if ( v14 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        134,
        "REQUEST_FILTER_CONFIG::Create",
        "GetConfigSection failed on %S - 0x%08x.\r\n",
        L"system.webServer/security/requestFiltering",
        v14);
    goto LABEL_13;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v115 + 72LL))(
          v115,
          L"allowDoubleEscaping",
          (char *)this + 8,
          0,
          0);
  v13 = v15;
  if ( v15 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        147,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"allowDoubleEscaping",
        v15);
    goto LABEL_13;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v115 + 72LL))(
          v115,
          L"allowHighBitCharacters",
          (char *)this + 12,
          0,
          0);
  v13 = v16;
  if ( v16 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        160,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"allowHighBitCharacters",
        v16);
    goto LABEL_13;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v115 + 72LL))(
          v115,
          L"removeServerHeader",
          (char *)this + 16,
          0,
          0);
  v13 = v17;
  if ( v17 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        173,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"removeServerHeader",
        v17);
    goto LABEL_13;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v115 + 72LL))(
          v115,
          L"unescapeQueryString",
          (char *)this + 20,
          0,
          0);
  v13 = v18;
  if ( v18 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        186,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"unescapeQueryString",
        v18);
    goto LABEL_13;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"fileExtensions",
          &v110);
  v13 = v19;
  if ( v19 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        203,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"fileExtensions",
        v19);
    goto LABEL_13;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 72LL))(
          v110,
          L"allowUnlisted",
          (char *)this + 36,
          0,
          0);
  v13 = v20;
  if ( v20 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        216,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"allowUnlisted",
        v20);
    goto LABEL_13;
  }
  v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 72LL))(
          v110,
          L"applyToWebDAV",
          (char *)this + 44,
          0,
          0);
  v13 = v21;
  if ( v21 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        229,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"applyToWebDAV",
        v21);
    goto LABEL_13;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  v13 = v22;
  if ( v22 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        241,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"fileExtensions",
        v22);
    goto LABEL_13;
  }
  v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v24;
  if ( v24 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        253,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"fileExtensions",
        v24);
LABEL_13:
    if ( v112 )
    {
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
      v112 = 0;
    }
    if ( v109 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
      v109 = 0;
    }
    if ( v110 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
      v110 = 0;
    }
    if ( v116 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
      v116 = 0;
    }
    if ( v115 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
      v115 = 0;
    }
    if ( v118 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
    return (unsigned int)v13;
  }
  for ( i = 0; i < v111; ++i )
  {
    v117 = 0;
    v113 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            i,
            &v112);
    v13 = v33;
    if ( v33 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          270,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"fileExtensions",
          v33);
      goto LABEL_13;
    }
    v34 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"fileExtension",
            &v117,
            0,
            0);
    v13 = v34;
    if ( v34 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          284,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"fileExtension",
          i,
          v34);
      goto LABEL_13;
    }
    v35 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v112 + 72LL))(
            v112,
            L"allowed",
            &v113,
            0,
            0);
    v13 = v35;
    if ( v35 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          298,
          "REQUEST_FILTER_CONFIG::Create",
          "GetBooleanProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"allowed",
          i,
          v35);
      goto LABEL_13;
    }
    if ( v113 )
    {
      if ( !MULTISZ::Append((REQUEST_FILTER_CONFIG *)((char *)this + 56), v117) )
        goto LABEL_84;
    }
    else if ( !MULTISZ::Append((REQUEST_FILTER_CONFIG *)((char *)this + 112), v117) )
    {
      goto LABEL_84;
    }
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"requestLimits",
          &v110);
  v13 = v26;
  if ( v26 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        347,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"requestLimits",
        v26);
    goto LABEL_13;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 48LL))(
          v110,
          L"maxAllowedContentLength",
          (char *)this + 24,
          0,
          0);
  v13 = v27;
  if ( v27 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        360,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"maxAllowedContentLength",
        v27);
    goto LABEL_13;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 48LL))(
          v110,
          L"maxUrl",
          (char *)this + 28,
          0,
          0);
  v13 = v28;
  if ( v28 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        373,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"maxUrl",
        v28);
    goto LABEL_13;
  }
  v29 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 48LL))(
          v110,
          L"maxQueryString",
          (char *)this + 32,
          0,
          0);
  v13 = v29;
  if ( v29 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        386,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"maxQueryString",
        v29);
    goto LABEL_13;
  }
  v30 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v110 + 32LL))(
          v110,
          L"headerLimits",
          &v116);
  v13 = v30;
  if ( v30 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        403,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"headerLimits",
        v30);
    goto LABEL_13;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v116 + 40LL))(v116, &v109);
  v13 = v31;
  if ( v31 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        415,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"headerLimits",
        v31);
    goto LABEL_13;
  }
  v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v32;
  if ( v32 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        427,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"headerLimits",
        v32);
    goto LABEL_13;
  }
  v36 = v111;
  *((_DWORD *)this + 142) = v111;
  if ( v36 )
  {
    v37 = LocalAlloc(0x40u, (unsigned __int64)v36 << 6);
    *((_QWORD *)this + 70) = v37;
    if ( !v37 )
    {
LABEL_84:
      v13 = -2147024882;
      goto LABEL_13;
    }
  }
  for ( j = 0; j < v111; ++j )
  {
    String = 0;
    v113 = 0;
    v39 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            j,
            &v112);
    v13 = v39;
    if ( v39 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          459,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"headerLimits",
          v39);
      goto LABEL_13;
    }
    v40 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"header",
            &String,
            0,
            0);
    v13 = v40;
    if ( v40 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          473,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"header",
          j,
          v40);
      goto LABEL_13;
    }
    v41 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v112 + 48LL))(
            v112,
            L"sizeLimit",
            &v113,
            0,
            0);
    v13 = v41;
    if ( v41 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          487,
          "REQUEST_FILTER_CONFIG::Create",
          "GetBooleanProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"sizeLimit",
          j,
          v41);
      goto LABEL_13;
    }
    v42 = (STRA *)operator new(0x40u);
    v43 = v42;
    if ( v42 )
      STRA::STRA(v42);
    else
      v43 = 0;
    v44 = 8LL * j;
    *(_QWORD *)(v44 + *((_QWORD *)this + 70)) = v43;
    v45 = *(STRA **)(v44 + *((_QWORD *)this + 70));
    if ( !v45 || (int)STRA::CopyW(v45, String) < 0 )
      goto LABEL_84;
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 70) + 8LL * j) + 56LL) = v113;
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
  v116 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v46 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(v115, L"verbs", &v110);
  v13 = v46;
  if ( v46 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        537,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"verbs",
        v46);
    goto LABEL_13;
  }
  v47 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 72LL))(
          v110,
          L"allowUnlisted",
          (char *)this + 40,
          0,
          0);
  v13 = v47;
  if ( v47 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        550,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"allowUnlisted",
        v47);
    goto LABEL_13;
  }
  v48 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 72LL))(
          v110,
          L"applyToWebDAV",
          (char *)this + 48,
          0,
          0);
  v13 = v48;
  if ( v48 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        563,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"applyToWebDAV",
        v48);
    goto LABEL_13;
  }
  v49 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  v13 = v49;
  if ( v49 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        575,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"verbs",
        v49);
    goto LABEL_13;
  }
  v50 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v50;
  if ( v50 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        587,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"verbs",
        v50);
    goto LABEL_13;
  }
  for ( k = 0; k < v111; ++k )
  {
    String = 0;
    v113 = 0;
    STRA::STRA((STRA *)v119);
    v52 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            k,
            &v112);
    v13 = v52;
    if ( v52 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          605,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"verbs",
          v52);
      goto LABEL_136;
    }
    v53 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"verb",
            &String,
            0,
            0);
    v13 = v53;
    if ( v53 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          619,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"verb",
          k,
          v53);
      goto LABEL_136;
    }
    if ( (int)STRA::CopyW((STRA *)v119, String) < 0 )
      goto LABEL_125;
    v54 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v112 + 72LL))(
            v112,
            L"allowed",
            &v113,
            0,
            0);
    v13 = v54;
    if ( v54 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          642,
          "REQUEST_FILTER_CONFIG::Create",
          "GetBooleanProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"allowed",
          k,
          v54);
LABEL_136:
      STRA::~STRA((STRA *)v119);
      goto LABEL_13;
    }
    if ( v113 )
    {
      Str = STRA::QueryStr((STRA *)v119);
      if ( !MULTISZA::Append((REQUEST_FILTER_CONFIG *)((char *)this + 168), Str) )
        goto LABEL_125;
    }
    else
    {
      v56 = STRA::QueryStr((STRA *)v119);
      if ( !MULTISZA::Append((REQUEST_FILTER_CONFIG *)((char *)this + 224), v56) )
      {
LABEL_125:
        v13 = -2147024882;
        STRA::~STRA((STRA *)v119);
        goto LABEL_13;
      }
    }
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
    STRA::~STRA((STRA *)v119);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v57 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"hiddenSegments",
          &v110);
  v13 = v57;
  if ( v57 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        691,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"hiddenSegments",
        v57);
    goto LABEL_13;
  }
  v58 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v110 + 72LL))(
          v110,
          L"applyToWebDAV",
          (char *)this + 52,
          0,
          0);
  v13 = v58;
  if ( v58 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        704,
        "REQUEST_FILTER_CONFIG::Create",
        "GetBooleanProperty failed on %S - 0x%08x\r\n",
        L"applyToWebDAV",
        v58);
    goto LABEL_13;
  }
  v59 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  v13 = v59;
  if ( v59 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        716,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"hiddenSegments",
        v59);
    goto LABEL_13;
  }
  v60 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v60;
  if ( v60 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        728,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"hiddenSegments",
        v60);
    goto LABEL_13;
  }
  for ( m = 0; m < v111; ++m )
  {
    STRU::STRU((STRU *)v119);
    String = 0;
    v62 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            m,
            &v112);
    v13 = v62;
    if ( v62 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          745,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"hiddenSegments",
          v62);
      goto LABEL_256;
    }
    v63 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"segment",
            &String,
            0,
            0);
    v13 = v63;
    if ( v63 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          759,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"hiddenSegments",
          m,
          v63);
LABEL_256:
      STRU::~STRU((STRU *)v119);
      goto LABEL_13;
    }
    v64 = -1;
    do
      ++v64;
    while ( String[v64] );
    if ( wcscspn(String, L"/\\") < v64 )
    {
      if ( a4 )
      {
        v67 = *(_QWORD *)a2;
        LOWORD(v113) = 0;
        LODWORD(v117) = 0;
        v68 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v67 + 24))(a2);
        v69 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v68 + 16LL))(v68, 23, &v113);
        *a4 = QueryLocalizedResourceString(v69, 0x3232u, (unsigned int *)&v117);
      }
      v13 = -2147023286;
      STRU::~STRU((STRU *)v119);
      goto LABEL_13;
    }
    if ( (int)STRU::Copy((STRU *)v119, String) < 0
      || (v65 = STRU::QueryStr((STRU *)v119),
          _wcslwr(v65),
          v66 = STRU::QueryStr((STRU *)v119),
          !MULTISZ::Append((REQUEST_FILTER_CONFIG *)((char *)this + 504), v66)) )
    {
LABEL_159:
      v13 = -2147024882;
      STRU::~STRU((STRU *)v119);
      goto LABEL_13;
    }
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
    STRU::~STRU((STRU *)v119);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v70 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"alwaysAllowedUrls",
          &v110);
  v13 = v70;
  if ( v70 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        840,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"alwaysAllowedUrls",
        v70);
    goto LABEL_13;
  }
  v71 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  v13 = v71;
  if ( v71 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        852,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"alwaysAllowedUrls",
        v71);
    goto LABEL_13;
  }
  v72 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v72;
  if ( v72 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        864,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"alwaysAllowedUrls",
        v72);
    goto LABEL_13;
  }
  for ( n = 0; n < v111; ++n )
  {
    String = 0;
    STRU::STRU((STRU *)v119);
    v74 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            n,
            &v112);
    v13 = v74;
    if ( v74 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          881,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"alwaysAllowedUrls",
          v74);
      goto LABEL_256;
    }
    v75 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"url",
            &String,
            0,
            0);
    v13 = v75;
    if ( v75 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          895,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"alwaysAllowedUrls",
          n,
          v75);
      goto LABEL_256;
    }
    if ( (int)STRU::Copy((STRU *)v119, String) < 0 )
      goto LABEL_159;
    v76 = STRU::QueryStr((STRU *)v119);
    _wcslwr(v76);
    v77 = STRU::QueryStr((STRU *)v119);
    if ( !MULTISZ::Append((REQUEST_FILTER_CONFIG *)((char *)this + 280), v77) )
      goto LABEL_159;
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
    STRU::~STRU((STRU *)v119);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v78 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"alwaysAllowedQueryStrings",
          &v110);
  v13 = v78;
  if ( v78 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        945,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"alwaysAllowedQueryStrings",
        v78);
    goto LABEL_13;
  }
  v79 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  v13 = v79;
  if ( v79 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        957,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"alwaysAllowedQueryStrings",
        v79);
    goto LABEL_13;
  }
  v80 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v80;
  if ( v80 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        969,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"alwaysAllowedQueryStrings",
        v80);
    goto LABEL_13;
  }
  for ( ii = 0; ii < v111; ++ii )
  {
    String = 0;
    STRU::STRU((STRU *)v119);
    v82 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            ii,
            &v112);
    v13 = v82;
    if ( v82 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          986,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"alwaysAllowedQueryStrings",
          v82);
      goto LABEL_256;
    }
    v83 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"queryString",
            &String,
            0,
            0);
    v13 = v83;
    if ( v83 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          1000,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"alwaysAllowedQueryStrings",
          ii,
          v83);
      goto LABEL_256;
    }
    if ( (int)STRU::Copy((STRU *)v119, String) < 0 )
      goto LABEL_159;
    v84 = STRU::QueryStr((STRU *)v119);
    _wcslwr(v84);
    v85 = STRU::QueryStr((STRU *)v119);
    if ( !MULTISZ::Append((REQUEST_FILTER_CONFIG *)((char *)this + 336), v85) )
      goto LABEL_159;
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
    STRU::~STRU((STRU *)v119);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v86 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"denyUrlSequences",
          &v110);
  v13 = v86;
  if ( v86 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        1050,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"denyUrlSequences",
        v86);
    goto LABEL_13;
  }
  v87 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  v13 = v87;
  if ( v87 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        1062,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"denyUrlSequences",
        v87);
    goto LABEL_13;
  }
  v88 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v88;
  if ( v88 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        1074,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"denyUrlSequences",
        v88);
    goto LABEL_13;
  }
  for ( jj = 0; jj < v111; ++jj )
  {
    String = 0;
    STRU::STRU((STRU *)v119);
    v90 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            jj,
            &v112);
    v13 = v90;
    if ( v90 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          1091,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"denyUrlSequences",
          v90);
      goto LABEL_256;
    }
    v91 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"sequence",
            &String,
            0,
            0);
    v13 = v91;
    if ( v91 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          1105,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"denyUrlSequences",
          jj,
          v91);
      goto LABEL_256;
    }
    if ( (int)STRU::Copy((STRU *)v119, String) < 0 )
      goto LABEL_159;
    v92 = STRU::QueryStr((STRU *)v119);
    _wcslwr(v92);
    v93 = STRU::QueryStr((STRU *)v119);
    if ( !MULTISZ::Append((REQUEST_FILTER_CONFIG *)((char *)this + 392), v93) )
      goto LABEL_159;
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
    STRU::~STRU((STRU *)v119);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v94 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"denyQueryStringSequences",
          &v110);
  v13 = v94;
  if ( v94 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        1155,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementProperty failed on %S - 0x%08x.\r\n",
        L"denyQueryStringSequences",
        v94);
    goto LABEL_13;
  }
  v95 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  v13 = v95;
  if ( v95 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        1167,
        "REQUEST_FILTER_CONFIG::Create",
        "GetDefaultCollection failed on %S - error 0x%08x.\r\n",
        L"denyQueryStringSequences",
        v95);
    goto LABEL_13;
  }
  v96 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  v13 = v96;
  if ( v96 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
        1179,
        "REQUEST_FILTER_CONFIG::Create",
        "GetElementCount failed on %S - error 0x%08x.\r\n",
        L"denyQueryStringSequences",
        v96);
    goto LABEL_13;
  }
  for ( kk = 0; kk < v111; ++kk )
  {
    String = 0;
    STRU::STRU((STRU *)v119);
    v98 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            kk,
            &v112);
    v13 = v98;
    if ( v98 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          1196,
          "REQUEST_FILTER_CONFIG::Create",
          "GetElementByIndex failed on %S - error 0x%08x.\r\n",
          L"denyQueryStringSequences",
          v98);
      goto LABEL_256;
    }
    v99 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v112 + 64LL))(
            v112,
            L"sequence",
            &String,
            0,
            0);
    v13 = v99;
    if ( v99 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\config.cxx",
          1210,
          "REQUEST_FILTER_CONFIG::Create",
          "GetStringProperty failed on %S, iteration %d.  Error 0x%08x\r\n",
          L"denyQueryStringSequences",
          kk,
          v99);
      goto LABEL_256;
    }
    if ( (int)STRU::Copy((STRU *)v119, String) < 0 )
      goto LABEL_159;
    v100 = STRU::QueryStr((STRU *)v119);
    _wcslwr(v100);
    v101 = STRU::QueryStr((STRU *)v119);
    if ( !MULTISZ::Append((REQUEST_FILTER_CONFIG *)((char *)this + 448), v101) )
      goto LABEL_159;
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
    STRU::~STRU((STRU *)v119);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v115 + 32LL))(
          v115,
          L"filteringRules",
          &v110);
  if ( v13 < 0 )
    goto LABEL_13;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 40LL))(v110, &v109);
  if ( v13 < 0 )
    goto LABEL_13;
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v109 + 24LL))(v109, &v111);
  if ( v13 < 0 )
    goto LABEL_13;
  v102 = v111;
  *((_DWORD *)this + 146) = v111;
  if ( (_DWORD)v102 )
  {
    v103 = LocalAlloc(0x40u, 240 * v102);
    *((_QWORD *)this + 72) = v103;
    if ( !v103 )
    {
      v13 = -2147024882;
      goto LABEL_13;
    }
  }
  for ( mm = 0; mm < v111; ++mm )
  {
    STRU::STRU((STRU *)v119);
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v109 + 32LL))(
            v109,
            mm,
            &v112);
    if ( v13 < 0 )
      goto LABEL_256;
    v105 = (STRU *)operator new(0xF0u);
    v106 = v105;
    if ( v105 )
    {
      STRU::STRU(v105);
      MULTISZA::MULTISZA((STRU *)((char *)v106 + 72));
      MULTISZ::MULTISZ((STRU *)((char *)v106 + 128));
      MULTISZ::MULTISZ((STRU *)((char *)v106 + 184));
    }
    else
    {
      v106 = 0;
    }
    v107 = 8LL * mm;
    *(_QWORD *)(v107 + *((_QWORD *)this + 72)) = v106;
    v108 = *(FILTERING_RULE **)(v107 + *((_QWORD *)this + 72));
    if ( !v108 )
      goto LABEL_159;
    v13 = FILTERING_RULE::Create(v108, v112);
    if ( v13 < 0 )
      goto LABEL_256;
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v112 + 16LL))(v112);
    v112 = 0;
    STRU::~STRU((STRU *)v119);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  v109 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  v110 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
  v115 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
  return 0;
}

```

## disassembly

```asm
0x180003080  push    rbp
0x180003082  push    rbx
0x180003083  push    rsi
0x180003084  push    rdi
0x180003085  push    r12
0x180003087  push    r13
0x180003089  push    r14
0x18000308b  push    r15
0x18000308d  lea     rbp, [rsp-1Fh]
0x180003092  sub     rsp, 0D8h
0x180003099  mov     rax, cs:__security_cookie
0x1800030a0  xor     rax, rsp
0x1800030a3  mov     [rbp+57h+var_48], rax
0x1800030a7  mov     rax, [rdx]
0x1800030aa  xor     r13d, r13d
0x1800030ad  mov     rdi, rcx
0x1800030b0  mov     [rbp+57h+var_88], r13
0x1800030b4  mov     rcx, rdx
0x1800030b7  mov     [rbp+57h+var_A0], r13
0x1800030bb  mov     r12, r9
0x1800030be  mov     [rbp+57h+var_C8], r13
0x1800030c2  mov     rax, [rax+0A0h]
0x1800030c9  mov     rsi, r8
0x1800030cc  mov     r15, rdx
0x1800030cf  mov     [rbp+57h+var_98], r13
0x1800030d3  mov     [rbp+57h+var_D0], r13
0x1800030d7  mov     [rbp+57h+var_B8], r13
0x1800030db  mov     [rbp+57h+var_C0], r13d
0x1800030df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e4  mov     rdx, rax
0x1800030e7  mov     rcx, [rax]
0x1800030ea  mov     rax, [rcx]
0x1800030ed  mov     rcx, rdx
0x1800030f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f5  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800030fc  mov     r14, rax
0x1800030ff  mov     rdx, [rcx]
0x180003102  mov     rax, [rdx+38h]
0x180003106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310b  mov     r9, rax
0x18000310e  lea     r8, [rbp+57h+var_88]
0x180003112  lea     rdx, IID_INativeConfigurationSystem
0x180003119  mov     rcx, [rax]
0x18000311c  mov     rax, [rcx]
0x18000311f  mov     rcx, r9
0x180003122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003127  mov     ebx, eax
0x180003129  test    eax, eax
0x18000312b  js      loc_18000330B
0x180003131  mov     rcx, [rbp+57h+var_88]
0x180003135  lea     r9, [rbp+57h+var_A0]
0x180003139  mov     [rsp+110h+var_E8], r13
0x18000313e  mov     r8, r14
0x180003141  mov     [rsp+110h+var_F0], rsi
0x180003146  lea     rsi, aSystemWebserve; "system.webServer/security/requestFilter"...
0x18000314d  mov     rdx, rsi
0x180003150  mov     rax, [rcx]
0x180003153  mov     rax, [rax+18h]
0x180003157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000315c  mov     ebx, eax
0x18000315e  test    eax, eax
0x180003160  js      loc_180003529
0x180003166  mov     rcx, [rbp+57h+var_A0]
0x18000316a  lea     rsi, aAllowdoubleesc; "allowDoubleEscaping"
0x180003171  lea     r8, [rdi+8]
0x180003175  mov     [rsp+110h+var_F0], r13
0x18000317a  xor     r9d, r9d
0x18000317d  mov     rdx, rsi
0x180003180  mov     rax, [rcx]
0x180003183  mov     rax, [rax+48h]
0x180003187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318c  mov     ebx, eax
0x18000318e  test    eax, eax
0x180003190  js      loc_18000355D
0x180003196  mov     rcx, [rbp+57h+var_A0]
0x18000319a  lea     rsi, aAllowhighbitch; "allowHighBitCharacters"
0x1800031a1  lea     r8, [rdi+0Ch]
0x1800031a5  mov     [rsp+110h+var_F0], r13
0x1800031aa  xor     r9d, r9d
0x1800031ad  mov     rdx, rsi
0x1800031b0  mov     rax, [rcx]
0x1800031b3  mov     rax, [rax+48h]
0x1800031b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bc  mov     ebx, eax
0x1800031be  test    eax, eax
0x1800031c0  js      loc_180003591
0x1800031c6  mov     rcx, [rbp+57h+var_A0]
0x1800031ca  lea     rsi, aRemoveserverhe; "removeServerHeader"
0x1800031d1  lea     r8, [rdi+10h]
0x1800031d5  mov     [rsp+110h+var_F0], r13
0x1800031da  xor     r9d, r9d
0x1800031dd  mov     rdx, rsi
0x1800031e0  mov     rax, [rcx]
0x1800031e3  mov     rax, [rax+48h]
0x1800031e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ec  mov     ebx, eax
0x1800031ee  test    eax, eax
0x1800031f0  js      loc_1800035C5
0x1800031f6  mov     rcx, [rbp+57h+var_A0]
0x1800031fa  lea     rsi, aUnescapequerys; "unescapeQueryString"
0x180003201  lea     r8, [rdi+14h]
0x180003205  mov     [rsp+110h+var_F0], r13
0x18000320a  xor     r9d, r9d
0x18000320d  mov     rdx, rsi
0x180003210  mov     rax, [rcx]
0x180003213  mov     rax, [rax+48h]
0x180003217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321c  mov     ebx, eax
0x18000321e  test    eax, eax
0x180003220  js      loc_1800035F9
0x180003226  mov     rcx, [rbp+57h+var_A0]
0x18000322a  lea     r14, aFileextensions; "fileExtensions"
0x180003231  lea     r8, [rbp+57h+var_C8]
0x180003235  mov     rdx, r14
0x180003238  mov     rax, [rcx]
0x18000323b  mov     rax, [rax+20h]
0x18000323f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003244  mov     ebx, eax
0x180003246  test    eax, eax
0x180003248  js      loc_18000362D
0x18000324e  mov     rcx, [rbp+57h+var_C8]
0x180003252  lea     rsi, aAllowunlisted; "allowUnlisted"
0x180003259  lea     r8, [rdi+24h]
0x18000325d  mov     [rsp+110h+var_F0], r13
0x180003262  xor     r9d, r9d
0x180003265  mov     rdx, rsi
0x180003268  mov     rax, [rcx]
0x18000326b  mov     rax, [rax+48h]
0x18000326f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003274  mov     ebx, eax
0x180003276  test    eax, eax
0x180003278  js      loc_180003661
0x18000327e  mov     rcx, [rbp+57h+var_C8]
0x180003282  lea     rsi, aApplytowebdav; "applyToWebDAV"
0x180003289  lea     r8, [rdi+2Ch]
0x18000328d  mov     [rsp+110h+var_F0], r13
0x180003292  xor     r9d, r9d
0x180003295  mov     rdx, rsi
0x180003298  mov     rax, [rcx]
0x18000329b  mov     rax, [rax+48h]
0x18000329f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a4  mov     ebx, eax
0x1800032a6  test    eax, eax
0x1800032a8  js      loc_180003695
0x1800032ae  mov     rcx, [rbp+57h+var_C8]
0x1800032b2  lea     rdx, [rbp+57h+var_D0]
0x1800032b6  mov     rax, [rcx]
0x1800032b9  mov     rax, [rax+28h]
0x1800032bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c2  mov     ebx, eax
0x1800032c4  test    eax, eax
0x1800032c6  jns     loc_180003387
0x1800032cc  test    byte ptr cs:g_dwDebugFlags, 3
0x1800032d3  jz      short loc_18000330B
0x1800032d5  mov     [rsp+110h+var_E0], eax
0x1800032d9  lea     r9, aRequestFilterC; "REQUEST_FILTER_CONFIG::Create"
0x1800032e0  lea     rax, aGetdefaultcoll; "GetDefaultCollection failed on %S - err"...
0x1800032e7  mov     [rsp+110h+var_E8], r14
0x1800032ec  mov     [rsp+110h+var_F0], rax
0x1800032f1  mov     r8d, 0F1h
0x1800032f7  mov     rcx, cs:g_pDebug
0x1800032fe  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003305  call    cs:__imp_PuDbgPrint
0x18000330b  mov     rcx, [rbp+57h+var_B8]
0x18000330f  test    rcx, rcx
0x180003312  jnz     loc_180004FE2
0x180003318  mov     rcx, [rbp+57h+var_D0]
0x18000331c  test    rcx, rcx
0x18000331f  jz      short loc_180003331
0x180003321  mov     rax, [rcx]
0x180003324  mov     rax, [rax+10h]
0x180003328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332d  mov     [rbp+57h+var_D0], r13
0x180003331  mov     rcx, [rbp+57h+var_C8]
0x180003335  test    rcx, rcx
0x180003338  jnz     loc_180004FF7
0x18000333e  mov     rcx, [rbp+57h+var_98]
0x180003342  test    rcx, rcx
0x180003345  jnz     loc_18000500C
0x18000334b  mov     rcx, [rbp+57h+var_A0]
0x18000334f  test    rcx, rcx
0x180003352  jnz     loc_180005021
0x180003358  mov     rcx, [rbp+57h+var_88]
0x18000335c  test    rcx, rcx
0x18000335f  jnz     loc_180005036
0x180003365  mov     eax, ebx
0x180003367  mov     rcx, [rbp+57h+var_48]
0x18000336b  xor     rcx, rsp; StackCookie
0x18000336e  call    __security_check_cookie
0x180003373  add     rsp, 0D8h
0x18000337a  pop     r15
0x18000337c  pop     r14
0x18000337e  pop     r13
0x180003380  pop     r12
0x180003382  pop     rdi
0x180003383  pop     rsi
0x180003384  pop     rbx
0x180003385  pop     rbp
0x180003386  retn
0x180003387  mov     rcx, [rbp+57h+var_D0]
0x18000338b  lea     rdx, [rbp+57h+var_C0]
0x18000338f  mov     rax, [rcx]
0x180003392  mov     rax, [rax+18h]
0x180003396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339b  mov     ebx, eax
0x18000339d  test    eax, eax
0x18000339f  js      loc_1800036C9
0x1800033a5  mov     esi, r13d
0x1800033a8  mov     rcx, [rbp+57h+var_D0]
0x1800033ac  cmp     esi, [rbp+57h+var_C0]
0x1800033af  jb      loc_1800036FD
0x1800033b5  mov     rax, [rcx]
0x1800033b8  mov     rax, [rax+10h]
0x1800033bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c1  mov     rcx, [rbp+57h+var_C8]
0x1800033c5  mov     [rbp+57h+var_D0], r13
0x1800033c9  mov     rax, [rcx]
0x1800033cc  mov     rax, [rax+10h]
0x1800033d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d5  mov     rcx, [rbp+57h+var_A0]
0x1800033d9  lea     rsi, aRequestlimits; "requestLimits"
0x1800033e0  mov     [rbp+57h+var_C8], r13
0x1800033e4  lea     r8, [rbp+57h+var_C8]
0x1800033e8  mov     rdx, rsi
0x1800033eb  mov     rax, [rcx]
0x1800033ee  mov     rax, [rax+20h]
0x1800033f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f7  mov     ebx, eax
0x1800033f9  test    eax, eax
0x1800033fb  js      loc_18000389B
0x180003401  mov     rcx, [rbp+57h+var_C8]
0x180003405  lea     rsi, aMaxallowedcont; "maxAllowedContentLength"
0x18000340c  lea     r8, [rdi+18h]
0x180003410  mov     [rsp+110h+var_F0], r13
0x180003415  xor     r9d, r9d
0x180003418  mov     rdx, rsi
0x18000341b  mov     rax, [rcx]
0x18000341e  mov     rax, [rax+30h]
0x180003422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003427  mov     ebx, eax
0x180003429  test    eax, eax
0x18000342b  js      loc_1800038CF
0x180003431  mov     rcx, [rbp+57h+var_C8]
0x180003435  lea     rsi, aMaxurl; "maxUrl"
0x18000343c  lea     r8, [rdi+1Ch]
0x180003440  mov     [rsp+110h+var_F0], r13
0x180003445  xor     r9d, r9d
0x180003448  mov     rdx, rsi
0x18000344b  mov     rax, [rcx]
0x18000344e  mov     rax, [rax+30h]
0x180003452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003457  mov     ebx, eax
0x180003459  test    eax, eax
0x18000345b  js      loc_180003903
0x180003461  mov     rcx, [rbp+57h+var_C8]
0x180003465  lea     rsi, aMaxquerystring; "maxQueryString"
0x18000346c  lea     r8, [rdi+20h]
0x180003470  mov     [rsp+110h+var_F0], r13
0x180003475  xor     r9d, r9d
0x180003478  mov     rdx, rsi
0x18000347b  mov     rax, [rcx]
0x18000347e  mov     rax, [rax+30h]
0x180003482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003487  mov     ebx, eax
0x180003489  test    eax, eax
0x18000348b  js      loc_180003937
0x180003491  mov     rcx, [rbp+57h+var_C8]
0x180003495  lea     r14, aHeaderlimits; "headerLimits"
0x18000349c  lea     r8, [rbp+57h+var_98]
0x1800034a0  mov     rdx, r14
0x1800034a3  mov     rax, [rcx]
0x1800034a6  mov     rax, [rax+20h]
0x1800034aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034af  mov     ebx, eax
0x1800034b1  test    eax, eax
0x1800034b3  js      loc_18000396B
0x1800034b9  mov     rcx, [rbp+57h+var_98]
0x1800034bd  lea     rdx, [rbp+57h+var_D0]
0x1800034c1  mov     rax, [rcx]
0x1800034c4  mov     rax, [rax+28h]
0x1800034c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034cd  mov     ebx, eax
0x1800034cf  test    eax, eax
0x1800034d1  js      loc_18000399F
0x1800034d7  mov     rcx, [rbp+57h+var_D0]
0x1800034db  lea     rdx, [rbp+57h+var_C0]
0x1800034df  mov     rax, [rcx]
0x1800034e2  mov     rax, [rax+18h]
0x1800034e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034eb  mov     ebx, eax
0x1800034ed  test    eax, eax
0x1800034ef  jns     loc_1800039D3
0x1800034f5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800034fc  jz      loc_18000330B
0x180003502  mov     [rsp+110h+var_E0], eax
0x180003506  lea     r9, aRequestFilterC; "REQUEST_FILTER_CONFIG::Create"
0x18000350d  lea     rax, aGetelementcoun; "GetElementCount failed on %S - error 0x"...
0x180003514  mov     [rsp+110h+var_E8], r14
0x180003519  mov     [rsp+110h+var_F0], rax
0x18000351e  mov     r8d, 1ABh
  ... truncated ...
```
