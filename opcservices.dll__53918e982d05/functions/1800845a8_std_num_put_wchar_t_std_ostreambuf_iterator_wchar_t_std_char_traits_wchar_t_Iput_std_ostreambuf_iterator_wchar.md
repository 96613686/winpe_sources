# std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>>::_Iput(std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>,std::ios_base &,wchar_t,char *,unsigned __int64)

- ea: `0x1800845a8`
- end: `0x1800848b9`
- name: `?_Iput@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@AEAVios_base@2@_WPEAD_K@Z`
- size: `785`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180084480`
- `0x1800de140`
- `0x1800de520`
- `0x1800de5d0`
- `0x1800de690`

## callees

- `0x180061600`
- `0x180062cf4`
- `0x1800845a8`
- `0x1800848c0`
- `0x180084a34`
- `0x180084ac8`
- `0x180084b50`
- `0x18008f45c`
- `0x1800cd1c4`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800847f2`
- `msvcrt!memmove_s` at `0x1800847f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_OWORD *__fastcall std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Iput(
        __int64 a1,
        _OWORD *a2,
        __int128 *a3,
        __int64 a4,
        unsigned __int16 a5,
        _BYTE *a6,
        unsigned __int64 a7)
{
  __int64 v7; // r14
  _OWORD *v9; // rdi
  _BYTE *v10; // r12
  unsigned __int64 v11; // r15
  std::locale::facet *v12; // rbx
  __int64 v13; // rsi
  struct std::locale::facet *v14; // rax
  __int64 MultiByteStr; // rsi
  void **v16; // rax
  void **v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rbx
  int v20; // eax
  __int128 v21; // xmm0
  unsigned __int16 v22; // si
  __int16 v23; // ax
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  void **v27; // rdi
  char v28; // al
  __int64 v29; // r14
  int v30; // ecx
  int v31[4]; // [rsp+40h] [rbp-71h] BYREF
  __int64 v32; // [rsp+50h] [rbp-61h] BYREF
  int v33[2]; // [rsp+58h] [rbp-59h] BYREF
  int v34[2]; // [rsp+68h] [rbp-49h]
  __int64 v35; // [rsp+70h] [rbp-41h]
  _BYTE v36[8]; // [rsp+78h] [rbp-39h] BYREF
  void *Block[3]; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int64 v38; // [rsp+98h] [rbp-19h]

  v35 = -2;
  v7 = a4;
  *(_QWORD *)v31 = a4;
  v9 = a2;
  *(_QWORD *)v33 = a2;
  *(_QWORD *)v34 = a1;
  v10 = a6;
  v11 = a7;
  v12 = **(std::locale::facet ***)(a4 + 64);
  v32 = (__int64)v12;
  std::locale::facet::_Incref(v12);
  v13 = std::use_facet<std::numpunct<wchar_t>>((std::locale *)&v32);
  v32 = v13;
  if ( v12 )
  {
    v14 = std::locale::facet::_Decref(v12);
    if ( v14 )
      (**(void (__fastcall ***)(struct std::locale::facet *, __int64))v14)(v14, 1);
  }
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 24LL))(v13, v36);
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
  v16 = Block;
  if ( v38 >= 0x10 )
    v16 = (void **)Block[0];
  if ( *(_BYTE *)v16 != 127 )
  {
    v17 = Block;
    if ( v38 >= 0x10 )
      v17 = (void **)Block[0];
    if ( *(char *)v17 > 0 )
    {
      v27 = Block;
      if ( v38 >= 0x10 )
        v27 = (void **)Block[0];
      v28 = *(_BYTE *)v27;
      if ( *(_BYTE *)v27 != 127 )
      {
        v29 = a7;
        do
        {
          if ( v28 <= 0 || v28 >= (unsigned __int64)(v29 - MultiByteStr) )
            break;
          v29 -= v28;
          memmove_s(&a6[v29 + 1], v11 - v29 + 1, &a6[v29], v11 - v29 + 1);
          a6[v29] = 0;
          ++v11;
          if ( *((char *)v27 + 1) > 0 )
            v27 = (void **)((char *)v27 + 1);
          v28 = *(_BYTE *)v27;
        }
        while ( *(_BYTE *)v27 != 127 );
        v7 = *(_QWORD *)v31;
      }
      v9 = *(_OWORD **)v33;
    }
  }
  v18 = *(_QWORD *)(v7 + 40);
  if ( v18 <= 0 || v18 <= v11 )
    v19 = 0;
  else
    v19 = v18 - v11;
  v20 = *(_DWORD *)(v7 + 24) & 0x1C0;
  if ( v20 == 64 )
  {
    v22 = a5;
  }
  else
  {
    v21 = *a3;
    if ( v20 == 256 )
    {
      *(_OWORD *)v31 = *a3;
      v10 = &a6[MultiByteStr];
      v11 -= MultiByteStr;
      *(_OWORD *)v31 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putc(
                                    v34[0],
                                    (int)v33,
                                    (int)v31,
                                    (int)a6,
                                    MultiByteStr);
      v22 = a5;
      *a3 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(
                         v30,
                         (unsigned int)v33,
                         (unsigned int)v31,
                         a5,
                         v19);
    }
    else
    {
      *(_OWORD *)v31 = *a3;
      v22 = a5;
      if ( v19 )
      {
        do
        {
          std::ostreambuf_iterator<wchar_t>::operator=(v31, a5);
          --v19;
        }
        while ( v19 );
        v21 = *(_OWORD *)v31;
      }
      *a3 = v21;
    }
    v19 = 0;
  }
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  *(_OWORD *)v31 = *a3;
  v24 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putgrouped(
                     *(_QWORD *)v34,
                     v33,
                     v31,
                     v10,
                     v11,
                     v23);
  *(_QWORD *)(v7 + 40) = 0;
  v25 = v24;
  *(_OWORD *)v31 = v24;
  if ( v19 )
  {
    do
    {
      std::ostreambuf_iterator<wchar_t>::operator=(v31, v22);
      --v19;
    }
    while ( v19 );
    v25 = *(_OWORD *)v31;
  }
  *v9 = v25;
  if ( v38 >= 0x10 )
    operator delete(Block[0]);
  return v9;
}

```

