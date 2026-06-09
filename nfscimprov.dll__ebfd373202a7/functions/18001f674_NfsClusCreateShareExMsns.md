# NfsClusCreateShareExMsns

- ea: `0x18001f674`
- end: `0x18001f953`
- name: `NfsClusCreateShareExMsns`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001ef68`

## callees

- `0x18001f674`
- `0x1800201c8`
- `0x180029768`
- `0x180029ff4`
- `0x18002a80c`
- `0x18002aa74`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f6cf`
- `KERNEL32!GetLastError` at `0x18001f704`
- `KERNEL32!GetLastError` at `0x18001f8ca`
- `KERNEL32!GetLastError` at `0x18001f6cf`
- `KERNEL32!GetLastError` at `0x18001f704`
- `KERNEL32!GetLastError` at `0x18001f8ca`
- `RESUTILS!ResUtilEnumResourcesEx` at `0x18001f8f2`
- `RESUTILS!ResUtilEnumResourcesEx` at `0x18001f8f2`
- `CLUSAPI!CloseClusterGroup` at `0x18001f803`
- `CLUSAPI!CloseClusterGroup` at `0x18001f803`
- `CLUSAPI!CloseCluster` at `0x18001f81a`
- `CLUSAPI!CloseCluster` at `0x18001f900`
- `CLUSAPI!CloseCluster` at `0x18001f81a`
- `CLUSAPI!CloseCluster` at `0x18001f900`
- `CLUSAPI!OpenClusterResource` at `0x18001f6e3`
- `CLUSAPI!OpenClusterResource` at `0x18001f6e3`
- `CLUSAPI!OpenCluster` at `0x18001f6c1`
- `CLUSAPI!OpenCluster` at `0x18001f8ba`
- `CLUSAPI!OpenCluster` at `0x18001f6c1`
- `CLUSAPI!OpenCluster` at `0x18001f8ba`
- `CLUSAPI!CloseClusterResource` at `0x18001f7f5`
- `CLUSAPI!CloseClusterResource` at `0x18001f811`
- `CLUSAPI!CloseClusterResource` at `0x18001f7f5`
- `CLUSAPI!CloseClusterResource` at `0x18001f811`

## string_xrefs

- `0x18001f760`: `NFS cluster resource already exists`

## pseudocode

