# Windows::Internal::StringReference::StringReference(ushort const (&)[2])

- ea: `0x180019d18`
- end: `0x180019d5b`
- name: `??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c744`
- `0x18002c844`
- `0x18002f378`

## callees

- `0x180019d18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019d4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019d4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019d33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019d33`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 1u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180019d18  push    rbx
0x180019d1a  sub     rsp, 20h
0x180019d1e  mov     rax, rdx
0x180019d21  lea     r8, [rcx+8]; hstringHeader
0x180019d25  mov     rbx, rcx
0x180019d28  mov     r9, rcx; string
0x180019d2b  mov     rcx, rax; sourceString
0x180019d2e  mov     edx, 1; length
0x180019d33  call    cs:__imp_WindowsCreateStringReference
0x180019d39  test    eax, eax
0x180019d3b  jns     short loc_180019D52
0x180019d3d  xor     r9d, r9d; lpArguments
0x180019d40  xor     r8d, r8d; nNumberOfArguments
0x180019d43  mov     ecx, 0C000000Dh; dwExceptionCode
0x180019d48  lea     edx, [r9+1]; dwExceptionFlags
0x180019d4c  call    cs:__imp_RaiseException
0x180019d52  mov     rax, rbx
0x180019d55  add     rsp, 20h
0x180019d59  pop     rbx
0x180019d5a  retn
```
