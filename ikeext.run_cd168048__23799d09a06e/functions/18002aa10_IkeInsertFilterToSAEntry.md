# IkeInsertFilterToSAEntry

- ea: `0x18002aa10`
- end: `0x18002b2e7`
- name: `IkeInsertFilterToSAEntry`
- size: `2263`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024f20`
- `0x1800c1268`
- `0x1800e1028`
- `0x1800eb6dc`
- `0x1800fa71c`

## callees

- `0x180003cf0`
- `0x180008388`
- `0x180010db0`
- `0x180011680`
- `0x18001afe0`
- `0x180024b34`
- `0x18002aa10`
- `0x18004882c`
- `0x18004890c`
- `0x180050850`
- `0x1800529a4`
- `0x18006ddbc`
- `0x180110d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aaa7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aaee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ad24`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aea4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002af11`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002af5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b192`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b1d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aaa7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aaee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ad24`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aea4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002af11`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002af5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b192`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b1d7`
- `ntdll!EtwEventWriteTransfer` at `0x18002abca`
- `ntdll!EtwEventWriteTransfer` at `0x18002b070`
- `ntdll!EtwEventWriteTransfer` at `0x18002b2a6`
- `ntdll!EtwEventWriteTransfer` at `0x18002abca`
- `ntdll!EtwEventWriteTransfer` at `0x18002b070`
- `ntdll!EtwEventWriteTransfer` at `0x18002b2a6`
- `ntdll!RtlInsertEntryHashTable` at `0x18002acd7`
- `ntdll!RtlInsertEntryHashTable` at `0x18002acd7`
- `ntdll!RtlNtStatusToDosError` at `0x18002ad65`
- `ntdll!RtlNtStatusToDosError` at `0x18002ad65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ac0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ac0f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002b115`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002b115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b0d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b130`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b0d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b130`

## string_xrefs

- `0x18002acf3`: `RtlCreateHashTable`
- `0x18002ad8a`: `RtlCreateHashTable`

## pseudocode

```c
__int64 __fastcall IkeInsertFilterToSAEntry(_QWORD *a1, __int64 a2, char a3, unsigned __int64 a4)
{
  __int64 v8; // rdi
  LPCRITICAL_SECTION v9; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v12; // rcx
  DWORD v13; // ecx
  char *v14; // rax
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  bool v17; // zf
  int v18; // eax
  _QWORD *v19; // rbx
  __int64 v20; // rsi
  __int64 v21; // r8
  LONG *p_LockCount; // rcx
  int v23; // r8d
  _QWORD *v24; // rcx
  DWORD v25; // edx
  LPVOID v26; // rax
  LPVOID v27; // rdx
  __int64 v28; // rcx
  int v29; // r9d
  ULONG v30; // eax
  int v31; // r8d
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 LockSemaphore_low; // rcx
  _QWORD *v34; // rbx
  __int64 *v35; // rax
  __int64 v36; // r14
  __int64 v37; // rbx
  __int64 TlsPeerAddr; // rax
  int v39; // r8d
  LPCRITICAL_SECTION v40; // rax
  DWORD v41; // ecx
  __int64 *v42; // rax
  __int64 v43; // rcx
  DWORD v44; // ecx
  char *v45; // rax
  const WCHAR *v46; // rdx
  __int64 v47; // rax
  int v48; // eax
  BOOL v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  LPCRITICAL_SECTION v53; // rax
  DWORD v54; // ecx
  __int64 *v55; // rax
  __int64 v56; // rcx
  DWORD v57; // ecx
  char *v58; // rax
  const WCHAR *v59; // rdx
  int v60; // edi
  unsigned int v62; // [rsp+40h] [rbp-99h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-91h] BYREF
  __int64 v64; // [rsp+50h] [rbp-89h] BYREF
  __int64 v65; // [rsp+58h] [rbp-81h] BYREF
  char *v66; // [rsp+60h] [rbp-79h] BYREF
  int v67; // [rsp+68h] [rbp-71h]
  int v68; // [rsp+6Ch] [rbp-6Dh]
  char *v69; // [rsp+70h] [rbp-69h]
  __int64 v70; // [rsp+78h] [rbp-61h]
  unsigned int *v71; // [rsp+80h] [rbp-59h]
  __int64 v72; // [rsp+88h] [rbp-51h]
  const WCHAR *v73; // [rsp+90h] [rbp-49h]
  int v74; // [rsp+98h] [rbp-41h]
  int v75; // [rsp+9Ch] [rbp-3Dh]
  LPVOID *p_lpMem; // [rsp+A0h] [rbp-39h]
  __int64 v77; // [rsp+A8h] [rbp-31h]
  __int64 *v78; // [rsp+B0h] [rbp-29h]
  __int64 v79; // [rsp+B8h] [rbp-21h]
  _QWORD *v80; // [rsp+C0h] [rbp-19h]
  __int64 v81; // [rsp+C8h] [rbp-11h]
  _QWORD v82[2]; // [rsp+D0h] [rbp-9h] BYREF
  int v83; // [rsp+E0h] [rbp+7h] BYREF
  int v84; // [rsp+E4h] [rbp+Bh]
  __int64 v85; // [rsp+E8h] [rbp+Fh]

  lpMem = 0;
  v8 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v9 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v9 = gIkeExtGlobals;
LABEL_9:
    v12 = 0;
    goto LABEL_10;
  }
  v12 = *Value;
  v9 = gIkeExtGlobals;
