# CreateConnection

- ea: `0x180016500`
- end: `0x1800176a4`
- name: `CreateConnection`
- size: `4516`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800360a0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x180005cf8`
- `0x18000c3c0`
- `0x18000c4a0`
- `0x180016500`
- `0x18001a5d0`
- `0x18001a618`
- `0x1800210e0`
- `0x180033d48`
- `0x180035a08`
- `0x180040998`
- `0x180040ddc`
- `0x1800425a4`
- `0x18004ca6c`
- `0x1800e8e7e`
- `0x1800e8e96`
- `0x1800e8ef0`
- `0x1800e8fb0`
- `0x1800eb010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180016631`
- `msvcrt!memcpy_s` at `0x180016631`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001712b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180017218`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001712b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180017218`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800172d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800172d3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017018`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800170c1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017018`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800170c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800170d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017466`
- `RPCRT4!RpcImpersonateClient` at `0x18001706f`
- `RPCRT4!RpcImpersonateClient` at `0x180017190`
- `RPCRT4!RpcImpersonateClient` at `0x1800172ea`
- `RPCRT4!RpcImpersonateClient` at `0x18001706f`
- `RPCRT4!RpcImpersonateClient` at `0x180017190`
- `RPCRT4!RpcImpersonateClient` at `0x1800172ea`
- `RPCRT4!RpcRevertToSelf` at `0x180017112`
- `RPCRT4!RpcRevertToSelf` at `0x18001723f`
- `RPCRT4!RpcRevertToSelf` at `0x18001739e`
- `RPCRT4!RpcRevertToSelf` at `0x180017112`
- `RPCRT4!RpcRevertToSelf` at `0x18001723f`
- `RPCRT4!RpcRevertToSelf` at `0x18001739e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001760a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001760a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001759e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001759e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800175bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800175bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800168ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016ad9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800168ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016ad9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001698a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001698a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017452`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017452`

## string_xrefs

- `0x180017591`: `rastls.dll`

## pseudocode

```c
int __fastcall CreateConnection(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 v3; // rsi
  struct _LIST_ENTRY *v5; // rbx
  __int64 v6; // r12
  int v7; // ebp
  _BYTE *v8; // r15
  _BYTE *v9; // r13
  __int64 v10; // r9
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rbx
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdi
  bool v16; // zf
  __int64 v17; // rdx
  int IsProcessAlive; // eax
  __int64 v19; // r12
  __int64 v20; // r13
  unsigned int v21; // eax
  size_t v22; // rdi
  _QWORD *v23; // rax
  _QWORD *v24; // r14
  int v25; // ebp
  __int64 v26; // r8
  __int64 v27; // rdi
  __int64 v28; // r9
  __int64 v29; // rdx
  _QWORD *v30; // rax
  HMODULE Library; // rax
  struct _LIST_ENTRY *v32; // rcx
  __int64 v33; // rdx
  int v34; // edi
  struct _LIST_ENTRY *v35; // r9
  __int64 v36; // rbp
  _BYTE *v37; // rdx
  __int64 v38; // r10
  __int64 v39; // r8
  __int64 v40; // rcx
  _BYTE *v41; // rax
  __int64 v42; // rax
  _BYTE *v43; // rdx
  _BYTE *v44; // r8
  __int64 v45; // rcx
  _BYTE *v46; // rax
  _BYTE *v47; // r8
  _BYTE *v48; // rdx
  __int64 v49; // rcx
  _BYTE *v50; // rax
  int v51; // eax
  HANDLE v52; // rax
  DWORD LastError; // eax
  unsigned int v54; // eax
  HANDLE v55; // rax
  DWORD v56; // eax
  BOOL v57; // edi
  DWORD v58; // ebp
  unsigned int v59; // eax
  DWORD v60; // eax
  unsigned int UserSidFromToken; // eax
  _QWORD *v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdi
  DWORD v65; // eax
  DWORD v66; // edi
  struct _LIST_ENTRY *v67; // rcx
  HMODULE v68; // rbx
  FARPROC ProcAddress; // rax
  int v71; // [rsp+30h] [rbp-2778h]
  DWORD dwProcessId; // [rsp+34h] [rbp-2774h]
  unsigned int v73; // [rsp+38h] [rbp-2770h]
  __int64 ConnectionFromEntry; // [rsp+40h] [rbp-2768h]
  WCHAR Destination[5000]; // [rsp+50h] [rbp-2758h] BYREF

  v3 = a3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 709, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *(unsigned int *)(v3 + 20);
  v7 = *(_DWORD *)(v3 + 24);
  v8 = (_BYTE *)(v3 + 44);
  v71 = *(_DWORD *)(v3 + 20);
  v9 = (_BYTE *)(v3 + 304);
  memset_0(Destination, 0, sizeof(Destination));
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(v5[1].Blink) & 0x2000) != 0 && BYTE1(v5[1].Blink) >= 4u )
    {
      WPP_SF_ss(v5[1].Flink, 710, (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v3 + 304, v3 + 44);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 5u )
    {
      WPP_SF_Dd(v5[1].Flink, 711, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, (unsigned int)v6, v7);
    }
  }
  memcpy_s(Destination, 0x2710u, (const void *const)(v3 + 1248), 0x1388u);
  memset_0((void *)(v3 + 1248), 0, 4 * v6);
  if ( *a2 )
  {
    v10 = (unsigned int)a2[2];
    dwProcessId = a2[2];
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      v12 = 712;
LABEL_22:
      WPP_SF_d(v11[1].Flink, v12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v10);
      v11 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v10 = *(unsigned int *)(v3 + 4);
    dwProcessId = *(_DWORD *)(v3 + 4);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      v12 = 713;
      goto LABEL_22;
    }
  }
  if ( v7 != 2 )
  {
    ConnectionFromEntry = FindConnectionFromEntry((char *)(v3 + 44), (char *)(v3 + 304));
    v13 = (_QWORD *)ConnectionFromEntry;
    if ( !ConnectionFromEntry )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 725, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      goto LABEL_66;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 714, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)(ConnectionFromEntry + 24) )
    {
      if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v14[1].Blink) & 0x2000) != 0
        && BYTE1(v14[1].Blink) >= 4u )
      {
        WPP_SF_(v14[1].Flink, 715, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      ++*(_DWORD *)(ConnectionFromEntry + 88);
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_qdq(
          WPP_GLOBAL_Control[1].Flink,
          716,
          WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          *(_QWORD *)(ConnectionFromEntry + 16),
          *(_DWORD *)(ConnectionFromEntry + 88),
          ConnectionFromEntry);
      }
      *(_DWORD *)(v3 + 16) = 2;
      goto LABEL_274;
    }
    if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v14[1].Blink) & 0x2000) != 0
      && BYTE1(v14[1].Blink) >= 4u )
    {
      WPP_SF_(v14[1].Flink, 717, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    v15 = 0;
    v16 = *(_DWORD *)(ConnectionFromEntry + 64) == 0;
    if ( *(_DWORD *)(ConnectionFromEntry + 64) )
    {
      while ( 1 )
      {
        v17 = *(_QWORD *)(*(_QWORD *)(ConnectionFromEntry + 56) + 8 * v15);
        if ( v17 )
        {
          if ( *(_DWORD *)(v17 + 28) != 4 )
            break;
        }
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= *(_DWORD *)(ConnectionFromEntry + 64) )
          goto LABEL_52;
      }
      if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v14[1].Blink) & 0x2000) != 0
        && BYTE1(v14[1].Blink) >= 4u )
      {
        WPP_SF_(v14[1].Flink, 718, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
LABEL_52:
      v16 = (_DWORD)v15 == *(_DWORD *)(ConnectionFromEntry + 64);
    }
    if ( !v16
      || *(_QWORD *)(ConnectionFromEntry + 80)
      && (IsProcessAlive = fIsProcessAlive(*(HANDLE *)(ConnectionFromEntry + 80)),
          v14 = WPP_GLOBAL_Control,
          IsProcessAlive) )
    {
      if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v14[1].Blink) & 0x2000) != 0
        && BYTE1(v14[1].Blink) >= 4u )
      {
        WPP_SF_qdq(
          v14[1].Flink,
          719,
          WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          *(_QWORD *)(ConnectionFromEntry + 16),
          *(_DWORD *)(ConnectionFromEntry + 88),
          ConnectionFromEntry);
      }
      *(_DWORD *)(v3 + 16) = 1;
