# __isa_available_init

- ea: `0x180007820`
- end: `0x180007aa3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000744c`
- `0x180007588`

## callees

- `0x180007820`

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
0x180007820  push    rbx
0x180007822  push    rbp
0x180007823  push    rsi
0x180007824  push    rdi
0x180007825  sub     rsp, 18h
0x180007829  xor     eax, eax
0x18000782b  xor     ecx, ecx
0x18000782d  cpuid
0x18000782f  xor     ecx, 6C65746Eh
0x180007835  xor     edx, 49656E69h
0x18000783b  or      edx, ecx
0x18000783d  mov     ebp, eax
0x18000783f  mov     eax, 1
0x180007844  xor     ebx, 756E6547h
0x18000784a  or      edx, ebx
0x18000784c  lea     ecx, [rax-1]
0x18000784f  cpuid
0x180007851  mov     edi, ecx
0x180007853  jnz     short loc_1800078B3
0x180007855  and     eax, 0FFF3FF0h
0x18000785a  mov     cs:__memset_fast_string_threshold, 8000h
0x180007865  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180007870  cmp     eax, 106C0h
0x180007875  jz      short loc_18000789F
0x180007877  cmp     eax, 20660h
0x18000787c  jz      short loc_18000789F
0x18000787e  cmp     eax, 20670h
0x180007883  jz      short loc_18000789F
0x180007885  add     eax, 0FFFCF9B0h
0x18000788a  cmp     eax, 20h ; ' '
0x18000788d  ja      short loc_1800078B3
0x18000788f  mov     rcx, 100010001h
0x180007899  bt      rcx, rax
0x18000789d  jnb     short loc_1800078B3
0x18000789f  mov     r8d, cs:__favor
0x1800078a6  or      r8d, 1
0x1800078aa  mov     cs:__favor, r8d
0x1800078b1  jmp     short loc_1800078BA
0x1800078b3  mov     r8d, cs:__favor
0x1800078ba  xor     r10d, r10d
0x1800078bd  xor     r11d, r11d
0x1800078c0  cmp     ebp, 7
0x1800078c3  jl      short loc_180007907
0x1800078c5  xor     ecx, ecx
0x1800078c7  lea     eax, [r10+7]
0x1800078cb  cpuid
0x1800078cd  mov     esi, edx
0x1800078cf  mov     r9d, ebx
0x1800078d2  bt      ebx, 9
0x1800078d6  jnb     short loc_1800078E3
0x1800078d8  or      r8d, 2
0x1800078dc  mov     cs:__favor, r8d
0x1800078e3  cmp     eax, 1
0x1800078e6  jl      short loc_1800078F5
0x1800078e8  mov     eax, 7
0x1800078ed  lea     ecx, [rax-6]
0x1800078f0  cpuid
0x1800078f2  mov     r10d, edx
0x1800078f5  mov     eax, 24h ; '$'
0x1800078fa  cmp     ebp, eax
0x1800078fc  jl      short loc_18000790C
0x1800078fe  xor     ecx, ecx
0x180007900  cpuid
0x180007902  mov     r11d, ebx
0x180007905  jmp     short loc_18000790C
0x180007907  xor     r9d, r9d
0x18000790a  xor     esi, esi
0x18000790c  mov     rax, cs:__isa_inverted
0x180007913  and     rax, 0FFFFFFFFFFFFFFFEh
0x180007917  mov     cs:__isa_available, 1
0x180007921  mov     cs:__isa_enabled, 2
0x18000792b  mov     cs:__isa_inverted, rax
0x180007932  bt      edi, 14h
0x180007936  jnb     short loc_180007957
0x180007938  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000793c  mov     cs:__isa_available, 2
0x180007946  mov     cs:__isa_inverted, rax
0x18000794d  mov     cs:__isa_enabled, 6
0x180007957  bt      edi, 1Bh
0x18000795b  jnb     loc_180007A98
0x180007961  xor     ecx, ecx
0x180007963  xgetbv
0x180007966  shl     rdx, 20h
0x18000796a  or      rdx, rax
0x18000796d  mov     [rsp+38h+arg_0], rdx
0x180007972  bt      edi, 1Ch
0x180007976  jnb     loc_180007A7C
0x18000797c  mov     rax, [rsp+38h+arg_0]
0x180007981  and     al, 6
0x180007983  cmp     al, 6
0x180007985  jnz     loc_180007A7C
0x18000798b  mov     eax, cs:__isa_enabled
0x180007991  mov     dl, 0E0h
0x180007993  or      eax, 8
0x180007996  mov     cs:__isa_available, 3
0x1800079a0  mov     cs:__isa_enabled, eax
0x1800079a6  test    r9b, 20h
0x1800079aa  jz      short loc_180007A0E
0x1800079ac  or      eax, 20h
0x1800079af  mov     cs:__isa_available, 5
0x1800079b9  mov     cs:__isa_enabled, eax
0x1800079bf  mov     ecx, 0D0030000h
0x1800079c4  mov     rax, cs:__isa_inverted
0x1800079cb  and     r9d, ecx
0x1800079ce  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800079d2  mov     cs:__isa_inverted, rax
0x1800079d9  cmp     r9d, ecx
0x1800079dc  jnz     short loc_180007A15
0x1800079de  mov     rax, [rsp+38h+arg_0]
0x1800079e3  and     al, dl
0x1800079e5  cmp     al, dl
0x1800079e7  jnz     short loc_180007A0E
0x1800079e9  mov     rax, cs:__isa_inverted
0x1800079f0  or      cs:__isa_enabled, 40h
0x1800079f7  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800079fb  mov     cs:__isa_available, 6
0x180007a05  mov     cs:__isa_inverted, rax
0x180007a0c  jmp     short loc_180007A15
0x180007a0e  mov     rax, cs:__isa_inverted
0x180007a15  bt      esi, 17h
0x180007a19  jnb     short loc_180007A27
0x180007a1b  btr     rax, 18h
0x180007a20  mov     cs:__isa_inverted, rax
0x180007a27  bt      r10d, 13h
0x180007a2c  jnb     short loc_180007A7C
0x180007a2e  mov     rax, [rsp+38h+arg_0]
0x180007a33  and     al, dl
0x180007a35  cmp     al, dl
0x180007a37  jnz     short loc_180007A7C
0x180007a39  mov     rdx, cs:__isa_inverted
0x180007a40  mov     eax, r11d
0x180007a43  shr     rax, 10h
0x180007a47  mov     ecx, r11d
0x180007a4a  and     eax, 6
0x180007a4d  and     ecx, 400FFh
0x180007a53  or      rax, 1000029h
0x180007a59  mov     cs:__avx10_version, ecx
0x180007a5f  not     rax
0x180007a62  and     rdx, rax
0x180007a65  mov     cs:__isa_inverted, rdx
0x180007a6c  cmp     cl, 1
0x180007a6f  jbe     short loc_180007A7C
0x180007a71  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180007a75  mov     cs:__isa_inverted, rdx
0x180007a7c  bt      r10d, 15h
0x180007a81  jnb     short loc_180007A98
0x180007a83  mov     rax, [rsp+38h+arg_0]
0x180007a88  bt      rax, 13h
0x180007a8d  jnb     short loc_180007A98
0x180007a8f  btr     cs:__isa_inverted, 7
0x180007a98  xor     eax, eax
0x180007a9a  add     rsp, 18h
0x180007a9e  pop     rdi
0x180007a9f  pop     rsi
0x180007aa0  pop     rbp
0x180007aa1  pop     rbx
0x180007aa2  retn
```
