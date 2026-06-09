# Intl_GetUserLocalFromLanguageProfileOptOut(void)

- ea: `0x1800256cc`
- end: `0x180025785`
- name: `?Intl_GetUserLocalFromLanguageProfileOptOut@@YA_NXZ`
- size: `185`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001ebc8`
- `0x18001f95c`

## callees

- `0x1800256cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025761`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025761`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002571a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002571a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025777`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025777`

## pseudocode

```c
bool Intl_GetUserLocalFromLanguageProfileOptOut(void)
{
  bool v0; // bl
  int pvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+18h] BYREF

  hkey = 0;
  v0 = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Control Panel\\International\\User Profile",
          0,
          0,
          0,
          0x20019u,
          0,
          &hkey,
          0) )
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"UserLocaleFromLanguageProfileOptOut", 0x18u, 0, &pvData, &pcbData) )
      v0 = pvData != 0;
  }
  RegCloseKey(hkey);
  return v0;
}

```

## disassembly

```asm
0x1800256cc  mov     r11, rsp
0x1800256cf  push    rbx
0x1800256d0  sub     rsp, 50h
0x1800256d4  mov     qword ptr [r11-18h], 0
0x1800256dc  lea     rax, [r11+18h]
0x1800256e0  mov     [r11-20h], rax
0x1800256e4  lea     rdx, aControlPanelIn_1; "Control Panel\\International\\User Prof"...
0x1800256eb  mov     qword ptr [r11-28h], 0
0x1800256f3  xor     r9d, r9d; lpClass
0x1800256f6  mov     [rsp+58h+samDesired], 20019h; samDesired
0x1800256fe  xor     r8d, r8d; Reserved
0x180025701  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180025708  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180025710  mov     qword ptr [r11+18h], 0
0x180025718  xor     bl, bl
0x18002571a  call    cs:__imp_RegCreateKeyExW
0x180025720  test    eax, eax
0x180025722  jnz     short loc_180025772
0x180025724  mov     rcx, [rsp+58h+hkey]; hkey
0x180025729  lea     r8, aUserlocalefrom; "UserLocaleFromLanguageProfileOptOut"
0x180025730  mov     [rsp+58h+pvData], eax
0x180025734  mov     r9d, 18h; dwFlags
0x18002573a  lea     rax, [rsp+58h+arg_8]
0x18002573f  mov     [rsp+58h+arg_8], 4
0x180025747  mov     [rsp+58h+pcbData], rax; pcbData
0x18002574c  xor     edx, edx; lpSubKey
0x18002574e  lea     rax, [rsp+58h+pvData]
0x180025753  mov     qword ptr [rsp+58h+samDesired], rax; pvData
0x180025758  mov     qword ptr [rsp+58h+dwOptions], 0; pdwType
0x180025761  call    cs:__imp_RegGetValueW
0x180025767  test    eax, eax
0x180025769  jnz     short loc_180025772
0x18002576b  cmp     [rsp+58h+pvData], eax
0x18002576f  setnz   bl
0x180025772  mov     rcx, [rsp+58h+hkey]; hKey
0x180025777  call    cs:__imp_RegCloseKey
0x18002577d  mov     al, bl
0x18002577f  add     rsp, 50h
0x180025783  pop     rbx
0x180025784  retn
```