LABEL_274:
      *(_QWORD *)(v3 + 8) = v13[2];
      *(_DWORD *)v3 = 0;
      if ( (Feature_VPN_Profile_Timestamps__private_featureState & 0x10) != 0 )
        LODWORD(Library) = Feature_VPN_Profile_Timestamps__private_featureState & 1;
      else
        LODWORD(Library) = Feature_VPN_Profile_Timestamps__private_IsEnabledDeviceUsageNoInline();
      if ( (_DWORD)Library )
      {
        Library = LoadLibraryExW(L"rastls.dll", 0, 0x800u);
        v68 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "RasEapSetTimeStampChar");
          if ( ProcAddress )
          {
            ((void (__fastcall *)(_BYTE *))ProcAddress)(v9);
          }
          else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 754, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          }
          LODWORD(Library) = FreeLibrary(v68);
        }
        else
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return (int)Library;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_291;
          LODWORD(Library) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 755, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
      }
      v32 = WPP_GLOBAL_Control;
LABEL_291:
      if ( v32 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v32[1].Blink) & 0x2000) == 0
        || BYTE1(v32[1].Blink) < 6u )
      {
        return (int)Library;
      }
      v33 = 756;
      goto LABEL_295;
    }
    v19 = *(unsigned int *)(ConnectionFromEntry + 64);
    v20 = *(_QWORD *)(ConnectionFromEntry + 16);
    v73 = *(_DWORD *)(ConnectionFromEntry + 140);
    if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v14[1].Blink) & 0x2000) != 0
      && BYTE1(v14[1].Blink) >= 4u )
    {
      WPP_SF_qdq(
        v14[1].Flink,
        720,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        v20,
        *(_DWORD *)(ConnectionFromEntry + 88),
        ConnectionFromEntry);
      v14 = WPP_GLOBAL_Control;
    }
    if ( (_DWORD)v19 )
    {
      v21 = 8 * v19;
      if ( (unsigned __int64)(8 * v19) <= 0xFFFFFFFF )
      {
        v22 = v21;
        v23 = LocalAlloc(0x40u, v21);
        v24 = v23;
        if ( v23 )
        {
          v25 = 0;
          memcpy_0(v23, *(const void **)(ConnectionFromEntry + 56), v22);
          v27 = 0;
          do
          {
            v28 = v24[v27];
            if ( v28 && *(_DWORD *)(v28 + 24) != 1 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
              {
                WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 722, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v28 + 8);
              }
              LOBYTE(v26) = 1;
              PortClose(v24[v27], v73, v26, 0);
              v25 = 1;
            }
            v27 = (unsigned int)(v27 + 1);
          }
          while ( (unsigned int)v27 < (unsigned int)v19 );
          LocalFree(v24);
          v13 = (_QWORD *)ConnectionFromEntry;
          v3 = a3;
          if ( v25 && !FindConnection(v20) )
            goto LABEL_65;
        }
        else
        {
          *(_DWORD *)v3 = -2147024882;
        }
LABEL_64:
        FreeConnection(v13);
LABEL_65:
        LODWORD(v6) = v71;
        v9 = (_BYTE *)(v3 + 304);
LABEL_66:
        v8 = (_BYTE *)(v3 + 44);
        goto LABEL_101;
      }
      if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v14[1].Blink) & 0x2000) == 0
        || BYTE1(v14[1].Blink) < 4u )
      {
        goto LABEL_64;
      }
      v29 = 721;
    }
    else
    {
      if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v14[1].Blink) & 0x2000) == 0
        || BYTE1(v14[1].Blink) < 4u )
      {
        goto LABEL_64;
      }
      v29 = 723;
    }
    WPP_SF_(v14[1].Flink, v29, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    goto LABEL_64;
  }
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v11[1].Blink) & 0x2000) != 0
    && BYTE1(v11[1].Blink) >= 4u )
  {
    WPP_SF_(v11[1].Flink, 726, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
LABEL_101:
  *(_DWORD *)(v3 + 16) = 0;
  v30 = LocalAlloc(0x40u, 0x3C0u);
  v13 = v30;
  if ( !v30 )
  {
    LODWORD(Library) = GetLastError();
    *(_DWORD *)v3 = (_DWORD)Library;
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return (int)Library;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      LODWORD(Library) = WPP_SF_d(
                           WPP_GLOBAL_Control[1].Flink,
                           727,
                           WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                           (unsigned int)Library);
      v32 = WPP_GLOBAL_Control;
    }
    if ( v32 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v32[1].Blink) & 0x2000) == 0
      || BYTE1(v32[1].Blink) < 6u )
    {
      return (int)Library;
    }
    v33 = 728;
