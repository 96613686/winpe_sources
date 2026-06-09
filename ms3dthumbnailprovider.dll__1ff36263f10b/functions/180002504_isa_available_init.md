# __isa_available_init

- ea: `0x180002504`
- end: `0x180002787`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f90`
- `0x1800020cc`

## callees

- `0x180002504`

## pseudocode

```c
int __cdecl _isa_available_init()
{
  int v5; // ebp
  bool v7; // zf
  int v12; // edi
  int v13; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // r10d
  unsigned int v18; // r11d
  int v24; // esi
  int v25; // r9d
  unsigned __int64 v36; // rax
  int v37; // eax
  unsigned __int64 v38; // rax
  __int64 v39; // rdx
  int v41; // [rsp+40h] [rbp+8h]

  _RAX = 0;
  __asm { cpuid }
  v5 = _RAX;
  _RAX = 1;
  v7 = ((unsigned int)_RBX ^ 0x756E6547 | (unsigned int)_RCX ^ 0x6C65746E | (unsigned int)_RDX ^ 0x49656E69) == 0;
  __asm { cpuid }
  v12 = _RCX;
  if ( v7
    && ((v13 = _RAX & 0xFFF3FF0, _memset_fast_string_threshold = 0x8000, _memset_nt_threshold = -1, v13 == 67264)
     || v13 == 132704
     || v13 == 132720
     || (v14 = (unsigned int)(v13 - 198224), (unsigned int)v14 <= 0x20) && (v15 = 0x100010001LL, _bittest64(&v15, v14))) )
  {
    v16 = _favor | 1;
    _favor |= 1u;
  }
  else
  {
    v16 = _favor;
  }
  v17 = 0;
  v18 = 0;
  if ( v5 < 7 )
  {
    v25 = 0;
    v24 = 0;
  }
  else
  {
    _RAX = 7;
    __asm { cpuid }
    v24 = _RDX;
    v25 = _RBX;
    if ( (_RBX & 0x200) != 0 )
      _favor = v16 | 2;
    if ( (int)_RAX >= 1 )
    {
      _RAX = 7;
      __asm { cpuid }
      v17 = _RDX;
    }
    _RAX = 36;
    if ( v5 >= 36 )
    {
      __asm { cpuid }
      v18 = _RBX;
    }
  }
  v36 = _isa_inverted & 0xFFFFFFFFFFFFFFFEuLL;
  _isa_available = 1;
  _isa_enabled = 2;
  _isa_inverted &= ~1uLL;
  if ( (v12 & 0x100000) != 0 )
  {
    v36 &= ~0x10uLL;
    _isa_available = 2;
    _isa_inverted = v36;
    _isa_enabled = 6;
  }
  if ( (v12 & 0x8000000) != 0 )
  {
    __asm { xgetbv }
    v41 = v36;
    if ( (v12 & 0x10000000) == 0 || (v36 & 6) != 6 )
    {
LABEL_33:
      if ( (v17 & 0x200000) != 0 && (*(_QWORD *)&v41 & 0x80000LL) != 0 )
        _isa_inverted &= ~0x80uLL;
      return 0;
    }
    v37 = _isa_enabled | 8;
    _isa_available = 3;
    _isa_enabled |= 8u;
    if ( (v25 & 0x20) != 0 )
    {
      _isa_available = 5;
      _isa_enabled = v37 | 0x20;
      v38 = _isa_inverted & 0xFFFFFFFFFFFFFFFDuLL;
      _isa_inverted &= ~2uLL;
      if ( (v25 & 0xD0030000) != 0xD0030000 )
      {
LABEL_27:
        if ( (v24 & 0x800000) != 0 )
          _isa_inverted = v38 & 0xFFFFFFFFFEFFFFFFuLL;
        if ( (v17 & 0x80000) != 0 && (v41 & 0xE0) == 0xE0 )
        {
          _avx10_version = v18 & 0x400FF;
          v39 = ~(HIWORD(v18) & 6 | 0x1000029LL) & _isa_inverted;
          _isa_inverted = v39;
          if ( (unsigned __int8)v18 > 1u )
            _isa_inverted = v39 & 0xFFFFFFFFFFFFFFBFuLL;
        }
        goto LABEL_33;
      }
      if ( (v41 & 0xE0) == 0xE0 )
      {
        _isa_enabled |= 0x40u;
        v38 = _isa_inverted & 0xFFFFFFFFFFFFFFDBuLL;
        _isa_available = 6;
        _isa_inverted &= 0xFFFFFFFFFFFFFFDBuLL;
        goto LABEL_27;
      }
    }
    v38 = _isa_inverted;
    goto LABEL_27;
  }
  return 0;
}

