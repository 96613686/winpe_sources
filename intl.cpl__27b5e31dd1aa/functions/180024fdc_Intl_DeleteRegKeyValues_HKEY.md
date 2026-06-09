# Intl_DeleteRegKeyValues(HKEY__ *)

- ea: `0x180024fdc`
- end: `0x180025070`
- name: `?Intl_DeleteRegKeyValues@@YAXPEAUHKEY__@@@Z`
- size: `148`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800265bc`
- `0x18002665c`

## callees

- `0x180024fdc`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002504d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002504d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002500c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002500c`

## pseudocode

```c
void __fastcall Intl_DeleteRegKeyValues(HKEY hKey)
{
  HKEY i; // rbx
  DWORD cchValueName[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR ValueName[256]; // [rsp+50h] [rbp-218h] BYREF

  if ( hKey )
  {
    for ( i = hKey; ; hKey = i )
    {
      cchValueName[0] = 256;
      if ( RegEnumValueW(hKey, 0, ValueName, cchValueName, 0, 0, 0, 0) )
        break;
      RegDeleteValueW(i, ValueName);
    }
  }
}

```

## disassembly

```asm
0x180024fdc  test    rcx, rcx
0x180024fdf  jz      locret_18002506F
0x180024fe5  push    rbx
0x180024fe6  sub     rsp, 260h
0x180024fed  mov     rax, cs:__security_cookie
0x180024ff4  xor     rax, rsp
0x180024ff7  mov     [rsp+268h+var_18], rax
0x180024fff  mov     rbx, rcx
0x180025002  jmp     short loc_180025015
0x180025004  lea     rdx, [rsp+268h+ValueName]; lpValueName
0x180025009  mov     rcx, rbx; hKey
0x18002500c  call    cs:__imp_RegDeleteValueW
0x180025012  mov     rcx, rbx; hKey
0x180025015  mov     [rsp+268h+lpcbData], 0; lpcbData
0x18002501e  lea     r9, [rsp+268h+cchValueName]; lpcchValueName
0x180025023  mov     [rsp+268h+lpData], 0; lpData
0x18002502c  lea     r8, [rsp+268h+ValueName]; lpValueName
0x180025031  mov     [rsp+268h+lpType], 0; lpType
0x18002503a  xor     edx, edx; dwIndex
0x18002503c  mov     [rsp+268h+lpReserved], 0; lpReserved
0x180025045  mov     [rsp+268h+cchValueName], 100h
0x18002504d  call    cs:__imp_RegEnumValueW
0x180025053  test    eax, eax
0x180025055  jz      short loc_180025004
0x180025057  mov     rcx, [rsp+268h+var_18]
0x18002505f  xor     rcx, rsp; StackCookie
0x180025062  call    __security_check_cookie
0x180025067  add     rsp, 260h
0x18002506e  pop     rbx
0x18002506f  retn
```
