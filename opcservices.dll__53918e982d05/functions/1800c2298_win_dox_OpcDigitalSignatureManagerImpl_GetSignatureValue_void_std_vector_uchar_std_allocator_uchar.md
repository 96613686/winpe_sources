# win_dox::OpcDigitalSignatureManagerImpl::GetSignatureValue(void *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800c2298`
- end: `0x1800c239b`
- name: `?GetSignatureValue@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a2494`

## callees

- `0x18001568c`
- `0x18002db70`
- `0x1800c2298`
- `0x1800c2d94`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `CRYPTXML!CryptXmlGetSignature` at `0x1800c2304`
- `CRYPTXML!CryptXmlGetSignature` at `0x1800c2304`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c22d0`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c22d0`

## pseudocode

```c
__int64 __fastcall win_dox::OpcDigitalSignatureManagerImpl::GetSignatureValue(__int64 a1, void *a2, __int64 a3)
{
  HRESULT Status; // eax
  int v6; // edx
  const char *v7; // r8
  unsigned int v8; // r9d
  HRESULT Signature; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  CRYPT_XML_SIGNATURE *ppStruct; // [rsp+40h] [rbp-D8h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(a2, &pStatus);
  if ( Status < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Status, v6, v7, v8);
  if ( (pStatus.dwInfoStatus & 0x10000) == 0 || (pStatus.dwErrorStatus & 0x10000) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x682u,
      0x80510019,
      (struct win_musl::TStringEllipseBase *)L"Cannot get signature value");
    throw (SplException::THResultException *)pExceptionObject;
  }
  ppStruct = 0;
  Signature = CryptXmlGetSignature(a2, (const CRYPT_XML_SIGNATURE **)&ppStruct);
  if ( Signature < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Signature, v10, v11, v12);
  return std::vector<unsigned char>::assign<unsigned char *>(
           a3,
           ppStruct->SignatureValue.pbData,
           &ppStruct->SignatureValue.pbData[ppStruct->SignatureValue.cbData]);
}

```

## disassembly

```asm
0x1800c2298  mov     [rsp+arg_0], rbx
0x1800c229d  push    rdi
0x1800c229e  sub     rsp, 110h
0x1800c22a5  mov     rax, cs:__security_cookie
0x1800c22ac  xor     rax, rsp
0x1800c22af  mov     [rsp+118h+var_18], rax
0x1800c22b7  mov     rbx, rdx
0x1800c22ba  xor     eax, eax
0x1800c22bc  mov     rcx, rbx; hCryptXml
0x1800c22bf  mov     qword ptr [rsp+118h+pStatus.cbSize], rax
0x1800c22c4  lea     rdx, [rsp+118h+pStatus]; pStatus
0x1800c22c9  mov     [rsp+118h+pStatus.dwInfoStatus], eax
0x1800c22cd  mov     rdi, r8
0x1800c22d0  call    cs:__imp_CryptXmlGetStatus
0x1800c22d6  test    eax, eax
0x1800c22d8  jns     short loc_1800C22E2
0x1800c22da  mov     ecx, eax; this
0x1800c22dc  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c22e2  mov     eax, 10000h
0x1800c22e7  test    [rsp+118h+pStatus.dwInfoStatus], eax
0x1800c22eb  jz      short loc_1800C2355
0x1800c22ed  test    [rsp+118h+pStatus.dwErrorStatus], eax
0x1800c22f1  jnz     short loc_1800C2355
0x1800c22f3  lea     rdx, [rsp+118h+ppStruct]; ppStruct
0x1800c22f8  mov     [rsp+118h+ppStruct], 0
0x1800c2301  mov     rcx, rbx; hCryptXml
0x1800c2304  call    cs:__imp_CryptXmlGetSignature
0x1800c230a  test    eax, eax
0x1800c230c  jns     short loc_1800C2316
0x1800c230e  mov     ecx, eax; this
0x1800c2310  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c2316  mov     rax, [rsp+118h+ppStruct]
0x1800c231b  mov     rcx, rdi
0x1800c231e  mov     rdx, [rax+90h]
0x1800c2325  mov     r8d, [rax+88h]
0x1800c232c  add     r8, rdx
0x1800c232f  call    ??$assign@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *>(uchar *,uchar *)
0x1800c2334  mov     rcx, [rsp+118h+var_18]
0x1800c233c  xor     rcx, rsp; StackCookie
0x1800c233f  call    __security_check_cookie
0x1800c2344  mov     rbx, [rsp+118h+arg_0]
0x1800c234c  add     rsp, 110h
0x1800c2353  pop     rdi
0x1800c2354  retn
0x1800c2355  lea     rax, aCannotGetSigna; "Cannot get signature value"
0x1800c235c  mov     [rsp+118h+var_E8], rax; struct win_musl::TStringEllipseBase *
0x1800c2361  lea     r9, word_180139126
0x1800c2368  mov     [rsp+118h+var_F0], 80510019h; unsigned int
0x1800c2370  lea     r8, aNoFilename; "(no filename)"
0x1800c2377  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800c237c  mov     [rsp+118h+var_F8], 682h; unsigned int
0x1800c2384  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c2389  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c2390  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800c2395  call    _CxxThrowException_0
```
