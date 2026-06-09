# __isa_available_init

- ea: `0x180004e00`
- end: `0x180005083`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a2c`
- `0x180004b68`

## callees

- `0x180004e00`

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
0x180004e00  push    rbx
0x180004e02  push    rbp
0x180004e03  push    rsi
0x180004e04  push    rdi
0x180004e05  sub     rsp, 18h
0x180004e09  xor     eax, eax
0x180004e0b  xor     ecx, ecx
0x180004e0d  cpuid
0x180004e0f  xor     ecx, 6C65746Eh
0x180004e15  xor     edx, 49656E69h
0x180004e1b  or      edx, ecx
0x180004e1d  mov     ebp, eax
0x180004e1f  mov     eax, 1
0x180004e24  xor     ebx, 756E6547h
0x180004e2a  or      edx, ebx
0x180004e2c  lea     ecx, [rax-1]
0x180004e2f  cpuid
0x180004e31  mov     edi, ecx
0x180004e33  jnz     short loc_180004E93
0x180004e35  and     eax, 0FFF3FF0h
0x180004e3a  mov     cs:__memset_fast_string_threshold, 8000h
0x180004e45  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180004e50  cmp     eax, 106C0h
0x180004e55  jz      short loc_180004E7F
0x180004e57  cmp     eax, 20660h
0x180004e5c  jz      short loc_180004E7F
0x180004e5e  cmp     eax, 20670h
0x180004e63  jz      short loc_180004E7F
0x180004e65  add     eax, 0FFFCF9B0h
0x180004e6a  cmp     eax, 20h ; ' '
0x180004e6d  ja      short loc_180004E93
0x180004e6f  mov     rcx, 100010001h
0x180004e79  bt      rcx, rax
0x180004e7d  jnb     short loc_180004E93
0x180004e7f  mov     r8d, cs:__favor
0x180004e86  or      r8d, 1
0x180004e8a  mov     cs:__favor, r8d
0x180004e91  jmp     short loc_180004E9A
0x180004e93  mov     r8d, cs:__favor
0x180004e9a  xor     r10d, r10d
0x180004e9d  xor     r11d, r11d
0x180004ea0  cmp     ebp, 7
0x180004ea3  jl      short loc_180004EE7
0x180004ea5  xor     ecx, ecx
0x180004ea7  lea     eax, [r10+7]
0x180004eab  cpuid
0x180004ead  mov     esi, edx
0x180004eaf  mov     r9d, ebx
0x180004eb2  bt      ebx, 9
0x180004eb6  jnb     short loc_180004EC3
0x180004eb8  or      r8d, 2
0x180004ebc  mov     cs:__favor, r8d
0x180004ec3  cmp     eax, 1
0x180004ec6  jl      short loc_180004ED5
0x180004ec8  mov     eax, 7
0x180004ecd  lea     ecx, [rax-6]
0x180004ed0  cpuid
0x180004ed2  mov     r10d, edx
0x180004ed5  mov     eax, 24h ; '$'
0x180004eda  cmp     ebp, eax
0x180004edc  jl      short loc_180004EEC
0x180004ede  xor     ecx, ecx
0x180004ee0  cpuid
0x180004ee2  mov     r11d, ebx
0x180004ee5  jmp     short loc_180004EEC
0x180004ee7  xor     r9d, r9d
0x180004eea  xor     esi, esi
0x180004eec  mov     rax, cs:__isa_inverted
0x180004ef3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180004ef7  mov     cs:__isa_available, 1
0x180004f01  mov     cs:__isa_enabled, 2
0x180004f0b  mov     cs:__isa_inverted, rax
0x180004f12  bt      edi, 14h
0x180004f16  jnb     short loc_180004F37
0x180004f18  and     rax, 0FFFFFFFFFFFFFFEFh
0x180004f1c  mov     cs:__isa_available, 2
0x180004f26  mov     cs:__isa_inverted, rax
0x180004f2d  mov     cs:__isa_enabled, 6
0x180004f37  bt      edi, 1Bh
0x180004f3b  jnb     loc_180005078
0x180004f41  xor     ecx, ecx
0x180004f43  xgetbv
0x180004f46  shl     rdx, 20h
0x180004f4a  or      rdx, rax
0x180004f4d  mov     [rsp+38h+arg_0], rdx
0x180004f52  bt      edi, 1Ch
0x180004f56  jnb     loc_18000505C
0x180004f5c  mov     rax, [rsp+38h+arg_0]
0x180004f61  and     al, 6
0x180004f63  cmp     al, 6
0x180004f65  jnz     loc_18000505C
0x180004f6b  mov     eax, cs:__isa_enabled
0x180004f71  mov     dl, 0E0h
0x180004f73  or      eax, 8
0x180004f76  mov     cs:__isa_available, 3
0x180004f80  mov     cs:__isa_enabled, eax
0x180004f86  test    r9b, 20h
0x180004f8a  jz      short loc_180004FEE
0x180004f8c  or      eax, 20h
0x180004f8f  mov     cs:__isa_available, 5
0x180004f99  mov     cs:__isa_enabled, eax
0x180004f9f  mov     ecx, 0D0030000h
0x180004fa4  mov     rax, cs:__isa_inverted
0x180004fab  and     r9d, ecx
0x180004fae  and     rax, 0FFFFFFFFFFFFFFFDh
0x180004fb2  mov     cs:__isa_inverted, rax
0x180004fb9  cmp     r9d, ecx
0x180004fbc  jnz     short loc_180004FF5
0x180004fbe  mov     rax, [rsp+38h+arg_0]
0x180004fc3  and     al, dl
0x180004fc5  cmp     al, dl
0x180004fc7  jnz     short loc_180004FEE
0x180004fc9  mov     rax, cs:__isa_inverted
0x180004fd0  or      cs:__isa_enabled, 40h
0x180004fd7  and     rax, 0FFFFFFFFFFFFFFDBh
0x180004fdb  mov     cs:__isa_available, 6
0x180004fe5  mov     cs:__isa_inverted, rax
0x180004fec  jmp     short loc_180004FF5
0x180004fee  mov     rax, cs:__isa_inverted
0x180004ff5  bt      esi, 17h
0x180004ff9  jnb     short loc_180005007
0x180004ffb  btr     rax, 18h
0x180005000  mov     cs:__isa_inverted, rax
0x180005007  bt      r10d, 13h
0x18000500c  jnb     short loc_18000505C
0x18000500e  mov     rax, [rsp+38h+arg_0]
0x180005013  and     al, dl
0x180005015  cmp     al, dl
0x180005017  jnz     short loc_18000505C
0x180005019  mov     rdx, cs:__isa_inverted
0x180005020  mov     eax, r11d
0x180005023  shr     rax, 10h
0x180005027  mov     ecx, r11d
0x18000502a  and     eax, 6
0x18000502d  and     ecx, 400FFh
0x180005033  or      rax, 1000029h
0x180005039  mov     cs:__avx10_version, ecx
0x18000503f  not     rax
0x180005042  and     rdx, rax
0x180005045  mov     cs:__isa_inverted, rdx
0x18000504c  cmp     cl, 1
0x18000504f  jbe     short loc_18000505C
0x180005051  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180005055  mov     cs:__isa_inverted, rdx
0x18000505c  bt      r10d, 15h
0x180005061  jnb     short loc_180005078
0x180005063  mov     rax, [rsp+38h+arg_0]
0x180005068  bt      rax, 13h
0x18000506d  jnb     short loc_180005078
0x18000506f  btr     cs:__isa_inverted, 7
0x180005078  xor     eax, eax
0x18000507a  add     rsp, 18h
0x18000507e  pop     rdi
0x18000507f  pop     rsi
0x180005080  pop     rbp
0x180005081  pop     rbx
0x180005082  retn
```
