# DllRegisterServer

- ea: `0x180012f50`
- end: `0x180012ff5`
- name: `DllRegisterServer`
- size: `165`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c628`
- `0x180012f50`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180012fc2`
- `ADVAPI32!RegSetValueExW` at `0x180012fc2`
- `ADVAPI32!RegOpenKeyExW` at `0x180012f8f`
- `ADVAPI32!RegOpenKeyExW` at `0x180012f8f`
- `ADVAPI32!RegCloseKey` at `0x180012fe0`
- `ADVAPI32!RegCloseKey` at `0x180012fe0`

## string_xrefs

- `0x180012fad`: `DllSurrogate`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v0; // edx
  struct ATL::_ATL_MODULE *v1; // rcx
  const struct _GUID *v2; // r8
  HRESULT v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v3 = ATL::AtlModuleRegisterServer(v1, v0, v2);
  if ( v3 >= 0 )
  {
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID\\{DCBCADF5-DB1b-4764-9320-9a5082af1581}", 0, 0x20006u, &hKey) )
    {
      return -2147221168;
    }
    else
    {
      v4 = RegSetValueExW(hKey, L"DllSurrogate", 0, 1u, " ", 2u);
      if ( v4 )
      {
        if ( v4 > 0 )
          v3 = (unsigned __int16)v4 | 0x80070000;
        else
          v3 = v4;
      }
      RegCloseKey(hKey);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180012f50  push    rbx
0x180012f52  sub     rsp, 30h
0x180012f56  call    ?AtlModuleRegisterServer@ATL@@YAJPEAU_ATL_MODULE@1@HPEBU_GUID@@@Z; ATL::AtlModuleRegisterServer(ATL::_ATL_MODULE *,int,_GUID const *)
0x180012f5b  mov     ebx, eax
0x180012f5d  test    eax, eax
0x180012f5f  js      loc_180012FED
0x180012f65  lea     rax, [rsp+38h+hKey]
0x180012f6a  mov     [rsp+38h+hKey], 0
0x180012f73  mov     r9d, 20006h; samDesired
0x180012f79  mov     [rsp+38h+phkResult], rax; phkResult
0x180012f7e  xor     r8d, r8d; ulOptions
0x180012f81  lea     rdx, SubKey; "AppID\\{DCBCADF5-DB1b-4764-9320-9a5082a"...
0x180012f88  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180012f8f  call    cs:__imp_RegOpenKeyExW
0x180012f95  test    eax, eax
0x180012f97  jnz     short loc_180012FE8
0x180012f99  mov     rcx, [rsp+38h+hKey]; hKey
0x180012f9e  lea     rax, Data; " "
0x180012fa5  mov     [rsp+38h+cbData], 2; cbData
0x180012fad  lea     rdx, ValueName; "DllSurrogate"
0x180012fb4  mov     r9d, 1; dwType
0x180012fba  mov     [rsp+38h+phkResult], rax; lpData
0x180012fbf  xor     r8d, r8d; Reserved
0x180012fc2  call    cs:__imp_RegSetValueExW
0x180012fc8  test    eax, eax
0x180012fca  jz      short loc_180012FDB
0x180012fcc  jg      short loc_180012FD2
0x180012fce  mov     ebx, eax
0x180012fd0  jmp     short loc_180012FDB
0x180012fd2  movzx   ebx, ax
0x180012fd5  or      ebx, 80070000h
0x180012fdb  mov     rcx, [rsp+38h+hKey]; hKey
0x180012fe0  call    cs:__imp_RegCloseKey
0x180012fe6  jmp     short loc_180012FED
0x180012fe8  mov     ebx, 80040150h
0x180012fed  mov     eax, ebx
0x180012fef  add     rsp, 30h
0x180012ff3  pop     rbx
0x180012ff4  retn
```
