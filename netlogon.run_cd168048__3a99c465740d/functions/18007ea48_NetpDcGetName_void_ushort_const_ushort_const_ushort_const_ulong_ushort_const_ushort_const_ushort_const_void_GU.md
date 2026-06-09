# NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)

- ea: `0x18007ea48`
- end: `0x180080aff`
- name: `?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z`
- size: `8375`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int, PCWSTR SourceString, LPCWCH lpWideCharStr, HLOCAL hMem, void *, struct _GUID *Buf1, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, struct _DOMAIN_CONTROLLER_INFOW **, struct _NL_DC_CACHE_ENTRY **)`
- caller_count: `5`
- callee_count: `44`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180029218`
- `0x180069290`
- `0x18007e3bc`
- `0x180082df8`
- `0x180083020`

## callees

- `0x180003250`
- `0x1800037f0`
- `0x180007518`
- `0x180009e3c`
- `0x18000a564`
- `0x18000af78`
- `0x18000b394`
- `0x18000b7bc`
- `0x18000bdf4`
- `0x18000c130`
- `0x18000c4e8`
- `0x18000c98c`
- `0x18000ca40`
- `0x18000ca88`
- `0x18000d324`
- `0x18000d358`
- `0x18000d528`
- `0x180018f38`
- `0x18001906c`
- `0x1800191e4`
- `0x180025a74`
- `0x18002d6bc`
- `0x180035744`
- `0x18003b32c`
- `0x18004412c`
- `0x180049848`
- `0x180074294`
- `0x18007a9a4`
- `0x18007dd80`
- `0x18007e224`
- `0x18007ea48`
- `0x180080b08`
- `0x180080f74`
- `0x180081e40`
- `0x180082a84`
- `0x180082df8`
- `0x180083020`
- `0x180083ed8`
- `0x180084098`
- `0x180084178`
- `0x180084240`
- `0x180084764`
- `0x1800847c0`
- `0x1800892fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800805c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800805c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f94a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008062c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800806ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080754`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f94a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008062c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800806ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080754`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080aac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080aac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080a93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f9fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fbc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800806ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008085d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f9fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fbc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800806ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008085d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007ecfb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007ecfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007edc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007edc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180080781`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180080781`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007f779`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007fe66`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800806f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007f779`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007fe66`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800806f9`
- `netutils!NetApiBufferFree` at `0x18007ee5e`
- `netutils!NetApiBufferFree` at `0x180080adc`
- `netutils!NetApiBufferFree` at `0x18007ee5e`
- `netutils!NetApiBufferFree` at `0x180080adc`

## string_xrefs

