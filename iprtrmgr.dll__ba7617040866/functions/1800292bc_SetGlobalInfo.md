# SetGlobalInfo

- ea: `0x1800292bc`
- end: `0x18002a4e0`
- name: `SetGlobalInfo`
- size: `4644`
- prototype: ``
- caller_count: `5`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800236d4`
- `0x18003dd20`
- `0x18003dd70`
- `0x18003ddc0`
- `0x18003dde0`

## callees

- `0x180002878`
- `0x18000ac60`
- `0x180011790`
- `0x1800150c8`
- `0x180015550`
- `0x180016d68`
- `0x18001e490`
- `0x18001f194`
- `0x1800292bc`
- `0x180035b58`
- `0x18003c1ac`
- `0x18003d534`
- `0x180057bac`
- `0x180057c8c`
- `0x180057cd0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800295c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800295cf`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800295c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800295cf`
- `ntdll!RtlReleaseResource` at `0x180029615`
- `ntdll!RtlReleaseResource` at `0x180029622`
- `ntdll!RtlReleaseResource` at `0x1800297b0`
- `ntdll!RtlReleaseResource` at `0x1800297bd`
- `ntdll!RtlReleaseResource` at `0x18002a31d`
- `ntdll!RtlReleaseResource` at `0x18002a32a`
- `ntdll!RtlReleaseResource` at `0x180029615`
- `ntdll!RtlReleaseResource` at `0x180029622`
- `ntdll!RtlReleaseResource` at `0x1800297b0`
- `ntdll!RtlReleaseResource` at `0x1800297bd`
- `ntdll!RtlReleaseResource` at `0x18002a31d`
- `ntdll!RtlReleaseResource` at `0x18002a32a`
- `KERNEL32!FreeLibrary` at `0x180029989`
- `KERNEL32!FreeLibrary` at `0x180029989`
- `KERNEL32!Sleep` at `0x18002967b`
- `KERNEL32!Sleep` at `0x18002997f`
- `KERNEL32!Sleep` at `0x18002967b`
- `KERNEL32!Sleep` at `0x18002997f`
- `KERNEL32!HeapFree` at `0x1800299bc`
- `KERNEL32!HeapFree` at `0x180029e03`
- `KERNEL32!HeapFree` at `0x1800299bc`
- `KERNEL32!HeapFree` at `0x180029e03`
- `KERNEL32!HeapAlloc` at `0x180029c6b`
- `KERNEL32!HeapAlloc` at `0x180029c6b`
- `KERNEL32!LeaveCriticalSection` at `0x1800293b6`
- `KERNEL32!LeaveCriticalSection` at `0x18002a396`
- `KERNEL32!LeaveCriticalSection` at `0x18002a45b`
- `KERNEL32!LeaveCriticalSection` at `0x18002a463`
- `KERNEL32!LeaveCriticalSection` at `0x1800293b6`
- `KERNEL32!LeaveCriticalSection` at `0x18002a396`
- `KERNEL32!LeaveCriticalSection` at `0x18002a45b`
- `KERNEL32!LeaveCriticalSection` at `0x18002a463`
- `KERNEL32!EnterCriticalSection` at `0x18002939a`
- `KERNEL32!EnterCriticalSection` at `0x18002a383`
- `KERNEL32!EnterCriticalSection` at `0x18002a448`
- `KERNEL32!EnterCriticalSection` at `0x18002939a`
- `KERNEL32!EnterCriticalSection` at `0x18002a383`
- `KERNEL32!EnterCriticalSection` at `0x18002a448`
- `rtutils!MprSetupProtocolFree` at `0x18002a310`
- `rtutils!MprSetupProtocolFree` at `0x18002a310`
- `rtutils!MprSetupProtocolEnum` at `0x18002972a`
- `rtutils!MprSetupProtocolEnum` at `0x18002972a`
- `iprtprio!SetPriorityInfo` at `0x18002959c`
- `iprtprio!SetPriorityInfo` at `0x18002959c`

## string_xrefs

- `0x180029663`: `SetGlobalInfo: Waiting for routing protocols to stop`
- `0x18002a3db`: `SetGlobalInfo: WAIT_TIMEOUT: Some routing protocols are in RTR_STATE_STOPPING state`
- `0x18002974c`: `SetGlobalInfo: Error %d loading protocol info from registry`
- `0x180029a65`: `SetGlobalInfo: SetRoutingDomainGlobalInfo for routing protocol %ws returned error %d`
- `0x180029abd`: `SetGlobalInfo: SetGlobalInfo for default compartment returned error %d`
- `0x18002a2e3`: `SetGlobalInfo: Couldnt find config information for %d`
- `0x180029ea9`: `SetGlobalInfo: %ws failed to set global config: %d\n`
- `0x18002a2b5`: `SetGlobalInfo: StartComplete for protocol %ws failed with error: %d`

## pseudocode

