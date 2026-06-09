# `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x14001f584`
- end: `0x14001f742`
- name: `??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@HU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `446`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b828`
- `0x14001c28c`

## callees

- `0x14001b604`
- `0x14001d1e0`
- `0x14001d2f4`
- `0x14001e5e8`
- `0x14001f584`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f66d`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f66d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,int>'::`2'::_lambda_1_::operator()(
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
         **(int **)(a1 + 16) < 0);
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
0x14001f584  mov     r11, rsp
0x14001f587  mov     [r11+10h], rbx
0x14001f58b  mov     [r11+18h], rbp
0x14001f58f  push    rsi
0x14001f590  push    rdi
0x14001f591  push    r14
0x14001f593  sub     rsp, 60h
0x14001f597  mov     rax, r8
0x14001f59a  mov     rbp, rdx
0x14001f59d  mov     rdi, rcx
0x14001f5a0  mov     r8, [rcx+10h]
0x14001f5a4  mov     r9d, [r8]
0x14001f5a7  shr     r9d, 1Fh
0x14001f5ab  mov     r8, [rcx+8]
0x14001f5af  mov     r8b, [r8+0Ah]
0x14001f5b3  mov     rdx, rax
0x14001f5b6  lea     rcx, [r11+8]
0x14001f5ba  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x14001f5bf  mov     rcx, [rdi+18h]
0x14001f5c3  mov     rdx, [rcx]
0x14001f5c6  mov     r8, [rcx+8]
0x14001f5ca  add     r8, rdx
0x14001f5cd  mov     r9, [rax]
0x14001f5d0  lea     rcx, [rsp+78h+arg_0]
0x14001f5d8  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f5dd  mov     rbx, [rax]
0x14001f5e0  mov     rax, [rdi+20h]
0x14001f5e4  cmp     byte ptr [rax], 0
0x14001f5e7  jz      short loc_14001F635
0x14001f5e9  mov     rax, [rdi+8]
0x14001f5ed  mov     ecx, [rax]
0x14001f5ef  mov     rax, [rdi+28h]
0x14001f5f3  cmp     [rax], ecx
0x14001f5f5  jge     short loc_14001F635
0x14001f5f7  sub     ecx, [rax]
0x14001f5f9  movsxd  rsi, ecx
0x14001f5fc  test    ecx, ecx
0x14001f5fe  jle     short loc_14001F635
0x14001f600  mov     rdx, [rbx+10h]
0x14001f604  inc     rdx
0x14001f607  cmp     rdx, [rbx+18h]
0x14001f60b  jbe     short loc_14001F61B
0x14001f60d  mov     rax, [rbx]
0x14001f610  mov     rcx, rbx
0x14001f613  mov     rax, [rax]
0x14001f616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f61b  mov     rcx, [rbx+10h]
0x14001f61f  mov     rax, [rbx+8]
0x14001f623  mov     word ptr [rax+rcx*2], 30h ; '0'
0x14001f629  inc     qword ptr [rbx+10h]
0x14001f62d  dec     rsi
0x14001f630  test    rsi, rsi
0x14001f633  jg      short loc_14001F600
0x14001f635  mov     rax, [rdi+30h]
0x14001f639  mov     r14d, [rax]
0x14001f63c  test    r14d, r14d
0x14001f63f  jle     loc_14001F715
0x14001f645  mov     rax, [rdi+48h]
0x14001f649  mov     rsi, [rax]
0x14001f64c  test    rsi, rsi
0x14001f64f  jz      short loc_14001F66B
0x14001f651  mov     rsi, [rsi+8]
0x14001f655  mov     [rsp+78h+var_30], rsi
0x14001f65a  mov     rax, [rsi]
0x14001f65d  mov     rcx, rsi
0x14001f660  mov     rax, [rax+8]
0x14001f664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f669  jmp     short loc_14001F67B
0x14001f66b  mov     cl, 1
0x14001f66d  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001f673  mov     rsi, rax
0x14001f676  mov     [rsp+78h+var_30], rax
0x14001f67b  lea     rcx, [rsp+78h+var_38]
0x14001f680  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001f685  mov     rdx, rax
0x14001f688  mov     rcx, [rax]
0x14001f68b  mov     rax, [rcx+20h]
0x14001f68f  mov     rcx, rdx
0x14001f692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f697  movzx   r8d, ax
0x14001f69b  mov     rax, [rdi+40h]
0x14001f69f  cmp     qword ptr [rax+18h], 0Fh
0x14001f6a4  jbe     short loc_14001F6AB
0x14001f6a6  mov     rcx, [rax]
0x14001f6a9  jmp     short loc_14001F6AE
0x14001f6ab  mov     rcx, rax
0x14001f6ae  mov     [rsp+78h+var_28], rcx
0x14001f6b3  mov     rax, [rax+10h]
0x14001f6b7  mov     [rsp+78h+var_20], rax
0x14001f6bc  mov     rdx, [rdi+38h]
0x14001f6c0  mov     [rsp+78h+var_48], rbx
0x14001f6c5  mov     [rsp+78h+var_50], r14d
0x14001f6ca  mov     [rsp+78h+var_58], r8w
0x14001f6d0  lea     r9, [rsp+78h+var_28]
0x14001f6d5  mov     r8, [rdi]
0x14001f6d8  mov     rdx, [rdx]
0x14001f6db  mov     rcx, rbp
0x14001f6de  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f6e3  nop
0x14001f6e4  test    rsi, rsi
0x14001f6e7  jz      short loc_14001F72A
0x14001f6e9  mov     rax, [rsi]
0x14001f6ec  mov     rcx, rsi
0x14001f6ef  mov     rax, [rax+10h]
0x14001f6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6f8  mov     r8, rax
0x14001f6fb  test    rax, rax
0x14001f6fe  jz      short loc_14001F72A
0x14001f700  mov     rcx, [rax]
0x14001f703  mov     rax, [rcx]
0x14001f706  mov     edx, 1
0x14001f70b  mov     rcx, r8
0x14001f70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f713  jmp     short loc_14001F72A
0x14001f715  mov     rdx, [rdi+38h]
0x14001f719  mov     r9, rbx
0x14001f71c  mov     r8, [rdi]
0x14001f71f  mov     rdx, [rdx]
0x14001f722  mov     rcx, rbp
0x14001f725  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f72a  mov     rax, rbp
0x14001f72d  lea     r11, [rsp+78h+var_18]
0x14001f732  mov     rbx, [r11+28h]
0x14001f736  mov     rbp, [r11+30h]
0x14001f73a  mov     rsp, r11
0x14001f73d  pop     r14
0x14001f73f  pop     rdi
0x14001f740  pop     rsi
0x14001f741  retn
```
