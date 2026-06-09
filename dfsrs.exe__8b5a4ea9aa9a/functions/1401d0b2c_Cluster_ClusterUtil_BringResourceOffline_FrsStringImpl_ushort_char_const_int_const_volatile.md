# Cluster::ClusterUtil::BringResourceOffline(FrsStringImpl<ushort,char> const &,int const volatile &)

- ea: `0x1401d0b2c`
- end: `0x1401d1032`
- name: `?BringResourceOffline@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEDH@Z`
- size: `1286`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1401db450`
- `0x1401dbce0`

## callees

- `0x14000c910`
- `0x14000e34c`
- `0x14001c31c`
- `0x1401b9494`
- `0x1401ce854`
- `0x1401d0b2c`
- `0x1401d1570`
- `0x1401d7bfc`

## import_xrefs

- `KERNEL32!Sleep` at `0x1401d0e82`
- `KERNEL32!Sleep` at `0x1401d0e82`
- `KERNEL32!GetLastError` at `0x1401d0bf4`
- `KERNEL32!GetLastError` at `0x1401d0f22`
- `KERNEL32!GetLastError` at `0x1401d0bf4`
- `KERNEL32!GetLastError` at `0x1401d0f22`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0c06`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0d05`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0e17`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0f30`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0f91`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0c06`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0d05`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0e17`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0f30`
- `KERNEL32!GetCurrentThreadId` at `0x1401d0f91`
- `CLUSAPI!OfflineClusterResource` at `0x1401d0cd9`
- `CLUSAPI!OfflineClusterResource` at `0x1401d0cd9`
- `CLUSAPI!GetClusterResourceState` at `0x1401d0bde`
- `CLUSAPI!GetClusterResourceState` at `0x1401d0e9f`
- `CLUSAPI!GetClusterResourceState` at `0x1401d0bde`
- `CLUSAPI!GetClusterResourceState` at `0x1401d0e9f`

## string_xrefs

- `0x1401d0ca4`: `[CLUSTER] Resource is already offline, offline pending or failed. resName:%? resState:%?`

## pseudocode

