# Windows::Internal::String::~String(void)

- ea: `0x180058a30`
- end: `0x180058a47`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180061470`
- `0x1800614f8`
- `0x180061fe0`
- `0x180062d00`
- `0x1800678bc`
- `0x1800678c8`
- `0x18006e0f9`

## callees

- `0x180058a30`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058a3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058a3c`

## pseudocode

```c
void __fastcall Windows::Internal::String::~String(
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > *this)
{
  HSTRING__ *m_ptr; // rcx

  m_ptr = this->m_ptr;
  if ( m_ptr )
    WindowsDeleteString(m_ptr);
}

```

## disassembly

```asm
0x180058a30  sub     rsp, 28h
0x180058a34  mov     this, [this]; string
0x180058a37  test    this, this
0x180058a3a  jz      short loc_180058A42
0x180058a3c  call    cs:__imp_WindowsDeleteString
0x180058a42  add     rsp, 28h
0x180058a46  retn
```