```

## disassembly

```asm
0x180002504  push    rbx
0x180002506  push    rbp
0x180002507  push    rsi
0x180002508  push    rdi
0x180002509  sub     rsp, 18h
0x18000250d  xor     eax, eax
0x18000250f  xor     ecx, ecx
0x180002511  cpuid
0x180002513  xor     ecx, 6C65746Eh
0x180002519  xor     edx, 49656E69h
0x18000251f  or      edx, ecx
0x180002521  mov     ebp, eax
0x180002523  mov     eax, 1
0x180002528  xor     ebx, 756E6547h
0x18000252e  or      edx, ebx
0x180002530  lea     ecx, [rax-1]
0x180002533  cpuid
0x180002535  mov     edi, ecx
0x180002537  jnz     short loc_180002597
0x180002539  and     eax, 0FFF3FF0h
0x18000253e  mov     cs:__memset_fast_string_threshold, 8000h
0x180002549  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002554  cmp     eax, 106C0h
0x180002559  jz      short loc_180002583
0x18000255b  cmp     eax, 20660h
0x180002560  jz      short loc_180002583
0x180002562  cmp     eax, 20670h
0x180002567  jz      short loc_180002583
0x180002569  add     eax, 0FFFCF9B0h
0x18000256e  cmp     eax, 20h ; ' '
0x180002571  ja      short loc_180002597
0x180002573  mov     rcx, 100010001h
0x18000257d  bt      rcx, rax
0x180002581  jnb     short loc_180002597
0x180002583  mov     r8d, cs:__favor
0x18000258a  or      r8d, 1
0x18000258e  mov     cs:__favor, r8d
0x180002595  jmp     short loc_18000259E
0x180002597  mov     r8d, cs:__favor
0x18000259e  xor     r10d, r10d
0x1800025a1  xor     r11d, r11d
0x1800025a4  cmp     ebp, 7
0x1800025a7  jl      short loc_1800025EB
0x1800025a9  xor     ecx, ecx
0x1800025ab  lea     eax, [r10+7]
0x1800025af  cpuid
0x1800025b1  mov     esi, edx
0x1800025b3  mov     r9d, ebx
0x1800025b6  bt      ebx, 9
0x1800025ba  jnb     short loc_1800025C7
0x1800025bc  or      r8d, 2
0x1800025c0  mov     cs:__favor, r8d
0x1800025c7  cmp     eax, 1
0x1800025ca  jl      short loc_1800025D9
0x1800025cc  mov     eax, 7
0x1800025d1  lea     ecx, [rax-6]
0x1800025d4  cpuid
0x1800025d6  mov     r10d, edx
0x1800025d9  mov     eax, 24h ; '$'
0x1800025de  cmp     ebp, eax
0x1800025e0  jl      short loc_1800025F0
0x1800025e2  xor     ecx, ecx
0x1800025e4  cpuid
0x1800025e6  mov     r11d, ebx
0x1800025e9  jmp     short loc_1800025F0
0x1800025eb  xor     r9d, r9d
0x1800025ee  xor     esi, esi
0x1800025f0  mov     rax, cs:__isa_inverted
0x1800025f7  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800025fb  mov     cs:__isa_available, 1
0x180002605  mov     cs:__isa_enabled, 2
0x18000260f  mov     cs:__isa_inverted, rax
0x180002616  bt      edi, 14h
0x18000261a  jnb     short loc_18000263B
0x18000261c  and     rax, 0FFFFFFFFFFFFFFEFh
0x180002620  mov     cs:__isa_available, 2
0x18000262a  mov     cs:__isa_inverted, rax
0x180002631  mov     cs:__isa_enabled, 6
0x18000263b  bt      edi, 1Bh
0x18000263f  jnb     loc_18000277C
0x180002645  xor     ecx, ecx
0x180002647  xgetbv
0x18000264a  shl     rdx, 20h
0x18000264e  or      rdx, rax
0x180002651  mov     [rsp+38h+arg_0], rdx
0x180002656  bt      edi, 1Ch
0x18000265a  jnb     loc_180002760
0x180002660  mov     rax, [rsp+38h+arg_0]
0x180002665  and     al, 6
0x180002667  cmp     al, 6
0x180002669  jnz     loc_180002760
0x18000266f  mov     eax, cs:__isa_enabled
0x180002675  mov     dl, 0E0h
0x180002677  or      eax, 8
0x18000267a  mov     cs:__isa_available, 3
0x180002684  mov     cs:__isa_enabled, eax
0x18000268a  test    r9b, 20h
0x18000268e  jz      short loc_1800026F2
0x180002690  or      eax, 20h
0x180002693  mov     cs:__isa_available, 5
0x18000269d  mov     cs:__isa_enabled, eax
0x1800026a3  mov     ecx, 0D0030000h
0x1800026a8  mov     rax, cs:__isa_inverted
0x1800026af  and     r9d, ecx
0x1800026b2  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800026b6  mov     cs:__isa_inverted, rax
0x1800026bd  cmp     r9d, ecx
0x1800026c0  jnz     short loc_1800026F9
0x1800026c2  mov     rax, [rsp+38h+arg_0]
0x1800026c7  and     al, dl
0x1800026c9  cmp     al, dl
0x1800026cb  jnz     short loc_1800026F2
0x1800026cd  mov     rax, cs:__isa_inverted
0x1800026d4  or      cs:__isa_enabled, 40h
0x1800026db  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800026df  mov     cs:__isa_available, 6
0x1800026e9  mov     cs:__isa_inverted, rax
0x1800026f0  jmp     short loc_1800026F9
0x1800026f2  mov     rax, cs:__isa_inverted
0x1800026f9  bt      esi, 17h
0x1800026fd  jnb     short loc_18000270B
0x1800026ff  btr     rax, 18h
0x180002704  mov     cs:__isa_inverted, rax
0x18000270b  bt      r10d, 13h
0x180002710  jnb     short loc_180002760
0x180002712  mov     rax, [rsp+38h+arg_0]
0x180002717  and     al, dl
0x180002719  cmp     al, dl
0x18000271b  jnz     short loc_180002760
0x18000271d  mov     rdx, cs:__isa_inverted
0x180002724  mov     eax, r11d
0x180002727  shr     rax, 10h
0x18000272b  mov     ecx, r11d
0x18000272e  and     eax, 6
0x180002731  and     ecx, 400FFh
0x180002737  or      rax, 1000029h
0x18000273d  mov     cs:__avx10_version, ecx
0x180002743  not     rax
0x180002746  and     rdx, rax
0x180002749  mov     cs:__isa_inverted, rdx
0x180002750  cmp     cl, 1
0x180002753  jbe     short loc_180002760
0x180002755  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002759  mov     cs:__isa_inverted, rdx
0x180002760  bt      r10d, 15h
0x180002765  jnb     short loc_18000277C
0x180002767  mov     rax, [rsp+38h+arg_0]
0x18000276c  bt      rax, 13h
0x180002771  jnb     short loc_18000277C
0x180002773  btr     cs:__isa_inverted, 7
0x18000277c  xor     eax, eax
0x18000277e  add     rsp, 18h
0x180002782  pop     rdi
0x180002783  pop     rsi
0x180002784  pop     rbp
0x180002785  pop     rbx
0x180002786  retn
```
