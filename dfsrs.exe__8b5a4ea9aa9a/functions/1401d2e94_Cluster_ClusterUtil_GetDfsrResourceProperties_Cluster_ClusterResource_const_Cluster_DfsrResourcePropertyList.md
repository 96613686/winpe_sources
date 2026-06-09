# Cluster::ClusterUtil::GetDfsrResourceProperties(Cluster::ClusterResource const &,Cluster::DfsrResourcePropertyList &)

- ea: `0x1401d2e94`
- end: `0x1401d4004`
- name: `?GetDfsrResourceProperties@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBVClusterResource@2@AEAVDfsrResourcePropertyList@2@@Z`
- size: `4464`
- prototype: `static struct FrsStatus *(const struct Cluster::ClusterResource *, struct Cluster::DfsrResourcePropertyList *)`
- caller_count: `6`
- callee_count: `20`
- tags: ``

## callers

- `0x14010abf4`
- `0x1401d6e60`
- `0x1401dad78`
- `0x1401db450`
- `0x1401dbce0`
- `0x1401ef978`

## callees

- `0x14000ee94`
- `0x14001c31c`
- `0x14001c608`
- `0x14001cfa0`
- `0x14001d4c4`
- `0x14001d7bc`
- `0x14001e3a8`
- `0x140022ce4`
- `0x1400237f4`
- `0x14002383c`
- `0x1401b3d14`
- `0x1401b9494`
- `0x1401d14f4`
- `0x1401d22b8`
- `0x1401d2e94`
- `0x1401d4808`
- `0x1401d5448`
- `0x1401d571c`
- `0x1401d59b0`
- `0x1401d6454`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401d2fd5`
- `KERNEL32!GetCurrentThreadId` at `0x1401d30c6`
- `KERNEL32!GetCurrentThreadId` at `0x1401d31cf`
- `KERNEL32!GetCurrentThreadId` at `0x1401d32c0`
- `KERNEL32!GetCurrentThreadId` at `0x1401d33ca`
- `KERNEL32!GetCurrentThreadId` at `0x1401d34bf`
- `KERNEL32!GetCurrentThreadId` at `0x1401d35cf`
- `KERNEL32!GetCurrentThreadId` at `0x1401d36c4`
- `KERNEL32!GetCurrentThreadId` at `0x1401d37d0`
- `KERNEL32!GetCurrentThreadId` at `0x1401d38e4`
- `KERNEL32!GetCurrentThreadId` at `0x1401d39f8`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3b0c`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3c20`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3d34`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3e80`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3f21`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3f83`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2fd5`
- `KERNEL32!GetCurrentThreadId` at `0x1401d30c6`
- `KERNEL32!GetCurrentThreadId` at `0x1401d31cf`
- `KERNEL32!GetCurrentThreadId` at `0x1401d32c0`
- `KERNEL32!GetCurrentThreadId` at `0x1401d33ca`
- `KERNEL32!GetCurrentThreadId` at `0x1401d34bf`
- `KERNEL32!GetCurrentThreadId` at `0x1401d35cf`
- `KERNEL32!GetCurrentThreadId` at `0x1401d36c4`
- `KERNEL32!GetCurrentThreadId` at `0x1401d37d0`
- `KERNEL32!GetCurrentThreadId` at `0x1401d38e4`
- `KERNEL32!GetCurrentThreadId` at `0x1401d39f8`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3b0c`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3c20`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3d34`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3e80`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3f21`
- `KERNEL32!GetCurrentThreadId` at `0x1401d3f83`

## string_xrefs

- `0x1401d370a`: `Replicated Folder Root Path`
- `0x1401d3a45`: `Staging Path`
- `0x1401d3b59`: `Conflict Path`
- `0x1401d37ad`: `[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Path property. resName:%?`
- `0x1401d3bfd`: `[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Conflict Path property. resName:%?`
- `0x1401d3ae9`: `[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Staging Path property. resName:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
struct FrsStatus *__fastcall Cluster::ClusterUtil::GetDfsrResourceProperties(
        const struct Cluster::ClusterResource *a1,
        struct Cluster::DfsrResourcePropertyList *a2)
{
  __int64 v4; // rdi
  int v5; // ebx
  struct FrsStatus *ResourceProperties; // rsi
  __int64 v7; // rax
  char v8; // r14
  __int64 ResourceName; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  char v16; // r14
  __int64 v17; // rax
  DWORD v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  DWORD v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  char v24; // r14
  __int64 v25; // rax
  DWORD v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rax
  DWORD v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  char v32; // r14
  __int64 v33; // rax
  DWORD v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  DWORD v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  char v40; // r14
  __int64 v41; // rax
  DWORD v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rax
  char v45; // r14
  __int64 v46; // rax
  DWORD v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rax
  char v50; // r14
  __int64 v51; // rax
  DWORD v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rax
  char v55; // r14
  __int64 v56; // rax
  DWORD v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rax
  char v60; // r14
  __int64 v61; // rax
  DWORD v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rax
  char v65; // r14
  __int64 v66; // rax
  DWORD v67; // eax
  __int64 v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rcx
  DWORD v75; // eax
  __int64 v76; // rcx
  DWORD v78; // [rsp+38h] [rbp-C8h]
  DWORD v79; // [rsp+38h] [rbp-C8h]
  const wchar_t *v80; // [rsp+50h] [rbp-B0h] BYREF
  int v81; // [rsp+58h] [rbp-A8h]
  int v82; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v83; // [rsp+60h] [rbp-A0h]
  _BYTE v84[8]; // [rsp+70h] [rbp-90h] BYREF
  void **v85; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v86[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v87[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v88[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v89[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v90[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v91[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v92[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v93[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v94[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v95[8]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v96[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v97[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v98[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v99[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v100[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v101[8]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v102[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v103[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v104[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v105[8]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v106[8]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v107[8]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v108[8]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v109[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v110[8]; // [rsp+150h] [rbp+50h] BYREF
  void **v111; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v112[10]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 *v113; // [rsp+1D8h] [rbp+D8h] BYREF

  v4 = 0;
  v5 = 0;
  v113 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v5 = 0;
  }
  Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList((Cluster::ResourcePrivatePropertyList *)&v85);
  Cluster::DfsrResourcePropertyList::ClearAll(a2);
  ResourceProperties = Cluster::ClusterResource::GetResourceProperties(
                         a1,
                         (struct Cluster::ResourcePrivatePropertyList *)&v85);
  if ( ResourceProperties
    || (v7 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v87, L"Replicated Folder ID"),
        v5 = 1,
        v8 = 1,
        (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v7, &v113)) )
  {
    v8 = 0;
  }
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v87);
  }
  if ( v8 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3380;
      v82 = 3;
      v83 = L"CLUS";
      ResourceName = Cluster::NodeNetworkName::GetResourceName(a1, v88);
      v5 |= 2u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder ID property. resName:%?",
        ResourceName);
    }
    if ( (v5 & 2) != 0 )
    {
      v5 &= ~2u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v88);
    }
    CurrentThreadId = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v11,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3383,
                                               CurrentThreadId,
                                               0);
  }
  if ( ResourceProperties )
    goto LABEL_26;
  if ( !(unsigned int)Guid::StringToGuid(&v113, (char *)a2 + 16) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3387;
      v82 = 3;
      v83 = L"CLUS";
      v12 = Cluster::NodeNetworkName::GetResourceName(a1, v89);
      v5 |= 4u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) The resource's Replicated Folder ID property contains an invalid GUID value. resName:%? propVal:%?",
        v12,
        &v113);
    }
    if ( (v5 & 4) != 0 )
    {
      v5 &= ~4u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v89);
    }
    v13 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v14,
                                               9231,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3391,
                                               v13,
                                               0);
    if ( ResourceProperties )
      goto LABEL_26;
  }
  v15 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v90, L"Replication Group ID");
  v5 |= 8u;
  v16 = 1;
  if ( (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v15, &v113) )
LABEL_26:
    v16 = 0;
  if ( (v5 & 8) != 0 )
  {
    v5 &= ~8u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v90);
  }
  if ( v16 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3399;
      v82 = 3;
      v83 = L"CLUS";
      v17 = Cluster::NodeNetworkName::GetResourceName(a1, v91);
      v5 |= 0x10u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replication Group ID property. resName:%?",
        v17);
    }
    if ( (v5 & 0x10) != 0 )
    {
      v5 &= ~0x10u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v91);
    }
    v18 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v19,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3402,
                                               v18,
                                               0);
  }
  if ( ResourceProperties )
    goto LABEL_47;
  if ( !(unsigned int)Guid::StringToGuid(&v113, (char *)a2 + 40) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3406;
      v82 = 3;
      v83 = L"CLUS";
      v20 = Cluster::NodeNetworkName::GetResourceName(a1, v92);
      v5 |= 0x20u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) The resource's Replication Group ID property contains an invalid GUID value. resName:%? propVal:%?",
        v20,
        &v113);
    }
    if ( (v5 & 0x20) != 0 )
    {
      v5 &= ~0x20u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v92);
    }
    v21 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v22,
                                               9231,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3410,
                                               v21,
                                               0);
    if ( ResourceProperties )
      goto LABEL_47;
  }
  v23 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v93, L"Volume ID");
  v5 |= 0x40u;
  v24 = 1;
  if ( (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v23, &v113) )
