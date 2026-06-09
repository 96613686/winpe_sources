# _alloca_probe

- ea: `0x18001edb0`
- end: `0x18001edfd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180001414`
- `0x180004404`
- `0x180005bc0`
- `0x180006a48`
- `0x1800070d0`
- `0x180008e60`
- `0x18000bab8`
- `0x18000bf1c`
- `0x18000d388`
- `0x1800103d0`
- `0x180010480`
- `0x180010574`
- `0x180013530`
- `0x180015438`
- `0x180016f70`
- `0x180017b60`
- `0x18001a3b4`
- `0x18001bba4`

## callees

- `0x18001edb0`

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
0x18001edb0  sub     rsp, 10h
0x18001edb4  mov     [rsp+10h+var_10], r10
0x18001edb8  mov     [rsp+10h+var_8], r11
0x18001edbd  xor     r11, r11
0x18001edc0  lea     r10, [rsp+10h+arg_0]
0x18001edc5  sub     r10, rax
0x18001edc8  cmovb   r10, r11
0x18001edcc  mov     r11, gs:10h
0x18001edd5  cmp     r10, r11
0x18001edd8  jnb     short loc_18001EDEF
0x18001edda  and     r10w, 0F000h
0x18001ede0  lea     r11, [r11-1000h]
0x18001ede7  test    [r11], r11b
0x18001edea  cmp     r10, r11
0x18001eded  jb      short loc_18001EDE0
0x18001edef  mov     r10, [rsp+10h+var_10]
0x18001edf3  mov     r11, [rsp+10h+var_8]
0x18001edf8  add     rsp, 10h
0x18001edfc  retn
```
