# LoadCNG

- ea: `0x14002c95c`
- end: `0x14002cc66`
- name: `LoadCNG`
- size: `778`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002c848`
- `0x14002c930`

## callees

- `0x14002c95c`
- `0x14002cc6c`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x14002c997`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002ca44`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002caec`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002cb22`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002cb94`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002c997`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002ca44`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002caec`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002cb22`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002cb94`
- `cng!BCryptSetProperty` at `0x14002c9ca`
- `cng!BCryptSetProperty` at `0x14002ca79`
- `cng!BCryptSetProperty` at `0x14002c9ca`
- `cng!BCryptSetProperty` at `0x14002ca79`
- `cng!BCryptGetProperty` at `0x14002ca0a`
- `cng!BCryptGetProperty` at `0x14002cab9`
- `cng!BCryptGetProperty` at `0x14002cb62`
- `cng!BCryptGetProperty` at `0x14002cbd0`
- `cng!BCryptGetProperty` at `0x14002ca0a`
- `cng!BCryptGetProperty` at `0x14002cab9`
- `cng!BCryptGetProperty` at `0x14002cb62`
- `cng!BCryptGetProperty` at `0x14002cbd0`

## pseudocode

```c
__int64 LoadCNG()
{
  NTSTATUS Property; // ebx
  ULONG v1; // eax
  ULONG pcbResult; // [rsp+40h] [rbp+8h] BYREF

  Property = 0;
  pcbResult = 0;
  if ( !cshAesPagedAlgHandle )
  {
    Property = BCryptOpenAlgorithmProvider(&cshAesPagedAlgHandle, L"AES", 0, 0);
    if ( Property < 0 )
      goto LABEL_17;
    Property = BCryptSetProperty(cshAesPagedAlgHandle, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
    if ( Property < 0 )
      goto LABEL_17;
    pcbResult = 4;
    Property = BCryptGetProperty(cshAesPagedAlgHandle, L"ObjectLength", &cshAesPagedKeyObjectSize, 4u, &pcbResult, 0);
    if ( Property < 0 )
      goto LABEL_17;
  }
  if ( !cshAesNonPagedAlgHandle )
  {
    Property = BCryptOpenAlgorithmProvider(&cshAesNonPagedAlgHandle, L"AES", 0, 1u);
    if ( Property < 0 )
      goto LABEL_17;
    Property = BCryptSetProperty(cshAesNonPagedAlgHandle, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
    if ( Property < 0 )
      goto LABEL_17;
    pcbResult = 4;
    Property = BCryptGetProperty(
                 cshAesNonPagedAlgHandle,
                 L"ObjectLength",
                 &cshAesNonPagedKeyObjectSize,
                 4u,
                 &pcbResult,
                 0);
    if ( Property < 0 )
      goto LABEL_17;
  }
  if ( !cshRngAlgHandle && (Property = BCryptOpenAlgorithmProvider(&cshRngAlgHandle, L"RNG", 0, 0), Property < 0)
    || !cshHmacShaPagedAlgHandle
    && ((Property = BCryptOpenAlgorithmProvider(&cshHmacShaPagedAlgHandle, L"SHA1", 0, 8u), Property < 0)
     || (pcbResult = 4,
         Property = BCryptGetProperty(
                      cshHmacShaPagedAlgHandle,
                      L"ObjectLength",
                      &cshHmacPagedShaObjectSize,
                      4u,
                      &pcbResult,
                      0),
         Property < 0))
    || !cshHmacShaNonPagedAlgHandle
    && ((Property = BCryptOpenAlgorithmProvider(&cshHmacShaNonPagedAlgHandle, L"SHA1", 0, 9u), Property < 0)
     || (pcbResult = 4,
         Property = BCryptGetProperty(
                      cshHmacShaNonPagedAlgHandle,
                      L"ObjectLength",
                      &cshHmacNonPagedShaObjectSize,
                      4u,
                      &pcbResult,
                      0),
         Property < 0)) )
  {
LABEL_17:
    UnloadCNG();
  }
  if ( csCNGPageable )
  {
    cshAesAlgHandle = cshAesPagedAlgHandle;
    cshAesKeyObjectSize = *(_DWORD *)&cshAesPagedKeyObjectSize;
    cshHmacShaAlgHandle = cshHmacShaPagedAlgHandle;
    v1 = *(_DWORD *)&cshHmacPagedShaObjectSize;
  }
  else
  {
    cshAesAlgHandle = cshAesNonPagedAlgHandle;
    cshAesKeyObjectSize = *(_DWORD *)&cshAesNonPagedKeyObjectSize;
    cshHmacShaAlgHandle = cshHmacShaNonPagedAlgHandle;
    v1 = *(_DWORD *)&cshHmacNonPagedShaObjectSize;
  }
  cshHmacShaObjectSize = v1;
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14002c95c  mov     [rsp+arg_8], rbx
0x14002c961  mov     [rsp+arg_10], rsi
0x14002c966  push    rdi
0x14002c967  sub     rsp, 30h
0x14002c96b  xor     edi, edi
0x14002c96d  cmp     cs:cshAesPagedAlgHandle, rdi
0x14002c974  mov     ebx, edi
0x14002c976  mov     [rsp+38h+pcbResult], edi
0x14002c97a  lea     esi, [rdi+4]
0x14002c97d  jnz     loc_14002CA20
0x14002c983  xor     r9d, r9d; dwFlags
0x14002c986  lea     rdx, Str2; "AES"
0x14002c98d  xor     r8d, r8d; pszImplementation
0x14002c990  lea     rcx, cshAesPagedAlgHandle; phAlgorithm
0x14002c997  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002c99e  nop     dword ptr [rax+rax+00h]
0x14002c9a3  mov     ebx, eax
0x14002c9a5  test    eax, eax
0x14002c9a7  js      loc_14002CBE2
0x14002c9ad  mov     rcx, cs:cshAesPagedAlgHandle; hObject
0x14002c9b4  lea     r9d, [rdi+20h]; cbInput
0x14002c9b8  lea     r8, aChainingmodecb; "ChainingModeCBC"
0x14002c9bf  mov     [rsp+38h+dwFlags], edi; dwFlags
0x14002c9c3  lea     rdx, aChainingmode; "ChainingMode"
0x14002c9ca  call    cs:__imp_BCryptSetProperty
0x14002c9d1  nop     dword ptr [rax+rax+00h]
0x14002c9d6  mov     ebx, eax
0x14002c9d8  test    eax, eax
0x14002c9da  js      loc_14002CBE2
0x14002c9e0  mov     rcx, cs:cshAesPagedAlgHandle; hObject
0x14002c9e7  lea     rax, [rsp+38h+pcbResult]
0x14002c9ec  mov     [rsp+38h+var_10], edi; dwFlags
0x14002c9f0  lea     r8, cshAesPagedKeyObjectSize; pbOutput
0x14002c9f7  mov     r9d, esi; cbOutput
0x14002c9fa  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x14002c9ff  lea     rdx, aObjectlength; "ObjectLength"
0x14002ca06  mov     [rsp+38h+pcbResult], esi
0x14002ca0a  call    cs:__imp_BCryptGetProperty
0x14002ca11  nop     dword ptr [rax+rax+00h]
0x14002ca16  mov     ebx, eax
0x14002ca18  test    eax, eax
0x14002ca1a  js      loc_14002CBE2
0x14002ca20  cmp     cs:cshAesNonPagedAlgHandle, rdi
0x14002ca27  jnz     loc_14002CACF
0x14002ca2d  mov     r9d, 1; dwFlags
0x14002ca33  lea     rdx, Str2; "AES"
0x14002ca3a  xor     r8d, r8d; pszImplementation
0x14002ca3d  lea     rcx, cshAesNonPagedAlgHandle; phAlgorithm
0x14002ca44  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002ca4b  nop     dword ptr [rax+rax+00h]
0x14002ca50  mov     ebx, eax
0x14002ca52  test    eax, eax
0x14002ca54  js      loc_14002CBE2
0x14002ca5a  mov     rcx, cs:cshAesNonPagedAlgHandle; hObject
0x14002ca61  lea     r8, aChainingmodecb; "ChainingModeCBC"
0x14002ca68  mov     r9d, 20h ; ' '; cbInput
0x14002ca6e  mov     [rsp+38h+dwFlags], edi; dwFlags
0x14002ca72  lea     rdx, aChainingmode; "ChainingMode"
0x14002ca79  call    cs:__imp_BCryptSetProperty
0x14002ca80  nop     dword ptr [rax+rax+00h]
0x14002ca85  mov     ebx, eax
0x14002ca87  test    eax, eax
0x14002ca89  js      loc_14002CBE2
0x14002ca8f  mov     rcx, cs:cshAesNonPagedAlgHandle; hObject
0x14002ca96  lea     rax, [rsp+38h+pcbResult]
0x14002ca9b  mov     [rsp+38h+var_10], edi; dwFlags
0x14002ca9f  lea     r8, cshAesNonPagedKeyObjectSize; pbOutput
0x14002caa6  mov     r9d, esi; cbOutput
0x14002caa9  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x14002caae  lea     rdx, aObjectlength; "ObjectLength"
0x14002cab5  mov     [rsp+38h+pcbResult], esi
0x14002cab9  call    cs:__imp_BCryptGetProperty
0x14002cac0  nop     dword ptr [rax+rax+00h]
0x14002cac5  mov     ebx, eax
0x14002cac7  test    eax, eax
0x14002cac9  js      loc_14002CBE2
0x14002cacf  cmp     cs:cshRngAlgHandle, rdi
0x14002cad6  jnz     short loc_14002CB02
0x14002cad8  xor     r9d, r9d; dwFlags
0x14002cadb  lea     rdx, aRng; "RNG"
0x14002cae2  xor     r8d, r8d; pszImplementation
0x14002cae5  lea     rcx, cshRngAlgHandle; phAlgorithm
0x14002caec  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002caf3  nop     dword ptr [rax+rax+00h]
0x14002caf8  mov     ebx, eax
0x14002cafa  test    eax, eax
0x14002cafc  js      loc_14002CBE2
0x14002cb02  cmp     cs:cshHmacShaPagedAlgHandle, rdi
0x14002cb09  jnz     short loc_14002CB74
0x14002cb0b  mov     r9d, 8; dwFlags
0x14002cb11  lea     rdx, aSha1; "SHA1"
0x14002cb18  xor     r8d, r8d; pszImplementation
0x14002cb1b  lea     rcx, cshHmacShaPagedAlgHandle; phAlgorithm
0x14002cb22  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002cb29  nop     dword ptr [rax+rax+00h]
0x14002cb2e  mov     ebx, eax
0x14002cb30  test    eax, eax
0x14002cb32  js      loc_14002CBE2
0x14002cb38  mov     rcx, cs:cshHmacShaPagedAlgHandle; hObject
0x14002cb3f  lea     rax, [rsp+38h+pcbResult]
0x14002cb44  mov     [rsp+38h+var_10], edi; dwFlags
0x14002cb48  lea     r8, cshHmacPagedShaObjectSize; pbOutput
0x14002cb4f  mov     r9d, esi; cbOutput
0x14002cb52  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x14002cb57  lea     rdx, aObjectlength; "ObjectLength"
0x14002cb5e  mov     [rsp+38h+pcbResult], esi
0x14002cb62  call    cs:__imp_BCryptGetProperty
0x14002cb69  nop     dword ptr [rax+rax+00h]
0x14002cb6e  mov     ebx, eax
0x14002cb70  test    eax, eax
0x14002cb72  js      short loc_14002CBE2
0x14002cb74  cmp     cs:cshHmacShaNonPagedAlgHandle, rdi
0x14002cb7b  jnz     short loc_14002CBE7
0x14002cb7d  mov     r9d, 9; dwFlags
0x14002cb83  lea     rdx, aSha1; "SHA1"
0x14002cb8a  xor     r8d, r8d; pszImplementation
0x14002cb8d  lea     rcx, cshHmacShaNonPagedAlgHandle; phAlgorithm
0x14002cb94  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002cb9b  nop     dword ptr [rax+rax+00h]
0x14002cba0  mov     ebx, eax
0x14002cba2  test    eax, eax
0x14002cba4  js      short loc_14002CBE2
0x14002cba6  mov     rcx, cs:cshHmacShaNonPagedAlgHandle; hObject
0x14002cbad  lea     rax, [rsp+38h+pcbResult]
0x14002cbb2  mov     [rsp+38h+var_10], edi; dwFlags
0x14002cbb6  lea     r8, cshHmacNonPagedShaObjectSize; pbOutput
0x14002cbbd  mov     r9d, esi; cbOutput
0x14002cbc0  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x14002cbc5  lea     rdx, aObjectlength; "ObjectLength"
0x14002cbcc  mov     [rsp+38h+pcbResult], esi
0x14002cbd0  call    cs:__imp_BCryptGetProperty
0x14002cbd7  nop     dword ptr [rax+rax+00h]
0x14002cbdc  mov     ebx, eax
0x14002cbde  test    eax, eax
0x14002cbe0  jns     short loc_14002CBE7
0x14002cbe2  call    UnloadCNG
0x14002cbe7  cmp     cs:csCNGPageable, edi
0x14002cbed  jz      short loc_14002CC1F
0x14002cbef  mov     rax, cs:cshAesPagedAlgHandle
0x14002cbf6  mov     cs:cshAesAlgHandle, rax
0x14002cbfd  mov     eax, cs:cshAesPagedKeyObjectSize
0x14002cc03  mov     cs:cshAesKeyObjectSize, eax
0x14002cc09  mov     rax, cs:cshHmacShaPagedAlgHandle
0x14002cc10  mov     cs:cshHmacShaAlgHandle, rax
0x14002cc17  mov     eax, cs:cshHmacPagedShaObjectSize
0x14002cc1d  jmp     short loc_14002CC4D
0x14002cc1f  mov     rax, cs:cshAesNonPagedAlgHandle
0x14002cc26  mov     cs:cshAesAlgHandle, rax
0x14002cc2d  mov     eax, cs:cshAesNonPagedKeyObjectSize
0x14002cc33  mov     cs:cshAesKeyObjectSize, eax
0x14002cc39  mov     rax, cs:cshHmacShaNonPagedAlgHandle
0x14002cc40  mov     cs:cshHmacShaAlgHandle, rax
0x14002cc47  mov     eax, cs:cshHmacNonPagedShaObjectSize
0x14002cc4d  mov     rsi, [rsp+38h+arg_10]
0x14002cc52  mov     cs:cshHmacShaObjectSize, eax
0x14002cc58  mov     eax, ebx
0x14002cc5a  mov     rbx, [rsp+38h+arg_8]
0x14002cc5f  add     rsp, 30h
0x14002cc63  pop     rdi
0x14002cc64  retn
```
