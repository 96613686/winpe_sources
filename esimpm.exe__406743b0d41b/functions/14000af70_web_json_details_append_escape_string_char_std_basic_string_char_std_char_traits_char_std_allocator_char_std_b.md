# web::json::details::append_escape_string<char>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x14000af70`
- end: `0x14000b58d`
- name: `??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z`
- size: `1565`
- prototype: `void __fastcall(char *Src, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000bf50`
- `0x14000c280`

## callees

- `0x14000af70`
- `0x140037140`

## pseudocode

```c
void __fastcall web::json::details::append_escape_string<char>(char *Src, _QWORD *a2)
{
  unsigned __int8 *v3; // rcx
  _QWORD *v4; // r8
  char *v5; // r14
  unsigned __int8 *v6; // rbp
  unsigned __int64 *v7; // rsi
  unsigned __int64 *v8; // rdi
  char v9; // r9
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  char *v17; // rax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  char *v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  char *v27; // rax
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  char *v32; // rax
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  char *v37; // rax
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rdx
  char *v42; // rax
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  char *v47; // rax
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rdx
  char *v50; // rax
  unsigned __int64 v51; // rcx
  unsigned __int64 v52; // rdx
  char *v53; // rax
  unsigned __int64 v54; // rcx
  unsigned __int64 v55; // rdx
  char *v56; // rax
  unsigned __int64 v57; // rcx
  unsigned __int64 v58; // rdx
  char v59; // r9
  char *v60; // rax
  char *v61; // rax

  if ( a2[3] <= 0xFu )
  {
    v4 = a2;
    v3 = (unsigned __int8 *)a2;
    v5 = (char *)a2;
  }
  else
  {
    v3 = (unsigned __int8 *)*a2;
    v4 = (_QWORD *)*a2;
    v5 = (char *)*a2;
  }
  v6 = (unsigned __int8 *)v4 + a2[2];
  if ( v3 != v6 )
  {
    v7 = (unsigned __int64 *)(Src + 24);
    v8 = (unsigned __int64 *)(Src + 16);
    while ( 1 )
    {
      v9 = *v5;
      switch ( *v5 )
      {
        case 8:
          v20 = *v8;
          v21 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v20 + 1;
            v22 = Src;
            if ( v21 > 0xF )
              v22 = *(char **)Src;
            *(_WORD *)&v22[v20] = 92;
          }
          v23 = *v8;
          v24 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *v8 = v23 + 1;
          if ( v24 <= 0xF )
            *(_WORD *)&Src[v23] = 98;
          else
            *(_WORD *)(*(_QWORD *)Src + v23) = 98;
          goto LABEL_27;
        case 9:
          v40 = *v8;
          v41 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v40 + 1;
            v42 = Src;
            if ( v41 > 0xF )
              v42 = *(char **)Src;
            *(_WORD *)&v42[v40] = 92;
          }
          v43 = *v8;
          v44 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v43 + 1;
          if ( v44 <= 0xF )
            *(_WORD *)&Src[v43] = 116;
          else
            *(_WORD *)(*(_QWORD *)Src + v43) = 116;
          goto LABEL_27;
        case 10:
          v35 = *v8;
          v36 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v35 + 1;
            v37 = Src;
            if ( v36 > 0xF )
              v37 = *(char **)Src;
            *(_WORD *)&v37[v35] = 92;
          }
          v38 = *v8;
          v39 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v38 + 1;
          if ( v39 <= 0xF )
            *(_WORD *)&Src[v38] = 110;
          else
            *(_WORD *)(*(_QWORD *)Src + v38) = 110;
          goto LABEL_27;
        case 12:
          v25 = *v8;
          v26 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v25 + 1;
            v27 = Src;
            if ( v26 > 0xF )
              v27 = *(char **)Src;
            *(_WORD *)&v27[v25] = 92;
          }
          v28 = *v8;
          v29 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v28 + 1;
          if ( v29 <= 0xF )
            *(_WORD *)&Src[v28] = 102;
          else
            *(_WORD *)(*(_QWORD *)Src + v28) = 102;
          goto LABEL_27;
        case 13:
          v30 = *v8;
          v31 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v30 + 1;
            v32 = Src;
            if ( v31 > 0xF )
              v32 = *(char **)Src;
            *(_WORD *)&v32[v30] = 92;
          }
          v33 = *v8;
          v34 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v33 + 1;
          if ( v34 <= 0xF )
            *(_WORD *)&Src[v33] = 114;
          else
            *(_WORD *)(*(_QWORD *)Src + v33) = 114;
          goto LABEL_27;
        case 34:
          v10 = *v8;
          v11 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v10 + 1;
            v12 = Src;
            if ( v11 > 0xF )
              v12 = *(char **)Src;
            *(_WORD *)&v12[v10] = 92;
          }
          v13 = *v8;
          v14 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            v8 = (unsigned __int64 *)(Src + 16);
            v7 = (unsigned __int64 *)(Src + 24);
          }
          else
          {
            *v8 = v13 + 1;
            if ( v14 <= 0xF )
            {
              *(_WORD *)&Src[v13] = 34;
              v8 = (unsigned __int64 *)(Src + 16);
              v7 = (unsigned __int64 *)(Src + 24);
            }
            else
            {
              v8 = (unsigned __int64 *)(Src + 16);
              v7 = (unsigned __int64 *)(Src + 24);
              *(_WORD *)(v13 + *(_QWORD *)Src) = 34;
            }
          }
          goto LABEL_27;
        case 92:
          v15 = *v8;
          v16 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v15 + 1;
            v17 = Src;
            if ( v16 > 0xF )
              v17 = *(char **)Src;
            *(_WORD *)&v17[v15] = 92;
          }
          v18 = *v8;
          v19 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *v8 = v18 + 1;
          if ( v19 <= 0xF )
            *(_WORD *)&Src[v18] = 92;
          else
            *(_WORD *)(v18 + *(_QWORD *)Src) = 92;
          goto LABEL_27;
        default:
          v45 = *v8;
          v46 = *v7;
          if ( (unsigned __int8)v9 > 0x1Fu )
          {
            if ( v45 < v46 )
            {
              *v8 = v45 + 1;
              goto LABEL_109;
            }
          }
          else
          {
            if ( v45 >= v46 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *v8 = v45 + 1;
              v47 = Src;
              if ( v46 > 0xF )
                v47 = *(char **)Src;
              *(_WORD *)&v47[v45] = 92;
            }
            v48 = *((_QWORD *)Src + 2);
            v49 = *((_QWORD *)Src + 3);
            if ( v48 >= v49 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v48 + 1;
              v50 = Src;
              if ( v49 > 0xF )
                v50 = *(char **)Src;
              *(_WORD *)&v50[v48] = 117;
            }
            v51 = *((_QWORD *)Src + 2);
            v52 = *((_QWORD *)Src + 3);
            if ( v51 >= v52 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v51 + 1;
              v53 = Src;
              if ( v52 > 0xF )
                v53 = *(char **)Src;
              *(_WORD *)&v53[v51] = 48;
            }
            v54 = *((_QWORD *)Src + 2);
            v55 = *((_QWORD *)Src + 3);
            if ( v54 >= v55 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v54 + 1;
              v56 = Src;
              if ( v55 > 0xF )
                v56 = *(char **)Src;
              *(_WORD *)&v56[v54] = 48;
            }
            v57 = *((_QWORD *)Src + 2);
            v58 = *((_QWORD *)Src + 3);
            v59 = `web::json::details::append_escape_string<char>'::`11'::intToHex[(unsigned __int64)(unsigned __int8)*v5 >> 4];
            if ( v57 >= v58 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v57 + 1;
              v60 = Src;
              if ( v58 > 0xF )
                v60 = *(char **)Src;
              v60[v57] = v59;
              v60[v57 + 1] = 0;
            }
            v45 = *((_QWORD *)Src + 2);
            v46 = *((_QWORD *)Src + 3);
            v9 = `web::json::details::append_escape_string<char>'::`11'::intToHex[*v5 & 0xF];
            if ( v45 < v46 )
            {
              *((_QWORD *)Src + 2) = v45 + 1;
LABEL_109:
              v61 = Src;
              if ( v46 > 0xF )
                v61 = *(char **)Src;
              v61[v45 + 1] = 0;
              v61[v45] = v9;
              goto LABEL_27;
            }
          }
