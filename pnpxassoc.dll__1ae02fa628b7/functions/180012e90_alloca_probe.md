# _alloca_probe

- ea: `0x180012e90`
- end: `0x180012edd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029d0`
- `0x180002c38`
- `0x180002ed4`
- `0x180005b14`
- `0x1800078f8`
- `0x180007c4c`
- `0x180008714`
- `0x180011c80`
- `0x180012ac0`

## callees

- `0x180012e90`

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
0x180012e90  sub     rsp, 10h
0x180012e94  mov     [rsp+10h+var_10], r10
0x180012e98  mov     [rsp+10h+var_8], r11
0x180012e9d  xor     r11, r11
0x180012ea0  lea     r10, [rsp+10h+arg_0]
0x180012ea5  sub     r10, rax
0x180012ea8  cmovb   r10, r11
0x180012eac  mov     r11, gs:10h
0x180012eb5  cmp     r10, r11
0x180012eb8  jnb     short loc_180012ECF
0x180012eba  and     r10w, 0F000h
0x180012ec0  lea     r11, [r11-1000h]
0x180012ec7  test    [r11], r11b
0x180012eca  cmp     r10, r11
0x180012ecd  jb      short loc_180012EC0
0x180012ecf  mov     r10, [rsp+10h+var_10]
0x180012ed3  mov     r11, [rsp+10h+var_8]
0x180012ed8  add     rsp, 10h
0x180012edc  retn
```
