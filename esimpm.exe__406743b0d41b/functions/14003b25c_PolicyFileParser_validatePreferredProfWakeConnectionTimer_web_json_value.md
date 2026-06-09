# PolicyFileParser::validatePreferredProfWakeConnectionTimer(web::json::value)

- ea: `0x14003b25c`
- end: `0x14003b41d`
- name: `?validatePreferredProfWakeConnectionTimer@PolicyFileParser@@YAXVvalue@json@web@@@Z`
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
- `0x140037f18`
- `0x140037fb4`
- `0x1400384a0`
- `0x14003b25c`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall PolicyFileParser::validatePreferredProfWakeConnectionTimer(_QWORD *a1)
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
  std::wstring::_Construct<1,unsigned short const *>(v8, L"preferredProfileWakeConnectionTimerInSeconds");
  v2 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*a1 + 8LL))(*a1, v8);
  result = std::wstring::_Tidy_deallocate(v8);
  if ( v2 )
  {
    memset(v9, 0, sizeof(v9));
    std::wstring::_Construct<1,unsigned short const *>(v9, L"preferredProfileWakeConnectionTimerInSeconds");
    v4 = (const struct web::json::value *)web::json::value::at(a1, v9);
    web::json::value::value((web::json::value *)v7, v4);
    std::wstring::_Tidy_deallocate(v9);
    if ( !web::json::value::is_integer((web::json::value *)v7) )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" does not have type Integer";
      *((_QWORD *)&v8[0] + 1) = 37;
      v6 = std::format<unsigned short const (&)[45]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v6);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    result = web::json::value::as_integer((web::json::value *)v7);
    if ( (int)result < 30 )
    {
      *(_QWORD *)&v8[0] = L"Field \"{}\" requires a minimum value of {}";
      *((_QWORD *)&v8[0] + 1) = 41;
      v5 = std::format<unsigned short const (&)[45],int>(Src);
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
0x14003b25c  mov     [rsp-8+arg_8], rbx
0x14003b261  mov     [rsp-8+arg_10], rdi
0x14003b266  push    rbp
0x14003b267  lea     rbp, [rsp-57h]
0x14003b26c  sub     rsp, 0E0h
0x14003b273  mov     rax, cs:__security_cookie
0x14003b27a  xor     rax, rsp
0x14003b27d  mov     [rbp+57h+var_8], rax
0x14003b281  mov     rdi, rcx
0x14003b284  mov     [rbp+57h+var_B0], rcx
0x14003b288  xorps   xmm0, xmm0
0x14003b28b  movups  [rbp+57h+var_A0], xmm0
0x14003b28f  xorps   xmm1, xmm1
0x14003b292  movdqu  [rbp+57h+var_90], xmm1
0x14003b297  mov     r8d, 2Ch ; ','
0x14003b29d  lea     rdx, aPreferredprofi; "preferredProfileWakeConnectionTimerInSe"...
0x14003b2a4  lea     rcx, [rbp+57h+var_A0]
0x14003b2a8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b2ad  nop
0x14003b2ae  mov     rcx, [rdi]
0x14003b2b1  mov     rax, [rcx]
0x14003b2b4  lea     rdx, [rbp+57h+var_A0]
0x14003b2b8  mov     rax, [rax+8]
0x14003b2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b2c1  mov     bl, al
0x14003b2c3  lea     rcx, [rbp+57h+var_A0]
0x14003b2c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b2cc  test    bl, bl
0x14003b2ce  jz      loc_14003B359
0x14003b2d4  xorps   xmm0, xmm0
0x14003b2d7  movups  [rbp+57h+var_80], xmm0
0x14003b2db  xorps   xmm1, xmm1
0x14003b2de  movdqu  [rbp+57h+var_70], xmm1
0x14003b2e3  mov     r8d, 2Ch ; ','
0x14003b2e9  lea     rdx, aPreferredprofi; "preferredProfileWakeConnectionTimerInSe"...
0x14003b2f0  lea     rcx, [rbp+57h+var_80]
0x14003b2f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b2f9  nop
0x14003b2fa  lea     rdx, [rbp+57h+var_80]
0x14003b2fe  mov     rcx, rdi
0x14003b301  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003b306  mov     rdx, rax; struct web::json::value *
0x14003b309  lea     rcx, [rbp+57h+var_B8]; this
0x14003b30d  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003b312  nop
0x14003b313  lea     rcx, [rbp+57h+var_80]
0x14003b317  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b31c  lea     rcx, [rbp+57h+var_B8]; this
0x14003b320  call    ?is_integer@value@json@web@@QEBA_NXZ; web::json::value::is_integer(void)
0x14003b325  test    al, al
0x14003b327  jz      loc_14003B3DF
0x14003b32d  lea     rcx, [rbp+57h+var_B8]; this
0x14003b331  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x14003b336  cmp     eax, 1Eh
0x14003b339  jl      short loc_14003B396
0x14003b33b  mov     rcx, [rbp+57h+var_B8]
0x14003b33f  test    rcx, rcx
0x14003b342  jz      short loc_14003B359
0x14003b344  mov     rax, [rcx]
0x14003b347  mov     edx, 1
0x14003b34c  mov     rax, [rax+0C0h]
0x14003b353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b358  nop
0x14003b359  mov     rcx, [rdi]
0x14003b35c  test    rcx, rcx
0x14003b35f  jz      short loc_14003B375
0x14003b361  mov     rax, [rcx]
0x14003b364  mov     edx, 1
0x14003b369  mov     rax, [rax+0C0h]
0x14003b370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b375  mov     rcx, [rbp+57h+var_8]
0x14003b379  xor     rcx, rsp; StackCookie
0x14003b37c  call    __security_check_cookie
0x14003b381  lea     r11, [rsp+0E0h+var_s0]
0x14003b389  mov     rbx, [r11+18h]
0x14003b38d  mov     rdi, [r11+20h]
0x14003b391  mov     rsp, r11
0x14003b394  pop     rbp
0x14003b395  retn
0x14003b396  mov     [rbp+57h+var_C0], 1Eh
0x14003b39d  lea     rax, aFieldRequiresA; "Field \"{}\" requires a minimum value o"...
0x14003b3a4  mov     qword ptr [rbp+57h+var_A0], rax
0x14003b3a8  mov     qword ptr [rbp+57h+var_A0+8], 29h ; ')'
0x14003b3b0  lea     r9, [rbp+57h+var_C0]
0x14003b3b4  lea     rdx, [rbp+57h+var_A0]
0x14003b3b8  lea     rcx, [rbp+57h+Src]; Src
0x14003b3bc  call    ??$format@AEAY0CN@$$CBGH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0CN@$$CBGH@0@AEAY0CN@$$CBG$$QEAH@Z; std::format<ushort const (&)[45],int>(std::basic_format_string<ushort,ushort const (&)[45],int>,ushort const (&)[45],int &&)
0x14003b3c1  nop
0x14003b3c2  mov     rdx, rax
0x14003b3c5  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b3c9  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b3ce  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b3d5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b3d9  call    _CxxThrowException_0
0x14003b3df  lea     rax, aFieldDoesNotHa_2; "Field \"{}\" does not have type Integer"
0x14003b3e6  mov     qword ptr [rbp+57h+var_A0], rax
0x14003b3ea  mov     qword ptr [rbp+57h+var_A0+8], 25h ; '%'
0x14003b3f2  lea     rdx, [rbp+57h+var_A0]
0x14003b3f6  lea     rcx, [rbp+57h+Src]; Src
0x14003b3fa  call    ??$format@AEAY0CN@$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY0CN@$$CBG@0@AEAY0CN@$$CBG@Z; std::format<ushort const (&)[45]>(std::basic_format_string<ushort,ushort const (&)[45]>,ushort const (&)[45])
0x14003b3ff  nop
0x14003b400  mov     rdx, rax
0x14003b403  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b407  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b40c  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b413  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b417  call    _CxxThrowException_0
```
