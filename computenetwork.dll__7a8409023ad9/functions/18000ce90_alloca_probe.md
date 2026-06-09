# _alloca_probe

- ea: `0x18000ce90`
- end: `0x18000cede`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030e4`
- `0x1800034f0`
- `0x180003770`
- `0x180003a3c`
- `0x180003ce8`
- `0x1800079f0`
- `0x180009e58`
- `0x180009fa0`
- `0x18000a558`

## callees

- `0x18000ce90`

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
0x18000ce90  sub     rsp, 10h
0x18000ce94  mov     [rsp+10h+var_10], r10
0x18000ce98  mov     [rsp+10h+var_8], r11
0x18000ce9d  xor     r11, r11
0x18000cea0  lea     r10, [rsp+10h+arg_0]
0x18000cea5  sub     r10, rax
0x18000cea8  cmovb   r10, r11
0x18000ceac  mov     r11, gs:10h
0x18000ceb5  cmp     r10, r11
0x18000ceb8  jnb     short cs20
0x18000ceba  and     r10w, 0F000h
0x18000cec0  lea     r11, [r11-1000h]
0x18000cec7  mov     byte ptr [r11], 0
0x18000cecb  cmp     r10, r11
0x18000cece  jnz     short cs10
0x18000ced0  mov     r10, [rsp+10h+var_10]
0x18000ced4  mov     r11, [rsp+10h+var_8]
0x18000ced9  add     rsp, 10h
0x18000cedd  retn
```
