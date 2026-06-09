# Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)

- ea: `0x1800f1064`
- end: `0x1800f10af`
- name: `?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *this, const Windows::Internal::String *string, Windows::Internal::String *newString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800f3430`

## callees

- `0x1800f1064`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f109c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f109c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800f1085`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800f1085`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Concat(
        Windows::Internal::String *this,
        const Windows::Internal::String *string,
        Windows::Internal::String *newString)
{
  HSTRING__ *hstring; // rdx
  HSTRING__ *v5; // rcx
  HRESULT v6; // edi
  HSTRING__ *v7; // rcx
  HSTRING__ *local; // [rsp+30h] [rbp+8h] BYREF

  hstring = string->_hstring;
  v5 = this->_hstring;
  local = 0;
  v6 = WindowsConcatString(v5, hstring, &local);
  if ( v6 >= 0 )
  {
    v7 = newString->_hstring;
    newString->_hstring = local;
    WindowsDeleteString(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800f1064  mov     [rsp+arg_8], rbx
0x1800f1069  push    rdi
0x1800f106a  sub     rsp, 20h
0x1800f106e  mov     string, [string]; string2
0x1800f1071  mov     rbx, newString
0x1800f1074  mov     this, [this]; string1
0x1800f1077  lea     newString, [rsp+28h+local]; newString
0x1800f107c  mov     [rsp+28h+local], 0
0x1800f1085  call    cs:__imp_WindowsConcatString
0x1800f108b  mov     edi, eax
0x1800f108d  test    eax, eax
0x1800f108f  js      short loc_1800F10A2
0x1800f1091  mov     string, [rsp+28h+local]
0x1800f1096  mov     this, [rbx]; string
0x1800f1099  mov     [rbx], string
0x1800f109c  call    cs:__imp_WindowsDeleteString
0x1800f10a2  mov     rbx, [rsp+28h+arg_8]
0x1800f10a7  mov     eax, edi
0x1800f10a9  add     rsp, 20h
0x1800f10ad  pop     rdi
0x1800f10ae  retn
```
