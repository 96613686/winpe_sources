# Windows::Internal::StringReference::CompareOrdinal(Windows::Internal::String const &)

- ea: `0x1800b653c`
- end: `0x1800b6562`
- name: `?CompareOrdinal@StringReference@Internal@Windows@@QEBAHAEBVString@23@@Z`
- size: `38`
- prototype: `__int64 __fastcall(Windows::Internal::StringReference *__hidden this, const struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003b240`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800b6553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800b6553`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StringReference::CompareOrdinal(HSTRING *this, HSTRING *a2)
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
0x1800b653c  sub     rsp, 28h
0x1800b6540  mov     rdx, [rdx]; string2
0x1800b6543  lea     r8, [rsp+28h+result]; result
0x1800b6548  mov     rcx, [rcx]; string1
0x1800b654b  mov     [rsp+28h+result], 0
0x1800b6553  call    cs:__imp_WindowsCompareStringOrdinal
0x1800b6559  mov     eax, [rsp+28h+result]
0x1800b655d  add     rsp, 28h
0x1800b6561  retn
```
