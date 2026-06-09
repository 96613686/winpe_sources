# NfsClusGetResourceHandleIfMatch

- ea: `0x18002a39c`
- end: `0x18002a431`
- name: `NfsClusGetResourceHandleIfMatch`
- size: `149`
- prototype: `__int64 __fastcall(HCLUSTER hCluster, HRESENUM hResEnum, DWORD dwIndex, LPCWSTR lpszResourceTypeName, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029ff4`

## callees

- `0x180029c74`
- `0x18002a39c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a415`
- `KERNEL32!GetLastError` at `0x18002a415`
- `KERNEL32!LocalFree` at `0x18002a420`
- `KERNEL32!LocalFree` at `0x18002a420`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x18002a3ee`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x18002a3ee`
- `CLUSAPI!OpenClusterResource` at `0x18002a3da`
- `CLUSAPI!OpenClusterResource` at `0x18002a3da`
- `CLUSAPI!CloseClusterResource` at `0x18002a400`
- `CLUSAPI!CloseClusterResource` at `0x18002a400`

## pseudocode

```c
__int64 __fastcall NfsClusGetResourceHandleIfMatch(
        HCLUSTER hCluster,
        HRESENUM hResEnum,
        DWORD dwIndex,
        LPCWSTR lpszResourceTypeName,
        struct _HRESOURCE **a5)
{
  DWORD ResourceNameFromResEnum; // edi
  struct _HRESOURCE *v8; // rax
  struct _HRESOURCE *v9; // rbx

  ResourceNameFromResEnum = GetResourceNameFromResEnum(hResEnum, dwIndex);
  if ( !ResourceNameFromResEnum )
  {
    v8 = OpenClusterResource(hCluster, 0);
    v9 = v8;
    if ( v8 )
    {
      if ( !ResUtilResourceTypesEqual(lpszResourceTypeName, v8) )
      {
        ResourceNameFromResEnum = 1169;
        CloseClusterResource(v9);
        v9 = 0;
      }
      *a5 = v9;
    }
    else
    {
      ResourceNameFromResEnum = GetLastError();
    }
    LocalFree(0);
  }
  return ResourceNameFromResEnum;
}

```

## disassembly

```asm
0x18002a39c  push    rbx
0x18002a39e  push    rbp
0x18002a39f  push    rsi
0x18002a3a0  push    rdi
0x18002a3a1  sub     rsp, 38h
0x18002a3a5  mov     eax, r8d
0x18002a3a8  mov     [rsp+58h+lpszResourceName], 0
0x18002a3b1  mov     r10, rdx
0x18002a3b4  lea     r8, [rsp+58h+lpszResourceName]
0x18002a3b9  mov     rbx, rcx
0x18002a3bc  mov     edx, eax; dwIndex
0x18002a3be  mov     rcx, r10; hResEnum
0x18002a3c1  mov     rbp, r9
0x18002a3c4  call    GetResourceNameFromResEnum
0x18002a3c9  mov     edi, eax
0x18002a3cb  test    eax, eax
0x18002a3cd  jnz     short loc_18002A426
0x18002a3cf  mov     rsi, [rsp+58h+lpszResourceName]
0x18002a3d4  mov     rcx, rbx; hCluster
0x18002a3d7  mov     rdx, rsi; lpszResourceName
0x18002a3da  call    cs:__imp_OpenClusterResource
0x18002a3e0  mov     rbx, rax
0x18002a3e3  test    rax, rax
0x18002a3e6  jz      short loc_18002A415
0x18002a3e8  mov     rdx, rax; hResource
0x18002a3eb  mov     rcx, rbp; lpszResourceTypeName
0x18002a3ee  call    cs:__imp_ResUtilResourceTypesEqual
0x18002a3f4  test    eax, eax
0x18002a3f6  jnz     short loc_18002A408
0x18002a3f8  mov     rcx, rbx; hResource
0x18002a3fb  mov     edi, 491h
0x18002a400  call    cs:__imp_CloseClusterResource
0x18002a406  xor     ebx, ebx
0x18002a408  mov     rax, [rsp+58h+arg_20]
0x18002a410  mov     [rax], rbx
0x18002a413  jmp     short loc_18002A41D
0x18002a415  call    cs:__imp_GetLastError
0x18002a41b  mov     edi, eax
0x18002a41d  mov     rcx, rsi; hMem
0x18002a420  call    cs:__imp_LocalFree
0x18002a426  mov     eax, edi
0x18002a428  add     rsp, 38h
0x18002a42c  pop     rdi
0x18002a42d  pop     rsi
0x18002a42e  pop     rbp
0x18002a42f  pop     rbx
0x18002a430  retn
```