- `0x18007ef6c`: `NetpDcGetName: NlCacheJoinDomainControllerInfo returned failure code: %ld\n`
- `0x18007ef9d`: `NetpDcGetName: NlCacheJoinDomainControllerInfo returned success\n`
- `0x18007f051`: `NetpDcGetName: %ws force-use of cached info due to low-power-mode ( NlDcCacheEntry = 0x%p ) \n`
- `0x18007f0a2`: `NetpDcGetName: no cached DC found in low power mode.\n`
- `0x18007f17e`: `NetpDcGetName: %ws cache is too old, need to redo discovery. %ld\n`
- `0x18007f249`: `NetpDcGetName: %ws cache not for closest site and it is too old. %ld\n`
- `0x18007f2ec`: `NetpDcGetName: %ws cache not for closest site and user wants to find a next closest site which we have not tried it yet. %ld\n`
- `0x18007f435`: `NetpDcGetName: %ws cache doesn't have right account name.\n`
- `0x18007f3c2`: `NetpDcGetName: %ws cache is too old. %ld\n`
- `0x18007f575`: `NetpDcGetName: %ws cache says use ldap but has no address\n`
- `0x18007f62b`: `NetpDcGetName: %ws cache says use maislot but has no Netbios name\n`
- `0x18007f7ff`: `NetpDcGetName: ping of cached entry failed: ( NlDcCacheEntry=0x%p ) 0x%x\n`
- `0x18007f8c5`: `NetpDcGetName: %ws using cached information ( NlDcCacheEntry = 0x%p )\n`
- `0x18007fb55`: `NetpDcGetName: %ws is permanently negative cached.\n`
- `0x18007fc88`: `NetpDcGetName: failing the request due to max limit of concurrent discovery attempts\n`
- `0x18008065f`: `Cache: %ws %ws: Ditch cache entry list %ld since force couldn't find DC\n`
- `0x1800807f0`: `Cache: %ws %ws: Cache entry %ld marked permanently negative.\n`

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
  __int64 v112; // rdx
  __int64 v113; // rcx
  unsigned int GcUsingNetbios; // eax
  unsigned __int64 v115; // r8
  struct _FILETIME *v116; // rcx
  char IsEnabled; // al
  unsigned __int16 *v118; // rcx
  struct _NL_DC_ADDRESS *v120; // [rsp+28h] [rbp-A1h]
  struct _NL_DC_CACHE_ENTRY **v121; // [rsp+30h] [rbp-99h]
  LPVOID *v122; // [rsp+38h] [rbp-91h]
  unsigned __int16 *v123; // [rsp+40h] [rbp-89h]
  unsigned int v124; // [rsp+58h] [rbp-71h]
  unsigned __int8 started; // [rsp+98h] [rbp-31h]
  int v126; // [rsp+9Ch] [rbp-2Dh] BYREF
  int v127; // [rsp+A0h] [rbp-29h]
  int v128; // [rsp+A4h] [rbp-25h] BYREF
  unsigned int v129; // [rsp+A8h] [rbp-21h] BYREF
  struct _NL_DC_CACHE_ENTRY *v130; // [rsp+B0h] [rbp-19h] BYREF
  LPVOID Buffer; // [rsp+B8h] [rbp-11h]
  void *v132; // [rsp+C0h] [rbp-9h] BYREF

  v17 = a4;
  v130 = 0;
  v128 = 0;
  v127 = 0;
  v132 = 0;
  v129 = 0;
  v126 = 0;
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
      WPP_SF_l(*((_QWORD *)v25 + 2), v26, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids, (unsigned int)NameIp);
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
                        v124,
                        v30 | 0x4000000E,
                        0,
                        &v132,
                        &v129);
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
            (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
            *(_QWORD *)(hMem + 72),
            NameIp);
        }
        goto LABEL_24;
      }
      v39 = NetpDcHandlePingResponse((struct _NL_GETDC_CONTEXT *)hMem, v132, v129, 4u, 0, &v130, &v126);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
    v40 = 1;
    *(_DWORD *)(hMem + 12) &= ~1u;
    v27 = (HLOCAL)hMem;
  }
  if ( g_LowPowerNQMState )
  {
    NlPrintRoutine(0x100u, L"NetpDcGetName: running in low-power mode (FORCE will be ignored).\n", v28, v27);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
    CacheEntry = NetpDcFindCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, &v126, &v128);
    v130 = CacheEntry;
    if ( CacheEntry )
    {
      NlPrintRoutine(
        0x100u,
        L"NetpDcGetName: %ws force-use of cached info due to low-power-mode ( NlDcCacheEntry = 0x%p ) \n",
        *(_QWORD *)(hMem + 72),
        CacheEntry);
      LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v43, *(_QWORD *)(hMem + 72), (char)v130);
      LODWORD(NameIp) = 0;
      v44 = 0;
      goto LABEL_356;
    }
    NlPrintRoutine(0x100u, L"NetpDcGetName: no cached DC found in low power mode.\n");
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
    goto LABEL_318;
  }
  LOBYTE(lpWideCharStr) = 0;
  if ( (*((_BYTE *)v27 + 12) & 1) == 0 )
  {
    v45 = 0;
    v46 = 0;
    v47 = NetpDcFindCacheEntry((struct _NL_GETDC_CONTEXT *)v27, &v126, &v128);
    v130 = v47;
    v48 = (unsigned int *)v47;
    if ( v47 )
    {
      v49 = NetpDcElapsedTime(*((_DWORD *)v47 + 5));
      v48 = (unsigned int *)v130;
      v45 = v49;
      v50 = *((_DWORD *)v130 + 106);
      if ( v50 )
      {
        v51 = NetpDcElapsedTime(v50);
        v48 = (unsigned int *)v130;
        v46 = v51;
      }
    }
    if ( v48 )
    {
      if ( (*(_DWORD *)(hMem + 12) & 0x100) == 0 )
      {
        v52 = (unsigned int)dword_1800F830C > 0x418937 ? -1 : 1000 * dword_1800F830C;
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
            v54 = NetpDcElapsedTime(*((_DWORD *)v130 + 5));
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              104,
              (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
              *(_QWORD *)(hMem + 72),
              v54);
          }
          NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v130);
          NetpDcDerefCacheEntry(v130);
          v48 = 0;
          v130 = 0;
          if ( v40 )
            goto LABEL_104;
          *(_DWORD *)(hMem + 12) |= 1u;
          v48 = (unsigned int *)v130;
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
              v57 = NetpDcElapsedTime(*((_DWORD *)v130 + 5));
              WPP_SF_SL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
                *(_QWORD *)(hMem + 72),
                v57);
            }
            NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v130);
LABEL_103:
            NetpDcDerefCacheEntry(v130);
            v48 = 0;
            v130 = 0;
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
              v59 = NetpDcElapsedTime(*((_DWORD *)v130 + 5));
              WPP_SF_SL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                106,
                (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
                *(_QWORD *)(hMem + 72),
                v59);
            }
            goto LABEL_103;
          }
        }
      }
    }
