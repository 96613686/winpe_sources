# CClfsHashObject::InitializeGlobals(void)

- ea: `0x14004ee7c`
- end: `0x14004efe1`
- name: `?InitializeGlobals@CClfsHashObject@@SAJXZ`
- size: `357`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004c5a0`

## callees

- `0x14004ee7c`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004ef92`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004efc5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004ef92`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004efc5`
- `cng!BCryptGetProperty` at `0x14004ef19`
- `cng!BCryptGetProperty` at `0x14004ef57`
- `cng!BCryptGetProperty` at `0x14004ef19`
- `cng!BCryptGetProperty` at `0x14004ef57`
- `cng!BCryptOpenAlgorithmProvider` at `0x14004eea8`
- `cng!BCryptOpenAlgorithmProvider` at `0x14004eecf`
- `cng!BCryptOpenAlgorithmProvider` at `0x14004eea8`
- `cng!BCryptOpenAlgorithmProvider` at `0x14004eecf`

## pseudocode

```c
NTSTATUS CClfsHashObject::InitializeGlobals(void)
{
  NTSTATUS result; // eax
  NTSTATUS v1; // ebx
  ULONG pcbResult; // [rsp+50h] [rbp+8h] BYREF

  pcbResult = 0;
  CClfsHashObject::m_fReusableHash = 1;
  if ( BCryptOpenAlgorithmProvider(&CClfsHashObject::m_hSha256Algorithm, L"SHA256", 0, 0x28u) < 0 )
  {
    result = BCryptOpenAlgorithmProvider(&CClfsHashObject::m_hSha256Algorithm, L"SHA256", 0, 8u);
    if ( result < 0 )
      return result;
    CClfsHashObject::m_fReusableHash = 0;
  }
  result = BCryptGetProperty(
             CClfsHashObject::m_hSha256Algorithm,
             L"ObjectLength",
             &CClfsHashObject::m_cbSha256HashObject,
             4u,
             &pcbResult,
             0);
  if ( result >= 0 )
  {
    result = BCryptGetProperty(
               CClfsHashObject::m_hSha256Algorithm,
               L"HashDigestLength",
               (PUCHAR)&CClfsHashObject::m_cbSha256Hash,
               4u,
               &pcbResult,
               0);
    v1 = result;
    if ( result >= 0 )
    {
      ExInitializePagedLookasideList(
        &CClfsHashObject::m_laSha256ObjectList,
        0,
        0,
        0,
        *(unsigned int *)&CClfsHashObject::m_cbSha256HashObject,
        0x54666C43u,
        0);
      ExInitializePagedLookasideList(&CClfsHashObject::m_laHashObjectList, 0, 0, 0, 0x18u, 0x4D666C43u, 0);
      result = v1;
      CClfsHashObject::m_fGlobalInitialized = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004ee7c  push    rbx
0x14004ee7e  sub     rsp, 40h
0x14004ee82  mov     r9d, 28h ; '('; dwFlags
0x14004ee88  mov     [rsp+48h+arg_0], 0
0x14004ee90  xor     r8d, r8d; pszImplementation
0x14004ee93  mov     cs:?m_fReusableHash@CClfsHashObject@@0EA, 1; uchar CClfsHashObject::m_fReusableHash
0x14004ee9a  lea     rdx, pszAlgId; "SHA256"
0x14004eea1  lea     rcx, ?m_hSha256Algorithm@CClfsHashObject@@0PEAXEA; phAlgorithm
0x14004eea8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14004eeaf  nop     dword ptr [rax+rax+00h]
0x14004eeb4  test    eax, eax
0x14004eeb6  jns     short loc_14004EEEA
0x14004eeb8  mov     r9d, 8; dwFlags
0x14004eebe  lea     rdx, pszAlgId; "SHA256"
0x14004eec5  xor     r8d, r8d; pszImplementation
0x14004eec8  lea     rcx, ?m_hSha256Algorithm@CClfsHashObject@@0PEAXEA; phAlgorithm
0x14004eecf  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14004eed6  nop     dword ptr [rax+rax+00h]
0x14004eedb  test    eax, eax
0x14004eedd  js      loc_14004EFDA
0x14004eee3  mov     cs:?m_fReusableHash@CClfsHashObject@@0EA, 0; uchar CClfsHashObject::m_fReusableHash
0x14004eeea  mov     rcx, cs:?m_hSha256Algorithm@CClfsHashObject@@0PEAXEA; hObject
0x14004eef1  lea     rax, [rsp+48h+arg_0]
0x14004eef6  mov     ebx, 4
0x14004eefb  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14004ef03  mov     r9d, ebx; cbOutput
0x14004ef06  mov     [rsp+48h+pcbResult], rax; pcbResult
0x14004ef0b  lea     r8, ?m_cbSha256HashObject@CClfsHashObject@@0KA; pbOutput
0x14004ef12  lea     rdx, pszProperty; "ObjectLength"
0x14004ef19  call    cs:__imp_BCryptGetProperty
0x14004ef20  nop     dword ptr [rax+rax+00h]
0x14004ef25  test    eax, eax
0x14004ef27  js      loc_14004EFDA
0x14004ef2d  mov     rcx, cs:?m_hSha256Algorithm@CClfsHashObject@@0PEAXEA; hObject
0x14004ef34  lea     rax, [rsp+48h+arg_0]
0x14004ef39  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14004ef41  lea     r8, ?m_cbSha256Hash@CClfsHashObject@@0KA; pbOutput
0x14004ef48  mov     r9d, ebx; cbOutput
0x14004ef4b  mov     [rsp+48h+pcbResult], rax; pcbResult
0x14004ef50  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14004ef57  call    cs:__imp_BCryptGetProperty
0x14004ef5e  nop     dword ptr [rax+rax+00h]
0x14004ef63  mov     ebx, eax
0x14004ef65  test    eax, eax
0x14004ef67  js      short loc_14004EFDA
0x14004ef69  mov     ecx, cs:?m_cbSha256HashObject@CClfsHashObject@@0KA; ulong CClfsHashObject::m_cbSha256HashObject
0x14004ef6f  xor     eax, eax
0x14004ef71  mov     [rsp+48h+Depth], ax; Depth
0x14004ef76  xor     r9d, r9d; Flags
0x14004ef79  mov     [rsp+48h+dwFlags], 54666C43h; Tag
0x14004ef81  xor     r8d, r8d; Free
0x14004ef84  mov     [rsp+48h+pcbResult], rcx; Size
0x14004ef89  xor     edx, edx; Allocate
0x14004ef8b  lea     rcx, ?m_laSha256ObjectList@CClfsHashObject@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004ef92  call    cs:__imp_ExInitializePagedLookasideList
0x14004ef99  nop     dword ptr [rax+rax+00h]
0x14004ef9e  xor     eax, eax
0x14004efa0  lea     rcx, ?m_laHashObjectList@CClfsHashObject@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004efa7  mov     [rsp+48h+Depth], ax; Depth
0x14004efac  xor     r9d, r9d; Flags
0x14004efaf  mov     [rsp+48h+dwFlags], 4D666C43h; Tag
0x14004efb7  xor     r8d, r8d; Free
0x14004efba  xor     edx, edx; Allocate
0x14004efbc  mov     [rsp+48h+pcbResult], 18h; Size
0x14004efc5  call    cs:__imp_ExInitializePagedLookasideList
0x14004efcc  nop     dword ptr [rax+rax+00h]
0x14004efd1  mov     eax, ebx
0x14004efd3  mov     cs:?m_fGlobalInitialized@CClfsHashObject@@0EA, 1; uchar CClfsHashObject::m_fGlobalInitialized
0x14004efda  add     rsp, 40h
0x14004efde  pop     rbx
0x14004efdf  retn
```
