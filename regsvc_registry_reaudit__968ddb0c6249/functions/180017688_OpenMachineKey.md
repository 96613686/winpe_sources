# OpenMachineKey

- ea: `0x180017688`
- end: `0x1800176cf`
- name: `OpenMachineKey`
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
__int64 __fastcall OpenMachineKey(HANDLE *a1)
{
  int v2; // [rsp+20h] [rbp-48h]
  __int128 v3; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v4; // [rsp+40h] [rbp-28h]
  __int64 v5; // [rsp+48h] [rbp-20h]
  __int128 v6; // [rsp+50h] [rbp-18h]

  v3 = 0x30u;
  v5 = 64;
  v4 = L"\"\"";
  v6 = 0;
  return Wow64NtOpenKey(a1, 0x2000000u, &v3, 0, v2);
}

```

## disassembly

```asm
0x180017688  mov     r11, rsp
0x18001768b  sub     rsp, 68h
0x18001768f  xor     eax, eax
0x180017691  mov     qword ptr [r11-38h], 30h ; '0'
0x180017699  mov     [r11-30h], rax
0x18001769d  lea     r8, [r11-38h]; int
0x1800176a1  lea     rax, MachineStringKey; "\"\""
0x1800176a8  mov     qword ptr [r11-20h], 40h ; '@'
0x1800176b0  xorps   xmm0, xmm0
0x1800176b3  mov     [r11-28h], rax
0x1800176b7  xor     r9d, r9d; int
0x1800176ba  mov     edx, 2000000h; int
0x1800176bf  movdqu  [rsp+68h+var_18], xmm0
0x1800176c5  call    Wow64NtOpenKey
0x1800176ca  add     rsp, 68h
0x1800176ce  retn
```
