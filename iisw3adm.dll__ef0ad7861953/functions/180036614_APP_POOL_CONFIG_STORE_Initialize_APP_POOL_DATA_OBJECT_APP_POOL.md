# APP_POOL_CONFIG_STORE::Initialize(APP_POOL_DATA_OBJECT *,APP_POOL *)

- ea: `0x180036614`
- end: `0x18003722e`
- name: `?Initialize@APP_POOL_CONFIG_STORE@@QEAAXPEAVAPP_POOL_DATA_OBJECT@@PEAVAPP_POOL@@@Z`
- size: `3098`
- prototype: `void __fastcall(APP_POOL_CONFIG_STORE *__hidden this, struct APP_POOL_DATA_OBJECT *, struct APP_POOL *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019e7c`

## callees

- `0x180007c0c`
- `0x180035de8`
- `0x180036614`
- `0x180037234`
- `0x18003d890`
- `0x180061002`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180036f13`
- `msvcrt!memcpy_s` at `0x180036f13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f33`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003715f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003715f`
- `iisutil!PuDbgPrint` at `0x180036dac`
- `iisutil!PuDbgPrint` at `0x1800371fd`
- `iisutil!PuDbgPrint` at `0x180036dac`
- `iisutil!PuDbgPrint` at `0x1800371fd`
- `iisutil!PuDbgPrintError` at `0x180036768`
- `iisutil!PuDbgPrintError` at `0x1800367ab`
- `iisutil!PuDbgPrintError` at `0x1800367ee`
- `iisutil!PuDbgPrintError` at `0x180036d5b`
- `iisutil!PuDbgPrintError` at `0x180036e70`
- `iisutil!PuDbgPrintError` at `0x180036ee1`
- `iisutil!PuDbgPrintError` at `0x180036f75`
- `iisutil!PuDbgPrintError` at `0x180036fdc`
- `iisutil!PuDbgPrintError` at `0x18003702f`
- `iisutil!PuDbgPrintError` at `0x18003707d`
- `iisutil!PuDbgPrintError` at `0x1800370d3`
- `iisutil!PuDbgPrintError` at `0x180037121`
- `iisutil!PuDbgPrintError` at `0x1800371a2`
- `iisutil!PuDbgPrintError` at `0x180036768`
- `iisutil!PuDbgPrintError` at `0x1800367ab`
- `iisutil!PuDbgPrintError` at `0x1800367ee`
- `iisutil!PuDbgPrintError` at `0x180036d5b`
- `iisutil!PuDbgPrintError` at `0x180036e70`
- `iisutil!PuDbgPrintError` at `0x180036ee1`
- `iisutil!PuDbgPrintError` at `0x180036f75`
- `iisutil!PuDbgPrintError` at `0x180036fdc`
- `iisutil!PuDbgPrintError` at `0x18003702f`
- `iisutil!PuDbgPrintError` at `0x18003707d`
- `iisutil!PuDbgPrintError` at `0x1800370d3`
- `iisutil!PuDbgPrintError` at `0x180037121`
- `iisutil!PuDbgPrintError` at `0x1800371a2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180036724`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003677c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800367bf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180037000`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003704e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800370a4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800370f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180036724`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003677c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800367bf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180037000`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003704e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800370a4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800370f2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180036e98`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180036e98`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180036dff`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180036dff`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180036df4`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180036df4`
- `iisutil!??0MULTISZ@@QEAA@PEBG@Z` at `0x180036de2`
- `iisutil!??0MULTISZ@@QEAA@PEBG@Z` at `0x180036de2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036d04`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036d04`
- `CRYPT32!CryptProtectMemory` at `0x180036f29`
- `CRYPT32!CryptProtectMemory` at `0x180036f29`

## string_xrefs

