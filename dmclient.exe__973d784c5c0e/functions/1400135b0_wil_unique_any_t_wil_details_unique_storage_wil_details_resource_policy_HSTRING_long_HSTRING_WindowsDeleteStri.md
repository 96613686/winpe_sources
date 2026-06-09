# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)

- ea: `0x1400135b0`
- end: `0x1400135ce`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140019b50`

## callees

- `0x1400135b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400135bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400135bc`

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
0x1400135b0  sub     rsp, 28h
0x1400135b4  mov     rcx, [rcx]; string
0x1400135b7  test    rcx, rcx
0x1400135ba  jz      short loc_1400135C8
0x1400135bc  call    cs:__imp_WindowsDeleteString
0x1400135c3  nop     dword ptr [rax+rax+00h]
0x1400135c8  add     rsp, 28h
0x1400135cc  retn
```
