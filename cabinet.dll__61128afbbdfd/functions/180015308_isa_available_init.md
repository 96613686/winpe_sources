# __isa_available_init

- ea: `0x180015308`
- end: `0x18001558b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014f58`
- `0x180015094`

## callees

- `0x180015308`

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
0x180015308  push    rbx
0x18001530a  push    rbp
0x18001530b  push    rsi
0x18001530c  push    rdi
0x18001530d  sub     rsp, 18h
0x180015311  xor     eax, eax
0x180015313  xor     ecx, ecx
0x180015315  cpuid
0x180015317  xor     ecx, 6C65746Eh
0x18001531d  xor     edx, 49656E69h
0x180015323  or      edx, ecx
0x180015325  mov     ebp, eax
0x180015327  mov     eax, 1
0x18001532c  xor     ebx, 756E6547h
0x180015332  or      edx, ebx
0x180015334  lea     ecx, [rax-1]
0x180015337  cpuid
0x180015339  mov     edi, ecx
0x18001533b  jnz     short loc_18001539B
0x18001533d  and     eax, 0FFF3FF0h
0x180015342  mov     cs:__memset_fast_string_threshold, 8000h
0x18001534d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180015358  cmp     eax, 106C0h
0x18001535d  jz      short loc_180015387
0x18001535f  cmp     eax, 20660h
0x180015364  jz      short loc_180015387
0x180015366  cmp     eax, 20670h
0x18001536b  jz      short loc_180015387
0x18001536d  add     eax, 0FFFCF9B0h
0x180015372  cmp     eax, 20h ; ' '
0x180015375  ja      short loc_18001539B
0x180015377  mov     rcx, 100010001h
0x180015381  bt      rcx, rax
0x180015385  jnb     short loc_18001539B
0x180015387  mov     r8d, cs:__favor
0x18001538e  or      r8d, 1
0x180015392  mov     cs:__favor, r8d
0x180015399  jmp     short loc_1800153A2
0x18001539b  mov     r8d, cs:__favor
0x1800153a2  xor     r10d, r10d
0x1800153a5  xor     r11d, r11d
0x1800153a8  cmp     ebp, 7
0x1800153ab  jl      short loc_1800153EF
0x1800153ad  xor     ecx, ecx
0x1800153af  lea     eax, [r10+7]
0x1800153b3  cpuid
0x1800153b5  mov     esi, edx
0x1800153b7  mov     r9d, ebx
0x1800153ba  bt      ebx, 9
0x1800153be  jnb     short loc_1800153CB
0x1800153c0  or      r8d, 2
0x1800153c4  mov     cs:__favor, r8d
0x1800153cb  cmp     eax, 1
0x1800153ce  jl      short loc_1800153DD
0x1800153d0  mov     eax, 7
0x1800153d5  lea     ecx, [rax-6]
0x1800153d8  cpuid
0x1800153da  mov     r10d, edx
0x1800153dd  mov     eax, 24h ; '$'
0x1800153e2  cmp     ebp, eax
0x1800153e4  jl      short loc_1800153F4
0x1800153e6  xor     ecx, ecx
0x1800153e8  cpuid
0x1800153ea  mov     r11d, ebx
0x1800153ed  jmp     short loc_1800153F4
0x1800153ef  xor     r9d, r9d
0x1800153f2  xor     esi, esi
0x1800153f4  mov     rax, cs:__isa_inverted
0x1800153fb  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800153ff  mov     cs:__isa_available, 1
0x180015409  mov     cs:__isa_enabled, 2
0x180015413  mov     cs:__isa_inverted, rax
0x18001541a  bt      edi, 14h
0x18001541e  jnb     short loc_18001543F
0x180015420  and     rax, 0FFFFFFFFFFFFFFEFh
0x180015424  mov     cs:__isa_available, 2
0x18001542e  mov     cs:__isa_inverted, rax
0x180015435  mov     cs:__isa_enabled, 6
0x18001543f  bt      edi, 1Bh
0x180015443  jnb     loc_180015580
0x180015449  xor     ecx, ecx
0x18001544b  xgetbv
0x18001544e  shl     rdx, 20h
0x180015452  or      rdx, rax
0x180015455  mov     [rsp+38h+arg_0], rdx
0x18001545a  bt      edi, 1Ch
0x18001545e  jnb     loc_180015564
0x180015464  mov     rax, [rsp+38h+arg_0]
0x180015469  and     al, 6
0x18001546b  cmp     al, 6
0x18001546d  jnz     loc_180015564
0x180015473  mov     eax, cs:__isa_enabled
0x180015479  mov     dl, 0E0h
0x18001547b  or      eax, 8
0x18001547e  mov     cs:__isa_available, 3
0x180015488  mov     cs:__isa_enabled, eax
0x18001548e  test    r9b, 20h
0x180015492  jz      short loc_1800154F6
0x180015494  or      eax, 20h
0x180015497  mov     cs:__isa_available, 5
0x1800154a1  mov     cs:__isa_enabled, eax
0x1800154a7  mov     ecx, 0D0030000h
0x1800154ac  mov     rax, cs:__isa_inverted
0x1800154b3  and     r9d, ecx
0x1800154b6  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800154ba  mov     cs:__isa_inverted, rax
0x1800154c1  cmp     r9d, ecx
0x1800154c4  jnz     short loc_1800154FD
0x1800154c6  mov     rax, [rsp+38h+arg_0]
0x1800154cb  and     al, dl
0x1800154cd  cmp     al, dl
0x1800154cf  jnz     short loc_1800154F6
0x1800154d1  mov     rax, cs:__isa_inverted
0x1800154d8  or      cs:__isa_enabled, 40h
0x1800154df  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800154e3  mov     cs:__isa_available, 6
0x1800154ed  mov     cs:__isa_inverted, rax
0x1800154f4  jmp     short loc_1800154FD
0x1800154f6  mov     rax, cs:__isa_inverted
0x1800154fd  bt      esi, 17h
0x180015501  jnb     short loc_18001550F
0x180015503  btr     rax, 18h
0x180015508  mov     cs:__isa_inverted, rax
0x18001550f  bt      r10d, 13h
0x180015514  jnb     short loc_180015564
0x180015516  mov     rax, [rsp+38h+arg_0]
0x18001551b  and     al, dl
0x18001551d  cmp     al, dl
0x18001551f  jnz     short loc_180015564
0x180015521  mov     rdx, cs:__isa_inverted
0x180015528  mov     eax, r11d
0x18001552b  shr     rax, 10h
0x18001552f  mov     ecx, r11d
0x180015532  and     eax, 6
0x180015535  and     ecx, 400FFh
0x18001553b  or      rax, 1000029h
0x180015541  mov     cs:__avx10_version, ecx
0x180015547  not     rax
0x18001554a  and     rdx, rax
0x18001554d  mov     cs:__isa_inverted, rdx
0x180015554  cmp     cl, 1
0x180015557  jbe     short loc_180015564
0x180015559  and     rdx, 0FFFFFFFFFFFFFFBFh
0x18001555d  mov     cs:__isa_inverted, rdx
0x180015564  bt      r10d, 15h
0x180015569  jnb     short loc_180015580
0x18001556b  mov     rax, [rsp+38h+arg_0]
0x180015570  bt      rax, 13h
0x180015575  jnb     short loc_180015580
0x180015577  btr     cs:__isa_inverted, 7
0x180015580  xor     eax, eax
0x180015582  add     rsp, 18h
0x180015586  pop     rdi
0x180015587  pop     rsi
0x180015588  pop     rbp
0x180015589  pop     rbx
0x18001558a  retn
```
