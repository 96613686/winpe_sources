# CreateOrOpenKey

- ea: `0x18000716c`
- end: `0x1800071dc`
- name: `CreateOrOpenKey`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006f60`
- `0x180041d50`
- `0x180041f10`

## callees

- `0x18000716c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800071b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800071b4`

## pseudocode

```c
LSTATUS __fastcall CreateOrOpenKey(HKEY a1, const WCHAR *a2, int a3, REGSAM a4, HKEY *a5)
{
  DWORD v6; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 || !a2 || !a5 )
    return 87;
  if ( !a3 )
    return RegOpenKeyExW(a1, a2, 0, a4, a5);
  v6 = 0;
  return RegCreateKeyExW(a1, a2, 0, 0, 0, a4, 0, a5, &v6);
}

```

## disassembly

```asm
0x18000716c  mov     r11, rsp
0x18000716f  sub     rsp, 58h
0x180007173  xor     r10d, r10d
0x180007176  test    rcx, rcx
0x180007179  jz      short loc_1800071D5
0x18000717b  test    rdx, rdx
0x18000717e  jz      short loc_1800071D5
0x180007180  mov     rax, [rsp+58h+arg_20]
0x180007188  test    rax, rax
0x18000718b  jz      short loc_1800071D5
0x18000718d  test    r8d, r8d
0x180007190  jz      short loc_1800071BF
0x180007192  lea     r8, [r11+8]
0x180007196  mov     [r11+8], r10d
0x18000719a  mov     [r11-18h], r8
0x18000719e  xor     r8d, r8d; Reserved
0x1800071a1  mov     [r11-20h], rax
0x1800071a5  mov     [r11-28h], r10
0x1800071a9  mov     [r11-30h], r9d
0x1800071ad  xor     r9d, r9d; lpClass
0x1800071b0  mov     [r11-38h], r10d
0x1800071b4  call    cs:__imp_RegCreateKeyExW
0x1800071ba  add     rsp, 58h
0x1800071be  retn
0x1800071bf  xor     r8d, r8d
0x1800071c2  mov     [rsp+58h+arg_20], rax
0x1800071ca  add     rsp, 58h
0x1800071ce  jmp     cs:__imp_RegOpenKeyExW
0x1800071d5  mov     eax, 57h ; 'W'
0x1800071da  jmp     short loc_1800071BA
```
