# __isa_available_init

- ea: `0x180001c20`
- end: `0x180001ea3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017a4`
- `0x1800018e0`

## callees

- `0x180001c20`

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
0x180001c20  push    rbx
0x180001c22  push    rbp
0x180001c23  push    rsi
0x180001c24  push    rdi
0x180001c25  sub     rsp, 18h
0x180001c29  xor     eax, eax
0x180001c2b  xor     ecx, ecx
0x180001c2d  cpuid
0x180001c2f  xor     ecx, 6C65746Eh
0x180001c35  xor     edx, 49656E69h
0x180001c3b  or      edx, ecx
0x180001c3d  mov     ebp, eax
0x180001c3f  mov     eax, 1
0x180001c44  xor     ebx, 756E6547h
0x180001c4a  or      edx, ebx
0x180001c4c  lea     ecx, [rax-1]
0x180001c4f  cpuid
0x180001c51  mov     edi, ecx
0x180001c53  jnz     short loc_180001CB3
0x180001c55  and     eax, 0FFF3FF0h
0x180001c5a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001c65  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001c70  cmp     eax, 106C0h
0x180001c75  jz      short loc_180001C9F
0x180001c77  cmp     eax, 20660h
0x180001c7c  jz      short loc_180001C9F
0x180001c7e  cmp     eax, 20670h
0x180001c83  jz      short loc_180001C9F
0x180001c85  add     eax, 0FFFCF9B0h
0x180001c8a  cmp     eax, 20h ; ' '
0x180001c8d  ja      short loc_180001CB3
0x180001c8f  mov     rcx, 100010001h
0x180001c99  bt      rcx, rax
0x180001c9d  jnb     short loc_180001CB3
0x180001c9f  mov     r8d, cs:__favor
0x180001ca6  or      r8d, 1
0x180001caa  mov     cs:__favor, r8d
0x180001cb1  jmp     short loc_180001CBA
0x180001cb3  mov     r8d, cs:__favor
0x180001cba  xor     r10d, r10d
0x180001cbd  xor     r11d, r11d
0x180001cc0  cmp     ebp, 7
0x180001cc3  jl      short loc_180001D07
0x180001cc5  xor     ecx, ecx
0x180001cc7  lea     eax, [r10+7]
0x180001ccb  cpuid
0x180001ccd  mov     esi, edx
0x180001ccf  mov     r9d, ebx
0x180001cd2  bt      ebx, 9
0x180001cd6  jnb     short loc_180001CE3
0x180001cd8  or      r8d, 2
0x180001cdc  mov     cs:__favor, r8d
0x180001ce3  cmp     eax, 1
0x180001ce6  jl      short loc_180001CF5
0x180001ce8  mov     eax, 7
0x180001ced  lea     ecx, [rax-6]
0x180001cf0  cpuid
0x180001cf2  mov     r10d, edx
0x180001cf5  mov     eax, 24h ; '$'
0x180001cfa  cmp     ebp, eax
0x180001cfc  jl      short loc_180001D0C
0x180001cfe  xor     ecx, ecx
0x180001d00  cpuid
0x180001d02  mov     r11d, ebx
0x180001d05  jmp     short loc_180001D0C
0x180001d07  xor     r9d, r9d
0x180001d0a  xor     esi, esi
0x180001d0c  mov     rax, cs:__isa_inverted
0x180001d13  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001d17  mov     cs:__isa_available, 1
0x180001d21  mov     cs:__isa_enabled, 2
0x180001d2b  mov     cs:__isa_inverted, rax
0x180001d32  bt      edi, 14h
0x180001d36  jnb     short loc_180001D57
0x180001d38  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001d3c  mov     cs:__isa_available, 2
0x180001d46  mov     cs:__isa_inverted, rax
0x180001d4d  mov     cs:__isa_enabled, 6
0x180001d57  bt      edi, 1Bh
0x180001d5b  jnb     loc_180001E98
0x180001d61  xor     ecx, ecx
0x180001d63  xgetbv
0x180001d66  shl     rdx, 20h
0x180001d6a  or      rdx, rax
0x180001d6d  mov     [rsp+38h+arg_0], rdx
0x180001d72  bt      edi, 1Ch
0x180001d76  jnb     loc_180001E7C
0x180001d7c  mov     rax, [rsp+38h+arg_0]
0x180001d81  and     al, 6
0x180001d83  cmp     al, 6
0x180001d85  jnz     loc_180001E7C
0x180001d8b  mov     eax, cs:__isa_enabled
0x180001d91  mov     dl, 0E0h
0x180001d93  or      eax, 8
0x180001d96  mov     cs:__isa_available, 3
0x180001da0  mov     cs:__isa_enabled, eax
0x180001da6  test    r9b, 20h
0x180001daa  jz      short loc_180001E0E
0x180001dac  or      eax, 20h
0x180001daf  mov     cs:__isa_available, 5
0x180001db9  mov     cs:__isa_enabled, eax
0x180001dbf  mov     ecx, 0D0030000h
0x180001dc4  mov     rax, cs:__isa_inverted
0x180001dcb  and     r9d, ecx
0x180001dce  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001dd2  mov     cs:__isa_inverted, rax
0x180001dd9  cmp     r9d, ecx
0x180001ddc  jnz     short loc_180001E15
0x180001dde  mov     rax, [rsp+38h+arg_0]
0x180001de3  and     al, dl
0x180001de5  cmp     al, dl
0x180001de7  jnz     short loc_180001E0E
0x180001de9  mov     rax, cs:__isa_inverted
0x180001df0  or      cs:__isa_enabled, 40h
0x180001df7  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001dfb  mov     cs:__isa_available, 6
0x180001e05  mov     cs:__isa_inverted, rax
0x180001e0c  jmp     short loc_180001E15
0x180001e0e  mov     rax, cs:__isa_inverted
0x180001e15  bt      esi, 17h
0x180001e19  jnb     short loc_180001E27
0x180001e1b  btr     rax, 18h
0x180001e20  mov     cs:__isa_inverted, rax
0x180001e27  bt      r10d, 13h
0x180001e2c  jnb     short loc_180001E7C
0x180001e2e  mov     rax, [rsp+38h+arg_0]
0x180001e33  and     al, dl
0x180001e35  cmp     al, dl
0x180001e37  jnz     short loc_180001E7C
0x180001e39  mov     rdx, cs:__isa_inverted
0x180001e40  mov     eax, r11d
0x180001e43  shr     rax, 10h
0x180001e47  mov     ecx, r11d
0x180001e4a  and     eax, 6
0x180001e4d  and     ecx, 400FFh
0x180001e53  or      rax, 1000029h
0x180001e59  mov     cs:__avx10_version, ecx
0x180001e5f  not     rax
0x180001e62  and     rdx, rax
0x180001e65  mov     cs:__isa_inverted, rdx
0x180001e6c  cmp     cl, 1
0x180001e6f  jbe     short loc_180001E7C
0x180001e71  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001e75  mov     cs:__isa_inverted, rdx
0x180001e7c  bt      r10d, 15h
0x180001e81  jnb     short loc_180001E98
0x180001e83  mov     rax, [rsp+38h+arg_0]
0x180001e88  bt      rax, 13h
0x180001e8d  jnb     short loc_180001E98
0x180001e8f  btr     cs:__isa_inverted, 7
0x180001e98  xor     eax, eax
0x180001e9a  add     rsp, 18h
0x180001e9e  pop     rdi
0x180001e9f  pop     rsi
0x180001ea0  pop     rbp
0x180001ea1  pop     rbx
0x180001ea2  retn
```
