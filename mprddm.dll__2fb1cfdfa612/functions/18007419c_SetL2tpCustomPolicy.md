# SetL2tpCustomPolicy

- ea: `0x18007419c`
- end: `0x180074248`
- name: `SetL2tpCustomPolicy`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180074028`

## callees

- `0x18007392c`
- `0x18007419c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180074235`
- `ADVAPI32!RegCloseKey` at `0x180074235`
- `ADVAPI32!RegCreateKeyExW` at `0x180074210`
- `ADVAPI32!RegCreateKeyExW` at `0x180074210`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800741d8`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800741d8`

## pseudocode

```c
__int64 __fastcall SetL2tpCustomPolicy(HKEY a1, BYTE *a2)
{
  unsigned int v3; // ebx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  dwDisposition = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v3 = RegCreateKeyExW(a1, L"L2TPCustomPolicy", 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
      if ( !v3 )
        v3 = SetCustomPolicyRegParams(hKey, a2);
    }
    else
    {
      v3 = 0;
      RegDeleteKeyExW(a1, L"L2TPCustomPolicy", 0, 0);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x18007419c  mov     [rsp+arg_8], rbx
0x1800741a1  push    rdi
0x1800741a2  sub     rsp, 50h
0x1800741a6  mov     [rsp+58h+hKey], 0
0x1800741af  mov     rdi, rdx
0x1800741b2  mov     [rsp+58h+dwDisposition], 0
0x1800741ba  test    rcx, rcx
0x1800741bd  jnz     short loc_1800741C4
0x1800741bf  lea     ebx, [rcx+57h]
0x1800741c2  jmp     short loc_18007423B
0x1800741c4  xor     r8d, r8d; Reserved
0x1800741c7  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x1800741ce  test    rdi, rdi
0x1800741d1  jnz     short loc_1800741E0
0x1800741d3  xor     ebx, ebx
0x1800741d5  xor     r9d, r9d; Reserved
0x1800741d8  call    cs:__imp_RegDeleteKeyExW
0x1800741de  jmp     short loc_18007422B
0x1800741e0  lea     rax, [rsp+58h+dwDisposition]
0x1800741e5  xor     r9d, r9d; lpClass
0x1800741e8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800741ed  lea     rax, [rsp+58h+hKey]
0x1800741f2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800741f7  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180074200  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x180074208  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180074210  call    cs:__imp_RegCreateKeyExW
0x180074216  mov     ebx, eax
0x180074218  test    eax, eax
0x18007421a  jnz     short loc_18007422B
0x18007421c  mov     rcx, [rsp+58h+hKey]; hKey
0x180074221  mov     rdx, rdi; lpData
0x180074224  call    SetCustomPolicyRegParams
0x180074229  mov     ebx, eax
0x18007422b  mov     rcx, [rsp+58h+hKey]; hKey
0x180074230  test    rcx, rcx
0x180074233  jz      short loc_18007423B
0x180074235  call    cs:__imp_RegCloseKey
0x18007423b  mov     eax, ebx
0x18007423d  mov     rbx, [rsp+58h+arg_8]
0x180074242  add     rsp, 50h
0x180074246  pop     rdi
0x180074247  retn
```
