# wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)

- ea: `0x180045d9c`
- end: `0x180045ddf`
- name: `??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18005cfbb`

## callees

- `0x180045d9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045dcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045dba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045dc5`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        __int64 a1)
{
  HSTRING *v1; // rdi
  HSTRING v2; // rbp
  HSTRING v3; // rsi
  DWORD LastError; // ebx

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = *(HSTRING **)a1;
    v2 = *(HSTRING *)(a1 + 8);
    v3 = **(HSTRING **)a1;
    if ( v3 )
    {
      LastError = GetLastError();
      WindowsDeleteString(v3);
      SetLastError(LastError);
    }
    *v1 = v2;
  }
}

```

## disassembly

```asm
0x180045d9c  push    rbx
0x180045d9e  push    rbp
0x180045d9f  push    rsi
0x180045da0  push    rdi
0x180045da1  sub     rsp, 28h
0x180045da5  cmp     byte ptr [rcx+10h], 0
0x180045da9  jz      short loc_180045DD6
0x180045dab  mov     rdi, [rcx]
0x180045dae  mov     rbp, [rcx+8]
0x180045db2  mov     rsi, [rdi]
0x180045db5  test    rsi, rsi
0x180045db8  jz      short loc_180045DD3
0x180045dba  call    cs:__imp_GetLastError
0x180045dc0  mov     rcx, rsi; string
0x180045dc3  mov     ebx, eax
0x180045dc5  call    cs:__imp_WindowsDeleteString
0x180045dcb  mov     ecx, ebx; dwErrCode
0x180045dcd  call    cs:__imp_SetLastError
0x180045dd3  mov     [rdi], rbp
0x180045dd6  add     rsp, 28h
0x180045dda  pop     rdi
0x180045ddb  pop     rsi
0x180045ddc  pop     rbp
0x180045ddd  pop     rbx
0x180045dde  retn
```
