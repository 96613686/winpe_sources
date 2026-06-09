# web::json::details::JSON_Parser<ushort>::_ParseObject(web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x140009f80`
- end: `0x14000a3b0`
- name: `?_ParseObject@?$JSON_Parser@G@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `1072`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000a3c0`

## callees

- `0x140002f60`
- `0x140002f84`
- `0x140003244`
- `0x140005960`
- `0x1400064b0`
- `0x140007f60`
- `0x140008630`
- `0x1400098a0`
- `0x140009f80`
- `0x14000a3c0`
- `0x14003e010`

## pseudocode

```c
_QWORD *__fastcall web::json::details::JSON_Parser<unsigned short>::_ParseObject(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  void *v6; // rsi
  bool v7; // al
  web::json::details *v8; // rcx
  unsigned __int64 v9; // rdi
  void **v10; // r14
  __m128i v11; // xmm7
  __m128i v12; // xmm6
  __int64 *v13; // rcx
  __int64 v14; // rax
  __m128i *v15; // rdx
  void *v16; // rcx
  const struct web::json::details::json_error_category_impl *v17; // rax
  _QWORD *v18; // rax
  void *v20; // rcx
  _QWORD *v21; // rax
  void *v22; // rcx
  __int64 v23; // [rsp+28h] [rbp-59h] BYREF
  web::json::details *v24; // [rsp+30h] [rbp-51h] BYREF
  _QWORD *v25; // [rsp+38h] [rbp-49h]
  void *v26; // [rsp+50h] [rbp-31h]
  void *Block[2]; // [rsp+58h] [rbp-29h] BYREF
  __m128i v28; // [rsp+68h] [rbp-19h]

  v6 = operator new(0x28u);
  v24 = (web::json::details *)v6;
  if ( v6 )
  {
    v7 = web::json::details::g_keep_json_object_unsorted;
    *(_QWORD *)v6 = &web::json::details::_Object::`vftable';
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_BYTE *)v6 + 32) = v7;
  }
  else
  {
    v6 = 0;
  }
  v26 = v6;
  web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
  if ( a3[18] )
    goto LABEL_33;
  v8 = (web::json::details *)*a3;
  if ( (_DWORD)v8 == 2 )
    goto LABEL_44;
  *(_OWORD *)Block = 0;
  v28.m128i_i64[0] = 0;
  v9 = 7;
  v28.m128i_i64[1] = 7;
  LOWORD(Block[0]) = 0;
  if ( (_DWORD)v8 != 7 )
  {
LABEL_31:
    if ( !a3[18] )
    {
      v17 = web::json::details::json_error_category(v8);
      a3[18] = 5;
      a3[19] = HIDWORD(v25);
      *((_QWORD *)a3 + 10) = v17;
    }
LABEL_33:
    v18 = operator new(8u);
    v25 = v18;
    if ( v18 )
      *v18 = &web::json::details::_Null::`vftable';
    *a2 = v18;
    if ( v6 )
      goto LABEL_36;
    return a2;
  }
  v10 = (void **)(a3 + 2);
  while ( 1 )
  {
    if ( Block == v10 )
    {
      v12 = v28;
      v11 = *(__m128i *)Block;
    }
    else
    {
      v11 = *(__m128i *)v10;
      *(_OWORD *)Block = *(_OWORD *)v10;
      v28 = *(__m128i *)(a3 + 6);
      v12 = v28;
      *((_QWORD *)a3 + 3) = 0;
      *((_QWORD *)a3 + 4) = 7;
      *(_WORD *)v10 = 0;
      v9 = _mm_srli_si128(v12, 8).m128i_u64[0];
    }
    web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
    if ( a3[18] )
      goto LABEL_49;
    if ( *a3 != 6 )
      goto LABEL_49;
    web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
    if ( a3[18] )
      goto LABEL_49;
    v13 = (__int64 *)web::json::details::JSON_Parser<unsigned short>::_ParseValue(a1, &v24, a3);
    v14 = *v13;
    *v13 = 0;
    v23 = v14;
    v15 = (__m128i *)*((_QWORD *)v6 + 2);
    if ( v15 == *((__m128i **)v6 + 3) )
    {
      std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(
        (_QWORD *)v6 + 1,
        v15,
        (__int64)Block,
        (__int64)&v23);
      v9 = v28.m128i_u64[1];
    }
    else
    {
      *v15 = v11;
      v15[1] = v12;
      v28.m128i_i64[0] = 0;
      v9 = 7;
      v28.m128i_i64[1] = 7;
      LOWORD(Block[0]) = 0;
      web::json::value::value((__m128i *)v15[2].m128i_i64, &v23);
      *((_QWORD *)v6 + 2) += 40LL;
    }
    if ( v23 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 192LL))(v23, 1);
    v8 = v24;
    if ( v24 )
      (*(void (__fastcall **)(web::json::details *, __int64))(*(_QWORD *)v24 + 192LL))(v24, 1);
    if ( a3[18] )
    {
LABEL_49:
      if ( v9 > 7 )
      {
        if ( 2 * v9 + 2 < 0x1000 )
        {
          operator delete(Block[0]);
        }
        else
        {
          v22 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v22 - 8) > 0x1F )
            goto LABEL_53;
          operator delete(v22);
        }
      }
      goto LABEL_31;
    }
    if ( *a3 == 2 )
      break;
    if ( *a3 != 5 )
      goto LABEL_49;
    web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
    if ( a3[18] )
      goto LABEL_49;
    if ( v9 > 7 )
    {
      v16 = Block[0];
      if ( 2 * v9 + 2 >= 0x1000 )
      {
        if ( (unsigned __int64)Block[0] - *((_QWORD *)Block[0] - 1) - 8 > 0x1F )
          goto LABEL_53;
        v16 = (void *)*((_QWORD *)Block[0] - 1);
      }
      operator delete(v16);
    }
    *(_OWORD *)Block = 0;
    v28.m128i_i64[0] = 0;
    v9 = 7;
    v28.m128i_i64[1] = 7;
    LOWORD(Block[0]) = 0;
    if ( *a3 != 7 )
      goto LABEL_31;
  }
  if ( v9 <= 7 )
    goto LABEL_44;
  if ( 2 * v9 + 2 < 0x1000 )
  {
    v20 = Block[0];
    goto LABEL_43;
  }
  v20 = (void *)*((_QWORD *)Block[0] - 1);
  if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
LABEL_53:
    __fastfail(5u);
LABEL_43:
  operator delete(v20);
LABEL_44:
  web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
  if ( a3[18] )
  {
    v21 = operator new(8u);
    v25 = v21;
    if ( v21 )
      *v21 = &web::json::details::_Null::`vftable';
    *a2 = v21;
    if ( v6 )
LABEL_36:
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v6 + 192LL))(v6, 1);
  }
  else
  {
    if ( !web::json::details::g_keep_json_object_unsorted )
      std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        *((_QWORD *)v6 + 1),
        *((__int128 **)v6 + 2),
        (*((_QWORD *)v6 + 2) - *((_QWORD *)v6 + 1)) / 40LL,
        (unsigned __int8 (__fastcall *)(__int128 *, __int64 *))web::json::object::compare_pairs);
    *a2 = v6;
  }
  return a2;
}

