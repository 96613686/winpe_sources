# nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::handle_value<nlohmann::detail::value_t>(nlohmann::detail::value_t &&,bool)

- ea: `0x180017598`
- end: `0x180017728`
- name: `??$handle_value@W4value_t@detail@nlohmann@@@?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAA?AU?$pair@_NPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@$$QEAW4value_t@12@_N@Z`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017b94`

## callees

- `0x180014e64`
- `0x180017598`
- `0x18001a674`
- `0x18002258c`
- `0x180022cf4`
- `0x18002588c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<enum nlohmann::detail::value_t>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  unsigned __int8 *v5; // r10
  __int64 v6; // rax
  unsigned __int8 v7; // al
  void *v8; // r8
  unsigned __int8 *v9; // rcx
  unsigned __int8 v10; // dl
  void *v11; // rax
  unsigned __int8 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // ebx
  unsigned __int8 v18; // al
  void *v19; // r8
  __int64 v20; // rcx
  unsigned __int8 v21; // dl
  void *v22; // rax
  unsigned __int8 v24[8]; // [rsp+20h] [rbp-28h] BYREF
  void *v25; // [rsp+28h] [rbp-20h] BYREF
  unsigned __int8 v26[8]; // [rsp+30h] [rbp-18h] BYREF
  void *v27[2]; // [rsp+38h] [rbp-10h] BYREF

  v4 = std::vector<bool>::back(a1 + 32, v26);
  if ( ((1 << *(_QWORD *)(v4 + 8)) & **(_DWORD **)v4) != 0 )
  {
    v24[0] = *v5;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v25,
      v24[0]);
    v6 = *(_QWORD *)(a1 + 16);
    if ( *(_QWORD *)(a1 + 8) == v6 )
    {
      v7 = v24[0];
      v8 = v25;
      v24[0] = 0;
      v25 = 0;
      v9 = *(unsigned __int8 **)a1;
      v10 = **(_BYTE **)a1;
      *v9 = v7;
      v26[0] = v10;
      v11 = (void *)*((_QWORD *)v9 + 1);
      *((_QWORD *)v9 + 1) = v8;
      v27[0] = v11;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        v27,
        v10);
      v12 = *(unsigned __int8 **)a1;
    }
    else
    {
      v13 = *(_QWORD *)(v6 - 8);
      if ( !v13 )
        goto LABEL_6;
      if ( *(_BYTE *)v13 == 2 )
      {
        v14 = *(_QWORD *)(v13 + 8);
        v15 = *(_QWORD *)(v14 + 8);
        if ( v15 == *(_QWORD *)(v14 + 16) )
        {
          std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
            (void **)v14,
            (char *)v15,
            (__int64)v24);
        }
        else
        {
          *(_BYTE *)v15 = v24[0];
          *(_QWORD *)(v15 + 8) = v25;
          v24[0] = 0;
          v25 = 0;
          *(_QWORD *)(v14 + 8) += 16LL;
        }
        *(_QWORD *)(a2 + 8) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) - 8LL) + 8LL) + 8LL) - 16LL;
        goto LABEL_15;
      }
      v16 = std::vector<bool>::back(a1 + 64, v26);
      v17 = **(_DWORD **)v16 & (1 << *(_QWORD *)(v16 + 8));
      std::vector<bool>::pop_back(a1 + 64);
      if ( !v17 )
      {
LABEL_6:
        *(_BYTE *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
LABEL_16:
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v25,
          v24[0]);
        return a2;
      }
      v18 = v24[0];
      v19 = v25;
      v24[0] = 0;
      v25 = 0;
      v20 = *(_QWORD *)(a1 + 96);
      v21 = *(_BYTE *)v20;
      *(_BYTE *)v20 = v18;
      v26[0] = v21;
      v22 = *(void **)(v20 + 8);
      *(_QWORD *)(v20 + 8) = v19;
      v27[0] = v22;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        v27,
        v21);
      v12 = *(unsigned __int8 **)(a1 + 96);
    }
    *(_QWORD *)(a2 + 8) = v12;
