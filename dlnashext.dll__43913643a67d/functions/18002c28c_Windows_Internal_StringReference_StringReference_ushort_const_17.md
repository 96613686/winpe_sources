# Windows::Internal::StringReference::StringReference(ushort const (&)[17])

- ea: `0x18002c28c`
- end: `0x18002c2cf`
- name: `??$?0$0BB@@StringReference@Internal@Windows@@QEAA@AEAY0BB@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002cc70`
- `0x18002e13c`

## callees

- `0x18002c28c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c2c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c2c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c2a7`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x10u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002c28c  push    rbx
0x18002c28e  sub     rsp, 20h
0x18002c292  mov     rax, rdx
0x18002c295  lea     r8, [rcx+8]; hstringHeader
0x18002c299  mov     rbx, rcx
0x18002c29c  mov     r9, rcx; string
0x18002c29f  mov     rcx, rax; sourceString
0x18002c2a2  mov     edx, 10h; length
0x18002c2a7  call    cs:__imp_WindowsCreateStringReference
0x18002c2ad  test    eax, eax
0x18002c2af  jns     short loc_18002C2C6
0x18002c2b1  xor     r9d, r9d; lpArguments
0x18002c2b4  xor     r8d, r8d; nNumberOfArguments
0x18002c2b7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c2bc  lea     edx, [r9+1]; dwExceptionFlags
0x18002c2c0  call    cs:__imp_RaiseException
0x18002c2c6  mov     rax, rbx
0x18002c2c9  add     rsp, 20h
0x18002c2cd  pop     rbx
0x18002c2ce  retn
```
