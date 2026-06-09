# std::_Sort_unchecked<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &)>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,__int64,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &))

- ea: `0x140005960`
- end: `0x140005c7e`
- name: `??$_Sort_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z`
- size: `798`
- prototype: `__int128 *__fastcall(unsigned __int64, __int128 *, __int64, unsigned __int8 (__fastcall *)(__int128 *, __int64 *))`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x140005960`
- `0x140009f80`

## callees

- `0x140002f60`
- `0x140003244`
- `0x140004670`
- `0x140004a60`
- `0x140004bc0`
- `0x140005060`
- `0x1400057b0`
- `0x140005960`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int128 *__fastcall std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        unsigned __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned __int8 (__fastcall *a4)(__int128 *, __int64 *))
{
  __int128 *v6; // rbp
  unsigned __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // r13
  __int64 v10; // rdx
  unsigned __int8 (__fastcall *v11)(__int64, __int64); // r9
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // r13
  unsigned __int64 v17; // rdi
  __int128 *v18; // rsi
  __int64 v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rax
  void *v23; // rcx
  __int64 v24; // [rsp+30h] [rbp-98h]
  __int128 *v25; // [rsp+38h] [rbp-90h]
  __int128 *v26; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-80h]
  _BYTE v28[24]; // [rsp+50h] [rbp-78h] BYREF
  unsigned __int64 v29; // [rsp+68h] [rbp-60h]
  __int64 v30; // [rsp+70h] [rbp-58h]

  v6 = a2;
  v7 = a1;
  if ( (__int64)((__int64)a2 - a1) < 1320 )
    return std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
             v7,
             v6,
             a4);
  while ( 1 )
  {
    v8 = (__int64)((__int64)v6 - v7) / 40;
    if ( a3 <= 0 )
      break;
    v9 = v7 + 40 * (v8 >> 1);
    v25 = (__int128 *)v9;
    v10 = (__int64)((__int64)v6 - v7 - 40) / 40;
    v11 = (unsigned __int8 (__fastcall *)(__int64, __int64))a4;
    v12 = v7;
    if ( v10 <= 40 )
    {
      v16 = (__int64)v6 - 40;
    }
    else
    {
      v13 = (v10 + 1) >> 3;
      v14 = 80 * v13;
      v15 = 40 * v13;
      v24 = 40 * v13 + v7;
      std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        v7,
        v24,
        80 * v13 + v7,
        (unsigned __int8 (__fastcall *)(__int64, __int64))a4);
      std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        v9 - v15,
        v9,
        v15 + v9,
        (unsigned __int8 (__fastcall *)(__int64, __int64))a4);
      v16 = (__int64)v6 - v15 - 40;
      std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        (__int64)&v6[v14 / 0xFFFFFFFFFFFFFFF0uLL - 2] - 8,
        v16,
        (__int64)v6 - 40,
        (unsigned __int8 (__fastcall *)(__int64, __int64))a4);
      v11 = (unsigned __int8 (__fastcall *)(__int64, __int64))a4;
      v12 = v24;
    }
    std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
      v12,
      (__int64)v25,
      v16,
      v11);
    std::_Partition_by_pivot_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
      &v26,
      v7,
      v25,
      (unsigned __int64)v6,
      (unsigned __int8 (__fastcall *)(char *, __int128 *))a4);
    a3 = (a3 >> 2) + (a3 >> 1);
    v17 = v27;
    v18 = v26;
    if ( (__int64)((__int64)v26 - v7) / 40 >= (__int64)((__int64)v6 - v27) / 40 )
    {
      std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        v27,
        v6,
        a3,
        a4);
      v6 = v18;
    }
    else
    {
      std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        v7,
        v26,
        a3,
        a4);
      v7 = v17;
    }
    if ( (__int64)((__int64)v6 - v7) < 1320 )
      return std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
               v7,
               v6,
               a4);
  }
  v20 = v8 >> 1;
  while ( v20 > 0 )
  {
    --v20;
    v21 = 40 * v20;
    *(_OWORD *)v28 = 0;
    *(_QWORD *)v28 = *(_QWORD *)(40 * v20 + v7);
    *(_OWORD *)&v28[8] = *(_OWORD *)(40 * v20 + v7 + 8);
    v29 = *(_QWORD *)(40 * v20 + v7 + 24);
    *(_QWORD *)(v21 + v7 + 16) = 0;
    *(_QWORD *)(v21 + v7 + 24) = 7;
    *(_WORD *)(v21 + v7) = 0;
    v22 = *(_QWORD *)(40 * v20 + v7 + 32);
    *(_QWORD *)(v21 + v7 + 32) = 0;
    v30 = v22;
    std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
      v7,
      v20,
      v8,
      (__int64)v28,
      (unsigned __int8 (__fastcall *)(__int64, __int64))a4);
    if ( v30 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 192LL))(v30, 1);
    if ( v29 > 7 )
    {
      v23 = *(void **)v28;
      if ( 2 * v29 + 2 >= 0x1000 )
      {
        if ( (unsigned __int64)(*(_QWORD *)v28 - *(_QWORD *)(*(_QWORD *)v28 - 8LL) - 8LL) > 0x1F )
          __fastfail(5u);
        v23 = *(void **)(*(_QWORD *)v28 - 8LL);
      }
      operator delete(v23);
    }
  }
  return (__int128 *)std::_Sort_heap_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
                       v7,
                       (__int64)v6,
                       (unsigned __int8 (__fastcall *)(__int64, __int64))a4);
}

```

