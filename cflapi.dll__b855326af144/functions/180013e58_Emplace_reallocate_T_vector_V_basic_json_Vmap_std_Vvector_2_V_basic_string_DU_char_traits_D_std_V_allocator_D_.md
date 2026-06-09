# ??$_Emplace_reallocate@$$T@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEA$$T@Z

- ea: `0x180013e58`
- end: `0x180013fe4`
- name: `??$_Emplace_reallocate@$$T@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEA$$T@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180018df4`

## callees

- `0x1800137a4`
- `0x180013e58`
- `0x18001a674`
- `0x18001b294`
- `0x1800214b0`
- `0x180022430`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<std::nullptr_t>(
        void **a1,
        char *a2,
        __int64 a3)
{
  char *v3; // rbx
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // r14
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  char *v11; // rbp
  char *v12; // r12
  char *v13; // r14
  char *v14; // r8
  char *v15; // rcx
  char *v16; // rdx
  char *v17; // rcx
  _QWORD v19[3]; // [rsp+20h] [rbp-58h] BYREF
  char *v20; // [rsp+38h] [rbp-40h]
  char *v21; // [rsp+40h] [rbp-38h]
  __int64 v22; // [rsp+90h] [rbp+18h] BYREF

  v22 = a3;
  v3 = a2;
  v5 = ((_BYTE *)a1[1] - (_BYTE *)*a1) >> 4;
  v6 = 0xFFFFFFFFFFFFFFFLL;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Xlength();
  v7 = a2 - (_BYTE *)*a1;
  v8 = v5 + 1;
  v9 = ((_BYTE *)a1[2] - (_BYTE *)*a1) >> 4;
  v10 = v9 >> 1;
  if ( v9 <= 0xFFFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v6 = v10 + v9;
    if ( v10 + v9 < v8 )
      v6 = v5 + 1;
  }
  v22 = v6;
  v11 = (char *)std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
                  v9,
                  &v22);
  v12 = &v11[v7 & 0xFFFFFFFFFFFFFFF0uLL];
  v13 = v12 + 16;
  v19[0] = a1;
  v19[2] = v6;
  v21 = v12 + 16;
  *v12 = 0;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
    (_QWORD *)v12 + 1,
    0);
  v20 = v12;
  v14 = (char *)a1[1];
  v15 = (char *)*a1;
  v16 = v11;
  if ( v3 == v14 )
  {
    while ( v15 != v14 )
    {
      *v16 = *v15;
      *((_QWORD *)v16 + 1) = *((_QWORD *)v15 + 1);
      *v15 = 0;
      *((_QWORD *)v15 + 1) = 0;
      v16 += 16;
      v15 += 16;
    }
  }
  else
  {
    while ( v15 != v3 )
    {
      *v16 = *v15;
      *((_QWORD *)v16 + 1) = *((_QWORD *)v15 + 1);
      *v15 = 0;
      *((_QWORD *)v15 + 1) = 0;
      v16 += 16;
      v15 += 16;
    }
    v20 = v11;
    v17 = (char *)a1[1];
    while ( v3 != v17 )
    {
      *v13 = *v3;
      *((_QWORD *)v13 + 1) = *((_QWORD *)v3 + 1);
      *v3 = 0;
      *((_QWORD *)v3 + 1) = 0;
      v13 += 16;
      v3 += 16;
    }
  }
  v19[1] = 0;
  std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Change_array(
    a1,
    v11,
    v8,
    v6);
  std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Reallocation_guard::~_Reallocation_guard(v19);
  return v12;
}