```c
__int64 __fastcall SetGlobalInfo(__int64 a1, unsigned int a2, unsigned int a3, struct _GUID *a4)
{
  __int64 v4; // r12
  __int64 v5; // rcx
  DWORD v7; // r13d
  unsigned __int64 v9; // rcx
  BOOL v10; // esi
  __int128 *v11; // r9
  unsigned int v13; // ebx
  char v14; // al
  __int128 *v15; // r9
  int v16; // ebx
  __int64 *v17; // rax
  __int64 *v18; // rcx
  __int128 *v19; // r9
  __int64 v20; // rcx
  __int64 PointerToTocEntry; // rax
  __int128 *v22; // r9
  unsigned int v23; // ecx
  __int64 v24; // rax
  DWORD v25; // eax
  __int128 *v26; // r9
  unsigned int v27; // eax
  __int64 v28; // rsi
  unsigned int v29; // r9d
  __int64 *v30; // rcx
  __int64 *v31; // rax
  __int64 *v32; // rbx
  int v33; // edx
  __int64 v34; // r8
  unsigned int v35; // r8d
  __int128 *v36; // r9
  unsigned int v37; // eax
  _QWORD *v38; // rcx
  LPVOID *v39; // rax
  __int64 (__fastcall *v40)(struct _GUID *, _QWORD, _QWORD, _QWORD, _DWORD); // rax
  unsigned int v41; // eax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 *v45; // rdx
  unsigned int v46; // ecx
  unsigned int v47; // eax
  __int64 (__fastcall *v48)(struct _GUID *, __int64, __int64, _QWORD, unsigned int); // r10
  __int64 v49; // r8
  DWORD i; // ecx
  __int64 v51; // r13
  __int64 v52; // rcx
  __int64 v53; // rax
  SIZE_T v54; // rbx
  unsigned int *v55; // r12
  __int128 *v56; // r9
  __int64 v57; // rax
  __int64 v58; // rbx
  unsigned int v59; // r14d
  int v60; // esi
  __int64 v61; // r8
  unsigned int v62; // r9d
  int v63; // edx
  int v64; // r10d
  unsigned int Protocol; // eax
  __int128 *v66; // r9
  __int64 InternalInterfaceForRoutingDomain; // r13
  int v68; // eax
  unsigned int v69; // r8d
  __int64 (__fastcall *v70)(struct _GUID *, __int64, __int64, _QWORD, int); // rax
  unsigned int v71; // eax
  __int128 *v72; // r9
  __int64 *v73; // rcx
  unsigned int **v74; // rax
  bool v75; // sf
  __int128 *v76; // r9
  unsigned int v77; // eax
  __int128 *v78; // r9
  __int64 *j; // rsi
  __int64 v80; // rbx
  int v81; // ecx
  __int64 v82; // rax
  unsigned __int8 *v83; // rcx
  void (__fastcall *v84)(_QWORD, __int64 *); // rax
  __int64 *v85; // rdx
  unsigned int v86; // eax
  __int128 *v87; // r9
  __int64 (*v88)(void); // rax
  unsigned int v89; // eax
  char v90; // al
  __int128 *v91; // r9
  BOOL v92; // [rsp+40h] [rbp-8E8h]
  int v94; // [rsp+48h] [rbp-8E0h]
  LPBYTE lpBuffer; // [rsp+50h] [rbp-8D8h] BYREF
  DWORD dwEntriesRead; // [rsp+58h] [rbp-8D0h] BYREF
  int v97; // [rsp+5Ch] [rbp-8CCh]
  unsigned int v98; // [rsp+60h] [rbp-8C8h]
  __int64 v99; // [rsp+68h] [rbp-8C0h] BYREF
  __int64 *v100; // [rsp+70h] [rbp-8B8h]
  __int64 v101; // [rsp+78h] [rbp-8B0h]
  __int64 v102; // [rsp+80h] [rbp-8A8h]
  __int128 v103; // [rsp+88h] [rbp-8A0h] BYREF
  __int128 v104; // [rsp+98h] [rbp-890h] BYREF
  int v105; // [rsp+A8h] [rbp-880h]
  int v106; // [rsp+B0h] [rbp-878h] BYREF
  __int128 v107; // [rsp+B4h] [rbp-874h]
  __int128 v108; // [rsp+C4h] [rbp-864h]
  int v109; // [rsp+D4h] [rbp-854h]
  int v110; // [rsp+E0h] [rbp-848h] BYREF
  char v111[2044]; // [rsp+E4h] [rbp-844h] BYREF

  v102 = a1;
  lpBuffer = 0;
  v4 = a1;
  dwEntriesRead = 0;
  v5 = *(_QWORD *)&a4->Data1;
  v97 = a3 == 33;
  v7 = a3;
  v9 = v5 - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v9 )
    v9 = *(_QWORD *)a4->Data4 - _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0];
  v110 = 0;
  v10 = v9 != 0;
  v92 = v10;
  memset_0(v111, 0, sizeof(v111));
  v106 = 0;
  v109 = 0;
  v107 = 0;
  v108 = 0;
  v103 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    v13 = 900;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v110) = 0;
      FormatRRASErrorString(&v110, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v110);
    }
    return v13;
  }
  ++HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v110) = 0;
    LOWORD(v106) = 0;
    FormatRRASErrorString(&v110, L"Entered: %ws", L"SetGlobalInfo");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v11 = &v103;
      if ( a4 )
        LODWORD(v11) = (_DWORD)a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v110,
        (_DWORD)v11,
        0,
        (__int64)&v106);
    }
  }
  if ( !(unsigned int)IsMultiTenancyEnabled() && v10 )
    return 87;
  if ( !v4 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v110) = 0;
      FormatRRASErrorString(&v110, L"Leaving: %ws", L"SetGlobalInfo");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v110);
    }
    v13 = 0;
LABEL_228:
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    return v13;
  }
  if ( !(unsigned int)ValidateRouterInfoBlock(v4, a2) )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v110) = 0;
      LOWORD(v106) = 0;
      FormatRRASErrorString(
        &v110,
        L"SetGlobalInfo: Validation Failed for Global Info for transport %d. Info size %d",
        v7,
        a2);
      v14 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v15 = &v103;
        if ( a4 )
          LODWORD(v15) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v110,
          (_DWORD)v15,
          0,
          (__int64)&v106);
        v14 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v14 < 0 )
    {
      LOWORD(v110) = 0;
      FormatRRASErrorString(&v110, L"Leaving: %ws", L"SetGlobalInfo");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v110);
    }
    v13 = 87;
    goto LABEL_228;
  }
  v16 = 300000;
  if ( !v10 )
  {
    SetPriorityInfo(v4);
    SetScopeInfo(v4);
  }
LABEL_29:
  if ( !v16 )
  {
    v90 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v106) = 0;
      v91 = &v103;
      if ( a4 )
        LODWORD(v91) = (_DWORD)a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"SetGlobalInfo: WAIT_TIMEOUT: Some routing protocols are in RTR_STATE_STOPPING state",
        (_DWORD)v91,
        0,
        (__int64)&v106);
      v90 = Microsoft_Windows_RRASEnableBits;
    }
    if ( v90 < 0 )
    {
      LOWORD(v110) = 0;
      FormatRRASErrorString(&v110, L"Leaving: %ws", L"SetGlobalInfo");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v110);
    }
    v13 = 258;
    goto LABEL_228;
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
  v17 = (__int64 *)g_leProtoCbListV6;
  v18 = (__int64 *)&g_leProtoCbListV4;
  if ( v7 == 33 )
    v17 = (__int64 *)g_leProtoCbListV4;
  else
    v18 = &g_leProtoCbListV6;
  while ( v17 != v18 )
  {
    if ( *((_DWORD *)v17 + 4) == 1 )
    {
      RtlReleaseResource(&stru_18008C4A0);
      RtlReleaseResource(&Resource);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v106) = 0;
        v19 = &v103;
        if ( a4 )
          LODWORD(v19) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)L"SetGlobalInfo: Waiting for routing protocols to stop",
          (_DWORD)v19,
          0,
          (__int64)&v106);
      }
      Sleep(0x64u);
      v16 -= 100;
      goto LABEL_29;
    }
    v17 = (__int64 *)*v17;
  }
  v20 = 4294901763LL;
  if ( v7 != 33 )
    v20 = 4294901775LL;
  PointerToTocEntry = GetPointerToTocEntry(v20, v4);
  if ( PointerToTocEntry )
  {
    if ( *(_DWORD *)(PointerToTocEntry + 4)
      && (v23 = *(_DWORD *)(PointerToTocEntry + 12), v23 < *(_DWORD *)(v4 + 4))
      && (v24 = v4 + v23) != 0 )
    {
      g_dwLoggingLevel = *(_DWORD *)(v24 + 4);
    }
    else
    {
      g_dwLoggingLevel = 0;
    }
  }
  else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v106) = 0;
    v22 = &v103;
    if ( a4 )
      LODWORD(v22) = (_DWORD)a4;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"SetGlobalInfo: No TOC found for Global Info",
      (_DWORD)v22,
      0,
      (__int64)&v106);
  }
  v25 = MprSetupProtocolEnum(v7, &lpBuffer, &dwEntriesRead);
  if ( v25 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v110) = 0;
      LOWORD(v106) = 0;
      FormatRRASErrorString(&v110, L"SetGlobalInfo: Error %d loading protocol info from registry", v25);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v26 = &v103;
        if ( a4 )
          LODWORD(v26) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v110,
          (_DWORD)v26,
          0,
          (__int64)&v106);
      }
    }
    RtlReleaseResource(&stru_18008C4A0);
    RtlReleaseResource(&Resource);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v110) = 0;
      FormatRRASErrorString(&v110, L"Leaving: %ws", L"SetGlobalInfo");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v110);
    }
    v13 = 1015;
    goto LABEL_228;
  }
  v27 = 0;
  while ( 1 )
  {
    v98 = v27;
    if ( v27 >= *(_DWORD *)(v4 + 8) )
      break;
    v28 = 2LL * v27;
    v29 = *(_DWORD *)(v4 + 16LL * v27 + 12);
    if ( (v29 & 0xC0000000) == 0xC0000000 )
      goto LABEL_88;
    v30 = (__int64 *)g_leProtoCbListV6;
    v31 = (__int64 *)&g_leProtoCbListV4;
    v32 = 0;
    v33 = 0;
    if ( v7 == 33 )
      v30 = (__int64 *)g_leProtoCbListV4;
    else
      v31 = &g_leProtoCbListV6;
    v100 = v31;
    while ( v30 != v31 )
    {
      v32 = v30;
      if ( *((_DWORD *)v30 + 15) == v29 )
      {
        v33 = 1;
        break;
      }
      v30 = (__int64 *)*v30;
      v31 = v100;
    }
    v34 = *(unsigned int *)(v4 + 8 * v28 + 16);
    if ( v33 )
    {
      if ( !(_DWORD)v34 )
      {
        if ( *((_DWORD *)v32 + 4) || !(unsigned int)IsProtocolEnabledForRoutingDomain(a4, v7, *((_DWORD *)v32 + 15)) )
          goto LABEL_88;
        v35 = *((_DWORD *)v32 + 15);
        --*((_DWORD *)v32 + 12);
        EnableOrDisableProtocolForRoutingDomain(a4, v7, v35, 0);
        if ( *((_DWORD *)v32 + 12) )
        {
          if ( v92 )
          {
            v40 = (__int64 (__fastcall *)(struct _GUID *, _QWORD, _QWORD, _QWORD, _DWORD))v32[38];
            if ( !v40 )
              goto LABEL_88;
            v41 = v40(a4, 0, 0, 0, 0);
            if ( !v41 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
              goto LABEL_88;
            v42 = L"SetGlobalInfo: SetRoutingDomainGlobalInfo for routing protocol %ws returned error %d";
          }
          else
          {
            v41 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v32[13])(0, 0, 0, 0);
            if ( !v41 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
              goto LABEL_88;
            v42 = L"SetGlobalInfo: SetGlobalInfo for default compartment returned error %d";
          }
          LOWORD(v110) = 0;
          LOWORD(v106) = 0;
          FormatRRASErrorString(&v110, v42, v32[4], v41);
          goto LABEL_133;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v110) = 0;
          LOWORD(v106) = 0;
          FormatRRASErrorString(
            &v110,
            L"SetGlobalInfo: Removing %ws since the TOC size was 0 and it is serving no routing domain now",
            v32[4]);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v36 = &v103;
            if ( a4 )
              LODWORD(v36) = (_DWORD)a4;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v110,
              (_DWORD)v36,
              0,
              (__int64)&v106);
          }
        }
        v37 = StopRoutingProtocol(v32);
        if ( v37 )
        {
          if ( v37 != 907 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v110) = 0;
            LOWORD(v106) = 0;
            FormatRRASErrorString(&v110, L"SetGlobalInfo: Error %d stopping %ws. Not removing from list", v37, v32[4]);
            goto LABEL_133;
          }
          goto LABEL_88;
        }
        Sleep(0);
        FreeLibrary((HMODULE)v32[5]);
        v38 = (_QWORD *)*v32;
        if ( *(__int64 **)(*v32 + 8) == v32 )
        {
          v39 = (LPVOID *)v32[1];
          if ( *v39 == v32 )
          {
            *v39 = v38;
            v38[1] = v39;
            HeapFree(IPRouterHeap, 0, v32);
            --TotalRoutingProtocols;
            goto LABEL_88;
          }
        }
LABEL_215:
        __fastfail(3u);
      }
      if ( !v92 )
      {
        if ( v32[13] )
          goto LABEL_103;
LABEL_106:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_88;
        LOWORD(v110) = 0;
        LOWORD(v106) = 0;
        FormatRRASErrorString(&v110, L"SetGlobalInfo: Invalid function pointers. %d setting info for %ws", 87, v32[4]);
LABEL_108:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_88;
        v45 = RasRtrmgrParamTraceInfo;
        goto LABEL_135;
      }
      if ( !v32[38] )
        goto LABEL_106;
LABEL_103:
      v43 = *(unsigned int *)(v4 + 8 * v28 + 24);
      if ( (unsigned int)v43 >= *(_DWORD *)(v4 + 4) )
        v44 = 0;
      else
        v44 = v4 + v43;
      v46 = *(_DWORD *)(v4 + 8 * v28 + 20);
      if ( v92 )
      {
        v48 = (__int64 (__fastcall *)(struct _GUID *, __int64, __int64, _QWORD, unsigned int))v32[38];
        if ( v48 )
        {
          v47 = v48(a4, v44, 1280, (unsigned int)v34, v46);
          goto LABEL_115;
        }
        v49 = 50;
      }
      else
      {
        v47 = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))v32[13])(v44, 1280, v34, v46);
LABEL_115:
        v49 = v47;
        if ( !v47 )
        {
          if ( !(unsigned int)IsProtocolEnabledForRoutingDomain(a4, v7, *((_DWORD *)v32 + 15)) )
          {
            ++*((_DWORD *)v32 + 12);
            EnableOrDisableProtocolForRoutingDomain(a4, v7, *((_DWORD *)v32 + 15), 1);
          }
          goto LABEL_88;
        }
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v110) = 0;
        LOWORD(v106) = 0;
        FormatRRASErrorString(&v110, L"SetGlobalInfo: Error %d setting info for %ws", v49, v32[4]);
        goto LABEL_133;
      }
      goto LABEL_88;
    }
    if ( !(_DWORD)v34 )
      goto LABEL_88;
    for ( i = 0; ; ++i )
    {
      if ( i >= dwEntriesRead )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_88;
        LOWORD(v110) = 0;
        LOWORD(v106) = 0;
        FormatRRASErrorString(&v110, L"SetGlobalInfo: Couldnt find config information for %d", v29);
        goto LABEL_108;
      }
      v51 = 184LL * i;
      v101 = v51;
      if ( *(_DWORD *)&lpBuffer[v51] == v29 )
        break;
    }
    v52 = -1;
    do
      ++v52;
    while ( *(_WORD *)&lpBuffer[2 * v52 + 4 + v51] );
    v53 = -1;
    do
      ++v53;
    while ( *(_WORD *)&lpBuffer[2 * v53 + 86 + v51] );
    v54 = (unsigned int)(2 * (v52 + v53) + 324);
    v55 = (unsigned int *)HeapAlloc(IPRouterHeap, 8u, v54);
    if ( !v55 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v110) = 0;
        LOWORD(v106) = 0;
        FormatRRASErrorString(
          &v110,
          L"SetGlobalInfo: Error allocating %d bytes for %ws",
          (unsigned int)v54,
          &lpBuffer[v51 + 4]);
        goto LABEL_133;
      }
      goto LABEL_88;
    }
    v57 = *(unsigned int *)(v102 + 8 * v28 + 24);
    if ( (unsigned int)v57 >= *(_DWORD *)(v102 + 4) )
      v58 = 0;
    else
      v58 = v102 + v57;
    v59 = *(_DWORD *)(v102 + 8 * v28 + 16);
    v60 = *(_DWORD *)(v102 + 8 * v28 + 20);
    if ( v92 )
    {
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
    }
    else
    {
      v61 = v58;
      v62 = 1280;
      v63 = v59;
      v64 = v60;
    }
    Protocol = LoadProtocol((int *)&lpBuffer[v51], (__int64)v55, v61, v62, v63, v64, v97);
    if ( Protocol )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v110) = 0;
        LOWORD(v106) = 0;
        FormatRRASErrorString(&v110, L"SetGlobalInfo: %ws failed to load: %d", &lpBuffer[v51 + 4], Protocol);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v66 = &v103;
          if ( a4 )
            LODWORD(v66) = (_DWORD)a4;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v110,
            (_DWORD)v66,
            0,
            (__int64)&v106);
        }
      }
      HeapFree(IPRouterHeap, 0, v55);
      goto LABEL_88;
    }
    InternalInterfaceForRoutingDomain = GetInternalInterfaceForRoutingDomain(a4, a3);
    v68 = g_bRouterBootCompleteV6;
    if ( a3 == 33 )
      v68 = g_bRouterBootCompleteV4;
    v69 = v55[15];
    v94 = v68;
    v55[4] = 0;
    v55[12] = 1;
    EnableOrDisableProtocolForRoutingDomain(a4, a3, v69, 1);
    if ( v92 )
    {
      v70 = (__int64 (__fastcall *)(struct _GUID *, __int64, __int64, _QWORD, int))*((_QWORD *)v55 + 38);
      if ( v70 )
      {
        v71 = v70(a4, v58, 1280, v59, v60);
        if ( v71 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v110) = 0;
            LOWORD(v106) = 0;
            FormatRRASErrorString(&v110, L"SetGlobalInfo: %ws failed to set global config: %d\n", lpBuffer + 4, v71);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v72 = &v103;
              if ( a4 )
                LODWORD(v72) = (_DWORD)a4;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v110,
                (_DWORD)v72,
                0,
                (__int64)&v106);
            }
          }
        }
      }
    }
    v73 = v100;
    v74 = (unsigned int **)v100[1];
    if ( *v74 != (unsigned int *)v100 )
      goto LABEL_215;
    *(_QWORD *)v55 = v100;
    *((_QWORD *)v55 + 1) = v74;
    *v74 = v55;
    v75 = (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL;
    v73[1] = (__int64)v55;
    if ( v75 )
    {
      LOWORD(v110) = 0;
      LOWORD(v106) = 0;
      FormatRRASErrorString(&v110, L"SetGlobalInfo: %ws successfully initialized", &lpBuffer[v101 + 4]);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v76 = &v103;
        if ( a4 )
          LODWORD(v76) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v110,
          (_DWORD)v76,
          0,
          (__int64)&v106);
      }
    }
    ++TotalRoutingProtocols;
    if ( (v55[16] & 0x10) != 0 )
    {
      if ( InternalInterfaceForRoutingDomain )
      {
        v77 = AddInterfaceToProtocol(InternalInterfaceForRoutingDomain, (_DWORD)v55, 0, 0, 0, 0);
        if ( v77 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v110) = 0;
            LOWORD(v106) = 0;
            FormatRRASErrorString(
              &v110,
              L"SetGlobalInfo: Error %d adding %ws to %ws promously",
              v77,
              *(_QWORD *)(InternalInterfaceForRoutingDomain + 72),
              *((_QWORD *)v55 + 4));
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v78 = &v103;
              if ( a4 )
                LODWORD(v78) = (_DWORD)a4;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v110,
                (_DWORD)v78,
                0,
                (__int64)&v106);
            }
          }
        }
        if ( *(_DWORD *)(InternalInterfaceForRoutingDomain + 172) == 1 )
          EnableInterfaceWithAllProtocols(InternalInterfaceForRoutingDomain);
        if ( *(_DWORD *)(InternalInterfaceForRoutingDomain + 512) )
          BindInterfaceInAllProtocols(InternalInterfaceForRoutingDomain);
      }
      for ( j = &ICBList; ; j = (__int64 *)*j )
      {
        v80 = *j;
        if ( (__int64 *)*j == &ICBList )
          break;
        if ( v80 != InternalInterfaceForRoutingDomain )
        {
          v81 = *(_DWORD *)(v80 + 144);
          if ( v81 != 7 && *(_DWORD *)(v80 + 516) == v97 )
          {
            if ( !v92 )
              goto LABEL_189;
            v82 = *(_QWORD *)(v80 + 688) - *(_QWORD *)&a4->Data1;
            if ( !v82 )
              v82 = *(_QWORD *)(v80 + 696) - *(_QWORD *)a4->Data4;
            if ( !v82 )
            {
LABEL_189:
              if ( v81 )
              {
                v86 = AddInterfaceToProtocol(v80, (_DWORD)v55, 0, 0, 0, 0);
                if ( v86 )
                {
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    LOWORD(v110) = 0;
                    LOWORD(v106) = 0;
                    FormatRRASErrorString(
                      &v110,
                      L"SetGlobalInfo: Error %d adding %ws to %ws promiscuously",
                      v86,
                      *(_QWORD *)(v80 + 72),
                      *((_QWORD *)v55 + 4));
                    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                    {
                      v87 = &v103;
                      if ( a4 )
                        LODWORD(v87) = (_DWORD)a4;
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasRtrMgrParamTraceError,
                        (unsigned int)&v110,
                        (_DWORD)v87,
                        0,
                        (__int64)&v106);
                    }
                  }
                }
                else
                {
                  if ( *(_DWORD *)(v80 + 172) == 1 )
                    EnableInterfaceWithAllProtocols(v80);
                  if ( *(_DWORD *)(v80 + 512) )
                    BindInterfaceInAllProtocols(v80);
                }
              }
              else
              {
                v83 = *(unsigned __int8 **)(v80 + 712);
                v99 = 0;
                v105 = 0;
                v104 = 0;
                if ( a3 == 33 )
                {
                  v99 = *(_QWORD *)v83;
                }
                else
                {
                  v104 = *(_OWORD *)(v83 + 4);
                  v105 = *v83;
                }
                v84 = (void (__fastcall *)(_QWORD, __int64 *))*((_QWORD *)v55 + 23);
                if ( v84 )
                {
                  v85 = (__int64 *)&v104;
                  if ( a3 == 33 )
                    v85 = &v99;
                  v84(*(unsigned int *)(InternalInterfaceForRoutingDomain + 16), v85);
                }
              }
            }
          }
        }
      }
    }
    if ( v94 )
    {
      v88 = (__int64 (*)(void))*((_QWORD *)v55 + 10);
      if ( v88 )
      {
        v89 = v88();
        if ( v89 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v110) = 0;
            LOWORD(v106) = 0;
            FormatRRASErrorString(
              &v110,
              L"SetGlobalInfo: StartComplete for protocol %ws failed with error: %d",
              &lpBuffer[v101 + 4],
              v89);
LABEL_133:
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v45 = RasRtrMgrParamTraceError;
LABEL_135:
              v56 = &v103;
              if ( a4 )
                LODWORD(v56) = (_DWORD)a4;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (_DWORD)v45,
                (unsigned int)&v110,
                (_DWORD)v56,
                0,
                (__int64)&v106);
            }
          }
        }
      }
    }
LABEL_88:
    v4 = v102;
    v27 = v98 + 1;
    v7 = a3;
  }
  MprSetupProtocolFree(lpBuffer);
  RtlReleaseResource(&stru_18008C4A0);
  RtlReleaseResource(&Resource);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v110) = 0;
    FormatRRASErrorString(&v110, L"Leaving: %ws", L"SetGlobalInfo");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v110);
  }
  EnterCriticalSection(&RouterStateLock);
  --HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  return 0;
}

```