LABEL_26:
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
LABEL_27:
          if ( ++v5 == (char *)v6 )
            return;
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x14000af70  push    rbx
0x14000af72  push    rbp
0x14000af73  push    r14
0x14000af75  sub     rsp, 20h
0x14000af79  cmp     qword ptr [rdx+18h], 0Fh
0x14000af7e  mov     rbx, rcx
0x14000af81  jbe     short loc_14000AF8E
0x14000af83  mov     rcx, [rdx]
0x14000af86  mov     r8, rcx
0x14000af89  mov     r14, rcx
0x14000af8c  jmp     short loc_14000AF97
0x14000af8e  mov     r8, rdx
0x14000af91  mov     rcx, rdx
0x14000af94  mov     r14, rdx
0x14000af97  mov     rbp, [rdx+10h]
0x14000af9b  add     rbp, r8
0x14000af9e  cmp     rcx, rbp
0x14000afa1  jz      loc_14000B12A
0x14000afa7  mov     [rsp+38h+arg_0], rsi
0x14000afac  lea     rsi, [rbx+18h]
0x14000afb0  mov     [rsp+38h+arg_8], rdi
0x14000afb5  lea     rdi, [rbx+10h]
0x14000afb9  mov     [rsp+38h+arg_10], r15
0x14000afbe  lea     r15, __ImageBase
0x14000afc5  nop     word ptr [rax+rax+00000000h]
0x14000afd0  movsx   r9d, byte ptr [r14]
0x14000afd4  mov     eax, r9d
0x14000afd7  add     eax, 0FFFFFFF8h; switch 85 cases
0x14000afda  cmp     eax, 54h
0x14000afdd  ja      def_14000AFF9; jumptable 000000014000AFF9 default case, cases 11,14-33,35-91
0x14000afe3  cdqe
0x14000afe5  movzx   eax, ds:(byte_14000B538 - 140000000h)[r15+rax]
0x14000afee  mov     ecx, ds:(jpt_14000AFF9 - 140000000h)[r15+rax*4]
0x14000aff6  add     rcx, r15
0x14000aff9  jmp     rcx; switch jump
0x14000affb  mov     rcx, [rdi]; jumptable 000000014000AFF9 case 34
0x14000affe  mov     rdx, [rsi]
0x14000b001  cmp     rcx, rdx
0x14000b004  jnb     short loc_14000B021
0x14000b006  lea     rax, [rcx+1]
0x14000b00a  mov     [rdi], rax
0x14000b00d  mov     rax, rbx
0x14000b010  cmp     rdx, 0Fh
0x14000b014  jbe     short loc_14000B019
0x14000b016  mov     rax, [rbx]
0x14000b019  mov     word ptr [rcx+rax], 5Ch ; '\'
0x14000b01f  jmp     short loc_14000B034
0x14000b021  mov     r9b, 5Ch ; '\'
0x14000b024  xor     r8d, r8d
0x14000b027  mov     edx, 1
0x14000b02c  mov     rcx, rbx; Src
0x14000b02f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b034  mov     rcx, [rdi]
0x14000b037  mov     rdx, [rsi]
0x14000b03a  cmp     rcx, rdx
0x14000b03d  jnb     short loc_14000B078
0x14000b03f  lea     rax, [rcx+1]
0x14000b043  mov     [rdi], rax
0x14000b046  cmp     rdx, 0Fh
0x14000b04a  jbe     short loc_14000B062
0x14000b04c  mov     rax, [rbx]
0x14000b04f  lea     rdi, [rbx+10h]
0x14000b053  lea     rsi, [rbx+18h]
0x14000b057  mov     word ptr [rcx+rax], 22h ; '"'
0x14000b05d  jmp     loc_14000B10F
0x14000b062  mov     rax, rbx
0x14000b065  mov     word ptr [rcx+rbx], 22h ; '"'
0x14000b06b  lea     rdi, [rbx+10h]
0x14000b06f  lea     rsi, [rbx+18h]
0x14000b073  jmp     loc_14000B10F
0x14000b078  mov     r9b, 22h ; '"'
0x14000b07b  xor     r8d, r8d
0x14000b07e  mov     edx, 1
0x14000b083  mov     rcx, rbx; Src
0x14000b086  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b08b  lea     rdi, [rbx+10h]
0x14000b08f  lea     rsi, [rbx+18h]
0x14000b093  jmp     short loc_14000B10F
0x14000b095  mov     rcx, [rdi]; jumptable 000000014000AFF9 case 92
0x14000b098  mov     rdx, [rsi]
0x14000b09b  cmp     rcx, rdx
0x14000b09e  jnb     short loc_14000B0BB
0x14000b0a0  lea     rax, [rcx+1]
0x14000b0a4  mov     [rdi], rax
0x14000b0a7  mov     rax, rbx
0x14000b0aa  cmp     rdx, 0Fh
0x14000b0ae  jbe     short loc_14000B0B3
0x14000b0b0  mov     rax, [rbx]
0x14000b0b3  mov     word ptr [rcx+rax], 5Ch ; '\'
0x14000b0b9  jmp     short loc_14000B0CE
0x14000b0bb  mov     r9b, 5Ch ; '\'
0x14000b0be  xor     r8d, r8d
0x14000b0c1  mov     edx, 1
0x14000b0c6  mov     rcx, rbx; Src
0x14000b0c9  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b0ce  mov     rcx, [rdi]
0x14000b0d1  mov     rdx, [rsi]
0x14000b0d4  cmp     rcx, rdx
0x14000b0d7  jnb     short loc_14000B0FC
0x14000b0d9  lea     rax, [rcx+1]
0x14000b0dd  mov     [rdi], rax
0x14000b0e0  cmp     rdx, 0Fh
0x14000b0e4  jbe     short loc_14000B0F1
0x14000b0e6  mov     rax, [rbx]
0x14000b0e9  mov     word ptr [rcx+rax], 5Ch ; '\'
0x14000b0ef  jmp     short loc_14000B10F
0x14000b0f1  mov     rax, rbx
0x14000b0f4  mov     word ptr [rcx+rbx], 5Ch ; '\'
0x14000b0fa  jmp     short loc_14000B10F
0x14000b0fc  mov     r9b, 5Ch ; '\'
0x14000b0ff  xor     r8d, r8d
0x14000b102  mov     edx, 1
0x14000b107  mov     rcx, rbx; Src
0x14000b10a  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b10f  inc     r14
0x14000b112  cmp     r14, rbp
0x14000b115  jnz     loc_14000AFD0
0x14000b11b  mov     r15, [rsp+38h+arg_10]
0x14000b120  mov     rdi, [rsp+38h+arg_8]
0x14000b125  mov     rsi, [rsp+38h+arg_0]
0x14000b12a  add     rsp, 20h
0x14000b12e  pop     r14
0x14000b130  pop     rbp
0x14000b131  pop     rbx
0x14000b132  retn
0x14000b133  mov     rcx, [rdi]; jumptable 000000014000AFF9 case 8
0x14000b136  mov     rdx, [rsi]
0x14000b139  cmp     rcx, rdx
0x14000b13c  jnb     short loc_14000B159
0x14000b13e  lea     rax, [rcx+1]
0x14000b142  mov     [rdi], rax
0x14000b145  mov     rax, rbx
0x14000b148  cmp     rdx, 0Fh
0x14000b14c  jbe     short loc_14000B151
0x14000b14e  mov     rax, [rbx]
0x14000b151  mov     word ptr [rax+rcx], 5Ch ; '\'
0x14000b157  jmp     short loc_14000B16C
0x14000b159  mov     r9b, 5Ch ; '\'
0x14000b15c  xor     r8d, r8d
0x14000b15f  mov     edx, 1
0x14000b164  mov     rcx, rbx; Src
0x14000b167  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b16c  mov     rcx, [rdi]
0x14000b16f  mov     rdx, [rsi]
0x14000b172  cmp     rcx, rdx
0x14000b175  jnb     short loc_14000B19D
0x14000b177  lea     rax, [rcx+1]
0x14000b17b  mov     [rdi], rax
0x14000b17e  cmp     rdx, 0Fh
0x14000b182  jbe     short loc_14000B18F
0x14000b184  mov     rax, [rbx]
0x14000b187  mov     word ptr [rax+rcx], 62h ; 'b'
0x14000b18d  jmp     short loc_14000B10F
0x14000b18f  mov     rax, rbx
0x14000b192  mov     word ptr [rbx+rcx], 62h ; 'b'
0x14000b198  jmp     loc_14000B10F
0x14000b19d  mov     r9b, 62h ; 'b'
0x14000b1a0  jmp     loc_14000B0FF
0x14000b1a5  mov     rcx, [rdi]; jumptable 000000014000AFF9 case 12
0x14000b1a8  mov     rdx, [rsi]
0x14000b1ab  cmp     rcx, rdx
0x14000b1ae  jnb     short loc_14000B1CB
0x14000b1b0  lea     rax, [rcx+1]
0x14000b1b4  mov     [rdi], rax
0x14000b1b7  mov     rax, rbx
0x14000b1ba  cmp     rdx, 0Fh
0x14000b1be  jbe     short loc_14000B1C3
0x14000b1c0  mov     rax, [rbx]
0x14000b1c3  mov     word ptr [rax+rcx], 5Ch ; '\'
0x14000b1c9  jmp     short loc_14000B1DE
0x14000b1cb  mov     r9b, 5Ch ; '\'
0x14000b1ce  xor     r8d, r8d
0x14000b1d1  mov     edx, 1
0x14000b1d6  mov     rcx, rbx; Src
0x14000b1d9  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b1de  mov     rcx, [rdi]
0x14000b1e1  mov     rdx, [rsi]
0x14000b1e4  cmp     rcx, rdx
0x14000b1e7  jnb     short loc_14000B213
0x14000b1e9  lea     rax, [rcx+1]
0x14000b1ed  mov     [rbx+10h], rax
0x14000b1f1  cmp     rdx, 0Fh
0x14000b1f5  jbe     short loc_14000B205
0x14000b1f7  mov     rax, [rbx]
0x14000b1fa  mov     word ptr [rax+rcx], 66h ; 'f'
0x14000b200  jmp     loc_14000B10F
0x14000b205  mov     rax, rbx
0x14000b208  mov     word ptr [rbx+rcx], 66h ; 'f'
0x14000b20e  jmp     loc_14000B10F
0x14000b213  mov     r9b, 66h ; 'f'
0x14000b216  jmp     loc_14000B0FF
0x14000b21b  mov     rcx, [rdi]; jumptable 000000014000AFF9 case 13
0x14000b21e  mov     rdx, [rsi]
0x14000b221  cmp     rcx, rdx
0x14000b224  jnb     short loc_14000B241
0x14000b226  lea     rax, [rcx+1]
0x14000b22a  mov     [rdi], rax
0x14000b22d  mov     rax, rbx
0x14000b230  cmp     rdx, 0Fh
0x14000b234  jbe     short loc_14000B239
0x14000b236  mov     rax, [rbx]
0x14000b239  mov     word ptr [rax+rcx], 5Ch ; '\'
0x14000b23f  jmp     short loc_14000B254
0x14000b241  mov     r9b, 5Ch ; '\'
0x14000b244  xor     r8d, r8d
0x14000b247  mov     edx, 1
0x14000b24c  mov     rcx, rbx; Src
0x14000b24f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b254  mov     rcx, [rdi]
0x14000b257  mov     rdx, [rsi]
0x14000b25a  cmp     rcx, rdx
0x14000b25d  jnb     short loc_14000B289
0x14000b25f  lea     rax, [rcx+1]
0x14000b263  mov     [rbx+10h], rax
0x14000b267  cmp     rdx, 0Fh
0x14000b26b  jbe     short loc_14000B27B
0x14000b26d  mov     rax, [rbx]
0x14000b270  mov     word ptr [rax+rcx], 72h ; 'r'
0x14000b276  jmp     loc_14000B10F
0x14000b27b  mov     rax, rbx
0x14000b27e  mov     word ptr [rbx+rcx], 72h ; 'r'
0x14000b284  jmp     loc_14000B10F
0x14000b289  mov     r9b, 72h ; 'r'
0x14000b28c  jmp     loc_14000B0FF
0x14000b291  mov     rcx, [rdi]; jumptable 000000014000AFF9 case 10
0x14000b294  mov     rdx, [rsi]
0x14000b297  cmp     rcx, rdx
0x14000b29a  jnb     short loc_14000B2B7
0x14000b29c  lea     rax, [rcx+1]
0x14000b2a0  mov     [rdi], rax
0x14000b2a3  mov     rax, rbx
0x14000b2a6  cmp     rdx, 0Fh
0x14000b2aa  jbe     short loc_14000B2AF
0x14000b2ac  mov     rax, [rbx]
0x14000b2af  mov     word ptr [rax+rcx], 5Ch ; '\'
0x14000b2b5  jmp     short loc_14000B2CA
0x14000b2b7  mov     r9b, 5Ch ; '\'
0x14000b2ba  xor     r8d, r8d
0x14000b2bd  mov     edx, 1
0x14000b2c2  mov     rcx, rbx; Src
0x14000b2c5  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b2ca  mov     rcx, [rdi]
0x14000b2cd  mov     rdx, [rsi]
0x14000b2d0  cmp     rcx, rdx
0x14000b2d3  jnb     short loc_14000B2FF
0x14000b2d5  lea     rax, [rcx+1]
0x14000b2d9  mov     [rbx+10h], rax
0x14000b2dd  cmp     rdx, 0Fh
0x14000b2e1  jbe     short loc_14000B2F1
0x14000b2e3  mov     rax, [rbx]
0x14000b2e6  mov     word ptr [rax+rcx], 6Eh ; 'n'
0x14000b2ec  jmp     loc_14000B10F
0x14000b2f1  mov     rax, rbx
0x14000b2f4  mov     word ptr [rbx+rcx], 6Eh ; 'n'
0x14000b2fa  jmp     loc_14000B10F
0x14000b2ff  mov     r9b, 6Eh ; 'n'
0x14000b302  jmp     loc_14000B0FF
0x14000b307  mov     rcx, [rdi]; jumptable 000000014000AFF9 case 9
0x14000b30a  mov     rdx, [rsi]
0x14000b30d  cmp     rcx, rdx
0x14000b310  jnb     short loc_14000B32D
0x14000b312  lea     rax, [rcx+1]
0x14000b316  mov     [rdi], rax
0x14000b319  mov     rax, rbx
0x14000b31c  cmp     rdx, 0Fh
0x14000b320  jbe     short loc_14000B325
0x14000b322  mov     rax, [rbx]
0x14000b325  mov     word ptr [rax+rcx], 5Ch ; '\'
0x14000b32b  jmp     short loc_14000B340
0x14000b32d  mov     r9b, 5Ch ; '\'
0x14000b330  xor     r8d, r8d
0x14000b333  mov     edx, 1
0x14000b338  mov     rcx, rbx; Src
0x14000b33b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000b340  mov     rcx, [rdi]
0x14000b343  mov     rdx, [rsi]
0x14000b346  cmp     rcx, rdx
0x14000b349  jnb     short loc_14000B375
0x14000b34b  lea     rax, [rcx+1]
0x14000b34f  mov     [rbx+10h], rax
0x14000b353  cmp     rdx, 0Fh
0x14000b357  jbe     short loc_14000B367
0x14000b359  mov     rax, [rbx]
0x14000b35c  mov     word ptr [rax+rcx], 74h ; 't'
0x14000b362  jmp     loc_14000B10F
0x14000b367  mov     rax, rbx
0x14000b36a  mov     word ptr [rbx+rcx], 74h ; 't'
0x14000b370  jmp     loc_14000B10F
0x14000b375  mov     r9b, 74h ; 't'
0x14000b378  jmp     loc_14000B0FF
0x14000b37d  mov     rcx, [rdi]; jumptable 000000014000AFF9 default case, cases 11,14-33,35-91
0x14000b380  mov     rdx, [rsi]
0x14000b383  cmp     r9b, 1Fh
0x14000b387  ja      loc_14000B4EC
0x14000b38d  cmp     rcx, rdx
0x14000b390  jnb     short loc_14000B3AD
0x14000b392  lea     rax, [rcx+1]
0x14000b396  mov     [rdi], rax
0x14000b399  mov     rax, rbx
0x14000b39c  cmp     rdx, 0Fh
  ... truncated ...
```
