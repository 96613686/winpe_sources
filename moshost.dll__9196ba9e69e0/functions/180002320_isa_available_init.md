# __isa_available_init

- ea: `0x180002320`
- end: `0x1800025a3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d70`
- `0x180001eac`

## callees

- `0x180002320`

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
0x180002320  push    rbx
0x180002322  push    rbp
0x180002323  push    rsi
0x180002324  push    rdi
0x180002325  sub     rsp, 18h
0x180002329  xor     eax, eax
0x18000232b  xor     ecx, ecx
0x18000232d  cpuid
0x18000232f  xor     ecx, 6C65746Eh
0x180002335  xor     edx, 49656E69h
0x18000233b  or      edx, ecx
0x18000233d  mov     ebp, eax
0x18000233f  mov     eax, 1
0x180002344  xor     ebx, 756E6547h
0x18000234a  or      edx, ebx
0x18000234c  lea     ecx, [rax-1]
0x18000234f  cpuid
0x180002351  mov     edi, ecx
0x180002353  jnz     short loc_1800023B3
0x180002355  and     eax, 0FFF3FF0h
0x18000235a  mov     cs:__memset_fast_string_threshold, 8000h
0x180002365  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002370  cmp     eax, 106C0h
0x180002375  jz      short loc_18000239F
0x180002377  cmp     eax, 20660h
0x18000237c  jz      short loc_18000239F
0x18000237e  cmp     eax, 20670h
0x180002383  jz      short loc_18000239F
0x180002385  add     eax, 0FFFCF9B0h
0x18000238a  cmp     eax, 20h ; ' '
0x18000238d  ja      short loc_1800023B3
0x18000238f  mov     rcx, 100010001h
0x180002399  bt      rcx, rax
0x18000239d  jnb     short loc_1800023B3
0x18000239f  mov     r8d, cs:__favor
0x1800023a6  or      r8d, 1
0x1800023aa  mov     cs:__favor, r8d
0x1800023b1  jmp     short loc_1800023BA
0x1800023b3  mov     r8d, cs:__favor
0x1800023ba  xor     r10d, r10d
0x1800023bd  xor     r11d, r11d
0x1800023c0  cmp     ebp, 7
0x1800023c3  jl      short loc_180002407
0x1800023c5  xor     ecx, ecx
0x1800023c7  lea     eax, [r10+7]
0x1800023cb  cpuid
0x1800023cd  mov     esi, edx
0x1800023cf  mov     r9d, ebx
0x1800023d2  bt      ebx, 9
0x1800023d6  jnb     short loc_1800023E3
0x1800023d8  or      r8d, 2
0x1800023dc  mov     cs:__favor, r8d
0x1800023e3  cmp     eax, 1
0x1800023e6  jl      short loc_1800023F5
0x1800023e8  mov     eax, 7
0x1800023ed  lea     ecx, [rax-6]
0x1800023f0  cpuid
0x1800023f2  mov     r10d, edx
0x1800023f5  mov     eax, 24h ; '$'
0x1800023fa  cmp     ebp, eax
0x1800023fc  jl      short loc_18000240C
0x1800023fe  xor     ecx, ecx
0x180002400  cpuid
0x180002402  mov     r11d, ebx
0x180002405  jmp     short loc_18000240C
0x180002407  xor     r9d, r9d
0x18000240a  xor     esi, esi
0x18000240c  mov     rax, cs:__isa_inverted
0x180002413  and     rax, 0FFFFFFFFFFFFFFFEh
0x180002417  mov     cs:__isa_available, 1
0x180002421  mov     cs:__isa_enabled, 2
0x18000242b  mov     cs:__isa_inverted, rax
0x180002432  bt      edi, 14h
0x180002436  jnb     short loc_180002457
0x180002438  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000243c  mov     cs:__isa_available, 2
0x180002446  mov     cs:__isa_inverted, rax
0x18000244d  mov     cs:__isa_enabled, 6
0x180002457  bt      edi, 1Bh
0x18000245b  jnb     loc_180002598
0x180002461  xor     ecx, ecx
0x180002463  xgetbv
0x180002466  shl     rdx, 20h
0x18000246a  or      rdx, rax
0x18000246d  mov     [rsp+38h+arg_0], rdx
0x180002472  bt      edi, 1Ch
0x180002476  jnb     loc_18000257C
0x18000247c  mov     rax, [rsp+38h+arg_0]
0x180002481  and     al, 6
0x180002483  cmp     al, 6
0x180002485  jnz     loc_18000257C
0x18000248b  mov     eax, cs:__isa_enabled
0x180002491  mov     dl, 0E0h
0x180002493  or      eax, 8
0x180002496  mov     cs:__isa_available, 3
0x1800024a0  mov     cs:__isa_enabled, eax
0x1800024a6  test    r9b, 20h
0x1800024aa  jz      short loc_18000250E
0x1800024ac  or      eax, 20h
0x1800024af  mov     cs:__isa_available, 5
0x1800024b9  mov     cs:__isa_enabled, eax
0x1800024bf  mov     ecx, 0D0030000h
0x1800024c4  mov     rax, cs:__isa_inverted
0x1800024cb  and     r9d, ecx
0x1800024ce  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800024d2  mov     cs:__isa_inverted, rax
0x1800024d9  cmp     r9d, ecx
0x1800024dc  jnz     short loc_180002515
0x1800024de  mov     rax, [rsp+38h+arg_0]
0x1800024e3  and     al, dl
0x1800024e5  cmp     al, dl
0x1800024e7  jnz     short loc_18000250E
0x1800024e9  mov     rax, cs:__isa_inverted
0x1800024f0  or      cs:__isa_enabled, 40h
0x1800024f7  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800024fb  mov     cs:__isa_available, 6
0x180002505  mov     cs:__isa_inverted, rax
0x18000250c  jmp     short loc_180002515
0x18000250e  mov     rax, cs:__isa_inverted
0x180002515  bt      esi, 17h
0x180002519  jnb     short loc_180002527
0x18000251b  btr     rax, 18h
0x180002520  mov     cs:__isa_inverted, rax
0x180002527  bt      r10d, 13h
0x18000252c  jnb     short loc_18000257C
0x18000252e  mov     rax, [rsp+38h+arg_0]
0x180002533  and     al, dl
0x180002535  cmp     al, dl
0x180002537  jnz     short loc_18000257C
0x180002539  mov     rdx, cs:__isa_inverted
0x180002540  mov     eax, r11d
0x180002543  shr     rax, 10h
0x180002547  mov     ecx, r11d
0x18000254a  and     eax, 6
0x18000254d  and     ecx, 400FFh
0x180002553  or      rax, 1000029h
0x180002559  mov     cs:__avx10_version, ecx
0x18000255f  not     rax
0x180002562  and     rdx, rax
0x180002565  mov     cs:__isa_inverted, rdx
0x18000256c  cmp     cl, 1
0x18000256f  jbe     short loc_18000257C
0x180002571  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002575  mov     cs:__isa_inverted, rdx
0x18000257c  bt      r10d, 15h
0x180002581  jnb     short loc_180002598
0x180002583  mov     rax, [rsp+38h+arg_0]
0x180002588  bt      rax, 13h
0x18000258d  jnb     short loc_180002598
0x18000258f  btr     cs:__isa_inverted, 7
0x180002598  xor     eax, eax
0x18000259a  add     rsp, 18h
0x18000259e  pop     rdi
0x18000259f  pop     rsi
0x1800025a0  pop     rbp
0x1800025a1  pop     rbx
0x1800025a2  retn
```
