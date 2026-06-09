# ___isa_available_init

- ea: `0x100130c5`
- end: `0x100133e1`
- name: `___isa_available_init`
- size: `796`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10012cd5`
- `0x10012dc5`

## callees

- `0x100130c5`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x100130e0`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x100130e0`

## pseudocode

```c
int __cdecl __isa_available_init()
{
  bool v5; // zf
  int v11; // eax
  int v12; // edx
  int v28; // eax
  unsigned int v29; // ecx
  int v31; // [esp+0h] [ebp-28h]
  int v32; // [esp+1Ch] [ebp-Ch]
  int v33; // [esp+24h] [ebp-4h]

  __isa_enabled |= 1u;
  __isa_available = 0;
  if ( IsProcessorFeaturePresent(0xAu) )
  {
    _EAX = 0;
    __asm { cpuid }
    v33 = _EAX;
    v5 = (_EBX ^ 0x756E6547 | _ECX ^ 0x6C65746E | _EDX ^ 0x49656E69) == 0;
    _EAX = 1;
    __asm { cpuid }
    v31 = _EAX;
    if ( v5 )
    {
      v11 = _EAX & 0xFFF3FF0;
      if ( (v31 & 0xFFF3FF0) == 0x106C0
        || v11 == 132704
        || v11 == 132720
        || v11 == 198224
        || v11 == 198240
        || v11 == 198256 )
      {
        __favor |= 1u;
      }
    }
    v12 = _ECX;
    v32 = _ECX;
    if ( v33 >= 7 )
    {
      _EAX = 7;
      __asm { cpuid }
      if ( (_EBX & 0x200) != 0 )
        __favor |= 2u;
      if ( _EAX >= 1 )
      {
        _EAX = 7;
        __asm { cpuid }
      }
      _EAX = 36;
      if ( v33 >= 36 )
        __asm { cpuid }
      v12 = v32;
    }
    v28 = __isa_enabled | 2;
    v29 = __isa_inverted & 0xFFFFFFFE;
    __isa_available = 1;
    __isa_enabled |= 2u;
    __isa_inverted &= ~1u;
    if ( (v12 & 0x100000) != 0 )
    {
      __isa_available = 2;
      __isa_enabled = v28 | 4;
      __isa_inverted = v29 & 0xFFFFFFEF;
      if ( (v12 & 0x18000000) == 0x18000000 )
        __asm { xgetbv }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100130c5  mov     edi, edi
0x100130c7  push    ebp
0x100130c8  mov     ebp, esp
0x100130ca  or      ___isa_enabled, 1
0x100130d1  sub     esp, 28h
0x100130d4  mov     ___isa_available, 0
0x100130de  push    0Ah; ProcessorFeature
0x100130e0  call    ds:__imp__IsProcessorFeaturePresent@4; IsProcessorFeaturePresent(x)
0x100130e6  test    eax, eax
0x100130e8  jz      loc_100133DD
0x100130ee  push    ebx
0x100130ef  push    esi
0x100130f0  push    edi
0x100130f1  xor     eax, eax
0x100130f3  lea     edi, [ebp+var_28]
0x100130f6  xor     ecx, ecx
0x100130f8  push    ebx
0x100130f9  cpuid
0x100130fb  mov     esi, ebx
0x100130fd  pop     ebx
0x100130fe  nop
0x100130ff  mov     [edi], eax
0x10013101  mov     [edi+4], esi
0x10013104  mov     [edi+8], ecx
0x10013107  mov     [edi+0Ch], edx
0x1001310a  mov     eax, [ebp+var_28]
0x1001310d  mov     ecx, [ebp+var_1C]
0x10013110  mov     [ebp+var_4], eax
0x10013113  xor     ecx, 49656E69h
0x10013119  mov     eax, [ebp+var_20]
0x1001311c  xor     eax, 6C65746Eh
0x10013121  or      ecx, eax
0x10013123  mov     eax, [ebp+var_24]
0x10013126  push    1
0x10013128  xor     eax, 756E6547h
0x1001312d  or      ecx, eax
0x1001312f  pop     eax
0x10013130  push    0
0x10013132  pop     ecx
0x10013133  push    ebx
0x10013134  cpuid
0x10013136  mov     esi, ebx
0x10013138  pop     ebx
0x10013139  nop
0x1001313a  mov     [edi], eax
0x1001313c  mov     [edi+4], esi
0x1001313f  mov     [edi+8], ecx
0x10013142  mov     [edi+0Ch], edx
0x10013145  jnz     short loc_10013180
0x10013147  mov     eax, [ebp+var_28]
0x1001314a  and     eax, 0FFF3FF0h
0x1001314f  cmp     eax, 106C0h
0x10013154  jz      short loc_10013179
0x10013156  cmp     eax, 20660h
0x1001315b  jz      short loc_10013179
0x1001315d  cmp     eax, 20670h
0x10013162  jz      short loc_10013179
0x10013164  cmp     eax, 30650h
0x10013169  jz      short loc_10013179
0x1001316b  cmp     eax, 30660h
0x10013170  jz      short loc_10013179
0x10013172  cmp     eax, 30670h
0x10013177  jnz     short loc_10013180
0x10013179  or      ___favor, 1
0x10013180  mov     edx, [ebp+var_20]
0x10013183  xor     ebx, ebx
0x10013185  xor     edi, edi
0x10013187  mov     [ebp+var_C], edx
0x1001318a  cmp     [ebp+var_4], 7
0x1001318e  mov     [ebp+var_14], ebx
0x10013191  mov     [ebp+var_18], ebx
0x10013194  jl      loc_10013221
0x1001319a  push    7
0x1001319c  pop     eax
0x1001319d  xor     ecx, ecx
0x1001319f  push    ebx
0x100131a0  cpuid
0x100131a2  mov     esi, ebx
0x100131a4  pop     ebx
0x100131a5  nop
0x100131a6  lea     ebx, [ebp+var_28]
0x100131a9  mov     [ebx], eax
0x100131ab  mov     [ebx+4], esi
0x100131ae  mov     [ebx+8], ecx
0x100131b1  mov     [ebx+0Ch], edx
0x100131b4  mov     ebx, [ebp+var_24]
0x100131b7  mov     eax, [ebp+var_1C]
0x100131ba  mov     [ebp+var_8], ebx
0x100131bd  mov     [ebp+var_14], eax
0x100131c0  test    ebx, 200h
0x100131c6  jz      short loc_100131CF
0x100131c8  or      ___favor, 2
0x100131cf  cmp     [ebp+var_28], 1
0x100131d3  jl      short loc_100131F9
0x100131d5  push    7
0x100131d7  pop     eax
0x100131d8  xor     ecx, ecx
0x100131da  inc     ecx
0x100131db  push    ebx
0x100131dc  cpuid
0x100131de  mov     esi, ebx
0x100131e0  pop     ebx
0x100131e1  nop
0x100131e2  lea     ebx, [ebp+var_28]
0x100131e5  mov     [ebx], eax
0x100131e7  mov     [ebx+4], esi
0x100131ea  mov     [ebx+8], ecx
0x100131ed  mov     [ebx+0Ch], edx
0x100131f0  mov     eax, [ebp+var_1C]
0x100131f3  mov     ebx, [ebp+var_8]
0x100131f6  mov     [ebp+var_18], eax
0x100131f9  push    24h ; '$'
0x100131fb  pop     eax
0x100131fc  cmp     [ebp+var_4], eax
0x100131ff  jl      short loc_1001321E
0x10013201  xor     ecx, ecx
0x10013203  lea     edi, [ebp+var_28]
0x10013206  push    ebx
0x10013207  cpuid
0x10013209  mov     esi, ebx
0x1001320b  pop     ebx
0x1001320c  nop
0x1001320d  mov     ebx, [ebp+var_8]
0x10013210  mov     [edi], eax
0x10013212  mov     [edi+4], esi
0x10013215  mov     [edi+8], ecx
0x10013218  mov     [edi+0Ch], edx
0x1001321b  mov     edi, [ebp+var_24]
0x1001321e  mov     edx, [ebp+var_C]
0x10013221  mov     eax, ___isa_enabled
0x10013226  mov     ecx, ___isa_inverted
0x1001322c  or      eax, 2
0x1001322f  mov     esi, dword_100140CC
0x10013235  and     ecx, 0FFFFFFFEh
0x10013238  mov     ___isa_available, 1
0x10013242  mov     ___isa_enabled, eax
0x10013247  mov     ___isa_inverted, ecx
0x1001324d  mov     dword_100140CC, esi
0x10013253  test    edx, 100000h
0x10013259  jz      loc_100133DA
0x1001325f  or      eax, 4
0x10013262  mov     ___isa_available, 2
0x1001326c  mov     ___isa_enabled, eax
0x10013271  and     ecx, 0FFFFFFEFh
0x10013274  mov     eax, 18000000h
0x10013279  mov     ___isa_inverted, ecx
0x1001327f  and     edx, eax
0x10013281  mov     dword_100140CC, esi
0x10013287  cmp     edx, eax
0x10013289  jnz     loc_100133DA
0x1001328f  xor     ecx, ecx
0x10013291  xgetbv
0x10013294  mov     [ebp+var_10], eax
0x10013297  xor     esi, esi
0x10013299  mov     [ebp+var_C], edx
0x1001329c  mov     eax, [ebp+var_10]
0x1001329f  mov     ecx, [ebp+var_C]
0x100132a2  and     eax, 6
0x100132a5  and     ecx, esi
0x100132a7  cmp     eax, 6
0x100132aa  jnz     loc_100133DA
0x100132b0  cmp     ecx, esi
0x100132b2  jnz     loc_100133DA
0x100132b8  mov     eax, ___isa_enabled
0x100132bd  or      eax, 8
0x100132c0  mov     ___isa_available, 3
0x100132ca  mov     ___isa_enabled, eax
0x100132cf  test    bl, 20h
0x100132d2  jz      short loc_1001334D
0x100132d4  mov     ecx, dword_100140CC
0x100132da  or      eax, 20h
0x100132dd  mov     ___isa_enabled, eax
0x100132e2  mov     edx, 0D0030000h
0x100132e7  mov     eax, ___isa_inverted
0x100132ec  and     ebx, edx
0x100132ee  and     eax, 0FFFFFFFDh
0x100132f1  mov     ___isa_available, 5
0x100132fb  mov     ___isa_inverted, eax
0x10013300  mov     dword_100140CC, ecx
0x10013306  cmp     ebx, edx
0x10013308  jnz     short loc_10013358
0x1001330a  mov     eax, [ebp+var_10]
0x1001330d  mov     edx, 0E0h
0x10013312  mov     ecx, [ebp+var_C]
0x10013315  and     eax, edx
0x10013317  and     ecx, esi
0x10013319  cmp     eax, edx
0x1001331b  jnz     short loc_1001334D
0x1001331d  cmp     ecx, esi
0x1001331f  jnz     short loc_1001334D
0x10013321  mov     eax, ___isa_inverted
0x10013326  or      ___isa_enabled, 40h
0x1001332d  and     eax, 0FFFFFFDBh
0x10013330  mov     ecx, dword_100140CC
0x10013336  mov     ___isa_available, 6
0x10013340  mov     ___isa_inverted, eax
0x10013345  mov     dword_100140CC, ecx
0x1001334b  jmp     short loc_10013358
0x1001334d  mov     ecx, dword_100140CC
0x10013353  mov     eax, ___isa_inverted
0x10013358  test    [ebp+var_14], 800000h
0x1001335f  jz      short loc_10013371
0x10013361  and     eax, 0FEFFFFFFh
0x10013366  mov     dword_100140CC, ecx
0x1001336c  mov     ___isa_inverted, eax
0x10013371  test    [ebp+var_18], 80000h
0x10013378  jz      short loc_100133DA
0x1001337a  mov     eax, [ebp+var_10]
0x1001337d  mov     edx, 0E0h
0x10013382  mov     ecx, [ebp+var_C]
0x10013385  and     eax, edx
0x10013387  and     ecx, esi
0x10013389  cmp     eax, edx
0x1001338b  jnz     short loc_100133DA
0x1001338d  cmp     ecx, esi
0x1001338f  jnz     short loc_100133DA
0x10013391  mov     eax, edi
0x10013393  xor     ecx, ecx
0x10013395  shr     edi, 10h
0x10013398  and     eax, 400FFh
0x1001339d  and     edi, 6
0x100133a0  mov     ___avx10_version, eax
0x100133a5  or      edi, 1000029h
0x100133ab  not     ecx
0x100133ad  and     ecx, dword_100140CC
0x100133b3  not     edi
0x100133b5  and     edi, ___isa_inverted
0x100133bb  mov     ___isa_inverted, edi
0x100133c1  mov     dword_100140CC, ecx
0x100133c7  cmp     al, 1
0x100133c9  jbe     short loc_100133DA
0x100133cb  and     edi, 0FFFFFFBFh
0x100133ce  mov     dword_100140CC, ecx
0x100133d4  mov     ___isa_inverted, edi
0x100133da  pop     edi
0x100133db  pop     esi
0x100133dc  pop     ebx
0x100133dd  xor     eax, eax
0x100133df  leave
0x100133e0  retn
```
