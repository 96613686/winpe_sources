# QuerySelection::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100922d0`
- end: `0x100922f0`
- name: `?GetRuntimeClassName@QuerySelection@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(QuerySelection *this, HSTRING__ **runtimeName)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x10092300`
- `0x10092310`
- `0x100aa280`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100922e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100922e6`

## string_xrefs

- `0x100922db`: `Windows.Data.Xml.Dom.XmlNodeList`

## pseudocode

```c
HRESULT __stdcall QuerySelection::GetRuntimeClassName(QuerySelection *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Data.Xml.Dom.XmlNodeList", 0x20u, runtimeName);
}

```

## disassembly

```asm
0x100922d0  mov     edi, edi
0x100922d2  push    ebp
0x100922d3  mov     ebp, esp
0x100922d5  mov     eax, [ebp+runtimeName]
0x100922d8  push    eax; string
0x100922d9  push    20h ; ' '; length
0x100922db  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlNodeList@@3QBGB; "Windows.Data.Xml.Dom.XmlNodeList"
0x100922e0  mov     dword ptr [eax], 0
0x100922e6  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100922ec  pop     ebp
0x100922ed  retn    8
```
