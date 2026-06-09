# _alloca_probe

- ea: `0x18000cda0`
- end: `0x18000cded`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e94`
- `0x1800040fc`
- `0x180004398`
- `0x180006700`
- `0x180008eac`
- `0x18000a6c0`

## callees

- `0x18000cda0`

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
0x18000cda0  sub     rsp, 10h
0x18000cda4  mov     [rsp+10h+var_10], r10
0x18000cda8  mov     [rsp+10h+var_8], r11
0x18000cdad  xor     r11, r11
0x18000cdb0  lea     r10, [rsp+10h+arg_0]
0x18000cdb5  sub     r10, rax
0x18000cdb8  cmovb   r10, r11
0x18000cdbc  mov     r11, gs:10h
0x18000cdc5  cmp     r10, r11
0x18000cdc8  jnb     short loc_18000CDDF
0x18000cdca  and     r10w, 0F000h
0x18000cdd0  lea     r11, [r11-1000h]
0x18000cdd7  test    [r11], r11b
0x18000cdda  cmp     r10, r11
0x18000cddd  jb      short loc_18000CDD0
0x18000cddf  mov     r10, [rsp+10h+var_10]
0x18000cde3  mov     r11, [rsp+10h+var_8]
0x18000cde8  add     rsp, 10h
0x18000cdec  retn
```
