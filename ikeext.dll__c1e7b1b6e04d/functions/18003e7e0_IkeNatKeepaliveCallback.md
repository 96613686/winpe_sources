# IkeNatKeepaliveCallback

- ea: `0x18003e7e0`
- end: `0x18003f255`
- name: `IkeNatKeepaliveCallback`
- size: `2677`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b890`
- `0x180011680`
- `0x180011cb0`
- `0x180013500`
- `0x180014b60`
- `0x180025d88`
- `0x18003c9f0`
- `0x18003e7e0`
- `0x180050850`
- `0x1800510ee`
- `0x18006e4f8`
- `0x1800ce8f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003ea6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003eae9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003ea6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003eae9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e869`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e8a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e91f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e966`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003eb36`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003eb6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ebce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ec15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ed47`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ed80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003edeb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ee32`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f00e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f047`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f0af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f0f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e869`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e8a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e91f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e966`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003eb36`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003eb6f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ebce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ec15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ed47`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ed80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003edeb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ee32`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f00e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f047`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f0af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003f0f4`
- `ntdll!EtwEventWriteTransfer` at `0x18003ea52`
- `ntdll!EtwEventWriteTransfer` at `0x18003ecf9`
- `ntdll!EtwEventWriteTransfer` at `0x18003ef66`
- `ntdll!EtwEventWriteTransfer` at `0x18003f205`
- `ntdll!EtwEventWriteTransfer` at `0x18003ea52`
- `ntdll!EtwEventWriteTransfer` at `0x18003ecf9`
- `ntdll!EtwEventWriteTransfer` at `0x18003ef66`
- `ntdll!EtwEventWriteTransfer` at `0x18003f205`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f227`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f227`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eaa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eaa6`

## string_xrefs

- `0x18003ec55`: `TimerContext already cancelled`

## pseudocode

