# Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)

- ea: `0x180022b74`
- end: `0x180022b9a`
- name: `?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z`
- size: `38`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, const struct Windows::Internal::String *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007b44`
- `0x18002cfb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180022b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180022b8b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::CompareOrdinal(HSTRING *this, HSTRING *a2)
{
  HSTRING v2; // rdx
  HSTRING v3; // rcx
  INT32 result; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a2;
  v3 = *this;
  result = 0;
  WindowsCompareStringOrdinal(v3, v2, &result);
  return (unsigned int)result;
}

```

## disassembly

```asm
0x180022b74  sub     rsp, 28h
0x180022b78  mov     rdx, [rdx]; string2
0x180022b7b  lea     r8, [rsp+28h+result]; result
0x180022b80  mov     rcx, [rcx]; string1
0x180022b83  mov     [rsp+28h+result], 0
0x180022b8b  call    cs:__imp_WindowsCompareStringOrdinal
0x180022b91  mov     eax, [rsp+28h+result]
0x180022b95  add     rsp, 28h
0x180022b99  retn
```
