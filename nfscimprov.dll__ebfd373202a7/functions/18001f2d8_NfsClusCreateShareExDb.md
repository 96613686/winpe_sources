# NfsClusCreateShareExDb

- ea: `0x18001f2d8`
- end: `0x18001f66e`
- name: `NfsClusCreateShareExDb`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001ef68`

## callees

- `0x18001f2d8`
- `0x1800201c8`
- `0x1800202dc`
- `0x180029768`
- `0x180029ff4`
- `0x18002a604`
- `0x18002a80c`
- `0x18002aa74`
- `0x18002aca8`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f32c`
- `KERNEL32!GetLastError` at `0x18001f36c`
- `KERNEL32!GetLastError` at `0x18001f3a4`
- `KERNEL32!GetLastError` at `0x18001f32c`
- `KERNEL32!GetLastError` at `0x18001f36c`
- `KERNEL32!GetLastError` at `0x18001f3a4`
- `KERNEL32!LocalFree` at `0x18001f5fa`
- `KERNEL32!LocalFree` at `0x18001f5fa`
- `CLUSAPI!ClusterAddGroupToAffinityRule` at `0x18001f501`
- `CLUSAPI!ClusterAddGroupToAffinityRule` at `0x18001f522`
- `CLUSAPI!ClusterAddGroupToAffinityRule` at `0x18001f501`
- `CLUSAPI!ClusterAddGroupToAffinityRule` at `0x18001f522`
- `CLUSAPI!ClusterCreateAffinityRule` at `0x18001f446`
- `CLUSAPI!ClusterCreateAffinityRule` at `0x18001f446`
- `CLUSAPI!CloseClusterGroup` at `0x18001f61a`
- `CLUSAPI!CloseClusterGroup` at `0x18001f628`
- `CLUSAPI!CloseClusterGroup` at `0x18001f61a`
- `CLUSAPI!CloseClusterGroup` at `0x18001f628`
- `CLUSAPI!CloseCluster` at `0x18001f64e`
- `CLUSAPI!CloseCluster` at `0x18001f64e`
- `CLUSAPI!OpenClusterResource` at `0x18001f383`
- `CLUSAPI!OpenClusterResource` at `0x18001f383`
- `CLUSAPI!OpenCluster` at `0x18001f31e`
- `CLUSAPI!OpenCluster` at `0x18001f31e`
- `CLUSAPI!ClusterRemoveAffinityRule` at `0x18001f5b9`
- `CLUSAPI!ClusterRemoveAffinityRule` at `0x18001f5b9`
- `CLUSAPI!CloseClusterResource` at `0x18001f608`
- `CLUSAPI!CloseClusterResource` at `0x18001f636`
- `CLUSAPI!CloseClusterResource` at `0x18001f645`
- `CLUSAPI!CloseClusterResource` at `0x18001f608`
- `CLUSAPI!CloseClusterResource` at `0x18001f636`
- `CLUSAPI!CloseClusterResource` at `0x18001f645`

## string_xrefs

- `0x18001f402`: `NFS cluster resource already exists`
- `0x18001f45e`: `cluster affinity rule already exists`

## pseudocode

