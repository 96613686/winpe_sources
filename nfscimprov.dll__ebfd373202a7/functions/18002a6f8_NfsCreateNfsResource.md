# NfsCreateNfsResource

- ea: `0x18002a6f8`
- end: `0x18002a806`
- name: `NfsCreateNfsResource`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ef68`

## callees

- `0x180029768`
- `0x180029b78`
- `0x18002a6f8`
- `0x18002a984`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a7a9`
- `KERNEL32!GetLastError` at `0x18002a7a9`
- `KERNEL32!LocalFree` at `0x18002a7e7`
- `KERNEL32!LocalFree` at `0x18002a7e7`
- `CLUSAPI!CloseClusterGroup` at `0x18002a7d9`
- `CLUSAPI!CloseClusterGroup` at `0x18002a7d9`
- `CLUSAPI!OnlineClusterResource` at `0x18002a789`
- `CLUSAPI!OnlineClusterResource` at `0x18002a789`
- `CLUSAPI!DeleteClusterResource` at `0x18002a7bd`
- `CLUSAPI!DeleteClusterResource` at `0x18002a7bd`
- `CLUSAPI!AddClusterResourceDependency` at `0x18002a76e`
- `CLUSAPI!AddClusterResourceDependency` at `0x18002a77a`
- `CLUSAPI!AddClusterResourceDependency` at `0x18002a76e`
- `CLUSAPI!AddClusterResourceDependency` at `0x18002a77a`
- `CLUSAPI!CreateClusterResource` at `0x18002a75a`
- `CLUSAPI!CreateClusterResource` at `0x18002a75a`
- `CLUSAPI!CloseClusterResource` at `0x18002a7c6`
- `CLUSAPI!CloseClusterResource` at `0x18002a7c6`

## pseudocode

```c
__int64 __fastcall NfsCreateNfsResource(
        struct _HCLUSTER *a1,
        struct _HRESOURCE *a2,
        struct _HRESOURCE *a3,
        struct _HRESOURCE **a4)
{
  WCHAR *v4; // rsi
  struct _HGROUP *ResourceGroupHandle; // rbp
  DWORD v9; // eax
  DWORD v10; // edi
  struct _HRESOURCE *ClusterResource; // rax
  struct _HRESOURCE *v12; // rbx
  DWORD LastError; // eax
  LPCWSTR lpszResourceName; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  lpszResourceName = 0;
  *a4 = 0;
  ResourceGroupHandle = (struct _HGROUP *)GetResourceGroupHandle(a1, a2);
  if ( !ResourceGroupHandle )
  {
    v12 = 0;
    goto LABEL_8;
  }
  v9 = NfsCreateNfsResourceName(a3, &lpszResourceName);
  v4 = (WCHAR *)lpszResourceName;
  v10 = v9;
  if ( !v9 )
  {
    ClusterResource = CreateClusterResource(ResourceGroupHandle, lpszResourceName, L"Network File System", 0);
    v12 = ClusterResource;
    if ( ClusterResource )
    {
      AddClusterResourceDependency(ClusterResource, a2);
      v10 = AddClusterResourceDependency(v12, a3);
      if ( v10 )
        goto LABEL_12;
      v10 = OnlineClusterResource(v12);
      if ( v10 != 997 )
      {
LABEL_10:
        if ( !v10 )
        {
          *a4 = v12;
LABEL_14:
          if ( !ResourceGroupHandle )
            goto LABEL_16;
          goto LABEL_15;
        }
        if ( !v12 )
          goto LABEL_14;
LABEL_12:
        DeleteClusterResource(v12);
        CloseClusterResource(v12);
        goto LABEL_14;
      }
      LastError = WaitForTargetState(v12, 2);
LABEL_9:
      v10 = LastError;
      goto LABEL_10;
    }
LABEL_8:
    LastError = GetLastError();
    goto LABEL_9;
  }
LABEL_15:
  CloseClusterGroup(ResourceGroupHandle);
LABEL_16:
  if ( v4 )
    LocalFree(v4);
  return v10;
}

```

## disassembly

