# std::vector<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>(nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> * const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> &&)

- ea: `0x180014e64`
- end: `0x180014fcd`
- name: `??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z`
- size: `361`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800171a0`
- `0x1800173a4`
- `0x180017598`
- `0x180017b94`
- `0x180022cf4`

## callees

- `0x1800137a4`
- `0x180014e64`
- `0x18001b294`
- `0x1800214b0`
- `0x180022430`

## pseudocode

```c
char *__fastcall std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
        void **a1,
        char *a2,
        __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  char *v6; // rbx
  unsigned __int64 v8; // rbp
  __int64 v9; // r14
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // rax
  char v13; // cl
  char *v14; // r14
  char *v15; // rdx
  char *v16; // r8
  char *v17; // r9
  char *v18; // rcx
  char *v19; // rcx
  _QWORD v21[3]; // [rsp+20h] [rbp-68h] BYREF
  char *v22; // [rsp+38h] [rbp-50h]
  char *v23; // [rsp+40h] [rbp-48h]
  __int64 v24; // [rsp+90h] [rbp+8h] BYREF

  v3 = 0xFFFFFFFFFFFFFFFLL;
  v5 = ((_BYTE *)a1[1] - (_BYTE *)*a1) >> 4;
  v6 = a2;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Xlength();
  v8 = v5 + 1;
  v9 = a2 - (_BYTE *)*a1;
  v10 = ((_BYTE *)a1[2] - (_BYTE *)*a1) >> 4;
  v11 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v11 + v10;
    if ( v11 + v10 < v8 )
      v3 = v5 + 1;
  }
  v24 = v3;
  v12 = (char *)std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
                  v10,
                  &v24);
  v13 = *(_BYTE *)a3;
  v21[0] = a1;
  v14 = &v12[v9 & 0xFFFFFFFFFFFFFFF0uLL];
  v21[2] = v3;
  v22 = v14;
  v15 = v12;
  *v14 = v13;
  v16 = v14 + 16;
  *((_QWORD *)v14 + 1) = *(_QWORD *)(a3 + 8);
  *(_BYTE *)a3 = 0;
  *(_QWORD *)(a3 + 8) = 0;
  v17 = (char *)a1[1];
  v18 = (char *)*a1;
  v23 = v14 + 16;
  if ( v6 == v17 )
  {
    while ( v18 != v17 )
    {
      *v15 = *v18;
      v15 += 16;
      *((_QWORD *)v15 - 1) = *((_QWORD *)v18 + 1);
      *v18 = 0;
      *((_QWORD *)v18 + 1) = 0;
      v18 += 16;
    }
  }
  else
  {
    while ( v18 != v6 )
    {
      *v15 = *v18;
      v15 += 16;
      *((_QWORD *)v15 - 1) = *((_QWORD *)v18 + 1);
      *v18 = 0;
      *((_QWORD *)v18 + 1) = 0;
      v18 += 16;
    }
    v19 = (char *)a1[1];
    v22 = v12;
    while ( v6 != v19 )
    {
      *v16 = *v6;
      v16 += 16;
      *((_QWORD *)v16 - 1) = *((_QWORD *)v6 + 1);
      *v6 = 0;
      *((_QWORD *)v6 + 1) = 0;
      v6 += 16;
    }
  }
  v21[1] = 0;
  std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Change_array(
    a1,
    v12,
    v8,
    v3);
  std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Reallocation_guard::~_Reallocation_guard(v21);
  return v14;
}

