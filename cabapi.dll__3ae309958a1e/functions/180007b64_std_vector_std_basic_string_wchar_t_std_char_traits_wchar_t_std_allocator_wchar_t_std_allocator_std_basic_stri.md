# std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180007b64`
- end: `0x180007db7`
- name: `??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z`
- size: `595`
- prototype: `char *__fastcall(__int64 *, __int64, __int64)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180008d80`
- `0x180009b60`
- `0x18000b84c`
- `0x18000e2fc`
- `0x180010124`

## callees

- `0x180001570`
- `0x180003930`
- `0x18000668c`
- `0x180006764`
- `0x1800067a4`
- `0x180007b64`
- `0x180007fd0`

## pseudocode

```c
char *__fastcall std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // r12
  unsigned __int64 v11; // rbp
  size_t v12; // rcx
  _QWORD *v13; // rsi
  void *v14; // rax
  __int64 v15; // rdi
  char *v16; // rbx
  __int64 v17; // r9
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rdx
  char *v22; // rcx
  _QWORD v24[2]; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v25; // [rsp+30h] [rbp-58h]
  _QWORD *v26; // [rsp+38h] [rbp-50h]
  char *v27; // [rsp+40h] [rbp-48h]
  __int64 v28; // [rsp+48h] [rbp-40h]

  v28 = -2;
  v6 = *a1;
  v7 = (a1[1] - *a1) >> 5;
  if ( v7 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<wchar_t>::_Xlength();
  v8 = (a1[2] - v6) >> 5;
  v9 = v8 >> 1;
  if ( v8 > 0x7FFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_25;
  v10 = v7 + 1;
  v11 = v7 + 1;
  if ( v9 + v8 >= v7 + 1 )
    v11 = v9 + v8;
  if ( v11 > 0x7FFFFFFFFFFFFFFLL )
    goto LABEL_25;
  v12 = 32 * v11;
  if ( !(32 * v11) )
  {
    v13 = 0;
    goto LABEL_14;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_14;
  }
  if ( v12 + 39 < v12 )
LABEL_25:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_14:
  v15 = (a2 - v6) >> 5;
  v16 = (char *)&v13[4 * v15];
  v24[0] = a1;
  v24[1] = v13;
  v25 = v11;
  v27 = v16 + 32;
  std::wstring::wstring(v16, a3);
  v26 = v16;
  v17 = a1[1];
  v18 = v13;
  v19 = *a1;
  if ( a2 == v17 )
  {
    for ( ; v19 != v17; v19 += 32 )
    {
      *(_OWORD *)v18 = 0;
      v18[2] = 0;
      v18[3] = 0;
      *(_OWORD *)v18 = *(_OWORD *)v19;
      *((_OWORD *)v18 + 1) = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
      v18 += 4;
    }
    v20 = 4 * v15;
  }
  else
  {
    while ( v19 != a2 )
    {
      *(_OWORD *)v18 = 0;
      v18[2] = 0;
      v18[3] = 0;
      *(_OWORD *)v18 = *(_OWORD *)v19;
      *((_OWORD *)v18 + 1) = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
      v18 += 4;
      v19 += 32;
    }
    v26 = v13;
    v20 = 4 * v15;
    v21 = a1[1];
    v22 = (char *)&v13[v20 + 4];
    while ( a2 != v21 )
    {
      *(_OWORD *)v22 = 0;
      *((_QWORD *)v22 + 2) = 0;
      *((_QWORD *)v22 + 3) = 0;
      *(_OWORD *)v22 = *(_OWORD *)a2;
      *((_OWORD *)v22 + 1) = *(_OWORD *)(a2 + 16);
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 7;
      *(_WORD *)a2 = 0;
      v22 += 32;
      a2 += 32;
    }
  }
  std::vector<std::wstring>::_Change_array(a1, v13, v10, v11, v24[0], 0, v25, v26, v27, v28);
  std::vector<std::wstring>::_Reallocation_guard::~_Reallocation_guard(v24);
  return (char *)&v13[v20];
}

```

## disassembly

