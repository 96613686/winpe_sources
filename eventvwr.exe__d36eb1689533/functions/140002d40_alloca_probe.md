# _alloca_probe

- ea: `0x140002d40`
- end: `0x140002d8d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f30`

## callees

- `0x140002d40`

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
0x140002d40  sub     rsp, 10h
0x140002d44  mov     [rsp+10h+var_10], r10
0x140002d48  mov     [rsp+10h+var_8], r11
0x140002d4d  xor     r11, r11
0x140002d50  lea     r10, [rsp+10h+arg_0]
0x140002d55  sub     r10, rax
0x140002d58  cmovb   r10, r11
0x140002d5c  mov     r11, gs:10h
0x140002d65  cmp     r10, r11
0x140002d68  jnb     short loc_140002D7F
0x140002d6a  and     r10w, 0F000h
0x140002d70  lea     r11, [r11-1000h]
0x140002d77  test    [r11], r11b
0x140002d7a  cmp     r10, r11
0x140002d7d  jb      short loc_140002D70
0x140002d7f  mov     r10, [rsp+10h+var_10]
0x140002d83  mov     r11, [rsp+10h+var_8]
0x140002d88  add     rsp, 10h
0x140002d8c  retn
```
