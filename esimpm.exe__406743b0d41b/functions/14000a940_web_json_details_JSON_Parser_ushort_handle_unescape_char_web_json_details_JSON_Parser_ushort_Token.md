# web::json::details::JSON_Parser<ushort>::handle_unescape_char(web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x14000a940`
- end: `0x14000ac64`
- name: `?handle_unescape_char@?$JSON_Parser@G@details@json@web@@IEAA_NAEAUToken@1234@@Z`
- size: `804`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1400097c0`

## callees

- `0x140002f60`
- `0x140003244`
- `0x140005450`
- `0x140007fd0`
- `0x14000a820`
- `0x14000a940`
- `0x14000dd20`
- `0x140013df8`
- `0x1400147cc`
- `0x1400167fc`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall web::json::details::JSON_Parser<unsigned short>::handle_unescape_char(
        unsigned __int16 (__fastcall ***a1)(_QWORD),
        __int64 a2)
{
  char result; // al
  int v5; // eax
  __int16 v6; // di
  int v7; // eax
  __int64 v8; // rax
  char **v9; // rdi
  const void *v10; // rdx
  void *v11; // rcx
  void **v12; // rcx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r8
  _WORD v15[4]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v16; // [rsp+28h] [rbp-60h]
  _BYTE v17[32]; // [rsp+30h] [rbp-58h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v19; // [rsp+60h] [rbp-28h]
  unsigned __int64 v20; // [rsp+68h] [rbp-20h]

  *(_BYTE *)(a2 + 56) = 1;
  switch ( (**a1)(a1) )
  {
    case '"':
      std::wstring::push_back(a2 + 8, 34);
      return 1;
    case '/':
      std::wstring::push_back(a2 + 8, 47);
      return 1;
    case '\\':
      std::wstring::push_back(a2 + 8, 92);
      return 1;
    case 'b':
      std::wstring::push_back(a2 + 8, 8);
      return 1;
    case 'f':
      std::wstring::push_back(a2 + 8, 12);
      return 1;
    case 'n':
      std::wstring::push_back(a2 + 8, 10);
      return 1;
    case 'r':
      std::wstring::push_back(a2 + 8, 13);
      return 1;
    case 't':
      std::wstring::push_back(a2 + 8, 9);
      return 1;
    case 'u':
      v5 = web::json::details::JSON_Parser<unsigned short>::convert_unicode_to_code_point(a1);
      v6 = v5;
      if ( v5 == -1 )
        return 0;
      if ( v5 >= 55296 && v5 <= 56319 )
      {
        if ( (**a1)(a1) != 92 )
          return 0;
        if ( (**a1)(a1) != 117 )
          return 0;
        v7 = web::json::details::JSON_Parser<unsigned short>::convert_unicode_to_code_point(a1);
        if ( v7 == -1 )
          return 0;
        v15[0] = v6;
        v15[1] = v7;
        *(_OWORD *)Block = 0;
        v19 = 0;
        v20 = 0;
        std::wstring::_Construct<1,unsigned short const *>(Block, v15, 2u);
        v8 = std::wstring::wstring(v17, Block);
        v9 = (char **)v8;
        v16 = v8;
        if ( *(_QWORD *)(v8 + 24) <= 7u )
          v10 = (const void *)v8;
        else
          v10 = *(const void **)v8;
        std::wstring::_Append<unsigned short>((_QWORD *)(a2 + 8), v10, *(_QWORD *)(v8 + 16));
        std::wstring::_Tidy_deallocate(v9);
        if ( v20 > 7 )
        {
          if ( 2 * v20 + 2 < 0x1000 )
          {
            operator delete(Block[0]);
            return 1;
          }
          else
          {
            v11 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v11 - 8) > 0x1F )
              __fastfail(5u);
            operator delete(v11);
            return 1;
          }
        }
        return 1;
      }
      v12 = (void **)(a2 + 8);
      v13 = *(_QWORD *)(a2 + 24);
      v14 = *(_QWORD *)(a2 + 32);
      if ( v13 >= v14 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
          v12,
          1u,
          0,
          v5);
        return 1;
      }
      *(_QWORD *)(a2 + 24) = v13 + 1;
      if ( v14 > 7 )
        v12 = (void **)*v12;
      *((_WORD *)v12 + v13) = v5;
      result = 1;
      *((_WORD *)v12 + v13 + 1) = 0;
      return result;
    default:
      return 0;
  }
}

```

## disassembly

