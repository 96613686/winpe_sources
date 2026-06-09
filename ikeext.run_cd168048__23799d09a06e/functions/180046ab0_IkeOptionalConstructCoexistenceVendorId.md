# IkeOptionalConstructCoexistenceVendorId

- ea: `0x180046ab0`
- end: `0x180047445`
- name: `IkeOptionalConstructCoexistenceVendorId`
- size: `2453`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800428c0`
- `0x180043270`
- `0x1800e2f28`
- `0x1800e36f4`
- `0x1800e3d54`
- `0x1800e4650`
- `0x1800e4a00`
- `0x1800e5090`
- `0x1800e7294`

## callees

- `0x180008388`
- `0x18001fc40`
- `0x180037290`
- `0x180046ab0`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046b3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046b83`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046ca5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046ce0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046d47`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046d8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046fd5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800470ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047152`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004719a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047303`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047348`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046b3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046b83`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046ca5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046ce0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046d47`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046d8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046fd5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800470ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047152`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004719a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047303`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047348`
- `ntdll!EtwEventWriteTransfer` at `0x180046c5b`
- `ntdll!EtwEventWriteTransfer` at `0x180046e6f`
- `ntdll!EtwEventWriteTransfer` at `0x1800470ad`
- `ntdll!EtwEventWriteTransfer` at `0x18004726f`
- `ntdll!EtwEventWriteTransfer` at `0x180047410`
- `ntdll!EtwEventWriteTransfer` at `0x180046c5b`
- `ntdll!EtwEventWriteTransfer` at `0x180046e6f`
- `ntdll!EtwEventWriteTransfer` at `0x1800470ad`
- `ntdll!EtwEventWriteTransfer` at `0x18004726f`
- `ntdll!EtwEventWriteTransfer` at `0x180047410`

## pseudocode

```c
__int64 __fastcall IkeOptionalConstructCoexistenceVendorId(int a1, _BYTE *a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  __int64 v9; // rdi
  LPCRITICAL_SECTION v10; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v13; // rcx
  DWORD v14; // ecx
  char *v15; // rax
  const WCHAR *v16; // rdx
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  _QWORD *v20; // rcx
  LPCRITICAL_SECTION v21; // rdx
  DWORD v22; // eax
  LPVOID v23; // rax
  LPVOID v24; // r8
  __int64 v25; // rbx
  DWORD v26; // eax
  __int64 *v27; // rax
  __int64 v28; // r9
  LPCRITICAL_SECTION v29; // rax
  DWORD v30; // ecx
  __int64 *v31; // rax
  __int64 v32; // rcx
  DWORD v33; // ecx
  char *v34; // rax
  const WCHAR *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  __int64 LockSemaphore_low; // rcx
  __int64 v39; // r9
  __int64 v40; // r14
  _QWORD *v41; // rbx
  __int64 *v42; // rax
  __int64 v43; // rsi
  __int64 v44; // rbx
  __int64 v45; // rax
  LPCRITICAL_SECTION v46; // rax
  DWORD v47; // ecx
  __int64 *v48; // rax
  __int64 v49; // rcx
  DWORD v50; // ecx
  char *v51; // rax
  const WCHAR *v52; // rdx
  __int64 v53; // rax
  int v54; // eax
  _QWORD *v55; // rbx
  __int64 *v56; // rax
  __int64 v57; // rsi
  __int64 v58; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v60; // rax
  DWORD v61; // ecx
  __int64 *v62; // rax
  __int64 v63; // rcx
  DWORD v64; // ecx
  char *v65; // rax
  const WCHAR *v66; // rdx
  __int64 v67; // rax
  int v68; // eax
  LPCRITICAL_SECTION v69; // rax
  DWORD v70; // ecx
  __int64 *v71; // rax
  __int64 v72; // rcx
  DWORD v73; // ecx
  char *v74; // rax
  const WCHAR *v75; // rdx
  int v76; // eax
  __int64 v78; // [rsp+28h] [rbp-81h]
  __int64 v79; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v80; // [rsp+38h] [rbp-71h] BYREF
  int v81; // [rsp+40h] [rbp-69h] BYREF
  int v82; // [rsp+44h] [rbp-65h]
  __int64 v83; // [rsp+48h] [rbp-61h]
  char *v84; // [rsp+50h] [rbp-59h] BYREF
  int v85; // [rsp+58h] [rbp-51h]
  int v86; // [rsp+5Ch] [rbp-4Dh]
  int *v87; // [rsp+60h] [rbp-49h]
  int v88; // [rsp+68h] [rbp-41h]
  int v89; // [rsp+6Ch] [rbp-3Dh]
  __int64 *v90; // [rsp+70h] [rbp-39h]
  __int64 v91; // [rsp+78h] [rbp-31h]
  const WCHAR *v92; // [rsp+80h] [rbp-29h]
  int v93; // [rsp+88h] [rbp-21h]
  int v94; // [rsp+8Ch] [rbp-1Dh]
  const char *v95; // [rsp+90h] [rbp-19h]
  __int64 v96; // [rsp+98h] [rbp-11h]
  _QWORD v97[2]; // [rsp+A0h] [rbp-9h] BYREF

  v4 = 0;
  v9 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v10 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v10 = gIkeExtGlobals;
LABEL_9:
    v13 = 0;
    goto LABEL_10;
  }
  v13 = *Value;
  v10 = gIkeExtGlobals;