LABEL_104:
    v60 = dword_1800F819C;
    if ( (*(_DWORD *)(hMem + 12) & 0x100) != 0 )
      v60 = dword_1800F8198;
    if ( v60 > 0x418937 )
      v61 = -1;
    else
      v61 = 1000 * v60;
    if ( !v48 )
    {
LABEL_172:
      _InterlockedAdd64(&qword_1800F8D80, 1u);
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(hMem + 112) + 360LL) + 64LL), 1u);
      EnterCriticalSection(&NlDcCritSect);
      v84 = hMem;
      v85 = *(_DWORD *)(*(_QWORD *)(hMem + 112) + 40LL * *(int *)(hMem + 4) + 112);
      if ( v85 )
      {
        v86 = NetpDcElapsedTime(v85);
        v87 = v86;
        v84 = hMem;
        if ( v86 < 1000 * dword_1800F8188 )
        {
          NlPrintRoutine(2u, L"NetpDcGetName: %ws similar query failed recently %ld\n", *(_QWORD *)(hMem + 72), v86);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              115,
              (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
          LODWORD(v120) = 1000 * *(_DWORD *)(v89 + 40LL * *(int *)(v84 + 4) + 116);
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws similar background query failed recently %ld %ld\n",
            *(_QWORD *)(v84 + 72),
            v87,
            v120);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_Sll(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              116,
              (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
              *(_QWORD *)(hMem + 72),
              v87,
              -24 * *(_BYTE *)(*(_QWORD *)(hMem + 112) + 40LL * *(int *)(hMem + 4) + 116));
          goto LABEL_177;
        }
        if ( dword_1800F8194 )
        {
          HasElapsed = NlTimeHasElapsedEx(
                         (union _LARGE_INTEGER *)(v89 + 128 + 40LL * *(int *)(v84 + 4)),
                         &stru_1800F82F8,
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
              &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
                  &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
                  *(_QWORD *)(hMem + 72));
              LODWORD(v25) = hMem;
              v130 = *(struct _NL_DC_CACHE_ENTRY **)(hMem + 216);
              v126 = *(unsigned __int8 *)(hMem + 224);
              *(_QWORD *)(hMem + 216) = 0;
LABEL_171:
              LODWORD(NameIp) = 0;
              v44 = 0;
              goto LABEL_356;
            }
            if ( dword_1800F6224[8 * *(int *)(hMem + 8)] == 4 )
            {
              v112 = *(_QWORD *)(hMem + 48);
              if ( v112 )
              {
                v113 = *(_QWORD *)(hMem + 56);
                if ( !v113 || !(unsigned int)_o__wcsicmp(v113, v112) )
                {
                  GcUsingNetbios = NetpGetGcUsingNetbios((struct _NL_GETDC_CONTEXT *)hMem, a14, a15, &v130);
                  LODWORD(NameIp) = GcUsingNetbios;
                  if ( !GcUsingNetbios )
                  {
                    v126 = 0;
LABEL_333:
                    v44 = v127;
                    goto LABEL_356;
                  }
                  if ( GcUsingNetbios != 1355 )
                    goto LABEL_24;
                }
              }
            }
            if ( (*(_BYTE *)(hMem + 16) & 8) == 0 )
            {
              if ( (*(_BYTE *)(hMem + 12) & 1) != 0 )
              {
                EnterCriticalSection(&NlDcCritSect);
                NetpDcFreeCacheEntryList((struct _LIST_ENTRY *)(*(_QWORD *)(hMem + 112)
                                                              + 8 * (5LL * *(int *)(hMem + 4) + 12)));
                LODWORD(v120) = *(_DWORD *)(hMem + 4);
                NlPrintRoutine(
                  0x20000u,
                  L"Cache: %ws %ws: Ditch cache entry list %ld since force couldn't find DC\n",
                  *(_QWORD *)(hMem + 112) + 36LL,
                  *(_QWORD *)(*(_QWORD *)(hMem + 112) + 72LL),
                  v120);
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
            v115 = hMem;
            v116 = (struct _FILETIME *)(*(_QWORD *)(hMem + 112) + 8 * (5LL * *(int *)(hMem + 4) + 16));
            if ( !*(_QWORD *)v116 )
            {
              GetSystemTimeAsFileTime(v116);
              *(_DWORD *)(*(_QWORD *)(hMem + 112) + 40LL * *(int *)(hMem + 4) + 116) = dword_1800F818C;
              v115 = hMem;
            }
            if ( (*(_DWORD *)(v115 + 16) & 0x1000) != 0 )
            {
              if ( *(_BYTE *)(v115 + 229) )
              {
                if ( !*(_BYTE *)(v115 + 228) )
                {
                  *(_BYTE *)(*(_QWORD *)(v115 + 112) + 40 * (*(int *)(v115 + 4) + 3LL)) = 1;
                  LODWORD(v120) = *(_DWORD *)(hMem + 4);
                  NlPrintRoutine(
                    0x4000u,
                    L"Cache: %ws %ws: Cache entry %ld marked permanently negative.\n",
                    *(_QWORD *)(hMem + 112) + 36LL,
                    *(_QWORD *)(*(_QWORD *)(hMem + 112) + 72LL),
                    v120);
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
              v44 = v127;
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
        if ( *(_DWORD *)(v95 + 40LL * *(int *)(hMem + 4) + 116) > (unsigned int)dword_1800F8190 )
          *(_DWORD *)(v95 + 40LL * *(int *)(hMem + 4) + 116) = dword_1800F8190;
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
            &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
            *(_QWORD *)(hMem + 72));
        LOBYTE(lpWideCharStr) = 1;
      }
      v17 = a4;
      goto LABEL_205;
    }
    if ( v128 )
    {
      NlPrintRoutine(2u, L"NetpDcGetName: %ws cache doesn't have right account name.\n", *(_QWORD *)(hMem + 72));
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
          *(_QWORD *)(hMem + 72));
    }
    else
    {
      if ( v46 <= v61 && (v48[106] || v45 <= v61) )
      {
LABEL_167:
        if ( v48 )
        {
          _InterlockedIncrement64(&qword_1800F8D78);
          _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(hMem + 112) + 360LL) + 56LL));
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws using cached information ( NlDcCacheEntry = 0x%p )\n",
            *(_QWORD *)(hMem + 72),
            v130);
          LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, v83, *(_QWORD *)(hMem + 72), (char)v130);
          goto LABEL_171;
        }
        goto LABEL_172;
      }
      v62 = NetpDcElapsedTime(v48[5]);
      NlPrintRoutine(2u, L"NetpDcGetName: %ws cache is too old. %ld\n", *(_QWORD *)(hMem + 72), v62);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v63 = NetpDcElapsedTime(*((_DWORD *)v130 + 5));
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
          *(_QWORD *)(hMem + 72),
          v63);
      }
    }
    v64 = v130;
    v65 = *((_DWORD *)v130 + 67);
    if ( (v65 & 2) != 0 )
    {
      v66 = (struct _SOCKET_ADDRESS *)((char *)v130 + 88);
      if ( *((_DWORD *)v130 + 24) )
      {
        if ( !dword_1800F8308 && v66->lpSockaddr->sa_family == 23 )
          v66 = (struct _SOCKET_ADDRESS *)((char *)v130 + 280);
        v67 = NetpDcProcessAddressList(
                (struct _NL_GETDC_CONTEXT *)hMem,
                *((unsigned __int16 **)v130 + 10),
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
        v68 = *((_QWORD *)v130 + 10);
        if ( v68 )
        {
          *(_QWORD *)(hMem + 96) = v68;
          *(_DWORD *)(hMem + 16) |= 0x100u;
        }
        else
        {
          v69 = *((_QWORD *)v130 + 9);
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
        WPP_SF_S(*((_QWORD *)v70 + 2), v71, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids, *(_QWORD *)(hMem + 72));
      }
    }
    else
    {
      if ( (v65 & 1) == 0 )
        goto LABEL_150;
      v72 = *((_QWORD *)v130 + 9);
      if ( v72 && *((_QWORD *)v130 + 6) )
      {
        *(_QWORD *)(hMem + 96) = v72;
        v73 = hMem;
        if ( !*(_QWORD *)(hMem + 48) )
        {
          v74 = (void *)NetpAllocWStrFromWStr(*((void **)v130 + 6));
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
    v64 = v130;
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
        NetpDcDerefCacheEntry(v130);
        v130 = 0;
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
              &v126,
              (struct _NL_DC_CACHE_ENTRY **)&SourceString);
      v78 = v77;
      *(_QWORD *)(hMem + 96) = 0;
      *(_DWORD *)(hMem + 16) &= 0xFFFFF0FF;
      if ( v77 )
      {
        NlPrintRoutine(2u, L"NetpDcGetName: ping of cached entry failed: ( NlDcCacheEntry=0x%p ) 0x%x\n", v130, v77);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v79, v80, v130, v78);
        if ( v78 != 1317 )
          NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v130);
        NetpDcDerefCacheEntry(v130);
        v130 = 0;
      }
      else
      {
        NetpDcDerefCacheEntry(v130);
        v130 = (struct _NL_DC_CACHE_ENTRY *)SourceString;
        *((_DWORD *)SourceString + 106) = *((_DWORD *)SourceString + 5);
        *((_DWORD *)v130 + 5) = v75;
      }
      v81 = NetpDcElapsedTime(TickCount);
      v82 = a14 - v81;
      if ( a14 <= v81 )
        v82 = a14;
      a14 = v82;
      v48 = (unsigned int *)v130;
    }
    else
    {
      NetpDcRemoveCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v64);
      NetpDcDerefCacheEntry(v130);
      v48 = 0;
      v130 = 0;
    }
    goto LABEL_167;
  }
