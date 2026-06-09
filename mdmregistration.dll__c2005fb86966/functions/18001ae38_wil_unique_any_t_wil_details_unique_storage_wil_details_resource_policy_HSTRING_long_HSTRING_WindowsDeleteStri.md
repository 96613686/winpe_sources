# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)

- ea: `0x18001ae38`
- end: `0x18001ae56`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004bf9b`
- `0x18004c786`

## callees

- `0x18001ae38`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ae44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ae44`

## pseudocode

```c
HRESULT __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(
        HSTRING *a1)
{
  HSTRING v1; // rcx
  HRESULT result; // eax

  v1 = *a1;
  if ( v1 )
    return WindowsDeleteString(v1);
  return result;
}

```

## disassembly

```asm
0x18001ae38  sub     rsp, 28h
0x18001ae3c  mov     rcx, [rcx]; string
0x18001ae3f  test    rcx, rcx
0x18001ae42  jz      short loc_18001AE50
0x18001ae44  call    cs:__imp_WindowsDeleteString
0x18001ae4b  nop     dword ptr [rax+rax+00h]
0x18001ae50  add     rsp, 28h
0x18001ae54  retn
```
