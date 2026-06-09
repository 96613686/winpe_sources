# web::json::details::format_string(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x14000c280`
- end: `0x14000c388`
- name: `?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `264`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x140005d80`

## callees

- `0x140002f60`
- `0x140003244`
- `0x14000af70`
- `0x14000c280`
- `0x14000c820`
- `0x140037140`

## pseudocode

```c
__int64 __fastcall web::json::details::format_string(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _BYTE *v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 result; // rax
  void *Block; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-20h]

  v2 = a2;
  v4 = a2[2];
  v5 = a2[3];
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
  v7 = (_QWORD *)utility::conversions::to_utf8string(&Block, a1);
  web::json::details::append_escape_string<char>((char *)v2, v7);
  if ( v13 > 0xF )
  {
    if ( v13 + 1 < 0x1000 )
    {
      v8 = Block;
    }
    else
    {
      v8 = (_BYTE *)*((_QWORD *)Block - 1);
      if ( (unsigned __int64)((_BYTE *)Block - v8 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v8);
  }
  v9 = v2[2];
  v10 = v2[3];
  if ( v9 >= v10 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  result = v9 + 1;
  v2[2] = v9 + 1;
  if ( v10 > 0xF )
    v2 = (_QWORD *)*v2;
  *(_WORD *)((char *)v2 + v9) = 34;
  return result;
}

```

## disassembly

```asm
0x14000c280  mov     [rsp+arg_10], rbx
0x14000c285  push    rdi
0x14000c286  sub     rsp, 50h
0x14000c28a  mov     rax, cs:__security_cookie
0x14000c291  xor     rax, rsp
0x14000c294  mov     [rsp+58h+var_18], rax
0x14000c299  mov     rbx, rdx
0x14000c29c  mov     rdi, rcx
0x14000c29f  mov     rcx, [rdx+10h]
0x14000c2a3  mov     rdx, [rdx+18h]
0x14000c2a7  cmp     rcx, rdx
0x14000c2aa  jnb     short loc_14000C2C8
0x14000c2ac  lea     rax, [rcx+1]
0x14000c2b0  mov     [rbx+10h], rax
0x14000c2b4  mov     rax, rbx
0x14000c2b7  cmp     rdx, 0Fh
0x14000c2bb  jbe     short loc_14000C2C0
0x14000c2bd  mov     rax, [rbx]
0x14000c2c0  mov     word ptr [rcx+rax], 22h ; '"'
0x14000c2c6  jmp     short loc_14000C2DB
0x14000c2c8  mov     r9b, 22h ; '"'
0x14000c2cb  xor     r8d, r8d
0x14000c2ce  mov     edx, 1
0x14000c2d3  mov     rcx, rbx; Src
0x14000c2d6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000c2db  mov     rdx, rdi
0x14000c2de  lea     rcx, [rsp+58h+Block]
0x14000c2e3  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x14000c2e8  nop
0x14000c2e9  mov     rdx, rax
0x14000c2ec  mov     rcx, rbx; Src
0x14000c2ef  call    ??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; web::json::details::append_escape_string<char>(std::string &,std::string const &)
0x14000c2f4  nop
0x14000c2f5  mov     rdx, [rsp+58h+var_20]
0x14000c2fa  cmp     rdx, 0Fh
0x14000c2fe  jbe     short loc_14000C337
0x14000c300  mov     rax, [rsp+58h+Block]
0x14000c305  inc     rdx
0x14000c308  cmp     rdx, 1000h
0x14000c30f  jb      short loc_14000C32F
0x14000c311  mov     rcx, [rax-8]
0x14000c315  sub     rax, rcx
0x14000c318  sub     rax, 8
0x14000c31c  cmp     rax, 1Fh
0x14000c320  ja      short loc_14000C328
0x14000c322  add     rdx, 27h ; '''
0x14000c326  jmp     short loc_14000C332
0x14000c328  mov     ecx, 5
0x14000c32d  int     29h; Win8: RtlFailFast(ecx)
0x14000c32f  mov     rcx, rax; Block
0x14000c332  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c337  mov     rcx, [rbx+10h]
0x14000c33b  mov     rdx, [rbx+18h]
0x14000c33f  cmp     rcx, rdx
0x14000c342  jnb     short loc_14000C35D
0x14000c344  lea     rax, [rcx+1]
0x14000c348  mov     [rbx+10h], rax
0x14000c34c  cmp     rdx, 0Fh
0x14000c350  jbe     short loc_14000C355
0x14000c352  mov     rbx, [rbx]
0x14000c355  mov     word ptr [rcx+rbx], 22h ; '"'
0x14000c35b  jmp     short loc_14000C370
0x14000c35d  mov     r9b, 22h ; '"'
0x14000c360  xor     r8d, r8d
0x14000c363  mov     edx, 1
0x14000c368  mov     rcx, rbx; Src
0x14000c36b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x14000c370  mov     rcx, [rsp+58h+var_18]
0x14000c375  xor     rcx, rsp; StackCookie
0x14000c378  call    __security_check_cookie
0x14000c37d  mov     rbx, [rsp+58h+arg_10]
0x14000c382  add     rsp, 50h
0x14000c386  pop     rdi
0x14000c387  retn
```
