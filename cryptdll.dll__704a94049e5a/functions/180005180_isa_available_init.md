# __isa_available_init

- ea: `0x180005180`
- end: `0x180005403`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004dac`
- `0x180004ee8`

## callees

- `0x180005180`

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
0x180005180  push    rbx
0x180005182  push    rbp
0x180005183  push    rsi
0x180005184  push    rdi
0x180005185  sub     rsp, 18h
0x180005189  xor     eax, eax
0x18000518b  xor     ecx, ecx
0x18000518d  cpuid
0x18000518f  xor     ecx, 6C65746Eh
0x180005195  xor     edx, 49656E69h
0x18000519b  or      edx, ecx
0x18000519d  mov     ebp, eax
0x18000519f  mov     eax, 1
0x1800051a4  xor     ebx, 756E6547h
0x1800051aa  or      edx, ebx
0x1800051ac  lea     ecx, [rax-1]
0x1800051af  cpuid
0x1800051b1  mov     edi, ecx
0x1800051b3  jnz     short loc_180005213
0x1800051b5  and     eax, 0FFF3FF0h
0x1800051ba  mov     cs:__memset_fast_string_threshold, 8000h
0x1800051c5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800051d0  cmp     eax, 106C0h
0x1800051d5  jz      short loc_1800051FF
0x1800051d7  cmp     eax, 20660h
0x1800051dc  jz      short loc_1800051FF
0x1800051de  cmp     eax, 20670h
0x1800051e3  jz      short loc_1800051FF
0x1800051e5  add     eax, 0FFFCF9B0h
0x1800051ea  cmp     eax, 20h ; ' '
0x1800051ed  ja      short loc_180005213
0x1800051ef  mov     rcx, 100010001h
0x1800051f9  bt      rcx, rax
0x1800051fd  jnb     short loc_180005213
0x1800051ff  mov     r8d, cs:__favor
0x180005206  or      r8d, 1
0x18000520a  mov     cs:__favor, r8d
0x180005211  jmp     short loc_18000521A
0x180005213  mov     r8d, cs:__favor
0x18000521a  xor     r10d, r10d
0x18000521d  xor     r11d, r11d
0x180005220  cmp     ebp, 7
0x180005223  jl      short loc_180005267
0x180005225  xor     ecx, ecx
0x180005227  lea     eax, [r10+7]
0x18000522b  cpuid
0x18000522d  mov     esi, edx
0x18000522f  mov     r9d, ebx
0x180005232  bt      ebx, 9
0x180005236  jnb     short loc_180005243
0x180005238  or      r8d, 2
0x18000523c  mov     cs:__favor, r8d
0x180005243  cmp     eax, 1
0x180005246  jl      short loc_180005255
0x180005248  mov     eax, 7
0x18000524d  lea     ecx, [rax-6]
0x180005250  cpuid
0x180005252  mov     r10d, edx
0x180005255  mov     eax, 24h ; '$'
0x18000525a  cmp     ebp, eax
0x18000525c  jl      short loc_18000526C
0x18000525e  xor     ecx, ecx
0x180005260  cpuid
0x180005262  mov     r11d, ebx
0x180005265  jmp     short loc_18000526C
0x180005267  xor     r9d, r9d
0x18000526a  xor     esi, esi
0x18000526c  mov     rax, cs:__isa_inverted
0x180005273  and     rax, 0FFFFFFFFFFFFFFFEh
0x180005277  mov     cs:__isa_available, 1
0x180005281  mov     cs:__isa_enabled, 2
0x18000528b  mov     cs:__isa_inverted, rax
0x180005292  bt      edi, 14h
0x180005296  jnb     short loc_1800052B7
0x180005298  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000529c  mov     cs:__isa_available, 2
0x1800052a6  mov     cs:__isa_inverted, rax
0x1800052ad  mov     cs:__isa_enabled, 6
0x1800052b7  bt      edi, 1Bh
0x1800052bb  jnb     loc_1800053F8
0x1800052c1  xor     ecx, ecx
0x1800052c3  xgetbv
0x1800052c6  shl     rdx, 20h
0x1800052ca  or      rdx, rax
0x1800052cd  mov     [rsp+38h+arg_0], rdx
0x1800052d2  bt      edi, 1Ch
0x1800052d6  jnb     loc_1800053DC
0x1800052dc  mov     rax, [rsp+38h+arg_0]
0x1800052e1  and     al, 6
0x1800052e3  cmp     al, 6
0x1800052e5  jnz     loc_1800053DC
0x1800052eb  mov     eax, cs:__isa_enabled
0x1800052f1  mov     dl, 0E0h
0x1800052f3  or      eax, 8
0x1800052f6  mov     cs:__isa_available, 3
0x180005300  mov     cs:__isa_enabled, eax
0x180005306  test    r9b, 20h
0x18000530a  jz      short loc_18000536E
0x18000530c  or      eax, 20h
0x18000530f  mov     cs:__isa_available, 5
0x180005319  mov     cs:__isa_enabled, eax
0x18000531f  mov     ecx, 0D0030000h
0x180005324  mov     rax, cs:__isa_inverted
0x18000532b  and     r9d, ecx
0x18000532e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180005332  mov     cs:__isa_inverted, rax
0x180005339  cmp     r9d, ecx
0x18000533c  jnz     short loc_180005375
0x18000533e  mov     rax, [rsp+38h+arg_0]
0x180005343  and     al, dl
0x180005345  cmp     al, dl
0x180005347  jnz     short loc_18000536E
0x180005349  mov     rax, cs:__isa_inverted
0x180005350  or      cs:__isa_enabled, 40h
0x180005357  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000535b  mov     cs:__isa_available, 6
0x180005365  mov     cs:__isa_inverted, rax
0x18000536c  jmp     short loc_180005375
0x18000536e  mov     rax, cs:__isa_inverted
0x180005375  bt      esi, 17h
0x180005379  jnb     short loc_180005387
0x18000537b  btr     rax, 18h
0x180005380  mov     cs:__isa_inverted, rax
0x180005387  bt      r10d, 13h
0x18000538c  jnb     short loc_1800053DC
0x18000538e  mov     rax, [rsp+38h+arg_0]
0x180005393  and     al, dl
0x180005395  cmp     al, dl
0x180005397  jnz     short loc_1800053DC
0x180005399  mov     rdx, cs:__isa_inverted
0x1800053a0  mov     eax, r11d
0x1800053a3  shr     rax, 10h
0x1800053a7  mov     ecx, r11d
0x1800053aa  and     eax, 6
0x1800053ad  and     ecx, 400FFh
0x1800053b3  or      rax, 1000029h
0x1800053b9  mov     cs:__avx10_version, ecx
0x1800053bf  not     rax
0x1800053c2  and     rdx, rax
0x1800053c5  mov     cs:__isa_inverted, rdx
0x1800053cc  cmp     cl, 1
0x1800053cf  jbe     short loc_1800053DC
0x1800053d1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800053d5  mov     cs:__isa_inverted, rdx
0x1800053dc  bt      r10d, 15h
0x1800053e1  jnb     short loc_1800053F8
0x1800053e3  mov     rax, [rsp+38h+arg_0]
0x1800053e8  bt      rax, 13h
0x1800053ed  jnb     short loc_1800053F8
0x1800053ef  btr     cs:__isa_inverted, 7
0x1800053f8  xor     eax, eax
0x1800053fa  add     rsp, 18h
0x1800053fe  pop     rdi
0x1800053ff  pop     rsi
0x180005400  pop     rbp
0x180005401  pop     rbx
0x180005402  retn
```
