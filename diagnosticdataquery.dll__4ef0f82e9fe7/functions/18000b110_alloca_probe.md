# _alloca_probe

- ea: `0x18000b110`
- end: `0x18000b15e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000562c`
- `0x18000589c`
- `0x180005b30`
- `0x180008a40`

## callees

- `0x18000b110`

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
0x18000b110  sub     rsp, 10h
0x18000b114  mov     [rsp+10h+var_10], r10
0x18000b118  mov     [rsp+10h+var_8], r11
0x18000b11d  xor     r11, r11
0x18000b120  lea     r10, [rsp+10h+arg_0]
0x18000b125  sub     r10, rax
0x18000b128  cmovb   r10, r11
0x18000b12c  mov     r11, gs:10h
0x18000b135  cmp     r10, r11
0x18000b138  jnb     short cs20
0x18000b13a  and     r10w, 0F000h
0x18000b140  lea     r11, [r11-1000h]
0x18000b147  mov     byte ptr [r11], 0
0x18000b14b  cmp     r10, r11
0x18000b14e  jnz     short cs10
0x18000b150  mov     r10, [rsp+10h+var_10]
0x18000b154  mov     r11, [rsp+10h+var_8]
0x18000b159  add     rsp, 10h
0x18000b15d  retn
```
