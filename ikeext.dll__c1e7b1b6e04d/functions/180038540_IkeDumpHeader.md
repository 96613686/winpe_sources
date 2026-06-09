# IkeDumpHeader

- ea: `0x180038540`
- end: `0x180038f01`
- name: `IkeDumpHeader`
- size: `2497`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014b60`
- `0x18002d940`
- `0x1800c761c`

## callees

- `0x180003cf0`
- `0x180018b20`
- `0x180019bd0`
- `0x180024970`
- `0x180038540`
- `0x18004882c`
- `0x180050850`
- `0x1800baec8`
- `0x1800baf50`
- `0x1800bb128`
- `0x180110d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800385e6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003861b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003881d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038861`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038a8a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038ac2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038b62`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038baa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038cb3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038cf8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800385e6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003861b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003881d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038861`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038a8a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038ac2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038b62`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038baa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038cb3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038cf8`
- `ntdll!EtwEventWriteTransfer` at `0x180038969`
- `ntdll!EtwEventWriteTransfer` at `0x180038dd5`
- `ntdll!EtwEventWriteTransfer` at `0x180038ed0`
- `ntdll!EtwEventWriteTransfer` at `0x180038969`
- `ntdll!EtwEventWriteTransfer` at `0x180038dd5`
- `ntdll!EtwEventWriteTransfer` at `0x180038ed0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180038a20`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180038a20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800389e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038a3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800389e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038a3b`
- `WS2_32!__imp_htonl` at `0x180038580`
- `WS2_32!__imp_htonl` at `0x18003858d`
- `WS2_32!__imp_htonl` at `0x180038580`
- `WS2_32!__imp_htonl` at `0x18003858d`

## pseudocode

