# Cluster::ClusterUtil::GetStorageResourceTypeList(ushort const *,ObjList<FrsStringImpl<ushort,char>> &)

- ea: `0x1401d60c8`
- end: `0x1401d644c`
- name: `?GetStorageResourceTypeList@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGAEAV?$ObjList@V?$FrsStringImpl@GD@@@@@Z`
- size: `900`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1401d2964`

## callees

- `0x14000cd1c`
- `0x14000ee94`
- `0x140010680`
- `0x14002c548`
- `0x14004691c`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401c3480`
- `0x1401d1594`
- `0x1401d60c8`
- `0x1401d7cc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401d6150`
- `KERNEL32!GetLastError` at `0x1401d6150`
- `KERNEL32!GetCurrentThreadId` at `0x1401d6142`
- `KERNEL32!GetCurrentThreadId` at `0x1401d6331`
- `KERNEL32!GetCurrentThreadId` at `0x1401d6390`
- `KERNEL32!GetCurrentThreadId` at `0x1401d63f4`
- `KERNEL32!GetCurrentThreadId` at `0x1401d6142`
- `KERNEL32!GetCurrentThreadId` at `0x1401d6331`
- `KERNEL32!GetCurrentThreadId` at `0x1401d6390`
- `KERNEL32!GetCurrentThreadId` at `0x1401d63f4`
- `CLUSAPI!ClusterCloseEnum` at `0x1401d63d2`
- `CLUSAPI!ClusterCloseEnum` at `0x1401d63d2`
- `CLUSAPI!ClusterEnum` at `0x1401d61b4`
- `CLUSAPI!ClusterEnum` at `0x1401d6208`
- `CLUSAPI!ClusterEnum` at `0x1401d61b4`
- `CLUSAPI!ClusterEnum` at `0x1401d6208`
- `CLUSAPI!ClusterOpenEnum` at `0x1401d6126`
- `CLUSAPI!ClusterOpenEnum` at `0x1401d6126`
- `CLUSAPI!ClusterResourceTypeControl` at `0x1401d6251`
- `CLUSAPI!ClusterResourceTypeControl` at `0x1401d6251`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Cluster::ClusterUtil::GetStorageResourceTypeList(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  struct _HCLUSENUM *v3; // rsi
  __int64 v4; // r14
  const unsigned __int16 *v5; // rcx
  struct FrsStatus *v6; // rbx
  struct _HCLUSTER *v7; // r13
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v10; // rcx
  DWORD v11; // r15d
  DWORD v12; // r14d
  WCHAR *v13; // r12
  DWORD v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD nOutBufferSize; // [rsp+38h] [rbp-41h]
  DWORD nOutBufferSizea; // [rsp+38h] [rbp-41h]
  unsigned __int16 *v23; // [rsp+50h] [rbp-29h] BYREF
  WCHAR *v24; // [rsp+58h] [rbp-21h] BYREF
  __int64 OutBuffer; // [rsp+60h] [rbp-19h] BYREF
  WCHAR *v26; // [rsp+68h] [rbp-11h] BYREF
  const wchar_t *v27; // [rsp+70h] [rbp-9h] BYREF
  int v28; // [rsp+78h] [rbp-1h]
  int v29; // [rsp+7Ch] [rbp+3h]
  const wchar_t *v30; // [rsp+80h] [rbp+7h]
  __int64 cchName; // [rsp+E0h] [rbp+67h] BYREF
  DWORD dwType; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v33; // [rsp+F0h] [rbp+77h]
  HCLUSTER hCluster; // [rsp+F8h] [rbp+7Fh] BYREF

  cchName = a1;
  v2 = 0;
  hCluster = 0;
  v3 = 0;
  v4 = a2 + 8;
  v33 = a2 + 8;
  std::vector<FrsStringImpl<unsigned short,char>>::clear(a2 + 8);
  v6 = Cluster::ClusterUtil::OpenClusterHandle(v5, &hCluster);
  v7 = hCluster;
  if ( !v6 )
  {
    v3 = ClusterOpenEnum(hCluster, 2u);
    if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      LastError = GetLastError();
      v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v10,
                                 LastError,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                 "Cluster::ClusterUtil::GetStorageResourceTypeList",
                                 4179,
                                 CurrentThreadId,
                                 0);
    }
  }
  v11 = 0;
  while ( !v6 )
  {
    dwType = 0;
    LODWORD(cchName) = 0;
    v24 = 0;
    v12 = ClusterEnum(v3, v11, &dwType, 0, (LPDWORD)&cchName);
    if ( v12
      || (LODWORD(cchName) = cchName + 1,
          v13 = (WCHAR *)operator_new(saturated_mul((unsigned int)cchName, 2u)),
          v24 = v13,
          (v12 = ClusterEnum(v3, v11, &dwType, v13, (LPDWORD)&cchName)) != 0) )
    {
      if ( v12 == 259 )
      {
        scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v24);
        v4 = v33;
        break;
      }
      nOutBufferSizea = GetCurrentThreadId();
      v16 = FrsStatusList::PushNewError(
              v17,
              v12,
              0,
              1,
              "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
              "Cluster::ClusterUtil::GetStorageResourceTypeList",
              4282,
              nOutBufferSizea,
              0);
LABEL_21:
      v6 = (struct FrsStatus *)v16;
      goto LABEL_22;
    }
    OutBuffer = 0;
    v14 = ClusterResourceTypeControl(v7, v13, 0, 0x200000Du, 0, 0, &OutBuffer, 8u, 0);
    if ( v14 )
    {
      if ( v14 != 5079 )
      {
        nOutBufferSize = GetCurrentThreadId();
        v16 = FrsStatusList::PushNewError(
                v15,
                v14,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                "Cluster::ClusterUtil::GetStorageResourceTypeList",
                4266,
                nOutBufferSize,
                0);
        goto LABEL_21;
      }
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) )
        goto LABEL_18;
      if ( SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v27 = L"Cluster::ClusterUtil::GetStorageResourceTypeList";
        v28 = 4257;
        v29 = 5;
        v30 = L"CLUS";
        v26 = v13;
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(
          &v27,
          L"[CLUSTER] Resource Type is not supported on this node. Skipping. resTypeName: %ws",
          &v26);
LABEL_18:
        v4 = v33;
        goto LABEL_19;
      }
