# DOMDocumentWrapper::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x10092310`
- end: `0x10092330`
- name: `?GetRuntimeClassName@DOMDocumentWrapper@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(DOMDocumentWrapper *this, HSTRING__ **runtimeName)`
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x10092340`
- `0x10092350`
- `0x10092360`
- `0x10092370`
- `0x10092380`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10092326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10092326`

## string_xrefs

- `0x1009231b`: `Windows.Data.Xml.Dom.XmlDocument`

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
0x10092310  mov     edi, edi
0x10092312  push    ebp
0x10092313  mov     ebp, esp
0x10092315  mov     eax, [ebp+runtimeName]
0x10092318  push    eax; string
0x10092319  push    20h ; ' '; length
0x1009231b  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x10092320  mov     dword ptr [eax], 0
0x10092326  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x1009232c  pop     ebp
0x1009232d  retn    8
```
