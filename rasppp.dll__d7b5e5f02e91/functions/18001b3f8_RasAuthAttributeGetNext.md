# RasAuthAttributeGetNext

- ea: `0x18001b3f8`
- end: `0x18001b41c`
- name: `RasAuthAttributeGetNext`
- size: `36`
- prototype: `_DWORD *__fastcall(_DWORD **, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001063c`
- `0x18001973c`
- `0x18001ae9c`
- `0x18001b0d4`
- `0x18001b198`
- `0x18001b424`
- `0x18001c310`

## callees

- `0x18001b3f8`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeGetNext(_DWORD **a1, int a2)
{
  _DWORD *result; // rax

  result = *a1;
  if ( *a1 )
  {
    while ( 1 )
    {
      result += 4;
      if ( !*result )
        break;
      if ( *result == a2 )
      {
        *a1 = result;
        return result;
      }
    }
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001b3f8  mov     rax, [rcx]
0x18001b3fb  test    rax, rax
0x18001b3fe  jz      short loc_18001B419
0x18001b400  add     rax, 10h
0x18001b404  cmp     dword ptr [rax], 0
0x18001b407  jz      short loc_18001B412
0x18001b409  cmp     [rax], edx
0x18001b40b  jnz     short loc_18001B400
0x18001b40d  mov     [rcx], rax
0x18001b410  retn
0x18001b412  mov     qword ptr [rcx], 0
0x18001b419  xor     eax, eax
0x18001b41b  retn
```