## disassembly

```asm
0x1800292bc  push    rbx
0x1800292be  push    rsi
0x1800292bf  push    rdi
0x1800292c0  push    r12
0x1800292c2  push    r13
0x1800292c4  push    r14
0x1800292c6  push    r15
0x1800292c8  sub     rsp, 8F0h
0x1800292cf  mov     rax, cs:__security_cookie
0x1800292d6  xor     rax, rsp
0x1800292d9  mov     [rsp+928h+var_48], rax
0x1800292e1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800292e8  xor     r14d, r14d
0x1800292eb  mov     [rsp+928h+var_8A8], rcx
0x1800292f3  mov     eax, r14d
0x1800292f6  mov     [rsp+928h+var_8E4], r8d
0x1800292fb  cmp     r8d, 21h ; '!'
0x1800292ff  mov     [rsp+928h+lpBuffer], r14
0x180029304  mov     r12, rcx
0x180029307  mov     [rsp+928h+dwEntriesRead], r14d
0x18002930c  mov     rcx, [r9]
0x18002930f  setz    al
0x180029312  mov     [rsp+928h+var_8CC], eax
0x180029316  mov     rdi, r9
0x180029319  movq    rax, xmm0
0x18002931e  mov     r13d, r8d
0x180029321  mov     ebx, edx
0x180029323  sub     rcx, rax
0x180029326  jnz     short loc_180029339
0x180029328  mov     rcx, [r9+8]
0x18002932c  psrldq  xmm0, 8
0x180029331  movq    rax, xmm0
0x180029336  sub     rcx, rax
0x180029339  test    rcx, rcx
0x18002933c  mov     [rsp+928h+var_848], r14d
0x180029344  mov     esi, r14d
0x180029347  lea     rcx, [rsp+928h+var_844]; void *
0x18002934f  setnz   sil
0x180029353  mov     r8d, 7FCh; Size
0x180029359  xor     edx, edx; Val
0x18002935b  mov     [rsp+928h+var_8E8], esi
0x18002935f  call    memset_0
0x180029364  xorps   xmm0, xmm0
0x180029367  mov     [rsp+928h+var_878], r14d
0x18002936f  xor     eax, eax
0x180029371  lea     r15, RouterStateLock
0x180029378  mov     rcx, r15; lpCriticalSection
0x18002937b  mov     [rsp+928h+var_854], eax
0x180029382  movups  [rsp+928h+var_874], xmm0
0x18002938a  movups  [rsp+928h+var_864], xmm0
0x180029392  movups  [rsp+928h+var_8A0], xmm0
0x18002939a  call    cs:__imp_EnterCriticalSection
0x1800293a0  cmp     dword ptr cs:RouterState, r14d
0x1800293a7  mov     rcx, r15; lpCriticalSection
0x1800293aa  jnz     loc_18002A463
0x1800293b0  inc     dword ptr cs:RouterState+4
0x1800293b6  call    cs:__imp_LeaveCriticalSection
0x1800293bc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800293c3  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800293ca  jge     short loc_18002943A
0x1800293cc  lea     r8, aSetglobalinfo; "SetGlobalInfo"
0x1800293d3  mov     word ptr [rsp+928h+var_848], r14w
0x1800293dc  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800293e3  mov     word ptr [rsp+928h+var_878], r14w
0x1800293ec  lea     rcx, [rsp+928h+var_848]
0x1800293f4  call    FormatRRASErrorString
0x1800293f9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180029400  jge     short loc_18002943A
0x180029402  test    rdi, rdi
0x180029405  lea     rax, [rsp+928h+var_878]
0x18002940d  mov     [rsp+928h+var_900], rax
0x180029412  lea     r9, [rsp+928h+var_8A0]
0x18002941a  cmovnz  r9, rdi
0x18002941e  mov     [rsp+928h+var_908], r14
0x180029423  lea     r8, [rsp+928h+var_848]
0x18002942b  mov     rcx, r15
0x18002942e  lea     rdx, RasRtrmgrParamTraceInfo
0x180029435  call    McTemplateU0zjzz_EventWriteTransfer
0x18002943a  call    IsMultiTenancyEnabled
0x18002943f  test    eax, eax
0x180029441  jnz     short loc_180029451
0x180029443  test    esi, esi
0x180029445  jz      short loc_180029451
0x180029447  mov     eax, 57h ; 'W'
0x18002944c  jmp     loc_18002A4BD
0x180029451  test    r12, r12
0x180029454  jnz     short loc_1800294AB
0x180029456  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002945d  jge     short loc_1800294A3
0x18002945f  lea     r8, aSetglobalinfo; "SetGlobalInfo"
0x180029466  mov     word ptr [rsp+928h+var_848], r14w
0x18002946f  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180029476  lea     rcx, [rsp+928h+var_848]
0x18002947e  call    FormatRRASErrorString
0x180029483  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002948a  jge     short loc_1800294A3
0x18002948c  lea     r8, [rsp+928h+var_848]
0x180029494  mov     rcx, r15
0x180029497  lea     rdx, RasRtrmgrTraceInfo
0x18002949e  call    McTemplateU0z_EventWriteTransfer
0x1800294a3  mov     ebx, r14d
0x1800294a6  jmp     loc_18002A441
0x1800294ab  mov     edx, ebx
0x1800294ad  mov     rcx, r12
0x1800294b0  call    ValidateRouterInfoBlock
0x1800294b5  test    eax, eax
0x1800294b7  jnz     loc_180029590
0x1800294bd  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800294c4  test    al, 40h
0x1800294c6  jz      short loc_18002953E
0x1800294c8  mov     r9d, ebx
0x1800294cb  mov     word ptr [rsp+928h+var_848], r14w
0x1800294d4  mov     r8d, r13d
0x1800294d7  mov     word ptr [rsp+928h+var_878], r14w
0x1800294e0  lea     rdx, aSetglobalinfoV; "SetGlobalInfo: Validation Failed for Gl"...
0x1800294e7  lea     rcx, [rsp+928h+var_848]
0x1800294ef  call    FormatRRASErrorString
0x1800294f4  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800294fb  test    al, 40h
0x1800294fd  jz      short loc_18002953E
0x1800294ff  test    rdi, rdi
0x180029502  lea     rax, [rsp+928h+var_878]
0x18002950a  mov     [rsp+928h+var_900], rax
0x18002950f  lea     r9, [rsp+928h+var_8A0]
0x180029517  cmovnz  r9, rdi
0x18002951b  mov     [rsp+928h+var_908], r14
0x180029520  lea     r8, [rsp+928h+var_848]
0x180029528  mov     rcx, r15
0x18002952b  lea     rdx, RasRtrMgrParamTraceError
0x180029532  call    McTemplateU0zjzz_EventWriteTransfer
0x180029537  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002953e  test    al, al
0x180029540  jns     short loc_180029586
0x180029542  lea     r8, aSetglobalinfo; "SetGlobalInfo"
0x180029549  mov     word ptr [rsp+928h+var_848], r14w
0x180029552  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180029559  lea     rcx, [rsp+928h+var_848]
0x180029561  call    FormatRRASErrorString
0x180029566  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002956d  jge     short loc_180029586
0x18002956f  lea     r8, [rsp+928h+var_848]
0x180029577  mov     rcx, r15
0x18002957a  lea     rdx, RasRtrmgrTraceInfo
0x180029581  call    McTemplateU0z_EventWriteTransfer
0x180029586  mov     ebx, 57h ; 'W'
0x18002958b  jmp     loc_18002A441
0x180029590  mov     ebx, 493E0h
0x180029595  test    esi, esi
0x180029597  jnz     short loc_1800295AA
0x180029599  mov     rcx, r12
0x18002959c  call    cs:__imp_SetPriorityInfo
0x1800295a2  mov     rcx, r12
0x1800295a5  call    SetScopeInfo
0x1800295aa  mov     r14b, 40h ; '@'
0x1800295ad  xor     esi, esi
0x1800295af  test    ebx, ebx
0x1800295b1  jz      loc_18002A3A3
0x1800295b7  mov     dl, 1; Wait
0x1800295b9  lea     rcx, Resource; Resource
0x1800295c0  call    cs:__imp_RtlAcquireResourceExclusive
0x1800295c6  mov     dl, 1; Wait
0x1800295c8  lea     rcx, stru_18008C4A0; Resource
0x1800295cf  call    cs:__imp_RtlAcquireResourceExclusive
0x1800295d5  mov     rax, cs:g_leProtoCbListV6
0x1800295dc  lea     rcx, g_leProtoCbListV4
0x1800295e3  cmp     r13d, 21h ; '!'
0x1800295e7  lea     rdx, g_leProtoCbListV6
0x1800295ee  cmovz   rax, cs:g_leProtoCbListV4
0x1800295f6  cmovnz  rcx, rdx
0x1800295fa  cmp     rax, rcx
0x1800295fd  jz      loc_180029689
0x180029603  cmp     dword ptr [rax+10h], 1
0x180029607  jz      short loc_18002960E
0x180029609  mov     rax, [rax]
0x18002960c  jmp     short loc_1800295FA
0x18002960e  lea     rcx, stru_18008C4A0; Resource
0x180029615  call    cs:__imp_RtlReleaseResource
0x18002961b  lea     rcx, Resource; Resource
0x180029622  call    cs:__imp_RtlReleaseResource
0x180029628  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18002962e  and     al, r14b
0x180029631  mov     byte ptr [rsp+928h+var_8E0], al
0x180029635  jz      short loc_180029676
0x180029637  test    rdi, rdi
0x18002963a  mov     word ptr [rsp+928h+var_878], si
0x180029642  lea     rax, [rsp+928h+var_878]
0x18002964a  mov     rcx, r15
0x18002964d  mov     [rsp+928h+var_900], rax
0x180029652  lea     r9, [rsp+928h+var_8A0]
0x18002965a  cmovnz  r9, rdi
0x18002965e  mov     [rsp+928h+var_908], rsi
0x180029663  lea     r8, aSetglobalinfoW; "SetGlobalInfo: Waiting for routing prot"...
0x18002966a  lea     rdx, RasRtrMgrParamTraceError
0x180029671  call    McTemplateU0zjzz_EventWriteTransfer
0x180029676  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002967b  call    cs:__imp_Sleep
0x180029681  add     ebx, 0FFFFFF9Ch
0x180029684  jmp     loc_1800295AF
0x180029689  mov     eax, 0FFFF000Fh
0x18002968e  cmp     r13d, 21h ; '!'
0x180029692  mov     ecx, 0FFFF0003h
0x180029697  mov     rdx, r12
0x18002969a  cmovnz  ecx, eax
0x18002969d  call    GetPointerToTocEntry
0x1800296a2  test    rax, rax
0x1800296a5  jnz     short loc_1800296F6
0x1800296a7  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x1800296ad  and     al, 80h
0x1800296af  mov     byte ptr [rsp+928h+var_8E0], al
0x1800296b3  jz      short loc_18002971D
0x1800296b5  test    rdi, rdi
0x1800296b8  mov     word ptr [rsp+928h+var_878], si
0x1800296c0  lea     rax, [rsp+928h+var_878]
0x1800296c8  mov     rcx, r15
0x1800296cb  mov     [rsp+928h+var_900], rax
0x1800296d0  lea     r9, [rsp+928h+var_8A0]
0x1800296d8  cmovnz  r9, rdi
0x1800296dc  mov     [rsp+928h+var_908], rsi
0x1800296e1  lea     r8, aSetglobalinfoN; "SetGlobalInfo: No TOC found for Global "...
0x1800296e8  lea     rdx, RasRtrmgrParamTraceInfo
0x1800296ef  call    McTemplateU0zjzz_EventWriteTransfer
0x1800296f4  jmp     short loc_18002971D
0x1800296f6  cmp     [rax+4], esi
0x1800296f9  jz      short loc_180029717
0x1800296fb  mov     ecx, [rax+0Ch]
0x1800296fe  cmp     ecx, [r12+4]
0x180029703  jnb     short loc_180029717
0x180029705  mov     eax, ecx
0x180029707  add     rax, r12
0x18002970a  jz      short loc_180029717
0x18002970c  mov     eax, [rax+4]
0x18002970f  mov     cs:g_dwLoggingLevel, eax
0x180029715  jmp     short loc_18002971D
0x180029717  mov     cs:g_dwLoggingLevel, esi
0x18002971d  lea     r8, [rsp+928h+dwEntriesRead]; lpdwEntriesRead
0x180029722  mov     ecx, r13d; dwTransportId
0x180029725  lea     rdx, [rsp+928h+lpBuffer]; lplpBuffer
0x18002972a  call    cs:__imp_MprSetupProtocolEnum
0x180029730  test    eax, eax
0x180029732  jz      loc_180029819
0x180029738  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002973f  jz      short loc_1800297A9
0x180029741  mov     r8d, eax
0x180029744  mov     word ptr [rsp+928h+var_848], si
0x18002974c  lea     rdx, aSetglobalinfoE_3; "SetGlobalInfo: Error %d loading protoco"...
0x180029753  mov     word ptr [rsp+928h+var_878], si
0x18002975b  lea     rcx, [rsp+928h+var_848]
0x180029763  call    FormatRRASErrorString
0x180029768  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002976f  jz      short loc_1800297A9
0x180029771  test    rdi, rdi
0x180029774  lea     rax, [rsp+928h+var_878]
0x18002977c  mov     [rsp+928h+var_900], rax
0x180029781  lea     r9, [rsp+928h+var_8A0]
0x180029789  cmovnz  r9, rdi
0x18002978d  mov     [rsp+928h+var_908], rsi
0x180029792  lea     r8, [rsp+928h+var_848]
0x18002979a  mov     rcx, r15
0x18002979d  lea     rdx, RasRtrMgrParamTraceError
0x1800297a4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800297a9  lea     rcx, stru_18008C4A0; Resource
0x1800297b0  call    cs:__imp_RtlReleaseResource
0x1800297b6  lea     rcx, Resource; Resource
0x1800297bd  call    cs:__imp_RtlReleaseResource
0x1800297c3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800297ca  jge     short loc_18002980F
0x1800297cc  lea     r8, aSetglobalinfo; "SetGlobalInfo"
0x1800297d3  mov     word ptr [rsp+928h+var_848], si
0x1800297db  lea     rdx, aLeavingWs; "Leaving: %ws"
0x1800297e2  lea     rcx, [rsp+928h+var_848]
0x1800297ea  call    FormatRRASErrorString
0x1800297ef  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800297f6  jge     short loc_18002980F
0x1800297f8  lea     r8, [rsp+928h+var_848]
0x180029800  mov     rcx, r15
0x180029803  lea     rdx, RasRtrmgrTraceInfo
0x18002980a  call    McTemplateU0z_EventWriteTransfer
0x18002980f  mov     ebx, 3F7h
0x180029814  jmp     loc_18002A441
0x180029819  mov     eax, esi
0x18002981b  mov     r10d, 57h ; 'W'
0x180029821  mov     [rsp+928h+var_8C8], eax
0x180029825  cmp     eax, [r12+8]
0x18002982a  jnb     loc_18002A30B
0x180029830  mov     esi, eax
0x180029832  add     rsi, rsi
0x180029835  mov     r9d, [r12+rsi*8+0Ch]
0x18002983a  mov     eax, r9d
0x18002983d  and     eax, 0C0000000h
0x180029842  cmp     eax, 0C0000000h
0x180029847  jz      loc_1800299CE
0x18002984d  mov     rcx, cs:g_leProtoCbListV6
0x180029854  lea     rax, g_leProtoCbListV4
0x18002985b  xor     r11d, r11d
0x18002985e  lea     r8, g_leProtoCbListV6
0x180029865  cmp     r13d, 21h ; '!'
0x180029869  mov     ebx, r11d
0x18002986c  mov     edx, r11d
0x18002986f  cmovz   rcx, cs:g_leProtoCbListV4
0x180029877  cmovnz  rax, r8
  ... truncated ...
```
