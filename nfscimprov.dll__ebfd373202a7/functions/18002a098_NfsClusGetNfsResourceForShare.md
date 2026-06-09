# NfsClusGetNfsResourceForShare

- ea: `0x18002a098`
- end: `0x18002a1cf`
- name: `NfsClusGetNfsResourceForShare`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f95c`
- `0x18001ffbc`

## callees

- `0x180029768`
- `0x180029ff4`
- `0x18002a098`
- `0x18002aaac`
- `0x18002ad9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a0dc`
- `KERNEL32!GetLastError` at `0x18002a110`
- `KERNEL32!GetLastError` at `0x18002a0dc`
- `KERNEL32!GetLastError` at `0x18002a110`
- `CLUSAPI!CloseClusterGroup` at `0x18002a1a2`
- `CLUSAPI!CloseClusterGroup` at `0x18002a1a2`
- `CLUSAPI!CloseCluster` at `0x18002a181`
- `CLUSAPI!CloseCluster` at `0x18002a181`
- `CLUSAPI!OpenCluster` at `0x18002a0ce`
- `CLUSAPI!OpenCluster` at `0x18002a0ce`
- `CLUSAPI!CloseClusterResource` at `0x18002a178`
- `CLUSAPI!CloseClusterResource` at `0x18002a194`
- `CLUSAPI!CloseClusterResource` at `0x18002a1b0`
- `CLUSAPI!CloseClusterResource` at `0x18002a178`
- `CLUSAPI!CloseClusterResource` at `0x18002a194`
- `CLUSAPI!CloseClusterResource` at `0x18002a1b0`

## pseudocode

```c
DWORD __fastcall NfsClusGetNfsResourceForShare(_WORD *a1, const wchar_t *a2, _QWORD *a3)
{
  struct _HRESOURCE *v4; // rsi
  struct _HCLUSTER *v7; // rax
  struct _HCLUSTER *v8; // r14
  struct _HGROUP *ResourceGroupHandle; // rbx
  DWORD DependentResource; // edi
  DWORD NetworkNameResourceInGroup; // eax
  HRESOURCE v13; // [rsp+28h] [rbp-30h] BYREF
  HRESOURCE v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  v4 = 0;
  v13 = 0;
  v7 = OpenCluster(0);
  v8 = v7;
  if ( !v7 )
    return GetLastError();
  if ( (unsigned int)NfsGetDiskResource(v7, a1, &v14) )
  {
    ResourceGroupHandle = (struct _HGROUP *)GetResourceGroupHandle(v8, v14);
    if ( ResourceGroupHandle || (DependentResource = GetLastError()) == 0 )
    {
      NetworkNameResourceInGroup = NfsGetNetworkNameResourceInGroup((__int64)v8, ResourceGroupHandle, a2, &v13);
      v4 = v13;
      DependentResource = NetworkNameResourceInGroup;
      if ( !NetworkNameResourceInGroup )
      {
        DependentResource = NfsClusGetDependentResource(v8, v13, L"Network File System");
        if ( !DependentResource )
          *a3 = 0;
      }
    }
  }
  else
  {
    ResourceGroupHandle = 0;
    DependentResource = 1168;
  }
  CloseCluster(v8);
  if ( v14 )
    CloseClusterResource(v14);
  if ( ResourceGroupHandle )
    CloseClusterGroup(ResourceGroupHandle);
  if ( v4 )
    CloseClusterResource(v4);
  return DependentResource;
}

