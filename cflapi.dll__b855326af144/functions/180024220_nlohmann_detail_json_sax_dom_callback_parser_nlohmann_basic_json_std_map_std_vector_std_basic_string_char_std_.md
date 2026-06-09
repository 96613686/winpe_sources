# nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::end_object(void)

- ea: `0x180024220`
- end: `0x18002451d`
- name: `?end_object@?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAA_NXZ`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180017b94`

## callees

- `0x180002490`
- `0x180002f04`
- `0x1800169ac`
- `0x180019d08`
- `0x180019fb8`
- `0x1800226a8`
- `0x180022cf4`
- `0x180024220`
- `0x18002588c`
- `0x180030010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024275`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024275`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::end_object(
        _QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  char *v5; // r8
  char v6; // cl
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int8 *v9; // rbx
  unsigned __int64 v10; // rcx
  int v11; // edi
  __int64 *i; // rax
  _BYTE *v13; // rdx
  unsigned __int64 v14; // r10
  __int64 **v15; // r8
  _BYTE *v16; // r9
  bool v17; // zf
  _BYTE *v18; // r8
  __int64 *v19; // r8
  __int64 *v20; // r9
  char v22[8]; // [rsp+30h] [rbp-29h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-21h] BYREF
  __int128 v24; // [rsp+48h] [rbp-11h]
  __int128 v25; // [rsp+70h] [rbp+17h] BYREF
  __int128 v26; // [rsp+80h] [rbp+27h]

  v2 = a1[2];
  if ( *(_QWORD *)(v2 - 8) )
  {
    LODWORD(pExceptionObject) = ((v2 - a1[1]) >> 3) - 1;
    v22[0] = 1;
    v3 = a1[21];
    if ( !v3 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int128 *, char *))(*(_QWORD *)v3 + 16LL))(
            v3,
            &pExceptionObject,
            v22) )
    {
      v4 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
             (__int64)&pExceptionObject,
             (__int64)(a1 + 23));
      v5 = *(char **)(a1[2] - 8LL);
      v6 = *v5;
      *v5 = *(_BYTE *)v4;
      *(_BYTE *)v4 = v6;
      v7 = *((_QWORD *)v5 + 1);
      *((_QWORD *)v5 + 1) = *(_QWORD *)(v4 + 8);
      *(_QWORD *)(v4 + 8) = v7;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        (void **)(v4 + 8),
        *(_BYTE *)v4);
    }
  }
  a1[2] -= 8LL;
  std::vector<bool>::pop_back(a1 + 4);
  v8 = a1[2];
  if ( a1[1] != v8 )
  {
    v9 = *(unsigned __int8 **)(v8 - 8);
    if ( v9 )
    {
      if ( (unsigned __int8)(*v9 - 1) <= 1u )
      {
        pExceptionObject = (unsigned __int64)v9;
        *(_QWORD *)&v24 = 0;
        v10 = 0x8000000000000000uLL;
        *((_QWORD *)&v24 + 1) = 0x8000000000000000uLL;
        v11 = *v9;
        if ( v11 != 1 )
        {
          if ( *v9 == 2 )
            goto LABEL_17;
          if ( !*v9 )
          {
            v10 = 1;
            goto LABEL_15;
          }
          if ( v11 != 1 )
          {
            if ( v11 != 2 )
            {
              v10 = 0;
LABEL_15:
              *((_QWORD *)&v24 + 1) = v10;
              i = (__int64 *)*((_QWORD *)&pExceptionObject + 1);
LABEL_19:
              v13 = (_BYTE *)v24;
              while ( 1 )
              {
LABEL_20:
                *((_QWORD *)&v25 + 1) = 0;
                v26 = 0;
                v14 = 0x8000000000000000uLL;
                if ( *v9 == 1 )
                  goto LABEL_26;
                if ( *v9 == 2 )
                  goto LABEL_25;
                if ( *v9 == 1 )
                {
LABEL_26:
                  v15 = (__int64 **)**((_QWORD **)v9 + 1);
                }
                else
                {
                  if ( *v9 == 2 )
                  {
LABEL_25:
                    v16 = *(_BYTE **)(*((_QWORD *)v9 + 1) + 8LL);
                    v15 = (__int64 **)*((_QWORD *)&v25 + 1);
                    goto LABEL_28;
                  }
                  v14 = 1;
                  v15 = (__int64 **)*((_QWORD *)&v25 + 1);
                }
                v16 = (_BYTE *)v26;
LABEL_28:
                if ( v11 == 1 )
                {
                  v17 = i == (__int64 *)v15;
                }
                else if ( v11 == 2 )
                {
                  v17 = v13 == v16;
                }
                else
                {
                  v17 = v10 == v14;
                }
                if ( v17 )
                  return 1;
                if ( v11 == 1 )
                {
                  v18 = i + 8;
                }
                else if ( v11 == 2 )
                {
                  v18 = v13;
                }
                else
                {
                  if ( v10 )
                  {
                    std::string::string(&v25, "cannot get value");
                    nlohmann::detail::invalid_iterator::create(&pExceptionObject, 214, &v25);
                    throw (nlohmann::detail::invalid_iterator *)&pExceptionObject;
                  }
                  v18 = v9;
                }
                if ( *v18 == 9 )
                {
                  v25 = pExceptionObject;
                  v26 = v24;
                  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::erase<nlohmann::detail::iter_impl<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>,0>(
                    v9,
                    (unsigned __int8 **)&pExceptionObject,
                    (unsigned __int8 **)&v25);
                  return 1;
                }
                if ( v11 == 1 )
                {
                  v19 = i;
                  i = (__int64 *)i[2];
                  if ( *((_BYTE *)i + 25) )
                  {
                    for ( i = (__int64 *)v19[1]; !*((_BYTE *)i + 25) && v19 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                      v19 = i;
                  }
                  else
                  {
                    v20 = (__int64 *)*i;
                    if ( !*(_BYTE *)(*i + 25) )
                    {
                      do
                      {
                        i = v20;
                        v20 = (__int64 *)*v20;
                      }
                      while ( !*((_BYTE *)v20 + 25) );
                    }
                  }
                  *((_QWORD *)&pExceptionObject + 1) = i;
                }
                else if ( v11 == 2 )
                {
                  v13 += 16;
                  *(_QWORD *)&v24 = v13;
                }
                else
                {
                  *((_QWORD *)&v24 + 1) = ++v10;
                }
              }
            }
LABEL_17:
            v13 = (_BYTE *)**((_QWORD **)v9 + 1);
            *(_QWORD *)&v24 = v13;
            i = (__int64 *)*((_QWORD *)&pExceptionObject + 1);
            goto LABEL_20;
          }
        }
        i = (__int64 *)***((_QWORD ***)v9 + 1);
        *((_QWORD *)&pExceptionObject + 1) = i;
        goto LABEL_19;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180024220  mov     [rsp-8+arg_8], rbx
0x180024225  mov     [rsp-8+arg_10], rsi
0x18002422a  push    rbp
0x18002422b  push    rdi
0x18002422c  push    r12
0x18002422e  lea     rbp, [rsp-47h]
0x180024233  sub     rsp, 0A0h
0x18002423a  mov     rax, cs:__security_cookie
0x180024241  xor     rax, rsp
0x180024244  mov     [rbp+57h+var_20], rax
0x180024248  mov     rbx, rcx
0x18002424b  mov     rax, [rcx+10h]
0x18002424f  mov     r9, [rax-8]
0x180024253  test    r9, r9
0x180024256  jz      short loc_1800242D5
0x180024258  sub     rax, [rcx+8]
0x18002425c  sar     rax, 3
0x180024260  dec     eax
0x180024262  mov     dword ptr [rbp+57h+pExceptionObject], eax
0x180024265  mov     [rbp+57h+var_80], 1
0x180024269  mov     rcx, [rcx+0A8h]
0x180024270  test    rcx, rcx
0x180024273  jnz     short loc_18002427C
0x180024275  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18002427b  int     3; Trap to Debugger
0x18002427c  mov     rax, [rcx]
0x18002427f  lea     r8, [rbp+57h+var_80]
0x180024283  lea     rdx, [rbp+57h+pExceptionObject]
0x180024287  mov     rax, [rax+10h]
0x18002428b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024290  test    al, al
0x180024292  jnz     short loc_1800242D5
0x180024294  lea     rdx, [rbx+0B8h]
0x18002429b  lea     rcx, [rbp+57h+pExceptionObject]
0x18002429f  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBV01@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &)
0x1800242a4  mov     r9, rax
0x1800242a7  mov     rax, [rbx+10h]
0x1800242ab  mov     r8, [rax-8]
0x1800242af  mov     cl, [r8]
0x1800242b2  mov     al, [r9]
0x1800242b5  mov     [r8], al
0x1800242b8  mov     [r9], cl
0x1800242bb  lea     rcx, [r9+8]
0x1800242bf  mov     rdx, [r8+8]
0x1800242c3  mov     rax, [rcx]
0x1800242c6  mov     [r8+8], rax
0x1800242ca  mov     [rcx], rdx
0x1800242cd  mov     dl, [r9]
0x1800242d0  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800242d5  add     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFF8h
0x1800242da  lea     rcx, [rbx+20h]
0x1800242de  call    ?pop_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXXZ; std::vector<bool>::pop_back(void)
0x1800242e3  mov     r8, [rbx+10h]
0x1800242e7  cmp     [rbx+8], r8
0x1800242eb  jz      loc_1800244C3
0x1800242f1  mov     rbx, [r8-8]
0x1800242f5  test    rbx, rbx
0x1800242f8  jz      loc_1800244C3
0x1800242fe  mov     al, [rbx]
0x180024300  dec     al
0x180024302  cmp     al, 1
0x180024304  ja      loc_1800244C3
0x18002430a  mov     qword ptr [rbp+57h+pExceptionObject], rbx
0x18002430e  xorps   xmm0, xmm0
0x180024311  movdqu  [rbp+57h+pExceptionObject+8], xmm0
0x180024316  xorps   xmm1, xmm1
0x180024319  movdqu  xmmword ptr [rbp-11h], xmm1
0x18002431e  mov     r12, 8000000000000000h
0x180024328  mov     rcx, r12
0x18002432b  mov     qword ptr [rbp+57h+var_68+8], rcx
0x18002432f  movzx   edi, byte ptr [rbx]
0x180024332  mov     edx, edi
0x180024334  sub     edx, 1
0x180024337  jz      short loc_180024372
0x180024339  cmp     edx, 1
0x18002433c  jz      short loc_180024361
0x18002433e  mov     edx, edi
0x180024340  test    edi, edi
0x180024342  jz      short loc_18002435A
0x180024344  sub     edx, 1
0x180024347  jz      short loc_180024372
0x180024349  cmp     edx, 1
0x18002434c  jz      short loc_180024361
0x18002434e  xor     ecx, ecx
0x180024350  mov     qword ptr [rbp+57h+var_68+8], rcx
0x180024354  mov     rax, qword ptr [rbp+57h+pExceptionObject+8]
0x180024358  jmp     short loc_180024380
0x18002435a  mov     ecx, 1
0x18002435f  jmp     short loc_180024350
0x180024361  mov     rdx, [rbx+8]
0x180024365  mov     rdx, [rdx]
0x180024368  mov     qword ptr [rbp+57h+var_68], rdx
0x18002436c  mov     rax, qword ptr [rbp+57h+pExceptionObject+8]
0x180024370  jmp     short loc_180024384
0x180024372  mov     rax, [rbx+8]
0x180024376  mov     rax, [rax]
0x180024379  mov     rax, [rax]
0x18002437c  mov     qword ptr [rbp+57h+pExceptionObject+8], rax
0x180024380  mov     rdx, qword ptr [rbp+57h+var_68]
0x180024384  xorps   xmm0, xmm0
0x180024387  movdqu  [rbp+57h+var_40+8], xmm0
0x18002438c  xorps   xmm1, xmm1
0x18002438f  movdqu  [rbp+57h+var_30], xmm1
0x180024394  mov     r10, r12
0x180024397  movzx   r9d, byte ptr [rbx]
0x18002439b  mov     r11d, r9d
0x18002439e  sub     r11d, 1
0x1800243a2  jz      short loc_1800243D0
0x1800243a4  cmp     r11d, 1
0x1800243a8  jz      short loc_1800243C2
0x1800243aa  sub     r9d, 1
0x1800243ae  jz      short loc_1800243D0
0x1800243b0  cmp     r9d, 1
0x1800243b4  jz      short loc_1800243C2
0x1800243b6  mov     r10d, 1
0x1800243bc  mov     r8, qword ptr [rbp+57h+var_40+8]
0x1800243c0  jmp     short loc_1800243D7
0x1800243c2  mov     r9, [rbx+8]
0x1800243c6  mov     r9, [r9+8]
0x1800243ca  mov     r8, qword ptr [rbp+57h+var_40+8]
0x1800243ce  jmp     short loc_1800243DB
0x1800243d0  mov     r8, [rbx+8]
0x1800243d4  mov     r8, [r8]
0x1800243d7  mov     r9, qword ptr [rbp+57h+var_30]
0x1800243db  mov     r11d, edi
0x1800243de  sub     r11d, 1
0x1800243e2  jz      short loc_1800243F4
0x1800243e4  cmp     r11d, 1
0x1800243e8  jz      short loc_1800243EF
0x1800243ea  cmp     rcx, r10
0x1800243ed  jmp     short loc_1800243F7
0x1800243ef  cmp     rdx, r9
0x1800243f2  jmp     short loc_1800243F7
0x1800243f4  cmp     rax, r8
0x1800243f7  setz    r8b
0x1800243fb  test    r8b, r8b
0x1800243fe  jnz     loc_1800244C3
0x180024404  mov     r9d, edi
0x180024407  sub     r9d, 1
0x18002440b  jz      short loc_180024426
0x18002440d  cmp     r9d, 1
0x180024411  jz      short loc_180024421
0x180024413  test    rcx, rcx
0x180024416  jnz     loc_1800244E9
0x18002441c  mov     r8, rbx
0x18002441f  jmp     short loc_18002442A
0x180024421  mov     r8, rdx
0x180024424  jmp     short loc_18002442A
0x180024426  lea     r8, [rax+40h]
0x18002442a  cmp     byte ptr [r8], 9
0x18002442e  jz      short loc_1800244A3
0x180024430  mov     r9d, edi
0x180024433  sub     r9d, 1
0x180024437  jz      short loc_180024458
0x180024439  cmp     r9d, 1
0x18002443d  jz      short loc_18002444B
0x18002443f  inc     rcx
0x180024442  mov     qword ptr [rbp+57h+var_68+8], rcx
0x180024446  jmp     loc_180024384
0x18002444b  add     rdx, 10h
0x18002444f  mov     qword ptr [rbp+57h+var_68], rdx
0x180024453  jmp     loc_180024384
0x180024458  mov     r8, rax
0x18002445b  mov     rax, [rax+10h]
0x18002445f  cmp     byte ptr [rax+19h], 0
0x180024463  jz      short loc_180024480
0x180024465  mov     rax, [r8+8]
0x180024469  jmp     short loc_180024478
0x18002446b  cmp     r8, [rax+10h]
0x18002446f  jnz     short loc_18002449A
0x180024471  mov     r8, rax
0x180024474  mov     rax, [rax+8]
0x180024478  cmp     byte ptr [rax+19h], 0
0x18002447c  jz      short loc_18002446B
0x18002447e  jmp     short loc_18002449A
0x180024480  mov     r9, [rax]
0x180024483  cmp     byte ptr [r9+19h], 0
0x180024488  jnz     short loc_18002449A
0x18002448a  mov     rax, r9
0x18002448d  mov     r8, [r9]
0x180024490  mov     r9, r8
0x180024493  cmp     byte ptr [r8+19h], 0
0x180024498  jz      short loc_18002448A
0x18002449a  mov     qword ptr [rbp+57h+pExceptionObject+8], rax
0x18002449e  jmp     loc_180024384
0x1800244a3  movups  xmm0, [rbp+57h+pExceptionObject]
0x1800244a7  movups  [rbp+57h+var_40], xmm0
0x1800244ab  movups  xmm1, [rbp+57h+var_68]
0x1800244af  movups  [rbp+57h+var_30], xmm1
0x1800244b3  lea     r8, [rbp+57h+var_40]
0x1800244b7  lea     rdx, [rbp+57h+pExceptionObject]
0x1800244bb  mov     rcx, rbx
0x1800244be  call    ??$erase@V?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA?AV?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@1@V231@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::erase<nlohmann::detail::iter_impl<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,0>(nlohmann::detail::iter_impl<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>)
0x1800244c3  mov     al, 1
0x1800244c5  mov     rcx, [rbp+57h+var_20]
0x1800244c9  xor     rcx, rsp; StackCookie
0x1800244cc  call    __security_check_cookie
0x1800244d1  lea     r11, [rsp+0B0h+var_10]
0x1800244d9  mov     rbx, [r11+28h]
0x1800244dd  mov     rsi, [r11+30h]
0x1800244e1  mov     rsp, r11
0x1800244e4  pop     r12
0x1800244e6  pop     rdi
0x1800244e7  pop     rbp
0x1800244e8  retn
0x1800244e9  lea     rdx, aCannotGetValue; "cannot get value"
0x1800244f0  lea     rcx, [rbp+57h+var_40]
0x1800244f4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800244f9  nop
0x1800244fa  lea     r8, [rbp+57h+var_40]
0x1800244fe  mov     edx, 0D6h
0x180024503  lea     rcx, [rbp+57h+pExceptionObject]
0x180024507  call    ?create@invalid_iterator@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::invalid_iterator::create(int,std::string const &)
0x18002450c  lea     rdx, _TI3?AVinvalid_iterator@detail@nlohmann@@; pThrowInfo
0x180024513  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180024517  call    _CxxThrowException_0
```
