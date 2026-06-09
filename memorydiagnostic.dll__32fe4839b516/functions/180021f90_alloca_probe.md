# _alloca_probe

- ea: `0x180021f90`
- end: `0x180021fde`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000487c`
- `0x1800049c4`
- `0x180004f4c`
- `0x180005058`
- `0x1800052ec`
- `0x1800055b0`
- `0x180005870`
- `0x1800103c4`
- `0x180019e40`
- `0x180019f6c`

## callees

- `0x180021f90`

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
0x180021f90  sub     rsp, 10h
0x180021f94  mov     [rsp+10h+var_10], r10
0x180021f98  mov     [rsp+10h+var_8], r11
0x180021f9d  xor     r11, r11
0x180021fa0  lea     r10, [rsp+10h+arg_0]
0x180021fa5  sub     r10, rax
0x180021fa8  cmovb   r10, r11
0x180021fac  mov     r11, gs:10h
0x180021fb5  cmp     r10, r11
0x180021fb8  jnb     short cs20
0x180021fba  and     r10w, 0F000h
0x180021fc0  lea     r11, [r11-1000h]
0x180021fc7  mov     byte ptr [r11], 0
0x180021fcb  cmp     r10, r11
0x180021fce  jnz     short cs10
0x180021fd0  mov     r10, [rsp+10h+var_10]
0x180021fd4  mov     r11, [rsp+10h+var_8]
0x180021fd9  add     rsp, 10h
0x180021fdd  retn
```
