# IkeCanProcessAcquire

- ea: `0x180040d70`
- end: `0x1800416e5`
- name: `IkeCanProcessAcquire`
- size: `2421`
- prototype: `__int64 __fastcall(__int64)`
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

- `0x180041242`: `Dropping AuthIP acquire because it contains                   peer impersonate token & no MM state exists`
- `0x18004140b`: `Dropping acquire because SA state already exists`

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
  unsigned int v23; // r15d
  __int64 v24; // rcx
  _QWORD *v25; // rsi
  DWORD v26; // ecx
  __int64 *v27; // rax
  __int64 v28; // r14
  _QWORD *v29; // rbx
  __int64 *v30; // rax
  __int64 v31; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v33; // rax
  DWORD v34; // ecx
  __int64 *v35; // rax
  __int64 v36; // rcx
  DWORD v37; // ecx
  char *v38; // rax
  const WCHAR *v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  __int64 KeyModString; // rax
  __int64 v43; // rsi
  __int64 v44; // rdi
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rax
  LPCRITICAL_SECTION v48; // rax
  DWORD v49; // ecx
  __int64 *v50; // rax
  __int64 v51; // rcx
  DWORD v52; // ecx
  char *v53; // rax
  const WCHAR *v54; // rdx
  __int64 v55; // rax
  int v56; // eax
  const char *v57; // rcx
  int v58; // eax
  const char *v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rax
  LPCRITICAL_SECTION v62; // rax
  DWORD v63; // ecx
  __int64 *v64; // rax
  __int64 v65; // rcx
  DWORD v66; // ecx
  char *v67; // rax
  const WCHAR *v68; // rdx
  int v69; // eax
  int v71; // [rsp+44h] [rbp-95h] BYREF
  unsigned int v72; // [rsp+48h] [rbp-91h] BYREF
  __int64 v73; // [rsp+50h] [rbp-89h] BYREF
  int v74; // [rsp+58h] [rbp-81h] BYREF
  int v75; // [rsp+5Ch] [rbp-7Dh]
  __int64 v76; // [rsp+60h] [rbp-79h]
  char *v77; // [rsp+70h] [rbp-69h] BYREF
  int v78; // [rsp+78h] [rbp-61h]
  int v79; // [rsp+7Ch] [rbp-5Dh]
  char *v80; // [rsp+80h] [rbp-59h]
  int v81; // [rsp+88h] [rbp-51h]
  int v82; // [rsp+8Ch] [rbp-4Dh]
  __int64 *v83; // [rsp+90h] [rbp-49h]
  __int64 v84; // [rsp+98h] [rbp-41h]
  const WCHAR *v85; // [rsp+A0h] [rbp-39h]
  int v86; // [rsp+A8h] [rbp-31h]
  int v87; // [rsp+ACh] [rbp-2Dh]
  const char *v88; // [rsp+B0h] [rbp-29h]
  __int64 v89; // [rsp+B8h] [rbp-21h]
  const char *v90; // [rsp+C0h] [rbp-19h]
  int v91; // [rsp+C8h] [rbp-11h]
  int v92; // [rsp+CCh] [rbp-Dh]
  const char *v93; // [rsp+D0h] [rbp-9h]
  int v94; // [rsp+D8h] [rbp-1h]
  int v95; // [rsp+DCh] [rbp+3h]

  v72 = 0;
  v71 = 0;
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
  v73 = v7;
  v83 = &v73;
  v84 = 8;
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
  v86 = v13;
  v75 = 5;
  v77 = off_180173280;
  v85 = v10;
  v87 = 0;
  v88 = "IkeCanProcessAcquire";
  v89 = 21;
  v74 = 184549376;
  v76 = 1;
  v78 = *(unsigned __int16 *)off_180173280;
  v80 = (char *)&dword_180166EA4;
  v79 = 2;
  v81 = 45;
  v82 = 1;
  EtwEventWriteTransfer(qword_180173298, &v74, 0, 0, 5, &v77);
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
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals )
      {
        LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore);
        if ( (_DWORD)LockSemaphore_low != -1 )
        {
          v30 = (__int64 *)TlsGetValue(LockSemaphore_low);
          v29 = WPP_GLOBAL_Control;
          if ( v30 )
            active = *v30;
        }
      }
      v31 = v29[2];
      TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
      WPP_SF_iS(v31, 10, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, active, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_82;
    v33 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v34 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v34 != -1 )
      {
        v35 = (__int64 *)TlsGetValue(v34);
        if ( v35 )
        {
          v36 = *v35;
          v33 = gIkeExtGlobals;
LABEL_72:
          v73 = v36;
          v83 = &v73;
          v84 = 8;
          if ( !v33 )
            goto LABEL_80;
          v37 = (DWORD)v33[86].LockSemaphore;
          if ( v37 == -1 )
            goto LABEL_80;
          v38 = (char *)TlsGetValue(v37);
          v39 = (const WCHAR *)(v38 + 8);
          if ( !v38 )
            v39 = 0;
          if ( v39 )
          {
            v40 = -1;
            do
              v12 = v39[++v40] == 0;
            while ( !v12 );
            v41 = 2 * v40 + 2;
          }
          else
          {
LABEL_80:
            v39 = &LocaleName;
            v41 = 2;
          }
          v86 = v41;
          v85 = v39;
          v88 = "Dropping AuthIP acquire because it contains                   peer impersonate token & no MM state exists";
          v75 = 4;
          v77 = off_180173280;
          v87 = 0;
          v89 = 106;
          v74 = 184549376;
          v76 = 0;
          v78 = *(unsigned __int16 *)off_180173280;
          v80 = byte_180162425;
          v79 = 2;
          v81 = 55;
          v82 = 1;
          EtwEventWriteTransfer(qword_180173298, &v74, 0, 0, 5, &v77);
LABEL_82:
          active = WfpReportSysErrorAsWinError(LockSemaphore_low, "IkeCanProcessAcquire", 13809, 1);
          goto LABEL_114;
        }
        v33 = gIkeExtGlobals;
      }
    }
    v36 = 0;
    goto LABEL_72;
  }
  active = IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken(a1);
  if ( active )
    goto LABEL_114;
