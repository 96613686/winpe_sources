# Windows::Internal::StringReference::StringReference(ushort const (&)[28])

- ea: `0x100a0a2e`
- end: `0x100a0a60`
- name: `??$?0$0BM@@StringReference@Internal@Windows@@QAE@AAY0BM@$$CBG@Z`
- size: `50`
- prototype: `void __thiscall(Windows::Internal::StringReference *this, const wchar_t (*)[28])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x100a1d90`
- `0x1013d73a`
- `0x1013d920`

## callees

- `0x100a0a2e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a0a54`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a0a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a0a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a0a3f`

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
0x100a0a2e  mov     edi, edi
0x100a0a30  push    esi
0x100a0a31  mov     esi, this
0x100a0a33  push    esi; string
0x100a0a34  lea     eax, [esi+4]
0x100a0a37  push    eax; hstringHeader
0x100a0a38  push    1Bh; length
0x100a0a3a  push    offset ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x100a0a3f  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100a0a45  test    eax, eax
0x100a0a47  jns     short loc_100A0A5A
0x100a0a49  push    0; lpArguments
0x100a0a4b  push    0; nNumberOfArguments
0x100a0a4d  push    1; dwExceptionFlags
0x100a0a4f  push    0C000000Dh; dwExceptionCode
0x100a0a54  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100a0a5a  mov     eax, esi
0x100a0a5c  pop     esi
0x100a0a5d  retn    4
```
