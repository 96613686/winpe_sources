# std::vector<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>::_Emplace_reallocate<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>(nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> * const,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180014170`
- end: `0x180014325`
- name: `??$_Emplace_reallocate@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180018df4`

## callees

- `0x18000289c`
- `0x1800137a4`
- `0x180014170`
- `0x180019eac`
- `0x18001b294`
- `0x1800214b0`
- `0x180022430`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<std::string &>(
        void **a1,
        char *a2,
        __int64 a3)
{
  char *v3; // r14
  __int64 v5; // rax
  __int64 v6; // r15
  __int64 v7; // rsi
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  char *v10; // r12
  char *v11; // rdi
  char *v12; // r9
  char *v13; // rcx
  char *v14; // r8
  __int64 v15; // rsi
  char *v16; // r8
  char *v17; // rcx
  void *v19; // [rsp+28h] [rbp-38h]
  void **v20; // [rsp+30h] [rbp-30h] BYREF
  char *v21; // [rsp+38h] [rbp-28h]
  __int64 v22; // [rsp+40h] [rbp-20h]
  char *v23; // [rsp+48h] [rbp-18h]
  char *v24; // [rsp+50h] [rbp-10h]
  __int64 v25; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h]
  __int64 v27; // [rsp+B0h] [rbp+50h]

  v27 = a3;
  v3 = a2;
  v5 = ((_BYTE *)a1[1] - (_BYTE *)*a1) >> 4;
  v6 = 0xFFFFFFFFFFFFFFFLL;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Xlength();
  v7 = (a2 - (_BYTE *)*a1) >> 4;
  v26 = v5 + 1;
  v8 = ((_BYTE *)a1[2] - (_BYTE *)*a1) >> 4;
  v9 = v8 >> 1;
  if ( v8 <= 0xFFFFFFFFFFFFFFFLL - (v8 >> 1) )
  {
    v6 = v8 + v9;
    if ( v8 + v9 < v5 + 1 )
      v6 = v5 + 1;
  }
  v25 = v6;
  v10 = (char *)std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
                  v8,
                  &v25);
  v11 = &v10[16 * v7];
  v20 = a1;
  v21 = v10;
  v22 = v6;
  v24 = v11 + 16;
  *((_QWORD *)v11 + 1) = 0;
  *v11 = 3;
  v19 = operator new(0x20u);
  std::string::string(v19, v27);
  *((_QWORD *)v11 + 1) = v19;
  v23 = v11;
  v12 = (char *)a1[1];
  v13 = (char *)*a1;
  v14 = v10;
  if ( v3 == v12 )
  {
    while ( v13 != v12 )
    {
      *v14 = *v13;
      *((_QWORD *)v14 + 1) = *((_QWORD *)v13 + 1);
      *v13 = 0;
      *((_QWORD *)v13 + 1) = 0;
      v14 += 16;
      v13 += 16;
    }
    v15 = 16 * v7;
  }
  else
  {
    while ( v13 != v3 )
    {
      *v14 = *v13;
      *((_QWORD *)v14 + 1) = *((_QWORD *)v13 + 1);
      *v13 = 0;
      *((_QWORD *)v13 + 1) = 0;
      v14 += 16;
      v13 += 16;
    }
    v23 = v10;
    v15 = 16 * v7;
    v16 = (char *)a1[1];
    v17 = &v10[v15 + 16];
    while ( v3 != v16 )
    {
      *v17 = *v3;
      *((_QWORD *)v17 + 1) = *((_QWORD *)v3 + 1);
      *v3 = 0;
      *((_QWORD *)v3 + 1) = 0;
      v17 += 16;
      v3 += 16;
    }
  }
  v21 = 0;
  std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Change_array(
    a1,
    v10,
    v26,
    v6);
  std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Reallocation_guard::~_Reallocation_guard(&v20);
  return &v10[v15];
}