```c
__int64 __fastcall Cluster::ClusterUtil::BringResourceOffline(__int64 a1, _DWORD *a2)
{
  __int64 v2; // rdi
  const unsigned __int16 *v5; // rcx
  int v6; // r15d
  struct FrsStatus *v7; // rbx
  CLUSTER_RESOURCE_STATE v8; // ecx
  DWORD LastError; // esi
  DWORD CurrentThreadId; // eax
  __int64 v11; // rcx
  __int32 v12; // ecx
  __int32 v13; // ecx
  LPCRITICAL_SECTION v14; // rax
  DWORD v15; // ebx
  DWORD v16; // eax
  __int64 v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD v21; // ebx
  DWORD v22; // eax
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rcx
  struct _HCLUSTER *v26; // [rsp+50h] [rbp-29h] BYREF
  const wchar_t *v27; // [rsp+58h] [rbp-21h] BYREF
  int v28; // [rsp+60h] [rbp-19h]
  int v29; // [rsp+64h] [rbp-15h]
  const wchar_t *v30; // [rsp+68h] [rbp-11h]
  const wchar_t *v31; // [rsp+70h] [rbp-9h] BYREF
  int v32; // [rsp+78h] [rbp-1h]
  int v33; // [rsp+7Ch] [rbp+3h]
  const wchar_t *v34; // [rsp+80h] [rbp+7h]
  const wchar_t *v35; // [rsp+88h] [rbp+Fh] BYREF
  int v36; // [rsp+90h] [rbp+17h]
  int v37; // [rsp+94h] [rbp+1Bh]
  const wchar_t *v38; // [rsp+98h] [rbp+1Fh]
  CLUSTER_RESOURCE_STATE ClusterResourceState; // [rsp+E0h] [rbp+67h] BYREF
  struct FrsStatus *v40; // [rsp+F0h] [rbp+77h] BYREF
  HRESOURCE hResource; // [rsp+F8h] [rbp+7Fh] BYREF

  ClusterResourceState = ClusterResourceStateUnknown;
  v2 = 0;
  v26 = 0;
  hResource = 0;
  v5 = L"CLUS";
  v6 = 1;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v30 = L"CLUS";
    v27 = L"Cluster::ClusterUtil::BringResourceOffline";
    v28 = 2123;
    v29 = 4;
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
      &v27,
      L"[CLUSTER] Offline resource. resName:%?",
      a1);
  }
  v40 = Cluster::ClusterUtil::OpenClusterAndResource(
          v5,
          (const unsigned __int16 *)(*(_QWORD *)a1 + 18LL),
          &v26,
          &hResource);
  v7 = v40;
  if ( v40 )
    goto LABEL_17;
  ClusterResourceState = GetClusterResourceState(hResource, 0, 0, 0, 0);
  v8 = ClusterResourceState;
  if ( ClusterResourceState == ClusterResourceStateUnknown )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      CurrentThreadId = GetCurrentThreadId();
      v40 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v11,
                                  LastError,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                  "Cluster::ClusterUtil::BringResourceOffline",
                                  2147,
                                  CurrentThreadId,
                                  0);
      v7 = v40;
      if ( v40 )
        goto LABEL_17;
    }
    v8 = ClusterResourceState;
  }
  v12 = v8 - 3;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 126 )
      {
LABEL_17:
        v14 = g_DebugLog;
        goto LABEL_18;
      }
    }
  }
  v14 = g_DebugLog;
  v6 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v27 = L"Cluster::ClusterUtil::BringResourceOffline";
    v30 = L"CLUS";
    v28 = 2163;
    v29 = 4;
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,enum CLUSTER_RESOURCE_STATE>(
      &v27,
      L"[CLUSTER] Resource is already offline, offline pending or failed. resName:%? resState:%?",
      a1,
      &ClusterResourceState);
    goto LABEL_17;
  }
LABEL_18:
  if ( v7 )
  {
LABEL_26:
    if ( *((_DWORD *)v7 + 1) == 5007 )
    {
      if ( v14 && LODWORD(v14[1].LockSemaphore) && SLODWORD(v14[1].OwningThread) >= 4 )
      {
        v35 = L"Cluster::ClusterUtil::BringResourceOffline";
        v38 = L"CLUS";
        v36 = 2235;
        v37 = 4;
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
          &v35,
          L"[CLUSTER] Resource is not found, nothing to offline. resName:%?",
          a1);
      }
      CLEAR_ERROR(&v40);
      v14 = g_DebugLog;
      v7 = v40;
    }
    if ( v7 && v14 && LODWORD(v14[1].LockSemaphore) && SLODWORD(v14[1].OwningThread) >= 2 )
    {
      v35 = L"Cluster::ClusterUtil::BringResourceOffline";
      v38 = L"CLUS";
      v36 = 2241;
      v37 = 2;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v35,
        L"[CLUSTER] Failed to offline a resource. resName:%?",
        a1);
    }
    goto LABEL_37;
  }
  if ( v6 )
  {
    v15 = OfflineClusterResource(hResource);
    if ( v15 == 997 )
    {
      ClusterResourceState = ClusterResourceOfflinePending;
      goto LABEL_42;
    }
    if ( v15 )
    {
      v16 = GetCurrentThreadId();
      v40 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v17,
                                  v15,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                  "Cluster::ClusterUtil::BringResourceOffline",
                                  2189,
                                  v16,
                                  0);
      v7 = v40;
      if ( v40 )
      {
        v14 = g_DebugLog;
        goto LABEL_26;
      }
    }
  }
LABEL_42:
  while ( !*a2 && ClusterResourceState == ClusterResourceOfflinePending )
  {
    Sleep(0x1F4u);
    ClusterResourceState = GetClusterResourceState(hResource, 0, 0, 0, 0);
  }
  if ( *a2 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v28 = 2206;
      v30 = L"CLUS";
      v27 = L"Cluster::ClusterUtil::BringResourceOffline";
      v29 = 3;
      dbgobj::DbgPrint<unsigned short>(&v27, L"[CLUSTER] Aborting offline because the shutdown flag was set");
    }
    goto LABEL_48;
  }
  if ( (unsigned int)(ClusterResourceState - 3) <= 1 )
  {
LABEL_48:
    v7 = v40;
    goto LABEL_37;
  }
  if ( ClusterResourceState == ClusterResourceStateUnknown )
  {
    v21 = GetLastError();
    v22 = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v23,
                               v21,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                               "Cluster::ClusterUtil::BringResourceOffline",
                               2218,
                               v22,
                               0);
    v40 = v7;
    v14 = g_DebugLog;
  }
  else
  {
    v24 = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v25,
                               9233,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                               "Cluster::ClusterUtil::BringResourceOffline",
                               2221,
                               v24,
                               0);
    v40 = v7;
    v14 = g_DebugLog;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v31 = L"Cluster::ClusterUtil::BringResourceOffline";
      v34 = L"CLUS";
      v32 = 2223;
      v33 = 2;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,enum CLUSTER_RESOURCE_STATE>(
        &v31,
        L"[CLUSTER] Failed to bring resource offline because resource  is in invalid state. resName:%? resState:%?",
        a1,
        &ClusterResourceState);
      v14 = g_DebugLog;
    }
  }
  if ( v7 )
    goto LABEL_26;
LABEL_37:
  Cluster::ClusterUtil::CloseClusterAndResource(&v26, &hResource);
  if ( v7 )
  {
    v18 = GetCurrentThreadId();
    return FrsStatusList::PushNewError(
             v19,
             *((unsigned int *)v7 + 1),
             *((unsigned int *)v7 + 2),
             *(unsigned int *)v7,
             "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
             "Cluster::ClusterUtil::BringResourceOffline",
             2247,
             v18,
             v7);
  }
  return v2;
}

```

