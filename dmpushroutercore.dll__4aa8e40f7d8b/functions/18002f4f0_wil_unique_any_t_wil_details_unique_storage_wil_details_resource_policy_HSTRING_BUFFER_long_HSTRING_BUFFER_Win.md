# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>>(void)

- ea: `0x18002f4f0`
- end: `0x18002f507`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800399ac`
- `0x1800399d0`

## callees

- `0x18002f4f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002f4fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002f4fc`

## pseudocode

```c
HRESULT __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>>(
        HSTRING_BUFFER *a1)
{
  HSTRING_BUFFER v1; // rcx
  HRESULT result; // eax

  v1 = *a1;
  if ( v1 )
    return WindowsDeleteStringBuffer(v1);
  return result;
}

```

## disassembly

```asm
0x18002f4f0  sub     rsp, 28h
0x18002f4f4  mov     rcx, [rcx]; bufferHandle
0x18002f4f7  test    rcx, rcx
0x18002f4fa  jz      short loc_18002F502
0x18002f4fc  call    cs:__imp_WindowsDeleteStringBuffer
0x18002f502  add     rsp, 28h
0x18002f506  retn
```