```c
DWORD __fastcall NfsClusCreateShareExMsns(BYTE *a1, const WCHAR *a2, __int64 *a3, unsigned int *a4)
{
  struct _HRESOURCE *v4; // rsi
  struct _HCLUSTER *v7; // rax
  struct _HCLUSTER *v8; // r13
  struct _HGROUP *ResourceGroupHandle; // r15
  struct _HRESOURCE *v11; // rax
  struct _HRESOURCE *v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rax
  int v15; // r12d
  int NfsResource; // eax
  struct _HCLUSTER *v17; // rax
  DWORD LastError; // r12d
  struct _HCLUSTER *hClustera; // [rsp+30h] [rbp-D0h]
  HRESOURCE hResource[2]; // [rsp+38h] [rbp-C8h] BYREF
  LPBYTE pInParams; // [rsp+48h] [rbp-B8h]
  _BYTE v23[512]; // [rsp+50h] [rbp-B0h] BYREF

  pInParams = a1;
  v4 = 0;
  hResource[0] = 0;
  *a4 = -2147479552;
  v7 = OpenCluster(0);
  v8 = v7;
  if ( !v7 )
    return GetLastError();
  ResourceGroupHandle = 0;
  v11 = OpenClusterResource(v7, a2);
  v12 = v11;
  if ( v11 )
  {
    ResourceGroupHandle = (struct _HGROUP *)GetResourceGroupHandle(v8, v11);
    if ( !ResourceGroupHandle )
    {
      LODWORD(v13) = GetLastError();
      if ( (_DWORD)v13 )
        goto LABEL_14;
    }
  }
  LODWORD(v13) = NfsClusGetDependentResource(v8, v12, L"NFS Multi Server Namespace");
  v14 = *a3;
  if ( (_DWORD)v13 == 1168 )
  {
    (*(void (__fastcall **)(__int64 *, __int64))v14)(a3, 1073745981);
    NfsResource = NfsCreateNfsResourceEx(ResourceGroupHandle, v12, hResource, L"NFS Multi Server Namespace", a2);
    v4 = hResource[0];
    LODWORD(v13) = NfsResource;
    if ( !NfsResource && hResource[0] )
    {
      v15 = 1;
      goto LABEL_10;
    }
    if ( NfsResource == 5940 )
    {
      memset_0(v23, 0, 0x1FEu);
      hResource[1] = (HRESOURCE)255;
      hResource[0] = (HRESOURCE)v23;
      v17 = OpenCluster(0);
      hClustera = v17;
      if ( v17 )
      {
        LastError = ResUtilEnumResourcesEx(
                      v17,
                      0,
                      L"NFS Multi Server Namespace",
                      NfsClusMSNResourceEnumGetDnsNameCallBack,
                      hResource);
        CloseCluster(hClustera);
      }
      else
      {
        LastError = GetLastError();
      }
      if ( !LastError )
        (*(void (__fastcall **)(__int64 *, __int64, __int64, _BYTE *))(*a3 + 40))(a3, 5940, 3221229676LL, v23);
    }
    else
    {
      v15 = 0;
      if ( !NfsResource )
        goto LABEL_10;
    }
    (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*a3 + 40))(a3, (unsigned int)v13, 3221229628LL);
    goto LABEL_14;
  }
  if ( (_DWORD)v13 )
  {
    (*(void (__fastcall **)(__int64 *, _QWORD, __int64, const WCHAR *))(v14 + 40))(
      a3,
      (unsigned int)v13,
      3221229626LL,
      a2);
    v4 = hResource[0];
    goto LABEL_14;
  }
  v15 = 0;
  (*(void (__fastcall **)(__int64 *, __int64, const wchar_t *, _QWORD))v14)(
    a3,
    3221229672LL,
    L"NFS cluster resource already exists",
    0);
  v4 = hResource[0];
LABEL_10:
  v13 = NfsClusterAddOrModifyShare(pInParams, v4, 0x1600006u, a4);
  (*(void (__fastcall **)(__int64 *, __int64, const wchar_t *, __int64))*a3)(
    a3,
    3221229672LL,
    L"NfsClusterAddOrModifyShare",
    v13);
  if ( !(_DWORD)v13 && !*a4 )
    goto LABEL_15;
  if ( v15 )
    NfsDeleteResource(v4);
LABEL_14:
  (*(void (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(*a3 + 40))(
    a3,
    (unsigned int)v13,
    3221229625LL,
    *((_QWORD *)pInParams + 1));
LABEL_15:
  if ( v12 )
    CloseClusterResource(v12);
  if ( ResourceGroupHandle )
    CloseClusterGroup(ResourceGroupHandle);
  if ( v4 )
    CloseClusterResource(v4);
  CloseCluster(v8);
  return v13;
}

```

## disassembly

