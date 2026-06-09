# win_dox::GetC14NTransformEngine(void)

- ea: `0x1800a8404`
- end: `0x1800a8505`
- name: `?GetC14NTransformEngine@win_dox@@YAP6AJPEBU_CRYPT_XML_ALGORITHM@@PEAU_CRYPT_XML_DATA_PROVIDER@@1@ZXZ`
- size: `257`
- prototype: `int (*__fastcall(win_dox *__hidden this))(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800a686c`

## callees

- `0x18001568c`
- `0x18002db70`
- `0x1800a8404`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `CRYPTXML!CryptXmlGetTransforms` at `0x1800a8459`
- `CRYPTXML!CryptXmlGetTransforms` at `0x1800a8459`

## string_xrefs

- `0x1800a8483`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`

## pseudocode

```c
int (*__fastcall win_dox::GetC14NTransformEngine(
        win_dox *this))(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *)
{
  HRESULT Transforms; // eax
  int v3; // edx
  const char *v4; // r8
  unsigned int v5; // r9d
  __int64 i; // rcx
  PCRYPT_XML_TRANSFORM_INFO v7; // r9
  LPCWSTR wszAlgorithm; // rax
  char *v9; // r10
  int v10; // r8d
  int v11; // edx
  CRYPT_XML_TRANSFORM_CHAIN_CONFIG *ppConfig; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B8h] BYREF

  if ( !qword_1801C5268 )
  {
    ppConfig = 0;
    Transforms = CryptXmlGetTransforms((const CRYPT_XML_TRANSFORM_CHAIN_CONFIG **)&ppConfig);
    if ( Transforms < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)Transforms, v3, v4, v5);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= ppConfig->cTransformInfo )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x164u,
          0x8000FFFF,
          (struct win_musl::TStringEllipseBase *)L"Cannot find C14N transform engine.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v7 = ppConfig->rgpTransformInfo[i];
      wszAlgorithm = v7->wszAlgorithm;
      v9 = (char *)((char *)L"http://www.w3.org/TR/2001/REC-xml-c14n-20010315" - (char *)wszAlgorithm);
      do
      {
        v10 = *(unsigned __int16 *)&v9[(_QWORD)wszAlgorithm];
        v11 = *wszAlgorithm - v10;
        if ( v11 )
          break;
        ++wszAlgorithm;
      }
      while ( v10 );
      if ( !v11 )
        break;
    }
    qword_1801C5268 = (__int64)v7->pfnCreateTransform;
  }
  return (int (*)(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *))qword_1801C5268;
}

```

## disassembly

```asm
0x1800a8404  push    rbx
0x1800a8406  sub     rsp, 100h
0x1800a840d  mov     rax, cs:__security_cookie
0x1800a8414  xor     rax, rsp
0x1800a8417  mov     [rsp+108h+var_18], rax
0x1800a841f  mov     rax, cs:qword_1801C5268
0x1800a8426  test    rax, rax
0x1800a8429  jz      short loc_1800A844B
0x1800a842b  mov     rax, cs:qword_1801C5268
0x1800a8432  mov     rcx, [rsp+108h+var_18]
0x1800a843a  xor     rcx, rsp; StackCookie
0x1800a843d  call    __security_check_cookie
0x1800a8442  add     rsp, 100h
0x1800a8449  pop     rbx
0x1800a844a  retn
0x1800a844b  lea     rcx, [rsp+108h+ppConfig]; ppConfig
0x1800a8450  mov     [rsp+108h+ppConfig], 0
0x1800a8459  call    cs:__imp_CryptXmlGetTransforms
0x1800a845f  test    eax, eax
0x1800a8461  jns     short loc_1800A846B
0x1800a8463  mov     ecx, eax; this
0x1800a8465  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a846b  mov     rax, [rsp+108h+ppConfig]
0x1800a8470  xor     ecx, ecx
0x1800a8472  mov     rbx, [rax+8]
0x1800a8476  mov     r11d, [rax+4]
0x1800a847a  cmp     ecx, r11d
0x1800a847d  jnb     short loc_1800A84BF
0x1800a847f  mov     r9, [rbx+rcx*8]
0x1800a8483  lea     r10, ?gc_C14NTransform@Value@DigitalSignatures@win_musl@@3QB_WB; "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x1800a848a  mov     rax, [r9+8]
0x1800a848e  sub     r10, rax
0x1800a8491  movzx   edx, word ptr [rax]
0x1800a8494  movzx   r8d, word ptr [rax+r10]
0x1800a8499  sub     edx, r8d
0x1800a849c  jnz     short loc_1800A84A7
0x1800a849e  add     rax, 2
0x1800a84a2  test    r8d, r8d
0x1800a84a5  jnz     short loc_1800A8491
0x1800a84a7  test    edx, edx
0x1800a84a9  jz      short loc_1800A84AF
0x1800a84ab  inc     ecx
0x1800a84ad  jmp     short loc_1800A847A
0x1800a84af  mov     rax, [r9+18h]
0x1800a84b3  mov     cs:qword_1801C5268, rax
0x1800a84ba  jmp     loc_1800A842B
0x1800a84bf  lea     rax, aCannotFindC14n; "Cannot find C14N transform engine."
0x1800a84c6  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800a84cb  lea     r9, word_180139126
0x1800a84d2  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x1800a84da  lea     r8, aNoFilename; "(no filename)"
0x1800a84e1  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800a84e6  mov     [rsp+108h+var_E8], 164h; unsigned int
0x1800a84ee  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a84f3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a84fa  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800a84ff  call    _CxxThrowException_0
```
