# __isa_available_init

- ea: `0x180001940`
- end: `0x180001bc3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000156c`
- `0x1800016a8`

## callees

- `0x180001940`

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
0x180001940  push    rbx
0x180001942  push    rbp
0x180001943  push    rsi
0x180001944  push    rdi
0x180001945  sub     rsp, 18h
0x180001949  xor     eax, eax
0x18000194b  xor     ecx, ecx
0x18000194d  cpuid
0x18000194f  xor     ecx, 6C65746Eh
0x180001955  xor     edx, 49656E69h
0x18000195b  or      edx, ecx
0x18000195d  mov     ebp, eax
0x18000195f  mov     eax, 1
0x180001964  xor     ebx, 756E6547h
0x18000196a  or      edx, ebx
0x18000196c  lea     ecx, [rax-1]
0x18000196f  cpuid
0x180001971  mov     edi, ecx
0x180001973  jnz     short loc_1800019D3
0x180001975  and     eax, 0FFF3FF0h
0x18000197a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001985  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001990  cmp     eax, 106C0h
0x180001995  jz      short loc_1800019BF
0x180001997  cmp     eax, 20660h
0x18000199c  jz      short loc_1800019BF
0x18000199e  cmp     eax, 20670h
0x1800019a3  jz      short loc_1800019BF
0x1800019a5  add     eax, 0FFFCF9B0h
0x1800019aa  cmp     eax, 20h ; ' '
0x1800019ad  ja      short loc_1800019D3
0x1800019af  mov     rcx, 100010001h
0x1800019b9  bt      rcx, rax
0x1800019bd  jnb     short loc_1800019D3
0x1800019bf  mov     r8d, cs:__favor
0x1800019c6  or      r8d, 1
0x1800019ca  mov     cs:__favor, r8d
0x1800019d1  jmp     short loc_1800019DA
0x1800019d3  mov     r8d, cs:__favor
0x1800019da  xor     r10d, r10d
0x1800019dd  xor     r11d, r11d
0x1800019e0  cmp     ebp, 7
0x1800019e3  jl      short loc_180001A27
0x1800019e5  xor     ecx, ecx
0x1800019e7  lea     eax, [r10+7]
0x1800019eb  cpuid
0x1800019ed  mov     esi, edx
0x1800019ef  mov     r9d, ebx
0x1800019f2  bt      ebx, 9
0x1800019f6  jnb     short loc_180001A03
0x1800019f8  or      r8d, 2
0x1800019fc  mov     cs:__favor, r8d
0x180001a03  cmp     eax, 1
0x180001a06  jl      short loc_180001A15
0x180001a08  mov     eax, 7
0x180001a0d  lea     ecx, [rax-6]
0x180001a10  cpuid
0x180001a12  mov     r10d, edx
0x180001a15  mov     eax, 24h ; '$'
0x180001a1a  cmp     ebp, eax
0x180001a1c  jl      short loc_180001A2C
0x180001a1e  xor     ecx, ecx
0x180001a20  cpuid
0x180001a22  mov     r11d, ebx
0x180001a25  jmp     short loc_180001A2C
0x180001a27  xor     r9d, r9d
0x180001a2a  xor     esi, esi
0x180001a2c  mov     rax, cs:__isa_inverted
0x180001a33  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001a37  mov     cs:__isa_available, 1
0x180001a41  mov     cs:__isa_enabled, 2
0x180001a4b  mov     cs:__isa_inverted, rax
0x180001a52  bt      edi, 14h
0x180001a56  jnb     short loc_180001A77
0x180001a58  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001a5c  mov     cs:__isa_available, 2
0x180001a66  mov     cs:__isa_inverted, rax
0x180001a6d  mov     cs:__isa_enabled, 6
0x180001a77  bt      edi, 1Bh
0x180001a7b  jnb     loc_180001BB8
0x180001a81  xor     ecx, ecx
0x180001a83  xgetbv
0x180001a86  shl     rdx, 20h
0x180001a8a  or      rdx, rax
0x180001a8d  mov     [rsp+38h+arg_0], rdx
0x180001a92  bt      edi, 1Ch
0x180001a96  jnb     loc_180001B9C
0x180001a9c  mov     rax, [rsp+38h+arg_0]
0x180001aa1  and     al, 6
0x180001aa3  cmp     al, 6
0x180001aa5  jnz     loc_180001B9C
0x180001aab  mov     eax, cs:__isa_enabled
0x180001ab1  mov     dl, 0E0h
0x180001ab3  or      eax, 8
0x180001ab6  mov     cs:__isa_available, 3
0x180001ac0  mov     cs:__isa_enabled, eax
0x180001ac6  test    r9b, 20h
0x180001aca  jz      short loc_180001B2E
0x180001acc  or      eax, 20h
0x180001acf  mov     cs:__isa_available, 5
0x180001ad9  mov     cs:__isa_enabled, eax
0x180001adf  mov     ecx, 0D0030000h
0x180001ae4  mov     rax, cs:__isa_inverted
0x180001aeb  and     r9d, ecx
0x180001aee  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001af2  mov     cs:__isa_inverted, rax
0x180001af9  cmp     r9d, ecx
0x180001afc  jnz     short loc_180001B35
0x180001afe  mov     rax, [rsp+38h+arg_0]
0x180001b03  and     al, dl
0x180001b05  cmp     al, dl
0x180001b07  jnz     short loc_180001B2E
0x180001b09  mov     rax, cs:__isa_inverted
0x180001b10  or      cs:__isa_enabled, 40h
0x180001b17  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b1b  mov     cs:__isa_available, 6
0x180001b25  mov     cs:__isa_inverted, rax
0x180001b2c  jmp     short loc_180001B35
0x180001b2e  mov     rax, cs:__isa_inverted
0x180001b35  bt      esi, 17h
0x180001b39  jnb     short loc_180001B47
0x180001b3b  btr     rax, 18h
0x180001b40  mov     cs:__isa_inverted, rax
0x180001b47  bt      r10d, 13h
0x180001b4c  jnb     short loc_180001B9C
0x180001b4e  mov     rax, [rsp+38h+arg_0]
0x180001b53  and     al, dl
0x180001b55  cmp     al, dl
0x180001b57  jnz     short loc_180001B9C
0x180001b59  mov     rdx, cs:__isa_inverted
0x180001b60  mov     eax, r11d
0x180001b63  shr     rax, 10h
0x180001b67  mov     ecx, r11d
0x180001b6a  and     eax, 6
0x180001b6d  and     ecx, 400FFh
0x180001b73  or      rax, 1000029h
0x180001b79  mov     cs:__avx10_version, ecx
0x180001b7f  not     rax
0x180001b82  and     rdx, rax
0x180001b85  mov     cs:__isa_inverted, rdx
0x180001b8c  cmp     cl, 1
0x180001b8f  jbe     short loc_180001B9C
0x180001b91  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001b95  mov     cs:__isa_inverted, rdx
0x180001b9c  bt      r10d, 15h
0x180001ba1  jnb     short loc_180001BB8
0x180001ba3  mov     rax, [rsp+38h+arg_0]
0x180001ba8  bt      rax, 13h
0x180001bad  jnb     short loc_180001BB8
0x180001baf  btr     cs:__isa_inverted, 7
0x180001bb8  xor     eax, eax
0x180001bba  add     rsp, 18h
0x180001bbe  pop     rdi
0x180001bbf  pop     rsi
0x180001bc0  pop     rbp
0x180001bc1  pop     rbx
0x180001bc2  retn
```
