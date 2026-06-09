# GetRegDword

- ea: `0x18000ac40`
- end: `0x18000ac9e`
- name: `GetRegDword`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009588`
- `0x180009784`
- `0x180009a30`

## callees

- `0x18000ac40`

## import_xrefs

- `KERNEL32!RegQueryValueExW` at `0x18000ac7a`
- `KERNEL32!RegQueryValueExW` at `0x18000ac7a`

## pseudocode

```c
LSTATUS __fastcall GetRegDword(HKEY a1, const WCHAR *a2, LSTATUS *a3)
{
  LSTATUS result; // eax
  DWORD v5; // [rsp+30h] [rbp-18h] BYREF
  LSTATUS v6[5]; // [rsp+34h] [rbp-14h] BYREF
  DWORD v7; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  v6[0] = 0;
  v5 = 4;
  result = RegQueryValueExW(a1, a2, 0, &v7, (LPBYTE)v6, &v5);
  if ( !result && v7 == 4 && v5 == 4 )
  {
    result = v6[0];
    *a3 = v6[0];
  }
  return result;
}

```

## disassembly

```asm
0x18000ac40  mov     r11, rsp
0x18000ac43  push    rbx
0x18000ac44  sub     rsp, 40h
0x18000ac48  lea     rax, [r11-18h]
0x18000ac4c  mov     [rsp+48h+arg_18], 0
0x18000ac54  mov     [r11-20h], rax
0x18000ac58  lea     r9, [r11+20h]; lpType
0x18000ac5c  lea     rax, [r11-14h]
0x18000ac60  mov     [rsp+48h+var_14], 0
0x18000ac68  mov     rbx, r8
0x18000ac6b  mov     [r11-28h], rax
0x18000ac6f  xor     r8d, r8d; lpReserved
0x18000ac72  mov     [rsp+48h+var_18], 4
0x18000ac7a  call    cs:__imp_RegQueryValueExW
0x18000ac80  test    eax, eax
0x18000ac82  jnz     short loc_18000AC98
0x18000ac84  cmp     [rsp+48h+arg_18], 4
0x18000ac89  jnz     short loc_18000AC98
0x18000ac8b  cmp     [rsp+48h+var_18], 4
0x18000ac90  jnz     short loc_18000AC98
0x18000ac92  mov     eax, [rsp+48h+var_14]
0x18000ac96  mov     [rbx], eax
0x18000ac98  add     rsp, 40h
0x18000ac9c  pop     rbx
0x18000ac9d  retn
```
