# RtrMgrSetInterfaceInfo

- ea: `0x180027dc0`
- end: `0x1800292b6`
- name: `RtrMgrSetInterfaceInfo`
- size: `5366`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dce0`
- `0x18003dd00`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x180011790`
- `0x1800150c8`
- `0x18001597c`
- `0x18001b6a0`
- `0x18001ba54`
- `0x18001bbf4`
- `0x18001e490`
- `0x18001f194`
- `0x180027dc0`
- `0x18004fd14`
- `0x180057bac`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180027f9e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180027f9e`
- `ntdll!RtlReleaseResource` at `0x18002813a`
- `ntdll!RtlReleaseResource` at `0x180028235`
- `ntdll!RtlReleaseResource` at `0x180028667`
- `ntdll!RtlReleaseResource` at `0x180028fd6`
- `ntdll!RtlReleaseResource` at `0x1800291d7`
- `ntdll!RtlReleaseResource` at `0x18002813a`
- `ntdll!RtlReleaseResource` at `0x180028235`
- `ntdll!RtlReleaseResource` at `0x180028667`
- `ntdll!RtlReleaseResource` at `0x180028fd6`
- `ntdll!RtlReleaseResource` at `0x1800291d7`
- `ntdll!RtlAcquireResourceShared` at `0x180028385`
- `ntdll!RtlAcquireResourceShared` at `0x180028385`
- `KERNEL32!HeapFree` at `0x180028db1`
- `KERNEL32!HeapFree` at `0x180028fba`
- `KERNEL32!HeapFree` at `0x1800290c2`
- `KERNEL32!HeapFree` at `0x180028db1`
- `KERNEL32!HeapFree` at `0x180028fba`
- `KERNEL32!HeapFree` at `0x1800290c2`
- `KERNEL32!HeapAlloc` at `0x1800282e8`
- `KERNEL32!HeapAlloc` at `0x18002874c`
- `KERNEL32!HeapAlloc` at `0x1800282e8`
- `KERNEL32!HeapAlloc` at `0x18002874c`
- `KERNEL32!LeaveCriticalSection` at `0x180027ea0`
- `KERNEL32!LeaveCriticalSection` at `0x180028702`
- `KERNEL32!LeaveCriticalSection` at `0x180029232`
- `KERNEL32!LeaveCriticalSection` at `0x18002923c`
- `KERNEL32!LeaveCriticalSection` at `0x180027ea0`
- `KERNEL32!LeaveCriticalSection` at `0x180028702`
- `KERNEL32!LeaveCriticalSection` at `0x180029232`
- `KERNEL32!LeaveCriticalSection` at `0x18002923c`
- `KERNEL32!EnterCriticalSection` at `0x180027e85`
- `KERNEL32!EnterCriticalSection` at `0x1800286ef`
- `KERNEL32!EnterCriticalSection` at `0x18002921f`
- `KERNEL32!EnterCriticalSection` at `0x180027e85`
- `KERNEL32!EnterCriticalSection` at `0x1800286ef`
- `KERNEL32!EnterCriticalSection` at `0x18002921f`

## string_xrefs

- `0x180027fca`: `RtrMgrSetInterfaceInfo: Setting configuration for %ws`
- `0x1800288db`: `RtrMgrSetInterfaceInfo: %ws already on %ws. Setting info`

## pseudocode

```c
__int64 __fastcall RtrMgrSetInterfaceInfo(unsigned int a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v6; // r13
  __int64 *v7; // rax
  int v8; // eax
  BOOL v9; // r15d
  unsigned int v10; // r12d
  char v11; // bl
  __int64 v12; // rax
  BOOL v13; // edi
  __int64 v14; // rbx
  __int128 *v15; // r9
  __int64 PointerToTocEntry; // rax
  __int64 v17; // rcx
  _DWORD *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // edi
  __int128 *v21; // r9
  __int128 *v22; // r9
  __int128 *v23; // r9
  __int128 *v24; // r9
  int v25; // eax
  unsigned int v26; // edi
  _DWORD *v27; // rax
  _DWORD *v28; // r12
  unsigned int v29; // r9d
  __int64 v30; // r8
  __int64 *v31; // r15
  __int64 *v32; // rax
  __int128 *v33; // r9
  __int64 v34; // rax
  _DWORD *v35; // rdi
  __int128 *v36; // r9
  unsigned int v37; // r8d
  __int64 v38; // rax
  __int64 v39; // rdx
  __int128 *v40; // r9
  __int128 *v41; // r9
  __int128 *v42; // r9
  __int64 v43; // rax
  char *v44; // r12
  bool v45; // zf
  unsigned int v46; // r13d
  __int128 *v47; // r9
  unsigned int v48; // eax
  __int128 *v49; // r9
  __int64 *k; // rdi
  __int128 *v51; // r9
  __int128 *v52; // r9
  unsigned int v53; // eax
  __int128 *v54; // r9
  unsigned int v55; // eax
  __int128 *v56; // r9
  LPVOID v57; // rdi
  __int128 *v58; // r9
  unsigned int v59; // eax
  __int128 *v60; // r9
  __int64 InternalInterfaceForRoutingDomain; // r13
  __int64 v62; // rcx
  __int64 *v63; // rdi
  __int64 v64; // rax
  __int64 *v65; // rdx
  __int128 *v66; // r9
  _QWORD *m; // rdi
  _QWORD *v68; // r13
  __int128 *v69; // r9
  unsigned int v70; // eax
  __int128 *v71; // r9
  _QWORD *v72; // rcx
  _QWORD *v73; // rax
  __int64 *v74; // r12
  __int64 j; // rdi
  unsigned int v76; // eax
  __int64 v77; // r9
  __int128 *v78; // r9
  unsigned int v79; // eax
  __int128 *v80; // r9
  __int64 v81; // rbx
  unsigned int dwBytes; // [rsp+34h] [rbp-8E4h] BYREF
  unsigned int dwBytes_4; // [rsp+38h] [rbp-8E0h]
  int v86; // [rsp+3Ch] [rbp-8DCh] BYREF
  int v87; // [rsp+40h] [rbp-8D8h] BYREF
  __int64 v88; // [rsp+48h] [rbp-8D0h]
  int v89; // [rsp+50h] [rbp-8C8h]
  __int64 v90; // [rsp+58h] [rbp-8C0h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-8B8h]
  __int64 v92; // [rsp+68h] [rbp-8B0h]
  __int64 *i; // [rsp+70h] [rbp-8A8h]
  __int64 *v94; // [rsp+78h] [rbp-8A0h]
  __int128 v95; // [rsp+80h] [rbp-898h] BYREF
  __int128 v96; // [rsp+90h] [rbp-888h] BYREF
  int v97; // [rsp+A0h] [rbp-878h]
  int v98; // [rsp+A8h] [rbp-870h] BYREF
  __int128 v99; // [rsp+ACh] [rbp-86Ch]
  __int128 v100; // [rsp+BCh] [rbp-85Ch]
  int v101; // [rsp+CCh] [rbp-84Ch]
  int v102; // [rsp+D0h] [rbp-848h] BYREF
  char v103[2044]; // [rsp+D4h] [rbp-844h] BYREF

  v88 = a2;
  dwBytes = 0;
  v86 = 0;
  v102 = 0;
  v6 = a2;
  v7 = &g_rgicInfoCbv4;
  if ( a4 != 33 )
    v7 = &g_rgicInfoCbv6;
  v94 = v7;
  v8 = 5;
  v9 = a4 == 33;
  if ( a4 != 33 )
    v8 = 3;
  dwBytes_4 = v8;
  v10 = a4;
  memset_0(v103, 0, sizeof(v103));
  v98 = 0;
  v101 = 0;
  v99 = 0;
  v100 = 0;
  v95 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    v20 = 900;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v102) = 0;
      FormatRRASErrorString(&v102, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v102);
    }
    return v20;
  }
  ++HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v102) = 0;
    FormatRRASErrorString(&v102, L"Entered: %ws", L"RtrMgrSetInterfaceInfo");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v102);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( v6 && !(unsigned int)ValidateRouterInfoBlock(v6, a3) )
  {
    if ( (v11 & 0x40) != 0 )
    {
      LOWORD(v102) = 0;
      FormatRRASErrorString(
        &v102,
        L"RtrMgrSetInterfaceInfo: Validation Failed for Interface Info for transport %d. Info size %d",
        v10,
        a3);
      v11 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v102);
        v11 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v11 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: RtrMgrSetInterfaceInfo");
LABEL_49:
    v20 = 87;
LABEL_96:
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    return v20;
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  v12 = InterfaceLookupByICBSeqNumber(a1);
  v13 = 0;
  v14 = v12;
  if ( v12 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v102) = 0;
      LOWORD(v98) = 0;
      FormatRRASErrorString(&v102, L"RtrMgrSetInterfaceInfo: Setting configuration for %ws", *(_QWORD *)(v12 + 72));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v15 = &v95;
        if ( v14 != -688 )
          LODWORD(v15) = v14 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v102,
          (_DWORD)v15,
          *(_QWORD *)(v14 + 72),
          (__int64)&v98);
      }
    }
    v92 = *(_QWORD *)(v14 + 184);
    v89 = 0;
    PointerToTocEntry = GetPointerToTocEntry(4294901764LL, v6);
    if ( PointerToTocEntry )
    {
      if ( *(_DWORD *)(PointerToTocEntry + 4) )
      {
        v17 = *(unsigned int *)(PointerToTocEntry + 12);
        if ( (unsigned int)v17 < *(_DWORD *)(v6 + 4) )
        {
          v18 = (_DWORD *)(v6 + v17);
          if ( v18 )
          {
            if ( *(_DWORD *)(v14 + 172) != 2 )
              goto LABEL_50;
            if ( *v18 == 1 )
            {
              v19 = SetInterfaceAdminStatus(v14, 1, &v86);
              v20 = v19;
              if ( v19 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  LOWORD(v102) = 0;
                  LOWORD(v98) = 0;
                  FormatRRASErrorString(
                    &v102,
                    L"RtrMgrSetInterfaceInfo: Error %d setting Admin Status on %ws",
                    v19,
                    *(_QWORD *)(v14 + 72));
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v21 = &v95;
                    if ( v14 != -688 )
                      LODWORD(v21) = v14 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v102,
                      (_DWORD)v21,
                      *(_QWORD *)(v14 + 72),
                      (__int64)&v98);
                  }
                }
                RtlReleaseResource(&Resource);
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  v22 = &v95;
                  LOWORD(v98) = 0;
                  if ( v14 != -688 )
                    LODWORD(v22) = v14 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)L"Leaving: RtrMgrSetInterfaceInfo",
                    (_DWORD)v22,
                    *(_QWORD *)(v14 + 72),
                    (__int64)&v98);
                }
                goto LABEL_96;
              }
              v89 = 1;
            }
          }
        }
      }
    }
    if ( *(_DWORD *)(v14 + 172) == 2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v102) = 0;
        LOWORD(v98) = 0;
        FormatRRASErrorString(
          &v102,
          L"RtrMgrSetInterfaceInfo: Can not set info for %ws since the the admin state is DOWN",
          *(_QWORD *)(v14 + 72));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v23 = &v95;
          if ( v14 != -688 )
            LODWORD(v23) = v14 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v102,
            (_DWORD)v23,
            *(_QWORD *)(v14 + 72),
            (__int64)&v98);
        }
      }
      RtlReleaseResource(&Resource);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v98) = 0;
        v24 = &v95;
        if ( v14 != -688 )
          LODWORD(v24) = v14 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)L"Leaving: RtrMgrSetInterfaceInfo",
          (_DWORD)v24,
          *(_QWORD *)(v14 + 72),
          (__int64)&v98);
      }
      goto LABEL_49;
    }
