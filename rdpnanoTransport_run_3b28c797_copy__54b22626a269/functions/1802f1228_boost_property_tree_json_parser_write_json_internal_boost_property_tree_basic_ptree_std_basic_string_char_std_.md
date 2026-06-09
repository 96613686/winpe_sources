# boost::property_tree::json_parser::write_json_internal<boost::property_tree::basic_ptree<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>>(std::basic_ostream<char,std::char_traits<char>> &,boost::property_tree::basic_ptree<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool)

- ea: `0x1802f1228`
- end: `0x1802f1369`
- name: `??$write_json_internal@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@json_parser@property_tree@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@_N@Z`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1802f0d30`

## callees

- `0x180024700`
- `0x180028210`
- `0x1800bf574`
- `0x1800f7df0`
- `0x1800f96c8`
- `0x1802f09e8`
- `0x1802f0bd0`
- `0x1802f0d78`
- `0x1802f1228`
- `0x18032f050`

## string_xrefs

- `0x1802f12b7`: `void __cdecl boost::property_tree::json_parser::write_json_internal<class boost::property_tree::basic_ptree<class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >,class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >,struct std::less<class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> > > >>(class std::basic_ostream<char,struct std::char_traits<char> > &,const class boost::property_tree::basic_pt`
- `0x1802f1314`: `void __cdecl boost::property_tree::json_parser::write_json_internal<class boost::property_tree::basic_ptree<class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >,class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >,struct std::less<class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> > > >>(class std::basic_ostream<char,struct std::char_traits<char> > &,const class boost::property_tree::basic_pt`
- `0x1802f12c4`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\boost/property_tree/json_parser/detail/write.hpp`
- `0x1802f1321`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\boost/property_tree/json_parser/detail/write.hpp`
- `0x1802f1335`: `ptree contains data that cannot be represented in JSON format`
- `0x1802f12d8`: `write error`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall boost::property_tree::json_parser::write_json_internal<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // r9
  __int64 result; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  _BYTE v14[32]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v16[96]; // [rsp+70h] [rbp-68h] BYREF

  if ( !(unsigned __int8)boost::property_tree::json_parser::verify_json<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(
                           a2,
                           0) )
  {
    v12 = boost::source_location::source_location(
            (boost::source_location *)v15,
            "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/property_tree/json_parser/detail/write.hpp",
            0xA0u,
            "void __cdecl boost::property_tree::json_parser::write_json_internal<class boost::property_tree::basic_ptree<"
            "class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >,class std::basic_str"
            "ing<char,struct std::char_traits<char>,class std::allocator<char> >,struct std::less<class std::basic_string"
            "<char,struct std::char_traits<char>,class std::allocator<char> > > >>(class std::basic_ostream<char,struct s"
            "td::char_traits<char> > &,const class boost::property_tree::basic_ptree<class std::basic_string<char,struct "
            "std::char_traits<char>,class std::allocator<char> >,class std::basic_string<char,struct std::char_traits<cha"
            "r>,class std::allocator<char> >,struct std::less<class std::basic_string<char,struct std::char_traits<char>,"
            "class std::allocator<char> > > > &,const class std::basic_string<char,struct std::char_traits<char>,class st"
            "d::allocator<char> > &,bool)",
            0xDu);
    std::string::string(v14, "ptree contains data that cannot be represented in JSON format");
    v13 = boost::property_tree::json_parser::json_parser_error::json_parser_error(v16, v14, a3, 0);
    boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(v13, v12);
  }
  LOBYTE(v8) = a4;
  boost::property_tree::json_parser::write_json_helper<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(
    a1,
    a2,
    0,
    v8);
  if ( a4 )
    std::endl<char,std::char_traits<char>>(a1);
  else
    std::flush<char,std::char_traits<char>>(a1);
  result = *a1;
  if ( *(_DWORD *)((char *)a1 + *(int *)(*a1 + 4) + 16) )
  {
    v10 = boost::source_location::source_location(
            (boost::source_location *)v15,
            "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/property_tree/json_parser/detail/write.hpp",
            0xA7u,
            "void __cdecl boost::property_tree::json_parser::write_json_internal<class boost::property_tree::basic_ptree<"
            "class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >,class std::basic_str"
            "ing<char,struct std::char_traits<char>,class std::allocator<char> >,struct std::less<class std::basic_string"
            "<char,struct std::char_traits<char>,class std::allocator<char> > > >>(class std::basic_ostream<char,struct s"
            "td::char_traits<char> > &,const class boost::property_tree::basic_ptree<class std::basic_string<char,struct "
            "std::char_traits<char>,class std::allocator<char> >,class std::basic_string<char,struct std::char_traits<cha"
            "r>,class std::allocator<char> >,struct std::less<class std::basic_string<char,struct std::char_traits<char>,"
            "class std::allocator<char> > > > &,const class std::basic_string<char,struct std::char_traits<char>,class st"
            "d::allocator<char> > &,bool)",
            0xDu);
    std::string::string(v14, "write error");
    v11 = boost::property_tree::json_parser::json_parser_error::json_parser_error(v16, v14, a3, 0);
    boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(v11, v10);
  }
  return result;
}

```

## disassembly

```asm
0x1802f1228  mov     [rsp+arg_0], rbx
0x1802f122d  mov     [rsp+arg_8], rbp
0x1802f1232  mov     [rsp+arg_10], rsi
0x1802f1237  push    rdi
0x1802f1238  mov     eax, 0D0h
0x1802f123d  call    _alloca_probe
0x1802f1242  sub     rsp, rax
0x1802f1245  mov     dil, r9b
0x1802f1248  mov     rbp, r8
0x1802f124b  mov     rsi, rdx
0x1802f124e  mov     rbx, rcx
0x1802f1251  xor     edx, edx
0x1802f1253  mov     rcx, rsi
0x1802f1256  call    ??$verify_json@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@json_parser@property_tree@boost@@YA_NAEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@12@H@Z; boost::property_tree::json_parser::verify_json<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>> const &,int)
0x1802f125b  test    al, al
0x1802f125d  jz      loc_1802F130C
0x1802f1263  mov     r9b, dil
0x1802f1266  xor     r8d, r8d
0x1802f1269  mov     rdx, rsi
0x1802f126c  mov     rcx, rbx
0x1802f126f  call    ??$write_json_helper@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@json_parser@property_tree@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@12@H_N@Z; boost::property_tree::json_parser::write_json_helper<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(std::ostream &,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>> const &,int,bool)
0x1802f1274  mov     rcx, rbx
0x1802f1277  test    dil, dil
0x1802f127a  jz      short loc_1802F1283
0x1802f127c  call    ??$endl@DU?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@@Z; std::endl<char,std::char_traits<char>>(std::ostream &)
0x1802f1281  jmp     short loc_1802F1288
0x1802f1283  call    ??$flush@DU?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@@Z; std::flush<char,std::char_traits<char>>(std::ostream &)
0x1802f1288  mov     rax, [rbx]
0x1802f128b  movsxd  rcx, dword ptr [rax+4]
0x1802f128f  cmp     dword ptr [rcx+rbx+10h], 0
0x1802f1294  jnz     short loc_1802F12AF
0x1802f1296  lea     r11, [rsp+0D8h+var_8]
0x1802f129e  mov     rbx, [r11+10h]
0x1802f12a2  mov     rbp, [r11+18h]
0x1802f12a6  mov     rsi, [r11+20h]
0x1802f12aa  mov     rsp, r11
0x1802f12ad  pop     rdi
0x1802f12ae  retn
0x1802f12af  mov     [rsp+0D8h+var_B8], 0Dh; unsigned int
0x1802f12b7  lea     r9, aVoidCdeclBoost_30; "void __cdecl boost::property_tree::json"...
0x1802f12be  mov     r8d, 0A7h; unsigned int
0x1802f12c4  lea     rdx, aCW1SExternalsV_6; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x1802f12cb  lea     rcx, [rsp+0D8h+var_88]; this
0x1802f12d0  call    ??0source_location@boost@@QEAA@PEBDI0I@Z; boost::source_location::source_location(char const *,uint,char const *,uint)
0x1802f12d5  mov     rbx, rax
0x1802f12d8  lea     rdx, aWriteError; "write error"
0x1802f12df  lea     rcx, [rsp+0D8h+var_A8]
0x1802f12e4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802f12e9  nop
0x1802f12ea  xor     r9d, r9d
0x1802f12ed  mov     r8, rbp
0x1802f12f0  lea     rdx, [rsp+0D8h+var_A8]
0x1802f12f5  lea     rcx, [rsp+0D8h+var_68]
0x1802f12fa  call    ??0json_parser_error@json_parser@property_tree@boost@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0K@Z; boost::property_tree::json_parser::json_parser_error::json_parser_error(std::string const &,std::string const &,ulong)
0x1802f12ff  nop
0x1802f1300  mov     rdx, rbx
0x1802f1303  mov     rcx, rax
0x1802f1306  call    ??$throw_exception@Vjson_parser_error@json_parser@property_tree@boost@@@boost@@YAXAEBVjson_parser_error@json_parser@property_tree@0@AEBUsource_location@0@@Z; boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(boost::property_tree::json_parser::json_parser_error const &,boost::source_location const &)
0x1802f130c  mov     [rsp+0D8h+var_B8], 0Dh; unsigned int
0x1802f1314  lea     r9, aVoidCdeclBoost_30; "void __cdecl boost::property_tree::json"...
0x1802f131b  mov     r8d, 0A0h; unsigned int
0x1802f1321  lea     rdx, aCW1SExternalsV_6; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x1802f1328  lea     rcx, [rsp+0D8h+var_88]; this
0x1802f132d  call    ??0source_location@boost@@QEAA@PEBDI0I@Z; boost::source_location::source_location(char const *,uint,char const *,uint)
0x1802f1332  mov     rbx, rax
0x1802f1335  lea     rdx, aPtreeContainsD; "ptree contains data that cannot be repr"...
0x1802f133c  lea     rcx, [rsp+0D8h+var_A8]
0x1802f1341  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802f1346  nop
0x1802f1347  xor     r9d, r9d
0x1802f134a  mov     r8, rbp
0x1802f134d  lea     rdx, [rsp+0D8h+var_A8]
0x1802f1352  lea     rcx, [rsp+0D8h+var_68]
0x1802f1357  call    ??0json_parser_error@json_parser@property_tree@boost@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0K@Z; boost::property_tree::json_parser::json_parser_error::json_parser_error(std::string const &,std::string const &,ulong)
0x1802f135c  nop
0x1802f135d  mov     rdx, rbx
0x1802f1360  mov     rcx, rax
0x1802f1363  call    ??$throw_exception@Vjson_parser_error@json_parser@property_tree@boost@@@boost@@YAXAEBVjson_parser_error@json_parser@property_tree@0@AEBUsource_location@0@@Z; boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(boost::property_tree::json_parser::json_parser_error const &,boost::source_location const &)
```
