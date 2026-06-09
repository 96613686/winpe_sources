# RegistrySerialization::s_QueryValue(HKEY__ * const,wchar_t const * const,ulong,ulong,uchar * const,ulong * const)

- ea: `0x1800186e4`
- end: `0x180018759`
- name: `?s_QueryValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKKQEAEQEAK@Z`
- size: `117`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *const, unsigned int, unsigned int, unsigned __int8 *const, unsigned int *const)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800114d4`
- `0x180017368`
- `0x1800187a0`

## callees

- `0x1800186e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018713`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018713`

## pseudocode

```c
__int64 __fastcall RegistrySerialization::s_QueryValue(
        HKEY a1,
        const WCHAR *a2,
        DWORD a3,
        int a4,
        unsigned __int8 *const a5,
        unsigned int *const a6)
{
  LSTATUS v7; // ecx
  DWORD v9[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v10; // [rsp+60h] [rbp+18h] BYREF

  v9[0] = a3;
  v10 = 0;
  v7 = RegQueryValueExW(a1, a2, 0, &v10, a5, v9);
  if ( v7 != 2 && v10 != a4 )
    return 3221225508LL;
  if ( a6 )
    *a6 = v9[0];
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0xC0070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800186e4  mov     r11, rsp
0x1800186e7  push    rbx
0x1800186e8  sub     rsp, 40h
0x1800186ec  lea     rax, [r11-18h]
0x1800186f0  mov     [r11-18h], r8d
0x1800186f4  mov     [r11-20h], rax
0x1800186f8  mov     ebx, r9d
0x1800186fb  mov     rax, [rsp+48h+arg_20]
0x180018700  lea     r9, [r11+18h]; lpType
0x180018704  xor     r8d, r8d; lpReserved
0x180018707  mov     [r11-28h], rax
0x18001870b  mov     [rsp+48h+arg_10], 0
0x180018713  call    cs:__imp_RegQueryValueExW
0x18001871a  nop     dword ptr [rax+rax+00h]
0x18001871f  mov     ecx, eax
0x180018721  cmp     eax, 2
0x180018724  jz      short loc_180018733
0x180018726  cmp     [rsp+48h+arg_10], ebx
0x18001872a  jz      short loc_180018733
0x18001872c  mov     eax, 0C0000024h
0x180018731  jmp     short loc_180018752
0x180018733  mov     rdx, [rsp+48h+arg_28]
0x180018738  test    rdx, rdx
0x18001873b  jz      short loc_180018743
0x18001873d  mov     eax, [rsp+48h+var_18]
0x180018741  mov     [rdx], eax
0x180018743  test    ecx, ecx
0x180018745  jle     short loc_180018750
0x180018747  movzx   ecx, cx
0x18001874a  or      ecx, 0C0070000h
0x180018750  mov     eax, ecx
0x180018752  add     rsp, 40h
0x180018756  pop     rbx
0x180018757  retn
```