LABEL_50:
    if ( v10 == 33 )
      SetRouterDiscoveryInfo(v14, v6);
    lpMem = 0;
    if ( !*(_DWORD *)(v14 + 512) )
      goto LABEL_59;
    v25 = SizeofIpBinding(*(unsigned int *)(v14 + 668), v9, &dwBytes);
    v26 = dwBytes;
    if ( v25 < 0 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0
        || (LOWORD(v102) = 0,
            LOWORD(v98) = 0,
            FormatRRASErrorString(
              &v102,
              L"SetInterfaceInfo: Arithmetic overflow error allocating %d bytes for binding",
              dwBytes),
            (Microsoft_Windows_RRASEnableBits & 0x40) == 0) )
      {
LABEL_89:
        RtlReleaseResource(&Resource);
        if ( v86 )
          ((void (__fastcall *)(__int64, _QWORD, __int64))EnableInterfaceWithDIM)(v92, v10, 1);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v42 = &v95;
          LOWORD(v98) = 0;
          if ( v14 != -688 )
            LODWORD(v42) = v14 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)L"Leaving: RtrMgrSetInterfaceInfo",
            (_DWORD)v42,
            *(_QWORD *)(v14 + 72),
            (__int64)&v98);
        }
        v20 = 8;
        goto LABEL_96;
      }
      v40 = &v95;
      if ( v14 != -688 )
        LODWORD(v40) = v14 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v102,
        (_DWORD)v40,
        *(_QWORD *)(v14 + 72),
        (__int64)&v98);
    }
    else
    {
      v27 = HeapAlloc(IPRouterHeap, 0, dwBytes);
      lpMem = v27;
      v28 = v27;
      if ( v27 )
      {
        *v27 = *(_DWORD *)(v14 + 668);
        if ( a4 == 33 )
        {
          v29 = 0;
          v27[1] = *(_DWORD *)(v14 + 672);
          v27[2] = *(_DWORD *)(v14 + 532);
          for ( *((_QWORD *)v27 + 2) = *(_QWORD *)(v14 + 536);
                v29 < *(_DWORD *)(v14 + 668);
                v27[2 * v30 + 7] = *(_DWORD *)(*(_QWORD *)(v14 + 712) + 28 * v30 + 4) )
          {
            v30 = v29++;
            v27[2 * v30 + 6] = *(_DWORD *)(28 * v30 + *(_QWORD *)(v14 + 712));
          }
        }
        else
        {
          v37 = 0;
          *(_OWORD *)(v27 + 1) = *(_OWORD *)(v14 + 672);
          v27[5] = *(_DWORD *)(v14 + 532);
          for ( *((_QWORD *)v27 + 3) = *(_QWORD *)(v14 + 536);
                v37 < *(_DWORD *)(v14 + 668);
                v28[v39 + 12] = *(unsigned __int8 *)(*(_QWORD *)(v14 + 712) + 28 * v38) )
          {
            v38 = v37++;
            v39 = 5 * v38;
            *(_OWORD *)&v28[v39 + 8] = *(_OWORD *)(28 * v38 + *(_QWORD *)(v14 + 712) + 4);
          }
        }
        v10 = a4;
LABEL_59:
        dwBytes = 0;
        RtlAcquireResourceShared(&stru_18008C4A0, 1u);
        v31 = (__int64 *)g_leProtoCbListV6;
        v32 = (__int64 *)&g_leProtoCbListV4;
        if ( v10 == 33 )
          v31 = (__int64 *)g_leProtoCbListV4;
        else
          v32 = &g_leProtoCbListV6;
        for ( i = v32; ; v32 = i )
        {
          if ( v31 == v32 )
          {
            RtlReleaseResource(&stru_18008C4A0);
            v74 = v94;
            for ( j = 0; (unsigned int)j < dwBytes_4; j = (unsigned int)(j + 1) )
            {
              v87 = 0;
              v76 = ((__int64 (__fastcall *)(__int64, __int64, int *))v74[5 * j + 2])(v14, v6, &v87);
              if ( v76 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v77 = v74[5 * j];
                  LOWORD(v102) = 0;
                  LOWORD(v98) = 0;
                  FormatRRASErrorString(
                    &v102,
                    L"RtrMgrSetInterfaceInfo: Error %d setting %hs info for %ws",
                    v76,
                    v77,
                    *(_QWORD *)(v14 + 72));
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v78 = &v95;
                    if ( v14 != -688 )
                      LODWORD(v78) = v14 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v102,
                      (_DWORD)v78,
                      *(_QWORD *)(v14 + 72),
                      (__int64)&v98);
                  }
                }
              }
            }
            if ( lpMem )
              HeapFree(IPRouterHeap, 0, lpMem);
            if ( !v89 )
            {
              v79 = SetInterfaceStatusInfo(v14, v6, &v86);
              if ( v79 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  LOWORD(v102) = 0;
                  LOWORD(v98) = 0;
                  FormatRRASErrorString(
                    &v102,
                    L"RtrMgrSetInterfaceInfo: Error %d setting status info for %ws",
                    v79,
                    *(_QWORD *)(v14 + 72));
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v80 = &v95;
                    if ( v14 != -688 )
                      LODWORD(v80) = v14 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v102,
                      (_DWORD)v80,
                      *(_QWORD *)(v14 + 72),
                      (__int64)&v98);
                  }
                }
              }
            }
            v10 = a4;
            v45 = *(_DWORD *)(v14 + 172) == 1;
            v81 = v92;
            v13 = v45;
            goto LABEL_217;
          }
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v102) = 0;
            LOWORD(v98) = 0;
            FormatRRASErrorString(&v102, L"RtrMgrSetInterfaceInfo: Checking for info for %ws", v31[4]);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v33 = &v95;
              if ( v14 != -688 )
                LODWORD(v33) = v14 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v102,
                (_DWORD)v33,
                *(_QWORD *)(v14 + 72),
                (__int64)&v98);
            }
          }
          v34 = GetPointerToTocEntry(*((unsigned int *)v31 + 15), v6);
          v35 = (_DWORD *)v34;
          if ( v34 )
            break;
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v102) = 0;
            LOWORD(v98) = 0;
            FormatRRASErrorString(&v102, L"RtrMgrSetInterfaceInfo: No TOC for %ws. No change", v31[4]);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v36 = &v95;
              if ( v14 != -688 )
                LODWORD(v36) = v14 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v102,
                (_DWORD)v36,
                *(_QWORD *)(v14 + 72),
                (__int64)&v98);
            }
          }
