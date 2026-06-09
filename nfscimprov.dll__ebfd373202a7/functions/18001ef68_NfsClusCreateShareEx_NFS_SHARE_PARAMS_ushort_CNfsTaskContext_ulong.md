# NfsClusCreateShareEx(_NFS_SHARE_PARAMS *,ushort *,CNfsTaskContext *,ulong *)

- ea: `0x18001ef68`
- end: `0x18001f2d0`
- name: `?NfsClusCreateShareEx@@YAKPEAU_NFS_SHARE_PARAMS@@PEAGPEAVCNfsTaskContext@@PEAK@Z`
- size: `872`
- prototype: `unsigned int __fastcall(struct _NFS_SHARE_PARAMS *, unsigned __int16 *, struct CNfsTaskContext *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d798`

## callees

- `0x18001ef68`
- `0x18001f2d8`
- `0x18001f674`
- `0x1800201c8`
- `0x180029768`
- `0x180029e00`
- `0x180029ff4`
- `0x18002a6f8`
- `0x18002aa74`
- `0x18002aaac`
- `0x18002ad9c`
- `0x18002afc0`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001efd3`
- `KERNEL32!GetLastError` at `0x18001f00a`
- `KERNEL32!GetLastError` at `0x18001efd3`
- `KERNEL32!GetLastError` at `0x18001f00a`
- `CLUSAPI!CloseClusterGroup` at `0x18001f235`
- `CLUSAPI!CloseClusterGroup` at `0x18001f235`
- `CLUSAPI!CloseCluster` at `0x18001f293`
- `CLUSAPI!CloseCluster` at `0x18001f293`
- `CLUSAPI!OpenCluster` at `0x18001efc5`
- `CLUSAPI!OpenCluster` at `0x18001efc5`
- `CLUSAPI!CloseClusterResource` at `0x18001f26e`
- `CLUSAPI!CloseClusterResource` at `0x18001f27c`
- `CLUSAPI!CloseClusterResource` at `0x18001f28a`
- `CLUSAPI!CloseClusterResource` at `0x18001f26e`
- `CLUSAPI!CloseClusterResource` at `0x18001f27c`
- `CLUSAPI!CloseClusterResource` at `0x18001f28a`

## string_xrefs

- `0x18001f214`: `Delete NFS resource completed with status=%d`
- `0x18001f2a0`: `Create cluster share failed with status %d`

## pseudocode

```c
DWORD __fastcall NfsClusCreateShareEx(
        struct _NFS_SHARE_PARAMS *a1,
        unsigned __int16 *a2,
        struct CNfsTaskContext *a3,
        unsigned int *a4)
{
  struct _HRESOURCE *v7; // r14
  struct _HRESOURCE *v8; // rdi
  struct _HCLUSTER *v10; // rax
  struct _HCLUSTER *v11; // r12
  struct _HGROUP *ResourceGroupHandle; // r13
  DWORD LastError; // ebx
  DWORD ResourceInGroupofType; // eax
  DWORD v15; // eax
  bool v16; // al
  DWORD NetworkNameResourceInGroup; // eax
  DWORD DependentResource; // eax
  DWORD v19; // eax
  char v20; // r15
  __int64 v21; // r8
  unsigned int v22; // eax
  HRESOURCE v23; // [rsp+38h] [rbp-18h] BYREF
  HRESOURCE v24; // [rsp+40h] [rbp-10h] BYREF
  HRESOURCE hResource; // [rsp+48h] [rbp-8h] BYREF

  v7 = 0;
  hResource = 0;
  v8 = 0;
  v24 = 0;
  v23 = 0;
  if ( *((_DWORD *)a1 + 16) )
    return NfsClusCreateShareExDb((__int64)a1, a2, (__int64 *)a3, a4);
  if ( *((_DWORD *)a1 + 15) )
    return NfsClusCreateShareExMsns((BYTE *)a1, a2, (__int64 *)a3, a4);
  v10 = OpenCluster(0);
  v11 = v10;
  if ( !v10 )
    return GetLastError();
  if ( (unsigned int)NfsGetDiskResource(v10, *((_WORD **)a1 + 1), &hResource) )
  {
    ResourceGroupHandle = (struct _HGROUP *)GetResourceGroupHandle(v11, hResource);
    if ( ResourceGroupHandle || (LastError = GetLastError()) == 0 )
    {
      if ( a2 )
      {
        NetworkNameResourceInGroup = NfsGetNetworkNameResourceInGroup(v11, ResourceGroupHandle, a2, &v24);
        LastError = NetworkNameResourceInGroup;
        if ( NetworkNameResourceInGroup )
        {
          (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD, __int64, unsigned __int16 *))(*(_QWORD *)a3 + 40LL))(
            a3,
            NetworkNameResourceInGroup,
            3221229626LL,
            a2);
          v7 = v24;
          goto LABEL_34;
        }
        v7 = v24;
        DependentResource = NfsClusGetDependentResource(v11, v24, L"Network File System");
        v8 = v23;
        LastError = 0;
        if ( DependentResource != 1168 )
          LastError = DependentResource;
        v16 = DependentResource == 1168;
      }
      else
      {
        LastError = NfsClusGetDependentResource(v11, hResource, L"Network File System");
        if ( LastError == 1168 )
        {
          ResourceInGroupofType = NfsGetResourceInGroupofType(v11, ResourceGroupHandle, L"Network File System", &v23);
          v8 = v23;
          LastError = ResourceInGroupofType;
          if ( !ResourceInGroupofType && v23 )
          {
            LastError = NfsAddDiskDependencyToNfsResource(v23, hResource);
            goto LABEL_36;
          }
          if ( ResourceInGroupofType == 1168 )
          {
            v15 = NfsGetResourceInGroupofType(v11, ResourceGroupHandle, L"Network Name", &v24);
            v7 = v24;
            LastError = v15;
            if ( !v15 )
            {
              if ( v24 )
                goto LABEL_26;
            }
          }
        }
        else
        {
          v8 = v23;
        }
        v16 = 0;
      }
      if ( !LastError )
      {
        if ( !v16 )
        {
          v20 = 0;
          goto LABEL_37;
        }
LABEL_26:
        (**(void (__fastcall ***)(struct CNfsTaskContext *, __int64))a3)(a3, 1073745981);
        v19 = NfsCreateNfsResource(v11, hResource, v7, &v23);
        v8 = v23;
        LastError = v19;
        if ( !v19 && v23 )
        {
          v20 = 1;
          goto LABEL_37;
        }
        v20 = 0;
        if ( !v19 )
        {
LABEL_37:
          LastError = NfsClusterAddOrModifyShare((LPBYTE)a1, v8, 0x1600006u, a4);
          if ( (LastError || *a4) && v20 )
          {
            (*(void (__fastcall **)(struct CNfsTaskContext *, const wchar_t *))(*(_QWORD *)a3 + 16LL))(
              a3,
              L"Deleting NFS resource ...");
            v22 = NfsDeleteResource(v8);
            (*(void (**)(struct CNfsTaskContext *, const wchar_t *, ...))(*(_QWORD *)a3 + 16LL))(
              a3,
              L"Delete NFS resource completed with status=%d",
              v22);
          }
          goto LABEL_41;
        }
        v21 = 3221229628LL;
        goto LABEL_35;
      }
LABEL_34:
      v21 = 3221229627LL;
LABEL_35:
      (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD, __int64))(*(_QWORD *)a3 + 40LL))(a3, LastError, v21);
