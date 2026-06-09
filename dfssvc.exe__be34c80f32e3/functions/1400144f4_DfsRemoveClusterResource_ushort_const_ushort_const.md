# DfsRemoveClusterResource(ushort const *,ushort const *)

- ea: `0x1400144f4`
- end: `0x14001460b`
- name: `?DfsRemoveClusterResource@@YAKPEBG0@Z`
- size: `279`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140010b2c`

## callees

- `0x140013864`
- `0x1400144ac`
- `0x1400144f4`
- `0x14001473c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014555`
- `CLUSAPI!CloseClusterResource` at `0x1400145d5`
- `CLUSAPI!CloseClusterResource` at `0x1400145d5`
- `CLUSAPI!CloseCluster` at `0x1400145e9`
- `CLUSAPI!CloseCluster` at `0x1400145e9`
- `CLUSAPI!OpenCluster` at `0x140014541`
- `CLUSAPI!OpenCluster` at `0x140014541`
- `CLUSAPI!OfflineClusterResource` at `0x140014589`
- `CLUSAPI!OfflineClusterResource` at `0x140014589`
- `CLUSAPI!DeleteClusterResource` at `0x1400145b8`
- `CLUSAPI!DeleteClusterResource` at `0x1400145b8`

## pseudocode

```c
__int64 __fastcall DfsRemoveClusterResource(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  struct _HRESOURCE *v2; // rdi
  struct _HCLUSTER *v3; // rsi
  DWORD IsCluster; // ebx
  struct _HCLUSTER *v7; // rax
  unsigned int DfsResourceInCluster; // eax
  DWORD v9; // eax
  unsigned __int8 v11; // [rsp+40h] [rbp+8h] BYREF
  HRESOURCE hResource; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v11 = 0;
  v3 = 0;
  hResource = 0;
  if ( a1 && a2 )
  {
    IsCluster = DfsNodeIsCluster(a1, &v11);
    if ( IsCluster )
      return IsCluster;
    v7 = OpenCluster(a1);
    v3 = v7;
    if ( !v7 )
      return GetLastError();
    DfsResourceInCluster = DfsGetDfsResourceInCluster(v7, a1, a2, &hResource);
    v2 = hResource;
    IsCluster = DfsResourceInCluster;
    if ( !DfsResourceInCluster )
    {
      v9 = OfflineClusterResource(hResource);
      IsCluster = v9;
      if ( !v9 || v9 == 997 )
      {
        IsCluster = DfsWaitResourceState(v2, ClusterResourceOffline);
        if ( !IsCluster )
          IsCluster = DeleteClusterResource(v2);
      }
    }
  }
  else
  {
    IsCluster = 87;
  }
  if ( v2 )
    CloseClusterResource(v2);
  if ( v3 )
    CloseCluster(v3);
  return IsCluster;
}

```

## disassembly

```asm
0x1400144f4  mov     rax, rsp
0x1400144f7  mov     [rax+10h], rbx
0x1400144fb  mov     [rax+20h], rbp
0x1400144ff  push    rsi
0x140014500  push    rdi
0x140014501  push    r14
0x140014503  sub     rsp, 20h
0x140014507  xor     edi, edi
0x140014509  mov     byte ptr [rax+8], 0
0x14001450d  xor     esi, esi
0x14001450f  mov     [rax+18h], rdi
0x140014513  mov     r14, rdx
0x140014516  mov     rbp, rcx
0x140014519  test    rcx, rcx
0x14001451c  jz      loc_1400145C8
0x140014522  test    rdx, rdx
0x140014525  jz      loc_1400145C8
0x14001452b  lea     rdx, [rax+8]; unsigned __int8 *
0x14001452f  call    ?DfsNodeIsCluster@@YAKPEBGPEAE@Z; DfsNodeIsCluster(ushort const *,uchar *)
0x140014534  mov     ebx, eax
0x140014536  test    eax, eax
0x140014538  jnz     loc_1400145F5
0x14001453e  mov     rcx, rbp; lpszClusterName
0x140014541  call    cs:__imp_OpenCluster
0x140014548  nop     dword ptr [rax+rax+00h]
0x14001454d  mov     rsi, rax
0x140014550  test    rax, rax
0x140014553  jnz     short loc_140014568
0x140014555  call    cs:__imp_GetLastError
0x14001455c  nop     dword ptr [rax+rax+00h]
0x140014561  mov     ebx, eax
0x140014563  jmp     loc_1400145F5
0x140014568  lea     r9, [rsp+38h+hResource]; struct _HRESOURCE **
0x14001456d  mov     r8, r14; unsigned __int16 *
0x140014570  mov     rdx, rbp; unsigned __int16 *
0x140014573  mov     rcx, rax; struct _HCLUSTER *
0x140014576  call    ?DfsGetDfsResourceInCluster@@YAKPEAU_HCLUSTER@@PEBG1PEAPEAU_HRESOURCE@@@Z; DfsGetDfsResourceInCluster(_HCLUSTER *,ushort const *,ushort const *,_HRESOURCE * *)
0x14001457b  mov     rdi, [rsp+38h+hResource]
0x140014580  mov     ebx, eax
0x140014582  test    eax, eax
0x140014584  jnz     short loc_1400145CD
0x140014586  mov     rcx, rdi; hResource
0x140014589  call    cs:__imp_OfflineClusterResource
0x140014590  nop     dword ptr [rax+rax+00h]
0x140014595  mov     ebx, eax
0x140014597  test    eax, eax
0x140014599  jz      short loc_1400145A2
0x14001459b  cmp     eax, 3E5h
0x1400145a0  jnz     short loc_1400145CD
0x1400145a2  mov     edx, 3; enum CLUSTER_RESOURCE_STATE
0x1400145a7  mov     rcx, rdi; hResource
0x1400145aa  call    ?DfsWaitResourceState@@YAKPEAU_HRESOURCE@@W4CLUSTER_RESOURCE_STATE@@@Z; DfsWaitResourceState(_HRESOURCE *,CLUSTER_RESOURCE_STATE)
0x1400145af  mov     ebx, eax
0x1400145b1  test    eax, eax
0x1400145b3  jnz     short loc_1400145CD
0x1400145b5  mov     rcx, rdi; hResource
0x1400145b8  call    cs:__imp_DeleteClusterResource
0x1400145bf  nop     dword ptr [rax+rax+00h]
0x1400145c4  mov     ebx, eax
0x1400145c6  jmp     short loc_1400145CD
0x1400145c8  mov     ebx, 57h ; 'W'
0x1400145cd  test    rdi, rdi
0x1400145d0  jz      short loc_1400145E1
0x1400145d2  mov     rcx, rdi; hResource
0x1400145d5  call    cs:__imp_CloseClusterResource
0x1400145dc  nop     dword ptr [rax+rax+00h]
0x1400145e1  test    rsi, rsi
0x1400145e4  jz      short loc_1400145F5
0x1400145e6  mov     rcx, rsi; hCluster
0x1400145e9  call    cs:__imp_CloseCluster
0x1400145f0  nop     dword ptr [rax+rax+00h]
0x1400145f5  mov     rbp, [rsp+38h+arg_18]
0x1400145fa  mov     eax, ebx
0x1400145fc  mov     rbx, [rsp+38h+arg_8]
0x140014601  add     rsp, 20h
0x140014605  pop     r14
0x140014607  pop     rdi
0x140014608  pop     rsi
0x140014609  retn
```