LABEL_10:
  v79 = v13;
  v90 = &v79;
  v91 = 8;
  if ( !v10 )
    goto LABEL_18;
  v14 = (DWORD)v10[86].LockSemaphore;
  if ( v14 == -1 )
    goto LABEL_18;
  v15 = (char *)TlsGetValue(v14);
  v16 = (const WCHAR *)(v15 + 8);
  if ( !v15 )
    v16 = 0;
  if ( v16 )
  {
    v17 = -1;
    do
      v18 = v16[++v17] == 0;
    while ( !v18 );
    v19 = 2 * v17 + 2;
  }
  else
  {
LABEL_18:
    v16 = &LocaleName;
    v19 = 2;
  }
  v93 = v19;
  v92 = v16;
  v95 = "IkeOptionalConstructCoexistenceVendorId";
  v84 = off_180173280;
  v94 = 0;
  v96 = 40;
  v97[0] = 0x50B000000LL;
  v97[1] = 1;
  v85 = *(unsigned __int16 *)off_180173280;
  v87 = &dword_180166EA4;
  v86 = 2;
  v88 = 45;
  v89 = 1;
  v80 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, v97, 0, 0, 5, &v84);
LABEL_20:
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v21 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v22 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v22 == -1) )
    {
      v24 = 0;
    }
    else
    {
      v23 = TlsGetValue(v22);
      v20 = WPP_GLOBAL_Control;
      v24 = v23;
      v21 = gIkeExtGlobals;
    }
    v25 = (__int64)v24 + 8;
    if ( !v24 )
      v25 = 0;
    if ( v21
      && (v26 = (DWORD)v21[86].LockSemaphore, v26 != -1)
      && (v27 = (__int64 *)TlsGetValue(v26), v20 = WPP_GLOBAL_Control, v27) )
    {
      v28 = *v27;
    }
    else
    {
      LODWORD(v28) = 0;
    }
    LODWORD(v78) = *(_DWORD *)(a4 + 588);
    WPP_SF_iSL(v20[2], 18, (unsigned int)WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids, v28, v25, v78, v79);
    v4 = 0;
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v29 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v30 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v30 != -1 )
      {
        v31 = (__int64 *)TlsGetValue(v30);
        if ( v31 )
        {
          v32 = *v31;
          v29 = gIkeExtGlobals;
LABEL_42:
          v97[0] = v32;
          v90 = v97;
          v91 = 8;
          if ( !v29 )
            goto LABEL_50;
          v33 = (DWORD)v29[86].LockSemaphore;
          if ( v33 == -1 )
            goto LABEL_50;
          v34 = (char *)TlsGetValue(v33);
          v35 = (const WCHAR *)(v34 + 8);
          if ( !v34 )
            v35 = 0;
          if ( v35 )
          {
            v36 = -1;
            do
              v18 = v35[++v36] == 0;
            while ( !v18 );
            v37 = 2 * v36 + 2;
          }
          else
          {
LABEL_50:
            v35 = &LocaleName;
            v37 = 2;
          }
          v93 = v37;
          v80 = *(_DWORD *)(a4 + 588);
          v92 = v35;
          v95 = (const char *)&v80;
          v82 = 4;
          v84 = off_180173280;
          v94 = 0;
          v96 = 4;
          v81 = 184549376;
          v83 = 0;
          v85 = *(unsigned __int16 *)off_180173280;
          v87 = (int *)&byte_180164637;
          v86 = 2;
          v88 = 61;
          v89 = 1;
          LODWORD(v79) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 5, &v84);
          goto LABEL_52;
        }
        v29 = gIkeExtGlobals;
      }
    }
    v32 = 0;
    goto LABEL_42;
  }
