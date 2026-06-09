# std::_Func_class<bool,int,nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> &>::~_Func_class<bool,int,nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> &>(void)

- ea: `0x18001a9e4`
- end: `0x18001aa16`
- name: `??1?$_Func_class@_NHW4parse_event_t@detail@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@std@@QEAA@XZ`
- size: `50`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002ee2a`
- `0x18002ee7d`
- `0x18002ee8f`
- `0x18002eea1`
- `0x18002eec9`
- `0x18002f3a8`
- `0x18002f91d`
- `0x18002f971`
- `0x18002fa29`

## callees

- `0x18001a9e4`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall std::_Func_class<bool,int,enum nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> &>::~_Func_class<bool,int,enum nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> &>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 56);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a9e4  push    rbx
0x18001a9e6  sub     rsp, 20h
0x18001a9ea  mov     rbx, rcx
0x18001a9ed  mov     rcx, [rcx+38h]
0x18001a9f1  test    rcx, rcx
0x18001a9f4  jz      short loc_18001AA10
0x18001a9f6  mov     rax, [rcx]
0x18001a9f9  cmp     rcx, rbx
0x18001a9fc  setnz   dl
0x18001a9ff  mov     rax, [rax+20h]
0x18001aa03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa08  mov     qword ptr [rbx+38h], 0
0x18001aa10  add     rsp, 20h
0x18001aa14  pop     rbx
0x18001aa15  retn
```
