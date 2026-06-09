# nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(void)

- ea: `0x180024a70`
- end: `0x180024bc8`
- name: `?get_token_string@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `344`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017b94`
- `0x180018df4`
- `0x180024524`
- `0x180025448`

## callees

- `0x180002490`
- `0x180002fc8`
- `0x1800159b0`
- `0x180015b04`
- `0x180024a70`
- `0x18002e008`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
        __int64 a1,
        _QWORD *a2)
{
  unsigned __int8 *v3; // rbp
  unsigned __int8 *i; // r14
  int v5; // r9d
  size_t Size; // rsi
  __int64 v7; // rcx
  _QWORD *v8; // rax
  char *v9; // rbx
  unsigned __int64 v10; // rcx
  _QWORD *v11; // rax
  char Buffer[8]; // [rsp+40h] [rbp-38h] BYREF
  char v14; // [rsp+48h] [rbp-30h]

  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 15;
  *(_BYTE *)a2 = 0;
  v3 = *(unsigned __int8 **)(a1 + 64);
  for ( i = *(unsigned __int8 **)(a1 + 56); i != v3; ++i )
  {
    v5 = *i;
    if ( (unsigned __int8)v5 > 0x1Fu )
    {
      v10 = a2[2];
      if ( v10 >= a2[3] )
      {
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(a2);
      }
      else
      {
        a2[2] = v10 + 1;
        v11 = a2;
        if ( a2[3] > 0xFu )
          v11 = (_QWORD *)*a2;
        *((_BYTE *)v11 + v10) = v5;
        *((_BYTE *)v11 + v10 + 1) = 0;
      }
    }
    else
    {
      *(_QWORD *)Buffer = 0;
      v14 = 0;
      snprintf(Buffer, 9u, "<U+%.4X>", v5);
      Size = -1;
      do
        ++Size;
      while ( Buffer[Size] );
      v7 = a2[2];
      if ( Size > a2[3] - v7 )
      {
        std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
          a2,
          Size);
      }
      else
      {
        a2[2] = v7 + Size;
        v8 = a2;
        if ( a2[3] > 0xFu )
          v8 = (_QWORD *)*a2;
        v9 = (char *)v8 + v7;
        memmove_0((char *)v8 + v7, Buffer, Size);
        v9[Size] = 0;
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180024a70  mov     [rsp+arg_10], rbx
0x180024a75  mov     [rsp+arg_18], rbp
0x180024a7a  push    rsi
0x180024a7b  push    rdi
0x180024a7c  push    r14
0x180024a7e  sub     rsp, 60h
0x180024a82  mov     rax, cs:__security_cookie
0x180024a89  xor     rax, rsp
0x180024a8c  mov     [rsp+78h+var_28], rax
0x180024a91  mov     rdi, rdx
0x180024a94  mov     [rsp+78h+var_40], rdx
0x180024a99  mov     [rsp+78h+var_48], 0
0x180024aa1  xorps   xmm0, xmm0
0x180024aa4  movups  xmmword ptr [rdx], xmm0
0x180024aa7  mov     qword ptr [rdx+10h], 0
0x180024aaf  mov     qword ptr [rdx+18h], 0Fh
0x180024ab7  mov     byte ptr [rdx], 0
0x180024aba  mov     [rsp+78h+var_48], 1
0x180024ac2  mov     rbp, [rcx+40h]
0x180024ac6  mov     r14, [rcx+38h]
0x180024aca  jmp     loc_180024B99
0x180024acf  movzx   r9d, byte ptr [r14]
0x180024ad3  cmp     r9b, 1Fh
0x180024ad7  ja      loc_180024B64
0x180024add  xor     eax, eax
0x180024adf  mov     qword ptr [rsp+78h+Buffer], rax
0x180024ae4  mov     [rsp+78h+var_30], al
0x180024ae8  lea     r8, aU4x; "<U+%.4X>"
0x180024aef  lea     edx, [rax+9]; BufferCount
0x180024af2  lea     rcx, [rsp+78h+Buffer]; Buffer
0x180024af7  call    snprintf
0x180024afc  lea     rax, [rsp+78h+Buffer]
0x180024b01  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024b05  inc     rsi
0x180024b08  cmp     byte ptr [rax+rsi], 0
0x180024b0c  jnz     short loc_180024B05
0x180024b0e  mov     rcx, [rdi+10h]
0x180024b12  mov     rax, [rdi+18h]
0x180024b16  sub     rax, rcx
0x180024b19  cmp     rsi, rax
0x180024b1c  ja      short loc_180024B4D
0x180024b1e  lea     rax, [rcx+rsi]
0x180024b22  mov     [rdi+10h], rax
0x180024b26  mov     rax, rdi
0x180024b29  cmp     qword ptr [rdi+18h], 0Fh
0x180024b2e  jbe     short loc_180024B33
0x180024b30  mov     rax, [rdi]
0x180024b33  lea     rbx, [rcx+rax]
0x180024b37  mov     r8, rsi; Size
0x180024b3a  lea     rdx, [rsp+78h+Buffer]; Src
0x180024b3f  mov     rcx, rbx; void *
0x180024b42  call    memmove_0
0x180024b47  mov     byte ptr [rbx+rsi], 0
0x180024b4b  jmp     short loc_180024B96
0x180024b4d  mov     [rsp+78h+Size], rsi; Size
0x180024b52  lea     r9, [rsp+78h+Buffer]
0x180024b57  mov     rdx, rsi
0x180024b5a  mov     rcx, rdi; Src
0x180024b5d  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180024b62  jmp     short loc_180024B96
0x180024b64  mov     rcx, [rdi+10h]
0x180024b68  cmp     rcx, [rdi+18h]
0x180024b6c  jnb     short loc_180024B8E
0x180024b6e  lea     rax, [rcx+1]
0x180024b72  mov     [rdi+10h], rax
0x180024b76  mov     rax, rdi
0x180024b79  cmp     qword ptr [rdi+18h], 0Fh
0x180024b7e  jbe     short loc_180024B83
0x180024b80  mov     rax, [rdi]
0x180024b83  mov     [rcx+rax], r9b
0x180024b87  mov     byte ptr [rcx+rax+1], 0
0x180024b8c  jmp     short loc_180024B96
0x180024b8e  mov     rcx, rdi; Src
0x180024b91  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180024b96  inc     r14
0x180024b99  cmp     r14, rbp
0x180024b9c  jnz     loc_180024ACF
0x180024ba2  mov     rax, rdi
0x180024ba5  mov     rcx, [rsp+78h+var_28]
0x180024baa  xor     rcx, rsp; StackCookie
0x180024bad  call    __security_check_cookie
0x180024bb2  lea     r11, [rsp+78h+var_18]
0x180024bb7  mov     rbx, [r11+30h]
0x180024bbb  mov     rbp, [r11+38h]
0x180024bbf  mov     rsp, r11
0x180024bc2  pop     r14
0x180024bc4  pop     rdi
0x180024bc5  pop     rsi
0x180024bc6  retn
```
