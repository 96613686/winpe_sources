# __isa_available_init

- ea: `0x180001938`
- end: `0x180001bbb`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001588`
- `0x1800016c4`

## callees

- `0x180001938`

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
0x180001938  push    rbx
0x18000193a  push    rbp
0x18000193b  push    rsi
0x18000193c  push    rdi
0x18000193d  sub     rsp, 18h
0x180001941  xor     eax, eax
0x180001943  xor     ecx, ecx
0x180001945  cpuid
0x180001947  xor     ecx, 6C65746Eh
0x18000194d  xor     edx, 49656E69h
0x180001953  or      edx, ecx
0x180001955  mov     ebp, eax
0x180001957  mov     eax, 1
0x18000195c  xor     ebx, 756E6547h
0x180001962  or      edx, ebx
0x180001964  lea     ecx, [rax-1]
0x180001967  cpuid
0x180001969  mov     edi, ecx
0x18000196b  jnz     short loc_1800019CB
0x18000196d  and     eax, 0FFF3FF0h
0x180001972  mov     cs:__memset_fast_string_threshold, 8000h
0x18000197d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001988  cmp     eax, 106C0h
0x18000198d  jz      short loc_1800019B7
0x18000198f  cmp     eax, 20660h
0x180001994  jz      short loc_1800019B7
0x180001996  cmp     eax, 20670h
0x18000199b  jz      short loc_1800019B7
0x18000199d  add     eax, 0FFFCF9B0h
0x1800019a2  cmp     eax, 20h ; ' '
0x1800019a5  ja      short loc_1800019CB
0x1800019a7  mov     rcx, 100010001h
0x1800019b1  bt      rcx, rax
0x1800019b5  jnb     short loc_1800019CB
0x1800019b7  mov     r8d, cs:__favor
0x1800019be  or      r8d, 1
0x1800019c2  mov     cs:__favor, r8d
0x1800019c9  jmp     short loc_1800019D2
0x1800019cb  mov     r8d, cs:__favor
0x1800019d2  xor     r10d, r10d
0x1800019d5  xor     r11d, r11d
0x1800019d8  cmp     ebp, 7
0x1800019db  jl      short loc_180001A1F
0x1800019dd  xor     ecx, ecx
0x1800019df  lea     eax, [r10+7]
0x1800019e3  cpuid
0x1800019e5  mov     esi, edx
0x1800019e7  mov     r9d, ebx
0x1800019ea  bt      ebx, 9
0x1800019ee  jnb     short loc_1800019FB
0x1800019f0  or      r8d, 2
0x1800019f4  mov     cs:__favor, r8d
0x1800019fb  cmp     eax, 1
0x1800019fe  jl      short loc_180001A0D
0x180001a00  mov     eax, 7
0x180001a05  lea     ecx, [rax-6]
0x180001a08  cpuid
0x180001a0a  mov     r10d, edx
0x180001a0d  mov     eax, 24h ; '$'
0x180001a12  cmp     ebp, eax
0x180001a14  jl      short loc_180001A24
0x180001a16  xor     ecx, ecx
0x180001a18  cpuid
0x180001a1a  mov     r11d, ebx
0x180001a1d  jmp     short loc_180001A24
0x180001a1f  xor     r9d, r9d
0x180001a22  xor     esi, esi
0x180001a24  mov     rax, cs:__isa_inverted
0x180001a2b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001a2f  mov     cs:__isa_available, 1
0x180001a39  mov     cs:__isa_enabled, 2
0x180001a43  mov     cs:__isa_inverted, rax
0x180001a4a  bt      edi, 14h
0x180001a4e  jnb     short loc_180001A6F
0x180001a50  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001a54  mov     cs:__isa_available, 2
0x180001a5e  mov     cs:__isa_inverted, rax
0x180001a65  mov     cs:__isa_enabled, 6
0x180001a6f  bt      edi, 1Bh
0x180001a73  jnb     loc_180001BB0
0x180001a79  xor     ecx, ecx
0x180001a7b  xgetbv
0x180001a7e  shl     rdx, 20h
0x180001a82  or      rdx, rax
0x180001a85  mov     [rsp+38h+arg_0], rdx
0x180001a8a  bt      edi, 1Ch
0x180001a8e  jnb     loc_180001B94
0x180001a94  mov     rax, [rsp+38h+arg_0]
0x180001a99  and     al, 6
0x180001a9b  cmp     al, 6
0x180001a9d  jnz     loc_180001B94
0x180001aa3  mov     eax, cs:__isa_enabled
0x180001aa9  mov     dl, 0E0h
0x180001aab  or      eax, 8
0x180001aae  mov     cs:__isa_available, 3
0x180001ab8  mov     cs:__isa_enabled, eax
0x180001abe  test    r9b, 20h
0x180001ac2  jz      short loc_180001B26
0x180001ac4  or      eax, 20h
0x180001ac7  mov     cs:__isa_available, 5
0x180001ad1  mov     cs:__isa_enabled, eax
0x180001ad7  mov     ecx, 0D0030000h
0x180001adc  mov     rax, cs:__isa_inverted
0x180001ae3  and     r9d, ecx
0x180001ae6  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001aea  mov     cs:__isa_inverted, rax
0x180001af1  cmp     r9d, ecx
0x180001af4  jnz     short loc_180001B2D
0x180001af6  mov     rax, [rsp+38h+arg_0]
0x180001afb  and     al, dl
0x180001afd  cmp     al, dl
0x180001aff  jnz     short loc_180001B26
0x180001b01  mov     rax, cs:__isa_inverted
0x180001b08  or      cs:__isa_enabled, 40h
0x180001b0f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b13  mov     cs:__isa_available, 6
0x180001b1d  mov     cs:__isa_inverted, rax
0x180001b24  jmp     short loc_180001B2D
0x180001b26  mov     rax, cs:__isa_inverted
0x180001b2d  bt      esi, 17h
0x180001b31  jnb     short loc_180001B3F
0x180001b33  btr     rax, 18h
0x180001b38  mov     cs:__isa_inverted, rax
0x180001b3f  bt      r10d, 13h
0x180001b44  jnb     short loc_180001B94
0x180001b46  mov     rax, [rsp+38h+arg_0]
0x180001b4b  and     al, dl
0x180001b4d  cmp     al, dl
0x180001b4f  jnz     short loc_180001B94
0x180001b51  mov     rdx, cs:__isa_inverted
0x180001b58  mov     eax, r11d
0x180001b5b  shr     rax, 10h
0x180001b5f  mov     ecx, r11d
0x180001b62  and     eax, 6
0x180001b65  and     ecx, 400FFh
0x180001b6b  or      rax, 1000029h
0x180001b71  mov     cs:__avx10_version, ecx
0x180001b77  not     rax
0x180001b7a  and     rdx, rax
0x180001b7d  mov     cs:__isa_inverted, rdx
0x180001b84  cmp     cl, 1
0x180001b87  jbe     short loc_180001B94
0x180001b89  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001b8d  mov     cs:__isa_inverted, rdx
0x180001b94  bt      r10d, 15h
0x180001b99  jnb     short loc_180001BB0
0x180001b9b  mov     rax, [rsp+38h+arg_0]
0x180001ba0  bt      rax, 13h
0x180001ba5  jnb     short loc_180001BB0
0x180001ba7  btr     cs:__isa_inverted, 7
0x180001bb0  xor     eax, eax
0x180001bb2  add     rsp, 18h
0x180001bb6  pop     rdi
0x180001bb7  pop     rsi
0x180001bb8  pop     rbp
0x180001bb9  pop     rbx
0x180001bba  retn
```
