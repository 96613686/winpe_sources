# _alloca_probe

- ea: `0x180011c00`
- end: `0x180011c4e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031bc`
- `0x180003424`
- `0x1800036b8`
- `0x1800077bc`
- `0x18000a350`
- `0x18000a478`

## callees

- `0x180011c00`

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
0x180011c00  sub     rsp, 10h
0x180011c04  mov     [rsp+10h+var_10], r10
0x180011c08  mov     [rsp+10h+var_8], r11
0x180011c0d  xor     r11, r11
0x180011c10  lea     r10, [rsp+10h+arg_0]
0x180011c15  sub     r10, rax
0x180011c18  cmovb   r10, r11
0x180011c1c  mov     r11, gs:10h
0x180011c25  cmp     r10, r11
0x180011c28  jnb     short cs20
0x180011c2a  and     r10w, 0F000h
0x180011c30  lea     r11, [r11-1000h]
0x180011c37  mov     byte ptr [r11], 0
0x180011c3b  cmp     r10, r11
0x180011c3e  jnz     short cs10
0x180011c40  mov     r10, [rsp+10h+var_10]
0x180011c44  mov     r11, [rsp+10h+var_8]
0x180011c49  add     rsp, 10h
0x180011c4d  retn
```
