# IkeValidateChainAgainstCAPI

- ea: `0x1800306a0`
- end: `0x180030ed9`
- name: `IkeValidateChainAgainstCAPI`
- size: `2105`
- prototype: `__int64 __fastcall(PCCERT_CHAIN_CONTEXT pChainContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800302f8`

## callees

- `0x1800061ec`
- `0x1800306a0`
- `0x18004890c`
- `0x180050850`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003074f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030793`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030925`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030960`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800309c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030a06`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030b77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030bf0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030c38`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030d92`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030dd7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003074f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030793`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030925`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030960`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800309c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030a06`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030b77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030bf0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030c38`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030d92`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030dd7`
- `ntdll!EtwEventWriteTransfer` at `0x180030872`
- `ntdll!EtwEventWriteTransfer` at `0x180030af8`
- `ntdll!EtwEventWriteTransfer` at `0x180030d24`
- `ntdll!EtwEventWriteTransfer` at `0x180030ea9`
- `ntdll!EtwEventWriteTransfer` at `0x180030872`
- `ntdll!EtwEventWriteTransfer` at `0x180030af8`
- `ntdll!EtwEventWriteTransfer` at `0x180030d24`
- `ntdll!EtwEventWriteTransfer` at `0x180030ea9`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800308d0`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800308d0`

## pseudocode

```c
__int64 __fastcall IkeValidateChainAgainstCAPI(
        PCCERT_CHAIN_CONTEXT pChainContext,
        __int64 a2,
        void *a3,
        const CHAR *a4)
{
  __int64 v4; // r13
  int v5; // r12d
  int v6; // r15d
  __int64 v10; // rsi
  LPCRITICAL_SECTION v11; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v14; // rcx
  DWORD v15; // ecx
  char *v16; // rax
  const WCHAR *v17; // rdx
  __int64 v18; // rax
  bool v19; // zf
  int v20; // eax
  int v21; // eax
  void *pvExtraPolicyPara; // rax
  _QWORD *LockSemaphore_low; // rcx
  LPCRITICAL_SECTION v24; // rdx
  DWORD v25; // eax
  LPVOID v26; // rax
  LPVOID v27; // r8
  __int64 v28; // rbx
  DWORD v29; // eax
  __int64 *v30; // rax
  __int64 v31; // r9
  LPCRITICAL_SECTION v32; // rax
  DWORD v33; // ecx
  __int64 *v34; // rax
  __int64 v35; // rcx
  DWORD v36; // ecx
  char *v37; // rax
  const WCHAR *v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  _QWORD *v41; // rdi
  __int64 *v42; // rax
  __int64 v43; // r14
  __int64 v44; // r15
  __int64 v45; // rdi
  int v46; // ebx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v48; // rax
  DWORD v49; // ecx
  __int64 *v50; // rax
  __int64 v51; // rcx
  DWORD v52; // ecx
  char *v53; // rax
  const WCHAR *v54; // rdx
  __int64 v55; // rax
  int v56; // eax
  LPCRITICAL_SECTION v57; // rax
  DWORD v58; // ecx
  __int64 *v59; // rax
  __int64 v60; // rcx
  DWORD v61; // ecx
  char *v62; // rax
  const WCHAR *v63; // rdx
  int v64; // esi
  __int64 v66; // [rsp+28h] [rbp-B1h]
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+38h] [rbp-A1h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+50h] [rbp-89h] BYREF
  DWORD dwError; // [rsp+60h] [rbp-79h] BYREF
  __int64 v71; // [rsp+68h] [rbp-71h] BYREF
  int v72; // [rsp+70h] [rbp-69h] BYREF
  int v73; // [rsp+74h] [rbp-65h]
  __int64 v74; // [rsp+78h] [rbp-61h]
  char *v75; // [rsp+80h] [rbp-59h] BYREF
  int v76; // [rsp+88h] [rbp-51h]
  int v77; // [rsp+8Ch] [rbp-4Dh]
  char *v78; // [rsp+90h] [rbp-49h]
  int v79; // [rsp+98h] [rbp-41h]
  int v80; // [rsp+9Ch] [rbp-3Dh]
  __int64 *v81; // [rsp+A0h] [rbp-39h]
  __int64 v82; // [rsp+A8h] [rbp-31h]
  const WCHAR *v83; // [rsp+B0h] [rbp-29h]
  int v84; // [rsp+B8h] [rbp-21h]
  int v85; // [rsp+BCh] [rbp-1Dh]
  const char *v86; // [rsp+C0h] [rbp-19h]
  __int64 v87; // [rsp+C8h] [rbp-11h]
  DWORD *p_dwError; // [rsp+D0h] [rbp-9h]
  __int64 v89; // [rsp+D8h] [rbp-1h]
  _QWORD v90[2]; // [rsp+E0h] [rbp+7h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v10 = -1;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v11 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v11 = gIkeExtGlobals;
