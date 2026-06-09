# `std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x14001f0fc`
- end: `0x14001f3bf`
- name: `??R_lambda_1_@?1???$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@OAEBU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `707`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140017ec8`
- `0x14001856c`
- `0x140018c1c`

## callees

- `0x14001b604`
- `0x14001d1e0`
- `0x14001d2f4`
- `0x14001e5e8`
- `0x14001f0fc`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f1c0`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001f1c0`

## pseudocode

```c
_QWORD *__fastcall `std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v5; // rbx
  int v6; // ecx
  _DWORD *v7; // rax
  int v8; // ecx
  __int64 i; // rsi
  __int64 v10; // rsi
  struct std::locale::_Locimp *v11; // rsi
  __int64 v12; // rdx
  void (__fastcall ***v13)(_QWORD, __int64); // r8
  struct std::_Facet_base *v14; // r14
  void (__fastcall ***v15)(_QWORD, __int64); // rax
  int v16; // esi
  __int16 v17; // r9
  __int64 v18; // rax
  char *v19; // rcx
  __int16 v20; // si
  __int64 v21; // rbx
  char *v23; // [rsp+40h] [rbp-48h] BYREF
  struct std::locale::_Locimp *v24; // [rsp+48h] [rbp-40h]
  __int64 v25; // [rsp+90h] [rbp+8h] BYREF

  v5 = *std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
          &v25,
          a3,
          **(_BYTE **)a1,
          **(_BYTE **)(a1 + 8));
  if ( **(_BYTE **)(a1 + 16) )
  {
    v6 = **(_DWORD **)(a1 + 32);
    v7 = *(_DWORD **)(a1 + 24);
    if ( *v7 < v6 )
    {
      v8 = v6 - *v7;
      for ( i = v8; i > 0; --i )
      {
        if ( (unsigned __int64)(*(_QWORD *)(v5 + 16) + 1LL) > *(_QWORD *)(v5 + 24) )
          (**(void (__fastcall ***)(__int64))v5)(v5);
        *(_WORD *)(*(_QWORD *)(v5 + 8) + 2LL * (*(_QWORD *)(v5 + 16))++) = 48;
      }
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 12LL) )
  {
    v10 = **(_QWORD **)(a1 + 40);
    if ( v10 )
    {
      v11 = *(struct std::locale::_Locimp **)(v10 + 8);
      v24 = v11;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v11 + 8LL))(v11);
    }
    else
    {
      v11 = std::locale::_Init(1);
      v24 = v11;
    }
    v14 = std::use_facet<std::numpunct<unsigned short>>((__int64)&v23);
    if ( v11 )
    {
      v15 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v11 + 16LL))(v11);
      v13 = v15;
      if ( v15 )
        (**v15)(v15, 1);
    }
    v16 = **(_DWORD **)(a1 + 72);
    v17 = (*(__int64 (__fastcall **)(struct std::_Facet_base *, __int64, void (__fastcall ***)(_QWORD, __int64)))(*(_QWORD *)v14 + 32LL))(
            v14,
            v12,
            v13);
    v18 = *(_QWORD *)(a1 + 64);
    if ( *(_QWORD *)(v18 + 24) <= 0xFu )
      v19 = *(char **)(a1 + 64);
    else
      v19 = *(char **)v18;
    v23 = v19;
    v24 = *(struct std::locale::_Locimp **)(v18 + 16);
    v5 = *std::_Write_separated_integer<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
            &v25,
            **(char ***)(a1 + 48),
            **(_QWORD **)(a1 + 56),
            &v23,
            v17,
            v16,
            v5);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) || **(_BYTE **)(a1 + 96) )
    {
      v20 = (*(__int64 (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v14 + 24LL))(v14);
      if ( (unsigned __int64)(*(_QWORD *)(v5 + 16) + 1LL) > *(_QWORD *)(v5 + 24) )
        (**(void (__fastcall ***)(__int64))v5)(v5);
      *(_WORD *)(*(_QWORD *)(v5 + 8) + 2LL * (*(_QWORD *)(v5 + 16))++) = v20;
      **(_BYTE **)(a1 + 96) = 0;
    }
    **(_QWORD **)(a1 + 48) = **(_QWORD **)(a1 + 56);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) )
      ++**(_QWORD **)(a1 + 48);
  }
  v21 = *std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
           &v25,
           **(char ***)(a1 + 48),
           **(char ***)(a1 + 104),
           v5);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 11LL) && **(_BYTE **)(a1 + 96) )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v21 + 16) + 1LL) > *(_QWORD *)(v21 + 24) )
      (**(void (__fastcall ***)(__int64))v21)(v21);
    *(_WORD *)(*(_QWORD *)(v21 + 8) + 2LL * (*(_QWORD *)(v21 + 16))++) = 46;
  }
  while ( **(int **)(a1 + 112) > 0 )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v21 + 16) + 1LL) > *(_QWORD *)(v21 + 24) )
      (**(void (__fastcall ***)(__int64))v21)(v21);
    *(_WORD *)(*(_QWORD *)(v21 + 8) + 2LL * (*(_QWORD *)(v21 + 16))++) = 48;
    --**(_DWORD **)(a1 + 112);
  }
  std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
    a2,
    **(char ***)(a1 + 104),
    **(char ***)(a1 + 88),
    v21);
  return a2;
}

