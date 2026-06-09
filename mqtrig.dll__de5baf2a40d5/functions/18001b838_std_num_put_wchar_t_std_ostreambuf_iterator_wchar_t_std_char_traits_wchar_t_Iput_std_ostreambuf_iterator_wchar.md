# std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>>::_Iput(std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>,std::ios_base &,wchar_t,char *,unsigned __int64)

- ea: `0x18001b838`
- end: `0x18001ba8f`
- name: `?_Iput@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@AEAVios_base@2@_WPEAD_K@Z`
- size: `599`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *, __int64, unsigned __int16, _BYTE *, size_t MaxCount)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c340`
- `0x18001c400`
- `0x18001c7e0`
- `0x18001c890`
- `0x18001c950`

## callees

- `0x18000417c`
- `0x1800180b8`
- `0x180018b34`
- `0x18001b838`
- `0x18001bb34`
- `0x18001bbc8`
- `0x18001bca4`
- `0x18001d304`
- `0x18001e380`
- `0x180022010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001b956`
- `msvcrt!memmove_s` at `0x18001b956`

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
0x18001b838  push    rbp
0x18001b83a  push    rbx
0x18001b83b  push    rsi
0x18001b83c  push    rdi
0x18001b83d  push    r12
0x18001b83f  push    r13
0x18001b841  push    r14
0x18001b843  push    r15
0x18001b845  lea     rbp, [rsp-7]
0x18001b84a  sub     rsp, 0C8h
0x18001b851  mov     rax, cs:__security_cookie
0x18001b858  xor     rax, rsp
0x18001b85b  mov     [rbp+3Fh+var_50], rax
0x18001b85f  mov     r15, r9
0x18001b862  mov     qword ptr [rsp+100h+var_C0], r9
0x18001b867  mov     r13, r8
0x18001b86a  mov     [rbp+3Fh+var_90], rdx
0x18001b86e  mov     qword ptr [rbp+3Fh+var_A8], rcx
0x18001b872  movzx   edi, [rbp+3Fh+arg_20]
0x18001b876  mov     [rsp+100h+var_D0], di
0x18001b87b  mov     r12, [rbp+3Fh+arg_28]
0x18001b87f  mov     r14, [rbp+3Fh+MaxCount]
0x18001b883  lea     rdx, [rbp+3Fh+var_B0]
0x18001b887  mov     rcx, r9
0x18001b88a  call    ?getloc@ios_base@std@@QEBA?AVlocale@2@XZ; std::ios_base::getloc(void)
0x18001b88f  nop
0x18001b890  mov     rcx, rax; this
0x18001b893  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<wchar_t>>(std::locale const &)
0x18001b898  mov     rbx, rax
0x18001b89b  mov     qword ptr [rbp+3Fh+var_A0], rax
0x18001b89f  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001b8a3  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18001b8a8  mov     rax, [rbx]
0x18001b8ab  lea     rdx, [rbp+3Fh+var_78]
0x18001b8af  mov     rcx, rbx
0x18001b8b2  mov     rax, [rax+18h]
0x18001b8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8bb  nop
0x18001b8bc  mov     cl, [r12]
0x18001b8c0  sub     cl, 2Bh ; '+'
0x18001b8c3  test    cl, 0FDh
0x18001b8c6  jz      short loc_18001B8E5
0x18001b8c8  cmp     byte ptr [r12], 30h ; '0'
0x18001b8cd  jnz     short loc_18001B8E1
0x18001b8cf  mov     al, [r12+1]
0x18001b8d4  sub     al, 58h ; 'X'
0x18001b8d6  test    al, 0DFh
0x18001b8d8  jnz     short loc_18001B8E1
0x18001b8da  mov     esi, 2
0x18001b8df  jmp     short loc_18001B8EA
0x18001b8e1  xor     esi, esi
0x18001b8e3  jmp     short loc_18001B8EA
0x18001b8e5  mov     esi, 1
0x18001b8ea  lea     rax, [rbp+3Fh+var_70]
0x18001b8ee  mov     rcx, [rbp+3Fh+var_70]
0x18001b8f2  mov     rdx, [rbp+3Fh+var_58]
0x18001b8f6  cmp     rdx, 10h
0x18001b8fa  cmovnb  rax, rcx
0x18001b8fe  cmp     byte ptr [rax], 7Fh
0x18001b901  jz      short loc_18001B97D
0x18001b903  lea     rax, [rbp+3Fh+var_70]
0x18001b907  cmp     rdx, 10h
0x18001b90b  cmovnb  rax, rcx
0x18001b90f  cmp     byte ptr [rax], 0
0x18001b912  jle     short loc_18001B97D
0x18001b914  lea     rdi, [rbp+3Fh+var_70]
0x18001b918  cmp     rdx, 10h
0x18001b91c  cmovnb  rdi, rcx
0x18001b920  mov     al, [rdi]
0x18001b922  cmp     al, 7Fh
0x18001b924  jz      short loc_18001B978
0x18001b926  mov     r15, r14
0x18001b929  test    al, al
0x18001b92b  jle     short loc_18001B973
0x18001b92d  movsx   rcx, al
0x18001b931  mov     rax, r15
0x18001b934  sub     rax, rsi
0x18001b937  cmp     rcx, rax
0x18001b93a  jnb     short loc_18001B973
0x18001b93c  sub     r15, rcx
0x18001b93f  mov     rdx, r14
0x18001b942  sub     rdx, r15
0x18001b945  inc     rdx; DestinationSize
0x18001b948  lea     rbx, [r12+r15]
0x18001b94c  lea     rcx, [rbx+1]; Destination
0x18001b950  mov     r9, rdx; SourceSize
0x18001b953  mov     r8, rbx; Source
0x18001b956  call    cs:__imp_memmove_s
0x18001b95c  mov     byte ptr [rbx], 0
0x18001b95f  inc     r14
0x18001b962  lea     rax, [rdi+1]
0x18001b966  cmp     byte ptr [rax], 0
0x18001b969  cmovg   rdi, rax
0x18001b96d  mov     al, [rdi]
0x18001b96f  cmp     al, 7Fh
0x18001b971  jnz     short loc_18001B929
0x18001b973  mov     r15, qword ptr [rsp+100h+var_C0]
0x18001b978  movzx   edi, [rsp+100h+var_D0]
0x18001b97d  mov     rbx, [r15+28h]
0x18001b981  test    rbx, rbx
0x18001b984  jle     short loc_18001B990
0x18001b986  cmp     rbx, r14
0x18001b989  jbe     short loc_18001B990
0x18001b98b  sub     rbx, r14
0x18001b98e  jmp     short loc_18001B992
0x18001b990  xor     ebx, ebx
0x18001b992  mov     eax, [r15+18h]
0x18001b996  and     eax, 1C0h
0x18001b99b  cmp     eax, 40h ; '@'
0x18001b99e  jz      short loc_18001B9FD
0x18001b9a0  movaps  xmm0, xmmword ptr [r13+0]
0x18001b9a5  lea     r8, [rsp+100h+var_C0]; int
0x18001b9aa  lea     rdx, [rbp+3Fh+var_88]; int
0x18001b9ae  movdqa  xmmword ptr [rsp+100h+var_C0], xmm0
0x18001b9b4  cmp     eax, 100h
0x18001b9b9  jnz     short loc_18001B9E4
0x18001b9bb  mov     qword ptr [rsp+100h+MultiByteStr], rsi; MultiByteStr
0x18001b9c0  mov     r9, r12; int
0x18001b9c3  mov     rcx, qword ptr [rbp+3Fh+var_A8]; int
0x18001b9c7  call    ?_Putc@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putc(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64)
0x18001b9cc  add     r12, rsi
0x18001b9cf  sub     r14, rsi
0x18001b9d2  movups  xmm0, xmmword ptr [rax]
0x18001b9d5  movdqu  xmmword ptr [rsp+100h+var_C0], xmm0
0x18001b9db  lea     r8, [rsp+100h+var_C0]
0x18001b9e0  lea     rdx, [rbp+3Fh+var_88]
0x18001b9e4  mov     qword ptr [rsp+100h+MultiByteStr], rbx
0x18001b9e9  movzx   r9d, di
0x18001b9ed  call    ?_Rep@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@_W_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(std::ostreambuf_iterator<wchar_t>,wchar_t,unsigned __int64)
0x18001b9f2  movups  xmm0, xmmword ptr [rax]
0x18001b9f5  xor     ebx, ebx
0x18001b9f7  movdqu  xmmword ptr [r13+0], xmm0
0x18001b9fd  mov     rcx, qword ptr [rbp+3Fh+var_A0]
0x18001ba01  mov     rax, [rcx]
0x18001ba04  mov     rax, [rax+10h]
0x18001ba08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba0d  movaps  xmm0, xmmword ptr [r13+0]
0x18001ba12  movdqa  [rbp+3Fh+var_A0], xmm0
0x18001ba17  mov     [rsp+100h+var_D8], ax; __int16
0x18001ba1c  mov     qword ptr [rsp+100h+MultiByteStr], r14; MaxCount
0x18001ba21  mov     r9, r12
0x18001ba24  lea     r8, [rbp+3Fh+var_A0]
0x18001ba28  lea     rdx, [rbp+3Fh+var_88]
0x18001ba2c  mov     rcx, qword ptr [rbp+3Fh+var_A8]; int
0x18001ba30  call    ?_Putgrouped@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K_W@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putgrouped(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64,wchar_t)
0x18001ba35  movups  xmm0, xmmword ptr [rax]
0x18001ba38  mov     qword ptr [r15+28h], 0
0x18001ba40  movdqa  [rbp+3Fh+var_A0], xmm0
0x18001ba45  mov     qword ptr [rsp+100h+MultiByteStr], rbx
0x18001ba4a  movzx   r9d, di
0x18001ba4e  lea     r8, [rbp+3Fh+var_A0]
0x18001ba52  mov     rdx, [rbp+3Fh+var_90]
0x18001ba56  call    ?_Rep@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@_W_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(std::ostreambuf_iterator<wchar_t>,wchar_t,unsigned __int64)
0x18001ba5b  nop
0x18001ba5c  xor     r8d, r8d
0x18001ba5f  mov     dl, 1
0x18001ba61  lea     rcx, [rbp+3Fh+var_78]
0x18001ba65  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18001ba6a  nop
0x18001ba6b  mov     rax, [rbp+3Fh+var_90]
0x18001ba6f  mov     rcx, [rbp+3Fh+var_50]
0x18001ba73  xor     rcx, rsp; StackCookie
0x18001ba76  call    __security_check_cookie
0x18001ba7b  add     rsp, 0C8h
0x18001ba82  pop     r15
0x18001ba84  pop     r14
0x18001ba86  pop     r13
0x18001ba88  pop     r12
0x18001ba8a  pop     rdi
0x18001ba8b  pop     rsi
0x18001ba8c  pop     rbx
0x18001ba8d  pop     rbp
0x18001ba8e  retn
```