- `0x180036738`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036d43`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036d84`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036e58`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036ec9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036f49`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036f7d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036731`: `APP_POOL_CONFIG_STORE::Initialize`
- `0x180036d28`: `APP_POOL_CONFIG_STORE::Initialize`
- `0x180036d63`: `APP_POOL_CONFIG_STORE::Initialize`
- `0x180036d34`: `Failed to convert Sid to string, ignoring and continuing\n`
- `0x180036da0`: ` Worker Process Identity SID as string = %S \n`

## pseudocode

```c
void __fastcall APP_POOL_CONFIG_STORE::Initialize(
        APP_POOL_CONFIG_STORE *this,
        struct APP_POOL_DATA_OBJECT *a2,
        struct APP_POOL *a3)
{
  _QWORD **v3; // rsi
  _QWORD *i; // rax
  struct CONFIG_ERROR *v7; // r8
  _QWORD *j; // rax
  struct CONFIG_ERROR *v9; // r8
  _QWORD *k; // rax
  struct CONFIG_ERROR *v11; // r8
  _QWORD *m; // rax
  struct CONFIG_ERROR *v13; // r8
  int v14; // eax
  int v15; // eax
  int v16; // eax
  _QWORD *n; // rax
  struct CONFIG_ERROR *v18; // r8
  _QWORD *ii; // rax
  struct CONFIG_ERROR *v20; // r8
  _QWORD *jj; // rax
  struct CONFIG_ERROR *v22; // r8
  _QWORD *kk; // rax
  struct CONFIG_ERROR *v24; // r8
  WMS_ERROR_LOGGER *v25; // rcx
  unsigned int v26; // r9d
  _QWORD *mm; // rax
  struct CONFIG_ERROR *v28; // r8
  int v29; // eax
  _QWORD *nn; // rax
  struct CONFIG_ERROR *v31; // r8
  _QWORD *i1; // rax
  struct CONFIG_ERROR *v33; // r8
  _QWORD *i2; // rax
  struct CONFIG_ERROR *v35; // r8
  _QWORD *i3; // rax
  struct CONFIG_ERROR *v37; // r8
  _QWORD *i4; // rax
  struct CONFIG_ERROR *v39; // r8
  _QWORD *i5; // rax
  struct CONFIG_ERROR *v41; // r8
  int v42; // eax
  _QWORD *i6; // rax
  struct CONFIG_ERROR *v44; // r8
  _DWORD *v45; // rbx
  _QWORD *i7; // rax
  struct CONFIG_ERROR *v47; // r8
  _QWORD *i8; // rax
  struct CONFIG_ERROR *v49; // r8
  int v50; // eax
  _QWORD *v51; // rax
  struct CONFIG_ERROR *v52; // r8
  _QWORD *i9; // rax
  struct CONFIG_ERROR *v54; // r8
  signed int LastError; // eax
  int v56; // edx
  int v57; // eax
  size_t v58; // rbx
  signed int v59; // eax
  signed int v60; // eax
  unsigned __int16 *v61; // rdx
  int v62; // eax
  const unsigned __int16 *v63; // rdx
  int v64; // eax
  const unsigned __int16 *v65; // rdx
  int v66; // eax
  const unsigned __int16 *v67; // rdx
  int v68; // eax
  const unsigned __int16 *v69; // rdx
  int v70; // eax
  _WORD *v71; // rax
  int i10; // edx
  bool v73; // zf
  _WORD *v74; // rcx
  SIZE_T v75; // rbx
  HGLOBAL v76; // rax
  int v77; // [rsp+20h] [rbp-A8h]
  unsigned int v78; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v79[56]; // [rsp+48h] [rbp-80h] BYREF

  *((_QWORD *)this + 92) = a3;
  v3 = (_QWORD **)((char *)a2 + 1000);
  for ( i = (_QWORD *)*((_QWORD *)a2 + 125); i != v3; i = (_QWORD *)*i )
  {
    v7 = (struct CONFIG_ERROR *)*(i - 1);
    if ( *((_DWORD *)v7 + 2) == 15 )
      goto LABEL_6;
  }
  v7 = 0;
LABEL_6:
  ApplyRangeCheck(*((_DWORD *)a2 + 56), *((const unsigned __int16 **)a2 + 10), v7, (unsigned int *)this + 14);
  for ( j = *v3; j != v3; j = (_QWORD *)*j )
  {
    v9 = (struct CONFIG_ERROR *)*(j - 1);
    if ( *((_DWORD *)v9 + 2) == 16 )
      goto LABEL_11;
  }
  v9 = 0;
LABEL_11:
  ApplyRangeCheck(*((_DWORD *)a2 + 57), *((const unsigned __int16 **)a2 + 10), v9, (unsigned int *)this + 15);
  for ( k = *v3; k != v3; k = (_QWORD *)*k )
  {
    v11 = (struct CONFIG_ERROR *)*(k - 1);
    if ( *((_DWORD *)v11 + 2) == 39 )
      goto LABEL_16;
  }
  v11 = 0;
LABEL_16:
  ApplyRangeCheck(*((_DWORD *)a2 + 180), *((const unsigned __int16 **)a2 + 10), v11, (unsigned int *)this + 98);
  for ( m = *v3; m != v3; m = (_QWORD *)*m )
  {
    v13 = (struct CONFIG_ERROR *)*(m - 1);
    if ( *((_DWORD *)v13 + 2) == 22 )
      goto LABEL_21;
  }
  v13 = 0;
LABEL_21:
  ApplyRangeCheck(*((_DWORD *)a2 + 90), *((const unsigned __int16 **)a2 + 10), v13, (unsigned int *)this + 54);
  v14 = STRU::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 408), *((const unsigned __int16 **)a2 + 97));
  if ( v14 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
      405,
      "APP_POOL_CONFIG_STORE::Initialize",
      v14,
      "Allocating memory failed, ignoring and continuing\n");
  v15 = STRU::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 464), *((const unsigned __int16 **)a2 + 104));
  if ( v15 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
      419,
      "APP_POOL_CONFIG_STORE::Initialize",
      v15,
      "Allocating memory failed, ignoring and continuing\n");
  v16 = STRU::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 520), *((const unsigned __int16 **)a2 + 111));
  if ( v16 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
      436,
      "APP_POOL_CONFIG_STORE::Initialize",
      v16,
      "Allocating memory failed, ignoring and continuing\n");
  *((_DWORD *)this + 144) = *((_DWORD *)a2 + 228);
  if ( *((_DWORD *)g_pWebAdminService + 412) )
  {
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 25) = 0;
    *((_DWORD *)this + 52) = 0;
    *((_DWORD *)this + 53) = 1;
    *(_QWORD *)((char *)this + 220) = 1;
    *((_QWORD *)this + 29) = 0;
    *((_QWORD *)this + 30) = 0;
    *((_QWORD *)this + 31) = 0;
    *((_QWORD *)this + 32) = 0;
    *((_QWORD *)this + 33) = 0;
    *((_DWORD *)this + 68) = 1;
    *(_QWORD *)((char *)this + 396) = 1;
    *((_DWORD *)this + 101) = 0;
    *((_DWORD *)this + 180) = 1;
    *((_DWORD *)this + 181) = 1;
    *((_DWORD *)this + 145) = 0;
    *((_DWORD *)this + 146) = 1;
    *((_QWORD *)this + 81) = 0;
    *((_QWORD *)this + 94) = 0;
    APP_POOL_CONFIG_STORE::SetTokenForWorkerProcesses(this, 0, 0, 0, 1u, 1, *((const unsigned __int16 **)a2 + 10), 0);
    return;
  }
  for ( n = *v3; n != v3; n = (_QWORD *)*n )
  {
    v18 = (struct CONFIG_ERROR *)*(n - 1);
    if ( *((_DWORD *)v18 + 2) == 1 )
      goto LABEL_37;
  }
  v18 = 0;