LABEL_205:
  started = NetpStartLocatorDiscovery();
  if ( !started )
  {
    _InterlockedAdd64(&qword_1800F8DF0, 1u);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(hMem + 112) + 360LL) + 176LL), 1u);
    LODWORD(NameIp) = 1355;
    NetpUpdatePerfCountersEnd((struct _NL_GETDC_CONTEXT *)hMem, 0x54Bu);
    NlPrintRoutine(2u, L"NetpDcGetName: failing the request due to max limit of concurrent discovery attempts\n");
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
    if ( a15 > 1 )
    {
      NlPrintRoutine(2u, L"NetpDcGetName: resetting RetryCount to 1\n");
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
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
    NameIp = NetpDcGetNameIp((struct _NL_GETDC_CONTEXT *)hMem, &v130, &v126);
    NlPrintRoutine(2u, L"NetpDcGetName: NetpDcGetNameIp for %ws returned %ld\n", *(_QWORD *)(hMem + 56), NameIp);
    LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_SL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
      NameIp = NetpDcGetNameNetbios((struct _NL_GETDC_CONTEXT *)hMem, &v130, &v126);
      *(_DWORD *)(hMem + 236) &= ~2u;
      NlPrintRoutine(2u, L"NetpDcGetName: NetpDcGetNameNetbios for %ws returned %ld\n", *(_QWORD *)(hMem + 48), NameIp);
      LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
              &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
        WPP_SF_S(*((_QWORD *)v109 + 2), v110, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids, *(_QWORD *)(hMem + 72));
      }
LABEL_318:
      LODWORD(NameIp) = 1355;
      goto LABEL_319;
    }
    if ( v99 )
    {
      PingResponse = NetpDcGetPingResponse((struct _NL_GETDC_CONTEXT *)hMem, 0xC8u, &v130, &v126);
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
          (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
          &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
          *(_QWORD *)(hMem + 72));
      LOBYTE(lpWideCharStr) = 0;
      v99 = 0;
    }
    v105 = NetpDcElapsedTime(*(_DWORD *)(hMem + 212));
    v106 = a14 * (*(_DWORD *)(hMem + 208) + 1) / a15;
    if ( v106 <= v105 || (v107 = v106 - v105, v107 <= 0x7D0) )
      v107 = 2000;
    v108 = NetpDcGetPingResponse((struct _NL_GETDC_CONTEXT *)hMem, v107, &v130, &v126);
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
  v44 = v127;
  if ( v130 )
    *((_DWORD *)v130 + 67) |= 0x20u;
