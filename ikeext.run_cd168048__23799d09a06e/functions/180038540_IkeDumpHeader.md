# IkeDumpHeader

- ea: `0x180038540`
- end: `0x180038f01`
- name: `IkeDumpHeader`
- size: `2497`
- prototype: ``
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
__int64 __fastcall IkeDumpHeader(__int64 a1)
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
  LPCRITICAL_SECTION v22; // rax
  DWORD v23; // ecx
  __int64 *v24; // rax
  __int64 v25; // rcx
  DWORD v26; // ecx
  char *v27; // rax
  const WCHAR *v28; // rdx
  __int64 v29; // rax
  bool v30; // zf
  int v31; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  BOOL v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  _QWORD *v37; // rsi
  LPCRITICAL_SECTION v38; // rdx
  DWORD v39; // ecx
  LPVOID v40; // rax
  LPVOID v41; // rcx
  __int64 v42; // r12
  DWORD v43; // ecx
  __int64 *v44; // rax
  __int64 v45; // r15
  unsigned __int8 v46; // bl
  __int64 v47; // rsi
  __int64 HdrFlagsString; // rdi
  __int64 ExchTypeString; // rax
  __int16 *v50; // rbx
  u_long v51; // edi
  int v52; // edx
  int v53; // r8d
  __int64 result; // rax
  LPCRITICAL_SECTION v55; // rax
  DWORD v56; // ecx
  __int64 *v57; // rax
  __int64 v58; // rcx
  DWORD v59; // ecx
  char *v60; // rax
  const WCHAR *v61; // rdx
  __int64 v62; // rax
  int v63; // eax
  __int64 v64; // rcx
  __int16 *v65; // rax
  __int64 v66; // rcx
  int v67; // ecx
  __int64 v68; // rax
  int v69; // eax
  char v70; // bl
  LPCRITICAL_SECTION v71; // rax
  DWORD v72; // ecx
  void **v73; // rax
  void *v74; // rcx
  DWORD v75; // ecx
  char *v76; // rax
  const WCHAR *v77; // rdx
  __int64 v78; // rax
  int v79; // eax
  const char *v80; // rax
  int v81; // [rsp+38h] [rbp-100h]
  int v82; // [rsp+40h] [rbp-F8h]
  int v83; // [rsp+48h] [rbp-F0h]
  __int64 v84; // [rsp+48h] [rbp-F0h]
  char v85; // [rsp+50h] [rbp-E8h]
  int v86; // [rsp+50h] [rbp-E8h]
  int v87; // [rsp+58h] [rbp-E0h]
  int v88; // [rsp+60h] [rbp-D8h]
  int v89; // [rsp+68h] [rbp-D0h]
  int v90; // [rsp+70h] [rbp-C8h]
  int v91; // [rsp+78h] [rbp-C0h]
  int v92; // [rsp+80h] [rbp-B8h]
  int v93; // [rsp+88h] [rbp-B0h]
  int v94; // [rsp+90h] [rbp-A8h]
  u_long v95; // [rsp+B8h] [rbp-80h]
  u_long v96; // [rsp+BCh] [rbp-7Ch]
  unsigned int v97; // [rsp+C0h] [rbp-78h] BYREF
  char *v98; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v99; // [rsp+D0h] [rbp-68h] BYREF
  LPVOID lpMem; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v101; // [rsp+E0h] [rbp-58h]
  __int64 v102[2]; // [rsp+E8h] [rbp-50h] BYREF
  char *v103; // [rsp+F8h] [rbp-40h] BYREF
  int v104; // [rsp+100h] [rbp-38h]
  int v105; // [rsp+104h] [rbp-34h]
  int *v106; // [rsp+108h] [rbp-30h]
  int v107; // [rsp+110h] [rbp-28h]
  int v108; // [rsp+114h] [rbp-24h]
  LPVOID *p_lpMem; // [rsp+118h] [rbp-20h]
  __int64 v110; // [rsp+120h] [rbp-18h]
  const WCHAR *v111; // [rsp+128h] [rbp-10h]
  int v112; // [rsp+130h] [rbp-8h]
  int v113; // [rsp+134h] [rbp-4h]
  __int16 *v114; // [rsp+138h] [rbp+0h]
  __int64 v115; // [rsp+140h] [rbp+8h]
  char *v116; // [rsp+148h] [rbp+10h] BYREF
  int v117; // [rsp+150h] [rbp+18h]
  int v118; // [rsp+154h] [rbp+1Ch]
  __int16 *v119; // [rsp+158h] [rbp+20h]
  int v120; // [rsp+160h] [rbp+28h]
  int v121; // [rsp+164h] [rbp+2Ch]
  __int64 *v122; // [rsp+168h] [rbp+30h]
  __int64 v123; // [rsp+170h] [rbp+38h]
  const WCHAR *v124; // [rsp+178h] [rbp+40h]
  int v125; // [rsp+180h] [rbp+48h]
  int v126; // [rsp+184h] [rbp+4Ch]
  __int16 *v127; // [rsp+188h] [rbp+50h]
  int v128; // [rsp+190h] [rbp+58h]
  int v129; // [rsp+194h] [rbp+5Ch]
  unsigned int *v130; // [rsp+198h] [rbp+60h]
  __int64 v131; // [rsp+1A0h] [rbp+68h]
  __int16 *v132; // [rsp+1A8h] [rbp+70h]
  int v133; // [rsp+1B0h] [rbp+78h]
  int v134; // [rsp+1B4h] [rbp+7Ch]
  const char *v135; // [rsp+1B8h] [rbp+80h]
  int v136; // [rsp+1C0h] [rbp+88h]
  int v137; // [rsp+1C4h] [rbp+8Ch]
  char **v138; // [rsp+1C8h] [rbp+90h]
  __int64 v139; // [rsp+1D0h] [rbp+98h]

  v1 = (char *)a1;
  v98 = (char *)a1;
  v95 = htonl(*(_DWORD *)(a1 + 24));
  v96 = htonl(*((_DWORD *)v1 + 5));
  v102[0] = IkeGetNextPayloadString((unsigned __int8)v1[16]);
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
    v99 = v6;
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
    v85 = v1[4];
    v1 = v98;
    WPP_SF_iSDDDDDDDDDDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_b4c0bdae5de2357ade4f23a969f1f973_Traceguids,
      (_DWORD)lpMem,
      v99,
      *v98,
      v98[1],
      v98[2],
      v98[3],
      v85,
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
    if ( !WfpMemAlloc(0x400u, 0) )
    {
      v94 = (unsigned __int8)v1[15];
      v93 = (unsigned __int8)v1[14];
      v92 = (unsigned __int8)v1[13];
      v91 = (unsigned __int8)v1[12];
      v90 = (unsigned __int8)v1[11];
      v89 = (unsigned __int8)v1[10];
      v21 = lpMem;
      v88 = (unsigned __int8)v1[9];
      v87 = (unsigned __int8)v1[8];
      v86 = (unsigned __int8)v1[7];
      v83 = (unsigned __int8)v1[6];
      v82 = (unsigned __int8)v1[5];
      v81 = (unsigned __int8)v1[4];
      v1 = v98;
      IkeFormatString(
        lpMem,
        "iCookie %02x%02x%02x%02x%02x%02x%02x%02x rCookie %02x%02x%02x%02x%02x%02x%02x%02x",
        (unsigned __int8)*v98,
        (unsigned __int8)v98[1],
        (unsigned __int8)v98[2],
        (unsigned __int8)v98[3],
        v81,
        v82,
        v83,
        v86,
        v87,
        v88,
        v89,
        v90,
        v91,
        v92,
        v93,
        v94);
      if ( (unsigned int)dword_180173278 <= 4 )
      {
LABEL_35:
        if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
        if ( IsEnabledDeviceUsageNoInline )
        {
          v20 = -1;
          v33 = HeapFree(gWfpHeap, 0, v21);
          if ( !gHeapFreeFailedFired && !v33 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v35, v34, v36);
            gHeapFreeFailedFired = 1;
          }
        }
        else
        {
          HeapFree(gWfpHeap, 0, v21);
          v20 = -1;
        }
        goto LABEL_43;
      }
      v22 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v23 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v23 != -1 )
        {
          v24 = (__int64 *)TlsGetValue(v23);
          if ( v24 )
          {
            v25 = *v24;
            v22 = gIkeExtGlobals;
LABEL_25:
            v99 = v25;
            p_lpMem = (LPVOID *)&v99;
            v110 = 8;
            if ( !v22 )
              goto LABEL_33;
            v26 = (DWORD)v22[86].LockSemaphore;
            if ( v26 == -1 )
              goto LABEL_33;
            v27 = (char *)TlsGetValue(v26);
            v28 = (const WCHAR *)(v27 + 8);
            if ( !v27 )
              v28 = 0;
            if ( v28 )
            {
              v29 = -1;
              do
                v30 = v28[++v29] == 0;
              while ( !v30 );
              v31 = 2 * v29 + 2;
            }
            else
            {
LABEL_33:
              v28 = &LocaleName;
              v31 = 2;
            }
            v111 = v28;
            v112 = v31;
            v113 = 0;
            v115 = 1;
            v103 = off_180173280;
            v114 = word_180122452;
            lpMem = (LPVOID)0x40B000000LL;
            v101 = 0;
            v104 = *(unsigned __int16 *)off_180173280;
            v106 = (int *)byte_18015A82B;
            v105 = 2;
            v107 = 49;
            v108 = 1;
            v97 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(qword_180173298, &lpMem, 0, 0, 5, &v103);
            goto LABEL_35;
          }
          v22 = gIkeExtGlobals;
        }
      }
      v25 = 0;
      goto LABEL_25;
    }
  }
