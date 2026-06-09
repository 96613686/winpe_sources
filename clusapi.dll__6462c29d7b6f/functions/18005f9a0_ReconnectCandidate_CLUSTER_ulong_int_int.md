# ReconnectCandidate(_CLUSTER *,ulong,int,int *)

- ea: `0x18005f9a0`
- end: `0x18005fe7f`
- name: `?ReconnectCandidate@@YAKPEAU_CLUSTER@@KHPEAH@Z`
- size: `1247`
- prototype: `unsigned int __fastcall(struct _CLUSTER *, unsigned int, int, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x18005ffe4`

## callees

- `0x180022508`
- `0x180023e60`
- `0x18003a45c`
- `0x18005f9a0`
- `0x18005fe88`
- `0x18006048c`
- `0x180060604`
- `0x180060774`
- `0x1800608e4`
- `0x180060a54`
- `0x180060e68`
- `0x180060fe0`
- `0x18006f910`
- `0x180090b7c`
- `0x180090c78`
- `0x180090ca4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fb0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fb16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fb0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fb16`

## string_xrefs

- `0x18005fbf7`: `%ws clusapi is not ready`
- `0x18005fc1e`: `Node %ws state is Up, reopening handles`
- `0x18005fc2d`: `ApiGetClusterName succeeded on node %ws, reopening handles`
- `0x18005fcaa`: `ApiOpenCluster failed %d`

## pseudocode

