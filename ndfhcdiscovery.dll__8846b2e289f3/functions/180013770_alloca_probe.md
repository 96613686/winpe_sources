# _alloca_probe

- ea: `0x180013770`
- end: `0x1800137bd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ce0`
- `0x18000615c`
- `0x180008d5c`
- `0x180009108`
- `0x180009ba0`
- `0x18000b484`

## callees

- `0x180013770`

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
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x180013770  sub     rsp, 10h
0x180013774  mov     [rsp+10h+var_10], r10
0x180013778  mov     [rsp+10h+var_8], r11
0x18001377d  xor     r11, r11
0x180013780  lea     r10, [rsp+10h+arg_0]
0x180013785  sub     r10, rax
0x180013788  cmovb   r10, r11
0x18001378c  mov     r11, gs:10h
0x180013795  cmp     r10, r11
0x180013798  jnb     short loc_1800137AF
0x18001379a  and     r10w, 0F000h
0x1800137a0  lea     r11, [r11-1000h]
0x1800137a7  test    [r11], r11b
0x1800137aa  cmp     r10, r11
0x1800137ad  jb      short loc_1800137A0
0x1800137af  mov     r10, [rsp+10h+var_10]
0x1800137b3  mov     r11, [rsp+10h+var_8]
0x1800137b8  add     rsp, 10h
0x1800137bc  retn
```