LABEL_43:
  if ( (*(_BYTE *)(a1 + 376) & 1) != 0 )
  {
    active = DoesActivePeerStateExist((int)a1 + 16, *(_DWORD *)(a1 + 372), 1, 1, 1, (__int64)&v71, (__int64)&v72);
    if ( !active )
    {
      if ( v71 )
      {
        v23 = v72;
        if ( (unsigned int)IkeIsKeyModEnabledForTraffic(v72, a1 + 16, a1 + 184) )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            if ( gIkeExtGlobals
              && (v26 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v26 != -1)
              && (v27 = (__int64 *)TlsGetValue(v26), v25 = WPP_GLOBAL_Control, v27) )
            {
              v28 = *v27;
            }
            else
            {
              LODWORD(v28) = 0;
            }
            KeyModString = IkeGetKeyModString(*(unsigned int *)(a1 + 372));
            v43 = v25[2];
            v44 = KeyModString;
            v45 = IkeGetKeyModString(v23);
            v47 = IkeGetTlsPeerAddr(v46);
            WPP_SF_iSss(v43, 11, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, v28, v47, v44, v45);
          }
          if ( (unsigned int)dword_180173278 <= 4 )
            goto LABEL_113;
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
LABEL_92:
                v73 = v51;
                v83 = &v73;
                v84 = 8;
                if ( !v48 )
                  goto LABEL_100;
                v52 = (DWORD)v48[86].LockSemaphore;
                if ( v52 == -1 )
                  goto LABEL_100;
                v53 = (char *)TlsGetValue(v52);
                v54 = (const WCHAR *)(v53 + 8);
                if ( !v53 )
                  v54 = 0;
                if ( v54 )
                {
                  v55 = -1;
                  do
                    v12 = v54[++v55] == 0;
                  while ( !v12 );
                  v56 = 2 * v55 + 2;
                }
                else
                {
LABEL_100:
                  v54 = &LocaleName;
                  v56 = 2;
                }
                v86 = v56;
                v85 = v54;
                v88 = "Dropping acquire because SA state already exists";
                v57 = "IKE";
                v58 = *(_DWORD *)(a1 + 372);
                v87 = 0;
                v89 = 49;
                if ( v58 )
                {
                  v59 = "IKEv2";
                  if ( v58 != 2 )
                    v59 = "AUTHIP";
                }
                else
                {
                  v59 = "IKE";
                }
                v60 = -1;
                do
                  ++v60;
                while ( v59[v60] );
                v90 = v59;
                v91 = v60 + 1;
                v92 = 0;
                if ( v23 )
                {
                  v57 = "IKEv2";
                  if ( v23 != 2 )
                    v57 = "AUTHIP";
                }
                v61 = -1;
                do
                  ++v61;
                while ( v57[v61] );
                v93 = v57;
                v94 = v61 + 1;
                v75 = 4;
                v77 = off_180173280;
                v95 = 0;
                v74 = 184549376;
                v76 = 0;
                v78 = *(unsigned __int16 *)off_180173280;
                v80 = (char *)&unk_180162468;
                v79 = 2;
                v81 = 93;
                v82 = 1;
                EtwEventWriteTransfer(qword_180173298, &v74, 0, 0, 7, &v77);
LABEL_113:
                active = WfpReportSysErrorAsWinError(v24, "IkeCanProcessAcquire", 13809, 1);
                goto LABEL_114;
              }
              v48 = gIkeExtGlobals;
            }
          }
          v51 = 0;
          goto LABEL_92;
        }
      }
    }
  }
LABEL_114:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(active, "IkeCanProcessAcquire");
  v62 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_122;
  v63 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v63 == -1 )
    goto LABEL_122;
  v64 = (__int64 *)TlsGetValue(v63);
  if ( !v64 )
  {
    v62 = gIkeExtGlobals;
LABEL_122:
    v65 = 0;
    goto LABEL_123;
  }
  v65 = *v64;
  v62 = gIkeExtGlobals;
LABEL_123:
  v73 = v65;
  v83 = &v73;
  v84 = 8;
  if ( !v62 )
    goto LABEL_130;
  v66 = (DWORD)v62[86].LockSemaphore;
  if ( v66 == -1 )
    goto LABEL_130;
  v67 = (char *)TlsGetValue(v66);
  v68 = (const WCHAR *)(v67 + 8);
  if ( !v67 )
    v68 = 0;
  if ( v68 )
  {
    do
      v12 = v68[++v3] == 0;
    while ( !v12 );
    v69 = 2 * v3 + 2;
  }
  else
  {
LABEL_130:
    v68 = &LocaleName;
    v69 = 2;
  }
  v86 = v69;
  v75 = 5;
  v77 = off_180173280;
  v85 = v68;
  v87 = 0;
  v88 = "IkeCanProcessAcquire";
  v89 = 21;
  v74 = 184549376;
  v76 = 1;
  v78 = *(unsigned __int16 *)off_180173280;
  v80 = byte_180166E6B;
  v79 = 2;
  v81 = 45;
  v82 = 1;
  EtwEventWriteTransfer(qword_180173298, &v74, 0, 0, 5, &v77);
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
0x180041252  movzx   eax, cs:word_18016241B
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
