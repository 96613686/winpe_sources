# Windows::Internal::StringReference::StringReference(ushort const (&)[28])

- ea: `0x180278174`
- end: `0x1802781c4`
- name: `??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z`
- size: `80`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180278a28`
- `0x18027abe4`

## callees

- `0x180278174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802781ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802781ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18027818f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18027818f`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x1Bu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180278174  push    rbx
0x180278176  sub     rsp, 20h
0x18027817a  mov     rax, rdx
0x18027817d  lea     r8, [rcx+8]; hstringHeader
0x180278181  mov     rbx, rcx
0x180278184  mov     r9, rcx; string
0x180278187  mov     rcx, rax; sourceString
0x18027818a  mov     edx, 1Bh; length
0x18027818f  call    cs:__imp_WindowsCreateStringReference
0x180278196  nop     dword ptr [rax+rax+00h]
0x18027819b  test    eax, eax
0x18027819d  jns     short loc_1802781BA
0x18027819f  xor     r9d, r9d; lpArguments
0x1802781a2  xor     r8d, r8d; nNumberOfArguments
0x1802781a5  mov     ecx, 0C000000Dh; dwExceptionCode
0x1802781aa  lea     edx, [r9+1]; dwExceptionFlags
0x1802781ae  call    cs:__imp_RaiseException
0x1802781b5  nop     dword ptr [rax+rax+00h]
0x1802781ba  mov     rax, rbx
0x1802781bd  add     rsp, 20h
0x1802781c1  pop     rbx
0x1802781c2  retn
```
