# std::regex_replace<std::regex_traits<ushort>,ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::regex_constants::match_flag_type)

- ea: `0x18002d8f8`
- end: `0x18002d9c4`
- name: `??$regex_replace@V?$regex_traits@G@std@@GU?$char_traits@G@2@V?$allocator@G@2@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV?$basic_regex@GV?$regex_traits@G@std@@@0@AEBV10@W4match_flag_type@regex_constants@0@@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002e434`

## callees

- `0x1800021d0`
- `0x180013cd0`
- `0x180017418`
- `0x18002d5ac`
- `0x18002d8f8`

## pseudocode

```c
__int64 __fastcall std::regex_replace<std::regex_traits<unsigned short>,unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        _QWORD *a4)
{
  __int64 v7; // r8
  __int16 *v8; // rcx
  __int16 *v9; // r8
  int v11; // [rsp+30h] [rbp-21h]
  __int64 v12; // [rsp+50h] [rbp-1h] BYREF
  __int128 v13; // [rsp+58h] [rbp+7h] BYREF
  __int128 v14; // [rsp+68h] [rbp+17h]

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v13 = 0;
  v14 = 0;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  std::wstring::_Construct<1,unsigned short const *>(&v13);
  v8 = (__int16 *)&v13;
  if ( *((_QWORD *)&v14 + 1) > 7u )
    v8 = (__int16 *)v13;
  v9 = (__int16 *)&v13;
  if ( *((_QWORD *)&v14 + 1) > 7u )
    v9 = (__int16 *)v13;
  std::_Regex_replace1<std::back_insert_iterator<std::wstring>,unsigned short const *,std::regex_traits<unsigned short>,unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
    &v12,
    a1,
    v9,
    &v8[v14],
    a3,
    a4,
    v11);
  std::wstring::~wstring(&v13);
  return a1;
}

```

## disassembly

```asm
0x18002d8f8  push    rbp
0x18002d8fa  push    rbx
0x18002d8fb  push    rsi
0x18002d8fc  push    rdi
0x18002d8fd  lea     rbp, [rsp-37h]
0x18002d902  sub     rsp, 88h
0x18002d909  mov     rax, cs:__security_cookie
0x18002d910  xor     rax, rsp
0x18002d913  mov     [rbp+4Fh+var_28], rax
0x18002d917  mov     rsi, r9
0x18002d91a  mov     rdi, r8
0x18002d91d  mov     rbx, rcx
0x18002d920  mov     [rbp+4Fh+var_58], rcx
0x18002d924  xor     ecx, ecx
0x18002d926  mov     [rbp+4Fh+var_60], ecx
0x18002d929  xorps   xmm0, xmm0
0x18002d92c  movups  xmmword ptr [rbx], xmm0
0x18002d92f  mov     [rbx+10h], rcx
0x18002d933  mov     qword ptr [rbx+18h], 7
0x18002d93b  mov     [rbx], cx
0x18002d93e  mov     [rbp+4Fh+var_60], 1
0x18002d945  movups  [rbp+4Fh+var_48], xmm0
0x18002d949  xorps   xmm1, xmm1
0x18002d94c  movdqu  [rbp+4Fh+var_38], xmm1
0x18002d951  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002d955  inc     r8
0x18002d958  cmp     [rdx+r8*2], cx
0x18002d95d  jnz     short loc_18002D955
0x18002d95f  lea     rcx, [rbp+4Fh+var_48]
0x18002d963  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d968  nop
0x18002d969  lea     rcx, [rbp+4Fh+var_48]
0x18002d96d  cmp     qword ptr [rbp+4Fh+var_38+8], 7
0x18002d972  cmova   rcx, qword ptr [rbp+4Fh+var_48]
0x18002d977  mov     rax, qword ptr [rbp+4Fh+var_38]
0x18002d97b  lea     r9, [rcx+rax*2]
0x18002d97f  lea     r8, [rbp+4Fh+var_48]
0x18002d983  cmova   r8, qword ptr [rbp+4Fh+var_48]
0x18002d988  mov     [rsp+0A0h+var_78], rsi
0x18002d98d  mov     [rsp+0A0h+var_80], rdi
0x18002d992  mov     rdx, rbx
0x18002d995  lea     rcx, [rbp+4Fh+var_50]
0x18002d999  call    ??$_Regex_replace1@V?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEBGV?$regex_traits@G@2@GU?$char_traits@G@2@V?$allocator@G@2@@std@@YA?AV?$back_insert_iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@V10@PEBG1AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@W4match_flag_type@regex_constants@0@@Z; std::_Regex_replace1<std::back_insert_iterator<std::wstring>,ushort const *,std::regex_traits<ushort>,ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::back_insert_iterator<std::wstring>,ushort const *,ushort const *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::wstring const &,std::regex_constants::match_flag_type)
0x18002d99e  nop
0x18002d99f  lea     rcx, [rbp+4Fh+var_48]
0x18002d9a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d9a8  mov     rax, rbx
0x18002d9ab  mov     rcx, [rbp+4Fh+var_28]
0x18002d9af  xor     rcx, rsp; StackCookie
0x18002d9b2  call    __security_check_cookie
0x18002d9b7  add     rsp, 88h
0x18002d9be  pop     rdi
0x18002d9bf  pop     rsi
0x18002d9c0  pop     rbx
0x18002d9c1  pop     rbp
0x18002d9c2  retn
```
