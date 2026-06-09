# PolicyFileParser::validateEnabled(web::json::value)

- ea: `0x14003a898`
- end: `0x14003a9d1`
- name: `?validateEnabled@PolicyFileParser@@YAXVvalue@json@web@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14002595c`

## callees

- `0x140002f60`
- `0x140003b64`
- `0x140007630`
- `0x140008500`
- `0x14000dd20`
- `0x140013df8`
- `0x140037760`
- `0x1400384a0`
- `0x14003a898`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyFileParser::validateEnabled(_QWORD *a1)
{
  char v2; // bl
  __int64 result; // rax
  wchar_t *v4; // rax
  int v5; // ebx
  __int64 **v6; // rax
  __int128 v7; // [rsp+30h] [rbp-29h] BYREF
  __int128 v8; // [rsp+40h] [rbp-19h]
  _BYTE pExceptionObject[56]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE Src[32]; // [rsp+88h] [rbp+2Fh] BYREF

  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v7, L"enabled", 7u);
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 8LL))(*a1, &v7);
  result = std::wstring::_Tidy_deallocate((char **)&v7);
  if ( v2 )
  {
    v7 = 0;
    v8 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v7, L"enabled", 7u);
    v4 = web::json::value::at(a1, (__int64)&v7);
    v5 = web::json::value::type(v4);
    result = std::wstring::_Tidy_deallocate((char **)&v7);
    if ( v5 != 1 )
    {
      *(_QWORD *)&v7 = L"Field \"{}\" does not have type Boolean";
      *((_QWORD *)&v7 + 1) = 37;
      v6 = (__int64 **)std::format<unsigned short const (&)[8]>(Src);
      PolicyFileParser::ParsingException::ParsingException((__int64)pExceptionObject, v6);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
  }
  if ( *a1 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 192LL))(*a1, 1);
  return result;
}

```

## disassembly

```asm
0x14003a898  mov     [rsp-8+arg_8], rbx
0x14003a89d  mov     [rsp-8+arg_10], rdi
0x14003a8a2  push    rbp
0x14003a8a3  lea     rbp, [rsp-57h]
0x14003a8a8  sub     rsp, 0B0h
0x14003a8af  mov     rax, cs:__security_cookie
0x14003a8b6  xor     rax, rsp
0x14003a8b9  mov     [rbp+57h+var_8], rax
0x14003a8bd  mov     rdi, rcx
0x14003a8c0  mov     [rbp+57h+var_90], rcx
0x14003a8c4  xorps   xmm0, xmm0
0x14003a8c7  movups  [rbp+57h+var_80], xmm0
0x14003a8cb  xorps   xmm1, xmm1
0x14003a8ce  movdqu  [rbp+57h+var_70], xmm1
0x14003a8d3  mov     r8d, 7
0x14003a8d9  lea     rdx, aEnabled_0; "enabled"
0x14003a8e0  lea     rcx, [rbp+57h+var_80]
0x14003a8e4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003a8e9  nop
0x14003a8ea  mov     rcx, [rdi]
0x14003a8ed  mov     rax, [rcx]
0x14003a8f0  lea     rdx, [rbp+57h+var_80]
0x14003a8f4  mov     rax, [rax+8]
0x14003a8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a8fd  mov     bl, al
0x14003a8ff  lea     rcx, [rbp+57h+var_80]
0x14003a903  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003a908  test    bl, bl
0x14003a90a  jz      short loc_14003A956
0x14003a90c  xorps   xmm0, xmm0
0x14003a90f  movups  [rbp+57h+var_80], xmm0
0x14003a913  xorps   xmm1, xmm1
0x14003a916  movdqu  [rbp+57h+var_70], xmm1
0x14003a91b  mov     r8d, 7
0x14003a921  lea     rdx, aEnabled_0; "enabled"
0x14003a928  lea     rcx, [rbp+57h+var_80]
0x14003a92c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003a931  nop
0x14003a932  lea     rdx, [rbp+57h+var_80]
0x14003a936  mov     rcx, rdi
0x14003a939  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14003a93e  mov     rcx, rax
0x14003a941  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x14003a946  mov     ebx, eax
0x14003a948  lea     rcx, [rbp+57h+var_80]
0x14003a94c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003a951  cmp     ebx, 1
0x14003a954  jnz     short loc_14003A993
0x14003a956  mov     rcx, [rdi]
0x14003a959  test    rcx, rcx
0x14003a95c  jz      short loc_14003A972
0x14003a95e  mov     rax, [rcx]
0x14003a961  mov     edx, 1
0x14003a966  mov     rax, [rax+0C0h]
0x14003a96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a972  mov     rcx, [rbp+57h+var_8]
0x14003a976  xor     rcx, rsp; StackCookie
0x14003a979  call    __security_check_cookie
0x14003a97e  lea     r11, [rsp+0B0h+var_s0]
0x14003a986  mov     rbx, [r11+18h]
0x14003a98a  mov     rdi, [r11+20h]
0x14003a98e  mov     rsp, r11
0x14003a991  pop     rbp
0x14003a992  retn
0x14003a993  lea     rax, aFieldDoesNotHa_0; "Field \"{}\" does not have type Boolean"
0x14003a99a  mov     qword ptr [rbp+57h+var_80], rax
0x14003a99e  mov     qword ptr [rbp+57h+var_80+8], 25h ; '%'
0x14003a9a6  lea     rdx, [rbp+57h+var_80]
0x14003a9aa  lea     rcx, [rbp+57h+Src]; Src
0x14003a9ae  call    ??$format@AEAY07$$CBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEAY07$$CBG@0@AEAY07$$CBG@Z; std::format<ushort const (&)[8]>(std::basic_format_string<ushort,ushort const (&)[8]>,ushort const (&)[8])
0x14003a9b3  nop
0x14003a9b4  mov     rdx, rax
0x14003a9b7  lea     rcx, [rbp+57h+pExceptionObject]
0x14003a9bb  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x14003a9c0  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x14003a9c7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14003a9cb  call    _CxxThrowException_0
```
