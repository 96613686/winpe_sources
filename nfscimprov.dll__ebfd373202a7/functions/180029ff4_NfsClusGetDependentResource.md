# NfsClusGetDependentResource

- ea: `0x180029ff4`
- end: `0x18002a092`
- name: `NfsClusGetDependentResource`
- size: `158`
- prototype: `__int64 __fastcall(HCLUSTER hCluster, HRESOURCE hResource, LPCWSTR lpszResourceTypeName)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ef68`
- `0x18001f2d8`
- `0x18001f674`
- `0x18002a098`
- `0x18002a1d8`

## callees

- `0x180029ff4`
- `0x18002a39c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a02c`
- `KERNEL32!GetLastError` at `0x18002a02c`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002a01e`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002a01e`
- `CLUSAPI!ClusterResourceCloseEnum` at `0x18002a07d`
- `CLUSAPI!ClusterResourceCloseEnum` at `0x18002a07d`

## pseudocode

```c
__int64 __fastcall NfsClusGetDependentResource(
        HCLUSTER hCluster,
        HRESOURCE hResource,
        LPCWSTR lpszResourceTypeName,
        __int64 *a4)
{
  struct _HRESENUM *v7; // rsi
  DWORD LastError; // ebx
  DWORD i; // edi
  DWORD ResourceHandleIfMatch; // eax
  __int64 v12[9]; // [rsp+30h] [rbp-48h] BYREF

  v12[0] = 0;
  v7 = ClusterResourceOpenEnum(hResource, 2u);
  if ( v7 || (LastError = GetLastError()) == 0 )
  {
    for ( i = 0; ; ++i )
    {
      ResourceHandleIfMatch = NfsClusGetResourceHandleIfMatch(hCluster, v7, i, lpszResourceTypeName, (__int64)v12);
      LastError = ResourceHandleIfMatch;
      if ( !ResourceHandleIfMatch )
        break;
      if ( ResourceHandleIfMatch == 259 )
      {
        LastError = 1168;
        goto LABEL_9;
      }
    }
    *a4 = v12[0];
LABEL_9:
    if ( v7 )
      ClusterResourceCloseEnum(v7);
  }
  return LastError;
}

```

## disassembly

```asm
0x180029ff4  push    rbx
0x180029ff6  push    rbp
0x180029ff7  push    rsi
0x180029ff8  push    rdi
0x180029ff9  push    r14
0x180029ffb  push    r15
0x180029ffd  sub     rsp, 48h
0x18002a001  mov     rax, rdx
0x18002a004  mov     [rsp+78h+var_48], 0
0x18002a00d  mov     r15, rcx
0x18002a010  mov     edx, 2; dwType
0x18002a015  mov     rcx, rax; hResource
0x18002a018  mov     r14, r9
0x18002a01b  mov     rbp, r8
0x18002a01e  call    cs:__imp_ClusterResourceOpenEnum
0x18002a024  mov     rsi, rax
0x18002a027  test    rax, rax
0x18002a02a  jnz     short loc_18002A038
0x18002a02c  call    cs:__imp_GetLastError
0x18002a032  mov     ebx, eax
0x18002a034  test    eax, eax
0x18002a036  jnz     short loc_18002A083
0x18002a038  xor     edi, edi
0x18002a03a  lea     rax, [rsp+78h+var_48]
0x18002a03f  mov     r9, rbp; lpszResourceTypeName
0x18002a042  mov     r8d, edi; dwIndex
0x18002a045  mov     [rsp+78h+var_58], rax; __int64
0x18002a04a  mov     rdx, rsi; hResEnum
0x18002a04d  mov     rcx, r15; hCluster
0x18002a050  call    NfsClusGetResourceHandleIfMatch
0x18002a055  mov     ebx, eax
0x18002a057  test    eax, eax
0x18002a059  jz      short loc_18002A06D
0x18002a05b  cmp     eax, 103h
0x18002a060  jz      short loc_18002A066
0x18002a062  inc     edi
0x18002a064  jmp     short loc_18002A03A
0x18002a066  mov     ebx, 490h
0x18002a06b  jmp     short loc_18002A075
0x18002a06d  mov     rax, [rsp+78h+var_48]
0x18002a072  mov     [r14], rax
0x18002a075  test    rsi, rsi
0x18002a078  jz      short loc_18002A083
0x18002a07a  mov     rcx, rsi; hResEnum
0x18002a07d  call    cs:__imp_ClusterResourceCloseEnum
0x18002a083  mov     eax, ebx
0x18002a085  add     rsp, 48h
0x18002a089  pop     r15
0x18002a08b  pop     r14
0x18002a08d  pop     rdi
0x18002a08e  pop     rsi
0x18002a08f  pop     rbp
0x18002a090  pop     rbx
0x18002a091  retn
```
