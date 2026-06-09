# wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)

- ea: `0x180066474`
- end: `0x1800664c1`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800268d0`
- `0x1800b2fc4`
- `0x1800b3404`

## callees

- `0x1800432a0`
- `0x18005671c`
- `0x180066474`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006649e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006649e`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        HSTRING *a1,
        HSTRING a2)
{
  HSTRING v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    WindowsDeleteString(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180066474  mov     [rsp+arg_8], rbx
0x180066479  mov     [rsp+arg_10], rsi
0x18006647e  push    rdi
0x18006647f  sub     rsp, 20h
0x180066483  mov     rdi, [rcx]
0x180066486  mov     rsi, rdx
0x180066489  mov     rbx, rcx
0x18006648c  test    rdi, rdi
0x18006648f  jz      short loc_1800664AE
0x180066491  lea     rcx, [rsp+28h+arg_0]; this
0x180066496  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006649b  mov     rcx, rdi; string
0x18006649e  call    cs:__imp_WindowsDeleteString
0x1800664a4  lea     rcx, [rsp+28h+arg_0]; this
0x1800664a9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800664ae  mov     [rbx], rsi
0x1800664b1  mov     rbx, [rsp+28h+arg_8]
0x1800664b6  mov     rsi, [rsp+28h+arg_10]
0x1800664bb  add     rsp, 20h
0x1800664bf  pop     rdi
0x1800664c0  retn
```
