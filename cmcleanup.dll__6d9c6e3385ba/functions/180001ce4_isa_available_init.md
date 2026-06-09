# __isa_available_init

- ea: `0x180001ce4`
- end: `0x180001f67`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015dc`
- `0x180001718`

## callees

- `0x180001ce4`

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
0x180001ce4  push    rbx
0x180001ce6  push    rbp
0x180001ce7  push    rsi
0x180001ce8  push    rdi
0x180001ce9  sub     rsp, 18h
0x180001ced  xor     eax, eax
0x180001cef  xor     ecx, ecx
0x180001cf1  cpuid
0x180001cf3  xor     ecx, 6C65746Eh
0x180001cf9  xor     edx, 49656E69h
0x180001cff  or      edx, ecx
0x180001d01  mov     ebp, eax
0x180001d03  mov     eax, 1
0x180001d08  xor     ebx, 756E6547h
0x180001d0e  or      edx, ebx
0x180001d10  lea     ecx, [rax-1]
0x180001d13  cpuid
0x180001d15  mov     edi, ecx
0x180001d17  jnz     short loc_180001D77
0x180001d19  and     eax, 0FFF3FF0h
0x180001d1e  mov     cs:__memset_fast_string_threshold, 8000h
0x180001d29  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001d34  cmp     eax, 106C0h
0x180001d39  jz      short loc_180001D63
0x180001d3b  cmp     eax, 20660h
0x180001d40  jz      short loc_180001D63
0x180001d42  cmp     eax, 20670h
0x180001d47  jz      short loc_180001D63
0x180001d49  add     eax, 0FFFCF9B0h
0x180001d4e  cmp     eax, 20h ; ' '
0x180001d51  ja      short loc_180001D77
0x180001d53  mov     rcx, 100010001h
0x180001d5d  bt      rcx, rax
0x180001d61  jnb     short loc_180001D77
0x180001d63  mov     r8d, cs:__favor
0x180001d6a  or      r8d, 1
0x180001d6e  mov     cs:__favor, r8d
0x180001d75  jmp     short loc_180001D7E
0x180001d77  mov     r8d, cs:__favor
0x180001d7e  xor     r10d, r10d
0x180001d81  xor     r11d, r11d
0x180001d84  cmp     ebp, 7
0x180001d87  jl      short loc_180001DCB
0x180001d89  xor     ecx, ecx
0x180001d8b  lea     eax, [r10+7]
0x180001d8f  cpuid
0x180001d91  mov     esi, edx
0x180001d93  mov     r9d, ebx
0x180001d96  bt      ebx, 9
0x180001d9a  jnb     short loc_180001DA7
0x180001d9c  or      r8d, 2
0x180001da0  mov     cs:__favor, r8d
0x180001da7  cmp     eax, 1
0x180001daa  jl      short loc_180001DB9
0x180001dac  mov     eax, 7
0x180001db1  lea     ecx, [rax-6]
0x180001db4  cpuid
0x180001db6  mov     r10d, edx
0x180001db9  mov     eax, 24h ; '$'
0x180001dbe  cmp     ebp, eax
0x180001dc0  jl      short loc_180001DD0
0x180001dc2  xor     ecx, ecx
0x180001dc4  cpuid
0x180001dc6  mov     r11d, ebx
0x180001dc9  jmp     short loc_180001DD0
0x180001dcb  xor     r9d, r9d
0x180001dce  xor     esi, esi
0x180001dd0  mov     rax, cs:__isa_inverted
0x180001dd7  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001ddb  mov     cs:__isa_available, 1
0x180001de5  mov     cs:__isa_enabled, 2
0x180001def  mov     cs:__isa_inverted, rax
0x180001df6  bt      edi, 14h
0x180001dfa  jnb     short loc_180001E1B
0x180001dfc  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001e00  mov     cs:__isa_available, 2
0x180001e0a  mov     cs:__isa_inverted, rax
0x180001e11  mov     cs:__isa_enabled, 6
0x180001e1b  bt      edi, 1Bh
0x180001e1f  jnb     loc_180001F5C
0x180001e25  xor     ecx, ecx
0x180001e27  xgetbv
0x180001e2a  shl     rdx, 20h
0x180001e2e  or      rdx, rax
0x180001e31  mov     [rsp+38h+arg_0], rdx
0x180001e36  bt      edi, 1Ch
0x180001e3a  jnb     loc_180001F40
0x180001e40  mov     rax, [rsp+38h+arg_0]
0x180001e45  and     al, 6
0x180001e47  cmp     al, 6
0x180001e49  jnz     loc_180001F40
0x180001e4f  mov     eax, cs:__isa_enabled
0x180001e55  mov     dl, 0E0h
0x180001e57  or      eax, 8
0x180001e5a  mov     cs:__isa_available, 3
0x180001e64  mov     cs:__isa_enabled, eax
0x180001e6a  test    r9b, 20h
0x180001e6e  jz      short loc_180001ED2
0x180001e70  or      eax, 20h
0x180001e73  mov     cs:__isa_available, 5
0x180001e7d  mov     cs:__isa_enabled, eax
0x180001e83  mov     ecx, 0D0030000h
0x180001e88  mov     rax, cs:__isa_inverted
0x180001e8f  and     r9d, ecx
0x180001e92  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001e96  mov     cs:__isa_inverted, rax
0x180001e9d  cmp     r9d, ecx
0x180001ea0  jnz     short loc_180001ED9
0x180001ea2  mov     rax, [rsp+38h+arg_0]
0x180001ea7  and     al, dl
0x180001ea9  cmp     al, dl
0x180001eab  jnz     short loc_180001ED2
0x180001ead  mov     rax, cs:__isa_inverted
0x180001eb4  or      cs:__isa_enabled, 40h
0x180001ebb  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001ebf  mov     cs:__isa_available, 6
0x180001ec9  mov     cs:__isa_inverted, rax
0x180001ed0  jmp     short loc_180001ED9
0x180001ed2  mov     rax, cs:__isa_inverted
0x180001ed9  bt      esi, 17h
0x180001edd  jnb     short loc_180001EEB
0x180001edf  btr     rax, 18h
0x180001ee4  mov     cs:__isa_inverted, rax
0x180001eeb  bt      r10d, 13h
0x180001ef0  jnb     short loc_180001F40
0x180001ef2  mov     rax, [rsp+38h+arg_0]
0x180001ef7  and     al, dl
0x180001ef9  cmp     al, dl
0x180001efb  jnz     short loc_180001F40
0x180001efd  mov     rdx, cs:__isa_inverted
0x180001f04  mov     eax, r11d
0x180001f07  shr     rax, 10h
0x180001f0b  mov     ecx, r11d
0x180001f0e  and     eax, 6
0x180001f11  and     ecx, 400FFh
0x180001f17  or      rax, 1000029h
0x180001f1d  mov     cs:__avx10_version, ecx
0x180001f23  not     rax
0x180001f26  and     rdx, rax
0x180001f29  mov     cs:__isa_inverted, rdx
0x180001f30  cmp     cl, 1
0x180001f33  jbe     short loc_180001F40
0x180001f35  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001f39  mov     cs:__isa_inverted, rdx
0x180001f40  bt      r10d, 15h
0x180001f45  jnb     short loc_180001F5C
0x180001f47  mov     rax, [rsp+38h+arg_0]
0x180001f4c  bt      rax, 13h
0x180001f51  jnb     short loc_180001F5C
0x180001f53  btr     cs:__isa_inverted, 7
0x180001f5c  xor     eax, eax
0x180001f5e  add     rsp, 18h
0x180001f62  pop     rdi
0x180001f63  pop     rsi
0x180001f64  pop     rbp
0x180001f65  pop     rbx
0x180001f66  retn
```