```

## disassembly

```asm
0x180014170  mov     [rsp-38h+arg_18], rbx
0x180014175  mov     [rsp-38h+arg_10], r8
0x18001417a  push    rbp
0x18001417b  push    rsi
0x18001417c  push    rdi
0x18001417d  push    r12
0x18001417f  push    r13
0x180014181  push    r14
0x180014183  push    r15
0x180014185  mov     rbp, rsp
0x180014188  sub     rsp, 60h
0x18001418c  mov     r14, rdx
0x18001418f  mov     r13, rcx
0x180014192  mov     rax, [rcx+8]
0x180014196  sub     rax, [rcx]
0x180014199  sar     rax, 4
0x18001419d  mov     r15, 0FFFFFFFFFFFFFFFh
0x1800141a7  cmp     rax, r15
0x1800141aa  jz      loc_18001431F
0x1800141b0  mov     rsi, rdx
0x1800141b3  sub     rsi, [rcx]
0x1800141b6  sar     rsi, 4
0x1800141ba  lea     r8, [rax+1]
0x1800141be  mov     [rbp+arg_8], r8
0x1800141c2  mov     rcx, [rcx+10h]
0x1800141c6  sub     rcx, [r13+0]
0x1800141ca  sar     rcx, 4
0x1800141ce  mov     rdx, rcx
0x1800141d1  shr     rdx, 1
0x1800141d4  mov     rax, r15
0x1800141d7  sub     rax, rdx
0x1800141da  cmp     rcx, rax
0x1800141dd  ja      short loc_1800141EA
0x1800141df  lea     r15, [rcx+rdx]
0x1800141e3  cmp     r15, r8
0x1800141e6  cmovb   r15, r8
0x1800141ea  mov     [rbp+arg_0], r15
0x1800141ee  lea     rdx, [rbp+arg_0]
0x1800141f2  call    ??$_Allocate_at_least_helper@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@YAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEAV?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@0@AEA_K@Z; std::_Allocate_at_least_helper<std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>(std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>> &,unsigned __int64 &)
0x1800141f7  mov     r12, rax
0x1800141fa  mov     rdi, rsi
0x1800141fd  shl     rdi, 4
0x180014201  add     rdi, rax
0x180014204  lea     rcx, [rdi+10h]
0x180014208  mov     [rbp+var_30], r13
0x18001420c  mov     [rbp+var_28], rax
0x180014210  mov     [rbp+var_20], r15
0x180014214  mov     [rbp+var_18], rcx
0x180014218  mov     [rbp+var_10], rcx
0x18001421c  xor     eax, eax
0x18001421e  mov     [rdi+8], rax
0x180014222  mov     byte ptr [rdi], 3
0x180014225  lea     ecx, [rax+20h]; Size
0x180014228  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001422d  mov     rbx, rax
0x180014230  lea     rax, [rbp+arg_0]
0x180014234  mov     [rbp+var_40], rax
0x180014238  mov     [rbp+var_38], rbx
0x18001423c  mov     rdx, [rbp+arg_10]
0x180014240  mov     rcx, rbx
0x180014243  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180014248  nop
0x180014249  mov     [rdi+8], rbx
0x18001424d  mov     [rbp+var_18], rdi
0x180014251  mov     r9, [r13+8]
0x180014255  mov     rcx, [r13+0]
0x180014259  mov     r8, r12
0x18001425c  xor     edx, edx
0x18001425e  cmp     r14, r9
0x180014261  jnz     short loc_1800142A6
0x180014263  jmp     short loc_180014280
0x180014265  mov     al, [rcx]
0x180014267  mov     [r8], al
0x18001426a  mov     rax, [rcx+8]
0x18001426e  mov     [r8+8], rax
0x180014272  mov     [rcx], dl
0x180014274  mov     [rcx+8], rdx
0x180014278  lea     r8, [r8+10h]
0x18001427c  add     rcx, 10h
0x180014280  cmp     rcx, r9
0x180014283  jnz     short loc_180014265
0x180014285  shl     rsi, 4
0x180014289  jmp     short loc_1800142E1
0x18001428b  mov     al, [rcx]
0x18001428d  mov     [r8], al
0x180014290  mov     rax, [rcx+8]
0x180014294  mov     [r8+8], rax
0x180014298  mov     [rcx], dl
0x18001429a  mov     [rcx+8], rdx
0x18001429e  lea     r8, [r8+10h]
0x1800142a2  add     rcx, 10h
0x1800142a6  cmp     rcx, r14
0x1800142a9  jnz     short loc_18001428B
0x1800142ab  mov     [rbp+var_18], r12
0x1800142af  shl     rsi, 4
0x1800142b3  mov     r8, [r13+8]
0x1800142b7  lea     rcx, [rsi+10h]
0x1800142bb  add     rcx, r12
0x1800142be  jmp     short loc_1800142DC
0x1800142c0  mov     al, [r14]
0x1800142c3  mov     [rcx], al
0x1800142c5  mov     rax, [r14+8]
0x1800142c9  mov     [rcx+8], rax
0x1800142cd  mov     [r14], dl
0x1800142d0  mov     [r14+8], rdx
0x1800142d4  lea     rcx, [rcx+10h]
0x1800142d8  add     r14, 10h
0x1800142dc  cmp     r14, r8
0x1800142df  jnz     short loc_1800142C0
0x1800142e1  mov     [rbp+var_28], rdx
0x1800142e5  mov     r9, r15
0x1800142e8  mov     r8, [rbp+arg_8]
0x1800142ec  mov     rdx, r12
0x1800142ef  mov     rcx, r13
0x1800142f2  call    ?_Change_array@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAXQEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@_K1@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Change_array(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,unsigned __int64,unsigned __int64)
0x1800142f7  lea     rbx, [rsi+r12]
0x1800142fb  lea     rcx, [rbp+var_30]
0x1800142ff  call    ??1_Reallocation_guard@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@QEAA@XZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180014304  mov     rax, rbx
0x180014307  mov     rbx, [rsp+60h+arg_18]
0x18001430f  add     rsp, 60h
0x180014313  pop     r15
0x180014315  pop     r14
0x180014317  pop     r13
0x180014319  pop     r12
0x18001431b  pop     rdi
0x18001431c  pop     rsi
0x18001431d  pop     rbp
0x18001431e  retn
0x18001431f  call    ?_Xlength@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@CAXXZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Xlength(void)
```
