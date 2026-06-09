# Windows::Internal::StringReference::StringReference(ushort const (&)[28])

- ea: `0x100a096e`
- end: `0x100a09a0`
- name: `??$?0$0BM@@StringReference@Internal@Windows@@QAE@AAY0BM@$$CBG@Z`
- size: `50`
- prototype: `void __thiscall(Windows::Internal::StringReference *this, const wchar_t (*)[28])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x100a1ca0`
- `0x1013d62a`
- `0x1013d810`

## callees

- `0x100a096e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a0994`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a0994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a097f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a097f`

## pseudocode

```c
void __thiscall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[28])
{
  if ( WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x100a096e  mov     edi, edi
0x100a0970  push    esi
0x100a0971  mov     esi, this
0x100a0973  push    esi; string
0x100a0974  lea     eax, [esi+4]
0x100a0977  push    eax; hstringHeader
0x100a0978  push    1Bh; length
0x100a097a  push    offset ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x100a097f  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100a0985  test    eax, eax
0x100a0987  jns     short loc_100A099A
0x100a0989  push    0; lpArguments
0x100a098b  push    0; nNumberOfArguments
0x100a098d  push    1; dwExceptionFlags
0x100a098f  push    0C000000Dh; dwExceptionCode
0x100a0994  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100a099a  mov     eax, esi
0x100a099c  pop     esi
0x100a099d  retn    4
```