```

## disassembly

```asm
0x18002a098  mov     rax, rsp
0x18002a09b  mov     [rax+8], rbx
0x18002a09f  mov     [rax+10h], rbp
0x18002a0a3  push    rsi
0x18002a0a4  push    rdi
0x18002a0a5  push    r12
0x18002a0a7  push    r13
0x18002a0a9  push    r14
0x18002a0ab  sub     rsp, 30h
0x18002a0af  mov     rbx, rcx
0x18002a0b2  mov     qword ptr [rax+20h], 0
0x18002a0ba  xor     esi, esi
0x18002a0bc  xor     ebp, ebp
0x18002a0be  xor     ecx, ecx; lpszClusterName
0x18002a0c0  mov     [rax-30h], rsi
0x18002a0c4  mov     [rax-38h], rbp
0x18002a0c8  mov     r13, r8
0x18002a0cb  mov     r12, rdx
0x18002a0ce  call    cs:__imp_OpenCluster
0x18002a0d4  mov     r14, rax
0x18002a0d7  test    rax, rax
0x18002a0da  jnz     short loc_18002A0E7
0x18002a0dc  call    cs:__imp_GetLastError
0x18002a0e2  jmp     loc_18002A1B8
0x18002a0e7  lea     r8, [rsp+58h+arg_18]
0x18002a0ec  mov     rdx, rbx
0x18002a0ef  mov     rcx, r14; hCluster
0x18002a0f2  call    NfsGetDiskResource
0x18002a0f7  test    eax, eax
0x18002a0f9  jz      short loc_18002A169
0x18002a0fb  mov     rdx, [rsp+58h+arg_18]; hResource
0x18002a100  mov     rcx, r14; hCluster
0x18002a103  call    GetResourceGroupHandle
0x18002a108  mov     rbx, rax
0x18002a10b  test    rax, rax
0x18002a10e  jnz     short loc_18002A11C
0x18002a110  call    cs:__imp_GetLastError
0x18002a116  mov     edi, eax
0x18002a118  test    eax, eax
0x18002a11a  jnz     short loc_18002A17E
0x18002a11c  lea     r9, [rsp+58h+var_30]
0x18002a121  mov     r8, r12
0x18002a124  mov     rdx, rbx
0x18002a127  mov     rcx, r14
0x18002a12a  call    NfsGetNetworkNameResourceInGroup
0x18002a12f  mov     rsi, [rsp+58h+var_30]
0x18002a134  mov     edi, eax
0x18002a136  test    eax, eax
0x18002a138  jnz     short loc_18002A17E
0x18002a13a  lea     r9, [rsp+58h+hResource]
0x18002a13f  mov     rdx, rsi; hResource
0x18002a142  lea     r8, szResourceTypeName; "Network File System"
0x18002a149  mov     rcx, r14; hCluster
0x18002a14c  call    NfsClusGetDependentResource
0x18002a151  mov     edi, eax
0x18002a153  test    eax, eax
0x18002a155  jnz     short loc_18002A162
0x18002a157  mov     rax, [rsp+58h+hResource]
0x18002a15c  mov     [r13+0], rax
0x18002a160  jmp     short loc_18002A17E
0x18002a162  mov     rbp, [rsp+58h+hResource]
0x18002a167  jmp     short loc_18002A170
0x18002a169  xor     ebx, ebx
0x18002a16b  mov     edi, 490h
0x18002a170  test    rbp, rbp
0x18002a173  jz      short loc_18002A17E
0x18002a175  mov     rcx, rbp; hResource
0x18002a178  call    cs:__imp_CloseClusterResource
0x18002a17e  mov     rcx, r14; hCluster
0x18002a181  call    cs:__imp_CloseCluster
0x18002a187  cmp     [rsp+58h+arg_18], 0
0x18002a18d  jz      short loc_18002A19A
0x18002a18f  mov     rcx, [rsp+58h+arg_18]; hResource
0x18002a194  call    cs:__imp_CloseClusterResource
0x18002a19a  test    rbx, rbx
0x18002a19d  jz      short loc_18002A1A8
0x18002a19f  mov     rcx, rbx; hGroup
0x18002a1a2  call    cs:__imp_CloseClusterGroup
0x18002a1a8  test    rsi, rsi
0x18002a1ab  jz      short loc_18002A1B6
0x18002a1ad  mov     rcx, rsi; hResource
0x18002a1b0  call    cs:__imp_CloseClusterResource
0x18002a1b6  mov     eax, edi
0x18002a1b8  mov     rbx, [rsp+58h+arg_0]
0x18002a1bd  mov     rbp, [rsp+58h+arg_8]
0x18002a1c2  add     rsp, 30h
0x18002a1c6  pop     r14
0x18002a1c8  pop     r13
0x18002a1ca  pop     r12
0x18002a1cc  pop     rdi
0x18002a1cd  pop     rsi
0x18002a1ce  retn
```
