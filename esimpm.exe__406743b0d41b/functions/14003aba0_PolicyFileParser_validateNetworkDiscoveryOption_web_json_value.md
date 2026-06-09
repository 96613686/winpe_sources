# PolicyFileParser::validateNetworkDiscoveryOption(web::json::value)

- ea: `0x14003aba0`
- end: `0x14003adbb`
- name: `?validateNetworkDiscoveryOption@PolicyFileParser@@YAXVvalue@json@web@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14002595c`

## callees

- `0x140002f60`
- `0x140003b64`
- `0x1400064d0`
- `0x140007590`
- `0x140007630`
- `0x140007f20`
- `0x14000dd20`
- `0x140013df8`
- `0x140037ad4`
- `0x140037b70`
- `0x1400384a0`
- `0x14003aba0`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PolicyFileParser::validateNetworkDiscoveryOption(_QWORD *a1)
{
  char v2; // bl
  __int64 result; // rax
  const struct web::json::value *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD v8[3]; // [rsp+28h] [rbp-61h] BYREF
  _OWORD v9[2]; // [rsp+40h] [rbp-49h] BYREF
  _OWORD v10[2]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE Src[32]; // [rsp+B8h] [rbp+2Fh] BYREF

  v8[1] = a1;
  memset(v9, 0, sizeof(v9));
  std::wstring::_Construct<1,unsigned short const *>(v9, L"networkDiscoveryOption");
  v2 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*a1 + 8LL))(*a1, v9);
  result = std::wstring::_Tidy_deallocate(v9);
  if ( v2 )
  {
    memset(v10, 0, sizeof(v10));
    std::wstring::_Construct<1,unsigned short const *>(v10, L"networkDiscoveryOption");
    v4 = (const struct web::json::value *)web::json::value::at(a1, v10);
    web::json::value::value((web::json::value *)v8, v4);
    std::wstring::_Tidy_deallocate(v10);
    if ( !web::json::value::is_integer((web::json::value *)v8) )
    {
      *(_QWORD *)&v9[0] = L"Field \"{}\" does not have type Integer";
      *((_QWORD *)&v9[0] + 1) = 37;
      v6 = std::format<unsigned short const (&)[23]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v6);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    if ( (int)web::json::value::as_integer((web::json::value *)v8) < 0 )
    {
      *(_QWORD *)&v9[0] = L"Field \"{}\" requires a minimum value of {}";
      *((_QWORD *)&v9[0] + 1) = 41;
      v7 = std::format<unsigned short const (&)[23],int>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v7);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    result = web::json::value::as_integer((web::json::value *)v8);
    if ( (int)result > 2 )
    {
      *(_QWORD *)&v9[0] = L"Field \"{}\" requires a maximum value of {}";
      *((_QWORD *)&v9[0] + 1) = 41;
      v5 = std::format<unsigned short const (&)[23],int>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v5);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    if ( v8[0] )
      result = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v8[0] + 192LL))(v8[0], 1);
  }
  if ( *a1 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 192LL))(*a1, 1);
  return result;
}