```asm
0x180007b64  mov     rax, rsp
0x180007b67  push    rbp
0x180007b68  push    rsi
0x180007b69  push    rdi
0x180007b6a  push    r12
0x180007b6c  push    r13
0x180007b6e  push    r14
0x180007b70  push    r15
0x180007b72  sub     rsp, 50h
0x180007b76  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x180007b7e  mov     [rax+20h], rbx
0x180007b82  mov     r13, r8
0x180007b85  mov     r14, rdx
0x180007b88  mov     r15, rcx
0x180007b8b  mov     rbx, [rcx]
0x180007b8e  mov     rdx, [rcx+8]
0x180007b92  sub     rdx, rbx
0x180007b95  sar     rdx, 5
0x180007b99  mov     r9, 7FFFFFFFFFFFFFFh
0x180007ba3  cmp     rdx, r9
0x180007ba6  jz      loc_180007DAB
0x180007bac  mov     rcx, [rcx+10h]
0x180007bb0  sub     rcx, rbx
0x180007bb3  sar     rcx, 5
0x180007bb7  mov     r8, rcx
0x180007bba  shr     r8, 1
0x180007bbd  mov     rax, r9
0x180007bc0  sub     rax, r8
0x180007bc3  cmp     rcx, rax
0x180007bc6  ja      loc_180007DB1
0x180007bcc  lea     r12, [rdx+1]
0x180007bd0  lea     rax, [r8+rcx]
0x180007bd4  mov     rbp, r12
0x180007bd7  cmp     rax, r12
0x180007bda  cmovnb  rbp, rax
0x180007bde  cmp     rbp, r9
0x180007be1  ja      loc_180007DB1
0x180007be7  mov     rcx, rbp
0x180007bea  shl     rcx, 5; Size
0x180007bee  test    rcx, rcx
0x180007bf1  jnz     short loc_180007BF7
0x180007bf3  xor     esi, esi
0x180007bf5  jmp     short loc_180007C35
0x180007bf7  cmp     rcx, 1000h
0x180007bfe  jb      short loc_180007C2D
0x180007c00  lea     rax, [rcx+27h]
0x180007c04  cmp     rax, rcx
0x180007c07  jbe     loc_180007DB1
0x180007c0d  mov     rcx, rax; Size
0x180007c10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c15  test    rax, rax
0x180007c18  jnz     short loc_180007C1F
0x180007c1a  lea     ecx, [rax+5]
0x180007c1d  int     29h; Win8: RtlFailFast(ecx)
0x180007c1f  lea     rsi, [rax+27h]
0x180007c23  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180007c27  mov     [rsi-8], rax
0x180007c2b  jmp     short loc_180007C35
0x180007c2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c32  mov     rsi, rax
0x180007c35  mov     rdi, r14
0x180007c38  sub     rdi, rbx
0x180007c3b  sar     rdi, 5
0x180007c3f  mov     rbx, rdi
0x180007c42  shl     rbx, 5
0x180007c46  add     rbx, rsi
0x180007c49  lea     rcx, [rbx+20h]
0x180007c4d  mov     [rsp+88h+var_68], r15
0x180007c52  mov     [rsp+88h+var_60], rsi
0x180007c57  mov     [rsp+88h+var_58], rbp
0x180007c5c  mov     [rsp+88h+var_50], rcx
0x180007c61  mov     [rsp+88h+var_48], rcx
0x180007c66  mov     rdx, r13
0x180007c69  mov     rcx, rbx
0x180007c6c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007c71  mov     [rsp+88h+var_50], rbx
0x180007c76  mov     r9, [r15+8]
0x180007c7a  mov     rdx, rsi
0x180007c7d  mov     rcx, [r15]
0x180007c80  cmp     r14, r9
0x180007c83  jnz     short loc_180007CDB
0x180007c85  cmp     rcx, r9
0x180007c88  jz      short loc_180007CD2
0x180007c8a  mov     r8d, 7
0x180007c90  xorps   xmm0, xmm0
0x180007c93  movups  xmmword ptr [rdx], xmm0
0x180007c96  mov     qword ptr [rdx+10h], 0
0x180007c9e  mov     qword ptr [rdx+18h], 0
0x180007ca6  movups  xmm0, xmmword ptr [rcx]
0x180007ca9  movups  xmmword ptr [rdx], xmm0
0x180007cac  movups  xmm1, xmmword ptr [rcx+10h]
0x180007cb0  movups  xmmword ptr [rdx+10h], xmm1
0x180007cb4  mov     qword ptr [rcx+10h], 0
0x180007cbc  mov     [rcx+18h], r8
0x180007cc0  xor     eax, eax
0x180007cc2  mov     [rcx], ax
0x180007cc5  lea     rdx, [rdx+20h]
0x180007cc9  add     rcx, 20h ; ' '
0x180007ccd  cmp     rcx, r9
0x180007cd0  jnz     short loc_180007C90
0x180007cd2  shl     rdi, 5
0x180007cd6  jmp     loc_180007D68
0x180007cdb  mov     r8d, 7
0x180007ce1  xor     r9d, r9d
0x180007ce4  cmp     rcx, r14
0x180007ce7  jz      short loc_180007D1B
0x180007ce9  xorps   xmm0, xmm0
0x180007cec  movups  xmmword ptr [rdx], xmm0
0x180007cef  mov     [rdx+10h], r9
0x180007cf3  mov     [rdx+18h], r9
0x180007cf7  movups  xmm0, xmmword ptr [rcx]
0x180007cfa  movups  xmmword ptr [rdx], xmm0
0x180007cfd  movups  xmm1, xmmword ptr [rcx+10h]
0x180007d01  movups  xmmword ptr [rdx+10h], xmm1
0x180007d05  mov     [rcx+10h], r9
0x180007d09  mov     [rcx+18h], r8
0x180007d0d  mov     [rcx], r9w
0x180007d11  lea     rdx, [rdx+20h]
0x180007d15  add     rcx, 20h ; ' '
0x180007d19  jmp     short loc_180007CE4
0x180007d1b  mov     [rsp+88h+var_50], rsi
0x180007d20  shl     rdi, 5
0x180007d24  mov     rdx, [r15+8]
0x180007d28  lea     rcx, [rdi+20h]
0x180007d2c  add     rcx, rsi
0x180007d2f  jmp     short loc_180007D63
0x180007d31  xorps   xmm0, xmm0
0x180007d34  movups  xmmword ptr [rcx], xmm0
0x180007d37  mov     [rcx+10h], r9
0x180007d3b  mov     [rcx+18h], r9
0x180007d3f  movups  xmm0, xmmword ptr [r14]
0x180007d43  movups  xmmword ptr [rcx], xmm0
0x180007d46  movups  xmm1, xmmword ptr [r14+10h]
0x180007d4b  movups  xmmword ptr [rcx+10h], xmm1
0x180007d4f  mov     [r14+10h], r9
0x180007d53  mov     [r14+18h], r8
0x180007d57  mov     [r14], r9w
0x180007d5b  lea     rcx, [rcx+20h]
0x180007d5f  add     r14, 20h ; ' '
0x180007d63  cmp     r14, rdx
0x180007d66  jnz     short loc_180007D31
0x180007d68  mov     [rsp+88h+var_60], 0
0x180007d71  mov     r9, rbp
0x180007d74  mov     r8, r12
0x180007d77  mov     rdx, rsi
0x180007d7a  mov     rcx, r15
0x180007d7d  call    ?_Change_array@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXQEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_K1@Z; std::vector<std::wstring>::_Change_array(std::wstring * const,unsigned __int64,unsigned __int64)
0x180007d82  lea     rbx, [rdi+rsi]
0x180007d86  lea     rcx, [rsp+88h+var_68]
0x180007d8b  call    ??1_Reallocation_guard@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::_Reallocation_guard::~_Reallocation_guard(void)
0x180007d90  mov     rax, rbx
0x180007d93  mov     rbx, [rsp+88h+arg_18]
0x180007d9b  add     rsp, 50h
0x180007d9f  pop     r15
0x180007da1  pop     r14
0x180007da3  pop     r13
0x180007da5  pop     r12
0x180007da7  pop     rdi
0x180007da8  pop     rsi
0x180007da9  pop     rbp
0x180007daa  retn
0x180007dab  call    ?_Xlength@?$vector@_WV?$allocator@_W@std@@@std@@CAXXZ; std::vector<wchar_t>::_Xlength(void)
0x180007db1  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
