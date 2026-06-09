# CryptXMLSignInternal

- ea: `0x18001b208`
- end: `0x18001b5c8`
- name: `CryptXMLSignInternal`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b098`

## callees

- `0x1800031a0`
- `0x18001b208`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b507`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b507`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b58a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b58a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b4f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b4f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b551`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001b4d9`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001b541`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001b4d9`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18001b541`
- `CRYPT32!CryptFindOIDInfo` at `0x18001b295`
- `CRYPT32!CryptFindOIDInfo` at `0x18001b295`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x18001b39c`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x18001b39c`
- `CRYPTXML!CryptXmlCreateReference` at `0x18001b3fb`
- `CRYPTXML!CryptXmlCreateReference` at `0x18001b3fb`
- `CRYPTXML!CryptXmlSign` at `0x18001b448`
- `CRYPTXML!CryptXmlSign` at `0x18001b448`
- `CRYPTXML!CryptXmlEncode` at `0x18001b49d`
- `CRYPTXML!CryptXmlEncode` at `0x18001b49d`
- `CRYPTXML!CryptXmlClose` at `0x18001b5a2`
- `CRYPTXML!CryptXmlClose` at `0x18001b5a2`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18001b25f`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18001b2cb`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18001b25f`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18001b2cb`

## string_xrefs

