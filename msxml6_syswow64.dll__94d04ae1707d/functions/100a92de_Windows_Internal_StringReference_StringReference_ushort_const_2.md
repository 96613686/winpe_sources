# Windows::Internal::StringReference::StringReference(ushort const (&)[2])

- ea: `0x100a92de`
- end: `0x100a9312`
- name: `??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z`
- size: `52`
- prototype: `void __thiscall(Windows::Internal::StringReference *this, const wchar_t (*stringRef)[2])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100abdf5`

## callees

- `0x100a92de`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a9305`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a9305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a92f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a92f0`

## pseudocode

```c
void __thiscall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*stringRef)[2])
{
  if ( WindowsCreateStringReference((PCWSTR)stringRef, 1u, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x100a92de  mov     edi, edi
0x100a92e0  push    ebp
0x100a92e1  mov     ebp, esp
0x100a92e3  push    esi
0x100a92e4  mov     esi, this
0x100a92e6  push    esi; string
0x100a92e7  lea     eax, [esi+4]
0x100a92ea  push    eax; hstringHeader
0x100a92eb  push    1; length
0x100a92ed  push    [ebp+stringRef]; sourceString
0x100a92f0  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100a92f6  test    eax, eax
0x100a92f8  jns     short loc_100A930B
0x100a92fa  push    0; lpArguments
0x100a92fc  push    0; nNumberOfArguments
0x100a92fe  push    1; dwExceptionFlags
0x100a9300  push    0C000000Dh; dwExceptionCode
0x100a9305  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100a930b  mov     eax, esi
0x100a930d  pop     esi
0x100a930e  pop     ebp
0x100a930f  retn    4
```