LABEL_15:
    *(_BYTE *)a2 = 1;
    goto LABEL_16;
  }
  *(_BYTE *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180017598  push    rbp
0x18001759a  push    rbx
0x18001759b  push    rdi
0x18001759c  push    r14
0x18001759e  mov     rbp, rsp
0x1800175a1  sub     rsp, 48h
0x1800175a5  mov     r10, r8
0x1800175a8  mov     rdi, rdx
0x1800175ab  mov     r14, rcx
0x1800175ae  add     rcx, 20h ; ' '
0x1800175b2  lea     rdx, [rbp+var_18]
0x1800175b6  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x1800175bb  mov     rcx, [rax+8]
0x1800175bf  mov     r9d, 1
0x1800175c5  shl     r9d, cl
0x1800175c8  mov     rax, [rax]
0x1800175cb  test    [rax], r9d
0x1800175ce  jnz     short loc_1800175E0
0x1800175d0  mov     byte ptr [rdi], 0
0x1800175d3  mov     qword ptr [rdi+8], 0
0x1800175db  jmp     loc_18001771B
0x1800175e0  mov     dl, [r10]
0x1800175e3  mov     [rbp+var_28], dl
0x1800175e6  lea     rcx, [rbp+var_20]
0x1800175ea  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x1800175ef  nop
0x1800175f0  mov     rax, [r14+10h]
0x1800175f4  cmp     [r14+8], rax
0x1800175f8  jnz     short loc_180017634
0x1800175fa  mov     al, [rbp+var_28]
0x1800175fd  mov     r8, [rbp+var_20]
0x180017601  mov     [rbp+var_28], 0
0x180017605  mov     [rbp+var_20], 0
0x18001760d  mov     rcx, [r14]
0x180017610  mov     dl, [rcx]
0x180017612  mov     [rcx], al
0x180017614  mov     [rbp+var_18], dl
0x180017617  mov     rax, [rcx+8]
0x18001761b  mov     [rcx+8], r8
0x18001761f  mov     [rbp+var_10], rax
0x180017623  lea     rcx, [rbp+var_10]
0x180017627  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001762c  mov     rax, [r14]
0x18001762f  jmp     loc_180017708
0x180017634  mov     rcx, [rax-8]
0x180017638  test    rcx, rcx
0x18001763b  jnz     short loc_18001764D
0x18001763d  mov     byte ptr [rdi], 0
0x180017640  mov     qword ptr [rdi+8], 0
0x180017648  jmp     loc_18001770F
0x18001764d  cmp     byte ptr [rcx], 2
0x180017650  jnz     short loc_1800176A3
0x180017652  mov     rcx, [rcx+8]
0x180017656  mov     rdx, [rcx+8]
0x18001765a  cmp     rdx, [rcx+10h]
0x18001765e  jz      short loc_180017680
0x180017660  mov     al, [rbp+var_28]
0x180017663  mov     [rdx], al
0x180017665  mov     rax, [rbp+var_20]
0x180017669  mov     [rdx+8], rax
0x18001766d  mov     [rbp+var_28], 0
0x180017671  mov     [rbp+var_20], 0
0x180017679  add     qword ptr [rcx+8], 10h
0x18001767e  jmp     short loc_180017689
0x180017680  lea     r8, [rbp+var_28]
0x180017684  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x180017689  mov     rax, [r14+10h]
0x18001768d  mov     rcx, [rax-8]
0x180017691  mov     rax, [rcx+8]
0x180017695  mov     rcx, [rax+8]
0x180017699  sub     rcx, 10h
0x18001769d  mov     [rdi+8], rcx
0x1800176a1  jmp     short loc_18001770C
0x1800176a3  lea     rdx, [rbp+var_18]
0x1800176a7  lea     rcx, [r14+40h]
0x1800176ab  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x1800176b0  mov     rcx, [rax+8]
0x1800176b4  mov     ebx, 1
0x1800176b9  shl     ebx, cl
0x1800176bb  mov     rax, [rax]
0x1800176be  and     ebx, [rax]
0x1800176c0  lea     rcx, [r14+40h]
0x1800176c4  call    ?pop_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXXZ; std::vector<bool>::pop_back(void)
0x1800176c9  test    ebx, ebx
0x1800176cb  jz      loc_18001763D
0x1800176d1  mov     al, [rbp+var_28]
0x1800176d4  mov     r8, [rbp+var_20]
0x1800176d8  mov     [rbp+var_28], 0
0x1800176dc  mov     [rbp+var_20], 0
0x1800176e4  mov     rcx, [r14+60h]
0x1800176e8  mov     dl, [rcx]
0x1800176ea  mov     [rcx], al
0x1800176ec  mov     [rbp+var_18], dl
0x1800176ef  mov     rax, [rcx+8]
0x1800176f3  mov     [rcx+8], r8
0x1800176f7  mov     [rbp+var_10], rax
0x1800176fb  lea     rcx, [rbp+var_10]
0x1800176ff  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180017704  mov     rax, [r14+60h]
0x180017708  mov     [rdi+8], rax
0x18001770c  mov     byte ptr [rdi], 1
0x18001770f  mov     dl, [rbp+var_28]
0x180017712  lea     rcx, [rbp+var_20]
0x180017716  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001771b  mov     rax, rdi
0x18001771e  add     rsp, 48h
0x180017722  pop     r14
0x180017724  pop     rdi
0x180017725  pop     rbx
0x180017726  pop     rbp
0x180017727  retn
```
