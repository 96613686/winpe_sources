# std::_Sort_heap_unchecked<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &)>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &))

- ea: `0x1400057b0`
- end: `0x140005959`
- name: `??$_Sort_heap_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@0P6A_NAEBU10@1@Z@Z`
- size: `425`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 (__fastcall *)(__int64, __int64))`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x140005960`

## callees

- `0x140002f60`
- `0x140003244`
- `0x140005060`
- `0x1400057b0`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall std::_Sort_heap_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 (__fastcall *a3)(__int64, __int64))
{
  __int64 v4; // rdi
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 *v8; // r9
  __int64 v9; // rax
  __int64 *v10; // r8
  __int64 v11; // rcx
  void *v12; // rcx
  _BYTE v13[24]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int64 v14; // [rsp+48h] [rbp-40h]
  __int64 v15; // [rsp+50h] [rbp-38h]

  v4 = a2;
  for ( result = a2 - a1; v4 - a1 >= 80; result = v4 - a1 )
  {
    if ( (v4 - a1) / 40 >= 2 )
    {
      v7 = v4 - 40;
      *(_OWORD *)v13 = 0;
      *(_QWORD *)v13 = *(_QWORD *)(v4 - 40);
      *(_OWORD *)&v13[8] = *(_OWORD *)(v4 - 40 + 8);
      v14 = *(_QWORD *)(v4 - 40 + 24);
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 24) = 7;
      *(_WORD *)v7 = 0;
      v8 = (__int64 *)(v4 - 40 + 32);
      v9 = *v8;
      *v8 = 0;
      v15 = v9;
      if ( v4 - 40 != a1 )
      {
        *(_QWORD *)(v7 + 16) = 0;
        *(_QWORD *)(v7 + 24) = 7;
        *(_WORD *)v7 = 0;
        *(_OWORD *)v7 = *(_OWORD *)a1;
        *(_OWORD *)(v7 + 16) = *(_OWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 7;
        *(_WORD *)a1 = 0;
      }
      v10 = (__int64 *)(a1 + 32);
      if ( v8 != (__int64 *)(a1 + 32) )
      {
        v11 = *v8;
        *v8 = *v10;
        *v10 = v11;
      }
      std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        a1,
        0,
        (v7 - a1) / 40,
        (__int64)v13,
        a3);
      if ( v15 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 192LL))(v15, 1);
      if ( v14 > 7 )
      {
        v12 = *(void **)v13;
        if ( 2 * v14 + 2 >= 0x1000 )
        {
          if ( (unsigned __int64)(*(_QWORD *)v13 - *(_QWORD *)(*(_QWORD *)v13 - 8LL) - 8LL) > 0x1F )
            __fastfail(5u);
          v12 = *(void **)(*(_QWORD *)v13 - 8LL);
        }
        operator delete(v12);
      }
    }
    v4 -= 40;
  }
  return result;
}

