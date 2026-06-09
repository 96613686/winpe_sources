# NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)

- ea: `0x180078f00`
- end: `0x18007af3e`
- name: `?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z`
- size: `8254`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, WCHAR *SourceString, LPCWCH lpWideCharStr, unsigned __int64 hMem, void *, struct _GUID *Buf1, unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, LPVOID *, struct _NL_DC_CACHE_ENTRY **)`
- caller_count: `5`
- callee_count: `44`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027d78`
- `0x180064834`
- `0x1800788c0`
- `0x18007d15c`
- `0x18007d384`

## callees

- `0x180003170`
- `0x180003670`
- `0x180007278`
- `0x1800098a8`
- `0x180009fb0`
- `0x18000a9ac`
- `0x18000ad34`
- `0x18000b1c4`
- `0x18000b7bc`
- `0x18000ba1c`
- `0x18000be30`
- `0x18000c2c0`
- `0x18000c368`
- `0x18000c3ac`
- `0x18000cbe0`
- `0x18000cc0c`
- `0x18000cdb4`
- `0x180018414`
- `0x18001852c`
- `0x180018690`
- `0x180024adc`
- `0x18002bd1c`
- `0x18003387c`
- `0x180039084`
- `0x180041568`
- `0x1800467b4`
- `0x18006ef9c`
- `0x180074f80`
- `0x1800782b8`
- `0x180078738`
- `0x180078f00`
- `0x18007af44`
- `0x18007b398`
- `0x18007c244`
- `0x18007cdf8`
- `0x18007d15c`
- `0x18007d384`
- `0x18007e198`
- `0x18007e350`
- `0x18007e424`
- `0x18007e4e4`
- `0x18007e9d8`
- `0x18007ea30`
- `0x18008315c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007aa49`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007aa49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079dea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007aaae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ab63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007abb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079dea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007aaae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ab63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007abb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007aef8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007aef8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007aee5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007aee5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079e94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007acb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079e94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007acb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800791b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800791b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079277`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079277`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007abdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007abdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079c1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007a2f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007ab69`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079c1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007a2f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007ab69`
- `netutils!NetApiBufferFree` at `0x18007930a`
- `netutils!NetApiBufferFree` at `0x18007af22`
- `netutils!NetApiBufferFree` at `0x18007930a`
- `netutils!NetApiBufferFree` at `0x18007af22`

## string_xrefs

- `0x180079412`: `NetpDcGetName: NlCacheJoinDomainControllerInfo returned failure code: %ld\n`
- `0x180079443`: `NetpDcGetName: NlCacheJoinDomainControllerInfo returned success\n`
- `0x1800794f7`: `NetpDcGetName: %ws force-use of cached info due to low-power-mode ( NlDcCacheEntry = 0x%p ) \n`
- `0x180079548`: `NetpDcGetName: no cached DC found in low power mode.\n`
- `0x180079624`: `NetpDcGetName: %ws cache is too old, need to redo discovery. %ld\n`
- `0x1800796ef`: `NetpDcGetName: %ws cache not for closest site and it is too old. %ld\n`
- `0x180079792`: `NetpDcGetName: %ws cache not for closest site and user wants to find a next closest site which we have not tried it yet. %ld\n`
- `0x1800798db`: `NetpDcGetName: %ws cache doesn't have right account name.\n`
- `0x180079868`: `NetpDcGetName: %ws cache is too old. %ld\n`
- `0x180079a1b`: `NetpDcGetName: %ws cache says use ldap but has no address\n`
- `0x180079ad1`: `NetpDcGetName: %ws cache says use maislot but has no Netbios name\n`
- `0x180079c9f`: `NetpDcGetName: ping of cached entry failed: ( NlDcCacheEntry=0x%p ) 0x%x\n`
- `0x180079d65`: `NetpDcGetName: %ws using cached information ( NlDcCacheEntry = 0x%p )\n`
- `0x180079fe9`: `NetpDcGetName: %ws is permanently negative cached.\n`
- `0x18007a116`: `NetpDcGetName: failing the request due to max limit of concurrent discovery attempts\n`
- `0x18007aadb`: `Cache: %ws %ws: Ditch cache entry list %ld since force couldn't find DC\n`
- `0x18007ac48`: `Cache: %ws %ws: Cache entry %ld marked permanently negative.\n`

## pseudocode

