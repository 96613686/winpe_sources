# StSecInitialize

- ea: `0x14000d604`
- end: `0x14000d7a0`
- name: `StSecInitialize`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140014300`

## callees

- `0x14000d604`
- `0x14000ddd0`
- `0x14000e858`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000d643`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000d6fa`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000d643`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000d6fa`
- `ksecdd!BCryptGetProperty` at `0x14000d684`
- `ksecdd!BCryptGetProperty` at `0x14000d6c5`
- `ksecdd!BCryptGetProperty` at `0x14000d73b`
- `ksecdd!BCryptGetProperty` at `0x14000d778`
- `ksecdd!BCryptGetProperty` at `0x14000d684`
- `ksecdd!BCryptGetProperty` at `0x14000d6c5`
- `ksecdd!BCryptGetProperty` at `0x14000d73b`
- `ksecdd!BCryptGetProperty` at `0x14000d778`

## pseudocode

```c
NTSTATUS __fastcall StSecInitialize(__int64 a1)
{
  PFLT_FILTER v1; // rbx
  NTSTATUS result; // eax
  ULONG pcbResult; // [rsp+40h] [rbp+8h] BYREF
  int v4; // [rsp+44h] [rbp+Ch]
  ULONG v5; // [rsp+48h] [rbp+10h] BYREF

  v4 = HIDWORD(a1);
  v1 = gFilterHandle;
  pcbResult = 0;
  v5 = 0;
  if ( g_HashProvider || (result = BCryptOpenAlgorithmProvider(&g_HashProvider, L"SHA256", 0, 0), result >= 0) )
  {
    result = BCryptGetProperty(g_HashProvider, L"ObjectLength", &g_cbHashObject, 4u, &pcbResult, 0);
    if ( result >= 0 )
    {
      result = BCryptGetProperty(g_HashProvider, L"HashDigestLength", &g_cbHashValue, 4u, &pcbResult, 0);
      if ( result >= 0 )
      {
        if ( g_HmacHashProvider
          || (result = BCryptOpenAlgorithmProvider(&g_HmacHashProvider, L"SHA256", 0, 8u), result >= 0) )
        {
          result = BCryptGetProperty(g_HmacHashProvider, L"HashDigestLength", &g_cbHashOutputLength, 4u, &v5, 0);
          if ( result >= 0 )
          {
            result = BCryptGetProperty(g_HmacHashProvider, L"ObjectLength", &g_cbHashObjectLength, 4u, &v5, 0);
            if ( result >= 0 )
            {
              result = StSecpCacheInitialize(v1);
              if ( result >= 0 )
                return StSecpInitializePolicyCache();
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d604  mov     qword ptr [rsp+arg_0], rcx
0x14000d609  push    rbx
0x14000d60a  sub     rsp, 30h
0x14000d60e  cmp     cs:g_HashProvider, 0
0x14000d616  mov     rbx, cs:gFilterHandle
0x14000d61d  mov     [rsp+38h+arg_0], 0
0x14000d625  mov     [rsp+38h+arg_8], 0
0x14000d62d  jnz     short loc_14000D657
0x14000d62f  xor     r9d, r9d; dwFlags
0x14000d632  lea     rdx, aSha256; "SHA256"
0x14000d639  xor     r8d, r8d; pszImplementation
0x14000d63c  lea     rcx, g_HashProvider; phAlgorithm
0x14000d643  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000d64a  nop     dword ptr [rax+rax+00h]
0x14000d64f  test    eax, eax
0x14000d651  js      loc_14000D799
0x14000d657  mov     rcx, cs:g_HashProvider; hObject
0x14000d65e  lea     rax, [rsp+38h+arg_0]
0x14000d663  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000d66b  lea     r8, g_cbHashObject; pbOutput
0x14000d672  mov     r9d, 4; cbOutput
0x14000d678  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14000d67d  lea     rdx, aObjectlength; "ObjectLength"
0x14000d684  call    cs:__imp_BCryptGetProperty
0x14000d68b  nop     dword ptr [rax+rax+00h]
0x14000d690  test    eax, eax
0x14000d692  js      loc_14000D799
0x14000d698  mov     rcx, cs:g_HashProvider; hObject
0x14000d69f  lea     rax, [rsp+38h+arg_0]
0x14000d6a4  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000d6ac  lea     r8, g_cbHashValue; pbOutput
0x14000d6b3  mov     r9d, 4; cbOutput
0x14000d6b9  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14000d6be  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14000d6c5  call    cs:__imp_BCryptGetProperty
0x14000d6cc  nop     dword ptr [rax+rax+00h]
0x14000d6d1  test    eax, eax
0x14000d6d3  js      loc_14000D799
0x14000d6d9  cmp     cs:g_HmacHashProvider, 0
0x14000d6e1  jnz     short loc_14000D70E
0x14000d6e3  mov     r9d, 8; dwFlags
0x14000d6e9  lea     rdx, aSha256; "SHA256"
0x14000d6f0  xor     r8d, r8d; pszImplementation
0x14000d6f3  lea     rcx, g_HmacHashProvider; phAlgorithm
0x14000d6fa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000d701  nop     dword ptr [rax+rax+00h]
0x14000d706  test    eax, eax
0x14000d708  js      loc_14000D799
0x14000d70e  mov     rcx, cs:g_HmacHashProvider; hObject
0x14000d715  lea     rax, [rsp+38h+arg_8]
0x14000d71a  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000d722  lea     r8, g_cbHashOutputLength; pbOutput
0x14000d729  mov     r9d, 4; cbOutput
0x14000d72f  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14000d734  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14000d73b  call    cs:__imp_BCryptGetProperty
0x14000d742  nop     dword ptr [rax+rax+00h]
0x14000d747  test    eax, eax
0x14000d749  js      short loc_14000D799
0x14000d74b  mov     rcx, cs:g_HmacHashProvider; hObject
0x14000d752  lea     rax, [rsp+38h+arg_8]
0x14000d757  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000d75f  lea     r8, g_cbHashObjectLength; pbOutput
0x14000d766  mov     r9d, 4; cbOutput
0x14000d76c  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14000d771  lea     rdx, aObjectlength; "ObjectLength"
0x14000d778  call    cs:__imp_BCryptGetProperty
0x14000d77f  nop     dword ptr [rax+rax+00h]
0x14000d784  test    eax, eax
0x14000d786  js      short loc_14000D799
0x14000d788  mov     rcx, rbx
0x14000d78b  call    StSecpCacheInitialize
0x14000d790  test    eax, eax
0x14000d792  js      short loc_14000D799
0x14000d794  call    StSecpInitializePolicyCache
0x14000d799  add     rsp, 30h
0x14000d79d  pop     rbx
0x14000d79e  retn
```
