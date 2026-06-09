# RegistryHelper::ExpandName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &)

- ea: `0x180009f44`
- end: `0x18000a29b`
- name: `?ExpandName@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z`
- size: `855`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64 ***)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180008520`

## callees

- `0x1800022e0`
- `0x180003330`
- `0x1800035e6`
- `0x1800035f2`
- `0x180007720`
- `0x180007f40`
- `0x180009764`
- `0x180009cb4`
- `0x180009f44`

## pseudocode

```c
__int64 __fastcall RegistryHelper::ExpandName(__int64 a1, _QWORD *a2, __int64 ***a3)
{
  __int64 *v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rdx
  char **v7; // r8
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rsi
  char *v10; // rdi
  __int64 v11; // rax
  void **v12; // r13
  unsigned __int64 v13; // rcx
  __int64 v14; // rsi
  unsigned __int64 v15; // r12
  _QWORD *v16; // rax
  unsigned __int64 v17; // r9
  _QWORD *v18; // rax
  char *v19; // rsi
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // r8
  _QWORD *v22; // r8
  void **v23; // r10
  __int64 v24; // r12
  __int64 **v25; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v29; // [rsp+40h] [rbp-59h]
  char *v30; // [rsp+40h] [rbp-59h]
  unsigned __int64 v31; // [rsp+48h] [rbp-51h]
  unsigned __int64 v32; // [rsp+48h] [rbp-51h]
  unsigned __int64 v33; // [rsp+58h] [rbp-41h]
  char *v35[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v36; // [rsp+80h] [rbp-19h]
  unsigned __int64 v37; // [rsp+88h] [rbp-11h]
  void *Src[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v39; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v40; // [rsp+A8h] [rbp+Fh]

  v4 = **a3;
  while ( !*((_BYTE *)v4 + 25) )
  {
    std::wstring::wstring((__int64)v35, (__int64)(v4 + 4));
    std::wstring::wstring((__int64)Src, (__int64)(v4 + 8));
    v5 = 0;
    v6 = v36;
    while ( 1 )
    {
      v7 = v35;
      if ( v37 > 7 )
        v7 = (char **)v35[0];
      v8 = a2[2];
      v9 = a2[3] <= 7u ? a2 : (_QWORD *)*a2;
      if ( v6 > v8 || v5 > v8 - v6 )
        break;
      if ( v6 )
      {
        v10 = (char *)v9 + 2 * v8;
        v11 = _std_search_2((char *)v9 + 2 * v5, v10, v7, v6);
        if ( (char *)v11 == v10 )
          break;
        v5 = (v11 - (__int64)v9) >> 1;
        v6 = v36;
      }
      if ( v5 == -1 )
        break;
      v12 = Src;
      if ( v40 > 7 )
        v12 = (void **)Src[0];
      v13 = a2[2];
      v31 = v13;
      if ( v13 < v5 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v13);
      v14 = v39;
      v29 = v39;
      v15 = v13 - v5;
      if ( v13 - v5 >= v6 )
        v15 = v6;
      if ( v15 == v39 )
      {
        if ( a2[3] <= 7u )
          v16 = a2;
        else
          v16 = (_QWORD *)*a2;
        memmove_0((char *)v16 + 2 * v5, v12, 2 * v39);
      }
      else
      {
        v17 = v13 - v15 - v5;
        v33 = v17;
        if ( v39 >= v15 )
        {
          v20 = v39 - v15;
          v32 = v39 - v15;
          v21 = a2[3];
          if ( v39 - v15 > v21 - v13 )
          {
            std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,unsigned short const *,unsigned __int64>(
              a2,
              v15,
              v12,
              v39);
          }
          else
          {
            a2[2] = v13 + v20;
            if ( v21 <= 7 )
              v22 = a2;
            else
              v22 = (_QWORD *)*a2;
            v30 = (char *)v22 + 2 * v5;
            v23 = (void **)&v30[2 * v15];
            if ( (char *)v12 + 2 * v14 <= v30 || v12 > (_QWORD *)((char *)v22 + 2 * v13) )
            {
              v24 = v14;
            }
            else if ( v23 > v12 )
            {
              v24 = ((char *)v23 - (char *)v12) >> 1;
            }
            else
            {
              v24 = 0;
            }
            memmove_0((char *)v23 + 2 * v20, v23, 2 * v17 + 2);
            memmove_0(v30, v12, 2 * v24);
            memcpy_0(&v30[2 * v24], (char *)v12 + 2 * v24 + 2 * v32, 2 * (v14 - v24));
          }
        }
        else
        {
          if ( a2[3] <= 7u )
            v18 = a2;
          else
            v18 = (_QWORD *)*a2;
          v19 = (char *)v18 + 2 * v5;
          memmove_0(v19, v12, 2 * v39);
          memmove_0(&v19[2 * v29], &v19[2 * v15], 2 * v33 + 2);
          a2[2] = v29 + v31 - v15;
        }
      }
      v6 = v36;
      v5 += v36;
    }
    std::wstring::~wstring((char **)Src);
    std::wstring::~wstring(v35);
    v25 = (__int64 **)v4[2];
    if ( *((_BYTE *)v25 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v25; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *((_OWORD *)a2 + 1);
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  std::wstring::~wstring((char **)a2);
  return a1;
}

```

## disassembly

```asm
0x180009f44  mov     [rsp-8+arg_10], rbx
0x180009f49  push    rbp
0x180009f4a  push    rsi
0x180009f4b  push    rdi
0x180009f4c  push    r12
0x180009f4e  push    r13
0x180009f50  push    r14
0x180009f52  push    r15
0x180009f54  lea     rbp, [rsp-27h]
0x180009f59  sub     rsp, 0C0h
0x180009f60  mov     rax, cs:__security_cookie
0x180009f67  xor     rax, rsp
0x180009f6a  mov     [rbp+57h+var_40], rax
0x180009f6e  mov     r14, rdx
0x180009f71  mov     [rbp+57h+var_90], rcx
0x180009f75  mov     [rbp+57h+var_A8], rcx
0x180009f79  mov     [rbp+57h+var_88], rdx
0x180009f7d  xor     r12d, r12d
0x180009f80  mov     rbx, [r8]
0x180009f83  mov     rbx, [rbx]
0x180009f86  cmp     [rbx+19h], r12b
0x180009f8a  jnz     loc_18000A231
0x180009f90  lea     rdx, [rbx+20h]
0x180009f94  lea     rcx, [rbp+57h+var_80]
0x180009f98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180009f9d  nop
0x180009f9e  lea     rdx, [rbx+40h]
0x180009fa2  lea     rcx, [rbp+57h+Src]
0x180009fa6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180009fab  nop
0x180009fac  mov     r15, r12
0x180009faf  mov     rdx, [rbp+57h+var_70]
0x180009fb3  lea     r8, [rbp+57h+var_80]
0x180009fb7  cmp     [rbp+57h+var_68], 7
0x180009fbc  cmova   r8, [rbp+57h+var_80]
0x180009fc1  mov     rcx, [r14+10h]
0x180009fc5  cmp     qword ptr [r14+18h], 7
0x180009fca  jbe     short loc_180009FD1
0x180009fcc  mov     rsi, [r14]
0x180009fcf  jmp     short loc_180009FD4
0x180009fd1  mov     rsi, r14
0x180009fd4  cmp     rdx, rcx
0x180009fd7  ja      loc_18000A1D0
0x180009fdd  mov     rax, rcx
0x180009fe0  sub     rax, rdx
0x180009fe3  cmp     r15, rax
0x180009fe6  ja      loc_18000A1D0
0x180009fec  test    rdx, rdx
0x180009fef  jz      short loc_18000A01A
0x180009ff1  lea     rdi, [rsi+rcx*2]
0x180009ff5  lea     rcx, [rsi+r15*2]
0x180009ff9  mov     r9, rdx
0x180009ffc  mov     rdx, rdi
0x180009fff  call    __std_search_2
0x18000a004  mov     r15, rax
0x18000a007  cmp     rax, rdi
0x18000a00a  jz      loc_18000A1D0
0x18000a010  sub     r15, rsi
0x18000a013  sar     r15, 1
0x18000a016  mov     rdx, [rbp+57h+var_70]
0x18000a01a  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000a01e  jz      loc_18000A1D0
0x18000a024  lea     r13, [rbp+57h+Src]
0x18000a028  cmp     [rbp+57h+var_48], 7
0x18000a02d  cmova   r13, [rbp+57h+Src]
0x18000a032  mov     rcx, [r14+10h]
0x18000a036  mov     [rbp+57h+var_A8], rcx
0x18000a03a  cmp     rcx, r15
0x18000a03d  jb      loc_18000A295
0x18000a043  mov     rsi, [rbp+57h+var_50]
0x18000a047  mov     [rbp+57h+var_B0], rsi
0x18000a04b  mov     r12, rcx
0x18000a04e  sub     r12, r15
0x18000a051  cmp     r12, rdx
0x18000a054  cmovnb  r12, rdx
0x18000a058  cmp     r12, rsi
0x18000a05b  jnz     short loc_18000A081
0x18000a05d  cmp     qword ptr [r14+18h], 7
0x18000a062  jbe     short loc_18000A069
0x18000a064  mov     rax, [r14]
0x18000a067  jmp     short loc_18000A06C
0x18000a069  mov     rax, r14
0x18000a06c  lea     r8, [rsi+rsi]; Size
0x18000a070  lea     rcx, [rax+r15*2]; void *
0x18000a074  mov     rdx, r13; Src
0x18000a077  call    memmove_0
0x18000a07c  jmp     loc_18000A1C1
0x18000a081  mov     r9, rcx
0x18000a084  sub     r9, r12
0x18000a087  sub     r9, r15
0x18000a08a  mov     [rbp+57h+var_98], r9
0x18000a08e  cmp     rsi, r12
0x18000a091  jnb     short loc_18000A0E9
0x18000a093  cmp     qword ptr [r14+18h], 7
0x18000a098  jbe     short loc_18000A09F
0x18000a09a  mov     rax, [r14]
0x18000a09d  jmp     short loc_18000A0A2
0x18000a09f  mov     rax, r14
0x18000a0a2  lea     rsi, [rax+r15*2]
0x18000a0a6  mov     rax, [rbp+57h+var_B0]
0x18000a0aa  lea     rdi, [rax+rax]
0x18000a0ae  mov     r8, rdi; Size
0x18000a0b1  mov     rdx, r13; Src
0x18000a0b4  mov     rcx, rsi; void *
0x18000a0b7  call    memmove_0
0x18000a0bc  mov     r8, [rbp+57h+var_98]
0x18000a0c0  lea     r8, ds:2[r8*2]; Size
0x18000a0c8  lea     rdx, [rsi+r12*2]; Src
0x18000a0cc  lea     rcx, [rsi+rdi]; void *
0x18000a0d0  call    memmove_0
0x18000a0d5  mov     rax, [rbp+57h+var_A8]
0x18000a0d9  sub     rax, r12
0x18000a0dc  add     rax, [rbp+57h+var_B0]
0x18000a0e0  mov     [r14+10h], rax
0x18000a0e4  jmp     loc_18000A1C1
0x18000a0e9  mov     rdx, rsi
0x18000a0ec  sub     rdx, r12
0x18000a0ef  mov     [rbp+57h+var_A8], rdx
0x18000a0f3  mov     r8, [r14+18h]
0x18000a0f7  mov     rax, r8
0x18000a0fa  sub     rax, rcx
0x18000a0fd  cmp     rdx, rax
0x18000a100  ja      loc_18000A1A7
0x18000a106  lea     rax, [rcx+rdx]
0x18000a10a  mov     [r14+10h], rax
0x18000a10e  cmp     r8, 7
0x18000a112  jbe     short loc_18000A119
0x18000a114  mov     r8, [r14]
0x18000a117  jmp     short loc_18000A11C
0x18000a119  mov     r8, r14
0x18000a11c  lea     r11, [r8+r15*2]
0x18000a120  mov     [rbp+57h+var_B0], r11
0x18000a124  lea     r10, [r11+r12*2]
0x18000a128  lea     rax, ds:0[rsi*2]
0x18000a130  add     rax, r13
0x18000a133  cmp     rax, r11
0x18000a136  jbe     short loc_18000A156
0x18000a138  lea     rax, [r8+rcx*2]
0x18000a13c  cmp     r13, rax
0x18000a13f  ja      short loc_18000A156
0x18000a141  cmp     r10, r13
0x18000a144  ja      short loc_18000A14B
0x18000a146  xor     r12d, r12d
0x18000a149  jmp     short loc_18000A159
0x18000a14b  mov     r12, r10
0x18000a14e  sub     r12, r13
0x18000a151  sar     r12, 1
0x18000a154  jmp     short loc_18000A159
0x18000a156  mov     r12, rsi
0x18000a159  lea     r8, ds:2[r9*2]; Size
0x18000a161  lea     rcx, [r10+rdx*2]; void *
0x18000a165  mov     rdx, r10; Src
0x18000a168  call    memmove_0
0x18000a16d  lea     rdi, [r12+r12]
0x18000a171  mov     r8, rdi; Size
0x18000a174  mov     rdx, r13; Src
0x18000a177  mov     rcx, [rbp+57h+var_B0]; void *
0x18000a17b  call    memmove_0
0x18000a180  sub     rsi, r12
0x18000a183  lea     r8, [rsi+rsi]; Size
0x18000a187  mov     rax, [rbp+57h+var_A8]
0x18000a18b  add     rax, r12
0x18000a18e  lea     rdx, ds:0[rax*2]
0x18000a196  add     rdx, r13; Src
0x18000a199  mov     rcx, [rbp+57h+var_B0]
0x18000a19d  add     rcx, rdi; void *
0x18000a1a0  call    memcpy_0
0x18000a1a5  jmp     short loc_18000A1C1
0x18000a1a7  mov     [rsp+0F0h+var_C0], rsi; __int64
0x18000a1ac  mov     [rsp+0F0h+var_C8], r13; void *
0x18000a1b1  mov     [rsp+0F0h+var_D0], r12; __int64
0x18000a1b6  mov     r9, r15
0x18000a1b9  mov     rcx, r14; Src
0x18000a1bc  call    ??$_Reallocate_grow_by@V_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K2PEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x18000a1c1  mov     rdx, [rbp+57h+var_70]
0x18000a1c5  add     r15, rdx
0x18000a1c8  xor     r12d, r12d
0x18000a1cb  jmp     loc_180009FB3
0x18000a1d0  lea     rcx, [rbp+57h+Src]; void *
0x18000a1d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a1d9  lea     rcx, [rbp+57h+var_80]; void *
0x18000a1dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a1e2  mov     rcx, [rbx+10h]
0x18000a1e6  cmp     [rcx+19h], r12b
0x18000a1ea  jz      short loc_18000A20D
0x18000a1ec  mov     rax, [rbx+8]
0x18000a1f0  jmp     short loc_18000A1FF
0x18000a1f2  cmp     rbx, [rax+10h]
0x18000a1f6  jnz     short loc_18000A205
0x18000a1f8  mov     rbx, rax
0x18000a1fb  mov     rax, [rax+8]
0x18000a1ff  cmp     [rax+19h], r12b
0x18000a203  jz      short loc_18000A1F2
0x18000a205  mov     rbx, rax
0x18000a208  jmp     loc_180009F86
0x18000a20d  mov     rbx, rcx
0x18000a210  mov     rcx, [rcx]
0x18000a213  cmp     [rcx+19h], r12b
0x18000a217  jnz     loc_180009F86
0x18000a21d  mov     rbx, rcx
0x18000a220  mov     rax, [rcx]
0x18000a223  mov     rcx, rax
0x18000a226  cmp     [rax+19h], r12b
0x18000a22a  jz      short loc_18000A21D
0x18000a22c  jmp     loc_180009F86
0x18000a231  xorps   xmm0, xmm0
0x18000a234  mov     rdi, [rbp+57h+var_90]
0x18000a238  movups  xmmword ptr [rdi], xmm0
0x18000a23b  mov     [rdi+10h], r12
0x18000a23f  mov     [rdi+18h], r12
0x18000a243  movups  xmm0, xmmword ptr [r14]
0x18000a247  movups  xmmword ptr [rdi], xmm0
0x18000a24a  movups  xmm1, xmmword ptr [r14+10h]
0x18000a24f  movups  xmmword ptr [rdi+10h], xmm1
0x18000a253  mov     [r14+10h], r12
0x18000a257  mov     qword ptr [r14+18h], 7
0x18000a25f  mov     [r14], r12w
0x18000a263  mov     rcx, r14; void *
0x18000a266  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a26b  mov     rax, rdi
0x18000a26e  mov     rcx, [rbp+57h+var_40]
0x18000a272  xor     rcx, rsp; StackCookie
0x18000a275  call    __security_check_cookie
0x18000a27a  mov     rbx, [rsp+0F0h+arg_10]
0x18000a282  add     rsp, 0C0h
0x18000a289  pop     r15
0x18000a28b  pop     r14
0x18000a28d  pop     r13
0x18000a28f  pop     r12
0x18000a291  pop     rdi
0x18000a292  pop     rsi
0x18000a293  pop     rbp
0x18000a294  retn
0x18000a295  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
