# std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>>::_Iput(std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>,std::ios_base &,wchar_t,char *,unsigned __int64)

- ea: `0x1400133e0`
- end: `0x140013637`
- name: `?_Iput@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@AEAVios_base@2@_WPEAD_K@Z`
- size: `599`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *, __int64, unsigned __int16, _BYTE *, size_t MaxCount)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x140013e20`
- `0x140013ee0`
- `0x1400142c0`
- `0x140014370`
- `0x140014430`

## callees

- `0x140004f2c`
- `0x14001068c`
- `0x140011030`
- `0x1400133e0`
- `0x1400136dc`
- `0x140013770`
- `0x14001384c`
- `0x140014d88`
- `0x14001cf00`
- `0x140020010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400134fe`
- `msvcrt!memmove_s` at `0x1400134fe`

## pseudocode

```c
__int64 __fastcall std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Iput(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        __int64 a4,
        unsigned __int16 a5,
        _BYTE *a6,
        size_t MaxCount)
{
  __int64 v7; // r15
  unsigned __int16 v9; // di
  size_t v10; // r14
  std::locale *v11; // rax
  __int64 v12; // rbx
  __int64 MultiByteStr; // rsi
  _BYTE *v14; // rax
  int v15; // ecx
  char *v16; // rax
  char *v17; // rdi
  char v18; // al
  size_t v19; // r15
  __int64 v20; // rbx
  __int64 v21; // rbx
  int v22; // eax
  _OWORD *v23; // rax
  __int16 v24; // ax
  __int128 v25; // xmm0
  int v26; // ecx
  __int64 v27; // rdx
  int v29[4]; // [rsp+40h] [rbp-81h] BYREF
  std::locale::facet *v30; // [rsp+50h] [rbp-71h] BYREF
  int v31[2]; // [rsp+58h] [rbp-69h]
  __int128 v32; // [rsp+60h] [rbp-61h] BYREF
  __int64 v33; // [rsp+70h] [rbp-51h]
  int v34[4]; // [rsp+78h] [rbp-49h] BYREF
  _BYTE v35[8]; // [rsp+88h] [rbp-39h] BYREF
  _QWORD v36[3]; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int64 v37; // [rsp+A8h] [rbp-19h]

  v7 = a4;
  *(_QWORD *)v29 = a4;
  v33 = a2;
  *(_QWORD *)v31 = a1;
  v9 = a5;
  v10 = MaxCount;
  v11 = (std::locale *)std::ios_base::getloc(a4, &v30);
  v12 = std::use_facet<std::numpunct<wchar_t>>(v11);
  *(_QWORD *)&v32 = v12;
  std::locale::~locale(&v30);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 24LL))(v12, v35);
  if ( ((*a6 - 43) & 0xFD) != 0 )
  {
    if ( *a6 != 48 || ((a6[1] - 88) & 0xDF) != 0 )
      MultiByteStr = 0;
    else
      MultiByteStr = 2;
  }
  else
  {
    MultiByteStr = 1;
  }
  v14 = v36;
  v15 = v36[0];
  if ( v37 >= 0x10 )
    v14 = (_BYTE *)v36[0];
  if ( *v14 != 127 )
  {
    v16 = (char *)v36;
    if ( v37 >= 0x10 )
      v16 = (char *)v36[0];
    if ( *v16 > 0 )
    {
      v17 = (char *)v36;
      if ( v37 >= 0x10 )
        v17 = (char *)v36[0];
      v18 = *v17;
      if ( *v17 != 127 )
      {
        v19 = MaxCount;
        do
        {
          if ( v18 <= 0 )
            break;
          v15 = v18;
          if ( v18 >= v19 - MultiByteStr )
            break;
          v19 -= v18;
          memmove_s(&a6[v19 + 1], v10 - v19 + 1, &a6[v19], v10 - v19 + 1);
          a6[v19] = 0;
          ++v10;
          if ( v17[1] > 0 )
            ++v17;
          v18 = *v17;
        }
        while ( *v17 != 127 );
        v7 = *(_QWORD *)v29;
      }
      v9 = a5;
    }
  }
  v20 = *(_QWORD *)(v7 + 40);
  if ( v20 <= 0 || v20 <= v10 )
    v21 = 0;
  else
    v21 = v20 - v10;
  v22 = *(_DWORD *)(v7 + 24) & 0x1C0;
  if ( v22 != 64 )
  {
    *(_OWORD *)v29 = *a3;
    if ( v22 == 256 )
    {
      v10 -= MultiByteStr;
      *(_OWORD *)v29 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putc(
                                    v31[0],
                                    (int)v34,
                                    (int)v29,
                                    (int)a6,
                                    MultiByteStr);
    }
    v23 = (_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(
                      v15,
                      (unsigned int)v34,
                      (unsigned int)v29,
                      v9,
                      v21);
    v21 = 0;
    *a3 = *v23;
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v32 + 16LL))(v32);
  v32 = *a3;
  v25 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putgrouped(v31[0], v10, v24);
  *(_QWORD *)(v7 + 40) = 0;
  v32 = v25;
  std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(v26, v33, (unsigned int)&v32, v9, v21);
  LOBYTE(v27) = 1;
  std::string::_Tidy(v35, v27, 0);
  return v33;
}

