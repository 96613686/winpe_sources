# XsltProcessorImpl::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x10073700`
- end: `0x10073720`
- name: `?GetRuntimeClassName@XsltProcessorImpl@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(XsltProcessorImpl *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x10073730`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10073716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x10073716`

## string_xrefs

- `0x1007370b`: `Windows.Data.Xml.Xsl.XsltProcessor`

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
0x10073700  mov     edi, edi
0x10073702  push    ebp
0x10073703  mov     ebp, esp
0x10073705  mov     eax, [ebp+runtimeName]
0x10073708  push    eax; string
0x10073709  push    22h ; '"'; length
0x1007370b  push    offset ?RuntimeClass_Windows_Data_Xml_Xsl_XsltProcessor@@3QBGB; "Windows.Data.Xml.Xsl.XsltProcessor"
0x10073710  mov     dword ptr [eax], 0
0x10073716  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x1007371c  pop     ebp
0x1007371d  retn    8
```
