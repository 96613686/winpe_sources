# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x180074db8`
- end: `0x180074dfb`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007515c`

## callees

- `0x180074db8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074dec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074dec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074dd3`

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
0x180074db8  push    rbx
0x180074dba  sub     rsp, 20h
0x180074dbe  mov     rax, rdx
0x180074dc1  lea     r8, [rcx+8]; hstringHeader
0x180074dc5  mov     rbx, rcx
0x180074dc8  mov     r9, rcx; string
0x180074dcb  mov     rcx, rax; sourceString
0x180074dce  mov     edx, 0Ch; length
0x180074dd3  call    cs:__imp_WindowsCreateStringReference
0x180074dd9  test    eax, eax
0x180074ddb  jns     short loc_180074DF2
0x180074ddd  xor     r9d, r9d; lpArguments
0x180074de0  xor     r8d, r8d; nNumberOfArguments
0x180074de3  mov     ecx, 0C000000Dh; dwExceptionCode
0x180074de8  lea     edx, [r9+1]; dwExceptionFlags
0x180074dec  call    cs:__imp_RaiseException
0x180074df2  mov     rax, rbx
0x180074df5  add     rsp, 20h
0x180074df9  pop     rbx
0x180074dfa  retn
```
