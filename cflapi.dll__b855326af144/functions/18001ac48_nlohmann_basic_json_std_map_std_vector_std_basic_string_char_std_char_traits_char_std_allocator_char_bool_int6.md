# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::~basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>(void)

- ea: `0x18001ac48`
- end: `0x18001ac53`
- name: `??1?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@XZ`
- size: `11`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002edc8`
- `0x18002edec`
- `0x18002ee3c`
- `0x18002effb`
- `0x18002f00d`
- `0x18002f01f`
- `0x18002f031`
- `0x18002f5bf`
- `0x18002f607`
- `0x18002f8b1`
- `0x18002f987`

## callees

- `0x180022cf4`

## pseudocode

```c
__int64 __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
        __int64 a1)
{
  return nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
           (void **)(a1 + 8),
           *(_BYTE *)a1);
}

```

## disassembly

```asm
0x18001ac48  mov     dl, [rcx]
0x18001ac4a  add     rcx, 8
0x18001ac4e  jmp     ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
```
