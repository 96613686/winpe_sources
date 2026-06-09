# PolicyFileParser::validateScreenOffDuration(web::json::value)

- ea: `0x14003ba84`
- end: `0x14003bc44`
- name: `?validateScreenOffDuration@PolicyFileParser@@YAXVvalue@json@web@@@Z`
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
- `0x140038084`
- `0x140038120`
- `0x1400384a0`
- `0x14003ba84`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall PolicyFileParser::validateScreenOffDuration(_QWORD *a1)
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
  std::wstring::_Construct<1,unsigned short const *>(v8, L"screenOffDurationToTriggerNetworkDiscoveryInMinutes");
  v2 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*a1 + 8LL))(*a1, v8);
  result = std::wstring::_Tidy_deallocate(v8);
  if ( v2 )
  {
    memset(v9, 0, sizeof(v9));
    std::wstring::_Construct<1,unsigned short const *>(v9, L"screenOffDurationToTriggerNetworkDiscoveryInMinutes");
    v4 = (const struct web::json::value *)web::json::value::at(a1, v9);
    web::json::value::value((web::json::value *)v7, v4);
    std::wstring::_Tidy_deallocate(v9);
    if ( !web::json::value::is_integer((web::json::value *)v7) )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" does not have type Integer";
      *((_QWORD *)&v8[0] + 1) = 37;
      v6 = std::format<unsigned short const (&)[52]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v6);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    result = web::json::value::as_integer((web::json::value *)v7);
    if ( (int)result < 0 )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" requires a minimum value of {}";
      *((_QWORD *)&v8[0] + 1) = 41;
      v5 = std::format<unsigned short const (&)[52],int>(Src);
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
0x14003ba84  mov     [rsp-8+arg_8], rbx
0x14003ba89  mov     [rsp-8+arg_10], rdi
0x14003ba8e  push    rbp
0x14003ba8f  lea     rbp, [rsp-57h]
0x14003ba94  sub     rsp, 0E0h
0x14003ba9b  mov     rax, cs:__security_cookie
0x14003baa2  xor     rax, rsp
0x14003baa5  mov     [rbp+57h+var_8], rax
0x14003baa9  mov     rdi, rcx
0x14003baac  mov     [rbp+57h+var_B0], rcx
0x14003bab0  xorps   xmm0, xmm0
0x14003bab3  movups  [rbp+57h+var_A0], xmm0
0x14003bab7  xorps   xmm1, xmm1
0x14003baba  movdqu  [rbp+57h+var_90], xmm1
0x14003babf  mov     r8d, 33h ; '3'
0x14003bac5  lea     rdx, aScreenoffdurat; "screenOffDurationToTriggerNetworkDiscov"...
0x14003bacc  lea     rcx, [rbp+57h+var_A0]
0x14003bad0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003bad5  nop
0x14003bad6  mov     rcx, [rdi]
0x14003bad9  mov     rax, [rcx]
0x14003badc  lea     rdx, [rbp+57h+var_A0]
0x14003bae0  mov     rax, [rax+8]
0x14003bae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bae9  mov     bl, al
0x14003baeb  lea     rcx, [rbp+57h+var_A0]
0x14003baef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003baf4  test    bl, bl
0x14003baf6  jz      loc_14003BB80
0x14003bafc  xorps   xmm0, xmm0
0x14003baff  movups  [rbp+57h+var_80], xmm0
0x14003bb03  xorps   xmm1, xmm1
0x14003bb06  movdqu  [rbp+57h+var_70], xmm1
0x14003bb0b  mov     r8d, 33h ; '3'
0x14003bb11  lea     rdx, aScreenoffdurat; "screenOffDurationToTriggerNetworkDiscov"...
0x14003bb18  lea     rcx, [rbp+57h+var_80]
0x14003bb1c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003bb21  nop
0x14003bb22  lea     rdx, [rbp+57h+var_80]
0x14003bb26  mov     rcx, rdi
0x14003bb29  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003bb2e  mov     rdx, rax; struct web::json::value *
0x14003bb31  lea     rcx, [rbp+57h+var_B8]; this
0x14003bb35  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003bb3a  nop
0x14003bb3b  lea     rcx, [rbp+57h+var_80]
0x14003bb3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003bb44  lea     rcx, [rbp+57h+var_B8]; this
0x14003bb48  call    ?is_integer@value@json@web@@QEBA_NXZ; web::json::value::is_integer(void)
0x14003bb4d  test    al, al
0x14003bb4f  jz      loc_14003BC06
0x14003bb55  lea     rcx, [rbp+57h+var_B8]; this
0x14003bb59  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x14003bb5e  test    eax, eax
0x14003bb60  js      short loc_14003BBBD
0x14003bb62  mov     rcx, [rbp+57h+var_B8]
0x14003bb66  test    rcx, rcx
0x14003bb69  jz      short loc_14003BB80
0x14003bb6b  mov     rax, [rcx]
0x14003bb6e  mov     edx, 1
0x14003bb73  mov     rax, [rax+0C0h]
0x14003bb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bb7f  nop
0x14003bb80  mov     rcx, [rdi]
0x14003bb83  test    rcx, rcx
0x14003bb86  jz      short loc_14003BB9C
0x14003bb88  mov     rax, [rcx]
0x14003bb8b  mov     edx, 1
0x14003bb90  mov     rax, [rax+0C0h]
0x14003bb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bb9c  mov     rcx, [rbp+57h+var_8]
0x14003bba0  xor     rcx, rsp; StackCookie
0x14003bba3  call    __security_check_cookie
0x14003bba8  lea     r11, [rsp+0E0h+var_s0]
0x14003bbb0  mov     rbx, [r11+18h]
0x14003bbb4  mov     rdi, [r11+20h]
0x14003bbb8  mov     rsp, r11
0x14003bbbb  pop     rbp
0x14003bbbc  retn
0x14003bbbd  mov     [rbp+57h+var_C0], 0
0x14003bbc4  lea     rax, aFieldRequiresA; "Field \"{}\" requires a minimum value o"...
0x14003bbcb  mov     qword ptr [rbp+57h+var_A0], rax
0x14003bbcf  mov     qword ptr [rbp+57h+var_A0+8], 29h ; ')'
0x14003bbd7  lea     r9, [rbp+57h+var_C0]
0x14003bbdb  lea     rdx, [rbp+57h+var_A0]
0x14003bbdf  lea     rcx, [rbp+57h+Src]; Src
0x14003bbe3  call    ??$format@AEAY0DE@$$CBGH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0DE@$$CBGH@0@AEAY0DE@$$CBG$$QEAH@Z; std::format<ushort const (&)[52],int>(std::basic_format_string<ushort,ushort const (&)[52],int>,ushort const (&)[52],int &&)
0x14003bbe8  nop
0x14003bbe9  mov     rdx, rax
0x14003bbec  lea     rcx, [rbp+57h+pExceptionObject]
0x14003bbf0  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003bbf5  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003bbfc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003bc00  call    _CxxThrowException_0
0x14003bc06  lea     rax, aFieldDoesNotHa_2; "Field \"{}\" does not have type Integer"
0x14003bc0d  mov     qword ptr [rbp+57h+var_A0], rax
0x14003bc11  mov     qword ptr [rbp+57h+var_A0+8], 25h ; '%'
0x14003bc19  lea     rdx, [rbp+57h+var_A0]
0x14003bc1d  lea     rcx, [rbp+57h+Src]; Src
0x14003bc21  call    ??$format@AEAY0DE@$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0DE@$$CBG@0@AEAY0DE@$$CBG@Z; std::format<ushort const (&)[52]>(std::basic_format_string<ushort,ushort const (&)[52]>,ushort const (&)[52])
0x14003bc26  nop
0x14003bc27  mov     rdx, rax
0x14003bc2a  lea     rcx, [rbp+57h+pExceptionObject]
0x14003bc2e  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003bc33  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003bc3a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003bc3e  call    _CxxThrowException_0
```
