# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x18007817c`
- end: `0x1800781cc`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z`
- size: `80`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180078554`

## callees

- `0x18007817c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800781b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800781b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078197`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0xCu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18007817c  push    rbx
0x18007817e  sub     rsp, 20h
0x180078182  mov     rax, rdx
0x180078185  lea     r8, [rcx+8]; hstringHeader
0x180078189  mov     rbx, rcx
0x18007818c  mov     r9, rcx; string
0x18007818f  mov     rcx, rax; sourceString
0x180078192  mov     edx, 0Ch; length
0x180078197  call    cs:__imp_WindowsCreateStringReference
0x18007819e  nop     dword ptr [rax+rax+00h]
0x1800781a3  test    eax, eax
0x1800781a5  jns     short loc_1800781C2
0x1800781a7  xor     r9d, r9d; lpArguments
0x1800781aa  xor     r8d, r8d; nNumberOfArguments
0x1800781ad  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800781b2  lea     edx, [r9+1]; dwExceptionFlags
0x1800781b6  call    cs:__imp_RaiseException
0x1800781bd  nop     dword ptr [rax+rax+00h]
0x1800781c2  mov     rax, rbx
0x1800781c5  add     rsp, 20h
0x1800781c9  pop     rbx
0x1800781ca  retn
```
