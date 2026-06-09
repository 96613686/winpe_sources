# IkeCanProcessAcquire

- ea: `0x180040d70`
- end: `0x1800416e5`
- name: `IkeCanProcessAcquire`
- size: `2421`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180043fb0`

## callees

- `0x1800061ec`
- `0x180006e60`
- `0x180008388`
- `0x180037290`
- `0x180040d70`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bfa0`
- `0x18005c4b8`
- `0x18007b608`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040e0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040e54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800410dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041154`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800411b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800411fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041373`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800413bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004159d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800415e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040e0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040e54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800410dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041154`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800411b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800411fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041373`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800413bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004159d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800415e4`
- `ntdll!EtwEventWriteTransfer` at `0x180040f21`
- `ntdll!EtwEventWriteTransfer` at `0x1800412cf`
- `ntdll!EtwEventWriteTransfer` at `0x180041513`
- `ntdll!EtwEventWriteTransfer` at `0x1800416b4`
- `ntdll!EtwEventWriteTransfer` at `0x180040f21`
- `ntdll!EtwEventWriteTransfer` at `0x1800412cf`
- `ntdll!EtwEventWriteTransfer` at `0x180041513`
- `ntdll!EtwEventWriteTransfer` at `0x1800416b4`

## string_xrefs

- `0x18004140b`: `Dropping acquire because SA state already exists`
- `0x180041242`: `Dropping AuthIP acquire because it contains                   peer impersonate token & no MM state exists`

## pseudocode

```c
__int64 __fastcall IkeCanProcessAcquire(__int64 a1)
{
  __int64 active; // rdi
  __int64 v3; // r12
  LPCRITICAL_SECTION v4; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v7; // rcx
  DWORD v8; // ecx
  char *v9; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  int v13; // eax
  __int64 v14; // r10
  unsigned int v15; // r8d
  __int64 v16; // r9
  unsigned int i; // edx
  unsigned int j; // edx
  unsigned int v19; // edx
  __int64 LockSemaphore_low; // rcx
  __int64 v21; // r9
  unsigned int v22; // edx
  __int64 v23; // r9
  unsigned int v24; // r15d
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  _QWORD *v29; // rsi
  DWORD v30; // ecx
  __int64 *v31; // rax
  __int64 v32; // r14
  _QWORD *v33; // rbx
  __int64 *v34; // rax
  __int64 v35; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v37; // rax
  DWORD v38; // ecx
  __int64 *v39; // rax
  __int64 v40; // rcx
  DWORD v41; // ecx
  char *v42; // rax
  const WCHAR *v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  __int64 KeyModString; // rax
  __int64 v47; // rsi
  __int64 v48; // rdi
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rbx
  __int64 v53; // rcx
  __int64 v54; // rax
  LPCRITICAL_SECTION v55; // rax
  DWORD v56; // ecx
  __int64 *v57; // rax
  __int64 v58; // rcx
  DWORD v59; // ecx
  char *v60; // rax
  const WCHAR *v61; // rdx
  __int64 v62; // rax
  int v63; // eax
  const char *v64; // rcx
  int v65; // eax
  const char *v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rax
  LPCRITICAL_SECTION v69; // rax
  DWORD v70; // ecx
  __int64 *v71; // rax
  __int64 v72; // rcx
  DWORD v73; // ecx
  char *v74; // rax
  const WCHAR *v75; // rdx
  int v76; // eax
  int v78; // [rsp+44h] [rbp-95h] BYREF
  unsigned int v79; // [rsp+48h] [rbp-91h] BYREF
  __int64 v80; // [rsp+50h] [rbp-89h] BYREF
  int v81; // [rsp+58h] [rbp-81h] BYREF
  int v82; // [rsp+5Ch] [rbp-7Dh]
  __int64 v83; // [rsp+60h] [rbp-79h]
  char *v84; // [rsp+70h] [rbp-69h] BYREF
  int v85; // [rsp+78h] [rbp-61h]
  int v86; // [rsp+7Ch] [rbp-5Dh]
  __int16 *v87; // [rsp+80h] [rbp-59h]
  int v88; // [rsp+88h] [rbp-51h]
  int v89; // [rsp+8Ch] [rbp-4Dh]
  __int64 *v90; // [rsp+90h] [rbp-49h]
  __int64 v91; // [rsp+98h] [rbp-41h]
  const WCHAR *v92; // [rsp+A0h] [rbp-39h]
  int v93; // [rsp+A8h] [rbp-31h]
  int v94; // [rsp+ACh] [rbp-2Dh]
  const char *v95; // [rsp+B0h] [rbp-29h]
  __int64 v96; // [rsp+B8h] [rbp-21h]
  const char *v97; // [rsp+C0h] [rbp-19h]
  int v98; // [rsp+C8h] [rbp-11h]
  int v99; // [rsp+CCh] [rbp-Dh]
  const char *v100; // [rsp+D0h] [rbp-9h]
  int v101; // [rsp+D8h] [rbp-1h]
  int v102; // [rsp+DCh] [rbp+3h]

  v79 = 0;
  v78 = 0;
  active = 0;
  v3 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v4 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v4 = gIkeExtGlobals;
LABEL_9:
    v7 = 0;
    goto LABEL_10;
  }
  v7 = *Value;
  v4 = gIkeExtGlobals;
