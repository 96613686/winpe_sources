# web::json::details::append_escape_string<ushort>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14000b5a0`
- end: `0x14000bbcd`
- name: `??$append_escape_string@G@details@json@web@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z`
- size: `1581`
- prototype: `void **__fastcall(void **Src, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000c090`
- `0x14000c1c0`

## callees

- `0x140005450`
- `0x14000b5a0`
- `0x14000bbe0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall web::json::details::append_escape_string<unsigned short>(void **Src, _QWORD *a2)
{
  _QWORD *v3; // rcx
  _QWORD *v4; // r8
  _WORD *v5; // rbp
  void **result; // rax
  _WORD *v7; // r14
  unsigned __int64 *v8; // rsi
  unsigned __int64 *v9; // rdi
  unsigned int v10; // r9d
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  void **v13; // r8
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  void **v18; // r8
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  void **v23; // r8
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  void **v28; // r8
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  void **v33; // r8
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  void **v38; // r8
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  void **v43; // r8
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // rdx
  void **v48; // r8
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rdx
  void **v51; // r8
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rdx
  void **v54; // r8
  unsigned __int64 v55; // rcx
  unsigned __int64 v56; // rdx
  void **v57; // r8
  void **v58; // r8

  if ( a2[3] <= 7u )
  {
    v4 = a2;
    v3 = a2;
    v5 = a2;
  }
  else
  {
    v3 = (_QWORD *)*a2;
    v4 = (_QWORD *)*a2;
    v5 = (_WORD *)*a2;
  }
  result = (void **)a2[2];
  v7 = (_WORD *)v4 + (_QWORD)result;
  if ( v3 != (_QWORD *)v7 )
  {
    v8 = (unsigned __int64 *)(Src + 3);
    v9 = (unsigned __int64 *)(Src + 2);
    do
    {
      v10 = (unsigned __int16)*v5;
      switch ( *v5 )
      {
        case 8:
          v21 = *v9;
          v22 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v23 = Src;
            *v9 = v21 + 1;
            if ( v22 > 7 )
              v23 = (void **)*Src;
            *(_DWORD *)((char *)v23 + 2 * v21) = 92;
          }
          v24 = *v9;
          v25 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 98;
            goto LABEL_27;
          }
          result = (void **)(v24 + 1);
          *v9 = v24 + 1;
          if ( v25 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v24) = 98;
          else
            *(_DWORD *)((char *)*Src + 2 * v24) = 98;
          break;
        case 9:
          v41 = *v9;
          v42 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v43 = Src;
            *v9 = v41 + 1;
            if ( v42 > 7 )
              v43 = (void **)*Src;
            *(_DWORD *)((char *)v43 + 2 * v41) = 92;
          }
          v44 = *v9;
          v45 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 116;
            goto LABEL_27;
          }
          result = (void **)(v44 + 1);
          Src[2] = (void *)(v44 + 1);
          if ( v45 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v44) = 116;
          else
            *(_DWORD *)((char *)*Src + 2 * v44) = 116;
          break;
        case 0xA:
          v36 = *v9;
          v37 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v38 = Src;
            *v9 = v36 + 1;
            if ( v37 > 7 )
              v38 = (void **)*Src;
            *(_DWORD *)((char *)v38 + 2 * v36) = 92;
          }
          v39 = *v9;
          v40 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 110;
            goto LABEL_27;
          }
          result = (void **)(v39 + 1);
          Src[2] = (void *)(v39 + 1);
          if ( v40 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v39) = 110;
          else
            *(_DWORD *)((char *)*Src + 2 * v39) = 110;
          break;
        case 0xC:
          v26 = *v9;
          v27 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v28 = Src;
            *v9 = v26 + 1;
            if ( v27 > 7 )
              v28 = (void **)*Src;
            *(_DWORD *)((char *)v28 + 2 * v26) = 92;
          }
          v29 = *v9;
          v30 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 102;
            goto LABEL_27;
          }
          result = (void **)(v29 + 1);
          Src[2] = (void *)(v29 + 1);
          if ( v30 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v29) = 102;
          else
            *(_DWORD *)((char *)*Src + 2 * v29) = 102;
          break;
        case 0xD:
          v31 = *v9;
          v32 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v33 = Src;
            *v9 = v31 + 1;
            if ( v32 > 7 )
              v33 = (void **)*Src;
            *(_DWORD *)((char *)v33 + 2 * v31) = 92;
          }
          v34 = *v9;
          v35 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 114;
            goto LABEL_27;
          }
          result = (void **)(v34 + 1);
          Src[2] = (void *)(v34 + 1);
          if ( v35 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v34) = 114;
          else
            *(_DWORD *)((char *)*Src + 2 * v34) = 114;
          break;
        case 0x22:
          v11 = *v9;
          v12 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v13 = Src;
            *v9 = v11 + 1;
            if ( v12 > 7 )
              v13 = (void **)*Src;
            *(_DWORD *)((char *)v13 + 2 * v11) = 92;
          }
          v14 = *v9;
          v15 = *v8;
          if ( *v9 >= *v8 )
          {
            result = ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                       Src,
                       1u,
                       0,
                       34);
            v9 = (unsigned __int64 *)(Src + 2);
            v8 = (unsigned __int64 *)(Src + 3);
          }
          else
          {
            result = (void **)(v14 + 1);
            *v9 = v14 + 1;
            if ( v15 <= 7 )
            {
              *(_DWORD *)((char *)Src + 2 * v14) = 34;
              v9 = (unsigned __int64 *)(Src + 2);
              v8 = (unsigned __int64 *)(Src + 3);
            }
            else
            {
              v9 = (unsigned __int64 *)(Src + 2);
              v8 = (unsigned __int64 *)(Src + 3);
              *(_DWORD *)((char *)*Src + 2 * v14) = 34;
            }
          }
          break;
        case 0x5C:
          v16 = *v9;
          v17 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v18 = Src;
            *v9 = v16 + 1;
            if ( v17 > 7 )
              v18 = (void **)*Src;
            *(_DWORD *)((char *)v18 + 2 * v16) = 92;
          }
          v19 = *v9;
          v20 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 92;
            goto LABEL_27;
          }
          result = (void **)(v19 + 1);
          *v9 = v19 + 1;
          if ( v20 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v19) = 92;
          else
            *(_DWORD *)((char *)*Src + 2 * v19) = 92;
          break;
        default:
          v46 = *v9;
          v47 = *v8;
          if ( v10 > 0x1F )
          {
            if ( v46 >= v47 )
            {
LABEL_27:
              result = ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                         Src,
                         1u,
                         0,
                         v10);
            }
            else
            {
              v58 = Src;
              *v9 = v46 + 1;
              if ( v47 > 7 )
                v58 = (void **)*Src;
              result = 0;
              *((_WORD *)v58 + v46) = v10;
              *((_WORD *)v58 + v46 + 1) = 0;
            }
          }
          else
          {
            if ( v46 >= v47 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                92);
            }
            else
            {
              v48 = Src;
              *v9 = v46 + 1;
              if ( v47 > 7 )
                v48 = (void **)*Src;
              *(_DWORD *)((char *)v48 + 2 * v46) = 92;
            }
            v49 = (unsigned __int64)Src[2];
            v50 = (unsigned __int64)Src[3];
            if ( v49 >= v50 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                117);
            }
            else
            {
              v51 = Src;
              Src[2] = (void *)(v49 + 1);
              if ( v50 > 7 )
                v51 = (void **)*Src;
              *(_DWORD *)((char *)v51 + 2 * v49) = 117;
            }
            v52 = (unsigned __int64)Src[2];
            v53 = (unsigned __int64)Src[3];
            if ( v52 >= v53 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                48);
            }
            else
            {
              v54 = Src;
              Src[2] = (void *)(v52 + 1);
              if ( v53 > 7 )
                v54 = (void **)*Src;
              *(_DWORD *)((char *)v54 + 2 * v52) = 48;
            }
            v55 = (unsigned __int64)Src[2];
            v56 = (unsigned __int64)Src[3];
            if ( v55 >= v56 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                48);
            }
            else
            {
              v57 = Src;
              Src[2] = (void *)(v55 + 1);
              if ( v56 > 7 )
                v57 = (void **)*Src;
              *(_DWORD *)((char *)v57 + 2 * v55) = 48;
            }
            std::wstring::operator+=(Src);
            result = (void **)std::wstring::operator+=(Src);
          }
          break;
      }
      ++v5;
    }
    while ( v5 != v7 );
  }
  return result;
}

```