```c
__int64 __fastcall NetpDcGetName(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        WCHAR *SourceString,
        LPCWCH lpWideCharStr,
        unsigned __int64 hMem,
        void *a9,
        struct _GUID *Buf1,
        unsigned __int16 *a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        unsigned int a15,
        LPVOID *a16,
        struct _NL_DC_CACHE_ENTRY **a17)
{
  const unsigned __int16 *v17; // rsi
  const unsigned __int16 *v18; // r14
  const unsigned __int16 *v19; // r13
  const unsigned __int16 *v20; // r12
  struct _GUID *v21; // r15
  unsigned int v22; // eax
  __int64 NameIp; // rbx
  const unsigned __int16 *v24; // rdx
  ScannerInfoNameMappings *v25; // rcx
  __int64 v26; // rdx
  HLOCAL v27; // r9
  __int64 v28; // r8
  unsigned int v29; // edx
  int v30; // ebx
  char *Utf8StrFromWStr; // rdi
  void *v32; // rsi
  unsigned int v33; // r14d
  char *v34; // rax
  char *v35; // rdi
  int v36; // r8d
  ScannerInfoNameMappings *v37; // rcx
  int v38; // edx
  unsigned int v39; // eax
  char v40; // bl
  unsigned int v41; // eax
  struct _NL_DC_CACHE_ENTRY *CacheEntry; // rax
  int v43; // r8d
  int v44; // edi
  unsigned int v45; // edi
  unsigned int v46; // esi
  struct _NL_DC_CACHE_ENTRY *v47; // rax
  unsigned int *v48; // rcx
  unsigned int v49; // eax
  unsigned int v50; // edx
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  char v54; // al
  unsigned int v55; // edx
  unsigned int v56; // eax
  char v57; // al
  unsigned int v58; // eax
  char v59; // al
  unsigned int v60; // eax
  unsigned int v61; // edx
  unsigned int v62; // eax
  char v63; // al
  struct _NL_DC_CACHE_ENTRY *v64; // rdx
  int v65; // eax
  struct _SOCKET_ADDRESS *v66; // r8
  unsigned int v67; // eax
  __int64 v68; // rcx
  __int64 v69; // rcx
  ScannerInfoNameMappings *v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // rcx
  unsigned __int64 v73; // rax
  void *v74; // rax
  int v75; // edi
  DWORD TickCount; // esi
  unsigned int v77; // eax
  unsigned int v78; // ebx
  __int64 v79; // rdx
  __int64 v80; // r8
  unsigned int v81; // eax
  unsigned int v82; // ecx
  int v83; // r8d
  unsigned __int64 v84; // r8
  unsigned int v85; // ecx
  unsigned int v86; // eax
  unsigned int v87; // ebx
  int v88; // eax
  __int64 v89; // rdx
  unsigned __int8 HasElapsed; // al
  ScannerInfoNameMappings *v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // rax
  unsigned __int64 v96; // rax
  unsigned int v97; // eax
  int v98; // ebx
  char v99; // r12
  int v100; // esi
  char v101; // r14
  int v102; // edi
  unsigned int PingResponse; // eax
  int v104; // eax
  unsigned int v105; // ecx
  unsigned int v106; // eax
  unsigned int v107; // eax
  unsigned int v108; // eax
  ScannerInfoNameMappings *v109; // rcx
  __int64 v110; // rdx
  int v111; // edx
  unsigned int GcUsingNetbios; // eax
  unsigned __int64 v113; // r8
  struct _FILETIME *v114; // rcx
  char IsEnabled; // al
  unsigned __int16 *v116; // rcx
  struct _NL_DC_ADDRESS *v118; // [rsp+28h] [rbp-A1h]
  struct _NL_DC_CACHE_ENTRY **v119; // [rsp+30h] [rbp-99h]
  LPVOID *v120; // [rsp+38h] [rbp-91h]
  unsigned __int16 *v121; // [rsp+40h] [rbp-89h]
  unsigned int v122; // [rsp+58h] [rbp-71h]
  unsigned __int8 started; // [rsp+98h] [rbp-31h]
  int v124; // [rsp+9Ch] [rbp-2Dh] BYREF
  int v125; // [rsp+A0h] [rbp-29h]
  int v126; // [rsp+A4h] [rbp-25h] BYREF
  unsigned int v127; // [rsp+A8h] [rbp-21h] BYREF
  struct _NL_DC_CACHE_ENTRY *v128; // [rsp+B0h] [rbp-19h] BYREF
  LPVOID Buffer; // [rsp+B8h] [rbp-11h]
  void *v130; // [rsp+C0h] [rbp-9h] BYREF

  v17 = a4;
  v128 = 0;
  v126 = 0;
  v125 = 0;
  v130 = 0;
  v127 = 0;
  v124 = 0;
  Buffer = 0;
  started = 0;
  if ( a16 )
    *a16 = 0;
  if ( a17 )
    *a17 = 0;
  v18 = lpWideCharStr;
  if ( lpWideCharStr )
    v18 = (const unsigned __int16 *)(-(__int64)(*lpWideCharStr != 0) & (unsigned __int64)lpWideCharStr);
  v19 = (const unsigned __int16 *)hMem;
  if ( hMem )
    v19 = (const unsigned __int16 *)(-(__int64)(*(_WORD *)hMem != 0) & hMem);
  v20 = SourceString;
  if ( SourceString )
    v20 = (const unsigned __int16 *)(-(__int64)(*SourceString != 0) & (unsigned __int64)SourceString);
  v21 = Buf1;
  hMem = 0;
  v22 = NetpDcInitializeContext(
          a1,
          a2,
          a3,
          a4,
          a5,
          v20,
          v18,
          v19,
          a9,
          Buf1,
          a11,
          0,
          0,
          0,
          a12,
          a13 | 0x80,
          1,
          (struct _NL_GETDC_CONTEXT **)&hMem);
  LODWORD(NameIp) = v22;
  if ( v22 )
  {
    NlPrintRoutine(0x100u, L"NetpDcGetName: NetpDcInitializeContext failed. %ld\n", v22);
    v25 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = 97;
LABEL_15:
      WPP_SF_l(*((_QWORD *)v25 + 2), v26, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids, (unsigned int)NameIp);
      goto LABEL_312;
    }
    goto LABEL_312;
  }
  NetpUpdatePerfCountersStart((struct _NL_GETDC_CONTEXT *)hMem);
  v27 = (HLOCAL)hMem;
  v28 = *(unsigned int *)(hMem + 12);
  v29 = ((*(_DWORD *)(hMem + 12) & 0xFFFFFFC0) << 25) | 0x20000000;
  if ( (v28 & 0x200) == 0 )
    v29 = (*(_DWORD *)(hMem + 12) & 0xFFFFFFC0) << 25;
  v30 = v29 | 0x10000000;
  if ( (v28 & 0x80u) == 0LL )
    v30 = v29;
  if ( (v28 & 0x4000) == 0 )
  {
    Utf8StrFromWStr = 0;
    if ( v18 )
    {
      Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(v18, 0, 0);
      if ( !Utf8StrFromWStr )
      {
        LODWORD(NameIp) = 8;
LABEL_24:
        v32 = Buffer;
LABEL_25:
        v33 = a12;
        goto LABEL_26;
      }
      v27 = (HLOCAL)hMem;
    }
    LODWORD(NameIp) = NlGetLocalPingResponse(
                        L"<Local>",
                        v20,
                        Utf8StrFromWStr,
                        v21,
                        a9,
                        *((_DWORD *)v27 + 1) == 5,
                        *((const unsigned __int16 **)v27 + 10),
                        *((const unsigned __int16 **)v27 + 11),
                        *((const unsigned __int16 **)v27 + 3),
                        *((_DWORD *)v27 + 8),
                        v122,
                        v30 | 0x4000000E,
                        0,
                        &v130,
                        &v127);
    if ( Utf8StrFromWStr )
      NetApiBufferFree(Utf8StrFromWStr);
    if ( (_DWORD)NameIp != 1355 )
    {
      if ( (_DWORD)NameIp )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcGetName: %ws: cannot get local ping response %ld\n",
          *(_QWORD *)(hMem + 72),
          (unsigned int)NameIp);
        v37 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v38 = 98;
LABEL_48:
          WPP_SF_SL(
            *((_QWORD *)v37 + 2),
            v38,
            (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
            *(_QWORD *)(hMem + 72),
            NameIp);
        }
        goto LABEL_24;
      }
      v39 = NetpDcHandlePingResponse((struct _NL_GETDC_CONTEXT *)hMem, v130, v127, 4u, 0, &v128, &v124);
      LODWORD(NameIp) = v39;
      if ( v39 != 13 && v39 != 121 && v39 != 1317 )
        goto LABEL_312;
    }
    v27 = (HLOCAL)hMem;
  }
  v40 = 0;
  if ( (*((_DWORD *)v27 + 4) & 0x4001) == 1 && !NlGlobalJoinLogicDone )
  {
    v41 = NlCacheJoinDomainControllerInfo();
    LODWORD(NameIp) = v41;
    if ( v41 )
    {
      NlPrintRoutine(0x100u, L"NetpDcGetName: NlCacheJoinDomainControllerInfo returned failure code: %ld\n", v41);
      v25 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 99;
        goto LABEL_15;
      }
LABEL_312:
      if ( (_DWORD)NameIp != 1355 )
        goto LABEL_354;
      goto LABEL_319;
    }
    NlPrintRoutine(0x100u, L"NetpDcGetName: NlCacheJoinDomainControllerInfo returned success\n");
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
    v40 = 1;
    *(_DWORD *)(hMem + 12) &= ~1u;
    v27 = (HLOCAL)hMem;
  }
  if ( g_LowPowerNQMState )
  {
    NlPrintRoutine(0x100u, L"NetpDcGetName: running in low-power mode (FORCE will be ignored).\n", v28, v27);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
    CacheEntry = NetpDcFindCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, &v124, &v126);
    v128 = CacheEntry;
    if ( CacheEntry )
    {
      NlPrintRoutine(
        0x100u,
        L"NetpDcGetName: %ws force-use of cached info due to low-power-mode ( NlDcCacheEntry = 0x%p ) \n",
        *(_QWORD *)(hMem + 72),
        CacheEntry);
      LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v43, *(_QWORD *)(hMem + 72), (char)v128);
      LODWORD(NameIp) = 0;
      v44 = 0;
      goto LABEL_356;
    }
    NlPrintRoutine(0x100u, L"NetpDcGetName: no cached DC found in low power mode.\n");
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
    goto LABEL_318;
  }
  LOBYTE(lpWideCharStr) = 0;
  if ( (*((_BYTE *)v27 + 12) & 1) == 0 )
  {
    v45 = 0;
    v46 = 0;
    v47 = NetpDcFindCacheEntry((struct _NL_GETDC_CONTEXT *)v27, &v124, &v126);
    v128 = v47;
    v48 = (unsigned int *)v47;
    if ( v47 )
    {
      v49 = NetpDcElapsedTime(*((_DWORD *)v47 + 5));
      v48 = (unsigned int *)v128;
      v45 = v49;
      v50 = *((_DWORD *)v128 + 106);
      if ( v50 )
      {
        v51 = NetpDcElapsedTime(v50);
        v48 = (unsigned int *)v128;
        v46 = v51;
      }
    }
    if ( v48 )
    {
      if ( (*(_DWORD *)(hMem + 12) & 0x100) == 0 )
      {
        v52 = (unsigned int)dword_1800F130C > 0x418937 ? -1 : 1000 * dword_1800F130C;
        if ( v45 > v52 )
        {
          v53 = NetpDcElapsedTime(v48[5]);
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws cache is too old, need to redo discovery. %ld\n",
            *(_QWORD *)(hMem + 72),
            v53);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v54 = NetpDcElapsedTime(*((_DWORD *)v128 + 5));
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              104,
              (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *(_QWORD *)(hMem + 72),
              v54);
          }
          NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v128);
          NetpDcDerefCacheEntry(v128);
          v48 = 0;
          v128 = 0;
          if ( v40 )
            goto LABEL_104;
          *(_DWORD *)(hMem + 12) |= 1u;
          v48 = (unsigned int *)v128;
        }
      }
      if ( v48 )
      {
        v55 = v48[67];
        if ( (v55 & 8) != 0 )
        {
          if ( v45 > 0xDBBA0 )
          {
            v56 = NetpDcElapsedTime(v48[5]);
            NlPrintRoutine(
              2u,
              L"NetpDcGetName: %ws cache not for closest site and it is too old. %ld\n",
              *(_QWORD *)(hMem + 72),
              v56);
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v57 = NetpDcElapsedTime(*((_DWORD *)v128 + 5));
              WPP_SF_SL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
                *(_QWORD *)(hMem + 72),
                v57);
            }
            NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v128);
LABEL_103:
            NetpDcDerefCacheEntry(v128);
            v48 = 0;
            v128 = 0;
            goto LABEL_104;
          }
          if ( (*(_DWORD *)(hMem + 12) & 0x40000) != 0 && (v55 & 0x20) == 0 )
          {
            v58 = NetpDcElapsedTime(v48[5]);
            NlPrintRoutine(
              2u,
              L"NetpDcGetName: %ws cache not for closest site and user wants to find a next closest site which we have not"
               " tried it yet. %ld\n",
              *(_QWORD *)(hMem + 72),
              v58);
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v59 = NetpDcElapsedTime(*((_DWORD *)v128 + 5));
              WPP_SF_SL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                106,
                (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
                *(_QWORD *)(hMem + 72),
                v59);
            }
            goto LABEL_103;
          }
        }
      }
    }
LABEL_104:
    v60 = dword_1800F119C;
    if ( (*(_DWORD *)(hMem + 12) & 0x100) != 0 )
      v60 = dword_1800F1198;
    if ( v60 > 0x418937 )
      v61 = -1;
    else
      v61 = 1000 * v60;
    if ( !v48 )
    {
LABEL_172:
      _InterlockedAdd64(&qword_1800F1DC0, 1u);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(hMem + 112) + 360LL) + 64LL), 1u);
      EnterCriticalSection(&NlDcCritSect);
      v84 = hMem;
      v85 = *(_DWORD *)(*(_QWORD *)(hMem + 112) + 40LL * *(int *)(hMem + 4) + 112);
      if ( v85 )
      {
        v86 = NetpDcElapsedTime(v85);
        v87 = v86;
        v84 = hMem;
        if ( v86 < 1000 * dword_1800F1188 )
        {
          NlPrintRoutine(2u, L"NetpDcGetName: %ws similar query failed recently %ld\n", *(_QWORD *)(hMem + 72), v86);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              115,
              (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *(_QWORD *)(hMem + 72),
              v87);
          goto LABEL_177;
        }
        v88 = 1;
      }
      else
      {
        v87 = -1;
        v88 = 0;
      }
      if ( (*(_DWORD *)(v84 + 12) & 0x100) != 0 && v88 )
      {
        v89 = *(_QWORD *)(v84 + 112);
        if ( v87 < 1000 * *(_DWORD *)(v89 + 40LL * *(int *)(v84 + 4) + 116) )
        {
          LODWORD(v118) = 1000 * *(_DWORD *)(v89 + 40LL * *(int *)(v84 + 4) + 116);
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws similar background query failed recently %ld %ld\n",
            *(_QWORD *)(v84 + 72),
            v87,
            v118);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_Sll(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              116,
              (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *(_QWORD *)(hMem + 72),
              v87,
              -24 * *(_BYTE *)(*(_QWORD *)(hMem + 112) + 40LL * *(int *)(hMem + 4) + 116));
          goto LABEL_177;
        }
        if ( dword_1800F1194 )
        {
          HasElapsed = NlTimeHasElapsedEx(
                         (union _LARGE_INTEGER *)(v89 + 128 + 40LL * *(int *)(v84 + 4)),
                         &stru_1800F12F8,
                         0);
          v84 = hMem;
          if ( HasElapsed )
          {
            NlPrintRoutine(2u, L"NetpDcGetName: %ws avoiding all future background queries\n", *(_QWORD *)(hMem + 72));
            v91 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              goto LABEL_177;
            v92 = 117;
LABEL_191:
            WPP_SF_S(
              *((_QWORD *)v91 + 2),
              v92,
              &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *(_QWORD *)(hMem + 72));
LABEL_177:
            LODWORD(NameIp) = 1355;
            *(_BYTE *)(hMem + 225) = 1;
            LeaveCriticalSection(&NlDcCritSect);
LABEL_319:
            if ( *(_BYTE *)(hMem + 226) )
            {
              LODWORD(NameIp) = 1317;
              goto LABEL_24;
            }
            if ( *(_QWORD *)(hMem + 216) && (*(_DWORD *)(hMem + 12) & 0x2000) != 0 )
            {
              NlPrintRoutine(2u, L"NetpDcGetName: %ws: Domain has no good timeserv.\n", *(_QWORD *)(hMem + 72));
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  138,
                  &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
                  *(_QWORD *)(hMem + 72));
              LODWORD(v25) = hMem;
              v128 = *(struct _NL_DC_CACHE_ENTRY **)(hMem + 216);
              v124 = *(unsigned __int8 *)(hMem + 224);
              *(_QWORD *)(hMem + 216) = 0;
LABEL_171:
              LODWORD(NameIp) = 0;
              v44 = 0;
              goto LABEL_356;
            }
            if ( dword_1800EF224[8 * *(int *)(hMem + 8)] == 4
              && *(_QWORD *)(hMem + 48)
              && (!*(_QWORD *)(hMem + 56) || !(unsigned int)_o__wcsicmp()) )
            {
              GcUsingNetbios = NetpGetGcUsingNetbios((struct _NL_GETDC_CONTEXT *)hMem, a14, a15, &v128);
              LODWORD(NameIp) = GcUsingNetbios;
              if ( !GcUsingNetbios )
              {
                v124 = 0;
LABEL_333:
                v44 = v125;
                goto LABEL_356;
              }
              if ( GcUsingNetbios != 1355 )
                goto LABEL_24;
            }
            if ( (*(_BYTE *)(hMem + 16) & 8) == 0 )
            {
              if ( (*(_BYTE *)(hMem + 12) & 1) != 0 )
              {
                EnterCriticalSection(&NlDcCritSect);
                NetpDcFreeCacheEntryList((struct _LIST_ENTRY *)(*(_QWORD *)(hMem + 112)
                                                              + 8 * (5LL * *(int *)(hMem + 4) + 12)));
                LODWORD(v118) = *(_DWORD *)(hMem + 4);
                NlPrintRoutine(
                  0x20000u,
                  L"Cache: %ws %ws: Ditch cache entry list %ld since force couldn't find DC\n",
                  *(_QWORD *)(hMem + 112) + 36LL,
                  *(_QWORD *)(*(_QWORD *)(hMem + 112) + 72LL),
                  v118);
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  WPP_SF_SSl(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    139,
                    *(_QWORD *)(hMem + 112),
                    *(_QWORD *)(hMem + 112) + 36,
                    *(_QWORD *)(*(_QWORD *)(hMem + 112) + 72LL),
                    *(_DWORD *)(hMem + 4));
                LeaveCriticalSection(&NlDcCritSect);
              }
              if ( !*(_BYTE *)(hMem + 225) )
              {
                EnterCriticalSection(&NlDcCritSect);
                *(_DWORD *)(*(_QWORD *)(hMem + 112) + 40LL * *(int *)(hMem + 4) + 112) = GetTickCount();
                LeaveCriticalSection(&NlDcCritSect);
              }
            }
            if ( (*(_BYTE *)(hMem + 16) & 8) != 0 )
            {
              v33 = a12;
              goto LABEL_380;
            }
            if ( *(_BYTE *)(hMem + 225) )
              goto LABEL_24;
            EnterCriticalSection(&NlDcCritSect);
            v113 = hMem;
            v114 = (struct _FILETIME *)(*(_QWORD *)(hMem + 112) + 8 * (5LL * *(int *)(hMem + 4) + 16));
            if ( !*(_QWORD *)v114 )
            {
              GetSystemTimeAsFileTime(v114);
              *(_DWORD *)(*(_QWORD *)(hMem + 112) + 40LL * *(int *)(hMem + 4) + 116) = dword_1800F118C;
              v113 = hMem;
            }
            if ( (*(_DWORD *)(v113 + 16) & 0x1000) != 0 )
            {
              if ( *(_BYTE *)(v113 + 229) )
              {
                if ( !*(_BYTE *)(v113 + 228) )
                {
                  *(_BYTE *)(*(_QWORD *)(v113 + 112) + 40 * (*(int *)(v113 + 4) + 3LL)) = 1;
                  LODWORD(v118) = *(_DWORD *)(hMem + 4);
                  NlPrintRoutine(
                    0x4000u,
                    L"Cache: %ws %ws: Cache entry %ld marked permanently negative.\n",
                    *(_QWORD *)(hMem + 112) + 36LL,
                    *(_QWORD *)(*(_QWORD *)(hMem + 112) + 72LL),
                    v118);
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                    WPP_SF_SSl(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      140,
                      *(_QWORD *)(hMem + 112),
                      *(_QWORD *)(hMem + 112) + 36,
                      *(_QWORD *)(*(_QWORD *)(hMem + 112) + 72LL),
                      *(_DWORD *)(hMem + 4));
                }
              }
            }
            LeaveCriticalSection(&NlDcCritSect);
LABEL_354:
            if ( !(_DWORD)NameIp )
            {
              v44 = v125;
              goto LABEL_356;
            }
            goto LABEL_24;
          }
        }
        v93 = *(int *)(v84 + 4);
        v94 = *(_QWORD *)(v84 + 112);
        if ( *(_BYTE *)(v94 + 40 * v93 + 120) )
        {
          NlPrintRoutine(2u, L"NetpDcGetName: %ws is permanently negative cached.\n", *(_QWORD *)(v84 + 72));
          v91 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            goto LABEL_177;
          v92 = 118;
          goto LABEL_191;
        }
        *(_DWORD *)(v94 + 40 * v93 + 116) *= 2;
        v95 = *(_QWORD *)(hMem + 112);
        if ( *(_DWORD *)(v95 + 40LL * *(int *)(hMem + 4) + 116) > (unsigned int)dword_1800F1190 )
          *(_DWORD *)(v95 + 40LL * *(int *)(hMem + 4) + 116) = dword_1800F1190;
      }
      LeaveCriticalSection(&NlDcCritSect);
      if ( (*(_DWORD *)(hMem + 12) & 0x2000) != 0 && *(_QWORD *)(hMem + 216) )
      {
        *(_BYTE *)(hMem + 225) = 1;
        NlPrintRoutine(2u, L"NetpDcGetName: %ws: Only try once to find good timeserver.\n", *(_QWORD *)(hMem + 72));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            119,
            &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
            *(_QWORD *)(hMem + 72));
        LOBYTE(lpWideCharStr) = 1;
      }
      v17 = a4;
      goto LABEL_205;
    }
    if ( v126 )
    {
      NlPrintRoutine(2u, L"NetpDcGetName: %ws cache doesn't have right account name.\n", *(_QWORD *)(hMem + 72));
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          *(_QWORD *)(hMem + 72));
    }
    else
    {
      if ( v46 <= v61 && (v48[106] || v45 <= v61) )
      {
LABEL_167:
        if ( v48 )
        {
          _InterlockedIncrement64(&qword_1800F1DB8);
          _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(hMem + 112) + 360LL) + 56LL));
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws using cached information ( NlDcCacheEntry = 0x%p )\n",
            *(_QWORD *)(hMem + 72),
            v128);
          LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, v83, *(_QWORD *)(hMem + 72), (char)v128);
          goto LABEL_171;
        }
        goto LABEL_172;
      }
      v62 = NetpDcElapsedTime(v48[5]);
      NlPrintRoutine(2u, L"NetpDcGetName: %ws cache is too old. %ld\n", *(_QWORD *)(hMem + 72), v62);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v63 = NetpDcElapsedTime(*((_DWORD *)v128 + 5));
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          *(_QWORD *)(hMem + 72),
          v63);
      }
    }
    v64 = v128;
    v65 = *((_DWORD *)v128 + 67);
    if ( (v65 & 2) != 0 )
    {
      v66 = (struct _SOCKET_ADDRESS *)((char *)v128 + 88);
      if ( *((_DWORD *)v128 + 24) )
      {
        if ( !dword_1800F1308 && v66->lpSockaddr->sa_family == 23 )
          v66 = (struct _SOCKET_ADDRESS *)((char *)v128 + 280);
        v67 = NetpDcProcessAddressList(
                (struct _NL_GETDC_CONTEXT *)hMem,
                *((unsigned __int16 **)v128 + 10),
                v66,
                1u,
                0,
                0);
        LODWORD(NameIp) = v67;
        if ( v67 )
        {
          NlPrintRoutine(0x100u, L"NetpDcGetName: NetpDcProcessAddressList failed. %ld\n", v67);
          v25 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = 109;
            goto LABEL_15;
          }
          goto LABEL_312;
        }
        v68 = *((_QWORD *)v128 + 10);
        if ( v68 )
        {
          *(_QWORD *)(hMem + 96) = v68;
          *(_DWORD *)(hMem + 16) |= 0x100u;
        }
        else
        {
          v69 = *((_QWORD *)v128 + 9);
          if ( v69 )
          {
            *(_QWORD *)(hMem + 96) = v69;
            *(_DWORD *)(hMem + 16) |= 0x200u;
          }
        }
        *(_DWORD *)(hMem + 16) |= 0x400u;
        goto LABEL_149;
      }
      NlPrintRoutine(0x100u, L"NetpDcGetName: %ws cache says use ldap but has no address\n", *(_QWORD *)(hMem + 72));
      v70 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v71 = 110;
LABEL_148:
        WPP_SF_S(*((_QWORD *)v70 + 2), v71, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids, *(_QWORD *)(hMem + 72));
      }
    }
    else
    {
      if ( (v65 & 1) == 0 )
        goto LABEL_150;
      v72 = *((_QWORD *)v128 + 9);
      if ( v72 && *((_QWORD *)v128 + 6) )
      {
        *(_QWORD *)(hMem + 96) = v72;
        v73 = hMem;
        if ( !*(_QWORD *)(hMem + 48) )
        {
          v74 = (void *)NetpAllocWStrFromWStr(*((void **)v128 + 6));
          Buffer = v74;
          v32 = v74;
          if ( !v74 )
          {
            LODWORD(NameIp) = 8;
            goto LABEL_25;
          }
          *(_QWORD *)(hMem + 48) = v74;
          v73 = hMem;
        }
        *(_DWORD *)(v73 + 16) |= 0x200u;
        *(_DWORD *)(hMem + 16) |= 0x800u;
        goto LABEL_149;
      }
      NlPrintRoutine(
        0x100u,
        L"NetpDcGetName: %ws cache says use maislot but has no Netbios name\n",
        *(_QWORD *)(hMem + 72));
      v70 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v71 = 111;
        goto LABEL_148;
      }
    }
LABEL_149:
    v64 = v128;
LABEL_150:
    if ( (*(_DWORD *)(hMem + 16) & 0x300) != 0 )
    {
      SourceString = 0;
      v75 = *((_DWORD *)v64 + 5);
      LODWORD(NameIp) = NetpDcInitializeContext(
                          a1,
                          a2,
                          a3,
                          a4,
                          *(_DWORD *)(hMem + 32),
                          v20,
                          v18,
                          v19,
                          a9,
                          Buf1,
                          a11,
                          0,
                          0,
                          0,
                          a12,
                          a13,
                          2,
                          (struct _NL_GETDC_CONTEXT **)&hMem);
      if ( (_DWORD)NameIp )
      {
        NetpDcDerefCacheEntry(v128);
        v128 = 0;
        NlPrintRoutine(0x100u, L"NetpDcGetName: NetpDcInitializeContext failed. %ld\n", (unsigned int)NameIp);
        v25 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = 112;
          goto LABEL_15;
        }
        goto LABEL_312;
      }
      TickCount = GetTickCount();
      v77 = NlPingDcNameWithContext(
              (struct _NL_GETDC_CONTEXT *)hMem,
              1u,
              1u,
              0x190u,
              &v124,
              (struct _NL_DC_CACHE_ENTRY **)&SourceString);
      v78 = v77;
      *(_QWORD *)(hMem + 96) = 0;
      *(_DWORD *)(hMem + 16) &= 0xFFFFF0FF;
      if ( v77 )
      {
        NlPrintRoutine(2u, L"NetpDcGetName: ping of cached entry failed: ( NlDcCacheEntry=0x%p ) 0x%x\n", v128, v77);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v79, v80, v128, v78);
        if ( v78 != 1317 )
          NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v128);
        NetpDcDerefCacheEntry(v128);
        v128 = 0;
      }
      else
      {
        NetpDcDerefCacheEntry(v128);
        v128 = (struct _NL_DC_CACHE_ENTRY *)SourceString;
        *((_DWORD *)SourceString + 106) = *((_DWORD *)SourceString + 5);
        *((_DWORD *)v128 + 5) = v75;
      }
      v81 = NetpDcElapsedTime(TickCount);
      v82 = a14 - v81;
      if ( a14 <= v81 )
        v82 = a14;
      a14 = v82;
      v48 = (unsigned int *)v128;
    }
    else
    {
      NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v64);
      NetpDcDerefCacheEntry(v128);
      v48 = 0;
      v128 = 0;
    }
    goto LABEL_167;
  }
LABEL_205:
  started = NetpStartLocatorDiscovery();
  if ( !started )
  {
    _InterlockedAdd64(&qword_1800F1E30, 1u);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(hMem + 112) + 360LL) + 176LL), 1u);
    LODWORD(NameIp) = 1355;
    NetpUpdatePerfCountersEnd((struct _NL_GETDC_CONTEXT *)hMem, 0x54Bu);
    NlPrintRoutine(2u, L"NetpDcGetName: failing the request due to max limit of concurrent discovery attempts\n");
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
    return (unsigned int)NameIp;
  }
  v96 = hMem;
  if ( !*(_QWORD *)(hMem + 160) && !*(_QWORD *)(hMem + 128) )
  {
    v97 = NetpDcInitializeContext(
            a1,
            a2,
            a3,
            v17,
            *(_DWORD *)(hMem + 32),
            v20,
            v18,
            v19,
            a9,
            Buf1,
            a11,
            0,
            0,
            0,
            a12,
            a13,
            2,
            (struct _NL_GETDC_CONTEXT **)&hMem);
    LODWORD(NameIp) = v97;
    if ( v97 )
    {
      NlPrintRoutine(0x100u, L"NetpDcGetName: NetpDcInitializeContext failed. %ld\n", v97);
      v25 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 121;
        goto LABEL_15;
      }
      goto LABEL_312;
    }
    v96 = hMem;
  }
  if ( *(_BYTE *)(v96 + 232) )
  {
    NlPrintRoutine(2u, L"NetpDcGetName: urgent ping mode is enabled\n");
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
    if ( a15 > 1 )
    {
      NlPrintRoutine(2u, L"NetpDcGetName: resetting RetryCount to 1\n");
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
      a15 = 1;
    }
    v96 = hMem;
  }
  v98 = *(_DWORD *)(v96 + 276);
  *(_DWORD *)(hMem + 212) = GetTickCount();
  *(_DWORD *)(hMem + 208) = 0;
  if ( *(_DWORD *)(hMem + 208) >= a15 )
    goto LABEL_318;
  v99 = (char)lpWideCharStr;
  v100 = 1;
  v101 = 0;
  v102 = v98 == 0;
  while ( 1 )
  {
    if ( !*(_QWORD *)(hMem + 56) )
    {
LABEL_235:
      v100 = 0;
      goto LABEL_247;
    }
    if ( !v100 )
      goto LABEL_247;
    NameIp = NetpDcGetNameIp((struct _NL_GETDC_CONTEXT *)hMem, &v128, &v124);
    NlPrintRoutine(2u, L"NetpDcGetName: NetpDcGetNameIp for %ws returned %ld\n", *(_QWORD *)(hMem + 56), NameIp);
    LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_SL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
        *(_QWORD *)(hMem + 56),
        NameIp);
    if ( !(_DWORD)NameIp )
      break;
    switch ( (_DWORD)NameIp )
    {
      case 0x267B:
        goto LABEL_235;
      case 0x79:
        v101 = 1;
        if ( !*(_DWORD *)(hMem + 276) && *(_DWORD *)(hMem + 272) )
          v102 = (*(_DWORD *)(hMem + 16) >> 17) & 1;
        break;
      case 0x54B:
        v100 = 0;
        if ( !*(_DWORD *)(hMem + 276) && *(_DWORD *)(hMem + 272) )
          v102 = (*(_DWORD *)(hMem + 16) >> 17) & 1;
        break;
      default:
        if ( (*(_DWORD *)(hMem + 16) & 0x20000) == 0 )
        {
          NlPrintRoutine(
            0x100u,
            L"NetpDcGetName: %ws: cannot find DC via IP/DNS %ld\n",
            *(_QWORD *)(hMem + 72),
            (unsigned int)NameIp);
          v37 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v38 = 125;
            goto LABEL_48;
          }
          goto LABEL_24;
        }
        if ( !*(_DWORD *)(hMem + 276) )
          v102 = 1;
        break;
    }
LABEL_247:
    if ( !*(_QWORD *)(hMem + 48) )
      goto LABEL_256;
    if ( v102 )
    {
      *(_DWORD *)(hMem + 236) |= 2u;
      NameIp = NetpDcGetNameNetbios((struct _NL_GETDC_CONTEXT *)hMem, &v128, &v124);
      *(_DWORD *)(hMem + 236) &= ~2u;
      NlPrintRoutine(2u, L"NetpDcGetName: NetpDcGetNameNetbios for %ws returned %ld\n", *(_QWORD *)(hMem + 48), NameIp);
      LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          *(_QWORD *)(hMem + 48),
          NameIp);
      switch ( (_DWORD)NameIp )
      {
        case 0:
          v44 = 1;
          goto LABEL_356;
        case 0x79:
          v101 = 1;
          break;
        case 0x54B:
LABEL_256:
          v102 = 0;
          break;
        case 0xBD1:
          v102 = 0;
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: NetpDcGetNameNetbios for %ws returned ERROR_REMOTE_MAILSLOTS_DEPRECATED (%d)\n",
            *(_QWORD *)(hMem + 48),
            3025);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              127,
              &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *(_QWORD *)(hMem + 72));
          break;
        default:
          NlPrintRoutine(
            0x100u,
            L"NetpDcGetName: %ws: cannot find DC via Netbios %ld\n",
            *(_QWORD *)(hMem + 72),
            (unsigned int)NameIp);
          v37 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v38 = 128;
            goto LABEL_48;
          }
          goto LABEL_24;
      }
    }
    if ( !v100 && !v102 )
    {
      NlPrintRoutine(0x100u, L"NetpDcGetName: %ws: IP and Netbios are both done.\n", *(_QWORD *)(hMem + 72));
      v109 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v110 = 129;
        goto LABEL_317;
      }
      goto LABEL_318;
    }
    if ( !v101 )
    {
      NlPrintRoutine(0x100u, L"NetpDcGetName: %ws: no datagrams were sent\n", *(_QWORD *)(hMem + 72));
      v109 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v110 = 130;
LABEL_317:
        WPP_SF_S(*((_QWORD *)v109 + 2), v110, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids, *(_QWORD *)(hMem + 72));
      }
LABEL_318:
      LODWORD(NameIp) = 1355;
      goto LABEL_319;
    }
    if ( v99 )
    {
      PingResponse = NetpDcGetPingResponse((struct _NL_GETDC_CONTEXT *)hMem, 0xC8u, &v128, &v124);
      LODWORD(NameIp) = PingResponse;
      if ( PingResponse != 121 )
      {
        if ( !PingResponse )
          goto LABEL_312;
        NlPrintRoutine(
          0x100u,
          L"NetpDcGetName: %ws: Cannot NetpDcGetPingResponse. %ld\n",
          *(_QWORD *)(hMem + 72),
          PingResponse);
        v25 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_312;
        v111 = 131;
LABEL_311:
        WPP_SF_SL(
          *((_QWORD *)v25 + 2),
          v111,
          (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          *(_QWORD *)(hMem + 72),
          NameIp);
        goto LABEL_312;
      }
      v104 = *(_DWORD *)(hMem + 12);
      if ( (v104 & 0x2020) == 0 )
      {
        NlPrintRoutine(2u, L"NetpDcGetName: %ws: Only try once done.\n", *(_QWORD *)(hMem + 72));
        v109 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v110 = 132;
          goto LABEL_317;
        }
        goto LABEL_318;
      }
      if ( *(_QWORD *)(hMem + 216) )
      {
        if ( (v104 & 0x20) != 0 )
        {
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws: Tried once to find NT 5.0 DC (Using found NT 4.0 DC).\n",
            *(_QWORD *)(hMem + 72));
          v109 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v110 = 133;
            goto LABEL_317;
          }
        }
        else if ( (v104 & 0x2000) != 0 )
        {
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws: Tried once to find good timeserver (Using previously found DC).\n",
            *(_QWORD *)(hMem + 72));
          v109 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v110 = 134;
            goto LABEL_317;
          }
        }
        goto LABEL_318;
      }
      *(_DWORD *)(hMem + 12) = v104 & 0xFFFFFFDF;
      NlPrintRoutine(2u, L"NetpDcGetName: %ws: Only try once reset.\n", *(_QWORD *)(hMem + 72));
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)(NameIp + 14),
          &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          *(_QWORD *)(hMem + 72));
      LOBYTE(lpWideCharStr) = 0;
      v99 = 0;
    }
    v105 = NetpDcElapsedTime(*(_DWORD *)(hMem + 212));
    v106 = a14 * (*(_DWORD *)(hMem + 208) + 1) / a15;
    if ( v106 <= v105 || (v107 = v106 - v105, v107 <= 0x7D0) )
      v107 = 2000;
    v108 = NetpDcGetPingResponse((struct _NL_GETDC_CONTEXT *)hMem, v107, &v128, &v124);
    LODWORD(NameIp) = v108;
    if ( v108 != 121 )
    {
      if ( !v108 )
        goto LABEL_312;
      NlPrintRoutine(0x100u, L"NetpDcGetName: %ws: Cannot NetpDcGetPingResponse. %ld\n", *(_QWORD *)(hMem + 72), v108);
      v25 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_312;
      v111 = 137;
      goto LABEL_311;
    }
    if ( !*(_QWORD *)(hMem + 216) && ++*(_DWORD *)(hMem + 208) < a15 )
      continue;
    goto LABEL_318;
  }
  if ( (*(_DWORD *)(hMem + 12) & 0x40000) == 0 )
    goto LABEL_333;
  v44 = v125;
  if ( v128 )
    *((_DWORD *)v128 + 67) |= 0x20u;
LABEL_356:
  if ( (*((_BYTE *)v128 + 268) & 0x10) == 0 )
  {
    if ( (*((_QWORD *)v128 + 31) || (*((_BYTE *)v128 + 264) & 0x10) != 0) && (*(_BYTE *)(hMem + 16) & 1) != 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
      v116 = (unsigned __int16 *)*((_QWORD *)v128 + 31);
      if ( IsEnabled )
        NlSetDynamicSiteName(v116);
      else
        NlSetDynamicSiteName_Old((BYTE *)v116);
    }
    NetpDcInsertCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v128);
  }
  if ( (*(_BYTE *)(hMem + 16) & 0x20) != 0 )
  {
    v25 = (ScannerInfoNameMappings *)*((_QWORD *)v128 + 7);
    if ( v25 )
    {
      v24 = (const unsigned __int16 *)*((_QWORD *)v128 + 29);
      if ( v24 )
      {
        if ( !(unsigned int)NlEqualDnsName((const unsigned __int16 *)v25, v24) )
        {
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws: Domain isn't the root domain %ws %ws.\n",
            *(_QWORD *)(hMem + 72),
            *((_QWORD *)v128 + 7),
            *((_QWORD *)v128 + 29));
          LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_SSS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              141,
              (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *(_QWORD *)(hMem + 72),
              *((_QWORD *)v128 + 7),
              *((_QWORD *)v128 + 29));
          LODWORD(NameIp) = 1355;
        }
      }
    }
  }
  if ( v44 && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
    McTemplateU0zzz_EventWriteTransfer(
      (_DWORD)v25,
      (_DWORD)v24,
      *((_QWORD *)v128 + 7),
      *((_QWORD *)v128 + 6),
      *((_QWORD *)v128 + 10));
  if ( (_DWORD)NameIp )
    goto LABEL_24;
  if ( v124 )
  {
    LODWORD(NameIp) = NetpGetBetterDc((struct _NL_GETDC_CONTEXT *)hMem, a14, a15, &v128);
    if ( (_DWORD)NameIp )
      goto LABEL_24;
  }
  v33 = a12;
  if ( a16 )
    LODWORD(NameIp) = NetpCreateDCInfoFromCacheEntry(
                        v124,
                        a12,
                        *(_DWORD *)(hMem + 12),
                        *(unsigned __int16 **)(hMem + 48),
                        *(const unsigned __int16 **)(hMem + 72),
                        v128,
                        a16);
LABEL_380:
  v32 = Buffer;
LABEL_26:
  if ( (NlGlobalParameters & 2) != 0 && NlGlobalMemberWorkstation )
  {
    if ( !(_DWORD)NameIp )
    {
      if ( (*((_BYTE *)v128 + 268) & 2) != 0
        && !v124
        && (*(_BYTE *)(hMem + 12) & 1) != 0
        && (*(_BYTE *)(hMem + 16) & 5) == 5
        && !*(_QWORD *)(hMem + 24)
        && (unsigned int)(*(_DWORD *)(hMem + 4) - 1) <= 1 )
      {
        v34 = (char *)LocalAlloc(0x40u, 0xC8u);
        v35 = v34;
        if ( v34 )
        {
          DsFlagsToString(v33, v34);
          LODWORD(v121) = *(_DWORD *)(hMem + 208);
          LODWORD(v120) = *(_DWORD *)(hMem + 184);
          LODWORD(v119) = *(_DWORD *)(hMem + 196);
          LODWORD(v118) = *(_DWORD *)(hMem + 192);
          NlPrintRoutine(
            2u,
            L"LoadBalanceDebug (Flags: %hs): DC=%ws, SrvCount=%lu, FailedAQueryCount=%lu, DcsPinged=%lu, LoopIndex=%lu\n",
            v35,
            *((_QWORD *)v128 + 9),
            v118,
            v119,
            v120,
            v121);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_sSLLLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              *((_QWORD *)v128 + 9),
              v36,
              (_DWORD)v35,
              *((_QWORD *)v128 + 9),
              *(_DWORD *)(hMem + 192),
              *(_DWORD *)(hMem + 196),
              *(_DWORD *)(hMem + 184),
              *(_DWORD *)(hMem + 208));
          LocalFree(v35);
        }
      }
LABEL_383:
      if ( a17 )
      {
        *a17 = v128;
        v128 = 0;
      }
    }
  }
  else if ( !(_DWORD)NameIp )
  {
    goto LABEL_383;
  }
  NetpUpdatePerfCountersEnd((struct _NL_GETDC_CONTEXT *)hMem, NameIp);
  NetpDcUninitializeContext((HLOCAL)hMem);
  if ( started )
  {
    AcquireSRWLockExclusive(&NlLocatorDiscoveryCounterLock);
    --NlLocatorDiscoveriesInProgress;
    ReleaseSRWLockExclusive(&NlLocatorDiscoveryCounterLock);
  }
  if ( v130 )
    NetpMemoryFree(v130);
  if ( v128 )
    NetpDcDerefCacheEntry(v128);
  if ( v32 )
    NetApiBufferFree(v32);
  return (unsigned int)NameIp;
}

```

