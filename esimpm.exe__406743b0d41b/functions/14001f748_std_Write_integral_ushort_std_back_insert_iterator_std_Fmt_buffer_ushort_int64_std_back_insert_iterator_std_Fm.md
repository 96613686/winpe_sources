# `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x14001f748`
- end: `0x14001f906`
- name: `??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_JU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `446`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b904`
- `0x14001ca34`

## callees

- `0x14001b604`
- `0x14001d1e0`
- `0x14001d2f4`
- `0x14001e5e8`
- `0x14001f748`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f831`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f831`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,__int64>'::`2'::_lambda_1_::operator()(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  int v7; // ecx
  _DWORD *v8; // rax
  int v9; // ecx
  __int64 i; // rsi
  int v11; // r14d
  __int64 v12; // rsi
  struct std::locale::_Locimp *v13; // rsi
  struct std::_Facet_base *v14; // rax
  __int16 v15; // r8
  __int64 v16; // rax
  char *v17; // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rax
  _BYTE v20[8]; // [rsp+40h] [rbp-38h] BYREF
  struct std::locale::_Locimp *v21; // [rsp+48h] [rbp-30h]
  char *v22[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v23; // [rsp+80h] [rbp+8h] BYREF

  v5 = std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
         &v23,
         a3,
         *(_BYTE *)(*(_QWORD *)(a1 + 8) + 10LL),
         **(__int64 **)(a1 + 16) < 0);
  v6 = *std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
          &v23,
          **(char ***)(a1 + 24),
          (char *)(**(_QWORD **)(a1 + 24) + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL)),
          *v5);
  if ( **(_BYTE **)(a1 + 32) )
  {
    v7 = **(_DWORD **)(a1 + 8);
    v8 = *(_DWORD **)(a1 + 40);
    if ( *v8 < v7 )
    {
      v9 = v7 - *v8;
      for ( i = v9; i > 0; --i )
      {
        if ( (unsigned __int64)(*(_QWORD *)(v6 + 16) + 1LL) > *(_QWORD *)(v6 + 24) )
          (**(void (__fastcall ***)(__int64))v6)(v6);
        *(_WORD *)(*(_QWORD *)(v6 + 8) + 2LL * (*(_QWORD *)(v6 + 16))++) = 48;
      }
    }
  }
  v11 = **(_DWORD **)(a1 + 48);
  if ( v11 <= 0 )
  {
    std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      a2,
      **(char ***)(a1 + 56),
      *(char **)a1,
      v6);
  }
  else
  {
    v12 = **(_QWORD **)(a1 + 72);
    if ( v12 )
    {
      v13 = *(struct std::locale::_Locimp **)(v12 + 8);
      v21 = v13;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    else
    {
      v13 = std::locale::_Init(1);
      v21 = v13;
    }
    v14 = std::use_facet<std::numpunct<unsigned short>>((__int64)v20);
    v15 = (*(__int64 (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v14 + 32LL))(v14);
    v16 = *(_QWORD *)(a1 + 64);
    if ( *(_QWORD *)(v16 + 24) <= 0xFu )
      v17 = *(char **)(a1 + 64);
    else
      v17 = *(char **)v16;
    v22[0] = v17;
    v22[1] = *(char **)(v16 + 16);
    std::_Write_separated_integer<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      a2,
      **(char ***)(a1 + 56),
      *(_QWORD *)a1,
      v22,
      v15,
      v11,
      v6);
    if ( v13 )
    {
      v18 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v18 )
        (**v18)(v18, 1);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x14001f748  mov     r11, rsp
0x14001f74b  mov     [r11+10h], rbx
0x14001f74f  mov     [r11+18h], rbp
0x14001f753  push    rsi
0x14001f754  push    rdi
0x14001f755  push    r14
0x14001f757  sub     rsp, 60h
0x14001f75b  mov     rax, r8
0x14001f75e  mov     rbp, rdx
0x14001f761  mov     rdi, rcx
0x14001f764  mov     r8, [rcx+10h]
0x14001f768  mov     r9, [r8]
0x14001f76b  shr     r9, 3Fh
0x14001f76f  mov     r8, [rcx+8]
0x14001f773  mov     r8b, [r8+0Ah]
0x14001f777  mov     rdx, rax
0x14001f77a  lea     rcx, [r11+8]
0x14001f77e  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x14001f783  mov     rcx, [rdi+18h]
0x14001f787  mov     rdx, [rcx]
0x14001f78a  mov     r8, [rcx+8]
0x14001f78e  add     r8, rdx
0x14001f791  mov     r9, [rax]
0x14001f794  lea     rcx, [rsp+78h+arg_0]
0x14001f79c  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f7a1  mov     rbx, [rax]
0x14001f7a4  mov     rax, [rdi+20h]
0x14001f7a8  cmp     byte ptr [rax], 0
0x14001f7ab  jz      short loc_14001F7F9
0x14001f7ad  mov     rax, [rdi+8]
0x14001f7b1  mov     ecx, [rax]
0x14001f7b3  mov     rax, [rdi+28h]
0x14001f7b7  cmp     [rax], ecx
0x14001f7b9  jge     short loc_14001F7F9
0x14001f7bb  sub     ecx, [rax]
0x14001f7bd  movsxd  rsi, ecx
0x14001f7c0  test    ecx, ecx
0x14001f7c2  jle     short loc_14001F7F9
0x14001f7c4  mov     rdx, [rbx+10h]
0x14001f7c8  inc     rdx
0x14001f7cb  cmp     rdx, [rbx+18h]
0x14001f7cf  jbe     short loc_14001F7DF
0x14001f7d1  mov     rax, [rbx]
0x14001f7d4  mov     rcx, rbx
0x14001f7d7  mov     rax, [rax]
0x14001f7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f7df  mov     rcx, [rbx+10h]
0x14001f7e3  mov     rax, [rbx+8]
0x14001f7e7  mov     word ptr [rax+rcx*2], 30h ; '0'
0x14001f7ed  inc     qword ptr [rbx+10h]
0x14001f7f1  dec     rsi
0x14001f7f4  test    rsi, rsi
0x14001f7f7  jg      short loc_14001F7C4
0x14001f7f9  mov     rax, [rdi+30h]
0x14001f7fd  mov     r14d, [rax]
0x14001f800  test    r14d, r14d
0x14001f803  jle     loc_14001F8D9
0x14001f809  mov     rax, [rdi+48h]
0x14001f80d  mov     rsi, [rax]
0x14001f810  test    rsi, rsi
0x14001f813  jz      short loc_14001F82F
0x14001f815  mov     rsi, [rsi+8]
0x14001f819  mov     [rsp+78h+var_30], rsi
0x14001f81e  mov     rax, [rsi]
0x14001f821  mov     rcx, rsi
0x14001f824  mov     rax, [rax+8]
0x14001f828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f82d  jmp     short loc_14001F83F
0x14001f82f  mov     cl, 1
0x14001f831  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001f837  mov     rsi, rax
0x14001f83a  mov     [rsp+78h+var_30], rax
0x14001f83f  lea     rcx, [rsp+78h+var_38]
0x14001f844  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001f849  mov     rdx, rax
0x14001f84c  mov     rcx, [rax]
0x14001f84f  mov     rax, [rcx+20h]
0x14001f853  mov     rcx, rdx
0x14001f856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f85b  movzx   r8d, ax
0x14001f85f  mov     rax, [rdi+40h]
0x14001f863  cmp     qword ptr [rax+18h], 0Fh
0x14001f868  jbe     short loc_14001F86F
0x14001f86a  mov     rcx, [rax]
0x14001f86d  jmp     short loc_14001F872
0x14001f86f  mov     rcx, rax
0x14001f872  mov     [rsp+78h+var_28], rcx
0x14001f877  mov     rax, [rax+10h]
0x14001f87b  mov     [rsp+78h+var_20], rax
0x14001f880  mov     rdx, [rdi+38h]
0x14001f884  mov     [rsp+78h+var_48], rbx
0x14001f889  mov     [rsp+78h+var_50], r14d
0x14001f88e  mov     [rsp+78h+var_58], r8w
0x14001f894  lea     r9, [rsp+78h+var_28]
0x14001f899  mov     r8, [rdi]
0x14001f89c  mov     rdx, [rdx]
0x14001f89f  mov     rcx, rbp
0x14001f8a2  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f8a7  nop
0x14001f8a8  test    rsi, rsi
0x14001f8ab  jz      short loc_14001F8EE
0x14001f8ad  mov     rax, [rsi]
0x14001f8b0  mov     rcx, rsi
0x14001f8b3  mov     rax, [rax+10h]
0x14001f8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f8bc  mov     r8, rax
0x14001f8bf  test    rax, rax
0x14001f8c2  jz      short loc_14001F8EE
0x14001f8c4  mov     rcx, [rax]
0x14001f8c7  mov     rax, [rcx]
0x14001f8ca  mov     edx, 1
0x14001f8cf  mov     rcx, r8
0x14001f8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f8d7  jmp     short loc_14001F8EE
0x14001f8d9  mov     rdx, [rdi+38h]
0x14001f8dd  mov     r9, rbx
0x14001f8e0  mov     r8, [rdi]
0x14001f8e3  mov     rdx, [rdx]
0x14001f8e6  mov     rcx, rbp
0x14001f8e9  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f8ee  mov     rax, rbp
0x14001f8f1  lea     r11, [rsp+78h+var_18]
0x14001f8f6  mov     rbx, [r11+28h]
0x14001f8fa  mov     rbp, [r11+30h]
0x14001f8fe  mov     rsp, r11
0x14001f901  pop     r14
0x14001f903  pop     rdi
0x14001f904  pop     rsi
0x14001f905  retn
```
