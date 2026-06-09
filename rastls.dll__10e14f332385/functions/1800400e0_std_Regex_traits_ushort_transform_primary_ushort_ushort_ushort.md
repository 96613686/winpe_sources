# std::_Regex_traits<ushort>::transform_primary<ushort *>(ushort *,ushort *)

- ea: `0x1800400e0`
- end: `0x180040217`
- name: `??$transform_primary@PEAG@?$_Regex_traits@G@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEAG0@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180046564`

## callees

- `0x18002756c`
- `0x180035178`
- `0x180035680`
- `0x18003d29c`
- `0x1800400e0`
- `0x1800406ec`
- `0x18004a91c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180040147`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004015b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180040147`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004015b`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180040133`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180040133`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall std::_Regex_traits<unsigned short>::transform_primary<unsigned short *>(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbp
  __int64 v11; // rdi
  unsigned __int64 v12; // rdi
  __int64 v13; // rbp
  _QWORD *v14; // rcx
  unsigned __int64 v15; // rax
  _QWORD v17[2]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v18; // [rsp+50h] [rbp-48h]

  std::wstring::wstring(a2);
  if ( v8 != v9 )
  {
    v10 = *a1;
    v11 = __RTtypeid(v10) + 8;
    if ( !(unsigned int)__std_type_info_compare(v11, &qword_18009D968)
      || !(unsigned int)__std_type_info_compare(v11, &qword_18009D4F8) )
    {
      std::wstring::wstring(v17, a3, a4);
      v12 = v18;
      if ( a2[2] < v18 )
      {
        v13 = v10 + 16;
        while ( 1 )
        {
          std::wstring::resize(a2, v12);
          v14 = a2[3] <= 7u ? a2 : (_QWORD *)*a2;
          v15 = _std_regex_transform_primary_wchar_t(v14, v13);
          v12 = v15;
          if ( v15 == -1 )
            break;
          if ( a2[2] >= v15 )
            goto LABEL_13;
        }
        v12 = 0;
      }
LABEL_13:
      std::wstring::resize(a2, v12);
      std::wstring::_Tidy_deallocate(v17);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800400e0  push    rbx
0x1800400e2  push    rbp
0x1800400e3  push    rsi
0x1800400e4  push    rdi
0x1800400e5  push    r14
0x1800400e7  sub     rsp, 70h
0x1800400eb  mov     rax, cs:__security_cookie
0x1800400f2  xor     rax, rsp
0x1800400f5  mov     [rsp+98h+var_38], rax
0x1800400fa  mov     r14, r9
0x1800400fd  mov     rsi, r8
0x180040100  mov     rbx, rdx
0x180040103  mov     rbp, rcx
0x180040106  mov     [rsp+98h+var_60], rdx
0x18004010b  mov     [rsp+98h+var_68], 0
0x180040113  mov     rcx, rdx
0x180040116  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004011b  mov     [rsp+98h+var_68], 1
0x180040123  cmp     r8, r9
0x180040126  jz      loc_1800401FB
0x18004012c  mov     rbp, [rbp+0]
0x180040130  mov     rcx, rbp
0x180040133  call    cs:__imp___RTtypeid
0x180040139  lea     rdi, [rax+8]
0x18004013d  lea     rdx, qword_18009D968
0x180040144  mov     rcx, rdi
0x180040147  call    cs:__imp___std_type_info_compare
0x18004014d  test    eax, eax
0x18004014f  jz      short loc_180040169
0x180040151  lea     rdx, qword_18009D4F8
0x180040158  mov     rcx, rdi
0x18004015b  call    cs:__imp___std_type_info_compare
0x180040161  test    eax, eax
0x180040163  jnz     loc_1800401FB
0x180040169  mov     r8, r14
0x18004016c  mov     rdx, rsi
0x18004016f  lea     rcx, [rsp+98h+var_58]
0x180040174  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180040179  nop
0x18004017a  lea     rsi, [rsp+98h+var_58]
0x18004017f  cmp     [rsp+98h+var_40], 7
0x180040185  cmova   rsi, [rsp+98h+var_58]
0x18004018b  mov     rdi, [rsp+98h+var_48]
0x180040190  cmp     [rbx+10h], rdi
0x180040194  jnb     short loc_1800401E5
0x180040196  lea     r14, [rsi+rdi*2]
0x18004019a  add     rbp, 10h
0x18004019e  mov     rdx, rdi
0x1800401a1  mov     rcx, rbx
0x1800401a4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800401a9  cmp     qword ptr [rbx+18h], 7
0x1800401ae  jbe     short loc_1800401B8
0x1800401b0  mov     rcx, [rbx]
0x1800401b3  mov     rax, rcx
0x1800401b6  jmp     short loc_1800401BE
0x1800401b8  mov     rax, rbx
0x1800401bb  mov     rcx, rbx; void *
0x1800401be  lea     rdx, [rax+rdi*2]
0x1800401c2  mov     [rsp+98h+var_78], rbp; __int64
0x1800401c7  mov     r9, r14
0x1800401ca  mov     r8, rsi
0x1800401cd  call    __std_regex_transform_primary_wchar_t
0x1800401d2  mov     rdi, rax
0x1800401d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800401d9  jz      short loc_1800401E3
0x1800401db  cmp     [rbx+10h], rax
0x1800401df  jb      short loc_18004019E
0x1800401e1  jmp     short loc_1800401E5
0x1800401e3  xor     edi, edi
0x1800401e5  mov     rdx, rdi
0x1800401e8  mov     rcx, rbx
0x1800401eb  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800401f0  nop
0x1800401f1  lea     rcx, [rsp+98h+var_58]
0x1800401f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800401fb  mov     rax, rbx
0x1800401fe  mov     rcx, [rsp+98h+var_38]
0x180040203  xor     rcx, rsp; StackCookie
0x180040206  call    __security_check_cookie
0x18004020b  add     rsp, 70h
0x18004020f  pop     r14
0x180040211  pop     rdi
0x180040212  pop     rsi
0x180040213  pop     rbp
0x180040214  pop     rbx
0x180040215  retn
```
