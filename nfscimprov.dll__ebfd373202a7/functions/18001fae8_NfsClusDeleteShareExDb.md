# NfsClusDeleteShareExDb

- ea: `0x18001fae8`
- end: `0x18001fcd5`
- name: `NfsClusDeleteShareExDb`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001dfb4`

## callees

- `0x18001fae8`
- `0x18001fed8`
- `0x180029894`
- `0x18002a1d8`
- `0x18002aa74`
- `0x180037010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001fc51`
- `KERNEL32!LocalFree` at `0x18001fc78`
- `KERNEL32!LocalFree` at `0x18001fc51`
- `KERNEL32!LocalFree` at `0x18001fc78`
- `RESUTILS!ResUtilGetResourceDependencyByName` at `0x18001fbe6`
- `RESUTILS!ResUtilGetResourceDependencyByName` at `0x18001fbe6`
- `CLUSAPI!ClusterResourceControl` at `0x18001fb81`
- `CLUSAPI!ClusterResourceControl` at `0x18001fb81`
- `CLUSAPI!OpenCluster` at `0x18001fb11`
- `CLUSAPI!OpenCluster` at `0x18001fb11`
- `CLUSAPI!CloseClusterResource` at `0x18001fbf4`
- `CLUSAPI!CloseClusterResource` at `0x18001fc86`
- `CLUSAPI!CloseClusterResource` at `0x18001fbf4`
- `CLUSAPI!CloseClusterResource` at `0x18001fc86`

## string_xrefs

- `0x18001fc3d`: `Delete NFS resource completed with status=%d`
- `0x18001fcac`: `Delete cluster share failed with status %d`

## pseudocode

```c
__int64 __fastcall NfsClusDeleteShareExDb(__int64 a1, __int64 a2)
{
  struct _HCLUSTER *v4; // r14
  DWORD NfsResourceForShare; // eax
  DWORD v6; // edi
  _WORD *v7; // r9
  __int64 v8; // rax
  HRESOURCE v9; // rsi
  HLOCAL v10; // rbp
  struct _HRESOURCE *ResourceDependencyByName; // rax
  unsigned int v12; // eax
  HRESOURCE hResource; // [rsp+80h] [rbp+18h] BYREF
  HLOCAL v15; // [rsp+88h] [rbp+20h] BYREF

  hResource = 0;
  v15 = 0;
  v4 = OpenCluster(0);
  NfsResourceForShare = NfsClusGetNfsResourceForShareEx(a1 + 32, (const WCHAR *)(a1 + 1098), *(_DWORD *)a1, &hResource);
  v6 = NfsResourceForShare;
  if ( NfsResourceForShare )
  {
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 40LL))(a2, NfsResourceForShare, 3221229627LL);
LABEL_21:
    (*(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)a2 + 16LL))(
      a2,
      L"Delete cluster share failed with status %d",
      v6);
    return v6;
  }
  v7 = (_WORD *)(a1 + 556);
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  v9 = hResource;
  v6 = ClusterResourceControl(hResource, 0, 0x160000Au, v7, 2 * v8 + 2, 0, 0, 0);
  if ( !v6 && !NfsClusGetShares(v9, (struct _NFS_SHARE_INFO_LIST **)&v15) )
  {
    v10 = v15;
    if ( !v15 || !*(_DWORD *)v15 )
    {
      (**(void (__fastcall ***)(__int64, __int64))a2)(a2, 1073745983);
      ResourceDependencyByName = ResUtilGetResourceDependencyByName(v4, v9, L"Network Name", 1);
      if ( ResourceDependencyByName )
      {
        CloseClusterResource(ResourceDependencyByName);
        if ( !(unsigned int)GetResourceName(v9)
          && (*(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 1073745982, 0) )
        {
          v12 = NfsDeleteResource(v9);
          (*(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)a2 + 16LL))(
            a2,
            L"Delete NFS resource completed with status=%d",
            v12);
        }
        LocalFree(0);
      }
      else
      {
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 40LL))(a2, 0, 3221229626LL);
      }
      if ( v10 )
        LocalFree(v10);
    }
  }
  if ( v9 )
    CloseClusterResource(v9);
  if ( v6 )
    goto LABEL_21;
  return v6;
}

