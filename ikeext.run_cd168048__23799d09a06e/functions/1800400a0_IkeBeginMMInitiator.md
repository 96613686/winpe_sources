# IkeBeginMMInitiator

- ea: `0x1800400a0`
- end: `0x180040d6a`
- name: `IkeBeginMMInitiator`
- size: `3274`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800bbdb0`
- `0x1800e0290`

## callees

- `0x180008388`
- `0x18000b2f0`
- `0x1800144c0`
- `0x18003aa50`
- `0x1800400a0`
- `0x180043fb0`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`
- `0x180066d30`
- `0x18006d608`
- `0x1800eb6dc`
- `0x1800ec038`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040157`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004019e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800403d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040440`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040487`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040595`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800405fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040641`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004079e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040830`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004087a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040a35`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040a82`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040c0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040c57`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040157`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004019e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800403d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040440`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040487`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040595`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800405fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040641`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004079e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040830`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004087a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040a35`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040a82`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040c0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040c57`
- `ntdll!EtwEventWriteTransfer` at `0x180040277`
- `ntdll!EtwEventWriteTransfer` at `0x18004035c`
- `ntdll!EtwEventWriteTransfer` at `0x180040548`
- `ntdll!EtwEventWriteTransfer` at `0x18004070c`
- `ntdll!EtwEventWriteTransfer` at `0x18004099d`
- `ntdll!EtwEventWriteTransfer` at `0x180040b71`
- `ntdll!EtwEventWriteTransfer` at `0x180040d2e`
- `ntdll!EtwEventWriteTransfer` at `0x180040277`
- `ntdll!EtwEventWriteTransfer` at `0x18004035c`
- `ntdll!EtwEventWriteTransfer` at `0x180040548`
- `ntdll!EtwEventWriteTransfer` at `0x18004070c`
- `ntdll!EtwEventWriteTransfer` at `0x18004099d`
- `ntdll!EtwEventWriteTransfer` at `0x180040b71`
- `ntdll!EtwEventWriteTransfer` at `0x180040d2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800409fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800409fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040365`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800409eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040365`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800409eb`

## pseudocode

