# fsc_SetupScan(StateVars *,DWRITE_Rect const *,ushort,bool,int,int,int,RevRoots *)

- ea: `0x14000ffd0`
- end: `0x1400104af`
- name: `?fsc_SetupScan@@YAHPEAUStateVars@@PEBUDWRITE_Rect@@G_NHHHPEAURevRoots@@@Z`
- size: `1247`
- prototype: `__int64 __fastcall(struct StateVars *, const struct DWRITE_Rect *, unsigned __int16, bool, int, int, int, struct RevRoots *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x14000e540`

## callees

- `0x14000ffd0`
- `0x1400104b8`
- `0x14001057c`
- `0x140072578`
- `0x140095fa0`

## pseudocode

```c
__int64 __fastcall fsc_SetupScan(
        struct StateVars *a1,
        const struct DWRITE_Rect *a2,
        char a3,
        char a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        struct RevRoots *a8)
{
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int16 v12; // r13
  __int64 (__fastcall *v13)(); // r8
  __int16 v14; // r10
  __int64 (__fastcall *v15)(); // r9
  __int16 v16; // ax
  __int64 v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r10
  struct RevRoots *v25; // rsi
  __int16 v26; // bp
  __int64 *v27; // r8
  __int64 *v28; // r9
  __int64 *v29; // r11
  __int64 *v30; // rbx
  __int64 *i; // rdi
  __int64 v32; // rax
  __int64 v33; // r10
  unsigned int v34; // ebx
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rax
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 v51; // r8
  __int16 v52; // bp
  __int64 v53; // rsi
  __int64 *v54; // r9
  __int64 *v55; // r10
  __int64 *v56; // r11
  __int64 *v57; // rbx
  __int64 *j; // rdi
  __int64 v59; // rax
  __int16 v61; // ax
  unsigned __int64 v62; // rbx
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // rax

  v10 = *(__int16 *)a2;
  *((_DWORD *)a1 + 8) = v10;
  v11 = *((__int16 *)a2 + 2);
  *((_DWORD *)a1 + 9) = v11;
  *((_DWORD *)a1 + 6) = *((__int16 *)a2 + 1);
  *((_DWORD *)a1 + 7) = *((__int16 *)a2 + 3);
  *((_BYTE *)a1 + 240) = a4;
  v12 = a3 & 2;
  if ( (a3 & 2) != 0 || (a3 & 4) == 0 )
  {
    v13 = AddVertSimpleScan;
    v14 = 0;
    v15 = AddHorizSimpleScan;
    v16 = 1;
  }
  else
  {
    v13 = AddVertSmartScan;
    v16 = 2;
    v15 = AddHorizSmartScan;
    v14 = 1;
  }
  v17 = v10 - v11;
  *((_WORD *)a1 + 137) = v16;
  *((_WORD *)a1 + 138) = v14;
  *((_QWORD *)a1 + 22) = v15;
  *((_QWORD *)a1 + 23) = v13;
  if ( (unsigned __int64)(v17 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_54;
  if ( (int)v17 < 0 )
  {
    v17 = (unsigned int)-(int)v17;
    if ( 8 * (unsigned __int64)(unsigned int)v17 > 0x80000000 )
      goto LABEL_54;
    v18 = -8 * v17;
  }
  else
  {
    if ( 8 * (unsigned __int64)(unsigned int)v17 > 0x7FFFFFFF )
      goto LABEL_54;
    v18 = 8 * v17;
  }
  v19 = fsc_AllocHMem(a1, v18);
  *((_QWORD *)a1 + 6) = v19;
  if ( !v19 )
    return 6657;
  v20 = fsc_AllocHMem(a1, v18);
  *((_QWORD *)a1 + 7) = v20;
  if ( !v20 )
    return 6657;
  v21 = fsc_AllocHMem(a1, v18);
  *((_QWORD *)a1 + 8) = v21;
  if ( !v21 )
    return 6657;
  v22 = fsc_AllocHMem(a1, v18);
  *((_QWORD *)a1 + 9) = v22;
  if ( !v22 )
    return 6657;
  v23 = fsc_AllocHMem(a1, v18);
  *((_QWORD *)a1 + 10) = v23;
  if ( !v23 )
    return 6657;
  v11 = a5;
  *((_QWORD *)a1 + 33) = a7;
  if ( a5 > 0x7FFFFFF )
    return 6657;
  v17 = *((__int16 *)a1 + 138) + 2LL;
  if ( (unsigned __int64)(*((__int16 *)a1 + 138) + 2147483650LL) > 0xFFFFFFFF )
    goto LABEL_54;
  v24 = fsc_AllocHMem(a1, a5 << v17);
  if ( !v24 )
    return 6657;
  if ( a8 != *((struct RevRoots **)a8 + 4) )
    FixPointers(a8);
  v11 = *((unsigned int *)a1 + 9);
  v17 = (unsigned int)(v11 + 0x8000);
  if ( (unsigned int)v17 > 0xFFFF )
    goto LABEL_54;
  v25 = *(struct RevRoots **)a8;
  v26 = 0;
  v27 = (__int64 *)*((_QWORD *)a1 + 6);
  v28 = (__int64 *)*((_QWORD *)a1 + 8);
  v29 = (__int64 *)*((_QWORD *)a1 + 7);
  v30 = (__int64 *)*((_QWORD *)a1 + 9);
  for ( i = (__int64 *)*((_QWORD *)a1 + 10); ; ++i )
  {
    v17 = *((unsigned int *)a1 + 8);
    if ( (unsigned int)(v17 + 0x8000) > 0xFFFF )
      goto LABEL_54;
    if ( (__int16)v17 <= (__int16)v11 )
      break;
    for ( ; *(__int16 *)v25 <= (__int16)v11; v26 += v61 << *((_WORD *)a1 + 138) )
    {
      v61 = *((_WORD *)v25 + 1);
      v25 = (struct RevRoots *)*((_QWORD *)v25 + 1);
    }
    *v27++ = v24;
    *v28++ = v24;
    v32 = 2LL * v26;
    v33 = v32 + v24;
    *v29++ = v33;
    *v30 = v33;
    v24 = v32 + v33;
    *i = v24;
    ++v30;
    LOWORD(v11) = v11 + 1;
  }
  if ( v12 )
    return 0;
  v17 = *((__int16 *)a2 + 3) - (__int64)*((__int16 *)a2 + 1);
  if ( (unsigned __int64)(v17 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_54;
  if ( (int)v17 < 0 )
  {
    v17 = (unsigned int)(*((__int16 *)a2 + 1) - *((__int16 *)a2 + 3));
    if ( 8 * (unsigned __int64)(unsigned int)v17 > 0x80000000 )
      goto LABEL_54;
    v34 = -8 * v17;
  }
  else
  {
    if ( 8 * (unsigned __int64)(unsigned int)v17 > 0x7FFFFFFF )
      goto LABEL_54;
    v34 = 8 * v17;
  }
  v35 = fsc_AllocVMem(a1, v34, v27, v28);
  *((_QWORD *)a1 + 14) = v35;
  if ( !v35 )
    return 6657;
  v38 = fsc_AllocVMem(a1, v34, v36, v37);
  *((_QWORD *)a1 + 15) = v38;
  if ( !v38 )
    return 6657;
  v41 = fsc_AllocVMem(a1, v34, v39, v40);
  *((_QWORD *)a1 + 16) = v41;
  if ( !v41 )
    return 6657;
  v44 = fsc_AllocVMem(a1, v34, v42, v43);
  *((_QWORD *)a1 + 17) = v44;
  if ( !v44 )
    return 6657;
  v47 = fsc_AllocVMem(a1, v34, v45, v46);
  *((_QWORD *)a1 + 18) = v47;
  if ( !v47 || a6 > 0x7FFFFFF )
    return 6657;
  v17 = *((__int16 *)a1 + 138) + 2LL;
  if ( (unsigned __int64)(*((__int16 *)a1 + 138) + 2147483650LL) > 0xFFFFFFFF )
  {
LABEL_54:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v17, v11);
    __debugbreak();
  }
  v50 = fsc_AllocVMem(a1, a6 << v17, v48, v49);
  if ( v50 )
  {
    v51 = *((unsigned __int16 *)a2 + 1);
    v52 = 0;
    v53 = *((_QWORD *)a8 + 1);
    v54 = (__int64 *)*((_QWORD *)a1 + 14);
    v55 = (__int64 *)*((_QWORD *)a1 + 16);
    v56 = (__int64 *)*((_QWORD *)a1 + 15);
    v57 = (__int64 *)*((_QWORD *)a1 + 17);
    for ( j = (__int64 *)*((_QWORD *)a1 + 18); (__int16)v51 < *((__int16 *)a2 + 3); ++j )
    {
      for ( ; *(__int16 *)v53 <= (__int16)v51; v52 += v11 )
      {
        v11 = *(unsigned __int16 *)(v53 + 2);
        v53 = *(_QWORD *)(v53 + 8);
        LOWORD(v11) = (_WORD)v11 << *((_WORD *)a1 + 138);
      }
      *v54 = v50;
      LOWORD(v51) = v51 + 1;
      *v55 = v50;
      ++v54;
      ++v55;
      v17 = 2LL * v52;
      v59 = v17 + v50;
      *v56++ = v59;
      *v57 = v59;
      v50 = v17 + v59;
      *j = v50;
      ++v57;
    }
    if ( (a3 & 4) == 0 )
      return 0;
    if ( a7 < 0x10000000 )
    {
      v62 = 4LL * a7;
      if ( v62 <= 0x7FFFFFFF )
      {
        v63 = fsc_AllocVMem(a1, (unsigned int)v62, v51, v54);
        *((_QWORD *)a1 + 31) = v63;
        if ( v63 )
        {
          v66 = fsc_AllocVMem(a1, (unsigned int)v62, v64, v65);
          *((_QWORD *)a1 + 32) = v66;
          if ( v66 )
            return 0;
        }
        return 6657;
      }
      goto LABEL_54;
    }
  }
  return 6657;
}

```

