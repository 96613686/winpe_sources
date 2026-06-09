# WcmCommon::Convert::EncodedStringToBinary(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WcmCommon::Convert::Encoding)

- ea: `0x18004ab20`
- end: `0x18004ac87`
- name: `?EncodedStringToBinary@Convert@WcmCommon@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@W4Encoding@12@@Z`
- size: `359`
- prototype: `std::vector<unsigned char> *__fastcall(std::vector<unsigned char> *result, const std::wstring *str, const WcmCommon::Convert::Encoding encoding)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018efc`
- `0x18003b3d4`
- `0x180042050`

## callees

- `0x180002790`
- `0x18000b178`
- `0x180011844`
- `0x18001a0d4`
- `0x180028f98`
- `0x180028fc8`
- `0x18004ab20`
- `0x18004ac90`
- `0x18004acb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac28`
- `CRYPT32!CryptStringToBinaryW` at `0x18004ab95`
- `CRYPT32!CryptStringToBinaryW` at `0x18004ac1e`
- `CRYPT32!CryptStringToBinaryW` at `0x18004ab95`
- `CRYPT32!CryptStringToBinaryW` at `0x18004ac1e`

## string_xrefs

- `0x18004abbc`: `onecoreuap\net\wcm\common\lib\wcm_convert.cpp`
- `0x18004ac45`: `onecoreuap\net\wcm\common\lib\wcm_convert.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::vector<_GUID> *__fastcall WcmCommon::Convert::EncodedStringToBinary(
        std::vector<_GUID> *result,
        const std::wstring *str,
        WcmCommon::Convert::Encoding encoding)
{
  DWORD v5; // esi
  const WCHAR *v6; // rax
  __int64 v7; // rdx
  const std::allocator<unsigned char> *v8; // r8
  signed int LastError; // eax
  const WCHAR *v10; // rax
  signed int v11; // eax
  std::vector<_GUID> *numBytes; // [rsp+48h] [rbp-40h] BYREF
  std::vector<unsigned char> bytes; // [rsp+50h] [rbp-38h] BYREF
  void *retaddr; // [rsp+88h] [rbp+0h]

  numBytes = result;
  if ( str->_Mypair._Myval2._Mysize )
  {
    v5 = EncodingToFlags(encoding);
    LODWORD(numBytes) = 0;
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&str->_Mypair._Myval2);
    if ( !CryptStringToBinaryW(v6, *(_DWORD *)(v7 + 16), v5, 0, (DWORD *)&numBytes, 0, 0) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x22u, "onecoreuap\\net\\wcm\\common\\lib\\wcm_convert.cpp", LastError);
    }
    memset(&bytes, 0, sizeof(bytes));
    std::vector<unsigned char>::vector<unsigned char>(&bytes, (unsigned int)numBytes, v8);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&str->_Mypair._Myval2);
    if ( !CryptStringToBinaryW(
            v10,
            str->_Mypair._Myval2._Mysize,
            v5,
            bytes._Mypair._Myval2._Myfirst,
            (DWORD *)&numBytes,
            0,
            0) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x2Au, "onecoreuap\\net\\wcm\\common\\lib\\wcm_convert.cpp", v11);
    }
    std::vector<_GUID>::vector<_GUID>(result, (std::vector<_GUID> *)&bytes);
    std::vector<unsigned char>::_Tidy((std::vector<char> *)&bytes);
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
0x18004ab20  push    rbx
0x18004ab22  push    rsi
0x18004ab23  push    rdi
0x18004ab24  sub     rsp, 70h
0x18004ab28  mov     rax, cs:__security_cookie
0x18004ab2f  xor     rax, rsp
0x18004ab32  mov     [rsp+88h+var_20], rax
0x18004ab37  mov     rdi, str
0x18004ab3a  mov     rbx, rcx
0x18004ab3d  mov     [rsp+88h+numBytes], rcx
0x18004ab42  cmp     qword ptr [str+10h], 0
0x18004ab47  jnz     short loc_18004AB53
0x18004ab49  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18004ab4e  jmp     loc_18004AC6F
0x18004ab53  mov     ecx, encoding; encoding
0x18004ab56  call    EncodingToFlags
0x18004ab5b  mov     esi, eax
0x18004ab5d  mov     dword ptr [rsp+88h+numBytes], 0
0x18004ab65  mov     rcx, rdi; this
0x18004ab68  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ab6d  mov     [rsp+88h+pdwFlags], 0; pdwFlags
0x18004ab76  mov     [rsp+88h+pdwSkip], 0; pdwSkip
0x18004ab7f  lea     rcx, [rsp+88h+numBytes]
0x18004ab84  mov     [rsp+88h+pcbBinary], rcx; pcbBinary
0x18004ab89  xor     r9d, r9d; pbBinary
0x18004ab8c  mov     encoding, esi; dwFlags
0x18004ab8f  mov     edx, [str+10h]; cchString
0x18004ab92  mov     rcx, rax; pszString
0x18004ab95  call    cs:__imp_CryptStringToBinaryW
0x18004ab9b  test    eax, eax
0x18004ab9d  jnz     short loc_18004ABCE
0x18004ab9f  call    cs:__imp_GetLastError
0x18004aba5  test    eax, eax
0x18004aba7  jle     short loc_18004ABB1
0x18004aba9  movzx   eax, ax
0x18004abac  or      eax, 80070000h
0x18004abb1  mov     rcx, [rsp+88h]; callerReturnAddress
0x18004abb9  mov     r9d, eax; hr
0x18004abbc  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004abc3  mov     edx, 22h ; '"'; lineNumber
0x18004abc8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004abce  xorps   xmm0, xmm0
0x18004abd1  xor     eax, eax
0x18004abd3  movups  xmmword ptr [rsp+88h+bytes._Mypair._Myval2._Myfirst], xmm0
0x18004abd8  mov     [rsp+88h+bytes._Mypair._Myval2._Myend], rax
0x18004abdd  mov     edx, dword ptr [rsp+88h+numBytes]; _Count
0x18004abe1  lea     rcx, [rsp+88h+bytes]; this
0x18004abe6  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18004abeb  nop
0x18004abec  mov     rcx, rdi; this
0x18004abef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004abf4  mov     [rsp+88h+pdwFlags], 0; pdwFlags
0x18004abfd  mov     [rsp+88h+pdwSkip], 0; pdwSkip
0x18004ac06  lea     rcx, [rsp+88h+numBytes]
0x18004ac0b  mov     [rsp+88h+pcbBinary], rcx; pcbBinary
0x18004ac10  mov     r9, [rsp+88h+bytes._Mypair._Myval2._Myfirst]; pbBinary
0x18004ac15  mov     encoding, esi; dwFlags
0x18004ac18  mov     edx, [rdi+10h]; cchString
0x18004ac1b  mov     rcx, rax; pszString
0x18004ac1e  call    cs:__imp_CryptStringToBinaryW
0x18004ac24  test    eax, eax
0x18004ac26  jnz     short loc_18004AC57
0x18004ac28  call    cs:__imp_GetLastError
0x18004ac2e  test    eax, eax
0x18004ac30  jle     short loc_18004AC3A
0x18004ac32  movzx   eax, ax
0x18004ac35  or      eax, 80070000h
0x18004ac3a  mov     rcx, [rsp+88h]; callerReturnAddress
0x18004ac42  mov     r9d, eax; hr
0x18004ac45  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004ac4c  mov     edx, 2Ah ; '*'; lineNumber
0x18004ac51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ac57  lea     str, [rsp+88h+bytes]; _Right
0x18004ac5c  mov     rcx, rbx; this
0x18004ac5f  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<_GUID>::vector<_GUID>(std::vector<_GUID> &&)
0x18004ac64  nop
0x18004ac65  lea     rcx, [rsp+88h+bytes]; this
0x18004ac6a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004ac6f  mov     rax, rbx
0x18004ac72  mov     rcx, [rsp+88h+var_20]
0x18004ac77  xor     rcx, rsp; StackCookie
0x18004ac7a  call    __security_check_cookie
0x18004ac7f  add     rsp, 70h
0x18004ac83  pop     rdi
0x18004ac84  pop     rsi
0x18004ac85  pop     rbx
0x18004ac86  retn
```
