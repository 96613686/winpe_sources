# RassrvRegSetBinary

- ea: `0x1800218dc`
- end: `0x18002198e`
- name: `RassrvRegSetBinary`
- size: `178`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180028c40`

## callees

- `0x1800218dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021974`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021974`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002193a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002193a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021962`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021962`

## pseudocode

```c
__int64 __fastcall RassrvRegSetBinary(BYTE *lpData, __int64 a2, const WCHAR *a3, const WCHAR *a4)
{
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  DWORD v9; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v9 = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x20006u, 0, &hKey, &v9);
  if ( !v6 )
    v6 = RegSetValueExW(hKey, a4, 0, 3u, lpData, 0x10u);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800218dc  mov     rax, rsp
0x1800218df  mov     [rax+8], rbx
0x1800218e3  mov     [rax+18h], rsi
0x1800218e7  mov     [rax+10h], edx
0x1800218ea  push    rdi
0x1800218eb  sub     rsp, 60h
0x1800218ef  mov     rsi, rcx
0x1800218f2  mov     qword ptr [rax-18h], 0
0x1800218fa  lea     rcx, [rax+10h]
0x1800218fe  mov     dword ptr [rax+10h], 0
0x180021905  mov     [rax-28h], rcx
0x180021909  mov     rdi, r9
0x18002190c  lea     rcx, [rax-18h]
0x180021910  mov     rdx, r8; lpSubKey
0x180021913  mov     [rax-30h], rcx
0x180021917  xor     r9d, r9d; lpClass
0x18002191a  mov     qword ptr [rax-38h], 0
0x180021922  xor     r8d, r8d; Reserved
0x180021925  mov     dword ptr [rax-40h], 20006h
0x18002192c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021933  mov     dword ptr [rax-48h], 0
0x18002193a  call    cs:__imp_RegCreateKeyExW
0x180021940  mov     ebx, eax
0x180021942  test    eax, eax
0x180021944  jnz     short loc_18002196A
0x180021946  mov     rcx, [rsp+68h+hKey]; hKey
0x18002194b  lea     r9d, [rax+3]; dwType
0x18002194f  mov     [rsp+68h+cbData], 10h; cbData
0x180021957  xor     r8d, r8d; Reserved
0x18002195a  mov     rdx, rdi; lpValueName
0x18002195d  mov     [rsp+68h+lpData], rsi; lpData
0x180021962  call    cs:__imp_RegSetValueExW
0x180021968  mov     ebx, eax
0x18002196a  mov     rcx, [rsp+68h+hKey]; hKey
0x18002196f  test    rcx, rcx
0x180021972  jz      short loc_18002197A
0x180021974  call    cs:__imp_RegCloseKey
0x18002197a  lea     r11, [rsp+68h+var_8]
0x18002197f  mov     eax, ebx
0x180021981  mov     rbx, [r11+10h]
0x180021985  mov     rsi, [r11+20h]
0x180021989  mov     rsp, r11
0x18002198c  pop     rdi
0x18002198d  retn
```