LABEL_9:
    v14 = 0;
    goto LABEL_10;
  }
  v14 = *Value;
  v11 = gIkeExtGlobals;
LABEL_10:
  v71 = v14;
  v81 = &v71;
  v82 = 8;
  if ( !v11 )
    goto LABEL_18;
  v15 = (DWORD)v11[86].LockSemaphore;
  if ( v15 == -1 )
    goto LABEL_18;
  v16 = (char *)TlsGetValue(v15);
  v17 = (const WCHAR *)(v16 + 8);
  if ( !v16 )
    v17 = 0;
  if ( v17 )
  {
    v18 = -1;
    do
      v19 = v17[++v18] == 0;
    while ( !v19 );
    v20 = 2 * v18 + 2;
  }
  else
  {
LABEL_18:
    v17 = &LocaleName;
    v20 = 2;
  }
  v84 = v20;
  v83 = v17;
  v86 = "IkeValidateChainAgainstCAPI";
  v75 = off_180173280;
  v85 = 0;
  v87 = 28;
  v90[0] = 0x50B000000LL;
  v90[1] = 1;
  v76 = *(unsigned __int16 *)off_180173280;
  v78 = (char *)&dword_180166EA4;
  v77 = 2;
  v79 = 45;
  v80 = 1;
  dwError = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, v90, 0, 0, 5, &v75);
