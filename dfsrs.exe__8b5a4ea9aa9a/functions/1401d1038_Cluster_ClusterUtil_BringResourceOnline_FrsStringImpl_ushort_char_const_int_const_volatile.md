# Cluster::ClusterUtil::BringResourceOnline(FrsStringImpl<ushort,char> const &,int const volatile &)

- ea: `0x1401d1038`
- end: `0x1401d14ed`
- name: `?BringResourceOnline@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEDH@Z`
- size: `1205`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1401db450`

## callees

- `0x14000c910`
- `0x14001c31c`
- `0x1401b9494`
- `0x1401ce854`
- `0x1401d1038`
- `0x1401d1570`
- `0x1401d7bfc`

## import_xrefs

- `KERNEL32!Sleep` at `0x1401d124a`
- `KERNEL32!Sleep` at `0x1401d124a`
- `KERNEL32!GetLastError` at `0x1401d10f6`
- `KERNEL32!GetLastError` at `0x1401d12ed`
- `KERNEL32!GetLastError` at `0x1401d10f6`
- `KERNEL32!GetLastError` at `0x1401d12ed`
- `KERNEL32!GetCurrentThreadId` at `0x1401d1109`
- `KERNEL32!GetCurrentThreadId` at `0x1401d1191`
- `KERNEL32!GetCurrentThreadId` at `0x1401d1342`
- `KERNEL32!GetCurrentThreadId` at `0x1401d138f`
- `KERNEL32!GetCurrentThreadId` at `0x1401d14a1`
- `KERNEL32!GetCurrentThreadId` at `0x1401d1109`
- `KERNEL32!GetCurrentThreadId` at `0x1401d1191`
- `KERNEL32!GetCurrentThreadId` at `0x1401d1342`
- `KERNEL32!GetCurrentThreadId` at `0x1401d138f`
- `KERNEL32!GetCurrentThreadId` at `0x1401d14a1`
- `CLUSAPI!OnlineClusterResource` at `0x1401d1174`
- `CLUSAPI!OnlineClusterResource` at `0x1401d1174`
- `CLUSAPI!GetClusterResourceState` at `0x1401d10e0`
- `CLUSAPI!GetClusterResourceState` at `0x1401d1267`
- `CLUSAPI!GetClusterResourceState` at `0x1401d10e0`
- `CLUSAPI!GetClusterResourceState` at `0x1401d1267`

## string_xrefs

- `0x1401d1223`: `[CLUSTER] Resource is already online or online pending. resName:%? resState:%?`

## pseudocode

```c
__int64 __fastcall Cluster::ClusterUtil::BringResourceOnline(const unsigned __int16 *a1, _DWORD *a2)
{
  __int64 v2; // rbx
  struct FrsStatus *v5; // rdi
  struct _HRESOURCE *v6; // r12
  CLUSTER_RESOURCE_STATE v7; // ecx
  DWORD LastError; // r14d
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  __int32 v11; // ecx
  DWORD v12; // eax
  DWORD v13; // r14d
  DWORD v14; // eax
  __int64 v15; // rcx
  struct _HRESOURCE *i; // rcx
  DWORD v17; // edi
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  DWORD v22; // eax
  __int64 v23; // rcx
  const wchar_t *v25; // [rsp+50h] [rbp-20h] BYREF
  int v26; // [rsp+58h] [rbp-18h]
  int v27; // [rsp+5Ch] [rbp-14h]
  const wchar_t *v28; // [rsp+60h] [rbp-10h]
  CLUSTER_RESOURCE_STATE ClusterResourceState; // [rsp+B0h] [rbp+40h] BYREF
  HRESOURCE hResource; // [rsp+C0h] [rbp+50h] BYREF
  struct _HCLUSTER *v31; // [rsp+C8h] [rbp+58h] BYREF

  ClusterResourceState = ClusterResourceStateUnknown;
  v2 = 0;
  v31 = 0;
  hResource = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v25 = L"Cluster::ClusterUtil::BringResourceOnline";
    v26 = 1932;
    v27 = 4;
    v28 = L"CLUS";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
      &v25,
      L"[CLUSTER] Bringing resource online. resName:%?",
      a1);
  }
  v5 = Cluster::ClusterUtil::OpenClusterAndResource(
         a1,
         (const unsigned __int16 *)(*(_QWORD *)a1 + 18LL),
         &v31,
         &hResource);
  if ( v5 )
    goto LABEL_40;
  v6 = hResource;
  ClusterResourceState = GetClusterResourceState(hResource, 0, 0, 0, 0);
  v7 = ClusterResourceState;
  if ( ClusterResourceState == ClusterResourceStateUnknown )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v10,
                                 LastError,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                 "Cluster::ClusterUtil::BringResourceOnline",
                                 1959,
                                 CurrentThreadId,
                                 0);
      if ( v5 )
        goto LABEL_40;
    }
    v7 = ClusterResourceState;
  }
  v11 = v7 - 2;
  if ( !v11 || v11 == 127 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v25 = L"Cluster::ClusterUtil::BringResourceOnline";
      v26 = 1974;
      v28 = L"CLUS";
      v27 = 4;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,enum CLUSTER_RESOURCE_STATE>(
        &v25,
        L"[CLUSTER] Resource is already online or online pending. resName:%? resState:%?",
        a1,
        &ClusterResourceState);
    }
    goto LABEL_16;
  }
  v12 = OnlineClusterResource(v6);
  v13 = 0;
  if ( v12 != 997 )
    v13 = v12;
  if ( !v13
    || (v14 = GetCurrentThreadId(),
        (v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v15,
                                    v13,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                    "Cluster::ClusterUtil::BringResourceOnline",
                                    2002,
                                    v14,
                                    0)) == 0) )
  {
LABEL_16:
    for ( i = v6; ; i = hResource )
    {
      ClusterResourceState = GetClusterResourceState(i, 0, 0, 0, 0);
      if ( *a2 || ClusterResourceState != ClusterResourceOnlinePending )
        break;
      Sleep(0x1F4u);
    }
    if ( *a2 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v26 = 2040;
        v25 = L"Cluster::ClusterUtil::BringResourceOnline";
        v27 = 3;
        v28 = L"CLUS";
        dbgobj::DbgPrint<unsigned short>(&v25, L"[CLUSTER] Aborting online because the shutdown flag was set");
      }
    }
    else if ( ClusterResourceState != ClusterResourceOnline )
    {
      if ( ClusterResourceState == ClusterResourceStateUnknown )
      {
        v17 = GetLastError();
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v26 = 2054;
          v25 = L"Cluster::ClusterUtil::BringResourceOnline";
          v27 = 2;
          v28 = L"CLUS";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
            &v25,
            L"[CLUSTER] Failed to bring resource online. resName:%?",
            a1);
        }
        v18 = GetCurrentThreadId();
        v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v19,
                                   v17,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                   "Cluster::ClusterUtil::BringResourceOnline",
                                   2057,
                                   v18,
                                   0);
      }
      else
      {
        v20 = GetCurrentThreadId();
        v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v21,
                                   9233,
                                   0,
                                   3,
                                   "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                   "Cluster::ClusterUtil::BringResourceOnline",
                                   2064,
                                   v20,
                                   0);
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v26 = 2065;
          v25 = L"Cluster::ClusterUtil::BringResourceOnline";
          v27 = 2;
          v28 = L"CLUS";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,enum CLUSTER_RESOURCE_STATE>(
            &v25,
            L"[CLUSTER] Failed to bring resource online because resource  is in invalid state. resName:%? resState:%?",
            a1,
            &ClusterResourceState);
        }
      }
    }
    goto LABEL_44;
  }