```c
__int64 __fastcall IkeNatKeepaliveCallback(__int64 a1, __int64 a2)
{
  int v3; // r8d
  _QWORD *v4; // rcx
  LPCRITICAL_SECTION v5; // rdx
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v8; // r8
  __int64 v9; // rbx
  DWORD v10; // eax
  __int64 *v11; // rax
  __int64 v12; // r9
  __int64 v13; // rbx
  LPCRITICAL_SECTION v14; // rax
  DWORD v15; // ecx
  __int64 *v16; // rax
  __int64 v17; // rcx
  DWORD v18; // ecx
  char *v19; // rax
  const WCHAR *v20; // rdx
  __int64 v21; // rax
  bool v22; // zf
  int v23; // eax
  DWORD v24; // ecx
  __int64 v25; // rsi
  LPCRITICAL_SECTION v26; // rdx
  DWORD v27; // ecx
  _QWORD *v28; // rcx
  DWORD v29; // eax
  LPVOID v30; // rax
  LPVOID v31; // r8
  __int64 v32; // rsi
  DWORD v33; // eax
  __int64 *v34; // rax
  __int64 v35; // r9
  LPCRITICAL_SECTION v36; // rax
  DWORD v37; // ecx
  __int64 *v38; // rax
  __int64 v39; // rcx
  DWORD v40; // ecx
  char *v41; // rax
  const WCHAR *v42; // rdx
  int v43; // ebx
  _QWORD *v44; // rcx
  LPCRITICAL_SECTION v45; // rdx
  DWORD v46; // eax
  LPVOID v47; // rax
  LPVOID v48; // r8
  __int64 v49; // rsi
  DWORD v50; // eax
  __int64 *v51; // rax
  __int64 v52; // r9
  LPCRITICAL_SECTION v53; // rax
  DWORD v54; // ecx
  __int64 *v55; // rax
  __int64 v56; // rcx
  DWORD v57; // ecx
  char *v58; // rax
  const WCHAR *v59; // rdx
  __int64 v60; // rax
  int v61; // eax
  _QWORD *v62; // rcx
  LPCRITICAL_SECTION v63; // rdx
  DWORD v64; // eax
  LPVOID v65; // rax
  LPVOID v66; // r8
  __int64 v67; // rsi
  DWORD v68; // eax
  __int64 *v69; // rax
  __int64 v70; // r9
  LPCRITICAL_SECTION v71; // rax
  DWORD v72; // ecx
  __int64 *v73; // rax
  __int64 v74; // rcx
  DWORD v75; // ecx
  char *v76; // rax
  const WCHAR *v77; // rdx
  int v78; // ebx
  unsigned int v80; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v82; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v83; // [rsp+58h] [rbp-A8h] BYREF
  __int64 TlsValue; // [rsp+60h] [rbp-A0h] BYREF
  char v85[168]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v86; // [rsp+110h] [rbp+10h] BYREF
  __int64 v87; // [rsp+118h] [rbp+18h]
  char *v88; // [rsp+120h] [rbp+20h] BYREF
  int v89; // [rsp+128h] [rbp+28h]
  int v90; // [rsp+12Ch] [rbp+2Ch]
  int *v91; // [rsp+130h] [rbp+30h]
  int v92; // [rsp+138h] [rbp+38h]
  int v93; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v94; // [rsp+140h] [rbp+40h]
  __int64 v95; // [rsp+148h] [rbp+48h]
  const WCHAR *v96; // [rsp+150h] [rbp+50h]
  int v97; // [rsp+158h] [rbp+58h]
  int v98; // [rsp+15Ch] [rbp+5Ch]
  const char *v99; // [rsp+160h] [rbp+60h]
  __int64 v100; // [rsp+168h] [rbp+68h]
  __int64 *v101; // [rsp+170h] [rbp+70h]
  __int64 v102; // [rsp+178h] [rbp+78h]
  unsigned int *v103; // [rsp+180h] [rbp+80h]
  __int64 v104; // [rsp+188h] [rbp+88h]
  __int64 *v105; // [rsp+190h] [rbp+90h]
  __int64 v106; // [rsp+198h] [rbp+98h]
  int v107; // [rsp+1A0h] [rbp+A0h] BYREF
  int v108; // [rsp+1A4h] [rbp+A4h]
  __int64 v109; // [rsp+1A8h] [rbp+A8h]

  memset_0(&TlsValue, 0, 0xA8u);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v5 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
    {
      v8 = 0;
    }
    else
    {
      Value = TlsGetValue(LockSemaphore);
      v4 = WPP_GLOBAL_Control;
      v8 = Value;
      v5 = gIkeExtGlobals;
    }
    v9 = (__int64)v8 + 8;
    if ( !v8 )
      v9 = 0;
    if ( v5
      && (v10 = (DWORD)v5[86].LockSemaphore, v10 != -1)
      && (v11 = (__int64 *)TlsGetValue(v10), v4 = WPP_GLOBAL_Control, v11) )
    {
      v12 = *v11;
    }
    else
    {
      LODWORD(v12) = 0;
    }
    WPP_SF_iSqq(
      v4[2],
      42,
      (unsigned int)WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids,
      v12,
      v9,
      a2,
      *(_QWORD *)(a2 + 104));
  }
  v13 = -1;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v14 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v15 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v15 != -1 )
      {
        v16 = (__int64 *)TlsGetValue(v15);
        if ( v16 )
        {
          v17 = *v16;
          v14 = gIkeExtGlobals;
LABEL_23:
          v83 = v17;
          v94 = &v83;
          v95 = 8;
          if ( !v14 )
            goto LABEL_31;
          v18 = (DWORD)v14[86].LockSemaphore;
          if ( v18 == -1 )
            goto LABEL_31;
          v19 = (char *)TlsGetValue(v18);
          v20 = (const WCHAR *)(v19 + 8);
          if ( !v19 )
            v20 = 0;
          if ( v20 )
          {
            v21 = -1;
            do
              v22 = v20[++v21] == 0;
            while ( !v22 );
            v23 = 2 * v21 + 2;
          }
          else
          {
LABEL_31:
            v20 = &LocaleName;
            v23 = 2;
          }
          v97 = v23;
          v96 = v20;
          v99 = (const char *)&v81;
          v82 = *(_QWORD *)(a2 + 104);
          v101 = &v82;
          v88 = off_180173280;
          v98 = 0;
          v81 = a2;
          v100 = 8;
          v102 = 8;
          v86 = 0x40B000000LL;
          v87 = 0;
          v89 = *(unsigned __int16 *)off_180173280;
          v91 = &dword_18015D69C;
          v90 = 2;
          v92 = 69;
          v93 = 1;
          v80 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v86, 0, 0, 6, &v88);
          goto LABEL_33;
        }
        v14 = gIkeExtGlobals;
      }
    }
    v17 = 0;
    goto LABEL_23;
  }
LABEL_33:
  v24 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v24 != -1 )
    TlsSetValue(v24, &TlsValue);
  if ( (Microsoft_Windows_NetworkSecurityEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)FwxTraceProvider_Context,
      (unsigned int)SaContextOperationBeginEvent,
      v3,
      1,
      (__int64)&v107);
  EnterCriticalSection((LPCRITICAL_SECTION)a2);
  v25 = *(_QWORD *)(a2 + 104);
  if ( v25 )
  {
    IkeAddrGetAddrString(v25 + 436, v85);
    v26 = gIkeExtGlobals;
    TlsValue = *(_QWORD *)(v25 + 992);
    v27 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
    if ( v27 == -1 )
      goto LABEL_41;
    TlsSetValue(v27, &TlsValue);
  }
  v26 = gIkeExtGlobals;
LABEL_41:
  if ( !*(_DWORD *)(a2 + 92) )
  {
    ++*(_DWORD *)(a2 + 292);
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
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
      WPP_SF_iSdqq(v44[2], 44, (_DWORD)v48, v52, v49, *(_DWORD *)(a2 + 292), a2, *(_QWORD *)(a2 + 104));
    }
    if ( (unsigned int)dword_180173278 <= 4 )
    {
LABEL_105:
      if ( !IkeSendPacketEx(
              a2 + 296,
              a2 + 120,
              *(_QWORD *)(a2 + 104) + 280LL,
              0,
              (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(a2 + 104) + 48LL),
              *(_QWORD *)(a2 + 104))
        && !WfpStartTimer((__int64)&IkeNatKeepaliveCallback, 0x14u, a2, gIkeExtGlobals + 67, (_DWORD *)(a2 + 48)) )
      {
        goto LABEL_139;
      }
      v62 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v63 = gIkeExtGlobals;
        if ( !gIkeExtGlobals || (v64 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v64 == -1) )
        {
          v66 = 0;
        }
        else
        {
          v65 = TlsGetValue(v64);
          v62 = WPP_GLOBAL_Control;
          v66 = v65;
          v63 = gIkeExtGlobals;
        }
        v67 = (__int64)v66 + 8;
        if ( !v66 )
          v67 = 0;
        if ( v63
          && (v68 = (DWORD)v63[86].LockSemaphore, v68 != -1)
          && (v69 = (__int64 *)TlsGetValue(v68), v62 = WPP_GLOBAL_Control, v69) )
        {
          v70 = *v69;
        }
        else
        {
          LODWORD(v70) = 0;
        }
        WPP_SF_iSqq(
          v62[2],
          45,
          (unsigned int)WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids,
          v70,
          v67,
          a2,
          *(_QWORD *)(a2 + 104));
      }
      if ( (unsigned int)dword_180173278 <= 4 )
        goto LABEL_138;
      v71 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v72 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v72 != -1 )
        {
          v73 = (__int64 *)TlsGetValue(v72);
          if ( v73 )
          {
            v74 = *v73;
            v71 = gIkeExtGlobals;
LABEL_129:
            v86 = v74;
            v94 = &v86;
            v95 = 8;
            if ( !v71 )
              goto LABEL_136;
            v75 = (DWORD)v71[86].LockSemaphore;
            if ( v75 == -1 )
              goto LABEL_136;
            v76 = (char *)TlsGetValue(v75);
            v77 = (const WCHAR *)(v76 + 8);
            if ( !v76 )
              v77 = 0;
            if ( v77 )
            {
              do
                v22 = v77[++v13] == 0;
              while ( !v22 );
              v78 = 2 * v13 + 2;
            }
            else
            {
LABEL_136:
              v77 = &LocaleName;
              v78 = 2;
            }
            v96 = v77;
            v99 = "IkeNatKeepaliveCallback failed";
            v97 = v78;
            v101 = &v82;
            v81 = *(_QWORD *)(a2 + 104);
            v98 = 0;
            v103 = (unsigned int *)&v81;
            v108 = 4;
            v88 = off_180173280;
            v100 = 31;
            v82 = a2;
            v102 = 8;
            v104 = 8;
            v107 = 184549376;
            v109 = 0;
            v89 = *(unsigned __int16 *)off_180173280;
            v91 = &dword_18015D42C;
            v90 = 2;
            v92 = 74;
            v93 = 1;
            LODWORD(v83) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(qword_180173298, &v107, 0, 0, 7, &v88);
LABEL_138:
            *(_DWORD *)(a2 + 92) = 1;
            goto LABEL_139;
          }
          v71 = gIkeExtGlobals;
        }
      }
      v74 = 0;
      goto LABEL_129;
    }
    v53 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v54 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v54 != -1 )
      {
        v55 = (__int64 *)TlsGetValue(v54);
        if ( v55 )
        {
          v56 = *v55;
          v53 = gIkeExtGlobals;
LABEL_95:
          v82 = v56;
          v94 = &v82;
          v95 = 8;
          if ( !v53 )
            goto LABEL_103;
          v57 = (DWORD)v53[86].LockSemaphore;
          if ( v57 == -1 )
            goto LABEL_103;
          v58 = (char *)TlsGetValue(v57);
          v59 = (const WCHAR *)(v58 + 8);
          if ( !v58 )
            v59 = 0;
          if ( v59 )
          {
            v60 = -1;
            do
              v22 = v59[++v60] == 0;
            while ( !v22 );
            v61 = 2 * v60 + 2;
          }
          else
          {
LABEL_103:
            v59 = &LocaleName;
            v61 = 2;
          }
          v97 = v61;
          v96 = v59;
          v99 = "Sending NAT keepalive packet";
          v98 = 0;
          v101 = &v81;
          v80 = *(_DWORD *)(a2 + 292);
          v103 = &v80;
          v86 = *(_QWORD *)(a2 + 104);
          v105 = &v86;
          v108 = 4;
          v88 = off_180173280;
          v100 = 29;
          v81 = a2;
          v102 = 8;
          v104 = 4;
          v106 = 8;
          v107 = 184549376;
          v109 = 0;
          v89 = *(unsigned __int16 *)off_180173280;
          v91 = (int *)word_18015D482;
          v90 = 2;
          v92 = 89;
          v93 = 1;
          LODWORD(v83) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v107, 0, 0, 8, &v88);
          goto LABEL_105;
        }
        v53 = gIkeExtGlobals;
      }
    }
    v56 = 0;
    goto LABEL_95;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( !v26 || (v29 = (DWORD)v26[86].LockSemaphore, v29 == -1) )
    {
      v31 = 0;
    }
    else
    {
      v30 = TlsGetValue(v29);
      v28 = WPP_GLOBAL_Control;
      v31 = v30;
      v26 = gIkeExtGlobals;
    }
    v32 = (__int64)v31 + 8;
    if ( !v31 )
      v32 = 0;
    if ( v26
      && (v33 = (DWORD)v26[86].LockSemaphore, v33 != -1)
      && (v34 = (__int64 *)TlsGetValue(v33), v28 = WPP_GLOBAL_Control, v34) )
    {
      v35 = *v34;
    }
    else
    {
      LODWORD(v35) = 0;
    }
    WPP_SF_iSq(v28[2], 43, (unsigned int)WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids, v35, v32, a2);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v36 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v37 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v37 != -1 )
      {
        v38 = (__int64 *)TlsGetValue(v37);
        if ( v38 )
        {
          v39 = *v38;
          v36 = gIkeExtGlobals;
LABEL_64:
          v82 = v39;
          v94 = &v82;
          v95 = 8;
          if ( !v36 )
            goto LABEL_71;
          v40 = (DWORD)v36[86].LockSemaphore;
          if ( v40 == -1 )
            goto LABEL_71;
          v41 = (char *)TlsGetValue(v40);
          v42 = (const WCHAR *)(v41 + 8);
          if ( !v41 )
            v42 = 0;
          if ( v42 )
          {
            do
              v22 = v42[++v13] == 0;
            while ( !v22 );
            v43 = 2 * v13 + 2;
          }
          else
          {
LABEL_71:
            v42 = &LocaleName;
            v43 = 2;
          }
          v96 = v42;
          v99 = "TimerContext already cancelled";
          v97 = v43;
          v101 = &v81;
          v88 = off_180173280;
          v98 = 0;
          v100 = 31;
          v81 = a2;
          v102 = 8;
          v86 = 0x40B000000LL;
          v87 = 0;
          v89 = *(unsigned __int16 *)off_180173280;
          v91 = (int *)byte_18015D643;
          v90 = 2;
          v92 = 77;
          v93 = 1;
          v80 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v86, 0, 0, 6, &v88);
          goto LABEL_139;
        }
        v36 = gIkeExtGlobals;
      }
    }
    v39 = 0;
    goto LABEL_64;
  }
LABEL_139:
  if ( *(_DWORD *)(a2 + 92) )
    IkeDerefTimerContext((LPCRITICAL_SECTION)a2, 1);
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)a2);
  return IkeTlsActivityEnd();
}

```

