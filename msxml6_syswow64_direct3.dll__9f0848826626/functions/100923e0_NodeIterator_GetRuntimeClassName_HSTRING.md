# NodeIterator::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100923e0`
- end: `0x10092400`
- name: `?GetRuntimeClassName@NodeIterator@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(NodeIterator *this, HSTRING__ **runtimeName)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100923f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100923f6`

## string_xrefs

- `0x100923eb`: `Windows.Foundation.Collections.IIterator`1<Windows.Data.Xml.Dom.IXmlNode>`

## pseudocode

```c
HRESULT __stdcall NodeIterator::GetRuntimeClassName(NodeIterator *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IIterator`1<Windows.Data.Xml.Dom.IXmlNode>",
           0x49u,
           runtimeName);
}

```

## disassembly

```asm
0x100923e0  mov     edi, edi
0x100923e2  push    ebp
0x100923e3  mov     ebp, esp
0x100923e5  mov     eax, [ebp+runtimeName]
0x100923e8  push    eax; string
0x100923e9  push    49h ; 'I'; length
0x100923eb  push    offset aWindowsFoundat_0; "Windows.Foundation.Collections.IIterato"...
0x100923f0  mov     dword ptr [eax], 0
0x100923f6  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100923fc  pop     ebp
0x100923fd  retn    8
```