LABEL_37:
  ApplyRangeCheck(*((_DWORD *)a2 + 26), *((const unsigned __int16 **)a2 + 10), v18, (unsigned int *)this + 4);
  *((_DWORD *)this + 5) = *((_DWORD *)a2 + 27);
  for ( ii = *v3; ii != v3; ii = (_QWORD *)*ii )
  {
    v20 = (struct CONFIG_ERROR *)*(ii - 1);
    if ( *((_DWORD *)v20 + 2) == 3 )
      goto LABEL_42;
  }
  v20 = 0;
LABEL_42:
  ApplyRangeCheck(*((_DWORD *)a2 + 28), *((const unsigned __int16 **)a2 + 10), v20, (unsigned int *)this + 8);
  for ( jj = *v3; jj != v3; jj = (_QWORD *)*jj )
  {
    v22 = (struct CONFIG_ERROR *)*(jj - 1);
    if ( *((_DWORD *)v22 + 2) == 4 )
      goto LABEL_47;
  }
  v22 = 0;
LABEL_47:
  ApplyRangeCheck(*((_DWORD *)a2 + 29), *((const unsigned __int16 **)a2 + 10), v22, (unsigned int *)this + 9);
  for ( kk = *v3; kk != v3; kk = (_QWORD *)*kk )
  {
    v24 = (struct CONFIG_ERROR *)*(kk - 1);
    if ( *((_DWORD *)v24 + 2) == 8 )
      goto LABEL_52;
  }
  v24 = 0;
LABEL_52:
  ApplyRangeCheck(*((_DWORD *)a2 + 45), *((const unsigned __int16 **)a2 + 10), v24, (unsigned int *)this + 11);
  v26 = *((_DWORD *)this + 4);
  if ( *((_DWORD *)this + 11) >= v26 && v26 )
    WMS_ERROR_LOGGER::LogIdleTimeoutGreaterThanRestartPeriod(
      v25,
      *((const unsigned __int16 **)a2 + 10),
      *((_DWORD *)this + 11),
      v26,
      v77);
  for ( mm = *v3; mm != v3; mm = (_QWORD *)*mm )
  {
    v28 = (struct CONFIG_ERROR *)*(mm - 1);
    if ( *((_DWORD *)v28 + 2) == 9 )
      goto LABEL_60;
  }
  v28 = 0;
LABEL_60:
  ApplyRangeCheck(*((_DWORD *)a2 + 46), *((const unsigned __int16 **)a2 + 10), v28, (unsigned int *)this + 12);
  *((_DWORD *)this + 13) = *((_DWORD *)a2 + 55);
  v29 = *((_DWORD *)a2 + 47);
  *((_DWORD *)this + 10) = v29;
  if ( v29 )
  {
    for ( nn = *v3; nn != v3; nn = (_QWORD *)*nn )
    {
      v31 = (struct CONFIG_ERROR *)*(nn - 1);
      if ( *((_DWORD *)v31 + 2) == 17 )
        goto LABEL_66;
    }
    v31 = 0;
LABEL_66:
    ApplyRangeCheck(*((_DWORD *)a2 + 58), *((const unsigned __int16 **)a2 + 10), v31, (unsigned int *)this + 16);
    for ( i1 = *v3; i1 != v3; i1 = (_QWORD *)*i1 )
    {
      v33 = (struct CONFIG_ERROR *)*(i1 - 1);
      if ( *((_DWORD *)v33 + 2) == 18 )
        goto LABEL_71;
    }
    v33 = 0;
LABEL_71:
    ApplyRangeCheck(*((_DWORD *)a2 + 59), *((const unsigned __int16 **)a2 + 10), v33, (unsigned int *)this + 17);
  }
  for ( i2 = *v3; i2 != v3; i2 = (_QWORD *)*i2 )
  {
    v35 = (struct CONFIG_ERROR *)*(i2 - 1);
    if ( *((_DWORD *)v35 + 2) == 31 )
      goto LABEL_77;
  }
  v35 = 0;
LABEL_77:
  ApplyRangeCheck(*((_DWORD *)a2 + 145), *((const unsigned __int16 **)a2 + 10), v35, (unsigned int *)this + 50);
  for ( i3 = *v3; i3 != v3; i3 = (_QWORD *)*i3 )
  {
    v37 = (struct CONFIG_ERROR *)*(i3 - 1);
    if ( *((_DWORD *)v37 + 2) == 32 )
      goto LABEL_82;
  }
  v37 = 0;
LABEL_82:
  ApplyRangeCheck(*((_DWORD *)a2 + 146), *((const unsigned __int16 **)a2 + 10), v37, (unsigned int *)this + 51);
  for ( i4 = *v3; i4 != v3; i4 = (_QWORD *)*i4 )
  {
    v39 = (struct CONFIG_ERROR *)*(i4 - 1);
    if ( *((_DWORD *)v39 + 2) == 33 )
      goto LABEL_87;
  }
  v39 = 0;
