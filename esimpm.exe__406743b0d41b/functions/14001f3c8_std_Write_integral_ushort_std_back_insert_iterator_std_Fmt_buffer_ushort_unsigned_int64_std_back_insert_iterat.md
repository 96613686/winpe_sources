# `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x14001f3c8`
- end: `0x14001f57e`
- name: `??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `438`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b74c`
- `0x14001bac8`
- `0x14001be84`
- `0x14001c664`
- `0x14001ce10`

## callees

- `0x14001b604`
- `0x14001d1e0`
- `0x14001d2f4`
- `0x14001e5e8`
- `0x14001f3c8`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f4a9`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f4a9`

## pseudocode

```c
__int64 *__fastcall `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
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
         0);
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
0x14001f3c8  mov     r11, rsp
0x14001f3cb  mov     [r11+10h], rbx
0x14001f3cf  mov     [r11+18h], rbp
0x14001f3d3  push    rsi
0x14001f3d4  push    rdi
0x14001f3d5  push    r14
0x14001f3d7  sub     rsp, 60h
0x14001f3db  mov     rax, r8
0x14001f3de  mov     rbp, rdx
0x14001f3e1  mov     rdi, rcx
0x14001f3e4  mov     r8, [rcx+8]
0x14001f3e8  xor     r9d, r9d
0x14001f3eb  mov     r8b, [r8+0Ah]
0x14001f3ef  mov     rdx, rax
0x14001f3f2  lea     rcx, [r11+8]
0x14001f3f6  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x14001f3fb  mov     r8, [rdi+18h]
0x14001f3ff  mov     rdx, [r8]
0x14001f402  mov     r8, [r8+8]
0x14001f406  add     r8, rdx
0x14001f409  mov     r9, [rax]
0x14001f40c  lea     rcx, [rsp+78h+arg_0]
0x14001f414  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f419  mov     rbx, [rax]
0x14001f41c  mov     rax, [rdi+20h]
0x14001f420  cmp     byte ptr [rax], 0
0x14001f423  jz      short loc_14001F471
0x14001f425  mov     rax, [rdi+8]
0x14001f429  mov     ecx, [rax]
0x14001f42b  mov     rax, [rdi+28h]
0x14001f42f  cmp     [rax], ecx
0x14001f431  jge     short loc_14001F471
0x14001f433  sub     ecx, [rax]
0x14001f435  movsxd  rsi, ecx
0x14001f438  test    ecx, ecx
0x14001f43a  jle     short loc_14001F471
0x14001f43c  mov     rdx, [rbx+10h]
0x14001f440  inc     rdx
0x14001f443  cmp     rdx, [rbx+18h]
0x14001f447  jbe     short loc_14001F457
0x14001f449  mov     rax, [rbx]
0x14001f44c  mov     rcx, rbx
0x14001f44f  mov     rax, [rax]
0x14001f452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f457  mov     rcx, [rbx+10h]
0x14001f45b  mov     rax, [rbx+8]
0x14001f45f  mov     word ptr [rax+rcx*2], 30h ; '0'
0x14001f465  inc     qword ptr [rbx+10h]
0x14001f469  dec     rsi
0x14001f46c  test    rsi, rsi
0x14001f46f  jg      short loc_14001F43C
0x14001f471  mov     rax, [rdi+30h]
0x14001f475  mov     r14d, [rax]
0x14001f478  test    r14d, r14d
0x14001f47b  jle     loc_14001F551
0x14001f481  mov     rax, [rdi+48h]
0x14001f485  mov     rsi, [rax]
0x14001f488  test    rsi, rsi
0x14001f48b  jz      short loc_14001F4A7
0x14001f48d  mov     rsi, [rsi+8]
0x14001f491  mov     [rsp+78h+var_30], rsi
0x14001f496  mov     rax, [rsi]
0x14001f499  mov     rcx, rsi
0x14001f49c  mov     rax, [rax+8]
0x14001f4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f4a5  jmp     short loc_14001F4B7
0x14001f4a7  mov     cl, 1
0x14001f4a9  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001f4af  mov     rsi, rax
0x14001f4b2  mov     [rsp+78h+var_30], rax
0x14001f4b7  lea     rcx, [rsp+78h+var_38]
0x14001f4bc  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001f4c1  mov     rdx, rax
0x14001f4c4  mov     rcx, [rax]
0x14001f4c7  mov     rax, [rcx+20h]
0x14001f4cb  mov     rcx, rdx
0x14001f4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f4d3  movzx   r8d, ax
0x14001f4d7  mov     rax, [rdi+40h]
0x14001f4db  cmp     qword ptr [rax+18h], 0Fh
0x14001f4e0  jbe     short loc_14001F4E7
0x14001f4e2  mov     rcx, [rax]
0x14001f4e5  jmp     short loc_14001F4EA
0x14001f4e7  mov     rcx, rax
0x14001f4ea  mov     [rsp+78h+var_28], rcx
0x14001f4ef  mov     rax, [rax+10h]
0x14001f4f3  mov     [rsp+78h+var_20], rax
0x14001f4f8  mov     rdx, [rdi+38h]
0x14001f4fc  mov     [rsp+78h+var_48], rbx
0x14001f501  mov     [rsp+78h+var_50], r14d
0x14001f506  mov     [rsp+78h+var_58], r8w
0x14001f50c  lea     r9, [rsp+78h+var_28]
0x14001f511  mov     r8, [rdi]
0x14001f514  mov     rdx, [rdx]
0x14001f517  mov     rcx, rbp
0x14001f51a  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f51f  nop
0x14001f520  test    rsi, rsi
0x14001f523  jz      short loc_14001F566
0x14001f525  mov     rax, [rsi]
0x14001f528  mov     rcx, rsi
0x14001f52b  mov     rax, [rax+10h]
0x14001f52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f534  mov     r8, rax
0x14001f537  test    rax, rax
0x14001f53a  jz      short loc_14001F566
0x14001f53c  mov     rcx, [rax]
0x14001f53f  mov     rax, [rcx]
0x14001f542  mov     edx, 1
0x14001f547  mov     rcx, r8
0x14001f54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f54f  jmp     short loc_14001F566
0x14001f551  mov     rdx, [rdi+38h]
0x14001f555  mov     r9, rbx
0x14001f558  mov     r8, [rdi]
0x14001f55b  mov     rdx, [rdx]
0x14001f55e  mov     rcx, rbp
0x14001f561  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f566  mov     rax, rbp
0x14001f569  lea     r11, [rsp+78h+var_18]
0x14001f56e  mov     rbx, [r11+28h]
0x14001f572  mov     rbp, [r11+30h]
0x14001f576  mov     rsp, r11
0x14001f579  pop     r14
0x14001f57b  pop     rdi
0x14001f57c  pop     rsi
0x14001f57d  retn
```
