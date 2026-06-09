# CertInUseGetPubKeyInfo

- ea: `0x18001bbe8`
- end: `0x18001bec5`
- name: `CertInUseGetPubKeyInfo`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800173c0`

## callees

- `0x180009cd0`
- `0x18000a650`
- `0x18000a770`
- `0x180012e00`
- `0x180014d6c`
- `0x18001993c`
- `0x18001a06c`
- `0x18001bbe8`
- `0x18001f15d`
- `0x18001f18d`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001be45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001be45`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x18001bd5a`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x18001bd5a`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x18001bd2f`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x18001bd2f`

## string_xrefs

- `0x18001be7d`: `Provider name can not be accessed`

## pseudocode

```c
__int64 __fastcall CertInUseGetPubKeyInfo(NCRYPT_HANDLE *a1, __int64 a2, _DWORD *a3, wchar_t *a4, _DWORD *a5)
{
  NCRYPT_HANDLE v5; // r14
  NCRYPT_HANDLE v6; // rcx
  __int64 pbOutput; // rdi
  wchar_t *v11; // rsi
  __int64 v12; // rbx
  unsigned int KeyAlgoGroupProp; // ebx
  __int64 ModuleHandle; // rax
  __int64 v15; // rdx
  unsigned int v16; // ebx
  int v17; // r14d
  _BYTE *v18; // rax
  wchar_t *String1; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbResult; // [rsp+90h] [rbp+40h] BYREF
  DWORD v22; // [rsp+A8h] [rbp+58h] BYREF

  v5 = *a1;
  v6 = *a1;
  pcbResult = 0;
  v22 = 0;
  String1 = 0;
  pbOutput = 0;
  v11 = 0;
  v12 = ValidateClientKeyHandle(v6);
  if ( !v12 )
  {
    KeyAlgoGroupProp = -2146892963;
    goto LABEL_20;
  }
  *a4 = (unsigned int)Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH__private_IsEnabledDeviceUsageNoInline() != 0 ? 36 : 43;
  StringCchCopyW(a4 + 1, 0x3Fu, *(STRSAFE_LPCWSTR *)(*(_QWORD *)(v12 + 8) + 280LL));
  *a5 = 0;
  v11 = String1;
  KeyAlgoGroupProp = GetKeyAlgoGroupProp(v5);
  if ( !KeyAlgoGroupProp )
  {
    if ( !wcscmp_0(String1, L"RSA") )
    {
      KeyAlgoGroupProp = NCryptExportKey(v5, 0, L"RSAPUBLICBLOB", 0, 0, 0, &pcbResult, 0);
      if ( KeyAlgoGroupProp )
        goto LABEL_20;
      pbOutput = SafeAllocaAllocateFromHeap(pcbResult);
      if ( !pbOutput )
        goto LABEL_7;
      KeyAlgoGroupProp = NCryptExportKey(v5, 0, L"RSAPUBLICBLOB", 0, (PBYTE)pbOutput, pcbResult, &v22, 0);
      if ( !KeyAlgoGroupProp )
      {
        ModuleHandle = RtlAsn1GetModuleHandle(L"{34e4912d-f770-4f49-b020-96dd74c99d01}");
        KeyAlgoGroupProp = 0;
        String1 = 0;
        if ( (int)RtlAsn1EncodeAndAllocate(ModuleHandle, 72, 0, 0, a2, &String1, pbOutput) >= 0 )
        {
          *a3 = (_DWORD)String1;
          goto LABEL_20;
        }
LABEL_7:
        KeyAlgoGroupProp = -2146893810;
      }
    }
    else if ( !wcscmp_0(String1, L"ECDSA") || !wcscmp_0(String1, L"ECDH") )
    {
      KeyAlgoGroupProp = NCryptExportKey(v5, 0, L"ECCPUBLICBLOB", 0, 0, 0, &pcbResult, 0);
      if ( !KeyAlgoGroupProp )
      {
        pbOutput = SafeAllocaAllocateFromHeap(pcbResult);
        if ( !pbOutput )
          goto LABEL_7;
        KeyAlgoGroupProp = NCryptExportKey(v5, 0, L"ECCPUBLICBLOB", 0, (PBYTE)pbOutput, pcbResult, &v22, 0);
        if ( !KeyAlgoGroupProp )
        {
          v15 = (unsigned int)(2 * *(_DWORD *)(pbOutput + 4));
          v16 = 2 * *(_DWORD *)(pbOutput + 4);
          if ( v22 < (unsigned __int64)(v15 + 8) )
            goto LABEL_7;
          v17 = v15 + 1;
          v18 = LocalAlloc(0x40u, (unsigned int)(v15 + 1));
          *(_QWORD *)a2 = v18;
          if ( !v18 )
            goto LABEL_7;
          *v18 = 4;
          memcpy_0((void *)(*(_QWORD *)a2 + 1LL), (const void *)(pbOutput + 8), v16);
          KeyAlgoGroupProp = 0;
          *a3 = v17;
        }
      }
    }
    else
    {
      KeyAlgoGroupProp = -2146893054;
    }
  }
LABEL_20:
  if ( !*a4 )
    StringCchCopyW(a4, 0x40u, L"Provider name can not be accessed");
  if ( pbOutput )
    MSCryptFree(pbOutput);
  if ( v11 )
    MSCryptFree(v11);
  return KeyAlgoGroupProp;
}

```