```

## disassembly

```asm
0x1400057b0  push    rbx
0x1400057b2  push    rbp
0x1400057b3  push    rsi
0x1400057b4  push    rdi
0x1400057b5  push    r14
0x1400057b7  sub     rsp, 60h
0x1400057bb  mov     rax, cs:__security_cookie
0x1400057c2  xor     rax, rsp
0x1400057c5  mov     [rsp+88h+var_30], rax
0x1400057ca  mov     rsi, r8
0x1400057cd  mov     rdi, rdx
0x1400057d0  mov     rbx, rcx
0x1400057d3  mov     rax, rdx
0x1400057d6  sub     rax, rcx
0x1400057d9  cmp     rax, 50h ; 'P'
0x1400057dd  jl      loc_14000593A
0x1400057e3  xor     ebp, ebp
0x1400057e5  mov     r14, 6666666666666667h
0x1400057ef  nop
0x1400057f0  mov     rcx, rdi
0x1400057f3  sub     rcx, rbx
0x1400057f6  mov     rax, r14
0x1400057f9  imul    rcx
0x1400057fc  sar     rdx, 4
0x140005800  mov     rax, rdx
0x140005803  shr     rax, 3Fh
0x140005807  add     rdx, rax
0x14000580a  cmp     rdx, 2
0x14000580e  jl      loc_140005926
0x140005814  lea     rdx, [rdi-28h]
0x140005818  xorps   xmm0, xmm0
0x14000581b  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x140005820  mov     rax, [rdx]
0x140005823  mov     qword ptr [rsp+88h+var_58], rax
0x140005828  movups  xmm0, xmmword ptr [rdx+8]
0x14000582c  movups  xmmword ptr [rsp+88h+var_58+8], xmm0
0x140005831  mov     rax, [rdx+18h]
0x140005835  mov     [rsp+88h+var_40], rax
0x14000583a  mov     [rdx+10h], rbp
0x14000583e  mov     qword ptr [rdx+18h], 7
0x140005846  mov     [rdx], bp
0x140005849  lea     r9, [rdx+20h]
0x14000584d  mov     rax, [r9]
0x140005850  mov     [r9], rbp
0x140005853  mov     [rsp+88h+var_38], rax
0x140005858  cmp     rdx, rbx
0x14000585b  jz      short loc_140005889
0x14000585d  mov     [rdx+10h], rbp
0x140005861  mov     qword ptr [rdx+18h], 7
0x140005869  mov     [rdx], bp
0x14000586c  movups  xmm0, xmmword ptr [rbx]
0x14000586f  movups  xmmword ptr [rdx], xmm0
0x140005872  movups  xmm1, xmmword ptr [rbx+10h]
0x140005876  movups  xmmword ptr [rdx+10h], xmm1
0x14000587a  mov     [rbx+10h], rbp
0x14000587e  mov     qword ptr [rbx+18h], 7
0x140005886  mov     [rbx], bp
0x140005889  lea     r8, [rbx+20h]
0x14000588d  cmp     r9, r8
0x140005890  jz      short loc_14000589E
0x140005892  mov     rcx, [r9]
0x140005895  mov     rax, [r8]
0x140005898  mov     [r9], rax
0x14000589b  mov     [r8], rcx
0x14000589e  sub     rdx, rbx
0x1400058a1  mov     rax, r14
0x1400058a4  imul    rdx
0x1400058a7  sar     rdx, 4
0x1400058ab  mov     r8, rdx
0x1400058ae  shr     r8, 3Fh
0x1400058b2  add     r8, rdx
0x1400058b5  mov     [rsp+88h+var_68], rsi
0x1400058ba  lea     r9, [rsp+88h+var_58]
0x1400058bf  xor     edx, edx
0x1400058c1  mov     rcx, rbx
0x1400058c4  call    ??$_Pop_heap_hole_by_index@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@U12@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@_J1$$QEAU10@P6A_NAEBU10@3@Z@Z; std::_Pop_heap_hole_by_index<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value>,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,__int64,__int64,std::pair<std::wstring,web::json::value> &&,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x1400058c9  nop
0x1400058ca  mov     rcx, [rsp+88h+var_38]
0x1400058cf  test    rcx, rcx
0x1400058d2  jz      short loc_1400058E8
0x1400058d4  mov     rax, [rcx]
0x1400058d7  mov     edx, 1
0x1400058dc  mov     rax, [rax+0C0h]
0x1400058e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058e8  mov     rdx, [rsp+88h+var_40]
0x1400058ed  cmp     rdx, 7
0x1400058f1  jbe     short loc_140005926
0x1400058f3  lea     rdx, ds:2[rdx*2]
0x1400058fb  mov     rcx, qword ptr [rsp+88h+var_58]
0x140005900  cmp     rdx, 1000h
0x140005907  jb      short loc_140005921
0x140005909  mov     rax, [rcx-8]
0x14000590d  sub     rcx, rax
0x140005910  sub     rcx, 8
0x140005914  cmp     rcx, 1Fh
0x140005918  ja      short loc_140005952
0x14000591a  add     rdx, 27h ; '''
0x14000591e  mov     rcx, rax; Block
0x140005921  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005926  sub     rdi, 28h ; '('
0x14000592a  mov     rax, rdi
0x14000592d  sub     rax, rbx
0x140005930  cmp     rax, 50h ; 'P'
0x140005934  jge     loc_1400057F0
0x14000593a  mov     rcx, [rsp+88h+var_30]
0x14000593f  xor     rcx, rsp; StackCookie
0x140005942  call    __security_check_cookie
0x140005947  add     rsp, 60h
0x14000594b  pop     r14
0x14000594d  pop     rdi
0x14000594e  pop     rsi
0x14000594f  pop     rbp
0x140005950  pop     rbx
0x140005951  retn
0x140005952  mov     ecx, 5
0x140005957  int     29h; Win8: RtlFailFast(ecx)
```
