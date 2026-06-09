# IkeConstructSspiPeerIdUnknownInitiator

- ea: `0x180043270`
- end: `0x180043fa2`
- name: `IkeConstructSspiPeerIdUnknownInitiator`
- size: `3378`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, installer_update`

## callers

- `0x1800416f0`

## callees

- `0x18000251c`
- `0x1800061ec`
- `0x180008388`
- `0x180010770`
- `0x18001fab0`
- `0x180031268`
- `0x180043270`
- `0x180045400`
- `0x1800460c0`
- `0x180046510`
- `0x180046ab0`
- `0x180047450`
- `0x180047bb0`
- `0x180049448`
- `0x18004ecc0`
- `0x180050850`
- `0x18007ca4c`
- `0x18007f2e8`
- `0x1800b4e30`
- `0x1800c1268`
- `0x1800c2a08`
- `0x1800c6c54`
- `0x1800e2aac`
- `0x1800fbcc4`
- `0x180102470`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004330b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043350`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800434c4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043509`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043690`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800436f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004388b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043a15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043a5a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043b8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043bd3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043e90`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004330b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043350`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800434c4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043509`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043690`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800436f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004388b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043a15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043a5a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043b8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043bd3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180043e90`
- `ntdll!EtwEventWriteTransfer` at `0x180043418`
- `ntdll!EtwEventWriteTransfer` at `0x1800435df`
- `ntdll!EtwEventWriteTransfer` at `0x1800437cd`
- `ntdll!EtwEventWriteTransfer` at `0x180043b23`
- `ntdll!EtwEventWriteTransfer` at `0x180043ca0`
- `ntdll!EtwEventWriteTransfer` at `0x180043f68`
- `ntdll!EtwEventWriteTransfer` at `0x180043418`
- `ntdll!EtwEventWriteTransfer` at `0x1800435df`
- `ntdll!EtwEventWriteTransfer` at `0x1800437cd`
- `ntdll!EtwEventWriteTransfer` at `0x180043b23`
- `ntdll!EtwEventWriteTransfer` at `0x180043ca0`
- `ntdll!EtwEventWriteTransfer` at `0x180043f68`

## pseudocode

```c
__int64 __fastcall IkeConstructSspiPeerIdUnknownInitiator(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // r12
  LPCRITICAL_SECTION v3; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v6; // rcx
  DWORD v7; // ecx
  char *v8; // rax
  const WCHAR *v9; // rdx
  __int64 v10; // rax
  bool v11; // zf
  int v12; // eax
  _DWORD *v13; // r8
  _QWORD *v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // r14
  LPCRITICAL_SECTION v17; // rax
  DWORD v18; // ecx
  __int64 *v19; // rax
  __int64 v20; // rcx
  DWORD v21; // ecx
  char *v22; // rax
  const WCHAR *v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rsi
  LPCRITICAL_SECTION v27; // rax
  DWORD v28; // ecx
  __int64 *v29; // rax
  __int64 v30; // rcx
  DWORD v31; // ecx
  char *v32; // rax
  const WCHAR *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  __int64 inited; // rbx
  LPCRITICAL_SECTION v37; // rax
  DWORD v38; // ecx
  __int64 *v39; // rax
  __int64 v40; // rcx
  LPCRITICAL_SECTION v41; // rax
  DWORD v42; // ecx
  __int64 *v43; // rax
  __int64 v44; // rcx
  DWORD v45; // ecx
  char *v46; // rax
  const WCHAR *v47; // rdx
  __int64 v48; // rax
  int v49; // eax
  __int64 SspiContext; // rbx
  LPCRITICAL_SECTION v51; // rax
  DWORD v52; // ecx
  __int64 *v53; // rax
  __int64 v54; // rcx
  DWORD v55; // ecx
  char *v56; // rax
  const WCHAR *v57; // rdx
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // r8
  unsigned int IPVersion; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  DWORD v64; // ecx
  char *v65; // rax
  const WCHAR *v66; // rdx
  int v67; // eax
  __int64 v69; // [rsp+38h] [rbp-61h] BYREF
  int v70; // [rsp+40h] [rbp-59h] BYREF
  int v71; // [rsp+44h] [rbp-55h]
  __int64 v72; // [rsp+48h] [rbp-51h]
  char *v73; // [rsp+50h] [rbp-49h] BYREF
  int v74; // [rsp+58h] [rbp-41h]
  int v75; // [rsp+5Ch] [rbp-3Dh]
  int *v76; // [rsp+60h] [rbp-39h]
  int v77; // [rsp+68h] [rbp-31h]
  int v78; // [rsp+6Ch] [rbp-2Dh]
  __int64 *v79; // [rsp+70h] [rbp-29h]
  __int64 v80; // [rsp+78h] [rbp-21h]
  const WCHAR *v81; // [rsp+80h] [rbp-19h]
  int v82; // [rsp+88h] [rbp-11h]
  int v83; // [rsp+8Ch] [rbp-Dh]
  const char *v84; // [rsp+90h] [rbp-9h]
  __int64 v85; // [rsp+98h] [rbp-1h]

  v1 = a1;
  v2 = -1;
  if ( (unsigned int)dword_180173278 <= 5 )
    goto LABEL_20;
  a1 = qword_180173290;
  if ( (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v3 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v3 = gIkeExtGlobals;
LABEL_9:
    v6 = 0;
    goto LABEL_10;
  }
  v6 = *Value;
  v3 = gIkeExtGlobals;
LABEL_10:
  v69 = v6;
  v79 = &v69;
  v80 = 8;
  if ( !v3 )
    goto LABEL_18;
  v7 = (DWORD)v3[86].LockSemaphore;
  if ( v7 == -1 )
    goto LABEL_18;
  v8 = (char *)TlsGetValue(v7);
  v9 = (const WCHAR *)(v8 + 8);
  if ( !v8 )
    v9 = 0;
  if ( v9 )
  {
    v10 = -1;
    do
      v11 = v9[++v10] == 0;
    while ( !v11 );
    v12 = 2 * v10 + 2;
  }
  else
  {
LABEL_18:
    v9 = &LocaleName;
    v12 = 2;
  }
  v82 = v12;
  v71 = 5;
  v73 = off_180173280;
  v81 = v9;
  v83 = 0;
  v84 = "IkeConstructSspiPeerIdUnknownInitiator";
  v85 = 39;
  v70 = 184549376;
  v72 = 1;
  v74 = *(unsigned __int16 *)off_180173280;
  v75 = 2;
  v76 = &dword_180166EA4;
  v77 = 45;
  v78 = 1;
  EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
LABEL_20:
  v13 = *(_DWORD **)(v1 + 608);
  switch ( *v13 )
  {
    case 0:
      inited = IkeConstructCrypto(v1 + 696, v1 + 752);
      if ( !inited )
      {
        inited = IkeConstructMMSA((int)v1 + 696, (int)v1 + 584, *(_QWORD *)(v1 + 736), 0, 0);
        if ( !inited )
        {
          inited = IkeConstructAuth(
                     v1 + 696,
                     *(unsigned int *)(**(_QWORD **)(v1 + 736) + 4LL),
                     *(_QWORD *)(**(_QWORD **)(v1 + 736) + 8LL),
                     *(_QWORD *)(v1 + 736) + 24LL);
          if ( !inited )
          {
            inited = IkeConstructNonce(v1 + 584, v1 + 696, v60, v1 + 880);
            if ( !inited )
            {
              IPVersion = IkeAddrGetIPVersion(v1 + 376);
              inited = IkeConstructStandardVendorIds(v1 + 696, v1 + 584, IPVersion);
              if ( !inited )
              {
                inited = IkeOptionalConstructCoexistenceVendorId(v1 + 696, v1 + 376, *(_QWORD *)(v1 + 1008) + 184LL, v1);
                if ( !inited )
                {
                  inited = IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId(v1 + 696, v62, v63, v1);
                  if ( !inited )
                  {
                    inited = IkeOptionalConstructNatDisc(v1 + 696, v1);
                    if ( !inited )
                    {
                      inited = IkeOptionalConstructKEInitiator(v1 + 696, v1);
                      if ( !inited )
                        **(_DWORD **)(v1 + 608) = 1;
                    }
                  }
                }
              }
            }
          }
        }
      }
      break;
    case 1:
      inited = IkeValidateKePayloadReceived(v1);
      if ( inited )
        break;
      if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
      {
LABEL_111:
        SspiContext = IkeGetSspiContext(v1, 0, 0);
        if ( (unsigned int)dword_180173278 <= 5
          || (qword_180173288 & 1) == 0
          || (qword_180173290 & 1) != qword_180173290 )
        {
LABEL_130:
          inited = IkeReturnError(SspiContext, "IkeGetSspiContextAuthIp");
          if ( !inited )
          {
            inited = IkeConstructCrypto(v1 + 696, v1 + 752);
            if ( !inited )
            {
              inited = IkeConstructSspi(v1, v1 + 696, *(_QWORD *)(v1 + 960));
              if ( !inited )
                **(_DWORD **)(v1 + 608) = 2;
            }
          }
          break;
        }
        v51 = gIkeExtGlobals;
        if ( gIkeExtGlobals )
        {
          v52 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v52 != -1 )
          {
            v53 = (__int64 *)TlsGetValue(v52);
            if ( v53 )
            {
              v54 = *v53;
              v51 = gIkeExtGlobals;
LABEL_120:
              v69 = v54;
              v79 = &v69;
              v80 = 8;
              if ( !v51 )
                goto LABEL_128;
              v55 = (DWORD)v51[86].LockSemaphore;
              if ( v55 == -1 )
                goto LABEL_128;
              v56 = (char *)TlsGetValue(v55);
              v57 = (const WCHAR *)(v56 + 8);
              if ( !v56 )
                v57 = 0;
              if ( v57 )
              {
                v58 = -1;
                do
                  v11 = v57[++v58] == 0;
                while ( !v11 );
                v59 = 2 * v58 + 2;
              }
              else
              {
LABEL_128:
                v57 = &LocaleName;
                v59 = 2;
              }
              v82 = v59;
              v71 = 5;
              v73 = off_180173280;
              v81 = v57;
              v83 = 0;
              v84 = "IkeGetSspiContextAuthIp";
              v85 = 24;
              v70 = 184549376;
              v72 = 1;
              v74 = *(unsigned __int16 *)off_180173280;
              v76 = (int *)byte_180166E6B;
              v75 = 2;
              v77 = 45;
              v78 = 1;
              EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
              goto LABEL_130;
            }
            v51 = gIkeExtGlobals;
          }
        }
        v54 = 0;
        goto LABEL_120;
      }
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
LABEL_101:
            v69 = v44;
            v79 = &v69;
            v80 = 8;
            if ( !v41 )
              goto LABEL_109;
            v45 = (DWORD)v41[86].LockSemaphore;
            if ( v45 == -1 )
              goto LABEL_109;
            v46 = (char *)TlsGetValue(v45);
            v47 = (const WCHAR *)(v46 + 8);
            if ( !v46 )
              v47 = 0;
            if ( v47 )
            {
              v48 = -1;
              do
                v11 = v47[++v48] == 0;
              while ( !v11 );
              v49 = 2 * v48 + 2;
            }
            else
            {
LABEL_109:
              v47 = &LocaleName;
              v49 = 2;
            }
            v82 = v49;
            v71 = 5;
            v73 = off_180173280;
            v81 = v47;
            v83 = 0;
            v84 = "IkeGetSspiContextAuthIp";
            v85 = 24;
            v70 = 184549376;
            v72 = 1;
            v74 = *(unsigned __int16 *)off_180173280;
            v76 = &dword_180166EA4;
            v75 = 2;
            v77 = 45;
            v78 = 1;
            EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
            goto LABEL_111;
          }
          v41 = gIkeExtGlobals;
        }
      }
      v44 = 0;
      goto LABEL_101;
    case 2:
      inited = IkeConstructCrypto(v1 + 696, v1 + 752);
      if ( !inited )
        inited = IkeConstructSspi(v1, v1 + 696, *(_QWORD *)(v1 + 960));
      break;
    case 3:
      IkeUpdateNatState(v1 + 624, v1 + 584, v1);
      IkeCheckSAFloatInitiator(v1);
      inited = IkeInitSACrypto(v1 + 752, 320LL * **(unsigned int **)(v1 + 744) + *(_QWORD *)(v1 + 744) + 16LL, v1);
      if ( !inited )
      {
        inited = IkeConstructCrypto(v1 + 696, v1 + 752);
        if ( !inited )
        {
          inited = IkeConstructMMHash(v1 + 696, v1 + 752, 1);
          if ( !inited )
          {
            inited = IkeBeginQMInitiator(v1 + 696, v1);
            if ( !inited )
              **(_DWORD **)(v1 + 608) = 4;
          }
        }
      }
      break;
    case 4:
      *v13 = 5;
      v14 = (_QWORD *)(v1 + 944);
      v15 = *(_QWORD *)(v1 + 944);
      v16 = 0;
      if ( (unsigned int)dword_180173278 <= 5
        || (a1 = qword_180173290, (qword_180173288 & 1) == 0)
        || (qword_180173290 & 1) != qword_180173290 )
      {
LABEL_45:
        if ( (_QWORD *)*v14 != v14 && *(_QWORD **)v15 == v14 )
        {
          a1 = *(unsigned int *)(v15 + 544);
          if ( (_DWORD)a1 )
          {
            a1 = (unsigned int)(a1 - 1);
            if ( (unsigned int)a1 > 1 || *(_QWORD *)(v15 + 552) )
              goto LABEL_51;
          }
          else if ( !*(_QWORD *)(v15 + 552) )
          {
LABEL_51:
            v26 = 0;
            v16 = v15;
            goto LABEL_52;
          }
        }
        v26 = WfpReportSysErrorAsWinError(a1, "IkeGetQMFromMM", 13804, 1);
LABEL_52:
        if ( (unsigned int)dword_180173278 <= 5
          || (qword_180173288 & 1) == 0
          || (qword_180173290 & 1) != qword_180173290 )
        {
LABEL_73:
          inited = IkeReturnError(v26, "IkeGetQMFromMM");
          if ( !inited )
          {
            inited = IkeConstructQM(v16 + 504, v1, v16);
            if ( !inited )
            {
              inited = IkeSendQMPacket((int)v16 + 504, 0, v1, v16, 0);
              if ( !inited )
                IkeFreePacket(v1 + 696);
            }
          }
          break;
        }
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
LABEL_63:
              v69 = v30;
              v79 = &v69;
              v80 = 8;
              if ( !v27 )
                goto LABEL_71;
              v31 = (DWORD)v27[86].LockSemaphore;
              if ( v31 == -1 )
                goto LABEL_71;
              v32 = (char *)TlsGetValue(v31);
              v33 = (const WCHAR *)(v32 + 8);
              if ( !v32 )
                v33 = 0;
              if ( v33 )
              {
                v34 = -1;
                do
                  v11 = v33[++v34] == 0;
                while ( !v11 );
                v35 = 2 * v34 + 2;
              }
              else
              {
LABEL_71:
                v33 = &LocaleName;
                v35 = 2;
              }
              v82 = v35;
              v81 = v33;
              v84 = "IkeGetQMFromMM";
              v71 = 5;
              v73 = off_180173280;
              v83 = 0;
              v85 = 15;
              v70 = 184549376;
              v72 = 1;
              v74 = *(unsigned __int16 *)off_180173280;
              v76 = (int *)byte_180166E6B;
              v75 = 2;
              v77 = 45;
              v78 = 1;
              EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
              goto LABEL_73;
            }
            v27 = gIkeExtGlobals;
          }
        }
        v30 = 0;
        goto LABEL_63;
      }
      v17 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v18 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v18 != -1 )
        {
          v19 = (__int64 *)TlsGetValue(v18);
          if ( v19 )
          {
            v20 = *v19;
            v17 = gIkeExtGlobals;
LABEL_35:
            v69 = v20;
            v79 = &v69;
            v80 = 8;
            if ( !v17 )
              goto LABEL_43;
            v21 = (DWORD)v17[86].LockSemaphore;
            if ( v21 == -1 )
              goto LABEL_43;
            v22 = (char *)TlsGetValue(v21);
            v23 = (const WCHAR *)(v22 + 8);
            if ( !v22 )
              v23 = 0;
            if ( v23 )
            {
              v24 = -1;
              do
                v11 = v23[++v24] == 0;
              while ( !v11 );
              v25 = 2 * v24 + 2;
            }
            else
            {
LABEL_43:
              v23 = &LocaleName;
              v25 = 2;
            }
            v82 = v25;
            v81 = v23;
            v84 = "IkeGetQMFromMM";
            v71 = 5;
            v73 = off_180173280;
            v83 = 0;
            v85 = 15;
            v70 = 184549376;
            v72 = 1;
            v74 = *(unsigned __int16 *)off_180173280;
            v76 = &dword_180166EA4;
            v75 = 2;
            v77 = 45;
            v78 = 1;
            EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
            goto LABEL_45;
          }
          v17 = gIkeExtGlobals;
        }
      }
      v20 = 0;
      goto LABEL_35;
    default:
      __fastfail(5u);
  }
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(inited, "IkeConstructSspiPeerIdUnknownInitiator");
  v37 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_145;
  v38 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v38 == -1 )
    goto LABEL_145;
  v39 = (__int64 *)TlsGetValue(v38);
  if ( !v39 )
  {
    v37 = gIkeExtGlobals;
LABEL_145:
    v40 = 0;
    goto LABEL_146;
  }
  v40 = *v39;
  v37 = gIkeExtGlobals;
