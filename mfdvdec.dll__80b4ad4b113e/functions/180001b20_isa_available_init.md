# __isa_available_init

- ea: `0x180001b20`
- end: `0x180001da3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016ec`
- `0x180001828`

## callees

- `0x180001b20`

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
0x180001b20  push    rbx
0x180001b22  push    rbp
0x180001b23  push    rsi
0x180001b24  push    rdi
0x180001b25  sub     rsp, 18h
0x180001b29  xor     eax, eax
0x180001b2b  xor     ecx, ecx
0x180001b2d  cpuid
0x180001b2f  xor     ecx, 6C65746Eh
0x180001b35  xor     edx, 49656E69h
0x180001b3b  or      edx, ecx
0x180001b3d  mov     ebp, eax
0x180001b3f  mov     eax, 1
0x180001b44  xor     ebx, 756E6547h
0x180001b4a  or      edx, ebx
0x180001b4c  lea     ecx, [rax-1]
0x180001b4f  cpuid
0x180001b51  mov     edi, ecx
0x180001b53  jnz     short loc_180001BB3
0x180001b55  and     eax, 0FFF3FF0h
0x180001b5a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001b65  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001b70  cmp     eax, 106C0h
0x180001b75  jz      short loc_180001B9F
0x180001b77  cmp     eax, 20660h
0x180001b7c  jz      short loc_180001B9F
0x180001b7e  cmp     eax, 20670h
0x180001b83  jz      short loc_180001B9F
0x180001b85  add     eax, 0FFFCF9B0h
0x180001b8a  cmp     eax, 20h ; ' '
0x180001b8d  ja      short loc_180001BB3
0x180001b8f  mov     rcx, 100010001h
0x180001b99  bt      rcx, rax
0x180001b9d  jnb     short loc_180001BB3
0x180001b9f  mov     r8d, cs:__favor
0x180001ba6  or      r8d, 1
0x180001baa  mov     cs:__favor, r8d
0x180001bb1  jmp     short loc_180001BBA
0x180001bb3  mov     r8d, cs:__favor
0x180001bba  xor     r10d, r10d
0x180001bbd  xor     r11d, r11d
0x180001bc0  cmp     ebp, 7
0x180001bc3  jl      short loc_180001C07
0x180001bc5  xor     ecx, ecx
0x180001bc7  lea     eax, [r10+7]
0x180001bcb  cpuid
0x180001bcd  mov     esi, edx
0x180001bcf  mov     r9d, ebx
0x180001bd2  bt      ebx, 9
0x180001bd6  jnb     short loc_180001BE3
0x180001bd8  or      r8d, 2
0x180001bdc  mov     cs:__favor, r8d
0x180001be3  cmp     eax, 1
0x180001be6  jl      short loc_180001BF5
0x180001be8  mov     eax, 7
0x180001bed  lea     ecx, [rax-6]
0x180001bf0  cpuid
0x180001bf2  mov     r10d, edx
0x180001bf5  mov     eax, 24h ; '$'
0x180001bfa  cmp     ebp, eax
0x180001bfc  jl      short loc_180001C0C
0x180001bfe  xor     ecx, ecx
0x180001c00  cpuid
0x180001c02  mov     r11d, ebx
0x180001c05  jmp     short loc_180001C0C
0x180001c07  xor     r9d, r9d
0x180001c0a  xor     esi, esi
0x180001c0c  mov     rax, cs:__isa_inverted
0x180001c13  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001c17  mov     cs:__isa_available, 1
0x180001c21  mov     cs:__isa_enabled, 2
0x180001c2b  mov     cs:__isa_inverted, rax
0x180001c32  bt      edi, 14h
0x180001c36  jnb     short loc_180001C57
0x180001c38  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001c3c  mov     cs:__isa_available, 2
0x180001c46  mov     cs:__isa_inverted, rax
0x180001c4d  mov     cs:__isa_enabled, 6
0x180001c57  bt      edi, 1Bh
0x180001c5b  jnb     loc_180001D98
0x180001c61  xor     ecx, ecx
0x180001c63  xgetbv
0x180001c66  shl     rdx, 20h
0x180001c6a  or      rdx, rax
0x180001c6d  mov     [rsp+38h+arg_0], rdx
0x180001c72  bt      edi, 1Ch
0x180001c76  jnb     loc_180001D7C
0x180001c7c  mov     rax, [rsp+38h+arg_0]
0x180001c81  and     al, 6
0x180001c83  cmp     al, 6
0x180001c85  jnz     loc_180001D7C
0x180001c8b  mov     eax, cs:__isa_enabled
0x180001c91  mov     dl, 0E0h
0x180001c93  or      eax, 8
0x180001c96  mov     cs:__isa_available, 3
0x180001ca0  mov     cs:__isa_enabled, eax
0x180001ca6  test    r9b, 20h
0x180001caa  jz      short loc_180001D0E
0x180001cac  or      eax, 20h
0x180001caf  mov     cs:__isa_available, 5
0x180001cb9  mov     cs:__isa_enabled, eax
0x180001cbf  mov     ecx, 0D0030000h
0x180001cc4  mov     rax, cs:__isa_inverted
0x180001ccb  and     r9d, ecx
0x180001cce  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001cd2  mov     cs:__isa_inverted, rax
0x180001cd9  cmp     r9d, ecx
0x180001cdc  jnz     short loc_180001D15
0x180001cde  mov     rax, [rsp+38h+arg_0]
0x180001ce3  and     al, dl
0x180001ce5  cmp     al, dl
0x180001ce7  jnz     short loc_180001D0E
0x180001ce9  mov     rax, cs:__isa_inverted
0x180001cf0  or      cs:__isa_enabled, 40h
0x180001cf7  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001cfb  mov     cs:__isa_available, 6
0x180001d05  mov     cs:__isa_inverted, rax
0x180001d0c  jmp     short loc_180001D15
0x180001d0e  mov     rax, cs:__isa_inverted
0x180001d15  bt      esi, 17h
0x180001d19  jnb     short loc_180001D27
0x180001d1b  btr     rax, 18h
0x180001d20  mov     cs:__isa_inverted, rax
0x180001d27  bt      r10d, 13h
0x180001d2c  jnb     short loc_180001D7C
0x180001d2e  mov     rax, [rsp+38h+arg_0]
0x180001d33  and     al, dl
0x180001d35  cmp     al, dl
0x180001d37  jnz     short loc_180001D7C
0x180001d39  mov     rdx, cs:__isa_inverted
0x180001d40  mov     eax, r11d
0x180001d43  shr     rax, 10h
0x180001d47  mov     ecx, r11d
0x180001d4a  and     eax, 6
0x180001d4d  and     ecx, 400FFh
0x180001d53  or      rax, 1000029h
0x180001d59  mov     cs:__avx10_version, ecx
0x180001d5f  not     rax
0x180001d62  and     rdx, rax
0x180001d65  mov     cs:__isa_inverted, rdx
0x180001d6c  cmp     cl, 1
0x180001d6f  jbe     short loc_180001D7C
0x180001d71  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001d75  mov     cs:__isa_inverted, rdx
0x180001d7c  bt      r10d, 15h
0x180001d81  jnb     short loc_180001D98
0x180001d83  mov     rax, [rsp+38h+arg_0]
0x180001d88  bt      rax, 13h
0x180001d8d  jnb     short loc_180001D98
0x180001d8f  btr     cs:__isa_inverted, 7
0x180001d98  xor     eax, eax
0x180001d9a  add     rsp, 18h
0x180001d9e  pop     rdi
0x180001d9f  pop     rsi
0x180001da0  pop     rbp
0x180001da1  pop     rbx
0x180001da2  retn
```
