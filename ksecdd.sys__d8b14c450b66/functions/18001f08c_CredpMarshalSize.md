# CredpMarshalSize

- ea: `0x18001f08c`
- end: `0x18001f0bb`
- name: `CredpMarshalSize`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000800c`
- `0x18001ff10`
- `0x1800267b0`

## callees

- `0x18001f08c`

## pseudocode

```c
__int64 __fastcall CredpMarshalSize(unsigned int a1)
{
  unsigned int v1; // edx
  unsigned int v2; // ecx
  int v3; // r8d

  v1 = a1 / 3;
  v2 = a1 % 3;
  v3 = 4 * v1;
  if ( v2 == 1 )
  {
    v3 += 2;
  }
  else if ( v2 == 2 )
  {
    v3 += 3;
  }
  return (unsigned int)(2 * v3);
}

```

## disassembly

```asm
0x18001f08c  mov     eax, 0AAAAAAABh
0x18001f091  mul     ecx
0x18001f093  shr     edx, 1
0x18001f095  lea     eax, [rdx+rdx*2]
0x18001f098  sub     ecx, eax
0x18001f09a  lea     r8d, ds:0[rdx*4]
0x18001f0a2  cmp     ecx, 1
0x18001f0a5  jnz     short loc_18001F0AD
0x18001f0a7  add     r8d, 2
0x18001f0ab  jmp     short loc_18001F0B6
0x18001f0ad  cmp     ecx, 2
0x18001f0b0  jnz     short loc_18001F0B6
0x18001f0b2  add     r8d, 3
0x18001f0b6  lea     eax, [r8+r8]
0x18001f0ba  retn
```
