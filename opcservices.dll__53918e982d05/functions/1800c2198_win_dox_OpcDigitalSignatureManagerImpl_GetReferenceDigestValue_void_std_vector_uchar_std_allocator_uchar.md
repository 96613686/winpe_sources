# win_dox::OpcDigitalSignatureManagerImpl::GetReferenceDigestValue(void *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800c2198`
- end: `0x1800c2292`
- name: `?GetReferenceDigestValue@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a0fe8`
- `0x1800a5080`

## callees

- `0x18001568c`
- `0x18002db70`
- `0x1800c2198`
- `0x1800c2d94`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `CRYPTXML!CryptXmlGetReference` at `0x1800c2201`
- `CRYPTXML!CryptXmlGetReference` at `0x1800c2201`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c21d0`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c21d0`

## pseudocode

```c
__int64 __fastcall win_dox::OpcDigitalSignatureManagerImpl::GetReferenceDigestValue(__int64 a1, void *a2, __int64 a3)
{
  HRESULT Status; // eax
  int v6; // edx
  const char *v7; // r8
  unsigned int v8; // r9d
  HRESULT Reference; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  CRYPT_XML_REFERENCE *ppStruct; // [rsp+40h] [rbp-D8h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(a2, &pStatus);
  if ( Status < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Status, v6, v7, v8);
  if ( (pStatus.dwInfoStatus & 8) == 0 || (pStatus.dwErrorStatus & 2) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x65Fu,
      0x8051001A,
      (struct win_musl::TStringEllipseBase *)L"Cannot get digest value for a signed reference");
    throw (SplException::THResultException *)pExceptionObject;
  }
  ppStruct = 0;
  Reference = CryptXmlGetReference(a2, (const CRYPT_XML_REFERENCE **)&ppStruct);
  if ( Reference < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Reference, v10, v11, v12);
  return std::vector<unsigned char>::assign<unsigned char *>(
           a3,
           ppStruct->DigestValue.pbData,
           &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
}

```

## disassembly

```asm
0x1800c2198  mov     [rsp+arg_0], rbx
0x1800c219d  push    rdi
0x1800c219e  sub     rsp, 110h
0x1800c21a5  mov     rax, cs:__security_cookie
0x1800c21ac  xor     rax, rsp
0x1800c21af  mov     [rsp+118h+var_18], rax
0x1800c21b7  mov     rbx, rdx
0x1800c21ba  xor     eax, eax
0x1800c21bc  mov     rcx, rbx; hCryptXml
0x1800c21bf  mov     qword ptr [rsp+118h+pStatus.cbSize], rax
0x1800c21c4  lea     rdx, [rsp+118h+pStatus]; pStatus
0x1800c21c9  mov     [rsp+118h+pStatus.dwInfoStatus], eax
0x1800c21cd  mov     rdi, r8
0x1800c21d0  call    cs:__imp_CryptXmlGetStatus
0x1800c21d6  test    eax, eax
0x1800c21d8  jns     short loc_1800C21E2
0x1800c21da  mov     ecx, eax; this
0x1800c21dc  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c21e2  test    byte ptr [rsp+118h+pStatus.dwInfoStatus], 8
0x1800c21e7  jz      short loc_1800C224C
0x1800c21e9  test    byte ptr [rsp+118h+pStatus.dwErrorStatus], 2
0x1800c21ee  jnz     short loc_1800C224C
0x1800c21f0  lea     rdx, [rsp+118h+ppStruct]; ppStruct
0x1800c21f5  mov     [rsp+118h+ppStruct], 0
0x1800c21fe  mov     rcx, rbx; hCryptXml
0x1800c2201  call    cs:__imp_CryptXmlGetReference
0x1800c2207  test    eax, eax
0x1800c2209  jns     short loc_1800C2213
0x1800c220b  mov     ecx, eax; this
0x1800c220d  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c2213  mov     rax, [rsp+118h+ppStruct]
0x1800c2218  mov     rcx, rdi
0x1800c221b  mov     rdx, [rax+50h]
0x1800c221f  mov     r8d, [rax+48h]
0x1800c2223  add     r8, rdx
0x1800c2226  call    ??$assign@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *>(uchar *,uchar *)
0x1800c222b  mov     rcx, [rsp+118h+var_18]
0x1800c2233  xor     rcx, rsp; StackCookie
0x1800c2236  call    __security_check_cookie
0x1800c223b  mov     rbx, [rsp+118h+arg_0]
0x1800c2243  add     rsp, 110h
0x1800c224a  pop     rdi
0x1800c224b  retn
0x1800c224c  lea     rax, aCannotGetDiges; "Cannot get digest value for a signed re"...
0x1800c2253  mov     [rsp+118h+var_E8], rax; struct win_musl::TStringEllipseBase *
0x1800c2258  lea     r9, word_180139126
0x1800c225f  mov     [rsp+118h+var_F0], 8051001Ah; unsigned int
0x1800c2267  lea     r8, aNoFilename; "(no filename)"
0x1800c226e  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800c2273  mov     [rsp+118h+var_F8], 65Fh; unsigned int
0x1800c227b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c2280  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c2287  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800c228c  call    _CxxThrowException_0
```
