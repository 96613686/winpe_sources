# Windows::Internal::StringReference::StringReference(ushort const *,uint)

- ea: `0x18000ae38`
- end: `0x18000ae7b`
- name: `??0StringReference@Internal@Windows@@QEAA@PEBGI@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString, UINT32 length)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180027260`
- `0x18002cfb4`
- `0x18002d49c`

## callees

- `0x18000ae38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ae6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ae6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ae53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ae53`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        PCWSTR sourceString,
        UINT32 length)
{
  if ( WindowsCreateStringReference(sourceString, length, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18000ae38  push    rbx
0x18000ae3a  sub     rsp, 20h
0x18000ae3e  mov     eax, r8d
0x18000ae41  mov     r10, rdx
0x18000ae44  lea     r8, [rcx+8]; hstringHeader
0x18000ae48  mov     rbx, rcx
0x18000ae4b  mov     r9, rcx; string
0x18000ae4e  mov     edx, eax; length
0x18000ae50  mov     rcx, r10; sourceString
0x18000ae53  call    cs:__imp_WindowsCreateStringReference
0x18000ae59  test    eax, eax
0x18000ae5b  jns     short loc_18000AE72
0x18000ae5d  xor     r9d, r9d; lpArguments
0x18000ae60  xor     r8d, r8d; nNumberOfArguments
0x18000ae63  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000ae68  lea     edx, [r9+1]; dwExceptionFlags
0x18000ae6c  call    cs:__imp_RaiseException
0x18000ae72  mov     rax, rbx
0x18000ae75  add     rsp, 20h
0x18000ae79  pop     rbx
0x18000ae7a  retn
```