```c
DWORD __fastcall NfsClusCreateShareExDb(__int64 a1, const WCHAR *a2, __int64 *a3, unsigned int *a4)
{
  __int64 v4; // rbx
  struct _HRESOURCE *v5; // r15
  HLOCAL v6; // r14
  struct _HCLUSTER *v8; // rax
  struct _HCLUSTER *v9; // rdi
  struct _HGROUP *ResourceGroupHandle; // r13
  struct _HRESOURCE *v12; // r12
  struct _HRESOURCE *v13; // rax
  __int64 v14; // rax
  int NfsAffinityRuleName; // eax
  int AffinityRule; // eax
  unsigned int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // [rsp+30h] [rbp-30h]
  HRESOURCE hResource; // [rsp+38h] [rbp-28h] BYREF
  HGROUP hGroup; // [rsp+40h] [rbp-20h]
  HRESOURCE v23; // [rsp+48h] [rbp-18h]
  HLOCAL hMem[2]; // [rsp+50h] [rbp-10h] BYREF

  v4 = a1;
  *a4 = -2147479552;
  v5 = 0;
  v6 = 0;
  hResource = 0;
  v23 = 0;
  hMem[0] = 0;
  v8 = OpenCluster(0);
  v9 = v8;
  if ( !v8 )
    return GetLastError();
  ResourceGroupHandle = 0;
  v12 = 0;
  LODWORD(v4) = NfsGetDiskResourceDb(v8, *(LPVOID *)(v4 + 8));
  if ( (_DWORD)v4 )
  {
    hGroup = 0;
    goto LABEL_36;
  }
  hGroup = (HGROUP)GetResourceGroupHandle(v9, v23);
  if ( !hGroup )
  {
    LODWORD(v4) = GetLastError();
    if ( (_DWORD)v4 )
      goto LABEL_36;
  }
  v13 = OpenClusterResource(v9, a2);
  v12 = v13;
  if ( v13 )
  {
    ResourceGroupHandle = (struct _HGROUP *)GetResourceGroupHandle(v9, v13);
    if ( !ResourceGroupHandle )
    {
      LODWORD(v4) = GetLastError();
      if ( (_DWORD)v4 )
        goto LABEL_36;
    }
  }
  LODWORD(v4) = NfsClusGetDependentResource(v9, v12, L"Network File System");
  v14 = *a3;
  if ( (_DWORD)v4 == 1168 )
  {
    (*(void (__fastcall **)(__int64 *, __int64))v14)(a3, 1073745981);
    v17 = NfsCreateNfsResourceEx(ResourceGroupHandle, v12, &hResource, L"Network File System", a2);
    v5 = hResource;
    LODWORD(v4) = v17;
    if ( v17 || !hResource )
    {
      v20 = 0;
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*a3 + 40))(a3, v17, 3221229628LL);
        goto LABEL_36;
      }
    }
    else
    {
      v20 = 1;
    }
LABEL_13:
    LODWORD(hResource) = 0;
    NfsAffinityRuleName = NfsCreateNfsAffinityRuleName(v12, hMem);
    v6 = hMem[0];
    LODWORD(v4) = NfsAffinityRuleName;
    if ( !NfsAffinityRuleName )
    {
      AffinityRule = ClusterCreateAffinityRule(v9, hMem[0], 2);
      LODWORD(v4) = AffinityRule;
      if ( AffinityRule == 5010 )
      {
        (*(void (__fastcall **)(__int64 *, __int64, const wchar_t *, __int64))*a3)(
          a3,
          3221229672LL,
          L"cluster affinity rule already exists",
          5010);
        goto LABEL_23;
      }
      if ( !AffinityRule )
      {
        LODWORD(hResource) = 1;
LABEL_23:
        v18 = ClusterAddGroupToAffinityRule(v9, v6, ResourceGroupHandle);
        LODWORD(v4) = v18;
        if ( v18 == 5010 || !v18 )
        {
          v19 = ClusterAddGroupToAffinityRule(v9, v6, hGroup);
          LODWORD(v4) = v19;
          if ( v19 == 5010 || !v19 )
          {
            v4 = (unsigned int)NfsEnsureTheSameNode(a3, ResourceGroupHandle, hGroup);
            (*(void (__fastcall **)(__int64 *, __int64, const wchar_t *, __int64))*a3)(
              a3,
              3221229672LL,
              L"NfsEnsureTheSameNode",
              v4);
            if ( !(_DWORD)v4 )
            {
              v4 = NfsClusterAddOrModifyShare((LPBYTE)a1, v5, 0x1600006u, a4);
              (*(void (__fastcall **)(__int64 *, __int64, const wchar_t *, __int64))*a3)(
                a3,
                3221229672LL,
                L"NfsClusterAddOrModifyShare",
                v4);
              if ( !(_DWORD)v4 && !*a4 )
                goto LABEL_37;
            }
          }
        }
      }
    }
    if ( v6 && (_DWORD)hResource )
      ClusterRemoveAffinityRule(v9, v6);
    if ( v20 )
      NfsDeleteResource(v5);
    goto LABEL_36;
  }
  if ( !(_DWORD)v4 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64 *, __int64, const wchar_t *, _QWORD))v14)(
      a3,
      3221229672LL,
      L"NFS cluster resource already exists",
      0);
    v5 = hResource;
    goto LABEL_13;
  }
  (*(void (__fastcall **)(__int64 *, _QWORD, __int64, const WCHAR *))(v14 + 40))(a3, (unsigned int)v4, 3221229626LL, a2);
  v5 = hResource;
LABEL_36:
  (*(void (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(*a3 + 40))(
    a3,
    (unsigned int)v4,
    3221229625LL,
    *(_QWORD *)(a1 + 8));
LABEL_37:
  if ( v6 )
    LocalFree(v6);
  if ( v12 )
    CloseClusterResource(v12);
  if ( hGroup )
    CloseClusterGroup(hGroup);
  if ( ResourceGroupHandle )
    CloseClusterGroup(ResourceGroupHandle);
  if ( v5 )
    CloseClusterResource(v5);
  if ( v23 )
    CloseClusterResource(v23);
  CloseCluster(v9);
  return v4;
}

```