LABEL_10:
  v80 = v7;
  v90 = &v80;
  v91 = 8;
  if ( !v4 )
    goto LABEL_18;
  v8 = (DWORD)v4[86].LockSemaphore;
  if ( v8 == -1 )
    goto LABEL_18;
  v9 = (char *)TlsGetValue(v8);
  v10 = (const WCHAR *)(v9 + 8);
  if ( !v9 )
    v10 = 0;
  if ( v10 )
  {
    v11 = -1;
    do
      v12 = v10[++v11] == 0;
    while ( !v12 );
    v13 = 2 * v11 + 2;
  }
  else
  {
LABEL_18:
    v10 = &LocaleName;
    v13 = 2;
  }
  v93 = v13;
  v82 = 5;
  v84 = off_180173280;
  v92 = v10;
  v94 = 0;
  v95 = "IkeCanProcessAcquire";
  v96 = 21;
  v81 = 184549376;
  v83 = 1;
  v85 = *(unsigned __int16 *)off_180173280;
  v87 = (__int16 *)&dword_180166EA4;
  v86 = 2;
  v88 = 45;
  v89 = 1;
  EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 5, &v84);
LABEL_20:
  if ( *(_DWORD *)(a1 + 372) != 1 )
    goto LABEL_43;
  v14 = *(_QWORD *)(a1 + 392);
  if ( !v14 )
    goto LABEL_43;
  v15 = *(_DWORD *)(v14 + 16);
  if ( !v15 )
    goto LABEL_43;
  v16 = *(_QWORD *)(v14 + 24);
  for ( i = 0; i < v15; ++i )
  {
    if ( *(_DWORD *)(v16 + 24LL * i) == 1 && !*(_DWORD *)(v16 + 24LL * i + 4) && !*(_DWORD *)(v16 + 24LL * i + 8) )
      goto LABEL_43;
  }
  for ( j = 0; j < v15; ++j )
  {
    if ( *(_DWORD *)(v16 + 24LL * j) == 1 && !*(_DWORD *)(v16 + 24LL * j + 4) && *(_DWORD *)(v16 + 24LL * j + 8) == 1 )
      goto LABEL_43;
  }
  v19 = 0;
  while ( 1 )
  {
    LockSemaphore_low = 3LL * v19;
    if ( *(_DWORD *)(v16 + 24LL * v19) == 1
      && *(_DWORD *)(v16 + 24LL * v19 + 4) == 1
      && !*(_DWORD *)(v16 + 24LL * v19 + 8) )
    {
      break;
    }
    if ( ++v19 >= v15 )
    {
      v21 = *(_QWORD *)(v14 + 24);
      v22 = 0;
      while ( 1 )
      {
        LockSemaphore_low = 3LL * v22;
        if ( *(_DWORD *)(v21 + 24LL * v22) == 1
          && *(_DWORD *)(v21 + 24LL * v22 + 4) == 1
          && *(_DWORD *)(v21 + 24LL * v22 + 8) == 1 )
        {
          goto LABEL_54;
        }
        if ( ++v22 >= v15 )
          goto LABEL_43;
      }
    }
  }
