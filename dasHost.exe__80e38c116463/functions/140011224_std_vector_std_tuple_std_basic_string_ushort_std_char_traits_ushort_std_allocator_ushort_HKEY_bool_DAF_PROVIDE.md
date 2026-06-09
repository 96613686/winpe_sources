# std::vector<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>,std::allocator<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>>>::_Emplace_reallocate<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>>(std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH> * const,std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH> &&)

- ea: `0x140011224`
- end: `0x1400115a0`
- name: `??$_Emplace_reallocate@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@AEAAPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@1@QEAV21@$$QEAV21@@Z`
- size: `892`
- prototype: `char *__fastcall(void **, char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140012c08`

## callees

- `0x1400018d4`
- `0x14000190c`
- `0x1400106b4`
- `0x140011224`
- `0x140011b6c`
- `0x140014548`
- `0x1400145a0`

## pseudocode

```c
char *__fastcall std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::_Emplace_reallocate<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>(
        void **a1,
        char *a2,
        __int64 a3)
{
  _BYTE *v3; // rbp
  unsigned __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  char *v9; // r8
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // r14
  _QWORD *v13; // rbx
  void *v14; // rax
  char *v15; // rdx
  _DWORD *v16; // r10
  __int64 v17; // r9
  char *v18; // rcx
  char *v19; // r11
  char *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rsi
  char *v23; // r8
  __int64 v24; // rax
  __int64 v25; // rsi
  char *v26; // r9
  char *v27; // rcx
  __int64 v28; // rax
  char *v29; // rbp
  char *v30; // r15
  char *v31; // rcx
  unsigned __int64 v32; // rdx
  void *v33; // rax
  _QWORD v35[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v36; // [rsp+38h] [rbp-60h]
  char *v37; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 4);
  if ( v6 == 0x555555555555555LL )
    std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::_Xlength();
  v8 = 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)a1[2] - v3) >> 4);
  v9 = (char *)(v8 >> 1);
  if ( v8 > 0x555555555555555LL - (v8 >> 1) )
    goto LABEL_36;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( (unsigned __int64)&v9[v8] >= v6 + 1 )
    v11 = (unsigned __int64)&v9[v8];
  if ( v11 > 0x555555555555555LL )
    goto LABEL_36;
  v12 = 48 * v11;
  if ( !(48 * v11) )
  {
    v13 = 0;
    goto LABEL_13;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(48 * v11);
    goto LABEL_13;
  }
  if ( v12 + 39 < v12 )
LABEL_36:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    goto LABEL_31;
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_13:
  v35[2] = v11;
  v35[0] = a1;
  v15 = (char *)((unsigned __int128)((a2 - v3) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64);
  v16 = v13;
  v17 = (a2 - v3) / 48;
  v18 = (char *)&v13[6 * v17];
  v36 = v18;
  v37 = v18 + 48;
  *(_DWORD *)v18 = *(_DWORD *)a3;
  v18[4] = *(_BYTE *)(a3 + 4);
  *((_QWORD *)v18 + 1) = *(_QWORD *)(a3 + 8);
  *((_OWORD *)v18 + 1) = 0;
  *((_QWORD *)v18 + 4) = 0;
  *((_QWORD *)v18 + 5) = 0;
  *((_OWORD *)v18 + 1) = *(_OWORD *)(a3 + 16);
  *((_OWORD *)v18 + 2) = *(_OWORD *)(a3 + 32);
  *(_QWORD *)(a3 + 32) = 0;
  *(_QWORD *)(a3 + 40) = 7;
  *(_WORD *)(a3 + 16) = 0;
  v19 = (char *)a1[1];
  v20 = (char *)*a1;
  if ( a2 == v19 )
  {
    if ( v20 != v19 )
    {
      v15 = (char *)(v13 + 2);
      v9 = v20 + 16;
      do
      {
        *v16 = *(_DWORD *)v20;
        v16 += 12;
        *((_BYTE *)v16 - 44) = v20[4];
        v21 = *((_QWORD *)v20 + 1);
        v20 += 48;
        *((_QWORD *)v16 - 5) = v21;
        *(_OWORD *)v15 = 0;
        *((_QWORD *)v15 + 2) = 0;
        *((_QWORD *)v15 + 3) = 0;
        *(_OWORD *)v15 = *(_OWORD *)v9;
        v15 += 48;
        *((_OWORD *)v15 - 2) = *((_OWORD *)v9 + 1);
        *((_QWORD *)v9 + 2) = 0;
        *((_QWORD *)v9 + 3) = 7;
        *(_WORD *)v9 = 0;
        v9 += 48;
      }
      while ( v20 != v19 );
    }
    v22 = 6 * v17;
  }
  else
  {
    if ( v20 != a2 )
    {
      v15 = (char *)(v13 + 2);
      v23 = v20 + 16;
      do
      {
        *v16 = *(_DWORD *)v20;
        v16 += 12;
        *((_BYTE *)v16 - 44) = v20[4];
        v24 = *((_QWORD *)v20 + 1);
        v20 += 48;
        *((_QWORD *)v16 - 5) = v24;
        *(_OWORD *)v15 = 0;
        *((_QWORD *)v15 + 2) = 0;
        *((_QWORD *)v15 + 3) = 0;
        *(_OWORD *)v15 = *(_OWORD *)v23;
        v15 += 48;
        *((_OWORD *)v15 - 2) = *((_OWORD *)v23 + 1);
        *((_QWORD *)v23 + 2) = 0;
        *((_QWORD *)v23 + 3) = 7;
        *(_WORD *)v23 = 0;
        v23 += 48;
      }
      while ( v20 != a2 );
    }
    v25 = 3 * v17;
    v36 = v13;
    v26 = (char *)a1[1];
    v22 = 2 * v25;
    v9 = (char *)&v13[v22 + 6];
    if ( a2 != v26 )
    {
      v27 = v9 + 16;
      v15 = a2 + 16;
      do
      {
        *(_DWORD *)v9 = *(_DWORD *)a2;
        v9 += 48;
        *(v9 - 44) = a2[4];
        v28 = *((_QWORD *)a2 + 1);
        a2 += 48;
        *((_QWORD *)v9 - 5) = v28;
        *(_OWORD *)v27 = 0;
        *((_QWORD *)v27 + 2) = 0;
        *((_QWORD *)v27 + 3) = 0;
        *(_OWORD *)v27 = *(_OWORD *)v15;
        v27 += 48;
        *((_OWORD *)v27 - 2) = *((_OWORD *)v15 + 1);
        *((_QWORD *)v15 + 2) = 0;
        *((_QWORD *)v15 + 3) = 7;
        *(_WORD *)v15 = 0;
        v15 += 48;
      }
      while ( a2 != v26 );
    }
  }
  v35[1] = 0;
  v29 = (char *)*a1;
  if ( *a1 )
  {
    v30 = (char *)a1[1];
    while ( v29 != v30 )
    {
      std::wstring::~wstring(v29 + 16);
      v29 += 48;
    }
    v31 = (char *)*a1;
    v32 = 16 * (((_BYTE *)a1[2] - (_BYTE *)*a1) >> 4);
    if ( v32 < 0x1000 )
    {
      v33 = *a1;
      goto LABEL_33;
    }
    v33 = (void *)*((_QWORD *)v31 - 1);
    if ( (unsigned __int64)(v31 - (_BYTE *)v33 - 8) <= 0x1F )
    {
      v32 += 39LL;
LABEL_33:
      operator delete(v33, v32);
      goto LABEL_34;
    }
LABEL_31:
    __fastfail(5u);
  }
LABEL_34:
  *a1 = v13;
  a1[1] = &v13[6 * v10];
  a1[2] = &v13[v12 / 8];
  std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::_Reallocation_guard::~_Reallocation_guard(
    v35,
    v15,
    v9);
  return (char *)&v13[v22];
}

```

