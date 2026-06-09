# std::vector<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18001b294`
- end: `0x18001b316`
- name: `??1_Reallocation_guard@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180013e58`
- `0x180013fec`
- `0x180014170`
- `0x18001432c`
- `0x18001449c`
- `0x18001460c`
- `0x180014e64`
- `0x180015218`
- `0x18002ebdf`
- `0x18002ec15`

## callees

- `0x180002860`
- `0x18001b294`
- `0x180022cf4`

## pseudocode

```c
void __fastcall std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 16 )
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        (void **)(i + 8),
        *(_BYTE *)i);
    v4 = a1[1];
    if ( (unsigned __int64)(16LL * a1[2]) < 0x1000 )
    {
      v5 = (void *)a1[1];
    }
    else
    {
      v5 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
}

```

## disassembly

```asm
0x18001b294  mov     [rsp+arg_0], rbx
0x18001b299  mov     [rsp+arg_8], rsi
0x18001b29e  push    rdi
0x18001b29f  sub     rsp, 20h
0x18001b2a3  cmp     qword ptr [rcx+8], 0
0x18001b2a8  mov     rbx, rcx
0x18001b2ab  jz      short loc_18001B306
0x18001b2ad  mov     rsi, [rcx+20h]
0x18001b2b1  mov     rdi, [rcx+18h]
0x18001b2b5  jmp     short loc_18001B2C6
0x18001b2b7  mov     dl, [rdi]
0x18001b2b9  lea     rcx, [rdi+8]
0x18001b2bd  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001b2c2  add     rdi, 10h
0x18001b2c6  cmp     rdi, rsi
0x18001b2c9  jnz     short loc_18001B2B7
0x18001b2cb  mov     rdx, [rbx+10h]
0x18001b2cf  mov     rax, [rbx+8]
0x18001b2d3  shl     rdx, 4; unsigned __int64
0x18001b2d7  cmp     rdx, 1000h
0x18001b2de  jb      short loc_18001B2FE
0x18001b2e0  mov     rcx, [rax-8]
0x18001b2e4  sub     rax, rcx
0x18001b2e7  sub     rax, 8
0x18001b2eb  cmp     rax, 1Fh
0x18001b2ef  ja      short loc_18001B2F7
0x18001b2f1  add     rdx, 27h ; '''
0x18001b2f5  jmp     short loc_18001B301
0x18001b2f7  mov     ecx, 5
0x18001b2fc  int     29h; Win8: RtlFailFast(ecx)
0x18001b2fe  mov     rcx, rax; void *
0x18001b301  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b306  mov     rbx, [rsp+28h+arg_0]
0x18001b30b  mov     rsi, [rsp+28h+arg_8]
0x18001b310  add     rsp, 20h
0x18001b314  pop     rdi
0x18001b315  retn
```
