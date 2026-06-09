# CfpGetPlaceholderState

- ea: `0x18001b850`
- end: `0x18001b8a9`
- name: `CfpGetPlaceholderState`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b960`
- `0x18001b790`
- `0x18001b7a0`
- `0x18001b840`

## callees

- `0x18001b850`

## pseudocode

```c
__int64 __fastcall CfpGetPlaceholderState(int a1, int a2)
{
  unsigned int v2; // r8d

  v2 = 0;
  if ( (a1 & 0x400) != 0 && (a2 & 0xFFFF0FFF) == 0x9000001A )
  {
    v2 = (a1 & 0x440000) != 0 ? 17 : 1;
    if ( (a2 & 0x1000) != 0 )
      v2 |= 2u;
    if ( (a2 & 0x4000) != 0 )
      v2 |= 8u;
    if ( (a2 & 0x2000) == 0 )
      v2 |= 0x20u;
    if ( (a2 & 0x8000) != 0 )
      v2 |= 4u;
  }
  return v2;
}

```

## disassembly

```asm
0x18001b850  xor     r8d, r8d
0x18001b853  bt      ecx, 0Ah
0x18001b857  jnb     short loc_18001B8A5
0x18001b859  mov     eax, edx
0x18001b85b  and     eax, 0FFFF0FFFh
0x18001b860  cmp     eax, 9000001Ah
0x18001b865  jnz     short loc_18001B8A5
0x18001b867  and     ecx, 440000h
0x18001b86d  neg     ecx
0x18001b86f  sbb     r8d, r8d
0x18001b872  and     r8d, 10h
0x18001b876  inc     r8d
0x18001b879  bt      edx, 0Ch
0x18001b87d  jnb     short loc_18001B883
0x18001b87f  or      r8d, 2
0x18001b883  bt      edx, 0Eh
0x18001b887  jnb     short loc_18001B88D
0x18001b889  or      r8d, 8
0x18001b88d  mov     eax, r8d
0x18001b890  or      eax, 20h
0x18001b893  bt      edx, 0Dh
0x18001b897  cmovnb  r8d, eax
0x18001b89b  bt      edx, 0Fh
0x18001b89f  jnb     short loc_18001B8A5
0x18001b8a1  or      r8d, 4
0x18001b8a5  mov     eax, r8d
0x18001b8a8  retn
```
