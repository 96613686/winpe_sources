# XsltProcessorImpl::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100736d0`
- end: `0x100736f0`
- name: `?GetRuntimeClassName@XsltProcessorImpl@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(XsltProcessorImpl *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x10073700`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100736e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100736e6`

## string_xrefs

- `0x100736db`: `Windows.Data.Xml.Xsl.XsltProcessor`

## pseudocode

```c
HRESULT __stdcall XsltProcessorImpl::GetRuntimeClassName(XsltProcessorImpl *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Data.Xml.Xsl.XsltProcessor", 0x22u, runtimeName);
}

```

## disassembly

```asm
0x100736d0  mov     edi, edi
0x100736d2  push    ebp
0x100736d3  mov     ebp, esp
0x100736d5  mov     eax, [ebp+runtimeName]
0x100736d8  push    eax; string
0x100736d9  push    22h ; '"'; length
0x100736db  push    offset ?RuntimeClass_Windows_Data_Xml_Xsl_XsltProcessor@@3QBGB; "Windows.Data.Xml.Xsl.XsltProcessor"
0x100736e0  mov     dword ptr [eax], 0
0x100736e6  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100736ec  pop     ebp
0x100736ed  retn    8
```