LABEL_10:
  v64 = v12;
  v71 = (unsigned int *)&v64;
  v72 = 8;
  if ( !v9 )
    goto LABEL_18;
  v13 = (DWORD)v9[86].LockSemaphore;
  if ( v13 == -1 )
    goto LABEL_18;
  v14 = (char *)TlsGetValue(v13);
  v15 = (const WCHAR *)(v14 + 8);
  if ( !v14 )
    v15 = 0;
  if ( v15 )
  {
    v16 = -1;
    do
      v17 = v15[++v16] == 0;
    while ( !v17 );
    v18 = 2 * v16 + 2;
  }
  else
  {
LABEL_18:
    v15 = &LocaleName;
    v18 = 2;
  }
  v74 = v18;
  v66 = off_180173280;
  v73 = v15;
  v75 = 0;
  p_lpMem = (LPVOID *)"IkeInsertFilterToSAEntry";
  v77 = 25;
  v82[0] = 0x50B000000LL;
  v82[1] = 1;
  v67 = *(unsigned __int16 *)off_180173280;
  v69 = (char *)&dword_180166EA4;
  v68 = 2;
  v70 = 0x10000002DLL;
  v62 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, v82, 0, 0, 5, &v66);
LABEL_20:
  v19 = lpMem;
  v20 = WfpMemAlloc(0x30u, 8u);
  if ( v20 )
    goto LABEL_46;
  *((_BYTE *)lpMem + 24) = a3;
  v19[4] = a4;
  v19[5] = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 248));
  IkeDestroyFilterToSAStateUnderLock(a1, a2);
  if ( a3 )
    a1[142] = v19;
  else
    *(_QWORD *)(a2 + 840) = v19;
  v20 = 0;
  v19[2] = HIBYTE(a4)
         + 37
         * (BYTE6(a4)
          + 37
          * (BYTE5(a4)
           + 37 * (BYTE4(a4) + 37 * (BYTE3(a4) + 37 * (BYTE2(a4) + 37 * (BYTE1(a4) + 37LL * (unsigned __int8)a4))))));
  v21 = v19[2];
  p_LockCount = &gIkeExtGlobals[62].LockCount;
  if ( !v21 )
  {
    v19[2] = -1;
    v21 = -1;
  }
  if ( !(unsigned __int8)RtlInsertEntryHashTable(p_LockCount, v19, v21, 0) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( !gIkeExtGlobals || (v25 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v25 == -1) )
      {
        v27 = 0;
      }
      else
      {
        v26 = TlsGetValue(v25);
        v24 = WPP_GLOBAL_Control;
        v27 = v26;
      }
      v28 = v24[2];
      v29 = (_DWORD)v27 + 8;
      if ( !v27 )
        v29 = 0;
      WPP_SF_Ssd(v28, 22, v23, v29, (__int64)"RtlCreateHashTable", 23);
    }
    v30 = RtlNtStatusToDosError(-1073741801);
    LODWORD(v20) = v30;
    if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
    {
      v62 = v30;
      v70 = 19;
      v69 = "RtlCreateHashTable";
      v72 = 4;
      v71 = &v62;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v31,
        3,
        (__int64)&v66);
    }
    if ( (int)v20 > 0 )
      LODWORD(v20) = (unsigned __int16)v20 | 0x80070000;
    v20 = (int)v20;
    if ( (_DWORD)v20 )
    {
      WfpReportError((int)v20, "WfpHashtableInsert");
      WfpRestructureHashtable(&gIkeExtGlobals[62].LockCount);
      if ( a3 )
        a1[142] = 0;
      else
        *(_QWORD *)(a2 + 840) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 248));
