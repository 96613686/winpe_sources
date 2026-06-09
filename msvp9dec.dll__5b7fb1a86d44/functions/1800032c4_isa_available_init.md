# __isa_available_init

- ea: `0x1800032c4`
- end: `0x180003547`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d38`
- `0x180002e74`

## callees

- `0x1800032c4`

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
0x1800032c4  push    rbx
0x1800032c6  push    rbp
0x1800032c7  push    rsi
0x1800032c8  push    rdi
0x1800032c9  sub     rsp, 18h
0x1800032cd  xor     eax, eax
0x1800032cf  xor     ecx, ecx
0x1800032d1  cpuid
0x1800032d3  xor     ecx, 6C65746Eh
0x1800032d9  xor     edx, 49656E69h
0x1800032df  or      edx, ecx
0x1800032e1  mov     ebp, eax
0x1800032e3  mov     eax, 1
0x1800032e8  xor     ebx, 756E6547h
0x1800032ee  or      edx, ebx
0x1800032f0  lea     ecx, [rax-1]
0x1800032f3  cpuid
0x1800032f5  mov     edi, ecx
0x1800032f7  jnz     short loc_180003357
0x1800032f9  and     eax, 0FFF3FF0h
0x1800032fe  mov     cs:__memset_fast_string_threshold, 8000h
0x180003309  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180003314  cmp     eax, 106C0h
0x180003319  jz      short loc_180003343
0x18000331b  cmp     eax, 20660h
0x180003320  jz      short loc_180003343
0x180003322  cmp     eax, 20670h
0x180003327  jz      short loc_180003343
0x180003329  add     eax, 0FFFCF9B0h
0x18000332e  cmp     eax, 20h ; ' '
0x180003331  ja      short loc_180003357
0x180003333  mov     rcx, 100010001h
0x18000333d  bt      rcx, rax
0x180003341  jnb     short loc_180003357
0x180003343  mov     r8d, cs:__favor
0x18000334a  or      r8d, 1
0x18000334e  mov     cs:__favor, r8d
0x180003355  jmp     short loc_18000335E
0x180003357  mov     r8d, cs:__favor
0x18000335e  xor     r10d, r10d
0x180003361  xor     r11d, r11d
0x180003364  cmp     ebp, 7
0x180003367  jl      short loc_1800033AB
0x180003369  xor     ecx, ecx
0x18000336b  lea     eax, [r10+7]
0x18000336f  cpuid
0x180003371  mov     esi, edx
0x180003373  mov     r9d, ebx
0x180003376  bt      ebx, 9
0x18000337a  jnb     short loc_180003387
0x18000337c  or      r8d, 2
0x180003380  mov     cs:__favor, r8d
0x180003387  cmp     eax, 1
0x18000338a  jl      short loc_180003399
0x18000338c  mov     eax, 7
0x180003391  lea     ecx, [rax-6]
0x180003394  cpuid
0x180003396  mov     r10d, edx
0x180003399  mov     eax, 24h ; '$'
0x18000339e  cmp     ebp, eax
0x1800033a0  jl      short loc_1800033B0
0x1800033a2  xor     ecx, ecx
0x1800033a4  cpuid
0x1800033a6  mov     r11d, ebx
0x1800033a9  jmp     short loc_1800033B0
0x1800033ab  xor     r9d, r9d
0x1800033ae  xor     esi, esi
0x1800033b0  mov     rax, cs:__isa_inverted
0x1800033b7  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800033bb  mov     cs:__isa_available, 1
0x1800033c5  mov     cs:__isa_enabled, 2
0x1800033cf  mov     cs:__isa_inverted, rax
0x1800033d6  bt      edi, 14h
0x1800033da  jnb     short loc_1800033FB
0x1800033dc  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800033e0  mov     cs:__isa_available, 2
0x1800033ea  mov     cs:__isa_inverted, rax
0x1800033f1  mov     cs:__isa_enabled, 6
0x1800033fb  bt      edi, 1Bh
0x1800033ff  jnb     loc_18000353C
0x180003405  xor     ecx, ecx
0x180003407  xgetbv
0x18000340a  shl     rdx, 20h
0x18000340e  or      rdx, rax
0x180003411  mov     [rsp+38h+arg_0], rdx
0x180003416  bt      edi, 1Ch
0x18000341a  jnb     loc_180003520
0x180003420  mov     rax, [rsp+38h+arg_0]
0x180003425  and     al, 6
0x180003427  cmp     al, 6
0x180003429  jnz     loc_180003520
0x18000342f  mov     eax, cs:__isa_enabled
0x180003435  mov     dl, 0E0h
0x180003437  or      eax, 8
0x18000343a  mov     cs:__isa_available, 3
0x180003444  mov     cs:__isa_enabled, eax
0x18000344a  test    r9b, 20h
0x18000344e  jz      short loc_1800034B2
0x180003450  or      eax, 20h
0x180003453  mov     cs:__isa_available, 5
0x18000345d  mov     cs:__isa_enabled, eax
0x180003463  mov     ecx, 0D0030000h
0x180003468  mov     rax, cs:__isa_inverted
0x18000346f  and     r9d, ecx
0x180003472  and     rax, 0FFFFFFFFFFFFFFFDh
0x180003476  mov     cs:__isa_inverted, rax
0x18000347d  cmp     r9d, ecx
0x180003480  jnz     short loc_1800034B9
0x180003482  mov     rax, [rsp+38h+arg_0]
0x180003487  and     al, dl
0x180003489  cmp     al, dl
0x18000348b  jnz     short loc_1800034B2
0x18000348d  mov     rax, cs:__isa_inverted
0x180003494  or      cs:__isa_enabled, 40h
0x18000349b  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000349f  mov     cs:__isa_available, 6
0x1800034a9  mov     cs:__isa_inverted, rax
0x1800034b0  jmp     short loc_1800034B9
0x1800034b2  mov     rax, cs:__isa_inverted
0x1800034b9  bt      esi, 17h
0x1800034bd  jnb     short loc_1800034CB
0x1800034bf  btr     rax, 18h
0x1800034c4  mov     cs:__isa_inverted, rax
0x1800034cb  bt      r10d, 13h
0x1800034d0  jnb     short loc_180003520
0x1800034d2  mov     rax, [rsp+38h+arg_0]
0x1800034d7  and     al, dl
0x1800034d9  cmp     al, dl
0x1800034db  jnz     short loc_180003520
0x1800034dd  mov     rdx, cs:__isa_inverted
0x1800034e4  mov     eax, r11d
0x1800034e7  shr     rax, 10h
0x1800034eb  mov     ecx, r11d
0x1800034ee  and     eax, 6
0x1800034f1  and     ecx, 400FFh
0x1800034f7  or      rax, 1000029h
0x1800034fd  mov     cs:__avx10_version, ecx
0x180003503  not     rax
0x180003506  and     rdx, rax
0x180003509  mov     cs:__isa_inverted, rdx
0x180003510  cmp     cl, 1
0x180003513  jbe     short loc_180003520
0x180003515  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180003519  mov     cs:__isa_inverted, rdx
0x180003520  bt      r10d, 15h
0x180003525  jnb     short loc_18000353C
0x180003527  mov     rax, [rsp+38h+arg_0]
0x18000352c  bt      rax, 13h
0x180003531  jnb     short loc_18000353C
0x180003533  btr     cs:__isa_inverted, 7
0x18000353c  xor     eax, eax
0x18000353e  add     rsp, 18h
0x180003542  pop     rdi
0x180003543  pop     rsi
0x180003544  pop     rbp
0x180003545  pop     rbx
0x180003546  retn
```
