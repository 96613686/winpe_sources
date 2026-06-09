# IkeInitializeCapi

- ea: `0x18005593c`
- end: `0x180055c69`
- name: `IkeInitializeCapi`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180054bf4`

## callees

- `0x180008388`
- `0x180016534`
- `0x18004aa3c`
- `0x18005593c`
- `0x180055c70`

## import_xrefs

- `MSASN1!ASN1_CreateModule` at `0x180055c3a`
- `MSASN1!ASN1_CreateModule` at `0x180055c3a`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a0f`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a4b`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a70`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a95`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055abe`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055ae7`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b10`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b39`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b63`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b8d`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055bb7`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055be1`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a0f`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a4b`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a70`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055a95`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055abe`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055ae7`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b10`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b39`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b63`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055b8d`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055bb7`
- `ncrypt!BCryptOpenAlgorithmProvider` at `0x180055be1`

## string_xrefs

- `0x180055a1c`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
__int64 IkeInitializeCapi()
{
  __int64 v0; // rbx
  unsigned int v1; // eax
  __int64 v2; // rcx

  TraceLogHelper("IkeInitializeCapi", 1);
  v0 = IkeInitializeCipher(L"DES");
  if ( !v0 )
  {
    v0 = IkeInitializeCipher(L"3DES");
    if ( !v0 )
    {
      v0 = IkeInitializeCipher(L"AES");
      if ( !v0 )
      {
        v0 = IkeInitializeCipher(L"AES");
        if ( !v0 )
        {
          v1 = BCryptOpenAlgorithmProvider(&gIkeExtGlobals[64].LockSemaphore, L"DH", 0, 0);
          if ( v1 )
            goto LABEL_6;
          v1 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&gIkeExtGlobals[65].DebugInfo, L"ECDH_P256", 0, 0);
          if ( v1 )
            goto LABEL_6;
          v1 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&gIkeExtGlobals[65].LockCount, L"ECDH_P384", 0, 0);
          if ( v1 )
            goto LABEL_6;
          v1 = BCryptOpenAlgorithmProvider(
                 (BCRYPT_ALG_HANDLE *)&gIkeExtGlobals[64].SpinCount,
                 L"SP800_56A_CONCAT",
                 0,
                 0);
          if ( v1 )
            goto LABEL_6;
          v1 = BCryptOpenAlgorithmProvider(&gIkeExtGlobals[65].OwningThread, L"MD5", 0, 0);
          if ( v1
            || (v1 = BCryptOpenAlgorithmProvider(&gIkeExtGlobals[65].LockSemaphore, L"SHA1", 0, 0)) != 0
            || (v1 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&gIkeExtGlobals[65].SpinCount, L"SHA256", 0, 0)) != 0
            || (v1 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&gIkeExtGlobals[66].DebugInfo, L"SHA384", 0, 0)) != 0
            || (v1 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&gIkeExtGlobals[66].LockCount, L"MD5", 0, 8u)) != 0
            || (v1 = BCryptOpenAlgorithmProvider(&gIkeExtGlobals[66].OwningThread, L"SHA1", 0, 8u)) != 0
            || (v1 = BCryptOpenAlgorithmProvider(&gIkeExtGlobals[66].LockSemaphore, L"SHA256", 0, 8u)) != 0
            || (v1 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&gIkeExtGlobals[66].SpinCount, L"SHA384", 0, 8u)) != 0 )
          {
LABEL_6:
            v0 = WfpReportSysErrorAsNtStatus(v2, "BCryptOpenAlgorithmProvider", v1);
          }
          else
          {
            gIkeAsn1Module = ASN1_CreateModule(
                               0x10000,
                               1024,
                               4096,
                               2,
                               0,
                               off_18011A290,
                               off_18011A2A0,
                               &qword_180124AB0,
                               1768977253);
          }
        }
      }
    }
  }
  TraceLogHelper("IkeInitializeCapi", 0);
  return IkeReturnError(v0, "IkeInitializeCapi");
}

