# CryptXMLSignInternal

- ea: `0x180043c14`
- end: `0x180043f5c`
- name: `CryptXMLSignInternal`
- size: `840`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043ad8`

## callees

- `0x180014148`
- `0x1800206a8`
- `0x18002ec8c`
- `0x180043c14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043f08`
- `CRYPT32!CryptFindOIDInfo` at `0x180043ca2`
- `CRYPT32!CryptFindOIDInfo` at `0x180043ca2`
- `CRYPTXML!CryptXmlEncode` at `0x180043e85`
- `CRYPTXML!CryptXmlEncode` at `0x180043e85`
- `CRYPTXML!CryptXmlClose` at `0x180043f38`
- `CRYPTXML!CryptXmlClose` at `0x180043f38`
- `CRYPTXML!CryptXmlSign` at `0x180043e38`
- `CRYPTXML!CryptXmlSign` at `0x180043e38`
- `CRYPTXML!CryptXmlCreateReference` at `0x180043df1`
- `CRYPTXML!CryptXmlCreateReference` at `0x180043df1`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x180043d97`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x180043d97`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x180043c74`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x180043cd6`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x180043c74`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x180043cd6`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x180043eb9`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x180043efe`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x180043eb9`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x180043efe`

## string_xrefs

- `0x180043d25`: `/Envelope/Header/Security`
- `0x180043d0b`: `http://www.w3.org/2000/09/xmldsig#enveloped-signature`
- `0x180043cf4`: `http://www.w3.org/2001/10/xml-exc-c14n#`

## pseudocode

