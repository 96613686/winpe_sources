# Intl_DeleteRegSubKeys(HKEY__ *)

- ea: `0x180025078`
- end: `0x18002510c`
- name: `?Intl_DeleteRegSubKeys@@YAXPEAUHKEY__@@@Z`
- size: `148`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800265bc`
- `0x18002665c`

## callees

- `0x180025078`
- `0x18002a150`

## import_xrefs

- `SHLWAPI!SHDeleteKeyW` at `0x1800250a8`
- `SHLWAPI!SHDeleteKeyW` at `0x1800250a8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800250e9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800250e9`

## pseudocode

```c
void __fastcall Intl_DeleteRegSubKeys(HKEY hKey)
{
  HKEY i; // rbx
  DWORD cchName[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR pszSubKey[256]; // [rsp+50h] [rbp-218h] BYREF

  if ( hKey )
  {
    for ( i = hKey; ; hKey = i )
    {
      cchName[0] = 256;
      if ( RegEnumKeyExW(hKey, 0, pszSubKey, cchName, 0, 0, 0, 0) )
        break;
      SHDeleteKeyW(i, pszSubKey);
    }
  }
}

```

## disassembly

```asm
0x180025078  test    rcx, rcx
0x18002507b  jz      locret_18002510B
0x180025081  push    rbx
0x180025082  sub     rsp, 260h
0x180025089  mov     rax, cs:__security_cookie
0x180025090  xor     rax, rsp
0x180025093  mov     [rsp+268h+var_18], rax
0x18002509b  mov     rbx, rcx
0x18002509e  jmp     short loc_1800250B1
0x1800250a0  lea     rdx, [rsp+268h+pszSubKey]; pszSubKey
0x1800250a5  mov     rcx, rbx; hkey
0x1800250a8  call    cs:__imp_SHDeleteKeyW
0x1800250ae  mov     rcx, rbx; hKey
0x1800250b1  mov     [rsp+268h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800250ba  lea     r9, [rsp+268h+cchName]; lpcchName
0x1800250bf  mov     [rsp+268h+lpcchClass], 0; lpcchClass
0x1800250c8  lea     r8, [rsp+268h+pszSubKey]; lpName
0x1800250cd  mov     [rsp+268h+lpClass], 0; lpClass
0x1800250d6  xor     edx, edx; dwIndex
0x1800250d8  mov     [rsp+268h+lpReserved], 0; lpReserved
0x1800250e1  mov     [rsp+268h+cchName], 100h
0x1800250e9  call    cs:__imp_RegEnumKeyExW
0x1800250ef  test    eax, eax
0x1800250f1  jz      short loc_1800250A0
0x1800250f3  mov     rcx, [rsp+268h+var_18]
0x1800250fb  xor     rcx, rsp; StackCookie
0x1800250fe  call    __security_check_cookie
0x180025103  add     rsp, 260h
0x18002510a  pop     rbx
0x18002510b  retn
```