```asm
0x18001f674  push    rbp
0x18001f676  push    rbx
0x18001f677  push    rsi
0x18001f678  push    rdi
0x18001f679  push    r12
0x18001f67b  push    r13
0x18001f67d  push    r14
0x18001f67f  push    r15
0x18001f681  lea     rbp, [rsp-168h]
0x18001f689  sub     rsp, 268h
0x18001f690  mov     rax, cs:__security_cookie
0x18001f697  xor     rax, rsp
0x18001f69a  mov     [rbp+1A0h+var_50], rax
0x18001f6a1  mov     [rsp+2A0h+pInParams], rcx
0x18001f6a6  xor     esi, esi
0x18001f6a8  xor     ecx, ecx; lpszClusterName
0x18001f6aa  mov     [rsp+2A0h+hResource], rsi
0x18001f6af  mov     [rsp+2A0h+hCluster], r9
0x18001f6b4  mov     rdi, r8
0x18001f6b7  mov     r12, rdx
0x18001f6ba  mov     dword ptr [r9], 80001000h
0x18001f6c1  call    cs:__imp_OpenCluster
0x18001f6c7  mov     r13, rax
0x18001f6ca  test    rax, rax
0x18001f6cd  jnz     short loc_18001F6DA
0x18001f6cf  call    cs:__imp_GetLastError
0x18001f6d5  jmp     loc_18001F822
0x18001f6da  mov     rdx, r12; lpszResourceName
0x18001f6dd  mov     rcx, r13; hCluster
0x18001f6e0  xor     r15d, r15d
0x18001f6e3  call    cs:__imp_OpenClusterResource
0x18001f6e9  mov     r14, rax
0x18001f6ec  test    rax, rax
0x18001f6ef  jz      short loc_18001F714
0x18001f6f1  mov     rdx, rax; hResource
0x18001f6f4  mov     rcx, r13; hCluster
0x18001f6f7  call    GetResourceGroupHandle
0x18001f6fc  mov     r15, rax
0x18001f6ff  test    rax, rax
0x18001f702  jnz     short loc_18001F714
0x18001f704  call    cs:__imp_GetLastError
0x18001f70a  mov     ebx, eax
0x18001f70c  test    eax, eax
0x18001f70e  jnz     loc_18001F7CD
0x18001f714  lea     r9, [rsp+2A0h+hResource]
0x18001f719  mov     rdx, r14; hResource
0x18001f71c  lea     r8, aNfsMultiServer; "NFS Multi Server Namespace"
0x18001f723  mov     rcx, r13; hCluster
0x18001f726  call    NfsClusGetDependentResource
0x18001f72b  mov     ebx, eax
0x18001f72d  cmp     eax, 490h
0x18001f732  mov     rax, [rdi]
0x18001f735  mov     rcx, rdi
0x18001f738  jz      loc_18001F845
0x18001f73e  test    ebx, ebx
0x18001f740  jz      short loc_18001F75D
0x18001f742  mov     rax, [rax+28h]
0x18001f746  mov     r9, r12
0x18001f749  mov     r8d, 0C000103Ah
0x18001f74f  mov     edx, ebx
0x18001f751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f756  mov     rsi, [rsp+2A0h+hResource]
0x18001f75b  jmp     short loc_18001F7CD
0x18001f75d  mov     rax, [rax]
0x18001f760  lea     r8, aNfsClusterReso; "NFS cluster resource already exists"
0x18001f767  xor     r12d, r12d
0x18001f76a  xor     r9d, r9d
0x18001f76d  mov     edx, 0C0001068h
0x18001f772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f777  mov     rsi, [rsp+2A0h+hResource]
0x18001f77c  mov     r9, [rsp+2A0h+hCluster]; unsigned int *
0x18001f781  mov     r8d, 1600006h; dwControlCode
0x18001f787  mov     rcx, [rsp+2A0h+pInParams]; pInParams
0x18001f78c  mov     rdx, rsi; hResource
0x18001f78f  call    ?NfsClusterAddOrModifyShare@@YAKPEAU_NFS_SHARE_PARAMS@@PEAU_HRESOURCE@@KPEAK@Z; NfsClusterAddOrModifyShare(_NFS_SHARE_PARAMS *,_HRESOURCE *,ulong,ulong *)
0x18001f794  mov     ebx, eax
0x18001f796  lea     r8, aNfsclusteraddo; "NfsClusterAddOrModifyShare"
0x18001f79d  mov     rax, [rdi]
0x18001f7a0  mov     r9d, ebx
0x18001f7a3  mov     edx, 0C0001068h
0x18001f7a8  mov     rcx, rdi
0x18001f7ab  mov     rax, [rax]
0x18001f7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7b3  test    ebx, ebx
0x18001f7b5  jnz     short loc_18001F7C0
0x18001f7b7  mov     rax, [rsp+2A0h+hCluster]
0x18001f7bc  cmp     [rax], ebx
0x18001f7be  jz      short loc_18001F7ED
0x18001f7c0  test    r12d, r12d
0x18001f7c3  jz      short loc_18001F7CD
0x18001f7c5  mov     rcx, rsi
0x18001f7c8  call    NfsDeleteResource
0x18001f7cd  mov     rax, [rdi]
0x18001f7d0  mov     r8d, 0C0001039h
0x18001f7d6  mov     r9, [rsp+2A0h+pInParams]
0x18001f7db  mov     edx, ebx
0x18001f7dd  mov     rcx, rdi
0x18001f7e0  mov     rax, [rax+28h]
0x18001f7e4  mov     r9, [r9+8]
0x18001f7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7ed  test    r14, r14
0x18001f7f0  jz      short loc_18001F7FB
0x18001f7f2  mov     rcx, r14; hResource
0x18001f7f5  call    cs:__imp_CloseClusterResource
0x18001f7fb  test    r15, r15
0x18001f7fe  jz      short loc_18001F809
0x18001f800  mov     rcx, r15; hGroup
0x18001f803  call    cs:__imp_CloseClusterGroup
0x18001f809  test    rsi, rsi
0x18001f80c  jz      short loc_18001F817
0x18001f80e  mov     rcx, rsi; hResource
0x18001f811  call    cs:__imp_CloseClusterResource
0x18001f817  mov     rcx, r13; hCluster
0x18001f81a  call    cs:__imp_CloseCluster
0x18001f820  mov     eax, ebx
0x18001f822  mov     rcx, [rbp+1A0h+var_50]
0x18001f829  xor     rcx, rsp; StackCookie
0x18001f82c  call    __security_check_cookie
0x18001f831  add     rsp, 268h
0x18001f838  pop     r15
0x18001f83a  pop     r14
0x18001f83c  pop     r13
0x18001f83e  pop     r12
0x18001f840  pop     rdi
0x18001f841  pop     rsi
0x18001f842  pop     rbx
0x18001f843  pop     rbp
0x18001f844  retn
0x18001f845  mov     rax, [rax]
0x18001f848  mov     edx, 4000103Dh
0x18001f84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f852  lea     r9, aNfsMultiServer; "NFS Multi Server Namespace"
0x18001f859  mov     [rsp+2A0h+pParameter], r12
0x18001f85e  lea     r8, [rsp+2A0h+hResource]
0x18001f863  mov     rdx, r14
0x18001f866  mov     rcx, r15
0x18001f869  call    NfsCreateNfsResourceEx
0x18001f86e  mov     rsi, [rsp+2A0h+hResource]
0x18001f873  mov     ebx, eax
0x18001f875  test    eax, eax
0x18001f877  jnz     short loc_18001F887
0x18001f879  test    rsi, rsi
0x18001f87c  jz      short loc_18001F887
0x18001f87e  lea     r12d, [rax+1]
0x18001f882  jmp     loc_18001F77C
0x18001f887  cmp     ebx, 1734h
0x18001f88d  jnz     loc_18001F92C
0x18001f893  xor     edx, edx; Val
0x18001f895  lea     rcx, [rsp+2A0h+var_250]; void *
0x18001f89a  mov     r8d, 1FEh; Size
0x18001f8a0  call    memset_0
0x18001f8a5  lea     rax, [rsp+2A0h+var_250]
0x18001f8aa  mov     [rsp+2A0h+var_260], 0FFh
0x18001f8b3  xor     ecx, ecx; lpszClusterName
0x18001f8b5  mov     [rsp+2A0h+hResource], rax
0x18001f8ba  call    cs:__imp_OpenCluster
0x18001f8c0  mov     [rsp+2A0h+hCluster], rax
0x18001f8c5  test    rax, rax
0x18001f8c8  jnz     short loc_18001F8D5
0x18001f8ca  call    cs:__imp_GetLastError
0x18001f8d0  mov     r12d, eax
0x18001f8d3  jmp     short loc_18001F906
0x18001f8d5  lea     rcx, [rsp+2A0h+hResource]
0x18001f8da  xor     edx, edx; hSelf
0x18001f8dc  mov     [rsp+2A0h+pParameter], rcx; pParameter
0x18001f8e1  lea     r9, NfsClusMSNResourceEnumGetDnsNameCallBack; pResCallBack
0x18001f8e8  mov     rcx, rax; hCluster
0x18001f8eb  lea     r8, aNfsMultiServer; "NFS Multi Server Namespace"
0x18001f8f2  call    cs:__imp_ResUtilEnumResourcesEx
0x18001f8f8  mov     rcx, [rsp+2A0h+hCluster]; hCluster
0x18001f8fd  mov     r12d, eax
0x18001f900  call    cs:__imp_CloseCluster
0x18001f906  test    r12d, r12d
0x18001f909  jnz     short loc_18001F937
0x18001f90b  mov     rax, [rdi]
0x18001f90e  lea     r9, [rsp+2A0h+var_250]
0x18001f913  mov     edx, 1734h
0x18001f918  mov     r8d, 0C000106Ch
0x18001f91e  mov     rcx, rdi
0x18001f921  mov     rax, [rax+28h]
0x18001f925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f92a  jmp     short loc_18001F937
0x18001f92c  xor     r12d, r12d
0x18001f92f  test    ebx, ebx
0x18001f931  jz      loc_18001F77C
0x18001f937  mov     rax, [rdi]
0x18001f93a  mov     r8d, 0C000103Ch
0x18001f940  mov     edx, ebx
0x18001f942  mov     rcx, rdi
0x18001f945  mov     rax, [rax+28h]
0x18001f949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f94e  jmp     loc_18001F7CD
```