```

## disassembly

```asm
0x14001f0fc  mov     r11, rsp
0x14001f0ff  push    rbx
0x14001f100  push    rbp
0x14001f101  push    rsi
0x14001f102  push    rdi
0x14001f103  push    r12
0x14001f105  push    r14
0x14001f107  sub     rsp, 58h
0x14001f10b  mov     rax, r8
0x14001f10e  mov     rbp, rdx
0x14001f111  mov     rdi, rcx
0x14001f114  mov     r9, [rcx+8]
0x14001f118  mov     r8, [rcx]
0x14001f11b  mov     r9b, [r9]
0x14001f11e  mov     r8b, [r8]
0x14001f121  mov     rdx, rax
0x14001f124  lea     rcx, [r11+8]
0x14001f128  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x14001f12d  mov     rbx, [rax]
0x14001f130  mov     rax, [rdi+10h]
0x14001f134  mov     r12d, 30h ; '0'
0x14001f13a  cmp     byte ptr [rax], 0
0x14001f13d  jz      short loc_14001F18A
0x14001f13f  mov     rax, [rdi+20h]
0x14001f143  mov     ecx, [rax]
0x14001f145  mov     rax, [rdi+18h]
0x14001f149  cmp     [rax], ecx
0x14001f14b  jge     short loc_14001F18A
0x14001f14d  sub     ecx, [rax]
0x14001f14f  movsxd  rsi, ecx
0x14001f152  test    ecx, ecx
0x14001f154  jle     short loc_14001F18A
0x14001f156  mov     rdx, [rbx+10h]
0x14001f15a  inc     rdx
0x14001f15d  cmp     rdx, [rbx+18h]
0x14001f161  jbe     short loc_14001F171
0x14001f163  mov     rax, [rbx]
0x14001f166  mov     rcx, rbx
0x14001f169  mov     rax, [rax]
0x14001f16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f171  mov     rcx, [rbx+10h]
0x14001f175  mov     rax, [rbx+8]
0x14001f179  mov     [rax+rcx*2], r12w
0x14001f17e  inc     qword ptr [rbx+10h]
0x14001f182  dec     rsi
0x14001f185  test    rsi, rsi
0x14001f188  jg      short loc_14001F156
0x14001f18a  mov     rax, [rdi+20h]
0x14001f18e  cmp     byte ptr [rax+0Ch], 0
0x14001f192  jz      loc_14001F2F8
0x14001f198  mov     rax, [rdi+28h]
0x14001f19c  mov     rsi, [rax]
0x14001f19f  test    rsi, rsi
0x14001f1a2  jz      short loc_14001F1BE
0x14001f1a4  mov     rsi, [rsi+8]
0x14001f1a8  mov     [rsp+88h+var_40], rsi
0x14001f1ad  mov     rax, [rsi]
0x14001f1b0  mov     rcx, rsi
0x14001f1b3  mov     rax, [rax+8]
0x14001f1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f1bc  jmp     short loc_14001F1CE
0x14001f1be  mov     cl, 1
0x14001f1c0  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001f1c6  mov     rsi, rax
0x14001f1c9  mov     [rsp+88h+var_40], rax
0x14001f1ce  lea     rcx, [rsp+88h+var_48]
0x14001f1d3  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001f1d8  mov     r14, rax
0x14001f1db  test    rsi, rsi
0x14001f1de  jz      short loc_14001F20A
0x14001f1e0  mov     rcx, [rsi]
0x14001f1e3  mov     rax, [rcx+10h]
0x14001f1e7  mov     rcx, rsi
0x14001f1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f1ef  mov     r8, rax
0x14001f1f2  test    rax, rax
0x14001f1f5  jz      short loc_14001F20A
0x14001f1f7  mov     rcx, [rax]
0x14001f1fa  mov     rax, [rcx]
0x14001f1fd  mov     edx, 1
0x14001f202  mov     rcx, r8
0x14001f205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f20a  mov     rax, [rdi+48h]
0x14001f20e  mov     esi, [rax]
0x14001f210  mov     rax, [r14]
0x14001f213  mov     rcx, r14
0x14001f216  mov     rax, [rax+20h]
0x14001f21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f21f  movzx   r9d, ax
0x14001f223  mov     rax, [rdi+40h]
0x14001f227  cmp     qword ptr [rax+18h], 0Fh
0x14001f22c  jbe     short loc_14001F233
0x14001f22e  mov     rcx, [rax]
0x14001f231  jmp     short loc_14001F236
0x14001f233  mov     rcx, rax
0x14001f236  mov     [rsp+88h+var_48], rcx
0x14001f23b  mov     rax, [rax+10h]
0x14001f23f  mov     [rsp+88h+var_40], rax
0x14001f244  mov     r8, [rdi+38h]
0x14001f248  mov     rdx, [rdi+30h]
0x14001f24c  mov     [rsp+88h+var_58], rbx
0x14001f251  mov     [rsp+88h+var_60], esi
0x14001f255  mov     [rsp+88h+var_68], r9w
0x14001f25b  lea     r9, [rsp+88h+var_48]
0x14001f260  mov     r8, [r8]
0x14001f263  mov     rdx, [rdx]
0x14001f266  lea     rcx, [rsp+88h+arg_0]
0x14001f26e  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f273  mov     rbx, [rax]
0x14001f276  mov     rax, [rdi+58h]
0x14001f27a  mov     rcx, [rdi+50h]
0x14001f27e  mov     rax, [rax]
0x14001f281  cmp     [rcx], rax
0x14001f284  jnz     short loc_14001F28F
0x14001f286  mov     rax, [rdi+60h]
0x14001f28a  cmp     byte ptr [rax], 0
0x14001f28d  jz      short loc_14001F2D3
0x14001f28f  mov     rax, [r14]
0x14001f292  mov     rcx, r14
0x14001f295  mov     rax, [rax+18h]
0x14001f299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f29e  movzx   esi, ax
0x14001f2a1  mov     rdx, [rbx+10h]
0x14001f2a5  inc     rdx
0x14001f2a8  cmp     rdx, [rbx+18h]
0x14001f2ac  jbe     short loc_14001F2BC
0x14001f2ae  mov     rcx, [rbx]
0x14001f2b1  mov     rax, [rcx]
0x14001f2b4  mov     rcx, rbx
0x14001f2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f2bc  mov     rcx, [rbx+10h]
0x14001f2c0  mov     rax, [rbx+8]
0x14001f2c4  mov     [rax+rcx*2], si
0x14001f2c8  inc     qword ptr [rbx+10h]
0x14001f2cc  mov     rax, [rdi+60h]
0x14001f2d0  mov     byte ptr [rax], 0
0x14001f2d3  mov     rax, [rdi+38h]
0x14001f2d7  mov     rcx, [rdi+30h]
0x14001f2db  mov     rax, [rax]
0x14001f2de  mov     [rcx], rax
0x14001f2e1  mov     rax, [rdi+58h]
0x14001f2e5  mov     rcx, [rdi+50h]
0x14001f2e9  mov     rax, [rax]
0x14001f2ec  cmp     [rcx], rax
0x14001f2ef  jz      short loc_14001F2F8
0x14001f2f1  mov     rax, [rdi+30h]
0x14001f2f5  inc     qword ptr [rax]
0x14001f2f8  mov     r8, [rdi+68h]
0x14001f2fc  mov     rdx, [rdi+30h]
0x14001f300  mov     r9, rbx
0x14001f303  mov     r8, [r8]
0x14001f306  mov     rdx, [rdx]
0x14001f309  lea     rcx, [rsp+88h+arg_0]
0x14001f311  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f316  mov     rbx, [rax]
0x14001f319  mov     rax, [rdi+20h]
0x14001f31d  cmp     byte ptr [rax+0Bh], 0
0x14001f321  jz      short loc_14001F38D
0x14001f323  mov     rax, [rdi+60h]
0x14001f327  cmp     byte ptr [rax], 0
0x14001f32a  jz      short loc_14001F38D
0x14001f32c  mov     rdx, [rbx+10h]
0x14001f330  inc     rdx
0x14001f333  cmp     rdx, [rbx+18h]
0x14001f337  jbe     short loc_14001F347
0x14001f339  mov     rax, [rbx]
0x14001f33c  mov     rcx, rbx
0x14001f33f  mov     rax, [rax]
0x14001f342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f347  mov     rcx, [rbx+10h]
0x14001f34b  mov     rax, [rbx+8]
0x14001f34f  mov     word ptr [rax+rcx*2], 2Eh ; '.'
0x14001f355  inc     qword ptr [rbx+10h]
0x14001f359  jmp     short loc_14001F38D
0x14001f35b  mov     rdx, [rbx+10h]
0x14001f35f  inc     rdx
0x14001f362  cmp     rdx, [rbx+18h]
0x14001f366  jbe     short loc_14001F376
0x14001f368  mov     rax, [rbx]
0x14001f36b  mov     rcx, rbx
0x14001f36e  mov     rax, [rax]
0x14001f371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f376  mov     rcx, [rbx+10h]
0x14001f37a  mov     rax, [rbx+8]
0x14001f37e  mov     [rax+rcx*2], r12w
0x14001f383  inc     qword ptr [rbx+10h]
0x14001f387  mov     rax, [rdi+70h]
0x14001f38b  dec     dword ptr [rax]
0x14001f38d  mov     rax, [rdi+70h]
0x14001f391  cmp     dword ptr [rax], 0
0x14001f394  jg      short loc_14001F35B
0x14001f396  mov     r8, [rdi+58h]
0x14001f39a  mov     rdx, [rdi+68h]
0x14001f39e  mov     r9, rbx
0x14001f3a1  mov     r8, [r8]
0x14001f3a4  mov     rdx, [rdx]
0x14001f3a7  mov     rcx, rbp
0x14001f3aa  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001f3af  mov     rax, rbp
0x14001f3b2  add     rsp, 58h
0x14001f3b6  pop     r14
0x14001f3b8  pop     r12
0x14001f3ba  pop     rdi
0x14001f3bb  pop     rsi
0x14001f3bc  pop     rbp
0x14001f3bd  pop     rbx
0x14001f3be  retn
```