## disassembly

```asm
0x18001f2d8  mov     rax, rsp
0x18001f2db  mov     [rax+18h], rbx
0x18001f2df  mov     [rax+20h], r9
0x18001f2e3  mov     [rax+10h], rdx
0x18001f2e7  mov     [rax+8], rcx
0x18001f2eb  push    rbp
0x18001f2ec  push    rsi
0x18001f2ed  push    rdi
0x18001f2ee  push    r12
0x18001f2f0  push    r13
0x18001f2f2  push    r14
0x18001f2f4  push    r15
0x18001f2f6  mov     rbp, rsp
0x18001f2f9  sub     rsp, 60h
0x18001f2fd  mov     rbx, rcx
0x18001f300  mov     dword ptr [r9], 80001000h
0x18001f307  xor     r15d, r15d
0x18001f30a  xor     r14d, r14d
0x18001f30d  xor     ecx, ecx; lpszClusterName
0x18001f30f  mov     [rbp+hResource], r15
0x18001f313  mov     [rbp+var_18], r15
0x18001f317  mov     rsi, r8
0x18001f31a  mov     [rbp+hMem], r14
0x18001f31e  call    cs:__imp_OpenCluster
0x18001f324  mov     rdi, rax
0x18001f327  test    rax, rax
0x18001f32a  jnz     short loc_18001F337
0x18001f32c  call    cs:__imp_GetLastError
0x18001f332  jmp     loc_18001F656
0x18001f337  mov     rdx, [rbx+8]; lpInBuffer
0x18001f33b  lea     r8, [rbp+var_18]
0x18001f33f  mov     rcx, rdi; hCluster
0x18001f342  xor     r13d, r13d
0x18001f345  xor     r12d, r12d
0x18001f348  call    NfsGetDiskResourceDb
0x18001f34d  mov     ebx, eax
0x18001f34f  test    eax, eax
0x18001f351  jnz     loc_18001F5CF
0x18001f357  mov     rdx, [rbp+var_18]; hResource
0x18001f35b  mov     rcx, rdi; hCluster
0x18001f35e  call    GetResourceGroupHandle
0x18001f363  mov     [rbp+hGroup], rax
0x18001f367  test    rax, rax
0x18001f36a  jnz     short loc_18001F37C
0x18001f36c  call    cs:__imp_GetLastError
0x18001f372  mov     ebx, eax
0x18001f374  test    eax, eax
0x18001f376  jnz     loc_18001F5D3
0x18001f37c  mov     rdx, [rbp+lpszResourceName]; lpszResourceName
0x18001f380  mov     rcx, rdi; hCluster
0x18001f383  call    cs:__imp_OpenClusterResource
0x18001f389  mov     r12, rax
0x18001f38c  test    rax, rax
0x18001f38f  jz      short loc_18001F3B4
0x18001f391  mov     rdx, rax; hResource
0x18001f394  mov     rcx, rdi; hCluster
0x18001f397  call    GetResourceGroupHandle
0x18001f39c  mov     r13, rax
0x18001f39f  test    rax, rax
0x18001f3a2  jnz     short loc_18001F3B4
0x18001f3a4  call    cs:__imp_GetLastError
0x18001f3aa  mov     ebx, eax
0x18001f3ac  test    eax, eax
0x18001f3ae  jnz     loc_18001F5D3
0x18001f3b4  lea     r9, [rbp+hResource]
0x18001f3b8  mov     rdx, r12; hResource
0x18001f3bb  lea     r8, szResourceTypeName; "Network File System"
0x18001f3c2  mov     rcx, rdi; hCluster
0x18001f3c5  call    NfsClusGetDependentResource
0x18001f3ca  mov     ebx, eax
0x18001f3cc  cmp     eax, 490h
0x18001f3d1  mov     rax, [rsi]
0x18001f3d4  mov     rcx, rsi
0x18001f3d7  jz      loc_18001F47A
0x18001f3dd  test    ebx, ebx
0x18001f3df  jz      short loc_18001F3FF
0x18001f3e1  mov     r9, [rbp+lpszResourceName]
0x18001f3e5  mov     r8d, 0C000103Ah
0x18001f3eb  mov     rax, [rax+28h]
0x18001f3ef  mov     edx, ebx
0x18001f3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3f6  mov     r15, [rbp+hResource]
0x18001f3fa  jmp     loc_18001F5D3
0x18001f3ff  mov     rax, [rax]
0x18001f402  lea     r8, aNfsClusterReso; "NFS cluster resource already exists"
0x18001f409  xor     r9d, r9d
0x18001f40c  mov     [rbp+var_30], r14d
0x18001f410  mov     edx, 0C0001068h
0x18001f415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f41a  mov     r15, [rbp+hResource]
0x18001f41e  lea     rdx, [rbp+hMem]
0x18001f422  mov     dword ptr [rbp+hResource], r14d
0x18001f426  mov     rcx, r12
0x18001f429  call    NfsCreateNfsAffinityRuleName
0x18001f42e  mov     r14, [rbp+hMem]
0x18001f432  mov     ebx, eax
0x18001f434  test    eax, eax
0x18001f436  jnz     loc_18001F5A8
0x18001f43c  lea     r8d, [rax+2]
0x18001f440  mov     rdx, r14
0x18001f443  mov     rcx, rdi
0x18001f446  call    cs:__imp_ClusterCreateAffinityRule
0x18001f44c  mov     ecx, 1392h
0x18001f451  mov     ebx, eax
0x18001f453  cmp     eax, ecx
0x18001f455  jnz     loc_18001F4E9
0x18001f45b  mov     rax, [rsi]
0x18001f45e  lea     r8, aClusterAffinit; "cluster affinity rule already exists"
0x18001f465  mov     r9d, ecx
0x18001f468  mov     edx, 0C0001068h
0x18001f46d  mov     rcx, rsi
0x18001f470  mov     rax, [rax]
0x18001f473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f478  jmp     short loc_18001F4F8
0x18001f47a  mov     rax, [rax]
0x18001f47d  mov     edx, 4000103Dh
0x18001f482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f487  mov     rax, [rbp+lpszResourceName]
0x18001f48b  lea     r9, szResourceTypeName; "Network File System"
0x18001f492  lea     r8, [rbp+hResource]
0x18001f496  mov     [rsp+60h+var_40], rax
0x18001f49b  mov     rdx, r12
0x18001f49e  mov     rcx, r13
0x18001f4a1  call    NfsCreateNfsResourceEx
0x18001f4a6  mov     r15, [rbp+hResource]
0x18001f4aa  mov     ebx, eax
0x18001f4ac  test    eax, eax
0x18001f4ae  jnz     short loc_18001F4C1
0x18001f4b0  test    r15, r15
0x18001f4b3  jz      short loc_18001F4C1
0x18001f4b5  mov     [rbp+var_30], 1
0x18001f4bc  jmp     loc_18001F41E
0x18001f4c1  mov     [rbp+var_30], r14d
0x18001f4c5  test    ebx, ebx
0x18001f4c7  jz      loc_18001F41E
0x18001f4cd  mov     rax, [rsi]
0x18001f4d0  mov     r8d, 0C000103Ch
0x18001f4d6  mov     edx, ebx
0x18001f4d8  mov     rcx, rsi
0x18001f4db  mov     rax, [rax+28h]
0x18001f4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4e4  jmp     loc_18001F5D3
0x18001f4e9  test    eax, eax
0x18001f4eb  jnz     loc_18001F5A8
0x18001f4f1  mov     dword ptr [rbp+hResource], 1
0x18001f4f8  mov     r8, r13
0x18001f4fb  mov     rdx, r14
0x18001f4fe  mov     rcx, rdi
0x18001f501  call    cs:__imp_ClusterAddGroupToAffinityRule
0x18001f507  mov     ebx, eax
0x18001f509  cmp     eax, 1392h
0x18001f50e  jz      short loc_18001F518
0x18001f510  test    eax, eax
0x18001f512  jnz     loc_18001F5A8
0x18001f518  mov     r8, [rbp+hGroup]
0x18001f51c  mov     rdx, r14
0x18001f51f  mov     rcx, rdi
0x18001f522  call    cs:__imp_ClusterAddGroupToAffinityRule
0x18001f528  mov     ebx, eax
0x18001f52a  cmp     eax, 1392h
0x18001f52f  jz      short loc_18001F535
0x18001f531  test    eax, eax
0x18001f533  jnz     short loc_18001F5A8
0x18001f535  mov     r8, [rbp+hGroup]
0x18001f539  mov     rdx, r13
0x18001f53c  mov     rcx, rsi
0x18001f53f  call    NfsEnsureTheSameNode
0x18001f544  mov     ebx, eax
0x18001f546  lea     r8, aNfsensurethesa; "NfsEnsureTheSameNode"
0x18001f54d  mov     rax, [rsi]
0x18001f550  mov     r9d, ebx
0x18001f553  mov     edx, 0C0001068h
0x18001f558  mov     rcx, rsi
0x18001f55b  mov     rax, [rax]
0x18001f55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f563  test    ebx, ebx
0x18001f565  jnz     short loc_18001F5A8
0x18001f567  mov     r9, [rbp+arg_18]; unsigned int *
0x18001f56b  mov     r8d, 1600006h; dwControlCode
0x18001f571  mov     rcx, [rbp+pInParams]; pInParams
0x18001f575  mov     rdx, r15; hResource
0x18001f578  call    ?NfsClusterAddOrModifyShare@@YAKPEAU_NFS_SHARE_PARAMS@@PEAU_HRESOURCE@@KPEAK@Z; NfsClusterAddOrModifyShare(_NFS_SHARE_PARAMS *,_HRESOURCE *,ulong,ulong *)
0x18001f57d  mov     ebx, eax
0x18001f57f  lea     r8, aNfsclusteraddo; "NfsClusterAddOrModifyShare"
0x18001f586  mov     rax, [rsi]
0x18001f589  mov     r9d, ebx
0x18001f58c  mov     edx, 0C0001068h
0x18001f591  mov     rcx, rsi
0x18001f594  mov     rax, [rax]
0x18001f597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59c  test    ebx, ebx
0x18001f59e  jnz     short loc_18001F5A8
0x18001f5a0  mov     rax, [rbp+arg_18]
0x18001f5a4  cmp     [rax], ebx
0x18001f5a6  jz      short loc_18001F5F2
0x18001f5a8  test    r14, r14
0x18001f5ab  jz      short loc_18001F5BF
0x18001f5ad  cmp     dword ptr [rbp+hResource], 0
0x18001f5b1  jz      short loc_18001F5BF
0x18001f5b3  mov     rdx, r14
0x18001f5b6  mov     rcx, rdi
0x18001f5b9  call    cs:__imp_ClusterRemoveAffinityRule
0x18001f5bf  cmp     [rbp+var_30], 0
0x18001f5c3  jz      short loc_18001F5D3
0x18001f5c5  mov     rcx, r15
0x18001f5c8  call    NfsDeleteResource
0x18001f5cd  jmp     short loc_18001F5D3
0x18001f5cf  mov     [rbp+hGroup], r12
0x18001f5d3  mov     rax, [rsi]
0x18001f5d6  mov     r8d, 0C0001039h
0x18001f5dc  mov     r9, [rbp+pInParams]
0x18001f5e0  mov     edx, ebx
0x18001f5e2  mov     rcx, rsi
0x18001f5e5  mov     rax, [rax+28h]
0x18001f5e9  mov     r9, [r9+8]
0x18001f5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5f2  test    r14, r14
0x18001f5f5  jz      short loc_18001F600
0x18001f5f7  mov     rcx, r14; hMem
0x18001f5fa  call    cs:__imp_LocalFree
0x18001f600  test    r12, r12
0x18001f603  jz      short loc_18001F60E
0x18001f605  mov     rcx, r12; hResource
0x18001f608  call    cs:__imp_CloseClusterResource
0x18001f60e  mov     rax, [rbp+hGroup]
0x18001f612  test    rax, rax
0x18001f615  jz      short loc_18001F620
0x18001f617  mov     rcx, rax; hGroup
0x18001f61a  call    cs:__imp_CloseClusterGroup
0x18001f620  test    r13, r13
0x18001f623  jz      short loc_18001F62E
0x18001f625  mov     rcx, r13; hGroup
0x18001f628  call    cs:__imp_CloseClusterGroup
0x18001f62e  test    r15, r15
0x18001f631  jz      short loc_18001F63C
0x18001f633  mov     rcx, r15; hResource
0x18001f636  call    cs:__imp_CloseClusterResource
0x18001f63c  mov     rcx, [rbp+var_18]; hResource
0x18001f640  test    rcx, rcx
0x18001f643  jz      short loc_18001F64B
0x18001f645  call    cs:__imp_CloseClusterResource
0x18001f64b  mov     rcx, rdi; hCluster
0x18001f64e  call    cs:__imp_CloseCluster
0x18001f654  mov     eax, ebx
0x18001f656  mov     rbx, [rsp+60h+arg_10]
0x18001f65e  add     rsp, 60h
0x18001f662  pop     r15
0x18001f664  pop     r14
0x18001f666  pop     r13
0x18001f668  pop     r12
0x18001f66a  pop     rdi
0x18001f66b  pop     rsi
0x18001f66c  pop     rbp
0x18001f66d  retn
```