LABEL_295:
    LODWORD(Library) = WPP_SF_(v32[1].Flink, v33, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    return (int)Library;
  }
  v30[115] = 0;
  v30[116] = 0;
  v30[117] = 0;
  v34 = 0;
  v35 = WPP_GLOBAL_Control;
LABEL_111:
  v36 = ((unsigned int)NextConnectionHandle < 0xFFFF ? (unsigned int)NextConnectionHandle + 1 : 1) << 16;
  NextConnectionHandle = (unsigned int)NextConnectionHandle < 0xFFFF ? (unsigned int)NextConnectionHandle + 1 : 1;
  if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v35[1].Blink) & 0x2000) != 0
    && BYTE1(v35[1].Blink) >= 6u )
  {
    WPP_SF_(v35[1].Flink, 706, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v35 = WPP_GLOBAL_Control;
  }
  for ( Library = (HMODULE)ConnectionBlockList; Library != (HMODULE)&ConnectionBlockList; Library = *(HMODULE *)Library )
  {
    if ( *((_QWORD *)Library + 2) == v36 )
    {
      if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v35[1].Blink) & 0x2000) != 0
        && BYTE1(v35[1].Blink) >= 6u )
      {
        LODWORD(Library) = WPP_SF_(v35[1].Flink, 707, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        v35 = WPP_GLOBAL_Control;
      }
      if ( (unsigned int)++v34 >= 0xFFFF )
      {
        *(_DWORD *)v3 = 633;
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            LODWORD(Library) = WPP_SF_d(
                                 WPP_GLOBAL_Control[1].Flink,
                                 729,
                                 WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                 633);
            v32 = WPP_GLOBAL_Control;
          }
          if ( v32 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v32[1].Blink) & 0x2000) != 0
            && BYTE1(v32[1].Blink) >= 6u )
          {
            v33 = 730;
            goto LABEL_295;
          }
        }
        return (int)Library;
      }
      goto LABEL_111;
    }
  }
  if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v35[1].Blink) & 0x2000) != 0
    && BYTE1(v35[1].Blink) >= 6u )
  {
    WPP_SF_(v35[1].Flink, 708, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  v13[2] = v36;
  v37 = v13 + 23;
  v38 = 2147483646;
  *((_DWORD *)v13 + 6) = 0;
  v13[6] = 0;
  v39 = 2147483646;
  *((_DWORD *)v13 + 42) = 0;
  v40 = 261;
  v13[114] = 0;
  v13[5] = v13 + 4;
  v13[4] = v13 + 4;
  do
  {
    if ( !v39 )
      break;
    if ( !*v8 )
      break;
    *v37++ = *v8++;
    --v39;
    --v40;
  }
  while ( v40 );
  v41 = v37 - 1;
  if ( v40 )
    v41 = v37;
  *v41 = 0;
  if ( !v40 )
  {
    *(_DWORD *)v3 = -2147024809;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control[1].Flink,
        731,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        v40 == 0 ? 0x8007007A : 0,
        -2147024809);
    }
    LODWORD(Library) = FreeConnection(v13);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v33 = 732;
      goto LABEL_295;
    }
    return (int)Library;
  }
  v42 = 2147483646;
  v43 = (char *)v13 + 445;
  v44 = v9;
  v45 = 257;
  do
  {
    if ( !v42 )
      break;
    if ( !*v44 )
      break;
    *v43++ = *v44++;
    --v42;
    --v45;
  }
  while ( v45 );
  v46 = v43 - 1;
  if ( v45 )
    v46 = v43;
  *v46 = 0;
  if ( !v45 )
  {
    *(_DWORD *)v3 = -2147024809;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control[1].Flink,
        733,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        v45 == 0 ? 0x8007007A : 0,
        -2147024809);
    }
    LODWORD(Library) = FreeConnection(v13);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v33 = 734;
      goto LABEL_295;
    }
    return (int)Library;
  }
  v47 = (_BYTE *)(v3 + 1104);
  *((_DWORD *)v13 + 176) = *(_DWORD *)(v3 + 1088);
  v48 = (char *)v13 + 716;
  v49 = 129;
  *((_DWORD *)v13 + 177) = *(_DWORD *)(v3 + 1092);
  *((_DWORD *)v13 + 178) = *(_DWORD *)(v3 + 1096);
  *((_DWORD *)v13 + 212) = *(_DWORD *)(v3 + 1100);
  *((_DWORD *)v13 + 215) = *(_DWORD *)(v3 + 1236);
  do
  {
    if ( !v38 )
      break;
    if ( !*v47 )
      break;
    *v48++ = *v47++;
    --v38;
    --v49;
  }
  while ( v49 );
  v50 = v48 - 1;
  if ( v49 )
    v50 = v48;
  *v50 = 0;
  if ( !v49 )
  {
    *(_DWORD *)v3 = -2147024809;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control[1].Flink,
        735,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        v49 == 0 ? 0x8007007A : 0,
        -2147024809);
    }
    LODWORD(Library) = FreeConnection(v13);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v33 = 736;
      goto LABEL_295;
    }
    return (int)Library;
  }
  *((_DWORD *)v13 + 28) &= ~1u;
  v51 = *((_DWORD *)v13 + 28);
  if ( *(_DWORD *)(v3 + 1240) )
  {
    v51 |= 0x100u;
    *((_DWORD *)v13 + 28) = v51;
  }
  if ( *(_DWORD *)(v3 + 1244) )
    *((_DWORD *)v13 + 28) = v51 | 0x200;
  *((_DWORD *)v13 + 22) = 1;
  *((_DWORD *)v13 + 29) = 1;
  *((_DWORD *)v13 + 18) = v6;
  *((_DWORD *)v13 + 35) = dwProcessId;
  v13[109] = 0;
  v13[111] = 0;
  v13[6] = 0;
  v13[7] = 0;
  v13[8] = 0;
  v13[10] = 0;
  *((_DWORD *)v13 + 34) = 0;
  *((_OWORD *)v13 + 9) = *(_OWORD *)(v3 + 28);
  v52 = OpenProcess(0x4C0u, 0, dwProcessId);
  v13[10] = v52;
  if ( !v52 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 737, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
    }
    v54 = RpcImpersonateClient(0);
    if ( v54 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 738, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v54);
      }
    }
    else
    {
      v55 = OpenProcess(0x4C0u, 0, dwProcessId);
      v13[10] = v55;
      if ( !v55 )
      {
        v56 = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 739, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v56);
        }
      }
      RpcRevertToSelf();
    }
  }
  v57 = ProcessIdToSessionId(dwProcessId, (DWORD *)v13 + 44);
  if ( !v57 )
  {
    v58 = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 740, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v58);
    }
    *(_DWORD *)v3 = v58;
    v59 = RpcImpersonateClient(0);
    if ( v59 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 741, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v59);
      }
      *(_DWORD *)v3 = 5;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 742, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 5);
      }
