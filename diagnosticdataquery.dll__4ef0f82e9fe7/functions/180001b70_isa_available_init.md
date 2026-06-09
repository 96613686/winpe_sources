# __isa_available_init

- ea: `0x180001b70`
- end: `0x180001df3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001564`
- `0x1800016a0`

## callees

- `0x180001b70`

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
0x180001b70  push    rbx
0x180001b72  push    rbp
0x180001b73  push    rsi
0x180001b74  push    rdi
0x180001b75  sub     rsp, 18h
0x180001b79  xor     eax, eax
0x180001b7b  xor     ecx, ecx
0x180001b7d  cpuid
0x180001b7f  xor     ecx, 6C65746Eh
0x180001b85  xor     edx, 49656E69h
0x180001b8b  or      edx, ecx
0x180001b8d  mov     ebp, eax
0x180001b8f  mov     eax, 1
0x180001b94  xor     ebx, 756E6547h
0x180001b9a  or      edx, ebx
0x180001b9c  lea     ecx, [rax-1]
0x180001b9f  cpuid
0x180001ba1  mov     edi, ecx
0x180001ba3  jnz     short loc_180001C03
0x180001ba5  and     eax, 0FFF3FF0h
0x180001baa  mov     cs:__memset_fast_string_threshold, 8000h
0x180001bb5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001bc0  cmp     eax, 106C0h
0x180001bc5  jz      short loc_180001BEF
0x180001bc7  cmp     eax, 20660h
0x180001bcc  jz      short loc_180001BEF
0x180001bce  cmp     eax, 20670h
0x180001bd3  jz      short loc_180001BEF
0x180001bd5  add     eax, 0FFFCF9B0h
0x180001bda  cmp     eax, 20h ; ' '
0x180001bdd  ja      short loc_180001C03
0x180001bdf  mov     rcx, 100010001h
0x180001be9  bt      rcx, rax
0x180001bed  jnb     short loc_180001C03
0x180001bef  mov     r8d, cs:__favor
0x180001bf6  or      r8d, 1
0x180001bfa  mov     cs:__favor, r8d
0x180001c01  jmp     short loc_180001C0A
0x180001c03  mov     r8d, cs:__favor
0x180001c0a  xor     r10d, r10d
0x180001c0d  xor     r11d, r11d
0x180001c10  cmp     ebp, 7
0x180001c13  jl      short loc_180001C57
0x180001c15  xor     ecx, ecx
0x180001c17  lea     eax, [r10+7]
0x180001c1b  cpuid
0x180001c1d  mov     esi, edx
0x180001c1f  mov     r9d, ebx
0x180001c22  bt      ebx, 9
0x180001c26  jnb     short loc_180001C33
0x180001c28  or      r8d, 2
0x180001c2c  mov     cs:__favor, r8d
0x180001c33  cmp     eax, 1
0x180001c36  jl      short loc_180001C45
0x180001c38  mov     eax, 7
0x180001c3d  lea     ecx, [rax-6]
0x180001c40  cpuid
0x180001c42  mov     r10d, edx
0x180001c45  mov     eax, 24h ; '$'
0x180001c4a  cmp     ebp, eax
0x180001c4c  jl      short loc_180001C5C
0x180001c4e  xor     ecx, ecx
0x180001c50  cpuid
0x180001c52  mov     r11d, ebx
0x180001c55  jmp     short loc_180001C5C
0x180001c57  xor     r9d, r9d
0x180001c5a  xor     esi, esi
0x180001c5c  mov     rax, cs:__isa_inverted
0x180001c63  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001c67  mov     cs:__isa_available, 1
0x180001c71  mov     cs:__isa_enabled, 2
0x180001c7b  mov     cs:__isa_inverted, rax
0x180001c82  bt      edi, 14h
0x180001c86  jnb     short loc_180001CA7
0x180001c88  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001c8c  mov     cs:__isa_available, 2
0x180001c96  mov     cs:__isa_inverted, rax
0x180001c9d  mov     cs:__isa_enabled, 6
0x180001ca7  bt      edi, 1Bh
0x180001cab  jnb     loc_180001DE8
0x180001cb1  xor     ecx, ecx
0x180001cb3  xgetbv
0x180001cb6  shl     rdx, 20h
0x180001cba  or      rdx, rax
0x180001cbd  mov     [rsp+38h+arg_0], rdx
0x180001cc2  bt      edi, 1Ch
0x180001cc6  jnb     loc_180001DCC
0x180001ccc  mov     rax, [rsp+38h+arg_0]
0x180001cd1  and     al, 6
0x180001cd3  cmp     al, 6
0x180001cd5  jnz     loc_180001DCC
0x180001cdb  mov     eax, cs:__isa_enabled
0x180001ce1  mov     dl, 0E0h
0x180001ce3  or      eax, 8
0x180001ce6  mov     cs:__isa_available, 3
0x180001cf0  mov     cs:__isa_enabled, eax
0x180001cf6  test    r9b, 20h
0x180001cfa  jz      short loc_180001D5E
0x180001cfc  or      eax, 20h
0x180001cff  mov     cs:__isa_available, 5
0x180001d09  mov     cs:__isa_enabled, eax
0x180001d0f  mov     ecx, 0D0030000h
0x180001d14  mov     rax, cs:__isa_inverted
0x180001d1b  and     r9d, ecx
0x180001d1e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001d22  mov     cs:__isa_inverted, rax
0x180001d29  cmp     r9d, ecx
0x180001d2c  jnz     short loc_180001D65
0x180001d2e  mov     rax, [rsp+38h+arg_0]
0x180001d33  and     al, dl
0x180001d35  cmp     al, dl
0x180001d37  jnz     short loc_180001D5E
0x180001d39  mov     rax, cs:__isa_inverted
0x180001d40  or      cs:__isa_enabled, 40h
0x180001d47  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001d4b  mov     cs:__isa_available, 6
0x180001d55  mov     cs:__isa_inverted, rax
0x180001d5c  jmp     short loc_180001D65
0x180001d5e  mov     rax, cs:__isa_inverted
0x180001d65  bt      esi, 17h
0x180001d69  jnb     short loc_180001D77
0x180001d6b  btr     rax, 18h
0x180001d70  mov     cs:__isa_inverted, rax
0x180001d77  bt      r10d, 13h
0x180001d7c  jnb     short loc_180001DCC
0x180001d7e  mov     rax, [rsp+38h+arg_0]
0x180001d83  and     al, dl
0x180001d85  cmp     al, dl
0x180001d87  jnz     short loc_180001DCC
0x180001d89  mov     rdx, cs:__isa_inverted
0x180001d90  mov     eax, r11d
0x180001d93  shr     rax, 10h
0x180001d97  mov     ecx, r11d
0x180001d9a  and     eax, 6
0x180001d9d  and     ecx, 400FFh
0x180001da3  or      rax, 1000029h
0x180001da9  mov     cs:__avx10_version, ecx
0x180001daf  not     rax
0x180001db2  and     rdx, rax
0x180001db5  mov     cs:__isa_inverted, rdx
0x180001dbc  cmp     cl, 1
0x180001dbf  jbe     short loc_180001DCC
0x180001dc1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001dc5  mov     cs:__isa_inverted, rdx
0x180001dcc  bt      r10d, 15h
0x180001dd1  jnb     short loc_180001DE8
0x180001dd3  mov     rax, [rsp+38h+arg_0]
0x180001dd8  bt      rax, 13h
0x180001ddd  jnb     short loc_180001DE8
0x180001ddf  btr     cs:__isa_inverted, 7
0x180001de8  xor     eax, eax
0x180001dea  add     rsp, 18h
0x180001dee  pop     rdi
0x180001def  pop     rsi
0x180001df0  pop     rbp
0x180001df1  pop     rbx
0x180001df2  retn
```