```c
__int64 __fastcall IkeBeginMMInitiator(__int64 a1, _DWORD *a2, LPCRITICAL_SECTION *a3)
{
  LPCRITICAL_SECTION *v3; // rdi
  _DWORD *v4; // r14
  __int64 v6; // r12
  LPCRITICAL_SECTION v7; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v10; // rcx
  DWORD v11; // ecx
  char *v12; // rax
  const WCHAR *v13; // rdx
  __int64 v14; // rax
  bool v15; // zf
  int v16; // eax
  __int64 inited; // rax
  LPCRITICAL_SECTION v18; // rbx
  __int64 started; // r15
  __int64 v20; // rax
  __int64 LockSemaphore_low; // rcx
  _QWORD *v22; // rdi
  __int64 *v23; // rax
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v27; // rax
  DWORD v28; // ecx
  __int64 *v29; // rax
  __int64 v30; // rcx
  DWORD v31; // ecx
  char *v32; // rax
  const WCHAR *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  _QWORD *v36; // rdi
  __int64 *v37; // rax
  __int64 v38; // rsi
  __int64 v39; // rdi
  __int64 v40; // rax
  LPCRITICAL_SECTION v41; // rax
  DWORD v42; // ecx
  __int64 *v43; // rax
  __int64 v44; // rcx
  DWORD v45; // ecx
  char *v46; // rax
  const WCHAR *v47; // rdx
  __int64 v48; // rax
  int v49; // eax
  int v50; // ecx
  int v51; // eax
  __int64 v52; // rcx
  _QWORD *v53; // rsi
  __int64 *v54; // rax
  __int64 v55; // r14
  __int64 v56; // rdi
  __int64 v57; // rsi
  __int64 v58; // rax
  int v59; // edx
  int v60; // r8d
  LPCRITICAL_SECTION v61; // rax
  DWORD v62; // ecx
  _QWORD *v63; // rax
  _DWORD *v64; // rcx
  DWORD v65; // ecx
  char *v66; // rax
  const WCHAR *v67; // rdx
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  LPCRITICAL_SECTION v72; // rax
  DWORD v73; // ecx
  _QWORD *v74; // rax
  _DWORD *v75; // rcx
  DWORD v76; // ecx
  char *v77; // rax
  const WCHAR *v78; // rdx
  __int64 v79; // rax
  int v80; // eax
  LPCRITICAL_SECTION v81; // rax
  DWORD v82; // ecx
  _QWORD *v83; // rax
  _DWORD *v84; // rcx
  DWORD v85; // ecx
  char *v86; // rax
  const WCHAR *v87; // rdx
  int v88; // eax
  unsigned int v90; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION *v91; // [rsp+48h] [rbp-B8h]
  __int64 v92; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v93; // [rsp+58h] [rbp-A8h] BYREF
  LPCRITICAL_SECTION v94; // [rsp+60h] [rbp-A0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-98h] BYREF
  __int128 v96; // [rsp+70h] [rbp-90h] BYREF
  __int128 v97; // [rsp+80h] [rbp-80h] BYREF
  __int64 v98; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v99; // [rsp+98h] [rbp-68h]
  __int128 *v100; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v101; // [rsp+A8h] [rbp-58h]
  int *v102; // [rsp+B0h] [rbp-50h]
  __int64 v103; // [rsp+B8h] [rbp-48h]
  __int64 *v104; // [rsp+C0h] [rbp-40h]
  __int64 v105; // [rsp+C8h] [rbp-38h]
  const WCHAR *v106; // [rsp+D0h] [rbp-30h]
  int v107; // [rsp+D8h] [rbp-28h]
  int v108; // [rsp+DCh] [rbp-24h]
  const char *v109; // [rsp+E0h] [rbp-20h]
  __int64 v110; // [rsp+E8h] [rbp-18h]
  __int64 *v111; // [rsp+F0h] [rbp-10h]
  __int64 v112; // [rsp+F8h] [rbp-8h]
  LPCRITICAL_SECTION *p_lpCriticalSection; // [rsp+100h] [rbp+0h]
  __int64 v114; // [rsp+108h] [rbp+8h]
  LPCRITICAL_SECTION *v115; // [rsp+110h] [rbp+10h]
  __int64 v116; // [rsp+118h] [rbp+18h]

  v91 = a3;
  v93 = a2;
  LODWORD(v94) = 0;
  lpCriticalSection = 0;
  v3 = a3;
  v4 = a2;
  v6 = -1;
  v97 = 0;
  v96 = 0;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v7 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v7 = gIkeExtGlobals;
LABEL_9:
    v10 = 0;
    goto LABEL_10;
  }
  v10 = *Value;
  v7 = gIkeExtGlobals;
LABEL_10:
  v92 = v10;
  v104 = &v92;
  v105 = 8;
  if ( !v7 )
    goto LABEL_18;
  v11 = (DWORD)v7[86].LockSemaphore;
  if ( v11 == -1 )
    goto LABEL_18;
  v12 = (char *)TlsGetValue(v11);
  v13 = (const WCHAR *)(v12 + 8);
  if ( !v12 )
    v13 = 0;
  if ( v13 )
  {
    v14 = -1;
    do
      v15 = v13[++v14] == 0;
    while ( !v15 );
    v16 = 2 * v14 + 2;
  }
  else
  {
LABEL_18:
    v13 = &LocaleName;
    v16 = 2;
  }
  v107 = v16;
  v106 = v13;
  v109 = "IkeBeginMMInitiator";
  v100 = (__int128 *)off_180173280;
  v108 = 0;
  v110 = 20;
  v98 = 0x50B000000LL;
  v99 = 1;
  v101 = *(unsigned __int16 *)off_180173280 | 0x200000000LL;
  v102 = &dword_180166EA4;
  v103 = 0x10000002DLL;
  v90 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v98, 0, 0, 5, &v100);
LABEL_20:
  inited = IkeInitMMInitiatorPhase1(a1, v4, &v94, &lpCriticalSection);
  v18 = lpCriticalSection;
  started = inited;
  if ( inited )
    goto LABEL_139;
  v20 = *(_QWORD *)(a1 + 360);
  *((_QWORD *)&v97 + 1) = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
  *(_QWORD *)&v97 = v20;
  *((_QWORD *)&v96 + 1) = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
  *(_QWORD *)&v96 = lpCriticalSection;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v98 = ActivityTransfer;
    v90 = 0;
    v99 = 0x8000000000000001uLL;
    if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    {
      v101 = 16;
      v100 = &Microsoft_Windows_Networking_ProviderId;
      v102 = (int *)&v90;
      v103 = 4;
      EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &v98, &v97, &v96, 2, &v100);
    }
    else
    {
      EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &v98, &v97, &v96, 0, 0);
    }
  }
  EnterCriticalSection(v18);
  if ( !(_DWORD)v94 || (*(_BYTE *)(a1 + 376) & 0x10) != 0 )
    LODWORD(v18[14].SpinCount) |= 0x100u;
  if ( (*(_BYTE *)(a1 + 376) & 0x10) != 0 )
  {
    LODWORD(v18[14].SpinCount) |= 0x1000u;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals
        && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
        && (v23 = (__int64 *)TlsGetValue(LockSemaphore_low), v22 = WPP_GLOBAL_Control, v23) )
      {
        v24 = *v23;
      }
      else
      {
        LODWORD(v24) = 0;
      }
      v25 = v22[2];
      TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
      WPP_SF_iS(v25, 13, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, v24, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v27 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v28 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v28 != -1 )
        {
          v29 = (__int64 *)TlsGetValue(v28);
          if ( v29 )
          {
            v30 = *v29;
            v27 = gIkeExtGlobals;
LABEL_45:
            v92 = v30;
            v104 = &v92;
            v105 = 8;
            if ( !v27 )
              goto LABEL_53;
            v31 = (DWORD)v27[86].LockSemaphore;
            if ( v31 == -1 )
              goto LABEL_53;
            v32 = (char *)TlsGetValue(v31);
            v33 = (const WCHAR *)(v32 + 8);
            if ( !v32 )
              v33 = 0;
            if ( v33 )
            {
              v34 = -1;
              do
                v15 = v33[++v34] == 0;
              while ( !v15 );
              v35 = 2 * v34 + 2;
            }
            else
            {
LABEL_53:
              v33 = &LocaleName;
              v35 = 2;
            }
            v107 = v35;
            v100 = (__int128 *)off_180173280;
            v106 = v33;
            v108 = 0;
            v98 = 0x40B000000LL;
            v99 = 0;
            v101 = *(unsigned __int16 *)off_180173280 | 0x200000000LL;
            v102 = (int *)byte_1801622E9;
            v103 = 0x100000029LL;
            v90 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(qword_180173298, &v98, 0, 0, 4, &v100);
            goto LABEL_55;
          }
          v27 = gIkeExtGlobals;
        }
      }
      v30 = 0;
      goto LABEL_45;
    }
  }
LABEL_55:
  if ( (*(_DWORD *)(a1 + 376) & 0x8000) == 0 )
    goto LABEL_83;
  v36 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( gIkeExtGlobals
      && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
      && (v37 = (__int64 *)TlsGetValue(LockSemaphore_low), v36 = WPP_GLOBAL_Control, v37) )
    {
      v38 = *v37;
    }
    else
    {
      LODWORD(v38) = 0;
    }
    v39 = v36[2];
    v40 = IkeGetTlsPeerAddr(LockSemaphore_low);
    WPP_SF_iS(v39, 14, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, v38, v40);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v41 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v42 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v42 != -1 )
      {
        v43 = (__int64 *)TlsGetValue(v42);
        if ( v43 )
        {
          v44 = *v43;
          v41 = gIkeExtGlobals;
LABEL_72:
          v92 = v44;
          v104 = &v92;
          v105 = 8;
          if ( !v41 )
            goto LABEL_80;
          v45 = (DWORD)v41[86].LockSemaphore;
          if ( v45 == -1 )
            goto LABEL_80;
          v46 = (char *)TlsGetValue(v45);
          v47 = (const WCHAR *)(v46 + 8);
          if ( !v46 )
            v47 = 0;
          if ( v47 )
          {
            v48 = -1;
            do
              v15 = v47[++v48] == 0;
            while ( !v15 );
            v49 = 2 * v48 + 2;
          }
          else
          {
LABEL_80:
            v47 = &LocaleName;
            v49 = 2;
          }
          v107 = v49;
          v100 = (__int128 *)off_180173280;
          v106 = v47;
          v108 = 0;
          v98 = 0x40B000000LL;
          v99 = 0;
          v101 = *(unsigned __int16 *)off_180173280 | 0x200000000LL;
          v102 = &dword_1801622B4;
          v103 = 0x100000029LL;
          v90 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v98, 0, 0, 4, &v100);
          goto LABEL_82;
        }
        v41 = gIkeExtGlobals;
      }
    }
    v44 = 0;
    goto LABEL_72;
  }
LABEL_82:
  HIDWORD(v18[14].SpinCount) |= 8u;
LABEL_83:
  v50 = *(_DWORD *)(a1 + 556);
  if ( v50 )
  {
    v51 = (int)v18[14].LockSemaphore;
    if ( v51 == 2 )
    {
      *((_DWORD *)v18[27].LockSemaphore + 152) = v50;
    }
    else
    {
      if ( v51 != 1 )
        __fastfail(5u);
      *((_DWORD *)v18[27].OwningThread + 97) = v50;
    }
  }
  started = IkeNotifyNLB(v18, 0, 0, 0);
  if ( started )
  {
    v3 = v91;
    goto LABEL_139;
  }
  v53 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( gIkeExtGlobals
      && (v52 = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)v52 != -1)
      && (v54 = (__int64 *)TlsGetValue(v52), v53 = WPP_GLOBAL_Control, v54) )
    {
      v55 = *v54;
    }
    else
    {
      LODWORD(v55) = 0;
    }
    v56 = *(_QWORD *)(a1 + 360);
    v57 = v53[2];
    v58 = IkeGetTlsPeerAddr(v52);
    WPP_SF_iSqIq(v57, v59, v60, v55, v58, a1, v56, (__int64)v18);
    v4 = v93;
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v61 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v62 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v62 != -1 )
      {
        v63 = TlsGetValue(v62);
        if ( v63 )
        {
          v64 = (_DWORD *)*v63;
          v61 = gIkeExtGlobals;
LABEL_106:
          v93 = v64;
          v104 = (__int64 *)&v93;
          v105 = 8;
          if ( !v61 )
            goto LABEL_114;
          v65 = (DWORD)v61[86].LockSemaphore;
          if ( v65 == -1 )
            goto LABEL_114;
          v66 = (char *)TlsGetValue(v65);
          v67 = (const WCHAR *)(v66 + 8);
          if ( !v66 )
            v67 = 0;
          if ( v67 )
          {
            v68 = -1;
            do
              v15 = v67[++v68] == 0;
            while ( !v15 );
            v69 = 2 * v68 + 2;
          }
          else
          {
LABEL_114:
            v67 = &LocaleName;
            v69 = 2;
          }
          v107 = v69;
          v106 = v67;
          v109 = "IkeBeginMMInitiatorSetting prime acquire for MM SA";
          v108 = 0;
          v111 = &v92;
          lpCriticalSection = *(LPCRITICAL_SECTION *)(a1 + 360);
          v110 = 51;
          p_lpCriticalSection = &lpCriticalSection;
          v115 = &v94;
          v100 = (__int128 *)off_180173280;
          v92 = a1;
          v112 = 8;
          v114 = 8;
          v94 = v18;
          v116 = 8;
          v98 = 0x40B000000LL;
          v99 = 0;
          v101 = *(unsigned __int16 *)off_180173280 | 0x200000000LL;
          v102 = (int *)&unk_180162368;
          v103 = 0x100000062LL;
          v90 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v98, 0, 0, 8, &v100);
          goto LABEL_116;
        }
        v61 = gIkeExtGlobals;
      }
    }
    v64 = 0;
    goto LABEL_106;
  }
LABEL_116:
  *(_QWORD *)&v18[25].LockCount = a1;
  *v4 = 1;
  if ( LODWORD(v18[14].LockSemaphore) == 1 && (unsigned int)IkeIsImpersonationActiveInitiator(v18, 0) )
    IkeUpdateDriverStatus(v71, v70, *(_QWORD *)&v18[25].LockCount + 360LL, v18);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v18 + 48));
  ++LODWORD(v18[4].LockSemaphore);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v18 + 48));
  v3 = v91;
  if ( !v91 )
  {
    if ( (unsigned int)dword_180173278 <= 4 )
    {
LABEL_137:
      started = IkeStartMMNegotiation(a1, v18);
      goto LABEL_139;
    }
    v72 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v73 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v73 != -1 )
      {
        v74 = TlsGetValue(v73);
        if ( v74 )
        {
          v75 = (_DWORD *)*v74;
          v72 = gIkeExtGlobals;
LABEL_127:
          v93 = v75;
          v104 = (__int64 *)&v93;
          v105 = 8;
          if ( !v72 )
            goto LABEL_135;
          v76 = (DWORD)v72[86].LockSemaphore;
          if ( v76 == -1 )
            goto LABEL_135;
          v77 = (char *)TlsGetValue(v76);
          v78 = (const WCHAR *)(v77 + 8);
          if ( !v77 )
            v78 = 0;
          if ( v78 )
          {
            v79 = -1;
            do
              v15 = v78[++v79] == 0;
            while ( !v15 );
            v80 = 2 * v79 + 2;
          }
          else
          {
LABEL_135:
            v78 = &LocaleName;
            v80 = 2;
          }
          v107 = v80;
          v106 = v78;
          v109 = "Staring MM Negotiation";
          v108 = 0;
          v111 = &v92;
          v100 = (__int128 *)off_180173280;
          v110 = 23;
          v92 = (__int64)v18;
          v112 = 8;
          v98 = 0x40B000000LL;
          v99 = 0;
          v101 = *(unsigned __int16 *)off_180173280 | 0x200000000LL;
          v102 = (int *)&word_18016231E;
          v103 = 0x10000003ELL;
          v90 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v98, 0, 0, 6, &v100);
          goto LABEL_137;
        }
        v72 = gIkeExtGlobals;
      }
    }
    v75 = 0;
    goto LABEL_127;
  }
LABEL_139:
  if ( v18 )
  {
    if ( started )
      IkeCleanupMMNegotiation(v18, started, 0);
    if ( !v3 || started )
      IkeFinishMMSAProcessing((char *)v18);
    else
      *v3 = v18;
  }
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v81 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v82 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v82 != -1 )
      {
        v83 = TlsGetValue(v82);
        if ( v83 )
        {
          v84 = (_DWORD *)*v83;
          v81 = gIkeExtGlobals;
LABEL_155:
          v93 = v84;
          v104 = (__int64 *)&v93;
          v105 = 8;
          if ( !v81 )
            goto LABEL_162;
          v85 = (DWORD)v81[86].LockSemaphore;
          if ( v85 == -1 )
            goto LABEL_162;
          v86 = (char *)TlsGetValue(v85);
          v87 = (const WCHAR *)(v86 + 8);
          if ( !v86 )
            v87 = 0;
          if ( v87 )
          {
            do
              v15 = v87[++v6] == 0;
            while ( !v15 );
            v88 = 2 * v6 + 2;
          }
          else
          {
LABEL_162:
            v87 = &LocaleName;
            v88 = 2;
          }
          v107 = v88;
          v106 = v87;
          v109 = "IkeBeginMMInitiator";
          v100 = (__int128 *)off_180173280;
          v108 = 0;
          v110 = 20;
          v98 = 0x50B000000LL;
          v99 = 1;
          v101 = *(unsigned __int16 *)off_180173280 | 0x200000000LL;
          v102 = (int *)byte_180166E6B;
          v103 = 0x10000002DLL;
          v90 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v98, 0, 0, 5, &v100);
          return IkeReturnError(started, "IkeBeginMMInitiator");
        }
        v81 = gIkeExtGlobals;
      }
    }
    v84 = 0;
    goto LABEL_155;
  }
  return IkeReturnError(started, "IkeBeginMMInitiator");
}

```