```c
double __fastcall IkeDumpHeader(__int64 a1)
{
  char *v1; // r13
  LPCRITICAL_SECTION v2; // rdx
  DWORD LockSemaphore; // ecx
  LPVOID Value; // rax
  LPVOID v5; // rcx
  __int64 v6; // r8
  DWORD v7; // ecx
  LPVOID *v8; // rax
  char v9; // al
  char v10; // cl
  char v11; // r8
  char v12; // r10
  char v13; // r11
  char v14; // bl
  char v15; // di
  char v16; // si
  char v17; // r14
  char v18; // r15
  char v19; // r12
  __int64 v20; // r14
  void *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  LPCRITICAL_SECTION v25; // rax
  DWORD v26; // ecx
  __int64 *v27; // rax
  __int64 v28; // rcx
  DWORD v29; // ecx
  char *v30; // rax
  const WCHAR *v31; // rdx
  __int64 v32; // rax
  bool v33; // zf
  int v34; // eax
  __int16 *v35; // rcx
  __int64 v36; // rax
  unsigned int v37; // eax
  double result; // xmm0_8
  int IsEnabledDeviceUsageNoInline; // eax
  BOOL v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  _QWORD *v44; // rsi
  LPCRITICAL_SECTION v45; // rdx
  DWORD v46; // ecx
  LPVOID v47; // rax
  LPVOID v48; // rcx
  __int64 v49; // r12
  DWORD v50; // ecx
  __int64 *v51; // rax
  __int64 v52; // r15
  unsigned __int8 v53; // bl
  __int64 v54; // rsi
  __int64 HdrFlagsString; // rdi
  __int64 ExchTypeString; // rax
  __int16 *v57; // rbx
  u_long v58; // edi
  int v59; // edx
  int v60; // r8d
  LPCRITICAL_SECTION v61; // rax
  DWORD v62; // ecx
  __int64 *v63; // rax
  __int64 v64; // rcx
  DWORD v65; // ecx
  char *v66; // rax
  const WCHAR *v67; // rdx
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // rcx
  __int16 *v71; // rax
  __int64 v72; // rcx
  int v73; // ecx
  __int64 v74; // rax
  int v75; // eax
  char v76; // bl
  LPCRITICAL_SECTION v77; // rax
  DWORD v78; // ecx
  void **v79; // rax
  void *v80; // rcx
  DWORD v81; // ecx
  char *v82; // rax
  const WCHAR *v83; // rdx
  __int64 v84; // rax
  int v85; // eax
  const char *v86; // rax
  int v87; // [rsp+38h] [rbp-100h]
  int v88; // [rsp+40h] [rbp-F8h]
  int v89; // [rsp+48h] [rbp-F0h]
  __int64 v90; // [rsp+48h] [rbp-F0h]
  char v91; // [rsp+50h] [rbp-E8h]
  int v92; // [rsp+50h] [rbp-E8h]
  int v93; // [rsp+58h] [rbp-E0h]
  int v94; // [rsp+60h] [rbp-D8h]
  int v95; // [rsp+68h] [rbp-D0h]
  int v96; // [rsp+70h] [rbp-C8h]
  int v97; // [rsp+78h] [rbp-C0h]
  int v98; // [rsp+80h] [rbp-B8h]
  int v99; // [rsp+88h] [rbp-B0h]
  int v100; // [rsp+90h] [rbp-A8h]
  u_long v101; // [rsp+B8h] [rbp-80h]
  u_long v102; // [rsp+BCh] [rbp-7Ch]
  unsigned int v103; // [rsp+C0h] [rbp-78h] BYREF
  char *v104; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v105; // [rsp+D0h] [rbp-68h] BYREF
  LPVOID lpMem; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v107; // [rsp+E0h] [rbp-58h]
  __int64 v108[2]; // [rsp+E8h] [rbp-50h] BYREF
  char *v109; // [rsp+F8h] [rbp-40h] BYREF
  int v110; // [rsp+100h] [rbp-38h]
  int v111; // [rsp+104h] [rbp-34h]
  int *v112; // [rsp+108h] [rbp-30h]
  int v113; // [rsp+110h] [rbp-28h]
  int v114; // [rsp+114h] [rbp-24h]
  LPVOID *p_lpMem; // [rsp+118h] [rbp-20h]
  __int64 v116; // [rsp+120h] [rbp-18h]
  const WCHAR *v117; // [rsp+128h] [rbp-10h]
  int v118; // [rsp+130h] [rbp-8h]
  int v119; // [rsp+134h] [rbp-4h]
  const char *v120; // [rsp+138h] [rbp+0h]
  __int64 v121; // [rsp+140h] [rbp+8h]
  char *v122; // [rsp+148h] [rbp+10h] BYREF
  int v123; // [rsp+150h] [rbp+18h]
  int v124; // [rsp+154h] [rbp+1Ch]
  __int16 *v125; // [rsp+158h] [rbp+20h]
  int v126; // [rsp+160h] [rbp+28h]
  int v127; // [rsp+164h] [rbp+2Ch]
  __int64 *v128; // [rsp+168h] [rbp+30h]
  __int64 v129; // [rsp+170h] [rbp+38h]
  const WCHAR *v130; // [rsp+178h] [rbp+40h]
  int v131; // [rsp+180h] [rbp+48h]
  int v132; // [rsp+184h] [rbp+4Ch]
  __int16 *v133; // [rsp+188h] [rbp+50h]
  int v134; // [rsp+190h] [rbp+58h]
  int v135; // [rsp+194h] [rbp+5Ch]
  unsigned int *v136; // [rsp+198h] [rbp+60h]
  __int64 v137; // [rsp+1A0h] [rbp+68h]
  __int16 *v138; // [rsp+1A8h] [rbp+70h]
  int v139; // [rsp+1B0h] [rbp+78h]
  int v140; // [rsp+1B4h] [rbp+7Ch]
  const char *v141; // [rsp+1B8h] [rbp+80h]
  int v142; // [rsp+1C0h] [rbp+88h]
  int v143; // [rsp+1C4h] [rbp+8Ch]
  char **v144; // [rsp+1C8h] [rbp+90h]
  __int64 v145; // [rsp+1D0h] [rbp+98h]

  v1 = (char *)a1;
  v104 = (char *)a1;
  v101 = htonl(*(_DWORD *)(a1 + 24));
  v102 = htonl(*((_DWORD *)v1 + 5));
  v108[0] = IkeGetNextPayloadString((unsigned __int8)v1[16]);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v2 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
    {
      v5 = 0;
    }
    else
    {
      Value = TlsGetValue(LockSemaphore);
      v2 = gIkeExtGlobals;
      v5 = Value;
    }
    v6 = (__int64)v5 + 8;
    if ( !v5 )
      v6 = 0;
    v105 = v6;
    if ( v2 && (v7 = (DWORD)v2[86].LockSemaphore, v7 != -1) && (v8 = (LPVOID *)TlsGetValue(v7)) != 0 )
      lpMem = *v8;
    else
      lpMem = 0;
    v9 = v1[15];
    v10 = v1[14];
    v11 = v1[13];
    v12 = v1[12];
    v13 = v1[11];
    v14 = v1[10];
    v15 = v1[9];
    v16 = v1[8];
    v17 = v1[7];
    v18 = v1[6];
    v19 = v1[5];
    v91 = v1[4];
    v1 = v104;
    WPP_SF_iSDDDDDDDDDDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_b4c0bdae5de2357ade4f23a969f1f973_Traceguids,
      (_DWORD)lpMem,
      v105,
      *v104,
      v104[1],
      v104[2],
      v104[3],
      v91,
      v19,
      v18,
      v17,
      v16,
      v15,
      v14,
      v13,
      v12,
      v11,
      v10,
      v9);
  }
  v20 = -1;
  if ( dword_1801732B0 )
  {
    lpMem = 0;
    if ( !WfpMemAlloc(0x400u, 0, &lpMem) )
    {
      v100 = (unsigned __int8)v1[15];
      v99 = (unsigned __int8)v1[14];
      v98 = (unsigned __int8)v1[13];
      v97 = (unsigned __int8)v1[12];
      v96 = (unsigned __int8)v1[11];
      v95 = (unsigned __int8)v1[10];
      v21 = lpMem;
      v94 = (unsigned __int8)v1[9];
      v93 = (unsigned __int8)v1[8];
      v92 = (unsigned __int8)v1[7];
      v89 = (unsigned __int8)v1[6];
      v88 = (unsigned __int8)v1[5];
      v87 = (unsigned __int8)v1[4];
      v1 = v104;
      IkeFormatString(
        lpMem,
        "iCookie %02x%02x%02x%02x%02x%02x%02x%02x rCookie %02x%02x%02x%02x%02x%02x%02x%02x",
        (unsigned __int8)*v104,
        (unsigned __int8)v104[1],
        (unsigned __int8)v104[2],
        (unsigned __int8)v104[3],
        v87,
        v88,
        v89,
        v92,
        v93,
        v94,
        v95,
        v96,
        v97,
        v98,
        v99,
        v100);
      if ( (unsigned int)dword_180173278 <= 4 )
      {
LABEL_40:
        if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
        if ( IsEnabledDeviceUsageNoInline )
        {
          v20 = -1;
          if ( gWfpTrackHeapAllocs && v21 && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
          {
            if ( !gMisalignedHeapTelemFired )
            {
              if ( gWfpNumHeapAllocs <= 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v23, v22, v24);
              gMisalignedHeapTelemFired = 1;
            }
            _InterlockedIncrement(&gWfpNumHeapAllocs);
          }
          else
          {
            v40 = HeapFree(gWfpHeap, 0, v21);
            if ( !gHeapFreeFailedFired && !v40 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v42, v41, v43);
              gHeapFreeFailedFired = 1;
            }
          }
        }
        else
        {
          if ( gWfpTrackHeapBytes && v21 )
            _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v21));
          HeapFree(gWfpHeap, 0, v21);
          v20 = -1;
        }
        goto LABEL_59;
      }
      v25 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v26 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v26 != -1 )
        {
          v27 = (__int64 *)TlsGetValue(v26);
          if ( v27 )
          {
            v28 = *v27;
            v25 = gIkeExtGlobals;
LABEL_25:
            v105 = v28;
            p_lpMem = (LPVOID *)&v105;
            v116 = 8;
            if ( !v25 )
              goto LABEL_33;
            v29 = (DWORD)v25[86].LockSemaphore;
            if ( v29 == -1 )
              goto LABEL_33;
            v30 = (char *)TlsGetValue(v29);
            v31 = (const WCHAR *)(v30 + 8);
            if ( !v30 )
              v31 = 0;
            if ( v31 )
            {
              v32 = -1;
              do
                v33 = v31[++v32] == 0;
              while ( !v33 );
              v34 = 2 * v32 + 2;
            }
            else
            {
LABEL_33:
              v31 = &LocaleName;
              v34 = 2;
            }
            v117 = v31;
            v118 = v34;
            v119 = 0;
            if ( v21 )
            {
              v35 = (__int16 *)v21;
              v36 = -1;
              do
                ++v36;
              while ( *((_BYTE *)v21 + v36) );
              v37 = v36 + 1;
            }
            else
            {
              v35 = word_180122432;
              v37 = 1;
            }
            v121 = v37;
            v109 = off_180173280;
            v120 = (const char *)v35;
            lpMem = (LPVOID)0x40B000000LL;
            v107 = 0;
            v110 = *(unsigned __int16 *)off_180173280;
            v112 = (int *)byte_18015A7F3;
            v111 = 2;
            v113 = 49;
            v114 = 1;
            v103 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            result = EtwEventWriteTransfer(qword_180173298, &lpMem, 0, 0, 5, &v109);
            goto LABEL_40;
          }
          v25 = gIkeExtGlobals;
        }
      }
      v28 = 0;
      goto LABEL_25;
    }
  }
LABEL_59:
  v44 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
  {
    v57 = (__int16 *)v108[0];
    v58 = v101;
  }
  else
  {
    v45 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v46 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v46 == -1) )
    {
      v48 = 0;
    }
    else
    {
      v47 = TlsGetValue(v46);
      v44 = WPP_GLOBAL_Control;
      v48 = v47;
      v45 = gIkeExtGlobals;
    }
    v49 = (__int64)v48 + 8;
    if ( !v48 )
      v49 = 0;
    if ( v45
      && (v50 = (DWORD)v45[86].LockSemaphore, v50 != -1)
      && (v51 = (__int64 *)TlsGetValue(v50), v44 = WPP_GLOBAL_Control, v51) )
    {
      v52 = *v51;
    }
    else
    {
      LODWORD(v52) = 0;
    }
    v53 = v1[18];
    v54 = v44[2];
    HdrFlagsString = IkeGetHdrFlagsString((unsigned __int8)v1[19]);
    ExchTypeString = IkeGetExchTypeString(v53);
    v57 = (__int16 *)v108[0];
    v90 = HdrFlagsString;
    v58 = v101;
    WPP_SF_iSsdssD(v54, v59, v60, v52, v49, ExchTypeString, v101, v108[0], v90, v102);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v61 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v62 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v62 != -1 )
      {
        v63 = (__int64 *)TlsGetValue(v62);
        if ( v63 )
        {
          v64 = *v63;
          v61 = gIkeExtGlobals;
          goto LABEL_82;
        }
        v61 = gIkeExtGlobals;
      }
    }
    v64 = 0;
LABEL_82:
    v105 = v64;
    v128 = &v105;
    v129 = 8;
    if ( !v61 )
      goto LABEL_90;
    v65 = (DWORD)v61[86].LockSemaphore;
    if ( v65 == -1 )
      goto LABEL_90;
    v66 = (char *)TlsGetValue(v65);
    v67 = (const WCHAR *)(v66 + 8);
    if ( !v66 )
      v67 = 0;
    if ( v67 )
    {
      v68 = -1;
      do
        v33 = v67[++v68] == 0;
      while ( !v33 );
      v69 = 2 * v68 + 2;
    }
    else
    {
LABEL_90:
      v67 = &LocaleName;
      v69 = 2;
    }
    v70 = (unsigned __int8)v1[18];
    v130 = v67;
    v131 = v69;
    v132 = 0;
    v71 = (__int16 *)IkeGetExchTypeString(v70);
    if ( v71 )
    {
      v72 = -1;
      do
        ++v72;
      while ( *((_BYTE *)v71 + v72) );
      v73 = v72 + 1;
    }
    else
    {
      v71 = word_180122432;
      v73 = 1;
    }
    v133 = v71;
    v136 = &v103;
    v134 = v73;
    v135 = 0;
    v103 = v58;
    v137 = 4;
    if ( v57 )
    {
      v74 = -1;
      do
        ++v74;
      while ( *((_BYTE *)v57 + v74) );
      v75 = v74 + 1;
    }
    else
    {
      v57 = word_180122432;
      v75 = 1;
    }
    v139 = v75;
    v138 = v57;
    v76 = v1[19];
    v140 = 0;
    if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
      goto LABEL_120;
    v77 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v78 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v78 != -1 )
      {
        v79 = (void **)TlsGetValue(v78);
        if ( v79 )
        {
          v80 = *v79;
          v77 = gIkeExtGlobals;
LABEL_110:
          lpMem = v80;
          p_lpMem = &lpMem;
          v116 = 8;
          if ( !v77 )
            goto LABEL_118;
          v81 = (DWORD)v77[86].LockSemaphore;
          if ( v81 == -1 )
            goto LABEL_118;
          v82 = (char *)TlsGetValue(v81);
          v83 = (const WCHAR *)(v82 + 8);
          if ( !v82 )
            v83 = 0;
          if ( v83 )
          {
            v84 = -1;
            do
              v33 = v83[++v84] == 0;
            while ( !v33 );
            v85 = 2 * v84 + 2;
          }
          else
          {
LABEL_118:
            v83 = &LocaleName;
            v85 = 2;
          }
          v118 = v85;
          v117 = v83;
          v120 = "IkeGetHdrFlagsString";
          v109 = off_180173280;
          v119 = 0;
          v121 = 21;
          v108[0] = 0x50B000000LL;
          v108[1] = 1;
          v110 = *(unsigned __int16 *)off_180173280;
          v112 = &dword_180166EA4;
          v111 = 2;
          v113 = 45;
          v114 = 1;
          EtwEventWriteTransfer(qword_180173298, v108, 0, 0, 5, &v109);
LABEL_120:
          if ( v76 == 8 )
          {
            v86 = "IKEV2_HDR_INITIATOR_BIT";
          }
          else if ( v76 == 16 )
          {
            v86 = "IKEV2_HDR_VERSION_BIT";
          }
          else
          {
            v86 = "UNKNOWN";
            if ( v76 == 32 )
              v86 = "IKEV2_HDR_RESPONSE_BIT";
          }
          do
            v33 = v86[++v20] == 0;
          while ( !v33 );
          v141 = v86;
          v143 = 0;
          v142 = v20 + 1;
          LODWORD(v104) = v102;
          v145 = 4;
          v144 = &v104;
          v122 = off_180173280;
          lpMem = (LPVOID)0x40B000000LL;
          v107 = 0;
          v123 = *(unsigned __int16 *)off_180173280;
          v125 = &word_18015A78E;
          v124 = 2;
          v126 = 89;
          v127 = 1;
          return EtwEventWriteTransfer(qword_180173298, &lpMem, 0, 0, 9, &v122);
        }
        v77 = gIkeExtGlobals;
      }
    }
    v80 = 0;
    goto LABEL_110;
  }
  return result;
}

```