```c
__int64 __fastcall CryptXMLSignInternal(
        __int64 a1,
        int a2,
        __int64 a3,
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE a4,
        DWORD dwKeySpec,
        HCRYPTXML phReference,
        __int64 a7,
        unsigned __int16 **a8)
{
  WCHAR *wszAlgorithmURI; // r15
  const WCHAR *OIDInfo; // rax
  const CRYPT_XML_BLOB *pEncoded; // rcx
  int v15; // ebx
  int v16; // eax
  int v17; // edi
  unsigned __int16 *v18; // rax
  signed int LastError; // eax
  __int128 pvCallbackState; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  _QWORD pvFindBy[2]; // [rsp+70h] [rbp-90h] BYREF
  CRYPT_XML_PROPERTY rgProperty; // [rsp+80h] [rbp-80h] BYREF
  CRYPT_XML_PROPERTY v26; // [rsp+98h] [rbp-68h] BYREF
  CRYPT_XML_ALGORITHM rgTransform; // [rsp+B0h] [rbp-50h] BYREF
  CRYPT_XML_ALGORITHM pDigestMethod; // [rsp+D0h] [rbp-30h] BYREF
  CRYPT_XML_ALGORITHM pCanonicalization; // [rsp+F0h] [rbp-10h] BYREF
  CRYPT_XML_ALGORITHM pSignatureMethod; // [rsp+110h] [rbp+10h] BYREF
  _BYTE pvKeyInfoSpec[80]; // [rsp+130h] [rbp+30h] BYREF
  HCRYPTXML hCryptXml; // [rsp+1B0h] [rbp+B0h] BYREF
  const wchar_t *v33; // [rsp+1C0h] [rbp+C0h] BYREF

  hCryptXml = 0;
  pvCallbackState = 0;
  memset_0(pvKeyInfoSpec, 0, 0x48u);
  wszAlgorithmURI = CryptXmlFindAlgorithmInfo(3u, L"SHA256", 1u, 0)->wszAlgorithmURI;
  OIDInfo = (const WCHAR *)CryptFindOIDInfo(
                             1u,
                             *(void **)(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(**(_QWORD **)(a3 + 16) + 16LL) + 8LL)
                                                  + 24LL)
                                      + 96LL),
                             3u);
  if ( OIDInfo )
  {
    pvFindBy[0] = L"SHA256";
    pvFindBy[1] = *((_QWORD *)OIDInfo + 6);
    OIDInfo = CryptXmlFindAlgorithmInfo(4u, pvFindBy, 2u, 0)->wszAlgorithmURI;
  }
  pSignatureMethod.wszAlgorithm = OIDInfo;
  pEncoded = (const CRYPT_XML_BLOB *)v22;
  *(_QWORD *)&pSignatureMethod.cbSize = 32;
  *(_QWORD *)&pCanonicalization.cbSize = 32;
  pCanonicalization.wszAlgorithm = L"http://www.w3.org/2001/10/xml-exc-c14n#";
  *(_QWORD *)&pDigestMethod.cbSize = 32;
  rgTransform.wszAlgorithm = L"http://www.w3.org/2000/09/xmldsig#enveloped-signature";
  pDigestMethod.wszAlgorithm = wszAlgorithmURI;
  v33 = L"/Envelope/Header/Security";
  rgProperty.pvValue = &v33;
  *(_QWORD *)&rgTransform.cbSize = 32;
  pSignatureMethod.Encoded = 0;
  if ( !a2 )
    pEncoded = 0;
  rgProperty.dwPropId = CRYPT_XML_PROPERTY_SIGNATURE_LOCATION;
  rgProperty.cbValue = 8;
  pCanonicalization.Encoded = 0;
  v22[0] = 2;
  pDigestMethod.Encoded = 0;
  v22[1] = a2;
  rgTransform.Encoded = 0;
  v23 = a1;
  v15 = CryptXmlOpenToEncode(0, 0, &wszURI, &rgProperty, 1u, pEncoded, &hCryptXml);
  if ( v15 >= 0 )
  {
    phReference = 0;
    v15 = CryptXmlCreateReference(hCryptXml, 0, 0, &wszURI, 0, &pDigestMethod, 1u, &rgTransform, &phReference);
    if ( v15 >= 0 )
    {
      v15 = CryptXmlSign(
              hCryptXml,
              a4,
              dwKeySpec,
              0,
              CRYPT_XML_KEYINFO_SPEC_PARAM,
              pvKeyInfoSpec,
              &pSignatureMethod,
              &pCanonicalization);
      if ( v15 >= 0 )
      {
        v26.pvValue = &qword_180082F80;
        v26.dwPropId = CRYPT_XML_PROPERTY_DOC_DECLARATION;
        v26.cbValue = 4;
        v15 = CryptXmlEncode(hCryptXml, CRYPT_XML_CHARSET_UTF8, &v26, 1u, &pvCallbackState, CryptXmlSignCallback);
        if ( v15 >= 0 )
        {
          v16 = SafeMultiByteToWideChar(0xFDE9u, 0, (const char *)pvCallbackState, DWORD2(pvCallbackState), 0, 0);
          v17 = v16;
          if ( !v16 )
            goto LABEL_13;
          v18 = (unsigned __int16 *)SafeHeapAlloc(2LL * v16);
          *a8 = v18;
          if ( !v18 )
          {
            v15 = -2147024882;
            goto LABEL_15;
          }
          if ( SafeMultiByteToWideChar(0xFDE9u, 0, (const char *)pvCallbackState, DWORD2(pvCallbackState), v18, v17) != v17 )
          {
LABEL_13:
            LastError = GetLastError();
            v15 = LastError;
            if ( LastError > 0 )
              v15 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
LABEL_15:
  if ( (_QWORD)pvCallbackState )
    SafeHeapFree((void *)pvCallbackState);
  if ( hCryptXml )
    CryptXmlClose(hCryptXml);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180043c14  mov     [rsp-8+arg_8], rbx
0x180043c19  mov     [rsp-8+arg_18], rsi
0x180043c1e  push    rbp
0x180043c1f  push    rdi
0x180043c20  push    r12
0x180043c22  push    r14
0x180043c24  push    r15
0x180043c26  lea     rbp, [rsp-80h]
0x180043c2b  sub     rsp, 180h
0x180043c32  mov     esi, edx
0x180043c34  mov     [rbp+0A0h+hCryptXml], 0
0x180043c3f  xor     edx, edx; Val
0x180043c41  mov     rbx, r8
0x180043c44  mov     r14, rcx
0x180043c47  xorps   xmm0, xmm0
0x180043c4a  lea     rcx, [rbp+0A0h+pvKeyInfoSpec]; void *
0x180043c4e  mov     rdi, r9
0x180043c51  movups  [rsp+1A0h+pvCallbackState], xmm0
0x180043c56  lea     r8d, [rdx+48h]; Size
0x180043c5a  call    memset_0
0x180043c5f  xor     r9d, r9d; dwFlags
0x180043c62  lea     rdx, aSha256; "SHA256"
0x180043c69  lea     r12d, [r9+3]
0x180043c6d  mov     ecx, r12d; dwFindByType
0x180043c70  lea     r8d, [r9+1]; dwGroupId
0x180043c74  call    cs:__imp_CryptXmlFindAlgorithmInfo
0x180043c7a  mov     r8d, r12d; dwGroupId
0x180043c7d  mov     r15, [rax+8]
0x180043c81  mov     rax, [rbx+10h]
0x180043c85  lea     r12d, [r8-2]
0x180043c89  mov     rcx, [rax]
0x180043c8c  mov     rax, [rcx+10h]
0x180043c90  mov     rcx, [rax]
0x180043c93  mov     rax, [rcx+8]
0x180043c97  mov     ecx, r12d; dwKeyType
0x180043c9a  mov     rdx, [rax+18h]
0x180043c9e  mov     rdx, [rdx+60h]; pvKey
0x180043ca2  call    cs:__imp_CryptFindOIDInfo
0x180043ca8  lea     ebx, [r12+1]
0x180043cad  test    rax, rax
0x180043cb0  jz      short loc_180043CE0
0x180043cb2  lea     rcx, aSha256; "SHA256"
0x180043cb9  xor     r9d, r9d; dwFlags
0x180043cbc  mov     [rsp+1A0h+pvFindBy], rcx
0x180043cc1  lea     rdx, [rsp+1A0h+pvFindBy]; pvFindBy
0x180043cc6  mov     rax, [rax+30h]
0x180043cca  mov     r8d, ebx; dwGroupId
0x180043ccd  mov     [rsp+1A0h+var_128], rax
0x180043cd2  lea     ecx, [r9+4]; dwFindByType
0x180043cd6  call    cs:__imp_CryptXmlFindAlgorithmInfo
0x180043cdc  mov     rax, [rax+8]
0x180043ce0  mov     [rbp+0A0h+pSignatureMethod.wszAlgorithm], rax
0x180043ce4  lea     rcx, [rsp+1A0h+var_140]
0x180043ce9  xorps   xmm0, xmm0
0x180043cec  mov     qword ptr [rbp+0A0h+pSignatureMethod.cbSize], 20h ; ' '
0x180043cf4  lea     rax, aHttpWwwW3Org20; "http://www.w3.org/2001/10/xml-exc-c14n#"
0x180043cfb  mov     qword ptr [rbp+0A0h+pCanonicalization.cbSize], 20h ; ' '
0x180043d03  mov     [rbp+0A0h+pCanonicalization.wszAlgorithm], rax
0x180043d07  lea     r9, [rbp+0A0h+rgProperty]; rgProperty
0x180043d0b  lea     rax, aHttpWwwW3Org20_0; "http://www.w3.org/2000/09/xmldsig#envel"...
0x180043d12  mov     qword ptr [rbp+0A0h+pDigestMethod.cbSize], 20h ; ' '
0x180043d1a  mov     [rbp+0A0h+var_F0.wszAlgorithm], rax
0x180043d1e  lea     r8, wszURI; wszId
0x180043d25  lea     rax, aEnvelopeHeader; "/Envelope/Header/Security"
0x180043d2c  mov     [rbp+0A0h+pDigestMethod.wszAlgorithm], r15
0x180043d30  mov     [rbp+0A0h+arg_10], rax
0x180043d37  lea     rax, [rbp+0A0h+arg_10]
0x180043d3e  mov     [rbp+0A0h+rgProperty.pvValue], rax
0x180043d42  xor     eax, eax
0x180043d44  test    esi, esi
0x180043d46  mov     qword ptr [rbp+0A0h+var_F0.cbSize], 20h ; ' '
0x180043d4e  movdqu  xmmword ptr [rbp+0A0h+pSignatureMethod.Encoded.dwCharset], xmm0
0x180043d53  cmovz   rcx, rax
0x180043d57  mov     [rbp+0A0h+rgProperty.dwPropId], ebx
0x180043d5a  lea     rax, [rbp+0A0h+hCryptXml]
0x180043d61  mov     [rbp+0A0h+rgProperty.cbValue], 8
0x180043d68  mov     [rsp+1A0h+phSignature], rax; phSignature
0x180043d6d  xor     edx, edx; dwFlags
0x180043d6f  mov     [rsp+1A0h+pEncoded], rcx; pEncoded
0x180043d74  xor     ecx, ecx; pConfig
0x180043d76  movdqu  xmmword ptr [rbp+0A0h+pCanonicalization.Encoded.dwCharset], xmm0
0x180043d7b  mov     [rsp+1A0h+var_140], ebx
0x180043d7f  movdqu  xmmword ptr [rbp+0A0h+pDigestMethod.Encoded.dwCharset], xmm0
0x180043d84  mov     [rsp+1A0h+var_13C], esi
0x180043d88  movdqu  xmmword ptr [rbp+0A0h+var_F0.Encoded.dwCharset], xmm0
0x180043d8d  mov     [rsp+1A0h+var_138], r14
0x180043d92  mov     [rsp+1A0h+cProperty], r12d; cProperty
0x180043d97  call    cs:__imp_CryptXmlOpenToEncode
0x180043d9d  mov     ebx, eax
0x180043d9f  test    eax, eax
0x180043da1  js      loc_180043F1D
0x180043da7  mov     rcx, [rbp+0A0h+hCryptXml]; hCryptXml
0x180043dae  lea     rax, [rbp+0A0h+arg_28]
0x180043db5  mov     [rsp+1A0h+phReference], rax; phReference
0x180043dba  lea     r9, wszURI; wszURI
0x180043dc1  lea     rax, [rbp+0A0h+var_F0]
0x180043dc5  mov     [rbp+0A0h+arg_28], 0
0x180043dd0  mov     [rsp+1A0h+rgTransform], rax; rgTransform
0x180043dd5  xor     r8d, r8d; wszId
0x180043dd8  lea     rax, [rbp+0A0h+pDigestMethod]
0x180043ddc  mov     dword ptr [rsp+1A0h+phSignature], r12d; cTransform
0x180043de1  mov     [rsp+1A0h+pEncoded], rax; pDigestMethod
0x180043de6  xor     edx, edx; dwFlags
0x180043de8  mov     qword ptr [rsp+1A0h+cProperty], 0; wszType
0x180043df1  call    cs:__imp_CryptXmlCreateReference
0x180043df7  mov     ebx, eax
0x180043df9  test    eax, eax
0x180043dfb  js      loc_180043F1D
0x180043e01  mov     r8d, [rbp+0A0h+dwKeySpec]; dwKeySpec
0x180043e08  lea     rax, [rbp+0A0h+pCanonicalization]
0x180043e0c  mov     rcx, [rbp+0A0h+hCryptXml]; hSignature
0x180043e13  xor     r9d, r9d; dwFlags
0x180043e16  mov     [rsp+1A0h+rgTransform], rax; pCanonicalization
0x180043e1b  mov     rdx, rdi; hKey
0x180043e1e  lea     rax, [rbp+0A0h+pSignatureMethod]
0x180043e22  mov     [rsp+1A0h+phSignature], rax; pSignatureMethod
0x180043e27  lea     rax, [rbp+0A0h+pvKeyInfoSpec]
0x180043e2b  mov     [rsp+1A0h+pEncoded], rax; pvKeyInfoSpec
0x180043e30  mov     [rsp+1A0h+cProperty], 2; dwKeyInfoSpec
0x180043e38  call    cs:__imp_CryptXmlSign
0x180043e3e  mov     ebx, eax
0x180043e40  test    eax, eax
0x180043e42  js      loc_180043F1D
0x180043e48  mov     ecx, 4
0x180043e4d  lea     rax, qword_180082F80
0x180043e54  mov     [rbp+0A0h+var_108.pvValue], rax
0x180043e58  lea     r8, [rbp+0A0h+var_108]; rgProperty
0x180043e5c  lea     rax, CryptXmlSignCallback
0x180043e63  mov     [rbp+0A0h+var_108.dwPropId], ecx
0x180043e66  mov     [rsp+1A0h+pEncoded], rax; pfnWrite
0x180043e6b  mov     r9d, r12d; cProperty
0x180043e6e  lea     rax, [rsp+1A0h+pvCallbackState]
0x180043e73  mov     [rbp+0A0h+var_108.cbValue], ecx
0x180043e76  mov     rcx, [rbp+0A0h+hCryptXml]; hCryptXml
0x180043e7d  mov     edx, r12d; dwCharset
0x180043e80  mov     qword ptr [rsp+1A0h+cProperty], rax; pvCallbackState
0x180043e85  call    cs:__imp_CryptXmlEncode
0x180043e8b  mov     ebx, eax
0x180043e8d  test    eax, eax
0x180043e8f  js      loc_180043F1D
0x180043e95  mov     r9d, dword ptr [rsp+1A0h+pvCallbackState+8]
0x180043e9a  mov     esi, 0FDE9h
0x180043e9f  mov     r8, qword ptr [rsp+1A0h+pvCallbackState]
0x180043ea4  mov     ecx, esi
0x180043ea6  mov     dword ptr [rsp+1A0h+pEncoded], 0
0x180043eae  xor     edx, edx
0x180043eb0  mov     qword ptr [rsp+1A0h+cProperty], 0
0x180043eb9  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x180043ebf  movsxd  rdi, eax
0x180043ec2  test    eax, eax
0x180043ec4  jz      short loc_180043F08
0x180043ec6  mov     rcx, rdi
0x180043ec9  add     rcx, rcx; unsigned __int64
0x180043ecc  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180043ed1  mov     rcx, [rbp+0A0h+arg_38]
0x180043ed8  mov     [rcx], rax
0x180043edb  test    rax, rax
0x180043ede  jnz     short loc_180043EE7
0x180043ee0  mov     ebx, 8007000Eh
0x180043ee5  jmp     short loc_180043F1D
0x180043ee7  mov     r9d, dword ptr [rsp+1A0h+pvCallbackState+8]
0x180043eec  xor     edx, edx
0x180043eee  mov     r8, qword ptr [rsp+1A0h+pvCallbackState]
0x180043ef3  mov     ecx, esi
0x180043ef5  mov     dword ptr [rsp+1A0h+pEncoded], edi
0x180043ef9  mov     qword ptr [rsp+1A0h+cProperty], rax
0x180043efe  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x180043f04  cmp     eax, edi
0x180043f06  jz      short loc_180043F1D
0x180043f08  call    cs:__imp_GetLastError
0x180043f0e  mov     ebx, eax
0x180043f10  test    eax, eax
0x180043f12  jle     short loc_180043F1D
0x180043f14  movzx   ebx, ax
0x180043f17  or      ebx, 80070000h
0x180043f1d  mov     rcx, qword ptr [rsp+1A0h+pvCallbackState]; void *
0x180043f22  test    rcx, rcx
0x180043f25  jz      short loc_180043F2C
0x180043f27  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180043f2c  mov     rcx, [rbp+0A0h+hCryptXml]; hCryptXml
0x180043f33  test    rcx, rcx
0x180043f36  jz      short loc_180043F3E
0x180043f38  call    cs:__imp_CryptXmlClose
0x180043f3e  lea     r11, [rsp+1A0h+var_20]
0x180043f46  mov     eax, ebx
0x180043f48  mov     rbx, [r11+38h]
0x180043f4c  mov     rsi, [r11+48h]
0x180043f50  mov     rsp, r11
0x180043f53  pop     r15
0x180043f55  pop     r14
0x180043f57  pop     r12
0x180043f59  pop     rdi
0x180043f5a  pop     rbp
0x180043f5b  retn
```
