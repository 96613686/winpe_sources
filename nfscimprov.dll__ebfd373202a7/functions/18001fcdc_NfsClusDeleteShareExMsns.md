# NfsClusDeleteShareExMsns

- ea: `0x18001fcdc`
- end: `0x18001fecf`
- name: `NfsClusDeleteShareExMsns`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001dfb4`

## callees

- `0x18001fcdc`
- `0x18001fed8`
- `0x180029894`
- `0x18002a1d8`
- `0x18002aa74`
- `0x180037010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001fe48`
- `KERNEL32!LocalFree` at `0x18001fe6f`
- `KERNEL32!LocalFree` at `0x18001fe48`
- `KERNEL32!LocalFree` at `0x18001fe6f`
- `RESUTILS!ResUtilGetResourceDependencyByName` at `0x18001fddd`
- `RESUTILS!ResUtilGetResourceDependencyByName` at `0x18001fddd`
- `CLUSAPI!ClusterResourceControl` at `0x18001fd79`
- `CLUSAPI!ClusterResourceControl` at `0x18001fd79`
- `CLUSAPI!OpenCluster` at `0x18001fd01`
- `CLUSAPI!OpenCluster` at `0x18001fd01`
- `CLUSAPI!CloseClusterResource` at `0x18001fdeb`
- `CLUSAPI!CloseClusterResource` at `0x18001fe7d`
- `CLUSAPI!CloseClusterResource` at `0x18001fdeb`
- `CLUSAPI!CloseClusterResource` at `0x18001fe7d`

## string_xrefs

- `0x18001fe34`: `Delete NFS resource completed with status=%d`
- `0x18001fe8a`: `Delete cluster share failed with status %d nad nredRes %d`

## pseudocode

```c
__int64 __fastcall NfsClusDeleteShareExMsns(__int64 a1, __int64 a2)
{
  HCLUSTER v4; // rax
  int v5; // r8d
  struct _HCLUSTER *v6; // r14
  DWORD NfsResourceForShare; // eax
  _WORD *v8; // r9
  __int64 v9; // rax
  HRESOURCE v10; // rdi
  DWORD v11; // ebp
  HLOCAL v12; // rsi
  struct _HRESOURCE *ResourceDependencyByName; // rax
  unsigned int v14; // eax
  HRESOURCE hResource; // [rsp+80h] [rbp+18h] BYREF
  HLOCAL v17; // [rsp+88h] [rbp+20h] BYREF

  hResource = 0;
  v4 = OpenCluster(0);
  v5 = *(_DWORD *)a1;
  v17 = 0;
  v6 = v4;
  NfsResourceForShare = NfsClusGetNfsResourceForShareEx(a1 + 32, (const WCHAR *)(a1 + 1098), v5, &hResource);
  if ( NfsResourceForShare )
  {
    v11 = -1073737669;
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 40LL))(a2, NfsResourceForShare, 3221229627LL);
  }
  else
  {
    v8 = (_WORD *)(a1 + 556);
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = hResource;
    v11 = ClusterResourceControl(hResource, 0, 0x160000Au, v8, 2 * v9 + 2, 0, 0, 0);
    if ( !v11 && !NfsClusGetShares(v10, (struct _NFS_SHARE_INFO_LIST **)&v17) )
    {
      v12 = v17;
      if ( !v17 || !*(_DWORD *)v17 )
      {
        (**(void (__fastcall ***)(__int64, __int64))a2)(a2, 1073745983);
        ResourceDependencyByName = ResUtilGetResourceDependencyByName(v6, v10, L"Distributed Network Name", 1);
        if ( ResourceDependencyByName )
        {
          CloseClusterResource(ResourceDependencyByName);
          if ( !(unsigned int)GetResourceName(v10)
            && (*(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 1073745982, 0) )
          {
            v14 = NfsDeleteResource(v10);
            (*(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)a2 + 16LL))(
              a2,
              L"Delete NFS resource completed with status=%d",
              v14);
          }
          LocalFree(0);
        }
        else
        {
          (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 40LL))(a2, 0, 3221229626LL);
        }
        if ( v12 )
          LocalFree(v12);
      }
    }
    if ( v10 )
      CloseClusterResource(v10);
    if ( v11 )
      (*(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)a2 + 16LL))(
        a2,
        L"Delete cluster share failed with status %d nad nredRes %d",
        v11,
        v10);
  }
  return v11;
}

