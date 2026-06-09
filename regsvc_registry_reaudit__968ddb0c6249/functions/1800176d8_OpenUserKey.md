# OpenUserKey

- ea: `0x1800176d8`
- end: `0x18001771f`
- name: `OpenUserKey`
- size: `71`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008870`
- `0x180016d3c`
- `0x180017210`

## callees

- `0x18001d698`

## pseudocode

```c
__int64 __fastcall OpenUserKey(HANDLE *a1)
{
  int v2; // [rsp+20h] [rbp-48h]
  __int128 v3; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v4; // [rsp+40h] [rbp-28h]
  __int64 v5; // [rsp+48h] [rbp-20h]
  __int128 v6; // [rsp+50h] [rbp-18h]

  v3 = 0x30u;
  v5 = 64;
  v4 = &UserStringKey;
  v6 = 0;
  return Wow64NtOpenKey(a1, 0x2000000u, &v3, 0, v2);
}

```

## disassembly

```asm
0x1800176d8  mov     r11, rsp
0x1800176db  sub     rsp, 68h
0x1800176df  xor     eax, eax
0x1800176e1  mov     qword ptr [r11-38h], 30h ; '0'
0x1800176e9  mov     [r11-30h], rax
0x1800176ed  lea     r8, [r11-38h]; int
0x1800176f1  lea     rax, UserStringKey
0x1800176f8  mov     qword ptr [r11-20h], 40h ; '@'
0x180017700  xorps   xmm0, xmm0
0x180017703  mov     [r11-28h], rax
0x180017707  xor     r9d, r9d; int
0x18001770a  mov     edx, 2000000h; int
0x18001770f  movdqu  [rsp+68h+var_18], xmm0
0x180017715  call    Wow64NtOpenKey
0x18001771a  add     rsp, 68h
0x18001771e  retn
```