LABEL_47:
    v24 = 0;
  if ( (v5 & 0x40) != 0 )
  {
    v5 &= ~0x40u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v93);
  }
  if ( v24 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3418;
      v82 = 3;
      v83 = L"CLUS";
      v25 = Cluster::NodeNetworkName::GetResourceName(a1, v94);
      v5 |= 0x80u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Volume ID property. resName:%?",
        v25);
    }
    if ( (v5 & 0x80u) != 0 )
    {
      v5 &= ~0x80u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v94);
    }
    v26 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v27,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3421,
                                               v26,
                                               0);
  }
  if ( ResourceProperties )
    goto LABEL_68;
  if ( !(unsigned int)Guid::StringToGuid(&v113, (char *)a2 + 84) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3425;
      v82 = 3;
      v83 = L"CLUS";
      v28 = Cluster::NodeNetworkName::GetResourceName(a1, v95);
      v5 |= 0x100u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) The resource's Volume ID property contains an invalid GUID value. resName:%? propVal:%?",
        v28,
        &v113);
    }
    if ( (v5 & 0x100) != 0 )
    {
      v5 &= ~0x100u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v95);
    }
    v29 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v30,
                                               9231,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3429,
                                               v29,
                                               0);
    if ( ResourceProperties )
      goto LABEL_68;
  }
  v31 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v96, L"Member ID");
  v5 |= 0x200u;
  v32 = 1;
  if ( (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v31, &v113) )