## disassembly

```asm
0x180078f00  mov     rax, rsp
0x180078f03  mov     [rax+20h], r9
0x180078f07  mov     [rax+18h], r8
0x180078f0b  mov     [rax+10h], rdx
0x180078f0f  mov     [rax+8], rcx
0x180078f13  push    rbp
0x180078f14  push    rbx
0x180078f15  push    rsi
0x180078f16  push    rdi
0x180078f17  push    r12
0x180078f19  push    r13
0x180078f1b  push    r14
0x180078f1d  push    r15
0x180078f1f  lea     rbp, [rax-47h]
0x180078f23  sub     rsp, 0C8h
0x180078f2a  mov     rax, [rbp+3Fh+arg_78]
0x180078f31  mov     rsi, r9
0x180078f34  mov     [rbp+3Fh+var_58], 0
0x180078f3c  mov     r10, rcx
0x180078f3f  mov     [rbp+3Fh+var_64], 0
0x180078f46  mov     [rbp+3Fh+var_68], 0
0x180078f4d  mov     [rbp+3Fh+var_48], 0
0x180078f55  mov     [rbp+3Fh+var_60], 0
0x180078f5c  mov     [rbp+3Fh+var_6C], 0
0x180078f63  mov     [rbp+3Fh+Buffer], 0
0x180078f6b  mov     [rbp+3Fh+var_70], 0
0x180078f6f  test    rax, rax
0x180078f72  jz      short loc_180078F7B
0x180078f74  mov     qword ptr [rax], 0
0x180078f7b  mov     rax, [rbp+3Fh+arg_80]
0x180078f82  test    rax, rax
0x180078f85  jz      short loc_180078F8E
0x180078f87  mov     qword ptr [rax], 0
0x180078f8e  mov     r14, [rbp+3Fh+lpWideCharStr]
0x180078f92  test    r14, r14
0x180078f95  jz      short loc_180078FA4
0x180078f97  movzx   eax, word ptr [r14]
0x180078f9b  neg     ax
0x180078f9e  sbb     rcx, rcx
0x180078fa1  and     r14, rcx
0x180078fa4  mov     r13, [rbp+3Fh+hMem]
0x180078fab  test    r13, r13
0x180078fae  jz      short loc_180078FBE
0x180078fb0  movzx   eax, word ptr [r13+0]
0x180078fb5  neg     ax
0x180078fb8  sbb     rcx, rcx
0x180078fbb  and     r13, rcx
0x180078fbe  mov     r12, [rbp+3Fh+SourceString]
0x180078fc2  test    r12, r12
0x180078fc5  jz      short loc_180078FD5
0x180078fc7  movzx   eax, word ptr [r12]
0x180078fcc  neg     ax
0x180078fcf  sbb     rcx, rcx
0x180078fd2  and     r12, rcx
0x180078fd5  mov     eax, [rbp+3Fh+arg_60]
0x180078fdb  lea     rcx, [rbp+3Fh+hMem]
0x180078fe2  mov     r15, [rbp+3Fh+Buf1]
0x180078fe9  bts     eax, 7
0x180078fed  mov     [rsp+88h], rcx; struct _NL_GETDC_CONTEXT **
0x180078ff5  mov     edi, 1
0x180078ffa  mov     dword ptr [rsp+100h+var_80], edi; char
0x180079001  mov     rcx, r10; void *
0x180079004  mov     [rsp+100h+var_88], eax; unsigned int
0x180079008  mov     eax, [rbp+3Fh+arg_58]
0x18007900e  mov     dword ptr [rsp+100h+var_90], eax; unsigned int
0x180079012  mov     rax, [rbp+3Fh+arg_50]
0x180079019  mov     dword ptr [rsp+100h+var_98], 0; unsigned int
0x180079021  mov     [rsp+100h+var_A0], 0; struct _SOCKET_ADDRESS *
0x18007902a  mov     [rsp+100h+var_A8], 0; unsigned __int16 *
0x180079033  mov     [rsp+100h+var_B0], rax; unsigned int
0x180079038  mov     rax, [rbp+3Fh+arg_40]
0x18007903f  mov     [rsp+100h+var_B8], r15; struct _GUID *
0x180079044  mov     [rsp+100h+var_C0], rax; void *
0x180079049  mov     eax, [rbp+3Fh+arg_20]
0x18007904c  mov     [rsp+100h+var_C8], r13; unsigned __int16 *
0x180079051  mov     [rsp+100h+var_D0], r14; unsigned __int16 *
0x180079056  mov     [rsp+100h+var_D8], r12; unsigned __int16 *
0x18007905b  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x18007905f  mov     [rbp+3Fh+hMem], 0
0x18007906a  call    ?NetpDcInitializeContext@@YAKPEAXPEBG11K1110PEAU_GUID@@11PEAU_SOCKET_ADDRESS@@KKKKPEAPEAU_NL_GETDC_CONTEXT@@@Z; NetpDcInitializeContext(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ushort const *,_SOCKET_ADDRESS *,ulong,ulong,ulong,ulong,_NL_GETDC_CONTEXT * *)
0x18007906f  mov     ebx, eax
0x180079071  test    eax, eax
0x180079073  jz      short loc_1800790BF
0x180079075  mov     r8d, eax
0x180079078  lea     rdx, aNetpdcgetnameN_3; "NetpDcGetName: NetpDcInitializeContext "...
0x18007907f  mov     ecx, 100h; unsigned int
0x180079084  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180079089  mov     rcx, cs:WPP_GLOBAL_Control
0x180079090  test    byte ptr [rcx+1Ch], 4
0x180079094  jz      loc_18007A907
0x18007909a  cmp     byte ptr [rcx+19h], 2
0x18007909e  jb      loc_18007A907
0x1800790a4  lea     edx, [rdi+60h]
0x1800790a7  mov     rcx, [rcx+10h]
0x1800790ab  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x1800790b2  mov     r9d, ebx
0x1800790b5  call    WPP_SF_l
0x1800790ba  jmp     loc_18007A907
0x1800790bf  mov     rcx, [rbp+3Fh+hMem]; struct _NL_GETDC_CONTEXT *
0x1800790c6  call    ?NetpUpdatePerfCountersStart@@YAXPEAU_NL_GETDC_CONTEXT@@@Z; NetpUpdatePerfCountersStart(_NL_GETDC_CONTEXT *)
0x1800790cb  mov     r9, [rbp+3Fh+hMem]
0x1800790d2  mov     r8d, [r9+0Ch]
0x1800790d6  mov     ecx, r8d
0x1800790d9  and     ecx, 0FFFFFFC0h
0x1800790dc  shl     ecx, 19h
0x1800790df  mov     edx, ecx
0x1800790e1  bts     edx, 1Dh
0x1800790e5  bt      r8d, 9
0x1800790ea  cmovnb  edx, ecx
0x1800790ed  mov     ebx, edx
0x1800790ef  bts     ebx, 1Ch
0x1800790f3  test    r8b, 80h
0x1800790f7  cmovz   ebx, edx
0x1800790fa  bt      r8d, 0Eh
0x1800790ff  jb      loc_1800793DB
0x180079105  xor     edi, edi
0x180079107  test    r14, r14
0x18007910a  jz      loc_180079289
0x180079110  xor     r8d, r8d; int
0x180079113  xor     edx, edx; lpMultiByteStr
0x180079115  mov     rcx, r14; lpWideCharStr
0x180079118  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18007911d  mov     rdi, rax
0x180079120  test    rax, rax
0x180079123  jnz     loc_180079282
0x180079129  lea     ebx, [rax+8]
0x18007912c  mov     rsi, [rbp+3Fh+Buffer]
0x180079130  mov     r14d, [rbp+3Fh+arg_58]
0x180079137  test    byte ptr cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 2; _NETLOGON_PARAMETERS NlGlobalParameters
0x18007913e  jz      loc_18007AE9F
0x180079144  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x18007914b  jz      loc_18007AE9F
0x180079151  test    ebx, ebx
0x180079153  jnz     loc_18007AEBE
0x180079159  mov     rax, [rbp+3Fh+var_58]
0x18007915d  test    byte ptr [rax+10Ch], 2
0x180079164  jz      loc_18007AEA3
0x18007916a  cmp     [rbp+3Fh+var_6C], ebx
0x18007916d  jnz     loc_18007AEA3
0x180079173  mov     rcx, [rbp+3Fh+hMem]
0x18007917a  test    byte ptr [rcx+0Ch], 1
0x18007917e  jz      loc_18007AEA3
0x180079184  mov     eax, [rcx+10h]
0x180079187  and     eax, 5
0x18007918a  cmp     al, 5
0x18007918c  jnz     loc_18007AEA3
0x180079192  cmp     qword ptr [rcx+18h], 0
0x180079197  jnz     loc_18007AEA3
0x18007919d  mov     eax, [rcx+4]
0x1800791a0  dec     eax
0x1800791a2  cmp     eax, 1
0x1800791a5  ja      loc_18007AEA3
0x1800791ab  mov     edx, 0C8h; uBytes
0x1800791b0  lea     ecx, [rbx+40h]; uFlags
0x1800791b3  call    cs:__imp_LocalAlloc
0x1800791b9  mov     rdi, rax
0x1800791bc  test    rax, rax
0x1800791bf  jz      loc_18007AEA3
0x1800791c5  mov     rdx, rax; char *
0x1800791c8  mov     ecx, r14d; unsigned int
0x1800791cb  call    ?DsFlagsToString@@YAXKPEAD@Z; DsFlagsToString(ulong,char *)
0x1800791d0  mov     rdx, [rbp+3Fh+hMem]
0x1800791d7  mov     r8, rdi
0x1800791da  mov     r9, [rbp+3Fh+var_58]
0x1800791de  mov     ecx, [rdx+0D0h]
0x1800791e4  mov     r9, [r9+48h]
0x1800791e8  mov     dword ptr [rsp+100h+var_C8], ecx
0x1800791ec  mov     ecx, [rdx+0B8h]
0x1800791f2  mov     dword ptr [rsp+100h+var_D0], ecx
0x1800791f6  mov     ecx, [rdx+0C4h]
0x1800791fc  mov     dword ptr [rsp+100h+var_D8], ecx
0x180079200  mov     ecx, [rdx+0C0h]
0x180079206  lea     rdx, aLoadbalancedeb; "LoadBalanceDebug (Flags: %hs): DC=%ws, "...
0x18007920d  mov     dword ptr [rsp+100h+var_E0], ecx
0x180079211  lea     ecx, [rbx+2]; unsigned int
0x180079214  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180079219  mov     rcx, cs:WPP_GLOBAL_Control
0x180079220  test    byte ptr [rcx+1Ch], 4
0x180079224  jz      short loc_180079274
0x180079226  cmp     byte ptr [rcx+19h], 4
0x18007922a  jb      short loc_180079274
0x18007922c  mov     rdx, [rbp+3Fh+hMem]
0x180079233  mov     r9, rdi
0x180079236  mov     rcx, [rcx+10h]
0x18007923a  mov     eax, [rdx+0D0h]
0x180079240  mov     dword ptr [rsp+100h+var_C0], eax
0x180079244  mov     eax, [rdx+0B8h]
0x18007924a  mov     dword ptr [rsp+100h+var_C8], eax
0x18007924e  mov     eax, [rdx+0C4h]
0x180079254  mov     dword ptr [rsp+100h+var_D0], eax
0x180079258  mov     eax, [rdx+0C0h]
0x18007925e  mov     dword ptr [rsp+100h+var_D8], eax
0x180079262  mov     rax, [rbp+3Fh+var_58]
0x180079266  mov     rdx, [rax+48h]
0x18007926a  mov     [rsp+100h+var_E0], rdx
0x18007926f  call    WPP_SF_sSLLLL
0x180079274  mov     rcx, rdi; hMem
0x180079277  call    cs:__imp_LocalFree
0x18007927d  jmp     loc_18007AEA3
0x180079282  mov     r9, [rbp+3Fh+hMem]
0x180079289  xor     ecx, ecx
0x18007928b  lea     rax, [rbp+3Fh+var_60]
0x18007928f  mov     [rsp+100h+var_90], rax; unsigned int *
0x180079294  or      ebx, 4000000Eh
0x18007929a  cmp     dword ptr [r9+4], 5
0x18007929f  lea     rax, [rbp+3Fh+var_48]
0x1800792a3  mov     [rsp+100h+var_98], rax; void **
0x1800792a8  mov     r8, rdi; char *
0x1800792ab  mov     eax, [r9+20h]
0x1800792af  setz    cl
0x1800792b2  mov     [rsp+100h+var_A0], 0; struct sockaddr *
0x1800792bb  mov     rdx, r12; SourceString
0x1800792be  mov     dword ptr [rsp+100h+var_A8], ebx; unsigned int
0x1800792c2  mov     dword ptr [rsp+100h+var_B8], eax; unsigned int
0x1800792c6  mov     rax, [r9+18h]
0x1800792ca  mov     [rsp+100h+var_C0], rax; unsigned __int16 *
0x1800792cf  mov     rax, [r9+58h]
0x1800792d3  mov     [rsp+100h+var_C8], rax; unsigned __int16 *
0x1800792d8  mov     rax, [r9+50h]
0x1800792dc  mov     r9, r15; Buf1
0x1800792df  mov     [rsp+100h+var_D0], rax; unsigned __int16 *
0x1800792e4  mov     rax, [rbp+3Fh+arg_40]
0x1800792eb  mov     dword ptr [rsp+100h+var_D8], ecx; int
0x1800792ef  lea     rcx, aLocal; "<Local>"
0x1800792f6  mov     [rsp+100h+var_E0], rax; void *
0x1800792fb  call    ?NlGetLocalPingResponse@@YAKPEBG0PEBDPEAU_GUID@@PEAXH000KKKPEAUsockaddr@@PEAPEAXPEAK@Z; NlGetLocalPingResponse(ushort const *,ushort const *,char const *,_GUID *,void *,int,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,sockaddr *,void * *,ulong *)
0x180079300  mov     ebx, eax
0x180079302  test    rdi, rdi
0x180079305  jz      short loc_180079310
0x180079307  mov     rcx, rdi; Buffer
0x18007930a  call    cs:__imp_NetApiBufferFree
0x180079310  cmp     ebx, 54Bh
0x180079316  jz      loc_1800793CF
0x18007931c  test    ebx, ebx
0x18007931e  jz      short loc_180079383
0x180079320  mov     r8, [rbp+3Fh+hMem]
0x180079327  lea     rdx, aNetpdcgetnameW_7; "NetpDcGetName: %ws: cannot get local pi"...
0x18007932e  mov     r9d, ebx
0x180079331  mov     ecx, 100h; unsigned int
0x180079336  mov     r8, [r8+48h]
0x18007933a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007933f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079346  test    byte ptr [rcx+1Ch], 4
0x18007934a  jz      loc_18007912C
0x180079350  cmp     byte ptr [rcx+19h], 2
0x180079354  jb      loc_18007912C
0x18007935a  mov     edx, 62h ; 'b'
0x18007935f  mov     r9, [rbp+3Fh+hMem]
0x180079366  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007936d  mov     rcx, [rcx+10h]
0x180079371  mov     dword ptr [rsp+100h+var_E0], ebx
0x180079375  mov     r9, [r9+48h]
0x180079379  call    WPP_SF_SL
0x18007937e  jmp     loc_18007912C
0x180079383  mov     r8d, [rbp+3Fh+var_60]; unsigned int
0x180079387  lea     rax, [rbp+3Fh+var_6C]
0x18007938b  mov     rdx, [rbp+3Fh+var_48]; void *
0x18007938f  mov     r9d, 4; unsigned int
0x180079395  mov     rcx, [rbp+3Fh+hMem]; struct _NL_GETDC_CONTEXT *
0x18007939c  mov     [rsp+100h+var_D0], rax; int *
0x1800793a1  lea     rax, [rbp+3Fh+var_58]
0x1800793a5  mov     [rsp+100h+var_D8], rax; struct _NL_DC_CACHE_ENTRY **
0x1800793aa  mov     [rsp+100h+var_E0], 0; struct _NL_DC_ADDRESS *
0x1800793b3  call    ?NetpDcHandlePingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@PEAXKKPEAU_NL_DC_ADDRESS@@PEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z; NetpDcHandlePingResponse(_NL_GETDC_CONTEXT *,void *,ulong,ulong,_NL_DC_ADDRESS *,_NL_DC_CACHE_ENTRY * *,int *)
0x1800793b8  mov     ebx, eax
0x1800793ba  cmp     eax, 0Dh
0x1800793bd  jz      short loc_1800793CF
0x1800793bf  cmp     eax, 79h ; 'y'
0x1800793c2  jz      short loc_1800793CF
0x1800793c4  cmp     eax, 525h
0x1800793c9  jnz     loc_18007A907
0x1800793cf  mov     r9, [rbp+3Fh+hMem]
0x1800793d6  mov     edi, 1
0x1800793db  mov     eax, [r9+10h]
0x1800793df  xor     bl, bl
0x1800793e1  and     eax, 4001h
0x1800793e6  mov     r15d, 100h
0x1800793ec  cmp     eax, edi
0x1800793ee  jnz     loc_18007948C
0x1800793f4  cmp     cs:?NlGlobalJoinLogicDone@@3HA, 0; int NlGlobalJoinLogicDone
0x1800793fb  jnz     loc_18007948C
0x180079401  call    ?NlCacheJoinDomainControllerInfo@@YAKXZ; NlCacheJoinDomainControllerInfo(void)
0x180079406  mov     ebx, eax
0x180079408  mov     ecx, r15d; unsigned int
0x18007940b  test    eax, eax
0x18007940d  jz      short loc_180079443
0x18007940f  mov     r8d, eax
0x180079412  lea     rdx, aNetpdcgetnameN_1; "NetpDcGetName: NlCacheJoinDomainControl"...
0x180079419  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007941e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079425  test    byte ptr [rcx+1Ch], 4
0x180079429  jz      loc_18007A907
0x18007942f  cmp     byte ptr [rcx+19h], 2
0x180079433  jb      loc_18007A907
0x180079439  mov     edx, 63h ; 'c'
0x18007943e  jmp     loc_1800790A7
0x180079443  lea     rdx, aNetpdcgetnameN_5; "NetpDcGetName: NlCacheJoinDomainControl"...
0x18007944a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007944f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079456  test    byte ptr [rcx+1Ch], 4
  ... truncated ...
```
