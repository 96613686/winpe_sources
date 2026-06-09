# Windows::Internal::StringReference::StringReference(ushort const (&)[9])

- ea: `0x18002c240`
- end: `0x18002c284`
- name: `??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[9])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ef70`
- `0x18002f190`

## callees

- `0x18002c240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c275`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c25c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c25c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[9])
{
  if ( WindowsCreateStringReference(L"dc:title", 8u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002c240  push    rbx
0x18002c242  sub     rsp, 20h
0x18002c246  mov     rbx, rcx
0x18002c249  lea     r8, [rcx+8]; hstringHeader
0x18002c24d  mov     r9, rcx; string
0x18002c250  mov     edx, 8; length
0x18002c255  lea     rcx, aDcTitle; "dc:title"
0x18002c25c  call    cs:__imp_WindowsCreateStringReference
0x18002c262  test    eax, eax
0x18002c264  jns     short loc_18002C27B
0x18002c266  xor     r9d, r9d; lpArguments
0x18002c269  xor     r8d, r8d; nNumberOfArguments
0x18002c26c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c271  lea     edx, [r9+1]; dwExceptionFlags
0x18002c275  call    cs:__imp_RaiseException
0x18002c27b  mov     rax, rbx
0x18002c27e  add     rsp, 20h
0x18002c282  pop     rbx
0x18002c283  retn
```
