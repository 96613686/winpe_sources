# PolicyFileParser::validatePriority(web::json::value,int &)

- ea: `0x14003b424`
- end: `0x14003b633`
- name: `?validatePriority@PolicyFileParser@@YAXVvalue@json@web@@AEAH@Z`
- size: `527`
- prototype: `__int64 __fastcall(_QWORD *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14003adc4`

## callees

- `0x140002f60`
- `0x140003b64`
- `0x140007590`
- `0x140007630`
- `0x140007f20`
- `0x14000dd20`
- `0x140013df8`
- `0x1400377fc`
- `0x14003789c`
- `0x1400384a0`
- `0x14003b424`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall PolicyFileParser::validatePriority(_QWORD *a1, int *a2)
{
  char v4; // bl
  web::json::value *v5; // rax
  bool is_integer; // bl
  web::json::value *v7; // rax
  __int64 result; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int128 v12; // [rsp+30h] [rbp-49h] BYREF
  __int128 v13; // [rsp+40h] [rbp-39h]
  _BYTE pExceptionObject[56]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE Src[32]; // [rsp+88h] [rbp+Fh] BYREF

  v12 = 0;
  v13 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v12, L"priority");
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 8LL))(*a1, &v12);
  std::wstring::_Tidy_deallocate(&v12);
  if ( !v4 )
  {
    *(_QWORD *)&v12 = L"Missing required field \"{}\"";
    *((_QWORD *)&v12 + 1) = 27;
    v10 = std::format<unsigned short const (&)[9]>(Src);
    PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v10);
    throw (PolicyFileParser::ParsingException *)pExceptionObject;
  }
  v12 = 0;
  v13 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v12, L"priority");
  v5 = (web::json::value *)web::json::value::at(a1, &v12);
  is_integer = web::json::value::is_integer(v5);
  std::wstring::_Tidy_deallocate(&v12);
  if ( !is_integer )
  {
    *(_QWORD *)&v12 = L"Field \"{}\" does not have type Integer";
    *((_QWORD *)&v12 + 1) = 37;
    v11 = std::format<unsigned short const (&)[9]>(Src);
    PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v11);
    throw (PolicyFileParser::ParsingException *)pExceptionObject;
  }
  v12 = 0;
  v13 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v12, L"priority");
  v7 = (web::json::value *)web::json::value::at(a1, &v12);
  *a2 = web::json::value::as_integer(v7);
  result = std::wstring::_Tidy_deallocate(&v12);
  if ( *a2 < 1 )
  {
    *(_QWORD *)&v12 = L"Field \"{}\" requires a minimum value of {}";
    *((_QWORD *)&v12 + 1) = 41;
    v9 = std::format<unsigned short const (&)[9],int>(Src);
    PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v9);
    throw (PolicyFileParser::ParsingException *)pExceptionObject;
  }
  if ( *a1 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 192LL))(*a1);
  return result;
}

