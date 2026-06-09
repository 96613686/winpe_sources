# DOMNamedNodeMapList::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100aa3a0`
- end: `0x100aa3c0`
- name: `?GetRuntimeClassName@DOMNamedNodeMapList@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(DOMNamedNodeMapList *this, HSTRING__ **runtimeName)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x100aa3d0`
- `0x100aa3e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100aa3b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100aa3b6`

## string_xrefs

- `0x100aa3ab`: `Windows.Data.Xml.Dom.XmlNamedNodeMap`

## pseudocode

```c
HRESULT __stdcall DOMNamedNodeMapList::GetRuntimeClassName(DOMNamedNodeMapList *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Data.Xml.Dom.XmlNamedNodeMap", 0x24u, runtimeName);
}

```

## disassembly

```asm
0x100aa3a0  mov     edi, edi
0x100aa3a2  push    ebp
0x100aa3a3  mov     ebp, esp
0x100aa3a5  mov     eax, [ebp+runtimeName]
0x100aa3a8  push    eax; string
0x100aa3a9  push    24h ; '$'; length
0x100aa3ab  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlNamedNodeMap@@3QBGB; "Windows.Data.Xml.Dom.XmlNamedNodeMap"
0x100aa3b0  mov     dword ptr [eax], 0
0x100aa3b6  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100aa3bc  pop     ebp
0x100aa3bd  retn    8
```