LABEL_54:
  if ( *(_DWORD *)(a1 + 312) != 2 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals )
      {
        LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore);
        if ( (_DWORD)LockSemaphore_low != -1 )
        {
          v34 = (__int64 *)TlsGetValue(LockSemaphore_low);
          v33 = WPP_GLOBAL_Control;
          if ( v34 )
            active = *v34;
        }
      }
      v35 = v33[2];
      TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
      WPP_SF_iS(v35, 10, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, active, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_82;
    v37 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v38 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v38 != -1 )
      {
        v39 = (__int64 *)TlsGetValue(v38);
        if ( v39 )
        {
          v40 = *v39;
          v37 = gIkeExtGlobals;
LABEL_72:
          v80 = v40;
          v90 = &v80;
          v91 = 8;
          if ( !v37 )
            goto LABEL_80;
          v41 = (DWORD)v37[86].LockSemaphore;
          if ( v41 == -1 )
            goto LABEL_80;
          v42 = (char *)TlsGetValue(v41);
          v43 = (const WCHAR *)(v42 + 8);
          if ( !v42 )
            v43 = 0;
          if ( v43 )
          {
            v44 = -1;
            do
              v12 = v43[++v44] == 0;
            while ( !v12 );
            v45 = 2 * v44 + 2;
          }
          else
          {
LABEL_80:
            v43 = &LocaleName;
            v45 = 2;
          }
          v93 = v45;
          v92 = v43;
          v95 = "Dropping AuthIP acquire because it contains                   peer impersonate token & no MM state exists";
          v82 = 4;
          v84 = off_180173280;
          v94 = 0;
          v96 = 106;
          v81 = 184549376;
          v83 = 0;
          v85 = *(unsigned __int16 *)off_180173280;
          v87 = &word_18016248E;
          v86 = 2;
          v88 = 55;
          v89 = 1;
          EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 5, &v84);
LABEL_82:
          active = WfpReportSysErrorAsWinError(LockSemaphore_low, "IkeCanProcessAcquire", 13809, 1);
          goto LABEL_114;
        }
        v37 = gIkeExtGlobals;
      }
    }
    v40 = 0;
    goto LABEL_72;
  }
  active = IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken(a1);
  if ( active )
    goto LABEL_114;
