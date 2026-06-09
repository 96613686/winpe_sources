# CreateConnection

- ea: `0x180015c90`
- end: `0x180016d79`
- name: `CreateConnection`
- size: `4329`
- prototype: `int __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180034890`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x180005f1c`
- `0x18000bfb0`
- `0x18000c080`
- `0x180015c90`
- `0x180019be8`
- `0x18002040c`
- `0x1800326fc`
- `0x18003426c`
- `0x18003ea70`
- `0x18003ee98`
- `0x18004055c`
- `0x18004a604`
- `0x1800e71ee`
- `0x1800e7206`
- `0x1800e7260`
- `0x1800e7320`
- `0x1800e9010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015dc1`
- `msvcrt!memcpy_s` at `0x180015dc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800169f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800169f5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180016871`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001694c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180016871`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001694c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001678a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016819`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001678a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001679d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001679d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b70`
- `RPCRT4!RpcImpersonateClient` at `0x1800167d5`
- `RPCRT4!RpcImpersonateClient` at `0x1800168ca`
- `RPCRT4!RpcImpersonateClient` at `0x180016a06`
- `RPCRT4!RpcImpersonateClient` at `0x1800167d5`
- `RPCRT4!RpcImpersonateClient` at `0x1800168ca`
- `RPCRT4!RpcImpersonateClient` at `0x180016a06`
- `RPCRT4!RpcRevertToSelf` at `0x18001685e`
- `RPCRT4!RpcRevertToSelf` at `0x180016967`
- `RPCRT4!RpcRevertToSelf` at `0x180016ab4`
- `RPCRT4!RpcRevertToSelf` at `0x18001685e`
- `RPCRT4!RpcRevertToSelf` at `0x180016967`
- `RPCRT4!RpcRevertToSelf` at `0x180016ab4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016c86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016c86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016ce6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016ce6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016054`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016257`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016054`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016257`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001610e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001610e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016b62`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016b62`

## string_xrefs

- `0x180016c6d`: `rastls.dll`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 709, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
      WPP_SF_ss(v5[1].Flink, 710, (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v3 + 304, v3 + 44);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 5u )
    {
      WPP_SF_Dd(v5[1].Flink, 711, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, (unsigned int)v6, v7);
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
      WPP_SF_d(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v10);
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
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 725, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      goto LABEL_66;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 714, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)(ConnectionFromEntry + 24) )
    {
      if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v14[1].Blink) & 0x2000) != 0
        && BYTE1(v14[1].Blink) >= 4u )
      {
        WPP_SF_(v14[1].Flink, 715, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      ++*(_DWORD *)(ConnectionFromEntry + 88);
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_qdq(
          WPP_GLOBAL_Control[1].Flink,
          716,
          WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
      WPP_SF_(v14[1].Flink, 717, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
        WPP_SF_(v14[1].Flink, 718, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
          WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
          *(_QWORD *)(ConnectionFromEntry + 16),
          *(_DWORD *)(ConnectionFromEntry + 88),
          ConnectionFromEntry);
      }
      *(_DWORD *)(v3 + 16) = 1;
LABEL_274:
      *(_QWORD *)(v3 + 8) = v13[2];
      *(_DWORD *)v3 = 0;
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
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 754, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        }
        LODWORD(Library) = FreeLibrary(v68);
      }
      else
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return (int)Library;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_287;
        LODWORD(Library) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 755, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      v32 = WPP_GLOBAL_Control;
LABEL_287:
      if ( v32 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v32[1].Blink) & 0x2000) == 0
        || BYTE1(v32[1].Blink) < 6u )
      {
        return (int)Library;
      }
      v33 = 756;
      goto LABEL_291;
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
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
                WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 722, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v28 + 8);
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
    WPP_SF_(v14[1].Flink, v29, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    goto LABEL_64;
  }
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v11[1].Blink) & 0x2000) != 0
    && BYTE1(v11[1].Blink) >= 4u )
  {
    WPP_SF_(v11[1].Flink, 726, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
                           WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
LABEL_291:
    LODWORD(Library) = WPP_SF_(v32[1].Flink, v33, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
    WPP_SF_(v35[1].Flink, 706, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
        LODWORD(Library) = WPP_SF_(v35[1].Flink, 707, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
                                 WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                 633);
            v32 = WPP_GLOBAL_Control;
          }
          if ( v32 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v32[1].Blink) & 0x2000) != 0
            && BYTE1(v32[1].Blink) >= 6u )
          {
            v33 = 730;
            goto LABEL_291;
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
    WPP_SF_(v35[1].Flink, 708, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
      goto LABEL_291;
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
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
      goto LABEL_291;
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
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
      goto LABEL_291;
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
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 737, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
    }
    v54 = RpcImpersonateClient(0);
    if ( v54 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 738, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v54);
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
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 739, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v56);
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
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 740, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v58);
    }
    *(_DWORD *)v3 = v58;
    v59 = RpcImpersonateClient(0);
    if ( v59 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 741, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v59);
      }
      *(_DWORD *)v3 = 5;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 742, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, 5);
      }
LABEL_219:
      LODWORD(Library) = FreeConnection(v13);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v33 = 743;
        goto LABEL_291;
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
      WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 745, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, 5);
      }
      LODWORD(Library) = FreeConnection(v13);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v33 = 746;
        goto LABEL_291;
      }
      return (int)Library;
    }
    UserSidFromToken = GetUserSidFromToken(0, v13 + 12);
    if ( UserSidFromToken
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 747, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, UserSidFromToken);
    }
    RpcRevertToSelf();
LABEL_243:
    v62 = (_QWORD *)qword_1801129C8;
    *v13 = &ConnectionBlockList;
    v13[1] = v62;
    *v62 = v13;
    qword_1801129C8 = (__int64)v13;
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
            WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 752, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
    }
    v67 = WPP_GLOBAL_Control;
LABEL_270:
    if ( v67 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v67[1].Blink) & 0x2000) != 0
      && BYTE1(v67[1].Blink) >= 4u )
    {
      WPP_SF_qdq(v67[1].Flink, 753, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v13[2], *((_DWORD *)v13 + 22), v13);
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
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 748, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v65);
  }
  *(_DWORD *)v3 = v66;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 749, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v66);
  }
  LODWORD(Library) = FreeConnection(v13);
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v33 = 750;
    goto LABEL_291;
  }
  return (int)Library;
}

```

