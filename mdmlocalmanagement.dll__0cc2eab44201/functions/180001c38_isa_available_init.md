# __isa_available_init

- ea: `0x180001c38`
- end: `0x180001ebb`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016c4`
- `0x180001800`

## callees

- `0x180001c38`

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
0x180001c38  push    rbx
0x180001c3a  push    rbp
0x180001c3b  push    rsi
0x180001c3c  push    rdi
0x180001c3d  sub     rsp, 18h
0x180001c41  xor     eax, eax
0x180001c43  xor     ecx, ecx
0x180001c45  cpuid
0x180001c47  xor     ecx, 6C65746Eh
0x180001c4d  xor     edx, 49656E69h
0x180001c53  or      edx, ecx
0x180001c55  mov     ebp, eax
0x180001c57  mov     eax, 1
0x180001c5c  xor     ebx, 756E6547h
0x180001c62  or      edx, ebx
0x180001c64  lea     ecx, [rax-1]
0x180001c67  cpuid
0x180001c69  mov     edi, ecx
0x180001c6b  jnz     short loc_180001CCB
0x180001c6d  and     eax, 0FFF3FF0h
0x180001c72  mov     cs:__memset_fast_string_threshold, 8000h
0x180001c7d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001c88  cmp     eax, 106C0h
0x180001c8d  jz      short loc_180001CB7
0x180001c8f  cmp     eax, 20660h
0x180001c94  jz      short loc_180001CB7
0x180001c96  cmp     eax, 20670h
0x180001c9b  jz      short loc_180001CB7
0x180001c9d  add     eax, 0FFFCF9B0h
0x180001ca2  cmp     eax, 20h ; ' '
0x180001ca5  ja      short loc_180001CCB
0x180001ca7  mov     rcx, 100010001h
0x180001cb1  bt      rcx, rax
0x180001cb5  jnb     short loc_180001CCB
0x180001cb7  mov     r8d, cs:__favor
0x180001cbe  or      r8d, 1
0x180001cc2  mov     cs:__favor, r8d
0x180001cc9  jmp     short loc_180001CD2
0x180001ccb  mov     r8d, cs:__favor
0x180001cd2  xor     r10d, r10d
0x180001cd5  xor     r11d, r11d
0x180001cd8  cmp     ebp, 7
0x180001cdb  jl      short loc_180001D1F
0x180001cdd  xor     ecx, ecx
0x180001cdf  lea     eax, [r10+7]
0x180001ce3  cpuid
0x180001ce5  mov     esi, edx
0x180001ce7  mov     r9d, ebx
0x180001cea  bt      ebx, 9
0x180001cee  jnb     short loc_180001CFB
0x180001cf0  or      r8d, 2
0x180001cf4  mov     cs:__favor, r8d
0x180001cfb  cmp     eax, 1
0x180001cfe  jl      short loc_180001D0D
0x180001d00  mov     eax, 7
0x180001d05  lea     ecx, [rax-6]
0x180001d08  cpuid
0x180001d0a  mov     r10d, edx
0x180001d0d  mov     eax, 24h ; '$'
0x180001d12  cmp     ebp, eax
0x180001d14  jl      short loc_180001D24
0x180001d16  xor     ecx, ecx
0x180001d18  cpuid
0x180001d1a  mov     r11d, ebx
0x180001d1d  jmp     short loc_180001D24
0x180001d1f  xor     r9d, r9d
0x180001d22  xor     esi, esi
0x180001d24  mov     rax, cs:__isa_inverted
0x180001d2b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001d2f  mov     cs:__isa_available, 1
0x180001d39  mov     cs:__isa_enabled, 2
0x180001d43  mov     cs:__isa_inverted, rax
0x180001d4a  bt      edi, 14h
0x180001d4e  jnb     short loc_180001D6F
0x180001d50  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001d54  mov     cs:__isa_available, 2
0x180001d5e  mov     cs:__isa_inverted, rax
0x180001d65  mov     cs:__isa_enabled, 6
0x180001d6f  bt      edi, 1Bh
0x180001d73  jnb     loc_180001EB0
0x180001d79  xor     ecx, ecx
0x180001d7b  xgetbv
0x180001d7e  shl     rdx, 20h
0x180001d82  or      rdx, rax
0x180001d85  mov     [rsp+38h+arg_0], rdx
0x180001d8a  bt      edi, 1Ch
0x180001d8e  jnb     loc_180001E94
0x180001d94  mov     rax, [rsp+38h+arg_0]
0x180001d99  and     al, 6
0x180001d9b  cmp     al, 6
0x180001d9d  jnz     loc_180001E94
0x180001da3  mov     eax, cs:__isa_enabled
0x180001da9  mov     dl, 0E0h
0x180001dab  or      eax, 8
0x180001dae  mov     cs:__isa_available, 3
0x180001db8  mov     cs:__isa_enabled, eax
0x180001dbe  test    r9b, 20h
0x180001dc2  jz      short loc_180001E26
0x180001dc4  or      eax, 20h
0x180001dc7  mov     cs:__isa_available, 5
0x180001dd1  mov     cs:__isa_enabled, eax
0x180001dd7  mov     ecx, 0D0030000h
0x180001ddc  mov     rax, cs:__isa_inverted
0x180001de3  and     r9d, ecx
0x180001de6  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001dea  mov     cs:__isa_inverted, rax
0x180001df1  cmp     r9d, ecx
0x180001df4  jnz     short loc_180001E2D
0x180001df6  mov     rax, [rsp+38h+arg_0]
0x180001dfb  and     al, dl
0x180001dfd  cmp     al, dl
0x180001dff  jnz     short loc_180001E26
0x180001e01  mov     rax, cs:__isa_inverted
0x180001e08  or      cs:__isa_enabled, 40h
0x180001e0f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001e13  mov     cs:__isa_available, 6
0x180001e1d  mov     cs:__isa_inverted, rax
0x180001e24  jmp     short loc_180001E2D
0x180001e26  mov     rax, cs:__isa_inverted
0x180001e2d  bt      esi, 17h
0x180001e31  jnb     short loc_180001E3F
0x180001e33  btr     rax, 18h
0x180001e38  mov     cs:__isa_inverted, rax
0x180001e3f  bt      r10d, 13h
0x180001e44  jnb     short loc_180001E94
0x180001e46  mov     rax, [rsp+38h+arg_0]
0x180001e4b  and     al, dl
0x180001e4d  cmp     al, dl
0x180001e4f  jnz     short loc_180001E94
0x180001e51  mov     rdx, cs:__isa_inverted
0x180001e58  mov     eax, r11d
0x180001e5b  shr     rax, 10h
0x180001e5f  mov     ecx, r11d
0x180001e62  and     eax, 6
0x180001e65  and     ecx, 400FFh
0x180001e6b  or      rax, 1000029h
0x180001e71  mov     cs:__avx10_version, ecx
0x180001e77  not     rax
0x180001e7a  and     rdx, rax
0x180001e7d  mov     cs:__isa_inverted, rdx
0x180001e84  cmp     cl, 1
0x180001e87  jbe     short loc_180001E94
0x180001e89  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001e8d  mov     cs:__isa_inverted, rdx
0x180001e94  bt      r10d, 15h
0x180001e99  jnb     short loc_180001EB0
0x180001e9b  mov     rax, [rsp+38h+arg_0]
0x180001ea0  bt      rax, 13h
0x180001ea5  jnb     short loc_180001EB0
0x180001ea7  btr     cs:__isa_inverted, 7
0x180001eb0  xor     eax, eax
0x180001eb2  add     rsp, 18h
0x180001eb6  pop     rdi
0x180001eb7  pop     rsi
0x180001eb8  pop     rbp
0x180001eb9  pop     rbx
0x180001eba  retn
```
