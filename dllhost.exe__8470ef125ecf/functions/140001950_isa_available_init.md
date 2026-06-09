# __isa_available_init

- ea: `0x140001950`
- end: `0x140001bd3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400013e4`

## callees

- `0x140001950`

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
0x140001950  push    rbx
0x140001952  push    rbp
0x140001953  push    rsi
0x140001954  push    rdi
0x140001955  sub     rsp, 18h
0x140001959  xor     eax, eax
0x14000195b  xor     ecx, ecx
0x14000195d  cpuid
0x14000195f  xor     ecx, 6C65746Eh
0x140001965  xor     edx, 49656E69h
0x14000196b  or      edx, ecx
0x14000196d  mov     ebp, eax
0x14000196f  mov     eax, 1
0x140001974  xor     ebx, 756E6547h
0x14000197a  or      edx, ebx
0x14000197c  lea     ecx, [rax-1]
0x14000197f  cpuid
0x140001981  mov     edi, ecx
0x140001983  jnz     short loc_1400019E3
0x140001985  and     eax, 0FFF3FF0h
0x14000198a  mov     cs:__memset_fast_string_threshold, 8000h
0x140001995  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1400019a0  cmp     eax, 106C0h
0x1400019a5  jz      short loc_1400019CF
0x1400019a7  cmp     eax, 20660h
0x1400019ac  jz      short loc_1400019CF
0x1400019ae  cmp     eax, 20670h
0x1400019b3  jz      short loc_1400019CF
0x1400019b5  add     eax, 0FFFCF9B0h
0x1400019ba  cmp     eax, 20h ; ' '
0x1400019bd  ja      short loc_1400019E3
0x1400019bf  mov     rcx, 100010001h
0x1400019c9  bt      rcx, rax
0x1400019cd  jnb     short loc_1400019E3
0x1400019cf  mov     r8d, cs:__favor
0x1400019d6  or      r8d, 1
0x1400019da  mov     cs:__favor, r8d
0x1400019e1  jmp     short loc_1400019EA
0x1400019e3  mov     r8d, cs:__favor
0x1400019ea  xor     r10d, r10d
0x1400019ed  xor     r11d, r11d
0x1400019f0  cmp     ebp, 7
0x1400019f3  jl      short loc_140001A37
0x1400019f5  xor     ecx, ecx
0x1400019f7  lea     eax, [r10+7]
0x1400019fb  cpuid
0x1400019fd  mov     esi, edx
0x1400019ff  mov     r9d, ebx
0x140001a02  bt      ebx, 9
0x140001a06  jnb     short loc_140001A13
0x140001a08  or      r8d, 2
0x140001a0c  mov     cs:__favor, r8d
0x140001a13  cmp     eax, 1
0x140001a16  jl      short loc_140001A25
0x140001a18  mov     eax, 7
0x140001a1d  lea     ecx, [rax-6]
0x140001a20  cpuid
0x140001a22  mov     r10d, edx
0x140001a25  mov     eax, 24h ; '$'
0x140001a2a  cmp     ebp, eax
0x140001a2c  jl      short loc_140001A3C
0x140001a2e  xor     ecx, ecx
0x140001a30  cpuid
0x140001a32  mov     r11d, ebx
0x140001a35  jmp     short loc_140001A3C
0x140001a37  xor     r9d, r9d
0x140001a3a  xor     esi, esi
0x140001a3c  mov     rax, cs:__isa_inverted
0x140001a43  and     rax, 0FFFFFFFFFFFFFFFEh
0x140001a47  mov     cs:__isa_available, 1
0x140001a51  mov     cs:__isa_enabled, 2
0x140001a5b  mov     cs:__isa_inverted, rax
0x140001a62  bt      edi, 14h
0x140001a66  jnb     short loc_140001A87
0x140001a68  and     rax, 0FFFFFFFFFFFFFFEFh
0x140001a6c  mov     cs:__isa_available, 2
0x140001a76  mov     cs:__isa_inverted, rax
0x140001a7d  mov     cs:__isa_enabled, 6
0x140001a87  bt      edi, 1Bh
0x140001a8b  jnb     loc_140001BC8
0x140001a91  xor     ecx, ecx
0x140001a93  xgetbv
0x140001a96  shl     rdx, 20h
0x140001a9a  or      rdx, rax
0x140001a9d  mov     [rsp+38h+arg_0], rdx
0x140001aa2  bt      edi, 1Ch
0x140001aa6  jnb     loc_140001BAC
0x140001aac  mov     rax, [rsp+38h+arg_0]
0x140001ab1  and     al, 6
0x140001ab3  cmp     al, 6
0x140001ab5  jnz     loc_140001BAC
0x140001abb  mov     eax, cs:__isa_enabled
0x140001ac1  mov     dl, 0E0h
0x140001ac3  or      eax, 8
0x140001ac6  mov     cs:__isa_available, 3
0x140001ad0  mov     cs:__isa_enabled, eax
0x140001ad6  test    r9b, 20h
0x140001ada  jz      short loc_140001B3E
0x140001adc  or      eax, 20h
0x140001adf  mov     cs:__isa_available, 5
0x140001ae9  mov     cs:__isa_enabled, eax
0x140001aef  mov     ecx, 0D0030000h
0x140001af4  mov     rax, cs:__isa_inverted
0x140001afb  and     r9d, ecx
0x140001afe  and     rax, 0FFFFFFFFFFFFFFFDh
0x140001b02  mov     cs:__isa_inverted, rax
0x140001b09  cmp     r9d, ecx
0x140001b0c  jnz     short loc_140001B45
0x140001b0e  mov     rax, [rsp+38h+arg_0]
0x140001b13  and     al, dl
0x140001b15  cmp     al, dl
0x140001b17  jnz     short loc_140001B3E
0x140001b19  mov     rax, cs:__isa_inverted
0x140001b20  or      cs:__isa_enabled, 40h
0x140001b27  and     rax, 0FFFFFFFFFFFFFFDBh
0x140001b2b  mov     cs:__isa_available, 6
0x140001b35  mov     cs:__isa_inverted, rax
0x140001b3c  jmp     short loc_140001B45
0x140001b3e  mov     rax, cs:__isa_inverted
0x140001b45  bt      esi, 17h
0x140001b49  jnb     short loc_140001B57
0x140001b4b  btr     rax, 18h
0x140001b50  mov     cs:__isa_inverted, rax
0x140001b57  bt      r10d, 13h
0x140001b5c  jnb     short loc_140001BAC
0x140001b5e  mov     rax, [rsp+38h+arg_0]
0x140001b63  and     al, dl
0x140001b65  cmp     al, dl
0x140001b67  jnz     short loc_140001BAC
0x140001b69  mov     rdx, cs:__isa_inverted
0x140001b70  mov     eax, r11d
0x140001b73  shr     rax, 10h
0x140001b77  mov     ecx, r11d
0x140001b7a  and     eax, 6
0x140001b7d  and     ecx, 400FFh
0x140001b83  or      rax, 1000029h
0x140001b89  mov     cs:__avx10_version, ecx
0x140001b8f  not     rax
0x140001b92  and     rdx, rax
0x140001b95  mov     cs:__isa_inverted, rdx
0x140001b9c  cmp     cl, 1
0x140001b9f  jbe     short loc_140001BAC
0x140001ba1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140001ba5  mov     cs:__isa_inverted, rdx
0x140001bac  bt      r10d, 15h
0x140001bb1  jnb     short loc_140001BC8
0x140001bb3  mov     rax, [rsp+38h+arg_0]
0x140001bb8  bt      rax, 13h
0x140001bbd  jnb     short loc_140001BC8
0x140001bbf  btr     cs:__isa_inverted, 7
0x140001bc8  xor     eax, eax
0x140001bca  add     rsp, 18h
0x140001bce  pop     rdi
0x140001bcf  pop     rsi
0x140001bd0  pop     rbp
0x140001bd1  pop     rbx
0x140001bd2  retn
```
