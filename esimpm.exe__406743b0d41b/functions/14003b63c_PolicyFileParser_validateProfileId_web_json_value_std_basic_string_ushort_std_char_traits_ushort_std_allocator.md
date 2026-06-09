# PolicyFileParser::validateProfileId(web::json::value,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14003b63c`
- end: `0x14003b8b3`
- name: `?validateProfileId@PolicyFileParser@@YAXVvalue@json@web@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x14003adc4`

## callees

- `0x140002f60`
- `0x140003b64`
- `0x1400064d0`
- `0x140007630`
- `0x140008500`
- `0x14000bc60`
- `0x14000dd20`
- `0x140013df8`
- `0x1400240fc`
- `0x14003796c`
- `0x140037a08`
- `0x1400384a0`
- `0x14003b63c`
- `0x14003e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14003b74d`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14003b74d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PolicyFileParser::validateProfileId(_QWORD *a1, _QWORD *a2)
{
  char v4; // bl
  const struct web::json::value *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  _QWORD *v8; // rax
  __int64 result; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-89h] BYREF
  _OWORD v15[2]; // [rsp+30h] [rbp-79h] BYREF
  _OWORD v16[2]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE Src[56]; // [rsp+A8h] [rbp-1h] BYREF

  v14[1] = a1;
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,unsigned short const *>(v15, L"profileId");
  v4 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*a1 + 8LL))(*a1, v15);
  std::wstring::_Tidy_deallocate(v15);
  if ( !v4 )
  {
    *(_QWORD *)&v15[0] = L"Missing required field \"{}\"";
    *((_QWORD *)&v15[0] + 1) = 27;
    v12 = std::format<unsigned short const (&)[10]>(v16);
    PolicyFileParser::ParsingException::ParsingException(Src, v12);
    throw (PolicyFileParser::ParsingException *)Src;
  }
  memset(v16, 0, sizeof(v16));
  std::wstring::_Construct<1,unsigned short const *>(v16, L"profileId");
  v5 = (const struct web::json::value *)web::json::value::at(a1, v16);
  web::json::value::value((web::json::value *)v14, v5);
  std::wstring::_Tidy_deallocate(v16);
  if ( (unsigned int)web::json::value::type(v14) != 2 )
  {
    *(_QWORD *)&v15[0] = L"Field \"{}\" does not have type String";
    *((_QWORD *)&v15[0] + 1) = 36;
    v11 = std::format<unsigned short const (&)[10]>(Src);
    PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v11);
    throw (PolicyFileParser::ParsingException *)pExceptionObject;
  }
  v6 = web::json::value::as_string(v14);
  std::wstring::operator=(a2, v6);
  if ( (unsigned __int64)(a2[2] - 5LL) > 1 )
  {
    *(_QWORD *)&v15[0] = L"Field \"{}\" with invalid length. \"{}\" must be 5 or 6 characters long";
    *((_QWORD *)&v15[0] + 1) = 67;
    v10 = std::format<unsigned short const (&)[10],unsigned short const (&)[10]>(Src);
    PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v10);
    throw (PolicyFileParser::ParsingException *)pExceptionObject;
  }
  v7 = 0;
  do
  {
    if ( a2[3] <= 7u )
      v8 = a2;
    else
      v8 = (_QWORD *)*a2;
    if ( !(unsigned int)_o_iswdigit(*((unsigned __int16 *)v8 + v7)) )
    {
      *(_QWORD *)&v15[0] = L"At least one character in the \"{}\" field is non-numeric";
      *((_QWORD *)&v15[0] + 1) = 55;
      v13 = std::format<unsigned short const (&)[10]>(Src);
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, v13);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    v7 = (unsigned int)(v7 + 1);
    result = (unsigned int)v7;
  }
  while ( (unsigned __int64)(unsigned int)v7 < a2[2] );
  if ( v14[0] )
    result = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v14[0] + 192LL))(v14[0], 1);
  if ( *a1 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 192LL))(*a1, 1);
  return result;
}