LABEL_20:
  v21 = *(_DWORD *)(a2 + 48);
  if ( (v21 & 2) == 0 )
  {
    v5 = 1;
    if ( (v21 & 4) != 0 )
      v6 = 1;
  }
  pvExtraPolicyPara = pPolicyPara.pvExtraPolicyPara;
  pPolicyPara.cbSize = 16;
  pPolicyPara.dwFlags = 4;
  if ( a3 )
    pvExtraPolicyPara = a3;
  pPolicyStatus.cbSize = 24;
  pPolicyPara.pvExtraPolicyPara = pvExtraPolicyPara;
  *(_QWORD *)&pPolicyStatus.lChainIndex = -1;
  CertVerifyCertificateChainPolicy(a4, pChainContext, &pPolicyPara, &pPolicyStatus);
  if ( !pPolicyStatus.dwError )
    goto LABEL_91;
  LockSemaphore_low = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v24 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v25 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v25 == -1) )
    {
      v27 = 0;
    }
    else
    {
      v26 = TlsGetValue(v25);
      LockSemaphore_low = WPP_GLOBAL_Control;
      v27 = v26;
      v24 = gIkeExtGlobals;
    }
    v28 = (__int64)v27 + 8;
    if ( !v27 )
      v28 = 0;
    if ( v24
      && (v29 = (DWORD)v24[86].LockSemaphore, v29 != -1)
      && (v30 = (__int64 *)TlsGetValue(v29), LockSemaphore_low = WPP_GLOBAL_Control, v30) )
    {
      v31 = *v30;
    }
    else
    {
      LODWORD(v31) = 0;
    }
    LODWORD(v66) = pPolicyStatus.dwError;
    WPP_SF_iSL(LockSemaphore_low[2], 26, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v31, v28, v66);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v32 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v33 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v33 != -1 )
      {
        v34 = (__int64 *)TlsGetValue(v33);
        if ( v34 )
        {
          v35 = *v34;
          v32 = gIkeExtGlobals;
LABEL_48:
          v90[0] = v35;
          v81 = v90;
          v82 = 8;
          if ( !v32 )
            goto LABEL_56;
          v36 = (DWORD)v32[86].LockSemaphore;
          if ( v36 == -1 )
            goto LABEL_56;
          v37 = (char *)TlsGetValue(v36);
          v38 = (const WCHAR *)(v37 + 8);
          if ( !v37 )
            v38 = 0;
          if ( v38 )
          {
            v39 = -1;
            do
              v19 = v38[++v39] == 0;
            while ( !v19 );
            v40 = 2 * v39 + 2;
          }
          else
          {
LABEL_56:
            v38 = &LocaleName;
            v40 = 2;
          }
          v84 = v40;
          v83 = v38;
          v86 = "CertChain did not pass CertVerifyCertificateChainPolicy";
          dwError = pPolicyStatus.dwError;
          v85 = 0;
          p_dwError = &dwError;
          v73 = 4;
          v75 = off_180173280;
          v87 = 56;
          v89 = 4;
          v72 = 184549376;
          v74 = 0;
          v76 = *(unsigned __int16 *)off_180173280;
          v78 = (char *)&unk_180158328;
          v77 = 2;
          v79 = 83;
          v80 = 1;
          LODWORD(v71) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v72, 0, 0, 6, &v75);
          goto LABEL_58;
        }
        v32 = gIkeExtGlobals;
      }
    }
    v35 = 0;
    goto LABEL_48;
  }
LABEL_58:
  if ( (pPolicyStatus.dwError + 2146885614 > 1 && pPolicyStatus.dwError != -2146762482 || v6)
    && (pPolicyStatus.dwError != -2146885616 || v5) )
  {
    v4 = WfpReportSysErrorAsWinError(LockSemaphore_low, "IkeValidateChainAgainstCAPI", pPolicyStatus.dwError, 1);
    goto LABEL_91;
  }
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
  {
    v44 = a2;
  }
  else
  {
    if ( gIkeExtGlobals
      && (LockSemaphore_low = (_QWORD *)LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
      && (v42 = (__int64 *)TlsGetValue((DWORD)LockSemaphore_low), v41 = WPP_GLOBAL_Control, v42) )
    {
      v43 = *v42;
    }
    else
    {
      LODWORD(v43) = 0;
    }
    v44 = a2;
    v45 = v41[2];
    v46 = *(_DWORD *)(a2 + 48);
    TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
    LODWORD(v66) = v46;
    WPP_SF_iSL(v45, 27, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v43, TlsPeerAddr, v66);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v48 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v49 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v49 != -1 )
      {
        v50 = (__int64 *)TlsGetValue(v49);
        if ( v50 )
        {
          v51 = *v50;
          v48 = gIkeExtGlobals;
LABEL_81:
          v90[0] = v51;
          v81 = v90;
          v82 = 8;
          if ( !v48 )
            goto LABEL_89;
          v52 = (DWORD)v48[86].LockSemaphore;
          if ( v52 == -1 )
            goto LABEL_89;
          v53 = (char *)TlsGetValue(v52);
          v54 = (const WCHAR *)(v53 + 8);
          if ( !v53 )
            v54 = 0;
          if ( v54 )
          {
            v55 = -1;
            do
              v19 = v54[++v55] == 0;
            while ( !v19 );
            v56 = 2 * v55 + 2;
          }
          else
          {
LABEL_89:
            v54 = &LocaleName;
            v56 = 2;
          }
          v84 = v56;
          v83 = v54;
          v86 = "Not failing because of the cert auth flags set in policy";
          LODWORD(v71) = *(_DWORD *)(v44 + 48);
          v85 = 0;
          p_dwError = (DWORD *)&v71;
          v73 = 4;
          v75 = off_180173280;
          v87 = 57;
          v89 = 4;
          v72 = 184549376;
          v74 = 0;
          v76 = *(unsigned __int16 *)off_180173280;
          v78 = &byte_1801582D7;
          v77 = 2;
          v79 = 69;
          v80 = 1;
          dwError = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v72, 0, 0, 6, &v75);
          goto LABEL_91;
        }
        v48 = gIkeExtGlobals;
      }
    }
    v51 = 0;
    goto LABEL_81;
  }