```asm
0x18002a6f8  mov     [rsp+arg_0], rbx
0x18002a6fd  mov     [rsp+arg_8], rbp
0x18002a702  push    rsi
0x18002a703  push    rdi
0x18002a704  push    r12
0x18002a706  push    r14
0x18002a708  push    r15
0x18002a70a  sub     rsp, 20h
0x18002a70e  xor     esi, esi
0x18002a710  mov     r15, r9
0x18002a713  mov     [rsp+48h+lpszResourceName], rsi
0x18002a718  mov     r14, r8
0x18002a71b  mov     [r9], rsi
0x18002a71e  mov     r12, rdx
0x18002a721  call    GetResourceGroupHandle
0x18002a726  mov     rbp, rax
0x18002a729  test    rax, rax
0x18002a72c  jz      short loc_18002A7A7
0x18002a72e  lea     rdx, [rsp+48h+lpszResourceName]
0x18002a733  mov     rcx, r14
0x18002a736  call    NfsCreateNfsResourceName
0x18002a73b  mov     rsi, [rsp+48h+lpszResourceName]
0x18002a740  mov     edi, eax
0x18002a742  test    eax, eax
0x18002a744  jnz     loc_18002A7D6
0x18002a74a  xor     r9d, r9d; dwFlags
0x18002a74d  lea     r8, szResourceTypeName; "Network File System"
0x18002a754  mov     rdx, rsi; lpszResourceName
0x18002a757  mov     rcx, rbp; hGroup
0x18002a75a  call    cs:__imp_CreateClusterResource
0x18002a760  mov     rbx, rax
0x18002a763  test    rax, rax
0x18002a766  jz      short loc_18002A7A9
0x18002a768  mov     rdx, r12; hDependsOn
0x18002a76b  mov     rcx, rax; hResource
0x18002a76e  call    cs:__imp_AddClusterResourceDependency
0x18002a774  mov     rdx, r14; hDependsOn
0x18002a777  mov     rcx, rbx; hResource
0x18002a77a  call    cs:__imp_AddClusterResourceDependency
0x18002a780  mov     edi, eax
0x18002a782  test    eax, eax
0x18002a784  jnz     short loc_18002A7BA
0x18002a786  mov     rcx, rbx; hResource
0x18002a789  call    cs:__imp_OnlineClusterResource
0x18002a78f  mov     edi, eax
0x18002a791  cmp     eax, 3E5h
0x18002a796  jnz     short loc_18002A7B1
0x18002a798  mov     edx, 2
0x18002a79d  mov     rcx, rbx
0x18002a7a0  call    WaitForTargetState
0x18002a7a5  jmp     short loc_18002A7AF
0x18002a7a7  xor     ebx, ebx
0x18002a7a9  call    cs:__imp_GetLastError
0x18002a7af  mov     edi, eax
0x18002a7b1  test    edi, edi
0x18002a7b3  jz      short loc_18002A7CE
0x18002a7b5  test    rbx, rbx
0x18002a7b8  jz      short loc_18002A7D1
0x18002a7ba  mov     rcx, rbx; hResource
0x18002a7bd  call    cs:__imp_DeleteClusterResource
0x18002a7c3  mov     rcx, rbx; hResource
0x18002a7c6  call    cs:__imp_CloseClusterResource
0x18002a7cc  jmp     short loc_18002A7D1
0x18002a7ce  mov     [r15], rbx
0x18002a7d1  test    rbp, rbp
0x18002a7d4  jz      short loc_18002A7DF
0x18002a7d6  mov     rcx, rbp; hGroup
0x18002a7d9  call    cs:__imp_CloseClusterGroup
0x18002a7df  test    rsi, rsi
0x18002a7e2  jz      short loc_18002A7ED
0x18002a7e4  mov     rcx, rsi; hMem
0x18002a7e7  call    cs:__imp_LocalFree
0x18002a7ed  mov     rbx, [rsp+48h+arg_0]
0x18002a7f2  mov     eax, edi
0x18002a7f4  mov     rbp, [rsp+48h+arg_8]
0x18002a7f9  add     rsp, 20h
0x18002a7fd  pop     r15
0x18002a7ff  pop     r14
0x18002a801  pop     r12
0x18002a803  pop     rdi
0x18002a804  pop     rsi
0x18002a805  retn
```
