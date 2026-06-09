# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::dump(int,char,bool,nlohmann::detail::error_handler_t)

- ea: `0x1800230a8`
- end: `0x180023305`
- name: `?dump@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HD_NW4error_handler_t@detail@2@@Z`
- size: `605`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fb28`
- `0x18002b264`

## callees

- `0x180002490`
- `0x18000289c`
- `0x180002ef8`
- `0x180008a68`
- `0x18001a1e8`
- `0x1800230a8`
- `0x18002330c`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_localeconv` at `0x180023186`
- `api-ms-win-crt-private-l1-1-0!_o_localeconv` at `0x180023186`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::dump(
        unsigned __int8 *a1,
        __int64 a2)
{
  char *v4; // rdi
  struct lconv *v5; // rcx
  char *thousands_sep; // rax
  volatile signed __int32 *v7; // rbx
  __int64 *v9; // [rsp+70h] [rbp-90h] BYREF
  volatile signed __int32 *v10; // [rsp+78h] [rbp-88h]
  char v11[64]; // [rsp+80h] [rbp-80h] BYREF
  struct lconv *v12; // [rsp+C0h] [rbp-40h]
  char v13; // [rsp+C8h] [rbp-38h]
  char v14; // [rsp+C9h] [rbp-37h]
  _BYTE v15[518]; // [rsp+CAh] [rbp-36h] BYREF
  _BYTE v16[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v17; // [rsp+2F0h] [rbp+1F0h]

  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 15;
  *(_BYTE *)a2 = 0;
  v4 = (char *)operator new(0x20u);
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = &std::_Ref_count_obj2<nlohmann::detail::output_string_adapter<char,std::string>>::`vftable';
  *((_QWORD *)v4 + 2) = &nlohmann::detail::output_string_adapter<char,std::string>::`vftable';
  *((_QWORD *)v4 + 3) = a2;
  _InterlockedAdd((volatile signed __int32 *)v4 + 2, 1u);
  v9 = (__int64 *)(v4 + 16);
  v10 = (volatile signed __int32 *)v4;
  memset_0(v11, 0, sizeof(v11));
  v5 = localeconv();
  v12 = v5;
  thousands_sep = v5->thousands_sep;
  if ( thousands_sep )
    v13 = *thousands_sep;
  else
    v13 = 0;
  if ( v5->decimal_point )
    v14 = *v5->decimal_point;
  else
    v14 = 0;
  memset_0(v15, 0, 0x200u);
  v15[512] = 32;
  std::string::string(v16, 512);
  v17 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v4)(v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
    &v9,
    a1,
    0,
    0,
    0,
    0);
  std::string::~string(v16);
  v7 = v10;
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800230a8  mov     [rsp-8+arg_10], rbx
0x1800230ad  push    rbp
0x1800230ae  push    rsi
0x1800230af  push    rdi
0x1800230b0  push    r14
0x1800230b2  push    r15
0x1800230b4  lea     rbp, [rsp-210h]
0x1800230bc  sub     rsp, 310h
0x1800230c3  mov     rax, cs:__security_cookie
0x1800230ca  xor     rax, rsp
0x1800230cd  mov     [rbp+230h+var_30], rax
0x1800230d4  mov     rsi, rdx
0x1800230d7  mov     r14, rcx
0x1800230da  mov     [rsp+330h+var_2E0], rdx
0x1800230df  mov     [rsp+330h+var_300], 0
0x1800230e7  xorps   xmm0, xmm0
0x1800230ea  movups  xmmword ptr [rdx], xmm0
0x1800230ed  mov     qword ptr [rdx+10h], 0
0x1800230f5  mov     qword ptr [rdx+18h], 0Fh
0x1800230fd  mov     byte ptr [rdx], 0
0x180023100  mov     ebx, 1
0x180023105  mov     [rsp+330h+var_300], ebx
0x180023109  lea     ecx, [rbx+1Fh]; Size
0x18002310c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023111  mov     rdi, rax
0x180023114  mov     [rsp+330h+var_2F8], rax
0x180023119  xorps   xmm0, xmm0
0x18002311c  movups  xmmword ptr [rax], xmm0
0x18002311f  mov     [rax+8], ebx
0x180023122  mov     [rax+0Ch], ebx
0x180023125  lea     rax, ??_7?$_Ref_count_obj2@V?$output_string_adapter@DV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@detail@nlohmann@@@std@@6B@; const std::_Ref_count_obj2<nlohmann::detail::output_string_adapter<char,std::string>>::`vftable'
0x18002312c  mov     [rdi], rax
0x18002312f  lea     rax, [rdi+10h]
0x180023133  lea     rcx, ??_7?$output_string_adapter@DV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@detail@nlohmann@@6B@; const nlohmann::detail::output_string_adapter<char,std::string>::`vftable'
0x18002313a  mov     [rax], rcx
0x18002313d  mov     [rax+8], rsi
0x180023141  mov     [rsp+330h+var_300], 3
0x180023149  mov     [rsp+330h+var_2D8], rax
0x18002314e  mov     [rsp+330h+var_2D0], rdi
0x180023153  movdqu  [rsp+330h+var_2F0], xmm0
0x180023159  lock add [rdi+8], ebx
0x18002315d  lea     rcx, [rsp+330h+var_2F0]
0x180023162  mov     [rsp+330h+var_2F8], rcx
0x180023167  mov     [rsp+330h+var_2C0], rax
0x18002316c  mov     [rsp+330h+var_2B8], rdi
0x180023171  movdqu  [rsp+330h+var_2F0], xmm0
0x180023177  xor     edx, edx; Val
0x180023179  lea     r8d, [rbx+3Fh]; Size
0x18002317d  lea     rcx, [rbp+230h+var_2B0]; void *
0x180023181  call    memset_0
0x180023186  call    cs:__imp_localeconv
0x18002318c  mov     rcx, rax
0x18002318f  mov     [rbp+230h+var_270], rax
0x180023193  mov     rax, [rax+8]
0x180023197  test    rax, rax
0x18002319a  jnz     short loc_1800231A1
0x18002319c  mov     [rbp+230h+var_268], al
0x18002319f  jmp     short loc_1800231A6
0x1800231a1  mov     al, [rax]
0x1800231a3  mov     [rbp+230h+var_268], al
0x1800231a6  mov     rax, [rcx]
0x1800231a9  test    rax, rax
0x1800231ac  jnz     short loc_1800231B3
0x1800231ae  mov     [rbp+230h+var_267], al
0x1800231b1  jmp     short loc_1800231B8
0x1800231b3  mov     al, [rax]
0x1800231b5  mov     [rbp+230h+var_267], al
0x1800231b8  mov     ebx, 200h
0x1800231bd  mov     r8d, ebx; Size
0x1800231c0  xor     edx, edx; Val
0x1800231c2  lea     rcx, [rbp+230h+var_266]; void *
0x1800231c6  call    memset_0
0x1800231cb  mov     [rbp+230h+var_66], 20h ; ' '
0x1800231d2  mov     r8b, 20h ; ' '
0x1800231d5  mov     edx, ebx
0x1800231d7  lea     rcx, [rbp+230h+var_60]
0x1800231de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x1800231e3  mov     [rbp+230h+var_40], 0
0x1800231ed  mov     rbx, qword ptr [rsp+330h+var_2F0+8]
0x1800231f2  or      r15d, 0FFFFFFFFh
0x1800231f6  test    rbx, rbx
0x1800231f9  jz      short loc_180023233
0x1800231fb  mov     eax, r15d
0x1800231fe  lock xadd [rbx+8], eax
0x180023203  add     eax, r15d
0x180023206  jnz     short loc_180023233
0x180023208  mov     rax, [rbx]
0x18002320b  mov     rcx, rbx
0x18002320e  mov     rax, [rax]
0x180023211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023216  mov     eax, r15d
0x180023219  lock xadd [rbx+0Ch], eax
0x18002321e  add     eax, r15d
0x180023221  jnz     short loc_180023233
0x180023223  mov     rax, [rbx]
0x180023226  mov     rcx, rbx
0x180023229  mov     rax, [rax+8]
0x18002322d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023232  nop
0x180023233  mov     eax, r15d
0x180023236  lock xadd [rdi+8], eax
0x18002323b  add     eax, r15d
0x18002323e  jnz     short loc_18002326A
0x180023240  mov     rax, [rdi]
0x180023243  mov     rcx, rdi
0x180023246  mov     rax, [rax]
0x180023249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002324e  mov     eax, r15d
0x180023251  lock xadd [rdi+0Ch], eax
0x180023256  add     eax, r15d
0x180023259  jnz     short loc_18002326A
0x18002325b  mov     rax, [rdi]
0x18002325e  mov     rcx, rdi
0x180023261  mov     rax, [rax+8]
0x180023265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002326a  mov     [rsp+330h+var_308], 0
0x180023272  mov     [rsp+330h+var_310], 0
0x18002327a  xor     r9d, r9d
0x18002327d  xor     r8d, r8d
0x180023280  mov     rdx, r14
0x180023283  lea     rcx, [rsp+330h+var_2C0]
0x180023288  call    ?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@_N1II@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &,bool,bool,uint,uint)
0x18002328d  nop
0x18002328e  lea     rcx, [rbp+230h+var_60]
0x180023295  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002329a  mov     rbx, [rsp+330h+var_2B8]
0x18002329f  test    rbx, rbx
0x1800232a2  jz      short loc_1800232DB
0x1800232a4  mov     eax, r15d
0x1800232a7  lock xadd [rbx+8], eax
0x1800232ac  add     eax, r15d
0x1800232af  jnz     short loc_1800232DB
0x1800232b1  mov     rax, [rbx]
0x1800232b4  mov     rcx, rbx
0x1800232b7  mov     rax, [rax]
0x1800232ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232bf  mov     edx, r15d
0x1800232c2  lock xadd [rbx+0Ch], edx
0x1800232c7  add     edx, r15d
0x1800232ca  jnz     short loc_1800232DB
0x1800232cc  mov     rdx, [rbx]
0x1800232cf  mov     rcx, rbx
0x1800232d2  mov     rax, [rdx+8]
0x1800232d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232db  mov     rax, rsi
0x1800232de  mov     rcx, [rbp+230h+var_30]
0x1800232e5  xor     rcx, rsp; StackCookie
0x1800232e8  call    __security_check_cookie
0x1800232ed  mov     rbx, [rsp+330h+arg_10]
0x1800232f5  add     rsp, 310h
0x1800232fc  pop     r15
0x1800232fe  pop     r14
0x180023300  pop     rdi
0x180023301  pop     rsi
0x180023302  pop     rbp
0x180023303  retn
```