LABEL_91:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return v4;
  v57 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_99;
  v58 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v58 == -1 )
    goto LABEL_99;
  v59 = (__int64 *)TlsGetValue(v58);
  if ( !v59 )
  {
    v57 = gIkeExtGlobals;
LABEL_99:
    v60 = 0;
    goto LABEL_100;
  }
  v60 = *v59;
  v57 = gIkeExtGlobals;
LABEL_100:
  v90[0] = v60;
  v81 = v90;
  v82 = 8;
  if ( !v57 )
    goto LABEL_107;
  v61 = (DWORD)v57[86].LockSemaphore;
  if ( v61 == -1 )
    goto LABEL_107;
  v62 = (char *)TlsGetValue(v61);
  v63 = (const WCHAR *)(v62 + 8);
  if ( !v62 )
    v63 = 0;
  if ( v63 )
  {
    do
      v19 = v63[++v10] == 0;
    while ( !v19 );
    v64 = 2 * v10 + 2;
  }
  else
  {
LABEL_107:
    v63 = &LocaleName;
    v64 = 2;
  }
  v73 = 5;
  v75 = off_180173280;
  v83 = v63;
  v84 = v64;
  v85 = 0;
  v86 = "IkeValidateChainAgainstCAPI";
  v87 = 28;
  v72 = 184549376;
  v74 = 1;
  v76 = *(unsigned __int16 *)off_180173280;
  v78 = byte_180166E6B;
  v77 = 2;
  v79 = 45;
  v80 = 1;
  LODWORD(v71) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v72, 0, 0, 5, &v75);
  return v4;
}

