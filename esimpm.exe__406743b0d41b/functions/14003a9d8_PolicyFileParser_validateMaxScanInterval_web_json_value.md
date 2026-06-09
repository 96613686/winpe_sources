# PolicyFileParser::validateMaxScanInterval(web::json::value)

- ea: `0x14003a9d8`
- end: `0x14003ab98`
- name: `?validateMaxScanInterval@PolicyFileParser@@YAXVvalue@json@web@@@Z`
- size: `448`
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
- `0x140037c40`
- `0x140037cdc`
- `0x1400384a0`
- `0x14003a9d8`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall PolicyFileParser::validateMaxScanInterval(_QWORD *a1)
{
  char v2; // bl
  __int64 result; // rax
  const struct web::json::value *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD v7[3]; // [rsp+28h] [rbp-61h] BYREF
  _OWORD v8[2]; // [rsp+40h] [rbp-49h] BYREF
  _OWORD v9[2]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE Src[32]; // [rsp+B8h] [rbp+2Fh] BYREF

  v7[1] = a1;
  memset(v8, 0, sizeof(v8));
  std::wstring::_Construct<1,unsigned short const *>(v8, L"maxRescanIntervalInSeconds");
  v2 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*a1 + 8LL))(*a1, v8);
  result = std::wstring::_Tidy_deallocate(v8);
  if ( v2 )
  {
    memset(v9, 0, sizeof(v9));
    std::wstring::_Construct<1,unsigned short const *>(v9, L"maxRescanIntervalInSeconds");
    v4 = (const struct web::json::value *)web::json::value::at(a1, v9);
    web::json::value::value((web::json::value *)v7, v4);
    std::wstring::_Tidy_deallocate(v9);
    if ( !web::json::value::is_integer((web::json::value *)v7) )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" does not have type Integer";
      *((_QWORD *)&v8[0] + 1) = 37;
      v6 = std::format<unsigned short const (&)[27]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v6);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    result = web::json::value::as_integer((web::json::value *)v7);
    if ( (int)result < 0 )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" requires a minimum value of {}";
      *((_QWORD *)&v8[0] + 1) = 41;
      v5 = std::format<unsigned short const (&)[27],int>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v5);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    if ( v7[0] )
      result = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v7[0] + 192LL))(v7[0], 1);
  }
  if ( *a1 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 192LL))(*a1, 1);
  return result;
}

