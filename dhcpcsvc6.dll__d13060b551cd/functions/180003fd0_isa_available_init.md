# __isa_available_init

- ea: `0x180003fd0`
- end: `0x180004253`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bfc`
- `0x180003d38`

## callees

- `0x180003fd0`

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
0x180003fd0  push    rbx
0x180003fd2  push    rbp
0x180003fd3  push    rsi
0x180003fd4  push    rdi
0x180003fd5  sub     rsp, 18h
0x180003fd9  xor     eax, eax
0x180003fdb  xor     ecx, ecx
0x180003fdd  cpuid
0x180003fdf  xor     ecx, 6C65746Eh
0x180003fe5  xor     edx, 49656E69h
0x180003feb  or      edx, ecx
0x180003fed  mov     ebp, eax
0x180003fef  mov     eax, 1
0x180003ff4  xor     ebx, 756E6547h
0x180003ffa  or      edx, ebx
0x180003ffc  lea     ecx, [rax-1]
0x180003fff  cpuid
0x180004001  mov     edi, ecx
0x180004003  jnz     short loc_180004063
0x180004005  and     eax, 0FFF3FF0h
0x18000400a  mov     cs:__memset_fast_string_threshold, 8000h
0x180004015  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180004020  cmp     eax, 106C0h
0x180004025  jz      short loc_18000404F
0x180004027  cmp     eax, 20660h
0x18000402c  jz      short loc_18000404F
0x18000402e  cmp     eax, 20670h
0x180004033  jz      short loc_18000404F
0x180004035  add     eax, 0FFFCF9B0h
0x18000403a  cmp     eax, 20h ; ' '
0x18000403d  ja      short loc_180004063
0x18000403f  mov     rcx, 100010001h
0x180004049  bt      rcx, rax
0x18000404d  jnb     short loc_180004063
0x18000404f  mov     r8d, cs:__favor
0x180004056  or      r8d, 1
0x18000405a  mov     cs:__favor, r8d
0x180004061  jmp     short loc_18000406A
0x180004063  mov     r8d, cs:__favor
0x18000406a  xor     r10d, r10d
0x18000406d  xor     r11d, r11d
0x180004070  cmp     ebp, 7
0x180004073  jl      short loc_1800040B7
0x180004075  xor     ecx, ecx
0x180004077  lea     eax, [r10+7]
0x18000407b  cpuid
0x18000407d  mov     esi, edx
0x18000407f  mov     r9d, ebx
0x180004082  bt      ebx, 9
0x180004086  jnb     short loc_180004093
0x180004088  or      r8d, 2
0x18000408c  mov     cs:__favor, r8d
0x180004093  cmp     eax, 1
0x180004096  jl      short loc_1800040A5
0x180004098  mov     eax, 7
0x18000409d  lea     ecx, [rax-6]
0x1800040a0  cpuid
0x1800040a2  mov     r10d, edx
0x1800040a5  mov     eax, 24h ; '$'
0x1800040aa  cmp     ebp, eax
0x1800040ac  jl      short loc_1800040BC
0x1800040ae  xor     ecx, ecx
0x1800040b0  cpuid
0x1800040b2  mov     r11d, ebx
0x1800040b5  jmp     short loc_1800040BC
0x1800040b7  xor     r9d, r9d
0x1800040ba  xor     esi, esi
0x1800040bc  mov     rax, cs:__isa_inverted
0x1800040c3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800040c7  mov     cs:__isa_available, 1
0x1800040d1  mov     cs:__isa_enabled, 2
0x1800040db  mov     cs:__isa_inverted, rax
0x1800040e2  bt      edi, 14h
0x1800040e6  jnb     short loc_180004107
0x1800040e8  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800040ec  mov     cs:__isa_available, 2
0x1800040f6  mov     cs:__isa_inverted, rax
0x1800040fd  mov     cs:__isa_enabled, 6
0x180004107  bt      edi, 1Bh
0x18000410b  jnb     loc_180004248
0x180004111  xor     ecx, ecx
0x180004113  xgetbv
0x180004116  shl     rdx, 20h
0x18000411a  or      rdx, rax
0x18000411d  mov     [rsp+38h+arg_0], rdx
0x180004122  bt      edi, 1Ch
0x180004126  jnb     loc_18000422C
0x18000412c  mov     rax, [rsp+38h+arg_0]
0x180004131  and     al, 6
0x180004133  cmp     al, 6
0x180004135  jnz     loc_18000422C
0x18000413b  mov     eax, cs:__isa_enabled
0x180004141  mov     dl, 0E0h
0x180004143  or      eax, 8
0x180004146  mov     cs:__isa_available, 3
0x180004150  mov     cs:__isa_enabled, eax
0x180004156  test    r9b, 20h
0x18000415a  jz      short loc_1800041BE
0x18000415c  or      eax, 20h
0x18000415f  mov     cs:__isa_available, 5
0x180004169  mov     cs:__isa_enabled, eax
0x18000416f  mov     ecx, 0D0030000h
0x180004174  mov     rax, cs:__isa_inverted
0x18000417b  and     r9d, ecx
0x18000417e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180004182  mov     cs:__isa_inverted, rax
0x180004189  cmp     r9d, ecx
0x18000418c  jnz     short loc_1800041C5
0x18000418e  mov     rax, [rsp+38h+arg_0]
0x180004193  and     al, dl
0x180004195  cmp     al, dl
0x180004197  jnz     short loc_1800041BE
0x180004199  mov     rax, cs:__isa_inverted
0x1800041a0  or      cs:__isa_enabled, 40h
0x1800041a7  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800041ab  mov     cs:__isa_available, 6
0x1800041b5  mov     cs:__isa_inverted, rax
0x1800041bc  jmp     short loc_1800041C5
0x1800041be  mov     rax, cs:__isa_inverted
0x1800041c5  bt      esi, 17h
0x1800041c9  jnb     short loc_1800041D7
0x1800041cb  btr     rax, 18h
0x1800041d0  mov     cs:__isa_inverted, rax
0x1800041d7  bt      r10d, 13h
0x1800041dc  jnb     short loc_18000422C
0x1800041de  mov     rax, [rsp+38h+arg_0]
0x1800041e3  and     al, dl
0x1800041e5  cmp     al, dl
0x1800041e7  jnz     short loc_18000422C
0x1800041e9  mov     rdx, cs:__isa_inverted
0x1800041f0  mov     eax, r11d
0x1800041f3  shr     rax, 10h
0x1800041f7  mov     ecx, r11d
0x1800041fa  and     eax, 6
0x1800041fd  and     ecx, 400FFh
0x180004203  or      rax, 1000029h
0x180004209  mov     cs:__avx10_version, ecx
0x18000420f  not     rax
0x180004212  and     rdx, rax
0x180004215  mov     cs:__isa_inverted, rdx
0x18000421c  cmp     cl, 1
0x18000421f  jbe     short loc_18000422C
0x180004221  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180004225  mov     cs:__isa_inverted, rdx
0x18000422c  bt      r10d, 15h
0x180004231  jnb     short loc_180004248
0x180004233  mov     rax, [rsp+38h+arg_0]
0x180004238  bt      rax, 13h
0x18000423d  jnb     short loc_180004248
0x18000423f  btr     cs:__isa_inverted, 7
0x180004248  xor     eax, eax
0x18000424a  add     rsp, 18h
0x18000424e  pop     rdi
0x18000424f  pop     rsi
0x180004250  pop     rbp
0x180004251  pop     rbx
0x180004252  retn
```