## disassembly

```asm
0x18003e7e0  push    rbp
0x18003e7e2  push    rbx
0x18003e7e3  push    rsi
0x18003e7e4  push    rdi
0x18003e7e5  push    r12
0x18003e7e7  push    r13
0x18003e7e9  push    r14
0x18003e7eb  push    r15
0x18003e7ed  lea     rbp, [rsp-0C8h]
0x18003e7f5  sub     rsp, 1C8h
0x18003e7fc  mov     rax, cs:__security_cookie
0x18003e803  xor     rax, rsp
0x18003e806  mov     [rbp+100h+var_50], rax
0x18003e80d  mov     rdi, rdx
0x18003e810  lea     rcx, [rsp+200h+TlsValue]; void *
0x18003e815  xor     edx, edx; Val
0x18003e817  mov     r8d, 0A8h; Size
0x18003e81d  call    memset_0
0x18003e822  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e829  lea     r12, WPP_GLOBAL_Control
0x18003e830  xor     r15d, r15d
0x18003e833  cmp     rcx, r12
0x18003e836  jz      loc_18003E8E4
0x18003e83c  cmp     byte ptr [rcx+19h], 4
0x18003e840  jb      loc_18003E8E4
0x18003e846  test    byte ptr [rcx+1Ch], 10h
0x18003e84a  jz      loc_18003E8E4
0x18003e850  mov     rdx, cs:gIkeExtGlobals
0x18003e857  test    rdx, rdx
0x18003e85a  jz      short loc_18003E882
0x18003e85c  mov     eax, [rdx+0D88h]
0x18003e862  cmp     eax, 0FFFFFFFFh
0x18003e865  jz      short loc_18003E882
0x18003e867  mov     ecx, eax; dwTlsIndex
0x18003e869  call    cs:__imp_TlsGetValue
0x18003e86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e876  mov     r8, rax
0x18003e879  mov     rdx, cs:gIkeExtGlobals
0x18003e880  jmp     short loc_18003E885
0x18003e882  mov     r8, r15
0x18003e885  test    r8, r8
0x18003e888  lea     rbx, [r8+8]
0x18003e88c  cmovz   rbx, r15
0x18003e890  test    rdx, rdx
0x18003e893  jz      short loc_18003E8B9
0x18003e895  mov     eax, [rdx+0D88h]
0x18003e89b  cmp     eax, 0FFFFFFFFh
0x18003e89e  jz      short loc_18003E8B9
0x18003e8a0  mov     ecx, eax; dwTlsIndex
0x18003e8a2  call    cs:__imp_TlsGetValue
0x18003e8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8af  test    rax, rax
0x18003e8b2  jz      short loc_18003E8B9
0x18003e8b4  mov     r9, [rax]
0x18003e8b7  jmp     short loc_18003E8BC
0x18003e8b9  mov     r9, r15
0x18003e8bc  mov     rax, [rdi+68h]
0x18003e8c0  lea     r8, WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids
0x18003e8c7  mov     rcx, [rcx+10h]
0x18003e8cb  mov     edx, 2Ah ; '*'
0x18003e8d0  mov     [rsp+200h+var_1D0], rax
0x18003e8d5  mov     [rsp+200h+var_1D8], rdi
0x18003e8da  mov     [rsp+200h+var_1E0], rbx
0x18003e8df  call    WPP_SF_iSqq
0x18003e8e4  mov     eax, cs:dword_180173278
0x18003e8ea  lea     r14, _TraceLoggingMetadataEnd
0x18003e8f1  lea     r13, _TraceLoggingMetadata
0x18003e8f8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18003e8ff  cmp     eax, 4
0x18003e902  jbe     loc_18003EA58
0x18003e908  mov     rax, cs:gIkeExtGlobals
0x18003e90f  test    rax, rax
0x18003e912  jz      short loc_18003E93D
0x18003e914  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003e91a  cmp     ecx, 0FFFFFFFFh
0x18003e91d  jz      short loc_18003E93D
0x18003e91f  call    cs:__imp_TlsGetValue
0x18003e925  test    rax, rax
0x18003e928  jz      short loc_18003E936
0x18003e92a  mov     rcx, [rax]
0x18003e92d  mov     rax, cs:gIkeExtGlobals
0x18003e934  jmp     short loc_18003E940
0x18003e936  mov     rax, cs:gIkeExtGlobals
0x18003e93d  mov     rcx, r15
0x18003e940  mov     [rsp+200h+var_1A8], rcx
0x18003e945  lea     rcx, [rsp+200h+var_1A8]
0x18003e94a  mov     [rbp+100h+var_C0], rcx
0x18003e94e  mov     [rbp+100h+var_B8], 8
0x18003e956  test    rax, rax
0x18003e959  jz      short loc_18003E995
0x18003e95b  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003e961  cmp     ecx, 0FFFFFFFFh
0x18003e964  jz      short loc_18003E995
0x18003e966  call    cs:__imp_TlsGetValue
0x18003e96c  test    rax, rax
0x18003e96f  lea     rdx, [rax+8]
0x18003e973  cmovz   rdx, r15
0x18003e977  test    rdx, rdx
0x18003e97a  jz      short loc_18003E995
0x18003e97c  mov     rax, rbx
0x18003e97f  nop
0x18003e980  cmp     [rdx+rax*2+2], r15w
0x18003e986  lea     rax, [rax+1]
0x18003e98a  jnz     short loc_18003E980
0x18003e98c  lea     eax, ds:2[rax*2]
0x18003e993  jmp     short loc_18003E9A1
0x18003e995  lea     rdx, LocaleName
0x18003e99c  mov     eax, 2
0x18003e9a1  mov     [rbp+100h+var_A8], eax
0x18003e9a4  xor     r9d, r9d
0x18003e9a7  mov     [rbp+100h+var_B0], rdx
0x18003e9ab  lea     rax, [rsp+200h+var_1B8]
0x18003e9b0  mov     [rbp+100h+var_A0], rax
0x18003e9b4  lea     rdx, [rbp+100h+var_F0]
0x18003e9b8  mov     rax, [rdi+68h]
0x18003e9bc  xor     r8d, r8d
0x18003e9bf  mov     [rsp+200h+var_1B0], rax
0x18003e9c4  lea     rax, [rsp+200h+var_1B0]
0x18003e9c9  mov     [rbp+100h+var_90], rax
0x18003e9cd  movzx   eax, cs:word_18015D692
0x18003e9d4  mov     dword ptr [rbp+100h+var_F0+4], eax
0x18003e9d7  mov     rax, cs:off_180173280
0x18003e9de  mov     [rbp+100h+var_E0], rax
0x18003e9e2  mov     [rbp+100h+var_A4], r15d
0x18003e9e6  mov     [rsp+200h+var_1B8], rdi
0x18003e9eb  mov     [rbp+100h+var_98], 8
0x18003e9f3  mov     [rbp+100h+var_88], 8
0x18003e9fb  mov     dword ptr [rbp+100h+var_F0], 0B000000h
0x18003ea02  mov     [rbp+100h+var_E8], r15
0x18003ea06  movzx   eax, word ptr [rax]
0x18003ea09  mov     [rbp+100h+var_D8], eax
0x18003ea0c  lea     rax, dword_18015D69C
0x18003ea13  mov     [rbp+100h+var_D0], rax
0x18003ea17  mov     rax, r14
0x18003ea1a  sub     eax, r13d
0x18003ea1d  mov     [rbp+100h+var_D4], 2
0x18003ea24  mov     [rbp+100h+var_C8], 45h ; 'E'
0x18003ea2b  mov     [rbp+100h+var_C4], 1
0x18003ea32  mov     [rsp+200h+var_1C0], eax
0x18003ea36  mov     eax, [rsp+200h+var_1C0]
0x18003ea3a  mov     rcx, cs:qword_180173298
0x18003ea41  lea     rax, [rbp+100h+var_E0]
0x18003ea45  mov     [rsp+200h+var_1D8], rax
0x18003ea4a  mov     dword ptr [rsp+200h+var_1E0], 6
0x18003ea52  call    cs:__imp_EtwEventWriteTransfer
0x18003ea58  mov     rax, cs:gIkeExtGlobals
0x18003ea5f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003ea65  cmp     ecx, 0FFFFFFFFh
0x18003ea68  jz      short loc_18003EA75
0x18003ea6a  lea     rdx, [rsp+200h+TlsValue]; lpTlsValue
0x18003ea6f  call    cs:__imp_TlsSetValue
0x18003ea75  test    byte ptr cs:Microsoft_Windows_NetworkSecurityEnableBits, 1
0x18003ea7c  jz      short loc_18003EAA3
0x18003ea7e  lea     rax, [rbp+100h+var_60]
0x18003ea85  mov     r9d, 1
0x18003ea8b  lea     rdx, SaContextOperationBeginEvent
0x18003ea92  mov     [rsp+200h+var_1E0], rax
0x18003ea97  lea     rcx, FwxTraceProvider_Context
0x18003ea9e  call    McGenEventWrite_EtwEventWriteTransfer
0x18003eaa3  mov     rcx, rdi; lpCriticalSection
0x18003eaa6  call    cs:__imp_EnterCriticalSection
0x18003eaac  mov     rsi, [rdi+68h]
0x18003eab0  test    rsi, rsi
0x18003eab3  jz      short loc_18003EAEF
0x18003eab5  lea     rcx, [rsi+1B4h]
0x18003eabc  lea     rdx, [rsp+200h+var_198]
0x18003eac1  call    IkeAddrGetAddrString
0x18003eac6  mov     rdx, cs:gIkeExtGlobals
0x18003eacd  mov     rax, [rsi+3E0h]
0x18003ead4  mov     [rsp+200h+TlsValue], rax
0x18003ead9  mov     ecx, [rdx+0D88h]; dwTlsIndex
0x18003eadf  cmp     ecx, 0FFFFFFFFh
0x18003eae2  jz      short loc_18003EAF6
0x18003eae4  lea     rdx, [rsp+200h+TlsValue]; lpTlsValue
0x18003eae9  call    cs:__imp_TlsSetValue
0x18003eaef  mov     rdx, cs:gIkeExtGlobals
0x18003eaf6  cmp     [rdi+5Ch], r15d
0x18003eafa  jz      loc_18003ED04
0x18003eb00  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eb07  cmp     rcx, r12
0x18003eb0a  jz      loc_18003EBA8
0x18003eb10  cmp     byte ptr [rcx+19h], 4
0x18003eb14  jb      loc_18003EBA8
0x18003eb1a  test    byte ptr [rcx+1Ch], 10h
0x18003eb1e  jz      loc_18003EBA8
0x18003eb24  test    rdx, rdx
0x18003eb27  jz      short loc_18003EB4F
0x18003eb29  mov     eax, [rdx+0D88h]
0x18003eb2f  cmp     eax, 0FFFFFFFFh
0x18003eb32  jz      short loc_18003EB4F
0x18003eb34  mov     ecx, eax; dwTlsIndex
0x18003eb36  call    cs:__imp_TlsGetValue
0x18003eb3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eb43  mov     r8, rax
0x18003eb46  mov     rdx, cs:gIkeExtGlobals
0x18003eb4d  jmp     short loc_18003EB52
0x18003eb4f  mov     r8, r15
0x18003eb52  test    r8, r8
0x18003eb55  lea     rsi, [r8+8]
0x18003eb59  cmovz   rsi, r15
0x18003eb5d  test    rdx, rdx
0x18003eb60  jz      short loc_18003EB86
0x18003eb62  mov     eax, [rdx+0D88h]
0x18003eb68  cmp     eax, 0FFFFFFFFh
0x18003eb6b  jz      short loc_18003EB86
0x18003eb6d  mov     ecx, eax; dwTlsIndex
0x18003eb6f  call    cs:__imp_TlsGetValue
0x18003eb75  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eb7c  test    rax, rax
0x18003eb7f  jz      short loc_18003EB86
0x18003eb81  mov     r9, [rax]
0x18003eb84  jmp     short loc_18003EB89
0x18003eb86  mov     r9, r15
0x18003eb89  mov     rcx, [rcx+10h]
0x18003eb8d  lea     r8, WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids
0x18003eb94  mov     edx, 2Bh ; '+'
0x18003eb99  mov     [rsp+200h+var_1D8], rdi
0x18003eb9e  mov     [rsp+200h+var_1E0], rsi
0x18003eba3  call    WPP_SF_iSq
0x18003eba8  mov     eax, cs:dword_180173278
0x18003ebae  cmp     eax, 4
0x18003ebb1  jbe     loc_18003F212
0x18003ebb7  mov     rax, cs:gIkeExtGlobals
0x18003ebbe  test    rax, rax
0x18003ebc1  jz      short loc_18003EBEC
0x18003ebc3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003ebc9  cmp     ecx, 0FFFFFFFFh
0x18003ebcc  jz      short loc_18003EBEC
0x18003ebce  call    cs:__imp_TlsGetValue
0x18003ebd4  test    rax, rax
0x18003ebd7  jz      short loc_18003EBE5
0x18003ebd9  mov     rcx, [rax]
0x18003ebdc  mov     rax, cs:gIkeExtGlobals
0x18003ebe3  jmp     short loc_18003EBEF
0x18003ebe5  mov     rax, cs:gIkeExtGlobals
0x18003ebec  mov     rcx, r15
0x18003ebef  mov     [rsp+200h+var_1B0], rcx
0x18003ebf4  lea     rcx, [rsp+200h+var_1B0]
0x18003ebf9  mov     [rbp+100h+var_C0], rcx
0x18003ebfd  mov     [rbp+100h+var_B8], 8
0x18003ec05  test    rax, rax
0x18003ec08  jz      short loc_18003EC45
0x18003ec0a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003ec10  cmp     ecx, 0FFFFFFFFh
0x18003ec13  jz      short loc_18003EC45
0x18003ec15  call    cs:__imp_TlsGetValue
0x18003ec1b  test    rax, rax
0x18003ec1e  lea     rdx, [rax+8]
0x18003ec22  cmovz   rdx, r15
0x18003ec26  test    rdx, rdx
0x18003ec29  jz      short loc_18003EC45
0x18003ec2b  nop     dword ptr [rax+rax+00h]
0x18003ec30  cmp     [rdx+rbx*2+2], r15w
0x18003ec36  lea     rbx, [rbx+1]
0x18003ec3a  jnz     short loc_18003EC30
0x18003ec3c  lea     ebx, ds:2[rbx*2]
0x18003ec43  jmp     short loc_18003EC51
0x18003ec45  lea     rdx, LocaleName
0x18003ec4c  mov     ebx, 2
0x18003ec51  mov     [rbp+100h+var_B0], rdx
0x18003ec55  lea     rax, aTimercontextAl; "TimerContext already cancelled"
0x18003ec5c  mov     [rbp+100h+var_A0], rax
0x18003ec60  lea     rdx, [rbp+100h+var_F0]
0x18003ec64  lea     rax, [rsp+200h+var_1B8]
0x18003ec69  mov     [rbp+100h+var_A8], ebx
0x18003ec6c  mov     [rbp+100h+var_90], rax
0x18003ec70  sub     r14d, r13d
0x18003ec73  movzx   eax, cs:word_18015D639
0x18003ec7a  xor     r9d, r9d
0x18003ec7d  mov     dword ptr [rbp+100h+var_F0+4], eax
0x18003ec80  xor     r8d, r8d
0x18003ec83  mov     rax, cs:off_180173280
0x18003ec8a  mov     [rbp+100h+var_E0], rax
0x18003ec8e  mov     [rbp+100h+var_A4], r15d
0x18003ec92  mov     [rbp+100h+var_98], 1Fh
0x18003ec9a  mov     [rsp+200h+var_1B8], rdi
0x18003ec9f  mov     [rbp+100h+var_88], 8
0x18003eca7  mov     dword ptr [rbp+100h+var_F0], 0B000000h
0x18003ecae  mov     [rbp+100h+var_E8], r15
0x18003ecb2  movzx   eax, word ptr [rax]
0x18003ecb5  mov     [rbp+100h+var_D8], eax
0x18003ecb8  lea     rax, byte_18015D643
0x18003ecbf  mov     [rbp+100h+var_D0], rax
0x18003ecc3  mov     [rbp+100h+var_D4], 2
0x18003ecca  mov     [rbp+100h+var_C8], 4Dh ; 'M'
0x18003ecd1  mov     [rbp+100h+var_C4], 1
0x18003ecd8  mov     [rsp+200h+var_1C0], r14d
0x18003ecdd  mov     eax, [rsp+200h+var_1C0]
0x18003ece1  mov     rcx, cs:qword_180173298
0x18003ece8  lea     rax, [rbp+100h+var_E0]
0x18003ecec  mov     [rsp+200h+var_1D8], rax
0x18003ecf1  mov     dword ptr [rsp+200h+var_1E0], 6
0x18003ecf9  call    cs:__imp_EtwEventWriteTransfer
0x18003ecff  jmp     loc_18003F212
0x18003ed04  inc     dword ptr [rdi+124h]
0x18003ed0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed11  cmp     rcx, r12
0x18003ed14  jz      loc_18003EDC5
0x18003ed1a  cmp     byte ptr [rcx+19h], 4
0x18003ed1e  jb      loc_18003EDC5
  ... truncated ...
```