LABEL_109:
          v31 = (__int64 *)*v31;
        }
        v43 = *(unsigned int *)(v34 + 12);
        if ( (unsigned int)v43 >= *(_DWORD *)(v6 + 4) )
          v44 = 0;
        else
          v44 = (char *)(v43 + v6);
        v45 = *v35 == -2127091947;
        v46 = v35[1];
        v87 = v35[2];
        if ( v45 )
        {
          if ( !v46 )
          {
            v44 = (char *)HeapAlloc(IPRouterHeap, 0, 0x24u);
            if ( !v44 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v102) = 0;
                LOWORD(v98) = 0;
                FormatRRASErrorString(&v102, L"SetInterfaceInfo: Error allocating %d bytes for NAT info", 36);
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v47 = &v95;
                  if ( v14 != -688 )
                    LODWORD(v47) = v14 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrMgrParamTraceError,
                    (unsigned int)&v102,
                    (_DWORD)v47,
                    *(_QWORD *)(v14 + 72),
                    (__int64)&v98);
                }
              }
LABEL_108:
              v6 = v88;
              goto LABEL_109;
            }
            v48 = *(_DWORD *)(v14 + 16);
            *((_DWORD *)v44 + 2) = 1;
            *(_QWORD *)v44 = v48;
            *(_QWORD *)(v44 + 12) = 28;
            v35[1] = 36;
            dwBytes = 1;