LABEL_68:
    v32 = 0;
  if ( (v5 & 0x200) != 0 )
  {
    v5 &= ~0x200u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v96);
  }
  if ( v32 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3437;
      v82 = 3;
      v83 = L"CLUS";
      v33 = Cluster::NodeNetworkName::GetResourceName(a1, v97);
      v5 |= 0x400u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Member ID property. resName:%?",
        v33);
    }
    if ( (v5 & 0x400) != 0 )
    {
      v5 &= ~0x400u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v97);
    }
    v34 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v35,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3440,
                                               v34,
                                               0);
  }
  if ( ResourceProperties )
    goto LABEL_89;
  if ( !(unsigned int)Guid::StringToGuid(&v113, (char *)a2 + 100) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3444;
      v82 = 3;
      v83 = L"CLUS";
      v36 = Cluster::NodeNetworkName::GetResourceName(a1, v98);
      v5 |= 0x800u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) The resource's Member ID property contains an invalid GUID value. resName:%? propVal:%?",
        v36,
        &v113);
    }
    if ( (v5 & 0x800) != 0 )
    {
      v5 &= ~0x800u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v98);
    }
    v37 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v38,
                                               9231,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3448,
                                               v37,
                                               0);
    if ( ResourceProperties )
      goto LABEL_89;
  }
  v39 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v99, L"Replicated Folder Root Path");
  v5 |= 0x1000u;
  v40 = 1;
  if ( (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v39, a2) )
