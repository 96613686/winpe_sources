# NodeIterator::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x10092320`
- end: `0x10092340`
- name: `?GetRuntimeClassName@NodeIterator@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(NodeIterator *this, HSTRING__ **runtimeName)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10092336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10092336`

## string_xrefs

- `0x1009232b`: `Windows.Foundation.Collections.IIterator`1<Windows.Data.Xml.Dom.IXmlNode>`

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
0x10092320  mov     edi, edi
0x10092322  push    ebp
0x10092323  mov     ebp, esp
0x10092325  mov     eax, [ebp+runtimeName]
0x10092328  push    eax; string
0x10092329  push    49h ; 'I'; length
0x1009232b  push    offset aWindowsFoundat_0; "Windows.Foundation.Collections.IIterato"...
0x10092330  mov     dword ptr [eax], 0
0x10092336  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x1009233c  pop     ebp
0x1009233d  retn    8
```
