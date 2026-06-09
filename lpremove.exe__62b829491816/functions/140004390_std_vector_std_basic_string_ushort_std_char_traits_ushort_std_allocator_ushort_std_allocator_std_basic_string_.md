# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Emplace_reallocate<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x140004390`
- end: `0x1400045cc`
- name: `??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z`
- size: `572`
- prototype: `char *__fastcall(_QWORD *, __int64, __int128 *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14000d124`
- `0x14000e114`
- `0x14000e25c`

## callees

- `0x1400021c0`
- `0x140004390`
- `0x140005960`
- `0x14000cd48`
- `0x14000ce78`
- `0x14000ceb8`

## pseudocode

```c
char *__fastcall std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(_QWORD *a1, __int64 a2, __int128 *a3)
{
  __int64 v3; // r15
  __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // r12
  unsigned __int64 v11; // rbp
  size_t v12; // rcx
  _QWORD *v13; // rbx
  void *v14; // rax
  __int64 v15; // rdi
  char *v16; // rdx
  __int128 v17; // xmm0
  _QWORD *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rdx
  char *v23; // rcx
  _QWORD *v25; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int64 v26; // [rsp+30h] [rbp-68h]
  _QWORD *v27; // [rsp+38h] [rbp-60h]
  char *v28; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = (__int64)(a1[1] - *a1) >> 5;
  if ( v6 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<std::wstring>::_Xlength();
  v8 = (a1[2] - v3) >> 5;
  v9 = v8 >> 1;
  if ( v8 > 0x7FFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_26;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x7FFFFFFFFFFFFFFLL )
    goto LABEL_26;
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
LABEL_26:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_14:
  v25 = a1;
  v26 = v11;
  v15 = (a2 - v3) >> 5;
  v16 = (char *)&v13[4 * v15];
  v27 = v16;
  *(_OWORD *)v16 = 0;
  *((_QWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 3) = 0;
  v17 = *a3;
  v28 = v16 + 32;
  *(_OWORD *)v16 = v17;
  *((_OWORD *)v16 + 1) = a3[1];
  *((_QWORD *)a3 + 2) = 0;
  v18 = v13;
  *((_QWORD *)a3 + 3) = 7;
  *(_WORD *)a3 = 0;
  v19 = a1[1];
  v20 = *a1;
  if ( a2 == v19 )
  {
    while ( v20 != v19 )
    {
      *(_OWORD *)v18 = 0;
      v18[2] = 0;
      v18[3] = 0;
      *(_OWORD *)v18 = *(_OWORD *)v20;
      v18 += 4;
      *((_OWORD *)v18 - 1) = *(_OWORD *)(v20 + 16);
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 7;
      *(_WORD *)v20 = 0;
      v20 += 32;
    }
    v21 = 4 * v15;
  }
  else
  {
    while ( v20 != a2 )
    {
      *(_OWORD *)v18 = 0;
      v18[2] = 0;
      v18[3] = 0;
      *(_OWORD *)v18 = *(_OWORD *)v20;
      v18 += 4;
      *((_OWORD *)v18 - 1) = *(_OWORD *)(v20 + 16);
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 7;
      *(_WORD *)v20 = 0;
      v20 += 32;
    }
    v22 = a1[1];
    v21 = 4 * v15;
    v27 = v13;
    v23 = (char *)&v13[v21 + 4];
    while ( a2 != v22 )
    {
      *(_OWORD *)v23 = 0;
      *((_QWORD *)v23 + 2) = 0;
      *((_QWORD *)v23 + 3) = 0;
      *(_OWORD *)v23 = *(_OWORD *)a2;
      v23 += 32;
      *((_OWORD *)v23 - 1) = *(_OWORD *)(a2 + 16);
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 7;
      *(_WORD *)a2 = 0;
      a2 += 32;
    }
  }
  std::vector<std::wstring>::_Change_array(a1, v13, v10, v11, v25, 0, v26, v27, v28);
  std::vector<std::wstring>::_Reallocation_guard::~_Reallocation_guard(&v25);
  return (char *)&v13[v21];
}

```

## disassembly