LABEL_22:
      v4 = v33;
      goto LABEL_19;
    }
    if ( (_DWORD)OutBuffer != 1 )
      goto LABEL_18;
    v23 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !byte_140315A80 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
      v7 = hCluster;
    }
    FrsStringImpl<unsigned short,char>::Set(&v23, v13);
    v4 = v33;
    std::vector<FrsStringImpl<unsigned short,char>>::push_back(v33, &v23);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v23);
LABEL_19:
    ++v11;
    scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v24);
  }
  if ( (unsigned __int64)v3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    ClusterCloseEnum(v3);
  Cluster::ClusterUtil::CloseClusterHandle(&hCluster);
  if ( v6 )
  {
    std::vector<FrsStringImpl<unsigned short,char>>::clear(v4);
    v18 = GetCurrentThreadId();
    return FrsStatusList::PushNewError(
             v19,
             *((unsigned int *)v6 + 1),
             *((unsigned int *)v6 + 2),
             *(unsigned int *)v6,
             "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
             "Cluster::ClusterUtil::GetStorageResourceTypeList",
             4309,
             v18,
             v6);
  }
  return v2;
}

```

## disassembly

```asm
0x1401d60c8  mov     [rsp-8+cchName], rcx
0x1401d60cd  push    rbp
0x1401d60ce  push    rbx
0x1401d60cf  push    rsi
0x1401d60d0  push    rdi
0x1401d60d1  push    r12
0x1401d60d3  push    r13
0x1401d60d5  push    r14
0x1401d60d7  push    r15
0x1401d60d9  lea     rbp, [rsp-1Fh]
0x1401d60de  sub     rsp, 98h
0x1401d60e5  xor     edi, edi
0x1401d60e7  mov     [rbp+57h+hCluster], rdi
0x1401d60eb  mov     esi, edi
0x1401d60ed  lea     r14, [rdx+8]
0x1401d60f1  mov     [rbp+57h+arg_10], r14
0x1401d60f5  mov     rcx, r14
0x1401d60f8  call    ?clear@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXXZ; std::vector<FrsStringImpl<ushort,char>>::clear(void)
0x1401d60fd  lea     rdx, [rbp+57h+hCluster]; struct _HCLUSTER **
0x1401d6101  call    ?OpenClusterHandle@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::OpenClusterHandle(ushort const *,_HCLUSTER * &)
0x1401d6106  mov     rbx, rax
0x1401d6109  lea     r12, aClusterCluster_8; "Cluster::ClusterUtil::GetStorageResourc"...
0x1401d6110  lea     r15, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d6117  mov     r13, [rbp+57h+hCluster]
0x1401d611b  test    rax, rax
0x1401d611e  jnz     short loc_1401D6188
0x1401d6120  lea     edx, [rdi+2]; dwType
0x1401d6123  mov     rcx, r13; hCluster
0x1401d6126  call    cs:__imp_ClusterOpenEnum
0x1401d612d  nop     dword ptr [rax+rax+00h]
0x1401d6132  mov     rsi, rax
0x1401d6135  lea     rcx, [rax+1]
0x1401d6139  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1401d6140  jnz     short loc_1401D6188
0x1401d6142  call    cs:__imp_GetCurrentThreadId
0x1401d6149  nop     dword ptr [rax+rax+00h]
0x1401d614e  mov     ebx, eax
0x1401d6150  call    cs:__imp_GetLastError
0x1401d6157  nop     dword ptr [rax+rax+00h]
0x1401d615c  mov     [rsp+0D0h+lpBytesReturned], rdi
0x1401d6161  mov     [rsp+0D0h+nOutBufferSize], ebx
0x1401d6165  mov     dword ptr [rsp+0D0h+lpOutBuffer], 1053h
0x1401d616d  mov     qword ptr [rsp+0D0h+nInBufferSize], r12
0x1401d6172  mov     [rsp+0D0h+lpcchName], r15
0x1401d6177  lea     r9d, [rdi+1]
0x1401d617b  xor     r8d, r8d
0x1401d617e  mov     edx, eax
0x1401d6180  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d6185  mov     rbx, rax
0x1401d6188  mov     r15d, edi
0x1401d618b  test    rbx, rbx
0x1401d618e  jnz     loc_1401D63C5
0x1401d6194  mov     [rbp+57h+dwType], edi
0x1401d6197  mov     dword ptr [rbp+57h+cchName], edi
0x1401d619a  mov     [rbp+57h+var_78], rdi
0x1401d619e  lea     rax, [rbp+57h+cchName]
0x1401d61a2  mov     [rsp+0D0h+lpcchName], rax; lpcchName
0x1401d61a7  xor     r9d, r9d; lpszName
0x1401d61aa  lea     r8, [rbp+57h+dwType]; lpdwType
0x1401d61ae  mov     edx, r15d; dwIndex
0x1401d61b1  mov     rcx, rsi; hEnum
0x1401d61b4  call    cs:__imp_ClusterEnum
0x1401d61bb  nop     dword ptr [rax+rax+00h]
0x1401d61c0  mov     r14d, eax
0x1401d61c3  test    eax, eax
0x1401d61c5  jnz     loc_1401D6387
0x1401d61cb  mov     eax, dword ptr [rbp+57h+cchName]
0x1401d61ce  inc     eax
0x1401d61d0  mov     dword ptr [rbp+57h+cchName], eax
0x1401d61d3  mov     ecx, eax
0x1401d61d5  lea     eax, [rbx+2]
0x1401d61d8  mul     rcx
0x1401d61db  lea     rcx, [rbx-1]
0x1401d61df  cmovo   rax, rcx
0x1401d61e3  mov     rcx, rax; unsigned __int64
0x1401d61e6  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401d61eb  mov     r12, rax
0x1401d61ee  mov     [rbp+57h+var_78], rax
0x1401d61f2  lea     rax, [rbp+57h+cchName]
0x1401d61f6  mov     [rsp+0D0h+lpcchName], rax; lpcchName
0x1401d61fb  mov     r9, r12; lpszName
0x1401d61fe  lea     r8, [rbp+57h+dwType]; lpdwType
0x1401d6202  mov     edx, r15d; dwIndex
0x1401d6205  mov     rcx, rsi; hEnum
0x1401d6208  call    cs:__imp_ClusterEnum
0x1401d620f  nop     dword ptr [rax+rax+00h]
0x1401d6214  mov     r14d, eax
0x1401d6217  test    eax, eax
0x1401d6219  jnz     loc_1401D6380
0x1401d621f  mov     [rbp+57h+OutBuffer], rdi
0x1401d6223  mov     [rsp+0D0h+lpBytesReturned], rdi; lpBytesReturned
0x1401d6228  mov     [rsp+0D0h+nOutBufferSize], 8; nOutBufferSize
0x1401d6230  lea     rax, [rbp+57h+OutBuffer]
0x1401d6234  mov     [rsp+0D0h+lpOutBuffer], rax; lpOutBuffer
0x1401d6239  mov     [rsp+0D0h+nInBufferSize], edi; nInBufferSize
0x1401d623d  mov     [rsp+0D0h+lpcchName], rdi; lpInBuffer
0x1401d6242  mov     r9d, 200000Dh; dwControlCode
0x1401d6248  xor     r8d, r8d; hHostNode
0x1401d624b  mov     rdx, r12; lpszResourceTypeName
0x1401d624e  mov     rcx, r13; hCluster
0x1401d6251  call    cs:__imp_ClusterResourceTypeControl
0x1401d6258  nop     dword ptr [rax+rax+00h]
0x1401d625d  mov     r14d, eax
0x1401d6260  test    eax, eax
0x1401d6262  jnz     short loc_1401D62B5
0x1401d6264  cmp     dword ptr [rbp+57h+OutBuffer], 1
0x1401d6268  jnz     loc_1401D6315
0x1401d626e  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d6275  mov     [rbp+57h+var_80], rax
0x1401d6279  cmp     cs:byte_140315A80, dil
0x1401d6280  jnz     short loc_1401D628D
0x1401d6282  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d6289  mov     r13, [rbp+57h+hCluster]
0x1401d628d  mov     rdx, r12
0x1401d6290  lea     rcx, [rbp+57h+var_80]
0x1401d6294  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401d6299  lea     rdx, [rbp+57h+var_80]
0x1401d629d  mov     r14, [rbp+57h+arg_10]
0x1401d62a1  mov     rcx, r14
0x1401d62a4  call    ?push_back@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXAEBV?$FrsStringImpl@GD@@@Z; std::vector<FrsStringImpl<ushort,char>>::push_back(FrsStringImpl<ushort,char> const &)
0x1401d62a9  nop
0x1401d62aa  lea     rcx, [rbp+57h+var_80]
0x1401d62ae  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d62b3  jmp     short loc_1401D6319
0x1401d62b5  cmp     r14d, 13D7h
0x1401d62bc  jnz     short loc_1401D6331
0x1401d62be  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d62c5  test    rax, rax
0x1401d62c8  jz      short loc_1401D6315
0x1401d62ca  cmp     [rax+40h], edi
0x1401d62cd  jz      short loc_1401D6315
0x1401d62cf  cmp     dword ptr [rax+38h], 5
0x1401d62d3  jl      loc_1401D63AF
0x1401d62d9  lea     rax, aClusterCluster_47; "Cluster::ClusterUtil::GetStorageResourc"...
0x1401d62e0  mov     [rbp+57h+var_60], rax
0x1401d62e4  mov     [rbp+57h+var_58], 10A1h
0x1401d62eb  mov     [rbp+57h+var_54], 5
0x1401d62f2  lea     rax, aClus; "CLUS"
0x1401d62f9  mov     [rbp+57h+var_50], rax
0x1401d62fd  mov     [rbp+57h+var_68], r12
0x1401d6301  lea     r8, [rbp+57h+var_68]
0x1401d6305  lea     rdx, aClusterResourc_0; "[CLUSTER] Resource Type is not supporte"...
0x1401d630c  lea     rcx, [rbp+57h+var_60]
0x1401d6310  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401d6315  mov     r14, [rbp+57h+arg_10]
0x1401d6319  lea     r12, aClusterCluster_8; "Cluster::ClusterUtil::GetStorageResourc"...
0x1401d6320  inc     r15d
0x1401d6323  lea     rcx, [rbp+57h+var_78]
0x1401d6327  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401d632c  jmp     loc_1401D618B
0x1401d6331  call    cs:__imp_GetCurrentThreadId
0x1401d6338  nop     dword ptr [rax+rax+00h]
0x1401d633d  mov     [rsp+0D0h+lpBytesReturned], rdi
0x1401d6342  mov     [rsp+0D0h+nOutBufferSize], eax
0x1401d6346  mov     dword ptr [rsp+0D0h+lpOutBuffer], 10AAh
0x1401d634e  lea     r12, aClusterCluster_8; "Cluster::ClusterUtil::GetStorageResourc"...
0x1401d6355  mov     qword ptr [rsp+0D0h+nInBufferSize], r12
0x1401d635a  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d6361  mov     [rsp+0D0h+lpcchName], rax
0x1401d6366  mov     r9d, 1
0x1401d636c  xor     r8d, r8d
0x1401d636f  mov     edx, r14d
0x1401d6372  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d6377  mov     rbx, rax
0x1401d637a  mov     r14, [rbp+57h+arg_10]
0x1401d637e  jmp     short loc_1401D6320
0x1401d6380  lea     r12, aClusterCluster_8; "Cluster::ClusterUtil::GetStorageResourc"...
0x1401d6387  cmp     r14d, 103h
0x1401d638e  jz      short loc_1401D63B8
0x1401d6390  call    cs:__imp_GetCurrentThreadId
0x1401d6397  nop     dword ptr [rax+rax+00h]
0x1401d639c  mov     [rsp+0D0h+lpBytesReturned], rdi
0x1401d63a1  mov     [rsp+0D0h+nOutBufferSize], eax
0x1401d63a5  mov     dword ptr [rsp+0D0h+lpOutBuffer], 10BAh
0x1401d63ad  jmp     short loc_1401D6355
0x1401d63af  lea     r12, aClusterCluster_8; "Cluster::ClusterUtil::GetStorageResourc"...
0x1401d63b6  jmp     short loc_1401D637A
0x1401d63b8  lea     rcx, [rbp+57h+var_78]
0x1401d63bc  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401d63c1  mov     r14, [rbp+57h+arg_10]
0x1401d63c5  lea     rax, [rsi-1]
0x1401d63c9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401d63cd  ja      short loc_1401D63DE
0x1401d63cf  mov     rcx, rsi; hEnum
0x1401d63d2  call    cs:__imp_ClusterCloseEnum
0x1401d63d9  nop     dword ptr [rax+rax+00h]
0x1401d63de  lea     rcx, [rbp+57h+hCluster]; struct _HCLUSTER **
0x1401d63e2  call    ?CloseClusterHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::CloseClusterHandle(_HCLUSTER * &)
0x1401d63e7  test    rbx, rbx
0x1401d63ea  jz      short loc_1401D6434
0x1401d63ec  mov     rcx, r14
0x1401d63ef  call    ?clear@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXXZ; std::vector<FrsStringImpl<ushort,char>>::clear(void)
0x1401d63f4  call    cs:__imp_GetCurrentThreadId
0x1401d63fb  nop     dword ptr [rax+rax+00h]
0x1401d6400  mov     [rsp+0D0h+lpBytesReturned], rbx
0x1401d6405  mov     [rsp+0D0h+nOutBufferSize], eax
0x1401d6409  mov     dword ptr [rsp+0D0h+lpOutBuffer], 10D5h
0x1401d6411  mov     qword ptr [rsp+0D0h+nInBufferSize], r12
0x1401d6416  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d641d  mov     [rsp+0D0h+lpcchName], rax
0x1401d6422  mov     r9d, [rbx]
0x1401d6425  mov     r8d, [rbx+8]
0x1401d6429  mov     edx, [rbx+4]
0x1401d642c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d6431  mov     rdi, rax
0x1401d6434  mov     rax, rdi
0x1401d6437  add     rsp, 98h
0x1401d643e  pop     r15
0x1401d6440  pop     r14
0x1401d6442  pop     r13
0x1401d6444  pop     r12
0x1401d6446  pop     rdi
0x1401d6447  pop     rsi
0x1401d6448  pop     rbx
0x1401d6449  pop     rbp
0x1401d644a  retn
```
