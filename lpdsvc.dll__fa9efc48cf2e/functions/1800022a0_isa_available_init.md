# __isa_available_init

- ea: `0x1800022a0`
- end: `0x180002523`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e78`
- `0x180001fb4`

## callees

- `0x1800022a0`

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
0x1800022a0  push    rbx
0x1800022a2  push    rbp
0x1800022a3  push    rsi
0x1800022a4  push    rdi
0x1800022a5  sub     rsp, 18h
0x1800022a9  xor     eax, eax
0x1800022ab  xor     ecx, ecx
0x1800022ad  cpuid
0x1800022af  xor     ecx, 6C65746Eh
0x1800022b5  xor     edx, 49656E69h
0x1800022bb  or      edx, ecx
0x1800022bd  mov     ebp, eax
0x1800022bf  mov     eax, 1
0x1800022c4  xor     ebx, 756E6547h
0x1800022ca  or      edx, ebx
0x1800022cc  lea     ecx, [rax-1]
0x1800022cf  cpuid
0x1800022d1  mov     edi, ecx
0x1800022d3  jnz     short loc_180002333
0x1800022d5  and     eax, 0FFF3FF0h
0x1800022da  mov     cs:__memset_fast_string_threshold, 8000h
0x1800022e5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800022f0  cmp     eax, 106C0h
0x1800022f5  jz      short loc_18000231F
0x1800022f7  cmp     eax, 20660h
0x1800022fc  jz      short loc_18000231F
0x1800022fe  cmp     eax, 20670h
0x180002303  jz      short loc_18000231F
0x180002305  add     eax, 0FFFCF9B0h
0x18000230a  cmp     eax, 20h ; ' '
0x18000230d  ja      short loc_180002333
0x18000230f  mov     rcx, 100010001h
0x180002319  bt      rcx, rax
0x18000231d  jnb     short loc_180002333
0x18000231f  mov     r8d, cs:__favor
0x180002326  or      r8d, 1
0x18000232a  mov     cs:__favor, r8d
0x180002331  jmp     short loc_18000233A
0x180002333  mov     r8d, cs:__favor
0x18000233a  xor     r10d, r10d
0x18000233d  xor     r11d, r11d
0x180002340  cmp     ebp, 7
0x180002343  jl      short loc_180002387
0x180002345  xor     ecx, ecx
0x180002347  lea     eax, [r10+7]
0x18000234b  cpuid
0x18000234d  mov     esi, edx
0x18000234f  mov     r9d, ebx
0x180002352  bt      ebx, 9
0x180002356  jnb     short loc_180002363
0x180002358  or      r8d, 2
0x18000235c  mov     cs:__favor, r8d
0x180002363  cmp     eax, 1
0x180002366  jl      short loc_180002375
0x180002368  mov     eax, 7
0x18000236d  lea     ecx, [rax-6]
0x180002370  cpuid
0x180002372  mov     r10d, edx
0x180002375  mov     eax, 24h ; '$'
0x18000237a  cmp     ebp, eax
0x18000237c  jl      short loc_18000238C
0x18000237e  xor     ecx, ecx
0x180002380  cpuid
0x180002382  mov     r11d, ebx
0x180002385  jmp     short loc_18000238C
0x180002387  xor     r9d, r9d
0x18000238a  xor     esi, esi
0x18000238c  mov     rax, cs:__isa_inverted
0x180002393  and     rax, 0FFFFFFFFFFFFFFFEh
0x180002397  mov     cs:__isa_available, 1
0x1800023a1  mov     cs:__isa_enabled, 2
0x1800023ab  mov     cs:__isa_inverted, rax
0x1800023b2  bt      edi, 14h
0x1800023b6  jnb     short loc_1800023D7
0x1800023b8  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800023bc  mov     cs:__isa_available, 2
0x1800023c6  mov     cs:__isa_inverted, rax
0x1800023cd  mov     cs:__isa_enabled, 6
0x1800023d7  bt      edi, 1Bh
0x1800023db  jnb     loc_180002518
0x1800023e1  xor     ecx, ecx
0x1800023e3  xgetbv
0x1800023e6  shl     rdx, 20h
0x1800023ea  or      rdx, rax
0x1800023ed  mov     [rsp+38h+arg_0], rdx
0x1800023f2  bt      edi, 1Ch
0x1800023f6  jnb     loc_1800024FC
0x1800023fc  mov     rax, [rsp+38h+arg_0]
0x180002401  and     al, 6
0x180002403  cmp     al, 6
0x180002405  jnz     loc_1800024FC
0x18000240b  mov     eax, cs:__isa_enabled
0x180002411  mov     dl, 0E0h
0x180002413  or      eax, 8
0x180002416  mov     cs:__isa_available, 3
0x180002420  mov     cs:__isa_enabled, eax
0x180002426  test    r9b, 20h
0x18000242a  jz      short loc_18000248E
0x18000242c  or      eax, 20h
0x18000242f  mov     cs:__isa_available, 5
0x180002439  mov     cs:__isa_enabled, eax
0x18000243f  mov     ecx, 0D0030000h
0x180002444  mov     rax, cs:__isa_inverted
0x18000244b  and     r9d, ecx
0x18000244e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180002452  mov     cs:__isa_inverted, rax
0x180002459  cmp     r9d, ecx
0x18000245c  jnz     short loc_180002495
0x18000245e  mov     rax, [rsp+38h+arg_0]
0x180002463  and     al, dl
0x180002465  cmp     al, dl
0x180002467  jnz     short loc_18000248E
0x180002469  mov     rax, cs:__isa_inverted
0x180002470  or      cs:__isa_enabled, 40h
0x180002477  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000247b  mov     cs:__isa_available, 6
0x180002485  mov     cs:__isa_inverted, rax
0x18000248c  jmp     short loc_180002495
0x18000248e  mov     rax, cs:__isa_inverted
0x180002495  bt      esi, 17h
0x180002499  jnb     short loc_1800024A7
0x18000249b  btr     rax, 18h
0x1800024a0  mov     cs:__isa_inverted, rax
0x1800024a7  bt      r10d, 13h
0x1800024ac  jnb     short loc_1800024FC
0x1800024ae  mov     rax, [rsp+38h+arg_0]
0x1800024b3  and     al, dl
0x1800024b5  cmp     al, dl
0x1800024b7  jnz     short loc_1800024FC
0x1800024b9  mov     rdx, cs:__isa_inverted
0x1800024c0  mov     eax, r11d
0x1800024c3  shr     rax, 10h
0x1800024c7  mov     ecx, r11d
0x1800024ca  and     eax, 6
0x1800024cd  and     ecx, 400FFh
0x1800024d3  or      rax, 1000029h
0x1800024d9  mov     cs:__avx10_version, ecx
0x1800024df  not     rax
0x1800024e2  and     rdx, rax
0x1800024e5  mov     cs:__isa_inverted, rdx
0x1800024ec  cmp     cl, 1
0x1800024ef  jbe     short loc_1800024FC
0x1800024f1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800024f5  mov     cs:__isa_inverted, rdx
0x1800024fc  bt      r10d, 15h
0x180002501  jnb     short loc_180002518
0x180002503  mov     rax, [rsp+38h+arg_0]
0x180002508  bt      rax, 13h
0x18000250d  jnb     short loc_180002518
0x18000250f  btr     cs:__isa_inverted, 7
0x180002518  xor     eax, eax
0x18000251a  add     rsp, 18h
0x18000251e  pop     rdi
0x18000251f  pop     rsi
0x180002520  pop     rbp
0x180002521  pop     rbx
0x180002522  retn
```
