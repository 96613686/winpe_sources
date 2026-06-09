# IkeIsKeyModEnabledForTraffic

- ea: `0x180037290`
- end: `0x180037e82`
- name: `IkeIsKeyModEnabledForTraffic`
- size: `3058`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180025110`
- `0x180040d70`
- `0x180046ab0`
- `0x18007660c`
- `0x1800e29fc`

## callees

- `0x1800145f8`
- `0x180014860`
- `0x18001c2d0`
- `0x180035234`
- `0x1800356c0`
- `0x180037290`
- `0x18004890c`
- `0x180050850`
- `0x18005bfa0`
- `0x18005c3d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037347`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003738e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800374b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037534`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003757b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800376bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037703`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037abb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037b02`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c61`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037cff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037d46`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037347`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003738e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800374b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037534`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003757b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800376bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037703`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037abb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037b02`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c61`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037cff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037d46`
- `ntdll!EtwEventWriteTransfer` at `0x180037468`
- `ntdll!EtwEventWriteTransfer` at `0x180037662`
- `ntdll!EtwEventWriteTransfer` at `0x1800379c1`
- `ntdll!EtwEventWriteTransfer` at `0x180037c10`
- `ntdll!EtwEventWriteTransfer` at `0x180037e50`
- `ntdll!EtwEventWriteTransfer` at `0x180037468`
- `ntdll!EtwEventWriteTransfer` at `0x180037662`
- `ntdll!EtwEventWriteTransfer` at `0x1800379c1`
- `ntdll!EtwEventWriteTransfer` at `0x180037c10`
- `ntdll!EtwEventWriteTransfer` at `0x180037e50`

## pseudocode