```

## disassembly

```asm
0x180014e64  push    rbx
0x180014e66  push    rbp
0x180014e67  push    rsi
0x180014e68  push    rdi
0x180014e69  push    r14
0x180014e6b  push    r15
0x180014e6d  sub     rsp, 58h
0x180014e71  mov     rax, [rcx+8]
0x180014e75  mov     rdi, 0FFFFFFFFFFFFFFFh
0x180014e7f  sub     rax, [rcx]
0x180014e82  mov     r15, r8
0x180014e85  sar     rax, 4
0x180014e89  mov     rbx, rdx
0x180014e8c  mov     rsi, rcx
0x180014e8f  cmp     rax, rdi
0x180014e92  jz      loc_180014FC7
0x180014e98  mov     r14, rdx
0x180014e9b  lea     rbp, [rax+1]
0x180014e9f  sub     r14, [rcx]
0x180014ea2  mov     rax, rdi
0x180014ea5  mov     rcx, [rcx+10h]
0x180014ea9  sub     rcx, [rsi]
0x180014eac  sar     rcx, 4
0x180014eb0  mov     rdx, rcx
0x180014eb3  shr     rdx, 1
0x180014eb6  sub     rax, rdx
0x180014eb9  cmp     rcx, rax
0x180014ebc  ja      short loc_180014EC9
0x180014ebe  lea     rdi, [rdx+rcx]
0x180014ec2  cmp     rdi, rbp
0x180014ec5  cmovb   rdi, rbp
0x180014ec9  lea     rdx, [rsp+88h+arg_0]
0x180014ed1  mov     [rsp+88h+arg_0], rdi
0x180014ed9  call    ??$_Allocate_at_least_helper@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@YAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEAV?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@0@AEA_K@Z; std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>(std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>> &,unsigned __int64 &)
0x180014ede  mov     cl, [r15]
0x180014ee1  xor     r11d, r11d
0x180014ee4  and     r14, 0FFFFFFFFFFFFFFF0h
0x180014ee8  mov     [rsp+88h+var_68], rsi
0x180014eed  add     r14, rax
0x180014ef0  mov     [rsp+88h+var_58], rdi
0x180014ef5  mov     r10, rax
0x180014ef8  mov     [rsp+88h+var_50], r14
0x180014efd  mov     rdx, rax
0x180014f00  mov     [r14], cl
0x180014f03  lea     r8, [r14+10h]
0x180014f07  mov     rcx, [r15+8]
0x180014f0b  mov     [r14+8], rcx
0x180014f0f  mov     [r15], r11b
0x180014f12  mov     [r15+8], r11
0x180014f16  mov     r9, [rsi+8]
0x180014f1a  mov     rcx, [rsi]
0x180014f1d  mov     [rsp+88h+var_48], r8
0x180014f22  cmp     rbx, r9
0x180014f25  jnz     short loc_180014F66
0x180014f27  jmp     short loc_180014F44
0x180014f29  mov     al, [rcx]
0x180014f2b  mov     [rdx], al
0x180014f2d  lea     rdx, [rdx+10h]
0x180014f31  mov     rax, [rcx+8]
0x180014f35  mov     [rdx-8], rax
0x180014f39  mov     [rcx], r11b
0x180014f3c  mov     [rcx+8], r11
0x180014f40  add     rcx, 10h
0x180014f44  cmp     rcx, r9
0x180014f47  jnz     short loc_180014F29
0x180014f49  jmp     short loc_180014F97
0x180014f4b  mov     al, [rcx]
0x180014f4d  mov     [rdx], al
0x180014f4f  lea     rdx, [rdx+10h]
0x180014f53  mov     rax, [rcx+8]
0x180014f57  mov     [rdx-8], rax
0x180014f5b  mov     [rcx], r11b
0x180014f5e  mov     [rcx+8], r11
0x180014f62  add     rcx, 10h
0x180014f66  cmp     rcx, rbx
0x180014f69  jnz     short loc_180014F4B
0x180014f6b  mov     rcx, [rsi+8]
0x180014f6f  mov     [rsp+88h+var_50], r10
0x180014f74  jmp     short loc_180014F92
0x180014f76  mov     al, [rbx]
0x180014f78  mov     [r8], al
0x180014f7b  lea     r8, [r8+10h]
0x180014f7f  mov     rax, [rbx+8]
0x180014f83  mov     [r8-8], rax
0x180014f87  mov     [rbx], r11b
0x180014f8a  mov     [rbx+8], r11
0x180014f8e  add     rbx, 10h
0x180014f92  cmp     rbx, rcx
0x180014f95  jnz     short loc_180014F76
0x180014f97  mov     r9, rdi
0x180014f9a  mov     [rsp+88h+var_60], r11
0x180014f9f  mov     r8, rbp
0x180014fa2  mov     rdx, r10
0x180014fa5  mov     rcx, rsi
0x180014fa8  call    ?_Change_array@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAXQEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@_K1@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Change_array(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,unsigned __int64,unsigned __int64)
0x180014fad  lea     rcx, [rsp+88h+var_68]
0x180014fb2  call    ??1_Reallocation_guard@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@QEAA@XZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180014fb7  mov     rax, r14
0x180014fba  add     rsp, 58h
0x180014fbe  pop     r15
0x180014fc0  pop     r14
0x180014fc2  pop     rdi
0x180014fc3  pop     rsi
0x180014fc4  pop     rbp
0x180014fc5  pop     rbx
0x180014fc6  retn
0x180014fc7  call    ?_Xlength@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@CAXXZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Xlength(void)
```
