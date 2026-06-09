# sub_1800CBECC

- ea: `0x1800cbecc`
- end: `0x1800cbee8`
- name: `sub_1800CBECC`
- size: `28`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e40`
- `0x1800166d0`
- `0x18001da00`
- `0x18001f0b0`
- `0x18001f210`
- `0x18001f8e0`
- `0x18001f970`
- `0x18003c960`
- `0x18007dcd0`

## callees

- `0x1800cbe10`
- `0x1800cbecc`

## pseudocode

```c
void *__fastcall sub_1800CBECC(size_t a1)
{
  return sub_1800CBE10(a1);
}

```

## disassembly

```asm
0x1800cbecc  sub     rsp, 38h
0x1800cbed0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800cbed9  call    sub_1800CBE10
0x1800cbede  jmp     short loc_1800CBEE2
0x1800cbee0  xor     eax, eax
0x1800cbee2  add     rsp, 38h
0x1800cbee6  retn
```
