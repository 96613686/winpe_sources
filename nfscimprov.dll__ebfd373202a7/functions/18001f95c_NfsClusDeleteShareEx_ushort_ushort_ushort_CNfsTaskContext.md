# NfsClusDeleteShareEx(ushort *,ushort *,ushort *,CNfsTaskContext *)

- ea: `0x18001f95c`
- end: `0x18001fae1`
- name: `?NfsClusDeleteShareEx@@YAKPEAG00PEAVCNfsTaskContext@@@Z`
- size: `389`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001dfb4`

## callees

- `0x18001f95c`
- `0x18001fed8`
- `0x180029894`
- `0x18002a098`
- `0x18002aa74`
- `0x180037010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001fa75`
- `KERNEL32!LocalFree` at `0x18001fa80`
- `KERNEL32!LocalFree` at `0x18001fa75`
- `KERNEL32!LocalFree` at `0x18001fa80`
- `CLUSAPI!ClusterResourceControl` at `0x18001f9d8`
- `CLUSAPI!ClusterResourceControl` at `0x18001f9d8`
- `CLUSAPI!CloseClusterResource` at `0x18001fa8e`
- `CLUSAPI!CloseClusterResource` at `0x18001fa8e`

## string_xrefs

- `0x18001fa63`: `Delete NFS resource completed with status=%d`
- `0x18001fab4`: `Delete cluster share failed with status %d`

## pseudocode

```c
__int64 __fastcall NfsClusDeleteShareEx(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct CNfsTaskContext *a4)
{
  DWORD NfsResourceForShare; // eax
  DWORD v7; // ebx
  __int64 v8; // rax
  unsigned __int16 *v9; // r9
  struct _HRESOURCE *v10; // rsi
  HLOCAL v11; // rbp
  DWORD v12; // eax
  HRESOURCE hResource; // [rsp+40h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-20h] BYREF

  hResource = 0;
  hMem = 0;
  NfsResourceForShare = NfsClusGetNfsResourceForShare(a1, a3, &hResource);
  v7 = NfsResourceForShare;
  if ( NfsResourceForShare )
  {
    (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD, __int64))(*(_QWORD *)a4 + 40LL))(
      a4,
      NfsResourceForShare,
      3221229627LL);
LABEL_17:
    (*(void (**)(struct CNfsTaskContext *, const wchar_t *, ...))(*(_QWORD *)a4 + 16LL))(
      a4,
      L"Delete cluster share failed with status %d",
      v7);
    return v7;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = a2;
  v10 = hResource;
  v7 = ClusterResourceControl(hResource, 0, 0x160000Au, v9, 2 * v8 + 2, 0, 0, 0);
  if ( !v7 && !NfsClusGetShares(v10, (struct _NFS_SHARE_INFO_LIST **)&hMem) )
  {
    v11 = hMem;
    if ( !hMem || !*(_DWORD *)hMem )
    {
      (**(void (__fastcall ***)(struct CNfsTaskContext *, __int64))a4)(a4, 1073745983);
      if ( !(unsigned int)GetResourceName(v10)
        && (*(unsigned __int8 (__fastcall **)(struct CNfsTaskContext *, __int64, _QWORD))(*(_QWORD *)a4 + 48LL))(
             a4,
             1073745982,
             0) )
      {
        v12 = NfsDeleteResource(v10);
        (*(void (**)(struct CNfsTaskContext *, const wchar_t *, ...))(*(_QWORD *)a4 + 16LL))(
          a4,
          L"Delete NFS resource completed with status=%d",
          v12);
      }
      LocalFree(v11);
      LocalFree(0);
    }
  }
  if ( v10 )
    CloseClusterResource(v10);
  if ( v7 )
    goto LABEL_17;
  return v7;
}