LABEL_219:
      LODWORD(Library) = FreeConnection(v13);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v33 = 743;
        goto LABEL_295;
      }
      return (int)Library;
    }
    if ( ProcessIdToSessionId(dwProcessId, (DWORD *)v13 + 44) )
    {
      v57 = 1;
      v60 = 0;
    }
    else
    {
      v60 = GetLastError();
    }
    *(_DWORD *)v3 = v60;
    RpcRevertToSelf();
    if ( !v57 )
      goto LABEL_219;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      744,
      WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
      *((unsigned int *)v13 + 44));
  }
  if ( dwProcessId != GetCurrentProcessId() )
  {
    if ( RpcImpersonateClient(0) )
    {
      *(_DWORD *)v3 = 5;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 745, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 5);
      }
      LODWORD(Library) = FreeConnection(v13);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v33 = 746;
        goto LABEL_295;
      }
      return (int)Library;
    }
    UserSidFromToken = GetUserSidFromToken(0, v13 + 12);
    if ( UserSidFromToken
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 747, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, UserSidFromToken);
    }
    RpcRevertToSelf();
LABEL_243:
    v62 = (_QWORD *)qword_1801138A8;
    *v13 = &ConnectionBlockList;
    v13[1] = v62;
    *v62 = v13;
    qword_1801138A8 = (__int64)v13;
    SetRasmanServiceStopControl(0);
    if ( *(_BYTE *)(v3 + 561) && *(_BYTE *)(v3 + 821) )
    {
      v63 = FindConnectionFromEntry((char *)(v3 + 561), (char *)(v3 + 821));
      v64 = v63;
      if ( v63 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control[1].Flink,
            751,
            WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
            *(_QWORD *)(v63 + 16));
        }
        v13[16] = *(_QWORD *)(v64 + 16);
      }
      else
      {
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_274;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_270;
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 752, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
    }
    v67 = WPP_GLOBAL_Control;
