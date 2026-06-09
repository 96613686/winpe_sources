# std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>(std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>> &,unsigned __int64 &)

- ea: `0x1800137a4`
- end: `0x18001380e`
- name: `??$_Allocate_at_least_helper@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@YAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEAV?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@0@AEA_K@Z`
- size: `106`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013e58`
- `0x180013fec`
- `0x180014170`
- `0x18001432c`
- `0x18001449c`
- `0x18001460c`
- `0x180014e64`
- `0x180015218`
- `0x18001a57c`
- `0x180025b80`

## callees

- `0x18000289c`
- `0x18000fc2c`
- `0x1800137a4`

## pseudocode

```c
_QWORD *__fastcall std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
        __int64 a1,
        _QWORD *a2)
{
  size_t v2; // rcx
  _QWORD *result; // rax
  void *v4; // rax
  void *v5; // rcx

  if ( *a2 > 0xFFFFFFFFFFFFFFFuLL )
    goto LABEL_10;
  v2 = 16LL * *a2;
  if ( !v2 )
    return 0;
  if ( v2 < 0x1000 )
    return operator new(v2);
  if ( v2 + 39 < v2 )
LABEL_10:
    __scrt_throw_std_bad_array_new_length();
  v4 = operator new(v2 + 39);
  v5 = v4;
  if ( !v4 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v4 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v5;
  return result;
}

```

## disassembly

```asm
0x1800137a4  sub     rsp, 28h
0x1800137a8  mov     rcx, [rdx]
0x1800137ab  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800137b5  cmp     rcx, rax
0x1800137b8  ja      short loc_180013808
0x1800137ba  shl     rcx, 4; Size
0x1800137be  test    rcx, rcx
0x1800137c1  jnz     short loc_1800137CA
0x1800137c3  xor     eax, eax
0x1800137c5  add     rsp, 28h
0x1800137c9  retn
0x1800137ca  cmp     rcx, 1000h
0x1800137d1  jb      short loc_1800137FF
0x1800137d3  lea     rax, [rcx+27h]
0x1800137d7  cmp     rax, rcx
0x1800137da  jbe     short loc_180013808
0x1800137dc  mov     rcx, rax; Size
0x1800137df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800137e4  mov     rcx, rax
0x1800137e7  test    rax, rax
0x1800137ea  jnz     short loc_1800137F1
0x1800137ec  lea     ecx, [rax+5]
0x1800137ef  int     29h; Win8: RtlFailFast(ecx)
0x1800137f1  add     rax, 27h ; '''
0x1800137f5  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800137f9  mov     [rax-8], rcx
0x1800137fd  jmp     short loc_1800137C5
0x1800137ff  add     rsp, 28h
0x180013803  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013808  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
