# DOMDocumentWrapper::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x10092250`
- end: `0x10092270`
- name: `?GetRuntimeClassName@DOMDocumentWrapper@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(DOMDocumentWrapper *this, HSTRING__ **runtimeName)`
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x10092280`
- `0x10092290`
- `0x100922a0`
- `0x100922b0`
- `0x100922c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10092266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10092266`

## string_xrefs

- `0x1009225b`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
HRESULT __stdcall DOMDocumentWrapper::GetRuntimeClassName(DOMDocumentWrapper *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, runtimeName);
}

```

## disassembly

```asm
0x10092250  mov     edi, edi
0x10092252  push    ebp
0x10092253  mov     ebp, esp
0x10092255  mov     eax, [ebp+runtimeName]
0x10092258  push    eax; string
0x10092259  push    20h ; ' '; length
0x1009225b  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x10092260  mov     dword ptr [eax], 0
0x10092266  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x1009226c  pop     ebp
0x1009226d  retn    8
```