```

## disassembly

```asm
0x1800306a0  mov     [rsp-8+arg_8], rbx
0x1800306a5  push    rbp
0x1800306a6  push    rsi
0x1800306a7  push    rdi
0x1800306a8  push    r12
0x1800306aa  push    r13
0x1800306ac  push    r14
0x1800306ae  push    r15
0x1800306b0  lea     rbp, [rsp-27h]
0x1800306b5  sub     rsp, 100h
0x1800306bc  mov     rax, cs:__security_cookie
0x1800306c3  xor     rax, rsp
0x1800306c6  mov     [rbp+57h+var_40], rax
0x1800306ca  xor     eax, eax
0x1800306cc  mov     [rsp+130h+var_100], rdx
0x1800306d1  mov     [rsp+130h+pPolicyStatus.pvExtraPolicyStatus], rax
0x1800306d6  xor     r13d, r13d
0x1800306d9  mov     eax, cs:dword_180173278
0x1800306df  xor     r12d, r12d
0x1800306e2  xor     r15d, r15d
0x1800306e5  xorps   xmm0, xmm0
0x1800306e8  xorps   xmm1, xmm1
0x1800306eb  mov     rdi, rcx
0x1800306ee  mov     r14, r9
0x1800306f1  mov     rbx, r8
0x1800306f4  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800306fb  mov     ecx, 1
0x180030700  movups  xmmword ptr [rsp+130h+pPolicyPara.cbSize], xmm0
0x180030705  movups  xmmword ptr [rsp+130h+pPolicyStatus.cbSize], xmm1
0x18003070a  cmp     eax, 5
0x18003070d  jbe     loc_18003087D
0x180030713  mov     rcx, cs:qword_180173290
0x18003071a  mov     rax, cs:qword_180173288
0x180030721  test    al, 1
0x180030723  jz      loc_180030878
0x180030729  mov     rax, rcx
0x18003072c  and     eax, 1
0x18003072f  cmp     rax, rcx
0x180030732  jnz     loc_180030878
0x180030738  mov     rax, cs:gIkeExtGlobals
0x18003073f  test    rax, rax
0x180030742  jz      short loc_18003076D
0x180030744  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003074a  cmp     ecx, 0FFFFFFFFh
0x18003074d  jz      short loc_18003076D
0x18003074f  call    cs:__imp_TlsGetValue
0x180030755  test    rax, rax
0x180030758  jz      short loc_180030766
0x18003075a  mov     rcx, [rax]
0x18003075d  mov     rax, cs:gIkeExtGlobals
0x180030764  jmp     short loc_18003076F
0x180030766  mov     rax, cs:gIkeExtGlobals
0x18003076d  xor     ecx, ecx
0x18003076f  mov     [rbp+57h+var_C8], rcx
0x180030773  lea     rcx, [rbp+57h+var_C8]
0x180030777  mov     [rbp+57h+var_90], rcx
0x18003077b  mov     [rbp+57h+var_88], 8
0x180030783  test    rax, rax
0x180030786  jz      short loc_1800307C6
0x180030788  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003078e  cmp     ecx, 0FFFFFFFFh
0x180030791  jz      short loc_1800307C6
0x180030793  call    cs:__imp_TlsGetValue
0x180030799  mov     rcx, rax
0x18003079c  lea     rdx, [rax+8]
0x1800307a0  xor     eax, eax
0x1800307a2  test    rcx, rcx
0x1800307a5  cmovz   rdx, rax
0x1800307a9  test    rdx, rdx
0x1800307ac  jz      short loc_1800307C6
0x1800307ae  mov     rax, rsi
0x1800307b1  cmp     [rdx+rax*2+2], r12w
0x1800307b7  lea     rax, [rax+1]
0x1800307bb  jnz     short loc_1800307B1
0x1800307bd  lea     eax, ds:2[rax*2]
0x1800307c4  jmp     short loc_1800307D2
0x1800307c6  lea     rdx, LocaleName
0x1800307cd  mov     eax, 2
0x1800307d2  mov     [rbp+57h+var_78], eax
0x1800307d5  lea     rcx, _TraceLoggingMetadata
0x1800307dc  mov     [rbp+57h+var_80], rdx
0x1800307e0  lea     rax, aIkevalidatecha_0; "IkeValidateChainAgainstCAPI"
0x1800307e7  mov     [rbp+57h+var_70], rax
0x1800307eb  lea     rdx, [rbp+57h+var_50]
0x1800307ef  movzx   eax, cs:word_180166E9A
0x1800307f6  xor     r9d, r9d
0x1800307f9  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800307fc  xor     r8d, r8d
0x1800307ff  mov     rax, cs:off_180173280
0x180030806  mov     [rbp+57h+var_B0], rax
0x18003080a  mov     [rbp+57h+var_74], r12d
0x18003080e  mov     [rbp+57h+var_68], 1Ch
0x180030816  mov     dword ptr [rbp+57h+var_50], 0B000000h
0x18003081d  mov     [rbp+57h+var_48], 1
0x180030825  movzx   eax, word ptr [rax]
0x180030828  mov     [rbp+57h+var_A8], eax
0x18003082b  lea     rax, dword_180166EA4
0x180030832  mov     [rbp+57h+var_A0], rax
0x180030836  lea     rax, _TraceLoggingMetadataEnd
0x18003083d  sub     eax, ecx
0x18003083f  mov     [rbp+57h+var_A4], 2
0x180030846  mov     [rbp+57h+var_98], 2Dh ; '-'
0x18003084d  mov     [rbp+57h+var_94], 1
0x180030854  mov     [rbp+57h+var_D0], eax
0x180030857  mov     eax, [rbp+57h+var_D0]
0x18003085a  mov     rcx, cs:qword_180173298
0x180030861  lea     rax, [rbp+57h+var_B0]
0x180030865  mov     [rsp+130h+var_108], rax
0x18003086a  mov     dword ptr [rsp+130h+var_110], 5
0x180030872  call    cs:__imp_EtwEventWriteTransfer
0x180030878  mov     ecx, 1
0x18003087d  mov     rax, [rsp+130h+var_100]
0x180030882  mov     eax, [rax+30h]
0x180030885  test    al, 2
0x180030887  jnz     short loc_180030892
0x180030889  test    al, 4
0x18003088b  mov     r12d, ecx
0x18003088e  cmovnz  r15d, ecx
0x180030892  mov     rax, [rsp+130h+pPolicyPara.pvExtraPolicyPara]
0x180030897  lea     r9, [rsp+130h+pPolicyStatus]; pPolicyStatus
0x18003089c  test    rbx, rbx
0x18003089f  mov     [rsp+130h+pPolicyPara.cbSize], 10h
0x1800308a7  lea     r8, [rsp+130h+pPolicyPara]; pPolicyPara
0x1800308ac  mov     [rsp+130h+pPolicyPara.dwFlags], 4
0x1800308b4  cmovnz  rax, rbx
0x1800308b8  mov     [rsp+130h+pPolicyStatus.cbSize], 18h
0x1800308c0  mov     rdx, rdi; pChainContext
0x1800308c3  mov     [rsp+130h+pPolicyPara.pvExtraPolicyPara], rax
0x1800308c8  mov     rcx, r14; pszPolicyOID
0x1800308cb  mov     qword ptr [rsp+130h+pPolicyStatus.lChainIndex], rsi
0x1800308d0  call    cs:__imp_CertVerifyCertificateChainPolicy
0x1800308d6  cmp     [rsp+130h+pPolicyStatus.dwError], r13d
0x1800308db  jz      loc_180030D3E
0x1800308e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308e8  lea     r14, WPP_GLOBAL_Control
0x1800308ef  cmp     rcx, r14
0x1800308f2  jz      loc_18003099C
0x1800308f8  cmp     byte ptr [rcx+19h], 4
0x1800308fc  jb      loc_18003099C
0x180030902  test    byte ptr [rcx+1Ch], 10h
0x180030906  jz      loc_18003099C
0x18003090c  mov     rdx, cs:gIkeExtGlobals
0x180030913  test    rdx, rdx
0x180030916  jz      short loc_18003093E
0x180030918  mov     eax, [rdx+0D88h]
0x18003091e  cmp     eax, 0FFFFFFFFh
0x180030921  jz      short loc_18003093E
0x180030923  mov     ecx, eax; dwTlsIndex
0x180030925  call    cs:__imp_TlsGetValue
0x18003092b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030932  mov     r8, rax
0x180030935  mov     rdx, cs:gIkeExtGlobals
0x18003093c  jmp     short loc_180030941
0x18003093e  xor     r8d, r8d
0x180030941  xor     eax, eax
0x180030943  lea     rbx, [r8+8]
0x180030947  test    r8, r8
0x18003094a  cmovz   rbx, rax
0x18003094e  test    rdx, rdx
0x180030951  jz      short loc_180030977
0x180030953  mov     eax, [rdx+0D88h]
0x180030959  cmp     eax, 0FFFFFFFFh
0x18003095c  jz      short loc_180030977
0x18003095e  mov     ecx, eax; dwTlsIndex
0x180030960  call    cs:__imp_TlsGetValue
0x180030966  mov     rcx, cs:WPP_GLOBAL_Control
0x18003096d  test    rax, rax
0x180030970  jz      short loc_180030977
0x180030972  mov     r9, [rax]
0x180030975  jmp     short loc_18003097A
0x180030977  xor     r9d, r9d
0x18003097a  mov     eax, [rsp+130h+pPolicyStatus.dwError]
0x18003097e  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x180030985  mov     rcx, [rcx+10h]
0x180030989  mov     edx, 1Ah
0x18003098e  mov     dword ptr [rsp+130h+var_108], eax
0x180030992  mov     [rsp+130h+var_110], rbx
0x180030997  call    WPP_SF_iSL
0x18003099c  mov     eax, cs:dword_180173278
0x1800309a2  cmp     eax, 4
0x1800309a5  jbe     loc_180030AFE
0x1800309ab  mov     rax, cs:gIkeExtGlobals
0x1800309b2  test    rax, rax
0x1800309b5  jz      short loc_1800309E0
0x1800309b7  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800309bd  cmp     ecx, 0FFFFFFFFh
0x1800309c0  jz      short loc_1800309E0
0x1800309c2  call    cs:__imp_TlsGetValue
0x1800309c8  test    rax, rax
0x1800309cb  jz      short loc_1800309D9
0x1800309cd  mov     rcx, [rax]
0x1800309d0  mov     rax, cs:gIkeExtGlobals
0x1800309d7  jmp     short loc_1800309E2
0x1800309d9  mov     rax, cs:gIkeExtGlobals
0x1800309e0  xor     ecx, ecx
0x1800309e2  mov     [rbp+57h+var_50], rcx
0x1800309e6  lea     rcx, [rbp+57h+var_50]
0x1800309ea  mov     [rbp+57h+var_90], rcx
0x1800309ee  mov     [rbp+57h+var_88], 8
0x1800309f6  test    rax, rax
0x1800309f9  jz      short loc_180030A39
0x1800309fb  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180030a01  cmp     ecx, 0FFFFFFFFh
0x180030a04  jz      short loc_180030A39
0x180030a06  call    cs:__imp_TlsGetValue
0x180030a0c  mov     rcx, rax
0x180030a0f  lea     rdx, [rax+8]
0x180030a13  xor     eax, eax
0x180030a15  test    rcx, rcx
0x180030a18  cmovz   rdx, rax
0x180030a1c  test    rdx, rdx
0x180030a1f  jz      short loc_180030A39
0x180030a21  mov     rax, rsi
0x180030a24  cmp     [rdx+rax*2+2], r13w
0x180030a2a  lea     rax, [rax+1]
0x180030a2e  jnz     short loc_180030A24
0x180030a30  lea     eax, ds:2[rax*2]
0x180030a37  jmp     short loc_180030A45
0x180030a39  lea     rdx, LocaleName
0x180030a40  mov     eax, 2
0x180030a45  mov     [rbp+57h+var_78], eax
0x180030a48  lea     rcx, _TraceLoggingMetadata
0x180030a4f  mov     [rbp+57h+var_80], rdx
0x180030a53  lea     rax, aCertchainDidNo; "CertChain did not pass CertVerifyCertif"...
0x180030a5a  mov     [rbp+57h+var_70], rax
0x180030a5e  lea     rdx, [rbp+57h+var_C0]
0x180030a62  mov     eax, [rsp+130h+pPolicyStatus.dwError]
0x180030a66  xor     r9d, r9d
0x180030a69  mov     [rbp+57h+var_D0], eax
0x180030a6c  xor     r8d, r8d
0x180030a6f  lea     rax, [rbp+57h+var_D0]
0x180030a73  mov     [rbp+57h+var_74], r13d
0x180030a77  mov     [rbp+57h+var_60], rax
0x180030a7b  movzx   eax, cs:word_18015831E
0x180030a82  mov     [rbp+57h+var_BC], eax
0x180030a85  mov     rax, cs:off_180173280
0x180030a8c  mov     [rbp+57h+var_B0], rax
0x180030a90  mov     [rbp+57h+var_68], 38h ; '8'
0x180030a98  mov     [rbp+57h+var_58], 4
0x180030aa0  mov     [rbp+57h+var_C0], 0B000000h
0x180030aa7  mov     [rbp+57h+var_B8], r13
0x180030aab  movzx   eax, word ptr [rax]
0x180030aae  mov     [rbp+57h+var_A8], eax
0x180030ab1  lea     rax, unk_180158328
0x180030ab8  mov     [rbp+57h+var_A0], rax
0x180030abc  lea     rax, _TraceLoggingMetadataEnd
0x180030ac3  sub     eax, ecx
0x180030ac5  mov     [rbp+57h+var_A4], 2
0x180030acc  mov     [rbp+57h+var_98], 53h ; 'S'
0x180030ad3  mov     [rbp+57h+var_94], 1
0x180030ada  mov     dword ptr [rbp+57h+var_C8], eax
0x180030add  mov     eax, dword ptr [rbp+57h+var_C8]
0x180030ae0  mov     rcx, cs:qword_180173298
0x180030ae7  lea     rax, [rbp+57h+var_B0]
0x180030aeb  mov     [rsp+130h+var_108], rax
0x180030af0  mov     dword ptr [rsp+130h+var_110], 6
0x180030af8  call    cs:__imp_EtwEventWriteTransfer
0x180030afe  mov     r8d, [rsp+130h+pPolicyStatus.dwError]
0x180030b03  lea     eax, [r8+7FF6DFEEh]
0x180030b0a  cmp     eax, 1
0x180030b0d  jbe     short loc_180030B18
0x180030b0f  cmp     r8d, 800B010Eh
0x180030b16  jnz     short loc_180030B1D
0x180030b18  test    r15d, r15d
0x180030b1b  jz      short loc_180030B48
0x180030b1d  cmp     r8d, 80092010h
0x180030b24  jnz     short loc_180030B2B
0x180030b26  test    r12d, r12d
0x180030b29  jz      short loc_180030B48
0x180030b2b  lea     rdi, aIkevalidatecha_0; "IkeValidateChainAgainstCAPI"
0x180030b32  mov     r9d, 1
0x180030b38  mov     rdx, rdi
0x180030b3b  call    WfpReportSysErrorAsWinError
0x180030b40  mov     r13, rax
0x180030b43  jmp     loc_180030D45
0x180030b48  mov     rdi, cs:WPP_GLOBAL_Control
0x180030b4f  cmp     rdi, r14
0x180030b52  jz      short loc_180030BC5
0x180030b54  cmp     byte ptr [rdi+19h], 4
0x180030b58  jb      short loc_180030BC5
0x180030b5a  test    byte ptr [rdi+1Ch], 10h
0x180030b5e  jz      short loc_180030BC5
0x180030b60  mov     rax, cs:gIkeExtGlobals
0x180030b67  test    rax, rax
0x180030b6a  jz      short loc_180030B8E
0x180030b6c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180030b72  cmp     ecx, 0FFFFFFFFh
0x180030b75  jz      short loc_180030B8E
0x180030b77  call    cs:__imp_TlsGetValue
0x180030b7d  mov     rdi, cs:WPP_GLOBAL_Control
0x180030b84  test    rax, rax
0x180030b87  jz      short loc_180030B8E
0x180030b89  mov     r14, [rax]
0x180030b8c  jmp     short loc_180030B91
0x180030b8e  xor     r14d, r14d
0x180030b91  mov     r15, [rsp+130h+var_100]
0x180030b96  mov     rdi, [rdi+10h]
0x180030b9a  mov     ebx, [r15+30h]
0x180030b9e  call    IkeGetTlsPeerAddr
0x180030ba3  mov     edx, 1Bh
  ... truncated ...
```
