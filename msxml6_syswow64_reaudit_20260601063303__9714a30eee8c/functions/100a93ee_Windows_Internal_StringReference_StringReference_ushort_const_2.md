# Windows::Internal::StringReference::StringReference(ushort const (&)[2])

- ea: `0x100a93ee`
- end: `0x100a9422`
- name: `??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z`
- size: `52`
- prototype: `void __thiscall(Windows::Internal::StringReference *this, const wchar_t (*stringRef)[2])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100abf05`

## callees

- `0x100a93ee`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a9415`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100a9415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a9400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100a9400`

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
0x100a93ee  mov     edi, edi
0x100a93f0  push    ebp
0x100a93f1  mov     ebp, esp
0x100a93f3  push    esi
0x100a93f4  mov     esi, this
0x100a93f6  push    esi; string
0x100a93f7  lea     eax, [esi+4]
0x100a93fa  push    eax; hstringHeader
0x100a93fb  push    1; length
0x100a93fd  push    [ebp+stringRef]; sourceString
0x100a9400  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100a9406  test    eax, eax
0x100a9408  jns     short loc_100A941B
0x100a940a  push    0; lpArguments
0x100a940c  push    0; nNumberOfArguments
0x100a940e  push    1; dwExceptionFlags
0x100a9410  push    0C000000Dh; dwExceptionCode
0x100a9415  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100a941b  mov     eax, esi
0x100a941d  pop     esi
0x100a941e  pop     ebp
0x100a941f  retn    4
```