LABEL_87:
  ApplyRangeCheck(*((_DWORD *)a2 + 147), *((const unsigned __int16 **)a2 + 10), v39, (unsigned int *)this + 52);
  *((_DWORD *)this + 53) = *((_DWORD *)a2 + 91);
  for ( i5 = *v3; i5 != v3; i5 = (_QWORD *)*i5 )
  {
    v41 = (struct CONFIG_ERROR *)*(i5 - 1);
    if ( *((_DWORD *)v41 + 2) == 6 )
      goto LABEL_92;
  }
  v41 = 0;
LABEL_92:
  ApplyRangeCheck(*((_DWORD *)a2 + 44), *((const unsigned __int16 **)a2 + 10), v41, (unsigned int *)this + 55);
  if ( !*((_DWORD *)this + 55) )
    *((_DWORD *)this + 55) = *((_DWORD *)g_pWebAdminService + 167);
  v42 = *((_DWORD *)a2 + 49);
  *((_DWORD *)this + 56) = v42;
  if ( v42 )
    *((_QWORD *)this + 29) = *((_QWORD *)a2 + 25);
  for ( i6 = *v3; i6 != v3; i6 = (_QWORD *)*i6 )
  {
    v44 = (struct CONFIG_ERROR *)*(i6 - 1);
    if ( *((_DWORD *)v44 + 2) == 47 )
      goto LABEL_101;
  }
  v44 = 0;
LABEL_101:
  v45 = (_DWORD *)((char *)this + 240);
  ApplyRangeCheck(*((_DWORD *)a2 + 52), *((const unsigned __int16 **)a2 + 10), v44, (unsigned int *)this + 60);
  if ( *((_DWORD *)this + 56) && *(_WORD *)v45 >= *((_WORD *)g_pWebAdminService + 332) )
    *v45 = 0;
  for ( i7 = *v3; i7 != v3; i7 = (_QWORD *)*i7 )
  {
    v47 = (struct CONFIG_ERROR *)*(i7 - 1);
    if ( *((_DWORD *)v47 + 2) == 48 )
      goto LABEL_109;
  }
  v47 = 0;
LABEL_109:
  ApplyRangeCheck(*((_DWORD *)a2 + 53), *((const unsigned __int16 **)a2 + 10), v47, (unsigned int *)this + 61);
  for ( i8 = *v3; i8 != v3; i8 = (_QWORD *)*i8 )
  {
    v49 = (struct CONFIG_ERROR *)*(i8 - 1);
    if ( *((_DWORD *)v49 + 2) == 49 )
      goto LABEL_114;
  }
  v49 = 0;
LABEL_114:
  ApplyRangeCheck(*((_DWORD *)a2 + 54), *((const unsigned __int16 **)a2 + 10), v49, (unsigned int *)this + 62);
  v50 = *((_DWORD *)a2 + 48);
  *((_DWORD *)this + 63) = v50;
  if ( v50 )
  {
    v51 = *v3;
    v78 = 0;
    while ( v51 != v3 )
    {
      v52 = (struct CONFIG_ERROR *)*(v51 - 1);
      if ( *((_DWORD *)v52 + 2) == 35 )
        goto LABEL_120;
      v51 = (_QWORD *)*v51;
    }
    v52 = 0;
LABEL_120:
    ApplyRangeCheck(*((_DWORD *)a2 + 150), *((const unsigned __int16 **)a2 + 10), v52, &v78);
    *((_DWORD *)this + 64) = 60000 * v78;
    for ( i9 = *v3; i9 != v3; i9 = (_QWORD *)*i9 )
    {
      v54 = (struct CONFIG_ERROR *)*(i9 - 1);
      if ( *((_DWORD *)v54 + 2) == 36 )
        goto LABEL_125;
    }
    v54 = 0;
LABEL_125:
    ApplyRangeCheck(*((_DWORD *)a2 + 151), *((const unsigned __int16 **)a2 + 10), v54, (unsigned int *)this + 65);
  }
  *((_DWORD *)this + 66) = *((_DWORD *)a2 + 181);
  *((_DWORD *)this + 67) = *((_DWORD *)a2 + 182);
  *((_DWORD *)this + 68) = *((_DWORD *)a2 + 60);
  *((_DWORD *)this + 99) = *((_DWORD *)a2 + 149);
  *((_DWORD *)this + 100) = *((_DWORD *)a2 + 183);
  *((_DWORD *)this + 101) = *((_DWORD *)a2 + 184);
  *((_DWORD *)this + 180) = *((_DWORD *)a2 + 229);
  *((_DWORD *)this + 181) = *((_DWORD *)a2 + 230);
  if ( !ConvertSidToStringSidW(*((PSID *)a2 + 124), (LPWSTR *)this + 24) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v56 = g_dwDebugFlags;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_132;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
      738,
      "APP_POOL_CONFIG_STORE::Initialize",
      LastError,
      "Failed to convert Sid to string, ignoring and continuing\n");
  }
  v56 = g_dwDebugFlags;
