# __isa_available_init

- ea: `0x140001a50`
- end: `0x140001cd3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014f8`

## callees

- `0x140001a50`

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
0x140001a50  push    rbx
0x140001a52  push    rbp
0x140001a53  push    rsi
0x140001a54  push    rdi
0x140001a55  sub     rsp, 18h
0x140001a59  xor     eax, eax
0x140001a5b  xor     ecx, ecx
0x140001a5d  cpuid
0x140001a5f  xor     ecx, 6C65746Eh
0x140001a65  xor     edx, 49656E69h
0x140001a6b  or      edx, ecx
0x140001a6d  mov     ebp, eax
0x140001a6f  mov     eax, 1
0x140001a74  xor     ebx, 756E6547h
0x140001a7a  or      edx, ebx
0x140001a7c  lea     ecx, [rax-1]
0x140001a7f  cpuid
0x140001a81  mov     edi, ecx
0x140001a83  jnz     short loc_140001AE3
0x140001a85  and     eax, 0FFF3FF0h
0x140001a8a  mov     cs:__memset_fast_string_threshold, 8000h
0x140001a95  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140001aa0  cmp     eax, 106C0h
0x140001aa5  jz      short loc_140001ACF
0x140001aa7  cmp     eax, 20660h
0x140001aac  jz      short loc_140001ACF
0x140001aae  cmp     eax, 20670h
0x140001ab3  jz      short loc_140001ACF
0x140001ab5  add     eax, 0FFFCF9B0h
0x140001aba  cmp     eax, 20h ; ' '
0x140001abd  ja      short loc_140001AE3
0x140001abf  mov     rcx, 100010001h
0x140001ac9  bt      rcx, rax
0x140001acd  jnb     short loc_140001AE3
0x140001acf  mov     r8d, cs:__favor
0x140001ad6  or      r8d, 1
0x140001ada  mov     cs:__favor, r8d
0x140001ae1  jmp     short loc_140001AEA
0x140001ae3  mov     r8d, cs:__favor
0x140001aea  xor     r10d, r10d
0x140001aed  xor     r11d, r11d
0x140001af0  cmp     ebp, 7
0x140001af3  jl      short loc_140001B37
0x140001af5  xor     ecx, ecx
0x140001af7  lea     eax, [r10+7]
0x140001afb  cpuid
0x140001afd  mov     esi, edx
0x140001aff  mov     r9d, ebx
0x140001b02  bt      ebx, 9
0x140001b06  jnb     short loc_140001B13
0x140001b08  or      r8d, 2
0x140001b0c  mov     cs:__favor, r8d
0x140001b13  cmp     eax, 1
0x140001b16  jl      short loc_140001B25
0x140001b18  mov     eax, 7
0x140001b1d  lea     ecx, [rax-6]
0x140001b20  cpuid
0x140001b22  mov     r10d, edx
0x140001b25  mov     eax, 24h ; '$'
0x140001b2a  cmp     ebp, eax
0x140001b2c  jl      short loc_140001B3C
0x140001b2e  xor     ecx, ecx
0x140001b30  cpuid
0x140001b32  mov     r11d, ebx
0x140001b35  jmp     short loc_140001B3C
0x140001b37  xor     r9d, r9d
0x140001b3a  xor     esi, esi
0x140001b3c  mov     rax, cs:__isa_inverted
0x140001b43  and     rax, 0FFFFFFFFFFFFFFFEh
0x140001b47  mov     cs:__isa_available, 1
0x140001b51  mov     cs:__isa_enabled, 2
0x140001b5b  mov     cs:__isa_inverted, rax
0x140001b62  bt      edi, 14h
0x140001b66  jnb     short loc_140001B87
0x140001b68  and     rax, 0FFFFFFFFFFFFFFEFh
0x140001b6c  mov     cs:__isa_available, 2
0x140001b76  mov     cs:__isa_inverted, rax
0x140001b7d  mov     cs:__isa_enabled, 6
0x140001b87  bt      edi, 1Bh
0x140001b8b  jnb     loc_140001CC8
0x140001b91  xor     ecx, ecx
0x140001b93  xgetbv
0x140001b96  shl     rdx, 20h
0x140001b9a  or      rdx, rax
0x140001b9d  mov     [rsp+38h+arg_0], rdx
0x140001ba2  bt      edi, 1Ch
0x140001ba6  jnb     loc_140001CAC
0x140001bac  mov     rax, [rsp+38h+arg_0]
0x140001bb1  and     al, 6
0x140001bb3  cmp     al, 6
0x140001bb5  jnz     loc_140001CAC
0x140001bbb  mov     eax, cs:__isa_enabled
0x140001bc1  mov     dl, 0E0h
0x140001bc3  or      eax, 8
0x140001bc6  mov     cs:__isa_available, 3
0x140001bd0  mov     cs:__isa_enabled, eax
0x140001bd6  test    r9b, 20h
0x140001bda  jz      short loc_140001C3E
0x140001bdc  or      eax, 20h
0x140001bdf  mov     cs:__isa_available, 5
0x140001be9  mov     cs:__isa_enabled, eax
0x140001bef  mov     ecx, 0D0030000h
0x140001bf4  mov     rax, cs:__isa_inverted
0x140001bfb  and     r9d, ecx
0x140001bfe  and     rax, 0FFFFFFFFFFFFFFFDh
0x140001c02  mov     cs:__isa_inverted, rax
0x140001c09  cmp     r9d, ecx
0x140001c0c  jnz     short loc_140001C45
0x140001c0e  mov     rax, [rsp+38h+arg_0]
0x140001c13  and     al, dl
0x140001c15  cmp     al, dl
0x140001c17  jnz     short loc_140001C3E
0x140001c19  mov     rax, cs:__isa_inverted
0x140001c20  or      cs:__isa_enabled, 40h
0x140001c27  and     rax, 0FFFFFFFFFFFFFFDBh
0x140001c2b  mov     cs:__isa_available, 6
0x140001c35  mov     cs:__isa_inverted, rax
0x140001c3c  jmp     short loc_140001C45
0x140001c3e  mov     rax, cs:__isa_inverted
0x140001c45  bt      esi, 17h
0x140001c49  jnb     short loc_140001C57
0x140001c4b  btr     rax, 18h
0x140001c50  mov     cs:__isa_inverted, rax
0x140001c57  bt      r10d, 13h
0x140001c5c  jnb     short loc_140001CAC
0x140001c5e  mov     rax, [rsp+38h+arg_0]
0x140001c63  and     al, dl
0x140001c65  cmp     al, dl
0x140001c67  jnz     short loc_140001CAC
0x140001c69  mov     rdx, cs:__isa_inverted
0x140001c70  mov     eax, r11d
0x140001c73  shr     rax, 10h
0x140001c77  mov     ecx, r11d
0x140001c7a  and     eax, 6
0x140001c7d  and     ecx, 400FFh
0x140001c83  or      rax, 1000029h
0x140001c89  mov     cs:__avx10_version, ecx
0x140001c8f  not     rax
0x140001c92  and     rdx, rax
0x140001c95  mov     cs:__isa_inverted, rdx
0x140001c9c  cmp     cl, 1
0x140001c9f  jbe     short loc_140001CAC
0x140001ca1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140001ca5  mov     cs:__isa_inverted, rdx
0x140001cac  bt      r10d, 15h
0x140001cb1  jnb     short loc_140001CC8
0x140001cb3  mov     rax, [rsp+38h+arg_0]
0x140001cb8  bt      rax, 13h
0x140001cbd  jnb     short loc_140001CC8
0x140001cbf  btr     cs:__isa_inverted, 7
0x140001cc8  xor     eax, eax
0x140001cca  add     rsp, 18h
0x140001cce  pop     rdi
0x140001ccf  pop     rsi
0x140001cd0  pop     rbp
0x140001cd1  pop     rbx
0x140001cd2  retn
```