LABEL_43:
  v37 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
  {
    v50 = (__int16 *)v102[0];
    v51 = v95;
  }
  else
  {
    v38 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v39 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v39 == -1) )
    {
      v41 = 0;
    }
    else
    {
      v40 = TlsGetValue(v39);
      v37 = WPP_GLOBAL_Control;
      v41 = v40;
      v38 = gIkeExtGlobals;
    }
    v42 = (__int64)v41 + 8;
    if ( !v41 )
      v42 = 0;
    if ( v38
      && (v43 = (DWORD)v38[86].LockSemaphore, v43 != -1)
      && (v44 = (__int64 *)TlsGetValue(v43), v37 = WPP_GLOBAL_Control, v44) )
    {
      v45 = *v44;
    }
    else
    {
      LODWORD(v45) = 0;
    }
    v46 = v1[18];
    v47 = v37[2];
    HdrFlagsString = IkeGetHdrFlagsString((unsigned __int8)v1[19]);
    ExchTypeString = IkeGetExchTypeString(v46);
    v50 = (__int16 *)v102[0];
    v84 = HdrFlagsString;
    v51 = v95;
    WPP_SF_iSsdssD(v47, v52, v53, v45, v42, ExchTypeString, v95, v102[0], v84, v96);
  }
  result = (unsigned int)dword_180173278;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v55 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v56 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v56 != -1 )
      {
        v57 = (__int64 *)TlsGetValue(v56);
        if ( v57 )
        {
          v58 = *v57;
          v55 = gIkeExtGlobals;
          goto LABEL_66;
        }
        v55 = gIkeExtGlobals;
      }
    }
    v58 = 0;
