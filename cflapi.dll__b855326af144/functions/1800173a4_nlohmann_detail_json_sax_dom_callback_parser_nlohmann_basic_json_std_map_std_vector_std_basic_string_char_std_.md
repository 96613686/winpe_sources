# nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::handle_value<bool &>(bool &,bool)

- ea: `0x1800173a4`
- end: `0x180017592`
- name: `??$handle_value@AEA_N@?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAA?AU?$pair@_NPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@AEA_N_N@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017b94`

## callees

- `0x180014e64`
- `0x1800173a4`
- `0x18002258c`
- `0x180022cf4`
- `0x18002588c`
- `0x180030010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001743c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001743c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<bool &>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v6; // rax
  _BYTE *v7; // r10
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned __int8 v10; // al
  void *v11; // r8
  unsigned __int8 *v12; // rcx
  unsigned __int8 v13; // dl
  void *v14; // rax
  unsigned __int8 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // ebx
  unsigned __int8 v21; // al
  void *v22; // r8
  __int64 v23; // rcx
  unsigned __int8 v24; // dl
  void *v25; // rax
  unsigned __int8 v27[8]; // [rsp+30h] [rbp-20h] BYREF
  void *v28; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v29[8]; // [rsp+40h] [rbp-10h] BYREF
  void *v30; // [rsp+48h] [rbp-8h] BYREF
  _BYTE v31[5]; // [rsp+70h] [rbp+20h] BYREF
  __int16 v32; // [rsp+75h] [rbp+25h]
  char v33; // [rsp+77h] [rbp+27h]
  char v34; // [rsp+88h] [rbp+38h] BYREF

  v34 = a4;
  v6 = std::vector<bool>::back(a1 + 32, v29);
  if ( ((1 << *(_QWORD *)(v6 + 8)) & **(_DWORD **)v6) != 0 )
  {
    v28 = 0;
    v27[0] = 4;
    LOBYTE(v28) = *v7;
    *(_DWORD *)((char *)&v28 + 1) = *(_DWORD *)&v31[1];
    *(_WORD *)((char *)&v28 + 5) = v32;
    HIBYTE(v28) = v33;
    v34 = 5;
    *(_DWORD *)v31 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3;
    v8 = *(_QWORD *)(a1 + 168);
    if ( !v8 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, _BYTE *, char *, unsigned __int8 *))(*(_QWORD *)v8 + 16LL))(
            v8,
            v31,
            &v34,
            v27) )
      goto LABEL_6;
    v9 = *(_QWORD *)(a1 + 16);
    if ( *(_QWORD *)(a1 + 8) == v9 )
    {
      v10 = v27[0];
      v11 = v28;
      v27[0] = 0;
      v28 = 0;
      v12 = *(unsigned __int8 **)a1;
      v13 = **(_BYTE **)a1;
      *v12 = v10;
      v29[0] = v13;
      v14 = (void *)*((_QWORD *)v12 + 1);
      *((_QWORD *)v12 + 1) = v11;
      v30 = v14;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        &v30,
        v13);
      v15 = *(unsigned __int8 **)a1;
    }
    else
    {
      v16 = *(_QWORD *)(v9 - 8);
      if ( !v16 )
        goto LABEL_6;
      if ( *(_BYTE *)v16 == 2 )
      {
        v17 = *(_QWORD *)(v16 + 8);
        v18 = *(_QWORD *)(v17 + 8);
        if ( v18 == *(_QWORD *)(v17 + 16) )
        {
          std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
            (void **)v17,
            (char *)v18,
            (__int64)v27);
        }
        else
        {
          *(_BYTE *)v18 = v27[0];
          *(_QWORD *)(v18 + 8) = v28;
          v27[0] = 0;
          v28 = 0;
          *(_QWORD *)(v17 + 8) += 16LL;
        }
        *(_QWORD *)(a2 + 8) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) - 8LL) + 8LL) + 8LL) - 16LL;
        goto LABEL_18;
      }
      v19 = std::vector<bool>::back(a1 + 64, v29);
      v20 = **(_DWORD **)v19 & (1 << *(_QWORD *)(v19 + 8));
      std::vector<bool>::pop_back(a1 + 64);
      if ( !v20 )
      {
LABEL_6:
        *(_BYTE *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
LABEL_19:
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v28,
          v27[0]);
        return a2;
      }
      v21 = v27[0];
      v22 = v28;
      v27[0] = 0;
      v28 = 0;
      v23 = *(_QWORD *)(a1 + 96);
      v24 = *(_BYTE *)v23;
      *(_BYTE *)v23 = v21;
      v29[0] = v24;
      v25 = *(void **)(v23 + 8);
      *(_QWORD *)(v23 + 8) = v22;
      v30 = v25;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        &v30,
        v24);
      v15 = *(unsigned __int8 **)(a1 + 96);
    }
    *(_QWORD *)(a2 + 8) = v15;
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
0x1800173a4  mov     [rsp-18h+arg_8], rbx
0x1800173a9  mov     [rsp-18h+arg_10], rsi
0x1800173ae  mov     [rsp-18h+arg_18], r9b
0x1800173b3  push    rbp
0x1800173b4  push    rdi
0x1800173b5  push    r14
0x1800173b7  mov     rbp, rsp
0x1800173ba  sub     rsp, 50h
0x1800173be  mov     r10, r8
0x1800173c1  mov     rdi, rdx
0x1800173c4  mov     r14, rcx
0x1800173c7  add     rcx, 20h ; ' '
0x1800173cb  lea     rdx, [rbp+var_10]
0x1800173cf  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x1800173d4  mov     rcx, [rax+8]
0x1800173d8  mov     r9d, 1
0x1800173de  shl     r9d, cl
0x1800173e1  mov     rax, [rax]
0x1800173e4  test    [rax], r9d
0x1800173e7  jnz     short loc_1800173F7
0x1800173e9  xor     esi, esi
0x1800173eb  mov     [rdi], sil
0x1800173ee  mov     [rdi+8], rsi
0x1800173f2  jmp     loc_18001757A
0x1800173f7  xor     eax, eax
0x1800173f9  mov     [rbp+var_18], rax
0x1800173fd  mov     [rbp+var_20], 4
0x180017401  mov     al, [r10]
0x180017404  mov     byte ptr [rbp+var_18], al
0x180017407  mov     eax, dword ptr [rbp+arg_0+1]
0x18001740a  mov     dword ptr [rbp+var_18+1], eax
0x18001740d  movzx   eax, [rbp+arg_5]
0x180017411  mov     word ptr [rbp+var_18+5], ax
0x180017415  mov     al, [rbp+arg_7]
0x180017418  mov     byte ptr [rbp+var_18+7], al
0x18001741b  mov     [rbp+arg_18], 5
0x18001741f  mov     rax, [r14+10h]
0x180017423  sub     rax, [r14+8]
0x180017427  sar     rax, 3
0x18001742b  mov     dword ptr [rbp+arg_0], eax
0x18001742e  mov     rcx, [r14+0A8h]
0x180017435  xor     esi, esi
0x180017437  test    rcx, rcx
0x18001743a  jnz     short loc_180017443
0x18001743c  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180017442  int     3; Trap to Debugger
0x180017443  mov     rax, [rcx]
0x180017446  lea     r9, [rbp+var_20]
0x18001744a  lea     r8, [rbp+arg_18]
0x18001744e  lea     rdx, [rbp+arg_0]
0x180017452  mov     rax, [rax+10h]
0x180017456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001745b  test    al, al
0x18001745d  jnz     short loc_18001746B
0x18001745f  mov     [rdi], sil
0x180017462  mov     [rdi+8], rsi
0x180017466  jmp     loc_18001756E
0x18001746b  mov     rax, [r14+10h]
0x18001746f  cmp     [r14+8], rax
0x180017473  jnz     short loc_1800174AB
0x180017475  mov     al, [rbp+var_20]
0x180017478  mov     r8, [rbp+var_18]
0x18001747c  mov     [rbp+var_20], sil
0x180017480  mov     [rbp+var_18], rsi
0x180017484  mov     rcx, [r14]
0x180017487  mov     dl, [rcx]
0x180017489  mov     [rcx], al
0x18001748b  mov     [rbp+var_10], dl
0x18001748e  mov     rax, [rcx+8]
0x180017492  mov     [rcx+8], r8
0x180017496  mov     [rbp+var_8], rax
0x18001749a  lea     rcx, [rbp+var_8]
0x18001749e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800174a3  mov     rax, [r14]
0x1800174a6  jmp     loc_180017567
0x1800174ab  mov     rcx, [rax-8]
0x1800174af  test    rcx, rcx
0x1800174b2  jz      short loc_18001745F
0x1800174b4  cmp     byte ptr [rcx], 2
0x1800174b7  jnz     short loc_180017506
0x1800174b9  mov     rcx, [rcx+8]
0x1800174bd  mov     rdx, [rcx+8]
0x1800174c1  cmp     rdx, [rcx+10h]
0x1800174c5  jz      short loc_1800174E3
0x1800174c7  mov     al, [rbp+var_20]
0x1800174ca  mov     [rdx], al
0x1800174cc  mov     rax, [rbp+var_18]
0x1800174d0  mov     [rdx+8], rax
0x1800174d4  mov     [rbp+var_20], sil
0x1800174d8  mov     [rbp+var_18], rsi
0x1800174dc  add     qword ptr [rcx+8], 10h
0x1800174e1  jmp     short loc_1800174EC
0x1800174e3  lea     r8, [rbp+var_20]
0x1800174e7  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x1800174ec  mov     rax, [r14+10h]
0x1800174f0  mov     rcx, [rax-8]
0x1800174f4  mov     rax, [rcx+8]
0x1800174f8  mov     rcx, [rax+8]
0x1800174fc  sub     rcx, 10h
0x180017500  mov     [rdi+8], rcx
0x180017504  jmp     short loc_18001756B
0x180017506  lea     rdx, [rbp+var_10]
0x18001750a  lea     rcx, [r14+40h]
0x18001750e  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x180017513  mov     rcx, [rax+8]
0x180017517  mov     ebx, 1
0x18001751c  shl     ebx, cl
0x18001751e  mov     rax, [rax]
0x180017521  and     ebx, [rax]
0x180017523  lea     rcx, [r14+40h]
0x180017527  call    ?pop_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXXZ; std::vector<bool>::pop_back(void)
0x18001752c  test    ebx, ebx
0x18001752e  jz      loc_18001745F
0x180017534  mov     al, [rbp+var_20]
0x180017537  mov     r8, [rbp+var_18]
0x18001753b  mov     [rbp+var_20], sil
0x18001753f  mov     [rbp+var_18], rsi
0x180017543  mov     rcx, [r14+60h]
0x180017547  mov     dl, [rcx]
0x180017549  mov     [rcx], al
0x18001754b  mov     [rbp+var_10], dl
0x18001754e  mov     rax, [rcx+8]
0x180017552  mov     [rcx+8], r8
0x180017556  mov     [rbp+var_8], rax
0x18001755a  lea     rcx, [rbp+var_8]
0x18001755e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180017563  mov     rax, [r14+60h]
0x180017567  mov     [rdi+8], rax
0x18001756b  mov     byte ptr [rdi], 1
0x18001756e  mov     dl, [rbp+var_20]
0x180017571  lea     rcx, [rbp+var_18]
0x180017575  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001757a  mov     rax, rdi
0x18001757d  lea     r11, [rsp+50h+var_s0]
0x180017582  mov     rbx, [r11+28h]
0x180017586  mov     rsi, [r11+30h]
0x18001758a  mov     rsp, r11
0x18001758d  pop     r14
0x18001758f  pop     rdi
0x180017590  pop     rbp
0x180017591  retn
```
