# WcmCommon::Convert::BinaryToEncodedString(unsigned __int64,uchar const * const,WcmCommon::Convert::Encoding)

- ea: `0x18004a9a8`
- end: `0x18004ab19`
- name: `?BinaryToEncodedString@Convert@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBEW4Encoding@12@@Z`
- size: `369`
- prototype: `std::wstring *__fastcall(std::wstring *result, const unsigned __int64 length, const unsigned __int8 *const buffer, const WcmCommon::Convert::Encoding length)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180026814`

## callees

- `0x180002790`
- `0x18000af58`
- `0x18000b0a0`
- `0x180011844`
- `0x180011cfc`
- `0x180012504`
- `0x180024c48`
- `0x18004a9a8`
- `0x18004ac90`
- `0x18004acb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aab2`
- `CRYPT32!CryptBinaryToStringW` at `0x18004aa35`
- `CRYPT32!CryptBinaryToStringW` at `0x18004aaa8`
- `CRYPT32!CryptBinaryToStringW` at `0x18004aa35`
- `CRYPT32!CryptBinaryToStringW` at `0x18004aaa8`

## string_xrefs

- `0x18004a9f8`: `onecoreuap\net\wcm\common\lib\wcm_convert.cpp`
- `0x18004aa5c`: `onecoreuap\net\wcm\common\lib\wcm_convert.cpp`
- `0x18004aacf`: `onecoreuap\net\wcm\common\lib\wcm_convert.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::wstring *__fastcall WcmCommon::Convert::BinaryToEncodedString(
        std::wstring *result,
        const unsigned __int64 length,
        const BYTE *buffer,
        const WcmCommon::Convert::Encoding a4)
{
  DWORD v5; // edi
  DWORD v7; // esi
  DWORD v8; // edx
  signed int LastError; // eax
  wchar_t v10; // r8
  WCHAR *v11; // rax
  signed int v12; // eax
  std::wstring *numCharsIncludingTerminator; // [rsp+38h] [rbp-50h] BYREF
  std::wstring str; // [rsp+40h] [rbp-48h] BYREF
  void *retaddr; // [rsp+88h] [rbp+0h]

  v5 = length;
  numCharsIncludingTerminator = result;
  if ( length )
  {
    if ( length > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Win32(retaddr, 0x3Du, "onecoreuap\\net\\wcm\\common\\lib\\wcm_convert.cpp", 0x5B6u);
    v7 = EncodingToFlags(Hex) | 0x40000000;
    LODWORD(numCharsIncludingTerminator) = 0;
    if ( !CryptBinaryToStringW(buffer, v8, v7, 0, (DWORD *)&numCharsIncludingTerminator) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x47u, "onecoreuap\\net\\wcm\\common\\lib\\wcm_convert.cpp", LastError);
    }
    std::wstring::wstring(&str);
    std::wstring::resize(&str, (unsigned int)((_DWORD)numCharsIncludingTerminator - 1), v10);
    v11 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&str._Mypair._Myval2);
    if ( !CryptBinaryToStringW(buffer, v5, v7, v11, (DWORD *)&numCharsIncludingTerminator) )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(retaddr, 0x50u, "onecoreuap\\net\\wcm\\common\\lib\\wcm_convert.cpp", v12);
    }
    std::wstring::wstring(result, &str);
    std::wstring::_Tidy_deallocate(&str);
  }
  else
  {
    std::wstring::wstring(result);
  }
  return result;
}

```

## disassembly

