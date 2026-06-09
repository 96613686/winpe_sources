# CUserModeSynth::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x180012220`
- end: `0x180012458`
- name: `?KsProperty@CUserModeSynth@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `568`
- prototype: `int(CUserModeSynth *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180012220`
- `0x1800148c5`
- `0x1800148d1`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CUserModeSynth::KsProperty(
        CUserModeSynth *this,
        struct KSIDENTIFIER *a2,
        int a3,
        _DWORD *a4,
        size_t Size,
        unsigned int *a6)
{
  unsigned int v9; // ebx
  ULONG v10; // edi
  unsigned int *v11; // r15
  __int64 result; // rax
  __int64 Id; // rdx
  struct GENERICPROPERTY near **v14; // r10
  ULONG v15; // edi
  ULONG v16; // edi
  struct GENERICPROPERTY near *v17; // rax
  __int64 v18; // rcx

  if ( a3 && !a2 )
    return 2147500035LL;
  v9 = Size;
  v10 = a2->Flags & 0x203;
  if ( (v10 == 2 || v10 == 512) && (_DWORD)Size && !a4 )
    return 2147500035LL;
  v11 = a6;
  if ( !a6 )
    return 2147500035LL;
  if ( !memcmp_0(a2, &GUID_DMUS_PROP_WavesReverb, 0x10u) && *((_QWORD *)this + 4) )
    return 2289570082LL;
  Id = a2->Id;
  v14 = &CUserModeSynth::m_aProperty;
  while ( *(_QWORD *)*v14 != a2->Alignment
       || *((_QWORD *)*v14 + 1) != *(&a2->Alignment + 1)
       || *((_DWORD *)v14 + 2) != (_DWORD)Id )
  {
    v14 += 7;
    if ( v14 == (struct GENERICPROPERTY near **)qword_18001E430 )
      return 2289570082LL;
  }
  v15 = v10 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      if ( v16 == 510 && v9 >= 4 )
      {
        *a4 = *((_DWORD *)v14 + 3);
        result = 0;
        *v11 = 4;
      }
      else
      {
        return 2147942487LL;
      }
    }
    else if ( (*((_BYTE *)v14 + 12) & 2) != 0 )
    {
      if ( ((_BYTE)v14[2] & 1) != 0 )
      {
        return ((__int64 (__fastcall *)(char *, __int64, __int64, _DWORD *, size_t *))v14[4])(
                 (char *)this + *((int *)v14 + 10) - 16,
                 Id,
                 1,
                 a4,
                 &Size);
      }
      else
      {
        if ( v9 > *((_DWORD *)v14 + 7) )
          v9 = *((_DWORD *)v14 + 7);
        memcpy_0(*(struct GENERICPROPERTY near **)((char *)v14 + 20), a4, v9);
        return 0;
      }
    }
    else
    {
      return 2289570083LL;
    }
  }
  else if ( (*((_BYTE *)v14 + 12) & 1) != 0 )
  {
    if ( ((_BYTE)v14[2] & 1) != 0 )
    {
      v17 = v14[4];
      v18 = *((int *)v14 + 10) - 16LL;
      *v11 = v9;
      return ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, _DWORD *, unsigned int *))v17)(
               (char *)this + v18,
               a2->Id,
               0,
               a4,
               v11);
    }
    else
    {
      if ( v9 > *((_DWORD *)v14 + 7) )
      {
        v9 = *((_DWORD *)v14 + 7);
        LODWORD(Size) = v9;
      }
      if ( a4 )
        memcpy_0(a4, *(struct GENERICPROPERTY near **)((char *)v14 + 20), v9);
      *v11 = v9;
      return 0;
    }
  }
  else
  {
    return 2289570084LL;
  }
  return result;
}

```

## disassembly

```asm
0x180012220  push    rbx
0x180012222  push    rbp
0x180012223  push    rsi
0x180012224  push    rdi
0x180012225  push    r14
0x180012227  push    r15
0x180012229  sub     rsp, 38h
0x18001222d  mov     r14, r9
0x180012230  mov     rsi, rdx
0x180012233  mov     rbp, rcx
0x180012236  test    r8d, r8d
0x180012239  jz      short loc_180012240
0x18001223b  test    rdx, rdx
0x18001223e  jz      short loc_180012273
0x180012240  mov     edi, [rdx+14h]
0x180012243  mov     ebx, dword ptr [rsp+68h+Size]
0x18001224a  and     edi, 203h
0x180012250  cmp     edi, 2
0x180012253  jz      short loc_18001225D
0x180012255  cmp     edi, 200h
0x18001225b  jnz     short loc_180012266
0x18001225d  test    ebx, ebx
0x18001225f  jz      short loc_180012266
0x180012261  test    r14, r14
0x180012264  jz      short loc_180012273
0x180012266  mov     r15, [rsp+68h+arg_28]
0x18001226e  test    r15, r15
0x180012271  jnz     short loc_180012285
0x180012273  mov     eax, 80004003h
0x180012278  add     rsp, 38h
0x18001227c  pop     r15
0x18001227e  pop     r14
0x180012280  pop     rdi
0x180012281  pop     rsi
0x180012282  pop     rbp
0x180012283  pop     rbx
0x180012284  retn
0x180012285  mov     r8d, 10h; Size
0x18001228b  lea     rdx, GUID_DMUS_PROP_WavesReverb; Buf2
0x180012292  mov     rcx, rsi; Buf1
0x180012295  call    memcmp_0
0x18001229a  test    eax, eax
0x18001229c  jnz     short loc_1800122A5
0x18001229e  cmp     qword ptr [rbp+20h], 0
0x1800122a3  jnz     short loc_1800122F4
0x1800122a5  mov     edx, [rsi+10h]
0x1800122a8  lea     r10, ?m_aProperty@CUserModeSynth@@0PAUGENERICPROPERTY@@A; GENERICPROPERTY near * CUserModeSynth::m_aProperty
0x1800122af  lea     r8, qword_18001E430
0x1800122b6  nop     word ptr [rax+rax+00000000h]
0x1800122c0  mov     eax, [r10]
0x1800122c3  xor     ecx, ecx
0x1800122c5  or      rcx, rax
0x1800122c8  mov     eax, [r10+4]
0x1800122cc  shl     rax, 20h
0x1800122d0  or      rcx, rax
0x1800122d3  mov     rax, [rcx]
0x1800122d6  cmp     rax, [rsi]
0x1800122d9  jnz     short loc_1800122EB
0x1800122db  mov     rax, [rcx+8]
0x1800122df  cmp     rax, [rsi+8]
0x1800122e3  jnz     short loc_1800122EB
0x1800122e5  cmp     [r10+8], edx
0x1800122e9  jz      short loc_180012306
0x1800122eb  add     r10, 38h ; '8'
0x1800122ef  cmp     r10, r8
0x1800122f2  jnz     short loc_1800122C0
0x1800122f4  mov     eax, 88781122h
0x1800122f9  add     rsp, 38h
0x1800122fd  pop     r15
0x1800122ff  pop     r14
0x180012301  pop     rdi
0x180012302  pop     rsi
0x180012303  pop     rbp
0x180012304  pop     rbx
0x180012305  retn
0x180012306  sub     edi, 1
0x180012309  jz      loc_1800123CF
0x18001230f  sub     edi, 1
0x180012312  jz      short loc_180012350
0x180012314  cmp     edi, 1FEh
0x18001231a  jnz     short loc_180012321
0x18001231c  cmp     ebx, 4
0x18001231f  jnb     short loc_180012333
0x180012321  mov     eax, 80070057h
0x180012326  add     rsp, 38h
0x18001232a  pop     r15
0x18001232c  pop     r14
0x18001232e  pop     rdi
0x18001232f  pop     rsi
0x180012330  pop     rbp
0x180012331  pop     rbx
0x180012332  retn
0x180012333  mov     eax, [r10+0Ch]
0x180012337  mov     [r14], eax
0x18001233a  xor     eax, eax
0x18001233c  mov     dword ptr [r15], 4
0x180012343  add     rsp, 38h
0x180012347  pop     r15
0x180012349  pop     r14
0x18001234b  pop     rdi
0x18001234c  pop     rsi
0x18001234d  pop     rbp
0x18001234e  pop     rbx
0x18001234f  retn
0x180012350  test    byte ptr [r10+0Ch], 2
0x180012355  jnz     short loc_180012369
0x180012357  mov     eax, 88781123h
0x18001235c  add     rsp, 38h
0x180012360  pop     r15
0x180012362  pop     r14
0x180012364  pop     rdi
0x180012365  pop     rsi
0x180012366  pop     rbp
0x180012367  pop     rbx
0x180012368  retn
0x180012369  test    byte ptr [r10+10h], 1
0x18001236e  jz      short loc_1800123A7
0x180012370  movsxd  rcx, dword ptr [r10+28h]
0x180012374  lea     rax, [rsp+68h+Size]
0x18001237c  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180012380  mov     [rsp+68h+var_48], rax
0x180012385  mov     rax, [r10+20h]
0x180012389  add     rcx, rbp
0x18001238c  mov     r9, r14
0x18001238f  mov     r8d, 1
0x180012395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001239a  add     rsp, 38h
0x18001239e  pop     r15
0x1800123a0  pop     r14
0x1800123a2  pop     rdi
0x1800123a3  pop     rsi
0x1800123a4  pop     rbp
0x1800123a5  pop     rbx
0x1800123a6  retn
0x1800123a7  mov     eax, [r10+1Ch]
0x1800123ab  cmp     ebx, eax
0x1800123ad  jbe     short loc_1800123B1
0x1800123af  mov     ebx, eax
0x1800123b1  mov     rcx, [r10+14h]; void *
0x1800123b5  mov     rdx, r14; Src
0x1800123b8  mov     r8d, ebx; Size
0x1800123bb  call    memcpy_0
0x1800123c0  xor     eax, eax
0x1800123c2  add     rsp, 38h
0x1800123c6  pop     r15
0x1800123c8  pop     r14
0x1800123ca  pop     rdi
0x1800123cb  pop     rsi
0x1800123cc  pop     rbp
0x1800123cd  pop     rbx
0x1800123ce  retn
0x1800123cf  test    byte ptr [r10+0Ch], 1
0x1800123d4  jnz     short loc_1800123E8
0x1800123d6  mov     eax, 88781124h
0x1800123db  add     rsp, 38h
0x1800123df  pop     r15
0x1800123e1  pop     r14
0x1800123e3  pop     rdi
0x1800123e4  pop     rsi
0x1800123e5  pop     rbp
0x1800123e6  pop     rbx
0x1800123e7  retn
0x1800123e8  test    byte ptr [r10+10h], 1
0x1800123ed  jz      short loc_180012421
0x1800123ef  movsxd  rcx, dword ptr [r10+28h]
0x1800123f3  mov     r9, r14
0x1800123f6  mov     rax, [r10+20h]
0x1800123fa  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800123fe  mov     [r15], ebx
0x180012401  add     rcx, rbp
0x180012404  mov     edx, [rsi+10h]
0x180012407  xor     r8d, r8d
0x18001240a  mov     [rsp+68h+var_48], r15
0x18001240f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012414  add     rsp, 38h
0x180012418  pop     r15
0x18001241a  pop     r14
0x18001241c  pop     rdi
0x18001241d  pop     rsi
0x18001241e  pop     rbp
0x18001241f  pop     rbx
0x180012420  retn
0x180012421  mov     eax, [r10+1Ch]
0x180012425  cmp     ebx, eax
0x180012427  jbe     short loc_180012432
0x180012429  mov     ebx, eax
0x18001242b  mov     dword ptr [rsp+68h+Size], eax
0x180012432  test    r14, r14
0x180012435  jz      short loc_180012446
0x180012437  mov     rdx, [r10+14h]; Src
0x18001243b  mov     rcx, r14; void *
0x18001243e  mov     r8d, ebx; Size
0x180012441  call    memcpy_0
0x180012446  mov     [r15], ebx
0x180012449  xor     eax, eax
0x18001244b  add     rsp, 38h
0x18001244f  pop     r15
0x180012451  pop     r14
0x180012453  pop     rdi
0x180012454  pop     rsi
0x180012455  pop     rbp
0x180012456  pop     rbx
0x180012457  retn
```
