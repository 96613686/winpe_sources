# NfsClusGetNfsResourceForShareEx

- ea: `0x18002a1d8`
- end: `0x18002a393`
- name: `NfsClusGetNfsResourceForShareEx`
- size: `443`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001fae8`
- `0x18001fcdc`
- `0x180020060`
- `0x180020114`

## callees

- `0x180029768`
- `0x180029ff4`
- `0x18002a1d8`
- `0x18002aaac`
- `0x18002ad9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a224`
- `KERNEL32!GetLastError` at `0x18002a289`
- `KERNEL32!GetLastError` at `0x18002a2c9`
- `KERNEL32!GetLastError` at `0x18002a224`
- `KERNEL32!GetLastError` at `0x18002a289`
- `KERNEL32!GetLastError` at `0x18002a2c9`
- `CLUSAPI!CloseClusterGroup` at `0x18002a35c`
- `CLUSAPI!CloseClusterGroup` at `0x18002a36a`
- `CLUSAPI!CloseClusterGroup` at `0x18002a35c`
- `CLUSAPI!CloseClusterGroup` at `0x18002a36a`
- `CLUSAPI!CloseCluster` at `0x18002a373`
- `CLUSAPI!CloseCluster` at `0x18002a373`
- `CLUSAPI!OpenClusterResource` at `0x18002a267`
- `CLUSAPI!OpenClusterResource` at `0x18002a267`
- `CLUSAPI!OpenCluster` at `0x18002a216`
- `CLUSAPI!OpenCluster` at `0x18002a216`
- `CLUSAPI!CloseClusterResource` at `0x18002a32e`
- `CLUSAPI!CloseClusterResource` at `0x18002a33c`
- `CLUSAPI!CloseClusterResource` at `0x18002a34a`
- `CLUSAPI!CloseClusterResource` at `0x18002a32e`
- `CLUSAPI!CloseClusterResource` at `0x18002a33c`
- `CLUSAPI!CloseClusterResource` at `0x18002a34a`

## pseudocode

```c
DWORD __fastcall NfsClusGetNfsResourceForShareEx(__int64 a1, const WCHAR *a2, int a3, _QWORD *a4)
{
  struct _HRESOURCE *v4; // rdi
  struct _HCLUSTER *v6; // rsi
  struct _HGROUP *ResourceGroupHandle; // r12
  const wchar_t *v9; // r13
  struct _HRESOURCE *v10; // rax
  DWORD LastError; // ebx
  const WCHAR *v12; // r8
  DWORD NetworkNameResourceInGroup; // eax
  struct _HRESOURCE *v14; // [rsp+28h] [rbp-18h] BYREF
  HRESOURCE hResource; // [rsp+30h] [rbp-10h]
  HGROUP hGroup; // [rsp+38h] [rbp-8h]

  v4 = 0;
  hResource = 0;
  v14 = 0;
  v6 = OpenCluster(0);
  if ( !v6 )
    return GetLastError();
  ResourceGroupHandle = 0;
  hGroup = 0;
  v9 = (const wchar_t *)((unsigned __int64)L"Network File System" & -(__int64)((a3 & 0x1000000) != 0));
  if ( (a3 & 0x2000000) != 0 )
  {
    v9 = L"NFS Multi Server Namespace";
LABEL_6:
    v10 = OpenClusterResource(v6, a2);
    v4 = v10;
    if ( !v10 || (hGroup = (HGROUP)GetResourceGroupHandle(v6, v10)) != 0 || (LastError = GetLastError()) == 0 )
    {
      v12 = v9;
      goto LABEL_15;
    }
    goto LABEL_19;
  }
  if ( v9 )
    goto LABEL_6;
  if ( !(unsigned int)NfsGetDiskResource(v6) )
  {
    LastError = 1168;
    goto LABEL_19;
  }
  ResourceGroupHandle = (struct _HGROUP *)GetResourceGroupHandle(v6, hResource);
  if ( ResourceGroupHandle || (LastError = GetLastError()) == 0 )
  {
    NetworkNameResourceInGroup = NfsGetNetworkNameResourceInGroup(v6, ResourceGroupHandle, a2, &v14);
    v4 = v14;
    LastError = NetworkNameResourceInGroup;
    if ( !NetworkNameResourceInGroup )
    {
      v12 = L"Network File System";
LABEL_15:
      LastError = NfsClusGetDependentResource(v6, v4, v12);
      if ( !LastError )
        *a4 = 0;
    }
LABEL_19:
    if ( v4 )
      CloseClusterResource(v4);
  }
  if ( hGroup )
    CloseClusterGroup(hGroup);
  if ( ResourceGroupHandle )
    CloseClusterGroup(ResourceGroupHandle);
  CloseCluster(v6);
  return LastError;
}