```asm
0x18004a9a8  mov     [rsp+arg_18], rbx
0x18004a9ad  push    rbp
0x18004a9ae  push    rsi
0x18004a9af  push    rdi
0x18004a9b0  sub     rsp, 70h
0x18004a9b4  mov     rax, cs:__security_cookie
0x18004a9bb  xor     rax, rsp
0x18004a9be  mov     [rsp+88h+var_28], rax
0x18004a9c3  mov     rbp, buffer
0x18004a9c6  mov     rdi, length
0x18004a9c9  mov     rbx, rcx
0x18004a9cc  mov     [rsp+88h+numCharsIncludingTerminator], rcx
0x18004a9d1  test    length, length
0x18004a9d4  jnz     short loc_18004A9E0
0x18004a9d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004a9db  jmp     loc_18004AAF9
0x18004a9e0  mov     eax, 0FFFFFFFFh
0x18004a9e5  cmp     rdi, rax
0x18004a9e8  jbe     short loc_18004AA0A
0x18004a9ea  mov     rcx, [rsp+88h]; callerReturnAddress
0x18004a9f2  mov     r9d, 5B6h; err
0x18004a9f8  lea     buffer, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004a9ff  mov     edx, 3Dh ; '='; lineNumber
0x18004aa04  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004aa0a  mov     ecx, 2; encoding
0x18004aa0f  call    EncodingToFlags
0x18004aa14  mov     esi, eax
0x18004aa16  bts     esi, 1Eh
0x18004aa1a  mov     dword ptr [rsp+88h+numCharsIncludingTerminator], 0
0x18004aa22  lea     rax, [rsp+88h+numCharsIncludingTerminator]
0x18004aa27  mov     [rsp+88h+pcchString], rax; pcchString
0x18004aa2c  xor     r9d, r9d; pszString
0x18004aa2f  mov     r8d, esi; dwFlags
0x18004aa32  mov     rcx, rbp; pbBinary
0x18004aa35  call    cs:__imp_CryptBinaryToStringW
0x18004aa3b  test    eax, eax
0x18004aa3d  jnz     short loc_18004AA6E
0x18004aa3f  call    cs:__imp_GetLastError
0x18004aa45  test    eax, eax
0x18004aa47  jle     short loc_18004AA51
0x18004aa49  movzx   eax, ax
0x18004aa4c  or      eax, 80070000h
0x18004aa51  mov     rcx, [rsp+88h]; callerReturnAddress
0x18004aa59  mov     r9d, eax; hr
0x18004aa5c  lea     buffer, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004aa63  mov     edx, 47h ; 'G'; lineNumber
0x18004aa68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004aa6e  lea     rcx, [rsp+88h+str]; this
0x18004aa73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004aa78  nop
0x18004aa79  mov     edx, dword ptr [rsp+88h+numCharsIncludingTerminator]
0x18004aa7d  dec     edx; _New_size
0x18004aa7f  lea     rcx, [rsp+88h+str]; this
0x18004aa84  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004aa89  lea     rcx, [rsp+88h+str]; this
0x18004aa8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004aa93  mov     r9, rax; pszString
0x18004aa96  lea     rax, [rsp+88h+numCharsIncludingTerminator]
0x18004aa9b  mov     [rsp+88h+pcchString], rax; pcchString
0x18004aaa0  mov     r8d, esi; dwFlags
0x18004aaa3  mov     edx, edi; cbBinary
0x18004aaa5  mov     rcx, rbp; pbBinary
0x18004aaa8  call    cs:__imp_CryptBinaryToStringW
0x18004aaae  test    eax, eax
0x18004aab0  jnz     short loc_18004AAE1
0x18004aab2  call    cs:__imp_GetLastError
0x18004aab8  test    eax, eax
0x18004aaba  jle     short loc_18004AAC4
0x18004aabc  movzx   eax, ax
0x18004aabf  or      eax, 80070000h
0x18004aac4  mov     rcx, [rsp+88h]; callerReturnAddress
0x18004aacc  mov     r9d, eax; hr
0x18004aacf  lea     buffer, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\common\\lib\\wcm_"...
0x18004aad6  mov     edx, 50h ; 'P'; lineNumber
0x18004aadb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004aae1  lea     length, [rsp+88h+str]; _Right
0x18004aae6  mov     rcx, rbx; this
0x18004aae9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18004aaee  nop
0x18004aaef  lea     rcx, [rsp+88h+str]; this
0x18004aaf4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004aaf9  mov     rax, rbx
0x18004aafc  mov     rcx, [rsp+88h+var_28]
0x18004ab01  xor     rcx, rsp; StackCookie
0x18004ab04  call    __security_check_cookie
0x18004ab09  mov     rbx, [rsp+88h+arg_18]
0x18004ab11  add     rsp, 70h
0x18004ab15  pop     rdi
0x18004ab16  pop     rsi
0x18004ab17  pop     rbp
0x18004ab18  retn
```
