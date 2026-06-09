# std::vector<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>::_Xlength(void)

- ea: `0x180022430`
- end: `0x180022442`
- name: `?_Xlength@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180012a3c`
- `0x180013e58`
- `0x180013fec`
- `0x180014170`
- `0x18001432c`
- `0x18001449c`
- `0x18001460c`
- `0x18001479c`
- `0x18001492c`
- `0x180014b74`
- `0x180014ce0`
- `0x180014e64`
- `0x180014fd4`
- `0x180015218`
- `0x1800154ac`
- `0x1800161cc`
- `0x180016350`
- `0x180016488`
- `0x18001a57c`
- `0x180021420`
- `0x180025b80`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002243b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002243b`

## pseudocode

```c
void __noreturn std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180022430  sub     rsp, 28h
0x180022434  lea     rcx, aVectorTooLong; "vector too long"
0x18002243b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