LABEL_52:
  v40 = IkeConstructVendor(a1, 10, *(_DWORD *)(a4 + 584) == 2, *(_DWORD *)(a4 + 588), 0);
  if ( v40 )
    goto LABEL_112;
  if ( !*(_DWORD *)(a4 + 584)
    && (*(_BYTE *)(a4 + 1056) & 1) != 0
    && (unsigned int)IkeIsKeyModEnabledForTraffic(1u, a2, a3, v39) )
  {
    v4 = 1;
  }
  if ( *(_DWORD *)(a4 + 584) == 1 || v4 )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals
        && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
        && (v56 = (__int64 *)TlsGetValue(LockSemaphore_low), v55 = WPP_GLOBAL_Control, v56) )
      {
        v57 = *v56;
      }
      else
      {
        LODWORD(v57) = 0;
      }
      v58 = v55[2];
      TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
      WPP_SF_iS(v58, 20, (unsigned int)WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids, v57, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_111;
    v60 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v61 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v61 != -1 )
      {
        v62 = (__int64 *)TlsGetValue(v61);
        if ( v62 )
        {
          v63 = *v62;
          v60 = gIkeExtGlobals;
LABEL_101:
          v97[0] = v63;
          v90 = v97;
          v91 = 8;
          if ( !v60 )
            goto LABEL_109;
          v64 = (DWORD)v60[86].LockSemaphore;
          if ( v64 == -1 )
            goto LABEL_109;
          v65 = (char *)TlsGetValue(v64);
          v66 = (const WCHAR *)(v65 + 8);
          if ( !v65 )
            v66 = 0;
          if ( v66 )
          {
            v67 = -1;
            do
              v18 = v66[++v67] == 0;
            while ( !v18 );
            v68 = 2 * v67 + 2;
          }
          else
          {
LABEL_109:
            v66 = &LocaleName;
            v68 = 2;
          }
          v93 = v68;
          v92 = v66;
          v95 = "IKE sending co-existence Vendor ID";
          v82 = 4;
          v84 = off_180173280;
          v94 = 0;
          v96 = 35;
          v81 = 184549376;
          v83 = 0;
          v85 = *(unsigned __int16 *)off_180173280;
          v87 = &dword_1801646C4;
          v86 = 2;
          v88 = 50;
          v89 = 1;
          LODWORD(v79) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 5, &v84);
LABEL_111:
          v40 = IkeConstructVendor(a1, 6, *(_DWORD *)(a4 + 584) == 2, 0, 0);
          goto LABEL_112;
        }
        v60 = gIkeExtGlobals;
      }
    }
    v63 = 0;
    goto LABEL_101;
  }
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( gIkeExtGlobals
      && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
      && (v42 = (__int64 *)TlsGetValue(LockSemaphore_low), v41 = WPP_GLOBAL_Control, v42) )
    {
      v43 = *v42;
    }
    else
    {
      LODWORD(v43) = 0;
    }
    v44 = v41[2];
    v45 = IkeGetTlsPeerAddr(LockSemaphore_low);
    WPP_SF_iS(v44, 19, (unsigned int)WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids, v43, v45);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v46 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v47 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v47 != -1 )
      {
        v48 = (__int64 *)TlsGetValue(v47);
        if ( v48 )
        {
          v49 = *v48;
          v46 = gIkeExtGlobals;
LABEL_75:
          v97[0] = v49;
          v90 = v97;
          v91 = 8;
          if ( !v46 )
            goto LABEL_83;
          v50 = (DWORD)v46[86].LockSemaphore;
          if ( v50 == -1 )
            goto LABEL_83;
          v51 = (char *)TlsGetValue(v50);
          v52 = (const WCHAR *)(v51 + 8);
          if ( !v51 )
            v52 = 0;
          if ( v52 )
          {
            v53 = -1;
            do
              v18 = v52[++v53] == 0;
            while ( !v18 );
            v54 = 2 * v53 + 2;
          }
          else
          {
LABEL_83:
            v52 = &LocaleName;
            v54 = 2;
          }
          v93 = v54;
          v92 = v52;
          v95 = "IKE not sending co-existence Vendor ID";
          v82 = 4;
          v84 = off_180173280;
          v94 = 0;
          v96 = 39;
          v81 = 184549376;
          v83 = 0;
          v85 = *(unsigned __int16 *)off_180173280;
          v87 = (int *)word_180164702;
          v86 = 2;
          v88 = 50;
          v89 = 1;
          LODWORD(v79) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 5, &v84);
          goto LABEL_112;
        }
        v46 = gIkeExtGlobals;
      }
    }
    v49 = 0;
    goto LABEL_75;
  }
