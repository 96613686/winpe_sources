# Dfdll::CConvert::ToUINTArray(ushort const *,ushort const *,Dfdll::CArray<Dfdll::CBuffer<uint>,uint> &)

- ea: `0x1800122cc`
- end: `0x1800125bf`
- name: `?ToUINTArray@CConvert@Dfdll@@SAJPEBG0AEAV?$CArray@V?$CBuffer@I@Dfdll@@I@2@@Z`
- size: `755`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180011ba8`

## callees

- `0x180002604`
- `0x18000d8e0`
- `0x1800122cc`
- `0x180012b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Dfdll::CConvert::ToUINTArray(struct std::nothrow_t *a1, _WORD *a2, unsigned int *a3)
{
  const struct std::nothrow_t *v5; // rdx
  int inserted; // ebx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  struct std::nothrow_t *v9; // rdx
  __int64 v10; // r10
  _WORD *v11; // rax
  __int64 v12; // r11
  unsigned int v13; // edi
  _WORD *v14; // r10
  int v15; // ecx
  int v16; // ecx
  unsigned int v17; // r10d
  int v18; // r9d
  const struct std::nothrow_t *v19; // rdx
  unsigned int v20; // r9d
  int v21; // ecx
  int v22; // r10d
  const struct std::nothrow_t *v23; // rdx
  void **v25; // [rsp+20h] [rbp-30h] BYREF
  void **v26; // [rsp+28h] [rbp-28h]
  struct std::nothrow_t *v27; // [rsp+30h] [rbp-20h]
  int v28; // [rsp+38h] [rbp-18h]
  unsigned int v29; // [rsp+40h] [rbp-10h]
  int v30; // [rsp+98h] [rbp+48h] BYREF

  v25 = &Dfdll::CString::`vftable';
  v27 = 0;
  v28 = 0;
  v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v29 = 0;
  inserted = Dfdll::CString::Assign((Dfdll::CString *)&v25, a1);
  if ( inserted >= 0 )
  {
    a3[2] = 0;
    v7 = 0;
    v8 = v29;
    v9 = v27;
    while ( a2 )
    {
      v10 = 0x7FFFFFFF;
      v11 = a2;
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v10;
      }
      while ( v10 );
      v12 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
      if ( !v10 )
        break;
      v13 = v7;
      if ( v7 >= v8 )
        goto LABEL_54;
      v14 = (_WORD *)((char *)v9 + 2 * v7);
      while ( 1 )
      {
        v15 = 0;
        if ( (_DWORD)v12 )
          break;
LABEL_16:
        ++v13;
        ++v14;
        if ( v13 >= v8 )
          goto LABEL_17;
      }
      while ( *v14 != a2[v15] )
      {
        if ( ++v15 >= (unsigned int)v12 )
          goto LABEL_16;
      }
      if ( v7 < v13 )
      {
        v16 = 0;
        v30 = 0;
        if ( v13 )
        {
          v17 = v13 - 1;
          if ( v9 && v7 <= v17 )
          {
            while ( 1 )
            {
              v18 = *((unsigned __int16 *)v9 + v7);
              if ( (unsigned __int16)(v18 - 48) > 9u )
                break;
              v16 = v18 + 2 * (5 * v16 - 24);
              v30 = v16;
              if ( ++v7 > v17 )
              {
                inserted = Dfdll::CArrayBase::InsertRangeInternal((Dfdll::CArrayBase *)a3, a3[2], &v30, 1u);
                if ( inserted >= 0 )
                {
                  v8 = v29;
                  v9 = v27;
                  goto LABEL_30;
                }
                v25 = &Dfdll::CString::`vftable';
                v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
                if ( v27 )
                  operator delete(v27, v19);
                return (unsigned int)inserted;
              }
            }
          }
          v25 = &Dfdll::CString::`vftable';
          v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v9 )
            operator delete(v9, v9);
          return (unsigned int)-2147024809;
        }
        inserted = -2147024362;
        v25 = &Dfdll::CString::`vftable';
        v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v9 )
          operator delete(v9, v9);
        return (unsigned int)inserted;
      }
