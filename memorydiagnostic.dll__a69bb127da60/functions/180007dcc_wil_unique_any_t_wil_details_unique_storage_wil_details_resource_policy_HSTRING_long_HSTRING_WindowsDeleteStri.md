# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)

- ea: `0x180007dcc`
- end: `0x180007de3`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `HRESULT __fastcall(HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180021308`

## callees

- `0x180007dcc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007dd8`

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
0x180007dcc  sub     rsp, 28h
0x180007dd0  mov     rcx, [rcx]; string
0x180007dd3  test    rcx, rcx
0x180007dd6  jz      short loc_180007DDE
0x180007dd8  call    cs:__imp_WindowsDeleteString
0x180007dde  add     rsp, 28h
0x180007de2  retn
```
