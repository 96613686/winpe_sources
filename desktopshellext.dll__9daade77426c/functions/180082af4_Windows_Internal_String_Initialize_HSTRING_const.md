# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x180082af4`
- end: `0x180082b3f`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180082f58`

## callees

- `0x180082af4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180082b15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180082b15`

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
0x180082af4  mov     [rsp+arg_8], rbx
0x180082af9  push    rdi
0x180082afa  sub     rsp, 20h
0x180082afe  mov     rax, rdx
0x180082b01  mov     [rsp+28h+newString], 0
0x180082b0a  mov     rbx, rcx
0x180082b0d  lea     rdx, [rsp+28h+newString]; newString
0x180082b12  mov     rcx, [rax]; string
0x180082b15  call    cs:__imp_WindowsDuplicateString
0x180082b1b  mov     edi, eax
0x180082b1d  test    eax, eax
0x180082b1f  js      short loc_180082B32
0x180082b21  mov     rdx, [rsp+28h+newString]
0x180082b26  mov     rcx, [rbx]; string
0x180082b29  mov     [rbx], rdx
0x180082b2c  call    cs:__imp_WindowsDeleteString
0x180082b32  mov     rbx, [rsp+28h+arg_8]
0x180082b37  mov     eax, edi
0x180082b39  add     rsp, 20h
0x180082b3d  pop     rdi
0x180082b3e  retn
```