LABEL_30:
      if ( v13 == -1 )
      {
        inserted = -2147024362;
        v25 = &Dfdll::CString::`vftable';
        v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v9 )
          operator delete(v9, v9);
        return (unsigned int)inserted;
      }
      v7 = v13 + 1;
    }
LABEL_17:
    if ( v7 >= v8 )
    {
LABEL_54:
      inserted = 0;
      v25 = &Dfdll::CString::`vftable';
      v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v9 )
        operator delete(v9, v9);
    }
    else
    {
      if ( v8 )
      {
        v20 = v8 - 1;
        if ( v9 && v7 <= v20 )
        {
          v21 = 0;
          v30 = 0;
          while ( 1 )
          {
            v22 = *((unsigned __int16 *)v9 + v7);
            if ( (unsigned __int16)(v22 - 48) > 9u )
              break;
            v21 = v22 + 2 * (5 * v21 - 24);
            v30 = v21;
            if ( ++v7 > v20 )
            {
              inserted = Dfdll::CArrayBase::InsertRangeInternal((Dfdll::CArrayBase *)a3, a3[2], &v30, 1u);
              if ( inserted >= 0 )
              {
                v9 = v27;
                goto LABEL_54;
              }
              v25 = &Dfdll::CString::`vftable';
              v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
              if ( v27 )
                operator delete(v27, v23);
              return (unsigned int)inserted;
            }
          }
        }
        v25 = &Dfdll::CString::`vftable';
        v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v9 )
          operator delete(v9, v9);
        return (unsigned int)-2147024809;
      }
      inserted = -2147024362;
      v25 = &Dfdll::CString::`vftable';
      v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v9 )
        operator delete(v9, v9);
    }
  }
  else
  {
    v25 = &Dfdll::CString::`vftable';
    v26 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v27 )
      operator delete(v27, v5);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800122cc  mov     [rsp-28h+arg_0], rbx
0x1800122d1  mov     [rsp-28h+arg_8], rsi
0x1800122d6  mov     [rsp-28h+arg_10], rdi
0x1800122db  push    rbp
0x1800122dc  push    r12
0x1800122de  push    r13
0x1800122e0  push    r14
0x1800122e2  push    r15
0x1800122e4  mov     rbp, rsp
0x1800122e7  sub     rsp, 50h
0x1800122eb  mov     rsi, r8
0x1800122ee  mov     r14, rdx
0x1800122f1  lea     r12, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x1800122f8  mov     [rbp+var_30], r12
0x1800122fc  xor     r15d, r15d
0x1800122ff  mov     [rbp+var_20], r15
0x180012303  mov     [rbp+var_18], r15d
0x180012307  lea     r13, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18001230e  mov     [rbp+var_28], r13
0x180012312  mov     [rbp+var_10], r15d
0x180012316  mov     rdx, rcx; unsigned __int16 *
0x180012319  lea     rcx, [rbp+var_30]; this
0x18001231d  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x180012322  mov     ebx, eax
0x180012324  test    eax, eax
0x180012326  jns     short loc_180012344
0x180012328  mov     [rbp+var_30], r12
0x18001232c  mov     [rbp+var_28], r13
0x180012330  mov     rcx, [rbp+var_20]; void *
0x180012334  test    rcx, rcx
0x180012337  jz      short loc_18001233F
0x180012339  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001233e  nop
0x18001233f  jmp     loc_180012584
0x180012344  mov     [rsi+8], r15d
0x180012348  mov     r8d, r15d
0x18001234b  mov     r9d, [rbp+var_10]
0x18001234f  mov     rdx, [rbp+var_20]; struct std::nothrow_t *
0x180012353  test    r14, r14
0x180012356  jz      short loc_1800123C4
0x180012358  mov     r10d, 7FFFFFFFh
0x18001235e  mov     rax, r14
0x180012361  cmp     [rax], r15w
0x180012365  jz      short loc_180012371
0x180012367  add     rax, 2
0x18001236b  sub     r10, 1
0x18001236f  jnz     short loc_180012361
0x180012371  mov     rax, r10
0x180012374  mov     ecx, 7FFFFFFFh
0x180012379  sub     rcx, r10
0x18001237c  neg     rax
0x18001237f  sbb     r11, r11
0x180012382  and     r11, rcx
0x180012385  test    r10, r10
0x180012388  jz      short loc_1800123C4
0x18001238a  mov     edi, r8d
0x18001238d  cmp     r8d, r9d
0x180012390  jnb     loc_18001256B
0x180012396  mov     eax, r8d
0x180012399  lea     r10, [rdx+rax*2]
0x18001239d  mov     ecx, r15d
0x1800123a0  test    r11d, r11d
0x1800123a3  jz      short loc_1800123B9
0x1800123a5  movzx   ebx, word ptr [r10]
0x1800123a9  mov     eax, ecx
0x1800123ab  cmp     bx, [r14+rax*2]
0x1800123b0  jz      short loc_1800123F7
0x1800123b2  inc     ecx
0x1800123b4  cmp     ecx, r11d
0x1800123b7  jb      short loc_1800123A9
0x1800123b9  inc     edi
0x1800123bb  add     r10, 2
0x1800123bf  cmp     edi, r9d
0x1800123c2  jb      short loc_18001239D
0x1800123c4  cmp     r8d, r9d
0x1800123c7  jnb     loc_18001256B
0x1800123cd  cmp     r9d, 1
0x1800123d1  jnb     loc_1800124ED
0x1800123d7  mov     ebx, 80070216h
0x1800123dc  mov     [rbp+var_30], r12
0x1800123e0  mov     [rbp+var_28], r13
0x1800123e4  test    rdx, rdx
0x1800123e7  jz      short loc_1800123F2
0x1800123e9  mov     rcx, rdx; void *
0x1800123ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800123f1  nop
0x1800123f2  jmp     loc_180012584
0x1800123f7  cmp     r8d, edi
0x1800123fa  jnb     short loc_180012463
0x1800123fc  mov     ecx, r15d
0x1800123ff  mov     [rbp+arg_18], ecx
0x180012402  cmp     edi, 1
0x180012405  jb      loc_1800124AD
0x18001240b  lea     r10d, [rdi-1]
0x18001240f  test    rdx, rdx
0x180012412  jz      short loc_18001248D
0x180012414  cmp     r8d, r10d
0x180012417  ja      short loc_18001248D
0x180012419  mov     eax, r8d
0x18001241c  movzx   r9d, word ptr [rdx+rax*2]
0x180012421  lea     eax, [r9-30h]
0x180012425  cmp     ax, 9
0x180012429  ja      short loc_18001248D
0x18001242b  lea     ecx, [rcx+rcx*4]
0x18001242e  lea     ecx, [rcx-18h]
0x180012431  lea     ecx, [r9+rcx*2]
0x180012435  mov     [rbp+arg_18], ecx
0x180012438  inc     r8d
0x18001243b  cmp     r8d, r10d
0x18001243e  jbe     short loc_180012419
0x180012440  mov     r9d, 1; unsigned int
0x180012446  lea     r8, [rbp+arg_18]; void *
0x18001244a  mov     edx, [rsi+8]; unsigned int
0x18001244d  mov     rcx, rsi; this
0x180012450  call    ?InsertRangeInternal@CArrayBase@Dfdll@@IEAAJIPEBXI@Z; Dfdll::CArrayBase::InsertRangeInternal(uint,void const *,uint)
0x180012455  mov     ebx, eax
0x180012457  test    eax, eax
0x180012459  js      short loc_180012471
0x18001245b  mov     r9d, [rbp+var_10]
0x18001245f  mov     rdx, [rbp+var_20]; struct std::nothrow_t *
0x180012463  cmp     edi, 0FFFFFFFEh
0x180012466  ja      short loc_1800124CD
0x180012468  lea     r8d, [rdi+1]
0x18001246c  jmp     loc_180012353
0x180012471  mov     [rbp+var_30], r12
0x180012475  mov     [rbp+var_28], r13
0x180012479  mov     rcx, [rbp+var_20]; void *
0x18001247d  test    rcx, rcx
0x180012480  jz      short loc_180012488
0x180012482  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012487  nop
0x180012488  jmp     loc_180012584
0x18001248d  mov     [rbp+var_30], r12
0x180012491  mov     [rbp+var_28], r13
0x180012495  test    rdx, rdx
0x180012498  jz      short loc_1800124A3
0x18001249a  mov     rcx, rdx; void *
0x18001249d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800124a2  nop
0x1800124a3  mov     ebx, 80070057h
0x1800124a8  jmp     loc_180012584
0x1800124ad  mov     ebx, 80070216h
0x1800124b2  mov     [rbp+var_30], r12
0x1800124b6  mov     [rbp+var_28], r13
0x1800124ba  test    rdx, rdx
0x1800124bd  jz      short loc_1800124C8
0x1800124bf  mov     rcx, rdx; void *
0x1800124c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800124c7  nop
0x1800124c8  jmp     loc_180012584
0x1800124cd  mov     ebx, 80070216h
0x1800124d2  mov     [rbp+var_30], r12
0x1800124d6  mov     [rbp+var_28], r13
0x1800124da  test    rdx, rdx
0x1800124dd  jz      short loc_1800124E8
0x1800124df  mov     rcx, rdx; void *
0x1800124e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800124e7  nop
0x1800124e8  jmp     loc_180012584
0x1800124ed  dec     r9d
0x1800124f0  test    rdx, rdx
0x1800124f3  jz      loc_1800125A4
0x1800124f9  cmp     r8d, r9d
0x1800124fc  ja      loc_1800125A4
0x180012502  mov     ecx, r15d
0x180012505  mov     [rbp+arg_18], ecx
0x180012508  mov     eax, r8d
0x18001250b  movzx   r10d, word ptr [rdx+rax*2]
0x180012510  lea     eax, [r10-30h]
0x180012514  cmp     ax, 9
0x180012518  ja      loc_1800125A4
0x18001251e  lea     ecx, [rcx+rcx*4]
0x180012521  lea     ecx, [rcx-18h]
0x180012524  lea     ecx, [r10+rcx*2]
0x180012528  mov     [rbp+arg_18], ecx
0x18001252b  inc     r8d
0x18001252e  cmp     r8d, r9d
0x180012531  jbe     short loc_180012508
0x180012533  mov     r9d, 1; unsigned int
0x180012539  lea     r8, [rbp+arg_18]; void *
0x18001253d  mov     edx, [rsi+8]; unsigned int
0x180012540  mov     rcx, rsi; this
0x180012543  call    ?InsertRangeInternal@CArrayBase@Dfdll@@IEAAJIPEBXI@Z; Dfdll::CArrayBase::InsertRangeInternal(uint,void const *,uint)
0x180012548  mov     ebx, eax
0x18001254a  test    eax, eax
0x18001254c  jns     short loc_180012567
0x18001254e  mov     [rbp+var_30], r12
0x180012552  mov     [rbp+var_28], r13
0x180012556  mov     rcx, [rbp+var_20]; void *
0x18001255a  test    rcx, rcx
0x18001255d  jz      short loc_180012565
0x18001255f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012564  nop
0x180012565  jmp     short loc_180012584
0x180012567  mov     rdx, [rbp+var_20]; struct std::nothrow_t *
0x18001256b  mov     ebx, r15d
0x18001256e  mov     [rbp+var_30], r12
0x180012572  mov     [rbp+var_28], r13
0x180012576  test    rdx, rdx
0x180012579  jz      short loc_180012584
0x18001257b  mov     rcx, rdx; void *
0x18001257e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012583  nop
0x180012584  mov     eax, ebx
0x180012586  lea     r11, [rsp+50h+var_s0]
0x18001258b  mov     rbx, [r11+30h]
0x18001258f  mov     rsi, [r11+38h]
0x180012593  mov     rdi, [r11+40h]
0x180012597  mov     rsp, r11
0x18001259a  pop     r15
0x18001259c  pop     r14
0x18001259e  pop     r13
0x1800125a0  pop     r12
0x1800125a2  pop     rbp
0x1800125a3  retn
0x1800125a4  mov     [rbp+var_30], r12
0x1800125a8  mov     [rbp+var_28], r13
0x1800125ac  test    rdx, rdx
0x1800125af  jz      short loc_1800125BA
0x1800125b1  mov     rcx, rdx; void *
0x1800125b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800125b9  nop
0x1800125ba  jmp     loc_1800124A3
```