LABEL_112:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(v40, "IkeOptionalConstructCoexistenceVendorId");
  v69 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_120;
  v70 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v70 == -1 )
    goto LABEL_120;
  v71 = (__int64 *)TlsGetValue(v70);
  if ( !v71 )
  {
    v69 = gIkeExtGlobals;
LABEL_120:
    v72 = 0;
    goto LABEL_121;
  }
  v72 = *v71;
  v69 = gIkeExtGlobals;
LABEL_121:
  v97[0] = v72;
  v90 = v97;
  v91 = 8;
  if ( !v69 )
    goto LABEL_128;
  v73 = (DWORD)v69[86].LockSemaphore;
  if ( v73 == -1 )
    goto LABEL_128;
  v74 = (char *)TlsGetValue(v73);
  v75 = (const WCHAR *)(v74 + 8);
  if ( !v74 )
    v75 = 0;
  if ( v75 )
  {
    do
      v18 = v75[++v9] == 0;
    while ( !v18 );
    v76 = 2 * v9 + 2;
  }
  else
  {
LABEL_128:
    v75 = &LocaleName;
    v76 = 2;
  }
  v93 = v76;
  v92 = v75;
  v95 = "IkeOptionalConstructCoexistenceVendorId";
  v82 = 5;
  v84 = off_180173280;
  v83 = 1;
  v94 = 0;
  v96 = 40;
  v81 = 184549376;
  v85 = *(unsigned __int16 *)off_180173280;
  v87 = (int *)byte_180166E6B;
  v89 = 1;
  v86 = 2;
  v88 = 45;
  LODWORD(v79) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 5, &v84);
  return IkeReturnError(v40, "IkeOptionalConstructCoexistenceVendorId");
}

