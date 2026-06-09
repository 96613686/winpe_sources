# nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::handle_value<std::basic_string<char,std::char_traits<char>,std::allocator<char>> &>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,bool)

- ea: `0x1800171a0`
- end: `0x18001739b`
- name: `??$handle_value@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAA?AU?$pair@_NPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@_N@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180017b94`

## callees

- `0x18000289c`
- `0x180014e64`
- `0x1800171a0`
- `0x180019eac`
- `0x18002258c`
- `0x180022cf4`
- `0x18002588c`
- `0x180030010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180017245`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180017245`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<std::string &>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v7; // rax
  void *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int8 v11; // al
  void *v12; // r8
  unsigned __int8 *v13; // rcx
  unsigned __int8 v14; // dl
  void *v15; // rax
  unsigned __int8 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // ebx
  unsigned __int8 v22; // al
  void *v23; // r8
  __int64 v24; // rcx
  unsigned __int8 v25; // dl
  void *v26; // rax
  unsigned __int8 v28[8]; // [rsp+30h] [rbp-20h] BYREF
  void *v29; // [rsp+38h] [rbp-18h] BYREF
  char *v30; // [rsp+40h] [rbp-10h] BYREF
  void *v31; // [rsp+48h] [rbp-8h] BYREF
  int v32; // [rsp+70h] [rbp+20h] BYREF
  char v33; // [rsp+88h] [rbp+38h] BYREF

  v33 = a4;
  v7 = std::vector<bool>::back(a1 + 32, &v30);
  if ( ((1 << *(_QWORD *)(v7 + 8)) & **(_DWORD **)v7) != 0 )
  {
    v28[0] = 3;
    v8 = operator new(0x20u);
    v30 = &v33;
    v31 = v8;
    std::string::string(v8, a3);
    v29 = v8;
    v33 = 5;
    v32 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3;
    v9 = *(_QWORD *)(a1 + 168);
    if ( !v9 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, int *, char *, unsigned __int8 *))(*(_QWORD *)v9 + 16LL))(
            v9,
            &v32,
            &v33,
            v28) )
      goto LABEL_6;
    v10 = *(_QWORD *)(a1 + 16);
    if ( *(_QWORD *)(a1 + 8) == v10 )
    {
      v11 = v28[0];
      v12 = v29;
      v28[0] = 0;
      v29 = 0;
      v13 = *(unsigned __int8 **)a1;
      v14 = **(_BYTE **)a1;
      *v13 = v11;
      LOBYTE(v30) = v14;
      v15 = (void *)*((_QWORD *)v13 + 1);
      *((_QWORD *)v13 + 1) = v12;
      v31 = v15;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        &v31,
        v14);
      v16 = *(unsigned __int8 **)a1;
    }
    else
    {
      v17 = *(_QWORD *)(v10 - 8);
      if ( !v17 )
        goto LABEL_6;
      if ( *(_BYTE *)v17 == 2 )
      {
        v18 = *(_QWORD *)(v17 + 8);
        v19 = *(_QWORD *)(v18 + 8);
        if ( v19 == *(_QWORD *)(v18 + 16) )
        {
          std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
            (void **)v18,
            (char *)v19,
            (__int64)v28);
        }
        else
        {
          *(_BYTE *)v19 = v28[0];
          *(_QWORD *)(v19 + 8) = v29;
          v28[0] = 0;
          v29 = 0;
          *(_QWORD *)(v18 + 8) += 16LL;
        }
        *(_QWORD *)(a2 + 8) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) - 8LL) + 8LL) + 8LL) - 16LL;
        goto LABEL_18;
      }
      v20 = std::vector<bool>::back(a1 + 64, &v30);
      v21 = **(_DWORD **)v20 & (1 << *(_QWORD *)(v20 + 8));
      std::vector<bool>::pop_back(a1 + 64);
      if ( !v21 )
      {
LABEL_6:
        *(_BYTE *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
LABEL_19:
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v29,
          v28[0]);
        return a2;
      }
      v22 = v28[0];
      v23 = v29;
      v28[0] = 0;
      v29 = 0;
      v24 = *(_QWORD *)(a1 + 96);
      v25 = *(_BYTE *)v24;
      *(_BYTE *)v24 = v22;
      LOBYTE(v30) = v25;
      v26 = *(void **)(v24 + 8);
      *(_QWORD *)(v24 + 8) = v23;
      v31 = v26;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        &v31,
        v25);
      v16 = *(unsigned __int8 **)(a1 + 96);
    }
    *(_QWORD *)(a2 + 8) = v16;
LABEL_18:
    *(_BYTE *)a2 = 1;
    goto LABEL_19;
  }
  *(_BYTE *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x1800171a0  mov     [rsp-18h+arg_8], rbx
0x1800171a5  mov     [rsp-18h+arg_10], rsi
0x1800171aa  mov     [rsp-18h+arg_18], r9b
0x1800171af  push    rbp
0x1800171b0  push    rdi
0x1800171b1  push    r14
0x1800171b3  mov     rbp, rsp
0x1800171b6  sub     rsp, 50h
0x1800171ba  mov     rsi, r8
0x1800171bd  mov     rdi, rdx
0x1800171c0  mov     r14, rcx
0x1800171c3  add     rcx, 20h ; ' '
0x1800171c7  lea     rdx, [rbp+var_10]
0x1800171cb  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x1800171d0  mov     rcx, [rax+8]
0x1800171d4  mov     r9d, 1
0x1800171da  shl     r9d, cl
0x1800171dd  mov     rax, [rax]
0x1800171e0  test    [rax], r9d
0x1800171e3  jnz     short loc_1800171F3
0x1800171e5  xor     esi, esi
0x1800171e7  mov     [rdi], sil
0x1800171ea  mov     [rdi+8], rsi
0x1800171ee  jmp     loc_180017383
0x1800171f3  xor     eax, eax
0x1800171f5  mov     [rbp+var_18], rax
0x1800171f9  mov     [rbp+var_20], 3
0x1800171fd  lea     ecx, [rax+20h]; Size
0x180017200  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017205  mov     rbx, rax
0x180017208  lea     rax, [rbp+arg_18]
0x18001720c  mov     [rbp+var_10], rax
0x180017210  mov     [rbp+var_8], rbx
0x180017214  mov     rdx, rsi
0x180017217  mov     rcx, rbx
0x18001721a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001721f  nop
0x180017220  mov     [rbp+var_18], rbx
0x180017224  mov     [rbp+arg_18], 5
0x180017228  mov     rax, [r14+10h]
0x18001722c  sub     rax, [r14+8]
0x180017230  sar     rax, 3
0x180017234  mov     [rbp+arg_0], eax
0x180017237  mov     rcx, [r14+0A8h]
0x18001723e  xor     esi, esi
0x180017240  test    rcx, rcx
0x180017243  jnz     short loc_18001724C
0x180017245  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001724b  int     3; Trap to Debugger
0x18001724c  mov     rax, [rcx]
0x18001724f  lea     r9, [rbp+var_20]
0x180017253  lea     r8, [rbp+arg_18]
0x180017257  lea     rdx, [rbp+arg_0]
0x18001725b  mov     rax, [rax+10h]
0x18001725f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017264  test    al, al
0x180017266  jnz     short loc_180017274
0x180017268  mov     [rdi], sil
0x18001726b  mov     [rdi+8], rsi
0x18001726f  jmp     loc_180017377
0x180017274  mov     rcx, [r14+10h]
0x180017278  cmp     [r14+8], rcx
0x18001727c  jnz     short loc_1800172B4
0x18001727e  mov     al, [rbp+var_20]
0x180017281  mov     r8, [rbp+var_18]
0x180017285  mov     [rbp+var_20], sil
0x180017289  mov     [rbp+var_18], rsi
0x18001728d  mov     rcx, [r14]
0x180017290  mov     dl, [rcx]
0x180017292  mov     [rcx], al
0x180017294  mov     byte ptr [rbp+var_10], dl
0x180017297  mov     rax, [rcx+8]
0x18001729b  mov     [rcx+8], r8
0x18001729f  mov     [rbp+var_8], rax
0x1800172a3  lea     rcx, [rbp+var_8]
0x1800172a7  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800172ac  mov     rax, [r14]
0x1800172af  jmp     loc_180017370
0x1800172b4  mov     rcx, [rcx-8]
0x1800172b8  test    rcx, rcx
0x1800172bb  jz      short loc_180017268
0x1800172bd  cmp     byte ptr [rcx], 2
0x1800172c0  jnz     short loc_18001730F
0x1800172c2  mov     rcx, [rcx+8]
0x1800172c6  mov     rdx, [rcx+8]
0x1800172ca  cmp     rdx, [rcx+10h]
0x1800172ce  jz      short loc_1800172EC
0x1800172d0  mov     al, [rbp+var_20]
0x1800172d3  mov     [rdx], al
0x1800172d5  mov     rax, [rbp+var_18]
0x1800172d9  mov     [rdx+8], rax
0x1800172dd  mov     [rbp+var_20], sil
0x1800172e1  mov     [rbp+var_18], rsi
0x1800172e5  add     qword ptr [rcx+8], 10h
0x1800172ea  jmp     short loc_1800172F5
0x1800172ec  lea     r8, [rbp+var_20]
0x1800172f0  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x1800172f5  mov     rax, [r14+10h]
0x1800172f9  mov     rcx, [rax-8]
0x1800172fd  mov     rax, [rcx+8]
0x180017301  mov     rcx, [rax+8]
0x180017305  sub     rcx, 10h
0x180017309  mov     [rdi+8], rcx
0x18001730d  jmp     short loc_180017374
0x18001730f  lea     rdx, [rbp+var_10]
0x180017313  lea     rcx, [r14+40h]
0x180017317  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x18001731c  mov     rcx, [rax+8]
0x180017320  mov     ebx, 1
0x180017325  shl     ebx, cl
0x180017327  mov     rax, [rax]
0x18001732a  and     ebx, [rax]
0x18001732c  lea     rcx, [r14+40h]
0x180017330  call    ?pop_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXXZ; std::vector<bool>::pop_back(void)
0x180017335  test    ebx, ebx
0x180017337  jz      loc_180017268
0x18001733d  mov     al, [rbp+var_20]
0x180017340  mov     r8, [rbp+var_18]
0x180017344  mov     [rbp+var_20], sil
0x180017348  mov     [rbp+var_18], rsi
0x18001734c  mov     rcx, [r14+60h]
0x180017350  mov     dl, [rcx]
0x180017352  mov     [rcx], al
0x180017354  mov     byte ptr [rbp+var_10], dl
0x180017357  mov     rax, [rcx+8]
0x18001735b  mov     [rcx+8], r8
0x18001735f  mov     [rbp+var_8], rax
0x180017363  lea     rcx, [rbp+var_8]
0x180017367  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001736c  mov     rax, [r14+60h]
0x180017370  mov     [rdi+8], rax
0x180017374  mov     byte ptr [rdi], 1
0x180017377  mov     dl, [rbp+var_20]
0x18001737a  lea     rcx, [rbp+var_18]
0x18001737e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180017383  mov     rax, rdi
0x180017386  lea     r11, [rsp+50h+var_s0]
0x18001738b  mov     rbx, [r11+28h]
0x18001738f  mov     rsi, [r11+30h]
0x180017393  mov     rsp, r11
0x180017396  pop     r14
0x180017398  pop     rdi
0x180017399  pop     rbp
0x18001739a  retn
```