LABEL_113:
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              LOWORD(v102) = 0;
              LOWORD(v98) = 0;
              FormatRRASErrorString(&v102, L"RtrMgrSetInterfaceInfo: TOC Found for %ws", v31[4]);
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                v49 = &v95;
                if ( v14 != -688 )
                  LODWORD(v49) = v14 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)&v102,
                  (_DWORD)v49,
                  *(_QWORD *)(v14 + 72),
                  (__int64)&v98);
              }
            }
            for ( k = *(__int64 **)(v14 + 56); k != (__int64 *)(v14 + 56); k = (__int64 *)*k )
            {
              if ( *(_DWORD *)(k[3] + 60) == *((_DWORD *)v31 + 15) )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  LOWORD(v102) = 0;
                  LOWORD(v98) = 0;
                  FormatRRASErrorString(
                    &v102,
                    L"RtrMgrSetInterfaceInfo: %ws already on %ws. Setting info",
                    v31[4],
                    *(_QWORD *)(v14 + 72));
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                  {
                    v51 = &v95;
                    if ( v14 != -688 )
                      LODWORD(v51) = v14 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrmgrParamTraceInfo,
                      (unsigned int)&v102,
                      (_DWORD)v51,
                      *(_QWORD *)(v14 + 72),
                      (__int64)&v98);
                  }
                }
                (*(void (__fastcall **)(_QWORD, char *, __int64, _QWORD, int))(k[3] + 160))(
                  *(unsigned int *)(v14 + 16),
                  v44,
                  1280,
                  v46,
                  v87);
                *((_DWORD *)k + 4) = 0;
                goto LABEL_169;
              }
            }
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              LOWORD(v102) = 0;
              LOWORD(v98) = 0;
              FormatRRASErrorString(
                &v102,
                L"RtrMgrSetInterfaceInfo: %ws not running %ws. Adding interface",
                v31[4],
                *(_QWORD *)(v14 + 72));
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                v52 = &v95;
                if ( v14 != -688 )
                  LODWORD(v52) = v14 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)&v102,
                  (_DWORD)v52,
                  *(_QWORD *)(v14 + 72),
                  (__int64)&v98);
              }
            }
            v53 = AddInterfaceToProtocol(v14, (__int64)v31, (__int64)v44, 1280, v46, v87);
            if ( v53 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v102) = 0;
                LOWORD(v98) = 0;
                FormatRRASErrorString(
                  &v102,
                  L"RtrMgrSetInterfaceInfo: Error %d adding %ws to %ws",
                  v53,
                  *(_QWORD *)(v14 + 72),
                  v31[4]);
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v54 = &v95;
                  if ( v14 != -688 )
                    LODWORD(v54) = v14 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrMgrParamTraceError,
                    (unsigned int)&v102,
                    (_DWORD)v54,
                    *(_QWORD *)(v14 + 72),
                    (__int64)&v98);
                }
              }
            }
            v55 = ((__int64 (__fastcall *)(_QWORD, bool, __int64))v31[18])(
                    *(unsigned int *)(v14 + 16),
                    *(_DWORD *)(v14 + 168) >= 4u,
                    1);
            if ( v55 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v102) = 0;
                LOWORD(v98) = 0;
                FormatRRASErrorString(
                  &v102,
                  L"RtrMgrSetInterfaceInfo: Error %d enabling %ws with %ws",
                  v55,
                  *(_QWORD *)(v14 + 72),
                  v31[4]);
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v56 = &v95;
                  if ( v14 != -688 )
                    LODWORD(v56) = v14 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrMgrParamTraceError,
                    (unsigned int)&v102,
                    (_DWORD)v56,
                    *(_QWORD *)(v14 + 72),
                    (__int64)&v98);
                }
              }
            }
            v57 = lpMem;
            if ( lpMem )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                LOWORD(v102) = 0;
                LOWORD(v98) = 0;
                FormatRRASErrorString(
                  &v102,
                  L"RtrMgrSetInterfaceInfo: Binding %ws in %ws",
                  *(_QWORD *)(v14 + 72),
                  v31[3]);
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  v58 = &v95;
                  if ( v14 != -688 )
                    LODWORD(v58) = v14 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)&v102,
                    (_DWORD)v58,
                    *(_QWORD *)(v14 + 72),
                    (__int64)&v98);
                }
              }
              v59 = BindInterfaceInProtocol(v14, v31, v57);
              if ( v59 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  LOWORD(v102) = 0;
                  LOWORD(v98) = 0;
                  FormatRRASErrorString(
                    &v102,
                    L"RtrMgrSetInterfaceInfo: Error %d binding %ws to %ws",
                    v59,
                    *(_QWORD *)(v14 + 72),
                    v31[3]);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v60 = &v95;
                    if ( v14 != -688 )
                      LODWORD(v60) = v14 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v102,
                      (_DWORD)v60,
                      *(_QWORD *)(v14 + 72),
                      (__int64)&v98);
                  }
                }
              }
            }
            InternalInterfaceForRoutingDomain = GetInternalInterfaceForRoutingDomain((struct _GUID *)(v14 + 688), a4);
            if ( v14 == InternalInterfaceForRoutingDomain )
            {
              if ( v31[23] )
              {
                v62 = ICBList;
                v97 = 0;
                v90 = 0;
                v96 = 0;
                if ( (__int64 *)ICBList != &ICBList )
                {
                  v63 = &ICBList;
                  do
                  {
                    if ( !*(_DWORD *)(v62 + 144) )
                    {
                      v64 = *(_QWORD *)(v62 + 712);
                      if ( a4 == 33 )
                      {
                        LODWORD(v90) = *(_DWORD *)v64;
                        HIDWORD(v90) = *(_DWORD *)(*(_QWORD *)(v62 + 712) + 4LL);
                      }
                      else
                      {
                        v96 = *(_OWORD *)(v64 + 4);
                        v97 = **(unsigned __int8 **)(v62 + 712);
                      }
                      v65 = (__int64 *)&v96;
                      if ( a4 == 33 )
                        v65 = &v90;
                      ((void (__fastcall *)(_QWORD, __int64 *))v31[23])(
                        *(unsigned int *)(InternalInterfaceForRoutingDomain + 16),
                        v65);
                    }
                    v63 = (__int64 *)*v63;
                    v62 = *v63;
                  }
                  while ( (__int64 *)*v63 != &ICBList );
                }
              }
            }
