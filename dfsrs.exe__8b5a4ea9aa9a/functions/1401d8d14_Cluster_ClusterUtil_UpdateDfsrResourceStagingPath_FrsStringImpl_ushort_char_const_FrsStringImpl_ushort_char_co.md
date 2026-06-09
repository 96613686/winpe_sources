# Cluster::ClusterUtil::UpdateDfsrResourceStagingPath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)

- ea: `0x1401d8d14`
- end: `0x1401d92d0`
- name: `?UpdateDfsrResourceStagingPath@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@0@Z`
- size: `1468`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x1401127a4`

## callees

- `0x14000ee94`
- `0x14001c31c`
- `0x14001cfa0`
- `0x14001d7bc`
- `0x14001e19c`
- `0x14001e4a0`
- `0x14002383c`
- `0x1401b9494`
- `0x1401ce6dc`
- `0x1401cff28`
- `0x1401d01d8`
- `0x1401d07ec`
- `0x1401d1594`
- `0x1401d15fc`
- `0x1401d42b4`
- `0x1401d59b0`
- `0x1401d6454`
- `0x1401d759c`
- `0x1401d7cc0`
- `0x1401d7dfc`
- `0x1401d841c`
- `0x1401d8664`
- `0x1401d8d14`
- `0x1401d97b4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401d8eba`
- `KERNEL32!GetCurrentThreadId` at `0x1401d9075`
- `KERNEL32!GetCurrentThreadId` at `0x1401d922b`
- `KERNEL32!GetCurrentThreadId` at `0x1401d8eba`
- `KERNEL32!GetCurrentThreadId` at `0x1401d9075`
- `KERNEL32!GetCurrentThreadId` at `0x1401d922b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401d8f2a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401d911e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401d8f2a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401d911e`

## string_xrefs

- `0x1401d8ff9`: `Replicated Folder Root Path`
- `0x1401d8e2c`: `Staging Path`
- `0x1401d9159`: `Staging Path`
- `0x1401d8e62`: `Cluster::ClusterUtil::UpdateDfsrResourceStagingPath`
- `0x1401d8f81`: `[CLUSTER] Staging path did not change for the resource. resName:%? oldStagingPath:%? newStagingPath:%?`
- `0x1401d8fe8`: `[CLUSTER] Staging path changed for the resource.  resName:%? oldStagingPath:%? newStagingPath:%?`
- `0x1401d8ea9`: `[CLUSTER] Failed to find staging path property for the resource. resName:%?`
- `0x1401d8ddb`: `Cluster::ClusterUtil::UpdateDfsrResourceStagingPath`
- `0x1401d8ed7`: `Cluster::ClusterUtil::UpdateDfsrResourceStagingPath`
- `0x1401d9092`: `Cluster::ClusterUtil::UpdateDfsrResourceStagingPath`
- `0x1401d90d1`: `Cluster::ClusterUtil::UpdateDfsrResourceStagingPath`
- `0x1401d9215`: `Cluster::ClusterUtil::UpdateDfsrResourceStagingPath`
- `0x1401d9064`: `[CLUSTER] Failed to find root path property for the resource. resName:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Cluster::ClusterUtil::UpdateDfsrResourceStagingPath(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  char v5; // al
  struct FrsStatus *ResourceInformation; // rbx
  __int64 v7; // rax
  int StringPropertyValue; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // ebx
  DWORD v13; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  const wchar_t *v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v21; // [rsp+60h] [rbp-A0h]
  struct _HCLUSTER *v22; // [rsp+68h] [rbp-98h] BYREF
  struct _HRESOURCE *v23; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v25; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v26; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v27; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[8]; // [rsp+98h] [rbp-68h] BYREF
  void **v29; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v30[24]; // [rsp+A8h] [rbp-58h] BYREF
  void **v31; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v32[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v33[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v34[104]; // [rsp+F8h] [rbp-8h] BYREF
  int v35; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 *v36; // [rsp+188h] [rbp+88h] BYREF

  Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)v34);
  v4 = 0;
  v22 = 0;
  Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList((Cluster::ResourcePrivatePropertyList *)&v29);
  v36 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v5 = byte_140315A80;
  if ( !byte_140315A80 )
  {
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v5 = 0;
  }
  v24 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v5 )
  {
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v5 = byte_140315A80;
  }
  v27 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v5 )
  {
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v5 = byte_140315A80;
  }
  v26 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v5 )
  {
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v5 = byte_140315A80;
  }
  v25 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v5 )
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
  ResourceInformation = Cluster::ClusterUtil::OpenClusterHandle(&FrsStringImpl<unsigned short,char>::s_Empty, &v22);
  if ( !ResourceInformation )
  {
    ResourceInformation = Cluster::ClusterResource::LoadResourceInformation(
                            (Cluster::ClusterResource *)v34,
                            v22,
                            (const unsigned __int16 *)(*(_QWORD *)a1 + 18LL));
    if ( !ResourceInformation )
    {
      ResourceInformation = Cluster::ClusterResource::GetResourceProperties(
                              (Cluster::ClusterResource *)v34,
                              (struct Cluster::ResourcePrivatePropertyList *)&v29);
      if ( !ResourceInformation )
      {
        v7 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v23, L"Staging Path");
        StringPropertyValue = Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v29, v7, &v36);
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v23);
        if ( StringPropertyValue )
          goto LABEL_52;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v18 = L"Cluster::ClusterUtil::UpdateDfsrResourceStagingPath";
          v19 = 5604;
          v20 = 2;
          v21 = L"CLUS";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
            &v18,
            L"[CLUSTER] Failed to find staging path property for the resource. resName:%?",
            a1);
        }
        CurrentThreadId = GetCurrentThreadId();
        ResourceInformation = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v10,
                                                    9230,
                                                    0,
                                                    3,
                                                    "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                                    "Cluster::ClusterUtil::UpdateDfsrResourceStagingPath",
                                                    5607,
                                                    CurrentThreadId,
                                                    0);
        if ( !ResourceInformation )
        {
LABEL_52:
          if ( !*((_QWORD *)v36 + 1) )
            goto LABEL_42;
          if ( !(unsigned int)_o__wcsicmp(v36 + 9, *(_QWORD *)a2 + 18LL) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
            {
              v18 = L"Cluster::ClusterUtil::UpdateDfsrResourceStagingPath";
              v19 = 5624;
              v20 = 5;
              v21 = L"CLUS";
              dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
                (unsigned int)&v18,
                (unsigned int)L"[CLUSTER] Staging path did not change for the resource. resName:%? oldStagingPath:%? newStagingPath:%?",
                a1,
                (unsigned int)&v36,
                a2);
            }
            Cluster::ClusterUtil::CloseClusterHandle(&v22);
            goto LABEL_49;
          }
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v18 = L"Cluster::ClusterUtil::UpdateDfsrResourceStagingPath";
            v19 = 5635;
            v20 = 4;
            v21 = L"CLUS";
            dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
              (unsigned int)&v18,
              (unsigned int)L"[CLUSTER] Staging path changed for the resource.  resName:%? oldStagingPath:%? newStagingPath:%?",
              a1,
              (unsigned int)&v36,
              a2);
          }
          v11 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(
                  v28,
                  L"Replicated Folder Root Path");
          v12 = Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v29, v11, &v27);
          FrsStringImpl<char,unsigned short>::ReleaseBody(v28);
          if ( v12 )
            goto LABEL_53;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v18 = L"Cluster::ClusterUtil::UpdateDfsrResourceStagingPath";
            v19 = 5645;
            v20 = 2;
            v21 = L"CLUS";
            dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
              &v18,
              L"[CLUSTER] Failed to find root path property for the resource. resName:%?",
              a1);
          }
          v13 = GetCurrentThreadId();
          ResourceInformation = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                      v14,
                                                      9230,
                                                      0,
                                                      3,
                                                      "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                                      "Cluster::ClusterUtil::UpdateDfsrResourceStagingPath",
                                                      5648,
                                                      v13,
                                                      0);
          if ( !ResourceInformation )
          {
LABEL_53:
            ResourceInformation = (struct FrsStatus *)Cluster::ClusterUtil::GetDiskResourceNameForPath(&v36, &v24);
            if ( !ResourceInformation )
            {
              ResourceInformation = (struct FrsStatus *)Cluster::ClusterUtil::GetDiskResourceNameForPath(&v27, &v26);
              if ( !ResourceInformation
                && (!(unsigned int)_o__wcsicmp(v24 + 9, v26 + 9)
                 || (ResourceInformation = (struct FrsStatus *)Cluster::ClusterUtil::RemoveResourceDependency(a1, &v24)) == 0) )
              {
LABEL_42:
                Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList((Cluster::ResourcePrivatePropertyList *)&v31);
                v23 = 0;
                Cluster::ResourcePrivateProperty::ResourcePrivateProperty(
                  (Cluster::ResourcePrivateProperty *)v33,
                  L"Staging Path",
                  (const unsigned __int16 *)(*(_QWORD *)a2 + 18LL));
                std::vector<Cluster::ResourcePrivateProperty>::push_back(v32, v33);
                ResourceInformation = Cluster::ClusterUtil::OpenResourceHandle(
                                        v22,
                                        (const unsigned __int16 *)(*(_QWORD *)a1 + 18LL),
                                        &v23);
                if ( !ResourceInformation )
                {
                  v35 = 1;
                  ResourceInformation = Cluster::ClusterUtil::SetResourceProperties(
                                          v23,
                                          (const struct Cluster::ResourcePrivatePropertyList *)&v31,
                                          (const enum Cluster::_ResourcePropertyType *)&v35);
                }
                Cluster::ClusterUtil::CloseResourceHandle(&v23);
                INetwork::RemotePartnerInfo::~RemotePartnerInfo((INetwork::RemotePartnerInfo *)v33);
                v31 = &ObjList<Cluster::ResourcePrivateProperty>::`vftable';
                std::vector<Cluster::ResourcePrivateProperty>::_Tidy(v32);
                if ( !ResourceInformation )
                {
                  ResourceInformation = (struct FrsStatus *)Cluster::ClusterUtil::GetDiskResourceNameForPath(a2, &v25);
                  if ( !ResourceInformation )
                    ResourceInformation = (struct FrsStatus *)Cluster::ClusterUtil::AddResourceDependency(a1, &v25);
                }
              }
            }
          }
        }
      }
    }
  }
  Cluster::ClusterUtil::CloseClusterHandle(&v22);
  if ( ResourceInformation )
  {
    v15 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v16,
           *((unsigned int *)ResourceInformation + 1),
           *((unsigned int *)ResourceInformation + 2),
           *(unsigned int *)ResourceInformation,
           "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
           "Cluster::ClusterUtil::UpdateDfsrResourceStagingPath",
           5705,
           v15,
           ResourceInformation);
  }
LABEL_49:
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v25);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v26);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v27);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v24);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v36);
  v29 = &ObjList<Cluster::ResourcePrivateProperty>::`vftable';
  std::vector<Cluster::ResourcePrivateProperty>::_Tidy(v30);
  Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v34);
  return v4;
}

```

## disassembly

```asm
0x1401d8d14  mov     [rsp-8+arg_0], rbx
0x1401d8d19  push    rbp
0x1401d8d1a  push    rsi
0x1401d8d1b  push    rdi
0x1401d8d1c  push    r12
0x1401d8d1e  push    r13
0x1401d8d20  push    r14
0x1401d8d22  push    r15
0x1401d8d24  lea     rbp, [rsp-30h]
0x1401d8d29  sub     rsp, 130h
0x1401d8d30  mov     r14, rdx
0x1401d8d33  mov     rsi, rcx
0x1401d8d36  lea     rcx, [rbp+60h+var_68]; this
0x1401d8d3a  call    ??0ClusterResource@Cluster@@QEAA@XZ; Cluster::ClusterResource::ClusterResource(void)
0x1401d8d3f  nop
0x1401d8d40  xor     edi, edi
0x1401d8d42  mov     [rsp+160h+var_F8], rdi
0x1401d8d47  lea     rcx, [rbp+60h+var_C0]; this
0x1401d8d4b  call    ??0ResourcePrivatePropertyList@Cluster@@QEAA@XZ; Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList(void)
0x1401d8d50  nop
0x1401d8d51  lea     rcx, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; unsigned __int16 *
0x1401d8d58  mov     [rbp+60h+arg_18], rcx
0x1401d8d5f  lea     r15d, [rdi+1]
0x1401d8d63  mov     al, cs:byte_140315A80
0x1401d8d69  test    al, al
0x1401d8d6b  jnz     short loc_1401D8D7B
0x1401d8d6d  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, r15d; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d8d75  mov     al, cs:byte_140315A80
0x1401d8d7b  mov     [rsp+160h+var_E8], rcx
0x1401d8d80  test    al, al
0x1401d8d82  jnz     short loc_1401D8D92
0x1401d8d84  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, r15d; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d8d8c  mov     al, cs:byte_140315A80
0x1401d8d92  mov     [rbp+60h+var_D0], rcx
0x1401d8d96  test    al, al
0x1401d8d98  jnz     short loc_1401D8DA8
0x1401d8d9a  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, r15d; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d8da2  mov     al, cs:byte_140315A80
0x1401d8da8  mov     [rbp+60h+var_D8], rcx
0x1401d8dac  test    al, al
0x1401d8dae  jnz     short loc_1401D8DBE
0x1401d8db0  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, r15d; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d8db8  mov     al, cs:byte_140315A80
0x1401d8dbe  mov     [rbp+60h+var_E0], rcx
0x1401d8dc2  test    al, al
0x1401d8dc4  jnz     short loc_1401D8DCE
0x1401d8dc6  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, r15d; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d8dce  lea     rdx, [rsp+160h+var_F8]; struct _HCLUSTER **
0x1401d8dd3  call    ?OpenClusterHandle@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::OpenClusterHandle(ushort const *,_HCLUSTER * &)
0x1401d8dd8  mov     rbx, rax
0x1401d8ddb  lea     r12, aClusterCluster_22; "Cluster::ClusterUtil::UpdateDfsrResourc"...
0x1401d8de2  lea     r13, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d8de9  test    rax, rax
0x1401d8dec  jnz     loc_1401D90C5
0x1401d8df2  mov     r8, [rsi]
0x1401d8df5  add     r8, 12h; unsigned __int16 *
0x1401d8df9  mov     rdx, [rsp+160h+var_F8]; struct _HCLUSTER *
0x1401d8dfe  lea     rcx, [rbp+60h+var_68]; this
0x1401d8e02  call    ?LoadResourceInformation@ClusterResource@Cluster@@QEAAPEAVFrsStatus@@PEAU_HCLUSTER@@PEBG@Z; Cluster::ClusterResource::LoadResourceInformation(_HCLUSTER *,ushort const *)
0x1401d8e07  mov     rbx, rax
0x1401d8e0a  test    rax, rax
0x1401d8e0d  jnz     loc_1401D90C5
0x1401d8e13  lea     rdx, [rbp+60h+var_C0]; struct Cluster::ResourcePrivatePropertyList *
0x1401d8e17  lea     rcx, [rbp+60h+var_68]; this
0x1401d8e1b  call    ?GetResourceProperties@ClusterResource@Cluster@@QEBAPEAVFrsStatus@@AEAVResourcePrivatePropertyList@2@@Z; Cluster::ClusterResource::GetResourceProperties(Cluster::ResourcePrivatePropertyList &)
0x1401d8e20  mov     rbx, rax
0x1401d8e23  test    rax, rax
0x1401d8e26  jnz     loc_1401D90C5
0x1401d8e2c  lea     rdx, aStagingPath_0; "Staging Path"
0x1401d8e33  lea     rcx, [rsp+160h+var_F0]
0x1401d8e38  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d8e3d  lea     r8, [rbp+60h+arg_18]
0x1401d8e44  mov     rdx, rax
0x1401d8e47  lea     rcx, [rbp+60h+var_C0]
0x1401d8e4b  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x1401d8e50  mov     ebx, eax
0x1401d8e52  lea     rcx, [rsp+160h+var_F0]
0x1401d8e57  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d8e5c  mov     r12d, 2
0x1401d8e62  lea     r13, aClusterCluster_12; "Cluster::ClusterUtil::UpdateDfsrResourc"...
0x1401d8e69  lea     rcx, aClus; "CLUS"
0x1401d8e70  test    ebx, ebx
0x1401d8e72  jnz     loc_1401D8F0E
0x1401d8e78  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d8e7f  test    rax, rax
0x1401d8e82  jz      short loc_1401D8EBA
0x1401d8e84  cmp     [rax+40h], edi
0x1401d8e87  jz      short loc_1401D8EBA
0x1401d8e89  cmp     [rax+38h], r12d
0x1401d8e8d  jl      short loc_1401D8EBA
0x1401d8e8f  mov     [rsp+160h+var_110], r13
0x1401d8e94  mov     [rsp+160h+var_108], 15E4h
0x1401d8e9c  mov     [rsp+160h+var_104], r12d
0x1401d8ea1  mov     [rsp+160h+var_100], rcx
0x1401d8ea6  mov     r8, rsi
0x1401d8ea9  lea     rdx, aClusterFailedT_32; "[CLUSTER] Failed to find staging path p"...
0x1401d8eb0  lea     rcx, [rsp+160h+var_110]
0x1401d8eb5  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d8eba  call    cs:__imp_GetCurrentThreadId
0x1401d8ec1  nop     dword ptr [rax+rax+00h]
0x1401d8ec6  mov     [rsp+160h+var_120], rdi
0x1401d8ecb  mov     [rsp+160h+var_128], eax
0x1401d8ecf  mov     [rsp+160h+var_130], 15E7h
0x1401d8ed7  lea     rax, aClusterCluster_22; "Cluster::ClusterUtil::UpdateDfsrResourc"...
0x1401d8ede  mov     [rsp+160h+var_138], rax
0x1401d8ee3  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d8eea  mov     [rsp+160h+var_140], rax
0x1401d8eef  mov     r9d, 3
0x1401d8ef5  xor     r8d, r8d
0x1401d8ef8  mov     edx, 240Eh
0x1401d8efd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d8f02  mov     rbx, rax
0x1401d8f05  test    rax, rax
0x1401d8f08  jnz     loc_1401D9207
0x1401d8f0e  mov     rax, [rbp+60h+arg_18]
0x1401d8f15  cmp     [rax+8], rdi
0x1401d8f19  jbe     loc_1401D9143
0x1401d8f1f  mov     rdx, [r14]
0x1401d8f22  add     rdx, 12h
0x1401d8f26  lea     rcx, [rax+12h]
0x1401d8f2a  call    cs:__imp__o__wcsicmp
0x1401d8f31  nop     dword ptr [rax+rax+00h]
0x1401d8f36  test    eax, eax
0x1401d8f38  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d8f3f  jnz     short loc_1401D8FA8
0x1401d8f41  test    rax, rax
0x1401d8f44  jz      short loc_1401D8F92
0x1401d8f46  cmp     [rax+40h], edi
0x1401d8f49  jz      short loc_1401D8F92
0x1401d8f4b  cmp     dword ptr [rax+38h], 5
0x1401d8f4f  jl      short loc_1401D8F92
0x1401d8f51  mov     [rsp+160h+var_110], r13
0x1401d8f56  mov     [rsp+160h+var_108], 15F8h
0x1401d8f5e  mov     [rsp+160h+var_104], 5
0x1401d8f66  lea     rax, aClus; "CLUS"
0x1401d8f6d  mov     [rsp+160h+var_100], rax
0x1401d8f72  mov     [rsp+160h+var_140], r14
0x1401d8f77  lea     r9, [rbp+60h+arg_18]
0x1401d8f7e  mov     r8, rsi
0x1401d8f81  lea     rdx, aClusterStaging_0; "[CLUSTER] Staging path did not change f"...
0x1401d8f88  lea     rcx, [rsp+160h+var_110]
0x1401d8f8d  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@V1@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@11@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1401d8f92  lea     rcx, [rsp+160h+var_F8]; struct _HCLUSTER **
0x1401d8f97  call    ?CloseClusterHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::CloseClusterHandle(_HCLUSTER * &)
0x1401d8f9c  lea     r15, ??_7?$ObjList@VResourcePrivateProperty@Cluster@@@@6B@; const ObjList<Cluster::ResourcePrivateProperty>::`vftable'
0x1401d8fa3  jmp     loc_1401D9264
0x1401d8fa8  test    rax, rax
0x1401d8fab  jz      short loc_1401D8FF9
0x1401d8fad  cmp     [rax+40h], edi
0x1401d8fb0  jz      short loc_1401D8FF9
0x1401d8fb2  cmp     dword ptr [rax+38h], 4
0x1401d8fb6  jl      short loc_1401D8FF9
0x1401d8fb8  mov     [rsp+160h+var_110], r13
0x1401d8fbd  mov     [rsp+160h+var_108], 1603h
0x1401d8fc5  mov     [rsp+160h+var_104], 4
0x1401d8fcd  lea     rax, aClus; "CLUS"
0x1401d8fd4  mov     [rsp+160h+var_100], rax
0x1401d8fd9  mov     [rsp+160h+var_140], r14
0x1401d8fde  lea     r9, [rbp+60h+arg_18]
0x1401d8fe5  mov     r8, rsi
0x1401d8fe8  lea     rdx, aClusterStaging; "[CLUSTER] Staging path changed for the "...
0x1401d8fef  lea     rcx, [rsp+160h+var_110]
0x1401d8ff4  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@V1@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@11@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1401d8ff9  lea     rdx, aReplicatedFold_0; "Replicated Folder Root Path"
0x1401d9000  lea     rcx, [rbp+60h+var_C8]
0x1401d9004  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d9009  lea     r8, [rbp+60h+var_D0]
0x1401d900d  mov     rdx, rax
0x1401d9010  lea     rcx, [rbp+60h+var_C0]
0x1401d9014  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x1401d9019  mov     ebx, eax
0x1401d901b  lea     rcx, [rbp+60h+var_C8]
0x1401d901f  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d9024  test    ebx, ebx
0x1401d9026  jnz     loc_1401D90D1
0x1401d902c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d9033  test    rax, rax
0x1401d9036  jz      short loc_1401D9075
0x1401d9038  cmp     [rax+40h], edi
0x1401d903b  jz      short loc_1401D9075
0x1401d903d  cmp     [rax+38h], r12d
0x1401d9041  jl      short loc_1401D9075
0x1401d9043  mov     [rsp+160h+var_110], r13
0x1401d9048  mov     [rsp+160h+var_108], 160Dh
0x1401d9050  mov     [rsp+160h+var_104], r12d
0x1401d9055  lea     rax, aClus; "CLUS"
0x1401d905c  mov     [rsp+160h+var_100], rax
0x1401d9061  mov     r8, rsi
0x1401d9064  lea     rdx, aClusterFailedT_2; "[CLUSTER] Failed to find root path prop"...
0x1401d906b  lea     rcx, [rsp+160h+var_110]
0x1401d9070  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d9075  call    cs:__imp_GetCurrentThreadId
0x1401d907c  nop     dword ptr [rax+rax+00h]
0x1401d9081  mov     [rsp+160h+var_120], rdi
0x1401d9086  mov     [rsp+160h+var_128], eax
0x1401d908a  mov     [rsp+160h+var_130], 1610h
0x1401d9092  lea     r12, aClusterCluster_22; "Cluster::ClusterUtil::UpdateDfsrResourc"...
0x1401d9099  mov     [rsp+160h+var_138], r12
0x1401d909e  lea     r13, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d90a5  mov     [rsp+160h+var_140], r13
0x1401d90aa  mov     r9d, 3
0x1401d90b0  xor     r8d, r8d
0x1401d90b3  mov     edx, 240Eh
0x1401d90b8  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d90bd  mov     rbx, rax
0x1401d90c0  test    rax, rax
0x1401d90c3  jz      short loc_1401D90DF
0x1401d90c5  lea     r15, ??_7?$ObjList@VResourcePrivateProperty@Cluster@@@@6B@; const ObjList<Cluster::ResourcePrivateProperty>::`vftable'
0x1401d90cc  jmp     loc_1401D921C
0x1401d90d1  lea     r12, aClusterCluster_22; "Cluster::ClusterUtil::UpdateDfsrResourc"...
0x1401d90d8  lea     r13, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d90df  lea     rdx, [rsp+160h+var_E8]
0x1401d90e4  lea     rcx, [rbp+60h+arg_18]
0x1401d90eb  call    ?GetDiskResourceNameForPath@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@PEAV4@@Z; Cluster::ClusterUtil::GetDiskResourceNameForPath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> *)
0x1401d90f0  mov     rbx, rax
0x1401d90f3  test    rax, rax
0x1401d90f6  jnz     short loc_1401D90C5
0x1401d90f8  lea     rdx, [rbp+60h+var_D8]
0x1401d90fc  lea     rcx, [rbp+60h+var_D0]
0x1401d9100  call    ?GetDiskResourceNameForPath@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@PEAV4@@Z; Cluster::ClusterUtil::GetDiskResourceNameForPath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> *)
0x1401d9105  mov     rbx, rax
0x1401d9108  test    rax, rax
0x1401d910b  jnz     short loc_1401D90C5
0x1401d910d  mov     rdx, [rbp+60h+var_D8]
0x1401d9111  add     rdx, 12h
0x1401d9115  mov     rcx, [rsp+160h+var_E8]
0x1401d911a  add     rcx, 12h
0x1401d911e  call    cs:__imp__o__wcsicmp
0x1401d9125  nop     dword ptr [rax+rax+00h]
0x1401d912a  test    eax, eax
0x1401d912c  jz      short loc_1401D9143
0x1401d912e  lea     rdx, [rsp+160h+var_E8]
0x1401d9133  mov     rcx, rsi
0x1401d9136  call    ?RemoveResourceDependency@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@0@Z; Cluster::ClusterUtil::RemoveResourceDependency(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1401d913b  mov     rbx, rax
0x1401d913e  test    rax, rax
0x1401d9141  jnz     short loc_1401D90C5
0x1401d9143  lea     rcx, [rbp+60h+var_A0]; this
0x1401d9147  call    ??0ResourcePrivatePropertyList@Cluster@@QEAA@XZ; Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList(void)
0x1401d914c  nop
0x1401d914d  mov     [rsp+160h+var_F0], rdi
0x1401d9152  mov     r8, [r14]
0x1401d9155  add     r8, 12h; unsigned __int16 *
0x1401d9159  lea     rdx, aStagingPath_0; "Staging Path"
0x1401d9160  lea     rcx, [rbp+60h+var_80]; this
0x1401d9164  call    ??0ResourcePrivateProperty@Cluster@@QEAA@PEBG0@Z; Cluster::ResourcePrivateProperty::ResourcePrivateProperty(ushort const *,ushort const *)
0x1401d9169  nop
0x1401d916a  lea     rdx, [rbp+60h+var_80]
0x1401d916e  lea     rcx, [rbp+60h+var_98]
0x1401d9172  call    ?push_back@?$vector@VResourcePrivateProperty@Cluster@@V?$allocator@VResourcePrivateProperty@Cluster@@@std@@@std@@QEAAXAEBVResourcePrivateProperty@Cluster@@@Z; std::vector<Cluster::ResourcePrivateProperty>::push_back(Cluster::ResourcePrivateProperty const &)
0x1401d9177  mov     rdx, [rsi]
0x1401d917a  add     rdx, 12h; unsigned __int16 *
0x1401d917e  lea     r8, [rsp+160h+var_F0]; struct _HRESOURCE **
0x1401d9183  mov     rcx, [rsp+160h+var_F8]; struct _HCLUSTER *
0x1401d9188  call    ?OpenResourceHandle@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEAU_HCLUSTER@@PEBGAEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::OpenResourceHandle(_HCLUSTER *,ushort const *,_HRESOURCE * &)
0x1401d918d  mov     rbx, rax
0x1401d9190  test    rax, rax
0x1401d9193  jnz     short loc_1401D91B4
0x1401d9195  mov     [rbp+60h+arg_10], r15d
0x1401d919c  lea     r8, [rbp+60h+arg_10]; enum Cluster::_ResourcePropertyType *
0x1401d91a3  lea     rdx, [rbp+60h+var_A0]; struct Cluster::ResourcePrivatePropertyList *
0x1401d91a7  mov     rcx, [rsp+160h+var_F0]; struct _HRESOURCE *
0x1401d91ac  call    ?SetResourceProperties@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEAU_HRESOURCE@@AEBVResourcePrivatePropertyList@2@AEBW4_ResourcePropertyType@2@@Z; Cluster::ClusterUtil::SetResourceProperties(_HRESOURCE *,Cluster::ResourcePrivatePropertyList const &,Cluster::_ResourcePropertyType const &)
0x1401d91b1  mov     rbx, rax
0x1401d91b4  lea     rcx, [rsp+160h+var_F0]; struct _HRESOURCE **
0x1401d91b9  call    ?CloseResourceHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::CloseResourceHandle(_HRESOURCE * &)
0x1401d91be  nop
0x1401d91bf  lea     rcx, [rbp+60h+var_80]; this
0x1401d91c3  call    ??1RemotePartnerInfo@INetwork@@QEAA@XZ; INetwork::RemotePartnerInfo::~RemotePartnerInfo(void)
0x1401d91c8  nop
0x1401d91c9  lea     r15, ??_7?$ObjList@VResourcePrivateProperty@Cluster@@@@6B@; const ObjList<Cluster::ResourcePrivateProperty>::`vftable'
0x1401d91d0  mov     [rbp+60h+var_A0], r15
0x1401d91d4  lea     rcx, [rbp+60h+var_98]
0x1401d91d8  call    ?_Tidy@?$vector@VResourcePrivateProperty@Cluster@@V?$allocator@VResourcePrivateProperty@Cluster@@@std@@@std@@AEAAXXZ; std::vector<Cluster::ResourcePrivateProperty>::_Tidy(void)
0x1401d91dd  test    rbx, rbx
0x1401d91e0  jnz     short loc_1401D920E
0x1401d91e2  lea     rdx, [rbp+60h+var_E0]
0x1401d91e6  mov     rcx, r14
0x1401d91e9  call    ?GetDiskResourceNameForPath@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@PEAV4@@Z; Cluster::ClusterUtil::GetDiskResourceNameForPath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> *)
0x1401d91ee  mov     rbx, rax
0x1401d91f1  test    rax, rax
0x1401d91f4  jnz     short loc_1401D920E
0x1401d91f6  lea     rdx, [rbp+60h+var_E0]
0x1401d91fa  mov     rcx, rsi
0x1401d91fd  call    ?AddResourceDependency@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@0@Z; Cluster::ClusterUtil::AddResourceDependency(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1401d9202  mov     rbx, rax
0x1401d9205  jmp     short loc_1401D920E
0x1401d9207  lea     r15, ??_7?$ObjList@VResourcePrivateProperty@Cluster@@@@6B@; const ObjList<Cluster::ResourcePrivateProperty>::`vftable'
0x1401d920e  lea     r13, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d9215  lea     r12, aClusterCluster_22; "Cluster::ClusterUtil::UpdateDfsrResourc"...
0x1401d921c  lea     rcx, [rsp+160h+var_F8]; struct _HCLUSTER **
0x1401d9221  call    ?CloseClusterHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::CloseClusterHandle(_HCLUSTER * &)
0x1401d9226  test    rbx, rbx
0x1401d9229  jz      short loc_1401D9264
0x1401d922b  call    cs:__imp_GetCurrentThreadId
0x1401d9232  nop     dword ptr [rax+rax+00h]
0x1401d9237  mov     [rsp+160h+var_120], rbx
0x1401d923c  mov     [rsp+160h+var_128], eax
0x1401d9240  mov     [rsp+160h+var_130], 1649h
0x1401d9248  mov     [rsp+160h+var_138], r12
  ... truncated ...
```
