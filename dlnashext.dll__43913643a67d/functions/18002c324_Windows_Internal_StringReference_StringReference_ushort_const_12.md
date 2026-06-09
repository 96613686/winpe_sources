# Windows::Internal::StringReference::StringReference(ushort const (&)[12])

- ea: `0x18002c324`
- end: `0x18002c367`
- name: `??$?0$0M@@StringReference@Internal@Windows@@QEAA@AEAY0M@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002cc70`
- `0x18002e13c`

## callees

- `0x18002c324`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c358`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c33f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c33f`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0xBu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002c324  push    rbx
0x18002c326  sub     rsp, 20h
0x18002c32a  mov     rax, rdx
0x18002c32d  lea     r8, [rcx+8]; hstringHeader
0x18002c331  mov     rbx, rcx
0x18002c334  mov     r9, rcx; string
0x18002c337  mov     rcx, rax; sourceString
0x18002c33a  mov     edx, 0Bh; length
0x18002c33f  call    cs:__imp_WindowsCreateStringReference
0x18002c345  test    eax, eax
0x18002c347  jns     short loc_18002C35E
0x18002c349  xor     r9d, r9d; lpArguments
0x18002c34c  xor     r8d, r8d; nNumberOfArguments
0x18002c34f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c354  lea     edx, [r9+1]; dwExceptionFlags
0x18002c358  call    cs:__imp_RaiseException
0x18002c35e  mov     rax, rbx
0x18002c361  add     rsp, 20h
0x18002c365  pop     rbx
0x18002c366  retn
```
