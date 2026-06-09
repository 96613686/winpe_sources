# DllUnregisterServer

- ea: `0x18000eab0`
- end: `0x18000eb21`
- name: `DllUnregisterServer`
- size: `113`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ab30`
- `0x18000eab0`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000eae7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000eae7`
- `msdmo!DMOUnregister` at `0x18000eafd`
- `msdmo!DMOUnregister` at `0x18000eafd`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const struct _GUID *v0; // rcx
  LSTATUS CLSIDRegPath; // ebx
  HRESULT result; // eax
  WCHAR SubKey[80]; // [rsp+20h] [rbp-B8h] BYREF

  CLSIDRegPath = MakeCLSIDRegPath(v0, SubKey);
  if ( CLSIDRegPath >= 0 )
    CLSIDRegPath = RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey);
  result = DMOUnregister(&CLSID_CColorConvertDMO, &DMOCATEGORY_VIDEO_EFFECT);
  if ( CLSIDRegPath < 0 )
    return CLSIDRegPath;
  return result;
}

```

## disassembly

```asm
0x18000eab0  push    rbx
0x18000eab2  sub     rsp, 0D0h
0x18000eab9  mov     rax, cs:__security_cookie
0x18000eac0  xor     rax, rsp
0x18000eac3  mov     [rsp+0D8h+var_18], rax
0x18000eacb  lea     rdx, [rsp+0D8h+SubKey]; unsigned __int16 *
0x18000ead0  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18000ead5  mov     ebx, eax
0x18000ead7  test    eax, eax
0x18000ead9  js      short loc_18000EAEF
0x18000eadb  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x18000eae0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000eae7  call    cs:__imp_RegDeleteTreeW
0x18000eaed  mov     ebx, eax
0x18000eaef  lea     rdx, DMOCATEGORY_VIDEO_EFFECT; guidCategory
0x18000eaf6  lea     rcx, CLSID_CColorConvertDMO; clsidDMO
0x18000eafd  call    cs:__imp_DMOUnregister
0x18000eb03  test    ebx, ebx
0x18000eb05  cmovs   eax, ebx
0x18000eb08  mov     rcx, [rsp+0D8h+var_18]
0x18000eb10  xor     rcx, rsp; StackCookie
0x18000eb13  call    __security_check_cookie
0x18000eb18  add     rsp, 0D0h
0x18000eb1f  pop     rbx
0x18000eb20  retn
```
