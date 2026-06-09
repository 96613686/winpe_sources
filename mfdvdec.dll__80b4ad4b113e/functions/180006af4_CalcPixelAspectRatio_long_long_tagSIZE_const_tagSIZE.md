# CalcPixelAspectRatio(long,long,tagSIZE const &,tagSIZE *)

- ea: `0x180006af4`
- end: `0x180006b67`
- name: `?CalcPixelAspectRatio@@YAXJJAEBUtagSIZE@@PEAU1@@Z`
- size: `115`
- prototype: `void __fastcall(int, int, const struct tagSIZE *, struct tagSIZE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005340`
- `0x180006b70`

## callees

- `0x180006af4`

## pseudocode

```c
void __fastcall CalcPixelAspectRatio(int a1, int a2, const struct tagSIZE *a3, struct tagSIZE *a4)
{
  unsigned int v4; // r11d
  unsigned int v6; // r10d
  unsigned int v7; // r9d
  unsigned int v8; // r8d
  unsigned int v9; // ecx

  v4 = a3->cx * a2;
  v6 = a3->cy * a1;
  if ( v4 && v6 )
  {
    v7 = a3->cy * a1;
    v8 = a3->cx * a2;
    if ( v4 < v6 )
    {
      v8 = v6;
      v7 = v4;
    }
    do
    {
      v9 = v7;
      v7 = v8 % v7;
      v8 = v9;
    }
    while ( v7 );
  }
  else
  {
    v8 = 1;
  }
  a4->cx = v4 / v8;
  a4->cy = v6 / v8;
}

```

## disassembly

```asm
0x180006af4  mov     [rsp+arg_0], rbx
0x180006af9  mov     r11d, edx
0x180006afc  mov     r10d, ecx
0x180006aff  imul    r11d, [r8]
0x180006b03  mov     rbx, r9
0x180006b06  imul    r10d, [r8+4]
0x180006b0b  test    r11d, r11d
0x180006b0e  jz      short loc_180006B46
0x180006b10  test    r10d, r10d
0x180006b13  jz      short loc_180006B46
0x180006b15  mov     r9d, r10d
0x180006b18  mov     r8d, r11d
0x180006b1b  cmp     r11d, r10d
0x180006b1e  jnb     short loc_180006B26
0x180006b20  mov     r8d, r10d
0x180006b23  mov     r9d, r11d
0x180006b26  xor     edx, edx
0x180006b28  mov     eax, r8d
0x180006b2b  div     r9d
0x180006b2e  mov     ecx, r9d
0x180006b31  mov     r9d, edx
0x180006b34  mov     r8d, ecx
0x180006b37  test    edx, edx
0x180006b39  jnz     short loc_180006B26
0x180006b3b  test    ecx, ecx
0x180006b3d  lea     eax, [rdx+1]
0x180006b40  cmovz   r8d, eax
0x180006b44  jmp     short loc_180006B4C
0x180006b46  mov     r8d, 1
0x180006b4c  xor     edx, edx
0x180006b4e  mov     eax, r11d
0x180006b51  div     r8d
0x180006b54  xor     edx, edx
0x180006b56  mov     [rbx], eax
0x180006b58  mov     eax, r10d
0x180006b5b  div     r8d
0x180006b5e  mov     [rbx+4], eax
0x180006b61  mov     rbx, [rsp+arg_0]
0x180006b66  retn
```
