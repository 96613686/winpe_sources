# _parse_stream_unsigned_short_

- ea: `0x140008af0`
- end: `0x140008ccf`
- name: `_parse_stream_unsigned_short_`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x14000ade0`

## callees

- `0x140002f60`
- `0x140003244`
- `0x140008540`
- `0x140008af0`
- `0x1400098a0`
- `0x14000a3c0`
- `0x14000ad90`
- `0x14000c800`
- `0x14000de08`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?rdbuf@?$basic_ios@GU?$char_traits@G@std@@@std@@QEBAPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@XZ` at `0x140008b50`
- `msvcp_win!?rdbuf@?$basic_ios@GU?$char_traits@G@std@@@std@@QEBAPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@XZ` at `0x140008b50`

## string_xrefs

- `0x140008c5d`: `Left-over characters in stream after parsing a JSON value`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char **__fastcall parse_stream_unsigned_short_(char **a1, __int64 a2)
{
  char **v3; // rax
  char *v4; // rcx
  void *v5; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  char *v11; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v12[6]; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+60h] [rbp-A0h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-98h]
  __int64 v15; // [rsp+78h] [rbp-88h]
  unsigned __int64 v16; // [rsp+80h] [rbp-80h]
  int v17; // [rsp+A8h] [rbp-58h] BYREF
  void ***v18; // [rsp+B0h] [rbp-50h]
  _BYTE v19[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v20[32]; // [rsp+E0h] [rbp-20h] BYREF

  v12[5] = a1;
  v12[1] = 1;
  v12[2] = 1;
  v12[3] = 0;
  v12[0] = &web::json::details::JSON_StreamParser<unsigned short>::`vftable';
  v12[4] = std::basic_ios<unsigned short>::rdbuf(a2 + *(int *)(*(_QWORD *)a2 + 4LL));
  v13 = 0;
  *(_OWORD *)Block = 0;
  v15 = 0;
  v16 = 7;
  LOWORD(Block[0]) = 0;
  v17 = 0;
  v18 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  web::json::details::JSON_Parser<unsigned short>::GetNextToken(v12, &v13);
  if ( v17 )
  {
    v7 = std::error_code::message(&v17, v19);
    v8 = utility::conversions::to_string_t(v20, v7);
    web::json::details::CreateException<web::json::details::JSON_Parser<unsigned short>::Token>((__int64)&v13, v8);
  }
  v3 = web::json::details::JSON_Parser<unsigned short>::_ParseValue((web::json::details *)v12, &v11, (__int64)&v13);
  v4 = *v3;
  *v3 = 0;
  *a1 = v4;
  if ( v11 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v11 + 192LL))(v11, 1);
  if ( v17 )
  {
    v9 = std::error_code::message(&v17, v20);
    v10 = utility::conversions::to_string_t(v19, v9);
    web::json::details::CreateException<web::json::details::JSON_Parser<unsigned short>::Token>((__int64)&v13, v10);
  }
  if ( v13 )
  {
    std::wstring::wstring(v19, L"Left-over characters in stream after parsing a JSON value");
    web::json::details::CreateException<web::json::details::JSON_Parser<unsigned short>::Token>(
      (__int64)&v13,
      (__int64)v19);
  }
  if ( v16 > 7 )
  {
    if ( 2 * v16 + 2 < 0x1000 )
    {
      v5 = Block[0];
    }
    else
    {
      v5 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x140008af0  mov     [rsp-8+arg_10], rbx
0x140008af5  mov     [rsp-8+arg_18], rdi
0x140008afa  push    rbp
0x140008afb  lea     rbp, [rsp-10h]
0x140008b00  sub     rsp, 110h
0x140008b07  mov     rax, cs:__security_cookie
0x140008b0e  xor     rax, rsp
0x140008b11  mov     [rbp+10h+var_10], rax
0x140008b15  mov     rbx, rcx
0x140008b18  mov     [rsp+110h+var_B8], rcx
0x140008b1d  xor     edi, edi
0x140008b1f  mov     [rsp+110h+var_F0], edi
0x140008b23  mov     [rsp+110h+var_D8], 1
0x140008b2c  mov     [rsp+110h+var_D0], 1
0x140008b35  mov     [rsp+110h+var_C8], rdi
0x140008b3a  lea     rax, ??_7?$JSON_StreamParser@G@details@json@web@@6B@; const web::json::details::JSON_StreamParser<ushort>::`vftable'
0x140008b41  mov     [rsp+110h+var_E0], rax
0x140008b46  mov     rax, [rdx]
0x140008b49  movsxd  rcx, dword ptr [rax+4]
0x140008b4d  add     rcx, rdx
0x140008b50  call    cs:__imp_?rdbuf@?$basic_ios@GU?$char_traits@G@std@@@std@@QEBAPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@XZ; std::basic_ios<ushort>::rdbuf(void)
0x140008b56  mov     [rsp+110h+var_C0], rax
0x140008b5b  mov     [rsp+110h+var_B0], edi
0x140008b5f  xorps   xmm0, xmm0
0x140008b62  movups  xmmword ptr [rsp+110h+Block], xmm0
0x140008b67  mov     [rsp+110h+var_98], rdi
0x140008b6c  mov     [rbp+10h+var_90], 7
0x140008b74  mov     word ptr [rsp+110h+Block], di
0x140008b79  mov     [rbp+10h+var_68], edi
0x140008b7c  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x140008b83  mov     [rbp+10h+var_60], rax
0x140008b87  lea     rdx, [rsp+110h+var_B0]
0x140008b8c  lea     rcx, [rsp+110h+var_E0]
0x140008b91  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x140008b96  cmp     [rbp+10h+var_68], edi
0x140008b99  jnz     loc_140008C7D
0x140008b9f  lea     r8, [rsp+110h+var_B0]
0x140008ba4  lea     rdx, [rsp+110h+var_E8]
0x140008ba9  lea     rcx, [rsp+110h+var_E0]
0x140008bae  call    ?_ParseValue@?$JSON_Parser@G@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::_ParseValue(web::json::details::JSON_Parser<ushort>::Token &)
0x140008bb3  mov     rcx, [rax]
0x140008bb6  mov     [rax], rdi
0x140008bb9  mov     [rbx], rcx
0x140008bbc  mov     rcx, [rsp+110h+var_E8]
0x140008bc1  test    rcx, rcx
0x140008bc4  jz      short loc_140008BDA
0x140008bc6  mov     rax, [rcx]
0x140008bc9  mov     edx, 1
0x140008bce  mov     rax, [rax+0C0h]
0x140008bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008bda  mov     [rsp+110h+var_F0], 3
0x140008be2  cmp     [rbp+10h+var_68], 0
0x140008be6  jnz     loc_140008CA6
0x140008bec  cmp     [rsp+110h+var_B0], 0
0x140008bf1  jnz     short loc_140008C5D
0x140008bf3  mov     rdx, [rbp+10h+var_90]
0x140008bf7  cmp     rdx, 7
0x140008bfb  jbe     short loc_140008C39
0x140008bfd  mov     rax, [rsp+110h+Block]
0x140008c02  lea     rdx, ds:2[rdx*2]
0x140008c0a  cmp     rdx, 1000h
0x140008c11  jb      short loc_140008C31
0x140008c13  mov     rcx, [rax-8]
0x140008c17  sub     rax, rcx
0x140008c1a  sub     rax, 8
0x140008c1e  cmp     rax, 1Fh
0x140008c22  ja      short loc_140008C2A
0x140008c24  add     rdx, 27h ; '''
0x140008c28  jmp     short loc_140008C34
0x140008c2a  mov     ecx, 5
0x140008c2f  int     29h; Win8: RtlFailFast(ecx)
0x140008c31  mov     rcx, rax; Block
0x140008c34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008c39  mov     rax, rbx
0x140008c3c  mov     rcx, [rbp+10h+var_10]
0x140008c40  xor     rcx, rsp; StackCookie
0x140008c43  call    __security_check_cookie
0x140008c48  lea     r11, [rsp+110h+var_s0]
0x140008c50  mov     rbx, [r11+20h]
0x140008c54  mov     rdi, [r11+28h]
0x140008c58  mov     rsp, r11
0x140008c5b  pop     rbp
0x140008c5c  retn
0x140008c5d  lea     rdx, aLeftOverCharac; "Left-over characters in stream after pa"...
0x140008c64  lea     rcx, [rbp+10h+var_50]
0x140008c68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140008c6d  nop
0x140008c6e  lea     rdx, [rbp+10h+var_50]
0x140008c72  lea     rcx, [rsp+110h+var_B0]
0x140008c77  call    ??$CreateException@UToken@?$JSON_Parser@G@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@G@012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<ushort>::Token>(web::json::details::JSON_Parser<ushort>::Token const &,std::wstring const &)
0x140008c7d  lea     rdx, [rbp+10h+var_50]
0x140008c81  lea     rcx, [rbp+10h+var_68]
0x140008c85  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x140008c8a  nop
0x140008c8b  mov     rdx, rax
0x140008c8e  lea     rcx, [rbp+10h+var_30]
0x140008c92  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x140008c97  nop
0x140008c98  mov     rdx, rax
0x140008c9b  lea     rcx, [rsp+110h+var_B0]
0x140008ca0  call    ??$CreateException@UToken@?$JSON_Parser@G@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@G@012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<ushort>::Token>(web::json::details::JSON_Parser<ushort>::Token const &,std::wstring const &)
0x140008ca6  lea     rdx, [rbp+10h+var_30]
0x140008caa  lea     rcx, [rbp+10h+var_68]
0x140008cae  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x140008cb3  nop
0x140008cb4  mov     rdx, rax
0x140008cb7  lea     rcx, [rbp+10h+var_50]
0x140008cbb  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x140008cc0  nop
0x140008cc1  mov     rdx, rax
0x140008cc4  lea     rcx, [rsp+110h+var_B0]
0x140008cc9  call    ??$CreateException@UToken@?$JSON_Parser@G@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@G@012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<ushort>::Token>(web::json::details::JSON_Parser<ushort>::Token const &,std::wstring const &)
```
