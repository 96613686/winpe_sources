# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x1800b6450`
- end: `0x1800b6494`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[13])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b240`

## callees

- `0x1800b6450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6485`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b646c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b646c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[13])
{
  if ( WindowsCreateStringReference(L"paddingColor", 0xCu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800b6450  push    rbx
0x1800b6452  sub     rsp, 20h
0x1800b6456  mov     rbx, rcx
0x1800b6459  lea     r8, [rcx+8]; hstringHeader
0x1800b645d  mov     r9, rcx; string
0x1800b6460  mov     edx, 0Ch; length
0x1800b6465  lea     rcx, aPaddingcolor; "paddingColor"
0x1800b646c  call    cs:__imp_WindowsCreateStringReference
0x1800b6472  test    eax, eax
0x1800b6474  jns     short loc_1800B648B
0x1800b6476  xor     r9d, r9d; lpArguments
0x1800b6479  xor     r8d, r8d; nNumberOfArguments
0x1800b647c  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b6481  lea     edx, [r9+1]; dwExceptionFlags
0x1800b6485  call    cs:__imp_RaiseException
0x1800b648b  mov     rax, rbx
0x1800b648e  add     rsp, 20h
0x1800b6492  pop     rbx
0x1800b6493  retn
```
