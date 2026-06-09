# Windows::Internal::StringReference::StringReference(ushort const (&)[28])

- ea: `0x1800eb51c`
- end: `0x1800eb560`
- name: `??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z`
- size: `68`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[28])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ec8f0`
- `0x18015be74`
- `0x18015c110`

## callees

- `0x1800eb51c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eb551`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eb551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eb538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eb538`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[28])
{
  if ( WindowsCreateStringReference(RuntimeClass_Windows_Storage_StorageFile, 0x1Bu, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800eb51c  push    rbx
0x1800eb51e  sub     rsp, 20h
0x1800eb522  mov     rbx, this
0x1800eb525  lea     r8, [this+8]; hstringHeader
0x1800eb529  mov     r9, this; string
0x1800eb52c  mov     edx, 1Bh; length
0x1800eb531  lea     this, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; sourceString
0x1800eb538  call    cs:__imp_WindowsCreateStringReference
0x1800eb53e  test    eax, eax
0x1800eb540  jns     short loc_1800EB557
0x1800eb542  xor     r9d, r9d; lpArguments
0x1800eb545  xor     r8d, r8d; nNumberOfArguments
0x1800eb548  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800eb54d  lea     edx, [r9+1]; dwExceptionFlags
0x1800eb551  call    cs:__imp_RaiseException
0x1800eb557  mov     rax, rbx
0x1800eb55a  add     rsp, 20h
0x1800eb55e  pop     rbx
0x1800eb55f  retn
```