LABEL_146:
  v69 = v40;
  v79 = &v69;
  v80 = 8;
  if ( !v37 )
    goto LABEL_153;
  v64 = (DWORD)v37[86].LockSemaphore;
  if ( v64 == -1 )
    goto LABEL_153;
  v65 = (char *)TlsGetValue(v64);
  v66 = (const WCHAR *)(v65 + 8);
  if ( !v65 )
    v66 = 0;
  if ( v66 )
  {
    do
      v11 = v66[++v2] == 0;
    while ( !v11 );
    v67 = 2 * v2 + 2;
  }
  else
  {
LABEL_153:
    v66 = &LocaleName;
    v67 = 2;
  }
  v82 = v67;
  v71 = 5;
  v73 = off_180173280;
  v81 = v66;
  v83 = 0;
  v84 = "IkeConstructSspiPeerIdUnknownInitiator";
  v85 = 39;
  v70 = 184549376;
  v72 = 1;
  v74 = *(unsigned __int16 *)off_180173280;
  v75 = 2;
  v76 = (int *)byte_180166E6B;
  v77 = 45;
  v78 = 1;
  EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
  return IkeReturnError(inited, "IkeConstructSspiPeerIdUnknownInitiator");
}

```

## disassembly

```asm
0x180043270  push    rbp
0x180043272  push    rbx
0x180043273  push    rsi
0x180043274  push    rdi
0x180043275  push    r12
0x180043277  push    r13
0x180043279  push    r14
0x18004327b  push    r15
0x18004327d  lea     rbp, [rsp-1Fh]
0x180043282  sub     rsp, 0B8h
0x180043289  mov     rax, cs:__security_cookie
0x180043290  xor     rax, rsp
0x180043293  mov     [rbp+57h+var_50], rax
0x180043297  mov     eax, cs:dword_180173278
0x18004329d  lea     rsi, aIkeconstructss_3; "IkeConstructSspiPeerIdUnknownInitiator"
0x1800432a4  xor     r15d, r15d
0x1800432a7  lea     r14, dword_180166EA4
0x1800432ae  lea     r13, _TraceLoggingMetadataEnd
0x1800432b5  mov     rdi, rcx
0x1800432b8  lea     rbx, _TraceLoggingMetadata
0x1800432bf  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800432c6  cmp     eax, 5
0x1800432c9  jbe     loc_18004341E
0x1800432cf  mov     rcx, cs:qword_180173290
0x1800432d6  mov     rax, cs:qword_180173288
0x1800432dd  test    al, 1
0x1800432df  jz      loc_18004341E
0x1800432e5  mov     rax, rcx
0x1800432e8  and     eax, 1
0x1800432eb  cmp     rax, rcx
0x1800432ee  jnz     loc_18004341E
0x1800432f4  mov     rax, cs:gIkeExtGlobals
0x1800432fb  test    rax, rax
0x1800432fe  jz      short loc_180043329
0x180043300  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180043306  cmp     ecx, 0FFFFFFFFh
0x180043309  jz      short loc_180043329
0x18004330b  call    cs:__imp_TlsGetValue
0x180043311  test    rax, rax
0x180043314  jz      short loc_180043322
0x180043316  mov     rcx, [rax]
0x180043319  mov     rax, cs:gIkeExtGlobals
0x180043320  jmp     short loc_18004332C
0x180043322  mov     rax, cs:gIkeExtGlobals
0x180043329  mov     rcx, r15
0x18004332c  mov     [rbp+57h+var_B8], rcx
0x180043330  lea     rcx, [rbp+57h+var_B8]
0x180043334  mov     [rbp+57h+var_80], rcx
0x180043338  mov     [rbp+57h+var_78], 8
0x180043340  test    rax, rax
0x180043343  jz      short loc_180043385
0x180043345  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004334b  cmp     ecx, 0FFFFFFFFh
0x18004334e  jz      short loc_180043385
0x180043350  call    cs:__imp_TlsGetValue
0x180043356  test    rax, rax
0x180043359  lea     rdx, [rax+8]
0x18004335d  cmovz   rdx, r15
0x180043361  test    rdx, rdx
0x180043364  jz      short loc_180043385
0x180043366  mov     rax, r12
0x180043369  nop     dword ptr [rax+00000000h]
0x180043370  cmp     [rdx+rax*2+2], r15w
0x180043376  lea     rax, [rax+1]
0x18004337a  jnz     short loc_180043370
0x18004337c  lea     eax, ds:2[rax*2]
0x180043383  jmp     short loc_180043391
0x180043385  lea     rdx, LocaleName
0x18004338c  mov     eax, 2
0x180043391  mov     [rbp+57h+var_68], eax
0x180043394  xor     r9d, r9d
0x180043397  movzx   eax, cs:word_180166E9A
0x18004339e  xor     r8d, r8d
0x1800433a1  mov     [rbp+57h+var_AC], eax
0x1800433a4  mov     rax, cs:off_180173280
0x1800433ab  mov     [rbp+57h+var_A0], rax
0x1800433af  mov     [rbp+57h+var_70], rdx
0x1800433b3  lea     rdx, [rbp+57h+var_B0]
0x1800433b7  mov     [rbp+57h+var_64], r15d
0x1800433bb  mov     [rbp+57h+var_60], rsi
0x1800433bf  mov     [rbp+57h+var_58], 27h ; '''
0x1800433c7  mov     [rbp+57h+var_B0], 0B000000h
0x1800433ce  mov     [rbp+57h+var_A8], 1
0x1800433d6  movzx   eax, word ptr [rax]
0x1800433d9  mov     [rbp+57h+var_98], eax
0x1800433dc  mov     rax, r13
0x1800433df  sub     eax, ebx
0x1800433e1  mov     [rbp+57h+var_94], 2
0x1800433e8  mov     [rbp+57h+var_90], r14
0x1800433ec  mov     [rbp+57h+var_88], 2Dh ; '-'
0x1800433f3  mov     [rbp+57h+var_84], 1
0x1800433fa  mov     [rbp+57h+var_C0], eax
0x1800433fd  mov     eax, [rbp+57h+var_C0]
0x180043400  mov     rcx, cs:qword_180173298
0x180043407  lea     rax, [rbp+57h+var_A0]
0x18004340b  mov     [rsp+0F0h+var_C8], rax
0x180043410  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180043418  call    cs:__imp_EtwEventWriteTransfer
0x18004341e  mov     r8, [rdi+260h]
0x180043425  lea     rsi, byte_180166E6B
0x18004342c  mov     edx, [r8]
0x18004342f  test    edx, edx
0x180043431  jz      loc_180043D17
0x180043437  sub     edx, 1
0x18004343a  jz      loc_1800439AF
0x180043440  sub     edx, 1
0x180043443  jz      loc_180043972
0x180043449  sub     edx, 1
0x18004344c  jz      loc_1800438A9
0x180043452  cmp     edx, 1
0x180043455  jz      short loc_18004345E
0x180043457  mov     ecx, 5
0x18004345c  int     29h; Win8: RtlFailFast(ecx)
0x18004345e  mov     dword ptr [r8], 5
0x180043465  lea     rsi, [rdi+3B0h]
0x18004346c  mov     eax, cs:dword_180173278
0x180043472  lea     rdx, aIkegetqmfrommm; "IkeGetQMFromMM"
0x180043479  mov     rbx, [rsi]
0x18004347c  mov     r14, r15
0x18004347f  cmp     eax, 5
0x180043482  jbe     loc_1800435EC
0x180043488  mov     rcx, cs:qword_180173290
0x18004348f  mov     rax, cs:qword_180173288
0x180043496  test    al, 1
0x180043498  jz      loc_1800435EC
0x18004349e  mov     rax, rcx
0x1800434a1  and     eax, 1
0x1800434a4  cmp     rax, rcx
0x1800434a7  jnz     loc_1800435EC
0x1800434ad  mov     rax, cs:gIkeExtGlobals
0x1800434b4  test    rax, rax
0x1800434b7  jz      short loc_1800434E2
0x1800434b9  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800434bf  cmp     ecx, 0FFFFFFFFh
0x1800434c2  jz      short loc_1800434E2
0x1800434c4  call    cs:__imp_TlsGetValue
0x1800434ca  test    rax, rax
0x1800434cd  jz      short loc_1800434DB
0x1800434cf  mov     rcx, [rax]
0x1800434d2  mov     rax, cs:gIkeExtGlobals
0x1800434d9  jmp     short loc_1800434E5
0x1800434db  mov     rax, cs:gIkeExtGlobals
0x1800434e2  mov     rcx, r15
0x1800434e5  mov     [rbp+57h+var_B8], rcx
0x1800434e9  lea     rcx, [rbp+57h+var_B8]
0x1800434ed  mov     [rbp+57h+var_80], rcx
0x1800434f1  mov     [rbp+57h+var_78], 8
0x1800434f9  test    rax, rax
0x1800434fc  jz      short loc_180043537
0x1800434fe  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180043504  cmp     ecx, 0FFFFFFFFh
0x180043507  jz      short loc_180043537
0x180043509  call    cs:__imp_TlsGetValue
0x18004350f  test    rax, rax
0x180043512  lea     rdx, [rax+8]
0x180043516  cmovz   rdx, r15
0x18004351a  test    rdx, rdx
0x18004351d  jz      short loc_180043537
0x18004351f  mov     rax, r12
0x180043522  cmp     [rdx+rax*2+2], r15w
0x180043528  lea     rax, [rax+1]
0x18004352c  jnz     short loc_180043522
0x18004352e  lea     eax, ds:2[rax*2]
0x180043535  jmp     short loc_180043543
0x180043537  lea     rdx, LocaleName
0x18004353e  mov     eax, 2
0x180043543  mov     [rbp+57h+var_68], eax
0x180043546  lea     rcx, _TraceLoggingMetadata
0x18004354d  mov     [rbp+57h+var_70], rdx
0x180043551  lea     rax, aIkegetqmfrommm; "IkeGetQMFromMM"
0x180043558  mov     [rbp+57h+var_60], rax
0x18004355c  lea     rdx, [rbp+57h+var_B0]
0x180043560  movzx   eax, cs:word_180166E9A
0x180043567  xor     r9d, r9d
0x18004356a  mov     [rbp+57h+var_AC], eax
0x18004356d  xor     r8d, r8d
0x180043570  mov     rax, cs:off_180173280
0x180043577  mov     [rbp+57h+var_A0], rax
0x18004357b  mov     [rbp+57h+var_64], r15d
0x18004357f  mov     [rbp+57h+var_58], 0Fh
0x180043587  mov     [rbp+57h+var_B0], 0B000000h
0x18004358e  mov     [rbp+57h+var_A8], 1
0x180043596  movzx   eax, word ptr [rax]
0x180043599  mov     [rbp+57h+var_98], eax
0x18004359c  lea     rax, dword_180166EA4
0x1800435a3  mov     [rbp+57h+var_90], rax
0x1800435a7  mov     rax, r13
0x1800435aa  sub     eax, ecx
0x1800435ac  mov     [rbp+57h+var_94], 2
0x1800435b3  mov     [rbp+57h+var_88], 2Dh ; '-'
0x1800435ba  mov     [rbp+57h+var_84], 1
0x1800435c1  mov     [rbp+57h+var_C0], eax
0x1800435c4  mov     eax, [rbp+57h+var_C0]
0x1800435c7  mov     rcx, cs:qword_180173298
0x1800435ce  lea     rax, [rbp+57h+var_A0]
0x1800435d2  mov     [rsp+0F0h+var_C8], rax
0x1800435d7  mov     dword ptr [rsp+0F0h+var_D0], 5
0x1800435df  call    cs:__imp_EtwEventWriteTransfer
0x1800435e5  lea     rdx, aIkegetqmfrommm; "IkeGetQMFromMM"
0x1800435ec  cmp     [rsi], rsi
0x1800435ef  jnz     short loc_180043607
0x1800435f1  mov     r9d, 1
0x1800435f7  mov     r8d, 35ECh
0x1800435fd  call    WfpReportSysErrorAsWinError
0x180043602  mov     rsi, rax
0x180043605  jmp     short loc_180043645
0x180043607  cmp     [rbx], rsi
0x18004360a  jz      short loc_180043622
0x18004360c  mov     r9d, 1
0x180043612  mov     r8d, 35ECh
0x180043618  call    WfpReportSysErrorAsWinError
0x18004361d  mov     rsi, rax
0x180043620  jmp     short loc_180043645
0x180043622  mov     ecx, [rbx+220h]
0x180043628  test    ecx, ecx
0x18004362a  jz      short loc_1800436A7
0x18004362c  sub     ecx, 1
0x18004362f  jz      short loc_180043636
0x180043631  cmp     ecx, 1
0x180043634  jnz     short loc_18004363F
0x180043636  cmp     [rbx+228h], r15
0x18004363d  jz      short loc_1800436B0
0x18004363f  mov     rsi, r15
0x180043642  mov     r14, rbx
0x180043645  mov     eax, cs:dword_180173278
0x18004364b  cmp     eax, 5
0x18004364e  jbe     loc_1800437D3
0x180043654  mov     rcx, cs:qword_180173290
0x18004365b  mov     rax, cs:qword_180173288
0x180043662  test    al, 1
0x180043664  jz      loc_1800437D3
0x18004366a  mov     rax, rcx
0x18004366d  and     eax, 1
0x180043670  cmp     rax, rcx
0x180043673  jnz     loc_1800437D3
0x180043679  mov     rax, cs:gIkeExtGlobals
0x180043680  test    rax, rax
0x180043683  jz      short loc_1800436D0
0x180043685  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004368b  cmp     ecx, 0FFFFFFFFh
0x18004368e  jz      short loc_1800436D0
0x180043690  call    cs:__imp_TlsGetValue
0x180043696  test    rax, rax
0x180043699  jz      short loc_1800436C9
0x18004369b  mov     rcx, [rax]
0x18004369e  mov     rax, cs:gIkeExtGlobals
0x1800436a5  jmp     short loc_1800436D3
0x1800436a7  cmp     [rbx+228h], r15
0x1800436ae  jz      short loc_18004363F
0x1800436b0  mov     r9d, 1
0x1800436b6  mov     r8d, 35ECh
0x1800436bc  call    WfpReportSysErrorAsWinError
0x1800436c1  mov     rsi, rax
0x1800436c4  jmp     loc_180043645
0x1800436c9  mov     rax, cs:gIkeExtGlobals
0x1800436d0  mov     rcx, r15
0x1800436d3  mov     [rbp+57h+var_B8], rcx
0x1800436d7  lea     rcx, [rbp+57h+var_B8]
0x1800436db  mov     [rbp+57h+var_80], rcx
0x1800436df  mov     [rbp+57h+var_78], 8
0x1800436e7  test    rax, rax
0x1800436ea  jz      short loc_180043725
0x1800436ec  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800436f2  cmp     ecx, 0FFFFFFFFh
0x1800436f5  jz      short loc_180043725
0x1800436f7  call    cs:__imp_TlsGetValue
0x1800436fd  test    rax, rax
0x180043700  lea     rdx, [rax+8]
0x180043704  cmovz   rdx, r15
0x180043708  test    rdx, rdx
0x18004370b  jz      short loc_180043725
0x18004370d  mov     rax, r12
0x180043710  cmp     [rdx+rax*2+2], r15w
0x180043716  lea     rax, [rax+1]
0x18004371a  jnz     short loc_180043710
0x18004371c  lea     eax, ds:2[rax*2]
0x180043723  jmp     short loc_180043731
0x180043725  lea     rdx, LocaleName
0x18004372c  mov     eax, 2
0x180043731  mov     [rbp+57h+var_68], eax
0x180043734  lea     rcx, _TraceLoggingMetadata
0x18004373b  mov     [rbp+57h+var_70], rdx
0x18004373f  lea     rax, aIkegetqmfrommm; "IkeGetQMFromMM"
0x180043746  mov     [rbp+57h+var_60], rax
0x18004374a  lea     rdx, [rbp+57h+var_B0]
0x18004374e  movzx   eax, cs:word_180166E61
0x180043755  xor     r9d, r9d
0x180043758  mov     [rbp+57h+var_AC], eax
0x18004375b  xor     r8d, r8d
0x18004375e  mov     rax, cs:off_180173280
0x180043765  mov     [rbp+57h+var_A0], rax
0x180043769  mov     [rbp+57h+var_64], r15d
0x18004376d  mov     [rbp+57h+var_58], 0Fh
0x180043775  mov     [rbp+57h+var_B0], 0B000000h
0x18004377c  mov     [rbp+57h+var_A8], 1
0x180043784  movzx   eax, word ptr [rax]
0x180043787  mov     [rbp+57h+var_98], eax
0x18004378a  lea     rax, byte_180166E6B
0x180043791  mov     [rbp+57h+var_90], rax
0x180043795  mov     rax, r13
  ... truncated ...
```
