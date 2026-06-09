# _alloca_probe

- ea: `0x1400130e0`
- end: `0x14001312e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140003af8`
- `0x140003bb4`
- `0x140003c24`
- `0x140003e8c`
- `0x140004158`
- `0x140004404`
- `0x140008348`
- `0x14000905c`
- `0x14000bc10`
- `0x14000bd38`
- `0x140010e84`
- `0x140011688`

## callees

- `0x1400130e0`

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
0x1400130e0  sub     rsp, 10h
0x1400130e4  mov     [rsp+10h+var_10], r10
0x1400130e8  mov     [rsp+10h+var_8], r11
0x1400130ed  xor     r11, r11
0x1400130f0  lea     r10, [rsp+10h+arg_0]
0x1400130f5  sub     r10, rax
0x1400130f8  cmovb   r10, r11
0x1400130fc  mov     r11, gs:10h
0x140013105  cmp     r10, r11
0x140013108  jnb     short loc_140013120
0x14001310a  and     r10w, 0F000h
0x140013110  lea     r11, [r11-1000h]
0x140013117  mov     byte ptr [r11], 0
0x14001311b  cmp     r10, r11
0x14001311e  jnz     short loc_140013110
0x140013120  mov     r10, [rsp+10h+var_10]
0x140013124  mov     r11, [rsp+10h+var_8]
0x140013129  add     rsp, 10h
0x14001312d  retn
```