LABEL_43:
  if ( (*(_BYTE *)(a1 + 376) & 1) != 0 )
  {
    active = DoesActivePeerStateExist((int)a1 + 16, *(_DWORD *)(a1 + 372), 1, 1, 1, (__int64)&v78, (__int64)&v79);
    if ( !active )
    {
      if ( v78 )
      {
        v24 = v79;
        if ( (unsigned int)IkeIsKeyModEnabledForTraffic(v79, (_BYTE *)(a1 + 16), a1 + 184, v23) )
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            if ( gIkeExtGlobals
              && (v30 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v30 != -1)
              && (v31 = (__int64 *)TlsGetValue(v30), v29 = WPP_GLOBAL_Control, v31) )
            {
              v32 = *v31;
            }
            else
            {
              LODWORD(v32) = 0;
            }
            KeyModString = IkeGetKeyModString(*(unsigned int *)(a1 + 372), v25, v27, v28);
            v47 = v29[2];
            v48 = KeyModString;
            v52 = IkeGetKeyModString(v24, v49, v50, v51);
            v54 = IkeGetTlsPeerAddr(v53);
            WPP_SF_iSss(v47, 11, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, v32, v54, v48, v52);
          }
          if ( (unsigned int)dword_180173278 <= 4 )
            goto LABEL_113;
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
LABEL_92:
                v80 = v58;
                v90 = &v80;
                v91 = 8;
                if ( !v55 )
                  goto LABEL_100;
                v59 = (DWORD)v55[86].LockSemaphore;
                if ( v59 == -1 )
                  goto LABEL_100;
                v60 = (char *)TlsGetValue(v59);
                v61 = (const WCHAR *)(v60 + 8);
                if ( !v60 )
                  v61 = 0;
                if ( v61 )
                {
                  v62 = -1;
                  do
                    v12 = v61[++v62] == 0;
                  while ( !v12 );
                  v63 = 2 * v62 + 2;
                }
                else
                {
LABEL_100:
                  v61 = &LocaleName;
                  v63 = 2;
                }
                v93 = v63;
                v92 = v61;
                v95 = "Dropping acquire because SA state already exists";
                v64 = "IKE";
                v65 = *(_DWORD *)(a1 + 372);
                v94 = 0;
                v96 = 49;
                if ( v65 )
                {
                  v66 = "IKEv2";
                  if ( v65 != 2 )
                    v66 = "AUTHIP";
                }
                else
                {
                  v66 = "IKE";
                }
                v67 = -1;
                do
                  ++v67;
                while ( v66[v67] );
                v97 = v66;
                v98 = v67 + 1;
                v99 = 0;
                if ( v24 )
                {
                  v64 = "IKEv2";
                  if ( v24 != 2 )
                    v64 = "AUTHIP";
                }
                v68 = -1;
                do
                  ++v68;
                while ( v64[v68] );
                v100 = v64;
                v101 = v68 + 1;
                v82 = 4;
                v84 = off_180173280;
                v102 = 0;
                v81 = 184549376;
                v83 = 0;
                v85 = *(unsigned __int16 *)off_180173280;
                v87 = &word_1801623D6;
                v86 = 2;
                v88 = 93;
                v89 = 1;
                EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 7, &v84);
LABEL_113:
                active = WfpReportSysErrorAsWinError(v26, "IkeCanProcessAcquire", 13809, 1);
                goto LABEL_114;
              }
              v55 = gIkeExtGlobals;
            }
          }
          v58 = 0;
          goto LABEL_92;
        }
      }
    }
  }
LABEL_114:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(active, "IkeCanProcessAcquire");
  v69 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_122;
  v70 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v70 == -1 )
    goto LABEL_122;
  v71 = (__int64 *)TlsGetValue(v70);
  if ( !v71 )
  {
    v69 = gIkeExtGlobals;
LABEL_122:
    v72 = 0;
    goto LABEL_123;
  }
  v72 = *v71;
  v69 = gIkeExtGlobals;
LABEL_123:
  v80 = v72;
  v90 = &v80;
  v91 = 8;
  if ( !v69 )
    goto LABEL_130;
  v73 = (DWORD)v69[86].LockSemaphore;
  if ( v73 == -1 )
    goto LABEL_130;
  v74 = (char *)TlsGetValue(v73);
  v75 = (const WCHAR *)(v74 + 8);
  if ( !v74 )
    v75 = 0;
  if ( v75 )
  {
    do
      v12 = v75[++v3] == 0;
    while ( !v12 );
    v76 = 2 * v3 + 2;
  }
  else
  {
LABEL_130:
    v75 = &LocaleName;
    v76 = 2;
  }
  v93 = v76;
  v82 = 5;
  v84 = off_180173280;
  v92 = v75;
  v94 = 0;
  v95 = "IkeCanProcessAcquire";
  v96 = 21;
  v81 = 184549376;
  v83 = 1;
  v85 = *(unsigned __int16 *)off_180173280;
  v87 = (__int16 *)byte_180166E6B;
  v86 = 2;
  v88 = 45;
  v89 = 1;
  EtwEventWriteTransfer(qword_180173298, &v81, 0, 0, 5, &v84);
  return IkeReturnError(active, "IkeCanProcessAcquire");
}

