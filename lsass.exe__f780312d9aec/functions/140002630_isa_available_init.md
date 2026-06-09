# __isa_available_init

- ea: `0x140002630`
- end: `0x1400028b3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002124`

## callees

- `0x140002630`

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
0x140002630  push    rbx
0x140002632  push    rbp
0x140002633  push    rsi
0x140002634  push    rdi
0x140002635  sub     rsp, 18h
0x140002639  xor     eax, eax
0x14000263b  xor     ecx, ecx
0x14000263d  cpuid
0x14000263f  xor     ecx, 6C65746Eh
0x140002645  xor     edx, 49656E69h
0x14000264b  or      edx, ecx
0x14000264d  mov     ebp, eax
0x14000264f  mov     eax, 1
0x140002654  xor     ebx, 756E6547h
0x14000265a  or      edx, ebx
0x14000265c  lea     ecx, [rax-1]
0x14000265f  cpuid
0x140002661  mov     edi, ecx
0x140002663  jnz     short loc_1400026C3
0x140002665  and     eax, 0FFF3FF0h
0x14000266a  mov     cs:__memset_fast_string_threshold, 8000h
0x140002675  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140002680  cmp     eax, 106C0h
0x140002685  jz      short loc_1400026AF
0x140002687  cmp     eax, 20660h
0x14000268c  jz      short loc_1400026AF
0x14000268e  cmp     eax, 20670h
0x140002693  jz      short loc_1400026AF
0x140002695  add     eax, 0FFFCF9B0h
0x14000269a  cmp     eax, 20h ; ' '
0x14000269d  ja      short loc_1400026C3
0x14000269f  mov     rcx, 100010001h
0x1400026a9  bt      rcx, rax
0x1400026ad  jnb     short loc_1400026C3
0x1400026af  mov     r8d, cs:__favor
0x1400026b6  or      r8d, 1
0x1400026ba  mov     cs:__favor, r8d
0x1400026c1  jmp     short loc_1400026CA
0x1400026c3  mov     r8d, cs:__favor
0x1400026ca  xor     r10d, r10d
0x1400026cd  xor     r11d, r11d
0x1400026d0  cmp     ebp, 7
0x1400026d3  jl      short loc_140002717
0x1400026d5  xor     ecx, ecx
0x1400026d7  lea     eax, [r10+7]
0x1400026db  cpuid
0x1400026dd  mov     esi, edx
0x1400026df  mov     r9d, ebx
0x1400026e2  bt      ebx, 9
0x1400026e6  jnb     short loc_1400026F3
0x1400026e8  or      r8d, 2
0x1400026ec  mov     cs:__favor, r8d
0x1400026f3  cmp     eax, 1
0x1400026f6  jl      short loc_140002705
0x1400026f8  mov     eax, 7
0x1400026fd  lea     ecx, [rax-6]
0x140002700  cpuid
0x140002702  mov     r10d, edx
0x140002705  mov     eax, 24h ; '$'
0x14000270a  cmp     ebp, eax
0x14000270c  jl      short loc_14000271C
0x14000270e  xor     ecx, ecx
0x140002710  cpuid
0x140002712  mov     r11d, ebx
0x140002715  jmp     short loc_14000271C
0x140002717  xor     r9d, r9d
0x14000271a  xor     esi, esi
0x14000271c  mov     rax, cs:__isa_inverted
0x140002723  and     rax, 0FFFFFFFFFFFFFFFEh
0x140002727  mov     cs:__isa_available, 1
0x140002731  mov     cs:__isa_enabled, 2
0x14000273b  mov     cs:__isa_inverted, rax
0x140002742  bt      edi, 14h
0x140002746  jnb     short loc_140002767
0x140002748  and     rax, 0FFFFFFFFFFFFFFEFh
0x14000274c  mov     cs:__isa_available, 2
0x140002756  mov     cs:__isa_inverted, rax
0x14000275d  mov     cs:__isa_enabled, 6
0x140002767  bt      edi, 1Bh
0x14000276b  jnb     loc_1400028A8
0x140002771  xor     ecx, ecx
0x140002773  xgetbv
0x140002776  shl     rdx, 20h
0x14000277a  or      rdx, rax
0x14000277d  mov     [rsp+38h+arg_0], rdx
0x140002782  bt      edi, 1Ch
0x140002786  jnb     loc_14000288C
0x14000278c  mov     rax, [rsp+38h+arg_0]
0x140002791  and     al, 6
0x140002793  cmp     al, 6
0x140002795  jnz     loc_14000288C
0x14000279b  mov     eax, cs:__isa_enabled
0x1400027a1  mov     dl, 0E0h
0x1400027a3  or      eax, 8
0x1400027a6  mov     cs:__isa_available, 3
0x1400027b0  mov     cs:__isa_enabled, eax
0x1400027b6  test    r9b, 20h
0x1400027ba  jz      short loc_14000281E
0x1400027bc  or      eax, 20h
0x1400027bf  mov     cs:__isa_available, 5
0x1400027c9  mov     cs:__isa_enabled, eax
0x1400027cf  mov     ecx, 0D0030000h
0x1400027d4  mov     rax, cs:__isa_inverted
0x1400027db  and     r9d, ecx
0x1400027de  and     rax, 0FFFFFFFFFFFFFFFDh
0x1400027e2  mov     cs:__isa_inverted, rax
0x1400027e9  cmp     r9d, ecx
0x1400027ec  jnz     short loc_140002825
0x1400027ee  mov     rax, [rsp+38h+arg_0]
0x1400027f3  and     al, dl
0x1400027f5  cmp     al, dl
0x1400027f7  jnz     short loc_14000281E
0x1400027f9  mov     rax, cs:__isa_inverted
0x140002800  or      cs:__isa_enabled, 40h
0x140002807  and     rax, 0FFFFFFFFFFFFFFDBh
0x14000280b  mov     cs:__isa_available, 6
0x140002815  mov     cs:__isa_inverted, rax
0x14000281c  jmp     short loc_140002825
0x14000281e  mov     rax, cs:__isa_inverted
0x140002825  bt      esi, 17h
0x140002829  jnb     short loc_140002837
0x14000282b  btr     rax, 18h
0x140002830  mov     cs:__isa_inverted, rax
0x140002837  bt      r10d, 13h
0x14000283c  jnb     short loc_14000288C
0x14000283e  mov     rax, [rsp+38h+arg_0]
0x140002843  and     al, dl
0x140002845  cmp     al, dl
0x140002847  jnz     short loc_14000288C
0x140002849  mov     rdx, cs:__isa_inverted
0x140002850  mov     eax, r11d
0x140002853  shr     rax, 10h
0x140002857  mov     ecx, r11d
0x14000285a  and     eax, 6
0x14000285d  and     ecx, 400FFh
0x140002863  or      rax, 1000029h
0x140002869  mov     cs:__avx10_version, ecx
0x14000286f  not     rax
0x140002872  and     rdx, rax
0x140002875  mov     cs:__isa_inverted, rdx
0x14000287c  cmp     cl, 1
0x14000287f  jbe     short loc_14000288C
0x140002881  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140002885  mov     cs:__isa_inverted, rdx
0x14000288c  bt      r10d, 15h
0x140002891  jnb     short loc_1400028A8
0x140002893  mov     rax, [rsp+38h+arg_0]
0x140002898  bt      rax, 13h
0x14000289d  jnb     short loc_1400028A8
0x14000289f  btr     cs:__isa_inverted, 7
0x1400028a8  xor     eax, eax
0x1400028aa  add     rsp, 18h
0x1400028ae  pop     rdi
0x1400028af  pop     rsi
0x1400028b0  pop     rbp
0x1400028b1  pop     rbx
0x1400028b2  retn
```
