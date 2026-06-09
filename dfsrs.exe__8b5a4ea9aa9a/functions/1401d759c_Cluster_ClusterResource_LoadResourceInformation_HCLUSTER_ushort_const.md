# Cluster::ClusterResource::LoadResourceInformation(_HCLUSTER *,ushort const *)

- ea: `0x1401d759c`
- end: `0x1401d7ba6`
- name: `?LoadResourceInformation@ClusterResource@Cluster@@QEAAPEAVFrsStatus@@PEAU_HCLUSTER@@PEBG@Z`
- size: `1546`
- prototype: `struct FrsStatus *(Cluster::ClusterResource *__hidden this, struct _HCLUSTER *, const unsigned __int16 *)`
- caller_count: `12`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x14010abf4`
- `0x1401d16dc`
- `0x1401d25a0`
- `0x1401d2964`
- `0x1401d6b78`
- `0x1401d6e60`
- `0x1401d7458`
- `0x1401d8d14`
- `0x1401dad78`
- `0x1401db450`
- `0x1401dbce0`
- `0x1401ef978`

## callees

- `0x14000cd1c`
- `0x140010680`
- `0x14004d52c`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401d15c8`
- `0x1401d15fc`
- `0x1401d759c`
- `0x1401d7d60`
- `0x1401d7dfc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401d772f`
- `KERNEL32!GetLastError` at `0x1401d77b3`
- `KERNEL32!GetLastError` at `0x1401d7b3f`
- `KERNEL32!GetLastError` at `0x1401d772f`
- `KERNEL32!GetLastError` at `0x1401d77b3`
- `KERNEL32!GetLastError` at `0x1401d7b3f`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7634`
- `KERNEL32!GetCurrentThreadId` at `0x1401d77c7`
- `KERNEL32!GetCurrentThreadId` at `0x1401d78d0`
- `KERNEL32!GetCurrentThreadId` at `0x1401d79ef`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7aa8`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7af9`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7b4d`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7634`
- `KERNEL32!GetCurrentThreadId` at `0x1401d77c7`
- `KERNEL32!GetCurrentThreadId` at `0x1401d78d0`
- `KERNEL32!GetCurrentThreadId` at `0x1401d79ef`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7aa8`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7af9`
- `KERNEL32!GetCurrentThreadId` at `0x1401d7b4d`
- `CLUSAPI!GetClusterResourceState` at `0x1401d7713`
- `CLUSAPI!GetClusterResourceState` at `0x1401d779a`
- `CLUSAPI!GetClusterResourceState` at `0x1401d7713`
- `CLUSAPI!GetClusterResourceState` at `0x1401d779a`
- `CLUSAPI!ClusterResourceControl` at `0x1401d7974`
- `CLUSAPI!ClusterResourceControl` at `0x1401d79ce`
- `CLUSAPI!ClusterResourceControl` at `0x1401d7a73`
- `CLUSAPI!ClusterResourceControl` at `0x1401d7974`
- `CLUSAPI!ClusterResourceControl` at `0x1401d79ce`
- `CLUSAPI!ClusterResourceControl` at `0x1401d7a73`
- `CLUSAPI!ClusterGroupControl` at `0x1401d7879`
- `CLUSAPI!ClusterGroupControl` at `0x1401d7879`

## pseudocode

```c
struct FrsStatus *__fastcall Cluster::ClusterResource::LoadResourceInformation(
        Cluster::ClusterResource *this,
        struct _HCLUSTER *a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // rdi
  struct FrsStatus *v7; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  WCHAR *v10; // r12
  struct _HRESOURCE *v11; // rbx
  CLUSTER_RESOURCE_STATE ClusterResourceState; // eax
  DWORD v13; // r15d
  CLUSTER_RESOURCE_STATE v14; // eax
  DWORD v15; // eax
  __int64 v16; // rcx
  void *v17; // r15
  DWORD v18; // r15d
  DWORD v19; // eax
  __int64 v20; // rcx
  void *lpOutBuffer; // r15
  DWORD v22; // r12d
  DWORD v23; // eax
  __int64 v24; // rcx
  DWORD v25; // ebx
  DWORD v26; // eax
  __int64 v27; // rcx
  DWORD v29; // eax
  __int64 v30; // rcx
  DWORD LastError; // ebx
  DWORD v32; // eax
  __int64 v33; // rcx
  struct FrsStatus *v34; // rax
  HGROUP hGroup; // [rsp+50h] [rbp-29h] BYREF
  void *Block; // [rsp+58h] [rbp-21h] BYREF
  HRESOURCE hResource; // [rsp+60h] [rbp-19h] BYREF
  __int64 OutBuffer; // [rsp+68h] [rbp-11h] BYREF
  const wchar_t *v39; // [rsp+70h] [rbp-9h] BYREF
  int v40; // [rsp+78h] [rbp-1h]
  int v41; // [rsp+7Ch] [rbp+3h]
  const wchar_t *v42; // [rsp+80h] [rbp+7h]
  WCHAR szNodeName; // [rsp+E0h] [rbp+67h] BYREF
  DWORD cchGroupName; // [rsp+E8h] [rbp+6Fh] BYREF
  const unsigned __int16 *v45; // [rsp+F0h] [rbp+77h] BYREF
  DWORD cchNodeName; // [rsp+F8h] [rbp+7Fh] BYREF

  v45 = a3;
  v3 = 0;
  hResource = 0;
  v7 = 0;
  if ( (((unsigned __int64)a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v40 = 6143;
      v39 = L"Cluster::ClusterResource::LoadResourceInformation";
      v41 = 2;
      v42 = L"CLUS";
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v39, L"Invalid cluster handle passed. resName:%?", &v45);
    }
    CurrentThreadId = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v9,
                               87,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                               "Cluster::ClusterResource::LoadResourceInformation",
                               6145,
                               CurrentThreadId,
                               0);
  }
  FrsStringImpl<unsigned short,char>::Set(this, &pServiceName);
  FrsStringImpl<unsigned short,char>::Set((char *)this + 8, &pServiceName);
  FrsStringImpl<unsigned short,char>::Set((char *)this + 16, &pServiceName);
  *((_DWORD *)this + 6) = -1;
  FrsStringImpl<unsigned short,char>::Set((char *)this + 32, &pServiceName);
  *((_DWORD *)this + 10) = 0;
  if ( !v7 )
  {
    v7 = Cluster::ClusterUtil::OpenResourceHandle(a2, a3, &hResource);
    if ( v7 )
    {
      LastError = GetLastError();
      v32 = GetCurrentThreadId();
      v34 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v33,
                                  LastError,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                  "Cluster::ClusterResource::LoadResourceInformation",
                                  6345,
                                  v32,
                                  0);
      v7 = PROPAGATE_ERROR_WITH_NEW_STATUS(v7, v34);
      hResource = 0;
      goto LABEL_34;
    }
    Block = 0;
    cchNodeName = 0;
    v10 = 0;
    cchGroupName = 0;
    szNodeName = 0;
    hGroup = 0;
    FrsStringImpl<unsigned short,char>::Set(this, a3);
    v11 = hResource;
    ClusterResourceState = GetClusterResourceState(hResource, &szNodeName, &cchNodeName, &szNodeName, &cchGroupName);
    *((_DWORD *)this + 6) = ClusterResourceState;
    if ( ClusterResourceState == ClusterResourceStateUnknown )
    {
      v13 = GetLastError();
      if ( v13 != 234 )
      {
LABEL_13:
        if ( v13 )
        {
          v15 = GetCurrentThreadId();
          v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v16,
                                     v13,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                     "Cluster::ClusterResource::LoadResourceInformation",
                                     6220,
                                     v15,
                                     0);
        }
        v17 = Block;
        goto LABEL_16;
      }
      ++cchGroupName;
      v10 = (WCHAR *)operator_new(saturated_mul(++cchNodeName, 2u));
      Block = operator_new(saturated_mul(cchGroupName, 2u));
      v14 = GetClusterResourceState(v11, v10, &cchNodeName, (LPWSTR)Block, &cchGroupName);
      *((_DWORD *)this + 6) = v14;
      if ( v14 == ClusterResourceStateUnknown )
      {
        v13 = GetLastError();
        goto LABEL_13;
      }
      FrsStringImpl<unsigned short,char>::Set((char *)this + 8, v10);
      v17 = Block;
      FrsStringImpl<unsigned short,char>::Set((char *)this + 16, Block);
    }
    else
    {
      v17 = 0;
    }
