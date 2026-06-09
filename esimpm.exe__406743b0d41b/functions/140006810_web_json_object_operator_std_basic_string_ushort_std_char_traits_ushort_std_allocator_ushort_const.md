# web::json::object::operator[](std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140006810`
- end: `0x140006a26`
- name: `??Aobject@json@web@@QEAAAEAVvalue@12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `534`
- prototype: `char *__fastcall(wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140007ef0`

## callees

- `0x140002f60`
- `0x140002f84`
- `0x1400041b0`
- `0x1400043e0`
- `0x140004ae0`
- `0x140006810`
- `0x140007880`
- `0x140013df8`
- `0x1400147cc`
- `0x140022f0c`
- `0x14003e010`

## pseudocode

```c
char *__fastcall web::json::object::operator[](wchar_t *a1, __int64 a2)
{
  char *v4; // rbx
  const wchar_t *v5; // rdx
  const wchar_t *v6; // rcx
  size_t v7; // r8
  bool v8; // cl
  wchar_t *v9; // rdi
  __m128i *v10; // r8
  wchar_t *v11; // r14
  __int8 *v12; // rdx
  __int64 v13; // rax
  wchar_t *S2[2]; // [rsp+20h] [rbp-39h] BYREF
  _OWORD v16[2]; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *v17; // [rsp+50h] [rbp-9h]
  __m128i v18; // [rsp+58h] [rbp-1h] BYREF
  __m128i si128; // [rsp+68h] [rbp+Fh]
  wchar_t *v20; // [rsp+78h] [rbp+1Fh]

  web::json::object::find_insert_location(a1, S2, a2);
  v4 = (char *)S2[0];
  if ( S2[0] == *((wchar_t **)a1 + 1)
    || (*((_QWORD *)S2[0] + 3) <= 7u ? (v5 = S2[0]) : (v5 = *(const wchar_t **)S2[0]),
        *(_QWORD *)(a2 + 24) <= 7u ? (v6 = (const wchar_t *)a2) : (v6 = *(const wchar_t **)a2),
        (v7 = *(_QWORD *)(a2 + 16), v7 == *((_QWORD *)S2[0] + 2))
      ? (v7
       ? (v8 = wmemcmp(v6, v5, v7) != 0)
       : (v8 = 0))
      : (v8 = 1),
        v8) )
  {
    v9 = (wchar_t *)operator new(8u);
    S2[0] = v9;
    if ( v9 )
      *(_QWORD *)v9 = &web::json::details::_Null::`vftable';
    else
      v9 = 0;
    S2[0] = v9;
    std::wstring::wstring(&v18, a2);
    S2[0] = 0;
    v20 = v9;
    v10 = (__m128i *)*((_QWORD *)a1 + 1);
    if ( v10 == *((__m128i **)a1 + 2) )
    {
      v4 = std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(
             a1,
             (__int64)v4,
             (__int64)&v18);
      v11 = v20;
    }
    else
    {
      v11 = 0;
      v20 = 0;
      if ( v4 == (char *)v10 )
      {
        *v10 = v18;
        v10[1] = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v18.m128i_i16[0] = 0;
        v10[2].m128i_i64[0] = (__int64)v9;
        *((_QWORD *)a1 + 1) += 40LL;
      }
      else
      {
        S2[1] = a1;
        v16[0] = v18;
        v16[1] = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v18.m128i_i16[0] = 0;
        v17 = v9;
        v12 = &v10[-3].m128i_i8[8];
        *v10 = *(__m128i *)((char *)v10 - 40);
        v10[1] = *(__m128i *)((char *)&v10[-2] + 8);
        *((_QWORD *)v12 + 2) = 0;
        *((_QWORD *)v12 + 3) = 7;
        *(_WORD *)v12 = 0;
        v13 = v10[-1].m128i_i64[1];
        *((_QWORD *)v12 + 4) = 0;
        v10[2].m128i_i64[0] = v13;
        *((_QWORD *)a1 + 1) += 40LL;
        std::_Move_backward_unchecked<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *>(
          (__int64)v4,
          (__int64)&v10[-3].m128i_i64[1],
          v10);
        std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(
          v4,
          (__int64)v16);
        if ( v17 )
          (*(void (__fastcall **)(wchar_t *, __int64))(*(_QWORD *)v17 + 192LL))(v17, 1);
        std::wstring::_Tidy_deallocate(v16);
      }
    }
    if ( v11 )
      (*(void (__fastcall **)(wchar_t *, __int64))(*(_QWORD *)v11 + 192LL))(v11, 1);
    std::wstring::_Tidy_deallocate(&v18);
  }
  return v4 + 32;
}

```

## disassembly

```asm
0x140006810  mov     [rsp-8+arg_10], rbx
0x140006815  push    rbp
0x140006816  push    rsi
0x140006817  push    rdi
0x140006818  push    r14
0x14000681a  push    r15
0x14000681c  lea     rbp, [rsp-37h]
0x140006821  sub     rsp, 90h
0x140006828  mov     rax, cs:__security_cookie
0x14000682f  xor     rax, rsp
0x140006832  mov     [rbp+57h+var_30], rax
0x140006836  mov     r14, rdx
0x140006839  mov     rsi, rcx
0x14000683c  xor     r15d, r15d
0x14000683f  mov     r8, rdx
0x140006842  lea     rdx, [rbp+57h+S2]
0x140006846  call    ?find_insert_location@object@json@web@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; web::json::object::find_insert_location(std::wstring const &)
0x14000684b  mov     rbx, [rbp+57h+S2]
0x14000684f  cmp     rbx, [rsi+8]
0x140006853  jz      short loc_1400068A0
0x140006855  cmp     qword ptr [rbx+18h], 7
0x14000685a  jbe     short loc_140006861
0x14000685c  mov     rdx, [rbx]
0x14000685f  jmp     short loc_140006864
0x140006861  mov     rdx, rbx; S2
0x140006864  cmp     qword ptr [r14+18h], 7
0x140006869  jbe     short loc_140006870
0x14000686b  mov     rcx, [r14]
0x14000686e  jmp     short loc_140006873
0x140006870  mov     rcx, r14; S1
0x140006873  mov     r8, [r14+10h]; N
0x140006877  cmp     r8, [rbx+10h]
0x14000687b  jz      short loc_140006884
0x14000687d  mov     ecx, 1
0x140006882  jmp     short loc_140006898
0x140006884  test    r8, r8
0x140006887  jnz     short loc_14000688E
0x140006889  mov     ecx, r15d
0x14000688c  jmp     short loc_140006898
0x14000688e  call    wmemcmp
0x140006893  test    eax, eax
0x140006895  setnz   cl
0x140006898  test    cl, cl
0x14000689a  jz      loc_1400069FF
0x1400068a0  mov     ecx, 8; Size
0x1400068a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400068aa  mov     rdi, rax
0x1400068ad  mov     [rbp+57h+S2], rax
0x1400068b1  test    rax, rax
0x1400068b4  jz      short loc_1400068C2
0x1400068b6  lea     rax, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x1400068bd  mov     [rdi], rax
0x1400068c0  jmp     short loc_1400068C5
0x1400068c2  mov     rdi, r15
0x1400068c5  mov     [rbp+57h+S2], rdi
0x1400068c9  mov     rdx, r14
0x1400068cc  lea     rcx, [rbp+57h+var_58]
0x1400068d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400068d5  mov     [rbp+57h+S2], r15
0x1400068d9  mov     [rbp+57h+var_38], rdi
0x1400068dd  mov     r8, [rsi+8]
0x1400068e1  cmp     r8, [rsi+10h]
0x1400068e5  jz      loc_1400069C3
0x1400068eb  mov     r14, r15
0x1400068ee  mov     [rbp+57h+var_38], r15
0x1400068f2  cmp     rbx, r8
0x1400068f5  jnz     short loc_140006928
0x1400068f7  movups  xmm0, [rbp+57h+var_58]
0x1400068fb  movups  xmmword ptr [r8], xmm0
0x1400068ff  movups  xmm1, [rbp+57h+var_48]
0x140006903  movups  xmmword ptr [r8+10h], xmm1
0x140006908  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140006910  movdqu  [rbp+57h+var_48], xmm0
0x140006915  mov     word ptr [rbp+57h+var_58], r15w
0x14000691a  mov     [r8+20h], rdi
0x14000691e  add     qword ptr [rsi+8], 28h ; '('
0x140006923  jmp     loc_1400069D9
0x140006928  mov     [rbp+57h+var_88], rsi
0x14000692c  movups  xmm1, [rbp+57h+var_58]
0x140006930  movups  [rbp+57h+var_80], xmm1
0x140006934  movups  xmm0, [rbp+57h+var_48]
0x140006938  movups  [rbp+57h+var_70], xmm0
0x14000693c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140006944  movdqu  [rbp+57h+var_48], xmm1
0x140006949  mov     word ptr [rbp+57h+var_58], r15w
0x14000694e  mov     [rbp+57h+var_60], rdi
0x140006952  lea     rdx, [r8-28h]
0x140006956  movups  xmm0, xmmword ptr [rdx]
0x140006959  movups  xmmword ptr [r8], xmm0
0x14000695d  movups  xmm1, xmmword ptr [rdx+10h]
0x140006961  movups  xmmword ptr [r8+10h], xmm1
0x140006966  mov     [rdx+10h], r15
0x14000696a  mov     qword ptr [rdx+18h], 7
0x140006972  mov     [rdx], r15w
0x140006976  mov     rax, [rdx+20h]
0x14000697a  mov     [rdx+20h], r15
0x14000697e  mov     [r8+20h], rax
0x140006982  add     qword ptr [rsi+8], 28h ; '('
0x140006987  mov     rcx, rbx
0x14000698a  call    ??$_Move_backward_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@PEAU12@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@PEAU10@00@Z; std::_Move_backward_unchecked<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *)
0x14000698f  lea     rdx, [rbp+57h+var_80]
0x140006993  mov     rcx, rbx
0x140006996  call    ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(std::pair<std::wstring,web::json::value> &&)
0x14000699b  mov     rcx, [rbp+57h+var_60]
0x14000699f  test    rcx, rcx
0x1400069a2  jz      short loc_1400069B8
0x1400069a4  mov     rax, [rcx]
0x1400069a7  mov     edx, 1
0x1400069ac  mov     rax, [rax+0C0h]
0x1400069b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069b8  lea     rcx, [rbp+57h+var_80]
0x1400069bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400069c1  jmp     short loc_1400069D9
0x1400069c3  lea     r8, [rbp+57h+var_58]
0x1400069c7  mov     rdx, rbx
0x1400069ca  mov     rcx, rsi
0x1400069cd  call    ??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> &&)
0x1400069d2  mov     rbx, rax
0x1400069d5  mov     r14, [rbp+57h+var_38]
0x1400069d9  test    r14, r14
0x1400069dc  jz      short loc_1400069F5
0x1400069de  mov     rax, [r14]
0x1400069e1  mov     edx, 1
0x1400069e6  mov     rcx, r14
0x1400069e9  mov     rax, [rax+0C0h]
0x1400069f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069f5  lea     rcx, [rbp+57h+var_58]
0x1400069f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400069fe  nop
0x1400069ff  lea     rax, [rbx+20h]
0x140006a03  mov     rcx, [rbp+57h+var_30]
0x140006a07  xor     rcx, rsp; StackCookie
0x140006a0a  call    __security_check_cookie
0x140006a0f  mov     rbx, [rsp+0B0h+arg_10]
0x140006a17  add     rsp, 90h
0x140006a1e  pop     r15
0x140006a20  pop     r14
0x140006a22  pop     rdi
0x140006a23  pop     rsi
0x140006a24  pop     rbp
0x140006a25  retn
```
