# QuerySelection::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x10092390`
- end: `0x100923b0`
- name: `?GetRuntimeClassName@QuerySelection@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(QuerySelection *this, HSTRING__ **runtimeName)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x100923c0`
- `0x100923d0`
- `0x100aa390`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100923a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100923a6`

## string_xrefs

- `0x1009239b`: `Windows.Data.Xml.Dom.XmlNodeList`

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
0x10092390  mov     edi, edi
0x10092392  push    ebp
0x10092393  mov     ebp, esp
0x10092395  mov     eax, [ebp+runtimeName]
0x10092398  push    eax; string
0x10092399  push    20h ; ' '; length
0x1009239b  push    offset ?RuntimeClass_Windows_Data_Xml_Dom_XmlNodeList@@3QBGB; "Windows.Data.Xml.Dom.XmlNodeList"
0x100923a0  mov     dword ptr [eax], 0
0x100923a6  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100923ac  pop     ebp
0x100923ad  retn    8
```
