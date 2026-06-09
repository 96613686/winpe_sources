# __isa_available_init

- ea: `0x180009850`
- end: `0x180009ad3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000947c`
- `0x1800095b8`

## callees

- `0x180009850`

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
0x180009850  push    rbx
0x180009852  push    rbp
0x180009853  push    rsi
0x180009854  push    rdi
0x180009855  sub     rsp, 18h
0x180009859  xor     eax, eax
0x18000985b  xor     ecx, ecx
0x18000985d  cpuid
0x18000985f  xor     ecx, 6C65746Eh
0x180009865  xor     edx, 49656E69h
0x18000986b  or      edx, ecx
0x18000986d  mov     ebp, eax
0x18000986f  mov     eax, 1
0x180009874  xor     ebx, 756E6547h
0x18000987a  or      edx, ebx
0x18000987c  lea     ecx, [rax-1]
0x18000987f  cpuid
0x180009881  mov     edi, ecx
0x180009883  jnz     short loc_1800098E3
0x180009885  and     eax, 0FFF3FF0h
0x18000988a  mov     cs:__memset_fast_string_threshold, 8000h
0x180009895  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800098a0  cmp     eax, 106C0h
0x1800098a5  jz      short loc_1800098CF
0x1800098a7  cmp     eax, 20660h
0x1800098ac  jz      short loc_1800098CF
0x1800098ae  cmp     eax, 20670h
0x1800098b3  jz      short loc_1800098CF
0x1800098b5  add     eax, 0FFFCF9B0h
0x1800098ba  cmp     eax, 20h ; ' '
0x1800098bd  ja      short loc_1800098E3
0x1800098bf  mov     rcx, 100010001h
0x1800098c9  bt      rcx, rax
0x1800098cd  jnb     short loc_1800098E3
0x1800098cf  mov     r8d, cs:__favor
0x1800098d6  or      r8d, 1
0x1800098da  mov     cs:__favor, r8d
0x1800098e1  jmp     short loc_1800098EA
0x1800098e3  mov     r8d, cs:__favor
0x1800098ea  xor     r10d, r10d
0x1800098ed  xor     r11d, r11d
0x1800098f0  cmp     ebp, 7
0x1800098f3  jl      short loc_180009937
0x1800098f5  xor     ecx, ecx
0x1800098f7  lea     eax, [r10+7]
0x1800098fb  cpuid
0x1800098fd  mov     esi, edx
0x1800098ff  mov     r9d, ebx
0x180009902  bt      ebx, 9
0x180009906  jnb     short loc_180009913
0x180009908  or      r8d, 2
0x18000990c  mov     cs:__favor, r8d
0x180009913  cmp     eax, 1
0x180009916  jl      short loc_180009925
0x180009918  mov     eax, 7
0x18000991d  lea     ecx, [rax-6]
0x180009920  cpuid
0x180009922  mov     r10d, edx
0x180009925  mov     eax, 24h ; '$'
0x18000992a  cmp     ebp, eax
0x18000992c  jl      short loc_18000993C
0x18000992e  xor     ecx, ecx
0x180009930  cpuid
0x180009932  mov     r11d, ebx
0x180009935  jmp     short loc_18000993C
0x180009937  xor     r9d, r9d
0x18000993a  xor     esi, esi
0x18000993c  mov     rax, cs:__isa_inverted
0x180009943  and     rax, 0FFFFFFFFFFFFFFFEh
0x180009947  mov     cs:__isa_available, 1
0x180009951  mov     cs:__isa_enabled, 2
0x18000995b  mov     cs:__isa_inverted, rax
0x180009962  bt      edi, 14h
0x180009966  jnb     short loc_180009987
0x180009968  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000996c  mov     cs:__isa_available, 2
0x180009976  mov     cs:__isa_inverted, rax
0x18000997d  mov     cs:__isa_enabled, 6
0x180009987  bt      edi, 1Bh
0x18000998b  jnb     loc_180009AC8
0x180009991  xor     ecx, ecx
0x180009993  xgetbv
0x180009996  shl     rdx, 20h
0x18000999a  or      rdx, rax
0x18000999d  mov     [rsp+38h+arg_0], rdx
0x1800099a2  bt      edi, 1Ch
0x1800099a6  jnb     loc_180009AAC
0x1800099ac  mov     rax, [rsp+38h+arg_0]
0x1800099b1  and     al, 6
0x1800099b3  cmp     al, 6
0x1800099b5  jnz     loc_180009AAC
0x1800099bb  mov     eax, cs:__isa_enabled
0x1800099c1  mov     dl, 0E0h
0x1800099c3  or      eax, 8
0x1800099c6  mov     cs:__isa_available, 3
0x1800099d0  mov     cs:__isa_enabled, eax
0x1800099d6  test    r9b, 20h
0x1800099da  jz      short loc_180009A3E
0x1800099dc  or      eax, 20h
0x1800099df  mov     cs:__isa_available, 5
0x1800099e9  mov     cs:__isa_enabled, eax
0x1800099ef  mov     ecx, 0D0030000h
0x1800099f4  mov     rax, cs:__isa_inverted
0x1800099fb  and     r9d, ecx
0x1800099fe  and     rax, 0FFFFFFFFFFFFFFFDh
0x180009a02  mov     cs:__isa_inverted, rax
0x180009a09  cmp     r9d, ecx
0x180009a0c  jnz     short loc_180009A45
0x180009a0e  mov     rax, [rsp+38h+arg_0]
0x180009a13  and     al, dl
0x180009a15  cmp     al, dl
0x180009a17  jnz     short loc_180009A3E
0x180009a19  mov     rax, cs:__isa_inverted
0x180009a20  or      cs:__isa_enabled, 40h
0x180009a27  and     rax, 0FFFFFFFFFFFFFFDBh
0x180009a2b  mov     cs:__isa_available, 6
0x180009a35  mov     cs:__isa_inverted, rax
0x180009a3c  jmp     short loc_180009A45
0x180009a3e  mov     rax, cs:__isa_inverted
0x180009a45  bt      esi, 17h
0x180009a49  jnb     short loc_180009A57
0x180009a4b  btr     rax, 18h
0x180009a50  mov     cs:__isa_inverted, rax
0x180009a57  bt      r10d, 13h
0x180009a5c  jnb     short loc_180009AAC
0x180009a5e  mov     rax, [rsp+38h+arg_0]
0x180009a63  and     al, dl
0x180009a65  cmp     al, dl
0x180009a67  jnz     short loc_180009AAC
0x180009a69  mov     rdx, cs:__isa_inverted
0x180009a70  mov     eax, r11d
0x180009a73  shr     rax, 10h
0x180009a77  mov     ecx, r11d
0x180009a7a  and     eax, 6
0x180009a7d  and     ecx, 400FFh
0x180009a83  or      rax, 1000029h
0x180009a89  mov     cs:__avx10_version, ecx
0x180009a8f  not     rax
0x180009a92  and     rdx, rax
0x180009a95  mov     cs:__isa_inverted, rdx
0x180009a9c  cmp     cl, 1
0x180009a9f  jbe     short loc_180009AAC
0x180009aa1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180009aa5  mov     cs:__isa_inverted, rdx
0x180009aac  bt      r10d, 15h
0x180009ab1  jnb     short loc_180009AC8
0x180009ab3  mov     rax, [rsp+38h+arg_0]
0x180009ab8  bt      rax, 13h
0x180009abd  jnb     short loc_180009AC8
0x180009abf  btr     cs:__isa_inverted, 7
0x180009ac8  xor     eax, eax
0x180009aca  add     rsp, 18h
0x180009ace  pop     rdi
0x180009acf  pop     rsi
0x180009ad0  pop     rbp
0x180009ad1  pop     rbx
0x180009ad2  retn
```