```asm
0x14000a940  mov     [rsp+arg_10], rbx
0x14000a945  mov     [rsp+arg_18], rsi
0x14000a94a  push    rdi
0x14000a94b  sub     rsp, 80h
0x14000a952  mov     rax, cs:__security_cookie
0x14000a959  xor     rax, rsp
0x14000a95c  mov     [rsp+88h+var_18], rax
0x14000a961  mov     rbx, rdx
0x14000a964  mov     rsi, rcx
0x14000a967  mov     byte ptr [rdx+38h], 1
0x14000a96b  mov     rax, [rcx]
0x14000a96e  mov     rax, [rax]
0x14000a971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a976  movzx   ecx, ax
0x14000a979  add     ecx, 0FFFFFFDEh; switch 84 cases
0x14000a97c  cmp     ecx, 53h
0x14000a97f  ja      def_14000A9A1; jumptable 000000014000A9A1 default case, cases 35-46,48-91,93-97,99-101,103-109,111-113,115
0x14000a985  movsxd  rax, ecx
0x14000a988  lea     rdx, __ImageBase
0x14000a98f  movzx   eax, ds:(byte_14000AC10 - 140000000h)[rdx+rax]
0x14000a997  mov     ecx, ds:(jpt_14000A9A1 - 140000000h)[rdx+rax*4]
0x14000a99e  add     rcx, rdx
0x14000a9a1  jmp     rcx; switch jump
0x14000a9a3  mov     edx, 22h ; '"'; jumptable 000000014000A9A1 case 34
0x14000a9a8  lea     rcx, [rbx+8]
0x14000a9ac  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000a9b1  mov     al, 1
0x14000a9b3  jmp     loc_14000ABC4
0x14000a9b8  mov     edx, 5Ch ; '\'; jumptable 000000014000A9A1 case 92
0x14000a9bd  lea     rcx, [rbx+8]
0x14000a9c1  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000a9c6  mov     al, 1
0x14000a9c8  jmp     loc_14000ABC4
0x14000a9cd  mov     edx, 2Fh ; '/'; jumptable 000000014000A9A1 case 47
0x14000a9d2  lea     rcx, [rbx+8]
0x14000a9d6  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000a9db  mov     al, 1
0x14000a9dd  jmp     loc_14000ABC4
0x14000a9e2  mov     edx, 8; jumptable 000000014000A9A1 case 98
0x14000a9e7  lea     rcx, [rbx+8]
0x14000a9eb  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000a9f0  mov     al, 1
0x14000a9f2  jmp     loc_14000ABC4
0x14000a9f7  mov     edx, 0Ch; jumptable 000000014000A9A1 case 102
0x14000a9fc  lea     rcx, [rbx+8]
0x14000aa00  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000aa05  mov     al, 1
0x14000aa07  jmp     loc_14000ABC4
0x14000aa0c  mov     edx, 0Dh; jumptable 000000014000A9A1 case 114
0x14000aa11  lea     rcx, [rbx+8]
0x14000aa15  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000aa1a  mov     al, 1
0x14000aa1c  jmp     loc_14000ABC4
0x14000aa21  mov     edx, 0Ah; jumptable 000000014000A9A1 case 110
0x14000aa26  lea     rcx, [rbx+8]
0x14000aa2a  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000aa2f  mov     al, 1
0x14000aa31  jmp     loc_14000ABC4
0x14000aa36  mov     edx, 9; jumptable 000000014000A9A1 case 116
0x14000aa3b  lea     rcx, [rbx+8]
0x14000aa3f  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x14000aa44  mov     al, 1
0x14000aa46  jmp     loc_14000ABC4
0x14000aa4b  mov     rcx, rsi; jumptable 000000014000A9A1 case 117
0x14000aa4e  call    ?convert_unicode_to_code_point@?$JSON_Parser@G@details@json@web@@IEAAHXZ; web::json::details::JSON_Parser<ushort>::convert_unicode_to_code_point(void)
0x14000aa53  mov     edi, eax
0x14000aa55  cmp     eax, 0FFFFFFFFh
0x14000aa58  jz      def_14000A9A1; jumptable 000000014000A9A1 default case, cases 35-46,48-91,93-97,99-101,103-109,111-113,115
0x14000aa5e  cmp     eax, 0D800h
0x14000aa63  jl      loc_14000AB7C
0x14000aa69  cmp     eax, 0DBFFh
0x14000aa6e  jg      loc_14000AB7C
0x14000aa74  mov     rcx, [rsi]
0x14000aa77  mov     rax, [rcx]
0x14000aa7a  mov     rcx, rsi
0x14000aa7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa82  cmp     ax, 5Ch ; '\'
0x14000aa86  jnz     def_14000A9A1; jumptable 000000014000A9A1 default case, cases 35-46,48-91,93-97,99-101,103-109,111-113,115
0x14000aa8c  mov     rax, [rsi]
0x14000aa8f  mov     rcx, rsi
0x14000aa92  mov     rax, [rax]
0x14000aa95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa9a  cmp     ax, 75h ; 'u'
0x14000aa9e  jnz     def_14000A9A1; jumptable 000000014000A9A1 default case, cases 35-46,48-91,93-97,99-101,103-109,111-113,115
0x14000aaa4  mov     rcx, rsi
0x14000aaa7  call    ?convert_unicode_to_code_point@?$JSON_Parser@G@details@json@web@@IEAAHXZ; web::json::details::JSON_Parser<ushort>::convert_unicode_to_code_point(void)
0x14000aaac  cmp     eax, 0FFFFFFFFh
0x14000aaaf  jz      def_14000A9A1; jumptable 000000014000A9A1 default case, cases 35-46,48-91,93-97,99-101,103-109,111-113,115
0x14000aab5  mov     [rsp+88h+var_68], di
0x14000aaba  mov     [rsp+88h+var_66], ax
0x14000aabf  xorps   xmm0, xmm0
0x14000aac2  movups  xmmword ptr [rsp+88h+Block], xmm0
0x14000aac7  xor     eax, eax
0x14000aac9  mov     [rsp+88h+var_28], rax
0x14000aace  mov     [rsp+88h+var_20], rax
0x14000aad3  mov     r8d, 2
0x14000aad9  lea     rdx, [rsp+88h+var_68]
0x14000aade  lea     rcx, [rsp+88h+Block]
0x14000aae3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000aae8  nop
0x14000aae9  lea     rdx, [rsp+88h+Block]
0x14000aaee  lea     rcx, [rsp+88h+var_58]
0x14000aaf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000aaf8  mov     rdi, rax
0x14000aafb  mov     [rsp+88h+var_60], rax
0x14000ab00  cmp     qword ptr [rax+18h], 7
0x14000ab05  jbe     short loc_14000AB0C
0x14000ab07  mov     rdx, [rax]
0x14000ab0a  jmp     short loc_14000AB0F
0x14000ab0c  mov     rdx, rdi
0x14000ab0f  lea     rcx, [rbx+8]; Src
0x14000ab13  mov     r8, [rax+10h]
0x14000ab17  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14000ab1c  nop
0x14000ab1d  mov     rcx, rdi
0x14000ab20  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000ab25  nop
0x14000ab26  mov     rdx, [rsp+88h+var_20]
0x14000ab2b  cmp     rdx, 7
0x14000ab2f  jbe     loc_14000ABBE
0x14000ab35  mov     rax, [rsp+88h+Block]
0x14000ab3a  lea     rdx, ds:2[rdx*2]
0x14000ab42  cmp     rdx, 1000h
0x14000ab49  jb      short loc_14000AB70
0x14000ab4b  mov     rcx, [rax-8]; Block
0x14000ab4f  sub     rax, rcx
0x14000ab52  sub     rax, 8
0x14000ab56  cmp     rax, 1Fh
0x14000ab5a  ja      short loc_14000AB69
0x14000ab5c  add     rdx, 27h ; '''
0x14000ab60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ab65  mov     al, 1
0x14000ab67  jmp     short loc_14000ABC4
0x14000ab69  mov     ecx, 5
0x14000ab6e  int     29h; Win8: RtlFailFast(ecx)
0x14000ab70  mov     rcx, rax; Block
0x14000ab73  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ab78  mov     al, 1
0x14000ab7a  jmp     short loc_14000ABC4
0x14000ab7c  lea     rcx, [rbx+8]; Src
0x14000ab80  mov     rdx, [rcx+10h]
0x14000ab84  mov     r8, [rcx+18h]
0x14000ab88  cmp     rdx, r8
0x14000ab8b  jnb     short loc_14000ABAD
0x14000ab8d  lea     rax, [rdx+1]
0x14000ab91  mov     [rcx+10h], rax
0x14000ab95  cmp     r8, 7
0x14000ab99  jbe     short loc_14000AB9E
0x14000ab9b  mov     rcx, [rcx]
0x14000ab9e  mov     [rcx+rdx*2], di
0x14000aba2  xor     eax, eax
0x14000aba4  mov     [rcx+rdx*2+2], ax
0x14000aba9  mov     al, 1
0x14000abab  jmp     short loc_14000ABC4
0x14000abad  movzx   r9d, di
0x14000abb1  xor     r8d, r8d
0x14000abb4  mov     edx, 1
0x14000abb9  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000abbe  mov     al, 1
0x14000abc0  jmp     short loc_14000ABC4
0x14000abc2  xor     al, al; jumptable 000000014000A9A1 default case, cases 35-46,48-91,93-97,99-101,103-109,111-113,115
0x14000abc4  mov     rcx, [rsp+88h+var_18]
0x14000abc9  xor     rcx, rsp; StackCookie
0x14000abcc  call    __security_check_cookie
0x14000abd1  lea     r11, [rsp+88h+var_8]
0x14000abd9  mov     rbx, [r11+20h]
0x14000abdd  mov     rsi, [r11+28h]
0x14000abe1  mov     rsp, r11
0x14000abe4  pop     rdi
0x14000abe5  retn
```