LABEL_89:
    v40 = 0;
  if ( (v5 & 0x1000) != 0 )
  {
    v5 &= ~0x1000u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v99);
  }
  if ( v40 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3456;
      v82 = 3;
      v83 = L"CLUS";
      v41 = Cluster::NodeNetworkName::GetResourceName(a1, v100);
      v5 |= 0x2000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Path property. resName:%?",
        v41);
    }
    if ( (v5 & 0x2000) != 0 )
    {
      v5 &= ~0x2000u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v100);
    }
    v42 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v43,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3459,
                                               v42,
                                               0);
  }
  if ( ResourceProperties
    || (v44 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v101, L"Replicated Folder Name"),
        v5 |= 0x4000u,
        v45 = 1,
        (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v44, (char *)a2 + 8)) )
  {
    v45 = 0;
  }
  if ( (v5 & 0x4000) != 0 )
  {
    v5 &= ~0x4000u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v101);
  }
  if ( v45 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3467;
      v82 = 3;
      v83 = L"CLUS";
      v46 = Cluster::NodeNetworkName::GetResourceName(a1, v102);
      v5 |= 0x8000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Name property. resName:%?",
        v46);
    }
    if ( (v5 & 0x8000) != 0 )
    {
      v5 &= ~0x8000u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v102);
    }
    v47 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v48,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3470,
                                               v47,
                                               0);
  }
  if ( ResourceProperties
    || (v49 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v103, L"Replication Group Name"),
        v5 |= 0x10000u,
        v50 = 1,
        (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v49, (char *)a2 + 32)) )
  {
    v50 = 0;
  }
  if ( (v5 & 0x10000) != 0 )
  {
    v5 &= ~0x10000u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v103);
  }
  if ( v50 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3478;
      v82 = 3;
      v83 = L"CLUS";
      v51 = Cluster::NodeNetworkName::GetResourceName(a1, v104);
      v5 |= 0x20000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replication Group Name property. resName:%?",
        v51);
    }
    if ( (v5 & 0x20000) != 0 )
    {
      v5 &= ~0x20000u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v104);
    }
    v52 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v53,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3481,
                                               v52,
                                               0);
  }
  if ( ResourceProperties
    || (v54 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v105, L"Staging Path"),
        v5 |= 0x40000u,
        v55 = 1,
        (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v54, (char *)a2 + 56)) )
  {
    v55 = 0;
  }
  if ( (v5 & 0x40000) != 0 )
  {
    v5 &= ~0x40000u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v105);
  }
  if ( v55 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3489;
      v82 = 3;
      v83 = L"CLUS";
      v56 = Cluster::NodeNetworkName::GetResourceName(a1, v106);
      v5 |= 0x80000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Staging Path property. resName:%?",
        v56);
    }
    if ( (v5 & 0x80000) != 0 )
    {
      v5 &= ~0x80000u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v106);
    }
    v57 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v58,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3492,
                                               v57,
                                               0);
  }
  if ( ResourceProperties
    || (v59 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v107, L"Conflict Path"),
        v5 |= 0x100000u,
        v60 = 1,
        (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v85, v59, (char *)a2 + 64)) )
  {
    v60 = 0;
  }
  if ( (v5 & 0x100000) != 0 )
  {
    v5 &= ~0x100000u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v107);
  }
  if ( v60 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3500;
      v82 = 3;
      v83 = L"CLUS";
      v61 = Cluster::NodeNetworkName::GetResourceName(a1, v108);
      v5 |= 0x200000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Conflict Path property. resName:%?",
        v61);
    }
    if ( (v5 & 0x200000) != 0 )
    {
      v5 &= ~0x200000u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v108);
    }
    v62 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v63,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3503,
                                               v62,
                                               0);
  }
  if ( ResourceProperties
    || (v64 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v109, L"Replicated Folder Flags"),
        v5 |= 0x400000u,
        v65 = 1,
        (unsigned int)Cluster::ResourcePrivatePropertyList::GetDwordPropertyValue(&v85, v64, (char *)a2 + 80)) )
  {
    v65 = 0;
  }
  if ( (v5 & 0x400000) != 0 )
  {
    v5 &= ~0x400000u;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v109);
  }
  if ( v65 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3511;
      v82 = 3;
      v83 = L"CLUS";
      v66 = Cluster::NodeNetworkName::GetResourceName(a1, v110);
      v5 |= 0x800000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder Flags property. resName:%?",
        v66);
    }
    if ( (v5 & 0x800000) != 0 )
    {
      v5 &= ~0x800000u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v110);
    }
    v67 = GetCurrentThreadId();
    ResourceProperties = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v68,
                                               9230,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                               "Cluster::ClusterUtil::GetDfsrResourceProperties",
                                               3514,
                                               v67,
                                               0);
  }
  if ( ResourceProperties )
    goto LABEL_185;
  Cluster::NodeNetworkNameList::NodeNetworkNameList((Cluster::NodeNetworkNameList *)&v111);
  ResourceProperties = Cluster::ClusterResource::GetResourceNetworkNames(
                         a1,
                         (struct Cluster::NodeNetworkNameList *)&v111);
  if ( ResourceProperties )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3545;
      v82 = 3;
      v83 = L"CLUS";
      v73 = Cluster::NodeNetworkName::GetResourceName(a1, v84);
      v5 |= 0x2000000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to query the resource's VCO Resource List. resName:%?",
        v73);
    }
    if ( (v5 & 0x2000000) != 0 )
      FrsStringImpl<char,unsigned short>::ReleaseBody(v84);
    v79 = GetCurrentThreadId();
    v72 = FrsStatusList::PushNewError(
            v74,
            9230,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
            "Cluster::ClusterUtil::GetDfsrResourceProperties",
            3548,
            v79,
            0);
  }
  else
  {
    if ( (unsigned int)((__int64)(v112[1] - v112[0]) >> 5) == 1 )
    {
      ObjList<Cluster::NodeNetworkName>::GetAt(&v111, &v80, 0);
      v69 = Cluster::NodeNetworkName::GetResourceName(&v80, v84);
      FrsStringImpl<unsigned short,char>::Set((char *)a2 + 72, v69);
      FrsStringImpl<char,unsigned short>::ReleaseBody(v84);
      Cluster::NodeNetworkName::~NodeNetworkName((Cluster::NodeNetworkName *)&v80);
      goto LABEL_184;
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v80 = L"Cluster::ClusterUtil::GetDfsrResourceProperties";
      v81 = 3538;
      v82 = 3;
      v83 = L"CLUS";
      v70 = Cluster::NodeNetworkName::GetResourceName(a1, v84);
      v5 |= 0x1000000u;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v80,
        L"[CLUSTER] (Ignored) Failed to retrieve the resource's VCO Resource Name. resName:%?",
        v70);
    }
    if ( (v5 & 0x1000000) != 0 )
      FrsStringImpl<char,unsigned short>::ReleaseBody(v84);
    v78 = GetCurrentThreadId();
    v72 = FrsStatusList::PushNewError(
            v71,
            9231,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
            "Cluster::ClusterUtil::GetDfsrResourceProperties",
            3541,
            v78,
            0);
  }
  ResourceProperties = (struct FrsStatus *)v72;