```

## disassembly

```asm
0x18001fae8  mov     rax, rsp
0x18001faeb  mov     [rax+10h], rbx
0x18001faef  push    rbp
0x18001faf0  push    rsi
0x18001faf1  push    rdi
0x18001faf2  push    r14
0x18001faf4  push    r15
0x18001faf6  sub     rsp, 40h
0x18001fafa  xor     r15d, r15d
0x18001fafd  mov     rsi, rcx
0x18001fb00  xor     ecx, ecx; lpszClusterName
0x18001fb02  mov     [rax+18h], r15
0x18001fb06  mov     [rax+8], r15
0x18001fb0a  mov     rbx, rdx
0x18001fb0d  mov     [rax+20h], r15
0x18001fb11  call    cs:__imp_OpenCluster
0x18001fb17  mov     r8d, [rsi]
0x18001fb1a  lea     rdx, [rsi+44Ah]
0x18001fb21  lea     rcx, [rsi+20h]
0x18001fb25  mov     r14, rax
0x18001fb28  lea     r9, [rsp+68h+hResource]
0x18001fb30  call    NfsClusGetNfsResourceForShareEx
0x18001fb35  mov     edi, eax
0x18001fb37  test    eax, eax
0x18001fb39  jnz     loc_18001FC92
0x18001fb3f  lea     r9, [rsi+22Ch]; lpInBuffer
0x18001fb46  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fb4a  inc     rax
0x18001fb4d  cmp     [r9+rax*2], r15w
0x18001fb52  jnz     short loc_18001FB4A
0x18001fb54  mov     rsi, [rsp+68h+hResource]
0x18001fb5c  lea     eax, ds:2[rax*2]
0x18001fb63  mov     [rsp+68h+lpBytesReturned], r15; lpBytesReturned
0x18001fb68  mov     rcx, rsi; hResource
0x18001fb6b  mov     [rsp+68h+cbOutBufferSize], r15d; cbOutBufferSize
0x18001fb70  xor     edx, edx; hHostNode
0x18001fb72  mov     [rsp+68h+lpOutBuffer], r15; lpOutBuffer
0x18001fb77  mov     r8d, 160000Ah; dwControlCode
0x18001fb7d  mov     [rsp+68h+cbInBufferSize], eax; cbInBufferSize
0x18001fb81  call    cs:__imp_ClusterResourceControl
0x18001fb87  mov     edi, eax
0x18001fb89  test    eax, eax
0x18001fb8b  jnz     loc_18001FC7E
0x18001fb91  lea     rdx, [rsp+68h+arg_18]; struct _NFS_SHARE_INFO_LIST **
0x18001fb99  mov     rcx, rsi; hResource
0x18001fb9c  call    ?NfsClusGetShares@@YAKPEAU_HRESOURCE@@PEAPEAU_NFS_SHARE_INFO_LIST@@@Z; NfsClusGetShares(_HRESOURCE *,_NFS_SHARE_INFO_LIST * *)
0x18001fba1  test    eax, eax
0x18001fba3  jnz     loc_18001FC7E
0x18001fba9  mov     rbp, [rsp+68h+arg_18]
0x18001fbb1  test    rbp, rbp
0x18001fbb4  jz      short loc_18001FBC0
0x18001fbb6  cmp     [rbp+0], r15d
0x18001fbba  jnz     loc_18001FC7E
0x18001fbc0  mov     rax, [rbx]
0x18001fbc3  mov     edx, 4000103Fh
0x18001fbc8  mov     rcx, rbx
0x18001fbcb  mov     rax, [rax]
0x18001fbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbd3  mov     r9d, 1; bRecurse
0x18001fbd9  lea     r8, szResourceType; "Network Name"
0x18001fbe0  mov     rdx, rsi; hSelf
0x18001fbe3  mov     rcx, r14; hCluster
0x18001fbe6  call    cs:__imp_ResUtilGetResourceDependencyByName
0x18001fbec  test    rax, rax
0x18001fbef  jz      short loc_18001FC59
0x18001fbf1  mov     rcx, rax; hResource
0x18001fbf4  call    cs:__imp_CloseClusterResource
0x18001fbfa  lea     rdx, [rsp+68h+hMem]
0x18001fbff  mov     rcx, rsi; hResource
0x18001fc02  call    GetResourceName
0x18001fc07  test    eax, eax
0x18001fc09  jnz     short loc_18001FC4C
0x18001fc0b  mov     rax, [rbx]
0x18001fc0e  mov     edx, 4000103Eh
0x18001fc13  mov     r8, [rsp+68h+hMem]
0x18001fc18  mov     rcx, rbx
0x18001fc1b  mov     rax, [rax+30h]
0x18001fc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc24  test    al, al
0x18001fc26  jz      short loc_18001FC4C
0x18001fc28  mov     rcx, rsi
0x18001fc2b  call    NfsDeleteResource
0x18001fc30  mov     rdx, [rbx]
0x18001fc33  mov     r8d, eax
0x18001fc36  mov     rcx, rbx
0x18001fc39  mov     r9, [rdx+10h]
0x18001fc3d  lea     rdx, aDeleteNfsResou; "Delete NFS resource completed with stat"...
0x18001fc44  mov     rax, r9
0x18001fc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc4c  mov     rcx, [rsp+68h+hMem]; hMem
0x18001fc51  call    cs:__imp_LocalFree
0x18001fc57  jmp     short loc_18001FC70
0x18001fc59  mov     rax, [rbx]
0x18001fc5c  xor     edx, edx
0x18001fc5e  mov     r8d, 0C000103Ah
0x18001fc64  mov     rcx, rbx
0x18001fc67  mov     rax, [rax+28h]
0x18001fc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc70  test    rbp, rbp
0x18001fc73  jz      short loc_18001FC7E
0x18001fc75  mov     rcx, rbp; hMem
0x18001fc78  call    cs:__imp_LocalFree
0x18001fc7e  test    rsi, rsi
0x18001fc81  jz      short loc_18001FC8C
0x18001fc83  mov     rcx, rsi; hResource
0x18001fc86  call    cs:__imp_CloseClusterResource
0x18001fc8c  test    edi, edi
0x18001fc8e  jz      short loc_18001FCC2
0x18001fc90  jmp     short loc_18001FCA9
0x18001fc92  mov     rax, [rbx]
0x18001fc95  mov     r8d, 0C000103Bh
0x18001fc9b  mov     edx, edi
0x18001fc9d  mov     rcx, rbx
0x18001fca0  mov     rax, [rax+28h]
0x18001fca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fca9  mov     rax, [rbx]
0x18001fcac  lea     rdx, aDeleteClusterS_0; "Delete cluster share failed with status"...
0x18001fcb3  mov     r8d, edi
0x18001fcb6  mov     rcx, rbx
0x18001fcb9  mov     rax, [rax+10h]
0x18001fcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcc2  mov     rbx, [rsp+68h+arg_8]
0x18001fcc7  mov     eax, edi
0x18001fcc9  add     rsp, 40h
0x18001fccd  pop     r15
0x18001fccf  pop     r14
0x18001fcd1  pop     rdi
0x18001fcd2  pop     rsi
0x18001fcd3  pop     rbp
0x18001fcd4  retn
```