## disassembly

```asm
0x18001bbe8  mov     [rsp-38h+arg_8], rbx
0x18001bbed  push    rbp
0x18001bbee  push    rsi
0x18001bbef  push    rdi
0x18001bbf0  push    r12
0x18001bbf2  push    r13
0x18001bbf4  push    r14
0x18001bbf6  push    r15
0x18001bbf8  mov     rbp, rsp
0x18001bbfb  sub     rsp, 50h
0x18001bbff  mov     r14, [rcx]
0x18001bc02  xor     eax, eax
0x18001bc04  mov     rcx, r14
0x18001bc07  mov     [rbp+arg_0], eax
0x18001bc0a  mov     r15, r9
0x18001bc0d  mov     [rbp+arg_18], eax
0x18001bc10  mov     r13, r8
0x18001bc13  mov     [rbp+String1], rax
0x18001bc17  mov     r12, rdx
0x18001bc1a  mov     edi, eax
0x18001bc1c  mov     esi, eax
0x18001bc1e  call    ValidateClientKeyHandle
0x18001bc23  mov     rbx, rax
0x18001bc26  test    rax, rax
0x18001bc29  jnz     short loc_18001BC35
0x18001bc2b  mov     ebx, 8009035Dh
0x18001bc30  jmp     loc_18001BE74
0x18001bc35  call    Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH__private_IsEnabledDeviceUsageNoInline
0x18001bc3a  neg     eax
0x18001bc3c  mov     edx, 3Fh ; '?'; cchDest
0x18001bc41  sbb     cx, cx
0x18001bc44  and     cx, 0FFF9h
0x18001bc49  add     cx, 2Bh ; '+'
0x18001bc4d  mov     [r15], cx
0x18001bc51  lea     rcx, [r15+2]; pszDest
0x18001bc55  mov     r8, [rbx+8]
0x18001bc59  mov     r8, [r8+118h]; pszSrc
0x18001bc60  call    StringCchCopyW
0x18001bc65  mov     r11, [rbp+arg_20]
0x18001bc69  lea     rdx, [rbp+String1]
0x18001bc6d  mov     rcx, r14; hObject
0x18001bc70  mov     [r11], esi
0x18001bc73  call    GetKeyAlgoGroupProp
0x18001bc78  mov     rsi, [rbp+String1]
0x18001bc7c  mov     ebx, eax
0x18001bc7e  test    eax, eax
0x18001bc80  jnz     loc_18001BE74
0x18001bc86  lea     rdx, aRsa; "RSA"
0x18001bc8d  mov     rcx, rsi; String1
0x18001bc90  call    wcscmp_0
0x18001bc95  xor     ebx, ebx
0x18001bc97  test    eax, eax
0x18001bc99  jnz     loc_18001BD74
0x18001bc9f  mov     [rsp+50h+dwFlags], ebx; dwFlags
0x18001bca3  lea     rax, [rbp+arg_0]
0x18001bca7  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18001bcac  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x18001bcb3  mov     [rsp+50h+cbOutput], ebx; cbOutput
0x18001bcb7  xor     r9d, r9d; pParameterList
0x18001bcba  xor     edx, edx; hExportKey
0x18001bcbc  mov     [rsp+50h+pbOutput], rbx; pbOutput
0x18001bcc1  mov     rcx, r14; hKey
0x18001bcc4  call    NCryptExportKey
0x18001bcc9  mov     ebx, eax
0x18001bccb  test    eax, eax
0x18001bccd  jnz     loc_18001BE74
0x18001bcd3  mov     ecx, [rbp+arg_0]
0x18001bcd6  call    SafeAllocaAllocateFromHeap
0x18001bcdb  mov     rdi, rax
0x18001bcde  test    rax, rax
0x18001bce1  jnz     short loc_18001BCED
0x18001bce3  mov     ebx, 8009000Eh
0x18001bce8  jmp     loc_18001BE74
0x18001bced  lea     rax, [rbp+arg_18]
0x18001bcf1  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18001bcf9  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18001bcfe  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x18001bd05  mov     eax, [rbp+arg_0]
0x18001bd08  xor     r9d, r9d; pParameterList
0x18001bd0b  mov     [rsp+50h+cbOutput], eax; cbOutput
0x18001bd0f  xor     edx, edx; hExportKey
0x18001bd11  mov     rcx, r14; hKey
0x18001bd14  mov     [rsp+50h+pbOutput], rdi; pbOutput
0x18001bd19  call    NCryptExportKey
0x18001bd1e  mov     ebx, eax
0x18001bd20  test    eax, eax
0x18001bd22  jnz     loc_18001BE74
0x18001bd28  lea     rcx, a34e4912dF7704f; "{34e4912d-f770-4f49-b020-96dd74c99d01}"
0x18001bd2f  call    cs:__imp_RtlAsn1GetModuleHandle
0x18001bd35  xor     ebx, ebx
0x18001bd37  mov     [rsp+50h+pcbResult], rdi
0x18001bd3c  lea     rcx, [rbp+String1]
0x18001bd40  mov     [rbp+String1], rbx
0x18001bd44  mov     qword ptr [rsp+50h+cbOutput], rcx
0x18001bd49  xor     r9d, r9d
0x18001bd4c  xor     r8d, r8d
0x18001bd4f  mov     [rsp+50h+pbOutput], r12
0x18001bd54  lea     edx, [rbx+48h]
0x18001bd57  mov     rcx, rax
0x18001bd5a  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x18001bd60  test    eax, eax
0x18001bd62  js      loc_18001BCE3
0x18001bd68  mov     eax, dword ptr [rbp+String1]
0x18001bd6b  mov     [r13+0], eax
0x18001bd6f  jmp     loc_18001BE74
0x18001bd74  lea     rdx, aEcdsa; "ECDSA"
0x18001bd7b  mov     rcx, rsi; String1
0x18001bd7e  call    wcscmp_0
0x18001bd83  test    eax, eax
0x18001bd85  jz      short loc_18001BDA4
0x18001bd87  lea     rdx, aEcdh; "ECDH"
0x18001bd8e  mov     rcx, rsi; String1
0x18001bd91  call    wcscmp_0
0x18001bd96  test    eax, eax
0x18001bd98  jz      short loc_18001BDA4
0x18001bd9a  mov     ebx, 80090302h
0x18001bd9f  jmp     loc_18001BE74
0x18001bda4  mov     [rsp+50h+dwFlags], ebx; dwFlags
0x18001bda8  lea     rax, [rbp+arg_0]
0x18001bdac  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18001bdb1  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x18001bdb8  mov     [rsp+50h+cbOutput], ebx; cbOutput
0x18001bdbc  xor     r9d, r9d; pParameterList
0x18001bdbf  xor     edx, edx; hExportKey
0x18001bdc1  mov     [rsp+50h+pbOutput], rbx; pbOutput
0x18001bdc6  mov     rcx, r14; hKey
0x18001bdc9  call    NCryptExportKey
0x18001bdce  mov     ebx, eax
0x18001bdd0  test    eax, eax
0x18001bdd2  jnz     loc_18001BE74
0x18001bdd8  mov     ecx, [rbp+arg_0]
0x18001bddb  call    SafeAllocaAllocateFromHeap
0x18001bde0  xor     ebx, ebx
0x18001bde2  mov     rdi, rax
0x18001bde5  test    rax, rax
0x18001bde8  jz      loc_18001BCE3
0x18001bdee  lea     rax, [rbp+arg_18]
0x18001bdf2  mov     [rsp+50h+dwFlags], ebx; dwFlags
0x18001bdf6  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18001bdfb  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x18001be02  mov     eax, [rbp+arg_0]
0x18001be05  xor     r9d, r9d; pParameterList
0x18001be08  mov     [rsp+50h+cbOutput], eax; cbOutput
0x18001be0c  xor     edx, edx; hExportKey
0x18001be0e  mov     rcx, r14; hKey
0x18001be11  mov     [rsp+50h+pbOutput], rdi; pbOutput
0x18001be16  call    NCryptExportKey
0x18001be1b  mov     ebx, eax
0x18001be1d  test    eax, eax
0x18001be1f  jnz     short loc_18001BE74
0x18001be21  mov     eax, [rdi+4]
0x18001be24  lea     edx, [rax+rax]
0x18001be27  mov     eax, [rbp+arg_18]
0x18001be2a  lea     rcx, [rdx+8]
0x18001be2e  mov     ebx, edx
0x18001be30  cmp     rax, rcx
0x18001be33  jb      loc_18001BCE3
0x18001be39  lea     r14d, [rdx+1]
0x18001be3d  mov     ecx, 40h ; '@'; uFlags
0x18001be42  mov     edx, r14d; uBytes
0x18001be45  call    cs:__imp_LocalAlloc
0x18001be4b  mov     [r12], rax
0x18001be4f  test    rax, rax
0x18001be52  jz      loc_18001BCE3
0x18001be58  mov     byte ptr [rax], 4
0x18001be5b  lea     rdx, [rdi+8]; Src
0x18001be5f  mov     rcx, [r12]
0x18001be63  mov     r8d, ebx; Size
0x18001be66  inc     rcx; void *
0x18001be69  call    memcpy_0
0x18001be6e  xor     ebx, ebx
0x18001be70  mov     [r13+0], r14d
0x18001be74  xor     r12d, r12d
0x18001be77  cmp     [r15], r12w
0x18001be7b  jnz     short loc_18001BE91
0x18001be7d  lea     r8, aProviderNameCa; "Provider name can not be accessed"
0x18001be84  mov     rcx, r15; pszDest
0x18001be87  lea     edx, [r12+40h]; cchDest
0x18001be8c  call    StringCchCopyW
0x18001be91  test    rdi, rdi
0x18001be94  jz      short loc_18001BE9E
0x18001be96  mov     rcx, rdi
0x18001be99  call    MSCryptFree
0x18001be9e  test    rsi, rsi
0x18001bea1  jz      short loc_18001BEAB
0x18001bea3  mov     rcx, rsi
0x18001bea6  call    MSCryptFree
0x18001beab  mov     eax, ebx
0x18001bead  mov     rbx, [rsp+50h+arg_8]
0x18001beb5  add     rsp, 50h
0x18001beb9  pop     r15
0x18001bebb  pop     r14
0x18001bebd  pop     r13
0x18001bebf  pop     r12
0x18001bec1  pop     rdi
0x18001bec2  pop     rsi
0x18001bec3  pop     rbp
0x18001bec4  retn
```
