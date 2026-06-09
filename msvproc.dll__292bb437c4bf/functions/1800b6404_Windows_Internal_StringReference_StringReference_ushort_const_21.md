# Windows::Internal::StringReference::StringReference(ushort const (&)[21])

- ea: `0x1800b6404`
- end: `0x1800b6447`
- name: `??$?0$0BF@@StringReference@Internal@Windows@@QEAA@AEAY0BF@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b240`

## callees

- `0x1800b6404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6438`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b641f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b641f`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x14u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800b6404  push    rbx
0x1800b6406  sub     rsp, 20h
0x1800b640a  mov     rax, rdx
0x1800b640d  lea     r8, [rcx+8]; hstringHeader
0x1800b6411  mov     rbx, rcx
0x1800b6414  mov     r9, rcx; string
0x1800b6417  mov     rcx, rax; sourceString
0x1800b641a  mov     edx, 14h; length
0x1800b641f  call    cs:__imp_WindowsCreateStringReference
0x1800b6425  test    eax, eax
0x1800b6427  jns     short loc_1800B643E
0x1800b6429  xor     r9d, r9d; lpArguments
0x1800b642c  xor     r8d, r8d; nNumberOfArguments
0x1800b642f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b6434  lea     edx, [r9+1]; dwExceptionFlags
0x1800b6438  call    cs:__imp_RaiseException
0x1800b643e  mov     rax, rbx
0x1800b6441  add     rsp, 20h
0x1800b6445  pop     rbx
0x1800b6446  retn
```
