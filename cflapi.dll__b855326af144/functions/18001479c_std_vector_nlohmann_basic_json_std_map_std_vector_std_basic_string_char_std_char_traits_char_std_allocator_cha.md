# std::vector<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> *>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> * const &>(nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> * * const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> * const &)

- ea: `0x18001479c`
- end: `0x180014923`
- name: `??$_Emplace_reallocate@AEBQEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAPEAV23@AEBQEAV23@@Z`
- size: `391`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180017b94`
- `0x180018df4`

## callees

- `0x180002860`
- `0x18000289c`
- `0x18000fc2c`
- `0x18001479c`
- `0x180022430`
- `0x18002e008`

## pseudocode

```c
char *__fastcall std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> * const &>(
        _QWORD *a1,
        _BYTE *a2,
        _QWORD *a3)
{
  _BYTE *v3; // rbp
  __int64 v6; // r9
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // r12
  unsigned __int64 v11; // rsi
  size_t v12; // rsi
  _QWORD *v13; // rbx
  void *v14; // rax
  _QWORD *v15; // r15
  void *v16; // rcx
  _BYTE *v17; // r8
  _BYTE *v18; // rdx
  size_t v19; // r8
  _BYTE *v20; // rcx
  _BYTE *v21; // rax
  char *result; // rax

  v3 = (_BYTE *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Xlength();
  v8 = (__int64)(a1[2] - (_QWORD)v3) >> 3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_24;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_24;
  v12 = 8 * v11;
  if ( !v12 )
  {
    v13 = 0;
    goto LABEL_13;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_13;
  }
  if ( v12 + 39 < v12 )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    goto LABEL_19;
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_13:
  v15 = &v13[(a2 - v3) >> 3];
  *v15 = *a3;
  v16 = v13;
  v17 = (_BYTE *)a1[1];
  v18 = (_BYTE *)*a1;
  if ( a2 == v17 )
  {
    v19 = v17 - v18;
  }
  else
  {
    memmove_0(v13, v18, (size_t)&a2[-*a1]);
    v16 = v15 + 1;
    v19 = a1[1] - (_QWORD)a2;
    v18 = a2;
  }
  memmove_0(v16, v18, v19);
  v20 = (_BYTE *)*a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(8 * ((__int64)(a1[2] - (_QWORD)v20) >> 3)) < 0x1000 )
    {
      v21 = (_BYTE *)*a1;
    }
    else
    {
      v21 = (_BYTE *)*((_QWORD *)v20 - 1);
      if ( (unsigned __int64)(v20 - v21 - 8) > 0x1F )
LABEL_19:
        __fastfail(5u);
    }
    operator delete(v21);
  }
  *a1 = v13;
  a1[1] = &v13[v10];
  result = (char *)&v13[(a2 - v3) >> 3];
  a1[2] = &v13[v12 / 8];
  return result;
}

