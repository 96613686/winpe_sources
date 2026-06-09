# Windows::Internal::StringReference::StringReference(ushort const (&)[1])

- ea: `0x180038c64`
- end: `0x180038ca5`
- name: `??$?0$00@StringReference@Internal@Windows@@QEAA@AEAY00$$CBG@Z`
- size: `65`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[1])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180039ef8`

## callees

- `0x180038c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038c96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038c96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038c7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038c7d`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[1])
{
  if ( WindowsCreateStringReference(&sourceString, 0, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180038c64  push    rbx
0x180038c66  sub     rsp, 20h
0x180038c6a  mov     rbx, rcx
0x180038c6d  lea     r8, [rcx+8]; hstringHeader
0x180038c71  mov     r9, rcx; string
0x180038c74  xor     edx, edx; length
0x180038c76  lea     rcx, sourceString; sourceString
0x180038c7d  call    cs:__imp_WindowsCreateStringReference
0x180038c83  test    eax, eax
0x180038c85  jns     short loc_180038C9C
0x180038c87  xor     r9d, r9d; lpArguments
0x180038c8a  xor     r8d, r8d; nNumberOfArguments
0x180038c8d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180038c92  lea     edx, [r9+1]; dwExceptionFlags
0x180038c96  call    cs:__imp_RaiseException
0x180038c9c  mov     rax, rbx
0x180038c9f  add     rsp, 20h
0x180038ca3  pop     rbx
0x180038ca4  retn
```
