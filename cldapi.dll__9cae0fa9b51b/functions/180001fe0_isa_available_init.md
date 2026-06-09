# __isa_available_init

- ea: `0x180001fe0`
- end: `0x180002263`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c0c`
- `0x180001d48`

## callees

- `0x180001fe0`

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
0x180001fe0  push    rbx
0x180001fe2  push    rbp
0x180001fe3  push    rsi
0x180001fe4  push    rdi
0x180001fe5  sub     rsp, 18h
0x180001fe9  xor     eax, eax
0x180001feb  xor     ecx, ecx
0x180001fed  cpuid
0x180001fef  xor     ecx, 6C65746Eh
0x180001ff5  xor     edx, 49656E69h
0x180001ffb  or      edx, ecx
0x180001ffd  mov     ebp, eax
0x180001fff  mov     eax, 1
0x180002004  xor     ebx, 756E6547h
0x18000200a  or      edx, ebx
0x18000200c  lea     ecx, [rax-1]
0x18000200f  cpuid
0x180002011  mov     edi, ecx
0x180002013  jnz     short loc_180002073
0x180002015  and     eax, 0FFF3FF0h
0x18000201a  mov     cs:__memset_fast_string_threshold, 8000h
0x180002025  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002030  cmp     eax, 106C0h
0x180002035  jz      short loc_18000205F
0x180002037  cmp     eax, 20660h
0x18000203c  jz      short loc_18000205F
0x18000203e  cmp     eax, 20670h
0x180002043  jz      short loc_18000205F
0x180002045  add     eax, 0FFFCF9B0h
0x18000204a  cmp     eax, 20h ; ' '
0x18000204d  ja      short loc_180002073
0x18000204f  mov     rcx, 100010001h
0x180002059  bt      rcx, rax
0x18000205d  jnb     short loc_180002073
0x18000205f  mov     r8d, cs:__favor
0x180002066  or      r8d, 1
0x18000206a  mov     cs:__favor, r8d
0x180002071  jmp     short loc_18000207A
0x180002073  mov     r8d, cs:__favor
0x18000207a  xor     r10d, r10d
0x18000207d  xor     r11d, r11d
0x180002080  cmp     ebp, 7
0x180002083  jl      short loc_1800020C7
0x180002085  xor     ecx, ecx
0x180002087  lea     eax, [r10+7]
0x18000208b  cpuid
0x18000208d  mov     esi, edx
0x18000208f  mov     r9d, ebx
0x180002092  bt      ebx, 9
0x180002096  jnb     short loc_1800020A3
0x180002098  or      r8d, 2
0x18000209c  mov     cs:__favor, r8d
0x1800020a3  cmp     eax, 1
0x1800020a6  jl      short loc_1800020B5
0x1800020a8  mov     eax, 7
0x1800020ad  lea     ecx, [rax-6]
0x1800020b0  cpuid
0x1800020b2  mov     r10d, edx
0x1800020b5  mov     eax, 24h ; '$'
0x1800020ba  cmp     ebp, eax
0x1800020bc  jl      short loc_1800020CC
0x1800020be  xor     ecx, ecx
0x1800020c0  cpuid
0x1800020c2  mov     r11d, ebx
0x1800020c5  jmp     short loc_1800020CC
0x1800020c7  xor     r9d, r9d
0x1800020ca  xor     esi, esi
0x1800020cc  mov     rax, cs:__isa_inverted
0x1800020d3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800020d7  mov     cs:__isa_available, 1
0x1800020e1  mov     cs:__isa_enabled, 2
0x1800020eb  mov     cs:__isa_inverted, rax
0x1800020f2  bt      edi, 14h
0x1800020f6  jnb     short loc_180002117
0x1800020f8  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800020fc  mov     cs:__isa_available, 2
0x180002106  mov     cs:__isa_inverted, rax
0x18000210d  mov     cs:__isa_enabled, 6
0x180002117  bt      edi, 1Bh
0x18000211b  jnb     loc_180002258
0x180002121  xor     ecx, ecx
0x180002123  xgetbv
0x180002126  shl     rdx, 20h
0x18000212a  or      rdx, rax
0x18000212d  mov     [rsp+38h+arg_0], rdx
0x180002132  bt      edi, 1Ch
0x180002136  jnb     loc_18000223C
0x18000213c  mov     rax, [rsp+38h+arg_0]
0x180002141  and     al, 6
0x180002143  cmp     al, 6
0x180002145  jnz     loc_18000223C
0x18000214b  mov     eax, cs:__isa_enabled
0x180002151  mov     dl, 0E0h
0x180002153  or      eax, 8
0x180002156  mov     cs:__isa_available, 3
0x180002160  mov     cs:__isa_enabled, eax
0x180002166  test    r9b, 20h
0x18000216a  jz      short loc_1800021CE
0x18000216c  or      eax, 20h
0x18000216f  mov     cs:__isa_available, 5
0x180002179  mov     cs:__isa_enabled, eax
0x18000217f  mov     ecx, 0D0030000h
0x180002184  mov     rax, cs:__isa_inverted
0x18000218b  and     r9d, ecx
0x18000218e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180002192  mov     cs:__isa_inverted, rax
0x180002199  cmp     r9d, ecx
0x18000219c  jnz     short loc_1800021D5
0x18000219e  mov     rax, [rsp+38h+arg_0]
0x1800021a3  and     al, dl
0x1800021a5  cmp     al, dl
0x1800021a7  jnz     short loc_1800021CE
0x1800021a9  mov     rax, cs:__isa_inverted
0x1800021b0  or      cs:__isa_enabled, 40h
0x1800021b7  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800021bb  mov     cs:__isa_available, 6
0x1800021c5  mov     cs:__isa_inverted, rax
0x1800021cc  jmp     short loc_1800021D5
0x1800021ce  mov     rax, cs:__isa_inverted
0x1800021d5  bt      esi, 17h
0x1800021d9  jnb     short loc_1800021E7
0x1800021db  btr     rax, 18h
0x1800021e0  mov     cs:__isa_inverted, rax
0x1800021e7  bt      r10d, 13h
0x1800021ec  jnb     short loc_18000223C
0x1800021ee  mov     rax, [rsp+38h+arg_0]
0x1800021f3  and     al, dl
0x1800021f5  cmp     al, dl
0x1800021f7  jnz     short loc_18000223C
0x1800021f9  mov     rdx, cs:__isa_inverted
0x180002200  mov     eax, r11d
0x180002203  shr     rax, 10h
0x180002207  mov     ecx, r11d
0x18000220a  and     eax, 6
0x18000220d  and     ecx, 400FFh
0x180002213  or      rax, 1000029h
0x180002219  mov     cs:__avx10_version, ecx
0x18000221f  not     rax
0x180002222  and     rdx, rax
0x180002225  mov     cs:__isa_inverted, rdx
0x18000222c  cmp     cl, 1
0x18000222f  jbe     short loc_18000223C
0x180002231  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002235  mov     cs:__isa_inverted, rdx
0x18000223c  bt      r10d, 15h
0x180002241  jnb     short loc_180002258
0x180002243  mov     rax, [rsp+38h+arg_0]
0x180002248  bt      rax, 13h
0x18000224d  jnb     short loc_180002258
0x18000224f  btr     cs:__isa_inverted, 7
0x180002258  xor     eax, eax
0x18000225a  add     rsp, 18h
0x18000225e  pop     rdi
0x18000225f  pop     rsi
0x180002260  pop     rbp
0x180002261  pop     rbx
0x180002262  retn
```