```c
__int64 __fastcall IkeIsKeyModEnabledForTraffic(unsigned int a1, _BYTE *a2, __int64 a3)
{
  __int64 v6; // rsi
  LPCRITICAL_SECTION v7; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v10; // rcx
  DWORD v11; // ecx
  char *v12; // rax
  const WCHAR *v13; // rdx
  __int64 v14; // rax
  bool v15; // zf
  int v16; // eax
  _QWORD *v17; // rdi
  DWORD v18; // ecx
  __int64 *v19; // rax
  __int64 v20; // r14
  __int64 v21; // rdi
  __int64 KeyModString; // rbx
  __int64 v23; // rcx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v25; // rax
  DWORD v26; // ecx
  __int64 *v27; // rax
  __int64 v28; // rcx
  DWORD v29; // ecx
  char *v30; // rax
  const WCHAR *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  LPCRITICAL_SECTION v34; // rax
  DWORD v35; // ecx
  __int64 *v36; // rax
  __int64 v37; // rcx
  DWORD v38; // ecx
  char *v39; // rax
  const WCHAR *v40; // rdx
  int v41; // esi
  __int64 MMPolicy; // rbx
  LPCRITICAL_SECTION v43; // rax
  DWORD v44; // ecx
  __int64 *v45; // rax
  __int64 v46; // rcx
  DWORD v47; // ecx
  char *v48; // rax
  const WCHAR *v49; // rdx
  __int64 v50; // rax
  int v51; // eax
  LPCRITICAL_SECTION v52; // rdx
  DWORD v53; // ecx
  LPVOID v54; // rax
  LPVOID v55; // rcx
  __int64 v56; // rbx
  DWORD v57; // ecx
  __int64 v58; // rax
  __int64 v59; // r10
  int v60; // r9d
  LPCRITICAL_SECTION v61; // rax
  DWORD v62; // ecx
  __int64 *v63; // rax
  __int64 v64; // rcx
  DWORD v65; // ecx
  char *v66; // rax
  const WCHAR *v67; // rdx
  __int64 v68; // rax
  int v69; // eax
  const char *v70; // rax
  LPCRITICAL_SECTION v72; // rdx
  DWORD v73; // ecx
  LPVOID v74; // rax
  LPVOID v75; // rcx
  __int64 v76; // rbx
  DWORD v77; // ecx
  __int64 v78; // rax
  __int64 v79; // r10
  int v80; // r9d
  LPCRITICAL_SECTION v81; // rax
  DWORD v82; // ecx
  __int64 *v83; // rax
  __int64 v84; // rcx
  DWORD v85; // ecx
  char *v86; // rax
  const WCHAR *v87; // rdx
  __int64 v88; // rax
  int v89; // eax
  const char *v90; // rax
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v92; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v93; // [rsp+68h] [rbp-98h] BYREF
  __int64 v94; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v95[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v96; // [rsp+98h] [rbp-68h]
  int v97; // [rsp+A0h] [rbp-60h] BYREF
  int v98; // [rsp+A4h] [rbp-5Ch]
  __int64 v99; // [rsp+A8h] [rbp-58h]
  char *v100; // [rsp+B0h] [rbp-50h] BYREF
  int v101; // [rsp+B8h] [rbp-48h]
  int v102; // [rsp+BCh] [rbp-44h]
  char *v103; // [rsp+C0h] [rbp-40h]
  int v104; // [rsp+C8h] [rbp-38h]
  int v105; // [rsp+CCh] [rbp-34h]
  __int64 *v106; // [rsp+D0h] [rbp-30h]
  __int64 v107; // [rsp+D8h] [rbp-28h]
  const WCHAR *v108; // [rsp+E0h] [rbp-20h]
  int v109; // [rsp+E8h] [rbp-18h]
  int v110; // [rsp+ECh] [rbp-14h]
  const char *v111; // [rsp+F0h] [rbp-10h]
  __int64 v112; // [rsp+F8h] [rbp-8h]
  const char *v113; // [rsp+100h] [rbp+0h]
  __int64 v114; // [rsp+108h] [rbp+8h]

  lpMem = 0;
  v96 = 0;
  v92 = 0;
  v93 = 0;
  v6 = -1;
  memset(v95, 0, sizeof(v95));
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v7 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v7 = gIkeExtGlobals;
LABEL_9:
    v10 = 0;
    goto LABEL_10;
  }
  v10 = *Value;
  v7 = gIkeExtGlobals;
LABEL_10:
  v94 = v10;
  v106 = &v94;
  v107 = 8;
  if ( !v7 )
    goto LABEL_18;
  v11 = (DWORD)v7[86].LockSemaphore;
  if ( v11 == -1 )
    goto LABEL_18;
  v12 = (char *)TlsGetValue(v11);
  v13 = (const WCHAR *)(v12 + 8);
  if ( !v12 )
    v13 = 0;
  if ( v13 )
  {
    v14 = -1;
    do
      v15 = v13[++v14] == 0;
    while ( !v15 );
    v16 = 2 * v14 + 2;
  }
  else
  {
LABEL_18:
    v13 = &LocaleName;
    v16 = 2;
  }
  v109 = v16;
  v98 = 5;
  v100 = off_180173280;
  v108 = v13;
  v110 = 0;
  v111 = "IkeIsKeyModEnabledForTraffic";
  v112 = 29;
  v97 = 184549376;
  v99 = 1;
  v101 = *(unsigned __int16 *)off_180173280;
  v103 = (char *)&dword_180166EA4;
  v102 = 2;
  v104 = 45;
  v105 = 1;
  EtwEventWriteTransfer(qword_180173298, &v97, 0, 0, 5, &v100);
LABEL_20:
  if ( a1 == 1 && ((__int64)gIkeExtGlobals[50].LockSemaphore & 0x40) != 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v18 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v18 == -1 || (v19 = (__int64 *)TlsGetValue(v18), v17 = WPP_GLOBAL_Control, !v19) )
        LODWORD(v20) = 0;
      else
        v20 = *v19;
      v21 = v17[2];
      KeyModString = IkeGetKeyModString(1);
      TlsPeerAddr = IkeGetTlsPeerAddr(v23);
      WPP_SF_iSs(v21, 50, (unsigned int)WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids, v20, TlsPeerAddr, KeyModString);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
    {
LABEL_47:
      if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
        return 0;
      v34 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v35 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v35 != -1 )
        {
          v36 = (__int64 *)TlsGetValue(v35);
          if ( v36 )
          {
            v37 = *v36;
            v34 = gIkeExtGlobals;
LABEL_56:
            v94 = v37;
            v106 = &v94;
            v107 = 8;
            if ( !v34 )
              goto LABEL_63;
            v38 = (DWORD)v34[86].LockSemaphore;
            if ( v38 == -1 )
              goto LABEL_63;
            v39 = (char *)TlsGetValue(v38);
            v40 = (const WCHAR *)(v39 + 8);
            if ( !v39 )
              v40 = 0;
            if ( v40 )
            {
              do
                v15 = v40[++v6] == 0;
              while ( !v15 );
              v41 = 2 * v6 + 2;
            }
            else
            {
LABEL_63:
              v40 = &LocaleName;
              v41 = 2;
            }
            v98 = 5;
            v100 = off_180173280;
            v108 = v40;
            v109 = v41;
            v110 = 0;
            v111 = "IkeIsKeyModEnabledForTraffic";
            v112 = 29;
            v97 = 184549376;
            v99 = 1;
            v101 = *(unsigned __int16 *)off_180173280;
            v103 = byte_180166E6B;
            v102 = 2;
            v104 = 45;
            v105 = 1;
            EtwEventWriteTransfer(qword_180173298, &v97, 0, 0, 5, &v100);
            return 0;
          }
          v34 = gIkeExtGlobals;
        }
      }
      v37 = 0;
      goto LABEL_56;
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
LABEL_37:
          v94 = v28;
          v106 = &v94;
          v107 = 8;
          if ( !v25 )
            goto LABEL_45;
          v29 = (DWORD)v25[86].LockSemaphore;
          if ( v29 == -1 )
            goto LABEL_45;
          v30 = (char *)TlsGetValue(v29);
          v31 = (const WCHAR *)(v30 + 8);
          if ( !v30 )
            v31 = 0;
          if ( v31 )
          {
            v32 = -1;
            do
              v15 = v31[++v32] == 0;
            while ( !v15 );
            v33 = 2 * v32 + 2;
          }
          else
          {
LABEL_45:
            v31 = &LocaleName;
            v33 = 2;
          }
          v109 = v33;
          v108 = v31;
          v111 = "keying module is not enabled for traffic";
          v98 = 4;
          v100 = off_180173280;
          v113 = "AUTHIP";
          v110 = 0;
          v112 = 41;
          v114 = 7;
          v97 = 184549376;
          v99 = 0;
          v101 = *(unsigned __int16 *)off_180173280;
          v103 = &byte_180159BFF;
          v102 = 2;
          v104 = 76;
          v105 = 1;
          EtwEventWriteTransfer(qword_180173298, &v97, 0, 0, 6, &v100);
          goto LABEL_47;
        }
        v25 = gIkeExtGlobals;
      }
    }
    v28 = 0;
    goto LABEL_37;
  }
  LODWORD(v95[0]) = a1;
  MMPolicy = IkeFindMMPolicy((__int64)a2, (unsigned int *)v95, 1, 0, &lpMem);
  if ( !MMPolicy && a3 )
    MMPolicy = IkeFindQMPolicy(0, a2, a3, 0, (__int64)v95, 0, 0, 1, &v92, &v93);
  IkeFreeMMPolicy(lpMem);
  IkeFreeQMExtPolicy(v92);
  IkeFreeUMPolicy(v93);
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v43 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v44 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v44 != -1 )
      {
        v45 = (__int64 *)TlsGetValue(v44);
        if ( v45 )
        {
          v46 = *v45;
          v43 = gIkeExtGlobals;
LABEL_77:
          v94 = v46;
          v106 = &v94;
          v107 = 8;
          if ( !v43 )
            goto LABEL_85;
          v47 = (DWORD)v43[86].LockSemaphore;
          if ( v47 == -1 )
            goto LABEL_85;
          v48 = (char *)TlsGetValue(v47);
          v49 = (const WCHAR *)(v48 + 8);
          if ( !v48 )
            v49 = 0;
          if ( v49 )
          {
            v50 = -1;
            do
              v15 = v49[++v50] == 0;
            while ( !v15 );
            v51 = 2 * v50 + 2;
          }
          else
          {
LABEL_85:
            v49 = &LocaleName;
            v51 = 2;
          }
          v109 = v51;
          v108 = v49;
          v111 = "IkeIsKeyModEnabledForTraffic";
          v98 = 5;
          v100 = off_180173280;
          v110 = 0;
          v112 = 29;
          v97 = 184549376;
          v99 = 1;
          v101 = *(unsigned __int16 *)off_180173280;
          v103 = byte_180166E6B;
          v102 = 2;
          v104 = 45;
          v105 = 1;
          EtwEventWriteTransfer(qword_180173298, &v97, 0, 0, 5, &v100);
          goto LABEL_87;
        }
        v43 = gIkeExtGlobals;
      }
    }
    v46 = 0;
    goto LABEL_77;
  }
LABEL_87:
  if ( MMPolicy )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v52 = gIkeExtGlobals;
      if ( !gIkeExtGlobals || (v53 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v53 == -1) )
      {
        v55 = 0;
      }
      else
      {
        v54 = TlsGetValue(v53);
        v52 = gIkeExtGlobals;
        v55 = v54;
      }
      v56 = (__int64)v55 + 8;
      if ( !v55 )
        v56 = 0;
      if ( v52 )
      {
        v57 = (DWORD)v52[86].LockSemaphore;
        if ( v57 != -1 )
          TlsGetValue(v57);
      }
      v58 = IkeGetKeyModString(a1);
      WPP_SF_iSs(
        *(_QWORD *)(v59 + 16),
        51,
        (unsigned int)WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids,
        v60,
        v56,
        v58);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      return 0;
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
LABEL_108:
          v94 = v64;
          v106 = &v94;
          v107 = 8;
          if ( !v61 )
            goto LABEL_116;
          v65 = (DWORD)v61[86].LockSemaphore;
          if ( v65 == -1 )
            goto LABEL_116;
          v66 = (char *)TlsGetValue(v65);
          v67 = (const WCHAR *)(v66 + 8);
          if ( !v66 )
            v67 = 0;
          if ( v67 )
          {
            v68 = -1;
            do
              v15 = v67[++v68] == 0;
            while ( !v15 );
            v69 = 2 * v68 + 2;
          }
          else
          {
LABEL_116:
            v67 = &LocaleName;
            v69 = 2;
          }
          v109 = v69;
          v111 = "keying module is not enabled for traffic";
          v108 = v67;
          v110 = 0;
          v112 = 41;
          if ( a1 )
          {
            v70 = "IKEv2";
            if ( a1 != 2 )
              v70 = "AUTHIP";
          }
          else
          {
            v70 = "IKE";
          }
          do
            v15 = v70[++v6] == 0;
          while ( !v15 );
          v113 = v70;
          v114 = (unsigned int)(v6 + 1);
          v98 = 4;
          v100 = off_180173280;
          v97 = 184549376;
          v99 = 0;
          v101 = *(unsigned __int16 *)off_180173280;
          v103 = &byte_180159BA7;
          v102 = 2;
          v104 = 76;
          v105 = 1;
          EtwEventWriteTransfer(qword_180173298, &v97, 0, 0, 6, &v100);
          return 0;
        }
        v61 = gIkeExtGlobals;
      }
    }
    v64 = 0;
    goto LABEL_108;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v72 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v73 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v73 == -1) )
    {
      v75 = 0;
    }
    else
    {
      v74 = TlsGetValue(v73);
      v72 = gIkeExtGlobals;
      v75 = v74;
    }
    v76 = (__int64)v75 + 8;
    if ( !v75 )
      v76 = 0;
    if ( v72 )
    {
      v77 = (DWORD)v72[86].LockSemaphore;
      if ( v77 != -1 )
        TlsGetValue(v77);
    }
    v78 = IkeGetKeyModString(a1);
    WPP_SF_iSs(*(_QWORD *)(v79 + 16), 52, (unsigned int)WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids, v80, v76, v78);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v81 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v82 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v82 != -1 )
      {
        v83 = (__int64 *)TlsGetValue(v82);
        if ( v83 )
        {
          v84 = *v83;
          v81 = gIkeExtGlobals;
LABEL_144:
          v94 = v84;
          v106 = &v94;
          v107 = 8;
          if ( !v81 )
            goto LABEL_152;
          v85 = (DWORD)v81[86].LockSemaphore;
          if ( v85 == -1 )
            goto LABEL_152;
          v86 = (char *)TlsGetValue(v85);
          v87 = (const WCHAR *)(v86 + 8);
          if ( !v86 )
            v87 = 0;
          if ( v87 )
          {
            v88 = -1;
            do
              v15 = v87[++v88] == 0;
            while ( !v15 );
            v89 = 2 * v88 + 2;
          }
          else
          {
LABEL_152:
            v87 = &LocaleName;
            v89 = 2;
          }
          v109 = v89;
          v111 = "keying module is enabled for traffic";
          v108 = v87;
          v110 = 0;
          v112 = 37;
          if ( a1 )
          {
            v90 = "IKEv2";
            if ( a1 != 2 )
              v90 = "AUTHIP";
          }
          else
          {
            v90 = "IKE";
          }
          do
            v15 = v90[++v6] == 0;
          while ( !v15 );
          v113 = v90;
          v114 = (unsigned int)(v6 + 1);
          v98 = 4;
          v100 = off_180173280;
          v97 = 184549376;
          v99 = 0;
          v101 = *(unsigned __int16 *)off_180173280;
          v103 = &byte_180159B07;
          v102 = 2;
          v104 = 75;
          v105 = 1;
          EtwEventWriteTransfer(qword_180173298, &v97, 0, 0, 6, &v100);
          return 1;
        }
        v81 = gIkeExtGlobals;
      }
    }
    v84 = 0;
    goto LABEL_144;
  }
  return 1;
}

```