LABEL_356:
  if ( (*((_BYTE *)v130 + 268) & 0x10) == 0 )
  {
    if ( (*((_QWORD *)v130 + 31) || (*((_BYTE *)v130 + 264) & 0x10) != 0) && (*(_BYTE *)(hMem + 16) & 1) != 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
      v118 = (unsigned __int16 *)*((_QWORD *)v130 + 31);
      if ( IsEnabled )
        NlSetDynamicSiteName(v118);
      else
        NlSetDynamicSiteName_Old((BYTE *)v118);
    }
    NetpDcInsertCacheEntry((struct _NL_GETDC_CONTEXT *)hMem, v130);
  }
  if ( (*(_BYTE *)(hMem + 16) & 0x20) != 0 )
  {
    v25 = (ScannerInfoNameMappings *)*((_QWORD *)v130 + 7);
    if ( v25 )
    {
      v24 = (const unsigned __int16 *)*((_QWORD *)v130 + 29);
      if ( v24 )
      {
        if ( !(unsigned int)NlEqualDnsName((const unsigned __int16 *)v25, v24) )
        {
          NlPrintRoutine(
            2u,
            L"NetpDcGetName: %ws: Domain isn't the root domain %ws %ws.\n",
            *(_QWORD *)(hMem + 72),
            *((_QWORD *)v130 + 7),
            *((_QWORD *)v130 + 29));
          LODWORD(v25) = (_DWORD)WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_SSS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              141,
              (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
              *(_QWORD *)(hMem + 72),
              *((_QWORD *)v130 + 7),
              *((_QWORD *)v130 + 29));
          LODWORD(NameIp) = 1355;
        }
      }
    }
  }
  if ( v44 && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
    McTemplateU0zzz_EventWriteTransfer(
      (_DWORD)v25,
      (_DWORD)v24,
      *((_QWORD *)v130 + 7),
      *((_QWORD *)v130 + 6),
      *((_QWORD *)v130 + 10));
  if ( (_DWORD)NameIp )
    goto LABEL_24;
  if ( v126 )
  {
    LODWORD(NameIp) = NetpGetBetterDc((struct _NL_GETDC_CONTEXT *)hMem, a14, a15, &v130);
    if ( (_DWORD)NameIp )
      goto LABEL_24;
  }
  v33 = a12;
  if ( a16 )
    LODWORD(NameIp) = NetpCreateDCInfoFromCacheEntry(
                        v126,
                        a12,
                        *(_DWORD *)(hMem + 12),
                        *(const unsigned __int16 **)(hMem + 48),
                        *(const unsigned __int16 **)(hMem + 72),
                        v130,
                        a16);
LABEL_380:
  v32 = Buffer;
LABEL_26:
  if ( (NlGlobalParameters & 2) != 0 && NlGlobalMemberWorkstation )
  {
    if ( !(_DWORD)NameIp )
    {
      if ( (*((_BYTE *)v130 + 268) & 2) != 0
        && !v126
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
          LODWORD(v123) = *(_DWORD *)(hMem + 208);
          LODWORD(v122) = *(_DWORD *)(hMem + 184);
          LODWORD(v121) = *(_DWORD *)(hMem + 196);
          LODWORD(v120) = *(_DWORD *)(hMem + 192);
          NlPrintRoutine(
            2u,
            L"LoadBalanceDebug (Flags: %hs): DC=%ws, SrvCount=%lu, FailedAQueryCount=%lu, DcsPinged=%lu, LoopIndex=%lu\n",
            v35,
            *((_QWORD *)v130 + 9),
            v120,
            v121,
            v122,
            v123);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_sSLLLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              *((_QWORD *)v130 + 9),
              v36,
              (_DWORD)v35,
              *((_QWORD *)v130 + 9),
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
        *a17 = v130;
        v130 = 0;
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
  if ( v132 )
    NetpMemoryFree(v132);
  if ( v130 )
    NetpDcDerefCacheEntry(v130);
  if ( v32 )
    NetApiBufferFree(v32);
  return (unsigned int)NameIp;
}

```

## disassembly

```asm
0x18007ea48  mov     rax, rsp
0x18007ea4b  mov     [rax+20h], r9
0x18007ea4f  mov     [rax+18h], r8
0x18007ea53  mov     [rax+10h], rdx
0x18007ea57  mov     [rax+8], rcx
0x18007ea5b  push    rbp
0x18007ea5c  push    rbx
0x18007ea5d  push    rsi
0x18007ea5e  push    rdi
0x18007ea5f  push    r12
0x18007ea61  push    r13
0x18007ea63  push    r14
0x18007ea65  push    r15
0x18007ea67  lea     rbp, [rax-47h]
0x18007ea6b  sub     rsp, 0C8h
0x18007ea72  mov     rax, [rbp+3Fh+arg_78]
0x18007ea79  mov     rsi, r9
0x18007ea7c  mov     [rbp+3Fh+var_58], 0
0x18007ea84  mov     r10, rcx
0x18007ea87  mov     [rbp+3Fh+var_64], 0
0x18007ea8e  mov     [rbp+3Fh+var_68], 0
0x18007ea95  mov     [rbp+3Fh+var_48], 0
0x18007ea9d  mov     [rbp+3Fh+var_60], 0
0x18007eaa4  mov     [rbp+3Fh+var_6C], 0
0x18007eaab  mov     [rbp+3Fh+Buffer], 0
0x18007eab3  mov     [rbp+3Fh+var_70], 0
0x18007eab7  test    rax, rax
0x18007eaba  jz      short loc_18007EAC3
0x18007eabc  mov     qword ptr [rax], 0
0x18007eac3  mov     rax, [rbp+3Fh+arg_80]
0x18007eaca  test    rax, rax
0x18007eacd  jz      short loc_18007EAD6
0x18007eacf  mov     qword ptr [rax], 0
0x18007ead6  mov     r14, [rbp+3Fh+lpWideCharStr]
0x18007eada  test    r14, r14
0x18007eadd  jz      short loc_18007EAEC
0x18007eadf  movzx   eax, word ptr [r14]
0x18007eae3  neg     ax
0x18007eae6  sbb     rcx, rcx
0x18007eae9  and     r14, rcx
0x18007eaec  mov     r13, [rbp+3Fh+hMem]
0x18007eaf3  test    r13, r13
0x18007eaf6  jz      short loc_18007EB06
0x18007eaf8  movzx   eax, word ptr [r13+0]
0x18007eafd  neg     ax
0x18007eb00  sbb     rcx, rcx
0x18007eb03  and     r13, rcx
0x18007eb06  mov     r12, [rbp+3Fh+SourceString]
0x18007eb0a  test    r12, r12
0x18007eb0d  jz      short loc_18007EB1D
0x18007eb0f  movzx   eax, word ptr [r12]
0x18007eb14  neg     ax
0x18007eb17  sbb     rcx, rcx
0x18007eb1a  and     r12, rcx
0x18007eb1d  mov     eax, [rbp+3Fh+arg_60]
0x18007eb23  lea     rcx, [rbp+3Fh+hMem]
0x18007eb2a  mov     r15, [rbp+3Fh+Buf1]
0x18007eb31  bts     eax, 7
0x18007eb35  mov     [rsp+88h], rcx; struct _NL_GETDC_CONTEXT **
0x18007eb3d  mov     edi, 1
0x18007eb42  mov     dword ptr [rsp+100h+var_80], edi; char
0x18007eb49  mov     rcx, r10; void *
0x18007eb4c  mov     [rsp+100h+var_88], eax; unsigned int
0x18007eb50  mov     eax, [rbp+3Fh+arg_58]
0x18007eb56  mov     dword ptr [rsp+100h+var_90], eax; unsigned int
0x18007eb5a  mov     rax, [rbp+3Fh+arg_50]
0x18007eb61  mov     dword ptr [rsp+100h+var_98], 0; unsigned int
0x18007eb69  mov     [rsp+100h+var_A0], 0; struct _SOCKET_ADDRESS *
0x18007eb72  mov     [rsp+100h+var_A8], 0; unsigned __int16 *
0x18007eb7b  mov     [rsp+100h+var_B0], rax; unsigned int
0x18007eb80  mov     rax, [rbp+3Fh+arg_40]
0x18007eb87  mov     [rsp+100h+var_B8], r15; struct _GUID *
0x18007eb8c  mov     [rsp+100h+var_C0], rax; void *
0x18007eb91  mov     eax, [rbp+3Fh+arg_20]
0x18007eb94  mov     [rsp+100h+var_C8], r13; unsigned __int16 *
0x18007eb99  mov     [rsp+100h+var_D0], r14; unsigned __int16 *
0x18007eb9e  mov     [rsp+100h+var_D8], r12; unsigned __int16 *
0x18007eba3  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x18007eba7  mov     [rbp+3Fh+hMem], 0
0x18007ebb2  call    ?NetpDcInitializeContext@@YAKPEAXPEBG11K1110PEAU_GUID@@11PEAU_SOCKET_ADDRESS@@KKKKPEAPEAU_NL_GETDC_CONTEXT@@@Z; NetpDcInitializeContext(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ushort const *,_SOCKET_ADDRESS *,ulong,ulong,ulong,ulong,_NL_GETDC_CONTEXT * *)
0x18007ebb7  mov     ebx, eax
0x18007ebb9  test    eax, eax
0x18007ebbb  jz      short loc_18007EC07
0x18007ebbd  mov     r8d, eax
0x18007ebc0  lea     rdx, aNetpdcgetnameN_3; "NetpDcGetName: NetpDcInitializeContext "...
0x18007ebc7  mov     ecx, 100h; unsigned int
0x18007ebcc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007ebd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ebd8  test    byte ptr [rcx+1Ch], 4
0x18007ebdc  jz      loc_18008047F
0x18007ebe2  cmp     byte ptr [rcx+19h], 2
0x18007ebe6  jb      loc_18008047F
0x18007ebec  lea     edx, [rdi+60h]
0x18007ebef  mov     rcx, [rcx+10h]
0x18007ebf3  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18007ebfa  mov     r9d, ebx
0x18007ebfd  call    WPP_SF_l
0x18007ec02  jmp     loc_18008047F
0x18007ec07  mov     rcx, [rbp+3Fh+hMem]; struct _NL_GETDC_CONTEXT *
0x18007ec0e  call    ?NetpUpdatePerfCountersStart@@YAXPEAU_NL_GETDC_CONTEXT@@@Z; NetpUpdatePerfCountersStart(_NL_GETDC_CONTEXT *)
0x18007ec13  mov     r9, [rbp+3Fh+hMem]
0x18007ec1a  mov     r8d, [r9+0Ch]
0x18007ec1e  mov     ecx, r8d
0x18007ec21  and     ecx, 0FFFFFFC0h
0x18007ec24  shl     ecx, 19h
0x18007ec27  mov     edx, ecx
0x18007ec29  bts     edx, 1Dh
0x18007ec2d  bt      r8d, 9
0x18007ec32  cmovnb  edx, ecx
0x18007ec35  mov     ebx, edx
0x18007ec37  bts     ebx, 1Ch
0x18007ec3b  test    r8b, 80h
0x18007ec3f  cmovz   ebx, edx
0x18007ec42  bt      r8d, 0Eh
0x18007ec47  jb      loc_18007EF35
0x18007ec4d  xor     edi, edi
0x18007ec4f  test    r14, r14
0x18007ec52  jz      loc_18007EDDD
0x18007ec58  xor     r8d, r8d; int
0x18007ec5b  xor     edx, edx; lpMultiByteStr
0x18007ec5d  mov     rcx, r14; lpWideCharStr
0x18007ec60  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18007ec65  mov     rdi, rax
0x18007ec68  test    rax, rax
0x18007ec6b  jnz     loc_18007EDD6
0x18007ec71  lea     ebx, [rax+8]
0x18007ec74  mov     rsi, [rbp+3Fh+Buffer]
0x18007ec78  mov     r14d, [rbp+3Fh+arg_58]
0x18007ec7f  test    byte ptr cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 2; _NETLOGON_PARAMETERS NlGlobalParameters
0x18007ec86  jz      loc_180080A4D
0x18007ec8c  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x18007ec93  jz      loc_180080A4D
0x18007ec99  test    ebx, ebx
0x18007ec9b  jnz     loc_180080A6C
0x18007eca1  mov     rax, [rbp+3Fh+var_58]
0x18007eca5  test    byte ptr [rax+10Ch], 2
0x18007ecac  jz      loc_180080A51
0x18007ecb2  cmp     [rbp+3Fh+var_6C], ebx
0x18007ecb5  jnz     loc_180080A51
0x18007ecbb  mov     rcx, [rbp+3Fh+hMem]
0x18007ecc2  test    byte ptr [rcx+0Ch], 1
0x18007ecc6  jz      loc_180080A51
0x18007eccc  mov     eax, [rcx+10h]
0x18007eccf  and     eax, 5
0x18007ecd2  cmp     al, 5
0x18007ecd4  jnz     loc_180080A51
0x18007ecda  cmp     qword ptr [rcx+18h], 0
0x18007ecdf  jnz     loc_180080A51
0x18007ece5  mov     eax, [rcx+4]
0x18007ece8  dec     eax
0x18007ecea  cmp     eax, 1
0x18007eced  ja      loc_180080A51
0x18007ecf3  mov     edx, 0C8h; uBytes
0x18007ecf8  lea     ecx, [rbx+40h]; uFlags
0x18007ecfb  call    cs:__imp_LocalAlloc
0x18007ed02  nop     dword ptr [rax+rax+00h]
0x18007ed07  mov     rdi, rax
0x18007ed0a  test    rax, rax
0x18007ed0d  jz      loc_180080A51
0x18007ed13  mov     rdx, rax; char *
0x18007ed16  mov     ecx, r14d; unsigned int
0x18007ed19  call    ?DsFlagsToString@@YAXKPEAD@Z; DsFlagsToString(ulong,char *)
0x18007ed1e  mov     rdx, [rbp+3Fh+hMem]
0x18007ed25  mov     r8, rdi
0x18007ed28  mov     r9, [rbp+3Fh+var_58]
0x18007ed2c  mov     ecx, [rdx+0D0h]
0x18007ed32  mov     r9, [r9+48h]
0x18007ed36  mov     dword ptr [rsp+100h+var_C8], ecx
0x18007ed3a  mov     ecx, [rdx+0B8h]
0x18007ed40  mov     dword ptr [rsp+100h+var_D0], ecx
0x18007ed44  mov     ecx, [rdx+0C4h]
0x18007ed4a  mov     dword ptr [rsp+100h+var_D8], ecx
0x18007ed4e  mov     ecx, [rdx+0C0h]
0x18007ed54  lea     rdx, aLoadbalancedeb; "LoadBalanceDebug (Flags: %hs): DC=%ws, "...
0x18007ed5b  mov     dword ptr [rsp+100h+var_E0], ecx
0x18007ed5f  lea     ecx, [rbx+2]; unsigned int
0x18007ed62  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007ed67  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed6e  test    byte ptr [rcx+1Ch], 4
0x18007ed72  jz      short loc_18007EDC2
0x18007ed74  cmp     byte ptr [rcx+19h], 4
0x18007ed78  jb      short loc_18007EDC2
0x18007ed7a  mov     rdx, [rbp+3Fh+hMem]
0x18007ed81  mov     r9, rdi
0x18007ed84  mov     rcx, [rcx+10h]
0x18007ed88  mov     eax, [rdx+0D0h]
0x18007ed8e  mov     dword ptr [rsp+100h+var_C0], eax
0x18007ed92  mov     eax, [rdx+0B8h]
0x18007ed98  mov     dword ptr [rsp+100h+var_C8], eax
0x18007ed9c  mov     eax, [rdx+0C4h]
0x18007eda2  mov     dword ptr [rsp+100h+var_D0], eax
0x18007eda6  mov     eax, [rdx+0C0h]
0x18007edac  mov     dword ptr [rsp+100h+var_D8], eax
0x18007edb0  mov     rax, [rbp+3Fh+var_58]
0x18007edb4  mov     rdx, [rax+48h]
0x18007edb8  mov     [rsp+100h+var_E0], rdx
0x18007edbd  call    WPP_SF_sSLLLL
0x18007edc2  mov     rcx, rdi; hMem
0x18007edc5  call    cs:__imp_LocalFree
0x18007edcc  nop     dword ptr [rax+rax+00h]
0x18007edd1  jmp     loc_180080A51
0x18007edd6  mov     r9, [rbp+3Fh+hMem]
0x18007eddd  xor     ecx, ecx
0x18007eddf  lea     rax, [rbp+3Fh+var_60]
0x18007ede3  mov     [rsp+100h+var_90], rax; unsigned int *
0x18007ede8  or      ebx, 4000000Eh
0x18007edee  cmp     dword ptr [r9+4], 5
0x18007edf3  lea     rax, [rbp+3Fh+var_48]
0x18007edf7  mov     [rsp+100h+var_98], rax; void **
0x18007edfc  mov     r8, rdi; char *
0x18007edff  mov     eax, [r9+20h]
0x18007ee03  setz    cl
0x18007ee06  mov     [rsp+100h+var_A0], 0; struct sockaddr *
0x18007ee0f  mov     rdx, r12; SourceString
0x18007ee12  mov     dword ptr [rsp+100h+var_A8], ebx; unsigned int
0x18007ee16  mov     dword ptr [rsp+100h+var_B8], eax; unsigned int
0x18007ee1a  mov     rax, [r9+18h]
0x18007ee1e  mov     [rsp+100h+var_C0], rax; unsigned __int16 *
0x18007ee23  mov     rax, [r9+58h]
0x18007ee27  mov     [rsp+100h+var_C8], rax; unsigned __int16 *
0x18007ee2c  mov     rax, [r9+50h]
0x18007ee30  mov     r9, r15; Buf1
0x18007ee33  mov     [rsp+100h+var_D0], rax; unsigned __int16 *
0x18007ee38  mov     rax, [rbp+3Fh+arg_40]
0x18007ee3f  mov     dword ptr [rsp+100h+var_D8], ecx; int
0x18007ee43  lea     rcx, aLocal; "<Local>"
0x18007ee4a  mov     [rsp+100h+var_E0], rax; void *
0x18007ee4f  call    ?NlGetLocalPingResponse@@YAKPEBG0PEBDPEAU_GUID@@PEAXH000KKKPEAUsockaddr@@PEAPEAXPEAK@Z; NlGetLocalPingResponse(ushort const *,ushort const *,char const *,_GUID *,void *,int,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,sockaddr *,void * *,ulong *)
0x18007ee54  mov     ebx, eax
0x18007ee56  test    rdi, rdi
0x18007ee59  jz      short loc_18007EE6A
0x18007ee5b  mov     rcx, rdi; Buffer
0x18007ee5e  call    cs:__imp_NetApiBufferFree
0x18007ee65  nop     dword ptr [rax+rax+00h]
0x18007ee6a  cmp     ebx, 54Bh
0x18007ee70  jz      loc_18007EF29
0x18007ee76  test    ebx, ebx
0x18007ee78  jz      short loc_18007EEDD
0x18007ee7a  mov     r8, [rbp+3Fh+hMem]
0x18007ee81  lea     rdx, aNetpdcgetnameW_7; "NetpDcGetName: %ws: cannot get local pi"...
0x18007ee88  mov     r9d, ebx
0x18007ee8b  mov     ecx, 100h; unsigned int
0x18007ee90  mov     r8, [r8+48h]
0x18007ee94  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007ee99  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eea0  test    byte ptr [rcx+1Ch], 4
0x18007eea4  jz      loc_18007EC74
0x18007eeaa  cmp     byte ptr [rcx+19h], 2
0x18007eeae  jb      loc_18007EC74
0x18007eeb4  mov     edx, 62h ; 'b'
0x18007eeb9  mov     r9, [rbp+3Fh+hMem]
0x18007eec0  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18007eec7  mov     rcx, [rcx+10h]
0x18007eecb  mov     dword ptr [rsp+100h+var_E0], ebx
0x18007eecf  mov     r9, [r9+48h]
0x18007eed3  call    WPP_SF_SL
0x18007eed8  jmp     loc_18007EC74
0x18007eedd  mov     r8d, [rbp+3Fh+var_60]; unsigned int
0x18007eee1  lea     rax, [rbp+3Fh+var_6C]
0x18007eee5  mov     rdx, [rbp+3Fh+var_48]; void *
0x18007eee9  mov     r9d, 4; unsigned int
0x18007eeef  mov     rcx, [rbp+3Fh+hMem]; struct _NL_GETDC_CONTEXT *
0x18007eef6  mov     [rsp+100h+var_D0], rax; int *
0x18007eefb  lea     rax, [rbp+3Fh+var_58]
0x18007eeff  mov     [rsp+100h+var_D8], rax; struct _NL_DC_CACHE_ENTRY **
0x18007ef04  mov     [rsp+100h+var_E0], 0; struct _NL_DC_ADDRESS *
0x18007ef0d  call    ?NetpDcHandlePingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@PEAXKKPEAU_NL_DC_ADDRESS@@PEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z; NetpDcHandlePingResponse(_NL_GETDC_CONTEXT *,void *,ulong,ulong,_NL_DC_ADDRESS *,_NL_DC_CACHE_ENTRY * *,int *)
0x18007ef12  mov     ebx, eax
0x18007ef14  cmp     eax, 0Dh
0x18007ef17  jz      short loc_18007EF29
0x18007ef19  cmp     eax, 79h ; 'y'
0x18007ef1c  jz      short loc_18007EF29
0x18007ef1e  cmp     eax, 525h
0x18007ef23  jnz     loc_18008047F
0x18007ef29  mov     r9, [rbp+3Fh+hMem]
0x18007ef30  mov     edi, 1
0x18007ef35  mov     eax, [r9+10h]
0x18007ef39  xor     bl, bl
0x18007ef3b  and     eax, 4001h
0x18007ef40  mov     r15d, 100h
0x18007ef46  cmp     eax, edi
0x18007ef48  jnz     loc_18007EFE6
0x18007ef4e  cmp     cs:?NlGlobalJoinLogicDone@@3HA, 0; int NlGlobalJoinLogicDone
0x18007ef55  jnz     loc_18007EFE6
0x18007ef5b  call    ?NlCacheJoinDomainControllerInfo@@YAKXZ; NlCacheJoinDomainControllerInfo(void)
0x18007ef60  mov     ebx, eax
0x18007ef62  mov     ecx, r15d; unsigned int
0x18007ef65  test    eax, eax
0x18007ef67  jz      short loc_18007EF9D
0x18007ef69  mov     r8d, eax
0x18007ef6c  lea     rdx, aNetpdcgetnameN_1; "NetpDcGetName: NlCacheJoinDomainControl"...
0x18007ef73  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007ef78  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ef7f  test    byte ptr [rcx+1Ch], 4
0x18007ef83  jz      loc_18008047F
0x18007ef89  cmp     byte ptr [rcx+19h], 2
0x18007ef8d  jb      loc_18008047F
0x18007ef93  mov     edx, 63h ; 'c'
0x18007ef98  jmp     loc_18007EBEF
0x18007ef9d  lea     rdx, aNetpdcgetnameN_5; "NetpDcGetName: NlCacheJoinDomainControl"...
  ... truncated ...
```