```

## disassembly

```asm
0x180013e58  mov     [rsp+arg_0], rbx
0x180013e5d  mov     [rsp+arg_8], rbp
0x180013e62  mov     [rsp+arg_10], r8
0x180013e67  push    rsi
0x180013e68  push    rdi
0x180013e69  push    r12
0x180013e6b  push    r14
0x180013e6d  push    r15
0x180013e6f  sub     rsp, 50h
0x180013e73  mov     rbx, rdx
0x180013e76  mov     rsi, rcx
0x180013e79  mov     rax, [rcx+8]
0x180013e7d  sub     rax, [rcx]
0x180013e80  sar     rax, 4
0x180013e84  mov     rdi, 0FFFFFFFFFFFFFFFh
0x180013e8e  cmp     rax, rdi
0x180013e91  jz      loc_180013FDE
0x180013e97  mov     r14, rdx
0x180013e9a  sub     r14, [rcx]
0x180013e9d  lea     r15, [rax+1]
0x180013ea1  mov     rcx, [rcx+10h]
0x180013ea5  sub     rcx, [rsi]
0x180013ea8  sar     rcx, 4
0x180013eac  mov     rdx, rcx
0x180013eaf  shr     rdx, 1
0x180013eb2  mov     rax, rdi
0x180013eb5  sub     rax, rdx
0x180013eb8  cmp     rcx, rax
0x180013ebb  ja      short loc_180013EC8
0x180013ebd  lea     rdi, [rdx+rcx]
0x180013ec1  cmp     rdi, r15
0x180013ec4  cmovb   rdi, r15
0x180013ec8  mov     [rsp+78h+arg_10], rdi
0x180013ed0  lea     rdx, [rsp+78h+arg_10]
0x180013ed8  call    ??$_Allocate_at_least_helper@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@YAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEAV?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@0@AEA_K@Z; std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>(std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>> &,unsigned __int64 &)
0x180013edd  mov     rbp, rax
0x180013ee0  and     r14, 0FFFFFFFFFFFFFFF0h
0x180013ee4  lea     r12, [r14+rax]
0x180013ee8  lea     r14, [r12+10h]
0x180013eed  mov     [rsp+78h+var_58], rsi
0x180013ef2  mov     [rsp+78h+var_48], rdi
0x180013ef7  mov     [rsp+78h+var_38], r14
0x180013efc  mov     byte ptr [r12], 0
0x180013f01  lea     rcx, [r12+8]
0x180013f06  xor     edx, edx
0x180013f08  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x180013f0d  nop
0x180013f0e  mov     [rsp+78h+var_40], r12
0x180013f13  mov     r8, [rsi+8]
0x180013f17  mov     rcx, [rsi]
0x180013f1a  mov     rdx, rbp
0x180013f1d  cmp     rbx, r8
0x180013f20  jnz     short loc_180013F69
0x180013f22  jmp     short loc_180013F43
0x180013f24  mov     al, [rcx]
0x180013f26  mov     [rdx], al
0x180013f28  mov     rax, [rcx+8]
0x180013f2c  mov     [rdx+8], rax
0x180013f30  mov     byte ptr [rcx], 0
0x180013f33  mov     qword ptr [rcx+8], 0
0x180013f3b  lea     rdx, [rdx+10h]
0x180013f3f  add     rcx, 10h
0x180013f43  cmp     rcx, r8
0x180013f46  jnz     short loc_180013F24
0x180013f48  jmp     short loc_180013F9E
0x180013f4a  mov     al, [rcx]
0x180013f4c  mov     [rdx], al
0x180013f4e  mov     rax, [rcx+8]
0x180013f52  mov     [rdx+8], rax
0x180013f56  mov     byte ptr [rcx], 0
0x180013f59  mov     qword ptr [rcx+8], 0
0x180013f61  lea     rdx, [rdx+10h]
0x180013f65  add     rcx, 10h
0x180013f69  cmp     rcx, rbx
0x180013f6c  jnz     short loc_180013F4A
0x180013f6e  mov     [rsp+78h+var_40], rbp
0x180013f73  mov     rcx, [rsi+8]
0x180013f77  jmp     short loc_180013F99
0x180013f79  mov     al, [rbx]
0x180013f7b  mov     [r14], al
0x180013f7e  mov     rax, [rbx+8]
0x180013f82  mov     [r14+8], rax
0x180013f86  mov     byte ptr [rbx], 0
0x180013f89  mov     qword ptr [rbx+8], 0
0x180013f91  lea     r14, [r14+10h]
0x180013f95  add     rbx, 10h
0x180013f99  cmp     rbx, rcx
0x180013f9c  jnz     short loc_180013F79
0x180013f9e  mov     [rsp+78h+var_50], 0
0x180013fa7  mov     r9, rdi
0x180013faa  mov     r8, r15
0x180013fad  mov     rdx, rbp
0x180013fb0  mov     rcx, rsi
0x180013fb3  call    ?_Change_array@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAXQEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@_K1@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Change_array(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,unsigned __int64,unsigned __int64)
0x180013fb8  lea     rcx, [rsp+78h+var_58]
0x180013fbd  call    ??1_Reallocation_guard@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@QEAA@XZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180013fc2  mov     rax, r12
0x180013fc5  lea     r11, [rsp+78h+var_28]
0x180013fca  mov     rbx, [r11+30h]
0x180013fce  mov     rbp, [r11+38h]
0x180013fd2  mov     rsp, r11
0x180013fd5  pop     r15
0x180013fd7  pop     r14
0x180013fd9  pop     r12
0x180013fdb  pop     rdi
0x180013fdc  pop     rsi
0x180013fdd  retn
0x180013fde  call    ?_Xlength@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@CAXXZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Xlength(void)
```