LABEL_66:
    v99 = v58;
    v122 = &v99;
    v123 = 8;
    if ( !v55 )
      goto LABEL_74;
    v59 = (DWORD)v55[86].LockSemaphore;
    if ( v59 == -1 )
      goto LABEL_74;
    v60 = (char *)TlsGetValue(v59);
    v61 = (const WCHAR *)(v60 + 8);
    if ( !v60 )
      v61 = 0;
    if ( v61 )
    {
      v62 = -1;
      do
        v30 = v61[++v62] == 0;
      while ( !v30 );
      v63 = 2 * v62 + 2;
    }
    else
    {
LABEL_74:
      v61 = &LocaleName;
      v63 = 2;
    }
    v64 = (unsigned __int8)v1[18];
    v124 = v61;
    v125 = v63;
    v126 = 0;
    v65 = (__int16 *)IkeGetExchTypeString(v64);
    if ( v65 )
    {
      v66 = -1;
      do
        ++v66;
      while ( *((_BYTE *)v65 + v66) );
      v67 = v66 + 1;
    }
    else
    {
      v65 = word_180122452;
      v67 = 1;
    }
    v127 = v65;
    v130 = &v97;
    v128 = v67;
    v129 = 0;
    v97 = v51;
    v131 = 4;
    if ( v50 )
    {
      v68 = -1;
      do
        ++v68;
      while ( *((_BYTE *)v50 + v68) );
      v69 = v68 + 1;
    }
    else
    {
      v50 = word_180122452;
      v69 = 1;
    }
    v133 = v69;
    v132 = v50;
    v70 = v1[19];
    v134 = 0;
    if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
      goto LABEL_104;
    v71 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v72 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v72 != -1 )
      {
        v73 = (void **)TlsGetValue(v72);
        if ( v73 )
        {
          v74 = *v73;
          v71 = gIkeExtGlobals;
LABEL_94:
          lpMem = v74;
          p_lpMem = &lpMem;
          v110 = 8;
          if ( !v71 )
            goto LABEL_102;
          v75 = (DWORD)v71[86].LockSemaphore;
          if ( v75 == -1 )
            goto LABEL_102;
          v76 = (char *)TlsGetValue(v75);
          v77 = (const WCHAR *)(v76 + 8);
          if ( !v76 )
            v77 = 0;
          if ( v77 )
          {
            v78 = -1;
            do
              v30 = v77[++v78] == 0;
            while ( !v30 );
            v79 = 2 * v78 + 2;
          }
          else
          {
LABEL_102:
            v77 = &LocaleName;
            v79 = 2;
          }
          v112 = v79;
          v111 = v77;
          v114 = (__int16 *)"IkeGetHdrFlagsString";
          v103 = off_180173280;
          v113 = 0;
          v115 = 21;
          v102[0] = 0x50B000000LL;
          v102[1] = 1;
          v104 = *(unsigned __int16 *)off_180173280;
          v106 = &dword_180166EA4;
          v105 = 2;
          v107 = 45;
          v108 = 1;
          EtwEventWriteTransfer(qword_180173298, v102, 0, 0, 5, &v103);
LABEL_104:
          if ( v70 == 8 )
          {
            v80 = "IKEV2_HDR_INITIATOR_BIT";
          }
          else if ( v70 == 16 )
          {
            v80 = "IKEV2_HDR_VERSION_BIT";
          }
          else
          {
            v80 = "UNKNOWN";
            if ( v70 == 32 )
              v80 = "IKEV2_HDR_RESPONSE_BIT";
          }
          do
            v30 = v80[++v20] == 0;
          while ( !v30 );
          v135 = v80;
          v137 = 0;
          v136 = v20 + 1;
          LODWORD(v98) = v96;
          v139 = 4;
          v138 = &v98;
          v116 = off_180173280;
          lpMem = (LPVOID)0x40B000000LL;
          v101 = 0;
          v117 = *(unsigned __int16 *)off_180173280;
          v119 = &word_18015A7C6;
          v118 = 2;
          v120 = 89;
          v121 = 1;
          return EtwEventWriteTransfer(qword_180173298, &lpMem, 0, 0, 9, &v116);
        }
        v71 = gIkeExtGlobals;
      }
    }
    v74 = 0;
    goto LABEL_94;
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
0x1800388cd  lea     rcx, word_180122452
0x1800388d4  mov     eax, 1
0x1800388d9  mov     dword ptr [rbp+0D0h+var_C8], eax
0x1800388dc  lea     rdx, [rbp+0D0h+lpMem]
0x1800388e0  movzx   eax, cs:word_18015A821
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
0x180038922  lea     rax, byte_18015A82B
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
0x1800389be  call    MicrosoftTelemetryAssertTriggeredNoArgs
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
0x1800389f5  call    MicrosoftTelemetryAssertTriggeredNoArgs
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