## disassembly

```asm
0x180015c90  mov     [rsp+arg_0], rbx
0x180015c95  push    rbp
0x180015c96  push    rsi
0x180015c97  push    rdi
0x180015c98  push    r12
0x180015c9a  push    r13
0x180015c9c  push    r14
0x180015c9e  push    r15
0x180015ca0  mov     eax, 2770h
0x180015ca5  call    _alloca_probe
0x180015caa  sub     rsp, rax
0x180015cad  mov     rax, cs:__security_cookie
0x180015cb4  xor     rax, rsp
0x180015cb7  mov     [rsp+27A8h+var_48], rax
0x180015cbf  mov     rsi, r8
0x180015cc2  mov     [rsp+27A8h+var_2760], r8
0x180015cc7  mov     rdi, rdx
0x180015cca  mov     rbx, cs:WPP_GLOBAL_Control
0x180015cd1  lea     rax, WPP_GLOBAL_Control
0x180015cd8  cmp     rbx, rax
0x180015cdb  jz      short loc_180015D08
0x180015cdd  test    dword ptr [rbx+1Ch], 2000h
0x180015ce4  jz      short loc_180015D08
0x180015ce6  cmp     byte ptr [rbx+19h], 6
0x180015cea  jb      short loc_180015D08
0x180015cec  mov     rcx, [rbx+10h]
0x180015cf0  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015cf7  mov     edx, 2C5h
0x180015cfc  call    WPP_SF_
0x180015d01  mov     rbx, cs:WPP_GLOBAL_Control
0x180015d08  mov     r12d, [rsi+14h]
0x180015d0c  lea     rcx, [rsp+27A8h+Destination]; void *
0x180015d11  mov     ebp, [rsi+18h]
0x180015d14  lea     r15, [rsi+2Ch]
0x180015d18  xor     edx, edx; Val
0x180015d1a  mov     [rsp+27A8h+var_2778], r12d
0x180015d1f  mov     r8d, 2710h; Size
0x180015d25  lea     r13, [rsi+130h]
0x180015d2c  lea     r14, [rsi+4E0h]
0x180015d33  call    memset_0
0x180015d38  lea     rax, WPP_GLOBAL_Control
0x180015d3f  cmp     rbx, rax
0x180015d42  jz      short loc_180015DAE
0x180015d44  test    dword ptr [rbx+1Ch], 2000h
0x180015d4b  jz      short loc_180015D7E
0x180015d4d  cmp     byte ptr [rbx+19h], 4
0x180015d51  jb      short loc_180015D7E
0x180015d53  mov     rcx, [rbx+10h]
0x180015d57  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015d5e  mov     edx, 2C6h
0x180015d63  mov     [rsp+27A8h+var_2788], r15
0x180015d68  mov     r9, r13
0x180015d6b  call    WPP_SF_ss
0x180015d70  mov     rbx, cs:WPP_GLOBAL_Control
0x180015d77  lea     rax, WPP_GLOBAL_Control
0x180015d7e  cmp     rbx, rax
0x180015d81  jz      short loc_180015DAE
0x180015d83  test    dword ptr [rbx+1Ch], 2000h
0x180015d8a  jz      short loc_180015DAE
0x180015d8c  cmp     byte ptr [rbx+19h], 5
0x180015d90  jb      short loc_180015DAE
0x180015d92  mov     rcx, [rbx+10h]
0x180015d96  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015d9d  mov     edx, 2C7h
0x180015da2  mov     dword ptr [rsp+27A8h+var_2788], ebp
0x180015da6  mov     r9d, r12d
0x180015da9  call    WPP_SF_Dd
0x180015dae  mov     r9d, 1388h; SourceSize
0x180015db4  lea     rcx, [rsp+27A8h+Destination]; Destination
0x180015db9  mov     r8, r14; Source
0x180015dbc  mov     edx, 2710h; DestinationSize
0x180015dc1  call    cs:__imp_memcpy_s
0x180015dc7  mov     r8, r12
0x180015dca  xor     edx, edx; Val
0x180015dcc  shl     r8, 2; Size
0x180015dd0  mov     rcx, r14; void *
0x180015dd3  call    memset_0
0x180015dd8  cmp     dword ptr [rdi], 0
0x180015ddb  jz      short loc_180015E0F
0x180015ddd  mov     r9d, [rdi+8]
0x180015de1  mov     [rsp+27A8h+dwProcessId], r9d
0x180015de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ded  lea     rdi, WPP_GLOBAL_Control
0x180015df4  cmp     rcx, rdi
0x180015df7  jz      short loc_180015E56
0x180015df9  test    dword ptr [rcx+1Ch], 2000h
0x180015e00  jz      short loc_180015E56
0x180015e02  cmp     byte ptr [rcx+19h], 5
0x180015e06  jb      short loc_180015E56
0x180015e08  mov     edx, 2C8h
0x180015e0d  jmp     short loc_180015E3F
0x180015e0f  mov     r9d, [rsi+4]
0x180015e13  mov     [rsp+27A8h+dwProcessId], r9d
0x180015e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e1f  lea     rdi, WPP_GLOBAL_Control
0x180015e26  cmp     rcx, rdi
0x180015e29  jz      short loc_180015E56
0x180015e2b  test    dword ptr [rcx+1Ch], 2000h
0x180015e32  jz      short loc_180015E56
0x180015e34  cmp     byte ptr [rcx+19h], 5
0x180015e38  jb      short loc_180015E56
0x180015e3a  mov     edx, 2C9h
0x180015e3f  mov     rcx, [rcx+10h]
0x180015e43  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015e4a  call    WPP_SF_d
0x180015e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e56  cmp     ebp, 2
0x180015e59  jz      loc_18001621E
0x180015e5f  mov     r9, r14
0x180015e62  mov     r8d, r12d
0x180015e65  mov     rdx, r13; char *
0x180015e68  mov     rcx, r15; String1
0x180015e6b  call    FindConnectionFromEntry
0x180015e70  mov     [rsp+27A8h+var_2768], rax
0x180015e75  mov     rbx, rax
0x180015e78  test    rax, rax
0x180015e7b  jz      loc_1800161DD
0x180015e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e88  lea     r12, WPP_GLOBAL_Control
0x180015e8f  mov     ebp, 2000h
0x180015e94  cmp     rcx, r12
0x180015e97  jz      short loc_180015EC0
0x180015e99  test    [rcx+1Ch], ebp
0x180015e9c  jz      short loc_180015EC0
0x180015e9e  cmp     byte ptr [rcx+19h], 4
0x180015ea2  jb      short loc_180015EC0
0x180015ea4  mov     rcx, [rcx+10h]
0x180015ea8  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015eaf  mov     edx, 2CAh
0x180015eb4  call    WPP_SF_
0x180015eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ec0  cmp     dword ptr [rbx+18h], 0
0x180015ec4  jz      short loc_180015F36
0x180015ec6  cmp     rcx, r12
0x180015ec9  jz      short loc_180015EEB
0x180015ecb  test    [rcx+1Ch], ebp
0x180015ece  jz      short loc_180015EEB
0x180015ed0  cmp     byte ptr [rcx+19h], 4
0x180015ed4  jb      short loc_180015EEB
0x180015ed6  mov     rcx, [rcx+10h]
0x180015eda  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015ee1  mov     edx, 2CBh
0x180015ee6  call    WPP_SF_
0x180015eeb  inc     dword ptr [rbx+58h]
0x180015eee  mov     eax, [rbx+58h]
0x180015ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ef8  cmp     rcx, r12
0x180015efb  jz      short loc_180015F2A
0x180015efd  test    [rcx+1Ch], ebp
0x180015f00  jz      short loc_180015F2A
0x180015f02  cmp     byte ptr [rcx+19h], 2
0x180015f06  jb      short loc_180015F2A
0x180015f08  mov     r9, [rbx+10h]
0x180015f0c  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015f13  mov     rcx, [rcx+10h]
0x180015f17  mov     edx, 2CCh
0x180015f1c  mov     [rsp+27A8h+var_2780], rbx
0x180015f21  mov     dword ptr [rsp+27A8h+var_2788], eax
0x180015f25  call    WPP_SF_qdq
0x180015f2a  mov     dword ptr [rsi+10h], 2
0x180015f31  jmp     loc_180016C69
0x180015f36  cmp     rcx, r12
0x180015f39  jz      short loc_180015F62
0x180015f3b  test    [rcx+1Ch], ebp
0x180015f3e  jz      short loc_180015F62
0x180015f40  cmp     byte ptr [rcx+19h], 4
0x180015f44  jb      short loc_180015F62
0x180015f46  mov     rcx, [rcx+10h]
0x180015f4a  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015f51  mov     edx, 2CDh
0x180015f56  call    WPP_SF_
0x180015f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f62  xor     edi, edi
0x180015f64  cmp     edi, [rbx+40h]
0x180015f67  jnb     short loc_180015FB4
0x180015f69  mov     r8, [rbx+38h]
0x180015f6d  mov     rdx, [r8+rdi*8]
0x180015f71  test    rdx, rdx
0x180015f74  jz      short loc_180015F7C
0x180015f76  cmp     dword ptr [rdx+1Ch], 4
0x180015f7a  jnz     short loc_180015F85
0x180015f7c  inc     edi
0x180015f7e  cmp     edi, [rbx+40h]
0x180015f81  jb      short loc_180015F6D
0x180015f83  jmp     short loc_180015FB1
0x180015f85  cmp     rcx, r12
0x180015f88  jz      short loc_180015FB1
0x180015f8a  test    [rcx+1Ch], ebp
0x180015f8d  jz      short loc_180015FB1
0x180015f8f  cmp     byte ptr [rcx+19h], 4
0x180015f93  jb      short loc_180015FB1
0x180015f95  mov     rcx, [rcx+10h]
0x180015f99  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180015fa0  mov     edx, 2CEh
0x180015fa5  call    WPP_SF_
0x180015faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fb1  cmp     edi, [rbx+40h]
0x180015fb4  jnz     loc_18001619C
0x180015fba  cmp     qword ptr [rbx+50h], 0
0x180015fbf  jz      short loc_180015FD9
0x180015fc1  mov     rcx, [rbx+50h]; hProcess
0x180015fc5  call    fIsProcessAlive
0x180015fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fd1  test    eax, eax
0x180015fd3  jnz     loc_18001619C
0x180015fd9  mov     eax, [rbx+8Ch]
0x180015fdf  mov     r12d, [rbx+40h]
0x180015fe3  mov     r13, [rbx+10h]
0x180015fe7  mov     [rsp+27A8h+var_2770], eax
0x180015feb  lea     rdi, WPP_GLOBAL_Control
0x180015ff2  cmp     rcx, rdi
0x180015ff5  jz      short loc_18001602D
0x180015ff7  test    [rcx+1Ch], ebp
0x180015ffa  jz      short loc_18001602D
0x180015ffc  cmp     byte ptr [rcx+19h], 4
0x180016000  jb      short loc_18001602D
0x180016002  mov     eax, [rbx+58h]
0x180016005  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001600c  mov     rcx, [rcx+10h]
0x180016010  mov     edx, 2D0h
0x180016015  mov     [rsp+27A8h+var_2780], rbx
0x18001601a  mov     r9, r13
0x18001601d  mov     dword ptr [rsp+27A8h+var_2788], eax
0x180016021  call    WPP_SF_qdq
0x180016026  mov     rcx, cs:WPP_GLOBAL_Control
0x18001602d  test    r12d, r12d
0x180016030  jz      loc_180016179
0x180016036  mov     rax, r12
0x180016039  mov     edx, 0FFFFFFFFh
0x18001603e  shl     rax, 3
0x180016042  cmp     rax, rdx
0x180016045  ja      loc_180016143
0x18001604b  mov     edx, eax; uBytes
0x18001604d  mov     ecx, 40h ; '@'; uFlags
0x180016052  mov     edi, eax
0x180016054  call    cs:__imp_LocalAlloc
0x18001605a  mov     r14, rax
0x18001605d  test    rax, rax
0x180016060  jnz     short loc_18001608C
0x180016062  mov     dword ptr [rsi], 8007000Eh
0x180016068  lea     rdi, WPP_GLOBAL_Control
0x18001606f  mov     rcx, rbx; hMem
0x180016072  call    FreeConnection
0x180016077  mov     r12d, [rsp+27A8h+var_2778]
0x18001607c  lea     r13, [rsi+130h]
0x180016083  lea     r15, [rsi+2Ch]
0x180016087  jmp     loc_180016247
0x18001608c  mov     rdx, [rbx+38h]; Src
0x180016090  mov     r8, rdi; Size
0x180016093  mov     rcx, r14; void *
0x180016096  xor     ebp, ebp
0x180016098  call    memcpy_0
0x18001609d  mov     esi, [rsp+27A8h+var_2770]
0x1800160a1  lea     rbx, WPP_GLOBAL_Control
0x1800160a8  xor     edi, edi
0x1800160aa  mov     r9, [r14+rdi*8]
0x1800160ae  test    r9, r9
0x1800160b1  jz      short loc_180016104
0x1800160b3  cmp     dword ptr [r9+18h], 1
0x1800160b8  jz      short loc_180016104
0x1800160ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160c1  cmp     rcx, rbx
0x1800160c4  jz      short loc_1800160EE
0x1800160c6  test    dword ptr [rcx+1Ch], 2000h
0x1800160cd  jz      short loc_1800160EE
0x1800160cf  cmp     byte ptr [rcx+19h], 4
0x1800160d3  jb      short loc_1800160EE
0x1800160d5  mov     rcx, [rcx+10h]
0x1800160d9  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800160e0  add     r9, 8
0x1800160e4  mov     edx, 2D2h
0x1800160e9  call    WPP_SF_s
0x1800160ee  mov     rcx, [r14+rdi*8]
0x1800160f2  xor     r9d, r9d
0x1800160f5  mov     r8b, 1
0x1800160f8  mov     edx, esi
0x1800160fa  call    PortClose
0x1800160ff  mov     ebp, 1
0x180016104  inc     edi
0x180016106  cmp     edi, r12d
0x180016109  jb      short loc_1800160AA
0x18001610b  mov     rcx, r14; hMem
0x18001610e  call    cs:__imp_LocalFree
0x180016114  mov     rbx, [rsp+27A8h+var_2768]
0x180016119  mov     rsi, [rsp+27A8h+var_2760]
0x18001611e  test    ebp, ebp
0x180016120  jz      loc_180016068
0x180016126  mov     rcx, r13
0x180016129  call    FindConnection
0x18001612e  lea     rdi, WPP_GLOBAL_Control
0x180016135  test    rax, rax
0x180016138  jz      loc_180016077
0x18001613e  jmp     loc_18001606F
0x180016143  cmp     rcx, rdi
0x180016146  jz      loc_18001606F
0x18001614c  test    [rcx+1Ch], ebp
0x18001614f  jz      loc_18001606F
0x180016155  cmp     byte ptr [rcx+19h], 4
0x180016159  jb      loc_18001606F
0x18001615f  mov     edx, 2D1h
  ... truncated ...
```
