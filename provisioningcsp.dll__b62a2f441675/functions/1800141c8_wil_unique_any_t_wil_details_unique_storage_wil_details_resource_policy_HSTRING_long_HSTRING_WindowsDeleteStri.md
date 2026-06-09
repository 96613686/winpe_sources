# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator&(void)

- ea: `0x1800141c8`
- end: `0x180014228`
- name: `??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180014f14`

## callees

- `0x1800141c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014201`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800141f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800141f3`

## pseudocode

```c
HSTRING *__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator&(
        HSTRING *a1)
{
  HSTRING v1; // rsi
  DWORD LastError; // ebx
  HSTRING *result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v1);
    SetLastError(LastError);
  }
  result = a1;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800141c8  mov     [rsp+arg_0], rbx
0x1800141cd  mov     [rsp+arg_8], rsi
0x1800141d2  push    rdi
0x1800141d3  sub     rsp, 20h
0x1800141d7  mov     rsi, [rcx]
0x1800141da  mov     rdi, rcx
0x1800141dd  test    rsi, rsi
0x1800141e0  jz      short loc_18001420D
0x1800141e2  call    cs:__imp_GetLastError
0x1800141e9  nop     dword ptr [rax+rax+00h]
0x1800141ee  mov     rcx, rsi; string
0x1800141f1  mov     ebx, eax
0x1800141f3  call    cs:__imp_WindowsDeleteString
0x1800141fa  nop     dword ptr [rax+rax+00h]
0x1800141ff  mov     ecx, ebx; dwErrCode
0x180014201  call    cs:__imp_SetLastError
0x180014208  nop     dword ptr [rax+rax+00h]
0x18001420d  mov     rbx, [rsp+28h+arg_0]
0x180014212  mov     rax, rdi
0x180014215  mov     rsi, [rsp+28h+arg_8]
0x18001421a  mov     qword ptr [rdi], 0
0x180014221  add     rsp, 20h
0x180014225  pop     rdi
0x180014226  retn
```
