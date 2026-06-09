# _alloca_probe

- ea: `0x180018590`
- end: `0x1800185dd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000261c`
- `0x180002884`
- `0x180002b18`
- `0x180004314`
- `0x180008558`
- `0x180008a7c`
- `0x180008dd0`
- `0x180009e1c`
- `0x18000b540`
- `0x18000f074`
- `0x180011a34`
- `0x180016a70`

## callees

- `0x180018590`

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
0x180018590  sub     rsp, 10h
0x180018594  mov     [rsp+10h+var_10], r10
0x180018598  mov     [rsp+10h+var_8], r11
0x18001859d  xor     r11, r11
0x1800185a0  lea     r10, [rsp+10h+arg_0]
0x1800185a5  sub     r10, rax
0x1800185a8  cmovb   r10, r11
0x1800185ac  mov     r11, gs:10h
0x1800185b5  cmp     r10, r11
0x1800185b8  jnb     short loc_1800185CF
0x1800185ba  and     r10w, 0F000h
0x1800185c0  lea     r11, [r11-1000h]
0x1800185c7  test    [r11], r11b
0x1800185ca  cmp     r10, r11
0x1800185cd  jb      short loc_1800185C0
0x1800185cf  mov     r10, [rsp+10h+var_10]
0x1800185d3  mov     r11, [rsp+10h+var_8]
0x1800185d8  add     rsp, 10h
0x1800185dc  retn
```
