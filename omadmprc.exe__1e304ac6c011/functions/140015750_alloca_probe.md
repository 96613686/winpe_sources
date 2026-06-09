# _alloca_probe

- ea: `0x140015750`
- end: `0x14001579d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003090`
- `0x14000330c`
- `0x1400035b4`
- `0x140007a24`
- `0x14000a760`
- `0x14000a87c`
- `0x140014d88`

## callees

- `0x140015750`

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
0x140015750  sub     rsp, 10h
0x140015754  mov     [rsp+10h+var_10], r10
0x140015758  mov     [rsp+10h+var_8], r11
0x14001575d  xor     r11, r11
0x140015760  lea     r10, [rsp+10h+arg_0]
0x140015765  sub     r10, rax
0x140015768  cmovb   r10, r11
0x14001576c  mov     r11, gs:10h
0x140015775  cmp     r10, r11
0x140015778  jnb     short loc_14001578F
0x14001577a  and     r10w, 0F000h
0x140015780  lea     r11, [r11-1000h]
0x140015787  test    [r11], r11b
0x14001578a  cmp     r10, r11
0x14001578d  jb      short loc_140015780
0x14001578f  mov     r10, [rsp+10h+var_10]
0x140015793  mov     r11, [rsp+10h+var_8]
0x140015798  add     rsp, 10h
0x14001579c  retn
```
