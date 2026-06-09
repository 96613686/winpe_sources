# RasAuthAttributeGetFirst

- ea: `0x18001b3d0`
- end: `0x18001b3ef`
- name: `RasAuthAttributeGetFirst`
- size: `31`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
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

- `0x18001ae70`
- `0x18001b3d0`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeGetFirst(int a1, __int64 a2)
{
  _DWORD *result; // rax
  _QWORD *v3; // r9

  result = RasAuthAttributeGet(a1, a2);
  if ( result )
    *v3 = result;
  else
    *v3 = 0;
  return result;
}

```

## disassembly

```asm
0x18001b3d0  sub     rsp, 28h
0x18001b3d4  mov     r9, r8
0x18001b3d7  call    RasAuthAttributeGet
0x18001b3dc  test    rax, rax
0x18001b3df  jnz     short loc_18001B3E6
0x18001b3e1  mov     [r9], rax
0x18001b3e4  jmp     short loc_18001B3E9
0x18001b3e6  mov     [r9], rax
0x18001b3e9  add     rsp, 28h
0x18001b3ed  retn
```
