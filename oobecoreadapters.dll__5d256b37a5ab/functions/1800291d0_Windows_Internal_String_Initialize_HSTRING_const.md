# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x1800291d0`
- end: `0x18002921b`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, HSTRING *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180026a40`
- `0x180026b10`
- `0x180026cd0`
- `0x1800279d0`
- `0x180027af0`
- `0x180027c60`
- `0x18002aff0`
- `0x18002b130`
- `0x180030190`
- `0x180030340`
- `0x1800346f0`
- `0x180034980`
- `0x180037080`
- `0x18004ae30`
- `0x1800687d0`

## callees

- `0x1800291d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800291f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800291f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029208`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(HSTRING *this, HSTRING *a2)
{
  HRESULT v3; // edi
  HSTRING v4; // rcx
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  newString = 0;
  v3 = WindowsDuplicateString(*a2, &newString);
  if ( v3 >= 0 )
  {
    v4 = *this;
    *this = newString;
    WindowsDeleteString(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800291d0  mov     [rsp+arg_8], rbx
0x1800291d5  push    rdi
0x1800291d6  sub     rsp, 20h
0x1800291da  mov     rax, rdx
0x1800291dd  mov     [rsp+28h+newString], 0
0x1800291e6  mov     rbx, rcx
0x1800291e9  lea     rdx, [rsp+28h+newString]; newString
0x1800291ee  mov     rcx, [rax]; string
0x1800291f1  call    cs:__imp_WindowsDuplicateString
0x1800291f7  mov     edi, eax
0x1800291f9  test    eax, eax
0x1800291fb  js      short loc_18002920E
0x1800291fd  mov     rdx, [rsp+28h+newString]
0x180029202  mov     rcx, [rbx]; string
0x180029205  mov     [rbx], rdx
0x180029208  call    cs:__imp_WindowsDeleteString
0x18002920e  mov     rbx, [rsp+28h+arg_8]
0x180029213  mov     eax, edi
0x180029215  add     rsp, 20h
0x180029219  pop     rdi
0x18002921a  retn
```
