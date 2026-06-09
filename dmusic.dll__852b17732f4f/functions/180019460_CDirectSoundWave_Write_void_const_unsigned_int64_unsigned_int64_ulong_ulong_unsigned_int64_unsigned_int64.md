# CDirectSoundWave::Write(void * * const,unsigned __int64,unsigned __int64,ulong,ulong,unsigned __int64,unsigned __int64)

- ea: `0x180019460`
- end: `0x18001995c`
- name: `?Write@CDirectSoundWave@@QEBAJQEAPEAX_K1KK11@Z`
- size: `1276`
- prototype: `__int64 __fastcall(CDirectSoundWave *__hidden this, void **const, unsigned __int64, unsigned __int64, unsigned int, unsigned int, unsigned __int64, size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180018324`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x180019460`
- `0x1800217bc`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectSoundWave::Write(
        CDirectSoundWave *this,
        void **const a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 a7,
        size_t Size)
{
  size_t v8; // r15
  unsigned int v9; // r11d
  char v10; // r13
  bool v11; // si
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rax
  __int64 v16; // r10
  unsigned int v17; // edi
  __int64 v18; // r14
  unsigned int v19; // r15d
  unsigned int v20; // r8d
  unsigned int *v21; // rdx
  unsigned __int64 v22; // rax
  char *v23; // rcx
  int v24; // eax
  __int64 v25; // r14
  size_t v26; // r12
  __int64 v27; // rdi
  __int64 v28; // r13
  void **v29; // rsi
  __int64 v30; // rdx
  unsigned int i; // r8d
  char *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  int v37; // edi
  __int64 v38; // r15
  unsigned int v39; // eax
  size_t v40; // r13
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  int v43; // r9d
  unsigned int v44; // edx
  int v45; // eax
  int v46; // esi
  size_t v47; // r15
  unsigned __int64 v48; // rcx
  __int64 v49; // rcx
  size_t v50; // r9
  __int64 v51; // rdx
  unsigned int v52; // r8d
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  unsigned int v58; // [rsp+90h] [rbp+40h]
  unsigned __int64 v59; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int64 v60; // [rsp+A8h] [rbp+58h]

  v59 = a3;
  v8 = Size;
  v9 = 0;
  v10 = 0;
  v58 = 0;
  v11 = 0;
  if ( *((_BYTE *)this + 32) )
  {
    if ( !*((_BYTE *)this + 33) && !Size )
    {
      v14 = *((_QWORD *)this + 15);
      if ( v14 <= a3 && a3 <= v14 + *((_QWORD *)this + 16) )
      {
        v10 = 1;
        v9 = *((_DWORD *)this + 22) * (a3 - v14);
        v58 = v9;
      }
    }
  }
  v15 = *((_QWORD *)this + 15) + *((_QWORD *)this + 16);
  v60 = a3 + a4;
  if ( a3 + a4 > v15 )
    v11 = v10 != 0;
  v16 = *((_QWORD *)this + 6);
  v17 = *((_DWORD *)this + 22) * a4;
  v18 = 0;
  if ( *(_WORD *)(v16 + 2) )
  {
    v19 = a6;
    v20 = a5;
    do
    {
      v21 = (unsigned int *)a2[v18];
      v21[1] = v18 + v20;
      *((_QWORD *)v21 + 1) = 2;
      *v21 = v19;
      if ( a4 == 0x7FFFFFFFFFFFFFFFLL )
        v22 = *((_QWORD *)this + 8);
      else
        v22 = a4;
      v23 = (char *)(v21 + 8);
      if ( !v22 )
        LODWORD(v22) = 1;
      v21[3] = ((*((_DWORD *)this + 14) * v22 + 7) & 0xFFFFFFF8) + 32;
      v24 = (_DWORD)v21 + 16 - LODWORD(a2[v18]) + 8;
      v21[6] = v17;
      v21[4] = v24;
      v21[5] = (_DWORD)v23 - LODWORD(a2[v18]);
      *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v18) = v23;
      v18 = (unsigned int)(v18 + 1);
      v16 = *((_QWORD *)this + 6);
    }
    while ( (unsigned int)v18 < *(unsigned __int16 *)(v16 + 2) );
    a3 = v59;
    v9 = v58;
    v8 = Size;
  }
  v25 = v17;
  v26 = v17;
  Size = 0;
  if ( v11 )
  {
    v25 = (unsigned int)(*((_DWORD *)this + 22) * (*((_DWORD *)this + 32) + *((_DWORD *)this + 30) - a3));
    Size = v17 - (unsigned int)v25;
  }
  if ( v10 )
  {
    v27 = 0;
    if ( *(_WORD *)(v16 + 2) )
    {
      v28 = v9;
      do
      {
        memcpy_0(
          *(void **)(*((_QWORD *)this + 12) + 8 * v27),
          (const void *)(v28 + *(_QWORD *)(*((_QWORD *)this + 13) + 8 * v27)),
          (unsigned int)v25);
        v16 = *((_QWORD *)this + 6);
        v27 = (unsigned int)(v27 + 1);
      }
      while ( (unsigned int)v27 < *(unsigned __int16 *)(v16 + 2) );
    }
    if ( v11 )
    {
      v29 = (void **)operator new[](saturated_mul(*(unsigned __int16 *)(v16 + 2), 8u));
      if ( !v29 )
        return (unsigned int)-2147024882;
      *v29 = operator new[]((unsigned int)Size * *(unsigned __int16 *)(*((_QWORD *)this + 6) + 2LL));
      v30 = *((_QWORD *)this + 6);
      for ( i = 1; i < *(unsigned __int16 *)(v30 + 2); v30 = *((_QWORD *)this + 6) )
      {
        v32 = (char *)v29[i - 1] + Size;
        v33 = i++;
        v29[v33] = v32;
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 40LL))(
        *((_QWORD *)this + 9),
        *((_DWORD *)this + 22)
      * (*((_DWORD *)this + 32) + *((_DWORD *)this + 30))
      * (unsigned int)*(unsigned __int16 *)(v30 + 2));
      v34 = *((_QWORD *)this + 6);
      v35 = *((_QWORD *)this + 9);
      LODWORD(v59) = 2;
      v37 = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, _QWORD, _QWORD, unsigned __int64 *, _DWORD, size_t *))(*(_QWORD *)v35 + 48LL))(
              v35,
              v29,
              0,
              0,
              0,
              &v59,
              *(unsigned __int16 *)(v34 + 2),
              &Size);
      if ( v37 < 0 )
      {
        v40 = v26;
      }
      else
      {
        v36 = *((_QWORD *)this + 6);
        v38 = 0;
        v39 = Size;
        v40 = Size + v26;
        if ( *(_WORD *)(v36 + 2) )
        {
          while ( 1 )
          {
            memcpy_0((void *)(v25 + *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v38)), v29[v38], v39);
            v38 = (unsigned int)(v38 + 1);
            if ( (unsigned int)v38 >= *(unsigned __int16 *)(*((_QWORD *)this + 6) + 2LL) )
              break;
            v39 = Size;
          }
        }
      }
      operator delete(*v29, v36);
      operator delete(v29, v41);
      goto LABEL_53;
    }
    v42 = *((_QWORD *)this + 16) + *((_QWORD *)this + 15);
    v43 = *(unsigned __int16 *)(v16 + 2);
    if ( v60 < v42 )
      v44 = v60 * v43 * *((_DWORD *)this + 22);
    else
      v44 = v43 * *((_DWORD *)this + 22) * v42;
    v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 40LL))(*((_QWORD *)this + 9), v44);
LABEL_52:
    v40 = v26;
    v37 = v45;
LABEL_53:
    if ( v37 >= 0 && v26 != v40 )
      return 1;
    return (unsigned int)v37;
  }
  if ( !v8 )
  {
    v56 = *((_QWORD *)this + 9);
    Size = v17;
    v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, size_t *))(*(_QWORD *)v56 + 48LL))(
            v56,
            *((_QWORD *)this + 12),
            0,
            0,
            0,
            0,
            *(unsigned __int16 *)(v16 + 2),
            &Size);
    goto LABEL_52;
  }
  v46 = a7;
  if ( a3 > a7 )
  {
    v47 = v8 - a7;
    v48 = -(__int64)a7 - (a3 - a7) % v47;
    if ( a4 > a7 + v47 + v48 )
      LODWORD(a4) = a7 + v47 + v48;
  }
  v49 = *((_QWORD *)this + 9);
  Size = (unsigned int)(*((_DWORD *)this + 22) * a4);
  v37 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, size_t *))(*(_QWORD *)v49 + 48LL))(
          v49,
          *((_QWORD *)this + 12),
          0,
          0,
          0,
          0,
          *(unsigned __int16 *)(v16 + 2),
          &Size);
  if ( v37 >= 0 )
  {
    v50 = Size;
    if ( Size < v26 )
    {
      v51 = *((_QWORD *)this + 6);
      v52 = 0;
      if ( *(_WORD *)(v51 + 2) )
      {
        while ( 1 )
        {
          v53 = v52++;
          *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v53) += v50;
          v51 = *((_QWORD *)this + 6);
          if ( v52 >= *(unsigned __int16 *)(v51 + 2) )
            break;
          v50 = Size;
        }
        v46 = a7;
      }
      v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 40LL))(
              *((_QWORD *)this + 9),
              *((_DWORD *)this + 22) * v46 * (unsigned int)*(unsigned __int16 *)(v51 + 2));
      Size = v26 - Size;
      if ( v37 >= 0 )
      {
        v54 = *((_QWORD *)this + 6);
        v55 = *((_QWORD *)this + 9);
        LODWORD(v59) = 3;
        v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, unsigned __int64 *, _DWORD, size_t *))(*(_QWORD *)v55 + 48LL))(
                v55,
                *((_QWORD *)this + 12),
                0,
                0,
                0,
                &v59,
                *(unsigned __int16 *)(v54 + 2),
                &Size);
        goto LABEL_52;
      }
    }
  }
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x180019460  mov     [rsp-38h+arg_8], rbx
0x180019465  mov     [rsp-38h+arg_10], r8
0x18001946a  push    rbp
0x18001946b  push    rsi
0x18001946c  push    rdi
0x18001946d  push    r12
0x18001946f  push    r13
0x180019471  push    r14
0x180019473  push    r15
0x180019475  mov     rbp, rsp
0x180019478  sub     rsp, 50h
0x18001947c  mov     r15, [rbp+Size]
0x180019480  xor     r11d, r11d
0x180019483  xor     r13b, r13b
0x180019486  mov     [rbp+arg_0], r11d
0x18001948a  xor     sil, sil
0x18001948d  mov     r12, rdx
0x180019490  mov     rbx, rcx
0x180019493  lea     r10d, [r11+1]
0x180019497  cmp     [rcx+20h], sil
0x18001949b  jz      short loc_1800194D2
0x18001949d  cmp     [rcx+21h], sil
0x1800194a1  jnz     short loc_1800194D2
0x1800194a3  test    r15, r15
0x1800194a6  jnz     short loc_1800194D2
0x1800194a8  mov     rdx, [rcx+78h]
0x1800194ac  cmp     rdx, r8
0x1800194af  ja      short loc_1800194D2
0x1800194b1  mov     rcx, [rcx+80h]
0x1800194b8  add     rcx, rdx
0x1800194bb  cmp     r8, rcx
0x1800194be  ja      short loc_1800194D2
0x1800194c0  mov     r11d, r8d
0x1800194c3  mov     r13b, r10b
0x1800194c6  sub     r11d, edx
0x1800194c9  imul    r11d, [rbx+58h]
0x1800194ce  mov     [rbp+arg_0], r11d
0x1800194d2  mov     rax, [rbx+80h]
0x1800194d9  lea     rcx, [r8+r9]
0x1800194dd  add     rax, [rbx+78h]
0x1800194e1  mov     [rbp+arg_18], rcx
0x1800194e5  cmp     rcx, rax
0x1800194e8  jbe     short loc_1800194F5
0x1800194ea  test    r13b, r13b
0x1800194ed  movzx   esi, sil
0x1800194f1  cmovnz  esi, r10d
0x1800194f5  mov     r10, [rbx+30h]
0x1800194f9  mov     edi, r9d
0x1800194fc  imul    edi, [rbx+58h]
0x180019500  xor     r14d, r14d
0x180019503  xor     eax, eax
0x180019505  cmp     ax, [r10+2]
0x18001950a  jnb     loc_1800195A3
0x180019510  mov     r15d, [rbp+arg_28]
0x180019514  lea     r11d, [r14+1]
0x180019518  mov     r8d, [rbp+arg_20]
0x18001951c  mov     rdx, [r12+r14*8]
0x180019520  lea     eax, [r14+r8]
0x180019524  mov     [rdx+4], eax
0x180019527  mov     rax, 7FFFFFFFFFFFFFFFh
0x180019531  mov     qword ptr [rdx+8], 2
0x180019539  mov     [rdx], r15d
0x18001953c  cmp     r9, rax
0x18001953f  jnz     short loc_180019547
0x180019541  mov     rax, [rbx+40h]
0x180019545  jmp     short loc_18001954A
0x180019547  mov     rax, r9
0x18001954a  test    rax, rax
0x18001954d  lea     rcx, [rdx+20h]
0x180019551  cmovz   rax, r11
0x180019555  imul    eax, [rbx+38h]
0x180019559  add     eax, 7
0x18001955c  and     eax, 0FFFFFFF8h
0x18001955f  add     eax, 20h ; ' '
0x180019562  mov     [rdx+0Ch], eax
0x180019565  lea     eax, [rdx+10h]
0x180019568  sub     eax, [r12+r14*8]
0x18001956c  add     eax, 8
0x18001956f  mov     [rdx+18h], edi
0x180019572  mov     [rdx+10h], eax
0x180019575  mov     eax, ecx
0x180019577  sub     eax, [r12+r14*8]
0x18001957b  mov     [rdx+14h], eax
0x18001957e  mov     rax, [rbx+60h]
0x180019582  mov     [rax+r14*8], rcx
0x180019586  add     r14d, r11d
0x180019589  mov     r10, [rbx+30h]
0x18001958d  movzx   eax, word ptr [r10+2]
0x180019592  cmp     r14d, eax
0x180019595  jb      short loc_18001951C
0x180019597  mov     r8, [rbp+arg_10]
0x18001959b  mov     r11d, [rbp+arg_0]
0x18001959f  mov     r15, [rbp+Size]
0x1800195a3  mov     r14d, edi
0x1800195a6  mov     r12d, edi
0x1800195a9  mov     [rbp+Size], 0
0x1800195b1  test    sil, sil
0x1800195b4  jz      short loc_1800195D2
0x1800195b6  mov     r14d, [rbx+78h]
0x1800195ba  sub     r14d, r8d
0x1800195bd  add     r14d, [rbx+80h]
0x1800195c4  imul    r14d, [rbx+58h]
0x1800195c9  sub     edi, r14d
0x1800195cc  mov     eax, edi
0x1800195ce  mov     [rbp+Size], rax
0x1800195d2  test    r13b, r13b
0x1800195d5  jz      loc_1800197BD
0x1800195db  xor     edi, edi
0x1800195dd  xor     eax, eax
0x1800195df  cmp     ax, [r10+2]
0x1800195e4  jnb     short loc_180019616
0x1800195e6  mov     r15d, r14d
0x1800195e9  mov     r13d, r11d
0x1800195ec  mov     rax, [rbx+68h]
0x1800195f0  mov     r8, r15; Size
0x1800195f3  mov     rcx, [rbx+60h]
0x1800195f7  mov     rdx, [rax+rdi*8]
0x1800195fb  mov     rcx, [rcx+rdi*8]; void *
0x1800195ff  add     rdx, r13; Src
0x180019602  call    memcpy_0
0x180019607  mov     r10, [rbx+30h]
0x18001960b  inc     edi
0x18001960d  movzx   eax, word ptr [r10+2]
0x180019612  cmp     edi, eax
0x180019614  jb      short loc_1800195EC
0x180019616  test    sil, sil
0x180019619  jz      loc_18001976F
0x18001961f  movzx   ecx, word ptr [r10+2]
0x180019624  mov     eax, 8
0x180019629  mul     rcx
0x18001962c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019633  cmovb   rax, rcx
0x180019637  mov     rcx, rax; unsigned __int64
0x18001963a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001963f  mov     rsi, rax
0x180019642  test    rax, rax
0x180019645  jz      loc_180019765
0x18001964b  mov     rcx, [rbx+30h]
0x18001964f  movzx   ecx, word ptr [rcx+2]
0x180019653  imul    ecx, dword ptr [rbp+Size]; unsigned __int64
0x180019657  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001965c  mov     [rsi], rax
0x18001965f  mov     r9d, 1
0x180019665  mov     rdx, [rbx+30h]
0x180019669  mov     r8d, r9d
0x18001966c  cmp     r9w, [rdx+2]
0x180019671  jnb     short loc_180019696
0x180019673  mov     rcx, [rbp+Size]
0x180019677  lea     eax, [r8-1]
0x18001967b  add     rcx, [rsi+rax*8]
0x18001967f  mov     eax, r8d
0x180019682  add     r8d, r9d
0x180019685  mov     [rsi+rax*8], rcx
0x180019689  mov     rdx, [rbx+30h]
0x18001968d  movzx   eax, word ptr [rdx+2]
0x180019691  cmp     r8d, eax
0x180019694  jb      short loc_180019673
0x180019696  mov     eax, [rbx+78h]
0x180019699  add     eax, [rbx+80h]
0x18001969f  movzx   edx, word ptr [rdx+2]
0x1800196a3  mov     rcx, [rbx+48h]
0x1800196a7  imul    edx, eax
0x1800196aa  mov     r8, [rcx]
0x1800196ad  imul    edx, [rbx+58h]
0x1800196b1  mov     rax, [r8+28h]
0x1800196b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ba  mov     rax, [rbx+30h]
0x1800196be  xor     r9d, r9d
0x1800196c1  mov     rcx, [rbx+48h]
0x1800196c5  mov     dword ptr [rbp+arg_10], 2
0x1800196cc  movzx   r8d, word ptr [rax+2]
0x1800196d1  mov     rdx, [rcx]
0x1800196d4  mov     rax, [rdx+30h]
0x1800196d8  lea     rdx, [rbp+Size]
0x1800196dc  mov     [rsp+50h+var_18], rdx
0x1800196e1  lea     rdx, [rbp+arg_10]
0x1800196e5  mov     [rsp+50h+var_20], r8d
0x1800196ea  xor     r8d, r8d
0x1800196ed  mov     [rsp+50h+var_28], rdx
0x1800196f2  mov     rdx, rsi
0x1800196f5  mov     [rsp+50h+var_30], 0
0x1800196fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019703  mov     edi, eax
0x180019705  test    eax, eax
0x180019707  js      short loc_18001974D
0x180019709  mov     rdx, [rbx+30h]
0x18001970d  xor     r15d, r15d
0x180019710  mov     rax, [rbp+Size]
0x180019714  xor     ecx, ecx
0x180019716  lea     r13, [rax+r12]
0x18001971a  cmp     cx, [rdx+2]
0x18001971e  jnb     short loc_180019750
0x180019720  mov     rdx, [rsi+r15*8]; Src
0x180019724  mov     r8d, eax; Size
0x180019727  mov     rax, [rbx+60h]
0x18001972b  mov     rcx, [rax+r15*8]
0x18001972f  add     rcx, r14; void *
0x180019732  call    memcpy_0
0x180019737  mov     rax, [rbx+30h]
0x18001973b  inc     r15d
0x18001973e  movzx   ecx, word ptr [rax+2]
0x180019742  cmp     r15d, ecx
0x180019745  jnb     short loc_180019750
0x180019747  mov     rax, [rbp+Size]
0x18001974b  jmp     short loc_180019720
0x18001974d  mov     r13, r12
0x180019750  mov     rcx, [rsi]; void *
0x180019753  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019758  mov     rcx, rsi; void *
0x18001975b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019760  jmp     loc_180019933
0x180019765  mov     edi, 8007000Eh
0x18001976a  jmp     loc_180019942
0x18001976f  mov     r8, [rbx+48h]
0x180019773  mov     rdx, [rbx+78h]
0x180019777  mov     rcx, r8
0x18001977a  add     rdx, [rbx+80h]
0x180019781  movzx   r9d, word ptr [r10+2]
0x180019786  mov     rax, [r8]
0x180019789  mov     r11, [rax+28h]
0x18001978d  mov     rax, [rbp+arg_18]
0x180019791  cmp     rax, rdx
0x180019794  jb      short loc_1800197B0
0x180019796  mov     eax, [rbx+58h]
0x180019799  imul    rdx, rax
0x18001979d  imul    rdx, r9
0x1800197a1  mov     edx, edx
0x1800197a3  mov     rax, r11
0x1800197a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197ab  jmp     loc_18001992E
0x1800197b0  mov     edx, [rbx+58h]
0x1800197b3  imul    rdx, r9
0x1800197b7  imul    rdx, rax
0x1800197bb  jmp     short loc_1800197A1
0x1800197bd  test    r15, r15
0x1800197c0  jz      loc_1800198EC
0x1800197c6  mov     rsi, [rbp+arg_30]
0x1800197ca  cmp     r8, rsi
0x1800197cd  jbe     short loc_1800197F4
0x1800197cf  sub     r15, rsi
0x1800197d2  xor     edx, edx
0x1800197d4  mov     rcx, r8
0x1800197d7  sub     rcx, rsi
0x1800197da  mov     rax, rcx
0x1800197dd  div     r15
0x1800197e0  sub     rcx, rdx
0x1800197e3  sub     rcx, r8
0x1800197e6  lea     rax, [r15+rcx]
0x1800197ea  add     rax, rsi
0x1800197ed  cmp     r9, rax
0x1800197f0  cmova   r9, rax
0x1800197f4  imul    r9d, [rbx+58h]
0x1800197f9  lea     r8, [rbp+Size]
0x1800197fd  mov     rcx, [rbx+48h]
0x180019801  xor     r13d, r13d
0x180019804  mov     [rsp+50h+var_18], r8
0x180019809  xor     r8d, r8d
0x18001980c  mov     eax, r9d
0x18001980f  xor     r9d, r9d
0x180019812  mov     [rbp+Size], rax
0x180019816  movzx   edx, word ptr [r10+2]
0x18001981b  mov     rax, [rcx]
0x18001981e  mov     [rsp+50h+var_20], edx
0x180019822  mov     rdx, [rbx+60h]
0x180019826  mov     [rsp+50h+var_28], r13
0x18001982b  mov     rax, [rax+30h]
0x18001982f  mov     [rsp+50h+var_30], r13
0x180019834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019839  mov     edi, eax
0x18001983b  test    eax, eax
0x18001983d  js      loc_180019942
0x180019843  mov     r9, [rbp+Size]
0x180019847  cmp     r9, r12
0x18001984a  jnb     loc_180019942
0x180019850  mov     rdx, [rbx+30h]
0x180019854  mov     r8d, r13d
0x180019857  cmp     r13w, [rdx+2]
0x18001985c  jnb     short loc_180019883
0x18001985e  mov     rax, [rbx+60h]
0x180019862  mov     ecx, r8d
0x180019865  inc     r8d
0x180019868  add     [rax+rcx*8], r9
0x18001986c  mov     rdx, [rbx+30h]
0x180019870  movzx   eax, word ptr [rdx+2]
0x180019874  cmp     r8d, eax
0x180019877  jnb     short loc_18001987F
0x180019879  mov     r9, [rbp+Size]
0x18001987d  jmp     short loc_18001985E
0x18001987f  mov     rsi, [rbp+arg_30]
0x180019883  movzx   edx, word ptr [rdx+2]
0x180019887  mov     rcx, [rbx+48h]
0x18001988b  imul    edx, esi
0x18001988e  mov     r8, [rcx]
0x180019891  imul    edx, [rbx+58h]
0x180019895  mov     rax, [r8+28h]
0x180019899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001989e  mov     edi, eax
0x1800198a0  mov     rax, r12
0x1800198a3  sub     rax, [rbp+Size]
0x1800198a7  mov     [rbp+Size], rax
  ... truncated ...
```
