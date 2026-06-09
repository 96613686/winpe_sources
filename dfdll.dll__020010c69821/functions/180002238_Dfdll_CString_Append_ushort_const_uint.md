# Dfdll::CString::Append(ushort const *,uint)

- ea: `0x180002238`
- end: `0x180002556`
- name: `?Append@CString@Dfdll@@QEAAJPEBGI@Z`
- size: `798`
- prototype: `int(Dfdll::CString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `14`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800020d4`
- `0x180002604`
- `0x180002b80`
- `0x180002ff8`
- `0x180003530`
- `0x1800037a0`
- `0x180003e88`
- `0x180005400`
- `0x180006180`
- `0x1800077d0`
- `0x180007a7c`
- `0x18000d59c`
- `0x1800116ac`
- `0x180012140`

## callees

- `0x180001fc8`
- `0x180002238`
- `0x180003a90`
- `0x180012b30`
- `0x1800140a0`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CString::Append(Dfdll::CString *this, struct std::nothrow_t *a2, unsigned int a3)
{
  struct std::nothrow_t *v3; // rsi
  int v5; // ebx
  unsigned int v6; // edi
  const unsigned __int16 *v7; // rax
  Dfdll::CBufferBase *v8; // r14
  unsigned int v9; // r8d
  unsigned int v10; // ecx
  int v11; // ecx
  char v12; // al
  struct std::nothrow_t *v13; // rdx
  struct std::nothrow_t *v14; // rcx
  struct std::nothrow_t *v15; // r8
  const struct std::nothrow_t *v16; // rdx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // r9d
  unsigned int v20; // r15d
  const struct std::nothrow_t *v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  void **v25; // [rsp+30h] [rbp-20h] BYREF
  struct std::nothrow_t *v26; // [rsp+38h] [rbp-18h]
  unsigned int v27; // [rsp+40h] [rbp-10h]
  void *v28; // [rsp+88h] [rbp+38h] BYREF

  v3 = a2;
  if ( !a2 )
    return 0;
  v6 = 0;
  if ( a3 )
  {
    v7 = (const unsigned __int16 *)a2;
    do
    {
      if ( !*v7 )
        break;
      ++v6;
      ++v7;
    }
    while ( v6 < a3 );
    if ( v6 > 0x7FFFFFFF )
      return (unsigned int)-2147024362;
  }
  v8 = (Dfdll::CString *)((char *)this + 8);
  if ( !(2 * v6) || !*((_DWORD *)this + 6) )
    goto LABEL_16;
  v28 = 0;
  v5 = (*(__int64 (__fastcall **)(char *, _QWORD, void **))(*(_QWORD *)v8 + 64LL))((char *)this + 8, 0, &v28);
  if ( v5 < 0 )
    return (unsigned int)v5;
  v9 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *))(*(_QWORD *)v8 + 72LL))(v8);
  v10 = *((_DWORD *)v8 + 4);
  if ( !v9 || v10 > 0xFFFFFFFF / v9 || (v11 = v9 * v10) == 0 )
    return (unsigned int)-2147024362;
  if ( (char *)v3 + 2 * v6 - 1 < v28 || (v12 = 1, v3 > (struct std::nothrow_t *)((char *)v28 + (unsigned int)(v11 - 1))) )
LABEL_16:
    v12 = 0;
  v13 = 0;
  v26 = 0;
  v27 = 0;
  v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v14 = 0;
  v15 = 0;
  if ( v12 )
  {
    v5 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v25, v6);
    if ( v5 < 0 )
    {
      v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v26 )
        operator delete(v26, v16);
      return (unsigned int)v5;
    }
    if ( !v6 )
      goto LABEL_36;
    if ( v27 && v27 >= v6 )
    {
      v28 = 0;
      v5 = ((__int64 (__fastcall *)(void ***, _QWORD, void **))v25[8])(&v25, 0, &v28);
      if ( v5 >= 0 )
      {
        v17 = ((__int64 (__fastcall *)(void ***))v25[9])(&v25);
        if ( !v17 )
        {
          v18 = 0;
LABEL_35:
          memmove(v28, v3, v18);
LABEL_36:
          v13 = v26;
          v3 = v26;
          v14 = v26;
          v15 = v26;
          goto LABEL_37;
        }
        v16 = (const struct std::nothrow_t *)(0xFFFFFFFF % v17);
        if ( v6 <= 0xFFFFFFFF / v17 )
        {
          v18 = v6 * v17;
          goto LABEL_35;
        }
        v5 = -2147024362;
      }
    }
    else
    {
      v5 = -2147024809;
    }
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v26 )
      operator delete(v26, v16);
    return (unsigned int)v5;
  }
