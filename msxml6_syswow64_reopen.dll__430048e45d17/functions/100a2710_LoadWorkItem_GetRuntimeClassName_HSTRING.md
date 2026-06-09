# LoadWorkItem::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x100a2710`
- end: `0x100a2730`
- name: `?GetRuntimeClassName@LoadWorkItem@@UAGJPAPAUHSTRING__@@@Z`
- size: `32`
- prototype: `HRESULT __stdcall(LoadWorkItem *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x100a2740`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100a2726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x100a2726`

## string_xrefs

- `0x100a271b`: `Windows.Foundation.IAsyncOperation`1<Windows.Data.Xml.Dom.XmlDocument>`

## pseudocode

```c
HRESULT __stdcall LoadWorkItem::GetRuntimeClassName(LoadWorkItem *this, HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(
           L"Windows.Foundation.IAsyncOperation`1<Windows.Data.Xml.Dom.XmlDocument>",
           0x46u,
           runtimeName);
}

```

## disassembly

```asm
0x100a2710  mov     edi, edi
0x100a2712  push    ebp
0x100a2713  mov     ebp, esp
0x100a2715  mov     eax, [ebp+runtimeName]
0x100a2718  push    eax; string
0x100a2719  push    46h ; 'F'; length
0x100a271b  push    offset aWindowsFoundat; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x100a2720  mov     dword ptr [eax], 0
0x100a2726  call    ds:__imp__WindowsCreateString@12; WindowsCreateString(x,x,x)
0x100a272c  pop     ebp
0x100a272d  retn    8
```
