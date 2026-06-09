# FveOpenAlgorithmProvider

- ea: `0x18001ea4c`
- end: `0x18001eaee`
- name: `FveOpenAlgorithmProvider`
- size: `162`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, ULONG dwFlags)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18011d1d0`
- `0x18011d418`
- `0x18011d480`
- `0x18011d4e8`

## callees

- `0x18001d830`
- `0x18001ea4c`
- `0x180030060`
- `0x18011d388`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001ea8b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001eaba`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001ea8b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001eaba`

## pseudocode

```c
__int64 __fastcall FveOpenAlgorithmProvider(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, ULONG dwFlags)
{
  NTSTATUS v6; // edi
  LPCWSTR pszImplementation[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v9; // [rsp+78h] [rbp+20h] BYREF

  pszImplementation[0] = 0;
  v9 = 0;
  FveRegistryGetAlgorithmProvider(pszImplementation, &v9);
  v6 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, pszImplementation[0], dwFlags);
  if ( v6 < 0 )
  {
    if ( !pszImplementation[0] )
      return (unsigned int)v6;
    if ( (unsigned __int8)FveDefaultToExistingProviders() )
      v6 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, 0, dwFlags);
  }
  if ( pszImplementation[0] )
    FveLibFreeWithTag(pszImplementation[0], v9, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ea4c  mov     rax, rsp
0x18001ea4f  push    rbp
0x18001ea50  push    rsi
0x18001ea51  push    rdi
0x18001ea52  push    r14
0x18001ea54  sub     rsp, 38h
0x18001ea58  mov     rbp, rdx
0x18001ea5b  mov     qword ptr [rax-38h], 0
0x18001ea63  mov     r14, rcx
0x18001ea66  mov     dword ptr [rax+20h], 0
0x18001ea6d  lea     rdx, [rax+20h]
0x18001ea71  mov     esi, r8d
0x18001ea74  lea     rcx, [rax-38h]
0x18001ea78  call    FveRegistryGetAlgorithmProvider
0x18001ea7d  mov     r8, [rsp+58h+pszImplementation]; pszImplementation
0x18001ea82  mov     r9d, esi; dwFlags
0x18001ea85  mov     rdx, rbp; pszAlgId
0x18001ea88  mov     rcx, r14; phAlgorithm
0x18001ea8b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001ea92  nop     dword ptr [rax+rax+00h]
0x18001ea97  mov     edi, eax
0x18001ea99  test    eax, eax
0x18001ea9b  jns     short loc_18001EAC8
0x18001ea9d  cmp     [rsp+58h+pszImplementation], 0
0x18001eaa3  jz      short loc_18001EAE1
0x18001eaa5  call    FveDefaultToExistingProviders
0x18001eaaa  test    al, al
0x18001eaac  jz      short loc_18001EAC8
0x18001eaae  mov     r9d, esi; dwFlags
0x18001eab1  xor     r8d, r8d; pszImplementation
0x18001eab4  mov     rdx, rbp; pszAlgId
0x18001eab7  mov     rcx, r14; phAlgorithm
0x18001eaba  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001eac1  nop     dword ptr [rax+rax+00h]
0x18001eac6  mov     edi, eax
0x18001eac8  cmp     [rsp+58h+pszImplementation], 0
0x18001eace  jz      short loc_18001EAE1
0x18001ead0  mov     edx, [rsp+58h+arg_18]
0x18001ead4  xor     r8d, r8d
0x18001ead7  mov     rcx, [rsp+58h+pszImplementation]
0x18001eadc  call    FveLibFreeWithTag
0x18001eae1  mov     eax, edi
0x18001eae3  add     rsp, 38h
0x18001eae7  pop     r14
0x18001eae9  pop     rdi
0x18001eaea  pop     rsi
0x18001eaeb  pop     rbp
0x18001eaec  retn
```
