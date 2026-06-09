# Windows::Internal::StringReference::StringReference(ushort const (&)[15])

- ea: `0x18002c370`
- end: `0x18002c3b4`
- name: `??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[15])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002cc70`

## callees

- `0x18002c370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c3a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c3a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c38c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c38c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[15])
{
  if ( WindowsCreateStringReference(L"DLNA.ORG_FLAGS", 0xEu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002c370  push    rbx
0x18002c372  sub     rsp, 20h
0x18002c376  mov     rbx, rcx
0x18002c379  lea     r8, [rcx+8]; hstringHeader
0x18002c37d  mov     r9, rcx; string
0x18002c380  mov     edx, 0Eh; length
0x18002c385  lea     rcx, aDlnaOrgFlags; "DLNA.ORG_FLAGS"
0x18002c38c  call    cs:__imp_WindowsCreateStringReference
0x18002c392  test    eax, eax
0x18002c394  jns     short loc_18002C3AB
0x18002c396  xor     r9d, r9d; lpArguments
0x18002c399  xor     r8d, r8d; nNumberOfArguments
0x18002c39c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c3a1  lea     edx, [r9+1]; dwExceptionFlags
0x18002c3a5  call    cs:__imp_RaiseException
0x18002c3ab  mov     rax, rbx
0x18002c3ae  add     rsp, 20h
0x18002c3b2  pop     rbx
0x18002c3b3  retn
```
