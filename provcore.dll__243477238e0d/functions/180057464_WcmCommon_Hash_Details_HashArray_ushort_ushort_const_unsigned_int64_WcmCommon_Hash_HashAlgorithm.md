# WcmCommon::Hash::Details::HashArray<ushort>(ushort const *,unsigned __int64,WcmCommon::Hash::HashAlgorithm)

- ea: `0x180057464`
- end: `0x1800576d7`
- name: `??$HashArray@G@Details@Hash@WcmCommon@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEBG_KW4HashAlgorithm@12@@Z`
- size: `627`
- prototype: `std::vector<_GUID> *__fastcall(std::vector<_GUID> *result, const BYTE *Buffer, unsigned __int64 NumElements, WcmCommon::Hash::HashAlgorithm)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800577dc`

## callees

- `0x180002790`
- `0x18000b178`
- `0x18001a0d4`
- `0x180028f98`
- `0x180028fc8`
- `0x18004acb0`
- `0x180057464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005752c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005757b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005765c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005752c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005757b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005765c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800574c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800574c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800576a2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800576a2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180057522`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180057522`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180057571`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180057571`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800575c9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180057652`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800575c9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180057652`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800576af`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800576af`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
std::vector<_GUID> *__fastcall WcmCommon::Hash::Details::HashArray<unsigned short>(
        std::vector<_GUID> *result,
        const BYTE *Buffer,
        unsigned __int64 NumElements,
        WcmCommon::Hash::HashAlgorithm a4)
{
  int v4; // edi
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  const std::allocator<unsigned char> *v10; // r8
  signed int v11; // eax
  signed int v12; // eax
  unsigned int hashLength; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int64 hashHandle; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int64 providerHandle; // [rsp+68h] [rbp+Fh] BYREF
  unsigned int hashLengthSize; // [rsp+70h] [rbp+17h] BYREF
  std::vector<unsigned char> hashBlob; // [rsp+78h] [rbp+1Fh] BYREF
  void *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = NumElements;
  providerHandle = (unsigned __int64)result;
  if ( NumElements )
  {
    providerHandle = 0;
    if ( !CryptAcquireContextW(&providerHandle, 0, 0, 1u, 0xF0000040) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x41u, "onecore\\private\\net\\inc\\wcm\\wcm_hash.h", LastError);
    }
    hashHandle = 0;
    if ( !CryptCreateHash(providerHandle, 0x8004u, 0, 0, &hashHandle) )
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x4Cu, "onecore\\private\\net\\inc\\wcm\\wcm_hash.h", v8);
    }
    if ( !CryptHashData(hashHandle, Buffer, 2 * v4, 0) )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x56u, "onecore\\private\\net\\inc\\wcm\\wcm_hash.h", v9);
    }
    hashLength = 0;
    hashLengthSize = 4;
    if ( !CryptGetHashParam(hashHandle, 4u, (BYTE *)&hashLength, &hashLengthSize, 0) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x60u, "onecore\\private\\net\\inc\\wcm\\wcm_hash.h", v11);
    }
    if ( !hashLength )
      wil::details::in1diag3::Throw_Hr(retaddr, 0x65u, "onecore\\private\\net\\inc\\wcm\\wcm_hash.h", -2147467259);
    memset(&hashBlob, 0, sizeof(hashBlob));
    std::vector<unsigned char>::vector<unsigned char>(&hashBlob, hashLength, v10);
    if ( !CryptGetHashParam(hashHandle, 2u, hashBlob._Mypair._Myval2._Myfirst, &hashLength, 0) )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x6Eu, "onecore\\private\\net\\inc\\wcm\\wcm_hash.h", v12);
    }
    std::vector<_GUID>::vector<_GUID>(result, (std::vector<_GUID> *)&hashBlob);
    std::vector<unsigned char>::_Tidy((std::vector<char> *)&hashBlob);
    CryptDestroyHash(hashHandle);
    CryptReleaseContext(providerHandle, 0);
  }
  else
  {
    std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(result);
  }
  return result;
}

```

## disassembly

