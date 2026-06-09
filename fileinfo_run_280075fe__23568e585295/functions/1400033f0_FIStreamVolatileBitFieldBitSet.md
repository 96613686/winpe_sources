# FIStreamVolatileBitFieldBitSet

- ea: `0x1400033f0`
- end: `0x140003493`
- name: `FIStreamVolatileBitFieldBitSet`
- size: `163`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d64`
- `0x140003140`
- `0x14000df58`
- `0x14000e148`
- `0x14001334c`
- `0x140016910`
- `0x140016bc0`
- `0x140017510`

## callees

- `0x1400033f0`

## pseudocode

```c
__int64 __fastcall FIStreamVolatileBitFieldBitSet(__int64 a1, int a2, unsigned __int8 a3)
{
  __int64 result; // rax
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // r8d
  int v12; // ecx

  result = *(unsigned int *)(a1 + 56);
  if ( !a2 )
  {
    v12 = (a3 ^ (unsigned __int8)result) & 1;
    goto LABEL_18;
  }
  v5 = a2 - 1;
  if ( !v5 )
  {
    v12 = ((unsigned __int8)result ^ (unsigned __int8)(2 * a3)) & 2;
    goto LABEL_18;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v12 = ((unsigned __int8)result ^ (unsigned __int8)(4 * a3)) & 4;
    goto LABEL_18;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v12 = ((unsigned __int8)result ^ (unsigned __int8)(8 * a3)) & 8;
LABEL_18:
    result = v12 ^ (unsigned int)result;
    goto LABEL_19;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v11 = ((unsigned __int8)result ^ (unsigned __int8)(16 * a3)) & 0x10;
    goto LABEL_13;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v11 = ((unsigned __int8)result ^ (unsigned __int8)(32 * a3)) & 0x20;
    goto LABEL_13;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v11 = ((unsigned __int8)result ^ (unsigned __int8)(a3 << 6)) & 0x40;
    goto LABEL_13;
  }
  if ( v10 == 1 )
  {
    v11 = ((unsigned __int8)result ^ (unsigned __int8)(a3 << 7)) & 0x80;
LABEL_13:
    result = v11 ^ (unsigned int)result;
  }
LABEL_19:
  *(_DWORD *)(a1 + 56) = result;
  return result;
}

```

## disassembly

```asm
0x1400033f0  mov     eax, [rcx+38h]
0x1400033f3  mov     r10, rcx
0x1400033f6  test    edx, edx
0x1400033f8  jz      loc_140003484
0x1400033fe  sub     edx, 1
0x140003401  jz      short loc_140003479
0x140003403  sub     edx, 1
0x140003406  jz      short loc_14000346A
0x140003408  sub     edx, 1
0x14000340b  jz      short loc_14000345B
0x14000340d  sub     edx, 1
0x140003410  jz      short loc_14000344B
0x140003412  sub     edx, 1
0x140003415  jz      short loc_14000343E
0x140003417  sub     edx, 1
0x14000341a  jz      short loc_140003431
0x14000341c  cmp     edx, 1
0x14000341f  jnz     short loc_14000348E
0x140003421  shl     r8d, 7
0x140003425  xor     r8d, eax
0x140003428  and     r8d, 80h
0x14000342f  jmp     short loc_140003456
0x140003431  shl     r8d, 6
0x140003435  xor     r8d, eax
0x140003438  and     r8d, 40h
0x14000343c  jmp     short loc_140003456
0x14000343e  shl     r8d, 5
0x140003442  xor     r8d, eax
0x140003445  and     r8d, 20h
0x140003449  jmp     short loc_140003456
0x14000344b  shl     r8d, 4
0x14000344f  xor     r8d, eax
0x140003452  and     r8d, 10h
0x140003456  xor     eax, r8d
0x140003459  jmp     short loc_14000348E
0x14000345b  lea     ecx, ds:0[r8*8]
0x140003463  xor     ecx, eax
0x140003465  and     ecx, 8
0x140003468  jmp     short loc_14000348C
0x14000346a  lea     ecx, ds:0[r8*4]
0x140003472  xor     ecx, eax
0x140003474  and     ecx, 4
0x140003477  jmp     short loc_14000348C
0x140003479  lea     ecx, [r8+r8]
0x14000347d  xor     ecx, eax
0x14000347f  and     ecx, 2
0x140003482  jmp     short loc_14000348C
0x140003484  mov     ecx, eax
0x140003486  xor     ecx, r8d
0x140003489  and     ecx, 1
0x14000348c  xor     eax, ecx
0x14000348e  mov     [r10+38h], eax
0x140003492  retn
```
