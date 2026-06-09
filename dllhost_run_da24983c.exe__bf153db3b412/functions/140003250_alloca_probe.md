# _alloca_probe

- ea: `0x140003250`
- end: `0x14000329e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ed8`
- `0x140002174`

## callees

- `0x140003250`

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
0x140003250  sub     rsp, 10h
0x140003254  mov     [rsp+10h+var_10], r10
0x140003258  mov     [rsp+10h+var_8], r11
0x14000325d  xor     r11, r11
0x140003260  lea     r10, [rsp+10h+arg_0]
0x140003265  sub     r10, rax
0x140003268  cmovb   r10, r11
0x14000326c  mov     r11, gs:10h
0x140003275  cmp     r10, r11
0x140003278  jnb     short loc_140003290
0x14000327a  and     r10w, 0F000h
0x140003280  lea     r11, [r11-1000h]
0x140003287  mov     byte ptr [r11], 0
0x14000328b  cmp     r10, r11
0x14000328e  jnz     short loc_140003280
0x140003290  mov     r10, [rsp+10h+var_10]
0x140003294  mov     r11, [rsp+10h+var_8]
0x140003299  add     rsp, 10h
0x14000329d  retn
```