LABEL_184:
  v111 = &ObjList<Cluster::NodeNetworkName>::`vftable';
  std::vector<Cluster::NodeNetworkName>::_Tidy(v112);
  if ( ResourceProperties )
  {
LABEL_185:
    Cluster::DfsrResourcePropertyList::ClearAll(a2);
    v75 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v76,
           *((unsigned int *)ResourceProperties + 1),
           *((unsigned int *)ResourceProperties + 2),
           *(unsigned int *)ResourceProperties,
           "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
           "Cluster::ClusterUtil::GetDfsrResourceProperties",
           3559,
           v75,
           ResourceProperties);
  }
  v85 = &ObjList<Cluster::ResourcePrivateProperty>::`vftable';
  std::vector<Cluster::ResourcePrivateProperty>::_Tidy(v86);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v113);
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x1401d2e94  mov     [rsp-8+arg_0], rbx
0x1401d2e99  push    rbp
0x1401d2e9a  push    rsi
0x1401d2e9b  push    rdi
0x1401d2e9c  push    r12
0x1401d2e9e  push    r13
0x1401d2ea0  push    r14
0x1401d2ea2  push    r15
0x1401d2ea4  lea     rbp, [rsp-80h]
0x1401d2ea9  sub     rsp, 180h
0x1401d2eb0  mov     r13, rdx
0x1401d2eb3  mov     r15, rcx
0x1401d2eb6  xor     edi, edi
0x1401d2eb8  mov     ebx, edi
0x1401d2eba  mov     [rbp+0B0h+arg_10], ebx
0x1401d2ec0  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d2ec7  mov     [rbp+0B0h+arg_18], rax
0x1401d2ece  cmp     cs:byte_140315A80, dil
0x1401d2ed5  jnz     short loc_1401D2EE4
0x1401d2ed7  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401d2ede  mov     ebx, [rbp+0B0h+arg_10]
0x1401d2ee4  lea     rcx, [rsp+1B0h+var_138]; this
0x1401d2ee9  call    ??0ResourcePrivatePropertyList@Cluster@@QEAA@XZ; Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList(void)
0x1401d2eee  nop
0x1401d2eef  mov     rcx, r13; this
0x1401d2ef2  call    ?ClearAll@DfsrResourcePropertyList@Cluster@@QEAAXXZ; Cluster::DfsrResourcePropertyList::ClearAll(void)
0x1401d2ef7  lea     rdx, [rsp+1B0h+var_138]; struct Cluster::ResourcePrivatePropertyList *
0x1401d2efc  mov     rcx, r15; this
0x1401d2eff  call    ?GetResourceProperties@ClusterResource@Cluster@@QEBAPEAVFrsStatus@@AEAVResourcePrivatePropertyList@2@@Z; Cluster::ClusterResource::GetResourceProperties(Cluster::ResourcePrivatePropertyList &)
0x1401d2f04  mov     rsi, rax
0x1401d2f07  test    rax, rax
0x1401d2f0a  jnz     short loc_1401D2F3A
0x1401d2f0c  lea     rdx, aReplicatedFold_2; "Replicated Folder ID"
0x1401d2f13  lea     rcx, [rbp+0B0h+var_118]
0x1401d2f17  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d2f1c  lea     ebx, [rsi+1]
0x1401d2f1f  lea     r8, [rbp+0B0h+arg_18]
0x1401d2f26  mov     rdx, rax
0x1401d2f29  lea     rcx, [rsp+1B0h+var_138]
0x1401d2f2e  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x1401d2f33  test    eax, eax
0x1401d2f35  mov     r14b, bl
0x1401d2f38  jz      short loc_1401D2F3D
0x1401d2f3a  mov     r14b, dil
0x1401d2f3d  test    bl, 1
0x1401d2f40  jz      short loc_1401D2F4E
0x1401d2f42  and     ebx, 0FFFFFFFEh
0x1401d2f45  lea     rcx, [rbp+0B0h+var_118]
0x1401d2f49  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d2f4e  mov     r12d, 3
0x1401d2f54  lea     rcx, aClusterCluster_9; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d2f5b  lea     rdx, aClus; "CLUS"
0x1401d2f62  test    r14b, r14b
0x1401d2f65  jz      loc_1401D301F
0x1401d2f6b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d2f72  test    rax, rax
0x1401d2f75  jz      short loc_1401D2FC4
0x1401d2f77  cmp     [rax+40h], edi
0x1401d2f7a  jz      short loc_1401D2FC4
0x1401d2f7c  cmp     [rax+38h], r12d
0x1401d2f80  jl      short loc_1401D2FC4
0x1401d2f82  mov     [rsp+1B0h+var_160], rcx
0x1401d2f87  mov     [rsp+1B0h+var_158], 0D34h
0x1401d2f8f  mov     [rsp+1B0h+var_154], r12d
0x1401d2f94  mov     [rsp+1B0h+var_150], rdx
0x1401d2f99  lea     rdx, [rbp+0B0h+var_110]
0x1401d2f9d  mov     rcx, r15
0x1401d2fa0  call    ?GetResourceName@NodeNetworkName@Cluster@@QEAA?AV?$FrsStringImpl@GD@@XZ; Cluster::NodeNetworkName::GetResourceName(void)
0x1401d2fa5  nop
0x1401d2fa6  or      ebx, 2
0x1401d2fa9  mov     [rbp+0B0h+arg_10], ebx
0x1401d2faf  mov     r8, rax
0x1401d2fb2  lea     rdx, aClusterIgnored_32; "[CLUSTER] (Ignored) Failed to retrieve "...
0x1401d2fb9  lea     rcx, [rsp+1B0h+var_160]
0x1401d2fbe  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d2fc3  nop
0x1401d2fc4  test    bl, 2
0x1401d2fc7  jz      short loc_1401D2FD5
0x1401d2fc9  and     ebx, 0FFFFFFFDh
0x1401d2fcc  lea     rcx, [rbp+0B0h+var_110]
0x1401d2fd0  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d2fd5  call    cs:__imp_GetCurrentThreadId
0x1401d2fdc  nop     dword ptr [rax+rax+00h]
0x1401d2fe1  mov     [rsp+1B0h+var_170], rdi
0x1401d2fe6  mov     [rsp+1B0h+var_178], eax
0x1401d2fea  mov     [rsp+1B0h+var_180], 0D37h
0x1401d2ff2  lea     r14, aClusterCluster_37; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d2ff9  mov     [rsp+1B0h+var_188], r14
0x1401d2ffe  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d3005  mov     [rsp+1B0h+var_190], rax
0x1401d300a  mov     r9d, r12d
0x1401d300d  xor     r8d, r8d
0x1401d3010  mov     edx, 240Eh
0x1401d3015  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d301a  mov     rsi, rax
0x1401d301d  jmp     short loc_1401D3026
0x1401d301f  lea     r14, aClusterCluster_37; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d3026  test    rsi, rsi
0x1401d3029  jnz     loc_1401D313A
0x1401d302f  lea     rdx, [r13+10h]
0x1401d3033  lea     rcx, [rbp+0B0h+arg_18]
0x1401d303a  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1401d303f  test    eax, eax
0x1401d3041  jnz     loc_1401D310C
0x1401d3047  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d304e  test    rax, rax
0x1401d3051  jz      short loc_1401D30B5
0x1401d3053  cmp     [rax+40h], edi
0x1401d3056  jz      short loc_1401D30B5
0x1401d3058  cmp     [rax+38h], r12d
0x1401d305c  jl      short loc_1401D30B5
0x1401d305e  lea     rax, aClusterCluster_9; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d3065  mov     [rsp+1B0h+var_160], rax
0x1401d306a  mov     [rsp+1B0h+var_158], 0D3Bh
0x1401d3072  mov     [rsp+1B0h+var_154], r12d
0x1401d3077  lea     rax, aClus; "CLUS"
0x1401d307e  mov     [rsp+1B0h+var_150], rax
0x1401d3083  lea     rdx, [rbp+0B0h+var_108]
0x1401d3087  mov     rcx, r15
0x1401d308a  call    ?GetResourceName@NodeNetworkName@Cluster@@QEAA?AV?$FrsStringImpl@GD@@XZ; Cluster::NodeNetworkName::GetResourceName(void)
0x1401d308f  nop
0x1401d3090  or      ebx, 4
0x1401d3093  mov     [rbp+0B0h+arg_10], ebx
0x1401d3099  lea     r9, [rbp+0B0h+arg_18]
0x1401d30a0  mov     r8, rax
0x1401d30a3  lea     rdx, aClusterIgnored_26; "[CLUSTER] (Ignored) The resource's Repl"...
0x1401d30aa  lea     rcx, [rsp+1B0h+var_160]
0x1401d30af  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@1@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1401d30b4  nop
0x1401d30b5  test    bl, 4
0x1401d30b8  jz      short loc_1401D30C6
0x1401d30ba  and     ebx, 0FFFFFFFBh
0x1401d30bd  lea     rcx, [rbp+0B0h+var_108]
0x1401d30c1  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d30c6  call    cs:__imp_GetCurrentThreadId
0x1401d30cd  nop     dword ptr [rax+rax+00h]
0x1401d30d2  mov     [rsp+1B0h+var_170], rdi
0x1401d30d7  mov     [rsp+1B0h+var_178], eax
0x1401d30db  mov     [rsp+1B0h+var_180], 0D3Fh
0x1401d30e3  mov     [rsp+1B0h+var_188], r14
0x1401d30e8  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d30ef  mov     [rsp+1B0h+var_190], rax
0x1401d30f4  mov     r9d, r12d
0x1401d30f7  xor     r8d, r8d
0x1401d30fa  mov     edx, 240Fh
0x1401d30ff  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d3104  mov     rsi, rax
0x1401d3107  test    rax, rax
0x1401d310a  jnz     short loc_1401D313A
0x1401d310c  lea     rdx, aReplicationGro_2; "Replication Group ID"
0x1401d3113  lea     rcx, [rbp+0B0h+var_100]
0x1401d3117  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d311c  or      ebx, 8
0x1401d311f  lea     r8, [rbp+0B0h+arg_18]
0x1401d3126  mov     rdx, rax
0x1401d3129  lea     rcx, [rsp+1B0h+var_138]
0x1401d312e  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x1401d3133  test    eax, eax
0x1401d3135  mov     r14b, 1
0x1401d3138  jz      short loc_1401D313D
0x1401d313a  mov     r14b, dil
0x1401d313d  test    bl, 8
0x1401d3140  jz      short loc_1401D314E
0x1401d3142  and     ebx, 0FFFFFFF7h
0x1401d3145  lea     rcx, [rbp+0B0h+var_100]
0x1401d3149  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d314e  test    r14b, r14b
0x1401d3151  jz      loc_1401D3219
0x1401d3157  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d315e  test    rax, rax
0x1401d3161  jz      short loc_1401D31BE
0x1401d3163  cmp     [rax+40h], edi
0x1401d3166  jz      short loc_1401D31BE
0x1401d3168  cmp     [rax+38h], r12d
0x1401d316c  jl      short loc_1401D31BE
0x1401d316e  lea     rax, aClusterCluster_9; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d3175  mov     [rsp+1B0h+var_160], rax
0x1401d317a  mov     [rsp+1B0h+var_158], 0D47h
0x1401d3182  mov     [rsp+1B0h+var_154], r12d
0x1401d3187  lea     rax, aClus; "CLUS"
0x1401d318e  mov     [rsp+1B0h+var_150], rax
0x1401d3193  lea     rdx, [rbp+0B0h+var_F8]
0x1401d3197  mov     rcx, r15
0x1401d319a  call    ?GetResourceName@NodeNetworkName@Cluster@@QEAA?AV?$FrsStringImpl@GD@@XZ; Cluster::NodeNetworkName::GetResourceName(void)
0x1401d319f  nop
0x1401d31a0  or      ebx, 10h
0x1401d31a3  mov     [rbp+0B0h+arg_10], ebx
0x1401d31a9  mov     r8, rax
0x1401d31ac  lea     rdx, aClusterIgnored_45; "[CLUSTER] (Ignored) Failed to retrieve "...
0x1401d31b3  lea     rcx, [rsp+1B0h+var_160]
0x1401d31b8  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401d31bd  nop
0x1401d31be  test    bl, 10h
0x1401d31c1  jz      short loc_1401D31CF
0x1401d31c3  and     ebx, 0FFFFFFEFh
0x1401d31c6  lea     rcx, [rbp+0B0h+var_F8]
0x1401d31ca  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d31cf  call    cs:__imp_GetCurrentThreadId
0x1401d31d6  nop     dword ptr [rax+rax+00h]
0x1401d31db  mov     [rsp+1B0h+var_170], rdi
0x1401d31e0  mov     [rsp+1B0h+var_178], eax
0x1401d31e4  mov     [rsp+1B0h+var_180], 0D4Ah
0x1401d31ec  lea     r14, aClusterCluster_37; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d31f3  mov     [rsp+1B0h+var_188], r14
0x1401d31f8  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d31ff  mov     [rsp+1B0h+var_190], rax
0x1401d3204  mov     r9d, r12d
0x1401d3207  xor     r8d, r8d
0x1401d320a  mov     edx, 240Eh
0x1401d320f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d3214  mov     rsi, rax
0x1401d3217  jmp     short loc_1401D3220
0x1401d3219  lea     r14, aClusterCluster_37; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d3220  test    rsi, rsi
0x1401d3223  jnz     loc_1401D3334
0x1401d3229  lea     rdx, [r13+28h]
0x1401d322d  lea     rcx, [rbp+0B0h+arg_18]
0x1401d3234  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1401d3239  test    eax, eax
0x1401d323b  jnz     loc_1401D3306
0x1401d3241  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d3248  test    rax, rax
0x1401d324b  jz      short loc_1401D32AF
0x1401d324d  cmp     [rax+40h], edi
0x1401d3250  jz      short loc_1401D32AF
0x1401d3252  cmp     [rax+38h], r12d
0x1401d3256  jl      short loc_1401D32AF
0x1401d3258  lea     rax, aClusterCluster_9; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d325f  mov     [rsp+1B0h+var_160], rax
0x1401d3264  mov     [rsp+1B0h+var_158], 0D4Eh
0x1401d326c  mov     [rsp+1B0h+var_154], r12d
0x1401d3271  lea     rax, aClus; "CLUS"
0x1401d3278  mov     [rsp+1B0h+var_150], rax
0x1401d327d  lea     rdx, [rbp+0B0h+var_F0]
0x1401d3281  mov     rcx, r15
0x1401d3284  call    ?GetResourceName@NodeNetworkName@Cluster@@QEAA?AV?$FrsStringImpl@GD@@XZ; Cluster::NodeNetworkName::GetResourceName(void)
0x1401d3289  nop
0x1401d328a  or      ebx, 20h
0x1401d328d  mov     [rbp+0B0h+arg_10], ebx
0x1401d3293  lea     r9, [rbp+0B0h+arg_18]
0x1401d329a  mov     r8, rax
0x1401d329d  lea     rdx, aClusterIgnored_2; "[CLUSTER] (Ignored) The resource's Repl"...
0x1401d32a4  lea     rcx, [rsp+1B0h+var_160]
0x1401d32a9  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@1@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1401d32ae  nop
0x1401d32af  test    bl, 20h
0x1401d32b2  jz      short loc_1401D32C0
0x1401d32b4  and     ebx, 0FFFFFFDFh
0x1401d32b7  lea     rcx, [rbp+0B0h+var_F0]
0x1401d32bb  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d32c0  call    cs:__imp_GetCurrentThreadId
0x1401d32c7  nop     dword ptr [rax+rax+00h]
0x1401d32cc  mov     [rsp+1B0h+var_170], rdi
0x1401d32d1  mov     [rsp+1B0h+var_178], eax
0x1401d32d5  mov     [rsp+1B0h+var_180], 0D52h
0x1401d32dd  mov     [rsp+1B0h+var_188], r14
0x1401d32e2  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d32e9  mov     [rsp+1B0h+var_190], rax
0x1401d32ee  mov     r9d, r12d
0x1401d32f1  xor     r8d, r8d
0x1401d32f4  mov     edx, 240Fh
0x1401d32f9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d32fe  mov     rsi, rax
0x1401d3301  test    rax, rax
0x1401d3304  jnz     short loc_1401D3334
0x1401d3306  lea     rdx, aVolumeId; "Volume ID"
0x1401d330d  lea     rcx, [rbp+0B0h+var_E8]
0x1401d3311  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d3316  or      ebx, 40h
0x1401d3319  lea     r8, [rbp+0B0h+arg_18]
0x1401d3320  mov     rdx, rax
0x1401d3323  lea     rcx, [rsp+1B0h+var_138]
0x1401d3328  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x1401d332d  test    eax, eax
0x1401d332f  mov     r14b, 1
0x1401d3332  jz      short loc_1401D3337
0x1401d3334  mov     r14b, dil
0x1401d3337  test    bl, 40h
0x1401d333a  jz      short loc_1401D3348
0x1401d333c  and     ebx, 0FFFFFFBFh
0x1401d333f  lea     rcx, [rbp+0B0h+var_E8]
0x1401d3343  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d3348  test    r14b, r14b
0x1401d334b  jz      loc_1401D3414
0x1401d3351  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d3358  test    rax, rax
0x1401d335b  jz      short loc_1401D33B9
0x1401d335d  cmp     [rax+40h], edi
0x1401d3360  jz      short loc_1401D33B9
0x1401d3362  cmp     [rax+38h], r12d
0x1401d3366  jl      short loc_1401D33B9
0x1401d3368  lea     rax, aClusterCluster_9; "Cluster::ClusterUtil::GetDfsrResourcePr"...
0x1401d336f  mov     [rsp+1B0h+var_160], rax
0x1401d3374  mov     [rsp+1B0h+var_158], 0D5Ah
0x1401d337c  mov     [rsp+1B0h+var_154], r12d
0x1401d3381  lea     rax, aClus; "CLUS"
0x1401d3388  mov     [rsp+1B0h+var_150], rax
0x1401d338d  lea     rdx, [rbp+0B0h+var_E0]
0x1401d3391  mov     rcx, r15
0x1401d3394  call    ?GetResourceName@NodeNetworkName@Cluster@@QEAA?AV?$FrsStringImpl@GD@@XZ; Cluster::NodeNetworkName::GetResourceName(void)
  ... truncated ...
```
