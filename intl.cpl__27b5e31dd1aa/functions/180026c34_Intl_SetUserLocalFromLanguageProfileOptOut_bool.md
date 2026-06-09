# Intl_SetUserLocalFromLanguageProfileOptOut(bool)

- ea: `0x180026c34`
- end: `0x180026cda`
- name: `?Intl_SetUserLocalFromLanguageProfileOptOut@@YA_N_N@Z`
- size: `166`
- prototype: `bool __fastcall(bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001e95c`

## callees

- `0x180026c34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026cc1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026cc1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026c8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026c8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026ccc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026ccc`

## pseudocode

```c
char __fastcall Intl_SetUserLocalFromLanguageProfileOptOut(char a1)
{
  bool v1; // bl
  BOOL Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  LOBYTE(Data) = a1;
  v1 = g_fSetUserLocaleBasedOnLanguageListOptOut;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\International\\User Profile", 0, 0, 0, 2u, 0, &hKey, 0) )
  {
    Data = v1;
    RegSetValueExW(hKey, L"UserLocaleFromLanguageProfileOptOut", 0, 4u, (const BYTE *)&Data, 4u);
  }
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x180026c34  mov     byte ptr [rsp+Data], cl
0x180026c38  mov     r11, rsp
0x180026c3b  push    rbx
0x180026c3c  sub     rsp, 50h
0x180026c40  mov     bl, cs:?g_fSetUserLocaleBasedOnLanguageListOptOut@@3_NA; bool g_fSetUserLocaleBasedOnLanguageListOptOut
0x180026c46  lea     rax, [r11+10h]
0x180026c4a  mov     qword ptr [r11-18h], 0
0x180026c52  lea     rdx, aControlPanelIn_1; "Control Panel\\International\\User Prof"...
0x180026c59  mov     [r11-20h], rax
0x180026c5d  xor     r9d, r9d; lpClass
0x180026c60  mov     qword ptr [r11-28h], 0
0x180026c68  xor     r8d, r8d; Reserved
0x180026c6b  mov     [rsp+58h+samDesired], 2; samDesired
0x180026c73  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180026c7a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180026c82  mov     qword ptr [r11+10h], 0
0x180026c8a  call    cs:__imp_RegCreateKeyExW
0x180026c90  test    eax, eax
0x180026c92  jnz     short loc_180026CC7
0x180026c94  mov     rcx, [rsp+58h+hKey]; hKey
0x180026c99  lea     rdx, aUserlocalefrom; "UserLocaleFromLanguageProfileOptOut"
0x180026ca0  test    bl, bl
0x180026ca2  mov     r9d, 4; dwType
0x180026ca8  mov     [rsp+58h+samDesired], r9d; cbData
0x180026cad  setnz   al
0x180026cb0  xor     r8d, r8d; Reserved
0x180026cb3  mov     [rsp+58h+Data], eax
0x180026cb7  lea     rax, [rsp+58h+Data]
0x180026cbc  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180026cc1  call    cs:__imp_RegSetValueExW
0x180026cc7  mov     rcx, [rsp+58h+hKey]; hKey
0x180026ccc  call    cs:__imp_RegCloseKey
0x180026cd2  mov     al, 1
0x180026cd4  add     rsp, 50h
0x180026cd8  pop     rbx
0x180026cd9  retn
```
