# IkeProcessPowerEvent

- ea: `0x18001b1a0`
- end: `0x18001b93f`
- name: `IkeProcessPowerEvent`
- size: `1951`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18001b110`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18001b1a0`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b238`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b27f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b39b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b3d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b439`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b47e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b5b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b5eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b645`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b68a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b7ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b844`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b238`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b27f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b39b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b3d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b439`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b47e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b5b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b5eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b645`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b68a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b7ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b763`
- `ntdll!EtwEventWriteTransfer` at `0x18001b351`
- `ntdll!EtwEventWriteTransfer` at `0x18001b56b`
- `ntdll!EtwEventWriteTransfer` at `0x18001b919`
- `ntdll!EtwEventWriteTransfer` at `0x18001b351`
- `ntdll!EtwEventWriteTransfer` at `0x18001b56b`
- `ntdll!EtwEventWriteTransfer` at `0x18001b919`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001b759`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001b759`

## string_xrefs

- `0x18001b76f`: `TrySubmitThreadpoolCallback`

## pseudocode

```c
double __fastcall IkeProcessPowerEvent(unsigned int a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
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
  double result; // xmm0_8
  _QWORD *v14; // rcx
  LPCRITICAL_SECTION v15; // rdx
  DWORD v16; // eax
  LPVOID v17; // rax
  LPVOID v18; // r8
  __int64 v19; // rdi
  DWORD v20; // eax
  __int64 *v21; // rax
  __int64 v22; // r9
  LPCRITICAL_SECTION v23; // rax
  DWORD v24; // ecx
  __int64 *v25; // rax
  __int64 v26; // rcx
  DWORD v27; // ecx
  char *v28; // rax
  const WCHAR *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  LPCRITICAL_SECTION v32; // rdx
  _QWORD *v33; // rcx
  DWORD v34; // eax
  LPVOID v35; // rax
  LPVOID v36; // r8
  __int64 v37; // rdi
  DWORD v38; // eax
  __int64 *v39; // rax
  __int64 v40; // r9
  LPCRITICAL_SECTION v41; // rax
  DWORD v42; // ecx
  __int64 *v43; // rax
  __int64 v44; // rcx
  DWORD v45; // ecx
  char *v46; // rax
  const WCHAR *v47; // rdx
  int v48; // ebx
  __int16 *v49; // rax
  __int64 v50; // rax
  _QWORD *v51; // rdi
  DWORD LastError; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  LPCRITICAL_SECTION v55; // rax
  DWORD v56; // ecx
  __int64 *v57; // rax
  __int64 v58; // rcx
  DWORD v59; // ecx
  char *v60; // rax
  const WCHAR *v61; // rdx
  int v62; // ebx
  __int64 v63; // [rsp+28h] [rbp-A1h]
  PVOID pv; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v65; // [rsp+38h] [rbp-91h] BYREF
  __int64 v66; // [rsp+40h] [rbp-89h] BYREF
  int v67; // [rsp+48h] [rbp-81h] BYREF
  int v68; // [rsp+4Ch] [rbp-7Dh]
  __int64 v69; // [rsp+50h] [rbp-79h]
  char *v70; // [rsp+60h] [rbp-69h] BYREF
  int v71; // [rsp+68h] [rbp-61h]
  int v72; // [rsp+6Ch] [rbp-5Dh]
  int *v73; // [rsp+70h] [rbp-59h]
  int v74; // [rsp+78h] [rbp-51h]
  int v75; // [rsp+7Ch] [rbp-4Dh]
  __int64 *v76; // [rsp+80h] [rbp-49h]
  __int64 v77; // [rsp+88h] [rbp-41h]
  const WCHAR *v78; // [rsp+90h] [rbp-39h]
  int v79; // [rsp+98h] [rbp-31h]
  int v80; // [rsp+9Ch] [rbp-2Dh]
  const char *v81; // [rsp+A0h] [rbp-29h]
  __int64 v82; // [rsp+A8h] [rbp-21h]
  unsigned int *v83; // [rsp+B0h] [rbp-19h]
  __int64 v84; // [rsp+B8h] [rbp-11h]
  _QWORD v85[2]; // [rsp+C0h] [rbp-9h] BYREF

  v1 = a1;
  pv = 0;
  v2 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
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
  v66 = v6;
  v76 = &v66;
  v77 = 8;
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
  v79 = v12;
  v70 = off_180173280;
  v78 = v9;
  v80 = 0;
  v81 = "IkeProcessPowerEvent";
  v82 = 21;
  v85[0] = 0x50B000000LL;
  v85[1] = 1;
  v71 = *(unsigned __int16 *)off_180173280;
  v73 = &dword_180166EA4;
  v72 = 2;
  v74 = 45;
  v75 = 1;
  v65 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  result = EtwEventWriteTransfer(qword_180173298, v85, 0, 0, 5, &v70);
LABEL_20:
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v15 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v16 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v16 == -1) )
    {
      v18 = 0;
    }
    else
    {
      v17 = TlsGetValue(v16);
      v14 = WPP_GLOBAL_Control;
      v18 = v17;
      v15 = gIkeExtGlobals;
    }
    v19 = (__int64)v18 + 8;
    if ( !v18 )
      v19 = 0;
    if ( v15
      && (v20 = (DWORD)v15[86].LockSemaphore, v20 != -1)
      && (v21 = (__int64 *)TlsGetValue(v20), v14 = WPP_GLOBAL_Control, v21) )
    {
      v22 = *v21;
    }
    else
    {
      LODWORD(v22) = 0;
    }
    LODWORD(v63) = v1;
    WPP_SF_iSL(v14[2], 17, (unsigned int)WPP_cc00778c82d836298410d94d06f43a3d_Traceguids, v22, v19, v63);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v23 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v24 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v24 != -1 )
      {
        v25 = (__int64 *)TlsGetValue(v24);
        if ( v25 )
        {
          v26 = *v25;
          v23 = gIkeExtGlobals;
LABEL_42:
          v85[0] = v26;
          v76 = v85;
          v77 = 8;
          if ( !v23 )
            goto LABEL_50;
          v27 = (DWORD)v23[86].LockSemaphore;
          if ( v27 == -1 )
            goto LABEL_50;
          v28 = (char *)TlsGetValue(v27);
          v29 = (const WCHAR *)(v28 + 8);
          if ( !v28 )
            v29 = 0;
          if ( v29 )
          {
            v30 = -1;
            do
              v11 = v29[++v30] == 0;
            while ( !v11 );
            v31 = 2 * v30 + 2;
          }
          else
          {
LABEL_50:
            v29 = &LocaleName;
            v31 = 2;
          }
          v79 = v31;
          v78 = v29;
          v81 = "Received Power event notification";
          v80 = 0;
          v83 = &v65;
          v68 = 4;
          v70 = off_180173280;
          v82 = 34;
          v65 = v1;
          v84 = 4;
          v67 = 184549376;
          v69 = 0;
          v71 = *(unsigned __int16 *)off_180173280;
          v73 = (int *)byte_18014FE11;
          v72 = 2;
          v74 = 66;
          v75 = 1;
          LODWORD(v66) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          result = EtwEventWriteTransfer(qword_180173298, &v67, 0, 0, 6, &v70);
          goto LABEL_52;
        }
        v23 = gIkeExtGlobals;
      }
    }
    v26 = 0;
    goto LABEL_42;
  }
LABEL_52:
  v32 = gIkeExtGlobals;
  if ( LODWORD(gIkeExtGlobals[50].SpinCount) != 2 )
  {
    v50 = WfpMemAlloc(0x10u, 8u, &pv);
    v51 = pv;
    if ( v50 )
      goto LABEL_88;
    *(_DWORD *)pv = 4;
    v51[1] = v1;
    if ( TrySubmitThreadpoolCallback(IkeHandlePolicyChange, v51, (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[76].LockCount) )
    {
      v54 = 0;
      _InterlockedIncrement((volatile signed __int32 *)&gIkeExtGlobals[48].SpinCount + 1);
    }
    else
    {
      LastError = GetLastError();
      v54 = WfpReportSysErrorAsWinError(v53, "TrySubmitThreadpoolCallback", LastError, 1);
    }
    if ( IkeReturnError(v54, "IkeQueueWorkItem") )
    {
LABEL_88:
      if ( v51 )
        WfpMemFree((LPCVOID *)&pv);
    }
    if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
      return result;
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
LABEL_99:
          v85[0] = v58;
          v76 = v85;
          v77 = 8;
          if ( !v55 )
            goto LABEL_106;
          v59 = (DWORD)v55[86].LockSemaphore;
          if ( v59 == -1 )
            goto LABEL_106;
          v60 = (char *)TlsGetValue(v59);
          v61 = (const WCHAR *)(v60 + 8);
          if ( !v60 )
            v61 = 0;
          if ( v61 )
          {
            do
              v11 = v61[++v2] == 0;
            while ( !v11 );
            v62 = 2 * v2 + 2;
          }
          else
          {
LABEL_106:
            v61 = &LocaleName;
            v62 = 2;
          }
          v68 = 5;
          v70 = off_180173280;
          v78 = v61;
          v79 = v62;
          v80 = 0;
          v81 = "IkeProcessPowerEvent";
          v82 = 21;
          v67 = 184549376;
          v69 = 1;
          v71 = *(unsigned __int16 *)off_180173280;
          v49 = (__int16 *)byte_180166E6B;
          v74 = 45;
          goto LABEL_108;
        }
        v55 = gIkeExtGlobals;
      }
    }
    v58 = 0;
    goto LABEL_99;
  }
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v34 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
    if ( v34 == -1 )
    {
      v36 = 0;
    }
    else
    {
      v35 = TlsGetValue(v34);
      v33 = WPP_GLOBAL_Control;
      v36 = v35;
      v32 = gIkeExtGlobals;
    }
    v37 = (__int64)v36 + 8;
    if ( !v36 )
      v37 = 0;
    if ( v32
      && (v38 = (DWORD)v32[86].LockSemaphore, v38 != -1)
      && (v39 = (__int64 *)TlsGetValue(v38), v33 = WPP_GLOBAL_Control, v39) )
    {
      v40 = *v39;
    }
    else
    {
      LODWORD(v40) = 0;
    }
    WPP_SF_iS(v33[2], 18, (unsigned int)WPP_cc00778c82d836298410d94d06f43a3d_Traceguids, v40, v37);
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
LABEL_74:
          v85[0] = v44;
          v76 = v85;
          v77 = 8;
          if ( !v41 )
            goto LABEL_81;
          v45 = (DWORD)v41[86].LockSemaphore;
          if ( v45 == -1 )
            goto LABEL_81;
          v46 = (char *)TlsGetValue(v45);
          v47 = (const WCHAR *)(v46 + 8);
          if ( !v46 )
            v47 = 0;
          if ( v47 )
          {
            do
              v11 = v47[++v2] == 0;
            while ( !v11 );
            v48 = 2 * v2 + 2;
          }
          else
          {
LABEL_81:
            v47 = &LocaleName;
            v48 = 2;
          }
          v78 = v47;
          v81 = "Ignoring notification due to shutdown";
          v68 = 4;
          v70 = off_180173280;
          v79 = v48;
          v80 = 0;
          v82 = 38;
          v67 = 184549376;
          v69 = 0;
          v71 = *(unsigned __int16 *)off_180173280;
          v49 = &word_18014FDC6;
          v74 = 63;
LABEL_108:
          v73 = (int *)v49;
          v72 = 2;
          v75 = 1;
          LODWORD(v66) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          return EtwEventWriteTransfer(qword_180173298, &v67, 0, 0, 5, &v70);
        }
        v41 = gIkeExtGlobals;
      }
    }
    v44 = 0;
    goto LABEL_74;
  }
  return result;
}

```