## disassembly

```asm
0x1800845a8  push    rbp
0x1800845aa  push    rbx
0x1800845ab  push    rsi
0x1800845ac  push    rdi
0x1800845ad  push    r12
0x1800845af  push    r13
0x1800845b1  push    r14
0x1800845b3  push    r15
0x1800845b5  lea     rbp, [rsp-7]
0x1800845ba  sub     rsp, 0B8h
0x1800845c1  mov     [rbp+3Fh+var_80], 0FFFFFFFFFFFFFFFEh
0x1800845c9  mov     rax, cs:__security_cookie
0x1800845d0  xor     rax, rsp
0x1800845d3  mov     [rbp+3Fh+var_50], rax
0x1800845d7  mov     r14, r9
0x1800845da  mov     qword ptr [rbp+3Fh+var_B0], r9
0x1800845de  mov     r13, r8
0x1800845e1  mov     rdi, rdx
0x1800845e4  mov     qword ptr [rbp+3Fh+var_98], rdx
0x1800845e8  mov     qword ptr [rbp+3Fh+var_88], rcx
0x1800845ec  movzx   eax, [rbp+3Fh+arg_20]
0x1800845f0  mov     [rsp+0F0h+var_C0], ax
0x1800845f5  mov     r12, [rbp+3Fh+arg_28]
0x1800845f9  mov     r15, [rbp+3Fh+arg_30]
0x1800845fd  mov     rbx, [r9+40h]
0x180084601  mov     rbx, [rbx]
0x180084604  mov     [rbp+3Fh+var_A0], rbx
0x180084608  mov     rcx, rbx; this
0x18008460b  call    ?_Incref@facet@locale@std@@QEAAXXZ; std::locale::facet::_Incref(void)
0x180084610  nop
0x180084611  lea     rcx, [rbp+3Fh+var_A0]; this
0x180084615  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<wchar_t>>(std::locale const &)
0x18008461a  mov     rsi, rax
0x18008461d  mov     [rbp+3Fh+var_A0], rax
0x180084621  test    rbx, rbx
0x180084624  jz      short loc_18008463A
0x180084626  mov     rcx, rbx; this
0x180084629  call    ?_Decref@facet@locale@std@@QEAAPEAV123@XZ; std::locale::facet::_Decref(void)
0x18008462e  mov     rcx, rax
0x180084631  test    rax, rax
0x180084634  jnz     loc_18008479B
0x18008463a  mov     rax, [rsi]
0x18008463d  lea     rdx, [rbp+3Fh+var_78]
0x180084641  mov     rcx, rsi
0x180084644  mov     rax, [rax+18h]
0x180084648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008464d  nop
0x18008464e  mov     al, [r12]
0x180084652  sub     al, 2Bh ; '+'
0x180084654  test    al, 0FDh
0x180084656  jz      loc_180084787
0x18008465c  cmp     byte ptr [r12], 30h ; '0'
0x180084661  jz      loc_180084763
0x180084667  xor     esi, esi
0x180084669  lea     rax, [rbp+3Fh+Block]
0x18008466d  mov     rcx, [rbp+3Fh+Block]
0x180084671  mov     rdx, [rbp+3Fh+var_58]
0x180084675  cmp     rdx, 10h
0x180084679  cmovnb  rax, rcx
0x18008467d  cmp     byte ptr [rax], 7Fh
0x180084680  jz      short loc_180084697
0x180084682  lea     rax, [rbp+3Fh+Block]
0x180084686  cmp     rdx, 10h
0x18008468a  cmovnb  rax, rcx
0x18008468e  cmp     byte ptr [rax], 0
0x180084691  jg      loc_1800847B0
0x180084697  mov     rbx, [r14+28h]
0x18008469b  test    rbx, rbx
0x18008469e  jg      loc_18008481C
0x1800846a4  xor     ebx, ebx
0x1800846a6  mov     eax, [r14+18h]
0x1800846aa  and     eax, 1C0h
0x1800846af  cmp     eax, 40h ; '@'
0x1800846b2  jz      loc_180084791
0x1800846b8  movaps  xmm0, xmmword ptr [r13+0]
0x1800846bd  cmp     eax, 100h
0x1800846c2  jz      loc_180084848
0x1800846c8  movaps  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x1800846cc  movzx   esi, [rsp+0F0h+var_C0]
0x1800846d1  test    rbx, rbx
0x1800846d4  jnz     loc_18008482D
0x1800846da  movdqa  xmmword ptr [r13+0], xmm0
0x1800846e0  xor     ebx, ebx
0x1800846e2  mov     rcx, [rbp+3Fh+var_A0]
0x1800846e6  mov     rax, [rcx]
0x1800846e9  mov     rax, [rax+10h]
0x1800846ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800846f2  movaps  xmm0, xmmword ptr [r13+0]
0x1800846f7  movdqa  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x1800846fc  mov     [rsp+0F0h+var_C8], ax
0x180084701  mov     qword ptr [rsp+0F0h+MultiByteStr], r15
0x180084706  mov     r9, r12
0x180084709  lea     r8, [rbp+3Fh+var_B0]
0x18008470d  lea     rdx, [rbp+3Fh+var_98]
0x180084711  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x180084715  call    ?_Putgrouped@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K_W@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putgrouped(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64,wchar_t)
0x18008471a  movups  xmm0, xmmword ptr [rax]
0x18008471d  mov     qword ptr [r14+28h], 0
0x180084725  movaps  xmm1, xmm0
0x180084728  movaps  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x18008472c  test    rbx, rbx
0x18008472f  jnz     loc_18008489D
0x180084735  movdqu  xmmword ptr [rdi], xmm1
0x180084739  cmp     [rbp+3Fh+var_58], 10h
0x18008473e  jnb     short loc_18008477C
0x180084740  mov     rax, rdi
0x180084743  mov     rcx, [rbp+3Fh+var_50]
0x180084747  xor     rcx, rsp; StackCookie
0x18008474a  call    __security_check_cookie
0x18008474f  add     rsp, 0B8h
0x180084756  pop     r15
0x180084758  pop     r14
0x18008475a  pop     r13
0x18008475c  pop     r12
0x18008475e  pop     rdi
0x18008475f  pop     rsi
0x180084760  pop     rbx
0x180084761  pop     rbp
0x180084762  retn
0x180084763  mov     al, [r12+1]
0x180084768  sub     al, 58h ; 'X'
0x18008476a  test    al, 0DFh
0x18008476c  jnz     loc_180084667
0x180084772  mov     esi, 2
0x180084777  jmp     loc_180084669
0x18008477c  mov     rcx, [rbp+3Fh+Block]; Block
0x180084780  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180084785  jmp     short loc_180084740
0x180084787  mov     esi, 1
0x18008478c  jmp     loc_180084669
0x180084791  movzx   esi, [rsp+0F0h+var_C0]
0x180084796  jmp     loc_1800846E2
0x18008479b  mov     rax, [rax]
0x18008479e  mov     edx, 1
0x1800847a3  mov     rax, [rax]
0x1800847a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800847ab  jmp     loc_18008463A
0x1800847b0  lea     rdi, [rbp+3Fh+Block]
0x1800847b4  cmp     rdx, 10h
0x1800847b8  cmovnb  rdi, rcx
0x1800847bc  mov     al, [rdi]
0x1800847be  cmp     al, 7Fh
0x1800847c0  jz      short loc_180084813
0x1800847c2  mov     r14, r15
0x1800847c5  test    al, al
0x1800847c7  jle     short loc_18008480F
0x1800847c9  movsx   rcx, al
0x1800847cd  mov     rax, r14
0x1800847d0  sub     rax, rsi
0x1800847d3  cmp     rcx, rax
0x1800847d6  jnb     short loc_18008480F
0x1800847d8  sub     r14, rcx
0x1800847db  mov     rdx, r15
0x1800847de  sub     rdx, r14
0x1800847e1  inc     rdx; DestinationSize
0x1800847e4  lea     rbx, [r12+r14]
0x1800847e8  lea     rcx, [rbx+1]; Destination
0x1800847ec  mov     r9, rdx; SourceSize
0x1800847ef  mov     r8, rbx; Source
0x1800847f2  call    cs:__imp_memmove_s
0x1800847f8  mov     byte ptr [rbx], 0
0x1800847fb  inc     r15
0x1800847fe  lea     rax, [rdi+1]
0x180084802  cmp     byte ptr [rax], 0
0x180084805  cmovg   rdi, rax
0x180084809  mov     al, [rdi]
0x18008480b  cmp     al, 7Fh
0x18008480d  jnz     short loc_1800847C5
0x18008480f  mov     r14, qword ptr [rbp+3Fh+var_B0]
0x180084813  mov     rdi, qword ptr [rbp+3Fh+var_98]
0x180084817  jmp     loc_180084697
0x18008481c  cmp     rbx, r15
0x18008481f  jbe     loc_1800846A4
0x180084825  sub     rbx, r15
0x180084828  jmp     loc_1800846A6
0x18008482d  movzx   edx, si
0x180084830  lea     rcx, [rbp+3Fh+var_B0]
0x180084834  call    ??4?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_W@Z; std::ostreambuf_iterator<wchar_t>::operator=(wchar_t)
0x180084839  sub     rbx, 1
0x18008483d  jnz     short loc_18008482D
0x18008483f  movaps  xmm0, xmmword ptr [rbp+3Fh+var_B0]
0x180084843  jmp     loc_1800846DA
0x180084848  movdqa  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x18008484d  mov     qword ptr [rsp+0F0h+MultiByteStr], rsi; MultiByteStr
0x180084852  mov     r9, r12; int
0x180084855  lea     r8, [rbp+3Fh+var_B0]; int
0x180084859  lea     rdx, [rbp+3Fh+var_98]; int
0x18008485d  mov     rcx, qword ptr [rbp+3Fh+var_88]; int
0x180084861  call    ?_Putc@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putc(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64)
0x180084866  add     r12, rsi
0x180084869  sub     r15, rsi
0x18008486c  movups  xmm0, xmmword ptr [rax]
0x18008486f  movdqu  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180084874  mov     qword ptr [rsp+0F0h+MultiByteStr], rbx
0x180084879  movzx   esi, [rsp+0F0h+var_C0]
0x18008487e  movzx   r9d, si
0x180084882  lea     r8, [rbp+3Fh+var_B0]
0x180084886  lea     rdx, [rbp+3Fh+var_98]
0x18008488a  call    ?_Rep@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@_W_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(std::ostreambuf_iterator<wchar_t>,wchar_t,unsigned __int64)
0x18008488f  movups  xmm0, xmmword ptr [rax]
0x180084892  movdqu  xmmword ptr [r13+0], xmm0
0x180084898  jmp     loc_1800846E0
0x18008489d  movzx   edx, si
0x1800848a0  lea     rcx, [rbp+3Fh+var_B0]
0x1800848a4  call    ??4?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_W@Z; std::ostreambuf_iterator<wchar_t>::operator=(wchar_t)
0x1800848a9  sub     rbx, 1
0x1800848ad  jnz     short loc_18008489D
0x1800848af  movaps  xmm1, xmmword ptr [rbp+3Fh+var_B0]
0x1800848b3  jmp     loc_180084735
```
