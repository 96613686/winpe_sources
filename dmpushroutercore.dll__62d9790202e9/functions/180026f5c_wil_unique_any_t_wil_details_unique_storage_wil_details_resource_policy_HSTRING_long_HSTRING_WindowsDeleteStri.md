# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)

- ea: `0x180026f5c`
- end: `0x180026f73`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `HRESULT __fastcall(HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800399be`
- `0x1800399e2`

## callees

- `0x180026f5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026f68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026f68`

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
0x180026f5c  sub     rsp, 28h
0x180026f60  mov     rcx, [rcx]; string
0x180026f63  test    rcx, rcx
0x180026f66  jz      short loc_180026F6E
0x180026f68  call    cs:__imp_WindowsDeleteString
0x180026f6e  add     rsp, 28h
0x180026f72  retn
```