## disassembly

```asm
0x18001b1a0  push    rbp
0x18001b1a2  push    rbx
0x18001b1a3  push    rsi
0x18001b1a4  push    rdi
0x18001b1a5  push    r12
0x18001b1a7  push    r13
0x18001b1a9  push    r14
0x18001b1ab  push    r15
0x18001b1ad  lea     rbp, [rsp-1Fh]
0x18001b1b2  sub     rsp, 0E8h
0x18001b1b9  mov     rax, cs:__security_cookie
0x18001b1c0  xor     rax, rsp
0x18001b1c3  mov     [rbp+57h+var_50], rax
0x18001b1c7  mov     eax, cs:dword_180173278
0x18001b1cd  lea     r13, aIkeprocesspowe; "IkeProcessPowerEvent"
0x18001b1d4  xor     r15d, r15d
0x18001b1d7  mov     esi, ecx
0x18001b1d9  mov     [rsp+120h+pv], r15
0x18001b1de  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001b1e5  lea     r14, _TraceLoggingMetadataEnd
0x18001b1ec  lea     rdi, _TraceLoggingMetadata
0x18001b1f3  cmp     eax, 5
0x18001b1f6  jbe     loc_18001B357
0x18001b1fc  mov     rcx, cs:qword_180173290
0x18001b203  mov     rax, cs:qword_180173288
0x18001b20a  test    al, 1
0x18001b20c  jz      loc_18001B357
0x18001b212  mov     rax, rcx
0x18001b215  and     eax, 1
0x18001b218  cmp     rax, rcx
0x18001b21b  jnz     loc_18001B357
0x18001b221  mov     rax, cs:gIkeExtGlobals
0x18001b228  test    rax, rax
0x18001b22b  jz      short loc_18001B256
0x18001b22d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001b233  cmp     ecx, 0FFFFFFFFh
0x18001b236  jz      short loc_18001B256
0x18001b238  call    cs:__imp_TlsGetValue
0x18001b23e  test    rax, rax
0x18001b241  jz      short loc_18001B24F
0x18001b243  mov     rcx, [rax]
0x18001b246  mov     rax, cs:gIkeExtGlobals
0x18001b24d  jmp     short loc_18001B259
0x18001b24f  mov     rax, cs:gIkeExtGlobals
0x18001b256  mov     rcx, r15
0x18001b259  mov     [rsp+120h+var_E0], rcx
0x18001b25e  lea     rcx, [rsp+120h+var_E0]
0x18001b263  mov     [rbp+57h+var_A0], rcx
0x18001b267  mov     [rbp+57h+var_98], 8
0x18001b26f  test    rax, rax
0x18001b272  jz      short loc_18001B2B5
0x18001b274  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001b27a  cmp     ecx, 0FFFFFFFFh
0x18001b27d  jz      short loc_18001B2B5
0x18001b27f  call    cs:__imp_TlsGetValue
0x18001b285  test    rax, rax
0x18001b288  lea     rdx, [rax+8]
0x18001b28c  cmovz   rdx, r15
0x18001b290  test    rdx, rdx
0x18001b293  jz      short loc_18001B2B5
0x18001b295  mov     rax, rbx
0x18001b298  nop     dword ptr [rax+rax+00000000h]
0x18001b2a0  cmp     [rdx+rax*2+2], r15w
0x18001b2a6  lea     rax, [rax+1]
0x18001b2aa  jnz     short loc_18001B2A0
0x18001b2ac  lea     eax, ds:2[rax*2]
0x18001b2b3  jmp     short loc_18001B2C1
0x18001b2b5  lea     rdx, LocaleName
0x18001b2bc  mov     eax, 2
0x18001b2c1  mov     [rbp+57h+var_88], eax
0x18001b2c4  xor     r9d, r9d
0x18001b2c7  movzx   eax, cs:word_180166E9A
0x18001b2ce  xor     r8d, r8d
0x18001b2d1  mov     dword ptr [rbp+57h+var_60+4], eax
0x18001b2d4  mov     rax, cs:off_180173280
0x18001b2db  mov     [rbp+57h+var_C0], rax
0x18001b2df  mov     [rbp+57h+var_90], rdx
0x18001b2e3  lea     rdx, [rbp+57h+var_60]
0x18001b2e7  mov     [rbp+57h+var_84], r15d
0x18001b2eb  mov     [rbp+57h+var_80], r13
0x18001b2ef  mov     [rbp+57h+var_78], 15h
0x18001b2f7  mov     dword ptr [rbp+57h+var_60], 0B000000h
0x18001b2fe  mov     [rbp+57h+var_58], 1
0x18001b306  movzx   eax, word ptr [rax]
0x18001b309  mov     [rbp+57h+var_B8], eax
0x18001b30c  lea     rax, dword_180166EA4
0x18001b313  mov     [rbp+57h+var_B0], rax
0x18001b317  mov     rax, r14
0x18001b31a  sub     eax, edi
0x18001b31c  mov     [rbp+57h+var_B4], 2
0x18001b323  mov     [rbp+57h+var_A8], 2Dh ; '-'
0x18001b32a  mov     [rbp+57h+var_A4], 1
0x18001b331  mov     [rsp+120h+var_E8], eax
0x18001b335  mov     eax, [rsp+120h+var_E8]
0x18001b339  mov     rcx, cs:qword_180173298
0x18001b340  lea     rax, [rbp+57h+var_C0]
0x18001b344  mov     [rsp+120h+var_F8], rax
0x18001b349  mov     dword ptr [rsp+120h+var_100], 5
0x18001b351  call    cs:__imp_EtwEventWriteTransfer
0x18001b357  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b35e  lea     r12, WPP_GLOBAL_Control
0x18001b365  cmp     rcx, r12
0x18001b368  jz      loc_18001B413
0x18001b36e  cmp     byte ptr [rcx+19h], 4
0x18001b372  jb      loc_18001B413
0x18001b378  test    byte ptr [rcx+1Ch], 10h
0x18001b37c  jz      loc_18001B413
0x18001b382  mov     rdx, cs:gIkeExtGlobals
0x18001b389  test    rdx, rdx
0x18001b38c  jz      short loc_18001B3B4
0x18001b38e  mov     eax, [rdx+0D88h]
0x18001b394  cmp     eax, 0FFFFFFFFh
0x18001b397  jz      short loc_18001B3B4
0x18001b399  mov     ecx, eax; dwTlsIndex
0x18001b39b  call    cs:__imp_TlsGetValue
0x18001b3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3a8  mov     r8, rax
0x18001b3ab  mov     rdx, cs:gIkeExtGlobals
0x18001b3b2  jmp     short loc_18001B3B7
0x18001b3b4  mov     r8, r15
0x18001b3b7  test    r8, r8
0x18001b3ba  lea     rdi, [r8+8]
0x18001b3be  cmovz   rdi, r15
0x18001b3c2  test    rdx, rdx
0x18001b3c5  jz      short loc_18001B3EB
0x18001b3c7  mov     eax, [rdx+0D88h]
0x18001b3cd  cmp     eax, 0FFFFFFFFh
0x18001b3d0  jz      short loc_18001B3EB
0x18001b3d2  mov     ecx, eax; dwTlsIndex
0x18001b3d4  call    cs:__imp_TlsGetValue
0x18001b3da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3e1  test    rax, rax
0x18001b3e4  jz      short loc_18001B3EB
0x18001b3e6  mov     r9, [rax]
0x18001b3e9  jmp     short loc_18001B3EE
0x18001b3eb  mov     r9, r15
0x18001b3ee  mov     rcx, [rcx+10h]
0x18001b3f2  lea     r8, WPP_cc00778c82d836298410d94d06f43a3d_Traceguids
0x18001b3f9  mov     edx, 11h
0x18001b3fe  mov     dword ptr [rsp+120h+var_F8], esi
0x18001b402  mov     [rsp+120h+var_100], rdi
0x18001b407  call    WPP_SF_iSL
0x18001b40c  lea     rdi, _TraceLoggingMetadata
0x18001b413  mov     eax, cs:dword_180173278
0x18001b419  cmp     eax, 4
0x18001b41c  jbe     loc_18001B571
0x18001b422  mov     rax, cs:gIkeExtGlobals
0x18001b429  test    rax, rax
0x18001b42c  jz      short loc_18001B457
0x18001b42e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001b434  cmp     ecx, 0FFFFFFFFh
0x18001b437  jz      short loc_18001B457
0x18001b439  call    cs:__imp_TlsGetValue
0x18001b43f  test    rax, rax
0x18001b442  jz      short loc_18001B450
0x18001b444  mov     rcx, [rax]
0x18001b447  mov     rax, cs:gIkeExtGlobals
0x18001b44e  jmp     short loc_18001B45A
0x18001b450  mov     rax, cs:gIkeExtGlobals
0x18001b457  mov     rcx, r15
0x18001b45a  mov     [rbp+57h+var_60], rcx
0x18001b45e  lea     rcx, [rbp+57h+var_60]
0x18001b462  mov     [rbp+57h+var_A0], rcx
0x18001b466  mov     [rbp+57h+var_98], 8
0x18001b46e  test    rax, rax
0x18001b471  jz      short loc_18001B4B5
0x18001b473  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001b479  cmp     ecx, 0FFFFFFFFh
0x18001b47c  jz      short loc_18001B4B5
0x18001b47e  call    cs:__imp_TlsGetValue
0x18001b484  test    rax, rax
0x18001b487  lea     rdx, [rax+8]
0x18001b48b  cmovz   rdx, r15
0x18001b48f  test    rdx, rdx
0x18001b492  jz      short loc_18001B4B5
0x18001b494  mov     rax, rbx
0x18001b497  nop     word ptr [rax+rax+00000000h]
0x18001b4a0  cmp     [rdx+rax*2+2], r15w
0x18001b4a6  lea     rax, [rax+1]
0x18001b4aa  jnz     short loc_18001B4A0
0x18001b4ac  lea     eax, ds:2[rax*2]
0x18001b4b3  jmp     short loc_18001B4C1
0x18001b4b5  lea     rdx, LocaleName
0x18001b4bc  mov     eax, 2
0x18001b4c1  mov     [rbp+57h+var_88], eax
0x18001b4c4  xor     r9d, r9d
0x18001b4c7  mov     [rbp+57h+var_90], rdx
0x18001b4cb  lea     rax, aReceivedPowerE; "Received Power event notification"
0x18001b4d2  mov     [rbp+57h+var_80], rax
0x18001b4d6  lea     rdx, [rsp+120h+var_D8]
0x18001b4db  lea     rax, [rsp+120h+var_E8]
0x18001b4e0  mov     [rbp+57h+var_84], r15d
0x18001b4e4  mov     [rbp+57h+var_70], rax
0x18001b4e8  xor     r8d, r8d
0x18001b4eb  movzx   eax, cs:word_18014FE07
0x18001b4f2  mov     [rbp+57h+var_D4], eax
0x18001b4f5  mov     rax, cs:off_180173280
0x18001b4fc  mov     [rbp+57h+var_C0], rax
0x18001b500  mov     [rbp+57h+var_78], 22h ; '"'
0x18001b508  mov     [rsp+120h+var_E8], esi
0x18001b50c  mov     [rbp+57h+var_68], 4
0x18001b514  mov     [rsp+120h+var_D8], 0B000000h
0x18001b51c  mov     [rbp+57h+var_D0], r15
0x18001b520  movzx   eax, word ptr [rax]
0x18001b523  mov     [rbp+57h+var_B8], eax
0x18001b526  lea     rax, byte_18014FE11
0x18001b52d  mov     [rbp+57h+var_B0], rax
0x18001b531  mov     rax, r14
0x18001b534  sub     eax, edi
0x18001b536  mov     [rbp+57h+var_B4], 2
0x18001b53d  mov     [rbp+57h+var_A8], 42h ; 'B'
0x18001b544  mov     [rbp+57h+var_A4], 1
0x18001b54b  mov     dword ptr [rsp+120h+var_E0], eax
0x18001b54f  mov     eax, dword ptr [rsp+120h+var_E0]
0x18001b553  mov     rcx, cs:qword_180173298
0x18001b55a  lea     rax, [rbp+57h+var_C0]
0x18001b55e  mov     [rsp+120h+var_F8], rax
0x18001b563  mov     dword ptr [rsp+120h+var_100], 6
0x18001b56b  call    cs:__imp_EtwEventWriteTransfer
0x18001b571  mov     rdx, cs:gIkeExtGlobals
0x18001b578  cmp     dword ptr [rdx+7F0h], 2
0x18001b57f  jnz     loc_18001B719
0x18001b585  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b58c  cmp     rcx, r12
0x18001b58f  jz      loc_18001B61F
0x18001b595  cmp     byte ptr [rcx+19h], 4
0x18001b599  jb      loc_18001B61F
0x18001b59f  test    byte ptr [rcx+1Ch], 10h
0x18001b5a3  jz      short loc_18001B61F
0x18001b5a5  mov     eax, [rdx+0D88h]
0x18001b5ab  cmp     eax, 0FFFFFFFFh
0x18001b5ae  jz      short loc_18001B5CB
0x18001b5b0  mov     ecx, eax; dwTlsIndex
0x18001b5b2  call    cs:__imp_TlsGetValue
0x18001b5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5bf  mov     r8, rax
0x18001b5c2  mov     rdx, cs:gIkeExtGlobals
0x18001b5c9  jmp     short loc_18001B5CE
0x18001b5cb  mov     r8, r15
0x18001b5ce  test    r8, r8
0x18001b5d1  lea     rdi, [r8+8]
0x18001b5d5  cmovz   rdi, r15
0x18001b5d9  test    rdx, rdx
0x18001b5dc  jz      short loc_18001B602
0x18001b5de  mov     eax, [rdx+0D88h]
0x18001b5e4  cmp     eax, 0FFFFFFFFh
0x18001b5e7  jz      short loc_18001B602
0x18001b5e9  mov     ecx, eax; dwTlsIndex
0x18001b5eb  call    cs:__imp_TlsGetValue
0x18001b5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5f8  test    rax, rax
0x18001b5fb  jz      short loc_18001B602
0x18001b5fd  mov     r9, [rax]
0x18001b600  jmp     short loc_18001B605
0x18001b602  mov     r9, r15
0x18001b605  mov     rcx, [rcx+10h]
0x18001b609  lea     r8, WPP_cc00778c82d836298410d94d06f43a3d_Traceguids
0x18001b610  mov     edx, 12h
0x18001b615  mov     [rsp+120h+var_100], rdi
0x18001b61a  call    WPP_SF_iS
0x18001b61f  mov     eax, cs:dword_180173278
0x18001b625  cmp     eax, 4
0x18001b628  jbe     loc_18001B91F
0x18001b62e  mov     rax, cs:gIkeExtGlobals
0x18001b635  test    rax, rax
0x18001b638  jz      short loc_18001B663
0x18001b63a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001b640  cmp     ecx, 0FFFFFFFFh
0x18001b643  jz      short loc_18001B663
0x18001b645  call    cs:__imp_TlsGetValue
0x18001b64b  test    rax, rax
0x18001b64e  jz      short loc_18001B65C
0x18001b650  mov     rcx, [rax]
0x18001b653  mov     rax, cs:gIkeExtGlobals
0x18001b65a  jmp     short loc_18001B666
0x18001b65c  mov     rax, cs:gIkeExtGlobals
0x18001b663  mov     rcx, r15
0x18001b666  mov     [rbp+57h+var_60], rcx
0x18001b66a  lea     rcx, [rbp+57h+var_60]
0x18001b66e  mov     [rbp+57h+var_A0], rcx
0x18001b672  mov     [rbp+57h+var_98], 8
0x18001b67a  test    rax, rax
0x18001b67d  jz      short loc_18001B6B5
0x18001b67f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001b685  cmp     ecx, 0FFFFFFFFh
0x18001b688  jz      short loc_18001B6B5
0x18001b68a  call    cs:__imp_TlsGetValue
0x18001b690  test    rax, rax
0x18001b693  lea     rdx, [rax+8]
0x18001b697  cmovz   rdx, r15
0x18001b69b  test    rdx, rdx
0x18001b69e  jz      short loc_18001B6B5
0x18001b6a0  cmp     [rdx+rbx*2+2], r15w
0x18001b6a6  lea     rbx, [rbx+1]
0x18001b6aa  jnz     short loc_18001B6A0
0x18001b6ac  lea     ebx, ds:2[rbx*2]
0x18001b6b3  jmp     short loc_18001B6C1
0x18001b6b5  lea     rdx, LocaleName
0x18001b6bc  mov     ebx, 2
0x18001b6c1  lea     rax, aIgnoringNotifi; "Ignoring notification due to shutdown"
  ... truncated ...
```