## disassembly

```asm
0x1800400a0  mov     [rsp-8+arg_18], rbx
0x1800400a5  push    rbp
0x1800400a6  push    rsi
0x1800400a7  push    rdi
0x1800400a8  push    r12
0x1800400aa  push    r13
0x1800400ac  push    r14
0x1800400ae  push    r15
0x1800400b0  lea     rbp, [rsp-30h]
0x1800400b5  sub     rsp, 130h
0x1800400bc  mov     rax, cs:__security_cookie
0x1800400c3  xor     rax, rsp
0x1800400c6  mov     [rbp+60h+var_40], rax
0x1800400ca  mov     eax, cs:dword_180173278
0x1800400d0  lea     rsi, _TraceLoggingMetadataEnd
0x1800400d7  xor     ebx, ebx
0x1800400d9  mov     [rsp+160h+var_118], r8
0x1800400de  mov     [rsp+160h+var_108], rdx
0x1800400e3  xorps   xmm0, xmm0
0x1800400e6  mov     dword ptr [rsp+160h+var_100], ebx
0x1800400ea  xorps   xmm1, xmm1
0x1800400ed  mov     [rsp+160h+lpCriticalSection], rbx
0x1800400f2  mov     rdi, r8
0x1800400f5  lea     r15, _TraceLoggingMetadata
0x1800400fc  mov     r14, rdx
0x1800400ff  mov     r13, rcx
0x180040102  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180040109  movups  [rbp+60h+var_E0], xmm0
0x18004010d  movups  [rsp+160h+var_F0], xmm1
0x180040112  cmp     eax, 5
0x180040115  jbe     loc_18004027D
0x18004011b  mov     rcx, cs:qword_180173290
0x180040122  mov     rax, cs:qword_180173288
0x180040129  test    al, 1
0x18004012b  jz      loc_18004027D
0x180040131  mov     rax, rcx
0x180040134  and     eax, 1
0x180040137  cmp     rax, rcx
0x18004013a  jnz     loc_18004027D
0x180040140  mov     rax, cs:gIkeExtGlobals
0x180040147  test    rax, rax
0x18004014a  jz      short loc_180040175
0x18004014c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180040152  cmp     ecx, 0FFFFFFFFh
0x180040155  jz      short loc_180040175
0x180040157  call    cs:__imp_TlsGetValue
0x18004015d  test    rax, rax
0x180040160  jz      short loc_18004016E
0x180040162  mov     rcx, [rax]
0x180040165  mov     rax, cs:gIkeExtGlobals
0x18004016c  jmp     short loc_180040178
0x18004016e  mov     rax, cs:gIkeExtGlobals
0x180040175  mov     rcx, rbx
0x180040178  mov     [rsp+160h+var_110], rcx
0x18004017d  lea     rcx, [rsp+160h+var_110]
0x180040182  mov     [rbp+60h+var_A0], rcx
0x180040186  mov     [rbp+60h+var_98], 8
0x18004018e  test    rax, rax
0x180040191  jz      short loc_1800401D4
0x180040193  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180040199  cmp     ecx, 0FFFFFFFFh
0x18004019c  jz      short loc_1800401D4
0x18004019e  call    cs:__imp_TlsGetValue
0x1800401a4  test    rax, rax
0x1800401a7  lea     rdx, [rax+8]
0x1800401ab  cmovz   rdx, rbx
0x1800401af  test    rdx, rdx
0x1800401b2  jz      short loc_1800401D4
0x1800401b4  mov     rax, r12
0x1800401b7  nop     word ptr [rax+rax+00000000h]
0x1800401c0  cmp     [rdx+rax*2+2], bx
0x1800401c5  lea     rax, [rax+1]
0x1800401c9  jnz     short loc_1800401C0
0x1800401cb  lea     eax, ds:2[rax*2]
0x1800401d2  jmp     short loc_1800401E0
0x1800401d4  lea     rdx, LocaleName
0x1800401db  mov     eax, 2
0x1800401e0  mov     [rbp+60h+var_88], eax
0x1800401e3  xor     r9d, r9d
0x1800401e6  mov     [rbp+60h+var_90], rdx
0x1800401ea  lea     rax, aIkebeginmminit; "IkeBeginMMInitiator"
0x1800401f1  mov     [rbp+60h+var_80], rax
0x1800401f5  lea     rdx, [rbp+60h+var_D0]
0x1800401f9  movzx   eax, cs:word_180166E9A
0x180040200  xor     r8d, r8d
0x180040203  mov     dword ptr [rbp+60h+var_D0+4], eax
0x180040206  mov     rax, cs:off_180173280
0x18004020d  mov     [rbp+60h+var_C0], rax
0x180040211  mov     [rbp+60h+var_84], ebx
0x180040214  mov     [rbp+60h+var_78], 14h
0x18004021c  mov     dword ptr [rbp+60h+var_D0], 0B000000h
0x180040223  mov     [rbp+60h+var_C8], 1
0x18004022b  movzx   eax, word ptr [rax]
0x18004022e  mov     dword ptr [rbp+60h+var_B8], eax
0x180040231  lea     rax, dword_180166EA4
0x180040238  mov     [rbp+60h+var_B0], rax
0x18004023c  mov     rax, rsi
0x18004023f  sub     eax, r15d
0x180040242  mov     dword ptr [rbp+60h+var_B8+4], 2
0x180040249  mov     dword ptr [rbp+60h+var_A8], 2Dh ; '-'
0x180040250  mov     dword ptr [rbp+60h+var_A8+4], 1
0x180040257  mov     [rsp+160h+var_120], eax
0x18004025b  mov     eax, [rsp+160h+var_120]
0x18004025f  mov     rcx, cs:qword_180173298
0x180040266  lea     rax, [rbp+60h+var_C0]
0x18004026a  mov     [rsp+160h+var_138], rax
0x18004026f  mov     dword ptr [rsp+160h+var_140], 5
0x180040277  call    cs:__imp_EtwEventWriteTransfer
0x18004027d  lea     r9, [rsp+160h+lpCriticalSection]
0x180040282  mov     rdx, r14
0x180040285  lea     r8, [rsp+160h+var_100]
0x18004028a  mov     rcx, r13
0x18004028d  call    IkeInitMMInitiatorPhase1
0x180040292  mov     rbx, [rsp+160h+lpCriticalSection]
0x180040297  mov     r15, rax
0x18004029a  test    rax, rax
0x18004029d  jnz     loc_180040B93
0x1800402a3  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x1800402aa  mov     rax, [r13+168h]
0x1800402b1  movups  [rbp+60h+var_E0], xmm0
0x1800402b5  mov     qword ptr [rbp+60h+var_E0], rax
0x1800402b9  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800402bf  movups  [rsp+160h+var_F0], xmm0
0x1800402c4  mov     qword ptr [rsp+160h+var_F0], rbx
0x1800402c9  test    eax, eax
0x1800402cb  jz      loc_180040362
0x1800402d1  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800402d7  test    eax, eax
0x1800402d9  jz      loc_180040362
0x1800402df  mov     rax, cs:ActivityTransfer
0x1800402e6  lea     r9, [rsp+160h+var_F0]
0x1800402eb  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle
0x1800402f2  lea     r8, [rbp+60h+var_E0]
0x1800402f6  mov     [rbp+60h+var_D0], rax
0x1800402fa  lea     rdx, [rbp+60h+var_D0]
0x1800402fe  mov     rax, 8000000000000001h
0x180040308  mov     [rsp+160h+var_120], r15d
0x18004030d  mov     [rbp+60h+var_C8], rax
0x180040311  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180040317  test    eax, eax
0x180040319  jz      short loc_180040352
0x18004031b  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180040322  mov     [rbp+60h+var_B8], 10h
0x18004032a  mov     [rbp+60h+var_C0], rax
0x18004032e  lea     rax, [rsp+160h+var_120]
0x180040333  mov     [rbp+60h+var_B0], rax
0x180040337  lea     rax, [rbp+60h+var_C0]
0x18004033b  mov     [rsp+160h+var_138], rax
0x180040340  mov     dword ptr [rsp+160h+var_140], 2
0x180040348  mov     [rbp+60h+var_A8], 4
0x180040350  jmp     short loc_18004035C
0x180040352  mov     [rsp+160h+var_138], r15
0x180040357  mov     dword ptr [rsp+160h+var_140], r15d
0x18004035c  call    cs:__imp_EtwEventWriteTransfer
0x180040362  mov     rcx, rbx; lpCriticalSection
0x180040365  call    cs:__imp_EnterCriticalSection
0x18004036b  cmp     dword ptr [rsp+160h+var_100], 0
0x180040370  jz      short loc_18004037C
0x180040372  test    byte ptr [r13+178h], 10h
0x18004037a  jz      short loc_180040386
0x18004037c  or      dword ptr [rbx+250h], 100h
0x180040386  test    byte ptr [r13+178h], 10h
0x18004038e  lea     rax, WPP_GLOBAL_Control
0x180040395  jz      loc_180040555
0x18004039b  or      dword ptr [rbx+250h], 1000h
0x1800403a5  mov     rdi, cs:WPP_GLOBAL_Control
0x1800403ac  cmp     rdi, rax
0x1800403af  jz      short loc_18004041A
0x1800403b1  cmp     byte ptr [rdi+19h], 4
0x1800403b5  jb      short loc_18004041A
0x1800403b7  test    byte ptr [rdi+1Ch], 10h
0x1800403bb  jz      short loc_18004041A
0x1800403bd  mov     rax, cs:gIkeExtGlobals
0x1800403c4  test    rax, rax
0x1800403c7  jz      short loc_1800403EB
0x1800403c9  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800403cf  cmp     ecx, 0FFFFFFFFh
0x1800403d2  jz      short loc_1800403EB
0x1800403d4  call    cs:__imp_TlsGetValue
0x1800403da  mov     rdi, cs:WPP_GLOBAL_Control
0x1800403e1  test    rax, rax
0x1800403e4  jz      short loc_1800403EB
0x1800403e6  mov     rsi, [rax]
0x1800403e9  jmp     short loc_1800403EE
0x1800403eb  mov     rsi, r15
0x1800403ee  mov     rdi, [rdi+10h]
0x1800403f2  call    IkeGetTlsPeerAddr
0x1800403f7  mov     edx, 0Dh
0x1800403fc  mov     [rsp+160h+var_140], rax
0x180040401  mov     r9, rsi
0x180040404  lea     r8, WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids
0x18004040b  mov     rcx, rdi
0x18004040e  call    WPP_SF_iS
0x180040413  lea     rsi, _TraceLoggingMetadataEnd
0x18004041a  mov     eax, cs:dword_180173278
0x180040420  cmp     eax, 4
0x180040423  jbe     loc_18004054E
0x180040429  mov     rax, cs:gIkeExtGlobals
0x180040430  test    rax, rax
0x180040433  jz      short loc_18004045E
0x180040435  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004043b  cmp     ecx, 0FFFFFFFFh
0x18004043e  jz      short loc_18004045E
0x180040440  call    cs:__imp_TlsGetValue
0x180040446  test    rax, rax
0x180040449  jz      short loc_180040457
0x18004044b  mov     rcx, [rax]
0x18004044e  mov     rax, cs:gIkeExtGlobals
0x180040455  jmp     short loc_180040461
0x180040457  mov     rax, cs:gIkeExtGlobals
0x18004045e  mov     rcx, r15
0x180040461  mov     [rsp+160h+var_110], rcx
0x180040466  lea     rcx, [rsp+160h+var_110]
0x18004046b  mov     [rbp+60h+var_A0], rcx
0x18004046f  mov     [rbp+60h+var_98], 8
0x180040477  test    rax, rax
0x18004047a  jz      short loc_1800404B5
0x18004047c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180040482  cmp     ecx, 0FFFFFFFFh
0x180040485  jz      short loc_1800404B5
0x180040487  call    cs:__imp_TlsGetValue
0x18004048d  test    rax, rax
0x180040490  lea     rdx, [rax+8]
0x180040494  cmovz   rdx, r15
0x180040498  test    rdx, rdx
0x18004049b  jz      short loc_1800404B5
0x18004049d  mov     rax, r12
0x1800404a0  cmp     word ptr [rdx+rax*2+2], 0
0x1800404a6  lea     rax, [rax+1]
0x1800404aa  jnz     short loc_1800404A0
0x1800404ac  lea     eax, ds:2[rax*2]
0x1800404b3  jmp     short loc_1800404C1
0x1800404b5  lea     rdx, LocaleName
0x1800404bc  mov     eax, 2
0x1800404c1  mov     [rbp+60h+var_88], eax
0x1800404c4  lea     rcx, _TraceLoggingMetadata
0x1800404cb  movzx   eax, cs:word_1801622DF
0x1800404d2  xor     r9d, r9d
0x1800404d5  mov     dword ptr [rbp+60h+var_D0+4], eax
0x1800404d8  xor     r8d, r8d
0x1800404db  mov     rax, cs:off_180173280
0x1800404e2  mov     [rbp+60h+var_C0], rax
0x1800404e6  mov     [rbp+60h+var_90], rdx
0x1800404ea  lea     rdx, [rbp+60h+var_D0]
0x1800404ee  mov     [rbp+60h+var_84], r15d
0x1800404f2  mov     dword ptr [rbp+60h+var_D0], 0B000000h
0x1800404f9  mov     [rbp+60h+var_C8], r15
0x1800404fd  movzx   eax, word ptr [rax]
0x180040500  mov     dword ptr [rbp+60h+var_B8], eax
0x180040503  lea     rax, byte_1801622E9
0x18004050a  mov     [rbp+60h+var_B0], rax
0x18004050e  mov     rax, rsi
0x180040511  sub     eax, ecx
0x180040513  mov     dword ptr [rbp+60h+var_B8+4], 2
0x18004051a  mov     dword ptr [rbp+60h+var_A8], 29h ; ')'
0x180040521  mov     dword ptr [rbp+60h+var_A8+4], 1
0x180040528  mov     [rsp+160h+var_120], eax
0x18004052c  mov     eax, [rsp+160h+var_120]
0x180040530  mov     rcx, cs:qword_180173298
0x180040537  lea     rax, [rbp+60h+var_C0]
0x18004053b  mov     [rsp+160h+var_138], rax
0x180040540  mov     dword ptr [rsp+160h+var_140], 4
0x180040548  call    cs:__imp_EtwEventWriteTransfer
0x18004054e  lea     rax, WPP_GLOBAL_Control
0x180040555  test    dword ptr [r13+178h], 8000h
0x180040560  jz      loc_180040719
0x180040566  mov     rdi, cs:WPP_GLOBAL_Control
0x18004056d  cmp     rdi, rax
0x180040570  jz      short loc_1800405D4
0x180040572  cmp     byte ptr [rdi+19h], 4
0x180040576  jb      short loc_1800405D4
0x180040578  test    byte ptr [rdi+1Ch], 10h
0x18004057c  jz      short loc_1800405D4
0x18004057e  mov     rax, cs:gIkeExtGlobals
0x180040585  test    rax, rax
0x180040588  jz      short loc_1800405AC
0x18004058a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180040590  cmp     ecx, 0FFFFFFFFh
0x180040593  jz      short loc_1800405AC
0x180040595  call    cs:__imp_TlsGetValue
0x18004059b  mov     rdi, cs:WPP_GLOBAL_Control
0x1800405a2  test    rax, rax
0x1800405a5  jz      short loc_1800405AC
0x1800405a7  mov     rsi, [rax]
0x1800405aa  jmp     short loc_1800405AF
0x1800405ac  mov     rsi, r15
0x1800405af  mov     rdi, [rdi+10h]
0x1800405b3  call    IkeGetTlsPeerAddr
0x1800405b8  mov     edx, 0Eh
0x1800405bd  mov     [rsp+160h+var_140], rax
0x1800405c2  mov     r9, rsi
0x1800405c5  lea     r8, WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids
0x1800405cc  mov     rcx, rdi
0x1800405cf  call    WPP_SF_iS
0x1800405d4  mov     eax, cs:dword_180173278
0x1800405da  cmp     eax, 4
0x1800405dd  jbe     loc_180040712
0x1800405e3  mov     rax, cs:gIkeExtGlobals
0x1800405ea  test    rax, rax
0x1800405ed  jz      short loc_180040618
  ... truncated ...
```
