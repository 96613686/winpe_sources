# std::_Regex_traits<ushort>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>)

- ea: `0x180040220`
- end: `0x18004037e`
- name: `??$transform_primary@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@?$_Regex_traits@G@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003e950`

## callees

- `0x18002756c`
- `0x180029094`
- `0x180035178`
- `0x180035680`
- `0x180040220`
- `0x1800406ec`
- `0x18004a91c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004028d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800402a1`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004028d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800402a1`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180040279`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180040279`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall std::_Regex_traits<unsigned short>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r14
  __int64 v7; // rbp
  unsigned __int64 v8; // rbx
  __int64 v9; // r14
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rax
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF
  __int128 v14; // [rsp+50h] [rbp-38h]

  std::wstring::wstring(a2);
  if ( v4 != v5 )
  {
    v6 = *a1;
    v7 = __RTtypeid(v6) + 8;
    if ( !(unsigned int)__std_type_info_compare(v7, &qword_18009D968)
      || !(unsigned int)__std_type_info_compare(v7, &qword_18009D4F8) )
    {
      v13 = 0;
      v14 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v13);
      v8 = v14;
      if ( a2[2] < (unsigned __int64)v14 )
      {
        v9 = v6 + 16;
        while ( 1 )
        {
          std::wstring::resize(a2, v8);
          v10 = a2[3] <= 7u ? a2 : (_QWORD *)*a2;
          v11 = _std_regex_transform_primary_wchar_t(v10, v9);
          v8 = v11;
          if ( v11 == -1 )
            break;
          if ( a2[2] >= v11 )
            goto LABEL_13;
        }
        v8 = 0;
      }
LABEL_13:
      std::wstring::resize(a2, v8);
      std::wstring::_Tidy_deallocate(&v13);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180040220  mov     [rsp+arg_10], rbx
0x180040225  mov     [rsp+arg_18], rbp
0x18004022a  push    rsi
0x18004022b  push    rdi
0x18004022c  push    r14
0x18004022e  sub     rsp, 70h
0x180040232  mov     rax, cs:__security_cookie
0x180040239  xor     rax, rsp
0x18004023c  mov     [rsp+88h+var_28], rax
0x180040241  mov     rbx, r9
0x180040244  mov     rdi, r8
0x180040247  mov     rsi, rdx
0x18004024a  mov     r14, rcx
0x18004024d  mov     [rsp+88h+var_50], rdx
0x180040252  mov     [rsp+88h+var_58], 0
0x18004025a  mov     rcx, rdx
0x18004025d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040262  mov     [rsp+88h+var_58], 1
0x18004026a  cmp     r8, r9
0x18004026d  jz      loc_180040358
0x180040273  mov     r14, [r14]
0x180040276  mov     rcx, r14
0x180040279  call    cs:__imp___RTtypeid
0x18004027f  lea     rbp, [rax+8]
0x180040283  lea     rdx, qword_18009D968
0x18004028a  mov     rcx, rbp
0x18004028d  call    cs:__imp___std_type_info_compare
0x180040293  test    eax, eax
0x180040295  jz      short loc_1800402AF
0x180040297  lea     rdx, qword_18009D4F8
0x18004029e  mov     rcx, rbp
0x1800402a1  call    cs:__imp___std_type_info_compare
0x1800402a7  test    eax, eax
0x1800402a9  jnz     loc_180040358
0x1800402af  xorps   xmm0, xmm0
0x1800402b2  movups  [rsp+88h+var_48], xmm0
0x1800402b7  xorps   xmm1, xmm1
0x1800402ba  movdqu  [rsp+88h+var_38], xmm1
0x1800402c0  sub     rbx, rdi
0x1800402c3  sar     rbx, 1
0x1800402c6  mov     r8, rbx
0x1800402c9  mov     rdx, rdi
0x1800402cc  lea     rcx, [rsp+88h+var_48]
0x1800402d1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800402d6  nop
0x1800402d7  lea     rdi, [rsp+88h+var_48]
0x1800402dc  cmp     qword ptr [rsp+88h+var_38+8], 7
0x1800402e2  cmova   rdi, qword ptr [rsp+88h+var_48]
0x1800402e8  mov     rbx, qword ptr [rsp+88h+var_38]
0x1800402ed  cmp     [rsi+10h], rbx
0x1800402f1  jnb     short loc_180040342
0x1800402f3  lea     rbp, [rdi+rbx*2]
0x1800402f7  add     r14, 10h
0x1800402fb  mov     rdx, rbx
0x1800402fe  mov     rcx, rsi
0x180040301  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180040306  cmp     qword ptr [rsi+18h], 7
0x18004030b  jbe     short loc_180040315
0x18004030d  mov     rcx, [rsi]
0x180040310  mov     rax, rcx
0x180040313  jmp     short loc_18004031B
0x180040315  mov     rax, rsi
0x180040318  mov     rcx, rsi; void *
0x18004031b  lea     rdx, [rax+rbx*2]
0x18004031f  mov     [rsp+88h+var_68], r14; __int64
0x180040324  mov     r9, rbp
0x180040327  mov     r8, rdi
0x18004032a  call    __std_regex_transform_primary_wchar_t
0x18004032f  mov     rbx, rax
0x180040332  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040336  jz      short loc_180040340
0x180040338  cmp     [rsi+10h], rax
0x18004033c  jb      short loc_1800402FB
0x18004033e  jmp     short loc_180040342
0x180040340  xor     ebx, ebx
0x180040342  mov     rdx, rbx
0x180040345  mov     rcx, rsi
0x180040348  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004034d  nop
0x18004034e  lea     rcx, [rsp+88h+var_48]
0x180040353  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040358  mov     rax, rsi
0x18004035b  mov     rcx, [rsp+88h+var_28]
0x180040360  xor     rcx, rsp; StackCookie
0x180040363  call    __security_check_cookie
0x180040368  lea     r11, [rsp+88h+var_18]
0x18004036d  mov     rbx, [r11+30h]
0x180040371  mov     rbp, [r11+38h]
0x180040375  mov     rsp, r11
0x180040378  pop     r14
0x18004037a  pop     rdi
0x18004037b  pop     rsi
0x18004037c  retn
```