## disassembly

```asm
0x14000ffd0  mov     [rsp+arg_10], r8w
0x14000ffd6  push    rsi
0x14000ffd7  push    rdi
0x14000ffd8  push    r13
0x14000ffda  push    r14
0x14000ffdc  push    r15
0x14000ffde  sub     rsp, 20h
0x14000ffe2  mov     r14, rcx
0x14000ffe5  mov     r15, rdx
0x14000ffe8  movsx   rcx, word ptr [rdx]
0x14000ffec  movzx   r13d, r8w
0x14000fff0  mov     [r14+20h], ecx
0x14000fff4  movsx   rdx, word ptr [rdx+4]
0x14000fff9  mov     [r14+24h], edx
0x14000fffd  movsx   eax, word ptr [r15+2]
0x140010002  mov     [r14+18h], eax
0x140010006  movsx   eax, word ptr [r15+6]
0x14001000b  mov     [r14+1Ch], eax
0x14001000f  mov     [r14+0F0h], r9b
0x140010016  and     r13w, 2
0x14001001b  jz      loc_14001047A
0x140010021  lea     r8, AddVertSimpleScan
0x140010028  xor     r10d, r10d
0x14001002b  lea     r9, AddHorizSimpleScan
0x140010032  mov     eax, 1
0x140010037  mov     [rsp+48h+arg_0], rbx
0x14001003c  sub     rcx, rdx
0x14001003f  mov     [rsp+48h+arg_8], rbp
0x140010044  mov     edi, 80000000h
0x140010049  mov     [rsp+48h+arg_18], r12
0x14001004e  mov     esi, 0FFFFFFFFh
0x140010053  mov     [r14+112h], ax
0x14001005b  mov     [r14+114h], r10w
0x140010063  lea     rax, [rcx+rdi]
0x140010067  mov     [r14+0B0h], r9
0x14001006e  mov     [r14+0B8h], r8
0x140010075  cmp     rax, rsi
0x140010078  ja      loc_140010474
0x14001007e  test    ecx, ecx
0x140010080  js      loc_1400103F1
0x140010086  mov     eax, ecx
0x140010088  shl     rax, 3
0x14001008c  cmp     rax, 7FFFFFFFh
0x140010092  ja      loc_140010474
0x140010098  mov     ebx, eax
0x14001009a  mov     edx, ebx
0x14001009c  mov     rcx, r14
0x14001009f  call    ?fsc_AllocHMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocHMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x1400100a4  mov     [r14+30h], rax
0x1400100a8  test    rax, rax
0x1400100ab  jz      loc_14001046A
0x1400100b1  mov     edx, ebx
0x1400100b3  mov     rcx, r14
0x1400100b6  call    ?fsc_AllocHMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocHMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x1400100bb  mov     [r14+38h], rax
0x1400100bf  test    rax, rax
0x1400100c2  jz      loc_14001046A
0x1400100c8  mov     edx, ebx
0x1400100ca  mov     rcx, r14
0x1400100cd  call    ?fsc_AllocHMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocHMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x1400100d2  mov     [r14+40h], rax
0x1400100d6  test    rax, rax
0x1400100d9  jz      loc_14001046A
0x1400100df  mov     edx, ebx
0x1400100e1  mov     rcx, r14
0x1400100e4  call    ?fsc_AllocHMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocHMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x1400100e9  mov     [r14+48h], rax
0x1400100ed  test    rax, rax
0x1400100f0  jz      loc_14001046A
0x1400100f6  mov     edx, ebx
0x1400100f8  mov     rcx, r14
0x1400100fb  call    ?fsc_AllocHMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocHMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140010100  mov     [r14+50h], rax
0x140010104  test    rax, rax
0x140010107  jz      loc_14001046A
0x14001010d  mov     edx, [rsp+48h+arg_20]
0x140010111  mov     eax, [rsp+48h+arg_30]
0x140010118  mov     dword ptr [r14+10Ch], 0
0x140010123  mov     [r14+108h], eax
0x14001012a  cmp     edx, 7FFFFFFh
0x140010130  ja      loc_14001046A
0x140010136  movsx   rcx, word ptr [r14+114h]
0x14001013e  add     rcx, 2
0x140010142  lea     rax, [rcx+rdi]
0x140010146  cmp     rax, rsi
0x140010149  ja      loc_140010474
0x14001014f  shl     edx, cl
0x140010151  mov     rcx, r14
0x140010154  call    ?fsc_AllocHMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocHMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140010159  mov     r10, rax
0x14001015c  test    rax, rax
0x14001015f  jz      loc_14001046A
0x140010165  mov     r12, [rsp+48h+arg_38]
0x14001016d  cmp     r12, [r12+20h]
0x140010172  jnz     loc_1400104A2
0x140010178  mov     edx, [r14+24h]
0x14001017c  lea     ecx, [rdx+8000h]
0x140010182  cmp     ecx, 0FFFFh
0x140010188  ja      loc_140010474
0x14001018e  mov     rsi, [r12]
0x140010192  xor     ebp, ebp
0x140010194  mov     r8, [r14+30h]
0x140010198  mov     r9, [r14+40h]
0x14001019c  mov     r11, [r14+38h]
0x1400101a0  mov     rbx, [r14+48h]
0x1400101a4  mov     rdi, [r14+50h]
0x1400101a8  nop     dword ptr [rax+rax+00000000h]
0x1400101b0  mov     ecx, [r14+20h]
0x1400101b4  lea     eax, [rcx+8000h]
0x1400101ba  cmp     eax, 0FFFFh
0x1400101bf  ja      loc_140010474
0x1400101c5  cmp     cx, dx
0x1400101c8  jle     short loc_140010208
0x1400101ca  cmp     [rsi], dx
0x1400101cd  jle     loc_1400103AE
0x1400101d3  mov     [r8], r10
0x1400101d6  add     r8, 8
0x1400101da  mov     [r9], r10
0x1400101dd  add     r9, 8
0x1400101e1  movsx   rax, bp
0x1400101e5  add     rax, rax
0x1400101e8  add     r10, rax
0x1400101eb  mov     [r11], r10
0x1400101ee  add     r11, 8
0x1400101f2  mov     [rbx], r10
0x1400101f5  add     r10, rax
0x1400101f8  mov     [rdi], r10
0x1400101fb  add     rbx, 8
0x1400101ff  add     rdi, 8
0x140010203  inc     dx
0x140010206  jmp     short loc_1400101B0
0x140010208  test    r13w, r13w
0x14001020c  jnz     loc_140010390
0x140010212  movsx   rax, word ptr [r15+2]
0x140010217  mov     esi, 80000000h
0x14001021c  movsx   rcx, word ptr [r15+6]
0x140010221  mov     ebp, 0FFFFFFFFh
0x140010226  sub     rcx, rax
0x140010229  lea     rax, [rcx+rsi]
0x14001022d  cmp     rax, rbp
0x140010230  ja      loc_140010474
0x140010236  test    ecx, ecx
0x140010238  js      loc_140010405
0x14001023e  mov     eax, ecx
0x140010240  shl     rax, 3
0x140010244  cmp     rax, 7FFFFFFFh
0x14001024a  ja      loc_140010474
0x140010250  mov     ebx, eax
0x140010252  mov     edi, [rsp+48h+arg_28]
0x140010256  mov     edx, ebx
0x140010258  mov     rcx, r14
0x14001025b  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140010260  mov     [r14+70h], rax
0x140010264  test    rax, rax
0x140010267  jz      loc_14001046A
0x14001026d  mov     edx, ebx
0x14001026f  mov     rcx, r14
0x140010272  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140010277  mov     [r14+78h], rax
0x14001027b  test    rax, rax
0x14001027e  jz      loc_14001046A
0x140010284  mov     edx, ebx
0x140010286  mov     rcx, r14
0x140010289  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x14001028e  mov     [r14+80h], rax
0x140010295  test    rax, rax
0x140010298  jz      loc_14001046A
0x14001029e  mov     edx, ebx
0x1400102a0  mov     rcx, r14
0x1400102a3  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x1400102a8  mov     [r14+88h], rax
0x1400102af  test    rax, rax
0x1400102b2  jz      loc_14001046A
0x1400102b8  mov     edx, ebx
0x1400102ba  mov     rcx, r14
0x1400102bd  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x1400102c2  mov     [r14+90h], rax
0x1400102c9  test    rax, rax
0x1400102cc  jz      loc_14001046A
0x1400102d2  cmp     edi, 7FFFFFFh
0x1400102d8  ja      loc_14001046A
0x1400102de  movsx   rcx, word ptr [r14+114h]
0x1400102e6  add     rcx, 2
0x1400102ea  lea     rax, [rcx+rsi]
0x1400102ee  cmp     rax, rbp
0x1400102f1  ja      loc_140010474
0x1400102f7  shl     edi, cl
0x1400102f9  mov     rcx, r14
0x1400102fc  mov     edx, edi
0x1400102fe  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140010303  test    rax, rax
0x140010306  jz      loc_14001046A
0x14001030c  movzx   r8d, word ptr [r15+2]
0x140010311  xor     ebp, ebp
0x140010313  mov     rsi, [r12+8]
0x140010318  mov     r9, [r14+70h]
0x14001031c  mov     r10, [r14+80h]
0x140010323  mov     r11, [r14+78h]
0x140010327  mov     rbx, [r14+88h]
0x14001032e  mov     rdi, [r14+90h]
0x140010335  cmp     r8w, [r15+6]
0x14001033a  jge     short loc_140010385
0x14001033c  nop     dword ptr [rax+00h]
0x140010340  cmp     [rsi], r8w
0x140010344  jle     loc_1400103CF
0x14001034a  mov     [r9], rax
0x14001034d  inc     r8w
0x140010351  mov     [r10], rax
0x140010354  add     r9, 8
0x140010358  movsx   rcx, bp
0x14001035c  add     r10, 8
0x140010360  add     rcx, rcx
0x140010363  add     rax, rcx
0x140010366  mov     [r11], rax
0x140010369  add     r11, 8
0x14001036d  mov     [rbx], rax
0x140010370  add     rax, rcx
0x140010373  mov     [rdi], rax
0x140010376  add     rbx, 8
0x14001037a  add     rdi, 8
0x14001037e  cmp     r8w, [r15+6]
0x140010383  jl      short loc_140010340
0x140010385  test    byte ptr [rsp+48h+arg_10], 4
0x14001038a  jnz     loc_140010419
0x140010390  xor     eax, eax
0x140010392  mov     r12, [rsp+48h+arg_18]
0x140010397  mov     rbp, [rsp+48h+arg_8]
0x14001039c  mov     rbx, [rsp+48h+arg_0]
0x1400103a1  add     rsp, 20h
0x1400103a5  pop     r15
0x1400103a7  pop     r14
0x1400103a9  pop     r13
0x1400103ab  pop     rdi
0x1400103ac  pop     rsi
0x1400103ad  retn
0x1400103ae  movsx   ecx, word ptr [r14+114h]
0x1400103b6  movzx   eax, word ptr [rsi+2]
0x1400103ba  mov     rsi, [rsi+8]
0x1400103be  shl     ax, cl
0x1400103c1  add     bp, ax
0x1400103c4  cmp     [rsi], dx
0x1400103c7  jg      loc_1400101D3
0x1400103cd  jmp     short loc_1400103B6
0x1400103cf  movsx   ecx, word ptr [r14+114h]
0x1400103d7  movzx   edx, word ptr [rsi+2]
0x1400103db  mov     rsi, [rsi+8]
0x1400103df  shl     dx, cl
0x1400103e2  add     bp, dx
0x1400103e5  cmp     [rsi], r8w
0x1400103e9  jg      loc_14001034A
0x1400103ef  jmp     short loc_1400103D7
0x1400103f1  neg     ecx
0x1400103f3  mov     ebx, ecx
0x1400103f5  shl     rbx, 3
0x1400103f9  cmp     rbx, rdi
0x1400103fc  ja      short loc_140010474
0x1400103fe  neg     ebx
0x140010400  jmp     loc_14001009A
0x140010405  neg     ecx
0x140010407  mov     ebx, ecx
0x140010409  shl     rbx, 3
0x14001040d  cmp     rbx, rsi
0x140010410  ja      short loc_140010474
0x140010412  neg     ebx
0x140010414  jmp     loc_140010252
0x140010419  mov     eax, [rsp+48h+arg_30]
0x140010420  test    eax, eax
0x140010422  js      short loc_14001046A
0x140010424  cmp     eax, 0FFFFFFFh
0x140010429  ja      short loc_14001046A
0x14001042b  mov     ebx, eax
0x14001042d  shl     rbx, 2
0x140010431  cmp     rbx, 7FFFFFFFh
0x140010438  ja      short loc_140010474
0x14001043a  mov     edx, ebx
0x14001043c  mov     rcx, r14
0x14001043f  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140010444  mov     [r14+0F8h], rax
0x14001044b  test    rax, rax
0x14001044e  jz      short loc_14001046A
0x140010450  mov     edx, ebx
0x140010452  mov     rcx, r14
0x140010455  call    ?fsc_AllocVMem@@YAPEAXPEAUStateVars@@V?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; fsc_AllocVMem(StateVars *,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x14001045a  mov     [r14+100h], rax
0x140010461  test    rax, rax
0x140010464  jnz     loc_140010390
0x14001046a  mov     eax, 1A01h
0x14001046f  jmp     loc_140010392
0x140010474  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140010479  int     3; Trap to Debugger
0x14001047a  test    r8b, 4
0x14001047e  jz      loc_140010021
0x140010484  lea     r8, AddVertSmartScan
0x14001048b  mov     eax, 2
0x140010490  lea     r9, AddHorizSmartScan
0x140010497  mov     r10d, 1
0x14001049d  jmp     loc_140010037
0x1400104a2  mov     rcx, r12
0x1400104a5  call    FixPointers
0x1400104aa  jmp     loc_140010178
  ... truncated ...
```
