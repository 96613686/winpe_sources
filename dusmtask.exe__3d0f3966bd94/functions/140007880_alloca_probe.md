# _alloca_probe

- ea: `0x140007880`
- end: `0x1400078ce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002324`
- `0x1400027b4`
- `0x140002a34`
- `0x140002d48`
- `0x140002ff4`
- `0x140006e60`

## callees

- `0x140007880`

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
0x140007880  sub     rsp, 10h
0x140007884  mov     [rsp+10h+var_10], r10
0x140007888  mov     [rsp+10h+var_8], r11
0x14000788d  xor     r11, r11
0x140007890  lea     r10, [rsp+10h+arg_0]
0x140007895  sub     r10, rax
0x140007898  cmovb   r10, r11
0x14000789c  mov     r11, gs:10h
0x1400078a5  cmp     r10, r11
0x1400078a8  jnb     short loc_1400078C0
0x1400078aa  and     r10w, 0F000h
0x1400078b0  lea     r11, [r11-1000h]
0x1400078b7  mov     byte ptr [r11], 0
0x1400078bb  cmp     r10, r11
0x1400078be  jnz     short loc_1400078B0
0x1400078c0  mov     r10, [rsp+10h+var_10]
0x1400078c4  mov     r11, [rsp+10h+var_8]
0x1400078c9  add     rsp, 10h
0x1400078cd  retn
```
