# Windows::Internal::StringReference::StringReference(ushort const (&)[9])

- ea: `0x1800b63b8`
- end: `0x1800b63fc`
- name: `??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[9])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b240`

## callees

- `0x1800b63b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b63ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b63ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b63d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b63d4`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[9])
{
  if ( WindowsCreateStringReference(L"rotation", 8u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800b63b8  push    rbx
0x1800b63ba  sub     rsp, 20h
0x1800b63be  mov     rbx, rcx
0x1800b63c1  lea     r8, [rcx+8]; hstringHeader
0x1800b63c5  mov     r9, rcx; string
0x1800b63c8  mov     edx, 8; length
0x1800b63cd  lea     rcx, aRotation; "rotation"
0x1800b63d4  call    cs:__imp_WindowsCreateStringReference
0x1800b63da  test    eax, eax
0x1800b63dc  jns     short loc_1800B63F3
0x1800b63de  xor     r9d, r9d; lpArguments
0x1800b63e1  xor     r8d, r8d; nNumberOfArguments
0x1800b63e4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b63e9  lea     edx, [r9+1]; dwExceptionFlags
0x1800b63ed  call    cs:__imp_RaiseException
0x1800b63f3  mov     rax, rbx
0x1800b63f6  add     rsp, 20h
0x1800b63fa  pop     rbx
0x1800b63fb  retn
```