```asm
0x140004390  push    rbx
0x140004392  push    rbp
0x140004393  push    rsi
0x140004394  push    rdi
0x140004395  push    r12
0x140004397  push    r13
0x140004399  push    r14
0x14000439b  push    r15
0x14000439d  sub     rsp, 58h
0x1400043a1  mov     r15, [rcx]
0x1400043a4  mov     rsi, rdx
0x1400043a7  mov     rdx, [rcx+8]
0x1400043ab  mov     r9, 7FFFFFFFFFFFFFFh
0x1400043b5  sub     rdx, r15
0x1400043b8  mov     r13, r8
0x1400043bb  sar     rdx, 5
0x1400043bf  mov     r14, rcx
0x1400043c2  cmp     rdx, r9
0x1400043c5  jz      loc_1400045C0
0x1400043cb  mov     rcx, [rcx+10h]
0x1400043cf  mov     rax, r9
0x1400043d2  sub     rcx, r15
0x1400043d5  sar     rcx, 5
0x1400043d9  mov     r8, rcx
0x1400043dc  shr     r8, 1
0x1400043df  sub     rax, r8
0x1400043e2  cmp     rcx, rax
0x1400043e5  ja      loc_1400045C6
0x1400043eb  lea     r12, [rdx+1]
0x1400043ef  lea     rax, [rcx+r8]
0x1400043f3  mov     rbp, r12
0x1400043f6  cmp     rax, r12
0x1400043f9  cmovnb  rbp, rax
0x1400043fd  cmp     rbp, r9
0x140004400  ja      loc_1400045C6
0x140004406  mov     rcx, rbp
0x140004409  xor     r9d, r9d
0x14000440c  shl     rcx, 5; Size
0x140004410  test    rcx, rcx
0x140004413  jnz     short loc_14000441A
0x140004415  mov     ebx, r9d
0x140004418  jmp     short loc_14000445E
0x14000441a  cmp     rcx, 1000h
0x140004421  jb      short loc_140004453
0x140004423  lea     rax, [rcx+27h]
0x140004427  cmp     rax, rcx
0x14000442a  jbe     loc_1400045C6
0x140004430  mov     rcx, rax; Size
0x140004433  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004438  xor     r9d, r9d
0x14000443b  test    rax, rax
0x14000443e  jnz     short loc_140004445
0x140004440  lea     ecx, [rax+5]
0x140004443  int     29h; Win8: RtlFailFast(ecx)
0x140004445  lea     rbx, [rax+27h]
0x140004449  and     rbx, 0FFFFFFFFFFFFFFE0h
0x14000444d  mov     [rbx-8], rax
0x140004451  jmp     short loc_14000445E
0x140004453  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004458  mov     rbx, rax
0x14000445b  xor     r9d, r9d
0x14000445e  xorps   xmm0, xmm0
0x140004461  mov     [rsp+98h+var_78], r14
0x140004466  mov     rdi, rsi
0x140004469  mov     [rsp+98h+var_68], rbp
0x14000446e  sub     rdi, r15
0x140004471  mov     r10d, 7
0x140004477  sar     rdi, 5
0x14000447b  mov     rdx, rdi
0x14000447e  shl     rdx, 5
0x140004482  add     rdx, rbx
0x140004485  mov     [rsp+98h+var_60], rdx
0x14000448a  movups  xmmword ptr [rdx], xmm0
0x14000448d  mov     [rdx+10h], r9
0x140004491  lea     rcx, [rdx+20h]
0x140004495  mov     [rdx+18h], r9
0x140004499  movups  xmm0, xmmword ptr [r13+0]
0x14000449e  mov     [rsp+98h+var_58], rcx
0x1400044a3  movups  xmmword ptr [rdx], xmm0
0x1400044a6  movups  xmm1, xmmword ptr [r13+10h]
0x1400044ab  movups  xmmword ptr [rdx+10h], xmm1
0x1400044af  mov     [r13+10h], r9
0x1400044b3  mov     rdx, rbx
0x1400044b6  mov     [r13+18h], r10
0x1400044ba  mov     [r13+0], r9w
0x1400044bf  mov     r8, [r14+8]
0x1400044c3  mov     rcx, [r14]
0x1400044c6  cmp     rsi, r8
0x1400044c9  jnz     short loc_14000453B
0x1400044cb  jmp     short loc_1400044FD
0x1400044cd  xorps   xmm0, xmm0
0x1400044d0  movups  xmmword ptr [rdx], xmm0
0x1400044d3  mov     [rdx+10h], r9
0x1400044d7  mov     [rdx+18h], r9
0x1400044db  movups  xmm0, xmmword ptr [rcx]
0x1400044de  movups  xmmword ptr [rdx], xmm0
0x1400044e1  lea     rdx, [rdx+20h]
0x1400044e5  movups  xmm1, xmmword ptr [rcx+10h]
0x1400044e9  movups  xmmword ptr [rdx-10h], xmm1
0x1400044ed  mov     [rcx+10h], r9
0x1400044f1  mov     [rcx+18h], r10
0x1400044f5  mov     [rcx], r9w
0x1400044f9  add     rcx, 20h ; ' '
0x1400044fd  cmp     rcx, r8
0x140004500  jnz     short loc_1400044CD
0x140004502  shl     rdi, 5
0x140004506  jmp     loc_14000458B
0x14000450b  xorps   xmm0, xmm0
0x14000450e  movups  xmmword ptr [rdx], xmm0
0x140004511  mov     [rdx+10h], r9
0x140004515  mov     [rdx+18h], r9
0x140004519  movups  xmm0, xmmword ptr [rcx]
0x14000451c  movups  xmmword ptr [rdx], xmm0
0x14000451f  lea     rdx, [rdx+20h]
0x140004523  movups  xmm1, xmmword ptr [rcx+10h]
0x140004527  movups  xmmword ptr [rdx-10h], xmm1
0x14000452b  mov     [rcx+10h], r9
0x14000452f  mov     [rcx+18h], r10
0x140004533  mov     [rcx], r9w
0x140004537  add     rcx, 20h ; ' '
0x14000453b  cmp     rcx, rsi
0x14000453e  jnz     short loc_14000450B
0x140004540  mov     rdx, [r14+8]
0x140004544  shl     rdi, 5
0x140004548  mov     [rsp+98h+var_60], rbx
0x14000454d  lea     rcx, [rdi+20h]
0x140004551  add     rcx, rbx
0x140004554  jmp     short loc_140004586
0x140004556  xorps   xmm0, xmm0
0x140004559  movups  xmmword ptr [rcx], xmm0
0x14000455c  mov     [rcx+10h], r9
0x140004560  mov     [rcx+18h], r9
0x140004564  movups  xmm0, xmmword ptr [rsi]
0x140004567  movups  xmmword ptr [rcx], xmm0
0x14000456a  lea     rcx, [rcx+20h]
0x14000456e  movups  xmm1, xmmword ptr [rsi+10h]
0x140004572  movups  xmmword ptr [rcx-10h], xmm1
0x140004576  mov     [rsi+10h], r9
0x14000457a  mov     [rsi+18h], r10
0x14000457e  mov     [rsi], r9w
0x140004582  add     rsi, 20h ; ' '
0x140004586  cmp     rsi, rdx
0x140004589  jnz     short loc_140004556
0x14000458b  mov     [rsp+98h+var_70], r9
0x140004590  mov     r8, r12
0x140004593  mov     r9, rbp
0x140004596  mov     rdx, rbx
0x140004599  mov     rcx, r14
0x14000459c  call    ?_Change_array@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXQEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K1@Z; std::vector<std::wstring>::_Change_array(std::wstring * const,unsigned __int64,unsigned __int64)
0x1400045a1  lea     rcx, [rsp+98h+var_78]
0x1400045a6  call    ??1_Reallocation_guard@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::_Reallocation_guard::~_Reallocation_guard(void)
0x1400045ab  lea     rax, [rbx+rdi]
0x1400045af  add     rsp, 58h
0x1400045b3  pop     r15
0x1400045b5  pop     r14
0x1400045b7  pop     r13
0x1400045b9  pop     r12
0x1400045bb  pop     rdi
0x1400045bc  pop     rsi
0x1400045bd  pop     rbp
0x1400045be  pop     rbx
0x1400045bf  retn
0x1400045c0  call    ?_Xlength@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@CAXXZ; std::vector<std::wstring>::_Xlength(void)
0x1400045c6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