```

## disassembly

```asm
0x14003b63c  mov     [rsp-8+arg_10], rbx
0x14003b641  push    rbp
0x14003b642  push    rsi
0x14003b643  push    rdi
0x14003b644  lea     rbp, [rsp-47h]
0x14003b649  sub     rsp, 0F0h
0x14003b650  mov     rax, cs:__security_cookie
0x14003b657  xor     rax, rsp
0x14003b65a  mov     [rbp+57h+var_20], rax
0x14003b65e  mov     rdi, rdx
0x14003b661  mov     rsi, rcx
0x14003b664  mov     [rsp+100h+var_D8], rcx
0x14003b669  xorps   xmm0, xmm0
0x14003b66c  movups  [rbp+57h+var_D0], xmm0
0x14003b670  xorps   xmm1, xmm1
0x14003b673  movdqu  [rbp+57h+var_C0], xmm1
0x14003b678  mov     r8d, 9
0x14003b67e  lea     rdx, aProfileid; "profileId"
0x14003b685  lea     rcx, [rbp+57h+var_D0]
0x14003b689  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b68e  nop
0x14003b68f  mov     rcx, [rsi]
0x14003b692  mov     rax, [rcx]
0x14003b695  lea     rdx, [rbp+57h+var_D0]
0x14003b699  mov     rax, [rax+8]
0x14003b69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b6a2  mov     bl, al
0x14003b6a4  lea     rcx, [rbp+57h+var_D0]
0x14003b6a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b6ad  lea     rcx, [rbp+57h+var_B0]; Src
0x14003b6b1  test    bl, bl
0x14003b6b3  jz      loc_14003B83B
0x14003b6b9  xorps   xmm0, xmm0
0x14003b6bc  movups  [rbp+57h+var_B0], xmm0
0x14003b6c0  xorps   xmm1, xmm1
0x14003b6c3  movdqu  [rbp+57h+var_A0], xmm1
0x14003b6c8  mov     r8d, 9
0x14003b6ce  lea     rdx, aProfileid; "profileId"
0x14003b6d5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b6da  nop
0x14003b6db  lea     rdx, [rbp+57h+var_B0]
0x14003b6df  mov     rcx, rsi
0x14003b6e2  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003b6e7  mov     rdx, rax; struct web::json::value *
0x14003b6ea  lea     rcx, [rsp+100h+var_E0]; this
0x14003b6ef  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003b6f4  nop
0x14003b6f5  lea     rcx, [rbp+57h+var_B0]
0x14003b6f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b6fe  lea     rcx, [rsp+100h+var_E0]
0x14003b703  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x14003b708  cmp     eax, 2
0x14003b70b  jnz     loc_14003B7FD
0x14003b711  lea     rcx, [rsp+100h+var_E0]
0x14003b716  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x14003b71b  mov     rdx, rax
0x14003b71e  mov     rcx, rdi
0x14003b721  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003b726  mov     rax, [rdi+10h]
0x14003b72a  sub     rax, 5
0x14003b72e  cmp     rax, 1
0x14003b732  ja      loc_14003B7BF
0x14003b738  xor     ebx, ebx
0x14003b73a  cmp     qword ptr [rdi+18h], 7
0x14003b73f  jbe     short loc_14003B746
0x14003b741  mov     rax, [rdi]
0x14003b744  jmp     short loc_14003B749
0x14003b746  mov     rax, rdi
0x14003b749  movzx   ecx, word ptr [rax+rbx*2]
0x14003b74d  call    cs:__imp__o_iswdigit
0x14003b753  test    eax, eax
0x14003b755  jz      loc_14003B875
0x14003b75b  inc     ebx
0x14003b75d  mov     eax, ebx
0x14003b75f  cmp     rax, [rdi+10h]
0x14003b763  jb      short loc_14003B73A
0x14003b765  mov     rcx, [rsp+100h+var_E0]
0x14003b76a  test    rcx, rcx
0x14003b76d  jz      short loc_14003B784
0x14003b76f  mov     rax, [rcx]
0x14003b772  mov     edx, 1
0x14003b777  mov     rax, [rax+0C0h]
0x14003b77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b783  nop
0x14003b784  mov     rcx, [rsi]
0x14003b787  test    rcx, rcx
0x14003b78a  jz      short loc_14003B7A0
0x14003b78c  mov     rax, [rcx]
0x14003b78f  mov     edx, 1
0x14003b794  mov     rax, [rax+0C0h]
0x14003b79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b7a0  mov     rcx, [rbp+57h+var_20]
0x14003b7a4  xor     rcx, rsp; StackCookie
0x14003b7a7  call    __security_check_cookie
0x14003b7ac  mov     rbx, [rsp+100h+arg_10]
0x14003b7b4  add     rsp, 0F0h
0x14003b7bb  pop     rdi
0x14003b7bc  pop     rsi
0x14003b7bd  pop     rbp
0x14003b7be  retn
0x14003b7bf  lea     rax, aFieldWithInval; "Field \"{}\" with invalid length. \"{}"...
0x14003b7c6  mov     qword ptr [rbp+57h+var_D0], rax
0x14003b7ca  mov     qword ptr [rbp+57h+var_D0+8], 43h ; 'C'
0x14003b7d2  lea     rdx, [rbp+57h+var_D0]
0x14003b7d6  lea     rcx, [rbp+57h+Src]; Src
0x14003b7da  call    ??$format@AEAY09$$CBGAEAY09$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY09$$CBGAEAY09$$CBG@0@AEAY09$$CBG1@Z; std::format<ushort const (&)[10],ushort const (&)[10]>(std::basic_format_string<ushort,ushort const (&)[10],ushort const (&)[10]>,ushort const (&)[10],ushort const (&)[10])
0x14003b7df  nop
0x14003b7e0  mov     rdx, rax
0x14003b7e3  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b7e7  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b7ec  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b7f3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b7f7  call    _CxxThrowException_0
0x14003b7fd  lea     rax, aFieldDoesNotHa; "Field \"{}\" does not have type String"
0x14003b804  mov     qword ptr [rbp+57h+var_D0], rax
0x14003b808  mov     qword ptr [rbp+57h+var_D0+8], 24h ; '$'
0x14003b810  lea     rdx, [rbp+57h+var_D0]
0x14003b814  lea     rcx, [rbp+57h+Src]; Src
0x14003b818  call    ??$format@AEAY09$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY09$$CBG@0@AEAY09$$CBG@Z; std::format<ushort const (&)[10]>(std::basic_format_string<ushort,ushort const (&)[10]>,ushort const (&)[10])
0x14003b81d  nop
0x14003b81e  mov     rdx, rax
0x14003b821  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b825  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b82a  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b831  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b835  call    _CxxThrowException_0
0x14003b83b  lea     rax, aMissingRequire; "Missing required field \"{}\""
0x14003b842  mov     qword ptr [rbp+57h+var_D0], rax
0x14003b846  mov     qword ptr [rbp+57h+var_D0+8], 1Bh
0x14003b84e  lea     rdx, [rbp+57h+var_D0]
0x14003b852  call    ??$format@AEAY09$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY09$$CBG@0@AEAY09$$CBG@Z; std::format<ushort const (&)[10]>(std::basic_format_string<ushort,ushort const (&)[10]>,ushort const (&)[10])
0x14003b857  nop
0x14003b858  mov     rdx, rax
0x14003b85b  lea     rcx, [rbp+57h+Src]
0x14003b85f  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b864  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b86b  lea     rcx, [rbp+57h+Src]; pExceptionObject
0x14003b86f  call    _CxxThrowException_0
0x14003b875  lea     rax, aAtLeastOneChar; "At least one character in the \"{}\" fi"...
0x14003b87c  mov     qword ptr [rbp+57h+var_D0], rax
0x14003b880  mov     qword ptr [rbp+57h+var_D0+8], 37h ; '7'
0x14003b888  lea     rdx, [rbp+57h+var_D0]
0x14003b88c  lea     rcx, [rbp+57h+Src]; Src
0x14003b890  call    ??$format@AEAY09$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY09$$CBG@0@AEAY09$$CBG@Z; std::format<ushort const (&)[10]>(std::basic_format_string<ushort,ushort const (&)[10]>,ushort const (&)[10])
0x14003b895  nop
0x14003b896  mov     rdx, rax
0x14003b899  lea     rcx, [rbp+57h+pExceptionObject]
0x14003b89d  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003b8a2  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003b8a9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003b8ad  call    _CxxThrowException_0
```