```

## disassembly

```asm
0x14003b424  mov     [rsp-8+arg_10], rbx
0x14003b429  push    rbp
0x14003b42a  push    rsi
0x14003b42b  push    rdi
0x14003b42c  push    r14
0x14003b42e  push    r15
0x14003b430  lea     rbp, [rsp-37h]
0x14003b435  sub     rsp, 0B0h
0x14003b43c  mov     rax, cs:__security_cookie
0x14003b443  xor     rax, rsp
0x14003b446  mov     [rbp+57h+var_28], rax
0x14003b44a  mov     rsi, rdx
0x14003b44d  mov     rdi, rcx
0x14003b450  mov     [rbp+57h+var_A8], rcx
0x14003b454  xorps   xmm0, xmm0
0x14003b457  movups  [rbp+57h+var_A0], xmm0
0x14003b45b  xorps   xmm1, xmm1
0x14003b45e  movdqu  [rbp+57h+var_90], xmm1
0x14003b463  mov     r15d, 8
0x14003b469  mov     r8d, r15d
0x14003b46c  lea     r14, aPriority; "priority"
0x14003b473  mov     rdx, r14
0x14003b476  lea     rcx, [rbp+57h+var_A0]
0x14003b47a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b47f  nop
0x14003b480  mov     rcx, [rdi]
0x14003b483  mov     rax, [rcx]
0x14003b486  lea     rdx, [rbp+57h+var_A0]
0x14003b48a  mov     rax, [rax+8]
0x14003b48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b493  mov     bl, al
0x14003b495  lea     rcx, [rbp+57h+var_A0]
0x14003b499  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b49e  test    bl, bl
0x14003b4a0  jz      loc_14003B5B1
0x14003b4a6  xorps   xmm0, xmm0
0x14003b4a9  movups  [rbp+57h+var_A0], xmm0
0x14003b4ad  xorps   xmm1, xmm1
0x14003b4b0  movdqu  [rbp+57h+var_90], xmm1
0x14003b4b5  mov     r8d, r15d
0x14003b4b8  mov     rdx, r14
0x14003b4bb  lea     rcx, [rbp+57h+var_A0]
0x14003b4bf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b4c4  nop
0x14003b4c5  lea     rdx, [rbp+57h+var_A0]
0x14003b4c9  mov     rcx, rdi
0x14003b4cc  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003b4d1  mov     rcx, rax; this
0x14003b4d4  call    ?is_integer@value@json@web@@QEBA_NXZ; web::json::value::is_integer(void)
0x14003b4d9  mov     bl, al
0x14003b4db  lea     rcx, [rbp+57h+var_A0]
0x14003b4df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b4e4  test    bl, bl
0x14003b4e6  jz      loc_14003B5F2
0x14003b4ec  xorps   xmm0, xmm0
0x14003b4ef  movups  [rbp+57h+var_A0], xmm0
0x14003b4f3  xorps   xmm1, xmm1
0x14003b4f6  movdqu  [rbp+57h+var_90], xmm1
0x14003b4fb  mov     r8d, r15d
0x14003b4fe  mov     rdx, r14
0x14003b501  lea     rcx, [rbp+57h+var_A0]
0x14003b505  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b50a  nop
0x14003b50b  lea     rdx, [rbp+57h+var_A0]
0x14003b50f  mov     rcx, rdi
0x14003b512  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003b517  mov     rcx, rax; this
0x14003b51a  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x14003b51f  mov     [rsi], eax
0x14003b521  lea     rcx, [rbp+57h+var_A0]
0x14003b525  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b52a  lea     edx, [r15-7]
0x14003b52e  cmp     [rsi], edx
0x14003b530  jl      short loc_14003B56C
0x14003b532  mov     rcx, [rdi]
0x14003b535  test    rcx, rcx
0x14003b538  jz      short loc_14003B549
0x14003b53a  mov     rax, [rcx]
0x14003b53d  mov     rax, [rax+0C0h]
0x14003b544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b549  mov     rcx, [rbp+57h+var_28]
0x14003b54d  xor     rcx, rsp; StackCookie
0x14003b550  call    __security_check_cookie
0x14003b555  mov     rbx, [rsp+0D0h+arg_10]
0x14003b55d  add     rsp, 0B0h
0x14003b564  pop     r15
0x14003b566  pop     r14
0x14003b568  pop     rdi
0x14003b569  pop     rsi
0x14003b56a  pop     rbp
0x14003b56b  retn
0x14003b56c  mov     [rbp+57h+var_B0], edx
0x14003b56f  lea     rax, aFieldRequiresA; "Field \"{}\" requires a minimum value o"...
0x14003b576  mov     qword ptr [rbp+57h+var_A0], rax
0x14003b57a  mov     qword ptr [rbp+57h+var_A0+8], 29h ; ')'
0x14003b582  lea     r9, [rbp+57h+var_B0]
0x14003b586  lea     rdx, [rbp+57h+var_A0]
0x14003b58a  lea     rcx, [rbp+57h+Src]; Src
0x14003b58e  call    ??$format@AEAY08$$CBGH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY08$$CBGH@0@AEAY08$$CBG$$QEAH@Z; std::format<ushort const (&)[9],int>(std::basic_format_string<ushort,ushort const (&)[9],int>,ushort const (&)[9],int &&)
0x14003b593  nop
0x14003b594  mov     rdx, rax
0x14003b597  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b59b  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b5a0  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b5a7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b5ab  call    _CxxThrowException_0
0x14003b5b1  lea     rax, aMissingRequire; "Missing required field \"{}\""
0x14003b5b8  mov     qword ptr [rbp+57h+var_A0], rax
0x14003b5bc  mov     qword ptr [rbp+57h+var_A0+8], 1Bh
0x14003b5c4  mov     r8, r14
0x14003b5c7  lea     rdx, [rbp+57h+var_A0]
0x14003b5cb  lea     rcx, [rbp+57h+Src]; Src
0x14003b5cf  call    ??$format@AEAY08$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY08$$CBG@0@AEAY08$$CBG@Z; std::format<ushort const (&)[9]>(std::basic_format_string<ushort,ushort const (&)[9]>,ushort const (&)[9])
0x14003b5d4  nop
0x14003b5d5  mov     rdx, rax
0x14003b5d8  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b5dc  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b5e1  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b5e8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b5ec  call    _CxxThrowException_0
0x14003b5f2  lea     rax, aFieldDoesNotHa_2; "Field \"{}\" does not have type Integer"
0x14003b5f9  mov     qword ptr [rbp+57h+var_A0], rax
0x14003b5fd  mov     qword ptr [rbp+57h+var_A0+8], 25h ; '%'
0x14003b605  mov     r8, r14
0x14003b608  lea     rdx, [rbp+57h+var_A0]
0x14003b60c  lea     rcx, [rbp+57h+Src]; Src
0x14003b610  call    ??$format@AEAY08$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY08$$CBG@0@AEAY08$$CBG@Z; std::format<ushort const (&)[9]>(std::basic_format_string<ushort,ushort const (&)[9]>,ushort const (&)[9])
0x14003b615  nop
0x14003b616  mov     rdx, rax
0x14003b619  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b61d  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b622  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b629  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b62d  call    _CxxThrowException_0
```