```

## disassembly

```asm
0x14003aba0  mov     [rsp-8+arg_8], rbx
0x14003aba5  mov     [rsp-8+arg_10], rdi
0x14003abaa  push    rbp
0x14003abab  lea     rbp, [rsp-57h]
0x14003abb0  sub     rsp, 0E0h
0x14003abb7  mov     rax, cs:__security_cookie
0x14003abbe  xor     rax, rsp
0x14003abc1  mov     [rbp+57h+var_8], rax
0x14003abc5  mov     rdi, rcx
0x14003abc8  mov     [rbp+57h+var_B0], rcx
0x14003abcc  xorps   xmm0, xmm0
0x14003abcf  movups  [rbp+57h+var_A0], xmm0
0x14003abd3  xorps   xmm1, xmm1
0x14003abd6  movdqu  [rbp+57h+var_90], xmm1
0x14003abdb  mov     r8d, 16h
0x14003abe1  lea     rdx, aNetworkdiscove; "networkDiscoveryOption"
0x14003abe8  lea     rcx, [rbp+57h+var_A0]
0x14003abec  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003abf1  nop
0x14003abf2  mov     rcx, [rdi]
0x14003abf5  mov     rax, [rcx]
0x14003abf8  lea     rdx, [rbp+57h+var_A0]
0x14003abfc  mov     rax, [rax+8]
0x14003ac00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac05  mov     bl, al
0x14003ac07  lea     rcx, [rbp+57h+var_A0]
0x14003ac0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003ac10  test    bl, bl
0x14003ac12  jz      loc_14003ACAE
0x14003ac18  xorps   xmm0, xmm0
0x14003ac1b  movups  [rbp+57h+var_80], xmm0
0x14003ac1f  xorps   xmm1, xmm1
0x14003ac22  movdqu  [rbp+57h+var_70], xmm1
0x14003ac27  mov     r8d, 16h
0x14003ac2d  lea     rdx, aNetworkdiscove; "networkDiscoveryOption"
0x14003ac34  lea     rcx, [rbp+57h+var_80]
0x14003ac38  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003ac3d  nop
0x14003ac3e  lea     rdx, [rbp+57h+var_80]
0x14003ac42  mov     rcx, rdi
0x14003ac45  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003ac4a  mov     rdx, rax; struct web::json::value *
0x14003ac4d  lea     rcx, [rbp+57h+var_B8]; this
0x14003ac51  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003ac56  nop
0x14003ac57  lea     rcx, [rbp+57h+var_80]
0x14003ac5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003ac60  lea     rcx, [rbp+57h+var_B8]; this
0x14003ac64  call    ?is_integer@value@json@web@@QEBA_NXZ; web::json::value::is_integer(void)
0x14003ac69  test    al, al
0x14003ac6b  jz      loc_14003AD34
0x14003ac71  lea     rcx, [rbp+57h+var_B8]; this
0x14003ac75  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x14003ac7a  test    eax, eax
0x14003ac7c  js      loc_14003AD72
0x14003ac82  lea     rcx, [rbp+57h+var_B8]; this
0x14003ac86  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x14003ac8b  cmp     eax, 2
0x14003ac8e  jg      short loc_14003ACEB
0x14003ac90  mov     rcx, [rbp+57h+var_B8]
0x14003ac94  test    rcx, rcx
0x14003ac97  jz      short loc_14003ACAE
0x14003ac99  mov     rax, [rcx]
0x14003ac9c  mov     edx, 1
0x14003aca1  mov     rax, [rax+0C0h]
0x14003aca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003acad  nop
0x14003acae  mov     rcx, [rdi]
0x14003acb1  test    rcx, rcx
0x14003acb4  jz      short loc_14003ACCA
0x14003acb6  mov     rax, [rcx]
0x14003acb9  mov     edx, 1
0x14003acbe  mov     rax, [rax+0C0h]
0x14003acc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003acca  mov     rcx, [rbp+57h+var_8]
0x14003acce  xor     rcx, rsp; StackCookie
0x14003acd1  call    __security_check_cookie
0x14003acd6  lea     r11, [rsp+0E0h+var_s0]
0x14003acde  mov     rbx, [r11+18h]
0x14003ace2  mov     rdi, [r11+20h]
0x14003ace6  mov     rsp, r11
0x14003ace9  pop     rbp
0x14003acea  retn
0x14003aceb  mov     [rbp+57h+var_C0], 2
0x14003acf2  lea     rax, aFieldRequiresA_0; "Field \"{}\" requires a maximum value o"...
0x14003acf9  mov     qword ptr [rbp+57h+var_A0], rax
0x14003acfd  mov     qword ptr [rbp+57h+var_A0+8], 29h ; ')'
0x14003ad05  lea     r9, [rbp+57h+var_C0]
0x14003ad09  lea     rdx, [rbp+57h+var_A0]
0x14003ad0d  lea     rcx, [rbp+57h+Src]; Src
0x14003ad11  call    ??$format@AEAY0BH@$$CBGH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0BH@$$CBGH@0@AEAY0BH@$$CBG$$QEAH@Z; std::format<ushort const (&)[23],int>(std::basic_format_string<ushort,ushort const (&)[23],int>,ushort const (&)[23],int &&)
0x14003ad16  nop
0x14003ad17  mov     rdx, rax
0x14003ad1a  lea     rcx, [rbp+57h+pExceptionObject]
0x14003ad1e  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003ad23  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003ad2a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003ad2e  call    _CxxThrowException_0
0x14003ad34  lea     rax, aFieldDoesNotHa_2; "Field \"{}\" does not have type Integer"
0x14003ad3b  mov     qword ptr [rbp+57h+var_A0], rax
0x14003ad3f  mov     qword ptr [rbp+57h+var_A0+8], 25h ; '%'
0x14003ad47  lea     rdx, [rbp+57h+var_A0]
0x14003ad4b  lea     rcx, [rbp+57h+Src]; Src
0x14003ad4f  call    ??$format@AEAY0BH@$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0BH@$$CBG@0@AEAY0BH@$$CBG@Z; std::format<ushort const (&)[23]>(std::basic_format_string<ushort,ushort const (&)[23]>,ushort const (&)[23])
0x14003ad54  nop
0x14003ad55  mov     rdx, rax
0x14003ad58  lea     rcx, [rbp+57h+pExceptionObject]
0x14003ad5c  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003ad61  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003ad68  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003ad6c  call    _CxxThrowException_0
0x14003ad72  mov     [rbp+57h+var_C0], 0
0x14003ad79  lea     rax, aFieldRequiresA; "Field \"{}\" requires a minimum value o"...
0x14003ad80  mov     qword ptr [rbp+57h+var_A0], rax
0x14003ad84  mov     qword ptr [rbp+57h+var_A0+8], 29h ; ')'
0x14003ad8c  lea     r9, [rbp+57h+var_C0]
0x14003ad90  lea     rdx, [rbp+57h+var_A0]
0x14003ad94  lea     rcx, [rbp+57h+Src]; Src
0x14003ad98  call    ??$format@AEAY0BH@$$CBGH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0BH@$$CBGH@0@AEAY0BH@$$CBG$$QEAH@Z; std::format<ushort const (&)[23],int>(std::basic_format_string<ushort,ushort const (&)[23],int>,ushort const (&)[23],int &&)
0x14003ad9d  nop
0x14003ad9e  mov     rdx, rax
0x14003ada1  lea     rcx, [rbp+57h+pExceptionObject]
0x14003ada5  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003adaa  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003adb1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003adb5  call    _CxxThrowException_0
```