```

## disassembly

```asm
0x18001479c  push    rbx
0x18001479e  push    rbp
0x18001479f  push    rsi
0x1800147a0  push    rdi
0x1800147a1  push    r12
0x1800147a3  push    r13
0x1800147a5  push    r14
0x1800147a7  push    r15
0x1800147a9  sub     rsp, 28h
0x1800147ad  mov     rbp, [rcx]
0x1800147b0  mov     r13, r8
0x1800147b3  mov     r9, [rcx+8]
0x1800147b7  mov     r8, 1FFFFFFFFFFFFFFFh
0x1800147c1  sub     r9, rbp
0x1800147c4  mov     r14, rdx
0x1800147c7  sar     r9, 3
0x1800147cb  mov     rdi, rcx
0x1800147ce  cmp     r9, r8
0x1800147d1  jz      loc_180014917
0x1800147d7  mov     rcx, [rcx+10h]
0x1800147db  mov     rax, r8
0x1800147de  sub     rcx, rbp
0x1800147e1  sar     rcx, 3
0x1800147e5  mov     rdx, rcx
0x1800147e8  shr     rdx, 1
0x1800147eb  sub     rax, rdx
0x1800147ee  cmp     rcx, rax
0x1800147f1  ja      loc_18001491D
0x1800147f7  lea     r12, [r9+1]
0x1800147fb  lea     rax, [rcx+rdx]
0x1800147ff  mov     rsi, r12
0x180014802  cmp     rax, r12
0x180014805  cmovnb  rsi, rax
0x180014809  cmp     rsi, r8
0x18001480c  ja      loc_18001491D
0x180014812  shl     rsi, 3
0x180014816  test    rsi, rsi
0x180014819  jnz     short loc_18001481F
0x18001481b  xor     ebx, ebx
0x18001481d  jmp     short loc_18001485C
0x18001481f  cmp     rsi, 1000h
0x180014826  jb      short loc_180014851
0x180014828  lea     rcx, [rsi+27h]; Size
0x18001482c  cmp     rcx, rsi
0x18001482f  jbe     loc_18001491D
0x180014835  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001483a  test    rax, rax
0x18001483d  jz      loc_1800148DE
0x180014843  lea     rbx, [rax+27h]
0x180014847  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001484b  mov     [rbx-8], rax
0x18001484f  jmp     short loc_18001485C
0x180014851  mov     rcx, rsi; Size
0x180014854  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014859  mov     rbx, rax
0x18001485c  mov     rcx, r14
0x18001485f  sub     rcx, rbp
0x180014862  sar     rcx, 3
0x180014866  lea     r15, [rbx+rcx*8]
0x18001486a  mov     rcx, [r13+0]
0x18001486e  mov     [r15], rcx
0x180014871  mov     rcx, rbx; void *
0x180014874  mov     r8, [rdi+8]
0x180014878  mov     rdx, [rdi]; Src
0x18001487b  cmp     r14, r8
0x18001487e  jnz     short loc_180014885
0x180014880  sub     r8, rdx
0x180014883  jmp     short loc_18001489E
0x180014885  mov     r8, r14
0x180014888  sub     r8, [rdi]; Size
0x18001488b  call    memmove_0
0x180014890  mov     r8, [rdi+8]
0x180014894  lea     rcx, [r15+8]; void *
0x180014898  sub     r8, r14; Size
0x18001489b  mov     rdx, r14; Src
0x18001489e  call    memmove_0
0x1800148a3  mov     rcx, [rdi]
0x1800148a6  test    rcx, rcx
0x1800148a9  jz      short loc_1800148F0
0x1800148ab  mov     rax, [rdi+10h]
0x1800148af  sub     rax, rcx
0x1800148b2  sar     rax, 3
0x1800148b6  lea     rdx, ds:0[rax*8]; unsigned __int64
0x1800148be  cmp     rdx, 1000h
0x1800148c5  jb      short loc_1800148E5
0x1800148c7  mov     rax, [rcx-8]
0x1800148cb  sub     rcx, rax
0x1800148ce  sub     rcx, 8
0x1800148d2  cmp     rcx, 1Fh
0x1800148d6  ja      short loc_1800148DE
0x1800148d8  add     rdx, 27h ; '''
0x1800148dc  jmp     short loc_1800148E8
0x1800148de  mov     ecx, 5
0x1800148e3  int     29h; Win8: RtlFailFast(ecx)
0x1800148e5  mov     rax, rcx
0x1800148e8  mov     rcx, rax; void *
0x1800148eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800148f0  lea     rcx, [rbx+r12*8]
0x1800148f4  mov     [rdi], rbx
0x1800148f7  mov     [rdi+8], rcx
0x1800148fb  mov     rax, r15
0x1800148fe  lea     rcx, [rsi+rbx]
0x180014902  mov     [rdi+10h], rcx
0x180014906  add     rsp, 28h
0x18001490a  pop     r15
0x18001490c  pop     r14
0x18001490e  pop     r13
0x180014910  pop     r12
0x180014912  pop     rdi
0x180014913  pop     rsi
0x180014914  pop     rbp
0x180014915  pop     rbx
0x180014916  retn
0x180014917  call    ?_Xlength@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@CAXXZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Xlength(void)
0x18001491d  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
