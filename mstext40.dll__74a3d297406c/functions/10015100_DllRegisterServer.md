# DllRegisterServer()

- ea: `0x10015100`
- end: `0x100151d2`
- name: `_DllRegisterServer@0`
- size: `210`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10008ea0`
- `0x1000a000`
- `0x1000a010`
- `0x10015100`
- `0x10015240`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x10015124`
- `KERNEL32!GetModuleFileNameA` at `0x10015124`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v1; // edi
  int v2; // esi
  CHAR Filename[264]; // [esp+0h] [ebp-318h] BYREF
  WCHAR WideCharStr[262]; // [esp+108h] [ebp-210h] BYREF

  if ( !GetModuleFileNameA(hModule, Filename, 0x105u) )
    return -2147467259;
  v1 = SetupConfigurationSpec(0);
  if ( !v1 || ErrMultiByteToWideN(Filename, WideCharStr, 0x105u) )
    return -2147467259;
  v2 = ConfigRegister(L"Software\\Microsoft\\Jet\\4.0", off_1003E460, 3, v1, WideCharStr);
  ConfigRelease(v1);
  return v2 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x10015100  sub     esp, 318h
0x10015106  mov     eax, ___security_cookie
0x1001510b  xor     eax, esp
0x1001510d  mov     [esp+318h+var_4], eax
0x10015114  push    105h; nSize
0x10015119  lea     eax, [esp+31Ch+Filename]
0x1001511d  push    eax; lpFilename
0x1001511e  push    hModule; hModule
0x10015124  call    ds:__imp__GetModuleFileNameA@12; GetModuleFileNameA(x,x,x)
0x1001512a  test    eax, eax
0x1001512c  jnz     short loc_10015148
0x1001512e  mov     eax, 80004005h
0x10015133  mov     ecx, [esp+318h+var_4]
0x1001513a  xor     ecx, esp; StackCookie
0x1001513c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10015141  add     esp, 318h
0x10015147  retn
0x10015148  push    edi
0x10015149  push    0
0x1001514b  call    SetupConfigurationSpec
0x10015150  mov     edi, eax
0x10015152  test    edi, edi
0x10015154  jz      short loc_10015171
0x10015156  push    105h; cchMax
0x1001515b  lea     eax, [esp+320h+WideCharStr]
0x10015162  push    eax; lpWideCharStr
0x10015163  lea     eax, [esp+324h+Filename]
0x10015167  push    eax; psz
0x10015168  call    _ErrMultiByteToWideN@12; ErrMultiByteToWideN(x,x,x)
0x1001516d  test    eax, eax
0x1001516f  jz      short loc_1001518C
0x10015171  mov     eax, 80004005h
0x10015176  pop     edi
0x10015177  mov     ecx, [esp+318h+var_4]
0x1001517e  xor     ecx, esp; StackCookie
0x10015180  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10015185  add     esp, 318h
0x1001518b  retn
0x1001518c  push    esi
0x1001518d  lea     eax, [esp+320h+WideCharStr]
0x10015194  push    eax
0x10015195  push    edi
0x10015196  push    3
0x10015198  push    offset off_1003E460; "Text"
0x1001519d  push    offset aSoftwareMicros_0; "Software\\Microsoft\\Jet\\4.0"
0x100151a2  call    _ConfigRegister@20; ConfigRegister(x,x,x,x,x)
0x100151a7  push    edi
0x100151a8  mov     esi, eax
0x100151aa  call    _ConfigRelease@4; ConfigRelease(x)
0x100151af  mov     ecx, [esp+320h+var_4]
0x100151b6  neg     esi
0x100151b8  sbb     esi, esi
0x100151ba  and     esi, 80004005h
0x100151c0  mov     eax, esi
0x100151c2  pop     esi
0x100151c3  pop     edi
0x100151c4  xor     ecx, esp; StackCookie
0x100151c6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100151cb  add     esp, 318h
0x100151d1  retn
```