```

## disassembly

```asm
0x180040d70  push    rbp
0x180040d72  push    rbx
0x180040d73  push    rsi
0x180040d74  push    rdi
0x180040d75  push    r12
0x180040d77  push    r13
0x180040d79  push    r14
0x180040d7b  push    r15
0x180040d7d  lea     rbp, [rsp-1Fh]
0x180040d82  sub     rsp, 0F8h
0x180040d89  mov     rax, cs:__security_cookie
0x180040d90  xor     rax, rsp
0x180040d93  mov     [rbp+57h+var_50], rax
0x180040d97  mov     eax, cs:dword_180173278
0x180040d9d  lea     r15, aIkecanprocessa; "IkeCanProcessAcquire"
0x180040da4  xor     esi, esi
0x180040da6  lea     r14, _TraceLoggingMetadataEnd
0x180040dad  mov     [rsp+130h+var_E8], esi
0x180040db1  mov     r13, rcx
0x180040db4  mov     [rsp+130h+var_EC], esi
0x180040db8  mov     edi, esi
0x180040dba  lea     rbx, _TraceLoggingMetadata
0x180040dc1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180040dc8  cmp     eax, 5
0x180040dcb  jbe     loc_180040F27
0x180040dd1  mov     rcx, cs:qword_180173290
0x180040dd8  mov     rax, cs:qword_180173288
0x180040ddf  test    al, 1
0x180040de1  jz      loc_180040F27
0x180040de7  mov     rax, rcx
0x180040dea  and     eax, 1
0x180040ded  cmp     rax, rcx
0x180040df0  jnz     loc_180040F27
0x180040df6  mov     rax, cs:gIkeExtGlobals
0x180040dfd  test    rax, rax
0x180040e00  jz      short loc_180040E2B
0x180040e02  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180040e08  cmp     ecx, 0FFFFFFFFh
0x180040e0b  jz      short loc_180040E2B
0x180040e0d  call    cs:__imp_TlsGetValue
0x180040e13  test    rax, rax
0x180040e16  jz      short loc_180040E24
0x180040e18  mov     rcx, [rax]
0x180040e1b  mov     rax, cs:gIkeExtGlobals
0x180040e22  jmp     short loc_180040E2E
0x180040e24  mov     rax, cs:gIkeExtGlobals
0x180040e2b  mov     rcx, rsi
0x180040e2e  mov     [rsp+130h+var_E0], rcx
0x180040e33  lea     rcx, [rsp+130h+var_E0]
0x180040e38  mov     [rbp+57h+var_A0], rcx
0x180040e3c  mov     [rbp+57h+var_98], 8
0x180040e44  test    rax, rax
0x180040e47  jz      short loc_180040E84
0x180040e49  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180040e4f  cmp     ecx, 0FFFFFFFFh
0x180040e52  jz      short loc_180040E84
0x180040e54  call    cs:__imp_TlsGetValue
0x180040e5a  test    rax, rax
0x180040e5d  lea     rdx, [rax+8]
0x180040e61  cmovz   rdx, rsi
0x180040e65  test    rdx, rdx
0x180040e68  jz      short loc_180040E84
0x180040e6a  mov     rax, r12
0x180040e6d  nop     dword ptr [rax]
0x180040e70  cmp     [rdx+rax*2+2], si
0x180040e75  lea     rax, [rax+1]
0x180040e79  jnz     short loc_180040E70
0x180040e7b  lea     eax, ds:2[rax*2]
0x180040e82  jmp     short loc_180040E90
0x180040e84  lea     rdx, LocaleName
0x180040e8b  mov     eax, 2
0x180040e90  mov     [rbp+57h+var_88], eax
0x180040e93  xor     r9d, r9d
0x180040e96  movzx   eax, cs:word_180166E9A
0x180040e9d  xor     r8d, r8d
0x180040ea0  mov     [rbp+57h+var_D4], eax
0x180040ea3  mov     rax, cs:off_180173280
0x180040eaa  mov     [rbp+57h+var_C0], rax
0x180040eae  mov     [rbp+57h+var_90], rdx
0x180040eb2  lea     rdx, [rsp+130h+var_D8]
0x180040eb7  mov     [rbp+57h+var_84], esi
0x180040eba  mov     [rbp+57h+var_80], r15
0x180040ebe  mov     [rbp+57h+var_78], 15h
0x180040ec6  mov     [rsp+130h+var_D8], 0B000000h
0x180040ece  mov     [rbp+57h+var_D0], 1
0x180040ed6  movzx   eax, word ptr [rax]
0x180040ed9  mov     [rbp+57h+var_B8], eax
0x180040edc  lea     rax, dword_180166EA4
0x180040ee3  mov     [rbp+57h+var_B0], rax
0x180040ee7  mov     rax, r14
0x180040eea  sub     eax, ebx
0x180040eec  mov     [rbp+57h+var_B4], 2
0x180040ef3  mov     [rbp+57h+var_A8], 2Dh ; '-'
0x180040efa  mov     [rbp+57h+var_A4], 1
0x180040f01  mov     [rsp+130h+var_F0], eax
0x180040f05  mov     eax, [rsp+130h+var_F0]
0x180040f09  mov     rcx, cs:qword_180173298
0x180040f10  lea     rax, [rbp+57h+var_C0]
0x180040f14  mov     [rsp+130h+var_108], rax
0x180040f19  mov     dword ptr [rsp+130h+var_110], 5
0x180040f21  call    cs:__imp_EtwEventWriteTransfer
0x180040f27  cmp     dword ptr [r13+174h], 1
0x180040f2f  jnz     loc_18004101A
0x180040f35  mov     r10, [r13+188h]
0x180040f3c  test    r10, r10
0x180040f3f  jz      loc_18004101A
0x180040f45  mov     r8d, [r10+10h]
0x180040f49  test    r8d, r8d
0x180040f4c  jz      loc_18004101A
0x180040f52  mov     r9, [r10+18h]
0x180040f56  mov     edx, esi
0x180040f58  nop     dword ptr [rax+rax+00000000h]
0x180040f60  mov     eax, edx
0x180040f62  lea     rcx, [rax+rax*2]
0x180040f66  cmp     dword ptr [r9+rcx*8], 1
0x180040f6b  jnz     short loc_180040F7F
0x180040f6d  cmp     [r9+rcx*8+4], esi
0x180040f72  jnz     short loc_180040F7F
0x180040f74  cmp     [r9+rcx*8+8], esi
0x180040f79  jz      loc_18004101A
0x180040f7f  inc     edx
0x180040f81  cmp     edx, r8d
0x180040f84  jb      short loc_180040F60
0x180040f86  mov     edx, esi
0x180040f88  nop     dword ptr [rax+rax+00000000h]
0x180040f90  mov     eax, edx
0x180040f92  lea     rcx, [rax+rax*2]
0x180040f96  cmp     dword ptr [r9+rcx*8], 1
0x180040f9b  jnz     short loc_180040FAC
0x180040f9d  cmp     [r9+rcx*8+4], esi
0x180040fa2  jnz     short loc_180040FAC
0x180040fa4  cmp     dword ptr [r9+rcx*8+8], 1
0x180040faa  jz      short loc_18004101A
0x180040fac  inc     edx
0x180040fae  cmp     edx, r8d
0x180040fb1  jb      short loc_180040F90
0x180040fb3  mov     edx, esi
0x180040fb5  nop     word ptr [rax+rax+00000000h]
0x180040fc0  mov     eax, edx
0x180040fc2  lea     rcx, [rax+rax*2]
0x180040fc6  cmp     dword ptr [r9+rcx*8], 1
0x180040fcb  jnz     short loc_180040FE0
0x180040fcd  cmp     dword ptr [r9+rcx*8+4], 1
0x180040fd3  jnz     short loc_180040FE0
0x180040fd5  cmp     [r9+rcx*8+8], esi
0x180040fda  jz      loc_1800410FB
0x180040fe0  inc     edx
0x180040fe2  cmp     edx, r8d
0x180040fe5  jb      short loc_180040FC0
0x180040fe7  test    r8d, r8d
0x180040fea  jz      short loc_18004101A
0x180040fec  mov     r9, [r10+18h]
0x180040ff0  mov     edx, esi
0x180040ff2  mov     eax, edx
0x180040ff4  lea     rcx, [rax+rax*2]
0x180040ff8  cmp     dword ptr [r9+rcx*8], 1
0x180040ffd  jnz     short loc_180041013
0x180040fff  cmp     dword ptr [r9+rcx*8+4], 1
0x180041005  jnz     short loc_180041013
0x180041007  cmp     dword ptr [r9+rcx*8+8], 1
0x18004100d  jz      loc_1800410FB
0x180041013  inc     edx
0x180041015  cmp     edx, r8d
0x180041018  jb      short loc_180040FF2
0x18004101a  test    byte ptr [r13+178h], 1
0x180041022  jz      loc_180041552
0x180041028  mov     edx, [r13+174h]
0x18004102f  lea     rax, [rsp+130h+var_E8]
0x180041034  mov     [rsp+130h+var_100], rax
0x180041039  lea     rcx, [r13+10h]
0x18004103d  lea     rax, [rsp+130h+var_EC]
0x180041042  mov     r9d, 1
0x180041048  mov     [rsp+130h+var_108], rax
0x18004104d  mov     r8d, r9d
0x180041050  mov     dword ptr [rsp+130h+var_110], 1
0x180041058  call    DoesActivePeerStateExist
0x18004105d  mov     rdi, rax
0x180041060  test    rax, rax
0x180041063  jnz     loc_18004154B
0x180041069  cmp     [rsp+130h+var_EC], esi
0x18004106d  jz      loc_18004154B
0x180041073  mov     r15d, [rsp+130h+var_E8]
0x180041078  lea     r8, [r13+0B8h]
0x18004107f  mov     ecx, r15d
0x180041082  lea     rdx, [r13+10h]
0x180041086  call    IkeIsKeyModEnabledForTraffic
0x18004108b  test    eax, eax
0x18004108d  jz      loc_180041544
0x180041093  mov     rsi, cs:WPP_GLOBAL_Control
0x18004109a  lea     rax, WPP_GLOBAL_Control
0x1800410a1  cmp     rsi, rax
0x1800410a4  jz      loc_18004134D
0x1800410aa  cmp     byte ptr [rsi+19h], 4
0x1800410ae  jb      loc_18004134D
0x1800410b4  test    byte ptr [rsi+1Ch], 10h
0x1800410b8  jz      loc_18004134D
0x1800410be  mov     rax, cs:gIkeExtGlobals
0x1800410c5  test    rax, rax
0x1800410c8  jz      loc_1800412FA
0x1800410ce  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800410d4  cmp     ecx, 0FFFFFFFFh
0x1800410d7  jz      loc_1800412FA
0x1800410dd  call    cs:__imp_TlsGetValue
0x1800410e3  mov     rsi, cs:WPP_GLOBAL_Control
0x1800410ea  test    rax, rax
0x1800410ed  jz      loc_1800412FA
0x1800410f3  mov     r14, [rax]
0x1800410f6  jmp     loc_1800412FD
0x1800410fb  cmp     dword ptr [r13+138h], 2
0x180041103  jnz     short loc_18004111E
0x180041105  mov     rcx, r13
0x180041108  call    IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken
0x18004110d  mov     rdi, rax
0x180041110  test    rax, rax
0x180041113  jnz     loc_180041552
0x180041119  jmp     loc_18004101A
0x18004111e  mov     rbx, cs:WPP_GLOBAL_Control
0x180041125  lea     rax, WPP_GLOBAL_Control
0x18004112c  cmp     rbx, rax
0x18004112f  jz      short loc_18004118E
0x180041131  cmp     byte ptr [rbx+19h], 4
0x180041135  jb      short loc_18004118E
0x180041137  test    byte ptr [rbx+1Ch], 10h
0x18004113b  jz      short loc_18004118E
0x18004113d  mov     rax, cs:gIkeExtGlobals
0x180041144  test    rax, rax
0x180041147  jz      short loc_180041169
0x180041149  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004114f  cmp     ecx, 0FFFFFFFFh
0x180041152  jz      short loc_180041169
0x180041154  call    cs:__imp_TlsGetValue
0x18004115a  mov     rbx, cs:WPP_GLOBAL_Control
0x180041161  test    rax, rax
0x180041164  jz      short loc_180041169
0x180041166  mov     rdi, [rax]
0x180041169  mov     rbx, [rbx+10h]
0x18004116d  call    IkeGetTlsPeerAddr
0x180041172  mov     edx, 0Ah
0x180041177  mov     [rsp+130h+var_110], rax
0x18004117c  mov     r9, rdi
0x18004117f  lea     r8, WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids
0x180041186  mov     rcx, rbx
0x180041189  call    WPP_SF_iS
0x18004118e  mov     eax, cs:dword_180173278
0x180041194  cmp     eax, 4
0x180041197  jbe     loc_1800412D7
0x18004119d  mov     rax, cs:gIkeExtGlobals
0x1800411a4  test    rax, rax
0x1800411a7  jz      short loc_1800411D2
0x1800411a9  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800411af  cmp     ecx, 0FFFFFFFFh
0x1800411b2  jz      short loc_1800411D2
0x1800411b4  call    cs:__imp_TlsGetValue
0x1800411ba  test    rax, rax
0x1800411bd  jz      short loc_1800411CB
0x1800411bf  mov     rcx, [rax]
0x1800411c2  mov     rax, cs:gIkeExtGlobals
0x1800411c9  jmp     short loc_1800411D5
0x1800411cb  mov     rax, cs:gIkeExtGlobals
0x1800411d2  mov     rcx, rsi
0x1800411d5  mov     [rsp+130h+var_E0], rcx
0x1800411da  lea     rcx, [rsp+130h+var_E0]
0x1800411df  mov     [rbp+57h+var_A0], rcx
0x1800411e3  mov     [rbp+57h+var_98], 8
0x1800411eb  test    rax, rax
0x1800411ee  jz      short loc_180041228
0x1800411f0  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800411f6  cmp     ecx, 0FFFFFFFFh
0x1800411f9  jz      short loc_180041228
0x1800411fb  call    cs:__imp_TlsGetValue
0x180041201  test    rax, rax
0x180041204  lea     rdx, [rax+8]
0x180041208  cmovz   rdx, rsi
0x18004120c  test    rdx, rdx
0x18004120f  jz      short loc_180041228
0x180041211  mov     rax, r12
0x180041214  cmp     [rdx+rax*2+2], si
0x180041219  lea     rax, [rax+1]
0x18004121d  jnz     short loc_180041214
0x18004121f  lea     eax, ds:2[rax*2]
0x180041226  jmp     short loc_180041234
0x180041228  lea     rdx, LocaleName
0x18004122f  mov     eax, 2
0x180041234  mov     [rbp+57h+var_88], eax
0x180041237  lea     rbx, _TraceLoggingMetadata
0x18004123e  mov     [rbp+57h+var_90], rdx
0x180041242  lea     rax, aDroppingAuthip; "Dropping AuthIP acquire because it cont"...
0x180041249  mov     [rbp+57h+var_80], rax
0x18004124d  lea     rdx, [rsp+130h+var_D8]
0x180041252  movzx   eax, cs:word_180162484
0x180041259  xor     r9d, r9d
0x18004125c  mov     [rbp+57h+var_D4], eax
0x18004125f  xor     r8d, r8d
0x180041262  mov     rax, cs:off_180173280
0x180041269  mov     [rbp+57h+var_C0], rax
0x18004126d  mov     [rbp+57h+var_84], esi
0x180041270  mov     [rbp+57h+var_78], 6Ah ; 'j'
0x180041278  mov     [rsp+130h+var_D8], 0B000000h
0x180041280  mov     [rbp+57h+var_D0], rsi
0x180041284  movzx   eax, word ptr [rax]
  ... truncated ...
```
