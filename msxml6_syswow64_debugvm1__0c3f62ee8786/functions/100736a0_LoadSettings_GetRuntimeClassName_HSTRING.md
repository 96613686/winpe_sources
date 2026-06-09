# LoadSettings::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100736a0`
- end: `0x100736c0`
- name: `?GetRuntimeClassName@LoadSettings@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(LoadSettings *this, HSTRING__ **runtimeName)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100736b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100736b6`

## string_xrefs

- `0x100736ab`: `Windows.Data.Xml.Dom.XmlLoadSettings`

## pseudocode

```c
HRESULT __stdcall LoadSettings::GetRuntimeClassName(LoadSettings *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Data.Xml.Dom.XmlLoadSettings", 0x24u, runtimeName);
}

```

## disassembly

```asm
0x100736a0  mov     edi, edi
0x100736a2  push    ebp
0x100736a3  mov     ebp, esp
0x100736a5  mov     eax, [ebp+runtimeName]
0x100736a8  push    eax; string
0x100736a9  push    24h ; '$'; length
0x100736ab  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlLoadSettings@@3QBGB; "Windows.Data.Xml.Dom.XmlLoadSettings"
0x100736b0  mov     dword ptr [eax], 0
0x100736b6  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100736bc  pop     ebp
0x100736bd  retn    8
```