LABEL_40:
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v25 = L"Cluster::ClusterUtil::BringResourceOnline";
    v26 = 2076;
    v27 = 2;
    v28 = L"CLUS";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
      &v25,
      L"[CLUSTER] Failed to issue resource online call. resName:%?",
      a1);
  }
LABEL_44:
  Cluster::ClusterUtil::CloseClusterAndResource(&v31, &hResource);
  if ( v5 )
  {
    v22 = GetCurrentThreadId();
    return FrsStatusList::PushNewError(
             v23,
             *((unsigned int *)v5 + 1),
             *((unsigned int *)v5 + 2),
             *(unsigned int *)v5,
             "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
             "Cluster::ClusterUtil::BringResourceOnline",
             2085,
             v22,
             v5);
  }
  return v2;
}

```

## disassembly

```asm
0x1401d1038  push    rbp
0x1401d103a  push    rbx
0x1401d103b  push    rsi
0x1401d103c  push    rdi
0x1401d103d  push    r12
0x1401d103f  push    r14
0x1401d1041  push    r15
0x1401d1043  mov     rbp, rsp
0x1401d1046  sub     rsp, 70h
0x1401d104a  or      [rbp+arg_0], 0FFFFFFFFh
0x1401d104e  lea     r14, aClusterCluster_27; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d1055  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d105c  lea     r12, aClus; "CLUS"
0x1401d1063  xor     ebx, ebx
0x1401d1065  mov     r15, rdx
0x1401d1068  mov     [rbp+arg_18], rbx
0x1401d106c  mov     rsi, rcx
0x1401d106f  mov     [rbp+hResource], rbx
0x1401d1073  test    rax, rax
0x1401d1076  jz      short loc_1401D10AC
0x1401d1078  cmp     [rax+40h], ebx
0x1401d107b  jz      short loc_1401D10AC
0x1401d107d  cmp     dword ptr [rax+38h], 4
0x1401d1081  jl      short loc_1401D10AC
0x1401d1083  mov     r8, rcx
0x1401d1086  mov     [rbp+var_20], r14
0x1401d108a  lea     rcx, [rbp+var_20]
0x1401d108e  mov     [rbp+var_18], 78Ch
0x1401d1095  lea     rdx, aClusterBringin; "[CLUSTER] Bringing resource online. res"...
0x1401d109c  mov     [rbp+var_14], 4
0x1401d10a3  mov     [rbp+var_10], r12
0x1401d10a7  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d10ac  mov     rdx, [rsi]
0x1401d10af  lea     r9, [rbp+hResource]; struct _HRESOURCE **
0x1401d10b3  add     rdx, 12h; unsigned __int16 *
0x1401d10b7  lea     r8, [rbp+arg_18]; struct _HCLUSTER **
0x1401d10bb  call    ?OpenClusterAndResource@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBG0AEAPEAU_HCLUSTER@@AEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::OpenClusterAndResource(ushort const *,ushort const *,_HCLUSTER * &,_HRESOURCE * &)
0x1401d10c0  mov     rdi, rax
0x1401d10c3  test    rax, rax
0x1401d10c6  jnz     loc_1401D1441
0x1401d10cc  mov     r12, [rbp+hResource]
0x1401d10d0  xor     r9d, r9d; lpszGroupName
0x1401d10d3  mov     rcx, r12; hResource
0x1401d10d6  mov     [rsp+70h+lpcchGroupName], rbx; lpcchGroupName
0x1401d10db  xor     r8d, r8d; lpcchNodeName
0x1401d10de  xor     edx, edx; lpszNodeName
0x1401d10e0  call    cs:__imp_GetClusterResourceState
0x1401d10e7  nop     dword ptr [rax+rax+00h]
0x1401d10ec  mov     [rbp+arg_0], eax
0x1401d10ef  mov     ecx, eax
0x1401d10f1  cmp     eax, 0FFFFFFFFh
0x1401d10f4  jnz     short loc_1401D1163
0x1401d10f6  call    cs:__imp_GetLastError
0x1401d10fd  nop     dword ptr [rax+rax+00h]
0x1401d1102  mov     r14d, eax
0x1401d1105  test    eax, eax
0x1401d1107  jz      short loc_1401D1159
0x1401d1109  call    cs:__imp_GetCurrentThreadId
0x1401d1110  nop     dword ptr [rax+rax+00h]
0x1401d1115  mov     [rsp+70h+var_30], rbx
0x1401d111a  lea     r9d, [rdi+1]
0x1401d111e  mov     [rsp+70h+var_38], eax
0x1401d1122  xor     r8d, r8d
0x1401d1125  lea     rax, aClusterCluster_7; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d112c  mov     [rsp+70h+var_40], 7A7h
0x1401d1134  mov     [rsp+70h+var_48], rax
0x1401d1139  mov     edx, r14d
0x1401d113c  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d1143  mov     [rsp+70h+lpcchGroupName], rax
0x1401d1148  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d114d  mov     rdi, rax
0x1401d1150  test    rax, rax
0x1401d1153  jnz     loc_1401D1433
0x1401d1159  mov     ecx, [rbp+arg_0]
0x1401d115c  lea     r14, aClusterCluster_27; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d1163  sub     ecx, 2
0x1401d1166  jz      loc_1401D11EF
0x1401d116c  cmp     ecx, 7Fh
0x1401d116f  jz      short loc_1401D11EF
0x1401d1171  mov     rcx, r12; hResource
0x1401d1174  call    cs:__imp_OnlineClusterResource
0x1401d117b  nop     dword ptr [rax+rax+00h]
0x1401d1180  cmp     eax, 3E5h
0x1401d1185  mov     r14d, ebx
0x1401d1188  cmovnz  r14d, eax
0x1401d118c  test    r14d, r14d
0x1401d118f  jz      short loc_1401D11E3
0x1401d1191  call    cs:__imp_GetCurrentThreadId
0x1401d1198  nop     dword ptr [rax+rax+00h]
0x1401d119d  mov     [rsp+70h+var_30], rbx
0x1401d11a2  mov     r9d, 1
0x1401d11a8  mov     [rsp+70h+var_38], eax
0x1401d11ac  xor     r8d, r8d
0x1401d11af  lea     rax, aClusterCluster_7; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d11b6  mov     [rsp+70h+var_40], 7D2h
0x1401d11be  mov     [rsp+70h+var_48], rax
0x1401d11c3  mov     edx, r14d
0x1401d11c6  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d11cd  mov     [rsp+70h+lpcchGroupName], rax
0x1401d11d2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d11d7  mov     rdi, rax
0x1401d11da  test    rax, rax
0x1401d11dd  jnz     loc_1401D1433
0x1401d11e3  lea     r14, aClus; "CLUS"
0x1401d11ea  mov     rcx, r12
0x1401d11ed  jmp     short loc_1401D125A
0x1401d11ef  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d11f6  test    rax, rax
0x1401d11f9  jz      short loc_1401D11E3
0x1401d11fb  cmp     [rax+40h], ebx
0x1401d11fe  jz      short loc_1401D11E3
0x1401d1200  cmp     dword ptr [rax+38h], 4
0x1401d1204  jl      short loc_1401D11E3
0x1401d1206  mov     [rbp+var_20], r14
0x1401d120a  lea     r9, [rbp+arg_0]
0x1401d120e  lea     r14, aClus; "CLUS"
0x1401d1215  mov     [rbp+var_18], 7B6h
0x1401d121c  mov     r8, rsi
0x1401d121f  mov     [rbp+var_10], r14
0x1401d1223  lea     rdx, aClusterResourc_5; "[CLUSTER] Resource is already online or"...
0x1401d122a  mov     [rbp+var_14], 4
0x1401d1231  lea     rcx, [rbp+var_20]
0x1401d1235  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@W4CLUSTER_RESOURCE_STATE@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBW4CLUSTER_RESOURCE_STATE@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,CLUSTER_RESOURCE_STATE>(ushort const *,FrsStringImpl<ushort,char> const &,CLUSTER_RESOURCE_STATE const &)
0x1401d123a  jmp     short loc_1401D11EA
0x1401d123c  cmp     [rbp+arg_0], 81h
0x1401d1243  jnz     short loc_1401D127D
0x1401d1245  mov     ecx, 1F4h; dwMilliseconds
0x1401d124a  call    cs:__imp_Sleep
0x1401d1251  nop     dword ptr [rax+rax+00h]
0x1401d1256  mov     rcx, [rbp+hResource]; hResource
0x1401d125a  xor     r9d, r9d; lpszGroupName
0x1401d125d  mov     [rsp+70h+lpcchGroupName], rbx; lpcchGroupName
0x1401d1262  xor     r8d, r8d; lpcchNodeName
0x1401d1265  xor     edx, edx; lpszNodeName
0x1401d1267  call    cs:__imp_GetClusterResourceState
0x1401d126e  nop     dword ptr [rax+rax+00h]
0x1401d1273  mov     [rbp+arg_0], eax
0x1401d1276  mov     eax, [r15]
0x1401d1279  test    eax, eax
0x1401d127b  jz      short loc_1401D123C
0x1401d127d  mov     eax, [r15]
0x1401d1280  test    eax, eax
0x1401d1282  jz      short loc_1401D12D9
0x1401d1284  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d128b  test    rax, rax
0x1401d128e  jz      loc_1401D1481
0x1401d1294  cmp     [rax+40h], ebx
0x1401d1297  jz      loc_1401D1481
0x1401d129d  cmp     dword ptr [rax+38h], 3
0x1401d12a1  jl      loc_1401D1481
0x1401d12a7  lea     rax, aClusterCluster_27; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d12ae  mov     [rbp+var_18], 7F8h
0x1401d12b5  lea     rdx, aClusterAbortin_0; "[CLUSTER] Aborting online because the s"...
0x1401d12bc  mov     [rbp+var_20], rax
0x1401d12c0  lea     rcx, [rbp+var_20]
0x1401d12c4  mov     [rbp+var_14], 3
0x1401d12cb  mov     [rbp+var_10], r14
0x1401d12cf  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401d12d4  jmp     loc_1401D1481
0x1401d12d9  cmp     [rbp+arg_0], 2
0x1401d12dd  jz      loc_1401D1481
0x1401d12e3  cmp     [rbp+arg_0], 0FFFFFFFFh
0x1401d12e7  jnz     loc_1401D138F
0x1401d12ed  call    cs:__imp_GetLastError
0x1401d12f4  nop     dword ptr [rax+rax+00h]
0x1401d12f9  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d1300  mov     edi, eax
0x1401d1302  test    rcx, rcx
0x1401d1305  jz      short loc_1401D1342
0x1401d1307  cmp     [rcx+40h], ebx
0x1401d130a  jz      short loc_1401D1342
0x1401d130c  cmp     dword ptr [rcx+38h], 2
0x1401d1310  jl      short loc_1401D1342
0x1401d1312  lea     rax, aClusterCluster_27; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d1319  mov     [rbp+var_18], 806h
0x1401d1320  mov     r8, rsi
0x1401d1323  mov     [rbp+var_20], rax
0x1401d1327  lea     rdx, aClusterFailedT_19; "[CLUSTER] Failed to bring resource onli"...
0x1401d132e  mov     [rbp+var_14], 2
0x1401d1335  lea     rcx, [rbp+var_20]
0x1401d1339  mov     [rbp+var_10], r14
0x1401d133d  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d1342  call    cs:__imp_GetCurrentThreadId
0x1401d1349  nop     dword ptr [rax+rax+00h]
0x1401d134e  mov     [rsp+70h+var_30], rbx
0x1401d1353  lea     rsi, aClusterCluster_7; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d135a  mov     [rsp+70h+var_38], eax
0x1401d135e  lea     r14, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d1365  mov     [rsp+70h+var_40], 809h
0x1401d136d  mov     r9d, 1
0x1401d1373  mov     [rsp+70h+var_48], rsi
0x1401d1378  xor     r8d, r8d
0x1401d137b  mov     edx, edi
0x1401d137d  mov     [rsp+70h+lpcchGroupName], r14
0x1401d1382  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d1387  mov     rdi, rax
0x1401d138a  jmp     loc_1401D148F
0x1401d138f  call    cs:__imp_GetCurrentThreadId
0x1401d1396  nop     dword ptr [rax+rax+00h]
0x1401d139b  mov     [rsp+70h+var_30], rbx
0x1401d13a0  mov     r9d, 3
0x1401d13a6  mov     [rsp+70h+var_38], eax
0x1401d13aa  xor     r8d, r8d
0x1401d13ad  lea     rax, aClusterCluster_7; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d13b4  mov     [rsp+70h+var_40], 810h
0x1401d13bc  mov     [rsp+70h+var_48], rax
0x1401d13c1  mov     edx, 2411h
0x1401d13c6  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d13cd  mov     [rsp+70h+lpcchGroupName], rax
0x1401d13d2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d13d7  mov     rdi, rax
0x1401d13da  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d13e1  test    rax, rax
0x1401d13e4  jz      loc_1401D1481
0x1401d13ea  cmp     [rax+40h], ebx
0x1401d13ed  jz      loc_1401D1481
0x1401d13f3  cmp     dword ptr [rax+38h], 2
0x1401d13f7  jl      loc_1401D1481
0x1401d13fd  lea     rax, aClusterCluster_27; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d1404  mov     [rbp+var_18], 811h
0x1401d140b  lea     r9, [rbp+arg_0]
0x1401d140f  mov     [rbp+var_20], rax
0x1401d1413  mov     r8, rsi
0x1401d1416  mov     [rbp+var_14], 2
0x1401d141d  lea     rdx, aClusterFailedT_15; "[CLUSTER] Failed to bring resource onli"...
0x1401d1424  mov     [rbp+var_10], r14
0x1401d1428  lea     rcx, [rbp+var_20]
0x1401d142c  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@W4CLUSTER_RESOURCE_STATE@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBW4CLUSTER_RESOURCE_STATE@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,CLUSTER_RESOURCE_STATE>(ushort const *,FrsStringImpl<ushort,char> const &,CLUSTER_RESOURCE_STATE const &)
0x1401d1431  jmp     short loc_1401D1481
0x1401d1433  lea     r12, aClus; "CLUS"
0x1401d143a  lea     r14, aClusterCluster_27; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d1441  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d1448  test    rax, rax
0x1401d144b  jz      short loc_1401D1481
0x1401d144d  cmp     [rax+40h], ebx
0x1401d1450  jz      short loc_1401D1481
0x1401d1452  cmp     dword ptr [rax+38h], 2
0x1401d1456  jl      short loc_1401D1481
0x1401d1458  mov     r8, rsi
0x1401d145b  mov     [rbp+var_20], r14
0x1401d145f  lea     rdx, aClusterFailedT_6; "[CLUSTER] Failed to issue resource onli"...
0x1401d1466  mov     [rbp+var_18], 81Ch
0x1401d146d  lea     rcx, [rbp+var_20]
0x1401d1471  mov     [rbp+var_14], 2
0x1401d1478  mov     [rbp+var_10], r12
0x1401d147c  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d1481  lea     rsi, aClusterCluster_7; "Cluster::ClusterUtil::BringResourceOnli"...
0x1401d1488  lea     r14, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d148f  lea     rdx, [rbp+hResource]; struct _HRESOURCE **
0x1401d1493  lea     rcx, [rbp+arg_18]; struct _HCLUSTER **
0x1401d1497  call    ?CloseClusterAndResource@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@AEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::CloseClusterAndResource(_HCLUSTER * &,_HRESOURCE * &)
0x1401d149c  test    rdi, rdi
0x1401d149f  jz      short loc_1401D14DA
0x1401d14a1  call    cs:__imp_GetCurrentThreadId
0x1401d14a8  nop     dword ptr [rax+rax+00h]
0x1401d14ad  mov     r9d, [rdi]
0x1401d14b0  mov     r8d, [rdi+8]
0x1401d14b4  mov     edx, [rdi+4]
0x1401d14b7  mov     [rsp+70h+var_30], rdi
0x1401d14bc  mov     [rsp+70h+var_38], eax
0x1401d14c0  mov     [rsp+70h+var_40], 825h
0x1401d14c8  mov     [rsp+70h+var_48], rsi
0x1401d14cd  mov     [rsp+70h+lpcchGroupName], r14
0x1401d14d2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d14d7  mov     rbx, rax
0x1401d14da  mov     rax, rbx
0x1401d14dd  add     rsp, 70h
0x1401d14e1  pop     r15
0x1401d14e3  pop     r14
0x1401d14e5  pop     r12
0x1401d14e7  pop     rdi
0x1401d14e8  pop     rsi
0x1401d14e9  pop     rbx
0x1401d14ea  pop     rbp
0x1401d14eb  retn
```