```

## disassembly

```asm
0x18001fcdc  mov     rax, rsp
0x18001fcdf  mov     [rax+10h], rbx
0x18001fce3  push    rbp
0x18001fce4  push    rsi
0x18001fce5  push    rdi
0x18001fce6  push    r14
0x18001fce8  push    r15
0x18001fcea  sub     rsp, 40h
0x18001fcee  mov     rdi, rcx
0x18001fcf1  xor     r15d, r15d
0x18001fcf4  xor     ecx, ecx; lpszClusterName
0x18001fcf6  mov     [rax+18h], r15
0x18001fcfa  mov     [rax+8], r15
0x18001fcfe  mov     rbx, rdx
0x18001fd01  call    cs:__imp_OpenCluster
0x18001fd07  mov     r8d, [rdi]
0x18001fd0a  lea     rdx, [rdi+44Ah]
0x18001fd11  lea     rcx, [rdi+20h]
0x18001fd15  mov     [rsp+68h+arg_18], r15
0x18001fd1d  lea     r9, [rsp+68h+hResource]
0x18001fd25  mov     r14, rax
0x18001fd28  call    NfsClusGetNfsResourceForShareEx
0x18001fd2d  mov     edx, eax
0x18001fd2f  test    eax, eax
0x18001fd31  jnz     loc_18001FEA5
0x18001fd37  lea     r9, [rdi+22Ch]; lpInBuffer
0x18001fd3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fd42  inc     rax
0x18001fd45  cmp     [r9+rax*2], r15w
0x18001fd4a  jnz     short loc_18001FD42
0x18001fd4c  mov     rdi, [rsp+68h+hResource]
0x18001fd54  lea     eax, ds:2[rax*2]
0x18001fd5b  mov     [rsp+68h+lpBytesReturned], r15; lpBytesReturned
0x18001fd60  mov     rcx, rdi; hResource
0x18001fd63  mov     [rsp+68h+cbOutBufferSize], r15d; cbOutBufferSize
0x18001fd68  xor     edx, edx; hHostNode
0x18001fd6a  mov     [rsp+68h+lpOutBuffer], r15; lpOutBuffer
0x18001fd6f  mov     r8d, 160000Ah; dwControlCode
0x18001fd75  mov     [rsp+68h+cbInBufferSize], eax; cbInBufferSize
0x18001fd79  call    cs:__imp_ClusterResourceControl
0x18001fd7f  mov     ebp, eax
0x18001fd81  test    eax, eax
0x18001fd83  jnz     loc_18001FE75
0x18001fd89  lea     rdx, [rsp+68h+arg_18]; struct _NFS_SHARE_INFO_LIST **
0x18001fd91  mov     rcx, rdi; hResource
0x18001fd94  call    ?NfsClusGetShares@@YAKPEAU_HRESOURCE@@PEAPEAU_NFS_SHARE_INFO_LIST@@@Z; NfsClusGetShares(_HRESOURCE *,_NFS_SHARE_INFO_LIST * *)
0x18001fd99  test    eax, eax
0x18001fd9b  jnz     loc_18001FE75
0x18001fda1  mov     rsi, [rsp+68h+arg_18]
0x18001fda9  test    rsi, rsi
0x18001fdac  jz      short loc_18001FDB7
0x18001fdae  cmp     [rsi], r15d
0x18001fdb1  jnz     loc_18001FE75
0x18001fdb7  mov     rax, [rbx]
0x18001fdba  mov     edx, 4000103Fh
0x18001fdbf  mov     rcx, rbx
0x18001fdc2  mov     rax, [rax]
0x18001fdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdca  mov     r9d, 1; bRecurse
0x18001fdd0  lea     r8, aDistributedNet; "Distributed Network Name"
0x18001fdd7  mov     rdx, rdi; hSelf
0x18001fdda  mov     rcx, r14; hCluster
0x18001fddd  call    cs:__imp_ResUtilGetResourceDependencyByName
0x18001fde3  test    rax, rax
0x18001fde6  jz      short loc_18001FE50
0x18001fde8  mov     rcx, rax; hResource
0x18001fdeb  call    cs:__imp_CloseClusterResource
0x18001fdf1  lea     rdx, [rsp+68h+hMem]
0x18001fdf6  mov     rcx, rdi; hResource
0x18001fdf9  call    GetResourceName
0x18001fdfe  test    eax, eax
0x18001fe00  jnz     short loc_18001FE43
0x18001fe02  mov     rax, [rbx]
0x18001fe05  mov     edx, 4000103Eh
0x18001fe0a  mov     r8, [rsp+68h+hMem]
0x18001fe0f  mov     rcx, rbx
0x18001fe12  mov     rax, [rax+30h]
0x18001fe16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe1b  test    al, al
0x18001fe1d  jz      short loc_18001FE43
0x18001fe1f  mov     rcx, rdi
0x18001fe22  call    NfsDeleteResource
0x18001fe27  mov     rdx, [rbx]
0x18001fe2a  mov     r8d, eax
0x18001fe2d  mov     rcx, rbx
0x18001fe30  mov     r9, [rdx+10h]
0x18001fe34  lea     rdx, aDeleteNfsResou; "Delete NFS resource completed with stat"...
0x18001fe3b  mov     rax, r9
0x18001fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe43  mov     rcx, [rsp+68h+hMem]; hMem
0x18001fe48  call    cs:__imp_LocalFree
0x18001fe4e  jmp     short loc_18001FE67
0x18001fe50  mov     rax, [rbx]
0x18001fe53  xor     edx, edx
0x18001fe55  mov     r8d, 0C000103Ah
0x18001fe5b  mov     rcx, rbx
0x18001fe5e  mov     rax, [rax+28h]
0x18001fe62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe67  test    rsi, rsi
0x18001fe6a  jz      short loc_18001FE75
0x18001fe6c  mov     rcx, rsi; hMem
0x18001fe6f  call    cs:__imp_LocalFree
0x18001fe75  test    rdi, rdi
0x18001fe78  jz      short loc_18001FE83
0x18001fe7a  mov     rcx, rdi; hResource
0x18001fe7d  call    cs:__imp_CloseClusterResource
0x18001fe83  test    ebp, ebp
0x18001fe85  jz      short loc_18001FEBC
0x18001fe87  mov     rax, [rbx]
0x18001fe8a  lea     rdx, aDeleteClusterS; "Delete cluster share failed with status"...
0x18001fe91  mov     r9, rdi
0x18001fe94  mov     r8d, ebp
0x18001fe97  mov     rcx, rbx
0x18001fe9a  mov     rax, [rax+10h]
0x18001fe9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fea3  jmp     short loc_18001FEBC
0x18001fea5  mov     rax, [rbx]
0x18001fea8  mov     ebp, 0C000103Bh
0x18001fead  mov     r8d, ebp
0x18001feb0  mov     rcx, rbx
0x18001feb3  mov     rax, [rax+28h]
0x18001feb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001febc  mov     rbx, [rsp+68h+arg_8]
0x18001fec1  mov     eax, ebp
0x18001fec3  add     rsp, 40h
0x18001fec7  pop     r15
0x18001fec9  pop     r14
0x18001fecb  pop     rdi
0x18001fecc  pop     rsi
0x18001fecd  pop     rbp
0x18001fece  retn
```
