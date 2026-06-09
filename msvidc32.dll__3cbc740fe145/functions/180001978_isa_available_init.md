# __isa_available_init

- ea: `0x180001978`
- end: `0x180001bfb`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015c4`
- `0x180001700`

## callees

- `0x180001978`

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
0x180001978  push    rbx
0x18000197a  push    rbp
0x18000197b  push    rsi
0x18000197c  push    rdi
0x18000197d  sub     rsp, 18h
0x180001981  xor     eax, eax
0x180001983  xor     ecx, ecx
0x180001985  cpuid
0x180001987  xor     ecx, 6C65746Eh
0x18000198d  xor     edx, 49656E69h
0x180001993  or      edx, ecx
0x180001995  mov     ebp, eax
0x180001997  mov     eax, 1
0x18000199c  xor     ebx, 756E6547h
0x1800019a2  or      edx, ebx
0x1800019a4  lea     ecx, [rax-1]
0x1800019a7  cpuid
0x1800019a9  mov     edi, ecx
0x1800019ab  jnz     short loc_180001A0B
0x1800019ad  and     eax, 0FFF3FF0h
0x1800019b2  mov     cs:__memset_fast_string_threshold, 8000h
0x1800019bd  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800019c8  cmp     eax, 106C0h
0x1800019cd  jz      short loc_1800019F7
0x1800019cf  cmp     eax, 20660h
0x1800019d4  jz      short loc_1800019F7
0x1800019d6  cmp     eax, 20670h
0x1800019db  jz      short loc_1800019F7
0x1800019dd  add     eax, 0FFFCF9B0h
0x1800019e2  cmp     eax, 20h ; ' '
0x1800019e5  ja      short loc_180001A0B
0x1800019e7  mov     rcx, 100010001h
0x1800019f1  bt      rcx, rax
0x1800019f5  jnb     short loc_180001A0B
0x1800019f7  mov     r8d, cs:__favor
0x1800019fe  or      r8d, 1
0x180001a02  mov     cs:__favor, r8d
0x180001a09  jmp     short loc_180001A12
0x180001a0b  mov     r8d, cs:__favor
0x180001a12  xor     r10d, r10d
0x180001a15  xor     r11d, r11d
0x180001a18  cmp     ebp, 7
0x180001a1b  jl      short loc_180001A5F
0x180001a1d  xor     ecx, ecx
0x180001a1f  lea     eax, [r10+7]
0x180001a23  cpuid
0x180001a25  mov     esi, edx
0x180001a27  mov     r9d, ebx
0x180001a2a  bt      ebx, 9
0x180001a2e  jnb     short loc_180001A3B
0x180001a30  or      r8d, 2
0x180001a34  mov     cs:__favor, r8d
0x180001a3b  cmp     eax, 1
0x180001a3e  jl      short loc_180001A4D
0x180001a40  mov     eax, 7
0x180001a45  lea     ecx, [rax-6]
0x180001a48  cpuid
0x180001a4a  mov     r10d, edx
0x180001a4d  mov     eax, 24h ; '$'
0x180001a52  cmp     ebp, eax
0x180001a54  jl      short loc_180001A64
0x180001a56  xor     ecx, ecx
0x180001a58  cpuid
0x180001a5a  mov     r11d, ebx
0x180001a5d  jmp     short loc_180001A64
0x180001a5f  xor     r9d, r9d
0x180001a62  xor     esi, esi
0x180001a64  mov     rax, cs:__isa_inverted
0x180001a6b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001a6f  mov     cs:__isa_available, 1
0x180001a79  mov     cs:__isa_enabled, 2
0x180001a83  mov     cs:__isa_inverted, rax
0x180001a8a  bt      edi, 14h
0x180001a8e  jnb     short loc_180001AAF
0x180001a90  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001a94  mov     cs:__isa_available, 2
0x180001a9e  mov     cs:__isa_inverted, rax
0x180001aa5  mov     cs:__isa_enabled, 6
0x180001aaf  bt      edi, 1Bh
0x180001ab3  jnb     loc_180001BF0
0x180001ab9  xor     ecx, ecx
0x180001abb  xgetbv
0x180001abe  shl     rdx, 20h
0x180001ac2  or      rdx, rax
0x180001ac5  mov     [rsp+38h+arg_0], rdx
0x180001aca  bt      edi, 1Ch
0x180001ace  jnb     loc_180001BD4
0x180001ad4  mov     rax, [rsp+38h+arg_0]
0x180001ad9  and     al, 6
0x180001adb  cmp     al, 6
0x180001add  jnz     loc_180001BD4
0x180001ae3  mov     eax, cs:__isa_enabled
0x180001ae9  mov     dl, 0E0h
0x180001aeb  or      eax, 8
0x180001aee  mov     cs:__isa_available, 3
0x180001af8  mov     cs:__isa_enabled, eax
0x180001afe  test    r9b, 20h
0x180001b02  jz      short loc_180001B66
0x180001b04  or      eax, 20h
0x180001b07  mov     cs:__isa_available, 5
0x180001b11  mov     cs:__isa_enabled, eax
0x180001b17  mov     ecx, 0D0030000h
0x180001b1c  mov     rax, cs:__isa_inverted
0x180001b23  and     r9d, ecx
0x180001b26  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001b2a  mov     cs:__isa_inverted, rax
0x180001b31  cmp     r9d, ecx
0x180001b34  jnz     short loc_180001B6D
0x180001b36  mov     rax, [rsp+38h+arg_0]
0x180001b3b  and     al, dl
0x180001b3d  cmp     al, dl
0x180001b3f  jnz     short loc_180001B66
0x180001b41  mov     rax, cs:__isa_inverted
0x180001b48  or      cs:__isa_enabled, 40h
0x180001b4f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b53  mov     cs:__isa_available, 6
0x180001b5d  mov     cs:__isa_inverted, rax
0x180001b64  jmp     short loc_180001B6D
0x180001b66  mov     rax, cs:__isa_inverted
0x180001b6d  bt      esi, 17h
0x180001b71  jnb     short loc_180001B7F
0x180001b73  btr     rax, 18h
0x180001b78  mov     cs:__isa_inverted, rax
0x180001b7f  bt      r10d, 13h
0x180001b84  jnb     short loc_180001BD4
0x180001b86  mov     rax, [rsp+38h+arg_0]
0x180001b8b  and     al, dl
0x180001b8d  cmp     al, dl
0x180001b8f  jnz     short loc_180001BD4
0x180001b91  mov     rdx, cs:__isa_inverted
0x180001b98  mov     eax, r11d
0x180001b9b  shr     rax, 10h
0x180001b9f  mov     ecx, r11d
0x180001ba2  and     eax, 6
0x180001ba5  and     ecx, 400FFh
0x180001bab  or      rax, 1000029h
0x180001bb1  mov     cs:__avx10_version, ecx
0x180001bb7  not     rax
0x180001bba  and     rdx, rax
0x180001bbd  mov     cs:__isa_inverted, rdx
0x180001bc4  cmp     cl, 1
0x180001bc7  jbe     short loc_180001BD4
0x180001bc9  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001bcd  mov     cs:__isa_inverted, rdx
0x180001bd4  bt      r10d, 15h
0x180001bd9  jnb     short loc_180001BF0
0x180001bdb  mov     rax, [rsp+38h+arg_0]
0x180001be0  bt      rax, 13h
0x180001be5  jnb     short loc_180001BF0
0x180001be7  btr     cs:__isa_inverted, 7
0x180001bf0  xor     eax, eax
0x180001bf2  add     rsp, 18h
0x180001bf6  pop     rdi
0x180001bf7  pop     rsi
0x180001bf8  pop     rbp
0x180001bf9  pop     rbx
0x180001bfa  retn
```