```asm
0x180057464  mov     [rsp-8+arg_18], rbx
0x180057469  push    rbp
0x18005746a  push    rsi
0x18005746b  push    rdi
0x18005746c  lea     rbp, [rsp-47h]
0x180057471  sub     rsp, 0A0h
0x180057478  mov     rax, cs:__security_cookie
0x18005747f  xor     rax, rsp
0x180057482  mov     [rbp+57h+var_20], rax
0x180057486  mov     rdi, NumElements
0x180057489  mov     rsi, Buffer
0x18005748c  mov     rbx, rcx
0x18005748f  mov     [rbp+57h+providerHandle], rcx
0x180057493  test    NumElements, NumElements
0x180057496  jnz     short loc_1800574A2
0x180057498  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18005749d  jmp     loc_1800576B5
0x1800574a2  mov     [rbp+57h+providerHandle], 0
0x1800574aa  mov     [rsp+0B0h+dwFlags], 0F0000040h; dwFlags
0x1800574b2  mov     r9d, 1; dwProvType
0x1800574b8  xor     r8d, r8d; szProvider
0x1800574bb  xor     edx, edx; szContainer
0x1800574bd  lea     rcx, [rbp+57h+providerHandle]; phProv
0x1800574c1  call    cs:__imp_CryptAcquireContextW
0x1800574c7  test    eax, eax
0x1800574c9  jnz     short loc_1800574F6
0x1800574cb  call    cs:__imp_GetLastError
0x1800574d1  test    eax, eax
0x1800574d3  jle     short loc_1800574DD
0x1800574d5  movzx   eax, ax
0x1800574d8  or      eax, 80070000h
0x1800574dd  mov     rcx, [rbp+5Fh]; callerReturnAddress
0x1800574e1  mov     r9d, eax; hr
0x1800574e4  lea     NumElements, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_ha"...
0x1800574eb  mov     edx, 41h ; 'A'; lineNumber
0x1800574f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800574f6  lea     rax, [rbp+57h+providerHandle]
0x1800574fa  mov     [rbp+57h+releaseProviderHandle.m_lambda.providerHandle], rax
0x1800574fe  mov     [rbp+57h+releaseProviderHandle.m_call], 1
0x180057502  mov     [rbp+57h+hashHandle], 0
0x18005750a  lea     rax, [rbp+57h+hashHandle]
0x18005750e  mov     qword ptr [rsp+0B0h+dwFlags], rax; phHash
0x180057513  xor     r9d, r9d; dwFlags
0x180057516  xor     r8d, r8d; hKey
0x180057519  mov     edx, 8004h; Algid
0x18005751e  mov     rcx, [rbp+57h+providerHandle]; hProv
0x180057522  call    cs:__imp_CryptCreateHash
0x180057528  test    eax, eax
0x18005752a  jnz     short loc_180057557
0x18005752c  call    cs:__imp_GetLastError
0x180057532  test    eax, eax
0x180057534  jle     short loc_18005753E
0x180057536  movzx   eax, ax
0x180057539  or      eax, 80070000h
0x18005753e  mov     rcx, [rbp+5Fh]; callerReturnAddress
0x180057542  mov     r9d, eax; hr
0x180057545  lea     NumElements, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_ha"...
0x18005754c  mov     edx, 4Ch ; 'L'; lineNumber
0x180057551  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057557  lea     rax, [rbp+57h+hashHandle]
0x18005755b  mov     [rbp+57h+destroyHash.m_lambda.hashHandle], rax
0x18005755f  mov     [rbp+57h+destroyHash.m_call], 1
0x180057563  lea     r8d, [rdi+rdi]; dwDataLen
0x180057567  xor     r9d, r9d; dwFlags
0x18005756a  mov     Buffer, rsi; pbData
0x18005756d  mov     rcx, [rbp+57h+hashHandle]; hHash
0x180057571  call    cs:__imp_CryptHashData
0x180057577  test    eax, eax
0x180057579  jnz     short loc_1800575A6
0x18005757b  call    cs:__imp_GetLastError
0x180057581  test    eax, eax
0x180057583  jle     short loc_18005758D
0x180057585  movzx   eax, ax
0x180057588  or      eax, 80070000h
0x18005758d  mov     rcx, [rbp+5Fh]; callerReturnAddress
0x180057591  mov     r9d, eax; hr
0x180057594  lea     NumElements, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_ha"...
0x18005759b  mov     edx, 56h ; 'V'; lineNumber
0x1800575a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800575a6  mov     [rbp+57h+hashLength], 0
0x1800575ad  mov     edx, 4; dwParam
0x1800575b2  mov     [rbp+57h+hashLengthSize], edx
0x1800575b5  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x1800575bd  lea     r9, [rbp+57h+hashLengthSize]; pdwDataLen
0x1800575c1  lea     NumElements, [rbp+57h+hashLength]; pbData
0x1800575c5  mov     rcx, [rbp+57h+hashHandle]; hHash
0x1800575c9  call    cs:__imp_CryptGetHashParam
0x1800575cf  test    eax, eax
0x1800575d1  jnz     short loc_1800575FE
0x1800575d3  call    cs:__imp_GetLastError
0x1800575d9  test    eax, eax
0x1800575db  jle     short loc_1800575E5
0x1800575dd  movzx   eax, ax
0x1800575e0  or      eax, 80070000h
0x1800575e5  mov     rcx, [rbp+5Fh]; callerReturnAddress
0x1800575e9  mov     r9d, eax; hr
0x1800575ec  lea     NumElements, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_ha"...
0x1800575f3  mov     edx, 60h ; '`'; lineNumber
0x1800575f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800575fe  mov     eax, [rbp+57h+hashLength]
0x180057601  test    eax, eax
0x180057603  jnz     short loc_18005761F
0x180057605  mov     rcx, [rbp+5Fh]; callerReturnAddress
0x180057609  mov     r9d, 80004005h; hr
0x18005760f  lea     NumElements, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_ha"...
0x180057616  lea     edx, [rax+65h]; lineNumber
0x180057619  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005761f  xorps   xmm0, xmm0
0x180057622  xor     ecx, ecx
0x180057624  movups  xmmword ptr [rbp+57h+hashBlob._Mypair._Myval2._Myfirst], xmm0
0x180057628  mov     [rbp+57h+hashBlob._Mypair._Myval2._Myend], rcx
0x18005762c  mov     Buffer, rax; _Count
0x18005762f  lea     rcx, [rbp+57h+hashBlob]; this
0x180057633  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180057638  nop
0x180057639  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x180057641  lea     r9, [rbp+57h+hashLength]; pdwDataLen
0x180057645  mov     NumElements, [rbp+57h+hashBlob._Mypair._Myval2._Myfirst]; pbData
0x180057649  mov     edx, 2; dwParam
0x18005764e  mov     rcx, [rbp+57h+hashHandle]; hHash
0x180057652  call    cs:__imp_CryptGetHashParam
0x180057658  test    eax, eax
0x18005765a  jnz     short loc_180057687
0x18005765c  call    cs:__imp_GetLastError
0x180057662  test    eax, eax
0x180057664  jle     short loc_18005766E
0x180057666  movzx   eax, ax
0x180057669  or      eax, 80070000h
0x18005766e  mov     rcx, [rbp+5Fh]; callerReturnAddress
0x180057672  mov     r9d, eax; hr
0x180057675  lea     NumElements, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_ha"...
0x18005767c  mov     edx, 6Eh ; 'n'; lineNumber
0x180057681  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057687  lea     Buffer, [rbp+57h+hashBlob]; _Right
0x18005768b  mov     rcx, rbx; this
0x18005768e  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<_GUID>::vector<_GUID>(std::vector<_GUID> &&)
0x180057693  nop
0x180057694  lea     rcx, [rbp+57h+hashBlob]; this
0x180057698  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005769d  nop
0x18005769e  mov     rcx, [rbp+57h+hashHandle]; hHash
0x1800576a2  call    cs:__imp_CryptDestroyHash
0x1800576a8  nop
0x1800576a9  xor     edx, edx; dwFlags
0x1800576ab  mov     rcx, [rbp+57h+providerHandle]; hProv
0x1800576af  call    cs:__imp_CryptReleaseContext
0x1800576b5  mov     rax, rbx
0x1800576b8  mov     rcx, [rbp+57h+var_20]
0x1800576bc  xor     rcx, rsp; StackCookie
0x1800576bf  call    __security_check_cookie
0x1800576c4  mov     rbx, [rsp+0B0h+arg_18]
0x1800576cc  add     rsp, 0A0h
0x1800576d3  pop     rdi
0x1800576d4  pop     rsi
0x1800576d5  pop     rbp
0x1800576d6  retn
```
