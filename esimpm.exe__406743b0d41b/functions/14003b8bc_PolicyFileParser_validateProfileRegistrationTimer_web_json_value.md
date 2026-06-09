# PolicyFileParser::validateProfileRegistrationTimer(web::json::value)

- ea: `0x14003b8bc`
- end: `0x14003ba7d`
- name: `?validateProfileRegistrationTimer@PolicyFileParser@@YAXVvalue@json@web@@@Z`
- size: `449`
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
- `0x140037dac`
- `0x140037e48`
- `0x1400384a0`
- `0x14003b8bc`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall PolicyFileParser::validateProfileRegistrationTimer(_QWORD *a1)
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
  std::wstring::_Construct<1,unsigned short const *>(v8, L"profileRegistrationTimerInSeconds");
  v2 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*a1 + 8LL))(*a1, v8);
  result = std::wstring::_Tidy_deallocate(v8);
  if ( v2 )
  {
    memset(v9, 0, sizeof(v9));
    std::wstring::_Construct<1,unsigned short const *>(v9, L"profileRegistrationTimerInSeconds");
    v4 = (const struct web::json::value *)web::json::value::at(a1, v9);
    web::json::value::value((web::json::value *)v7, v4);
    std::wstring::_Tidy_deallocate(v9);
    if ( !web::json::value::is_integer((web::json::value *)v7) )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" does not have type Integer";
      *((_QWORD *)&v8[0] + 1) = 37;
      v6 = std::format<unsigned short const (&)[34]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v6);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    result = web::json::value::as_integer((web::json::value *)v7);
    if ( (int)result < 30 )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" requires a minimum value of {}";
      *((_QWORD *)&v8[0] + 1) = 41;
      v5 = std::format<unsigned short const (&)[34],int>(Src);
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
0x14003b8bc  mov     [rsp-8+arg_8], rbx
0x14003b8c1  mov     [rsp-8+arg_10], rdi
0x14003b8c6  push    rbp
0x14003b8c7  lea     rbp, [rsp-57h]
0x14003b8cc  sub     rsp, 0E0h
0x14003b8d3  mov     rax, cs:__security_cookie
0x14003b8da  xor     rax, rsp
0x14003b8dd  mov     [rbp+57h+var_8], rax
0x14003b8e1  mov     rdi, rcx
0x14003b8e4  mov     [rbp+57h+var_B0], rcx
0x14003b8e8  xorps   xmm0, xmm0
0x14003b8eb  movups  [rbp+57h+var_A0], xmm0
0x14003b8ef  xorps   xmm1, xmm1
0x14003b8f2  movdqu  [rbp+57h+var_90], xmm1
0x14003b8f7  mov     r8d, 21h ; '!'
0x14003b8fd  lea     rdx, aProfileregistr; "profileRegistrationTimerInSeconds"
0x14003b904  lea     rcx, [rbp+57h+var_A0]
0x14003b908  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b90d  nop
0x14003b90e  mov     rcx, [rdi]
0x14003b911  mov     rax, [rcx]
0x14003b914  lea     rdx, [rbp+57h+var_A0]
0x14003b918  mov     rax, [rax+8]
0x14003b91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b921  mov     bl, al
0x14003b923  lea     rcx, [rbp+57h+var_A0]
0x14003b927  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b92c  test    bl, bl
0x14003b92e  jz      loc_14003B9B9
0x14003b934  xorps   xmm0, xmm0
0x14003b937  movups  [rbp+57h+var_80], xmm0
0x14003b93b  xorps   xmm1, xmm1
0x14003b93e  movdqu  [rbp+57h+var_70], xmm1
0x14003b943  mov     r8d, 21h ; '!'
0x14003b949  lea     rdx, aProfileregistr; "profileRegistrationTimerInSeconds"
0x14003b950  lea     rcx, [rbp+57h+var_80]
0x14003b954  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b959  nop
0x14003b95a  lea     rdx, [rbp+57h+var_80]
0x14003b95e  mov     rcx, rdi
0x14003b961  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003b966  mov     rdx, rax; struct web::json::value *
0x14003b969  lea     rcx, [rbp+57h+var_B8]; this
0x14003b96d  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003b972  nop
0x14003b973  lea     rcx, [rbp+57h+var_80]
0x14003b977  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b97c  lea     rcx, [rbp+57h+var_B8]; this
0x14003b980  call    ?is_integer@value@json@web@@QEBA_NXZ; web::json::value::is_integer(void)
0x14003b985  test    al, al
0x14003b987  jz      loc_14003BA3F
0x14003b98d  lea     rcx, [rbp+57h+var_B8]; this
0x14003b991  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x14003b996  cmp     eax, 1Eh
0x14003b999  jl      short loc_14003B9F6
0x14003b99b  mov     rcx, [rbp+57h+var_B8]
0x14003b99f  test    rcx, rcx
0x14003b9a2  jz      short loc_14003B9B9
0x14003b9a4  mov     rax, [rcx]
0x14003b9a7  mov     edx, 1
0x14003b9ac  mov     rax, [rax+0C0h]
0x14003b9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b9b8  nop
0x14003b9b9  mov     rcx, [rdi]
0x14003b9bc  test    rcx, rcx
0x14003b9bf  jz      short loc_14003B9D5
0x14003b9c1  mov     rax, [rcx]
0x14003b9c4  mov     edx, 1
0x14003b9c9  mov     rax, [rax+0C0h]
0x14003b9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b9d5  mov     rcx, [rbp+57h+var_8]
0x14003b9d9  xor     rcx, rsp; StackCookie
0x14003b9dc  call    __security_check_cookie
0x14003b9e1  lea     r11, [rsp+0E0h+var_s0]
0x14003b9e9  mov     rbx, [r11+18h]
0x14003b9ed  mov     rdi, [r11+20h]
0x14003b9f1  mov     rsp, r11
0x14003b9f4  pop     rbp
0x14003b9f5  retn
0x14003b9f6  mov     [rbp+57h+var_C0], 1Eh
0x14003b9fd  lea     rax, aFieldRequiresA; "Field \"{}\" requires a minimum value o"...
0x14003ba04  mov     qword ptr [rbp+57h+var_A0], rax
0x14003ba08  mov     qword ptr [rbp+57h+var_A0+8], 29h ; ')'
0x14003ba10  lea     r9, [rbp+57h+var_C0]
0x14003ba14  lea     rdx, [rbp+57h+var_A0]
0x14003ba18  lea     rcx, [rbp+57h+Src]; Src
0x14003ba1c  call    ??$format@AEAY0CC@$$CBGH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0CC@$$CBGH@0@AEAY0CC@$$CBG$$QEAH@Z; std::format<ushort const (&)[34],int>(std::basic_format_string<ushort,ushort const (&)[34],int>,ushort const (&)[34],int &&)
0x14003ba21  nop
0x14003ba22  mov     rdx, rax
0x14003ba25  lea     rcx, [rbp+57h+pExceptionObject]
0x14003ba29  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003ba2e  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003ba35  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003ba39  call    _CxxThrowException_0
0x14003ba3f  lea     rax, aFieldDoesNotHa_2; "Field \"{}\" does not have type Integer"
0x14003ba46  mov     qword ptr [rbp+57h+var_A0], rax
0x14003ba4a  mov     qword ptr [rbp+57h+var_A0+8], 25h ; '%'
0x14003ba52  lea     rdx, [rbp+57h+var_A0]
0x14003ba56  lea     rcx, [rbp+57h+Src]; Src
0x14003ba5a  call    ??$format@AEAY0CC@$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0CC@$$CBG@0@AEAY0CC@$$CBG@Z; std::format<ushort const (&)[34]>(std::basic_format_string<ushort,ushort const (&)[34]>,ushort const (&)[34])
0x14003ba5f  nop
0x14003ba60  mov     rdx, rax
0x14003ba63  lea     rcx, [rbp+57h+pExceptionObject]
0x14003ba67  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003ba6c  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003ba73  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003ba77  call    _CxxThrowException_0
```