```

## disassembly

```asm
0x18002a1d8  mov     rax, rsp
0x18002a1db  mov     [rax+18h], rbx
0x18002a1df  mov     [rax+20h], r9
0x18002a1e3  mov     [rax+10h], rdx
0x18002a1e7  mov     [rax+8], rcx
0x18002a1eb  push    rbp
0x18002a1ec  push    rsi
0x18002a1ed  push    rdi
0x18002a1ee  push    r12
0x18002a1f0  push    r13
0x18002a1f2  push    r14
0x18002a1f4  push    r15
0x18002a1f6  mov     rbp, rsp
0x18002a1f9  sub     rsp, 40h
0x18002a1fd  xor     r14d, r14d
0x18002a200  xor     r15d, r15d
0x18002a203  xor     edi, edi
0x18002a205  mov     [rbp+hResource], r14
0x18002a209  xor     ecx, ecx; lpszClusterName
0x18002a20b  mov     [rbp+var_20], r15
0x18002a20f  mov     [rbp+var_18], rdi
0x18002a213  mov     ebx, r8d
0x18002a216  call    cs:__imp_OpenCluster
0x18002a21c  mov     rsi, rax
0x18002a21f  test    rax, rax
0x18002a222  jnz     short loc_18002A22F
0x18002a224  call    cs:__imp_GetLastError
0x18002a22a  jmp     loc_18002A37B
0x18002a22f  xor     r12d, r12d
0x18002a232  mov     [rbp+hGroup], rdi
0x18002a236  mov     eax, ebx
0x18002a238  lea     rcx, szResourceTypeName; "Network File System"
0x18002a23f  and     eax, 1000000h
0x18002a244  neg     eax
0x18002a246  sbb     r13, r13
0x18002a249  and     r13, rcx
0x18002a24c  bt      ebx, 19h
0x18002a250  jnb     short loc_18002A25B
0x18002a252  lea     r13, aNfsMultiServer; "NFS Multi Server Namespace"
0x18002a259  jmp     short loc_18002A260
0x18002a25b  test    r13, r13
0x18002a25e  jz      short loc_18002A29E
0x18002a260  mov     rdx, [rbp+lpszResourceName]; lpszResourceName
0x18002a264  mov     rcx, rsi; hCluster
0x18002a267  call    cs:__imp_OpenClusterResource
0x18002a26d  mov     rdi, rax
0x18002a270  test    rax, rax
0x18002a273  jz      short loc_18002A299
0x18002a275  mov     rdx, rax; hResource
0x18002a278  mov     rcx, rsi; hCluster
0x18002a27b  call    GetResourceGroupHandle
0x18002a280  mov     [rbp+hGroup], rax
0x18002a284  test    rax, rax
0x18002a287  jnz     short loc_18002A299
0x18002a289  call    cs:__imp_GetLastError
0x18002a28f  mov     ebx, eax
0x18002a291  test    eax, eax
0x18002a293  jnz     loc_18002A326
0x18002a299  mov     r8, r13
0x18002a29c  jmp     short loc_18002A2F9
0x18002a29e  mov     rdx, [rbp+arg_0]
0x18002a2a2  lea     r8, [rbp+hResource]
0x18002a2a6  mov     rcx, rsi; hCluster
0x18002a2a9  call    NfsGetDiskResource
0x18002a2ae  mov     r14, [rbp+hResource]
0x18002a2b2  test    eax, eax
0x18002a2b4  jz      short loc_18002A321
0x18002a2b6  mov     rdx, r14; hResource
0x18002a2b9  mov     rcx, rsi; hCluster
0x18002a2bc  call    GetResourceGroupHandle
0x18002a2c1  mov     r12, rax
0x18002a2c4  test    rax, rax
0x18002a2c7  jnz     short loc_18002A2D5
0x18002a2c9  call    cs:__imp_GetLastError
0x18002a2cf  mov     ebx, eax
0x18002a2d1  test    eax, eax
0x18002a2d3  jnz     short loc_18002A342
0x18002a2d5  mov     r8, [rbp+lpszResourceName]
0x18002a2d9  lea     r9, [rbp+var_18]
0x18002a2dd  mov     rdx, r12
0x18002a2e0  mov     rcx, rsi
0x18002a2e3  call    NfsGetNetworkNameResourceInGroup
0x18002a2e8  mov     rdi, [rbp+var_18]
0x18002a2ec  mov     ebx, eax
0x18002a2ee  test    eax, eax
0x18002a2f0  jnz     short loc_18002A326
0x18002a2f2  lea     r8, szResourceTypeName; "Network File System"
0x18002a2f9  lea     r9, [rbp+var_20]
0x18002a2fd  mov     rdx, rdi; hResource
0x18002a300  mov     rcx, rsi; hCluster
0x18002a303  call    NfsClusGetDependentResource
0x18002a308  mov     ebx, eax
0x18002a30a  test    eax, eax
0x18002a30c  jnz     short loc_18002A31B
0x18002a30e  mov     rcx, [rbp+arg_18]
0x18002a312  mov     rax, [rbp+var_20]
0x18002a316  mov     [rcx], rax
0x18002a319  jmp     short loc_18002A326
0x18002a31b  mov     r15, [rbp+var_20]
0x18002a31f  jmp     short loc_18002A326
0x18002a321  mov     ebx, 490h
0x18002a326  test    rdi, rdi
0x18002a329  jz      short loc_18002A334
0x18002a32b  mov     rcx, rdi; hResource
0x18002a32e  call    cs:__imp_CloseClusterResource
0x18002a334  test    r15, r15
0x18002a337  jz      short loc_18002A342
0x18002a339  mov     rcx, r15; hResource
0x18002a33c  call    cs:__imp_CloseClusterResource
0x18002a342  test    r14, r14
0x18002a345  jz      short loc_18002A350
0x18002a347  mov     rcx, r14; hResource
0x18002a34a  call    cs:__imp_CloseClusterResource
0x18002a350  mov     rax, [rbp+hGroup]
0x18002a354  test    rax, rax
0x18002a357  jz      short loc_18002A362
0x18002a359  mov     rcx, rax; hGroup
0x18002a35c  call    cs:__imp_CloseClusterGroup
0x18002a362  test    r12, r12
0x18002a365  jz      short loc_18002A370
0x18002a367  mov     rcx, r12; hGroup
0x18002a36a  call    cs:__imp_CloseClusterGroup
0x18002a370  mov     rcx, rsi; hCluster
0x18002a373  call    cs:__imp_CloseCluster
0x18002a379  mov     eax, ebx
0x18002a37b  mov     rbx, [rsp+40h+arg_10]
0x18002a383  add     rsp, 40h
0x18002a387  pop     r15
0x18002a389  pop     r14
0x18002a38b  pop     r13
0x18002a38d  pop     r12
0x18002a38f  pop     rdi
0x18002a390  pop     rsi
0x18002a391  pop     rbp
0x18002a392  retn
```
