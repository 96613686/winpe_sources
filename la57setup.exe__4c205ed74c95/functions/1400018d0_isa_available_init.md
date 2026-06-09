# __isa_available_init

- ea: `0x1400018d0`
- end: `0x140001b53`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400013a4`

## callees

- `0x1400018d0`

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
0x1400018d0  push    rbx
0x1400018d2  push    rbp
0x1400018d3  push    rsi
0x1400018d4  push    rdi
0x1400018d5  sub     rsp, 18h
0x1400018d9  xor     eax, eax
0x1400018db  xor     ecx, ecx
0x1400018dd  cpuid
0x1400018df  xor     ecx, 6C65746Eh
0x1400018e5  xor     edx, 49656E69h
0x1400018eb  or      edx, ecx
0x1400018ed  mov     ebp, eax
0x1400018ef  mov     eax, 1
0x1400018f4  xor     ebx, 756E6547h
0x1400018fa  or      edx, ebx
0x1400018fc  lea     ecx, [rax-1]
0x1400018ff  cpuid
0x140001901  mov     edi, ecx
0x140001903  jnz     short loc_140001963
0x140001905  and     eax, 0FFF3FF0h
0x14000190a  mov     cs:__memset_fast_string_threshold, 8000h
0x140001915  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140001920  cmp     eax, 106C0h
0x140001925  jz      short loc_14000194F
0x140001927  cmp     eax, 20660h
0x14000192c  jz      short loc_14000194F
0x14000192e  cmp     eax, 20670h
0x140001933  jz      short loc_14000194F
0x140001935  add     eax, 0FFFCF9B0h
0x14000193a  cmp     eax, 20h ; ' '
0x14000193d  ja      short loc_140001963
0x14000193f  mov     rcx, 100010001h
0x140001949  bt      rcx, rax
0x14000194d  jnb     short loc_140001963
0x14000194f  mov     r8d, cs:__favor
0x140001956  or      r8d, 1
0x14000195a  mov     cs:__favor, r8d
0x140001961  jmp     short loc_14000196A
0x140001963  mov     r8d, cs:__favor
0x14000196a  xor     r10d, r10d
0x14000196d  xor     r11d, r11d
0x140001970  cmp     ebp, 7
0x140001973  jl      short loc_1400019B7
0x140001975  xor     ecx, ecx
0x140001977  lea     eax, [r10+7]
0x14000197b  cpuid
0x14000197d  mov     esi, edx
0x14000197f  mov     r9d, ebx
0x140001982  bt      ebx, 9
0x140001986  jnb     short loc_140001993
0x140001988  or      r8d, 2
0x14000198c  mov     cs:__favor, r8d
0x140001993  cmp     eax, 1
0x140001996  jl      short loc_1400019A5
0x140001998  mov     eax, 7
0x14000199d  lea     ecx, [rax-6]
0x1400019a0  cpuid
0x1400019a2  mov     r10d, edx
0x1400019a5  mov     eax, 24h ; '$'
0x1400019aa  cmp     ebp, eax
0x1400019ac  jl      short loc_1400019BC
0x1400019ae  xor     ecx, ecx
0x1400019b0  cpuid
0x1400019b2  mov     r11d, ebx
0x1400019b5  jmp     short loc_1400019BC
0x1400019b7  xor     r9d, r9d
0x1400019ba  xor     esi, esi
0x1400019bc  mov     rax, cs:__isa_inverted
0x1400019c3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400019c7  mov     cs:__isa_available, 1
0x1400019d1  mov     cs:__isa_enabled, 2
0x1400019db  mov     cs:__isa_inverted, rax
0x1400019e2  bt      edi, 14h
0x1400019e6  jnb     short loc_140001A07
0x1400019e8  and     rax, 0FFFFFFFFFFFFFFEFh
0x1400019ec  mov     cs:__isa_available, 2
0x1400019f6  mov     cs:__isa_inverted, rax
0x1400019fd  mov     cs:__isa_enabled, 6
0x140001a07  bt      edi, 1Bh
0x140001a0b  jnb     loc_140001B48
0x140001a11  xor     ecx, ecx
0x140001a13  xgetbv
0x140001a16  shl     rdx, 20h
0x140001a1a  or      rdx, rax
0x140001a1d  mov     [rsp+38h+arg_0], rdx
0x140001a22  bt      edi, 1Ch
0x140001a26  jnb     loc_140001B2C
0x140001a2c  mov     rax, [rsp+38h+arg_0]
0x140001a31  and     al, 6
0x140001a33  cmp     al, 6
0x140001a35  jnz     loc_140001B2C
0x140001a3b  mov     eax, cs:__isa_enabled
0x140001a41  mov     dl, 0E0h
0x140001a43  or      eax, 8
0x140001a46  mov     cs:__isa_available, 3
0x140001a50  mov     cs:__isa_enabled, eax
0x140001a56  test    r9b, 20h
0x140001a5a  jz      short loc_140001ABE
0x140001a5c  or      eax, 20h
0x140001a5f  mov     cs:__isa_available, 5
0x140001a69  mov     cs:__isa_enabled, eax
0x140001a6f  mov     ecx, 0D0030000h
0x140001a74  mov     rax, cs:__isa_inverted
0x140001a7b  and     r9d, ecx
0x140001a7e  and     rax, 0FFFFFFFFFFFFFFFDh
0x140001a82  mov     cs:__isa_inverted, rax
0x140001a89  cmp     r9d, ecx
0x140001a8c  jnz     short loc_140001AC5
0x140001a8e  mov     rax, [rsp+38h+arg_0]
0x140001a93  and     al, dl
0x140001a95  cmp     al, dl
0x140001a97  jnz     short loc_140001ABE
0x140001a99  mov     rax, cs:__isa_inverted
0x140001aa0  or      cs:__isa_enabled, 40h
0x140001aa7  and     rax, 0FFFFFFFFFFFFFFDBh
0x140001aab  mov     cs:__isa_available, 6
0x140001ab5  mov     cs:__isa_inverted, rax
0x140001abc  jmp     short loc_140001AC5
0x140001abe  mov     rax, cs:__isa_inverted
0x140001ac5  bt      esi, 17h
0x140001ac9  jnb     short loc_140001AD7
0x140001acb  btr     rax, 18h
0x140001ad0  mov     cs:__isa_inverted, rax
0x140001ad7  bt      r10d, 13h
0x140001adc  jnb     short loc_140001B2C
0x140001ade  mov     rax, [rsp+38h+arg_0]
0x140001ae3  and     al, dl
0x140001ae5  cmp     al, dl
0x140001ae7  jnz     short loc_140001B2C
0x140001ae9  mov     rdx, cs:__isa_inverted
0x140001af0  mov     eax, r11d
0x140001af3  shr     rax, 10h
0x140001af7  mov     ecx, r11d
0x140001afa  and     eax, 6
0x140001afd  and     ecx, 400FFh
0x140001b03  or      rax, 1000029h
0x140001b09  mov     cs:__avx10_version, ecx
0x140001b0f  not     rax
0x140001b12  and     rdx, rax
0x140001b15  mov     cs:__isa_inverted, rdx
0x140001b1c  cmp     cl, 1
0x140001b1f  jbe     short loc_140001B2C
0x140001b21  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140001b25  mov     cs:__isa_inverted, rdx
0x140001b2c  bt      r10d, 15h
0x140001b31  jnb     short loc_140001B48
0x140001b33  mov     rax, [rsp+38h+arg_0]
0x140001b38  bt      rax, 13h
0x140001b3d  jnb     short loc_140001B48
0x140001b3f  btr     cs:__isa_inverted, 7
0x140001b48  xor     eax, eax
0x140001b4a  add     rsp, 18h
0x140001b4e  pop     rdi
0x140001b4f  pop     rsi
0x140001b50  pop     rbp
0x140001b51  pop     rbx
0x140001b52  retn
```