```

## disassembly

```asm
0x1400133e0  push    rbp
0x1400133e2  push    rbx
0x1400133e3  push    rsi
0x1400133e4  push    rdi
0x1400133e5  push    r12
0x1400133e7  push    r13
0x1400133e9  push    r14
0x1400133eb  push    r15
0x1400133ed  lea     rbp, [rsp-7]
0x1400133f2  sub     rsp, 0C8h
0x1400133f9  mov     rax, cs:__security_cookie
0x140013400  xor     rax, rsp
0x140013403  mov     [rbp+3Fh+var_50], rax
0x140013407  mov     r15, r9
0x14001340a  mov     qword ptr [rsp+100h+var_C0], r9
0x14001340f  mov     r13, r8
0x140013412  mov     [rbp+3Fh+var_90], rdx
0x140013416  mov     qword ptr [rbp+3Fh+var_A8], rcx
0x14001341a  movzx   edi, [rbp+3Fh+arg_20]
0x14001341e  mov     [rsp+100h+var_D0], di
0x140013423  mov     r12, [rbp+3Fh+arg_28]
0x140013427  mov     r14, [rbp+3Fh+MaxCount]
0x14001342b  lea     rdx, [rbp+3Fh+var_B0]
0x14001342f  mov     rcx, r9
0x140013432  call    ?getloc@ios_base@std@@QEBA?AVlocale@2@XZ; std::ios_base::getloc(void)
0x140013437  nop
0x140013438  mov     rcx, rax; this
0x14001343b  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<wchar_t>>(std::locale const &)
0x140013440  mov     rbx, rax
0x140013443  mov     qword ptr [rbp+3Fh+var_A0], rax
0x140013447  lea     rcx, [rbp+3Fh+var_B0]; this
0x14001344b  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x140013450  mov     rax, [rbx]
0x140013453  lea     rdx, [rbp+3Fh+var_78]
0x140013457  mov     rcx, rbx
0x14001345a  mov     rax, [rax+18h]
0x14001345e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013463  nop
0x140013464  mov     cl, [r12]
0x140013468  sub     cl, 2Bh ; '+'
0x14001346b  test    cl, 0FDh
0x14001346e  jz      short loc_14001348D
0x140013470  cmp     byte ptr [r12], 30h ; '0'
0x140013475  jnz     short loc_140013489
0x140013477  mov     al, [r12+1]
0x14001347c  sub     al, 58h ; 'X'
0x14001347e  test    al, 0DFh
0x140013480  jnz     short loc_140013489
0x140013482  mov     esi, 2
0x140013487  jmp     short loc_140013492
0x140013489  xor     esi, esi
0x14001348b  jmp     short loc_140013492
0x14001348d  mov     esi, 1
0x140013492  lea     rax, [rbp+3Fh+var_70]
0x140013496  mov     rcx, [rbp+3Fh+var_70]
0x14001349a  mov     rdx, [rbp+3Fh+var_58]
0x14001349e  cmp     rdx, 10h
0x1400134a2  cmovnb  rax, rcx
0x1400134a6  cmp     byte ptr [rax], 7Fh
0x1400134a9  jz      short loc_140013525
0x1400134ab  lea     rax, [rbp+3Fh+var_70]
0x1400134af  cmp     rdx, 10h
0x1400134b3  cmovnb  rax, rcx
0x1400134b7  cmp     byte ptr [rax], 0
0x1400134ba  jle     short loc_140013525
0x1400134bc  lea     rdi, [rbp+3Fh+var_70]
0x1400134c0  cmp     rdx, 10h
0x1400134c4  cmovnb  rdi, rcx
0x1400134c8  mov     al, [rdi]
0x1400134ca  cmp     al, 7Fh
0x1400134cc  jz      short loc_140013520
0x1400134ce  mov     r15, r14
0x1400134d1  test    al, al
0x1400134d3  jle     short loc_14001351B
0x1400134d5  movsx   rcx, al
0x1400134d9  mov     rax, r15
0x1400134dc  sub     rax, rsi
0x1400134df  cmp     rcx, rax
0x1400134e2  jnb     short loc_14001351B
0x1400134e4  sub     r15, rcx
0x1400134e7  mov     rdx, r14
0x1400134ea  sub     rdx, r15
0x1400134ed  inc     rdx; DestinationSize
0x1400134f0  lea     rbx, [r12+r15]
0x1400134f4  lea     rcx, [rbx+1]; Destination
0x1400134f8  mov     r9, rdx; SourceSize
0x1400134fb  mov     r8, rbx; Source
0x1400134fe  call    cs:__imp_memmove_s
0x140013504  mov     byte ptr [rbx], 0
0x140013507  inc     r14
0x14001350a  lea     rax, [rdi+1]
0x14001350e  cmp     byte ptr [rax], 0
0x140013511  cmovg   rdi, rax
0x140013515  mov     al, [rdi]
0x140013517  cmp     al, 7Fh
0x140013519  jnz     short loc_1400134D1
0x14001351b  mov     r15, qword ptr [rsp+100h+var_C0]
0x140013520  movzx   edi, [rsp+100h+var_D0]
0x140013525  mov     rbx, [r15+28h]
0x140013529  test    rbx, rbx
0x14001352c  jle     short loc_140013538
0x14001352e  cmp     rbx, r14
0x140013531  jbe     short loc_140013538
0x140013533  sub     rbx, r14
0x140013536  jmp     short loc_14001353A
0x140013538  xor     ebx, ebx
0x14001353a  mov     eax, [r15+18h]
0x14001353e  and     eax, 1C0h
0x140013543  cmp     eax, 40h ; '@'
0x140013546  jz      short loc_1400135A5
0x140013548  movaps  xmm0, xmmword ptr [r13+0]
0x14001354d  lea     r8, [rsp+100h+var_C0]; int
0x140013552  lea     rdx, [rbp+3Fh+var_88]; int
0x140013556  movdqa  xmmword ptr [rsp+100h+var_C0], xmm0
0x14001355c  cmp     eax, 100h
0x140013561  jnz     short loc_14001358C
0x140013563  mov     qword ptr [rsp+100h+MultiByteStr], rsi; MultiByteStr
0x140013568  mov     r9, r12; int
0x14001356b  mov     rcx, qword ptr [rbp+3Fh+var_A8]; int
0x14001356f  call    ?_Putc@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putc(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64)
0x140013574  add     r12, rsi
0x140013577  sub     r14, rsi
0x14001357a  movups  xmm0, xmmword ptr [rax]
0x14001357d  movdqu  xmmword ptr [rsp+100h+var_C0], xmm0
0x140013583  lea     r8, [rsp+100h+var_C0]
0x140013588  lea     rdx, [rbp+3Fh+var_88]
0x14001358c  mov     qword ptr [rsp+100h+MultiByteStr], rbx
0x140013591  movzx   r9d, di
0x140013595  call    ?_Rep@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@_W_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(std::ostreambuf_iterator<wchar_t>,wchar_t,unsigned __int64)
0x14001359a  movups  xmm0, xmmword ptr [rax]
0x14001359d  xor     ebx, ebx
0x14001359f  movdqu  xmmword ptr [r13+0], xmm0
0x1400135a5  mov     rcx, qword ptr [rbp+3Fh+var_A0]
0x1400135a9  mov     rax, [rcx]
0x1400135ac  mov     rax, [rax+10h]
0x1400135b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400135b5  movaps  xmm0, xmmword ptr [r13+0]
0x1400135ba  movdqa  [rbp+3Fh+var_A0], xmm0
0x1400135bf  mov     [rsp+100h+var_D8], ax; __int16
0x1400135c4  mov     qword ptr [rsp+100h+MultiByteStr], r14; MaxCount
0x1400135c9  mov     r9, r12
0x1400135cc  lea     r8, [rbp+3Fh+var_A0]
0x1400135d0  lea     rdx, [rbp+3Fh+var_88]
0x1400135d4  mov     rcx, qword ptr [rbp+3Fh+var_A8]; int
0x1400135d8  call    ?_Putgrouped@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K_W@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putgrouped(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64,wchar_t)
0x1400135dd  movups  xmm0, xmmword ptr [rax]
0x1400135e0  mov     qword ptr [r15+28h], 0
0x1400135e8  movdqa  [rbp+3Fh+var_A0], xmm0
0x1400135ed  mov     qword ptr [rsp+100h+MultiByteStr], rbx
0x1400135f2  movzx   r9d, di
0x1400135f6  lea     r8, [rbp+3Fh+var_A0]
0x1400135fa  mov     rdx, [rbp+3Fh+var_90]
0x1400135fe  call    ?_Rep@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@_W_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(std::ostreambuf_iterator<wchar_t>,wchar_t,unsigned __int64)
0x140013603  nop
0x140013604  xor     r8d, r8d
0x140013607  mov     dl, 1
0x140013609  lea     rcx, [rbp+3Fh+var_78]
0x14001360d  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140013612  nop
0x140013613  mov     rax, [rbp+3Fh+var_90]
0x140013617  mov     rcx, [rbp+3Fh+var_50]
0x14001361b  xor     rcx, rsp; StackCookie
0x14001361e  call    __security_check_cookie
0x140013623  add     rsp, 0C8h
0x14001362a  pop     r15
0x14001362c  pop     r14
0x14001362e  pop     r13
0x140013630  pop     r12
0x140013632  pop     rdi
0x140013633  pop     rsi
0x140013634  pop     rbx
0x140013635  pop     rbp
0x140013636  retn
```