LABEL_169:
            if ( dwBytes )
            {
              HeapFree(IPRouterHeap, 0, v44);
              dwBytes = 0;
            }
            goto LABEL_108;
          }
        }
        else if ( !v46 )
        {
          goto LABEL_171;
        }
        if ( v44 )
          goto LABEL_113;
LABEL_171:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v102) = 0;
          LOWORD(v98) = 0;
          FormatRRASErrorString(
            &v102,
            L"RtrMgrSetInterfaceInfo: A zero size TOC was found for %ws on %ws",
            v31[3],
            *(_QWORD *)(v14 + 72));
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v66 = &v95;
            if ( v14 != -688 )
              LODWORD(v66) = v14 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v102,
              (_DWORD)v66,
              *(_QWORD *)(v14 + 72),
              (__int64)&v98);
          }
        }
        for ( m = *(_QWORD **)(v14 + 56); m != (_QWORD *)(v14 + 56); m = v68 )
        {
          v68 = (_QWORD *)*m;
          if ( *(_DWORD *)(m[3] + 60LL) == *((_DWORD *)v31 + 15) )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              LOWORD(v102) = 0;
              LOWORD(v98) = 0;
              FormatRRASErrorString(
                &v102,
                L"RtrMgrSetInterfaceInfo: Deleting %ws from %ws",
                v31[3],
                *(_QWORD *)(v14 + 72));
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                v69 = &v95;
                if ( v14 != -688 )
                  LODWORD(v69) = v14 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)&v102,
                  (_DWORD)v69,
                  *(_QWORD *)(v14 + 72),
                  (__int64)&v98);
              }
            }
            v70 = ((__int64 (__fastcall *)(_QWORD))v31[17])(*(unsigned int *)(v14 + 16));
            if ( v70 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v102) = 0;
                LOWORD(v98) = 0;
                FormatRRASErrorString(
                  &v102,
                  L"RtrMgrSetInterfaceInfo: Err %d deleting %ws from %ws",
                  v70,
                  *(_QWORD *)(v14 + 72),
                  v31[3]);
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v71 = &v95;
                  if ( v14 != -688 )
                    LODWORD(v71) = v14 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrMgrParamTraceError,
                    (unsigned int)&v102,
                    (_DWORD)v71,
                    *(_QWORD *)(v14 + 72),
                    (__int64)&v98);
                }
              }
            }
            else
            {
              v72 = (_QWORD *)*m;
              if ( *(_QWORD **)(*m + 8LL) != m || (v73 = (_QWORD *)m[1], (_QWORD *)*v73 != m) )
                __fastfail(3u);
              *v73 = v72;
              v72[1] = v73;
              HeapFree(IPRouterHeap, 0, m);
            }
          }
        }
        goto LABEL_108;
      }
      v10 = a4;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v102) = 0;
      LOWORD(v98) = 0;
      FormatRRASErrorString(&v102, L"RtrMgrSetInterfaceInfo: Error allocating %d bytes for binding", v26);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v41 = &v95;
        if ( v14 != -688 )
          LODWORD(v41) = v14 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v102,
          (_DWORD)v41,
          *(_QWORD *)(v14 + 72),
          (__int64)&v98);
      }
    }
    goto LABEL_89;
  }
  v81 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v102) = 0;
    FormatRRASErrorString(&v102, L"RtrMgrSetInterfaceInfo : No interface with ICB number %d", a1);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v102);
  }