LABEL_36:
      v20 = 0;
      if ( LastError )
      {
LABEL_41:
        if ( ResourceGroupHandle )
          CloseClusterGroup(ResourceGroupHandle);
        goto LABEL_44;
      }
      goto LABEL_37;
    }
  }
  else
  {
    LastError = 1168;
    (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, _QWORD))(*(_QWORD *)a3 + 40LL))(
      a3,
      1168,
      3221229625LL,
      *((_QWORD *)a1 + 1));
  }
LABEL_44:
  if ( hResource )
    CloseClusterResource(hResource);
  if ( v7 )
    CloseClusterResource(v7);
  if ( v8 )
    CloseClusterResource(v8);
  CloseCluster(v11);
  if ( LastError )
    (*(void (**)(struct CNfsTaskContext *, const wchar_t *, ...))(*(_QWORD *)a3 + 16LL))(
      a3,
      L"Create cluster share failed with status %d",
      LastError);
  return LastError;
}

```

## disassembly

```asm
0x18001ef68  mov     [rsp-38h+arg_8], rbx
0x18001ef6d  mov     [rsp-38h+arg_18], r9
0x18001ef72  mov     [rsp-38h+pInParams], rcx
0x18001ef77  push    rbp
0x18001ef78  push    rsi
0x18001ef79  push    rdi
0x18001ef7a  push    r12
0x18001ef7c  push    r13
0x18001ef7e  push    r14
0x18001ef80  push    r15
0x18001ef82  mov     rbp, rsp
0x18001ef85  sub     rsp, 50h
0x18001ef89  xor     ebx, ebx
0x18001ef8b  mov     rsi, r8
0x18001ef8e  mov     r15, rdx
0x18001ef91  mov     r13, rcx
0x18001ef94  mov     r14d, ebx
0x18001ef97  mov     [rbp+hResource], rbx
0x18001ef9b  mov     edi, ebx
0x18001ef9d  mov     [rbp+var_10], rbx
0x18001efa1  mov     [rbp+var_18], rbx
0x18001efa5  cmp     [rcx+40h], ebx
0x18001efa8  jz      short loc_18001EFB4
0x18001efaa  call    NfsClusCreateShareExDb
0x18001efaf  jmp     loc_18001F2B8
0x18001efb4  cmp     [rcx+3Ch], ebx
0x18001efb7  jz      short loc_18001EFC3
0x18001efb9  call    NfsClusCreateShareExMsns
0x18001efbe  jmp     loc_18001F2B8
0x18001efc3  xor     ecx, ecx; lpszClusterName
0x18001efc5  call    cs:__imp_OpenCluster
0x18001efcb  mov     r12, rax
0x18001efce  test    rax, rax
0x18001efd1  jnz     short loc_18001EFDE
0x18001efd3  call    cs:__imp_GetLastError
0x18001efd9  jmp     loc_18001F2B8
0x18001efde  mov     rdx, [r13+8]
0x18001efe2  lea     r8, [rbp+hResource]
0x18001efe6  mov     rcx, r12; hCluster
0x18001efe9  call    NfsGetDiskResource
0x18001efee  test    eax, eax
0x18001eff0  jz      loc_18001F23D
0x18001eff6  mov     rdx, [rbp+hResource]; hResource
0x18001effa  mov     rcx, r12; hCluster
0x18001effd  call    GetResourceGroupHandle
0x18001f002  mov     r13, rax
0x18001f005  test    rax, rax
0x18001f008  jnz     short loc_18001F01C
0x18001f00a  call    cs:__imp_GetLastError
0x18001f010  mov     ebx, eax
0x18001f012  test    eax, eax
0x18001f014  jnz     loc_18001F262
0x18001f01a  xor     ebx, ebx
0x18001f01c  mov     [rbp+var_1E], bl
0x18001f01f  mov     rcx, r12; hCluster
0x18001f022  mov     [rbp+var_1F], 1
0x18001f026  test    r15, r15
0x18001f029  jnz     loc_18001F0B9
0x18001f02f  mov     rdx, [rbp+hResource]; hResource
0x18001f033  lea     r9, [rbp+var_18]
0x18001f037  lea     r8, szResourceTypeName; "Network File System"
0x18001f03e  mov     [rbp+var_20], bl
0x18001f041  call    NfsClusGetDependentResource
0x18001f046  mov     r15d, 490h
0x18001f04c  mov     ebx, eax
0x18001f04e  cmp     eax, r15d
0x18001f051  jnz     short loc_18001F0B1
0x18001f053  lea     r9, [rbp+var_18]
0x18001f057  mov     rdx, r13
0x18001f05a  lea     r8, szResourceTypeName; "Network File System"
0x18001f061  mov     rcx, r12
0x18001f064  call    NfsGetResourceInGroupofType
0x18001f069  mov     rdi, [rbp+var_18]
0x18001f06d  mov     ebx, eax
0x18001f06f  test    eax, eax
0x18001f071  jnz     short loc_18001F07C
0x18001f073  test    rdi, rdi
0x18001f076  jnz     loc_18001F170
0x18001f07c  xor     al, al
0x18001f07e  mov     [rbp+var_20], r14b
0x18001f082  mov     [rbp+var_1F], al
0x18001f085  cmp     ebx, r15d
0x18001f088  jnz     short loc_18001F0B5
0x18001f08a  lea     r9, [rbp+var_10]
0x18001f08e  mov     rdx, r13
0x18001f091  lea     r8, szResourceType; "Network Name"
0x18001f098  mov     rcx, r12
0x18001f09b  call    NfsGetResourceInGroupofType
0x18001f0a0  mov     r14, [rbp+var_10]
0x18001f0a4  mov     ebx, eax
0x18001f0a6  test    eax, eax
0x18001f0a8  jnz     short loc_18001F0B5
0x18001f0aa  test    r14, r14
0x18001f0ad  jnz     short loc_18001F11E
0x18001f0af  jmp     short loc_18001F0B5
0x18001f0b1  mov     rdi, [rbp+var_18]
0x18001f0b5  xor     al, al
0x18001f0b7  jmp     short loc_18001F112
0x18001f0b9  lea     r9, [rbp+var_10]
0x18001f0bd  mov     r8, r15
0x18001f0c0  mov     rdx, r13
0x18001f0c3  call    NfsGetNetworkNameResourceInGroup
0x18001f0c8  mov     ebx, eax
0x18001f0ca  test    eax, eax
0x18001f0cc  jnz     loc_18001F188
0x18001f0d2  mov     r14, [rbp+var_10]
0x18001f0d6  lea     r9, [rbp+var_18]
0x18001f0da  mov     rdx, r14; hResource
0x18001f0dd  lea     r8, szResourceTypeName; "Network File System"
0x18001f0e4  mov     rcx, r12; hCluster
0x18001f0e7  call    NfsClusGetDependentResource
0x18001f0ec  mov     rdi, [rbp+var_18]
0x18001f0f0  test    eax, eax
0x18001f0f2  jnz     short loc_18001F0FD
0x18001f0f4  mov     [rbp+var_20], 1
0x18001f0f8  test    rdi, rdi
0x18001f0fb  jnz     short loc_18001F101
0x18001f0fd  mov     [rbp+var_20], 0
0x18001f101  xor     ebx, ebx
0x18001f103  mov     r15d, 490h
0x18001f109  cmp     eax, r15d
0x18001f10c  cmovnz  ebx, eax
0x18001f10f  setz    al
0x18001f112  test    ebx, ebx
0x18001f114  jnz     loc_18001F1A6
0x18001f11a  test    al, al
0x18001f11c  jz      short loc_18001F167
0x18001f11e  mov     rax, [rsi]
0x18001f121  mov     edx, 4000103Dh
0x18001f126  mov     rcx, rsi
0x18001f129  mov     rax, [rax]
0x18001f12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f131  mov     rdx, [rbp+hResource]
0x18001f135  lea     r9, [rbp+var_18]
0x18001f139  mov     r8, r14
0x18001f13c  mov     rcx, r12
0x18001f13f  call    NfsCreateNfsResource
0x18001f144  mov     rdi, [rbp+var_18]
0x18001f148  mov     ebx, eax
0x18001f14a  test    eax, eax
0x18001f14c  jnz     short loc_18001F158
0x18001f14e  test    rdi, rdi
0x18001f151  jz      short loc_18001F158
0x18001f153  mov     r15b, 1
0x18001f156  jmp     short loc_18001F1CA
0x18001f158  xor     r15b, r15b
0x18001f15b  test    ebx, ebx
0x18001f15d  jz      short loc_18001F1CA
0x18001f15f  mov     r8d, 0C000103Ch
0x18001f165  jmp     short loc_18001F1AC
0x18001f167  cmp     [rbp+var_20], 0
0x18001f16b  jz      short loc_18001F1C6
0x18001f16d  mov     al, [rbp+var_1F]
0x18001f170  test    rdi, rdi
0x18001f173  jz      short loc_18001F1C6
0x18001f175  mov     rdx, [rbp+hResource]; HRESOURCE
0x18001f179  mov     r8b, al
0x18001f17c  mov     rcx, rdi; hResource
0x18001f17f  call    NfsAddDiskDependencyToNfsResource
0x18001f184  mov     ebx, eax
0x18001f186  jmp     short loc_18001F1BD
0x18001f188  mov     rax, [rsi]
0x18001f18b  mov     r9, r15
0x18001f18e  mov     r8d, 0C000103Ah
0x18001f194  mov     edx, ebx
0x18001f196  mov     rcx, rsi
0x18001f199  mov     rax, [rax+28h]
0x18001f19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1a2  mov     r14, [rbp+var_10]
0x18001f1a6  mov     r8d, 0C000103Bh
0x18001f1ac  mov     rax, [rsi]
0x18001f1af  mov     edx, ebx
0x18001f1b1  mov     rcx, rsi
0x18001f1b4  mov     rax, [rax+28h]
0x18001f1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1bd  xor     r15b, r15b
0x18001f1c0  test    ebx, ebx
0x18001f1c2  jnz     short loc_18001F22D
0x18001f1c4  jmp     short loc_18001F1CA
0x18001f1c6  mov     r15b, [rbp+var_1E]
0x18001f1ca  mov     r9, [rbp+arg_18]; unsigned int *
0x18001f1ce  mov     r8d, 1600006h; dwControlCode
0x18001f1d4  mov     rcx, [rbp+pInParams]; pInParams
0x18001f1d8  mov     rdx, rdi; hResource
0x18001f1db  call    ?NfsClusterAddOrModifyShare@@YAKPEAU_NFS_SHARE_PARAMS@@PEAU_HRESOURCE@@KPEAK@Z; NfsClusterAddOrModifyShare(_NFS_SHARE_PARAMS *,_HRESOURCE *,ulong,ulong *)
0x18001f1e0  mov     ebx, eax
0x18001f1e2  test    eax, eax
0x18001f1e4  jnz     short loc_18001F1EE
0x18001f1e6  mov     rax, [rbp+arg_18]
0x18001f1ea  cmp     [rax], ebx
0x18001f1ec  jz      short loc_18001F22D
0x18001f1ee  test    r15b, r15b
0x18001f1f1  jz      short loc_18001F22D
0x18001f1f3  mov     rax, [rsi]
0x18001f1f6  lea     rdx, aDeletingNfsRes; "Deleting NFS resource ..."
0x18001f1fd  mov     rcx, rsi
0x18001f200  mov     rax, [rax+10h]
0x18001f204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f209  mov     rcx, rdi
0x18001f20c  call    NfsDeleteResource
0x18001f211  mov     rcx, [rsi]
0x18001f214  lea     rdx, aDeleteNfsResou; "Delete NFS resource completed with stat"...
0x18001f21b  mov     r8d, eax
0x18001f21e  mov     r9, [rcx+10h]
0x18001f222  mov     rcx, rsi
0x18001f225  mov     rax, r9
0x18001f228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f22d  test    r13, r13
0x18001f230  jz      short loc_18001F262
0x18001f232  mov     rcx, r13; hGroup
0x18001f235  call    cs:__imp_CloseClusterGroup
0x18001f23b  jmp     short loc_18001F262
0x18001f23d  mov     rax, [rsi]
0x18001f240  mov     r15d, 490h
0x18001f246  mov     r9, [r13+8]
0x18001f24a  mov     r8d, 0C0001039h
0x18001f250  mov     edx, r15d
0x18001f253  mov     rcx, rsi
0x18001f256  mov     ebx, r15d
0x18001f259  mov     rax, [rax+28h]
0x18001f25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f262  mov     rax, [rbp+hResource]
0x18001f266  test    rax, rax
0x18001f269  jz      short loc_18001F274
0x18001f26b  mov     rcx, rax; hResource
0x18001f26e  call    cs:__imp_CloseClusterResource
0x18001f274  test    r14, r14
0x18001f277  jz      short loc_18001F282
0x18001f279  mov     rcx, r14; hResource
0x18001f27c  call    cs:__imp_CloseClusterResource
0x18001f282  test    rdi, rdi
0x18001f285  jz      short loc_18001F290
0x18001f287  mov     rcx, rdi; hResource
0x18001f28a  call    cs:__imp_CloseClusterResource
0x18001f290  mov     rcx, r12; hCluster
0x18001f293  call    cs:__imp_CloseCluster
0x18001f299  test    ebx, ebx
0x18001f29b  jz      short loc_18001F2B6
0x18001f29d  mov     rax, [rsi]
0x18001f2a0  lea     rdx, aCreateClusterS; "Create cluster share failed with status"...
0x18001f2a7  mov     r8d, ebx
0x18001f2aa  mov     rcx, rsi
0x18001f2ad  mov     rax, [rax+10h]
0x18001f2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b6  mov     eax, ebx
0x18001f2b8  mov     rbx, [rsp+50h+arg_8]
0x18001f2c0  add     rsp, 50h
0x18001f2c4  pop     r15
0x18001f2c6  pop     r14
0x18001f2c8  pop     r13
0x18001f2ca  pop     r12
0x18001f2cc  pop     rdi
0x18001f2cd  pop     rsi
0x18001f2ce  pop     rbp
0x18001f2cf  retn
```