LABEL_270:
    if ( v67 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v67[1].Blink) & 0x2000) != 0
      && BYTE1(v67[1].Blink) >= 4u )
    {
      WPP_SF_qdq(v67[1].Flink, 753, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v13[2], *((_DWORD *)v13 + 22), v13);
    }
    goto LABEL_274;
  }
  if ( ConvertStringSidToSidW(Destination, (PSID *)v13 + 12) )
    goto LABEL_243;
  v65 = GetLastError();
  v66 = v65;
  if ( v65
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 748, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v65);
  }
  *(_DWORD *)v3 = v66;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 749, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v66);
  }
  LODWORD(Library) = FreeConnection(v13);
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v33 = 750;
    goto LABEL_295;
  }
  return (int)Library;
}

```

## disassembly

```asm
0x180016500  mov     [rsp+arg_0], rbx
0x180016505  push    rbp
0x180016506  push    rsi
0x180016507  push    rdi
0x180016508  push    r12
0x18001650a  push    r13
0x18001650c  push    r14
0x18001650e  push    r15
0x180016510  mov     eax, 2770h
0x180016515  call    _alloca_probe
0x18001651a  sub     rsp, rax
0x18001651d  mov     rax, cs:__security_cookie
0x180016524  xor     rax, rsp
0x180016527  mov     [rsp+27A8h+var_48], rax
0x18001652f  mov     rsi, r8
0x180016532  mov     [rsp+27A8h+var_2760], r8
0x180016537  mov     rdi, rdx
0x18001653a  mov     rbx, cs:WPP_GLOBAL_Control
0x180016541  lea     rax, WPP_GLOBAL_Control
0x180016548  cmp     rbx, rax
0x18001654b  jz      short loc_180016578
0x18001654d  test    dword ptr [rbx+1Ch], 2000h
0x180016554  jz      short loc_180016578
0x180016556  cmp     byte ptr [rbx+19h], 6
0x18001655a  jb      short loc_180016578
0x18001655c  mov     rcx, [rbx+10h]
0x180016560  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180016567  mov     edx, 2C5h
0x18001656c  call    WPP_SF_
0x180016571  mov     rbx, cs:WPP_GLOBAL_Control
0x180016578  mov     r12d, [rsi+14h]
0x18001657c  lea     rcx, [rsp+27A8h+Destination]; void *
0x180016581  mov     ebp, [rsi+18h]
0x180016584  lea     r15, [rsi+2Ch]
0x180016588  xor     edx, edx; Val
0x18001658a  mov     [rsp+27A8h+var_2778], r12d
0x18001658f  mov     r8d, 2710h; Size
0x180016595  lea     r13, [rsi+130h]
0x18001659c  lea     r14, [rsi+4E0h]
0x1800165a3  call    memset_0
0x1800165a8  lea     rax, WPP_GLOBAL_Control
0x1800165af  cmp     rbx, rax
0x1800165b2  jz      short loc_18001661E
0x1800165b4  test    dword ptr [rbx+1Ch], 2000h
0x1800165bb  jz      short loc_1800165EE
0x1800165bd  cmp     byte ptr [rbx+19h], 4
0x1800165c1  jb      short loc_1800165EE
0x1800165c3  mov     rcx, [rbx+10h]
0x1800165c7  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800165ce  mov     edx, 2C6h
0x1800165d3  mov     [rsp+27A8h+var_2788], r15
0x1800165d8  mov     r9, r13
0x1800165db  call    WPP_SF_ss
0x1800165e0  mov     rbx, cs:WPP_GLOBAL_Control
0x1800165e7  lea     rax, WPP_GLOBAL_Control
0x1800165ee  cmp     rbx, rax
0x1800165f1  jz      short loc_18001661E
0x1800165f3  test    dword ptr [rbx+1Ch], 2000h
0x1800165fa  jz      short loc_18001661E
0x1800165fc  cmp     byte ptr [rbx+19h], 5
0x180016600  jb      short loc_18001661E
0x180016602  mov     rcx, [rbx+10h]
0x180016606  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001660d  mov     edx, 2C7h
0x180016612  mov     dword ptr [rsp+27A8h+var_2788], ebp
0x180016616  mov     r9d, r12d
0x180016619  call    WPP_SF_Dd
0x18001661e  mov     r9d, 1388h; SourceSize
0x180016624  lea     rcx, [rsp+27A8h+Destination]; Destination
0x180016629  mov     r8, r14; Source
0x18001662c  mov     edx, 2710h; DestinationSize
0x180016631  call    cs:__imp_memcpy_s
0x180016638  nop     dword ptr [rax+rax+00h]
0x18001663d  mov     r8, r12
0x180016640  xor     edx, edx; Val
0x180016642  shl     r8, 2; Size
0x180016646  mov     rcx, r14; void *
0x180016649  call    memset_0
0x18001664e  cmp     dword ptr [rdi], 0
0x180016651  jz      short loc_180016685
0x180016653  mov     r9d, [rdi+8]
0x180016657  mov     [rsp+27A8h+dwProcessId], r9d
0x18001665c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016663  lea     rdi, WPP_GLOBAL_Control
0x18001666a  cmp     rcx, rdi
0x18001666d  jz      short loc_1800166CC
0x18001666f  test    dword ptr [rcx+1Ch], 2000h
0x180016676  jz      short loc_1800166CC
0x180016678  cmp     byte ptr [rcx+19h], 5
0x18001667c  jb      short loc_1800166CC
0x18001667e  mov     edx, 2C8h
0x180016683  jmp     short loc_1800166B5
0x180016685  mov     r9d, [rsi+4]
0x180016689  mov     [rsp+27A8h+dwProcessId], r9d
0x18001668e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016695  lea     rdi, WPP_GLOBAL_Control
0x18001669c  cmp     rcx, rdi
0x18001669f  jz      short loc_1800166CC
0x1800166a1  test    dword ptr [rcx+1Ch], 2000h
0x1800166a8  jz      short loc_1800166CC
0x1800166aa  cmp     byte ptr [rcx+19h], 5
0x1800166ae  jb      short loc_1800166CC
0x1800166b0  mov     edx, 2C9h
0x1800166b5  mov     rcx, [rcx+10h]
0x1800166b9  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800166c0  call    WPP_SF_d
0x1800166c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166cc  cmp     ebp, 2
0x1800166cf  jz      loc_180016AA0
0x1800166d5  mov     r9, r14
0x1800166d8  mov     r8d, r12d
0x1800166db  mov     rdx, r13; char *
0x1800166de  mov     rcx, r15; String1
0x1800166e1  call    FindConnectionFromEntry
0x1800166e6  mov     [rsp+27A8h+var_2768], rax
0x1800166eb  mov     rbx, rax
0x1800166ee  test    rax, rax
0x1800166f1  jz      loc_180016A5F
0x1800166f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166fe  lea     r12, WPP_GLOBAL_Control
0x180016705  mov     ebp, 2000h
0x18001670a  cmp     rcx, r12
0x18001670d  jz      short loc_180016736
0x18001670f  test    [rcx+1Ch], ebp
0x180016712  jz      short loc_180016736
0x180016714  cmp     byte ptr [rcx+19h], 4
0x180016718  jb      short loc_180016736
0x18001671a  mov     rcx, [rcx+10h]
0x18001671e  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180016725  mov     edx, 2CAh
0x18001672a  call    WPP_SF_
0x18001672f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016736  cmp     dword ptr [rbx+18h], 0
0x18001673a  jz      short loc_1800167AC
0x18001673c  cmp     rcx, r12
0x18001673f  jz      short loc_180016761
0x180016741  test    [rcx+1Ch], ebp
0x180016744  jz      short loc_180016761
0x180016746  cmp     byte ptr [rcx+19h], 4
0x18001674a  jb      short loc_180016761
0x18001674c  mov     rcx, [rcx+10h]
0x180016750  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180016757  mov     edx, 2CBh
0x18001675c  call    WPP_SF_
0x180016761  inc     dword ptr [rbx+58h]
0x180016764  mov     eax, [rbx+58h]
0x180016767  mov     rcx, cs:WPP_GLOBAL_Control
0x18001676e  cmp     rcx, r12
0x180016771  jz      short loc_1800167A0
0x180016773  test    [rcx+1Ch], ebp
0x180016776  jz      short loc_1800167A0
0x180016778  cmp     byte ptr [rcx+19h], 2
0x18001677c  jb      short loc_1800167A0
0x18001677e  mov     r9, [rbx+10h]
0x180016782  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180016789  mov     rcx, [rcx+10h]
0x18001678d  mov     edx, 2CCh
0x180016792  mov     [rsp+27A8h+var_2780], rbx
0x180016797  mov     dword ptr [rsp+27A8h+var_2788], eax
0x18001679b  call    WPP_SF_qdq
0x1800167a0  mov     dword ptr [rsi+10h], 2
0x1800167a7  jmp     loc_180017565
0x1800167ac  cmp     rcx, r12
0x1800167af  jz      short loc_1800167D8
0x1800167b1  test    [rcx+1Ch], ebp
0x1800167b4  jz      short loc_1800167D8
0x1800167b6  cmp     byte ptr [rcx+19h], 4
0x1800167ba  jb      short loc_1800167D8
0x1800167bc  mov     rcx, [rcx+10h]
0x1800167c0  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800167c7  mov     edx, 2CDh
0x1800167cc  call    WPP_SF_
0x1800167d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167d8  xor     edi, edi
0x1800167da  cmp     edi, [rbx+40h]
0x1800167dd  jnb     short loc_18001682A
0x1800167df  mov     r8, [rbx+38h]
0x1800167e3  mov     rdx, [r8+rdi*8]
0x1800167e7  test    rdx, rdx
0x1800167ea  jz      short loc_1800167F2
0x1800167ec  cmp     dword ptr [rdx+1Ch], 4
0x1800167f0  jnz     short loc_1800167FB
0x1800167f2  inc     edi
0x1800167f4  cmp     edi, [rbx+40h]
0x1800167f7  jb      short loc_1800167E3
0x1800167f9  jmp     short loc_180016827
0x1800167fb  cmp     rcx, r12
0x1800167fe  jz      short loc_180016827
0x180016800  test    [rcx+1Ch], ebp
0x180016803  jz      short loc_180016827
0x180016805  cmp     byte ptr [rcx+19h], 4
0x180016809  jb      short loc_180016827
0x18001680b  mov     rcx, [rcx+10h]
0x18001680f  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180016816  mov     edx, 2CEh
0x18001681b  call    WPP_SF_
0x180016820  mov     rcx, cs:WPP_GLOBAL_Control
0x180016827  cmp     edi, [rbx+40h]
0x18001682a  jnz     loc_180016A1E
0x180016830  cmp     qword ptr [rbx+50h], 0
0x180016835  jz      short loc_18001684F
0x180016837  mov     rcx, [rbx+50h]; hProcess
0x18001683b  call    fIsProcessAlive
0x180016840  mov     rcx, cs:WPP_GLOBAL_Control
0x180016847  test    eax, eax
0x180016849  jnz     loc_180016A1E
0x18001684f  mov     eax, [rbx+8Ch]
0x180016855  mov     r12d, [rbx+40h]
0x180016859  mov     r13, [rbx+10h]
0x18001685d  mov     [rsp+27A8h+var_2770], eax
0x180016861  lea     rdi, WPP_GLOBAL_Control
0x180016868  cmp     rcx, rdi
0x18001686b  jz      short loc_1800168A3
0x18001686d  test    [rcx+1Ch], ebp
0x180016870  jz      short loc_1800168A3
0x180016872  cmp     byte ptr [rcx+19h], 4
0x180016876  jb      short loc_1800168A3
0x180016878  mov     eax, [rbx+58h]
0x18001687b  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180016882  mov     rcx, [rcx+10h]
0x180016886  mov     edx, 2D0h
0x18001688b  mov     [rsp+27A8h+var_2780], rbx
0x180016890  mov     r9, r13
0x180016893  mov     dword ptr [rsp+27A8h+var_2788], eax
0x180016897  call    WPP_SF_qdq
0x18001689c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168a3  test    r12d, r12d
0x1800168a6  jz      loc_1800169FB
0x1800168ac  mov     rax, r12
0x1800168af  mov     edx, 0FFFFFFFFh
0x1800168b4  shl     rax, 3
0x1800168b8  cmp     rax, rdx
0x1800168bb  ja      loc_1800169C5
0x1800168c1  mov     edx, eax; uBytes
0x1800168c3  mov     ecx, 40h ; '@'; uFlags
0x1800168c8  mov     edi, eax
0x1800168ca  call    cs:__imp_LocalAlloc
0x1800168d1  nop     dword ptr [rax+rax+00h]
0x1800168d6  mov     r14, rax
0x1800168d9  test    rax, rax
0x1800168dc  jnz     short loc_180016908
0x1800168de  mov     dword ptr [rsi], 8007000Eh
0x1800168e4  lea     rdi, WPP_GLOBAL_Control
0x1800168eb  mov     rcx, rbx; hMem
0x1800168ee  call    FreeConnection
0x1800168f3  mov     r12d, [rsp+27A8h+var_2778]
0x1800168f8  lea     r13, [rsi+130h]
0x1800168ff  lea     r15, [rsi+2Ch]
0x180016903  jmp     loc_180016AC9
0x180016908  mov     rdx, [rbx+38h]; Src
0x18001690c  mov     r8, rdi; Size
0x18001690f  mov     rcx, r14; void *
0x180016912  xor     ebp, ebp
0x180016914  call    memcpy_0
0x180016919  mov     esi, [rsp+27A8h+var_2770]
0x18001691d  lea     rbx, WPP_GLOBAL_Control
0x180016924  xor     edi, edi
0x180016926  mov     r9, [r14+rdi*8]
0x18001692a  test    r9, r9
0x18001692d  jz      short loc_180016980
0x18001692f  cmp     dword ptr [r9+18h], 1
0x180016934  jz      short loc_180016980
0x180016936  mov     rcx, cs:WPP_GLOBAL_Control
0x18001693d  cmp     rcx, rbx
0x180016940  jz      short loc_18001696A
0x180016942  test    dword ptr [rcx+1Ch], 2000h
0x180016949  jz      short loc_18001696A
0x18001694b  cmp     byte ptr [rcx+19h], 4
0x18001694f  jb      short loc_18001696A
0x180016951  mov     rcx, [rcx+10h]
0x180016955  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001695c  add     r9, 8
0x180016960  mov     edx, 2D2h
0x180016965  call    WPP_SF_s
0x18001696a  mov     rcx, [r14+rdi*8]
0x18001696e  xor     r9d, r9d
0x180016971  mov     r8b, 1
0x180016974  mov     edx, esi
0x180016976  call    PortClose
0x18001697b  mov     ebp, 1
0x180016980  inc     edi
0x180016982  cmp     edi, r12d
0x180016985  jb      short loc_180016926
0x180016987  mov     rcx, r14; hMem
0x18001698a  call    cs:__imp_LocalFree
0x180016991  nop     dword ptr [rax+rax+00h]
0x180016996  mov     rbx, [rsp+27A8h+var_2768]
0x18001699b  mov     rsi, [rsp+27A8h+var_2760]
0x1800169a0  test    ebp, ebp
0x1800169a2  jz      loc_1800168E4
0x1800169a8  mov     rcx, r13
0x1800169ab  call    FindConnection
0x1800169b0  lea     rdi, WPP_GLOBAL_Control
0x1800169b7  test    rax, rax
0x1800169ba  jz      loc_1800168F3
0x1800169c0  jmp     loc_1800168EB
0x1800169c5  cmp     rcx, rdi
0x1800169c8  jz      loc_1800168EB
0x1800169ce  test    [rcx+1Ch], ebp
0x1800169d1  jz      loc_1800168EB
  ... truncated ...
```
