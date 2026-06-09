# CreateLinearAlut

- ea: `0x180020758`
- end: `0x1800207c9`
- name: `CreateLinearAlut`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`
- `0x18000464c`
- `0x18001bb30`
- `0x180020984`

## callees

- `0x180020758`

## pseudocode

```c
__int64 __fastcall CreateLinearAlut(__int64 a1)
{
  int i; // ecx
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r10
  int v6; // edx

  for ( i = 1; i < 100; ++i )
  {
    if ( 1 << i == 1024 )
      break;
  }
  result = (unsigned int)(i - 1);
  if ( (unsigned int)result <= 0x62 )
  {
    if ( i - 8 <= 0 )
      v4 = 0;
    else
      v4 = 1 << (i - 9);
    v5 = 0;
    do
    {
      v6 = (v4 + (int)v5) >> (i - 8);
      if ( v6 > 255 )
        LOBYTE(v6) = -1;
      *(_BYTE *)(v5 + a1) = v6;
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (int)v5 < 1024 );
  }
  return result;
}

```

## disassembly

```asm
0x180020758  mov     [rsp+arg_0], rsi
0x18002075d  mov     r11, rcx
0x180020760  mov     ecx, 1
0x180020765  mov     eax, 1
0x18002076a  shl     eax, cl
0x18002076c  cmp     eax, 400h
0x180020771  jz      short loc_18002077A
0x180020773  inc     ecx
0x180020775  cmp     ecx, 64h ; 'd'
0x180020778  jl      short loc_180020765
0x18002077a  lea     eax, [rcx-1]
0x18002077d  cmp     eax, 62h ; 'b'
0x180020780  ja      short loc_1800207C3
0x180020782  lea     r9d, [rcx-8]
0x180020786  test    r9d, r9d
0x180020789  jle     short loc_18002079A
0x18002078b  lea     ecx, [r9-1]
0x18002078f  mov     r8d, 1
0x180020795  shl     r8d, cl
0x180020798  jmp     short loc_18002079D
0x18002079a  xor     r8d, r8d
0x18002079d  xor     r10d, r10d
0x1800207a0  mov     esi, 0FFh
0x1800207a5  lea     edx, [r8+r10]
0x1800207a9  mov     ecx, r9d
0x1800207ac  sar     edx, cl
0x1800207ae  cmp     edx, esi
0x1800207b0  cmovg   edx, esi
0x1800207b3  mov     [r10+r11], dl
0x1800207b7  inc     r10d
0x1800207ba  cmp     r10d, 400h
0x1800207c1  jl      short loc_1800207A5
0x1800207c3  mov     rsi, [rsp+arg_0]
0x1800207c8  retn
```
