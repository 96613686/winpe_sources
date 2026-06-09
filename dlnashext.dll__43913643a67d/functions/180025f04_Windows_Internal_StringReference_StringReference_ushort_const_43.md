# Windows::Internal::StringReference::StringReference(ushort const (&)[43])

- ea: `0x180025f04`
- end: `0x180025f48`
- name: `??$?0$0CL@@StringReference@Internal@Windows@@QEAA@AEAY0CL@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[43])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180027260`

## callees

- `0x180025f04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025f39`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025f39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025f20`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[43])
{
  if ( WindowsCreateStringReference(
         L"Windows.Foundation.Collections.PropertySet",
         0x2Au,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180025f04  push    rbx
0x180025f06  sub     rsp, 20h
0x180025f0a  mov     rbx, rcx
0x180025f0d  lea     r8, [rcx+8]; hstringHeader
0x180025f11  mov     r9, rcx; string
0x180025f14  mov     edx, 2Ah ; '*'; length
0x180025f19  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180025f20  call    cs:__imp_WindowsCreateStringReference
0x180025f26  test    eax, eax
0x180025f28  jns     short loc_180025F3F
0x180025f2a  xor     r9d, r9d; lpArguments
0x180025f2d  xor     r8d, r8d; nNumberOfArguments
0x180025f30  mov     ecx, 0C000000Dh; dwExceptionCode
0x180025f35  lea     edx, [r9+1]; dwExceptionFlags
0x180025f39  call    cs:__imp_RaiseException
0x180025f3f  mov     rax, rbx
0x180025f42  add     rsp, 20h
0x180025f46  pop     rbx
0x180025f47  retn
```
