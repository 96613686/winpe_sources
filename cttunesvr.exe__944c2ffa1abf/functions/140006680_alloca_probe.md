# _alloca_probe

- ea: `0x140006680`
- end: `0x1400066cd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400025a4`
- `0x140003f98`
- `0x1400042ec`
- `0x140004e78`

## callees

- `0x140006680`

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
0x140006680  sub     rsp, 10h
0x140006684  mov     [rsp+10h+var_10], r10
0x140006688  mov     [rsp+10h+var_8], r11
0x14000668d  xor     r11, r11
0x140006690  lea     r10, [rsp+10h+arg_0]
0x140006695  sub     r10, rax
0x140006698  cmovb   r10, r11
0x14000669c  mov     r11, gs:10h
0x1400066a5  cmp     r10, r11
0x1400066a8  jnb     short loc_1400066BF
0x1400066aa  and     r10w, 0F000h
0x1400066b0  lea     r11, [r11-1000h]
0x1400066b7  test    [r11], r11b
0x1400066ba  cmp     r10, r11
0x1400066bd  jb      short loc_1400066B0
0x1400066bf  mov     r10, [rsp+10h+var_10]
0x1400066c3  mov     r11, [rsp+10h+var_8]
0x1400066c8  add     rsp, 10h
0x1400066cc  retn
```