## disassembly

```asm
0x1401d0b2c  push    rbp
0x1401d0b2e  push    rbx
0x1401d0b2f  push    rsi
0x1401d0b30  push    rdi
0x1401d0b31  push    r12
0x1401d0b33  push    r14
0x1401d0b35  push    r15
0x1401d0b37  lea     rbp, [rsp-27h]
0x1401d0b3c  sub     rsp, 0A0h
0x1401d0b43  or      [rbp+57h+arg_0], 0FFFFFFFFh
0x1401d0b47  lea     rsi, aClusterCluster_14; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0b4e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0b55  xor     edi, edi
0x1401d0b57  mov     [rbp+57h+var_80], rdi
0x1401d0b5b  mov     r14, rcx
0x1401d0b5e  mov     [rbp+57h+hResource], rdi
0x1401d0b62  mov     r12, rdx
0x1401d0b65  lea     rcx, aClus; "CLUS"
0x1401d0b6c  lea     r15d, [rdi+1]
0x1401d0b70  test    rax, rax
0x1401d0b73  jz      short loc_1401D0BA9
0x1401d0b75  cmp     [rax+40h], edi
0x1401d0b78  jz      short loc_1401D0BA9
0x1401d0b7a  cmp     dword ptr [rax+38h], 4
0x1401d0b7e  jl      short loc_1401D0BA9
0x1401d0b80  mov     [rbp+57h+var_68], rcx
0x1401d0b84  lea     rdx, aClusterOffline_0; "[CLUSTER] Offline resource. resName:%?"
0x1401d0b8b  lea     rcx, [rbp+57h+var_78]
0x1401d0b8f  mov     [rbp+57h+var_78], rsi
0x1401d0b93  mov     r8, r14
0x1401d0b96  mov     [rbp+57h+var_70], 84Bh
0x1401d0b9d  mov     [rbp+57h+var_6C], 4
0x1401d0ba4  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d0ba9  mov     rdx, [r14]
0x1401d0bac  lea     r9, [rbp+57h+hResource]; struct _HRESOURCE **
0x1401d0bb0  add     rdx, 12h; unsigned __int16 *
0x1401d0bb4  lea     r8, [rbp+57h+var_80]; struct _HCLUSTER **
0x1401d0bb8  call    ?OpenClusterAndResource@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBG0AEAPEAU_HCLUSTER@@AEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::OpenClusterAndResource(ushort const *,ushort const *,_HCLUSTER * &,_HRESOURCE * &)
0x1401d0bbd  mov     [rbp+57h+arg_10], rax
0x1401d0bc1  mov     rbx, rax
0x1401d0bc4  test    rax, rax
0x1401d0bc7  jnz     loc_1401D0CBB
0x1401d0bcd  mov     rcx, [rbp+57h+hResource]; hResource
0x1401d0bd1  xor     r9d, r9d; lpszGroupName
0x1401d0bd4  xor     r8d, r8d; lpcchNodeName
0x1401d0bd7  mov     [rsp+0D0h+lpcchGroupName], rdi; lpcchGroupName
0x1401d0bdc  xor     edx, edx; lpszNodeName
0x1401d0bde  call    cs:__imp_GetClusterResourceState
0x1401d0be5  nop     dword ptr [rax+rax+00h]
0x1401d0bea  mov     [rbp+57h+arg_0], eax
0x1401d0bed  mov     ecx, eax
0x1401d0bef  cmp     eax, 0FFFFFFFFh
0x1401d0bf2  jnz     short loc_1401D0C5E
0x1401d0bf4  call    cs:__imp_GetLastError
0x1401d0bfb  nop     dword ptr [rax+rax+00h]
0x1401d0c00  mov     esi, eax
0x1401d0c02  test    eax, eax
0x1401d0c04  jz      short loc_1401D0C54
0x1401d0c06  call    cs:__imp_GetCurrentThreadId
0x1401d0c0d  nop     dword ptr [rax+rax+00h]
0x1401d0c12  mov     [rsp+0D0h+var_90], rdi
0x1401d0c17  mov     r9d, r15d
0x1401d0c1a  mov     [rsp+0D0h+var_98], eax
0x1401d0c1e  xor     r8d, r8d
0x1401d0c21  lea     rax, aClusterCluster_56; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0c28  mov     [rsp+0D0h+var_A0], 863h
0x1401d0c30  mov     [rsp+0D0h+var_A8], rax
0x1401d0c35  mov     edx, esi
0x1401d0c37  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d0c3e  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d0c43  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d0c48  mov     [rbp+57h+arg_10], rax
0x1401d0c4c  mov     rbx, rax
0x1401d0c4f  test    rax, rax
0x1401d0c52  jnz     short loc_1401D0CBB
0x1401d0c54  mov     ecx, [rbp+57h+arg_0]
0x1401d0c57  lea     rsi, aClusterCluster_14; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0c5e  sub     ecx, 3
0x1401d0c61  jz      short loc_1401D0C6D
0x1401d0c63  sub     ecx, r15d
0x1401d0c66  jz      short loc_1401D0C6D
0x1401d0c68  cmp     ecx, 7Eh ; '~'
0x1401d0c6b  jnz     short loc_1401D0CBB
0x1401d0c6d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0c74  mov     r15d, edi
0x1401d0c77  test    rax, rax
0x1401d0c7a  jz      short loc_1401D0CC2
0x1401d0c7c  cmp     [rax+40h], edi
0x1401d0c7f  jz      short loc_1401D0CC2
0x1401d0c81  cmp     dword ptr [rax+38h], 4
0x1401d0c85  jl      short loc_1401D0CC2
0x1401d0c87  lea     rax, aClus; "CLUS"
0x1401d0c8e  mov     [rbp+57h+var_78], rsi
0x1401d0c92  lea     r9, [rbp+57h+arg_0]
0x1401d0c96  mov     [rbp+57h+var_68], rax
0x1401d0c9a  mov     r8, r14
0x1401d0c9d  mov     [rbp+57h+var_70], 873h
0x1401d0ca4  lea     rdx, aClusterResourc_3; "[CLUSTER] Resource is already offline, "...
0x1401d0cab  mov     [rbp+57h+var_6C], 4
0x1401d0cb2  lea     rcx, [rbp+57h+var_78]
0x1401d0cb6  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@W4CLUSTER_RESOURCE_STATE@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBW4CLUSTER_RESOURCE_STATE@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,CLUSTER_RESOURCE_STATE>(ushort const *,FrsStringImpl<ushort,char> const &,CLUSTER_RESOURCE_STATE const &)
0x1401d0cbb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0cc2  mov     esi, 2
0x1401d0cc7  test    rbx, rbx
0x1401d0cca  jnz     loc_1401D0D61
0x1401d0cd0  test    r15d, r15d
0x1401d0cd3  jz      short loc_1401D0CF5
0x1401d0cd5  mov     rcx, [rbp+57h+hResource]; hResource
0x1401d0cd9  call    cs:__imp_OfflineClusterResource
0x1401d0ce0  nop     dword ptr [rax+rax+00h]
0x1401d0ce5  mov     ebx, eax
0x1401d0ce7  cmp     eax, 3E5h
0x1401d0cec  jnz     short loc_1401D0D01
0x1401d0cee  mov     [rbp+57h+arg_0], 82h
0x1401d0cf5  lea     r15, aClusterCluster_56; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0cfc  jmp     loc_1401D0EAE
0x1401d0d01  test    ebx, ebx
0x1401d0d03  jz      short loc_1401D0CF5
0x1401d0d05  call    cs:__imp_GetCurrentThreadId
0x1401d0d0c  nop     dword ptr [rax+rax+00h]
0x1401d0d11  mov     [rsp+0D0h+var_90], rdi
0x1401d0d16  lea     r15, aClusterCluster_56; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0d1d  mov     [rsp+0D0h+var_98], eax
0x1401d0d21  mov     r9d, 1
0x1401d0d27  mov     [rsp+0D0h+var_A0], 88Dh
0x1401d0d2f  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d0d36  mov     [rsp+0D0h+var_A8], r15
0x1401d0d3b  xor     r8d, r8d
0x1401d0d3e  mov     edx, ebx
0x1401d0d40  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d0d45  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d0d4a  mov     [rbp+57h+arg_10], rax
0x1401d0d4e  mov     rbx, rax
0x1401d0d51  test    rax, rax
0x1401d0d54  jz      loc_1401D0EAE
0x1401d0d5a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0d61  lea     r15, aClusterCluster_14; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0d68  cmp     dword ptr [rbx+4], 138Fh
0x1401d0d6f  jnz     short loc_1401D0DC5
0x1401d0d71  test    rax, rax
0x1401d0d74  jz      short loc_1401D0DB1
0x1401d0d76  cmp     [rax+40h], edi
0x1401d0d79  jz      short loc_1401D0DB1
0x1401d0d7b  cmp     dword ptr [rax+38h], 4
0x1401d0d7f  jl      short loc_1401D0DB1
0x1401d0d81  lea     rax, aClus; "CLUS"
0x1401d0d88  mov     [rbp+57h+var_48], r15
0x1401d0d8c  mov     r8, r14
0x1401d0d8f  mov     [rbp+57h+var_38], rax
0x1401d0d93  lea     rdx, aClusterResourc_1; "[CLUSTER] Resource is not found, nothin"...
0x1401d0d9a  mov     [rbp+57h+var_40], 8BBh
0x1401d0da1  lea     rcx, [rbp+57h+var_48]
0x1401d0da5  mov     [rbp+57h+var_3C], 4
0x1401d0dac  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d0db1  lea     rcx, [rbp+57h+arg_10]; struct FrsStatus **
0x1401d0db5  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401d0dba  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0dc1  mov     rbx, [rbp+57h+arg_10]
0x1401d0dc5  test    rbx, rbx
0x1401d0dc8  jz      short loc_1401D0E05
0x1401d0dca  test    rax, rax
0x1401d0dcd  jz      short loc_1401D0E05
0x1401d0dcf  cmp     [rax+40h], edi
0x1401d0dd2  jz      short loc_1401D0E05
0x1401d0dd4  cmp     [rax+38h], esi
0x1401d0dd7  jl      short loc_1401D0E05
0x1401d0dd9  lea     rax, aClus; "CLUS"
0x1401d0de0  mov     [rbp+57h+var_48], r15
0x1401d0de4  mov     r8, r14
0x1401d0de7  mov     [rbp+57h+var_38], rax
0x1401d0deb  lea     rdx, aClusterFailedT_29; "[CLUSTER] Failed to offline a resource."...
0x1401d0df2  mov     [rbp+57h+var_40], 8C1h
0x1401d0df9  lea     rcx, [rbp+57h+var_48]
0x1401d0dfd  mov     [rbp+57h+var_3C], esi
0x1401d0e00  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d0e05  lea     rdx, [rbp+57h+hResource]; struct _HRESOURCE **
0x1401d0e09  lea     rcx, [rbp+57h+var_80]; struct _HCLUSTER **
0x1401d0e0d  call    ?CloseClusterAndResource@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@AEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::CloseClusterAndResource(_HCLUSTER * &,_HRESOURCE * &)
0x1401d0e12  test    rbx, rbx
0x1401d0e15  jz      short loc_1401D0E5E
0x1401d0e17  call    cs:__imp_GetCurrentThreadId
0x1401d0e1e  nop     dword ptr [rax+rax+00h]
0x1401d0e23  mov     r9d, [rbx]
0x1401d0e26  mov     r8d, [rbx+8]
0x1401d0e2a  mov     edx, [rbx+4]
0x1401d0e2d  mov     [rsp+0D0h+var_90], rbx
0x1401d0e32  mov     [rsp+0D0h+var_98], eax
0x1401d0e36  lea     rax, aClusterCluster_56; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0e3d  mov     [rsp+0D0h+var_A0], 8C7h
0x1401d0e45  mov     [rsp+0D0h+var_A8], rax
0x1401d0e4a  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d0e51  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d0e56  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d0e5b  mov     rdi, rax
0x1401d0e5e  mov     rax, rdi
0x1401d0e61  add     rsp, 0A0h
0x1401d0e68  pop     r15
0x1401d0e6a  pop     r14
0x1401d0e6c  pop     r12
0x1401d0e6e  pop     rdi
0x1401d0e6f  pop     rsi
0x1401d0e70  pop     rbx
0x1401d0e71  pop     rbp
0x1401d0e72  retn
0x1401d0e74  cmp     [rbp+57h+arg_0], 82h
0x1401d0e7b  jnz     short loc_1401D0EB6
0x1401d0e7d  mov     ecx, 1F4h; dwMilliseconds
0x1401d0e82  call    cs:__imp_Sleep
0x1401d0e89  nop     dword ptr [rax+rax+00h]
0x1401d0e8e  mov     rcx, [rbp+57h+hResource]; hResource
0x1401d0e92  xor     r9d, r9d; lpszGroupName
0x1401d0e95  xor     r8d, r8d; lpcchNodeName
0x1401d0e98  mov     [rsp+0D0h+lpcchGroupName], rdi; lpcchGroupName
0x1401d0e9d  xor     edx, edx; lpszNodeName
0x1401d0e9f  call    cs:__imp_GetClusterResourceState
0x1401d0ea6  nop     dword ptr [rax+rax+00h]
0x1401d0eab  mov     [rbp+57h+arg_0], eax
0x1401d0eae  mov     eax, [r12]
0x1401d0eb2  test    eax, eax
0x1401d0eb4  jz      short loc_1401D0E74
0x1401d0eb6  mov     eax, [r12]
0x1401d0eba  test    eax, eax
0x1401d0ebc  jz      short loc_1401D0F12
0x1401d0ebe  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0ec5  test    rax, rax
0x1401d0ec8  jz      short loc_1401D0F09
0x1401d0eca  cmp     [rax+40h], edi
0x1401d0ecd  jz      short loc_1401D0F09
0x1401d0ecf  cmp     dword ptr [rax+38h], 3
0x1401d0ed3  jl      short loc_1401D0F09
0x1401d0ed5  lea     rax, aClus; "CLUS"
0x1401d0edc  mov     [rbp+57h+var_70], 89Eh
0x1401d0ee3  lea     r15, aClusterCluster_14; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0eea  mov     [rbp+57h+var_68], rax
0x1401d0eee  lea     rdx, aClusterAbortin; "[CLUSTER] Aborting offline because the "...
0x1401d0ef5  mov     [rbp+57h+var_78], r15
0x1401d0ef9  lea     rcx, [rbp+57h+var_78]
0x1401d0efd  mov     [rbp+57h+var_6C], 3
0x1401d0f04  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401d0f09  mov     rbx, [rbp+57h+arg_10]
0x1401d0f0d  jmp     loc_1401D0E05
0x1401d0f12  mov     ecx, [rbp+57h+arg_0]
0x1401d0f15  lea     eax, [rcx-3]
0x1401d0f18  cmp     eax, 1
0x1401d0f1b  jbe     short loc_1401D0F09
0x1401d0f1d  cmp     ecx, 0FFFFFFFFh
0x1401d0f20  jnz     short loc_1401D0F91
0x1401d0f22  call    cs:__imp_GetLastError
0x1401d0f29  nop     dword ptr [rax+rax+00h]
0x1401d0f2e  mov     ebx, eax
0x1401d0f30  call    cs:__imp_GetCurrentThreadId
0x1401d0f37  nop     dword ptr [rax+rax+00h]
0x1401d0f3c  mov     [rsp+0D0h+var_90], rdi
0x1401d0f41  mov     r9d, 1
0x1401d0f47  mov     [rsp+0D0h+var_98], eax
0x1401d0f4b  xor     r8d, r8d
0x1401d0f4e  mov     [rsp+0D0h+var_A0], 8AAh
0x1401d0f56  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d0f5d  mov     [rsp+0D0h+var_A8], r15
0x1401d0f62  mov     edx, ebx
0x1401d0f64  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d0f69  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d0f6e  mov     rbx, rax
0x1401d0f71  mov     [rbp+57h+arg_10], rax
0x1401d0f75  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0f7c  lea     r15, aClusterCluster_14; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0f83  test    rbx, rbx
0x1401d0f86  jz      loc_1401D0E05
0x1401d0f8c  jmp     loc_1401D0D68
0x1401d0f91  call    cs:__imp_GetCurrentThreadId
0x1401d0f98  nop     dword ptr [rax+rax+00h]
0x1401d0f9d  mov     [rsp+0D0h+var_90], rdi
0x1401d0fa2  mov     r9d, 3
0x1401d0fa8  mov     [rsp+0D0h+var_98], eax
0x1401d0fac  xor     r8d, r8d
0x1401d0faf  mov     [rsp+0D0h+var_A0], 8ADh
0x1401d0fb7  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d0fbe  mov     [rsp+0D0h+var_A8], r15
0x1401d0fc3  mov     edx, 2411h
0x1401d0fc8  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d0fcd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d0fd2  mov     rbx, rax
0x1401d0fd5  mov     [rbp+57h+arg_10], rax
0x1401d0fd9  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d0fe0  test    rax, rax
0x1401d0fe3  jz      short loc_1401D0F7C
0x1401d0fe5  lea     r15, aClusterCluster_14; "Cluster::ClusterUtil::BringResourceOffl"...
0x1401d0fec  cmp     [rax+40h], edi
0x1401d0fef  jz      short loc_1401D0F83
0x1401d0ff1  cmp     [rax+38h], esi
0x1401d0ff4  jl      short loc_1401D0F83
0x1401d0ff6  lea     rax, aClus; "CLUS"
0x1401d0ffd  mov     [rbp+57h+var_60], r15
0x1401d1001  lea     r9, [rbp+57h+arg_0]
0x1401d1005  mov     [rbp+57h+var_50], rax
0x1401d1009  mov     r8, r14
0x1401d100c  mov     [rbp+57h+var_58], 8AFh
0x1401d1013  lea     rdx, aClusterFailedT_33; "[CLUSTER] Failed to bring resource offl"...
0x1401d101a  mov     [rbp+57h+var_54], esi
0x1401d101d  lea     rcx, [rbp+57h+var_60]
  ... truncated ...
```