```

## disassembly

```asm
0x140009f80  mov     rax, rsp
0x140009f83  mov     [rax+20h], rbx
0x140009f87  push    rbp
0x140009f88  push    rsi
0x140009f89  push    rdi
0x140009f8a  push    r12
0x140009f8c  push    r13
0x140009f8e  push    r14
0x140009f90  push    r15
0x140009f92  lea     rbp, [rax-5Fh]
0x140009f96  sub     rsp, 0A0h
0x140009f9d  movaps  xmmword ptr [rax-48h], xmm6
0x140009fa1  movaps  xmmword ptr [rax-58h], xmm7
0x140009fa5  mov     rax, cs:__security_cookie
0x140009fac  xor     rax, rsp
0x140009faf  mov     [rbp+57h+var_60], rax
0x140009fb3  mov     rbx, r8
0x140009fb6  mov     r13, rdx
0x140009fb9  mov     r15, rcx
0x140009fbc  mov     [rbp+57h+var_A8], rdx
0x140009fc0  mov     ecx, 28h ; '('; Size
0x140009fc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009fca  mov     rsi, rax
0x140009fcd  mov     [rbp+57h+var_A8], rax
0x140009fd1  test    rax, rax
0x140009fd4  jz      short loc_14000A004
0x140009fd6  movzx   eax, cs:?g_keep_json_object_unsorted@details@json@web@@3_NA; bool web::json::details::g_keep_json_object_unsorted
0x140009fdd  lea     rcx, ??_7_Object@details@json@web@@6B@; const web::json::details::_Object::`vftable'
0x140009fe4  mov     [rsi], rcx
0x140009fe7  mov     qword ptr [rsi+8], 0
0x140009fef  mov     qword ptr [rsi+10h], 0
0x140009ff7  mov     qword ptr [rsi+18h], 0
0x140009fff  mov     [rsi+20h], al
0x14000a002  jmp     short loc_14000A006
0x14000a004  xor     esi, esi
0x14000a006  mov     [rbp+57h+var_88], rsi
0x14000a00a  mov     rdx, rbx
0x14000a00d  mov     rcx, r15
0x14000a010  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a015  cmp     dword ptr [rbx+48h], 0
0x14000a019  jnz     loc_14000A219
0x14000a01f  mov     ecx, [rbx]
0x14000a021  cmp     ecx, 2
0x14000a024  jz      loc_14000A2C8
0x14000a02a  xorps   xmm0, xmm0
0x14000a02d  movups  xmmword ptr [rbp+57h+Block], xmm0
0x14000a031  xor     edx, edx
0x14000a033  mov     qword ptr [rbp+57h+var_70], rdx
0x14000a037  mov     edi, 7
0x14000a03c  mov     qword ptr [rbp+57h+var_70+8], rdi
0x14000a040  mov     word ptr [rbp+57h+Block], dx
0x14000a044  cmp     ecx, edi
0x14000a046  jnz     loc_14000A1FD
0x14000a04c  lea     r14, [rbx+8]
0x14000a050  lea     rax, [rbp+57h+Block]
0x14000a054  cmp     rax, r14
0x14000a057  jz      short loc_14000A08A
0x14000a059  movups  xmm7, xmmword ptr [r14]
0x14000a05d  movups  xmmword ptr [rbp+57h+Block], xmm7
0x14000a061  movups  xmm6, xmmword ptr [r14+10h]
0x14000a066  movups  [rbp+57h+var_70], xmm6
0x14000a06a  mov     [r14+10h], rdx
0x14000a06e  mov     qword ptr [r14+18h], 7
0x14000a076  mov     [r14], dx
0x14000a07a  movdqa  xmm0, xmm6
0x14000a07e  psrldq  xmm0, 8
0x14000a083  movq    rdi, xmm0
0x14000a088  jmp     short loc_14000A092
0x14000a08a  movups  xmm6, [rbp+57h+var_70]
0x14000a08e  movups  xmm7, xmmword ptr [rbp+57h+Block]
0x14000a092  mov     rdx, rbx
0x14000a095  mov     rcx, r15
0x14000a098  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a09d  cmp     dword ptr [rbx+48h], 0
0x14000a0a1  jnz     loc_14000A316
0x14000a0a7  cmp     dword ptr [rbx], 6
0x14000a0aa  jnz     loc_14000A316
0x14000a0b0  mov     rdx, rbx
0x14000a0b3  mov     rcx, r15
0x14000a0b6  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a0bb  cmp     dword ptr [rbx+48h], 0
0x14000a0bf  jnz     loc_14000A316
0x14000a0c5  mov     r8, rbx
0x14000a0c8  lea     rdx, [rbp+57h+var_A8]
0x14000a0cc  mov     rcx, r15
0x14000a0cf  call    ?_ParseValue@?$JSON_Parser@G@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::_ParseValue(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a0d4  mov     rcx, rax
0x14000a0d7  mov     rax, [rax]
0x14000a0da  xor     r8d, r8d
0x14000a0dd  mov     [rcx], r8
0x14000a0e0  mov     [rbp+57h+var_B0], rax
0x14000a0e4  mov     rdx, [rsi+10h]
0x14000a0e8  cmp     rdx, [rsi+18h]
0x14000a0ec  jz      short loc_14000A11B
0x14000a0ee  movups  xmmword ptr [rdx], xmm7
0x14000a0f1  movups  xmmword ptr [rdx+10h], xmm6
0x14000a0f5  mov     qword ptr [rbp+57h+var_70], r8
0x14000a0f9  mov     edi, 7
0x14000a0fe  mov     qword ptr [rbp+57h+var_70+8], rdi
0x14000a102  mov     word ptr [rbp+57h+Block], r8w
0x14000a107  lea     rcx, [rdx+20h]
0x14000a10b  lea     rdx, [rbp+57h+var_B0]
0x14000a10f  call    ??0value@json@web@@QEAA@$$QEAV012@@Z; web::json::value::value(web::json::value &&)
0x14000a114  add     qword ptr [rsi+10h], 28h ; '('
0x14000a119  jmp     short loc_14000A130
0x14000a11b  lea     r9, [rbp+57h+var_B0]
0x14000a11f  lea     r8, [rbp+57h+Block]
0x14000a123  lea     rcx, [rsi+8]
0x14000a127  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAVvalue@json@web@@@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(std::pair<std::wstring,web::json::value> * const,std::wstring &&,web::json::value &&)
0x14000a12c  mov     rdi, qword ptr [rbp+57h+var_70+8]
0x14000a130  mov     rcx, [rbp+57h+var_B0]
0x14000a134  test    rcx, rcx
0x14000a137  jz      short loc_14000A14E
0x14000a139  mov     rax, [rcx]
0x14000a13c  mov     edx, 1
0x14000a141  mov     rax, [rax+0C0h]
0x14000a148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a14d  nop
0x14000a14e  mov     rcx, [rbp+57h+var_A8]
0x14000a152  test    rcx, rcx
0x14000a155  jz      short loc_14000A16B
0x14000a157  mov     rax, [rcx]
0x14000a15a  mov     edx, 1
0x14000a15f  mov     rax, [rax+0C0h]
0x14000a166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a16b  cmp     dword ptr [rbx+48h], 0
0x14000a16f  jnz     loc_14000A316
0x14000a175  mov     eax, [rbx]
0x14000a177  cmp     eax, 2
0x14000a17a  jz      loc_14000A28A
0x14000a180  cmp     eax, 5
0x14000a183  jnz     loc_14000A316
0x14000a189  mov     rdx, rbx
0x14000a18c  mov     rcx, r15
0x14000a18f  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a194  nop
0x14000a195  cmp     dword ptr [rbx+48h], 0
0x14000a199  jnz     loc_14000A316
0x14000a19f  cmp     rdi, 7
0x14000a1a3  jbe     short loc_14000A1DB
0x14000a1a5  lea     rdx, ds:2[rdi*2]
0x14000a1ad  mov     rcx, [rbp+57h+Block]
0x14000a1b1  cmp     rdx, 1000h
0x14000a1b8  jb      short loc_14000A1D6
0x14000a1ba  mov     rax, [rcx-8]
0x14000a1be  sub     rcx, rax
0x14000a1c1  sub     rcx, 8
0x14000a1c5  cmp     rcx, 1Fh
0x14000a1c9  ja      loc_14000A354
0x14000a1cf  add     rdx, 27h ; '''
0x14000a1d3  mov     rcx, rax; Block
0x14000a1d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000a1db  xorps   xmm0, xmm0
0x14000a1de  movups  xmmword ptr [rbp+57h+Block], xmm0
0x14000a1e2  xor     edx, edx
0x14000a1e4  mov     qword ptr [rbp+57h+var_70], rdx
0x14000a1e8  mov     edi, 7
0x14000a1ed  mov     qword ptr [rbp+57h+var_70+8], rdi
0x14000a1f1  mov     word ptr [rbp+57h+Block], dx
0x14000a1f5  cmp     [rbx], edi
0x14000a1f7  jz      loc_14000A050
0x14000a1fd  cmp     dword ptr [rbx+48h], 0
0x14000a201  jnz     short loc_14000A219
0x14000a203  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x14000a208  mov     dword ptr [rbx+48h], 5
0x14000a20f  mov     ecx, [rbp+57h+var_9C]
0x14000a212  mov     [rbx+4Ch], ecx
0x14000a215  mov     [rbx+50h], rax
0x14000a219  mov     ecx, 8; Size
0x14000a21e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a223  mov     [rbp-49h], rax
0x14000a227  test    rax, rax
0x14000a22a  jz      short loc_14000A236
0x14000a22c  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x14000a233  mov     [rax], rcx
0x14000a236  mov     [r13+0], rax
0x14000a23a  test    rsi, rsi
0x14000a23d  jz      short loc_14000A256
0x14000a23f  mov     rax, [rsi]
0x14000a242  mov     rax, [rax+0C0h]
0x14000a249  mov     edx, 1
0x14000a24e  mov     rcx, rsi
0x14000a251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a256  mov     rax, r13
0x14000a259  mov     rcx, [rbp+57h+var_60]
0x14000a25d  xor     rcx, rsp; StackCookie
0x14000a260  call    __security_check_cookie
0x14000a265  lea     r11, [rsp+0D0h+var_30]
0x14000a26d  mov     rbx, [r11+58h]
0x14000a271  movaps  xmm6, xmmword ptr [r11-10h]
0x14000a276  movaps  xmm7, xmmword ptr [r11-20h]
0x14000a27b  mov     rsp, r11
0x14000a27e  pop     r15
0x14000a280  pop     r14
0x14000a282  pop     r13
0x14000a284  pop     r12
0x14000a286  pop     rdi
0x14000a287  pop     rsi
0x14000a288  pop     rbp
0x14000a289  retn
0x14000a28a  cmp     rdi, 7
0x14000a28e  jbe     short loc_14000A2C8
0x14000a290  mov     rax, [rbp+57h+Block]
0x14000a294  lea     rdx, ds:2[rdi*2]
0x14000a29c  cmp     rdx, 1000h
0x14000a2a3  jb      short loc_14000A2C0
0x14000a2a5  mov     rcx, [rax-8]
0x14000a2a9  sub     rax, rcx
0x14000a2ac  sub     rax, 8
0x14000a2b0  cmp     rax, 1Fh
0x14000a2b4  ja      loc_14000A354
0x14000a2ba  add     rdx, 27h ; '''
0x14000a2be  jmp     short loc_14000A2C3
0x14000a2c0  mov     rcx, rax; Block
0x14000a2c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000a2c8  mov     rdx, rbx
0x14000a2cb  mov     rcx, r15
0x14000a2ce  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a2d3  cmp     dword ptr [rbx+48h], 0
0x14000a2d7  jz      loc_14000A368
0x14000a2dd  mov     ecx, 8; Size
0x14000a2e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a2e7  mov     [rbp-49h], rax
0x14000a2eb  test    rax, rax
0x14000a2ee  jz      short loc_14000A2FA
0x14000a2f0  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x14000a2f7  mov     [rax], rcx
0x14000a2fa  mov     [r13+0], rax
0x14000a2fe  test    rsi, rsi
0x14000a301  jz      loc_14000A256
0x14000a307  mov     r8, [rsi]
0x14000a30a  mov     rax, [r8+0C0h]
0x14000a311  jmp     loc_14000A249
0x14000a316  cmp     rdi, 7
0x14000a31a  jbe     loc_14000A1FD
0x14000a320  mov     rax, [rbp+57h+Block]
0x14000a324  lea     rdx, ds:2[rdi*2]
0x14000a32c  cmp     rdx, 1000h
0x14000a333  jb      short loc_14000A35B
0x14000a335  mov     rcx, [rax-8]; Block
0x14000a339  sub     rax, rcx
0x14000a33c  sub     rax, 8
0x14000a340  cmp     rax, 1Fh
0x14000a344  ja      short loc_14000A354
0x14000a346  add     rdx, 27h ; '''
0x14000a34a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000a34f  jmp     loc_14000A1FD
0x14000a354  mov     ecx, 5
0x14000a359  int     29h; Win8: RtlFailFast(ecx)
0x14000a35b  mov     rcx, rax; Block
0x14000a35e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000a363  jmp     loc_14000A1FD
0x14000a368  cmp     cs:?g_keep_json_object_unsorted@details@json@web@@3_NA, 0; bool web::json::details::g_keep_json_object_unsorted
0x14000a36f  jnz     short loc_14000A3A7
0x14000a371  mov     rcx, [rsi+8]
0x14000a375  mov     r8, [rsi+10h]
0x14000a379  sub     r8, rcx
0x14000a37c  mov     rax, 6666666666666667h
0x14000a386  imul    r8
0x14000a389  sar     rdx, 4
0x14000a38d  mov     r8, rdx
0x14000a390  shr     r8, 3Fh
0x14000a394  add     r8, rdx
0x14000a397  lea     r9, ?compare_pairs@object@json@web@@CA_NAEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@0@Z; web::json::object::compare_pairs(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)
0x14000a39e  mov     rdx, [rsi+10h]
0x14000a3a2  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z; std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,__int64,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x14000a3a7  mov     [r13+0], rsi
0x14000a3ab  jmp     loc_14000A256
```
