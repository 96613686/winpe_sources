# _alloca_probe

- ea: `0x140016200`
- end: `0x14001624d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x140001330`
- `0x140001edc`
- `0x140002180`
- `0x1400032a8`
- `0x1400043bc`
- `0x1400046bc`
- `0x140004b50`
- `0x140004fd0`
- `0x1400051cc`
- `0x140005418`
- `0x140005610`
- `0x140005760`
- `0x140008ec4`
- `0x1400090b4`
- `0x1400098d4`
- `0x14000a734`
- `0x14000a99c`
- `0x14000ac38`
- `0x14000cf38`
- `0x14000d674`
- `0x14000f464`
- `0x140014900`
- `0x140014b54`
- `0x140014e0c`

## callees

- `0x140016200`

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
0x140016200  sub     rsp, 10h
0x140016204  mov     [rsp+10h+var_10], r10
0x140016208  mov     [rsp+10h+var_8], r11
0x14001620d  xor     r11, r11
0x140016210  lea     r10, [rsp+10h+arg_0]
0x140016215  sub     r10, rax
0x140016218  cmovb   r10, r11
0x14001621c  mov     r11, gs:10h
0x140016225  cmp     r10, r11
0x140016228  jnb     short loc_14001623F
0x14001622a  and     r10w, 0F000h
0x140016230  lea     r11, [r11-1000h]
0x140016237  test    [r11], r11b
0x14001623a  cmp     r10, r11
0x14001623d  jb      short loc_140016230
0x14001623f  mov     r10, [rsp+10h+var_10]
0x140016243  mov     r11, [rsp+10h+var_8]
0x140016248  add     rsp, 10h
0x14001624c  retn
```