## disassembly

```asm
0x180038540  mov     r11, rsp
0x180038543  mov     [r11+18h], rbx
0x180038547  mov     [r11+20h], rsi
0x18003854b  push    rbp
0x18003854c  push    rdi
0x18003854d  push    r13
0x18003854f  push    r14
0x180038551  push    r15
0x180038553  lea     rbp, [r11-0D8h]
0x18003855a  sub     rsp, 1E0h
0x180038561  mov     rax, cs:__security_cookie
0x180038568  xor     rax, rsp
0x18003856b  mov     [rbp+0D0h+var_30], rax
0x180038572  mov     r13, rcx
0x180038575  mov     [rbp+0D0h+var_140], rcx
0x180038579  mov     ecx, [rcx+18h]; hostlong
0x18003857c  mov     [r11+10h], r12
0x180038580  call    cs:__imp_htonl
0x180038586  mov     ecx, [r13+14h]; hostlong
0x18003858a  mov     [rbp+0D0h+var_150], eax
0x18003858d  call    cs:__imp_htonl
0x180038593  movzx   ecx, byte ptr [r13+10h]
0x180038598  mov     [rbp+0D0h+var_14C], eax
0x18003859b  call    IkeGetNextPayloadString
0x1800385a0  mov     [rbp+0D0h+var_120], rax
0x1800385a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800385ab  lea     rcx, WPP_GLOBAL_Control
0x1800385b2  cmp     rax, rcx
0x1800385b5  jz      loc_18003870F
0x1800385bb  cmp     byte ptr [rax+19h], 4
0x1800385bf  jb      loc_18003870F
0x1800385c5  test    byte ptr [rax+1Ch], 10h
0x1800385c9  jz      loc_18003870F
0x1800385cf  mov     rdx, cs:gIkeExtGlobals
0x1800385d6  test    rdx, rdx
0x1800385d9  jz      short loc_1800385F8
0x1800385db  mov     ecx, [rdx+0D88h]; dwTlsIndex
0x1800385e1  cmp     ecx, 0FFFFFFFFh
0x1800385e4  jz      short loc_1800385F8
0x1800385e6  call    cs:__imp_TlsGetValue
0x1800385ec  mov     rdx, cs:gIkeExtGlobals
0x1800385f3  mov     rcx, rax
0x1800385f6  jmp     short loc_1800385FA
0x1800385f8  xor     ecx, ecx
0x1800385fa  xor     eax, eax
0x1800385fc  lea     r8, [rcx+8]
0x180038600  test    rcx, rcx
0x180038603  cmovz   r8, rax
0x180038607  mov     [rbp+0D0h+var_138], r8
0x18003860b  test    rdx, rdx
0x18003860e  jz      short loc_18003862F
0x180038610  mov     ecx, [rdx+0D88h]; dwTlsIndex
0x180038616  cmp     ecx, 0FFFFFFFFh
0x180038619  jz      short loc_18003862F
0x18003861b  call    cs:__imp_TlsGetValue
0x180038621  test    rax, rax
0x180038624  jz      short loc_18003862F
0x180038626  mov     rax, [rax]
0x180038629  mov     [rbp+0D0h+lpMem], rax
0x18003862d  jmp     short loc_180038637
0x18003862f  mov     [rbp+0D0h+lpMem], 0
0x180038637  movzx   eax, byte ptr [r13+0Fh]
0x18003863c  movzx   ecx, byte ptr [r13+0Eh]
0x180038641  movzx   r8d, byte ptr [r13+0Dh]
0x180038646  movzx   r10d, byte ptr [r13+0Ch]
0x18003864b  movzx   r11d, byte ptr [r13+0Bh]
0x180038650  movzx   ebx, byte ptr [r13+0Ah]
0x180038655  movzx   edi, byte ptr [r13+9]
0x18003865a  movzx   esi, byte ptr [r13+8]
0x18003865f  movzx   r14d, byte ptr [r13+7]
0x180038664  movzx   r15d, byte ptr [r13+6]
0x180038669  movzx   r12d, byte ptr [r13+5]
0x18003866e  movzx   r13d, byte ptr [r13+4]
0x180038673  mov     rdx, [rbp+0D0h+var_140]
0x180038677  mov     [rsp+200h+var_160], eax
0x18003867e  mov     [rsp+200h+var_168], ecx
0x180038685  mov     rcx, cs:WPP_GLOBAL_Control
0x18003868c  movzx   r9d, byte ptr [rdx+3]
0x180038691  mov     edx, 0Bh
0x180038696  mov     [rsp+200h+var_170], r8d
0x18003869e  lea     r8, WPP_b4c0bdae5de2357ade4f23a969f1f973_Traceguids
0x1800386a5  mov     [rsp+200h+var_178], r10d
0x1800386ad  mov     rcx, [rcx+10h]
0x1800386b1  mov     [rsp+200h+var_180], r11d
0x1800386b9  mov     [rsp+200h+var_188], ebx
0x1800386bd  mov     [rsp+200h+var_190], edi
0x1800386c1  mov     [rsp+200h+var_198], esi
0x1800386c5  mov     [rsp+200h+var_1A0], r14d
0x1800386ca  mov     [rsp+200h+var_1A8], r15d
0x1800386cf  mov     [rsp+200h+var_1B0], r12d
0x1800386d4  mov     [rsp+200h+var_1B8], r13d
0x1800386d9  mov     r13, [rbp+0D0h+var_140]
0x1800386dd  mov     dword ptr [rsp+200h+var_1C0], r9d
0x1800386e2  mov     r9, [rbp+0D0h+lpMem]
0x1800386e6  movzx   eax, byte ptr [r13+2]
0x1800386eb  mov     dword ptr [rsp+200h+var_1C8], eax
0x1800386ef  movzx   eax, byte ptr [r13+1]
0x1800386f4  mov     dword ptr [rsp+200h+var_1D0], eax
0x1800386f8  movzx   eax, byte ptr [r13+0]
0x1800386fd  mov     [rsp+200h+var_1D8], eax
0x180038701  mov     rax, [rbp+0D0h+var_138]
0x180038705  mov     [rsp+200h+var_1E0], rax
0x18003870a  call    WPP_SF_iSDDDDDDDDDDDDDDDD
0x18003870f  mov     eax, cs:dword_1801732B0
0x180038715  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18003871c  test    eax, eax
0x18003871e  jz      loc_180038A48
0x180038724  lea     r8, [rbp+0D0h+lpMem]
0x180038728  mov     [rbp+0D0h+lpMem], 0
0x180038730  xor     edx, edx; dwFlags
0x180038732  mov     ecx, 400h; dwBytes
0x180038737  call    WfpMemAlloc
0x18003873c  test    rax, rax
0x18003873f  jnz     loc_180038A48
0x180038745  movzx   eax, byte ptr [r13+0Fh]
0x18003874a  movzx   ecx, byte ptr [r13+0Eh]
0x18003874f  movzx   edx, byte ptr [r13+0Dh]
0x180038754  movzx   ebx, byte ptr [r13+0Ah]
0x180038759  movzx   r10d, byte ptr [r13+0Ch]
0x18003875e  movzx   r11d, byte ptr [r13+0Bh]
0x180038763  movzx   edi, byte ptr [r13+9]
0x180038768  movzx   esi, byte ptr [r13+8]
0x18003876d  movzx   r14d, byte ptr [r13+7]
0x180038772  movzx   r15d, byte ptr [r13+6]
0x180038777  movzx   r12d, byte ptr [r13+5]
0x18003877c  movzx   r13d, byte ptr [r13+4]
0x180038781  mov     r9, [rbp+0D0h+var_140]
0x180038785  mov     r8, [rbp+0D0h+var_140]
0x180038789  mov     [rsp+200h+var_178], eax
0x180038790  mov     [rsp+200h+var_180], ecx
0x180038797  movzx   r9d, byte ptr [r9+1]
0x18003879c  movzx   r8d, byte ptr [r8]
0x1800387a0  mov     [rsp+200h+var_188], edx
0x1800387a4  lea     rdx, aIcookie02x02x0; "iCookie %02x%02x%02x%02x%02x%02x%02x%02"...
0x1800387ab  mov     [rsp+200h+var_190], r10d
0x1800387b0  mov     [rsp+200h+var_198], r11d
0x1800387b5  mov     [rsp+200h+var_1A0], ebx
0x1800387b9  mov     rbx, [rbp+0D0h+lpMem]
0x1800387bd  mov     [rsp+200h+var_1A8], edi
0x1800387c1  mov     rcx, rbx
0x1800387c4  mov     [rsp+200h+var_1B0], esi
0x1800387c8  mov     [rsp+200h+var_1B8], r14d
0x1800387cd  mov     dword ptr [rsp+200h+var_1C0], r15d
0x1800387d2  mov     dword ptr [rsp+200h+var_1C8], r12d
0x1800387d7  mov     dword ptr [rsp+200h+var_1D0], r13d
0x1800387dc  mov     r13, [rbp+0D0h+var_140]
0x1800387e0  movzx   eax, byte ptr [r13+3]
0x1800387e5  mov     [rsp+200h+var_1D8], eax
0x1800387e9  movzx   eax, byte ptr [r13+2]
0x1800387ee  mov     dword ptr [rsp+200h+var_1E0], eax
0x1800387f2  call    IkeFormatString
0x1800387f7  mov     eax, cs:dword_180173278
0x1800387fd  cmp     eax, 4
0x180038800  jbe     loc_18003896F
0x180038806  mov     rax, cs:gIkeExtGlobals
0x18003880d  test    rax, rax
0x180038810  jz      short loc_18003883B
0x180038812  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180038818  cmp     ecx, 0FFFFFFFFh
0x18003881b  jz      short loc_18003883B
0x18003881d  call    cs:__imp_TlsGetValue
0x180038823  test    rax, rax
0x180038826  jz      short loc_180038834
0x180038828  mov     rcx, [rax]
0x18003882b  mov     rax, cs:gIkeExtGlobals
0x180038832  jmp     short loc_18003883D
0x180038834  mov     rax, cs:gIkeExtGlobals
0x18003883b  xor     ecx, ecx
0x18003883d  mov     [rbp+0D0h+var_138], rcx
0x180038841  lea     rcx, [rbp+0D0h+var_138]
0x180038845  mov     [rbp+0D0h+var_F0], rcx
0x180038849  mov     [rbp+0D0h+var_E8], 8
0x180038851  test    rax, rax
0x180038854  jz      short loc_180038894
0x180038856  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003885c  cmp     ecx, 0FFFFFFFFh
0x18003885f  jz      short loc_180038894
0x180038861  call    cs:__imp_TlsGetValue
0x180038867  xor     ecx, ecx
0x180038869  test    rax, rax
0x18003886c  lea     rdx, [rax+8]
0x180038870  cmovz   rdx, rcx
0x180038874  test    rdx, rdx
0x180038877  jz      short loc_180038894
0x180038879  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180038880  cmp     [rdx+rax*2+2], cx
0x180038885  lea     rax, [rax+1]
0x180038889  jnz     short loc_180038880
0x18003888b  lea     eax, ds:2[rax*2]
0x180038892  jmp     short loc_1800388A0
0x180038894  lea     rdx, LocaleName
0x18003889b  mov     eax, 2
0x1800388a0  mov     [rbp+0D0h+var_E0], rdx
0x1800388a4  mov     [rbp+0D0h+var_D8], eax
0x1800388a7  mov     [rbp+0D0h+var_D4], 0
0x1800388ae  test    rbx, rbx
0x1800388b1  jz      short loc_1800388CD
0x1800388b3  mov     rcx, rbx
0x1800388b6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800388bd  nop     dword ptr [rax]
0x1800388c0  inc     rax
0x1800388c3  cmp     byte ptr [rbx+rax], 0
0x1800388c7  jnz     short loc_1800388C0
0x1800388c9  inc     eax
0x1800388cb  jmp     short loc_1800388D9
0x1800388cd  lea     rcx, word_180122432
0x1800388d4  mov     eax, 1
0x1800388d9  mov     dword ptr [rbp+0D0h+var_C8], eax
0x1800388dc  lea     rdx, [rbp+0D0h+lpMem]
0x1800388e0  movzx   eax, cs:word_18015A7E9
0x1800388e7  xor     r9d, r9d
0x1800388ea  mov     dword ptr [rbp+0D0h+lpMem+4], eax
0x1800388ed  xor     r8d, r8d
0x1800388f0  mov     rax, cs:off_180173280
0x1800388f7  mov     [rbp+0D0h+var_110], rax
0x1800388fb  mov     [rbp+0D0h+var_D0], rcx
0x1800388ff  lea     rcx, _TraceLoggingMetadata
0x180038906  mov     dword ptr [rbp+0D0h+var_C8+4], 0
0x18003890d  mov     dword ptr [rbp+0D0h+lpMem], 0B000000h
0x180038914  mov     [rbp+0D0h+var_128], 0
0x18003891c  movzx   eax, word ptr [rax]
0x18003891f  mov     [rbp+0D0h+var_108], eax
0x180038922  lea     rax, byte_18015A7F3
0x180038929  mov     [rbp+0D0h+var_100], rax
0x18003892d  lea     rax, _TraceLoggingMetadataEnd
0x180038934  sub     eax, ecx
0x180038936  mov     [rbp+0D0h+var_104], 2
0x18003893d  mov     [rbp+0D0h+var_F8], 31h ; '1'
0x180038944  mov     [rbp+0D0h+var_F4], 1
0x18003894b  mov     [rbp+0D0h+var_148], eax
0x18003894e  mov     eax, [rbp+0D0h+var_148]
0x180038951  mov     rcx, cs:qword_180173298
0x180038958  lea     rax, [rbp+0D0h+var_110]
0x18003895c  mov     qword ptr [rsp+200h+var_1D8], rax
0x180038961  mov     dword ptr [rsp+200h+var_1E0], 5
0x180038969  call    cs:__imp_EtwEventWriteTransfer
0x18003896f  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180038975  test    al, 10h
0x180038977  jz      short loc_18003897E
0x180038979  and     eax, 1
0x18003897c  jmp     short loc_180038983
0x18003897e  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180038983  test    eax, eax
0x180038985  jz      short loc_180038A06
0x180038987  cmp     cs:gWfpTrackHeapAllocs, 0
0x18003898e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180038995  jz      short loc_1800389D6
0x180038997  test    rbx, rbx
0x18003899a  jz      short loc_1800389D6
0x18003899c  mov     eax, r14d
0x18003899f  lock xadd cs:gWfpNumHeapAllocs, eax
0x1800389a7  cmp     eax, 1
0x1800389aa  jns     short loc_1800389D6
0x1800389ac  cmp     cs:gMisalignedHeapTelemFired, 0
0x1800389b3  jnz     short loc_1800389CD
0x1800389b5  cmp     cs:gWfpNumHeapAllocs, 0
0x1800389bc  jg      short loc_1800389C3
0x1800389be  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gWfpNumHeapAllocs > 0", "allocs and frees are out of sync")
0x1800389c3  mov     cs:gMisalignedHeapTelemFired, 1
0x1800389cd  lock inc cs:gWfpNumHeapAllocs
0x1800389d4  jmp     short loc_180038A48
0x1800389d6  mov     rcx, cs:gWfpHeap; hHeap
0x1800389dd  mov     r8, rbx; lpMem
0x1800389e0  xor     edx, edx; dwFlags
0x1800389e2  call    cs:__imp_HeapFree
0x1800389e8  cmp     cs:gHeapFreeFailedFired, 0
0x1800389ef  jnz     short loc_180038A48
0x1800389f1  test    eax, eax
0x1800389f3  jnz     short loc_180038A48
0x1800389f5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success", "HeapFree failed")
0x1800389fa  mov     cs:gHeapFreeFailedFired, 1
0x180038a04  jmp     short loc_180038A48
0x180038a06  cmp     cs:gWfpTrackHeapBytes, 0
0x180038a0d  jz      short loc_180038A2F
0x180038a0f  test    rbx, rbx
0x180038a12  jz      short loc_180038A2F
0x180038a14  mov     rcx, cs:gWfpHeap; hHeap
0x180038a1b  mov     r8, rbx; lpMem
0x180038a1e  xor     edx, edx; dwFlags
0x180038a20  call    cs:__imp_HeapSize
0x180038a26  neg     eax
0x180038a28  lock add cs:gWfpHeapBytesAllocated, eax
0x180038a2f  mov     rcx, cs:gWfpHeap; hHeap
0x180038a36  mov     r8, rbx; lpMem
0x180038a39  xor     edx, edx; dwFlags
0x180038a3b  call    cs:__imp_HeapFree
0x180038a41  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180038a48  mov     rsi, cs:WPP_GLOBAL_Control
0x180038a4f  lea     rax, WPP_GLOBAL_Control
0x180038a56  cmp     rsi, rax
0x180038a59  jz      loc_180038B2D
0x180038a5f  cmp     byte ptr [rsi+19h], 4
0x180038a63  jb      loc_180038B2D
0x180038a69  test    byte ptr [rsi+1Ch], 10h
0x180038a6d  jz      loc_180038B2D
0x180038a73  mov     rdx, cs:gIkeExtGlobals
0x180038a7a  test    rdx, rdx
0x180038a7d  jz      short loc_180038AA3
0x180038a7f  mov     ecx, [rdx+0D88h]; dwTlsIndex
0x180038a85  cmp     ecx, 0FFFFFFFFh
  ... truncated ...
```
