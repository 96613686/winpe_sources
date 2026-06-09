# DOMImplementation::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100b0fe0`
- end: `0x100b1000`
- name: `?GetRuntimeClassName@DOMImplementation@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(DOMImplementation *this, HSTRING__ **runtimeName)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100b0ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100b0ff6`

## string_xrefs

- `0x100b0feb`: `Windows.Data.Xml.Dom.XmlDomImplementation`

## pseudocode

```c
HRESULT __stdcall DOMImplementation::GetRuntimeClassName(DOMImplementation *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Data.Xml.Dom.XmlDomImplementation", 0x29u, runtimeName);
}

```

## disassembly

```asm
0x100b0fe0  mov     edi, edi
0x100b0fe2  push    ebp
0x100b0fe3  mov     ebp, esp
0x100b0fe5  mov     eax, [ebp+runtimeName]
0x100b0fe8  push    eax; string
0x100b0fe9  push    29h ; ')'; length
0x100b0feb  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlDomImplementation@@3QBGB; "Windows.Data.Xml.Dom.XmlDomImplementati"...
0x100b0ff0  mov     dword ptr [eax], 0
0x100b0ff6  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100b0ffc  pop     ebp
0x100b0ffd  retn    8
```
