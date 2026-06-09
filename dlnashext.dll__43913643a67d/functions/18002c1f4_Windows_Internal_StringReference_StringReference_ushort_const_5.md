# Windows::Internal::StringReference::StringReference(ushort const (&)[5])

- ea: `0x18002c1f4`
- end: `0x18002c238`
- name: `??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[5])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002cab8`

## callees

- `0x18002c1f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c229`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c210`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[5])
{
  if ( WindowsCreateStringReference(L"role", 4u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002c1f4  push    rbx
0x18002c1f6  sub     rsp, 20h
0x18002c1fa  mov     rbx, rcx
0x18002c1fd  lea     r8, [rcx+8]; hstringHeader
0x18002c201  mov     r9, rcx; string
0x18002c204  mov     edx, 4; length
0x18002c209  lea     rcx, aRole; "role"
0x18002c210  call    cs:__imp_WindowsCreateStringReference
0x18002c216  test    eax, eax
0x18002c218  jns     short loc_18002C22F
0x18002c21a  xor     r9d, r9d; lpArguments
0x18002c21d  xor     r8d, r8d; nNumberOfArguments
0x18002c220  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c225  lea     edx, [r9+1]; dwExceptionFlags
0x18002c229  call    cs:__imp_RaiseException
0x18002c22f  mov     rax, rbx
0x18002c232  add     rsp, 20h
0x18002c236  pop     rbx
0x18002c237  retn
```
