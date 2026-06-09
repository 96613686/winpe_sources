# Windows::Internal::StringReference::StringReference(ushort const (&)[4])

- ea: `0x18002c1a8`
- end: `0x18002c1ec`
- name: `??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[4])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c844`
- `0x18002f378`

## callees

- `0x18002c1a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c1dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c1dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c1c4`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[4])
{
  if ( WindowsCreateStringReference(L" \\\\", 3u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002c1a8  push    rbx
0x18002c1aa  sub     rsp, 20h
0x18002c1ae  mov     rbx, rcx
0x18002c1b1  lea     r8, [rcx+8]; hstringHeader
0x18002c1b5  mov     r9, rcx; string
0x18002c1b8  mov     edx, 3; length
0x18002c1bd  lea     rcx, asc_18003E980; " \\\\"
0x18002c1c4  call    cs:__imp_WindowsCreateStringReference
0x18002c1ca  test    eax, eax
0x18002c1cc  jns     short loc_18002C1E3
0x18002c1ce  xor     r9d, r9d; lpArguments
0x18002c1d1  xor     r8d, r8d; nNumberOfArguments
0x18002c1d4  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c1d9  lea     edx, [r9+1]; dwExceptionFlags
0x18002c1dd  call    cs:__imp_RaiseException
0x18002c1e3  mov     rax, rbx
0x18002c1e6  add     rsp, 20h
0x18002c1ea  pop     rbx
0x18002c1eb  retn
```