```c
__int64 __fastcall ReconnectCandidate(struct _CLUSTER *a1, unsigned int a2, int a3, int *a4)
{
  __int64 v4; // rax
  __int64 v9; // r15
  unsigned int v10; // eax
  unsigned int ClusterMajorVersion; // eax
  __int64 v13; // rcx
  unsigned int ClusterName; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  struct _CLUSTER *v21; // rdi
  struct _CKEY *v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int i; // ecx
  __int64 v31; // rdx
  __int64 v32; // [rsp+28h] [rbp-38h]
  __int64 v33; // [rsp+28h] [rbp-38h]
  __int64 v34; // [rsp+30h] [rbp-30h]
  __int64 v35; // [rsp+40h] [rbp-20h] BYREF
  __int64 v36; // [rsp+48h] [rbp-18h] BYREF
  void *v37; // [rsp+50h] [rbp-10h] BYREF
  void *v38; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v39; // [rsp+A8h] [rbp+48h] BYREF

  v4 = *((_QWORD *)a1 + 35);
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v39 = 0;
  v9 = 2LL * a2;
  v38 = 0;
  TraceMsg(4u, 7u, (__int64)L"ReconnectCandidate", 1271, L"Binding to %ws", *(_QWORD *)(v4 + 16LL * a2 + 8));
  v10 = ConnectRemoteClusterParallel(
          *(const wchar_t **)(*((_QWORD *)a1 + 35) + 8 * v9 + 8),
          *((_DWORD *)a1 + 54),
          &v38,
          a1);
  v39 = v10;
  if ( v10 )
  {
    LODWORD(v32) = v10;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1277, L"ConnectRemoteClusterParallel failed %d", v32);
    return v39;
  }
  v37 = (void *)*((_QWORD *)a1 + 5);
  *((_QWORD *)a1 + 5) = v38;
  FreeRpcBindingOrContext(a1, &v37, 1);
  if ( *((_WORD *)a1 + 162) > 5u )
  {
    ClusterMajorVersion = GetClusterMajorVersion(
                            a1,
                            (unsigned __int16 *const)a1 + 162,
                            (unsigned __int16 *const)a1 + 163);
    v39 = ClusterMajorVersion;
    if ( ClusterMajorVersion )
    {
      LODWORD(v32) = ClusterMajorVersion;
      TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1298, L"Getting the cluster os version failed: %d", v32);
      return v39;
    }
  }
  v13 = *((_QWORD *)a1 + 5);
  v36 = 0;
  v35 = 0;
  ClusterName = ApiGetClusterName(v13, &v35, &v36);
  v39 = ClusterName;
  if ( ClusterName )
  {
    LODWORD(v32) = ClusterName;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1311, L"ApiGetClusterName failed: %d", v32);
    return v39;
  }
  LocalFree(*((HLOCAL *)a1 + 2));
  LocalFree(*((HLOCAL *)a1 + 3));
  v15 = v35;
  v16 = v36;
  *((_QWORD *)a1 + 2) = v35;
  *((_QWORD *)a1 + 3) = v16;
  if ( v15 && v16 )
    TraceMsg(4u, 7u, (__int64)L"ReconnectCandidate", 1322, L"Reconnected to ClusterName %ws, nodeName %ws", v15, v16);
  if ( a3 )
  {
    TraceMsg(
      4u,
      7u,
      (__int64)L"ReconnectCandidate",
      1351,
      L"ApiGetClusterName succeeded on node %ws, reopening handles",
      *((_QWORD *)a1 + 3));
  }
  else
  {
    TraceMsg(4u, 7u, (__int64)L"ReconnectCandidate", 1331, L"ApiGetClusterName succeeded, checking node state");
    v17 = ReconnectCheckCandidateNodeState(a1, a4);
    v39 = v17;
    if ( v17 )
    {
      LODWORD(v34) = v17;
      TraceMsg(
        2u,
        7u,
        (__int64)L"ReconnectCandidate",
        1336,
        L"Failed to determine node state of reconnect candidate %ws, status %d",
        *((_QWORD *)a1 + 3),
        v34);
      return v39;
    }
    if ( *a4 )
    {
      TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1340, L"%ws clusapi is not ready", *((_QWORD *)a1 + 3));
      return 70;
    }
    TraceMsg(
      4u,
      7u,
      (__int64)L"ReconnectCandidate",
      1349,
      L"Node %ws state is Up, reopening handles",
      *((_QWORD *)a1 + 3));
  }
  if ( *((_QWORD *)a1 + 6) )
    FreeRpcBindingOrContext(a1, (void **)a1 + 6, 0);
  v18 = *((_QWORD *)a1 + 5);
  if ( *((_WORD *)a1 + 162) <= 5u )
  {
    v20 = ApiOpenCluster(v18, &v39);
  }
  else
  {
    v19 = *((unsigned int *)a1 + 80);
    LODWORD(v38) = 0;
    v20 = ApiOpenClusterEx(v18, v19, &v38, &v39);
  }
  *((_QWORD *)a1 + 6) = v20;
  if ( !v20 )
  {
    LODWORD(v33) = v39;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1366, L"ApiOpenCluster failed %d", v33);
    return v39;
  }
  v21 = (struct _CLUSTER *)*((_QWORD *)a1 + 7);
  while ( v21 != (struct _CLUSTER *)((char *)a1 + 56) )
  {
    v22 = v21;
    v21 = *(struct _CLUSTER **)v21;
    v23 = ReopenKeyWorker(v22);
    if ( v23 )
    {
      v39 = v23;
      LODWORD(v33) = v23;
      TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1376, L"ReconnectKeys failed %d", v33);
      return v39;
    }
  }
  v39 = 0;
  v24 = ReconnectResources(a1);
  v39 = v24;
  if ( v24 )
  {
    LODWORD(v33) = v24;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1382, L"ReconnectResources failed %d", v33);
    return v39;
  }
  v25 = ReconnectGroups(a1);
  v39 = v25;
  if ( v25 )
  {
    LODWORD(v33) = v25;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1388, L"ReconnectGroups failed %d", v33);
    return v39;
  }
  v26 = ReconnectNodes(a1);
  v39 = v26;
  if ( v26 )
  {
    LODWORD(v33) = v26;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1394, L"ReconnectNodes failed %d", v33);
    return v39;
  }
  v27 = ReconnectNetworks(a1);
  v39 = v27;
  if ( v27 )
  {
    LODWORD(v33) = v27;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1400, L"ReconnectNetworks failed %d", v33);
    return v39;
  }
  v28 = ReconnectNetInterfaces(a1);
  v39 = v28;
  if ( v28 )
  {
    LODWORD(v33) = v28;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1406, L"ReconnectNetInterfaces failed %d", v33);
    return v39;
  }
  v29 = ReconnectNotifySessions(a1);
  v39 = v29;
  if ( v29 )
  {
    LODWORD(v33) = v29;
    TraceMsg(2u, 7u, (__int64)L"ReconnectCandidate", 1416, L"ReconnectNotifySessions failed %d", v33);
    return v39;
  }
  LODWORD(v33) = ++*((_DWORD *)a1 + 68);
  TraceMsg(4u, 7u, (__int64)L"ReconnectCandidate", 1424, L"New reconnection generation #: %d", v33);
  for ( i = 0; i < *((_DWORD *)a1 + 69); ++i )
  {
    v31 = *((_QWORD *)a1 + 35);
    if ( i == a2 )
      *(_DWORD *)(v31 + 8 * v9 + 4) = 1;
    else
      *(_DWORD *)(v31 + 16LL * i + 4) = 0;
  }
  TraceMsg(
    4u,
    0,
    (__int64)L"ReconnectCandidate",
    1438,
    L"Successfully reconnected to %ws",
    *(_QWORD *)(*((_QWORD *)a1 + 35) + 8 * v9 + 8));
  return 0;
}

```