LABEL_46:
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        v49 = HeapFree(gWfpHeap, 0, v19);
        if ( !gHeapFreeFailedFired && !v49 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v51, v50, v52);
          gHeapFreeFailedFired = 1;
        }
      }
      else
      {
        HeapFree(gWfpHeap, 0, v19);
      }
      goto LABEL_81;
    }
  }
  WfpRestructureHashtable(&gIkeExtGlobals[62].LockCount);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 248));
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( gIkeExtGlobals
      && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
      && (v35 = (__int64 *)TlsGetValue(LockSemaphore_low), v34 = WPP_GLOBAL_Control, v35) )
    {
      v36 = *v35;
    }
    else
    {
      LODWORD(v36) = 0;
    }
    v37 = v34[2];
    TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
    WPP_SF_iSIqq(v37, 21, v39, v36, TlsPeerAddr, a4, (__int64)a1, a2);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v40 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v41 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v41 != -1 )
      {
        v42 = (__int64 *)TlsGetValue(v41);
        if ( v42 )
        {
          v43 = *v42;
          v40 = gIkeExtGlobals;
LABEL_65:
          v64 = v43;
          v71 = (unsigned int *)&v64;
          v72 = 8;
          if ( !v40 )
            goto LABEL_73;
          v44 = (DWORD)v40[86].LockSemaphore;
          if ( v44 == -1 )
            goto LABEL_73;
          v45 = (char *)TlsGetValue(v44);
          v46 = (const WCHAR *)(v45 + 8);
          if ( !v45 )
            v46 = 0;
          if ( v46 )
          {
            v47 = -1;
            do
              v17 = v46[++v47] == 0;
            while ( !v17 );
            v48 = 2 * v47 + 2;
          }
          else
          {
LABEL_73:
            v46 = &LocaleName;
            v48 = 2;
          }
          v74 = v48;
          v73 = v46;
          p_lpMem = &lpMem;
          lpMem = a1;
          v78 = &v65;
          v75 = 0;
          v80 = v82;
          v84 = 4;
          v66 = off_180173280;
          v77 = 8;
          v65 = a2;
          v79 = 8;
          v82[0] = a4;
          v81 = 8;
          v83 = 184549376;
          v85 = 0;
          v67 = *(unsigned __int16 *)off_180173280;
          v69 = (char *)&word_180152A36;
          v68 = 2;
          v70 = 0x100000042LL;
          v62 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v83, 0, 0, 7, &v66);
          goto LABEL_81;
        }
        v40 = gIkeExtGlobals;
      }
    }
    v43 = 0;
    goto LABEL_65;
  }
LABEL_81:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(v20, "IkeInsertFilterToSAEntry");
  v53 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_89;
  v54 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v54 == -1 )
    goto LABEL_89;
  v55 = (__int64 *)TlsGetValue(v54);
  if ( !v55 )
  {
    v53 = gIkeExtGlobals;
LABEL_89:
    v56 = 0;
    goto LABEL_90;
  }
  v56 = *v55;
  v53 = gIkeExtGlobals;
LABEL_90:
  v82[0] = v56;
  v71 = (unsigned int *)v82;
  v72 = 8;
  if ( !v53 )
    goto LABEL_97;
  v57 = (DWORD)v53[86].LockSemaphore;
  if ( v57 == -1 )
    goto LABEL_97;
  v58 = (char *)TlsGetValue(v57);
  v59 = (const WCHAR *)(v58 + 8);
  if ( !v58 )
    v59 = 0;
  if ( v59 )
  {
    do
      v17 = v59[++v8] == 0;
    while ( !v17 );
    v60 = 2 * v8 + 2;
  }
  else
  {
LABEL_97:
    v59 = &LocaleName;
    v60 = 2;
  }
  v84 = 5;
  v66 = off_180173280;
  v74 = v60;
  v73 = v59;
  v75 = 0;
  p_lpMem = (LPVOID *)"IkeInsertFilterToSAEntry";
  v77 = 25;
  v83 = 184549376;
  v85 = 1;
  v67 = *(unsigned __int16 *)off_180173280;
  v69 = byte_180166E6B;
  v68 = 2;
  v70 = 0x10000002DLL;
  v62 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v83, 0, 0, 5, &v66);
  return IkeReturnError(v20, "IkeInsertFilterToSAEntry");
}

