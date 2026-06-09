# NfsClusGetResourceIdForNetworkName

- ea: `0x18002a4dc`
- end: `0x18002a545`
- name: `NfsClusGetResourceIdForNetworkName`
- size: `105`
- prototype: `__int64 __fastcall(LPCWSTR lpszResourceName)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a834`
- `0x18001b224`
- `0x18001b680`

## callees

- `0x18002a438`
- `0x18002a4dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a532`
- `KERNEL32!GetLastError` at `0x18002a532`
- `CLUSAPI!CloseCluster` at `0x18002a52a`
- `CLUSAPI!CloseCluster` at `0x18002a52a`
- `CLUSAPI!OpenClusterResource` at `0x18002a503`
- `CLUSAPI!OpenClusterResource` at `0x18002a503`
- `CLUSAPI!OpenCluster` at `0x18002a4ed`
- `CLUSAPI!OpenCluster` at `0x18002a4ed`
- `CLUSAPI!CloseClusterResource` at `0x18002a521`
- `CLUSAPI!CloseClusterResource` at `0x18002a521`

## pseudocode

```c
__int64 __fastcall NfsClusGetResourceIdForNetworkName(LPCWSTR lpszResourceName, __int64 a2)
{
  struct _HCLUSTER *v4; // rax
  struct _HCLUSTER *v5; // rdi
  unsigned int ResourceId; // ebx
  HRESOURCE v7; // rax
  struct _HRESOURCE *v8; // rsi

  v4 = OpenCluster(0);
  v5 = v4;
  if ( v4 )
  {
    ResourceId = 0;
    v7 = OpenClusterResource(v4, lpszResourceName);
    v8 = v7;
    if ( v7 )
    {
      ResourceId = NfsClusGetResourceId(v7, a2);
      CloseClusterResource(v8);
    }
    CloseCluster(v5);
  }
  else
  {
    return GetLastError();
  }
  return ResourceId;
}

```

## disassembly

```asm
0x18002a4dc  push    rbx
0x18002a4de  push    rbp
0x18002a4df  push    rsi
0x18002a4e0  push    rdi
0x18002a4e1  sub     rsp, 28h
0x18002a4e5  mov     rsi, rcx
0x18002a4e8  mov     rbp, rdx
0x18002a4eb  xor     ecx, ecx; lpszClusterName
0x18002a4ed  call    cs:__imp_OpenCluster
0x18002a4f3  mov     rdi, rax
0x18002a4f6  test    rax, rax
0x18002a4f9  jz      short loc_18002A532
0x18002a4fb  mov     rdx, rsi; lpszResourceName
0x18002a4fe  mov     rcx, rax; hCluster
0x18002a501  xor     ebx, ebx
0x18002a503  call    cs:__imp_OpenClusterResource
0x18002a509  mov     rsi, rax
0x18002a50c  test    rax, rax
0x18002a50f  jz      short loc_18002A527
0x18002a511  mov     rdx, rbp
0x18002a514  mov     rcx, rax
0x18002a517  call    NfsClusGetResourceId
0x18002a51c  mov     rcx, rsi; hResource
0x18002a51f  mov     ebx, eax
0x18002a521  call    cs:__imp_CloseClusterResource
0x18002a527  mov     rcx, rdi; hCluster
0x18002a52a  call    cs:__imp_CloseCluster
0x18002a530  jmp     short loc_18002A53A
0x18002a532  call    cs:__imp_GetLastError
0x18002a538  mov     ebx, eax
0x18002a53a  mov     eax, ebx
0x18002a53c  add     rsp, 28h
0x18002a540  pop     rdi
0x18002a541  pop     rsi
0x18002a542  pop     rbp
0x18002a543  pop     rbx
0x18002a544  retn
```
