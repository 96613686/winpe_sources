# _alloca_probe

- ea: `0x1400113b0`
- end: `0x1400113fe`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000377c`
- `0x1400038d0`
- `0x140003cd4`
- `0x140003f54`
- `0x1400042ec`
- `0x140004598`
- `0x14000badc`
- `0x140010c10`
- `0x140010d38`

## callees

- `0x1400113b0`

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
0x1400113b0  sub     rsp, 10h
0x1400113b4  mov     [rsp+10h+var_10], r10
0x1400113b8  mov     [rsp+10h+var_8], r11
0x1400113bd  xor     r11, r11
0x1400113c0  lea     r10, [rsp+10h+arg_0]
0x1400113c5  sub     r10, rax
0x1400113c8  cmovb   r10, r11
0x1400113cc  mov     r11, gs:10h
0x1400113d5  cmp     r10, r11
0x1400113d8  jnb     short loc_1400113F0
0x1400113da  and     r10w, 0F000h
0x1400113e0  lea     r11, [r11-1000h]
0x1400113e7  mov     byte ptr [r11], 0
0x1400113eb  cmp     r10, r11
0x1400113ee  jnz     short loc_1400113E0
0x1400113f0  mov     r10, [rsp+10h+var_10]
0x1400113f4  mov     r11, [rsp+10h+var_8]
0x1400113f9  add     rsp, 10h
0x1400113fd  retn
```