## disassembly

```asm
0x140011224  push    rbx
0x140011226  push    rbp
0x140011227  push    rsi
0x140011228  push    rdi
0x140011229  push    r12
0x14001122b  push    r13
0x14001122d  push    r14
0x14001122f  push    r15
0x140011231  sub     rsp, 58h
0x140011235  mov     rbp, [rcx]
0x140011238  mov     r15, rdx
0x14001123b  mov     rdx, [rcx+8]
0x14001123f  mov     rax, 0AAAAAAAAAAAAAAABh
0x140011249  sub     rdx, rbp
0x14001124c  mov     r9, 555555555555555h
0x140011256  sar     rdx, 4
0x14001125a  mov     r13, r8
0x14001125d  imul    rdx, rax
0x140011261  mov     rdi, rcx
0x140011264  cmp     rdx, r9
0x140011267  jz      loc_140011594
0x14001126d  mov     rcx, [rcx+10h]
0x140011271  sub     rcx, rbp
0x140011274  sar     rcx, 4
0x140011278  imul    rcx, rax
0x14001127c  mov     rax, r9
0x14001127f  mov     r8, rcx
0x140011282  shr     r8, 1
0x140011285  sub     rax, r8
0x140011288  cmp     rcx, rax
0x14001128b  ja      loc_14001159A
0x140011291  lea     r12, [rdx+1]
0x140011295  lea     rax, [rcx+r8]
0x140011299  mov     rsi, r12
0x14001129c  cmp     rax, r12
0x14001129f  cmovnb  rsi, rax
0x1400112a3  cmp     rsi, r9
0x1400112a6  ja      loc_14001159A
0x1400112ac  lea     r14, [rsi+rsi*2]
0x1400112b0  shl     r14, 4
0x1400112b4  test    r14, r14
0x1400112b7  jnz     short loc_1400112BD
0x1400112b9  xor     ebx, ebx
0x1400112bb  jmp     short loc_1400112FA
0x1400112bd  cmp     r14, 1000h
0x1400112c4  jb      short loc_1400112EF
0x1400112c6  lea     rcx, [r14+27h]; Size
0x1400112ca  cmp     rcx, r14
0x1400112cd  jbe     loc_14001159A
0x1400112d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400112d8  test    rax, rax
0x1400112db  jz      loc_140011549
0x1400112e1  lea     rbx, [rax+27h]
0x1400112e5  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1400112e9  mov     [rbx-8], rax
0x1400112ed  jmp     short loc_1400112FA
0x1400112ef  mov     rcx, r14; Size
0x1400112f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400112f7  mov     rbx, rax
0x1400112fa  mov     rcx, r15
0x1400112fd  mov     [rsp+98h+var_68], rsi
0x140011302  sub     rcx, rbp
0x140011305  mov     [rsp+98h+var_78], rdi
0x14001130a  xor     ebp, ebp
0x14001130c  mov     rax, 2AAAAAAAAAAAAAABh
0x140011316  imul    rcx
0x140011319  xorps   xmm0, xmm0
0x14001131c  lea     esi, [rbp+7]
0x14001131f  mov     r10, rbx
0x140011322  mov     r9, rdx
0x140011325  sar     r9, 3
0x140011329  mov     rcx, r9
0x14001132c  shr     rcx, 3Fh
0x140011330  add     r9, rcx
0x140011333  lea     rcx, [r9+r9*2]
0x140011337  shl     rcx, 4
0x14001133b  add     rcx, rbx
0x14001133e  mov     [rsp+98h+var_60], rcx
0x140011343  lea     rax, [rcx+30h]
0x140011347  mov     [rsp+98h+var_58], rax
0x14001134c  mov     eax, [r13+0]
0x140011350  mov     [rcx], eax
0x140011352  mov     al, [r13+4]
0x140011356  mov     [rcx+4], al
0x140011359  mov     rax, [r13+8]
0x14001135d  mov     [rcx+8], rax
0x140011361  movups  xmmword ptr [rcx+10h], xmm0
0x140011365  mov     [rcx+20h], rbp
0x140011369  mov     [rcx+28h], rbp
0x14001136d  movups  xmm0, xmmword ptr [r13+10h]
0x140011372  movups  xmmword ptr [rcx+10h], xmm0
0x140011376  movups  xmm1, xmmword ptr [r13+20h]
0x14001137b  movups  xmmword ptr [rcx+20h], xmm1
0x14001137f  mov     [r13+20h], rbp
0x140011383  mov     [r13+28h], rsi
0x140011387  mov     [r13+10h], bp
0x14001138c  mov     r11, [rdi+8]
0x140011390  mov     rcx, [rdi]
0x140011393  cmp     r15, r11
0x140011396  jnz     short loc_140011405
0x140011398  cmp     rcx, r11
0x14001139b  jz      short loc_1400113F8
0x14001139d  lea     rdx, [rbx+10h]
0x1400113a1  lea     r8, [rcx+10h]
0x1400113a5  mov     eax, [rcx]
0x1400113a7  xorps   xmm0, xmm0
0x1400113aa  mov     [r10], eax
0x1400113ad  lea     r10, [r10+30h]
0x1400113b1  mov     al, [rcx+4]
0x1400113b4  mov     [r10-2Ch], al
0x1400113b8  mov     rax, [rcx+8]
0x1400113bc  add     rcx, 30h ; '0'
0x1400113c0  mov     [r10-28h], rax
0x1400113c4  movups  xmmword ptr [rdx], xmm0
0x1400113c7  mov     [rdx+10h], rbp
0x1400113cb  mov     [rdx+18h], rbp
0x1400113cf  movups  xmm0, xmmword ptr [r8]
0x1400113d3  movups  xmmword ptr [rdx], xmm0
0x1400113d6  lea     rdx, [rdx+30h]
0x1400113da  movups  xmm1, xmmword ptr [r8+10h]
0x1400113df  movups  xmmword ptr [rdx-20h], xmm1
0x1400113e3  mov     [r8+10h], rbp
0x1400113e7  mov     [r8+18h], rsi
0x1400113eb  mov     [r8], bp
0x1400113ef  lea     r8, [r8+30h]
0x1400113f3  cmp     rcx, r11
0x1400113f6  jnz     short loc_1400113A5
0x1400113f8  lea     rsi, [r9+r9*2]
0x1400113fc  shl     rsi, 4
0x140011400  jmp     loc_1400114E0
0x140011405  cmp     rcx, r15
0x140011408  jz      short loc_140011465
0x14001140a  lea     rdx, [rbx+10h]
0x14001140e  lea     r8, [rcx+10h]
0x140011412  mov     eax, [rcx]
0x140011414  xorps   xmm0, xmm0
0x140011417  mov     [r10], eax
0x14001141a  lea     r10, [r10+30h]
0x14001141e  mov     al, [rcx+4]
0x140011421  mov     [r10-2Ch], al
0x140011425  mov     rax, [rcx+8]
0x140011429  add     rcx, 30h ; '0'
0x14001142d  mov     [r10-28h], rax
0x140011431  movups  xmmword ptr [rdx], xmm0
0x140011434  mov     [rdx+10h], rbp
0x140011438  mov     [rdx+18h], rbp
0x14001143c  movups  xmm0, xmmword ptr [r8]
0x140011440  movups  xmmword ptr [rdx], xmm0
0x140011443  lea     rdx, [rdx+30h]
0x140011447  movups  xmm1, xmmword ptr [r8+10h]
0x14001144c  movups  xmmword ptr [rdx-20h], xmm1
0x140011450  mov     [r8+10h], rbp
0x140011454  mov     [r8+18h], rsi
0x140011458  mov     [r8], bp
0x14001145c  lea     r8, [r8+30h]
0x140011460  cmp     rcx, r15
0x140011463  jnz     short loc_140011412
0x140011465  lea     rsi, [r9+r9*2]
0x140011469  mov     [rsp+98h+var_60], rbx
0x14001146e  mov     r9, [rdi+8]
0x140011472  shl     rsi, 4
0x140011476  lea     r8, [rsi+30h]
0x14001147a  add     r8, rbx
0x14001147d  cmp     r15, r9
0x140011480  jz      short loc_1400114E0
0x140011482  lea     rcx, [r8+10h]
0x140011486  lea     rdx, [r15+10h]
0x14001148a  mov     eax, [r15]
0x14001148d  xorps   xmm0, xmm0
0x140011490  mov     [r8], eax
0x140011493  lea     r8, [r8+30h]
0x140011497  mov     al, [r15+4]
0x14001149b  mov     [r8-2Ch], al
0x14001149f  mov     rax, [r15+8]
0x1400114a3  add     r15, 30h ; '0'
0x1400114a7  mov     [r8-28h], rax
0x1400114ab  movups  xmmword ptr [rcx], xmm0
0x1400114ae  mov     [rcx+10h], rbp
0x1400114b2  mov     [rcx+18h], rbp
0x1400114b6  movups  xmm0, xmmword ptr [rdx]
0x1400114b9  movups  xmmword ptr [rcx], xmm0
0x1400114bc  lea     rcx, [rcx+30h]
0x1400114c0  movups  xmm1, xmmword ptr [rdx+10h]
0x1400114c4  movups  xmmword ptr [rcx-20h], xmm1
0x1400114c8  mov     [rdx+10h], rbp
0x1400114cc  mov     qword ptr [rdx+18h], 7
0x1400114d4  mov     [rdx], bp
0x1400114d7  lea     rdx, [rdx+30h]
0x1400114db  cmp     r15, r9
0x1400114de  jnz     short loc_14001148A
0x1400114e0  mov     [rsp+98h+var_70], rbp
0x1400114e5  mov     rbp, [rdi]
0x1400114e8  test    rbp, rbp
0x1400114eb  jz      short loc_14001155B
0x1400114ed  mov     r15, [rdi+8]
0x1400114f1  jmp     short loc_140011500
0x1400114f3  lea     rcx, [rbp+10h]
0x1400114f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400114fc  add     rbp, 30h ; '0'
0x140011500  cmp     rbp, r15
0x140011503  jnz     short loc_1400114F3
0x140011505  mov     rcx, [rdi]
0x140011508  mov     rdx, 0AAAAAAAAAAAAAAABh
0x140011512  mov     rax, [rdi+10h]
0x140011516  sub     rax, rcx
0x140011519  sar     rax, 4
0x14001151d  imul    rax, rdx
0x140011521  lea     rdx, [rax+rax*2]
0x140011525  shl     rdx, 4; unsigned __int64
0x140011529  cmp     rdx, 1000h
0x140011530  jb      short loc_140011550
0x140011532  mov     rax, [rcx-8]
0x140011536  sub     rcx, rax
0x140011539  sub     rcx, 8
0x14001153d  cmp     rcx, 1Fh
0x140011541  ja      short loc_140011549
0x140011543  add     rdx, 27h ; '''
0x140011547  jmp     short loc_140011553
0x140011549  mov     ecx, 5
0x14001154e  int     29h; Win8: RtlFailFast(ecx)
0x140011550  mov     rax, rcx
0x140011553  mov     rcx, rax; void *
0x140011556  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001155b  mov     [rdi], rbx
0x14001155e  lea     rax, [r12+r12*2]
0x140011562  shl     rax, 4
0x140011566  lea     rcx, [rsp+98h+var_78]
0x14001156b  add     rax, rbx
0x14001156e  mov     [rdi+8], rax
0x140011572  lea     rax, [r14+rbx]
0x140011576  mov     [rdi+10h], rax
0x14001157a  call    ??1_Reallocation_guard@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@QEAA@XZ; std::vector<std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH>>::_Reallocation_guard::~_Reallocation_guard(void)
0x14001157f  lea     rax, [rsi+rbx]
0x140011583  add     rsp, 58h
0x140011587  pop     r15
0x140011589  pop     r14
0x14001158b  pop     r13
0x14001158d  pop     r12
0x14001158f  pop     rdi
0x140011590  pop     rsi
0x140011591  pop     rbp
0x140011592  pop     rbx
0x140011593  retn
0x140011594  call    ?_Xlength@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@CAXXZ; std::vector<std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH>>::_Xlength(void)
0x14001159a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