```

## disassembly

```asm
0x180046ab0  push    rbp
0x180046ab2  push    rbx
0x180046ab3  push    rsi
0x180046ab4  push    rdi
0x180046ab5  push    r12
0x180046ab7  push    r13
0x180046ab9  push    r14
0x180046abb  push    r15
0x180046abd  lea     rbp, [rsp-1Fh]
0x180046ac2  sub     rsp, 0C8h
0x180046ac9  mov     rax, cs:__security_cookie
0x180046ad0  xor     rax, rsp
0x180046ad3  mov     [rbp+57h+var_50], rax
0x180046ad7  mov     eax, cs:dword_180173278
0x180046add  lea     r14, _TraceLoggingMetadataEnd
0x180046ae4  xor     ebx, ebx
0x180046ae6  mov     r15, r9
0x180046ae9  mov     r12, r8
0x180046aec  mov     rsi, rdx
0x180046aef  mov     r13, rcx
0x180046af2  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180046af9  cmp     eax, 5
0x180046afc  jbe     loc_180046C61
0x180046b02  mov     rcx, cs:qword_180173290
0x180046b09  mov     rax, cs:qword_180173288
0x180046b10  test    al, 1
0x180046b12  jz      loc_180046C61
0x180046b18  mov     rax, rcx
0x180046b1b  and     eax, 1
0x180046b1e  cmp     rax, rcx
0x180046b21  jnz     loc_180046C61
0x180046b27  mov     rax, cs:gIkeExtGlobals
0x180046b2e  test    rax, rax
0x180046b31  jz      short loc_180046B5C
0x180046b33  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046b39  cmp     ecx, 0FFFFFFFFh
0x180046b3c  jz      short loc_180046B5C
0x180046b3e  call    cs:__imp_TlsGetValue
0x180046b44  test    rax, rax
0x180046b47  jz      short loc_180046B55
0x180046b49  mov     rcx, [rax]
0x180046b4c  mov     rax, cs:gIkeExtGlobals
0x180046b53  jmp     short loc_180046B5F
0x180046b55  mov     rax, cs:gIkeExtGlobals
0x180046b5c  mov     rcx, rbx
0x180046b5f  mov     [rbp+57h+var_D0], rcx
0x180046b63  lea     rcx, [rbp+57h+var_D0]
0x180046b67  mov     [rbp+57h+var_90], rcx
0x180046b6b  mov     [rbp+57h+var_88], 8
0x180046b73  test    rax, rax
0x180046b76  jz      short loc_180046BB4
0x180046b78  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046b7e  cmp     ecx, 0FFFFFFFFh
0x180046b81  jz      short loc_180046BB4
0x180046b83  call    cs:__imp_TlsGetValue
0x180046b89  test    rax, rax
0x180046b8c  lea     rdx, [rax+8]
0x180046b90  cmovz   rdx, rbx
0x180046b94  test    rdx, rdx
0x180046b97  jz      short loc_180046BB4
0x180046b99  mov     rax, rdi
0x180046b9c  nop     dword ptr [rax+00h]
0x180046ba0  cmp     [rdx+rax*2+2], bx
0x180046ba5  lea     rax, [rax+1]
0x180046ba9  jnz     short loc_180046BA0
0x180046bab  lea     eax, ds:2[rax*2]
0x180046bb2  jmp     short loc_180046BC0
0x180046bb4  lea     rdx, LocaleName
0x180046bbb  mov     eax, 2
0x180046bc0  mov     [rbp+57h+var_78], eax
0x180046bc3  lea     rcx, _TraceLoggingMetadata
0x180046bca  mov     [rbp+57h+var_80], rdx
0x180046bce  lea     rax, aIkeoptionalcon_16; "IkeOptionalConstructCoexistenceVendorId"
0x180046bd5  mov     [rbp+57h+var_70], rax
0x180046bd9  lea     rdx, [rbp+57h+var_60]
0x180046bdd  movzx   eax, cs:word_180166E9A
0x180046be4  xor     r9d, r9d
0x180046be7  mov     dword ptr [rbp+57h+var_60+4], eax
0x180046bea  xor     r8d, r8d
0x180046bed  mov     rax, cs:off_180173280
0x180046bf4  mov     [rbp+57h+var_B0], rax
0x180046bf8  mov     [rbp+57h+var_74], ebx
0x180046bfb  mov     [rbp+57h+var_68], 28h ; '('
0x180046c03  mov     dword ptr [rbp+57h+var_60], 0B000000h
0x180046c0a  mov     [rbp+57h+var_58], 1
0x180046c12  movzx   eax, word ptr [rax]
0x180046c15  mov     [rbp+57h+var_A8], eax
0x180046c18  lea     rax, dword_180166EA4
0x180046c1f  mov     [rbp+57h+var_A0], rax
0x180046c23  mov     rax, r14
0x180046c26  sub     eax, ecx
0x180046c28  mov     [rbp+57h+var_A4], 2
0x180046c2f  mov     [rbp+57h+var_98], 2Dh ; '-'
0x180046c36  mov     [rbp+57h+var_94], 1
0x180046c3d  mov     [rbp+57h+var_C8], eax
0x180046c40  mov     eax, [rbp+57h+var_C8]
0x180046c43  mov     rcx, cs:qword_180173298
0x180046c4a  lea     rax, [rbp+57h+var_B0]
0x180046c4e  mov     [rsp+100h+var_D8], rax
0x180046c53  mov     dword ptr [rsp+100h+var_E0], 5
0x180046c5b  call    cs:__imp_EtwEventWriteTransfer
0x180046c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c68  lea     rax, WPP_GLOBAL_Control
0x180046c6f  cmp     rcx, rax
0x180046c72  jz      loc_180046D21
0x180046c78  cmp     byte ptr [rcx+19h], 4
0x180046c7c  jb      loc_180046D21
0x180046c82  test    byte ptr [rcx+1Ch], 10h
0x180046c86  jz      loc_180046D21
0x180046c8c  mov     rdx, cs:gIkeExtGlobals
0x180046c93  test    rdx, rdx
0x180046c96  jz      short loc_180046CBE
0x180046c98  mov     eax, [rdx+0D88h]
0x180046c9e  cmp     eax, 0FFFFFFFFh
0x180046ca1  jz      short loc_180046CBE
0x180046ca3  mov     ecx, eax; dwTlsIndex
0x180046ca5  call    cs:__imp_TlsGetValue
0x180046cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180046cb2  mov     r8, rax
0x180046cb5  mov     rdx, cs:gIkeExtGlobals
0x180046cbc  jmp     short loc_180046CC1
0x180046cbe  mov     r8, rbx
0x180046cc1  xor     eax, eax
0x180046cc3  lea     rbx, [r8+8]
0x180046cc7  test    r8, r8
0x180046cca  cmovz   rbx, rax
0x180046cce  test    rdx, rdx
0x180046cd1  jz      short loc_180046CF7
0x180046cd3  mov     eax, [rdx+0D88h]
0x180046cd9  cmp     eax, 0FFFFFFFFh
0x180046cdc  jz      short loc_180046CF7
0x180046cde  mov     ecx, eax; dwTlsIndex
0x180046ce0  call    cs:__imp_TlsGetValue
0x180046ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ced  test    rax, rax
0x180046cf0  jz      short loc_180046CF7
0x180046cf2  mov     r9, [rax]
0x180046cf5  jmp     short loc_180046CFA
0x180046cf7  xor     r9d, r9d
0x180046cfa  mov     eax, [r15+24Ch]
0x180046d01  lea     r8, WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids
0x180046d08  mov     rcx, [rcx+10h]
0x180046d0c  mov     edx, 12h
0x180046d11  mov     dword ptr [rsp+100h+var_D8], eax
0x180046d15  mov     [rsp+100h+var_E0], rbx
0x180046d1a  call    WPP_SF_iSL
0x180046d1f  xor     ebx, ebx
0x180046d21  mov     eax, cs:dword_180173278
0x180046d27  cmp     eax, 4
0x180046d2a  jbe     loc_180046E75
0x180046d30  mov     rax, cs:gIkeExtGlobals
0x180046d37  test    rax, rax
0x180046d3a  jz      short loc_180046D65
0x180046d3c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046d42  cmp     ecx, 0FFFFFFFFh
0x180046d45  jz      short loc_180046D65
0x180046d47  call    cs:__imp_TlsGetValue
0x180046d4d  test    rax, rax
0x180046d50  jz      short loc_180046D5E
0x180046d52  mov     rcx, [rax]
0x180046d55  mov     rax, cs:gIkeExtGlobals
0x180046d5c  jmp     short loc_180046D68
0x180046d5e  mov     rax, cs:gIkeExtGlobals
0x180046d65  mov     rcx, rbx
0x180046d68  mov     [rbp+57h+var_60], rcx
0x180046d6c  lea     rcx, [rbp+57h+var_60]
0x180046d70  mov     [rbp+57h+var_90], rcx
0x180046d74  mov     [rbp+57h+var_88], 8
0x180046d7c  test    rax, rax
0x180046d7f  jz      short loc_180046DC5
0x180046d81  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046d87  cmp     ecx, 0FFFFFFFFh
0x180046d8a  jz      short loc_180046DC5
0x180046d8c  call    cs:__imp_TlsGetValue
0x180046d92  test    rax, rax
0x180046d95  lea     rdx, [rax+8]
0x180046d99  cmovz   rdx, rbx
0x180046d9d  test    rdx, rdx
0x180046da0  jz      short loc_180046DC5
0x180046da2  mov     rax, rdi
0x180046da5  nop     word ptr [rax+rax+00000000h]
0x180046db0  cmp     word ptr [rdx+rax*2+2], 0
0x180046db6  lea     rax, [rax+1]
0x180046dba  jnz     short loc_180046DB0
0x180046dbc  lea     eax, ds:2[rax*2]
0x180046dc3  jmp     short loc_180046DD1
0x180046dc5  lea     rdx, LocaleName
0x180046dcc  mov     eax, 2
0x180046dd1  mov     [rbp+57h+var_78], eax
0x180046dd4  lea     rcx, _TraceLoggingMetadata
0x180046ddb  mov     eax, [r15+24Ch]
0x180046de2  xor     r9d, r9d
0x180046de5  mov     [rbp+57h+var_C8], eax
0x180046de8  xor     r8d, r8d
0x180046deb  mov     [rbp+57h+var_80], rdx
0x180046def  lea     rax, [rbp+57h+var_C8]
0x180046df3  mov     [rbp+57h+var_70], rax
0x180046df7  lea     rdx, [rbp+57h+var_C0]
0x180046dfb  movzx   eax, cs:word_18016462D
0x180046e02  mov     [rbp+57h+var_BC], eax
0x180046e05  mov     rax, cs:off_180173280
0x180046e0c  mov     [rbp+57h+var_B0], rax
0x180046e10  mov     [rbp+57h+var_74], ebx
0x180046e13  mov     [rbp+57h+var_68], 4
0x180046e1b  mov     [rbp+57h+var_C0], 0B000000h
0x180046e22  mov     [rbp+57h+var_B8], rbx
0x180046e26  movzx   eax, word ptr [rax]
0x180046e29  mov     [rbp+57h+var_A8], eax
0x180046e2c  lea     rax, byte_180164637
0x180046e33  mov     [rbp+57h+var_A0], rax
0x180046e37  mov     rax, r14
0x180046e3a  sub     eax, ecx
0x180046e3c  mov     [rbp+57h+var_A4], 2
0x180046e43  mov     [rbp+57h+var_98], 3Dh ; '='
0x180046e4a  mov     [rbp+57h+var_94], 1
0x180046e51  mov     dword ptr [rbp+57h+var_D0], eax
0x180046e54  mov     eax, dword ptr [rbp+57h+var_D0]
0x180046e57  mov     rcx, cs:qword_180173298
0x180046e5e  lea     rax, [rbp+57h+var_B0]
0x180046e62  mov     [rsp+100h+var_D8], rax
0x180046e67  mov     dword ptr [rsp+100h+var_E0], 5
0x180046e6f  call    cs:__imp_EtwEventWriteTransfer
0x180046e75  cmp     dword ptr [r15+248h], 2
0x180046e7d  mov     r8d, ebx
0x180046e80  mov     r9d, [r15+24Ch]
0x180046e87  mov     edx, 0Ah
0x180046e8c  setz    r8b
0x180046e90  mov     dword ptr [rsp+100h+var_E0], ebx
0x180046e94  mov     rcx, r13
0x180046e97  call    IkeConstructVendor
0x180046e9c  mov     r14, rax
0x180046e9f  test    rax, rax
0x180046ea2  jnz     loc_1800472A8
0x180046ea8  cmp     [r15+248h], eax
0x180046eaf  jnz     short loc_180046ED7
0x180046eb1  test    byte ptr [r15+420h], 1
0x180046eb9  jz      short loc_180046ED7
0x180046ebb  mov     r8, r12
0x180046ebe  mov     rdx, rsi
0x180046ec1  mov     r12d, 1
0x180046ec7  mov     ecx, r12d
0x180046eca  call    IkeIsKeyModEnabledForTraffic
0x180046ecf  test    eax, eax
0x180046ed1  cmovnz  ebx, r12d
0x180046ed5  jmp     short loc_180046EDD
0x180046ed7  mov     r12d, 1
0x180046edd  cmp     dword ptr [r15+248h], 1
0x180046ee5  jz      loc_1800470B8
0x180046eeb  test    ebx, ebx
0x180046eed  jnz     loc_1800470B8
0x180046ef3  mov     rbx, cs:WPP_GLOBAL_Control
0x180046efa  lea     rax, WPP_GLOBAL_Control
0x180046f01  cmp     rbx, rax
0x180046f04  jz      short loc_180046F67
0x180046f06  cmp     byte ptr [rbx+19h], 4
0x180046f0a  jb      short loc_180046F67
0x180046f0c  test    byte ptr [rbx+1Ch], 10h
0x180046f10  jz      short loc_180046F67
0x180046f12  mov     rax, cs:gIkeExtGlobals
0x180046f19  test    rax, rax
0x180046f1c  jz      short loc_180046F40
0x180046f1e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046f24  cmp     ecx, 0FFFFFFFFh
0x180046f27  jz      short loc_180046F40
0x180046f29  call    cs:__imp_TlsGetValue
0x180046f2f  mov     rbx, cs:WPP_GLOBAL_Control
0x180046f36  test    rax, rax
0x180046f39  jz      short loc_180046F40
0x180046f3b  mov     rsi, [rax]
0x180046f3e  jmp     short loc_180046F42
0x180046f40  xor     esi, esi
0x180046f42  mov     rbx, [rbx+10h]
0x180046f46  call    IkeGetTlsPeerAddr
0x180046f4b  mov     edx, 13h
0x180046f50  mov     [rsp+100h+var_E0], rax
0x180046f55  mov     r9, rsi
0x180046f58  lea     r8, WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids
0x180046f5f  mov     rcx, rbx
0x180046f62  call    WPP_SF_iS
0x180046f67  mov     eax, cs:dword_180173278
0x180046f6d  cmp     eax, 4
0x180046f70  jbe     loc_1800472A8
0x180046f76  mov     rax, cs:gIkeExtGlobals
0x180046f7d  test    rax, rax
0x180046f80  jz      short loc_180046FAD
0x180046f82  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046f88  cmp     ecx, 0FFFFFFFFh
0x180046f8b  jz      short loc_180046FAD
0x180046f8d  call    cs:__imp_TlsGetValue
0x180046f93  test    rax, rax
0x180046f96  jz      short loc_180046FA6
0x180046f98  mov     rcx, [rax]
0x180046f9b  xor     esi, esi
0x180046f9d  mov     rax, cs:gIkeExtGlobals
0x180046fa4  jmp     short loc_180046FB1
0x180046fa6  mov     rax, cs:gIkeExtGlobals
0x180046fad  xor     esi, esi
0x180046faf  mov     ecx, esi
0x180046fb1  mov     [rbp+57h+var_60], rcx
0x180046fb5  lea     rcx, [rbp+57h+var_60]
  ... truncated ...
```
