# _alloca_probe

- ea: `0x180012350`
- end: `0x18001239e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000366c`
- `0x180004ea8`
- `0x18000521c`
- `0x180005b98`
- `0x18000b9e4`
- `0x18000bc54`
- `0x18000bef0`
- `0x180010490`

## callees

- `0x180012350`

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
0x180012350  sub     rsp, 10h
0x180012354  mov     [rsp+10h+var_10], r10
0x180012358  mov     [rsp+10h+var_8], r11
0x18001235d  xor     r11, r11
0x180012360  lea     r10, [rsp+10h+arg_0]
0x180012365  sub     r10, rax
0x180012368  cmovb   r10, r11
0x18001236c  mov     r11, gs:10h
0x180012375  cmp     r10, r11
0x180012378  jnb     short cs20
0x18001237a  and     r10w, 0F000h
0x180012380  lea     r11, [r11-1000h]
0x180012387  mov     byte ptr [r11], 0
0x18001238b  cmp     r10, r11
0x18001238e  jnz     short cs10
0x180012390  mov     r10, [rsp+10h+var_10]
0x180012394  mov     r11, [rsp+10h+var_8]
0x180012399  add     rsp, 10h
0x18001239d  retn
```
