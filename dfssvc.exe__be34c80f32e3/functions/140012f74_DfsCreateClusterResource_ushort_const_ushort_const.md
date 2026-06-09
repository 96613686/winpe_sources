# DfsCreateClusterResource(ushort const *,ushort const *)

- ea: `0x140012f74`
- end: `0x140013294`
- name: `?DfsCreateClusterResource@@YAKPEBG0@Z`
- size: `800`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010924`

## callees

- `0x140012f74`
- `0x14001329c`
- `0x140014364`
- `0x1400144ac`
- `0x140014614`
- `0x14001473c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400130d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400130d2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14001314b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14001314b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400131f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400131f7`
- `CLUSAPI!CloseClusterResource` at `0x14001320b`
- `CLUSAPI!CloseClusterResource` at `0x140013220`
- `CLUSAPI!CloseClusterResource` at `0x140013234`
- `CLUSAPI!CloseClusterResource` at `0x14001320b`
- `CLUSAPI!CloseClusterResource` at `0x140013220`
- `CLUSAPI!CloseClusterResource` at `0x140013234`
- `CLUSAPI!CloseCluster` at `0x14001325c`
- `CLUSAPI!CloseCluster` at `0x14001325c`
- `CLUSAPI!OpenCluster` at `0x140013005`
- `CLUSAPI!OpenCluster` at `0x140013005`
- `CLUSAPI!CloseClusterGroup` at `0x140013248`
- `CLUSAPI!CloseClusterGroup` at `0x140013248`
- `CLUSAPI!CreateClusterResource` at `0x1400130be`
- `CLUSAPI!CreateClusterResource` at `0x1400130be`
- `CLUSAPI!AddClusterResourceDependency` at `0x1400130eb`
- `CLUSAPI!AddClusterResourceDependency` at `0x140013108`
- `CLUSAPI!AddClusterResourceDependency` at `0x1400130eb`
- `CLUSAPI!AddClusterResourceDependency` at `0x140013108`
- `CLUSAPI!OnlineClusterResource` at `0x14001317b`
- `CLUSAPI!OnlineClusterResource` at `0x14001317b`
- `CLUSAPI!OfflineClusterResource` at `0x1400131b1`
- `CLUSAPI!OfflineClusterResource` at `0x1400131b1`
- `CLUSAPI!DeleteClusterResource` at `0x1400131d6`
- `CLUSAPI!DeleteClusterResource` at `0x1400131d6`
- `netutils!NetApiBufferFree` at `0x140013271`
- `netutils!NetApiBufferFree` at `0x140013271`
- `srvcli!NetShareGetInfo` at `0x140013040`
- `srvcli!NetShareGetInfo` at `0x140013040`

## pseudocode

```c
__int64 __fastcall DfsCreateClusterResource(unsigned __int16 *a1, WCHAR *a2)
{
  struct _HRESOURCE *v3; // r14
  struct _HRESOURCE *v4; // rdi
  struct _HGROUP *v5; // rsi
  struct _HCLUSTER *v6; // r13
  WCHAR *v7; // r15
  DWORD IsCluster; // ebx
  const unsigned __int16 *v9; // rsi
  unsigned int ResourceHandlesForPath; // eax
  unsigned int DfsResourceName; // eax
  struct _HRESOURCE *ClusterResource; // rax
  struct RESUTIL_PROPERTY_ITEM *v13; // rdx
  unsigned int v14; // r9d
  DWORD v15; // eax
  DWORD v16; // eax
  LPCWSTR lpszResourceName; // [rsp+30h] [rbp-39h] BYREF
  HRESOURCE hDependsOn; // [rsp+38h] [rbp-31h] BYREF
  HRESOURCE hResource; // [rsp+40h] [rbp-29h] BYREF
  __int128 v21; // [rsp+48h] [rbp-21h] BYREF
  __int128 v22; // [rsp+58h] [rbp-11h]
  __int128 v23; // [rsp+68h] [rbp-1h]
  unsigned __int8 v24; // [rsp+D0h] [rbp+67h] BYREF
  LPWSTR netname; // [rsp+D8h] [rbp+6Fh]
  LPBYTE bufptr; // [rsp+E0h] [rbp+77h] BYREF
  HGROUP hGroup; // [rsp+E8h] [rbp+7Fh] BYREF

  netname = a2;
  v24 = 0;
  v3 = 0;
  bufptr = 0;
  v4 = 0;
  hDependsOn = 0;
  v5 = 0;
  hResource = 0;
  v6 = 0;
  hGroup = 0;
  v7 = 0;
  lpszResourceName = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( a1 && a2 )
  {
    IsCluster = DfsNodeIsCluster(a1, &v24);
    if ( IsCluster )
      goto LABEL_36;
    if ( !v24 )
    {
      IsCluster = 50;
      goto LABEL_36;
    }
    v6 = OpenCluster(a1);
    if ( !v6 )
    {
      IsCluster = GetLastError();
      goto LABEL_36;
    }
    v9 = netname;
    IsCluster = NetShareGetInfo(a1, netname, 0x1F6u, &bufptr);
    if ( IsCluster )
      goto LABEL_35;
    ResourceHandlesForPath = DfsGetResourceHandlesForPath(
                               a1,
                               *((const unsigned __int16 **)bufptr + 5),
                               v6,
                               &hDependsOn,
                               &hResource,
                               &hGroup);
    v3 = hDependsOn;
    IsCluster = ResourceHandlesForPath;
    if ( ResourceHandlesForPath )
    {
      v5 = hGroup;
      goto LABEL_26;
    }
    DfsResourceName = DfsCreateDfsResourceName(hDependsOn, v9, (unsigned __int16 **)&lpszResourceName);
    v7 = (WCHAR *)lpszResourceName;
    IsCluster = DfsResourceName;
    v5 = hGroup;
    if ( !DfsResourceName )
    {
      ClusterResource = CreateClusterResource(hGroup, lpszResourceName, L"Distributed File System", 0);
      v4 = ClusterResource;
      if ( ClusterResource )
      {
        IsCluster = AddClusterResourceDependency(ClusterResource, v3);
        if ( !IsCluster )
        {
          IsCluster = AddClusterResourceDependency(v4, hResource);
          if ( !IsCluster )
          {
            *(_QWORD *)&v21 = netname;
            DWORD2(v22) = *((_DWORD *)bufptr + 7);
            HIDWORD(v22) = 1;
            *((_QWORD *)&v21 + 1) = *((_QWORD *)bufptr + 5);
            *(_QWORD *)&v23 = *((_QWORD *)bufptr + 8);
            DWORD2(v23) = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)bufptr + 8));
            *(_QWORD *)&v22 = *((_QWORD *)bufptr + 2);
            IsCluster = DfsSetProperties(v4, v13, &v21, v14);
            if ( !IsCluster )
            {
              v15 = OnlineClusterResource(v4);
              IsCluster = v15;
              if ( !v15 || v15 == 997 )
              {
                IsCluster = DfsWaitResourceState(v4, ClusterResourceOnline);
                if ( IsCluster == 1460 )
                {
                  v16 = OfflineClusterResource(v4);
                  if ( !v16 || v16 == 997 )
                  {
                    DfsWaitResourceState(v4, ClusterResourceOffline);
                    DeleteClusterResource(v4);
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        IsCluster = GetLastError();
      }
    }
  }
  else
  {
    IsCluster = 87;
  }
  if ( v7 )
    LocalFree(v7);
LABEL_26:
  if ( v3 )
    CloseClusterResource(v3);
  if ( hResource )
    CloseClusterResource(hResource);
  if ( v4 )
    CloseClusterResource(v4);
  if ( v5 )
    CloseClusterGroup(v5);
  if ( v6 )
LABEL_35:
    CloseCluster(v6);
LABEL_36:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return IsCluster;
}

```

## disassembly

```asm
0x140012f74  mov     [rsp-8+netname], rdx
0x140012f79  push    rbp
0x140012f7a  push    rbx
0x140012f7b  push    rsi
0x140012f7c  push    rdi
0x140012f7d  push    r12
0x140012f7f  push    r13
0x140012f81  push    r14
0x140012f83  push    r15
0x140012f85  lea     rbp, [rsp-1Fh]
0x140012f8a  sub     rsp, 88h
0x140012f91  xorps   xmm0, xmm0
0x140012f94  mov     r12, rcx
0x140012f97  xor     ecx, ecx
0x140012f99  mov     rax, rdx
0x140012f9c  mov     [rbp+57h+arg_0], cl
0x140012f9f  mov     r14d, ecx
0x140012fa2  mov     [rbp+57h+bufptr], rcx
0x140012fa6  mov     edi, ecx
0x140012fa8  mov     [rbp+57h+hDependsOn], rcx
0x140012fac  mov     esi, ecx
0x140012fae  mov     [rbp+57h+hResource], rcx
0x140012fb2  mov     r13d, ecx
0x140012fb5  mov     [rbp+57h+hGroup], rcx
0x140012fb9  mov     r15d, ecx
0x140012fbc  mov     [rbp+57h+lpszResourceName], rcx
0x140012fc0  movups  [rbp+57h+var_78], xmm0
0x140012fc4  movups  [rbp+57h+var_68], xmm0
0x140012fc8  movups  [rbp+57h+var_58], xmm0
0x140012fcc  test    r12, r12
0x140012fcf  jz      loc_1400131EA
0x140012fd5  test    rax, rax
0x140012fd8  jz      loc_1400131EA
0x140012fde  lea     rdx, [rbp+57h+arg_0]; unsigned __int8 *
0x140012fe2  mov     rcx, r12; unsigned __int16 *
0x140012fe5  call    ?DfsNodeIsCluster@@YAKPEBGPEAE@Z; DfsNodeIsCluster(ushort const *,uchar *)
0x140012fea  mov     ebx, eax
0x140012fec  test    eax, eax
0x140012fee  jnz     loc_140013268
0x140012ff4  cmp     [rbp+57h+arg_0], sil
0x140012ff8  jnz     short loc_140013002
0x140012ffa  lea     ebx, [rax+32h]
0x140012ffd  jmp     loc_140013268
0x140013002  mov     rcx, r12; lpszClusterName
0x140013005  call    cs:__imp_OpenCluster
0x14001300c  nop     dword ptr [rax+rax+00h]
0x140013011  mov     r13, rax
0x140013014  test    rax, rax
0x140013017  jnz     short loc_14001302C
0x140013019  call    cs:__imp_GetLastError
0x140013020  nop     dword ptr [rax+rax+00h]
0x140013025  mov     ebx, eax
0x140013027  jmp     loc_140013268
0x14001302c  mov     rsi, [rbp+57h+netname]
0x140013030  lea     r9, [rbp+57h+bufptr]; bufptr
0x140013034  mov     rdx, rsi; netname
0x140013037  mov     r8d, 1F6h; level
0x14001303d  mov     rcx, r12; servername
0x140013040  call    cs:__imp_NetShareGetInfo
0x140013047  nop     dword ptr [rax+rax+00h]
0x14001304c  mov     ebx, eax
0x14001304e  test    eax, eax
0x140013050  jnz     loc_140013259
0x140013056  mov     rdx, [rbp+57h+bufptr]
0x14001305a  lea     rax, [rbp+57h+hGroup]
0x14001305e  mov     [rsp+0C0h+var_98], rax; struct _HGROUP **
0x140013063  lea     r9, [rbp+57h+hDependsOn]; struct _HRESOURCE **
0x140013067  lea     rax, [rbp+57h+hResource]
0x14001306b  mov     r8, r13; hCluster
0x14001306e  mov     rcx, r12; unsigned __int16 *
0x140013071  mov     [rsp+0C0h+var_A0], rax; struct _HRESOURCE **
0x140013076  mov     rdx, [rdx+28h]; lpInBuffer
0x14001307a  call    ?DfsGetResourceHandlesForPath@@YAKPEBG0PEAU_HCLUSTER@@PEAPEAU_HRESOURCE@@2PEAPEAU_HGROUP@@@Z; DfsGetResourceHandlesForPath(ushort const *,ushort const *,_HCLUSTER *,_HRESOURCE * *,_HRESOURCE * *,_HGROUP * *)
0x14001307f  mov     r14, [rbp+57h+hDependsOn]
0x140013083  mov     ebx, eax
0x140013085  test    eax, eax
0x140013087  jnz     loc_1400131E4
0x14001308d  lea     r8, [rbp+57h+lpszResourceName]; unsigned __int16 **
0x140013091  mov     rdx, rsi; unsigned __int16 *
0x140013094  mov     rcx, r14; struct _HRESOURCE *
0x140013097  call    ?DfsCreateDfsResourceName@@YAKPEAU_HRESOURCE@@PEBGPEAPEAG@Z; DfsCreateDfsResourceName(_HRESOURCE *,ushort const *,ushort * *)
0x14001309c  mov     r15, [rbp+57h+lpszResourceName]
0x1400130a0  mov     ebx, eax
0x1400130a2  mov     rsi, [rbp+57h+hGroup]
0x1400130a6  test    eax, eax
0x1400130a8  jnz     loc_1400131EF
0x1400130ae  xor     r9d, r9d; dwFlags
0x1400130b1  lea     r8, szResTypeName; "Distributed File System"
0x1400130b8  mov     rdx, r15; lpszResourceName
0x1400130bb  mov     rcx, rsi; hGroup
0x1400130be  call    cs:__imp_CreateClusterResource
0x1400130c5  nop     dword ptr [rax+rax+00h]
0x1400130ca  mov     rdi, rax
0x1400130cd  test    rax, rax
0x1400130d0  jnz     short loc_1400130E5
0x1400130d2  call    cs:__imp_GetLastError
0x1400130d9  nop     dword ptr [rax+rax+00h]
0x1400130de  mov     ebx, eax
0x1400130e0  jmp     loc_1400131EF
0x1400130e5  mov     rdx, r14; hDependsOn
0x1400130e8  mov     rcx, rdi; hResource
0x1400130eb  call    cs:__imp_AddClusterResourceDependency
0x1400130f2  nop     dword ptr [rax+rax+00h]
0x1400130f7  mov     ebx, eax
0x1400130f9  test    eax, eax
0x1400130fb  jnz     loc_1400131EF
0x140013101  mov     rdx, [rbp+57h+hResource]; hDependsOn
0x140013105  mov     rcx, rdi; hResource
0x140013108  call    cs:__imp_AddClusterResourceDependency
0x14001310f  nop     dword ptr [rax+rax+00h]
0x140013114  mov     ebx, eax
0x140013116  test    eax, eax
0x140013118  jnz     loc_1400131EF
0x14001311e  mov     rcx, [rbp+57h+bufptr]
0x140013122  mov     rax, [rbp+57h+netname]
0x140013126  mov     qword ptr [rbp+57h+var_78], rax
0x14001312a  mov     eax, [rcx+1Ch]
0x14001312d  mov     dword ptr [rbp+57h+var_68+8], eax
0x140013130  mov     dword ptr [rbp+57h+var_68+0Ch], 1
0x140013137  mov     rax, [rcx+28h]
0x14001313b  mov     qword ptr [rbp+57h+var_78+8], rax
0x14001313f  mov     rax, [rcx+40h]
0x140013143  mov     qword ptr [rbp+57h+var_58], rax
0x140013147  mov     rcx, [rcx+40h]; pSecurityDescriptor
0x14001314b  call    cs:__imp_GetSecurityDescriptorLength
0x140013152  nop     dword ptr [rax+rax+00h]
0x140013157  mov     dword ptr [rbp+57h+var_58+8], eax
0x14001315a  lea     r8, [rbp+57h+var_78]; void *
0x14001315e  mov     rax, [rbp+57h+bufptr]
0x140013162  mov     rcx, [rax+10h]
0x140013166  mov     qword ptr [rbp+57h+var_68], rcx
0x14001316a  mov     rcx, rdi; hResource
0x14001316d  call    ?DfsSetProperties@@YAKPEAU_HRESOURCE@@PEAURESUTIL_PROPERTY_ITEM@@PEAXK@Z; DfsSetProperties(_HRESOURCE *,RESUTIL_PROPERTY_ITEM *,void *,ulong)
0x140013172  mov     ebx, eax
0x140013174  test    eax, eax
0x140013176  jnz     short loc_1400131EF
0x140013178  mov     rcx, rdi; hResource
0x14001317b  call    cs:__imp_OnlineClusterResource
0x140013182  nop     dword ptr [rax+rax+00h]
0x140013187  mov     ebx, eax
0x140013189  mov     r12d, 3E5h
0x14001318f  test    eax, eax
0x140013191  jz      short loc_140013198
0x140013193  cmp     eax, r12d
0x140013196  jnz     short loc_1400131EF
0x140013198  mov     edx, 2; enum CLUSTER_RESOURCE_STATE
0x14001319d  mov     rcx, rdi; hResource
0x1400131a0  call    ?DfsWaitResourceState@@YAKPEAU_HRESOURCE@@W4CLUSTER_RESOURCE_STATE@@@Z; DfsWaitResourceState(_HRESOURCE *,CLUSTER_RESOURCE_STATE)
0x1400131a5  mov     ebx, eax
0x1400131a7  cmp     eax, 5B4h
0x1400131ac  jnz     short loc_1400131EF
0x1400131ae  mov     rcx, rdi; hResource
0x1400131b1  call    cs:__imp_OfflineClusterResource
0x1400131b8  nop     dword ptr [rax+rax+00h]
0x1400131bd  test    eax, eax
0x1400131bf  jz      short loc_1400131C6
0x1400131c1  cmp     eax, r12d
0x1400131c4  jnz     short loc_1400131EF
0x1400131c6  mov     edx, 3; enum CLUSTER_RESOURCE_STATE
0x1400131cb  mov     rcx, rdi; hResource
0x1400131ce  call    ?DfsWaitResourceState@@YAKPEAU_HRESOURCE@@W4CLUSTER_RESOURCE_STATE@@@Z; DfsWaitResourceState(_HRESOURCE *,CLUSTER_RESOURCE_STATE)
0x1400131d3  mov     rcx, rdi; hResource
0x1400131d6  call    cs:__imp_DeleteClusterResource
0x1400131dd  nop     dword ptr [rax+rax+00h]
0x1400131e2  jmp     short loc_1400131EF
0x1400131e4  mov     rsi, [rbp+57h+hGroup]
0x1400131e8  jmp     short loc_140013203
0x1400131ea  mov     ebx, 57h ; 'W'
0x1400131ef  test    r15, r15
0x1400131f2  jz      short loc_140013203
0x1400131f4  mov     rcx, r15; hMem
0x1400131f7  call    cs:__imp_LocalFree
0x1400131fe  nop     dword ptr [rax+rax+00h]
0x140013203  test    r14, r14
0x140013206  jz      short loc_140013217
0x140013208  mov     rcx, r14; hResource
0x14001320b  call    cs:__imp_CloseClusterResource
0x140013212  nop     dword ptr [rax+rax+00h]
0x140013217  mov     rcx, [rbp+57h+hResource]; hResource
0x14001321b  test    rcx, rcx
0x14001321e  jz      short loc_14001322C
0x140013220  call    cs:__imp_CloseClusterResource
0x140013227  nop     dword ptr [rax+rax+00h]
0x14001322c  test    rdi, rdi
0x14001322f  jz      short loc_140013240
0x140013231  mov     rcx, rdi; hResource
0x140013234  call    cs:__imp_CloseClusterResource
0x14001323b  nop     dword ptr [rax+rax+00h]
0x140013240  test    rsi, rsi
0x140013243  jz      short loc_140013254
0x140013245  mov     rcx, rsi; hGroup
0x140013248  call    cs:__imp_CloseClusterGroup
0x14001324f  nop     dword ptr [rax+rax+00h]
0x140013254  test    r13, r13
0x140013257  jz      short loc_140013268
0x140013259  mov     rcx, r13; hCluster
0x14001325c  call    cs:__imp_CloseCluster
0x140013263  nop     dword ptr [rax+rax+00h]
0x140013268  mov     rcx, [rbp+57h+bufptr]; Buffer
0x14001326c  test    rcx, rcx
0x14001326f  jz      short loc_14001327D
0x140013271  call    cs:__imp_NetApiBufferFree
0x140013278  nop     dword ptr [rax+rax+00h]
0x14001327d  mov     eax, ebx
0x14001327f  add     rsp, 88h
0x140013286  pop     r15
0x140013288  pop     r14
0x14001328a  pop     r13
0x14001328c  pop     r12
0x14001328e  pop     rdi
0x14001328f  pop     rsi
0x140013290  pop     rbx
0x140013291  pop     rbp
0x140013292  retn
```