## disassembly

```asm
0x18005f9a0  mov     [rsp-38h+arg_10], rbx
0x18005f9a5  push    rbp
0x18005f9a6  push    rsi
0x18005f9a7  push    rdi
0x18005f9a8  push    r12
0x18005f9aa  push    r13
0x18005f9ac  push    r14
0x18005f9ae  push    r15
0x18005f9b0  mov     rbp, rsp
0x18005f9b3  sub     rsp, 60h
0x18005f9b7  mov     rax, [rcx+118h]
0x18005f9be  xor     r13d, r13d
0x18005f9c1  mov     r15d, edx
0x18005f9c4  mov     rbx, rcx
0x18005f9c7  mov     [rbp+var_20], r13
0x18005f9cb  mov     rdi, r9
0x18005f9ce  mov     [rbp+var_18], r13
0x18005f9d2  mov     r14d, r8d
0x18005f9d5  mov     [rbp+var_10], r13
0x18005f9d9  lea     esi, [r13+7]
0x18005f9dd  mov     [rbp+arg_8], r13d
0x18005f9e1  lea     r8, aReconnectcandi; "ReconnectCandidate"
0x18005f9e8  mov     r12d, edx
0x18005f9eb  add     r15, r15
0x18005f9ee  mov     r9d, 4F7h
0x18005f9f4  mov     [rbp+arg_0], r13
0x18005f9f8  mov     edx, esi
0x18005f9fa  mov     rcx, [rax+r15*8+8]
0x18005f9ff  lea     rax, aBindingToWs; "Binding to %ws"
0x18005fa06  mov     [rsp+60h+var_38], rcx
0x18005fa0b  lea     ecx, [rsi-3]
0x18005fa0e  mov     [rsp+60h+var_40], rax
0x18005fa13  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fa18  mov     rcx, [rbx+118h]
0x18005fa1f  lea     r8, [rbp+arg_0]; void **
0x18005fa23  mov     edx, [rbx+0D8h]; unsigned int
0x18005fa29  mov     r9, rbx; struct _CLUSTER *
0x18005fa2c  mov     rcx, [rcx+r15*8+8]; wchar_t *
0x18005fa31  call    ?ConnectRemoteClusterParallel@@YAKPEB_WKAEAPEAXPEAU_CLUSTER@@@Z; ConnectRemoteClusterParallel(wchar_t const *,ulong,void * &,_CLUSTER *)
0x18005fa36  mov     [rbp+arg_8], eax
0x18005fa39  test    eax, eax
0x18005fa3b  jz      short loc_18005FA6E
0x18005fa3d  mov     dword ptr [rsp+60h+var_38], eax
0x18005fa41  lea     r8, aReconnectcandi; "ReconnectCandidate"
0x18005fa48  lea     rax, aConnectremotec_2; "ConnectRemoteClusterParallel failed %d"
0x18005fa4f  mov     r9d, 4FDh
0x18005fa55  mov     edx, esi
0x18005fa57  mov     ecx, 2
0x18005fa5c  mov     [rsp+60h+var_40], rax
0x18005fa61  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fa66  mov     eax, [rbp+arg_8]
0x18005fa69  jmp     loc_18005FE67
0x18005fa6e  mov     rax, [rbx+28h]
0x18005fa72  lea     rdx, [rbp+var_10]; void **
0x18005fa76  mov     [rbp+var_10], rax
0x18005fa7a  mov     r8d, 1; int
0x18005fa80  mov     rax, [rbp+arg_0]
0x18005fa84  mov     rcx, rbx; struct _CLUSTER *
0x18005fa87  mov     [rbx+28h], rax
0x18005fa8b  call    ?FreeRpcBindingOrContext@@YAJPEAU_CLUSTER@@PEAPEAXH@Z; FreeRpcBindingOrContext(_CLUSTER *,void * *,int)
0x18005fa90  lea     rsi, [rbx+144h]
0x18005fa97  cmp     word ptr [rsi], 5
0x18005fa9b  jbe     short loc_18005FAD5
0x18005fa9d  lea     r8, [rbx+146h]; unsigned __int16 *
0x18005faa4  mov     rdx, rsi; unsigned __int16 *
0x18005faa7  mov     rcx, rbx; struct _HCLUSTER *
0x18005faaa  call    ?GetClusterMajorVersion@@YAKPEAU_HCLUSTER@@QEAG1@Z; GetClusterMajorVersion(_HCLUSTER *,ushort * const,ushort * const)
0x18005faaf  mov     [rbp+arg_8], eax
0x18005fab2  test    eax, eax
0x18005fab4  jz      short loc_18005FAD5
0x18005fab6  mov     dword ptr [rsp+60h+var_38], eax
0x18005faba  mov     r9d, 512h
0x18005fac0  lea     rax, aGettingTheClus; "Getting the cluster os version failed: "...
0x18005fac7  lea     r8, aReconnectcandi; "ReconnectCandidate"
0x18005face  mov     edx, 7
0x18005fad3  jmp     short loc_18005FA57
0x18005fad5  mov     rcx, [rbx+28h]
0x18005fad9  lea     r8, [rbp+var_18]
0x18005fadd  lea     rdx, [rbp+var_20]
0x18005fae1  mov     [rbp+var_18], r13
0x18005fae5  mov     [rbp+var_20], r13
0x18005fae9  call    ApiGetClusterName
0x18005faee  mov     [rbp+arg_8], eax
0x18005faf1  test    eax, eax
0x18005faf3  jz      short loc_18005FB08
0x18005faf5  mov     dword ptr [rsp+60h+var_38], eax
0x18005faf9  mov     r9d, 51Fh
0x18005faff  lea     rax, aApigetclustern_1; "ApiGetClusterName failed: %d"
0x18005fb06  jmp     short loc_18005FAC7
0x18005fb08  mov     rcx, [rbx+10h]; hMem
0x18005fb0c  call    cs:__imp_LocalFree
0x18005fb12  mov     rcx, [rbx+18h]; hMem
0x18005fb16  call    cs:__imp_LocalFree
0x18005fb1c  mov     rcx, [rbp+var_20]
0x18005fb20  mov     rax, [rbp+var_18]
0x18005fb24  mov     [rbx+10h], rcx
0x18005fb28  mov     [rbx+18h], rax
0x18005fb2c  test    rcx, rcx
0x18005fb2f  jz      short loc_18005FB66
0x18005fb31  test    rax, rax
0x18005fb34  jz      short loc_18005FB66
0x18005fb36  mov     [rsp+60h+var_30], rax
0x18005fb3b  lea     r8, aReconnectcandi; "ReconnectCandidate"
0x18005fb42  mov     [rsp+60h+var_38], rcx
0x18005fb47  lea     rax, aReconnectedToC; "Reconnected to ClusterName %ws, nodeNam"...
0x18005fb4e  mov     edx, 7
0x18005fb53  mov     [rsp+60h+var_40], rax
0x18005fb58  mov     r9d, 52Ah
0x18005fb5e  lea     ecx, [rdx-3]
0x18005fb61  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fb66  test    r14d, r14d
0x18005fb69  lea     r14, aReconnectcandi; "ReconnectCandidate"
0x18005fb70  jnz     loc_18005FC27
0x18005fb76  mov     edx, 7
0x18005fb7b  lea     rax, aApigetclustern_0; "ApiGetClusterName succeeded, checking n"...
0x18005fb82  mov     r9d, 533h
0x18005fb88  mov     [rsp+60h+var_40], rax
0x18005fb8d  mov     r8, r14
0x18005fb90  lea     ecx, [rdx-3]
0x18005fb93  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fb98  mov     rdx, rdi; int *
0x18005fb9b  mov     rcx, rbx; struct _CLUSTER *
0x18005fb9e  call    ?ReconnectCheckCandidateNodeState@@YAKPEAU_CLUSTER@@PEAH@Z; ReconnectCheckCandidateNodeState(_CLUSTER *,int *)
0x18005fba3  mov     [rbp+arg_8], eax
0x18005fba6  test    eax, eax
0x18005fba8  jz      short loc_18005FBDE
0x18005fbaa  mov     dword ptr [rsp+60h+var_30], eax
0x18005fbae  mov     edx, 7
0x18005fbb3  mov     rax, [rbx+18h]
0x18005fbb7  mov     r9d, 538h
0x18005fbbd  mov     [rsp+60h+var_38], rax
0x18005fbc2  mov     r8, r14
0x18005fbc5  lea     rax, aFailedToDeterm_0; "Failed to determine node state of recon"...
0x18005fbcc  lea     ecx, [rdx-5]
0x18005fbcf  mov     [rsp+60h+var_40], rax
0x18005fbd4  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fbd9  jmp     loc_18005FA66
0x18005fbde  cmp     [rdi], r13d
0x18005fbe1  jz      short loc_18005FC18
0x18005fbe3  mov     rax, [rbx+18h]
0x18005fbe7  mov     edx, 7
0x18005fbec  mov     [rsp+60h+var_38], rax
0x18005fbf1  mov     r9d, 53Ch
0x18005fbf7  lea     rax, aWsClusapiIsNot; "%ws clusapi is not ready"
0x18005fbfe  mov     r8, r14
0x18005fc01  mov     [rsp+60h+var_40], rax
0x18005fc06  lea     ecx, [rdx-5]
0x18005fc09  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fc0e  mov     eax, 46h ; 'F'
0x18005fc13  jmp     loc_18005FE67
0x18005fc18  mov     r9d, 545h
0x18005fc1e  lea     rcx, aNodeWsStateIsU; "Node %ws state is Up, reopening handles"
0x18005fc25  jmp     short loc_18005FC34
0x18005fc27  mov     r9d, 547h
0x18005fc2d  lea     rcx, aApigetclustern_2; "ApiGetClusterName succeeded on node %ws"...
0x18005fc34  mov     rax, [rbx+18h]
0x18005fc38  mov     edx, 7
0x18005fc3d  mov     [rsp+60h+var_38], rax
0x18005fc42  mov     r8, r14
0x18005fc45  mov     [rsp+60h+var_40], rcx
0x18005fc4a  lea     ecx, [rdx-3]
0x18005fc4d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fc52  lea     rdi, [rbx+30h]
0x18005fc56  cmp     [rdi], r13
0x18005fc59  jz      short loc_18005FC69
0x18005fc5b  xor     r8d, r8d; int
0x18005fc5e  mov     rdx, rdi; void **
0x18005fc61  mov     rcx, rbx; struct _CLUSTER *
0x18005fc64  call    ?FreeRpcBindingOrContext@@YAJPEAU_CLUSTER@@PEAPEAXH@Z; FreeRpcBindingOrContext(_CLUSTER *,void * *,int)
0x18005fc69  cmp     word ptr [rsi], 5
0x18005fc6d  mov     rcx, [rbx+28h]
0x18005fc71  jbe     short loc_18005FC8C
0x18005fc73  mov     edx, [rbx+140h]
0x18005fc79  lea     r9, [rbp+arg_8]
0x18005fc7d  lea     r8, [rbp+arg_0]
0x18005fc81  mov     dword ptr [rbp+arg_0], r13d
0x18005fc85  call    ApiOpenClusterEx
0x18005fc8a  jmp     short loc_18005FC95
0x18005fc8c  lea     rdx, [rbp+arg_8]
0x18005fc90  call    ApiOpenCluster
0x18005fc95  mov     [rdi], rax
0x18005fc98  test    rax, rax
0x18005fc9b  jnz     short loc_18005FCB9
0x18005fc9d  mov     eax, [rbp+arg_8]
0x18005fca0  mov     r9d, 556h
0x18005fca6  mov     dword ptr [rsp+60h+var_38], eax
0x18005fcaa  lea     rax, aApiopencluster_1; "ApiOpenCluster failed %d"
0x18005fcb1  mov     r8, r14
0x18005fcb4  jmp     loc_18005FACE
0x18005fcb9  lea     rsi, [rbx+38h]
0x18005fcbd  mov     rdi, [rsi]
0x18005fcc0  cmp     rdi, rsi
0x18005fcc3  jz      short loc_18005FCEA
0x18005fcc5  mov     rcx, rdi; struct _CKEY *
0x18005fcc8  mov     rdi, [rdi]
0x18005fccb  call    ?ReopenKeyWorker@@YAKPEAU_CKEY@@@Z; ReopenKeyWorker(_CKEY *)
0x18005fcd0  test    eax, eax
0x18005fcd2  jz      short loc_18005FCC0
0x18005fcd4  mov     [rbp+arg_8], eax
0x18005fcd7  mov     r9d, 560h
0x18005fcdd  mov     dword ptr [rsp+60h+var_38], eax
0x18005fce1  lea     rax, aReconnectkeysF; "ReconnectKeys failed %d"
0x18005fce8  jmp     short loc_18005FCB1
0x18005fcea  mov     rcx, rbx; struct _CLUSTER *
0x18005fced  mov     [rbp+arg_8], r13d
0x18005fcf1  call    ?ReconnectResources@@YAKPEAU_CLUSTER@@@Z; ReconnectResources(_CLUSTER *)
0x18005fcf6  mov     [rbp+arg_8], eax
0x18005fcf9  test    eax, eax
0x18005fcfb  jz      short loc_18005FD10
0x18005fcfd  mov     dword ptr [rsp+60h+var_38], eax
0x18005fd01  mov     r9d, 566h
0x18005fd07  lea     rax, aReconnectresou_0; "ReconnectResources failed %d"
0x18005fd0e  jmp     short loc_18005FCB1
0x18005fd10  mov     rcx, rbx; struct _CLUSTER *
0x18005fd13  call    ?ReconnectGroups@@YAKPEAU_CLUSTER@@@Z; ReconnectGroups(_CLUSTER *)
0x18005fd18  mov     [rbp+arg_8], eax
0x18005fd1b  test    eax, eax
0x18005fd1d  jz      short loc_18005FD35
0x18005fd1f  mov     dword ptr [rsp+60h+var_38], eax
0x18005fd23  mov     r9d, 56Ch
0x18005fd29  lea     rax, aReconnectgroup; "ReconnectGroups failed %d"
0x18005fd30  jmp     loc_18005FCB1
0x18005fd35  mov     rcx, rbx; struct _CLUSTER *
0x18005fd38  call    ?ReconnectNodes@@YAKPEAU_CLUSTER@@@Z; ReconnectNodes(_CLUSTER *)
0x18005fd3d  mov     [rbp+arg_8], eax
0x18005fd40  test    eax, eax
0x18005fd42  jz      short loc_18005FD5A
0x18005fd44  mov     dword ptr [rsp+60h+var_38], eax
0x18005fd48  mov     r9d, 572h
0x18005fd4e  lea     rax, aReconnectnodes_0; "ReconnectNodes failed %d"
0x18005fd55  jmp     loc_18005FCB1
0x18005fd5a  mov     rcx, rbx; struct _CLUSTER *
0x18005fd5d  call    ?ReconnectNetworks@@YAKPEAU_CLUSTER@@@Z; ReconnectNetworks(_CLUSTER *)
0x18005fd62  mov     [rbp+arg_8], eax
0x18005fd65  test    eax, eax
0x18005fd67  jz      short loc_18005FD7F
0x18005fd69  mov     dword ptr [rsp+60h+var_38], eax
0x18005fd6d  mov     r9d, 578h
0x18005fd73  lea     rax, aReconnectnetwo_0; "ReconnectNetworks failed %d"
0x18005fd7a  jmp     loc_18005FCB1
0x18005fd7f  mov     rcx, rbx; struct _CLUSTER *
0x18005fd82  call    ?ReconnectNetInterfaces@@YAKPEAU_CLUSTER@@@Z; ReconnectNetInterfaces(_CLUSTER *)
0x18005fd87  mov     [rbp+arg_8], eax
0x18005fd8a  test    eax, eax
0x18005fd8c  jz      short loc_18005FDA4
0x18005fd8e  mov     dword ptr [rsp+60h+var_38], eax
0x18005fd92  mov     r9d, 57Eh
0x18005fd98  lea     rax, aReconnectnetin_0; "ReconnectNetInterfaces failed %d"
0x18005fd9f  jmp     loc_18005FCB1
0x18005fda4  mov     rcx, rbx; struct _CLUSTER *
0x18005fda7  call    ?ReconnectNotifySessions@@YAKPEAU_CLUSTER@@@Z; ReconnectNotifySessions(_CLUSTER *)
0x18005fdac  mov     [rbp+arg_8], eax
0x18005fdaf  mov     r8, r14
0x18005fdb2  mov     edx, 7
0x18005fdb7  test    eax, eax
0x18005fdb9  jz      short loc_18005FDD1
0x18005fdbb  mov     dword ptr [rsp+60h+var_38], eax
0x18005fdbf  mov     r9d, 588h
0x18005fdc5  lea     rax, aReconnectnotif; "ReconnectNotifySessions failed %d"
0x18005fdcc  jmp     loc_18005FA57
0x18005fdd1  inc     dword ptr [rbx+110h]
0x18005fdd7  mov     edi, 4
0x18005fddc  mov     eax, [rbx+110h]
0x18005fde2  mov     r9d, 590h
0x18005fde8  mov     dword ptr [rsp+60h+var_38], eax
0x18005fdec  mov     ecx, edi
0x18005fdee  lea     rax, aNewReconnectio; "New reconnection generation #: %d"
0x18005fdf5  mov     [rsp+60h+var_40], rax
0x18005fdfa  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fdff  mov     ecx, r13d
0x18005fe02  cmp     [rbx+114h], r13d
0x18005fe09  jbe     short loc_18005FE36
0x18005fe0b  mov     rdx, [rbx+118h]
0x18005fe12  cmp     ecx, r12d
0x18005fe15  jz      short loc_18005FE23
0x18005fe17  mov     eax, ecx
0x18005fe19  add     rax, rax
0x18005fe1c  mov     [rdx+rax*8+4], r13d
0x18005fe21  jmp     short loc_18005FE2C
0x18005fe23  mov     dword ptr [rdx+r15*8+4], 1
0x18005fe2c  inc     ecx
0x18005fe2e  cmp     ecx, [rbx+114h]
0x18005fe34  jb      short loc_18005FE0B
0x18005fe36  mov     rax, [rbx+118h]
0x18005fe3d  mov     r9d, 59Eh
0x18005fe43  mov     r8, r14
0x18005fe46  mov     ecx, edi
0x18005fe48  mov     rdx, [rax+r15*8+8]
0x18005fe4d  lea     rax, aSuccessfullyRe; "Successfully reconnected to %ws"
0x18005fe54  mov     [rsp+60h+var_38], rdx
0x18005fe59  xor     edx, edx
0x18005fe5b  mov     [rsp+60h+var_40], rax
0x18005fe60  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005fe65  xor     eax, eax
0x18005fe67  mov     rbx, [rsp+60h+arg_10]
0x18005fe6f  add     rsp, 60h
0x18005fe73  pop     r15
0x18005fe75  pop     r14
0x18005fe77  pop     r13
0x18005fe79  pop     r12
  ... truncated ...
```