LABEL_37:
  v19 = *((_DWORD *)this + 8);
  if ( v19 > ~v6 )
    goto LABEL_40;
  v20 = v19 + v6;
  if ( v19 + v6 == -1 )
  {
    v14 = v15;
LABEL_40:
    v5 = -2147024362;
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v14 )
      operator delete(v13, v13);
    return (unsigned int)v5;
  }
  if ( v20 + 1 <= *((_DWORD *)this + 6) || (v5 = Dfdll::CBufferBase::Reallocate(v8, v20 + 1), v5 >= 0) )
  {
    v5 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, struct std::nothrow_t *, _QWORD, _QWORD))(*(_QWORD *)v8 + 104LL))(
           v8,
           v3,
           *((unsigned int *)this + 8),
           v6);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, _QWORD))(*(_QWORD *)v8 + 40LL))(v8, v20);
      if ( v5 >= 0 )
      {
        *((_DWORD *)this + 8) = v20;
        v5 = 0;
        v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v26 )
          operator delete(v26, v23);
      }
      else
      {
        v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v26 )
          operator delete(v26, v23);
      }
    }
    else
    {
      v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v26 )
        operator delete(v26, v22);
    }
  }
  else
  {
    v25 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v26 )
      operator delete(v26, v21);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002238  mov     [rsp-28h+arg_0], rbx
