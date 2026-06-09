# _alloca_probe

- ea: `0x180008fb0`
- end: `0x180008ffe`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030cc`
- `0x18000317c`
- `0x180003410`
- `0x180006190`
- `0x180006744`
- `0x180006810`

## callees

- `0x180008fb0`

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
0x180008fb0  sub     rsp, 10h
0x180008fb4  mov     [rsp+10h+var_10], r10
0x180008fb8  mov     [rsp+10h+var_8], r11
0x180008fbd  xor     r11, r11
0x180008fc0  lea     r10, [rsp+10h+arg_0]
0x180008fc5  sub     r10, rax
0x180008fc8  cmovb   r10, r11
0x180008fcc  mov     r11, gs:10h
0x180008fd5  cmp     r10, r11
0x180008fd8  jnb     short cs20
0x180008fda  and     r10w, 0F000h
0x180008fe0  lea     r11, [r11-1000h]
0x180008fe7  mov     byte ptr [r11], 0
0x180008feb  cmp     r10, r11
0x180008fee  jnz     short cs10
0x180008ff0  mov     r10, [rsp+10h+var_10]
0x180008ff4  mov     r11, [rsp+10h+var_8]
0x180008ff9  add     rsp, 10h
0x180008ffd  retn
```
