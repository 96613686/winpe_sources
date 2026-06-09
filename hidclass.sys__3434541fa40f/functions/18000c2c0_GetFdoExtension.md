# GetFdoExtension

- ea: `0x18000c2c0`
- end: `0x18000c2d5`
- name: `GetFdoExtension`
- size: `21`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000621c`
- `0x18000a264`
- `0x18000b140`
- `0x18001e99c`

## callees

- `0x18000c2c0`

## pseudocode

```c
__int64 __fastcall GetFdoExtension(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 24) )
    return *(_QWORD *)(a1 + 96) + 32LL;
  else
    return a1 + 32;
}

```

## disassembly

```asm
0x18000c2c0  cmp     byte ptr [rcx+18h], 0
0x18000c2c4  jnz     short loc_18000C2CC
0x18000c2c6  lea     rax, [rcx+20h]
0x18000c2ca  retn
0x18000c2cc  mov     rax, [rcx+60h]
0x18000c2d0  add     rax, 20h ; ' '
0x18000c2d4  retn
```