## disassembly

```asm
0x140005960  push    rbx
0x140005962  push    rbp
0x140005963  push    rsi
0x140005964  push    rdi
0x140005965  push    r12
0x140005967  push    r13
0x140005969  push    r14
0x14000596b  push    r15
0x14000596d  sub     rsp, 88h
0x140005974  mov     rax, cs:__security_cookie
0x14000597b  xor     rax, rsp
0x14000597e  mov     [rsp+0C8h+var_50], rax
0x140005983  mov     r14, r9
0x140005986  mov     r15, r8
0x140005989  mov     rbp, rdx
0x14000598c  mov     rbx, rcx
0x14000598f  mov     rax, rdx
0x140005992  sub     rax, rcx
0x140005995  cmp     rax, 528h
0x14000599b  jl      loc_140005B42
0x1400059a1  mov     r8, 6666666666666667h
0x1400059ab  nop     dword ptr [rax+rax+00h]
0x1400059b0  mov     rcx, rbp
0x1400059b3  sub     rcx, rbx
0x1400059b6  mov     rax, r8
0x1400059b9  imul    rcx
0x1400059bc  mov     rdi, rdx
0x1400059bf  sar     rdi, 4
0x1400059c3  mov     rax, rdi
0x1400059c6  shr     rax, 3Fh
0x1400059ca  add     rdi, rax
0x1400059cd  test    r15, r15
0x1400059d0  jle     loc_140005B71
0x1400059d6  sar     rdi, 1
0x1400059d9  lea     rax, [rdi+rdi*4]
0x1400059dd  lea     r13, [rbx+rax*8]
0x1400059e1  mov     [rsp+0C8h+var_90], r13
0x1400059e6  lea     rcx, [rbp-28h]
0x1400059ea  sub     rcx, rbx
0x1400059ed  mov     rax, r8
0x1400059f0  imul    rcx
0x1400059f3  sar     rdx, 4
0x1400059f7  mov     rax, rdx
0x1400059fa  shr     rax, 3Fh
0x1400059fe  add     rdx, rax
0x140005a01  mov     r9, r14
0x140005a04  mov     rcx, rbx
0x140005a07  cmp     rdx, 28h ; '('
0x140005a0b  jle     short loc_140005A7A
0x140005a0d  lea     rax, [rdx+1]
0x140005a11  sar     rax, 3
0x140005a15  lea     rsi, [rax+rax*4]
0x140005a19  shl     rsi, 4
0x140005a1d  lea     rax, [rax+rax*4]
0x140005a21  lea     rdi, ds:0[rax*8]
0x140005a29  lea     rax, [rdi+rbx]
0x140005a2d  mov     [rsp+0C8h+var_98], rax
0x140005a32  lea     r8, [rsi+rbx]
0x140005a36  mov     rdx, rax
0x140005a39  call    ??$_Med3_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@00P6A_NAEBU10@1@Z@Z; std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005a3e  lea     r8, [rdi+r13]
0x140005a42  mov     rcx, r13
0x140005a45  sub     rcx, rdi
0x140005a48  mov     r9, r14
0x140005a4b  mov     rdx, r13
0x140005a4e  call    ??$_Med3_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@00P6A_NAEBU10@1@Z@Z; std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005a53  lea     r13, [rbp-28h]
0x140005a57  sub     r13, rdi
0x140005a5a  lea     rcx, [rbp-28h]
0x140005a5e  sub     rcx, rsi
0x140005a61  mov     r9, r14
0x140005a64  lea     r8, [rbp-28h]
0x140005a68  mov     rdx, r13
0x140005a6b  call    ??$_Med3_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@00P6A_NAEBU10@1@Z@Z; std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005a70  mov     r9, r14
0x140005a73  mov     rcx, [rsp+0C8h+var_98]
0x140005a78  jmp     short loc_140005A7E
0x140005a7a  lea     r13, [rbp-28h]
0x140005a7e  mov     r8, r13
0x140005a81  mov     rdx, [rsp+0C8h+var_90]
0x140005a86  call    ??$_Med3_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@00P6A_NAEBU10@1@Z@Z; std::_Med3_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005a8b  mov     [rsp+0C8h+var_A8], r14
0x140005a90  mov     r9, rbp
0x140005a93  mov     r8, [rsp+0C8h+var_90]
0x140005a98  mov     rdx, rbx
0x140005a9b  lea     rcx, [rsp+0C8h+var_88]
0x140005aa0  call    ??$_Partition_by_pivot_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YA?AU?$pair@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@PEAU12@@0@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@00P6A_NAEBU20@1@Z@Z; std::_Partition_by_pivot_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005aa5  mov     rcx, r15
0x140005aa8  sar     rcx, 2
0x140005aac  sar     r15, 1
0x140005aaf  add     r15, rcx
0x140005ab2  mov     rcx, rbp
0x140005ab5  mov     rdi, [rsp+0C8h+var_80]
0x140005aba  sub     rcx, rdi
0x140005abd  mov     r8, 6666666666666667h
0x140005ac7  mov     rax, r8
0x140005aca  imul    rcx
0x140005acd  mov     rcx, rdx
0x140005ad0  sar     rcx, 4
0x140005ad4  mov     rax, rcx
0x140005ad7  shr     rax, 3Fh
0x140005adb  add     rcx, rax
0x140005ade  mov     rsi, [rsp+0C8h+var_88]
0x140005ae3  mov     rdx, rsi
0x140005ae6  sub     rdx, rbx
0x140005ae9  mov     rax, r8
0x140005aec  imul    rdx
0x140005aef  sar     rdx, 4
0x140005af3  mov     rax, rdx
0x140005af6  shr     rax, 3Fh
0x140005afa  add     rdx, rax
0x140005afd  mov     r9, r14
0x140005b00  mov     r8, r15
0x140005b03  cmp     rdx, rcx
0x140005b06  jge     short loc_140005B18
0x140005b08  mov     rdx, rsi
0x140005b0b  mov     rcx, rbx
0x140005b0e  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z; std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,__int64,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005b13  mov     rbx, rdi
0x140005b16  jmp     short loc_140005B26
0x140005b18  mov     rdx, rbp
0x140005b1b  mov     rcx, rdi
0x140005b1e  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z; std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,__int64,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005b23  mov     rbp, rsi
0x140005b26  mov     rax, rbp
0x140005b29  sub     rax, rbx
0x140005b2c  cmp     rax, 528h
0x140005b32  mov     r8, 6666666666666667h
0x140005b3c  jge     loc_1400059B0
0x140005b42  mov     r8, r14
0x140005b45  mov     rdx, rbp
0x140005b48  mov     rcx, rbx
0x140005b4b  call    ??$_Insertion_sort_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0P6A_NAEBU10@1@Z@Z; std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005b50  mov     rcx, [rsp+0C8h+var_50]
0x140005b55  xor     rcx, rsp; StackCookie
0x140005b58  call    __security_check_cookie
0x140005b5d  add     rsp, 88h
0x140005b64  pop     r15
0x140005b66  pop     r14
0x140005b68  pop     r13
0x140005b6a  pop     r12
0x140005b6c  pop     rdi
0x140005b6d  pop     rsi
0x140005b6e  pop     rbp
0x140005b6f  pop     rbx
0x140005b70  retn
0x140005b71  mov     rsi, rdi
0x140005b74  sar     rsi, 1
0x140005b77  test    rsi, rsi
0x140005b7a  jle     loc_140005C64
0x140005b80  xor     r15d, r15d
0x140005b83  nop     dword ptr [rax+00h]
0x140005b87  nop     word ptr [rax+rax+00000000h]
0x140005b90  dec     rsi
0x140005b93  lea     rax, [rsi+rsi*4]
0x140005b97  lea     rcx, ds:0[rax*8]
0x140005b9f  xorps   xmm0, xmm0
0x140005ba2  movups  xmmword ptr [rsp+0C8h+var_78], xmm0
0x140005ba7  mov     rax, [rcx+rbx]
0x140005bab  mov     qword ptr [rsp+0C8h+var_78], rax
0x140005bb0  movups  xmm0, xmmword ptr [rcx+rbx+8]
0x140005bb5  movups  xmmword ptr [rsp+0C8h+var_78+8], xmm0
0x140005bba  mov     rax, [rcx+rbx+18h]
0x140005bbf  mov     [rsp+0C8h+var_60], rax
0x140005bc4  mov     [rcx+rbx+10h], r15
0x140005bc9  mov     qword ptr [rcx+rbx+18h], 7
0x140005bd2  mov     [rcx+rbx], r15w
0x140005bd7  mov     rax, [rcx+rbx+20h]
0x140005bdc  mov     [rcx+rbx+20h], r15
0x140005be1  mov     [rsp+0C8h+var_58], rax
0x140005be6  mov     [rsp+0C8h+var_A8], r14
0x140005beb  lea     r9, [rsp+0C8h+var_78]
0x140005bf0  mov     r8, rdi
0x140005bf3  mov     rdx, rsi
0x140005bf6  mov     rcx, rbx
0x140005bf9  call    ??$_Pop_heap_hole_by_index@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@U12@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@_J1$$QEAU10@P6A_NAEBU10@3@Z@Z; std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,__int64,__int64,std::pair<std::wstring,web::json::value> &&,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005bfe  nop
0x140005bff  mov     rcx, [rsp+0C8h+var_58]
0x140005c04  test    rcx, rcx
0x140005c07  jz      short loc_140005C1D
0x140005c09  mov     rax, [rcx]
0x140005c0c  mov     edx, 1
0x140005c11  mov     rax, [rax+0C0h]
0x140005c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c1d  mov     rdx, [rsp+0C8h+var_60]
0x140005c22  cmp     rdx, 7
0x140005c26  jbe     short loc_140005C5B
0x140005c28  lea     rdx, ds:2[rdx*2]
0x140005c30  mov     rcx, qword ptr [rsp+0C8h+var_78]
0x140005c35  cmp     rdx, 1000h
0x140005c3c  jb      short loc_140005C56
0x140005c3e  mov     rax, [rcx-8]
0x140005c42  sub     rcx, rax
0x140005c45  sub     rcx, 8
0x140005c49  cmp     rcx, 1Fh
0x140005c4d  ja      short loc_140005C77
0x140005c4f  add     rdx, 27h ; '''
0x140005c53  mov     rcx, rax; Block
0x140005c56  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005c5b  test    rsi, rsi
0x140005c5e  jg      loc_140005B90
0x140005c64  mov     r8, r14
0x140005c67  mov     rdx, rbp
0x140005c6a  mov     rcx, rbx
0x140005c6d  call    ??$_Sort_heap_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@0P6A_NAEBU10@1@Z@Z; std::_Sort_heap_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x140005c72  jmp     loc_140005B50
0x140005c77  mov     ecx, 5
0x140005c7c  int     29h; Win8: RtlFailFast(ecx)
```
