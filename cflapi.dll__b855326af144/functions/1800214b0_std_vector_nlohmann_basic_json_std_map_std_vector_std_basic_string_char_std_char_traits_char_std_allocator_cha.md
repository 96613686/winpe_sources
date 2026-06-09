# std::vector<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>::_Change_array(nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> * const,unsigned __int64,unsigned __int64)

- ea: `0x1800214b0`
- end: `0x18002154e`
- name: `?_Change_array@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAXQEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@_K1@Z`
- size: `158`
- prototype: ``
- caller_count: `9`
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
- `0x180025b80`

## callees

- `0x180002860`
- `0x1800214b0`
- `0x180022cf4`

## pseudocode

```c
void __fastcall std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Change_array(
        void **a1,
        char *a2,
        __int64 a3,
        __int64 a4)
{
  void **v4; // rbx
  void **v9; // r14
  char *v10; // rax
  _BYTE *v11; // rcx

  v4 = (void **)*a1;
  if ( *a1 )
  {
    v9 = (void **)a1[1];
    while ( v4 != v9 )
    {
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        v4 + 1,
        *(_BYTE *)v4);
      v4 += 2;
    }
    v10 = (char *)*a1;
    if ( (((_BYTE *)a1[2] - (_BYTE *)*a1) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
    {
      v11 = *a1;
    }
    else
    {
      v11 = (_BYTE *)*((_QWORD *)v10 - 1);
      if ( (unsigned __int64)(v10 - v11 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v11);
  }
  *a1 = a2;
  a1[1] = &a2[16 * a3];
  a1[2] = &a2[16 * a4];
}

```

## disassembly

```asm
0x1800214b0  push    rbx
0x1800214b2  push    rbp
0x1800214b3  push    rsi
0x1800214b4  push    rdi
0x1800214b5  push    r14
0x1800214b7  push    r15
0x1800214b9  sub     rsp, 28h
0x1800214bd  mov     rbx, [rcx]
0x1800214c0  mov     rsi, r9
0x1800214c3  mov     rbp, r8
0x1800214c6  mov     r15, rdx
0x1800214c9  mov     rdi, rcx
0x1800214cc  test    rbx, rbx
0x1800214cf  jz      short loc_180021528
0x1800214d1  mov     r14, [rcx+8]
0x1800214d5  jmp     short loc_1800214E6
0x1800214d7  mov     dl, [rbx]
0x1800214d9  lea     rcx, [rbx+8]
0x1800214dd  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800214e2  add     rbx, 10h
0x1800214e6  cmp     rbx, r14
0x1800214e9  jnz     short loc_1800214D7
0x1800214eb  mov     rax, [rdi]
0x1800214ee  mov     rdx, [rdi+10h]
0x1800214f2  sub     rdx, rax
0x1800214f5  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x1800214f9  cmp     rdx, 1000h
0x180021500  jb      short loc_180021520
0x180021502  mov     rcx, [rax-8]
0x180021506  sub     rax, rcx
0x180021509  sub     rax, 8
0x18002150d  cmp     rax, 1Fh
0x180021511  ja      short loc_180021519
0x180021513  add     rdx, 27h ; '''
0x180021517  jmp     short loc_180021523
0x180021519  mov     ecx, 5
0x18002151e  int     29h; Win8: RtlFailFast(ecx)
0x180021520  mov     rcx, rax; void *
0x180021523  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021528  shl     rbp, 4
0x18002152c  add     rbp, r15
0x18002152f  mov     [rdi], r15
0x180021532  shl     rsi, 4
0x180021536  add     rsi, r15
0x180021539  mov     [rdi+8], rbp
0x18002153d  mov     [rdi+10h], rsi
0x180021541  add     rsp, 28h
0x180021545  pop     r15
0x180021547  pop     r14
0x180021549  pop     rdi
0x18002154a  pop     rsi
0x18002154b  pop     rbp
0x18002154c  pop     rbx
0x18002154d  retn
```
