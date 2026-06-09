# DllUnregisterServer

- ea: `0x18000fc50`
- end: `0x18000fcc1`
- name: `DllUnregisterServer`
- size: `113`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000e3a0`
- `0x18000fc50`
- `0x18000fdd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000fc87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000fc87`
- `msdmo!DMOUnregister` at `0x18000fc9d`
- `msdmo!DMOUnregister` at `0x18000fc9d`

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
  result = DMOUnregister(&CLSID_CMP3DecMediaObject, &DMOCATEGORY_AUDIO_DECODER);
  if ( CLSIDRegPath < 0 )
    return CLSIDRegPath;
  return result;
}

```

## disassembly

```asm
0x18000fc50  push    rbx
0x18000fc52  sub     rsp, 0D0h
0x18000fc59  mov     rax, cs:__security_cookie
0x18000fc60  xor     rax, rsp
0x18000fc63  mov     [rsp+0D8h+var_18], rax
0x18000fc6b  lea     rdx, [rsp+0D8h+SubKey]; unsigned __int16 *
0x18000fc70  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18000fc75  mov     ebx, eax
0x18000fc77  test    eax, eax
0x18000fc79  js      short loc_18000FC8F
0x18000fc7b  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x18000fc80  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000fc87  call    cs:__imp_RegDeleteTreeW
0x18000fc8d  mov     ebx, eax
0x18000fc8f  lea     rdx, DMOCATEGORY_AUDIO_DECODER; guidCategory
0x18000fc96  lea     rcx, CLSID_CMP3DecMediaObject; clsidDMO
0x18000fc9d  call    cs:__imp_DMOUnregister
0x18000fca3  test    ebx, ebx
0x18000fca5  cmovs   eax, ebx
0x18000fca8  mov     rcx, [rsp+0D8h+var_18]
0x18000fcb0  xor     rcx, rsp; StackCookie
0x18000fcb3  call    __security_check_cookie
0x18000fcb8  add     rsp, 0D0h
0x18000fcbf  pop     rbx
0x18000fcc0  retn
```