## disassembly

```asm
0x14000b5a0  push    rbx
0x14000b5a2  push    rbp
0x14000b5a3  push    r14
0x14000b5a5  sub     rsp, 30h
0x14000b5a9  cmp     qword ptr [rdx+18h], 7
0x14000b5ae  mov     rbx, rcx
0x14000b5b1  jbe     short loc_14000B5BE
0x14000b5b3  mov     rcx, [rdx]
0x14000b5b6  mov     r8, rcx
0x14000b5b9  mov     rbp, rcx
0x14000b5bc  jmp     short loc_14000B5C7
0x14000b5be  mov     r8, rdx
0x14000b5c1  mov     rcx, rdx
0x14000b5c4  mov     rbp, rdx
0x14000b5c7  mov     rax, [rdx+10h]
0x14000b5cb  lea     r14, [r8+rax*2]
0x14000b5cf  cmp     rcx, r14
0x14000b5d2  jz      loc_14000B790
0x14000b5d8  mov     [rsp+48h+arg_0], rsi
0x14000b5dd  mov     r11d, 22h ; '"'
0x14000b5e3  mov     [rsp+48h+arg_8], rdi
0x14000b5e8  lea     rsi, [rbx+18h]
0x14000b5ec  mov     [rsp+48h+arg_10], r12
0x14000b5f1  lea     rdi, [rbx+10h]
0x14000b5f5  mov     [rsp+48h+var_20], r13
0x14000b5fa  mov     r10d, 75h ; 'u'
0x14000b600  mov     [rsp+48h+var_28], r15
0x14000b605  lea     r13, __ImageBase
0x14000b60c  mov     r15d, 5Ch ; '\'
0x14000b612  mov     r12d, 30h ; '0'
0x14000b618  nop     dword ptr [rax+rax+00000000h]
0x14000b620  movzx   r9d, word ptr [rbp+0]
0x14000b625  lea     eax, [r9-8]; switch 85 cases
0x14000b629  cmp     eax, 54h
0x14000b62c  ja      def_14000B648; jumptable 000000014000B648 default case, cases 11,14-33,35-91
0x14000b632  cdqe
0x14000b634  movzx   eax, ds:(byte_14000BB78 - 140000000h)[rax+r13]
0x14000b63d  mov     ecx, ds:(jpt_14000B648 - 140000000h)[r13+rax*4]
0x14000b645  add     rcx, r13
0x14000b648  jmp     rcx; switch jump
0x14000b64a  mov     rcx, [rdi]; jumptable 000000014000B648 case 34
0x14000b64d  mov     rdx, [rsi]
0x14000b650  cmp     rcx, rdx
0x14000b653  jnb     short loc_14000B66E
0x14000b655  lea     rax, [rcx+1]
0x14000b659  mov     r8, rbx
0x14000b65c  mov     [rdi], rax
0x14000b65f  cmp     rdx, 7
0x14000b663  jbe     short loc_14000B668
0x14000b665  mov     r8, [rbx]
0x14000b668  mov     [r8+rcx*2], r15d
0x14000b66c  jmp     short loc_14000B687
0x14000b66e  mov     r9d, r15d
0x14000b671  xor     r8d, r8d
0x14000b674  mov     edx, 1
0x14000b679  mov     rcx, rbx; Src
0x14000b67c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b681  mov     r11d, 22h ; '"'
0x14000b687  mov     rcx, [rdi]
0x14000b68a  mov     rdx, [rsi]
0x14000b68d  cmp     rcx, rdx
0x14000b690  jnb     short loc_14000B6CD
0x14000b692  lea     rax, [rcx+1]
0x14000b696  mov     [rdi], rax
0x14000b699  cmp     rdx, 7
0x14000b69d  jbe     short loc_14000B6B6
0x14000b69f  mov     rdx, [rbx]
0x14000b6a2  lea     rdi, [rbx+10h]
0x14000b6a6  lea     rsi, [rbx+18h]
0x14000b6aa  mov     dword ptr [rdx+rcx*2], 22h ; '"'
0x14000b6b1  jmp     loc_14000B75E
0x14000b6b6  mov     rdx, rbx
0x14000b6b9  mov     dword ptr [rbx+rcx*2], 22h ; '"'
0x14000b6c0  lea     rdi, [rbx+10h]
0x14000b6c4  lea     rsi, [rbx+18h]
0x14000b6c8  jmp     loc_14000B75E
0x14000b6cd  mov     r9d, r11d
0x14000b6d0  xor     r8d, r8d
0x14000b6d3  mov     edx, 1
0x14000b6d8  mov     rcx, rbx; Src
0x14000b6db  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b6e0  lea     rdi, [rbx+10h]
0x14000b6e4  lea     rsi, [rbx+18h]
0x14000b6e8  jmp     short loc_14000B75E
0x14000b6ea  mov     rcx, [rdi]; jumptable 000000014000B648 case 92
0x14000b6ed  mov     rdx, [rsi]
0x14000b6f0  cmp     rcx, rdx
0x14000b6f3  jnb     short loc_14000B70E
0x14000b6f5  lea     rax, [rcx+1]
0x14000b6f9  mov     r8, rbx
0x14000b6fc  mov     [rdi], rax
0x14000b6ff  cmp     rdx, 7
0x14000b703  jbe     short loc_14000B708
0x14000b705  mov     r8, [rbx]
0x14000b708  mov     [r8+rcx*2], r15d
0x14000b70c  jmp     short loc_14000B721
0x14000b70e  mov     r9d, r15d
0x14000b711  xor     r8d, r8d
0x14000b714  mov     edx, 1
0x14000b719  mov     rcx, rbx; Src
0x14000b71c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b721  mov     rcx, [rdi]
0x14000b724  mov     rdx, [rsi]
0x14000b727  cmp     rcx, rdx
0x14000b72a  jnb     short loc_14000B74B
0x14000b72c  lea     rax, [rcx+1]
0x14000b730  mov     [rdi], rax
0x14000b733  cmp     rdx, 7
0x14000b737  jbe     short loc_14000B742
0x14000b739  mov     rdx, [rbx]
0x14000b73c  mov     [rdx+rcx*2], r15d
0x14000b740  jmp     short loc_14000B75E
0x14000b742  mov     rdx, rbx
0x14000b745  mov     [rbx+rcx*2], r15d
0x14000b749  jmp     short loc_14000B75E
0x14000b74b  mov     r9d, r15d
0x14000b74e  xor     r8d, r8d
0x14000b751  mov     edx, 1
0x14000b756  mov     rcx, rbx; Src
0x14000b759  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b75e  mov     r10d, 75h ; 'u'
0x14000b764  add     rbp, 2
0x14000b768  mov     r11d, 22h ; '"'
0x14000b76e  cmp     rbp, r14
0x14000b771  jnz     loc_14000B620
0x14000b777  mov     r15, [rsp+48h+var_28]
0x14000b77c  mov     r13, [rsp+48h+var_20]
0x14000b781  mov     r12, [rsp+48h+arg_10]
0x14000b786  mov     rdi, [rsp+48h+arg_8]
0x14000b78b  mov     rsi, [rsp+48h+arg_0]
0x14000b790  add     rsp, 30h
0x14000b794  pop     r14
0x14000b796  pop     rbp
0x14000b797  pop     rbx
0x14000b798  retn
0x14000b799  mov     rcx, [rdi]; jumptable 000000014000B648 case 8
0x14000b79c  mov     rdx, [rsi]
0x14000b79f  cmp     rcx, rdx
0x14000b7a2  jnb     short loc_14000B7BD
0x14000b7a4  lea     rax, [rcx+1]
0x14000b7a8  mov     r8, rbx
0x14000b7ab  mov     [rdi], rax
0x14000b7ae  cmp     rdx, 7
0x14000b7b2  jbe     short loc_14000B7B7
0x14000b7b4  mov     r8, [rbx]
0x14000b7b7  mov     [r8+rcx*2], r15d
0x14000b7bb  jmp     short loc_14000B7D0
0x14000b7bd  mov     r9d, r15d
0x14000b7c0  xor     r8d, r8d
0x14000b7c3  mov     edx, 1
0x14000b7c8  mov     rcx, rbx; Src
0x14000b7cb  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b7d0  mov     rcx, [rdi]
0x14000b7d3  mov     rdx, [rsi]
0x14000b7d6  cmp     rcx, rdx
0x14000b7d9  jnb     short loc_14000B806
0x14000b7db  lea     rax, [rcx+1]
0x14000b7df  mov     [rdi], rax
0x14000b7e2  cmp     rdx, 7
0x14000b7e6  jbe     short loc_14000B7F7
0x14000b7e8  mov     rdx, [rbx]
0x14000b7eb  mov     dword ptr [rdx+rcx*2], 62h ; 'b'
0x14000b7f2  jmp     loc_14000B75E
0x14000b7f7  mov     rdx, rbx
0x14000b7fa  mov     dword ptr [rbx+rcx*2], 62h ; 'b'
0x14000b801  jmp     loc_14000B75E
0x14000b806  mov     r9d, 62h ; 'b'
0x14000b80c  jmp     loc_14000B74E
0x14000b811  mov     rcx, [rdi]; jumptable 000000014000B648 case 12
0x14000b814  mov     rdx, [rsi]
0x14000b817  cmp     rcx, rdx
0x14000b81a  jnb     short loc_14000B835
0x14000b81c  lea     rax, [rcx+1]
0x14000b820  mov     r8, rbx
0x14000b823  mov     [rdi], rax
0x14000b826  cmp     rdx, 7
0x14000b82a  jbe     short loc_14000B82F
0x14000b82c  mov     r8, [rbx]
0x14000b82f  mov     [r8+rcx*2], r15d
0x14000b833  jmp     short loc_14000B848
0x14000b835  mov     r9d, r15d
0x14000b838  xor     r8d, r8d
0x14000b83b  mov     edx, 1
0x14000b840  mov     rcx, rbx; Src
0x14000b843  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b848  mov     rcx, [rdi]
0x14000b84b  mov     rdx, [rsi]
0x14000b84e  cmp     rcx, rdx
0x14000b851  jnb     short loc_14000B87F
0x14000b853  lea     rax, [rcx+1]
0x14000b857  mov     [rbx+10h], rax
0x14000b85b  cmp     rdx, 7
0x14000b85f  jbe     short loc_14000B870
0x14000b861  mov     rdx, [rbx]
0x14000b864  mov     dword ptr [rdx+rcx*2], 66h ; 'f'
0x14000b86b  jmp     loc_14000B75E
0x14000b870  mov     rdx, rbx
0x14000b873  mov     dword ptr [rbx+rcx*2], 66h ; 'f'
0x14000b87a  jmp     loc_14000B75E
0x14000b87f  mov     r9d, 66h ; 'f'
0x14000b885  jmp     loc_14000B74E
0x14000b88a  mov     rcx, [rdi]; jumptable 000000014000B648 case 13
0x14000b88d  mov     rdx, [rsi]
0x14000b890  cmp     rcx, rdx
0x14000b893  jnb     short loc_14000B8AE
0x14000b895  lea     rax, [rcx+1]
0x14000b899  mov     r8, rbx
0x14000b89c  mov     [rdi], rax
0x14000b89f  cmp     rdx, 7
0x14000b8a3  jbe     short loc_14000B8A8
0x14000b8a5  mov     r8, [rbx]
0x14000b8a8  mov     [r8+rcx*2], r15d
0x14000b8ac  jmp     short loc_14000B8C1
0x14000b8ae  mov     r9d, r15d
0x14000b8b1  xor     r8d, r8d
0x14000b8b4  mov     edx, 1
0x14000b8b9  mov     rcx, rbx; Src
0x14000b8bc  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b8c1  mov     rcx, [rdi]
0x14000b8c4  mov     rdx, [rsi]
0x14000b8c7  cmp     rcx, rdx
0x14000b8ca  jnb     short loc_14000B8F8
0x14000b8cc  lea     rax, [rcx+1]
0x14000b8d0  mov     [rbx+10h], rax
0x14000b8d4  cmp     rdx, 7
0x14000b8d8  jbe     short loc_14000B8E9
0x14000b8da  mov     rdx, [rbx]
0x14000b8dd  mov     dword ptr [rdx+rcx*2], 72h ; 'r'
0x14000b8e4  jmp     loc_14000B75E
0x14000b8e9  mov     rdx, rbx
0x14000b8ec  mov     dword ptr [rbx+rcx*2], 72h ; 'r'
0x14000b8f3  jmp     loc_14000B75E
0x14000b8f8  mov     r9d, 72h ; 'r'
0x14000b8fe  jmp     loc_14000B74E
0x14000b903  mov     rcx, [rdi]; jumptable 000000014000B648 case 10
0x14000b906  mov     rdx, [rsi]
0x14000b909  cmp     rcx, rdx
0x14000b90c  jnb     short loc_14000B927
0x14000b90e  lea     rax, [rcx+1]
0x14000b912  mov     r8, rbx
0x14000b915  mov     [rdi], rax
0x14000b918  cmp     rdx, 7
0x14000b91c  jbe     short loc_14000B921
0x14000b91e  mov     r8, [rbx]
0x14000b921  mov     [r8+rcx*2], r15d
0x14000b925  jmp     short loc_14000B93A
0x14000b927  mov     r9d, r15d
0x14000b92a  xor     r8d, r8d
0x14000b92d  mov     edx, 1
0x14000b932  mov     rcx, rbx; Src
0x14000b935  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b93a  mov     rcx, [rdi]
0x14000b93d  mov     rdx, [rsi]
0x14000b940  cmp     rcx, rdx
0x14000b943  jnb     short loc_14000B971
0x14000b945  lea     rax, [rcx+1]
0x14000b949  mov     [rbx+10h], rax
0x14000b94d  cmp     rdx, 7
0x14000b951  jbe     short loc_14000B962
0x14000b953  mov     rdx, [rbx]
0x14000b956  mov     dword ptr [rdx+rcx*2], 6Eh ; 'n'
0x14000b95d  jmp     loc_14000B75E
0x14000b962  mov     rdx, rbx
0x14000b965  mov     dword ptr [rbx+rcx*2], 6Eh ; 'n'
0x14000b96c  jmp     loc_14000B75E
0x14000b971  mov     r9d, 6Eh ; 'n'
0x14000b977  jmp     loc_14000B74E
0x14000b97c  mov     rcx, [rdi]; jumptable 000000014000B648 case 9
0x14000b97f  mov     rdx, [rsi]
0x14000b982  cmp     rcx, rdx
0x14000b985  jnb     short loc_14000B9A0
0x14000b987  lea     rax, [rcx+1]
0x14000b98b  mov     r8, rbx
0x14000b98e  mov     [rdi], rax
0x14000b991  cmp     rdx, 7
0x14000b995  jbe     short loc_14000B99A
0x14000b997  mov     r8, [rbx]
0x14000b99a  mov     [r8+rcx*2], r15d
0x14000b99e  jmp     short loc_14000B9B3
0x14000b9a0  mov     r9d, r15d
0x14000b9a3  xor     r8d, r8d
0x14000b9a6  mov     edx, 1
0x14000b9ab  mov     rcx, rbx; Src
0x14000b9ae  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000b9b3  mov     rcx, [rdi]
0x14000b9b6  mov     rdx, [rsi]
0x14000b9b9  cmp     rcx, rdx
0x14000b9bc  jnb     short loc_14000B9EA
0x14000b9be  lea     rax, [rcx+1]
0x14000b9c2  mov     [rbx+10h], rax
0x14000b9c6  cmp     rdx, 7
0x14000b9ca  jbe     short loc_14000B9DB
0x14000b9cc  mov     rdx, [rbx]
0x14000b9cf  mov     dword ptr [rdx+rcx*2], 74h ; 't'
0x14000b9d6  jmp     loc_14000B75E
0x14000b9db  mov     rdx, rbx
0x14000b9de  mov     dword ptr [rbx+rcx*2], 74h ; 't'
0x14000b9e5  jmp     loc_14000B75E
0x14000b9ea  mov     r9d, 74h ; 't'
0x14000b9f0  jmp     loc_14000B74E
  ... truncated ...
```