```

## disassembly

```asm
0x14003a9d8  mov     [rsp-8+arg_8], rbx
0x14003a9dd  mov     [rsp-8+arg_10], rdi
0x14003a9e2  push    rbp
0x14003a9e3  lea     rbp, [rsp-57h]
0x14003a9e8  sub     rsp, 0E0h
0x14003a9ef  mov     rax, cs:__security_cookie
0x14003a9f6  xor     rax, rsp
0x14003a9f9  mov     [rbp+57h+var_8], rax
0x14003a9fd  mov     rdi, rcx
0x14003aa00  mov     [rbp+57h+var_B0], rcx
0x14003aa04  xorps   xmm0, xmm0
0x14003aa07  movups  [rbp+57h+var_A0], xmm0
0x14003aa0b  xorps   xmm1, xmm1
0x14003aa0e  movdqu  [rbp+57h+var_90], xmm1
0x14003aa13  mov     r8d, 1Ah
0x14003aa19  lea     rdx, aMaxrescaninter; "maxRescanIntervalInSeconds"
0x14003aa20  lea     rcx, [rbp+57h+var_A0]
0x14003aa24  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003aa29  nop
0x14003aa2a  mov     rcx, [rdi]
0x14003aa2d  mov     rax, [rcx]
0x14003aa30  lea     rdx, [rbp+57h+var_A0]
0x14003aa34  mov     rax, [rax+8]
0x14003aa38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aa3d  mov     bl, al
0x14003aa3f  lea     rcx, [rbp+57h+var_A0]
0x14003aa43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003aa48  test    bl, bl
0x14003aa4a  jz      loc_14003AAD4
0x14003aa50  xorps   xmm0, xmm0
0x14003aa53  movups  [rbp+57h+var_80], xmm0
0x14003aa57  xorps   xmm1, xmm1
0x14003aa5a  movdqu  [rbp+57h+var_70], xmm1
0x14003aa5f  mov     r8d, 1Ah
0x14003aa65  lea     rdx, aMaxrescaninter; "maxRescanIntervalInSeconds"
0x14003aa6c  lea     rcx, [rbp+57h+var_80]
0x14003aa70  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003aa75  nop
0x14003aa76  lea     rdx, [rbp+57h+var_80]
0x14003aa7a  mov     rcx, rdi
0x14003aa7d  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003aa82  mov     rdx, rax; struct web::json::value *
0x14003aa85  lea     rcx, [rbp+57h+var_B8]; this
0x14003aa89  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003aa8e  nop
0x14003aa8f  lea     rcx, [rbp+57h+var_80]
0x14003aa93  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003aa98  lea     rcx, [rbp+57h+var_B8]; this
0x14003aa9c  call    ?is_integer@value@json@web@@QEBA_NXZ; web::json::value::is_integer(void)
0x14003aaa1  test    al, al
0x14003aaa3  jz      loc_14003AB5A
0x14003aaa9  lea     rcx, [rbp+57h+var_B8]; this
0x14003aaad  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x14003aab2  test    eax, eax
0x14003aab4  js      short loc_14003AB11
0x14003aab6  mov     rcx, [rbp+57h+var_B8]
0x14003aaba  test    rcx, rcx
0x14003aabd  jz      short loc_14003AAD4
0x14003aabf  mov     rax, [rcx]
0x14003aac2  mov     edx, 1
0x14003aac7  mov     rax, [rax+0C0h]
0x14003aace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aad3  nop
0x14003aad4  mov     rcx, [rdi]
0x14003aad7  test    rcx, rcx
0x14003aada  jz      short loc_14003AAF0
0x14003aadc  mov     rax, [rcx]
0x14003aadf  mov     edx, 1
0x14003aae4  mov     rax, [rax+0C0h]
0x14003aaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aaf0  mov     rcx, [rbp+57h+var_8]
0x14003aaf4  xor     rcx, rsp; StackCookie
0x14003aaf7  call    __security_check_cookie
0x14003aafc  lea     r11, [rsp+0E0h+var_s0]
0x14003ab04  mov     rbx, [r11+18h]
0x14003ab08  mov     rdi, [r11+20h]
0x14003ab0c  mov     rsp, r11
0x14003ab0f  pop     rbp
0x14003ab10  retn
0x14003ab11  mov     [rbp+57h+var_C0], 0
0x14003ab18  lea     rax, aFieldRequiresA; "Field \"{}\" requires a minimum value o"...
0x14003ab1f  mov     qword ptr [rbp+57h+var_A0], rax
0x14003ab23  mov     qword ptr [rbp+57h+var_A0+8], 29h ; ')'
0x14003ab2b  lea     r9, [rbp+57h+var_C0]
0x14003ab2f  lea     rdx, [rbp+57h+var_A0]
0x14003ab33  lea     rcx, [rbp+57h+Src]; Src
0x14003ab37  call    ??$format@AEAY0BL@$$CBGH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0BL@$$CBGH@0@AEAY0BL@$$CBG$$QEAH@Z; std::format<ushort const (&)[27],int>(std::basic_format_string<ushort,ushort const (&)[27],int>,ushort const (&)[27],int &&)
0x14003ab3c  nop
0x14003ab3d  mov     rdx, rax
0x14003ab40  lea     rcx, [rbp+57h+pExceptionObject]
0x14003ab44  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003ab49  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003ab50  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003ab54  call    _CxxThrowException_0
0x14003ab5a  lea     rax, aFieldDoesNotHa_2; "Field \"{}\" does not have type Integer"
0x14003ab61  mov     qword ptr [rbp+57h+var_A0], rax
0x14003ab65  mov     qword ptr [rbp+57h+var_A0+8], 25h ; '%'
0x14003ab6d  lea     rdx, [rbp+57h+var_A0]
0x14003ab71  lea     rcx, [rbp+57h+Src]; Src
0x14003ab75  call    ??$format@AEAY0BL@$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0BL@$$CBG@0@AEAY0BL@$$CBG@Z; std::format<ushort const (&)[27]>(std::basic_format_string<ushort,ushort const (&)[27]>,ushort const (&)[27])
0x14003ab7a  nop
0x14003ab7b  mov     rdx, rax
0x14003ab7e  lea     rcx, [rbp+57h+pExceptionObject]
0x14003ab82  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003ab87  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003ab8e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003ab92  call    _CxxThrowException_0
```