LABEL_217:
  RtlReleaseResource(&Resource);
  if ( v86 )
    ((void (__fastcall *)(__int64, _QWORD, BOOL))EnableInterfaceWithDIM)(v81, v10, v13);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: RtrMgrSetInterfaceInfo");
  EnterCriticalSection(&RouterStateLock);
  --HIDWORD(RouterState);
  LeaveCriticalSection(&RouterStateLock);
  return 0;
}

```

## disassembly

```asm
0x180027dc0  push    rbx
0x180027dc2  push    rsi
0x180027dc3  push    rdi
0x180027dc4  push    r12
0x180027dc6  push    r13
0x180027dc8  push    r14
0x180027dca  push    r15
0x180027dcc  sub     rsp, 8E0h
0x180027dd3  mov     rax, cs:__security_cookie
0x180027dda  xor     rax, rsp
0x180027ddd  mov     [rsp+918h+var_48], rax
0x180027de5  xor     ebx, ebx
0x180027de7  mov     [rsp+918h+var_8D0], rdx
0x180027dec  cmp     r9d, 21h ; '!'
0x180027df0  mov     [rsp+918h+var_8E8], r9d
0x180027df5  mov     rsi, rcx
0x180027df8  mov     dword ptr [rsp+918h+dwBytes], ebx
0x180027dfc  lea     rcx, g_rgicInfoCbv6
0x180027e03  mov     [rsp+918h+var_8DC], ebx
0x180027e07  mov     edi, r8d
0x180027e0a  mov     [rsp+918h+var_848], ebx
0x180027e11  mov     r13, rdx
0x180027e14  lea     rax, g_rgicInfoCbv4
0x180027e1b  cmovnz  rax, rcx
0x180027e1f  mov     r15d, ebx
0x180027e22  mov     [rsp+918h+var_8A0], rax
0x180027e27  lea     ecx, [rbx+3]
0x180027e2a  lea     eax, [rbx+5]
0x180027e2d  setz    r15b
0x180027e31  cmovnz  eax, ecx
0x180027e34  mov     r8d, 7FCh; Size
0x180027e3a  xor     edx, edx; Val
0x180027e3c  mov     dword ptr [rsp+918h+dwBytes+4], eax
0x180027e40  lea     rcx, [rsp+918h+var_844]; void *
0x180027e48  mov     r12d, r9d
0x180027e4b  call    memset_0
0x180027e50  xorps   xmm0, xmm0
0x180027e53  mov     [rsp+918h+var_870], ebx
0x180027e5a  xor     eax, eax
0x180027e5c  lea     r14, RouterStateLock
0x180027e63  mov     rcx, r14; lpCriticalSection
0x180027e66  mov     [rsp+918h+var_84C], eax
0x180027e6d  movups  [rsp+918h+var_86C], xmm0
0x180027e75  movups  [rsp+918h+var_85C], xmm0
0x180027e7d  movups  [rsp+918h+var_898], xmm0
0x180027e85  call    cs:__imp_EnterCriticalSection
0x180027e8b  cmp     dword ptr cs:RouterState, ebx
0x180027e91  mov     rcx, r14; lpCriticalSection
0x180027e94  jnz     loc_18002923C
0x180027e9a  inc     dword ptr cs:RouterState+4
0x180027ea0  call    cs:__imp_LeaveCriticalSection
0x180027ea6  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x180027ead  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180027eb4  test    bl, bl
0x180027eb6  jns     short loc_180027F06
0x180027eb8  xor     eax, eax
0x180027eba  lea     r8, aRtrmgrsetinter_7; "RtrMgrSetInterfaceInfo"
0x180027ec1  lea     rdx, aEnteredWs; "Entered: %ws"
0x180027ec8  mov     word ptr [rsp+918h+var_848], ax
0x180027ed0  lea     rcx, [rsp+918h+var_848]
0x180027ed8  call    FormatRRASErrorString
0x180027edd  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x180027ee4  test    bl, bl
0x180027ee6  jns     short loc_180027F06
0x180027ee8  lea     r8, [rsp+918h+var_848]
0x180027ef0  mov     rcx, r14
0x180027ef3  lea     rdx, RasRtrmgrTraceInfo
0x180027efa  call    McTemplateU0z_EventWriteTransfer
0x180027eff  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x180027f06  test    r13, r13
0x180027f09  jz      loc_180027F95
0x180027f0f  mov     edx, edi
0x180027f11  mov     rcx, r13
0x180027f14  call    ValidateRouterInfoBlock
0x180027f19  test    eax, eax
0x180027f1b  jnz     short loc_180027F95
0x180027f1d  mov     sil, 40h ; '@'
0x180027f20  test    sil, bl
0x180027f23  jz      short loc_180027F71
0x180027f25  mov     r9d, edi
0x180027f28  mov     word ptr [rsp+918h+var_848], ax
0x180027f30  mov     r8d, r12d
0x180027f33  lea     rdx, aRtrmgrsetinter_19; "RtrMgrSetInterfaceInfo: Validation Fail"...
0x180027f3a  lea     rcx, [rsp+918h+var_848]
0x180027f42  call    FormatRRASErrorString
0x180027f47  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x180027f4e  test    sil, bl
0x180027f51  jz      short loc_180027F71
0x180027f53  lea     r8, [rsp+918h+var_848]
0x180027f5b  mov     rcx, r14
0x180027f5e  lea     rdx, RasRtrMgrTraceError
0x180027f65  call    McTemplateU0z_EventWriteTransfer
0x180027f6a  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x180027f71  test    bl, 80h
0x180027f74  jz      loc_18002828E
0x180027f7a  lea     r8, aLeavingRtrmgrs; "Leaving: RtrMgrSetInterfaceInfo"
0x180027f81  mov     rcx, r14
0x180027f84  lea     rdx, RasRtrmgrTraceInfo
0x180027f8b  call    McTemplateU0z_EventWriteTransfer
0x180027f90  jmp     loc_18002828E
0x180027f95  mov     dl, 1; Wait
0x180027f97  lea     rcx, Resource; Resource
0x180027f9e  call    cs:__imp_RtlAcquireResourceExclusive
0x180027fa4  mov     ecx, esi
0x180027fa6  call    InterfaceLookupByICBSeqNumber
0x180027fab  xor     edi, edi
0x180027fad  mov     rbx, rax
0x180027fb0  test    rax, rax
0x180027fb3  jz      loc_180029186
0x180027fb9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180027fc0  jge     short loc_180028036
0x180027fc2  mov     word ptr [rsp+918h+var_848], di
0x180027fca  lea     rdx, aRtrmgrsetinter_11; "RtrMgrSetInterfaceInfo: Setting configu"...
0x180027fd1  mov     word ptr [rsp+918h+var_870], di
0x180027fd9  lea     rcx, [rsp+918h+var_848]
0x180027fe1  mov     r8, [rax+48h]
0x180027fe5  call    FormatRRASErrorString
0x180027fea  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180027ff1  jge     short loc_180028036
0x180027ff3  lea     rax, [rbx+2B0h]
0x180027ffa  mov     rcx, r14
0x180027ffd  test    rax, rax
0x180028000  lea     r9, [rsp+918h+var_898]
0x180028008  lea     r8, [rsp+918h+var_848]
0x180028010  cmovnz  r9, rax
0x180028014  lea     rdx, RasRtrmgrParamTraceInfo
0x18002801b  lea     rax, [rsp+918h+var_870]
0x180028023  mov     [rsp+918h+var_8F0], rax
0x180028028  mov     rax, [rbx+48h]
0x18002802c  mov     [rsp+918h+var_8F8], rax
0x180028031  call    McTemplateU0zjzz_EventWriteTransfer
0x180028036  mov     rax, [rbx+0B8h]
0x18002803d  mov     rdx, r13
0x180028040  mov     ecx, 0FFFF0004h
0x180028045  mov     [rsp+918h+var_8B0], rax
0x18002804a  mov     [rsp+918h+var_8C8], edi
0x18002804e  call    GetPointerToTocEntry
0x180028053  test    rax, rax
0x180028056  jz      loc_1800281A4
0x18002805c  cmp     [rax+4], edi
0x18002805f  jz      loc_1800281A4
0x180028065  mov     ecx, [rax+0Ch]
0x180028068  cmp     ecx, [r13+4]
0x18002806c  jnb     loc_1800281A4
0x180028072  add     rcx, r13
0x180028075  jz      loc_1800281A4
0x18002807b  cmp     dword ptr [rbx+0ACh], 2
0x180028082  jnz     loc_180028298
0x180028088  mov     esi, 1
0x18002808d  cmp     [rcx], esi
0x18002808f  jnz     loc_1800281A4
0x180028095  lea     r8, [rsp+918h+var_8DC]
0x18002809a  mov     edx, esi
0x18002809c  mov     rcx, rbx
0x18002809f  call    SetInterfaceAdminStatus
0x1800280a4  mov     edi, eax
0x1800280a6  test    eax, eax
0x1800280a8  jz      loc_18002819E
0x1800280ae  mov     sil, 40h ; '@'
0x1800280b1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800280b8  jz      short loc_180028133
0x1800280ba  xor     ecx, ecx
0x1800280bc  lea     rdx, aRtrmgrsetinter_1; "RtrMgrSetInterfaceInfo: Error %d settin"...
0x1800280c3  mov     word ptr [rsp+918h+var_848], cx
0x1800280cb  mov     r8d, eax
0x1800280ce  mov     word ptr [rsp+918h+var_870], cx
0x1800280d6  lea     rcx, [rsp+918h+var_848]
0x1800280de  mov     r9, [rbx+48h]
0x1800280e2  call    FormatRRASErrorString
0x1800280e7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800280ee  jz      short loc_180028133
0x1800280f0  lea     rax, [rbx+2B0h]
0x1800280f7  mov     rcx, r14
0x1800280fa  test    rax, rax
0x1800280fd  lea     r9, [rsp+918h+var_898]
0x180028105  lea     r8, [rsp+918h+var_848]
0x18002810d  cmovnz  r9, rax
0x180028111  lea     rdx, RasRtrMgrParamTraceError
0x180028118  lea     rax, [rsp+918h+var_870]
0x180028120  mov     [rsp+918h+var_8F0], rax
0x180028125  mov     rax, [rbx+48h]
0x180028129  mov     [rsp+918h+var_8F8], rax
0x18002812e  call    McTemplateU0zjzz_EventWriteTransfer
0x180028133  lea     rcx, Resource; Resource
0x18002813a  call    cs:__imp_RtlReleaseResource
0x180028140  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180028147  jz      loc_1800286E8
0x18002814d  xor     eax, eax
0x18002814f  lea     r9, [rsp+918h+var_898]
0x180028157  mov     word ptr [rsp+918h+var_870], ax
0x18002815f  lea     r8, aLeavingRtrmgrs; "Leaving: RtrMgrSetInterfaceInfo"
0x180028166  lea     rax, [rbx+2B0h]
0x18002816d  mov     rcx, r14
0x180028170  test    rax, rax
0x180028173  lea     rdx, RasRtrmgrParamTraceInfo
0x18002817a  cmovnz  r9, rax
0x18002817e  lea     rax, [rsp+918h+var_870]
0x180028186  mov     [rsp+918h+var_8F0], rax
0x18002818b  mov     rax, [rbx+48h]
0x18002818f  mov     [rsp+918h+var_8F8], rax
0x180028194  call    McTemplateU0zjzz_EventWriteTransfer
0x180028199  jmp     loc_1800286E8
0x18002819e  mov     [rsp+918h+var_8C8], esi
0x1800281a2  xor     edi, edi
0x1800281a4  cmp     dword ptr [rbx+0ACh], 2
0x1800281ab  jnz     loc_180028298
0x1800281b1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800281b8  jge     short loc_18002822E
0x1800281ba  mov     word ptr [rsp+918h+var_848], di
0x1800281c2  lea     rdx, aRtrmgrsetinter_14; "RtrMgrSetInterfaceInfo: Can not set inf"...
0x1800281c9  mov     word ptr [rsp+918h+var_870], di
0x1800281d1  lea     rcx, [rsp+918h+var_848]
0x1800281d9  mov     r8, [rbx+48h]
0x1800281dd  call    FormatRRASErrorString
0x1800281e2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800281e9  jge     short loc_18002822E
0x1800281eb  lea     rax, [rbx+2B0h]
0x1800281f2  mov     rcx, r14
0x1800281f5  test    rax, rax
0x1800281f8  lea     r9, [rsp+918h+var_898]
0x180028200  lea     r8, [rsp+918h+var_848]
0x180028208  cmovnz  r9, rax
0x18002820c  lea     rdx, RasRtrmgrParamTraceInfo
0x180028213  lea     rax, [rsp+918h+var_870]
0x18002821b  mov     [rsp+918h+var_8F0], rax
0x180028220  mov     rax, [rbx+48h]
0x180028224  mov     [rsp+918h+var_8F8], rax
0x180028229  call    McTemplateU0zjzz_EventWriteTransfer
0x18002822e  lea     rcx, Resource; Resource
0x180028235  call    cs:__imp_RtlReleaseResource
0x18002823b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180028242  jz      short loc_18002828E
0x180028244  lea     rax, [rbx+2B0h]
0x18002824b  mov     word ptr [rsp+918h+var_870], di
0x180028253  test    rax, rax
0x180028256  lea     r9, [rsp+918h+var_898]
0x18002825e  lea     r8, aLeavingRtrmgrs; "Leaving: RtrMgrSetInterfaceInfo"
0x180028265  mov     rcx, r14
0x180028268  cmovnz  r9, rax
0x18002826c  lea     rdx, RasRtrmgrParamTraceInfo
0x180028273  lea     rax, [rsp+918h+var_870]
0x18002827b  mov     [rsp+918h+var_8F0], rax
0x180028280  mov     rax, [rbx+48h]
0x180028284  mov     [rsp+918h+var_8F8], rax
0x180028289  call    McTemplateU0zjzz_EventWriteTransfer
0x18002828e  mov     edi, 57h ; 'W'
0x180028293  jmp     loc_1800286E8
0x180028298  cmp     r12d, 21h ; '!'
0x18002829c  jnz     short loc_1800282A9
0x18002829e  mov     rdx, r13
0x1800282a1  mov     rcx, rbx
0x1800282a4  call    SetRouterDiscoveryInfo
0x1800282a9  mov     [rsp+918h+lpMem], rdi
0x1800282ae  cmp     [rbx+200h], edi
0x1800282b4  jz      loc_180028378
0x1800282ba  mov     ecx, [rbx+29Ch]
0x1800282c0  lea     r8, [rsp+918h+dwBytes]
0x1800282c5  mov     edx, r15d
0x1800282c8  call    SizeofIpBinding
0x1800282cd  mov     edi, dword ptr [rsp+918h+dwBytes]
0x1800282d1  mov     sil, 40h ; '@'
0x1800282d4  test    eax, eax
0x1800282d6  js      loc_18002855C
0x1800282dc  mov     rcx, cs:IPRouterHeap; hHeap
0x1800282e3  mov     r8d, edi; dwBytes
0x1800282e6  xor     edx, edx; dwFlags
0x1800282e8  call    cs:__imp_HeapAlloc
0x1800282ee  mov     [rsp+918h+lpMem], rax
0x1800282f3  mov     r12, rax
0x1800282f6  test    rax, rax
0x1800282f9  jz      loc_180028552
0x1800282ff  mov     ecx, [rbx+29Ch]
0x180028305  xor     edi, edi
0x180028307  cmp     [rsp+918h+var_8E8], 21h ; '!'
0x18002830c  mov     [rax], ecx
0x18002830e  jnz     loc_1800284E1
0x180028314  mov     eax, [rbx+2A0h]
0x18002831a  mov     r9d, edi
0x18002831d  mov     [r12+4], eax
0x180028322  mov     eax, [rbx+214h]
0x180028328  mov     [r12+8], eax
0x18002832d  mov     rax, [rbx+218h]
0x180028334  mov     [r12+10h], rax
0x180028339  cmp     [rbx+29Ch], edi
0x18002833f  jbe     short loc_180028373
0x180028341  mov     rax, [rbx+2C8h]
0x180028348  mov     r8d, r9d
0x18002834b  inc     r9d
0x18002834e  imul    rdx, r8, 1Ch
0x180028352  mov     ecx, [rdx+rax]
0x180028355  mov     [r12+r8*8+18h], ecx
0x18002835a  mov     rax, [rbx+2C8h]
0x180028361  mov     ecx, [rax+rdx+4]
0x180028365  mov     [r12+r8*8+1Ch], ecx
0x18002836a  cmp     r9d, [rbx+29Ch]
0x180028371  jb      short loc_180028341
0x180028373  mov     r12d, [rsp+918h+var_8E8]
0x180028378  mov     dl, 1; Wait
0x18002837a  mov     dword ptr [rsp+918h+dwBytes], edi
0x18002837e  lea     rcx, stru_18008C4A0; Resource
  ... truncated ...
```
