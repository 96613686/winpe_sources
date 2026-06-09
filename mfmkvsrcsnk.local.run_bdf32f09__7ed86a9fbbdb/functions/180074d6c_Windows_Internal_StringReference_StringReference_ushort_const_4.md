# Windows::Internal::StringReference::StringReference(ushort const (&)[4])

- ea: `0x180074d6c`
- end: `0x180074daf`
- name: `??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800761b0`

## callees

- `0x180074d6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074da0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074d87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074d87`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 3u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180074d6c  push    rbx
0x180074d6e  sub     rsp, 20h
0x180074d72  mov     rax, rdx
0x180074d75  lea     r8, [rcx+8]; hstringHeader
0x180074d79  mov     rbx, rcx
0x180074d7c  mov     r9, rcx; string
0x180074d7f  mov     rcx, rax; sourceString
0x180074d82  mov     edx, 3; length
0x180074d87  call    cs:__imp_WindowsCreateStringReference
0x180074d8d  test    eax, eax
0x180074d8f  jns     short loc_180074DA6
0x180074d91  xor     r9d, r9d; lpArguments
0x180074d94  xor     r8d, r8d; nNumberOfArguments
0x180074d97  mov     ecx, 0C000000Dh; dwExceptionCode
0x180074d9c  lea     edx, [r9+1]; dwExceptionFlags
0x180074da0  call    cs:__imp_RaiseException
0x180074da6  mov     rax, rbx
0x180074da9  add     rsp, 20h
0x180074dad  pop     rbx
0x180074dae  retn
```
