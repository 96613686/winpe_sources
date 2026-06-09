# Windows::Internal::StringReference::StringReference(ushort const (&)[46])

- ea: `0x180011638`
- end: `0x18001167b`
- name: `??$?0$0CO@@StringReference@Internal@Windows@@QEAA@AEAY0CO@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180012ab0`
- `0x180017980`
- `0x180022e9c`

## callees

- `0x180011638`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011653`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001166c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001166c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x2Du, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180011638  push    rbx
0x18001163a  sub     rsp, 20h
0x18001163e  mov     rax, rdx
0x180011641  lea     r8, [rcx+8]; hstringHeader
0x180011645  mov     rbx, rcx
0x180011648  mov     r9, rcx; string
0x18001164b  mov     rcx, rax; sourceString
0x18001164e  mov     edx, 2Dh ; '-'; length
0x180011653  call    cs:__imp_WindowsCreateStringReference
0x180011659  test    eax, eax
0x18001165b  jns     short loc_180011672
0x18001165d  xor     r9d, r9d; lpArguments
0x180011660  xor     r8d, r8d; nNumberOfArguments
0x180011663  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011668  lea     edx, [r9+1]; dwExceptionFlags
0x18001166c  call    cs:__imp_RaiseException
0x180011672  mov     rax, rbx
0x180011675  add     rsp, 20h
0x180011679  pop     rbx
0x18001167a  retn
```