```

## disassembly

```asm
0x18001f95c  mov     r11, rsp
0x18001f95f  mov     [r11+8], rbx
0x18001f963  mov     [r11+18h], rbp
0x18001f967  push    rsi
0x18001f968  push    rdi
0x18001f969  push    r14
0x18001f96b  sub     rsp, 50h
0x18001f96f  mov     rax, r8
0x18001f972  xor     r14d, r14d
0x18001f975  mov     rsi, rdx
0x18001f978  mov     [r11-28h], r14
0x18001f97c  mov     rdx, rax
0x18001f97f  mov     [r11+10h], r14
0x18001f983  lea     r8, [r11-28h]
0x18001f987  mov     [r11-20h], r14
0x18001f98b  mov     rdi, r9
0x18001f98e  call    NfsClusGetNfsResourceForShare
0x18001f993  mov     ebx, eax
0x18001f995  test    eax, eax
0x18001f997  jnz     loc_18001FA9A
0x18001f99d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f9a1  inc     rax
0x18001f9a4  cmp     [rsi+rax*2], r14w
0x18001f9a9  jnz     short loc_18001F9A1
0x18001f9ab  mov     [rsp+68h+lpBytesReturned], r14; lpBytesReturned
0x18001f9b0  lea     eax, ds:2[rax*2]
0x18001f9b7  mov     r9, rsi; lpInBuffer
0x18001f9ba  mov     [rsp+68h+cbOutBufferSize], r14d; cbOutBufferSize
0x18001f9bf  mov     rsi, [rsp+68h+hResource]
0x18001f9c4  xor     edx, edx; hHostNode
0x18001f9c6  mov     rcx, rsi; hResource
0x18001f9c9  mov     [rsp+68h+lpOutBuffer], r14; lpOutBuffer
0x18001f9ce  mov     r8d, 160000Ah; dwControlCode
0x18001f9d4  mov     [rsp+68h+cbInBufferSize], eax; cbInBufferSize
0x18001f9d8  call    cs:__imp_ClusterResourceControl
0x18001f9de  mov     ebx, eax
0x18001f9e0  test    eax, eax
0x18001f9e2  jnz     loc_18001FA86
0x18001f9e8  lea     rdx, [rsp+68h+hMem]; struct _NFS_SHARE_INFO_LIST **
0x18001f9ed  mov     rcx, rsi; hResource
0x18001f9f0  call    ?NfsClusGetShares@@YAKPEAU_HRESOURCE@@PEAPEAU_NFS_SHARE_INFO_LIST@@@Z; NfsClusGetShares(_HRESOURCE *,_NFS_SHARE_INFO_LIST * *)
0x18001f9f5  test    eax, eax
0x18001f9f7  jnz     loc_18001FA86
0x18001f9fd  mov     rbp, [rsp+68h+hMem]
0x18001fa02  test    rbp, rbp
0x18001fa05  jz      short loc_18001FA0D
0x18001fa07  cmp     [rbp+0], r14d
0x18001fa0b  jnz     short loc_18001FA86
0x18001fa0d  mov     rax, [rdi]
0x18001fa10  mov     edx, 4000103Fh
0x18001fa15  mov     rcx, rdi
0x18001fa18  mov     rax, [rax]
0x18001fa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa20  lea     rdx, [rsp+68h+arg_8]
0x18001fa25  mov     rcx, rsi; hResource
0x18001fa28  call    GetResourceName
0x18001fa2d  test    eax, eax
0x18001fa2f  jnz     short loc_18001FA72
0x18001fa31  mov     rax, [rdi]
0x18001fa34  mov     edx, 4000103Eh
0x18001fa39  mov     r8, [rsp+68h+arg_8]
0x18001fa3e  mov     rcx, rdi
0x18001fa41  mov     rax, [rax+30h]
0x18001fa45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa4a  test    al, al
0x18001fa4c  jz      short loc_18001FA72
0x18001fa4e  mov     rcx, rsi
0x18001fa51  call    NfsDeleteResource
0x18001fa56  mov     rdx, [rdi]
0x18001fa59  mov     r8d, eax
0x18001fa5c  mov     rcx, rdi
0x18001fa5f  mov     r9, [rdx+10h]
0x18001fa63  lea     rdx, aDeleteNfsResou; "Delete NFS resource completed with stat"...
0x18001fa6a  mov     rax, r9
0x18001fa6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa72  mov     rcx, rbp; hMem
0x18001fa75  call    cs:__imp_LocalFree
0x18001fa7b  mov     rcx, [rsp+68h+arg_8]; hMem
0x18001fa80  call    cs:__imp_LocalFree
0x18001fa86  test    rsi, rsi
0x18001fa89  jz      short loc_18001FA94
0x18001fa8b  mov     rcx, rsi; hResource
0x18001fa8e  call    cs:__imp_CloseClusterResource
0x18001fa94  test    ebx, ebx
0x18001fa96  jz      short loc_18001FACA
0x18001fa98  jmp     short loc_18001FAB1
0x18001fa9a  mov     rax, [rdi]
0x18001fa9d  mov     r8d, 0C000103Bh
0x18001faa3  mov     edx, ebx
0x18001faa5  mov     rcx, rdi
0x18001faa8  mov     rax, [rax+28h]
0x18001faac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fab1  mov     rax, [rdi]
0x18001fab4  lea     rdx, aDeleteClusterS_0; "Delete cluster share failed with status"...
0x18001fabb  mov     r8d, ebx
0x18001fabe  mov     rcx, rdi
0x18001fac1  mov     rax, [rax+10h]
0x18001fac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faca  lea     r11, [rsp+68h+var_18]
0x18001facf  mov     eax, ebx
0x18001fad1  mov     rbx, [r11+20h]
0x18001fad5  mov     rbp, [r11+30h]
0x18001fad9  mov     rsp, r11
0x18001fadc  pop     r14
0x18001fade  pop     rdi
0x18001fadf  pop     rsi
0x18001fae0  retn
```
