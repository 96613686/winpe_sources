# __isa_available_init

- ea: `0x180001a00`
- end: `0x180001c83`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800014c4`
- `0x180001600`

## callees

- `0x180001a00`

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
0x180001a00  push    rbx
0x180001a02  push    rbp
0x180001a03  push    rsi
0x180001a04  push    rdi
0x180001a05  sub     rsp, 18h
0x180001a09  xor     eax, eax
0x180001a0b  xor     ecx, ecx
0x180001a0d  cpuid
0x180001a0f  xor     ecx, 6C65746Eh
0x180001a15  xor     edx, 49656E69h
0x180001a1b  or      edx, ecx
0x180001a1d  mov     ebp, eax
0x180001a1f  mov     eax, 1
0x180001a24  xor     ebx, 756E6547h
0x180001a2a  or      edx, ebx
0x180001a2c  lea     ecx, [rax-1]
0x180001a2f  cpuid
0x180001a31  mov     edi, ecx
0x180001a33  jnz     short loc_180001A93
0x180001a35  and     eax, 0FFF3FF0h
0x180001a3a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001a45  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001a50  cmp     eax, 106C0h
0x180001a55  jz      short loc_180001A7F
0x180001a57  cmp     eax, 20660h
0x180001a5c  jz      short loc_180001A7F
0x180001a5e  cmp     eax, 20670h
0x180001a63  jz      short loc_180001A7F
0x180001a65  add     eax, 0FFFCF9B0h
0x180001a6a  cmp     eax, 20h ; ' '
0x180001a6d  ja      short loc_180001A93
0x180001a6f  mov     rcx, 100010001h
0x180001a79  bt      rcx, rax
0x180001a7d  jnb     short loc_180001A93
0x180001a7f  mov     r8d, cs:__favor
0x180001a86  or      r8d, 1
0x180001a8a  mov     cs:__favor, r8d
0x180001a91  jmp     short loc_180001A9A
0x180001a93  mov     r8d, cs:__favor
0x180001a9a  xor     r10d, r10d
0x180001a9d  xor     r11d, r11d
0x180001aa0  cmp     ebp, 7
0x180001aa3  jl      short loc_180001AE7
0x180001aa5  xor     ecx, ecx
0x180001aa7  lea     eax, [r10+7]
0x180001aab  cpuid
0x180001aad  mov     esi, edx
0x180001aaf  mov     r9d, ebx
0x180001ab2  bt      ebx, 9
0x180001ab6  jnb     short loc_180001AC3
0x180001ab8  or      r8d, 2
0x180001abc  mov     cs:__favor, r8d
0x180001ac3  cmp     eax, 1
0x180001ac6  jl      short loc_180001AD5
0x180001ac8  mov     eax, 7
0x180001acd  lea     ecx, [rax-6]
0x180001ad0  cpuid
0x180001ad2  mov     r10d, edx
0x180001ad5  mov     eax, 24h ; '$'
0x180001ada  cmp     ebp, eax
0x180001adc  jl      short loc_180001AEC
0x180001ade  xor     ecx, ecx
0x180001ae0  cpuid
0x180001ae2  mov     r11d, ebx
0x180001ae5  jmp     short loc_180001AEC
0x180001ae7  xor     r9d, r9d
0x180001aea  xor     esi, esi
0x180001aec  mov     rax, cs:__isa_inverted
0x180001af3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001af7  mov     cs:__isa_available, 1
0x180001b01  mov     cs:__isa_enabled, 2
0x180001b0b  mov     cs:__isa_inverted, rax
0x180001b12  bt      edi, 14h
0x180001b16  jnb     short loc_180001B37
0x180001b18  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001b1c  mov     cs:__isa_available, 2
0x180001b26  mov     cs:__isa_inverted, rax
0x180001b2d  mov     cs:__isa_enabled, 6
0x180001b37  bt      edi, 1Bh
0x180001b3b  jnb     loc_180001C78
0x180001b41  xor     ecx, ecx
0x180001b43  xgetbv
0x180001b46  shl     rdx, 20h
0x180001b4a  or      rdx, rax
0x180001b4d  mov     [rsp+38h+arg_0], rdx
0x180001b52  bt      edi, 1Ch
0x180001b56  jnb     loc_180001C5C
0x180001b5c  mov     rax, [rsp+38h+arg_0]
0x180001b61  and     al, 6
0x180001b63  cmp     al, 6
0x180001b65  jnz     loc_180001C5C
0x180001b6b  mov     eax, cs:__isa_enabled
0x180001b71  mov     dl, 0E0h
0x180001b73  or      eax, 8
0x180001b76  mov     cs:__isa_available, 3
0x180001b80  mov     cs:__isa_enabled, eax
0x180001b86  test    r9b, 20h
0x180001b8a  jz      short loc_180001BEE
0x180001b8c  or      eax, 20h
0x180001b8f  mov     cs:__isa_available, 5
0x180001b99  mov     cs:__isa_enabled, eax
0x180001b9f  mov     ecx, 0D0030000h
0x180001ba4  mov     rax, cs:__isa_inverted
0x180001bab  and     r9d, ecx
0x180001bae  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001bb2  mov     cs:__isa_inverted, rax
0x180001bb9  cmp     r9d, ecx
0x180001bbc  jnz     short loc_180001BF5
0x180001bbe  mov     rax, [rsp+38h+arg_0]
0x180001bc3  and     al, dl
0x180001bc5  cmp     al, dl
0x180001bc7  jnz     short loc_180001BEE
0x180001bc9  mov     rax, cs:__isa_inverted
0x180001bd0  or      cs:__isa_enabled, 40h
0x180001bd7  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001bdb  mov     cs:__isa_available, 6
0x180001be5  mov     cs:__isa_inverted, rax
0x180001bec  jmp     short loc_180001BF5
0x180001bee  mov     rax, cs:__isa_inverted
0x180001bf5  bt      esi, 17h
0x180001bf9  jnb     short loc_180001C07
0x180001bfb  btr     rax, 18h
0x180001c00  mov     cs:__isa_inverted, rax
0x180001c07  bt      r10d, 13h
0x180001c0c  jnb     short loc_180001C5C
0x180001c0e  mov     rax, [rsp+38h+arg_0]
0x180001c13  and     al, dl
0x180001c15  cmp     al, dl
0x180001c17  jnz     short loc_180001C5C
0x180001c19  mov     rdx, cs:__isa_inverted
0x180001c20  mov     eax, r11d
0x180001c23  shr     rax, 10h
0x180001c27  mov     ecx, r11d
0x180001c2a  and     eax, 6
0x180001c2d  and     ecx, 400FFh
0x180001c33  or      rax, 1000029h
0x180001c39  mov     cs:__avx10_version, ecx
0x180001c3f  not     rax
0x180001c42  and     rdx, rax
0x180001c45  mov     cs:__isa_inverted, rdx
0x180001c4c  cmp     cl, 1
0x180001c4f  jbe     short loc_180001C5C
0x180001c51  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001c55  mov     cs:__isa_inverted, rdx
0x180001c5c  bt      r10d, 15h
0x180001c61  jnb     short loc_180001C78
0x180001c63  mov     rax, [rsp+38h+arg_0]
0x180001c68  bt      rax, 13h
0x180001c6d  jnb     short loc_180001C78
0x180001c6f  btr     cs:__isa_inverted, 7
0x180001c78  xor     eax, eax
0x180001c7a  add     rsp, 18h
0x180001c7e  pop     rdi
0x180001c7f  pop     rsi
0x180001c80  pop     rbp
0x180001c81  pop     rbx
0x180001c82  retn
```