```

## disassembly

```asm
0x18002aa10  mov     [rsp-8+arg_10], rbx
0x18002aa15  push    rbp
0x18002aa16  push    rsi
0x18002aa17  push    rdi
0x18002aa18  push    r12
0x18002aa1a  push    r13
0x18002aa1c  push    r14
0x18002aa1e  push    r15
0x18002aa20  lea     rbp, [rsp-27h]
0x18002aa25  sub     rsp, 100h
0x18002aa2c  mov     rax, cs:__security_cookie
0x18002aa33  xor     rax, rsp
0x18002aa36  mov     [rbp+57h+var_40], rax
0x18002aa3a  mov     eax, cs:dword_180173278
0x18002aa40  lea     rsi, aIkeinsertfilte; "IkeInsertFilterToSAEntry"
0x18002aa47  xor     ebx, ebx
0x18002aa49  mov     r12, r9
0x18002aa4c  mov     [rsp+130h+lpMem], rbx
0x18002aa51  movzx   r14d, r8b
0x18002aa55  mov     r13, rdx
0x18002aa58  mov     r15, rcx
0x18002aa5b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18002aa62  cmp     eax, 5
0x18002aa65  jbe     loc_18002ABD0
0x18002aa6b  mov     rcx, cs:qword_180173290
0x18002aa72  mov     rax, cs:qword_180173288
0x18002aa79  test    al, 1
0x18002aa7b  jz      loc_18002ABD0
0x18002aa81  mov     rax, rcx
0x18002aa84  and     eax, 1
0x18002aa87  cmp     rax, rcx
0x18002aa8a  jnz     loc_18002ABD0
0x18002aa90  mov     rax, cs:gIkeExtGlobals
0x18002aa97  test    rax, rax
0x18002aa9a  jz      short loc_18002AAC5
0x18002aa9c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002aaa2  cmp     ecx, 0FFFFFFFFh
0x18002aaa5  jz      short loc_18002AAC5
0x18002aaa7  call    cs:__imp_TlsGetValue
0x18002aaad  test    rax, rax
0x18002aab0  jz      short loc_18002AABE
0x18002aab2  mov     rcx, [rax]
0x18002aab5  mov     rax, cs:gIkeExtGlobals
0x18002aabc  jmp     short loc_18002AAC8
0x18002aabe  mov     rax, cs:gIkeExtGlobals
0x18002aac5  mov     rcx, rbx
0x18002aac8  mov     [rsp+130h+var_E0], rcx
0x18002aacd  lea     rcx, [rsp+130h+var_E0]
0x18002aad2  mov     [rbp+57h+var_B0], rcx
0x18002aad6  mov     [rbp+57h+var_A8], 8
0x18002aade  test    rax, rax
0x18002aae1  jz      short loc_18002AB24
0x18002aae3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002aae9  cmp     ecx, 0FFFFFFFFh
0x18002aaec  jz      short loc_18002AB24
0x18002aaee  call    cs:__imp_TlsGetValue
0x18002aaf4  test    rax, rax
0x18002aaf7  lea     rdx, [rax+8]
0x18002aafb  cmovz   rdx, rbx
0x18002aaff  test    rdx, rdx
0x18002ab02  jz      short loc_18002AB24
0x18002ab04  mov     rax, rdi
0x18002ab07  nop     word ptr [rax+rax+00000000h]
0x18002ab10  cmp     [rdx+rax*2+2], bx
0x18002ab15  lea     rax, [rax+1]
0x18002ab19  jnz     short loc_18002AB10
0x18002ab1b  lea     eax, ds:2[rax*2]
0x18002ab22  jmp     short loc_18002AB30
0x18002ab24  lea     rdx, LocaleName
0x18002ab2b  mov     eax, 2
0x18002ab30  mov     [rbp+57h+var_98], eax
0x18002ab33  lea     rcx, _TraceLoggingMetadata
0x18002ab3a  movzx   eax, cs:word_180166E9A
0x18002ab41  xor     r9d, r9d
0x18002ab44  mov     dword ptr [rbp+57h+var_60+4], eax
0x18002ab47  xor     r8d, r8d
0x18002ab4a  mov     rax, cs:off_180173280
0x18002ab51  mov     [rbp+57h+var_D0], rax
0x18002ab55  mov     [rbp+57h+var_A0], rdx
0x18002ab59  lea     rdx, [rbp+57h+var_60]
0x18002ab5d  mov     [rbp+57h+var_94], ebx
0x18002ab60  mov     [rbp+57h+var_90], rsi
0x18002ab64  mov     [rbp+57h+var_88], 19h
0x18002ab6c  mov     dword ptr [rbp+57h+var_60], 0B000000h
0x18002ab73  mov     [rbp+57h+var_58], 1
0x18002ab7b  movzx   eax, word ptr [rax]
0x18002ab7e  mov     [rbp+57h+var_C8], eax
0x18002ab81  lea     rax, dword_180166EA4
0x18002ab88  mov     [rbp+57h+var_C0], rax
0x18002ab8c  lea     rax, _TraceLoggingMetadataEnd
0x18002ab93  sub     eax, ecx
0x18002ab95  mov     [rbp+57h+var_C4], 2
0x18002ab9c  mov     dword ptr [rbp+57h+var_B8], 2Dh ; '-'
0x18002aba3  mov     dword ptr [rbp+57h+var_B8+4], 1
0x18002abaa  mov     [rsp+130h+var_F0], eax
0x18002abae  mov     eax, [rsp+130h+var_F0]
0x18002abb2  mov     rcx, cs:qword_180173298
0x18002abb9  lea     rax, [rbp+57h+var_D0]
0x18002abbd  mov     [rsp+130h+var_108], rax
0x18002abc2  mov     dword ptr [rsp+130h+var_110], 5
0x18002abca  call    cs:__imp_EtwEventWriteTransfer
0x18002abd0  lea     r8, [rsp+130h+lpMem]
0x18002abd5  mov     edx, 8; dwFlags
0x18002abda  mov     ecx, 30h ; '0'; dwBytes
0x18002abdf  call    WfpMemAlloc
0x18002abe4  mov     rbx, [rsp+130h+lpMem]
0x18002abe9  mov     rsi, rax
0x18002abec  test    rax, rax
0x18002abef  jnz     loc_18002AE24
0x18002abf5  mov     [rbx+18h], r14b
0x18002abf9  mov     [rbx+20h], r12
0x18002abfd  mov     [rbx+28h], r15
0x18002ac01  mov     rcx, cs:gIkeExtGlobals
0x18002ac08  add     rcx, 0F8h; lpCriticalSection
0x18002ac0f  call    cs:__imp_EnterCriticalSection
0x18002ac15  mov     rdx, r13
0x18002ac18  mov     rcx, r15
0x18002ac1b  call    IkeDestroyFilterToSAStateUnderLock
0x18002ac20  test    r14b, r14b
0x18002ac23  jz      short loc_18002AC2E
0x18002ac25  mov     [r15+470h], rbx
0x18002ac2c  jmp     short loc_18002AC35
0x18002ac2e  mov     [r13+348h], rbx
0x18002ac35  movzx   eax, r12b
0x18002ac39  xor     esi, esi
0x18002ac3b  imul    rcx, rax, 25h ; '%'
0x18002ac3f  mov     rax, r12
0x18002ac42  shr     rax, 8
0x18002ac46  movzx   eax, al
0x18002ac49  add     rcx, rax
0x18002ac4c  mov     rax, r12
0x18002ac4f  shr     rax, 10h
0x18002ac53  movzx   eax, al
0x18002ac56  imul    rdx, rcx, 25h ; '%'
0x18002ac5a  add     rdx, rax
0x18002ac5d  mov     rax, r12
0x18002ac60  shr     rax, 18h
0x18002ac64  movzx   eax, al
0x18002ac67  imul    rcx, rdx, 25h ; '%'
0x18002ac6b  add     rcx, rax
0x18002ac6e  mov     rax, r12
0x18002ac71  shr     rax, 20h
0x18002ac75  movzx   eax, al
0x18002ac78  imul    rdx, rcx, 25h ; '%'
0x18002ac7c  add     rdx, rax
0x18002ac7f  mov     rax, r12
0x18002ac82  shr     rax, 28h
0x18002ac86  movzx   eax, al
0x18002ac89  imul    rcx, rdx, 25h ; '%'
0x18002ac8d  add     rcx, rax
0x18002ac90  mov     rax, r12
0x18002ac93  imul    rdx, rcx, 25h ; '%'
0x18002ac97  shr     rax, 30h
0x18002ac9b  movzx   eax, al
0x18002ac9e  add     rdx, rax
0x18002aca1  mov     rax, r12
0x18002aca4  imul    rcx, rdx, 25h ; '%'
0x18002aca8  shr     rax, 38h
0x18002acac  add     rcx, rax
0x18002acaf  mov     [rbx+10h], rcx
0x18002acb3  mov     rcx, cs:gIkeExtGlobals
0x18002acba  mov     r8, [rbx+10h]
0x18002acbe  add     rcx, 9B8h
0x18002acc5  test    r8, r8
0x18002acc8  jnz     short loc_18002ACD1
0x18002acca  mov     [rbx+10h], rdi
0x18002acce  mov     r8, rdi
0x18002acd1  xor     r9d, r9d
0x18002acd4  mov     rdx, rbx
0x18002acd7  call    cs:__imp_RtlInsertEntryHashTable
0x18002acdd  lea     rdx, WPP_GLOBAL_Control
0x18002ace4  test    al, al
0x18002ace6  jnz     loc_18002AE47
0x18002acec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acf3  lea     rsi, aRtlcreatehasht; "RtlCreateHashTable"
0x18002acfa  cmp     rcx, rdx
0x18002acfd  jz      short loc_18002AD60
0x18002acff  cmp     byte ptr [rcx+19h], 2
0x18002ad03  jb      short loc_18002AD60
0x18002ad05  test    byte ptr [rcx+1Ch], 1
0x18002ad09  jz      short loc_18002AD60
0x18002ad0b  mov     rax, cs:gIkeExtGlobals
0x18002ad12  test    rax, rax
0x18002ad15  jz      short loc_18002AD36
0x18002ad17  mov     edx, [rax+0D88h]
0x18002ad1d  cmp     edx, 0FFFFFFFFh
0x18002ad20  jz      short loc_18002AD36
0x18002ad22  mov     ecx, edx; dwTlsIndex
0x18002ad24  call    cs:__imp_TlsGetValue
0x18002ad2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad31  mov     rdx, rax
0x18002ad34  jmp     short loc_18002AD38
0x18002ad36  xor     edx, edx
0x18002ad38  mov     rcx, [rcx+10h]
0x18002ad3c  lea     r9, [rdx+8]
0x18002ad40  xor     eax, eax
0x18002ad42  mov     dword ptr [rsp+130h+var_108], 0C0000017h
0x18002ad4a  test    rdx, rdx
0x18002ad4d  mov     [rsp+130h+var_110], rsi
0x18002ad52  mov     edx, 16h
0x18002ad57  cmovz   r9, rax
0x18002ad5b  call    WPP_SF_Ssd
0x18002ad60  mov     ecx, 0C0000017h; Status
0x18002ad65  call    cs:__imp_RtlNtStatusToDosError
0x18002ad6b  cmp     cs:gWfpLogUserModeErrors, 0
0x18002ad72  mov     esi, eax
0x18002ad74  jz      short loc_18002ADC9
0x18002ad76  test    cs:byte_180178161, 1
0x18002ad7d  jz      short loc_18002ADC9
0x18002ad7f  mov     [rsp+130h+var_F0], eax
0x18002ad83  lea     rdx, WFP_USERMODE_ERROR
0x18002ad8a  lea     rax, aRtlcreatehasht; "RtlCreateHashTable"
0x18002ad91  mov     [rbp+57h+var_B8], 13h
0x18002ad99  mov     [rbp+57h+var_C0], rax
0x18002ad9d  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002ada4  lea     rax, [rsp+130h+var_F0]
0x18002ada9  mov     [rbp+57h+var_A8], 4
0x18002adb1  mov     [rbp+57h+var_B0], rax
0x18002adb5  mov     r9d, 3
0x18002adbb  lea     rax, [rbp+57h+var_D0]
0x18002adbf  mov     [rsp+130h+var_110], rax
0x18002adc4  call    McGenEventWrite_EtwEventWriteTransfer
0x18002adc9  test    esi, esi
0x18002adcb  jle     short loc_18002ADD6
0x18002adcd  movzx   esi, si
0x18002add0  or      esi, 80070000h
0x18002add6  movsxd  rsi, esi
0x18002add9  test    rsi, rsi
0x18002addc  jz      short loc_18002AE47
0x18002adde  lea     rdx, aWfphashtablein; "WfpHashtableInsert"
0x18002ade5  mov     rcx, rsi
0x18002ade8  call    WfpReportError
0x18002aded  mov     rcx, cs:gIkeExtGlobals
0x18002adf4  add     rcx, 9B8h
0x18002adfb  call    WfpRestructureHashtable
0x18002ae00  test    r14b, r14b
0x18002ae03  jz      short loc_18002AE3A
0x18002ae05  mov     qword ptr [r15+470h], 0
0x18002ae10  mov     rcx, cs:gIkeExtGlobals
0x18002ae17  add     rcx, 0F8h; lpCriticalSection
0x18002ae1e  call    cs:__imp_LeaveCriticalSection
0x18002ae24  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18002ae2a  test    al, 10h
0x18002ae2c  jz      loc_18002B07B
0x18002ae32  and     eax, 1
0x18002ae35  jmp     loc_18002B080
0x18002ae3a  mov     qword ptr [r13+348h], 0
0x18002ae45  jmp     short loc_18002AE10
0x18002ae47  mov     rcx, cs:gIkeExtGlobals
0x18002ae4e  add     rcx, 9B8h
0x18002ae55  call    WfpRestructureHashtable
0x18002ae5a  mov     rcx, cs:gIkeExtGlobals
0x18002ae61  add     rcx, 0F8h; lpCriticalSection
0x18002ae68  call    cs:__imp_LeaveCriticalSection
0x18002ae6e  mov     rbx, cs:WPP_GLOBAL_Control
0x18002ae75  lea     rax, WPP_GLOBAL_Control
0x18002ae7c  cmp     rbx, rax
0x18002ae7f  jz      short loc_18002AEEB
0x18002ae81  cmp     byte ptr [rbx+19h], 4
0x18002ae85  jb      short loc_18002AEEB
0x18002ae87  test    byte ptr [rbx+1Ch], 10h
0x18002ae8b  jz      short loc_18002AEEB
0x18002ae8d  mov     rax, cs:gIkeExtGlobals
0x18002ae94  test    rax, rax
0x18002ae97  jz      short loc_18002AEBB
0x18002ae99  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002ae9f  cmp     ecx, 0FFFFFFFFh
0x18002aea2  jz      short loc_18002AEBB
0x18002aea4  call    cs:__imp_TlsGetValue
0x18002aeaa  mov     rbx, cs:WPP_GLOBAL_Control
0x18002aeb1  test    rax, rax
0x18002aeb4  jz      short loc_18002AEBB
0x18002aeb6  mov     r14, [rax]
0x18002aeb9  jmp     short loc_18002AEBE
0x18002aebb  xor     r14d, r14d
0x18002aebe  mov     rbx, [rbx+10h]
0x18002aec2  call    IkeGetTlsPeerAddr
0x18002aec7  mov     [rsp+130h+var_F8], r13
0x18002aecc  mov     edx, 15h
0x18002aed1  mov     [rsp+130h+var_100], r15
0x18002aed6  mov     r9, r14
0x18002aed9  mov     [rsp+130h+var_108], r12
0x18002aede  mov     rcx, rbx
0x18002aee1  mov     [rsp+130h+var_110], rax
0x18002aee6  call    WPP_SF_iSIqq
0x18002aeeb  mov     eax, cs:dword_180173278
0x18002aef1  cmp     eax, 4
0x18002aef4  jbe     loc_18002B136
0x18002aefa  mov     rax, cs:gIkeExtGlobals
0x18002af01  test    rax, rax
0x18002af04  jz      short loc_18002AF32
0x18002af06  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002af0c  cmp     ecx, 0FFFFFFFFh
0x18002af0f  jz      short loc_18002AF32
0x18002af11  call    cs:__imp_TlsGetValue
0x18002af17  test    rax, rax
0x18002af1a  jz      short loc_18002AF2B
0x18002af1c  mov     rcx, [rax]
0x18002af1f  xor     r14d, r14d
0x18002af22  mov     rax, cs:gIkeExtGlobals
  ... truncated ...
```