- `0x18001b302`: `http://www.w3.org/2000/09/xmldsig#enveloped-signature`
- `0x18001b31c`: `/Envelope/Header/Security`
- `0x18001b2eb`: `http://www.w3.org/2001/10/xml-exc-c14n#`

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
  int v15; // edi
  int v16; // eax
  __int64 v17; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v19; // rax
  signed int LastError; // eax
  void *v21; // rbx
  HANDLE v22; // rax
  __int128 pvCallbackState; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h]
  _QWORD pvFindBy[2]; // [rsp+70h] [rbp-90h] BYREF
  CRYPT_XML_PROPERTY rgProperty; // [rsp+80h] [rbp-80h] BYREF
  CRYPT_XML_PROPERTY v29; // [rsp+98h] [rbp-68h] BYREF
  CRYPT_XML_ALGORITHM rgTransform; // [rsp+B0h] [rbp-50h] BYREF
  CRYPT_XML_ALGORITHM pDigestMethod; // [rsp+D0h] [rbp-30h] BYREF
  CRYPT_XML_ALGORITHM pCanonicalization; // [rsp+F0h] [rbp-10h] BYREF
  CRYPT_XML_ALGORITHM pSignatureMethod; // [rsp+110h] [rbp+10h] BYREF
  _BYTE pvKeyInfoSpec[112]; // [rsp+130h] [rbp+30h] BYREF
  HCRYPTXML hCryptXml; // [rsp+1B0h] [rbp+B0h] BYREF
  const wchar_t *v36; // [rsp+1C0h] [rbp+C0h] BYREF

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
  pEncoded = (const CRYPT_XML_BLOB *)v25;
  pDigestMethod.wszAlgorithm = wszAlgorithmURI;
  *(_QWORD *)&pSignatureMethod.cbSize = 32;
  pCanonicalization.wszAlgorithm = L"http://www.w3.org/2001/10/xml-exc-c14n#";
  *(_QWORD *)&pCanonicalization.cbSize = 32;
  rgTransform.wszAlgorithm = L"http://www.w3.org/2000/09/xmldsig#enveloped-signature";
  *(_QWORD *)&pDigestMethod.cbSize = 32;
  v36 = L"/Envelope/Header/Security";
  *(_QWORD *)&rgTransform.cbSize = 32;
  rgProperty.pvValue = &v36;
  rgProperty.dwPropId = CRYPT_XML_PROPERTY_SIGNATURE_LOCATION;
  pSignatureMethod.Encoded = 0;
  if ( !a2 )
    pEncoded = 0;
  rgProperty.cbValue = 8;
  v25[0] = 2;
  pCanonicalization.Encoded = 0;
  v25[1] = a2;
  pDigestMethod.Encoded = 0;
  v26 = a1;
  rgTransform.Encoded = 0;
  v15 = CryptXmlOpenToEncode(0, 0, &String2, &rgProperty, 1u, pEncoded, &hCryptXml);
  if ( v15 >= 0 )
  {
    phReference = 0;
    v15 = CryptXmlCreateReference(hCryptXml, 0, 0, &String2, 0, &pDigestMethod, 1u, &rgTransform, &phReference);
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
        v29.pvValue = qword_1800520A0;
        v29.dwPropId = CRYPT_XML_PROPERTY_DOC_DECLARATION;
        v29.cbValue = 4;
        v15 = CryptXmlEncode(hCryptXml, CRYPT_XML_CHARSET_UTF8, &v29, 1u, &pvCallbackState, CryptXmlSignCallback);
        if ( v15 >= 0 )
        {
          v16 = SafeMultiByteToWideChar(0xFDE9u, 0, (const char *)pvCallbackState, DWORD2(pvCallbackState), 0, 0);
          v17 = v16;
          if ( !v16 )
            goto LABEL_13;
          ProcessHeap = GetProcessHeap();
          v19 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v17);
          *a8 = v19;
          if ( !v19 )
          {
            v15 = -2147024882;
            goto LABEL_15;
          }
          if ( SafeMultiByteToWideChar(0xFDE9u, 0, (const char *)pvCallbackState, DWORD2(pvCallbackState), v19, v17) != (_DWORD)v17 )
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
  v21 = (void *)pvCallbackState;
  if ( (_QWORD)pvCallbackState )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  if ( hCryptXml )
    CryptXmlClose(hCryptXml);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001b208  mov     [rsp-8+arg_8], rbx
0x18001b20d  push    rbp
0x18001b20e  push    rsi
0x18001b20f  push    rdi
0x18001b210  push    r14
0x18001b212  push    r15
0x18001b214  lea     rbp, [rsp-80h]
0x18001b219  sub     rsp, 180h
0x18001b220  mov     edi, edx
0x18001b222  mov     [rbp+0A0h+hCryptXml], 0
0x18001b22d  xor     edx, edx; Val
0x18001b22f  mov     rbx, r8
0x18001b232  mov     r14, rcx
0x18001b235  xorps   xmm0, xmm0
0x18001b238  lea     rcx, [rbp+0A0h+pvKeyInfoSpec]; void *
0x18001b23c  mov     rsi, r9
0x18001b23f  movups  [rsp+1A0h+pvCallbackState], xmm0
0x18001b244  lea     r8d, [rdx+48h]; Size
0x18001b248  call    memset_0
0x18001b24d  xor     r9d, r9d; dwFlags
0x18001b250  lea     rdx, aSha256; "SHA256"
0x18001b257  lea     r8d, [r9+1]; dwGroupId
0x18001b25b  lea     ecx, [r9+3]; dwFindByType
0x18001b25f  call    cs:__imp_CryptXmlFindAlgorithmInfo
0x18001b266  nop     dword ptr [rax+rax+00h]
0x18001b26b  mov     r8d, 3; dwGroupId
0x18001b271  mov     r15, [rax+8]
0x18001b275  mov     rax, [rbx+10h]
0x18001b279  lea     ebx, [r8-2]
0x18001b27d  mov     rcx, [rax]
0x18001b280  mov     rax, [rcx+10h]
0x18001b284  mov     rcx, [rax]
0x18001b287  mov     rax, [rcx+8]
0x18001b28b  mov     ecx, ebx; dwKeyType
0x18001b28d  mov     rdx, [rax+18h]
0x18001b291  mov     rdx, [rdx+60h]; pvKey
0x18001b295  call    cs:__imp_CryptFindOIDInfo
0x18001b29c  nop     dword ptr [rax+rax+00h]
0x18001b2a1  test    rax, rax
0x18001b2a4  jz      short loc_18001B2DB
0x18001b2a6  xor     r9d, r9d; dwFlags
0x18001b2a9  lea     rcx, aSha256; "SHA256"
0x18001b2b0  mov     [rsp+1A0h+pvFindBy], rcx
0x18001b2b5  lea     rdx, [rsp+1A0h+pvFindBy]; pvFindBy
0x18001b2ba  mov     rax, [rax+30h]
0x18001b2be  mov     [rsp+1A0h+var_128], rax
0x18001b2c3  lea     r8d, [r9+2]; dwGroupId
0x18001b2c7  lea     ecx, [r9+4]; dwFindByType
0x18001b2cb  call    cs:__imp_CryptXmlFindAlgorithmInfo
0x18001b2d2  nop     dword ptr [rax+rax+00h]
0x18001b2d7  mov     rax, [rax+8]
0x18001b2db  mov     [rbp+0A0h+pSignatureMethod.wszAlgorithm], rax
0x18001b2df  lea     rcx, [rsp+1A0h+var_140]
0x18001b2e4  xorps   xmm0, xmm0
0x18001b2e7  mov     [rbp+0A0h+pDigestMethod.wszAlgorithm], r15
0x18001b2eb  lea     rax, aHttpWwwW3Org20; "http://www.w3.org/2001/10/xml-exc-c14n#"
0x18001b2f2  mov     qword ptr [rbp+0A0h+pSignatureMethod.cbSize], 20h ; ' '
0x18001b2fa  mov     [rbp+0A0h+pCanonicalization.wszAlgorithm], rax
0x18001b2fe  lea     r9, [rbp+0A0h+rgProperty]; rgProperty
0x18001b302  lea     rax, aHttpWwwW3Org20_0; "http://www.w3.org/2000/09/xmldsig#envel"...
0x18001b309  mov     qword ptr [rbp+0A0h+pCanonicalization.cbSize], 20h ; ' '
0x18001b311  mov     [rbp+0A0h+var_F0.wszAlgorithm], rax
0x18001b315  lea     r8, String2; wszId
0x18001b31c  lea     rax, aEnvelopeHeader; "/Envelope/Header/Security"
0x18001b323  mov     qword ptr [rbp+0A0h+pDigestMethod.cbSize], 20h ; ' '
0x18001b32b  mov     [rbp+0A0h+arg_10], rax
0x18001b332  mov     r15d, 8
0x18001b338  lea     rax, [rbp+0A0h+arg_10]
0x18001b33f  mov     qword ptr [rbp+0A0h+var_F0.cbSize], 20h ; ' '
0x18001b347  mov     [rbp+0A0h+rgProperty.pvValue], rax
0x18001b34b  xor     eax, eax
0x18001b34d  test    edi, edi
0x18001b34f  mov     [rbp+0A0h+rgProperty.dwPropId], 2
0x18001b356  movdqu  xmmword ptr [rbp+0A0h+pSignatureMethod.Encoded.dwCharset], xmm0
0x18001b35b  cmovz   rcx, rax
0x18001b35f  mov     [rbp+0A0h+rgProperty.cbValue], r15d
0x18001b363  lea     rax, [rbp+0A0h+hCryptXml]
0x18001b36a  mov     [rsp+1A0h+var_140], 2
0x18001b372  mov     [rsp+1A0h+phSignature], rax; phSignature
0x18001b377  xor     edx, edx; dwFlags
0x18001b379  mov     [rsp+1A0h+pEncoded], rcx; pEncoded
0x18001b37e  xor     ecx, ecx; pConfig
0x18001b380  movdqu  xmmword ptr [rbp+0A0h+pCanonicalization.Encoded.dwCharset], xmm0
0x18001b385  mov     [rsp+1A0h+var_13C], edi
0x18001b389  movdqu  xmmword ptr [rbp+0A0h+pDigestMethod.Encoded.dwCharset], xmm0
0x18001b38e  mov     [rsp+1A0h+var_138], r14
0x18001b393  movdqu  xmmword ptr [rbp+0A0h+var_F0.Encoded.dwCharset], xmm0
0x18001b398  mov     [rsp+1A0h+cProperty], ebx; cProperty
0x18001b39c  call    cs:__imp_CryptXmlOpenToEncode
0x18001b3a3  nop     dword ptr [rax+rax+00h]
0x18001b3a8  mov     edi, eax
0x18001b3aa  test    eax, eax
0x18001b3ac  js      loc_18001B56C
0x18001b3b2  mov     rcx, [rbp+0A0h+hCryptXml]; hCryptXml
0x18001b3b9  lea     rax, [rbp+0A0h+arg_28]
0x18001b3c0  mov     [rsp+1A0h+phReference], rax; phReference
0x18001b3c5  lea     r9, String2; wszURI
0x18001b3cc  lea     rax, [rbp+0A0h+var_F0]
0x18001b3d0  mov     [rbp+0A0h+arg_28], 0
0x18001b3db  mov     [rsp+1A0h+rgTransform], rax; rgTransform
0x18001b3e0  xor     r8d, r8d; wszId
0x18001b3e3  lea     rax, [rbp+0A0h+pDigestMethod]
0x18001b3e7  mov     dword ptr [rsp+1A0h+phSignature], ebx; cTransform
0x18001b3eb  mov     [rsp+1A0h+pEncoded], rax; pDigestMethod
0x18001b3f0  xor     edx, edx; dwFlags
0x18001b3f2  mov     qword ptr [rsp+1A0h+cProperty], 0; wszType
0x18001b3fb  call    cs:__imp_CryptXmlCreateReference
0x18001b402  nop     dword ptr [rax+rax+00h]
0x18001b407  mov     edi, eax
0x18001b409  test    eax, eax
0x18001b40b  js      loc_18001B56C
0x18001b411  mov     r8d, [rbp+0A0h+dwKeySpec]; dwKeySpec
0x18001b418  lea     rax, [rbp+0A0h+pCanonicalization]
0x18001b41c  mov     rcx, [rbp+0A0h+hCryptXml]; hSignature
0x18001b423  xor     r9d, r9d; dwFlags
0x18001b426  mov     [rsp+1A0h+rgTransform], rax; pCanonicalization
0x18001b42b  mov     rdx, rsi; hKey
0x18001b42e  lea     rax, [rbp+0A0h+pSignatureMethod]
0x18001b432  mov     [rsp+1A0h+phSignature], rax; pSignatureMethod
0x18001b437  lea     rax, [rbp+0A0h+pvKeyInfoSpec]
0x18001b43b  mov     [rsp+1A0h+pEncoded], rax; pvKeyInfoSpec
0x18001b440  mov     [rsp+1A0h+cProperty], 2; dwKeyInfoSpec
0x18001b448  call    cs:__imp_CryptXmlSign
0x18001b44f  nop     dword ptr [rax+rax+00h]
0x18001b454  mov     edi, eax
0x18001b456  test    eax, eax
0x18001b458  js      loc_18001B56C
0x18001b45e  mov     rcx, [rbp+0A0h+hCryptXml]; hCryptXml
0x18001b465  lea     rax, qword_1800520A0
0x18001b46c  mov     [rbp+0A0h+var_108.pvValue], rax
0x18001b470  lea     r8, [rbp+0A0h+var_108]; rgProperty
0x18001b474  lea     rax, CryptXmlSignCallback
0x18001b47b  mov     [rbp+0A0h+var_108.dwPropId], 4
0x18001b482  mov     [rsp+1A0h+pEncoded], rax; pfnWrite
0x18001b487  mov     r9d, ebx; cProperty
0x18001b48a  lea     rax, [rsp+1A0h+pvCallbackState]
0x18001b48f  mov     [rbp+0A0h+var_108.cbValue], 4
0x18001b496  mov     edx, ebx; dwCharset
0x18001b498  mov     qword ptr [rsp+1A0h+cProperty], rax; pvCallbackState
0x18001b49d  call    cs:__imp_CryptXmlEncode
0x18001b4a4  nop     dword ptr [rax+rax+00h]
0x18001b4a9  mov     edi, eax
0x18001b4ab  test    eax, eax
0x18001b4ad  js      loc_18001B56C
0x18001b4b3  mov     r9d, dword ptr [rsp+1A0h+pvCallbackState+8]
0x18001b4b8  mov     r14d, 0FDE9h
0x18001b4be  mov     r8, qword ptr [rsp+1A0h+pvCallbackState]
0x18001b4c3  mov     ecx, r14d
0x18001b4c6  mov     dword ptr [rsp+1A0h+pEncoded], 0
0x18001b4ce  xor     edx, edx
0x18001b4d0  mov     qword ptr [rsp+1A0h+cProperty], 0
0x18001b4d9  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x18001b4e0  nop     dword ptr [rax+rax+00h]
0x18001b4e5  movsxd  rsi, eax
0x18001b4e8  test    eax, eax
0x18001b4ea  jz      short loc_18001B551
0x18001b4ec  mov     rbx, rsi
0x18001b4ef  add     rbx, rbx
0x18001b4f2  call    cs:__imp_GetProcessHeap
0x18001b4f9  nop     dword ptr [rax+rax+00h]
0x18001b4fe  mov     r8, rbx; dwBytes
0x18001b501  mov     edx, r15d; dwFlags
0x18001b504  mov     rcx, rax; hHeap
0x18001b507  call    cs:__imp_HeapAlloc
0x18001b50e  nop     dword ptr [rax+rax+00h]
0x18001b513  mov     rcx, [rbp+0A0h+arg_38]
0x18001b51a  mov     [rcx], rax
0x18001b51d  test    rax, rax
0x18001b520  jnz     short loc_18001B529
0x18001b522  mov     edi, 8007000Eh
0x18001b527  jmp     short loc_18001B56C
0x18001b529  mov     r9d, dword ptr [rsp+1A0h+pvCallbackState+8]
0x18001b52e  xor     edx, edx
0x18001b530  mov     r8, qword ptr [rsp+1A0h+pvCallbackState]
0x18001b535  mov     ecx, r14d
0x18001b538  mov     dword ptr [rsp+1A0h+pEncoded], esi
0x18001b53c  mov     qword ptr [rsp+1A0h+cProperty], rax
0x18001b541  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x18001b548  nop     dword ptr [rax+rax+00h]
0x18001b54d  cmp     eax, esi
0x18001b54f  jz      short loc_18001B56C
0x18001b551  call    cs:__imp_GetLastError
0x18001b558  nop     dword ptr [rax+rax+00h]
0x18001b55d  mov     edi, eax
0x18001b55f  test    eax, eax
0x18001b561  jle     short loc_18001B56C
0x18001b563  movzx   edi, ax
0x18001b566  or      edi, 80070000h
0x18001b56c  mov     rbx, qword ptr [rsp+1A0h+pvCallbackState]
0x18001b571  test    rbx, rbx
0x18001b574  jz      short loc_18001B596
0x18001b576  call    cs:__imp_GetProcessHeap
0x18001b57d  nop     dword ptr [rax+rax+00h]
0x18001b582  mov     r8, rbx; lpMem
0x18001b585  xor     edx, edx; dwFlags
0x18001b587  mov     rcx, rax; hHeap
0x18001b58a  call    cs:__imp_HeapFree
0x18001b591  nop     dword ptr [rax+rax+00h]
0x18001b596  mov     rcx, [rbp+0A0h+hCryptXml]; hCryptXml
0x18001b59d  test    rcx, rcx
0x18001b5a0  jz      short loc_18001B5AE
0x18001b5a2  call    cs:__imp_CryptXmlClose
0x18001b5a9  nop     dword ptr [rax+rax+00h]
0x18001b5ae  mov     rbx, [rsp+1A0h+arg_8]
0x18001b5b6  mov     eax, edi
0x18001b5b8  add     rsp, 180h
0x18001b5bf  pop     r15
0x18001b5c1  pop     r14
0x18001b5c3  pop     rdi
0x18001b5c4  pop     rsi
0x18001b5c5  pop     rbp
0x18001b5c6  retn
```