LABEL_16:
    operator delete[](v10);
    operator delete[](v17);
    if ( !v7 )
    {
      v7 = Cluster::ClusterUtil::OpenGroupHandle(a2, (const unsigned __int16 *)(*((_QWORD *)this + 2) + 18LL), &hGroup);
      if ( !v7 )
      {
        LODWORD(Block) = 0;
        v18 = ClusterGroupControl(hGroup, 0, 0x3000009u, 0, 0, &Block, 4u, 0);
        if ( v18 )
        {
          v19 = GetCurrentThreadId();
          v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v20,
                                     v18,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                     "Cluster::ClusterResource::LoadResourceInformation",
                                     6257,
                                     v19,
                                     0);
        }
        else if ( ((unsigned __int8)Block & 1) != 0 )
        {
          *((_DWORD *)this + 10) = 1;
        }
      }
    }
    Cluster::ClusterUtil::CloseGroupHandle(&hGroup);
    if ( !v7 && v11 && v11 != (struct _HRESOURCE *)-1LL )
    {
      LODWORD(hGroup) = 0;
      lpOutBuffer = 0;
      v22 = ClusterResourceControl(v11, 0, 0x100002Du, 0, 0, 0, 0, (LPDWORD)&hGroup);
      if ( v22
        || (LODWORD(hGroup) = (_DWORD)hGroup + 2,
            lpOutBuffer = operator_new(saturated_mul((unsigned int)hGroup >> 1, 2u)),
            (v22 = ClusterResourceControl(v11, 0, 0x100002Du, 0, 0, lpOutBuffer, (DWORD)hGroup, 0)) != 0) )
      {
        v23 = GetCurrentThreadId();
        v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v24,
                                   v22,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                   "Cluster::ClusterResource::LoadResourceInformation",
                                   6308,
                                   v23,
                                   0);
      }
      else
      {
        FrsStringImpl<unsigned short,char>::Set((char *)this + 32, lpOutBuffer);
      }
      operator delete[](lpOutBuffer);
      if ( !v7 )
      {
        OutBuffer = 0;
        v25 = ClusterResourceControl(v11, 0, 0x100000Du, 0, 0, &OutBuffer, 8u, 0);
        if ( v25 )
        {
          v29 = GetCurrentThreadId();
          v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v30,
                                     v25,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                     "Cluster::ClusterResource::LoadResourceInformation",
                                     6337,
                                     v29,
                                     0);
        }
        else
        {
          *((_DWORD *)this + 11) = OutBuffer;
        }
      }
    }
  }