0x18000223d  mov     [rsp-28h+arg_10], rsi
0x180002242  mov     [rsp-28h+arg_18], rdi
0x180002247  push    rbp
0x180002248  push    r12
0x18000224a  push    r13
0x18000224c  push    r14
0x18000224e  push    r15
0x180002250  mov     rbp, rsp
0x180002253  sub     rsp, 50h
0x180002257  mov     rsi, rdx
0x18000225a  mov     r13, rcx
0x18000225d  xor     r12d, r12d
0x180002260  test    rdx, rdx
0x180002263  jnz     short loc_18000226D
0x180002265  mov     ebx, r12d
0x180002268  jmp     loc_180002536
0x18000226d  mov     edi, r12d
0x180002270  test    r8d, r8d
0x180002273  jz      short loc_180002295
0x180002275  mov     rax, rsi
0x180002278  cmp     [rax], r12w
0x18000227c  jz      short loc_180002289
0x18000227e  inc     edi
0x180002280  add     rax, 2
0x180002284  cmp     edi, r8d
0x180002287  jb      short loc_180002278
0x180002289  cmp     edi, 7FFFFFFFh
0x18000228f  ja      loc_180002531
0x180002295  lea     r15d, [rdi+rdi]
0x180002299  lea     r14, [rcx+8]
0x18000229d  test    r15d, r15d
0x1800022a0  jz      loc_180002335
0x1800022a6  cmp     [r14+10h], r12d
0x1800022aa  jz      loc_180002335
0x1800022b0  mov     [rbp+arg_8], r12
0x1800022b4  mov     rax, [r14]
0x1800022b7  lea     r8, [rbp+arg_8]
0x1800022bb  xor     edx, edx
0x1800022bd  mov     rcx, r14
0x1800022c0  mov     rax, [rax+40h]
0x1800022c4  call    cs:__guard_dispatch_icall_fptr
0x1800022ca  mov     ebx, eax
0x1800022cc  test    eax, eax
0x1800022ce  js      loc_180002536
0x1800022d4  mov     rax, [r14]
0x1800022d7  mov     rcx, r14
0x1800022da  mov     rax, [rax+48h]
0x1800022de  call    cs:__guard_dispatch_icall_fptr
0x1800022e4  mov     r8d, eax
0x1800022e7  mov     ecx, [r14+10h]
0x1800022eb  test    eax, eax
0x1800022ed  jz      loc_180002531
0x1800022f3  xor     edx, edx
0x1800022f5  or      eax, 0FFFFFFFFh
0x1800022f8  div     r8d
0x1800022fb  cmp     ecx, eax
0x1800022fd  ja      loc_180002531
0x180002303  imul    ecx, r8d
0x180002307  cmp     ecx, 1
0x18000230a  jb      loc_180002531
0x180002310  lea     edx, [rcx-1]
0x180002313  add     rdx, [rbp+arg_8]
0x180002317  cmp     r15d, 1
0x18000231b  jb      loc_180002531
0x180002321  lea     ecx, [r15-1]
0x180002325  add     rcx, rsi
0x180002328  cmp     rcx, [rbp+arg_8]
0x18000232c  jb      short loc_180002335
0x18000232e  cmp     rsi, rdx
0x180002331  mov     al, 1
0x180002333  jbe     short loc_180002338
0x180002335  mov     al, r12b
0x180002338  mov     rdx, r12
0x18000233b  mov     [rbp+var_18], rdx
0x18000233f  mov     [rbp+var_10], r12d
0x180002343  lea     r15, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000234a  mov     [rbp+var_20], r15
0x18000234e  mov     rcx, r12
0x180002351  mov     r8, r12
0x180002354  test    al, al
0x180002356  jz      loc_180002425
0x18000235c  mov     edx, edi; unsigned int
0x18000235e  lea     rcx, [rbp+var_20]; this
0x180002362  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180002367  mov     ebx, eax
0x180002369  test    eax, eax
0x18000236b  jns     short loc_180002385
0x18000236d  mov     [rbp+var_20], r15
0x180002371  mov     rcx, [rbp+var_18]; void *
0x180002375  test    rcx, rcx
0x180002378  jz      short loc_180002380
0x18000237a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000237f  nop
0x180002380  jmp     loc_180002536
0x180002385  test    edi, edi
0x180002387  jz      loc_180002418
0x18000238d  mov     eax, [rbp+var_10]
0x180002390  test    eax, eax
0x180002392  jnz     short loc_1800023B1
0x180002394  mov     ebx, 80070057h
0x180002399  mov     [rbp+var_20], r15
0x18000239d  mov     rcx, [rbp+var_18]; void *
0x1800023a1  test    rcx, rcx
0x1800023a4  jz      short loc_1800023AC
0x1800023a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800023ab  nop
0x1800023ac  jmp     loc_180002536
0x1800023b1  cmp     eax, edi
0x1800023b3  jb      short loc_180002394
0x1800023b5  mov     [rbp+arg_8], r12
0x1800023b9  mov     rax, [rbp+var_20]
0x1800023bd  lea     r8, [rbp+arg_8]
0x1800023c1  xor     edx, edx
0x1800023c3  lea     rcx, [rbp+var_20]
0x1800023c7  mov     rax, [rax+40h]
0x1800023cb  call    cs:__guard_dispatch_icall_fptr
0x1800023d1  mov     ebx, eax
0x1800023d3  test    eax, eax
0x1800023d5  js      short loc_180002399
0x1800023d7  mov     rax, [rbp+var_20]
0x1800023db  lea     rcx, [rbp+var_20]
0x1800023df  mov     rax, [rax+48h]
0x1800023e3  call    cs:__guard_dispatch_icall_fptr
0x1800023e9  mov     ecx, eax
0x1800023eb  test    eax, eax
0x1800023ed  jnz     short loc_1800023F4
0x1800023ef  mov     ecx, r12d
0x1800023f2  jmp     short loc_180002409
0x1800023f4  xor     edx, edx
0x1800023f6  or      eax, 0FFFFFFFFh
0x1800023f9  div     ecx
0x1800023fb  cmp     edi, eax
0x1800023fd  jbe     short loc_180002406
0x1800023ff  mov     ebx, 80070216h
0x180002404  jmp     short loc_180002399
0x180002406  imul    ecx, edi
0x180002409  mov     r8d, ecx; Size
0x18000240c  mov     rdx, rsi; Src
0x18000240f  mov     rcx, [rbp+arg_8]; void *
0x180002413  call    memmove
0x180002418  mov     rdx, [rbp+var_18]; struct std::nothrow_t *
0x18000241c  mov     rsi, rdx
0x18000241f  mov     rcx, rdx
0x180002422  mov     r8, rdx
0x180002425  mov     r9d, [r13+20h]
0x180002429  mov     eax, edi
0x18000242b  not     eax
0x18000242d  cmp     r9d, eax
0x180002430  ja      short loc_18000244A
0x180002432  lea     r15d, [r9+rdi]
0x180002436  mov     eax, r15d
0x180002439  not     eax
0x18000243b  cmp     eax, 1
0x18000243e  jnb     short loc_180002466
0x180002440  mov     rcx, r8
0x180002443  lea     r15, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000244a  mov     ebx, 80070216h
0x18000244f  mov     [rbp+var_20], r15
0x180002453  test    rcx, rcx
0x180002456  jz      short loc_180002461
0x180002458  mov     rcx, rdx; void *
0x18000245b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002460  nop
0x180002461  jmp     loc_180002536
0x180002466  lea     edx, [r15+1]; unsigned int
0x18000246a  cmp     edx, [r13+18h]
0x18000246e  jbe     short loc_18000249D
0x180002470  mov     rcx, r14; this
0x180002473  call    ?Reallocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Reallocate(uint)
0x180002478  mov     ebx, eax
0x18000247a  test    eax, eax
0x18000247c  jns     short loc_18000249D
0x18000247e  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180002485  mov     [rbp+var_20], rax
0x180002489  mov     rcx, [rbp+var_18]; void *
0x18000248d  test    rcx, rcx
0x180002490  jz      short loc_180002498
0x180002492  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002497  nop
0x180002498  jmp     loc_180002536
0x18000249d  mov     rax, [r14]
0x1800024a0  mov     r9d, edi
0x1800024a3  mov     r8d, [r13+20h]
0x1800024a7  mov     rdx, rsi
0x1800024aa  mov     rcx, r14
0x1800024ad  mov     rax, [rax+68h]
0x1800024b1  call    cs:__guard_dispatch_icall_fptr
0x1800024b7  mov     ebx, eax
0x1800024b9  test    eax, eax
0x1800024bb  jns     short loc_1800024D9
0x1800024bd  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800024c4  mov     [rbp+var_20], rax
0x1800024c8  mov     rcx, [rbp+var_18]; void *
0x1800024cc  test    rcx, rcx
0x1800024cf  jz      short loc_1800024D7
0x1800024d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800024d6  nop
0x1800024d7  jmp     short loc_180002536
0x1800024d9  mov     rax, [r14]
0x1800024dc  mov     edx, r15d
0x1800024df  mov     rcx, r14
0x1800024e2  mov     rax, [rax+28h]
0x1800024e6  call    cs:__guard_dispatch_icall_fptr
0x1800024ec  mov     ebx, eax
0x1800024ee  test    eax, eax
0x1800024f0  jns     short loc_18000250E
0x1800024f2  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800024f9  mov     [rbp+var_20], rax
0x1800024fd  mov     rcx, [rbp+var_18]; void *
0x180002501  test    rcx, rcx
0x180002504  jz      short loc_18000250C
0x180002506  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000250b  nop
0x18000250c  jmp     short loc_180002536
0x18000250e  mov     [r13+20h], r15d
0x180002512  mov     ebx, r12d
0x180002515  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000251c  mov     [rbp+var_20], rax
0x180002520  mov     rcx, [rbp+var_18]; void *
0x180002524  test    rcx, rcx
0x180002527  jz      short loc_18000252F
0x180002529  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000252e  nop
0x18000252f  jmp     short loc_180002536
0x180002531  mov     ebx, 80070216h
0x180002536  mov     eax, ebx
0x180002538  lea     r11, [rsp+50h+var_s0]
0x18000253d  mov     rbx, [r11+30h]
0x180002541  mov     rsi, [r11+40h]
0x180002545  mov     rdi, [r11+48h]
0x180002549  mov     rsp, r11
0x18000254c  pop     r15
0x18000254e  pop     r14
0x180002550  pop     r13
0x180002552  pop     r12
0x180002554  pop     rbp
0x180002555  retn
```
