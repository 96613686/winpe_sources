# web::json::details::_String::format(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x14000bf50`
- end: `0x14000c083`
- name: `?format@_String@details@json@web@@MEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x140002f60`
- `0x140003244`
- `0x140004350`
- `0x14000af70`
- `0x14000bf50`
- `0x14000c820`
- `0x140037140`

## pseudocode

```c
__int64 __fastcall web::json::details::_String::format(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rax
  void *v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 result; // rax
  void *Block[3]; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-20h]

  v2 = a2;
  v4 = a2[2];
  v5 = v2[3];
  if ( v4 >= v5 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  }
  else
  {
    v2[2] = v4 + 1;
    v6 = v2;
    if ( v5 > 0xF )
      v6 = (_QWORD *)*v2;
    *(_WORD *)((char *)v6 + v4) = 34;
  }
  v7 = a1 + 8;
  if ( *(_BYTE *)(a1 + 40) )
  {
    v8 = (_QWORD *)utility::conversions::to_utf8string(Block, v7);
    web::json::details::append_escape_string<char>((char *)v2, v8);
  }
  else
  {
    utility::conversions::to_utf8string(Block, v7);
    std::string::_Append<char>(v2);
  }
  if ( v14 > 0xF )
  {
    if ( v14 + 1 < 0x1000 )
    {
      v9 = Block[0];
    }
    else
    {
      v9 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v9);
  }
  v10 = v2[2];
  v11 = v2[3];
  if ( v10 >= v11 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  result = v10 + 1;
  v2[2] = v10 + 1;
  if ( v11 > 0xF )
    v2 = (_QWORD *)*v2;
  *(_WORD *)((char *)v2 + v10) = 34;
  return result;
}

```

## disassembly

```asm
0x14000bf50  mov     [rsp+arg_10], rbx
0x14000bf55  push    rdi
0x14000bf56  sub     rsp, 50h
0x14000bf5a  mov     rax, cs:__security_cookie
0x14000bf61  xor     rax, rsp
0x14000bf64  mov     [rsp+58h+var_18], rax
0x14000bf69  mov     rbx, rdx
0x14000bf6c  mov     rdi, rcx
0x14000bf6f  mov     rdx, [rdx+10h]
0x14000bf73  mov     rcx, [rbx+18h]
0x14000bf77  cmp     rdx, rcx
0x14000bf7a  jnb     short loc_14000BF98
0x14000bf7c  lea     rax, [rdx+1]
0x14000bf80  mov     [rbx+10h], rax
0x14000bf84  mov     rax, rbx
0x14000bf87  cmp     rcx, 0Fh
0x14000bf8b  jbe     short loc_14000BF90
0x14000bf8d  mov     rax, [rbx]
0x14000bf90  mov     word ptr [rdx+rax], 22h ; '"'
0x14000bf96  jmp     short loc_14000BFAB
0x14000bf98  mov     r9b, 22h ; '"'
0x14000bf9b  xor     r8d, r8d
0x14000bf9e  mov     edx, 1
0x14000bfa3  mov     rcx, rbx; Src
0x14000bfa6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000bfab  lea     rdx, [rdi+8]
0x14000bfaf  lea     rcx, [rsp+58h+Block]
0x14000bfb4  cmp     byte ptr [rdi+28h], 0
0x14000bfb8  jz      short loc_14000BFCE
0x14000bfba  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x14000bfbf  nop
0x14000bfc0  mov     rdx, rax
0x14000bfc3  mov     rcx, rbx; Src
0x14000bfc6  call    ??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; web::json::details::append_escape_string<char>(std::string &,std::string const &)
0x14000bfcb  nop
0x14000bfcc  jmp     short loc_14000BFF0
0x14000bfce  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x14000bfd3  nop
0x14000bfd4  cmp     qword ptr [rax+18h], 0Fh
0x14000bfd9  jbe     short loc_14000BFE0
0x14000bfdb  mov     rdx, [rax]
0x14000bfde  jmp     short loc_14000BFE3
0x14000bfe0  mov     rdx, rax
0x14000bfe3  mov     r8, [rax+10h]
0x14000bfe7  mov     rcx, rbx; Src
0x14000bfea  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x14000bfef  nop
0x14000bff0  mov     rdx, [rsp+58h+var_20]
0x14000bff5  cmp     rdx, 0Fh
0x14000bff9  jbe     short loc_14000C032
0x14000bffb  mov     rax, [rsp+58h+Block]
0x14000c000  inc     rdx
0x14000c003  cmp     rdx, 1000h
0x14000c00a  jb      short loc_14000C02A
0x14000c00c  mov     rcx, [rax-8]
0x14000c010  sub     rax, rcx
0x14000c013  sub     rax, 8
0x14000c017  cmp     rax, 1Fh
0x14000c01b  ja      short loc_14000C023
0x14000c01d  add     rdx, 27h ; '''
0x14000c021  jmp     short loc_14000C02D
0x14000c023  mov     ecx, 5
0x14000c028  int     29h; Win8: RtlFailFast(ecx)
0x14000c02a  mov     rcx, rax; Block
0x14000c02d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c032  mov     rcx, [rbx+10h]
0x14000c036  mov     rdx, [rbx+18h]
0x14000c03a  cmp     rcx, rdx
0x14000c03d  jnb     short loc_14000C058
0x14000c03f  lea     rax, [rcx+1]
0x14000c043  mov     [rbx+10h], rax
0x14000c047  cmp     rdx, 0Fh
0x14000c04b  jbe     short loc_14000C050
0x14000c04d  mov     rbx, [rbx]
0x14000c050  mov     word ptr [rcx+rbx], 22h ; '"'
0x14000c056  jmp     short loc_14000C06B
0x14000c058  mov     r9b, 22h ; '"'
0x14000c05b  xor     r8d, r8d
0x14000c05e  mov     edx, 1
0x14000c063  mov     rcx, rbx; Src
0x14000c066  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000c06b  mov     rcx, [rsp+58h+var_18]
0x14000c070  xor     rcx, rsp; StackCookie
0x14000c073  call    __security_check_cookie
0x14000c078  mov     rbx, [rsp+58h+arg_10]
0x14000c07d  add     rsp, 50h
0x14000c081  pop     rdi
0x14000c082  retn
```