## disassembly

```asm
0x180037290  mov     [rsp-8+arg_18], rbx
0x180037295  push    rbp
0x180037296  push    rsi
0x180037297  push    rdi
0x180037298  push    r12
0x18003729a  push    r13
0x18003729c  push    r14
0x18003729e  push    r15
0x1800372a0  lea     rbp, [rsp-20h]
0x1800372a5  sub     rsp, 120h
0x1800372ac  mov     rax, cs:__security_cookie
0x1800372b3  xor     rax, rsp
0x1800372b6  mov     [rbp+50h+var_40], rax
0x1800372ba  xor     r13d, r13d
0x1800372bd  lea     rbx, aIkeiskeymodena; "IkeIsKeyModEnabledForTraffic"
0x1800372c4  xor     eax, eax
0x1800372c6  mov     [rsp+150h+lpMem], r13
0x1800372cb  xorps   xmm0, xmm0
0x1800372ce  mov     [rbp+50h+var_B8], rax
0x1800372d2  mov     eax, cs:dword_180173278
0x1800372d8  lea     r12, _TraceLoggingMetadataEnd
0x1800372df  mov     [rsp+150h+var_F0], r13
0x1800372e4  mov     rdi, r8
0x1800372e7  mov     [rsp+150h+var_E8], r13
0x1800372ec  mov     r14, rdx
0x1800372ef  mov     r15d, ecx
0x1800372f2  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800372f9  movups  [rsp+150h+var_D8], xmm0
0x1800372fe  movups  [rbp+50h+var_C8], xmm0
0x180037302  cmp     eax, 5
0x180037305  jbe     loc_18003746E
0x18003730b  mov     rcx, cs:qword_180173290
0x180037312  mov     rax, cs:qword_180173288
0x180037319  test    al, 1
0x18003731b  jz      loc_18003746E
0x180037321  mov     rax, rcx
0x180037324  and     eax, 1
0x180037327  cmp     rax, rcx
0x18003732a  jnz     loc_18003746E
0x180037330  mov     rax, cs:gIkeExtGlobals
0x180037337  test    rax, rax
0x18003733a  jz      short loc_180037365
0x18003733c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037342  cmp     ecx, 0FFFFFFFFh
0x180037345  jz      short loc_180037365
0x180037347  call    cs:__imp_TlsGetValue
0x18003734d  test    rax, rax
0x180037350  jz      short loc_18003735E
0x180037352  mov     rcx, [rax]
0x180037355  mov     rax, cs:gIkeExtGlobals
0x18003735c  jmp     short loc_180037368
0x18003735e  mov     rax, cs:gIkeExtGlobals
0x180037365  mov     rcx, r13
0x180037368  mov     [rsp+150h+var_E0], rcx
0x18003736d  lea     rcx, [rsp+150h+var_E0]
0x180037372  mov     [rbp+50h+var_80], rcx
0x180037376  mov     [rbp+50h+var_78], 8
0x18003737e  test    rax, rax
0x180037381  jz      short loc_1800373C5
0x180037383  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037389  cmp     ecx, 0FFFFFFFFh
0x18003738c  jz      short loc_1800373C5
0x18003738e  call    cs:__imp_TlsGetValue
0x180037394  test    rax, rax
0x180037397  lea     rdx, [rax+8]
0x18003739b  cmovz   rdx, r13
0x18003739f  test    rdx, rdx
0x1800373a2  jz      short loc_1800373C5
0x1800373a4  mov     rax, rsi
0x1800373a7  nop     word ptr [rax+rax+00000000h]
0x1800373b0  cmp     [rdx+rax*2+2], r13w
0x1800373b6  lea     rax, [rax+1]
0x1800373ba  jnz     short loc_1800373B0
0x1800373bc  lea     eax, ds:2[rax*2]
0x1800373c3  jmp     short loc_1800373D1
0x1800373c5  lea     rdx, LocaleName
0x1800373cc  mov     eax, 2
0x1800373d1  mov     [rbp+50h+var_68], eax
0x1800373d4  lea     rcx, _TraceLoggingMetadata
0x1800373db  movzx   eax, cs:word_180166E9A
0x1800373e2  xor     r9d, r9d
0x1800373e5  mov     [rbp+50h+var_AC], eax
0x1800373e8  xor     r8d, r8d
0x1800373eb  mov     rax, cs:off_180173280
0x1800373f2  mov     [rbp+50h+var_A0], rax
0x1800373f6  mov     [rbp+50h+var_70], rdx
0x1800373fa  lea     rdx, [rbp+50h+var_B0]
0x1800373fe  mov     [rbp+50h+var_64], r13d
0x180037402  mov     [rbp+50h+var_60], rbx
0x180037406  mov     [rbp+50h+var_58], 1Dh
0x18003740e  mov     [rbp+50h+var_B0], 0B000000h
0x180037415  mov     [rbp+50h+var_A8], 1
0x18003741d  movzx   eax, word ptr [rax]
0x180037420  mov     [rbp+50h+var_98], eax
0x180037423  lea     rax, dword_180166EA4
0x18003742a  mov     [rbp+50h+var_90], rax
0x18003742e  mov     rax, r12
0x180037431  sub     eax, ecx
0x180037433  mov     [rbp+50h+var_94], 2
0x18003743a  mov     [rbp+50h+var_88], 2Dh ; '-'
0x180037441  mov     [rbp+50h+var_84], 1
0x180037448  mov     [rsp+150h+var_100], eax
0x18003744c  mov     eax, [rsp+150h+var_100]
0x180037450  mov     rcx, cs:qword_180173298
0x180037457  lea     rax, [rbp+50h+var_A0]
0x18003745b  mov     [rsp+150h+var_128], rax
0x180037460  mov     dword ptr [rsp+150h+var_130], 5
0x180037468  call    cs:__imp_EtwEventWriteTransfer
0x18003746e  cmp     r15d, 1
0x180037472  jnz     loc_1800377C4
0x180037478  mov     rcx, cs:gIkeExtGlobals
0x18003747f  test    byte ptr [rcx+7E8h], 40h
0x180037486  jz      loc_1800377C4
0x18003748c  mov     rdi, cs:WPP_GLOBAL_Control
0x180037493  lea     rax, WPP_GLOBAL_Control
0x18003749a  cmp     rdi, rax
0x18003749d  jz      short loc_18003750E
0x18003749f  cmp     byte ptr [rdi+19h], 4
0x1800374a3  jb      short loc_18003750E
0x1800374a5  test    byte ptr [rdi+1Ch], 10h
0x1800374a9  jz      short loc_18003750E
0x1800374ab  mov     ecx, [rcx+0D88h]; dwTlsIndex
0x1800374b1  cmp     ecx, 0FFFFFFFFh
0x1800374b4  jz      short loc_1800374CD
0x1800374b6  call    cs:__imp_TlsGetValue
0x1800374bc  mov     rdi, cs:WPP_GLOBAL_Control
0x1800374c3  test    rax, rax
0x1800374c6  jz      short loc_1800374CD
0x1800374c8  mov     r14, [rax]
0x1800374cb  jmp     short loc_1800374D0
0x1800374cd  mov     r14, r13
0x1800374d0  mov     rdi, [rdi+10h]
0x1800374d4  mov     ecx, 1
0x1800374d9  call    IkeGetKeyModString
0x1800374de  mov     rbx, rax
0x1800374e1  call    IkeGetTlsPeerAddr
0x1800374e6  mov     edx, 32h ; '2'
0x1800374eb  mov     [rsp+150h+var_128], rbx
0x1800374f0  mov     r9, r14
0x1800374f3  mov     [rsp+150h+var_130], rax
0x1800374f8  lea     r8, WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids
0x1800374ff  mov     rcx, rdi
0x180037502  call    WPP_SF_iSs
0x180037507  lea     rbx, aIkeiskeymodena; "IkeIsKeyModEnabledForTraffic"
0x18003750e  mov     eax, cs:dword_180173278
0x180037514  cmp     eax, 4
0x180037517  jbe     loc_18003766A
0x18003751d  mov     rax, cs:gIkeExtGlobals
0x180037524  test    rax, rax
0x180037527  jz      short loc_180037552
0x180037529  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003752f  cmp     ecx, 0FFFFFFFFh
0x180037532  jz      short loc_180037552
0x180037534  call    cs:__imp_TlsGetValue
0x18003753a  test    rax, rax
0x18003753d  jz      short loc_18003754B
0x18003753f  mov     rcx, [rax]
0x180037542  mov     rax, cs:gIkeExtGlobals
0x180037549  jmp     short loc_180037555
0x18003754b  mov     rax, cs:gIkeExtGlobals
0x180037552  mov     rcx, r13
0x180037555  mov     [rsp+150h+var_E0], rcx
0x18003755a  lea     rcx, [rsp+150h+var_E0]
0x18003755f  mov     [rbp+50h+var_80], rcx
0x180037563  mov     [rbp+50h+var_78], 8
0x18003756b  test    rax, rax
0x18003756e  jz      short loc_1800375A9
0x180037570  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037576  cmp     ecx, 0FFFFFFFFh
0x180037579  jz      short loc_1800375A9
0x18003757b  call    cs:__imp_TlsGetValue
0x180037581  test    rax, rax
0x180037584  lea     rdx, [rax+8]
0x180037588  cmovz   rdx, r13
0x18003758c  test    rdx, rdx
0x18003758f  jz      short loc_1800375A9
0x180037591  mov     rax, rsi
0x180037594  cmp     [rdx+rax*2+2], r13w
0x18003759a  lea     rax, [rax+1]
0x18003759e  jnz     short loc_180037594
0x1800375a0  lea     eax, ds:2[rax*2]
0x1800375a7  jmp     short loc_1800375B5
0x1800375a9  lea     rdx, LocaleName
0x1800375b0  mov     eax, 2
0x1800375b5  mov     [rbp+50h+var_68], eax
0x1800375b8  lea     rcx, aAuthip_0; "AUTHIP"
0x1800375bf  mov     [rbp+50h+var_70], rdx
0x1800375c3  lea     rax, aKeyingModuleIs; "keying module is not enabled for traffi"...
0x1800375ca  mov     [rbp+50h+var_60], rax
0x1800375ce  lea     rdi, _TraceLoggingMetadata
0x1800375d5  movzx   eax, cs:word_180159BF5
0x1800375dc  lea     rdx, [rbp+50h+var_B0]
0x1800375e0  mov     [rbp+50h+var_AC], eax
0x1800375e3  xor     r9d, r9d
0x1800375e6  mov     rax, cs:off_180173280
0x1800375ed  xor     r8d, r8d
0x1800375f0  mov     [rbp+50h+var_A0], rax
0x1800375f4  mov     [rbp+50h+var_50], rcx
0x1800375f8  mov     [rbp+50h+var_64], r13d
0x1800375fc  mov     [rbp+50h+var_58], 29h ; ')'
0x180037604  mov     [rbp+50h+var_48], 7
0x18003760c  mov     [rbp+50h+var_B0], 0B000000h
0x180037613  mov     [rbp+50h+var_A8], r13
0x180037617  movzx   eax, word ptr [rax]
0x18003761a  mov     [rbp+50h+var_98], eax
0x18003761d  lea     rax, byte_180159BFF
0x180037624  mov     [rbp+50h+var_90], rax
0x180037628  mov     rax, r12
0x18003762b  sub     eax, edi
0x18003762d  mov     [rbp+50h+var_94], 2
0x180037634  mov     [rbp+50h+var_88], 4Ch ; 'L'
0x18003763b  mov     [rbp+50h+var_84], 1
0x180037642  mov     [rsp+150h+var_100], eax
0x180037646  mov     eax, [rsp+150h+var_100]
0x18003764a  mov     rcx, cs:qword_180173298
0x180037651  lea     rax, [rbp+50h+var_A0]
0x180037655  mov     [rsp+150h+var_128], rax
0x18003765a  mov     dword ptr [rsp+150h+var_130], 6
0x180037662  call    cs:__imp_EtwEventWriteTransfer
0x180037668  jmp     short loc_180037671
0x18003766a  lea     rdi, _TraceLoggingMetadata
0x180037671  mov     eax, cs:dword_180173278
0x180037677  cmp     eax, 5
0x18003767a  jbe     loc_180037C16
0x180037680  mov     rcx, cs:qword_180173290
0x180037687  mov     rax, cs:qword_180173288
0x18003768e  test    al, 1
0x180037690  jz      loc_180037C16
0x180037696  mov     rax, rcx
0x180037699  and     eax, 1
0x18003769c  cmp     rax, rcx
0x18003769f  jnz     loc_180037C16
0x1800376a5  mov     rax, cs:gIkeExtGlobals
0x1800376ac  test    rax, rax
0x1800376af  jz      short loc_1800376DA
0x1800376b1  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800376b7  cmp     ecx, 0FFFFFFFFh
0x1800376ba  jz      short loc_1800376DA
0x1800376bc  call    cs:__imp_TlsGetValue
0x1800376c2  test    rax, rax
0x1800376c5  jz      short loc_1800376D3
0x1800376c7  mov     rcx, [rax]
0x1800376ca  mov     rax, cs:gIkeExtGlobals
0x1800376d1  jmp     short loc_1800376DD
0x1800376d3  mov     rax, cs:gIkeExtGlobals
0x1800376da  mov     rcx, r13
0x1800376dd  mov     [rsp+150h+var_E0], rcx
0x1800376e2  lea     rcx, [rsp+150h+var_E0]
0x1800376e7  mov     [rbp+50h+var_80], rcx
0x1800376eb  mov     [rbp+50h+var_78], 8
0x1800376f3  test    rax, rax
0x1800376f6  jz      short loc_180037735
0x1800376f8  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800376fe  cmp     ecx, 0FFFFFFFFh
0x180037701  jz      short loc_180037735
0x180037703  call    cs:__imp_TlsGetValue
0x180037709  test    rax, rax
0x18003770c  lea     rdx, [rax+8]
0x180037710  cmovz   rdx, r13
0x180037714  test    rdx, rdx
0x180037717  jz      short loc_180037735
0x180037719  nop     dword ptr [rax+00000000h]
0x180037720  cmp     [rdx+rsi*2+2], r13w
0x180037726  lea     rsi, [rsi+1]
0x18003772a  jnz     short loc_180037720
0x18003772c  lea     esi, ds:2[rsi*2]
0x180037733  jmp     short loc_180037741
0x180037735  lea     rdx, LocaleName
0x18003773c  mov     esi, 2
0x180037741  movzx   eax, cs:word_180166E61
0x180037748  sub     r12d, edi
0x18003774b  mov     [rbp+50h+var_AC], eax
0x18003774e  mov     rax, cs:off_180173280
0x180037755  mov     [rbp+50h+var_A0], rax
0x180037759  mov     [rbp+50h+var_70], rdx
0x18003775d  mov     [rbp+50h+var_68], esi
0x180037760  mov     [rbp+50h+var_64], r13d
0x180037764  mov     [rbp+50h+var_60], rbx
0x180037768  mov     [rbp+50h+var_58], 1Dh
0x180037770  mov     [rbp+50h+var_B0], 0B000000h
0x180037777  mov     [rbp+50h+var_A8], 1
0x18003777f  movzx   eax, word ptr [rax]
0x180037782  mov     [rbp+50h+var_98], eax
0x180037785  lea     rax, byte_180166E6B
0x18003778c  mov     [rbp+50h+var_90], rax
0x180037790  mov     [rbp+50h+var_94], 2
0x180037797  mov     [rbp+50h+var_88], 2Dh ; '-'
0x18003779e  mov     [rbp+50h+var_84], 1
0x1800377a5  mov     [rsp+150h+var_100], r12d
0x1800377aa  mov     eax, [rsp+150h+var_100]
0x1800377ae  lea     rax, [rbp+50h+var_A0]
0x1800377b2  mov     [rsp+150h+var_128], rax
0x1800377b7  mov     dword ptr [rsp+150h+var_130], 5
0x1800377bf  jmp     loc_180037BFF
0x1800377c4  lea     rax, [rsp+150h+lpMem]
0x1800377c9  mov     dword ptr [rsp+150h+var_D8], r15d
0x1800377ce  xor     r9d, r9d
0x1800377d1  mov     [rsp+150h+var_130], rax
0x1800377d6  mov     r8d, 1
0x1800377dc  lea     rdx, [rsp+150h+var_D8]
  ... truncated ...
```
