# _alloca_probe

- ea: `0x180003360`
- end: `0x1800033ad`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002504`

## callees

- `0x180003360`

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
0x180003360  sub     rsp, 10h
0x180003364  mov     [rsp+10h+var_10], r10
0x180003368  mov     [rsp+10h+var_8], r11
0x18000336d  xor     r11, r11
0x180003370  lea     r10, [rsp+10h+arg_0]
0x180003375  sub     r10, rax
0x180003378  cmovb   r10, r11
0x18000337c  mov     r11, gs:10h
0x180003385  cmp     r10, r11
0x180003388  jnb     short loc_18000339F
0x18000338a  and     r10w, 0F000h
0x180003390  lea     r11, [r11-1000h]
0x180003397  test    [r11], r11b
0x18000339a  cmp     r10, r11
0x18000339d  jb      short loc_180003390
0x18000339f  mov     r10, [rsp+10h+var_10]
0x1800033a3  mov     r11, [rsp+10h+var_8]
0x1800033a8  add     rsp, 10h
0x1800033ac  retn
```