LABEL_34:
  Cluster::ClusterUtil::CloseResourceHandle(&hResource);
  if ( v7 )
  {
    v26 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v27,
                                 *((unsigned int *)v7 + 1),
                                 *((unsigned int *)v7 + 2),
                                 *(unsigned int *)v7,
                                 "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                 "Cluster::ClusterResource::LoadResourceInformation",
                                 6352,
                                 v26,
                                 v7);
  }
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x1401d759c  mov     [rsp-8+arg_10], r8
0x1401d75a1  push    rbp
0x1401d75a2  push    rbx
0x1401d75a3  push    rsi
0x1401d75a4  push    rdi
0x1401d75a5  push    r12
0x1401d75a7  push    r13
0x1401d75a9  push    r14
0x1401d75ab  push    r15
0x1401d75ad  lea     rbp, [rsp-1Fh]
0x1401d75b2  sub     rsp, 98h
0x1401d75b9  xor     edi, edi
0x1401d75bb  lea     rax, [rdx+1]
0x1401d75bf  mov     [rbp+57h+hResource], rdi
0x1401d75c3  mov     rbx, r8
0x1401d75c6  lea     r15, aClusterCluster_2; "Cluster::ClusterResource::LoadResourceI"...
0x1401d75cd  mov     r13, rdx
0x1401d75d0  mov     r14, rcx
0x1401d75d3  mov     esi, edi
0x1401d75d5  lea     r12d, [rdi+1]
0x1401d75d9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1401d75df  jnz     loc_1401D7674
0x1401d75e5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d75ec  test    rax, rax
0x1401d75ef  jz      short loc_1401D7634
0x1401d75f1  cmp     [rax+40h], edi
0x1401d75f4  jz      short loc_1401D7634
0x1401d75f6  cmp     dword ptr [rax+38h], 2
0x1401d75fa  jl      short loc_1401D7634
0x1401d75fc  lea     rax, aClusterCluster_21; "Cluster::ClusterResource::LoadResourceI"...
0x1401d7603  mov     [rbp+57h+var_58], 17FFh
0x1401d760a  mov     [rbp+57h+var_60], rax
0x1401d760e  lea     r8, [rbp+57h+arg_10]
0x1401d7612  lea     rax, aClus; "CLUS"
0x1401d7619  mov     [rbp+57h+var_54], 2
0x1401d7620  lea     rdx, aInvalidCluster; "Invalid cluster handle passed. resName:"...
0x1401d7627  mov     [rbp+57h+var_50], rax
0x1401d762b  lea     rcx, [rbp+57h+var_60]
0x1401d762f  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401d7634  call    cs:__imp_GetCurrentThreadId
0x1401d763b  nop     dword ptr [rax+rax+00h]
0x1401d7640  mov     [rsp+0D0h+var_90], rdi
0x1401d7645  xor     r8d, r8d
0x1401d7648  mov     dword ptr [rsp+0D0h+lpBytesReturned], eax
0x1401d764c  mov     r9d, r12d
0x1401d764f  mov     [rsp+0D0h+nOutBufferSize], 1801h
0x1401d7657  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d765e  mov     [rsp+0D0h+lpOutBuffer], r15
0x1401d7663  lea     edx, [r8+57h]
0x1401d7667  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d766c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d7671  mov     rsi, rax
0x1401d7674  lea     r15, pServiceName
0x1401d767b  mov     rcx, r14
0x1401d767e  mov     rdx, r15
0x1401d7681  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d7686  lea     rcx, [r14+8]
0x1401d768a  mov     rdx, r15
0x1401d768d  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d7692  lea     rcx, [r14+10h]
0x1401d7696  mov     rdx, r15
0x1401d7699  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d769e  or      dword ptr [r14+18h], 0FFFFFFFFh
0x1401d76a3  lea     rcx, [r14+20h]
0x1401d76a7  mov     rdx, r15
0x1401d76aa  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d76af  mov     [r14+28h], edi
0x1401d76b3  test    rsi, rsi
0x1401d76b6  jnz     loc_1401D7A8C
0x1401d76bc  lea     r8, [rbp+57h+hResource]; struct _HRESOURCE **
0x1401d76c0  mov     rdx, rbx; unsigned __int16 *
0x1401d76c3  mov     rcx, r13; struct _HCLUSTER *
0x1401d76c6  call    ?OpenResourceHandle@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEAU_HCLUSTER@@PEBGAEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::OpenResourceHandle(_HCLUSTER *,ushort const *,_HRESOURCE * &)
0x1401d76cb  mov     rsi, rax
0x1401d76ce  test    rax, rax
0x1401d76d1  jnz     loc_1401D7B3F
0x1401d76d7  mov     rdx, rbx
0x1401d76da  mov     [rbp+57h+Block], rdi
0x1401d76de  mov     rcx, r14
0x1401d76e1  mov     [rbp+57h+cchNodeName], edi
0x1401d76e4  mov     r12, rdi
0x1401d76e7  mov     [rbp+57h+cchGroupName], edi
0x1401d76ea  mov     [rbp+57h+szNodeName], di
0x1401d76ee  mov     [rbp+57h+hGroup], rdi
0x1401d76f2  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d76f7  mov     rbx, [rbp+57h+hResource]
0x1401d76fb  lea     rax, [rbp+57h+cchGroupName]
0x1401d76ff  mov     rcx, rbx; hResource
0x1401d7702  mov     [rsp+0D0h+lpcchGroupName], rax; lpcchGroupName
0x1401d7707  lea     r9, [rbp+57h+szNodeName]; lpszGroupName
0x1401d770b  lea     r8, [rbp+57h+cchNodeName]; lpcchNodeName
0x1401d770f  lea     rdx, [rbp+57h+szNodeName]; lpszNodeName
0x1401d7713  call    cs:__imp_GetClusterResourceState
0x1401d771a  nop     dword ptr [rax+rax+00h]
0x1401d771f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1401d7723  mov     [r14+18h], eax
0x1401d7727  cmp     eax, ecx
0x1401d7729  jnz     loc_1401D78C8
0x1401d772f  call    cs:__imp_GetLastError
0x1401d7736  nop     dword ptr [rax+rax+00h]
0x1401d773b  mov     r15d, eax
0x1401d773e  cmp     eax, 0EAh
0x1401d7743  jnz     short loc_1401D77C2
0x1401d7745  mov     eax, [rbp+57h+cchNodeName]
0x1401d7748  lea     r15, [rsi-1]
0x1401d774c  inc     [rbp+57h+cchGroupName]
0x1401d774f  inc     eax
0x1401d7751  mov     ecx, eax
0x1401d7753  mov     [rbp+57h+cchNodeName], eax
0x1401d7756  lea     eax, [rsi+2]
0x1401d7759  mul     rcx
0x1401d775c  cmovo   rax, r15
0x1401d7760  mov     rcx, rax; unsigned __int64
0x1401d7763  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401d7768  mov     ecx, [rbp+57h+cchGroupName]
0x1401d776b  mov     r12, rax
0x1401d776e  lea     eax, [rsi+2]
0x1401d7771  mul     rcx
0x1401d7774  cmovo   rax, r15
0x1401d7778  mov     rcx, rax; unsigned __int64
0x1401d777b  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401d7780  lea     rcx, [rbp+57h+cchGroupName]
0x1401d7784  mov     [rbp+57h+Block], rax
0x1401d7788  mov     [rsp+0D0h+lpcchGroupName], rcx; lpcchGroupName
0x1401d778d  lea     r8, [rbp+57h+cchNodeName]; lpcchNodeName
0x1401d7791  mov     rcx, rbx; hResource
0x1401d7794  mov     r9, rax; lpszGroupName
0x1401d7797  mov     rdx, r12; lpszNodeName
0x1401d779a  call    cs:__imp_GetClusterResourceState
0x1401d77a1  nop     dword ptr [rax+rax+00h]
0x1401d77a6  mov     [r14+18h], eax
0x1401d77aa  cmp     eax, r15d
0x1401d77ad  jnz     loc_1401D78A7
0x1401d77b3  call    cs:__imp_GetLastError
0x1401d77ba  nop     dword ptr [rax+rax+00h]
0x1401d77bf  mov     r15d, eax
0x1401d77c2  test    r15d, r15d
0x1401d77c5  jz      short loc_1401D7810
0x1401d77c7  call    cs:__imp_GetCurrentThreadId
0x1401d77ce  nop     dword ptr [rax+rax+00h]
0x1401d77d3  mov     [rsp+0D0h+var_90], rdi
0x1401d77d8  mov     r9d, 1
0x1401d77de  mov     dword ptr [rsp+0D0h+lpBytesReturned], eax
0x1401d77e2  xor     r8d, r8d
0x1401d77e5  lea     rax, aClusterCluster_2; "Cluster::ClusterResource::LoadResourceI"...
0x1401d77ec  mov     [rsp+0D0h+nOutBufferSize], 184Ch
0x1401d77f4  mov     [rsp+0D0h+lpOutBuffer], rax
0x1401d77f9  mov     edx, r15d
0x1401d77fc  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d7803  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d7808  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d780d  mov     rsi, rax
0x1401d7810  mov     r15, [rbp+57h+Block]
0x1401d7814  mov     rcx, r12; Block
0x1401d7817  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401d781c  mov     rcx, r15; Block
0x1401d781f  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401d7824  test    rsi, rsi
0x1401d7827  jnz     loc_1401D791B
0x1401d782d  mov     rdx, [r14+10h]
0x1401d7831  lea     r8, [rbp+57h+hGroup]; struct _HGROUP **
0x1401d7835  add     rdx, 12h; unsigned __int16 *
0x1401d7839  mov     rcx, r13; struct _HCLUSTER *
0x1401d783c  call    ?OpenGroupHandle@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEAU_HCLUSTER@@PEBGAEAPEAU_HGROUP@@@Z; Cluster::ClusterUtil::OpenGroupHandle(_HCLUSTER *,ushort const *,_HGROUP * &)
0x1401d7841  mov     rsi, rax
0x1401d7844  test    rax, rax
0x1401d7847  jnz     loc_1401D791B
0x1401d784d  mov     rcx, [rbp+57h+hGroup]; hGroup
0x1401d7851  lea     rax, [rbp+57h+Block]
0x1401d7855  mov     [rsp+0D0h+lpBytesReturned], rdi; lpBytesReturned
0x1401d785a  xor     r9d, r9d; lpInBuffer
0x1401d785d  mov     [rsp+0D0h+nOutBufferSize], 4; nOutBufferSize
0x1401d7865  xor     edx, edx; hHostNode
0x1401d7867  mov     [rsp+0D0h+lpOutBuffer], rax; lpOutBuffer
0x1401d786c  mov     r8d, 3000009h; dwControlCode
0x1401d7872  mov     dword ptr [rsp+0D0h+lpcchGroupName], edi; nInBufferSize
0x1401d7876  mov     dword ptr [rbp+57h+Block], edi
0x1401d7879  call    cs:__imp_ClusterGroupControl
0x1401d7880  nop     dword ptr [rax+rax+00h]
0x1401d7885  mov     r15d, eax
0x1401d7888  test    eax, eax
0x1401d788a  jnz     short loc_1401D78D0
0x1401d788c  test    byte ptr [rbp+57h+Block], 1
0x1401d7890  lea     r13, aClusterCluster_2; "Cluster::ClusterResource::LoadResourceI"...
0x1401d7897  jz      loc_1401D7922
0x1401d789d  mov     dword ptr [r14+28h], 1
0x1401d78a5  jmp     short loc_1401D7922
0x1401d78a7  mov     rdx, r12
0x1401d78aa  lea     rcx, [r14+8]
0x1401d78ae  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d78b3  mov     r15, [rbp+57h+Block]
0x1401d78b7  lea     rcx, [r14+10h]
0x1401d78bb  mov     rdx, r15
0x1401d78be  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d78c3  jmp     loc_1401D7814
0x1401d78c8  mov     r15, rdi
0x1401d78cb  jmp     loc_1401D7814
0x1401d78d0  call    cs:__imp_GetCurrentThreadId
0x1401d78d7  nop     dword ptr [rax+rax+00h]
0x1401d78dc  mov     [rsp+0D0h+var_90], rdi
0x1401d78e1  lea     r13, aClusterCluster_2; "Cluster::ClusterResource::LoadResourceI"...
0x1401d78e8  mov     dword ptr [rsp+0D0h+lpBytesReturned], eax
0x1401d78ec  mov     r9d, 1
0x1401d78f2  mov     [rsp+0D0h+nOutBufferSize], 1871h
0x1401d78fa  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d7901  mov     [rsp+0D0h+lpOutBuffer], r13
0x1401d7906  xor     r8d, r8d
0x1401d7909  mov     edx, r15d
0x1401d790c  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d7911  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d7916  mov     rsi, rax
0x1401d7919  jmp     short loc_1401D7922
0x1401d791b  lea     r13, aClusterCluster_2; "Cluster::ClusterResource::LoadResourceI"...
0x1401d7922  lea     rcx, [rbp+57h+hGroup]; struct _HGROUP **
0x1401d7926  call    ?CloseGroupHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HGROUP@@@Z; Cluster::ClusterUtil::CloseGroupHandle(_HGROUP * &)
0x1401d792b  test    rsi, rsi
0x1401d792e  jnz     loc_1401D7A8C
0x1401d7934  test    rbx, rbx
0x1401d7937  jz      loc_1401D7A8C
0x1401d793d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1401d7941  cmp     rbx, rax
0x1401d7944  jz      loc_1401D7A8C
0x1401d794a  lea     rax, [rbp+57h+hGroup]
0x1401d794e  mov     dword ptr [rbp+57h+hGroup], edi
0x1401d7951  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x1401d7956  xor     r9d, r9d; lpInBuffer
0x1401d7959  mov     [rsp+0D0h+nOutBufferSize], edi; cbOutBufferSize
0x1401d795d  xor     edx, edx; hHostNode
0x1401d795f  mov     [rsp+0D0h+lpOutBuffer], rdi; lpOutBuffer
0x1401d7964  mov     r8d, 100002Dh; dwControlCode
0x1401d796a  mov     rcx, rbx; hResource
0x1401d796d  mov     dword ptr [rsp+0D0h+lpcchGroupName], edi; cbInBufferSize
0x1401d7971  mov     r15, rdi
0x1401d7974  call    cs:__imp_ClusterResourceControl
0x1401d797b  nop     dword ptr [rax+rax+00h]
0x1401d7980  mov     r12d, eax
0x1401d7983  test    eax, eax
0x1401d7985  jnz     short loc_1401D79EF
0x1401d7987  mov     ecx, dword ptr [rbp+57h+hGroup]
0x1401d798a  lea     eax, [rsi+2]
0x1401d798d  add     ecx, 2
0x1401d7990  mov     dword ptr [rbp+57h+hGroup], ecx
0x1401d7993  shr     ecx, 1
0x1401d7995  mul     rcx
0x1401d7998  lea     rcx, [rsi-1]
0x1401d799c  cmovo   rax, rcx
0x1401d79a0  mov     rcx, rax; unsigned __int64
0x1401d79a3  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401d79a8  mov     r15, rax
0x1401d79ab  mov     [rsp+0D0h+lpBytesReturned], rdi; lpBytesReturned
0x1401d79b0  mov     eax, dword ptr [rbp+57h+hGroup]
0x1401d79b3  xor     r9d, r9d; lpInBuffer
0x1401d79b6  mov     [rsp+0D0h+nOutBufferSize], eax; cbOutBufferSize
0x1401d79ba  xor     edx, edx; hHostNode
0x1401d79bc  mov     [rsp+0D0h+lpOutBuffer], r15; lpOutBuffer
0x1401d79c1  mov     r8d, 100002Dh; dwControlCode
0x1401d79c7  mov     rcx, rbx; hResource
0x1401d79ca  mov     dword ptr [rsp+0D0h+lpcchGroupName], edi; cbInBufferSize
0x1401d79ce  call    cs:__imp_ClusterResourceControl
0x1401d79d5  nop     dword ptr [rax+rax+00h]
0x1401d79da  mov     r12d, eax
0x1401d79dd  test    eax, eax
0x1401d79df  jnz     short loc_1401D79EF
0x1401d79e1  mov     rdx, r15
0x1401d79e4  lea     rcx, [r14+20h]
0x1401d79e8  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d79ed  jmp     short loc_1401D7A31
0x1401d79ef  call    cs:__imp_GetCurrentThreadId
0x1401d79f6  nop     dword ptr [rax+rax+00h]
0x1401d79fb  mov     [rsp+0D0h+var_90], rdi
0x1401d7a00  mov     r9d, 1
0x1401d7a06  mov     dword ptr [rsp+0D0h+lpBytesReturned], eax
0x1401d7a0a  xor     r8d, r8d
0x1401d7a0d  mov     [rsp+0D0h+nOutBufferSize], 18A4h
0x1401d7a15  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d7a1c  mov     [rsp+0D0h+lpOutBuffer], r13
0x1401d7a21  mov     edx, r12d
0x1401d7a24  mov     [rsp+0D0h+lpcchGroupName], rax
0x1401d7a29  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d7a2e  mov     rsi, rax
0x1401d7a31  mov     rcx, r15; Block
0x1401d7a34  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401d7a39  test    rsi, rsi
0x1401d7a3c  jnz     short loc_1401D7A8C
0x1401d7a3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1401d7a42  cmp     rbx, rax
0x1401d7a45  jz      short loc_1401D7A8C
0x1401d7a47  mov     [rsp+0D0h+lpBytesReturned], rdi; lpBytesReturned
0x1401d7a4c  lea     rax, [rbp+57h+OutBuffer]
0x1401d7a50  mov     [rsp+0D0h+nOutBufferSize], 8; cbOutBufferSize
0x1401d7a58  xor     r9d, r9d; lpInBuffer
0x1401d7a5b  mov     [rsp+0D0h+lpOutBuffer], rax; lpOutBuffer
0x1401d7a60  xor     edx, edx; hHostNode
0x1401d7a62  mov     r8d, 100000Dh; dwControlCode
0x1401d7a68  mov     dword ptr [rsp+0D0h+lpcchGroupName], edi; cbInBufferSize
0x1401d7a6c  mov     rcx, rbx; hResource
0x1401d7a6f  mov     [rbp+57h+OutBuffer], rdi
0x1401d7a73  call    cs:__imp_ClusterResourceControl
0x1401d7a7a  nop     dword ptr [rax+rax+00h]
0x1401d7a7f  mov     ebx, eax
  ... truncated ...
```