LABEL_132:
  if ( (v56 & 3) != 0 && (v56 & 0x10000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
      747,
      "APP_POOL_CONFIG_STORE::Initialize",
      " Worker Process Identity SID as string = %S \n",
      *((const wchar_t **)this + 24));
  *((_DWORD *)this + 145) = *((_DWORD *)a2 + 134);
  *((_DWORD *)this + 146) = *((_DWORD *)a2 + 233);
  *((_DWORD *)this + 162) = *((_DWORD *)a2 + 135);
  MULTISZ::MULTISZ((MULTISZ *)v79, *((const unsigned __int16 **)a2 + 121));
  MULTISZ::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 592), (const struct MULTISZ *)v79);
  MULTISZ::~MULTISZ((MULTISZ *)v79);
  *((_DWORD *)this + 163) = *((_DWORD *)a2 + 144);
  *((_DWORD *)this + 188) = *((_DWORD *)a2 + 231);
  *((_DWORD *)this + 189) = *((_DWORD *)a2 + 232);
  v57 = SMALL_STRU::Copy((unsigned __int16 **)this + 82, *((unsigned __int16 **)a2 + 50));
  if ( v57 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
      775,
      "APP_POOL_CONFIG_STORE::Initialize",
      v57,
      "Allocating memory failed, ignoring and continuing\n");
  v58 = (unsigned int)(2 * *((_DWORD *)a2 + 118) + 2);
  if ( ((2 * *((_DWORD *)a2 + 118) + 2) & 0xF) != 0 )
    v58 = (unsigned int)v58 - ((2 * *((_DWORD *)a2 + 118) + 2) & 0xF) + 16;
  if ( !BUFFER::Resize((APP_POOL_CONFIG_STORE *)((char *)this + 664), v58) )
  {
    v59 = GetLastError();
    if ( v59 > 0 )
      v59 = (unsigned __int16)v59 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
        806,
        "APP_POOL_CONFIG_STORE::Initialize",
        v59,
        "Failed to allocate memory for user password, ignoring and continuing\n");
  }
  memset_0(*((void **)this + 87), 0, v58);
  memcpy_s(*((void *const *)this + 87), v58, *((const void *const *)a2 + 57), (unsigned int)(2 * *((_DWORD *)a2 + 118)));
  if ( !CryptProtectMemory(*((LPVOID *)this + 87), *((_DWORD *)this + 176), 0) )
  {
    v60 = GetLastError();
    if ( v60 > 0 )
      v60 = (unsigned __int16)v60 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
        837,
        "APP_POOL_CONFIG_STORE::Initialize",
        v60,
        "Failed to encrypt user password, ignoring and continuing\n");
  }
  *((_QWORD *)this + 91) = *((_QWORD *)a2 + 124);
  v61 = (unsigned __int16 *)*((_QWORD *)a2 + 64);
  *((_QWORD *)a2 + 124) = 0;
  v62 = SMALL_STRU::Copy((unsigned __int16 **)this + 89, v61);
  if ( v62 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
      856,
      "APP_POOL_CONFIG_STORE::Initialize",
      v62,
      "Allocating memory failed, ignoring and continuing\n");
  v63 = (const unsigned __int16 *)*((_QWORD *)a2 + 35);
  if ( v63 && *v63 )
  {
    v64 = STRU::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 72), v63);
    if ( v64 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
        877,
        "APP_POOL_CONFIG_STORE::Initialize",
        v64,
        "Allocating memory failed, ignoring and continuing\n");
    v65 = (const unsigned __int16 *)*((_QWORD *)a2 + 42);
    if ( v65 )
    {
      if ( *v65 )
      {
        v66 = STRU::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 128), v65);
        if ( v66 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
            897,
            "APP_POOL_CONFIG_STORE::Initialize",
            v66,
            "Allocating memory failed, ignoring and continuing\n");
      }
    }
  }
  v67 = (const unsigned __int16 *)*((_QWORD *)a2 + 80);
  if ( v67 && *v67 )
  {
    v68 = STRU::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 280), v67);
    if ( v68 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
        920,
        "APP_POOL_CONFIG_STORE::Initialize",
        v68,
        "Allocating memory failed, ignoring and continuing\n");
    v69 = (const unsigned __int16 *)*((_QWORD *)a2 + 87);
    if ( v69 )
    {
      if ( *v69 )
      {
        v70 = STRU::Copy((APP_POOL_CONFIG_STORE *)((char *)this + 336), v69);
        if ( v70 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
            940,
            "APP_POOL_CONFIG_STORE::Initialize",
            v70,
            "Allocating memory failed, ignoring and continuing\n");
      }
    }
  }
  v71 = (_WORD *)*((_QWORD *)a2 + 19);
  if ( v71 )
  {
    for ( i10 = 0; ; ++i10 )
    {
      v73 = *v71 == 0;
      v74 = ++v71;
      if ( v73 && !*v74 )
        break;
    }
    v75 = (unsigned int)(2 * i10 + 4);
    v76 = GlobalAlloc(0, v75);
    *((_QWORD *)this + 3) = v76;
    if ( v76 )
    {
      memcpy_0(v76, *((const void **)a2 + 19), v75);
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
          984,
          "APP_POOL_CONFIG_STORE::Initialize",
          "First entry in Schedule %S\n",
          *((const wchar_t **)a2 + 19));
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
        967,
        "APP_POOL_CONFIG_STORE::Initialize",
        -2147024888,
        "Allocating memory for pPeriodicProcessRestartSchedule failed, ignoring and continuing\n");
    }
  }
}

