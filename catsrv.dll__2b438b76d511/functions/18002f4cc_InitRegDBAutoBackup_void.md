# InitRegDBAutoBackup(void)

- ea: `0x18002f4cc`
- end: `0x18002f5f2`
- name: `?InitRegDBAutoBackup@@YAXXZ`
- size: `294`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f5f8`

## callees

- `0x18002f4cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f55e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f55e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f5da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f5da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f523`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f523`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f590`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f590`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f5cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f5cf`

## string_xrefs

- `0x18002f554`: `Software\Microsoft\COM3`
- `0x18002f4e4`: `SOFTWARE\Microsoft\COM3\SelfReg\CLSID`

## pseudocode

```c
void InitRegDBAutoBackup(void)
{
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  cbData = 4;
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\COM3\\SelfReg\\CLSID", 0, 0, 0, 0, 0, &hKey, 0) )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3", 0, 0x2011Bu, &hKey) )
  {
    *(_DWORD *)&Data = 1;
  }
  else
  {
    if ( RegQueryValueExW(hKey, L"RegDBAutoBackUp", 0, 0, &Data, &cbData) || *(_DWORD *)&Data > 0xAu )
    {
      *(_DWORD *)&Data = 1;
      RegSetValueExW(hKey, L"RegDBAutoBackUp", 0, 4u, &Data, 4u);
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18002f4cc  mov     r11, rsp
0x18002f4cf  push    rsi
0x18002f4d0  sub     rsp, 50h
0x18002f4d4  mov     qword ptr [r11-18h], 0
0x18002f4dc  lea     rax, [r11+10h]
0x18002f4e0  mov     [r11-20h], rax
0x18002f4e4  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\COM3\\SelfReg\\CLS"...
0x18002f4eb  mov     qword ptr [r11-28h], 0
0x18002f4f3  mov     rsi, 0FFFFFFFF80000002h
0x18002f4fa  mov     [rsp+58h+samDesired], 0; samDesired
0x18002f502  xor     r9d, r9d; lpClass
0x18002f505  xor     r8d, r8d; Reserved
0x18002f508  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002f510  mov     rcx, rsi; hKey
0x18002f513  mov     qword ptr [r11+10h], 0
0x18002f51b  mov     [rsp+58h+cbData], 4
0x18002f523  call    cs:__imp_RegCreateKeyExW
0x18002f529  test    eax, eax
0x18002f52b  jnz     short loc_18002F541
0x18002f52d  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f532  call    cs:__imp_RegCloseKey
0x18002f538  mov     [rsp+58h+hKey], 0
0x18002f541  lea     rax, [rsp+58h+hKey]
0x18002f546  mov     r9d, 2011Bh; samDesired
0x18002f54c  xor     r8d, r8d; ulOptions
0x18002f54f  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x18002f554  lea     rdx, SubKey; "Software\\Microsoft\\COM3"
0x18002f55b  mov     rcx, rsi; hKey
0x18002f55e  call    cs:__imp_RegOpenKeyExW
0x18002f564  test    eax, eax
0x18002f566  jnz     short loc_18002F5E2
0x18002f568  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f56d  lea     rax, [rsp+58h+cbData]
0x18002f572  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18002f577  lea     rsi, Data
0x18002f57e  xor     r9d, r9d; lpType
0x18002f581  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x18002f586  xor     r8d, r8d; lpReserved
0x18002f589  lea     rdx, aRegdbautobacku; "RegDBAutoBackUp"
0x18002f590  call    cs:__imp_RegQueryValueExW
0x18002f596  test    eax, eax
0x18002f598  jnz     short loc_18002F5A3
0x18002f59a  cmp     cs:Data, 0Ah
0x18002f5a1  jbe     short loc_18002F5D5
0x18002f5a3  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f5a8  lea     rdx, aRegdbautobacku; "RegDBAutoBackUp"
0x18002f5af  mov     [rsp+58h+samDesired], 4; cbData
0x18002f5b7  mov     r9d, 4; dwType
0x18002f5bd  xor     r8d, r8d; Reserved
0x18002f5c0  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x18002f5c5  mov     cs:Data, 1
0x18002f5cf  call    cs:__imp_RegSetValueExW
0x18002f5d5  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f5da  call    cs:__imp_RegCloseKey
0x18002f5e0  jmp     short loc_18002F5EC
0x18002f5e2  mov     cs:Data, 1
0x18002f5ec  add     rsp, 50h
0x18002f5f0  pop     rsi
0x18002f5f1  retn
```
