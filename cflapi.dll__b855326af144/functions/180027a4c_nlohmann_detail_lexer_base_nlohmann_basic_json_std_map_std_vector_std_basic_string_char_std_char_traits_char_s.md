# nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::token_type_name(nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::token_type)

- ea: `0x180027a4c`
- end: `0x180027b22`
- name: `?token_type_name@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@SAPEBDW4token_type@123@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180024524`

## callees

- `0x180027a4c`

## string_xrefs

- `0x180027ada`: `unknown token`

## pseudocode

```c
const char *__fastcall nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::token_type_name(
        int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx

  if ( a1 <= 8 )
  {
    if ( a1 == 8 )
      return "'['";
    if ( !a1 )
      return "<uninitialized>";
    v1 = a1 - 1;
    if ( !v1 )
      return "true literal";
    v2 = v1 - 1;
    if ( !v2 )
      return "false literal";
    v3 = v2 - 1;
    if ( !v3 )
      return "null literal";
    v4 = v3 - 1;
    if ( !v4 )
      return "string literal";
    v5 = v4 - 1;
    if ( !v5 || (unsigned int)(v5 - 1) <= 1 )
      return "number literal";
    return "unknown token";
  }
  v7 = a1 - 9;
  if ( !v7 )
    return "'{'";
  v8 = v7 - 1;
  if ( !v8 )
    return "']'";
  v9 = v8 - 1;
  if ( !v9 )
    return "'}'";
  v10 = v9 - 1;
  if ( !v10 )
    return "':'";
  v11 = v10 - 1;
  if ( !v11 )
    return "','";
  v12 = v11 - 1;
  if ( !v12 )
    return "<parse error>";
  v13 = v12 - 1;
  if ( !v13 )
    return "end of input";
  if ( v13 != 1 )
    return "unknown token";
  return "'[', '{', or a literal";
}

```

## disassembly

```asm
0x180027a4c  cmp     ecx, 8
0x180027a4f  jg      short loc_180027AB2
0x180027a51  jz      short loc_180027AAA
0x180027a53  test    ecx, ecx
0x180027a55  jz      short loc_180027AA2
0x180027a57  sub     ecx, 1
0x180027a5a  jz      short loc_180027A9A
0x180027a5c  sub     ecx, 1
0x180027a5f  jz      short loc_180027A92
0x180027a61  sub     ecx, 1
0x180027a64  jz      short loc_180027A8A
0x180027a66  sub     ecx, 1
0x180027a69  jz      short loc_180027A82
0x180027a6b  sub     ecx, 1
0x180027a6e  jz      short loc_180027A7A
0x180027a70  sub     ecx, 1
0x180027a73  jz      short loc_180027A7A
0x180027a75  cmp     ecx, 1
0x180027a78  jnz     short loc_180027ADA
0x180027a7a  lea     rax, aNumberLiteral; "number literal"
0x180027a81  retn
0x180027a82  lea     rax, aStringLiteral; "string literal"
0x180027a89  retn
0x180027a8a  lea     rax, aNullLiteral; "null literal"
0x180027a91  retn
0x180027a92  lea     rax, aFalseLiteral; "false literal"
0x180027a99  retn
0x180027a9a  lea     rax, aTrueLiteral; "true literal"
0x180027aa1  retn
0x180027aa2  lea     rax, aUninitialized; "<uninitialized>"
0x180027aa9  retn
0x180027aaa  lea     rax, asc_180034820; "'['"
0x180027ab1  retn
0x180027ab2  sub     ecx, 9
0x180027ab5  jz      short loc_180027B1A
0x180027ab7  sub     ecx, 1
0x180027aba  jz      short loc_180027B12
0x180027abc  sub     ecx, 1
0x180027abf  jz      short loc_180027B0A
0x180027ac1  sub     ecx, 1
0x180027ac4  jz      short loc_180027B02
0x180027ac6  sub     ecx, 1
0x180027ac9  jz      short loc_180027AFA
0x180027acb  sub     ecx, 1
0x180027ace  jz      short loc_180027AF2
0x180027ad0  sub     ecx, 1
0x180027ad3  jz      short loc_180027AEA
0x180027ad5  cmp     ecx, 1
0x180027ad8  jz      short loc_180027AE2
0x180027ada  lea     rax, aUnknownToken; "unknown token"
0x180027ae1  retn
0x180027ae2  lea     rax, aOrALiteral; "'[', '{', or a literal"
0x180027ae9  retn
0x180027aea  lea     rax, aEndOfInput; "end of input"
0x180027af1  retn
0x180027af2  lea     rax, aParseError_1; "<parse error>"
0x180027af9  retn
0x180027afa  lea     rax, asc_180034834; "','"
0x180027b01  retn
0x180027b02  lea     rax, asc_180034830; "':'"
0x180027b09  retn
0x180027b0a  lea     rax, asc_18003482C; "'}'"
0x180027b11  retn
0x180027b12  lea     rax, asc_180034828; "']'"
0x180027b19  retn
0x180027b1a  lea     rax, asc_180034824; "'{'"
0x180027b21  retn
```
