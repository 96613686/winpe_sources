# _alloca_probe

- ea: `0x180025e90`
- end: `0x180025ede`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c300`
- `0x18001e92c`
- `0x18001e9dc`
- `0x18001ead0`
- `0x180021754`
- `0x180023010`
- `0x180023218`

## callees

- `0x180025e90`

## pseudocode

```c
unsigned __int64 __fastcall alloca_probe()
{
  unsigned __int64 result; // rax
  char *v1; // r10
  char *StackLimit; // r11
  char v3; // [rsp+18h] [rbp+8h] BYREF

  v1 = &v3 - result;
  if ( (unsigned __int64)&v3 < result )
    v1 = 0;
  StackLimit = (char *)NtCurrentTeb()->NtTib.StackLimit;
  if ( v1 < StackLimit )
  {
    LOWORD(v1) = (unsigned __int16)v1 & 0xF000;
    do
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x180025e90  sub     rsp, 10h
0x180025e94  mov     [rsp+10h+var_10], r10
0x180025e98  mov     [rsp+10h+var_8], r11
0x180025e9d  xor     r11, r11
0x180025ea0  lea     r10, [rsp+10h+arg_0]
0x180025ea5  sub     r10, rax
0x180025ea8  cmovb   r10, r11
0x180025eac  mov     r11, gs:10h
0x180025eb5  cmp     r10, r11
0x180025eb8  jnb     short cs20
0x180025eba  and     r10w, 0F000h
0x180025ec0  lea     r11, [r11-1000h]
0x180025ec7  mov     byte ptr [r11], 0
0x180025ecb  cmp     r10, r11
0x180025ece  jnz     short cs10
0x180025ed0  mov     r10, [rsp+10h+var_10]
0x180025ed4  mov     r11, [rsp+10h+var_8]
0x180025ed9  add     rsp, 10h
0x180025edd  retn
```