```

## disassembly

```asm
0x180036614  mov     [rsp+arg_10], rbx
0x180036619  push    rbp
0x18003661a  push    rsi
0x18003661b  push    rdi
0x18003661c  push    r12
0x18003661e  push    r13
0x180036620  push    r14
0x180036622  push    r15
0x180036624  sub     rsp, 90h
0x18003662b  mov     rax, cs:__security_cookie
0x180036632  xor     rax, rsp
0x180036635  mov     [rsp+0C8h+var_48], rax
0x18003663d  xor     r12d, r12d
0x180036640  mov     [rcx+2E0h], r8
0x180036647  lea     rsi, [rdx+3E8h]
0x18003664e  mov     rbp, rdx
0x180036651  mov     rax, [rsi]
0x180036654  mov     rdi, rcx
0x180036657  lea     r13d, [r12+0Fh]
0x18003665c  jmp     short loc_18003666B
0x18003665e  mov     r8, [rax-8]
0x180036662  cmp     [r8+8], r13d
0x180036666  jz      short loc_180036673
0x180036668  mov     rax, [rax]
0x18003666b  cmp     rax, rsi
0x18003666e  jnz     short loc_18003665E
0x180036670  mov     r8, r12; struct CONFIG_ERROR *
0x180036673  mov     rdx, [rdx+50h]; unsigned __int16 *
0x180036677  lea     r9, [rcx+38h]; unsigned int *
0x18003667b  mov     ecx, [rbp+0E0h]; unsigned int
0x180036681  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036686  mov     rax, [rsi]
0x180036689  jmp     short loc_180036699
0x18003668b  mov     r8, [rax-8]
0x18003668f  cmp     dword ptr [r8+8], 10h
0x180036694  jz      short loc_1800366A1
0x180036696  mov     rax, [rax]
0x180036699  cmp     rax, rsi
0x18003669c  jnz     short loc_18003668B
0x18003669e  mov     r8, r12; struct CONFIG_ERROR *
0x1800366a1  mov     rdx, [rbp+50h]; unsigned __int16 *
0x1800366a5  lea     r9, [rdi+3Ch]; unsigned int *
0x1800366a9  mov     ecx, [rbp+0E4h]; unsigned int
0x1800366af  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x1800366b4  mov     rax, [rsi]
0x1800366b7  jmp     short loc_1800366C7
0x1800366b9  mov     r8, [rax-8]
0x1800366bd  cmp     dword ptr [r8+8], 27h ; '''
0x1800366c2  jz      short loc_1800366CF
0x1800366c4  mov     rax, [rax]
0x1800366c7  cmp     rax, rsi
0x1800366ca  jnz     short loc_1800366B9
0x1800366cc  mov     r8, r12; struct CONFIG_ERROR *
0x1800366cf  mov     rdx, [rbp+50h]; unsigned __int16 *
0x1800366d3  lea     r9, [rdi+188h]; unsigned int *
0x1800366da  mov     ecx, [rbp+2D0h]; unsigned int
0x1800366e0  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x1800366e5  mov     rax, [rsi]
0x1800366e8  jmp     short loc_1800366F8
0x1800366ea  mov     r8, [rax-8]
0x1800366ee  cmp     dword ptr [r8+8], 16h
0x1800366f3  jz      short loc_180036700
0x1800366f5  mov     rax, [rax]
0x1800366f8  cmp     rax, rsi
0x1800366fb  jnz     short loc_1800366EA
0x1800366fd  mov     r8, r12; struct CONFIG_ERROR *
0x180036700  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036704  lea     r9, [rdi+0D8h]; unsigned int *
0x18003670b  mov     ecx, [rbp+168h]; unsigned int
0x180036711  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036716  mov     rdx, [rbp+308h]
0x18003671d  lea     rcx, [rdi+198h]
0x180036724  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003672a  lea     r15, aAllocatingMemo_1; "Allocating memory failed, ignoring and "...
0x180036731  lea     rbx, aAppPoolConfigS; "APP_POOL_CONFIG_STORE::Initialize"
0x180036738  lea     r14, aServercommonIn_48; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18003673f  test    eax, eax
0x180036741  jns     short loc_18003676E
0x180036743  test    byte ptr cs:g_dwDebugFlags, r13b
0x18003674a  jz      short loc_18003676E
0x18003674c  mov     rcx, cs:g_pDebug
0x180036753  mov     r9, rbx
0x180036756  mov     qword ptr [rsp+0C8h+var_A0], r15
0x18003675b  mov     r8d, 195h
0x180036761  mov     rdx, r14
0x180036764  mov     [rsp+0C8h+var_A8], eax
0x180036768  call    cs:__imp_PuDbgPrintError
0x18003676e  mov     rdx, [rbp+340h]
0x180036775  lea     rcx, [rdi+1D0h]
0x18003677c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180036782  test    eax, eax
0x180036784  jns     short loc_1800367B1
0x180036786  test    byte ptr cs:g_dwDebugFlags, r13b
0x18003678d  jz      short loc_1800367B1
0x18003678f  mov     rcx, cs:g_pDebug
0x180036796  mov     r9, rbx
0x180036799  mov     qword ptr [rsp+0C8h+var_A0], r15
0x18003679e  mov     r8d, 1A3h
0x1800367a4  mov     rdx, r14
0x1800367a7  mov     [rsp+0C8h+var_A8], eax
0x1800367ab  call    cs:__imp_PuDbgPrintError
0x1800367b1  mov     rdx, [rbp+378h]
0x1800367b8  lea     rcx, [rdi+208h]
0x1800367bf  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800367c5  test    eax, eax
0x1800367c7  jns     short loc_1800367F4
0x1800367c9  test    byte ptr cs:g_dwDebugFlags, r13b
0x1800367d0  jz      short loc_1800367F4
0x1800367d2  mov     rcx, cs:g_pDebug
0x1800367d9  mov     r9, rbx
0x1800367dc  mov     qword ptr [rsp+0C8h+var_A0], r15
0x1800367e1  mov     r8d, 1B4h
0x1800367e7  mov     rdx, r14
0x1800367ea  mov     [rsp+0C8h+var_A8], eax
0x1800367ee  call    cs:__imp_PuDbgPrintError
0x1800367f4  mov     eax, [rbp+390h]
0x1800367fa  mov     r15d, 1
0x180036800  mov     [rdi+240h], eax
0x180036806  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18003680d  cmp     [rax+670h], r12d
0x180036814  jz      loc_1800368D9
0x18003681a  mov     [rsp+0C8h+var_90], r12; void *
0x18003681f  xor     r9d, r9d; unsigned int
0x180036822  mov     [rdi+10h], r12
0x180036826  xor     r8d, r8d; String1
0x180036829  mov     [rdi+20h], r12
0x18003682d  xor     edx, edx; AccountName
0x18003682f  mov     [rdi+28h], r12
0x180036833  mov     rcx, rdi; this
0x180036836  mov     [rdi+40h], r12
0x18003683a  mov     [rdi+30h], r12
0x18003683e  mov     [rdi+0C8h], r12
0x180036845  mov     [rdi+0D0h], r12d
0x18003684c  mov     [rdi+0D4h], r15d
0x180036853  mov     [rdi+0DCh], r15
0x18003685a  mov     [rdi+0E8h], r12
0x180036861  mov     [rdi+0F0h], r12
0x180036868  mov     [rdi+0F8h], r12
0x18003686f  mov     [rdi+100h], r12
0x180036876  mov     [rdi+108h], r12
0x18003687d  mov     [rdi+110h], r15d
0x180036884  mov     [rdi+18Ch], r15
0x18003688b  mov     [rdi+194h], r12d
0x180036892  mov     [rdi+2D0h], r15d
0x180036899  mov     [rdi+2D4h], r15d
0x1800368a0  mov     [rdi+244h], r12d
0x1800368a7  mov     [rdi+248h], r15d
0x1800368ae  mov     [rdi+288h], r12
0x1800368b5  mov     [rdi+2F0h], r12
0x1800368bc  mov     rax, [rbp+50h]
0x1800368c0  mov     [rsp+0C8h+var_98], rax; unsigned __int16 *
0x1800368c5  mov     [rsp+0C8h+var_A0], r15d; int
0x1800368ca  mov     [rsp+0C8h+var_A8], r15d; unsigned int
0x1800368cf  call    ?SetTokenForWorkerProcesses@APP_POOL_CONFIG_STORE@@AEAAHPEBG0KKH0PEAX@Z; APP_POOL_CONFIG_STORE::SetTokenForWorkerProcesses(ushort const *,ushort const *,ulong,ulong,int,ushort const *,void *)
0x1800368d4  jmp     loc_180037203
0x1800368d9  mov     rax, [rsi]
0x1800368dc  jmp     short loc_1800368EB
0x1800368de  mov     r8, [rax-8]
0x1800368e2  cmp     [r8+8], r15d
0x1800368e6  jz      short loc_1800368F3
0x1800368e8  mov     rax, [rax]
0x1800368eb  cmp     rax, rsi
0x1800368ee  jnz     short loc_1800368DE
0x1800368f0  mov     r8, r12; struct CONFIG_ERROR *
0x1800368f3  mov     rdx, [rbp+50h]; unsigned __int16 *
0x1800368f7  lea     r9, [rdi+10h]; unsigned int *
0x1800368fb  mov     ecx, [rbp+68h]; unsigned int
0x1800368fe  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036903  mov     eax, [rbp+6Ch]
0x180036906  mov     [rdi+14h], eax
0x180036909  mov     rax, [rsi]
0x18003690c  jmp     short loc_18003691C
0x18003690e  mov     r8, [rax-8]
0x180036912  cmp     dword ptr [r8+8], 3
0x180036917  jz      short loc_180036924
0x180036919  mov     rax, [rax]
0x18003691c  cmp     rax, rsi
0x18003691f  jnz     short loc_18003690E
0x180036921  mov     r8, r12; struct CONFIG_ERROR *
0x180036924  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036928  lea     r9, [rdi+20h]; unsigned int *
0x18003692c  mov     ecx, [rbp+70h]; unsigned int
0x18003692f  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036934  mov     rax, [rsi]
0x180036937  jmp     short loc_180036947
0x180036939  mov     r8, [rax-8]
0x18003693d  cmp     dword ptr [r8+8], 4
0x180036942  jz      short loc_18003694F
0x180036944  mov     rax, [rax]
0x180036947  cmp     rax, rsi
0x18003694a  jnz     short loc_180036939
0x18003694c  mov     r8, r12; struct CONFIG_ERROR *
0x18003694f  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036953  lea     r9, [rdi+24h]; unsigned int *
0x180036957  mov     ecx, [rbp+74h]; unsigned int
0x18003695a  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x18003695f  mov     rax, [rsi]
0x180036962  jmp     short loc_180036972
0x180036964  mov     r8, [rax-8]
0x180036968  cmp     dword ptr [r8+8], 8
0x18003696d  jz      short loc_18003697A
0x18003696f  mov     rax, [rax]
0x180036972  cmp     rax, rsi
0x180036975  jnz     short loc_180036964
0x180036977  mov     r8, r12; struct CONFIG_ERROR *
0x18003697a  mov     rdx, [rbp+50h]; unsigned __int16 *
0x18003697e  lea     rbx, [rdi+2Ch]
0x180036982  mov     ecx, [rbp+0B4h]; unsigned int
0x180036988  mov     r9, rbx; unsigned int *
0x18003698b  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036990  mov     r9d, [rdi+10h]; unsigned int
0x180036994  cmp     [rbx], r9d
0x180036997  jb      short loc_1800369AA
0x180036999  test    r9d, r9d
0x18003699c  jz      short loc_1800369AA
0x18003699e  mov     r8d, [rbx]; unsigned int
0x1800369a1  mov     rdx, [rbp+50h]; unsigned __int16 *
0x1800369a5  call    ?LogIdleTimeoutGreaterThanRestartPeriod@WMS_ERROR_LOGGER@@QEAAXPEBGKKH@Z; WMS_ERROR_LOGGER::LogIdleTimeoutGreaterThanRestartPeriod(ushort const *,ulong,ulong,int)
0x1800369aa  mov     rax, [rsi]
0x1800369ad  jmp     short loc_1800369BD
0x1800369af  mov     r8, [rax-8]
0x1800369b3  cmp     dword ptr [r8+8], 9
0x1800369b8  jz      short loc_1800369C5
0x1800369ba  mov     rax, [rax]
0x1800369bd  cmp     rax, rsi
0x1800369c0  jnz     short loc_1800369AF
0x1800369c2  mov     r8, r12; struct CONFIG_ERROR *
0x1800369c5  mov     rdx, [rbp+50h]; unsigned __int16 *
0x1800369c9  lea     r9, [rdi+30h]; unsigned int *
0x1800369cd  mov     ecx, [rbp+0B8h]; unsigned int
0x1800369d3  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x1800369d8  mov     eax, [rbp+0DCh]
0x1800369de  mov     [rdi+34h], eax
0x1800369e1  mov     eax, [rbp+0BCh]
0x1800369e7  mov     [rdi+28h], eax
0x1800369ea  test    eax, eax
0x1800369ec  jz      short loc_180036A4A
0x1800369ee  mov     rax, [rsi]
0x1800369f1  jmp     short loc_180036A01
0x1800369f3  mov     r8, [rax-8]
0x1800369f7  cmp     dword ptr [r8+8], 11h
0x1800369fc  jz      short loc_180036A09
0x1800369fe  mov     rax, [rax]
0x180036a01  cmp     rax, rsi
0x180036a04  jnz     short loc_1800369F3
0x180036a06  mov     r8, r12; struct CONFIG_ERROR *
0x180036a09  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036a0d  lea     r9, [rdi+40h]; unsigned int *
0x180036a11  mov     ecx, [rbp+0E8h]; unsigned int
0x180036a17  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036a1c  mov     rax, [rsi]
0x180036a1f  jmp     short loc_180036A2F
0x180036a21  mov     r8, [rax-8]
0x180036a25  cmp     dword ptr [r8+8], 12h
0x180036a2a  jz      short loc_180036A37
0x180036a2c  mov     rax, [rax]
0x180036a2f  cmp     rax, rsi
0x180036a32  jnz     short loc_180036A21
0x180036a34  mov     r8, r12; struct CONFIG_ERROR *
0x180036a37  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036a3b  lea     r9, [rdi+44h]; unsigned int *
0x180036a3f  mov     ecx, [rbp+0ECh]; unsigned int
0x180036a45  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036a4a  mov     rax, [rsi]
0x180036a4d  jmp     short loc_180036A5D
0x180036a4f  mov     r8, [rax-8]
0x180036a53  cmp     dword ptr [r8+8], 1Fh
0x180036a58  jz      short loc_180036A65
0x180036a5a  mov     rax, [rax]
0x180036a5d  cmp     rax, rsi
0x180036a60  jnz     short loc_180036A4F
0x180036a62  mov     r8, r12; struct CONFIG_ERROR *
0x180036a65  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036a69  lea     r9, [rdi+0C8h]; unsigned int *
0x180036a70  mov     ecx, [rbp+244h]; unsigned int
0x180036a76  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036a7b  mov     rax, [rsi]
0x180036a7e  jmp     short loc_180036A8E
0x180036a80  mov     r8, [rax-8]
0x180036a84  cmp     dword ptr [r8+8], 20h ; ' '
0x180036a89  jz      short loc_180036A96
0x180036a8b  mov     rax, [rax]
0x180036a8e  cmp     rax, rsi
0x180036a91  jnz     short loc_180036A80
0x180036a93  mov     r8, r12; struct CONFIG_ERROR *
0x180036a96  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036a9a  lea     r9, [rdi+0CCh]; unsigned int *
0x180036aa1  mov     ecx, [rbp+248h]; unsigned int
0x180036aa7  call    ?ApplyRangeCheck@@YAXKPEBGPEAVCONFIG_ERROR@@PEAK@Z; ApplyRangeCheck(ulong,ushort const *,CONFIG_ERROR *,ulong *)
0x180036aac  mov     rax, [rsi]
0x180036aaf  jmp     short loc_180036ABF
0x180036ab1  mov     r8, [rax-8]
0x180036ab5  cmp     dword ptr [r8+8], 21h ; '!'
0x180036aba  jz      short loc_180036AC7
0x180036abc  mov     rax, [rax]
0x180036abf  cmp     rax, rsi
0x180036ac2  jnz     short loc_180036AB1
0x180036ac4  mov     r8, r12; struct CONFIG_ERROR *
0x180036ac7  mov     rdx, [rbp+50h]; unsigned __int16 *
0x180036acb  lea     r9, [rdi+0D0h]; unsigned int *
  ... truncated ...
```