```

## disassembly

```asm
0x18005593c  push    rbx
0x18005593e  sub     rsp, 50h
0x180055942  mov     edx, 1
0x180055947  lea     rcx, aIkeinitializec; "IkeInitializeCapi"
0x18005594e  call    TraceLogHelper
0x180055953  mov     r8, cs:gIkeExtGlobals
0x18005595a  lea     rcx, aDes; "DES"
0x180055961  add     r8, 9F8h
0x180055968  xor     edx, edx
0x18005596a  call    IkeInitializeCipher
0x18005596f  mov     rbx, rax
0x180055972  test    rax, rax
0x180055975  jnz     loc_180055C47
0x18005597b  mov     r8, cs:gIkeExtGlobals
0x180055982  lea     rcx, a3des; "3DES"
0x180055989  add     r8, 0A00h
0x180055990  xor     edx, edx
0x180055992  call    IkeInitializeCipher
0x180055997  mov     rbx, rax
0x18005599a  test    rax, rax
0x18005599d  jnz     loc_180055C47
0x1800559a3  mov     r8, cs:gIkeExtGlobals
0x1800559aa  lea     rcx, aAes; "AES"
0x1800559b1  add     r8, 0A08h
0x1800559b8  xor     edx, edx
0x1800559ba  call    IkeInitializeCipher
0x1800559bf  mov     rbx, rax
0x1800559c2  test    rax, rax
0x1800559c5  jnz     loc_180055C47
0x1800559cb  mov     r8, cs:gIkeExtGlobals
0x1800559d2  lea     edx, [rax+1]
0x1800559d5  add     r8, 0A10h
0x1800559dc  lea     rcx, aAes; "AES"
0x1800559e3  call    IkeInitializeCipher
0x1800559e8  mov     rbx, rax
0x1800559eb  test    rax, rax
0x1800559ee  jnz     loc_180055C47
0x1800559f4  mov     rcx, cs:gIkeExtGlobals
0x1800559fb  lea     rdx, pszAlgId; "DH"
0x180055a02  add     rcx, 0A18h; phAlgorithm
0x180055a09  xor     r9d, r9d; dwFlags
0x180055a0c  xor     r8d, r8d; pszImplementation
0x180055a0f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055a15  test    eax, eax
0x180055a17  jz      short loc_180055A30
0x180055a19  mov     r8d, eax
0x180055a1c  lea     rdx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x180055a23  call    WfpReportSysErrorAsNtStatus
0x180055a28  mov     rbx, rax
0x180055a2b  jmp     loc_180055C47
0x180055a30  mov     rcx, cs:gIkeExtGlobals
0x180055a37  lea     rdx, aEcdhP256; "ECDH_P256"
0x180055a3e  add     rcx, 0A28h; phAlgorithm
0x180055a45  xor     r9d, r9d; dwFlags
0x180055a48  xor     r8d, r8d; pszImplementation
0x180055a4b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055a51  test    eax, eax
0x180055a53  jnz     short loc_180055A19
0x180055a55  mov     rcx, cs:gIkeExtGlobals
0x180055a5c  lea     rdx, aEcdhP384; "ECDH_P384"
0x180055a63  add     rcx, 0A30h; phAlgorithm
0x180055a6a  xor     r9d, r9d; dwFlags
0x180055a6d  xor     r8d, r8d; pszImplementation
0x180055a70  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055a76  test    eax, eax
0x180055a78  jnz     short loc_180055A19
0x180055a7a  mov     rcx, cs:gIkeExtGlobals
0x180055a81  lea     rdx, aSp80056aConcat; "SP800_56A_CONCAT"
0x180055a88  add     rcx, 0A20h; phAlgorithm
0x180055a8f  xor     r9d, r9d; dwFlags
0x180055a92  xor     r8d, r8d; pszImplementation
0x180055a95  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055a9b  test    eax, eax
0x180055a9d  jnz     loc_180055A19
0x180055aa3  mov     rcx, cs:gIkeExtGlobals
0x180055aaa  lea     rdx, aMd5; "MD5"
0x180055ab1  add     rcx, 0A38h; phAlgorithm
0x180055ab8  xor     r9d, r9d; dwFlags
0x180055abb  xor     r8d, r8d; pszImplementation
0x180055abe  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055ac4  test    eax, eax
0x180055ac6  jnz     loc_180055A19
0x180055acc  mov     rcx, cs:gIkeExtGlobals
0x180055ad3  lea     rdx, aSha1; "SHA1"
0x180055ada  add     rcx, 0A40h; phAlgorithm
0x180055ae1  xor     r9d, r9d; dwFlags
0x180055ae4  xor     r8d, r8d; pszImplementation
0x180055ae7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055aed  test    eax, eax
0x180055aef  jnz     loc_180055A19
0x180055af5  mov     rcx, cs:gIkeExtGlobals
0x180055afc  lea     rdx, aSha256_0; "SHA256"
0x180055b03  add     rcx, 0A48h; phAlgorithm
0x180055b0a  xor     r9d, r9d; dwFlags
0x180055b0d  xor     r8d, r8d; pszImplementation
0x180055b10  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055b16  test    eax, eax
0x180055b18  jnz     loc_180055A19
0x180055b1e  mov     rcx, cs:gIkeExtGlobals
0x180055b25  lea     rdx, aSha384_0; "SHA384"
0x180055b2c  add     rcx, 0A50h; phAlgorithm
0x180055b33  xor     r9d, r9d; dwFlags
0x180055b36  xor     r8d, r8d; pszImplementation
0x180055b39  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055b3f  test    eax, eax
0x180055b41  jnz     loc_180055A19
0x180055b47  mov     rcx, cs:gIkeExtGlobals
0x180055b4e  lea     r9d, [rax+8]; dwFlags
0x180055b52  add     rcx, 0A58h; phAlgorithm
0x180055b59  lea     rdx, aMd5; "MD5"
0x180055b60  xor     r8d, r8d; pszImplementation
0x180055b63  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055b69  test    eax, eax
0x180055b6b  jnz     loc_180055A19
0x180055b71  mov     rcx, cs:gIkeExtGlobals
0x180055b78  lea     r9d, [rax+8]; dwFlags
0x180055b7c  add     rcx, 0A60h; phAlgorithm
0x180055b83  lea     rdx, aSha1; "SHA1"
0x180055b8a  xor     r8d, r8d; pszImplementation
0x180055b8d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055b93  test    eax, eax
0x180055b95  jnz     loc_180055A19
0x180055b9b  mov     rcx, cs:gIkeExtGlobals
0x180055ba2  lea     r9d, [rax+8]; dwFlags
0x180055ba6  add     rcx, 0A68h; phAlgorithm
0x180055bad  lea     rdx, aSha256_0; "SHA256"
0x180055bb4  xor     r8d, r8d; pszImplementation
0x180055bb7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055bbd  test    eax, eax
0x180055bbf  jnz     loc_180055A19
0x180055bc5  mov     rcx, cs:gIkeExtGlobals
0x180055bcc  lea     r9d, [rax+8]; dwFlags
0x180055bd0  add     rcx, 0A70h; phAlgorithm
0x180055bd7  lea     rdx, aSha384_0; "SHA384"
0x180055bde  xor     r8d, r8d; pszImplementation
0x180055be1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180055be7  test    eax, eax
0x180055be9  jnz     loc_180055A19
0x180055bef  mov     [rsp+58h+var_18], 69707365h
0x180055bf7  lea     rax, qword_180124AB0
0x180055bfe  mov     [rsp+58h+var_20], rax
0x180055c03  mov     edx, 400h
0x180055c08  lea     rax, off_18011A2A0
0x180055c0f  mov     ecx, 10000h
0x180055c14  mov     [rsp+58h+var_28], rax
0x180055c19  mov     r9d, 2
0x180055c1f  lea     rax, off_18011A290
0x180055c26  mov     r8d, 1000h
0x180055c2c  mov     [rsp+58h+var_30], rax
0x180055c31  mov     [rsp+58h+var_38], 0
0x180055c3a  call    cs:__imp_ASN1_CreateModule
0x180055c40  mov     cs:gIkeAsn1Module, rax
0x180055c47  xor     edx, edx
0x180055c49  lea     rcx, aIkeinitializec; "IkeInitializeCapi"
0x180055c50  call    TraceLogHelper
0x180055c55  lea     rdx, aIkeinitializec; "IkeInitializeCapi"
0x180055c5c  mov     rcx, rbx
0x180055c5f  add     rsp, 50h
0x180055c63  pop     rbx
0x180055c64  jmp     IkeReturnError
```
