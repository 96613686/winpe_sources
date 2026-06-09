# CreateOrOpenKey_0

- ea: `0x18001f340`
- end: `0x18001f3b0`
- name: `CreateOrOpenKey_0`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004da68`

## callees

- `0x18001f340`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f39f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f388`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f388`

## pseudocode

```c
LSTATUS __fastcall CreateOrOpenKey_0(HKEY a1, const WCHAR *a2, int a3, REGSAM a4, HKEY *a5)
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
0x18001f340  mov     r11, rsp
0x18001f343  sub     rsp, 58h
0x18001f347  xor     r10d, r10d
0x18001f34a  test    rcx, rcx
0x18001f34d  jz      short loc_18001F3A6
0x18001f34f  test    rdx, rdx
0x18001f352  jz      short loc_18001F3A6
0x18001f354  mov     rax, [rsp+58h+arg_20]
0x18001f35c  test    rax, rax
0x18001f35f  jz      short loc_18001F3A6
0x18001f361  test    r8d, r8d
0x18001f364  jz      short loc_18001F390
0x18001f366  lea     r8, [r11+8]
0x18001f36a  mov     [r11+8], r10d
0x18001f36e  mov     [r11-18h], r8
0x18001f372  xor     r8d, r8d; Reserved
0x18001f375  mov     [r11-20h], rax
0x18001f379  mov     [r11-28h], r10
0x18001f37d  mov     [r11-30h], r9d
0x18001f381  xor     r9d, r9d; lpClass
0x18001f384  mov     [r11-38h], r10d
0x18001f388  call    cs:__imp_RegCreateKeyExW
0x18001f38e  jmp     short loc_18001F3AB
0x18001f390  xor     r8d, r8d
0x18001f393  mov     [rsp+58h+arg_20], rax
0x18001f39b  add     rsp, 58h
0x18001f39f  jmp     cs:__imp_RegOpenKeyExW
0x18001f3a6  mov     eax, 57h ; 'W'
0x18001f3ab  add     rsp, 58h
0x18001f3af  retn
```
