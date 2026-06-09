# Windows::Internal::StringReference::StringReference(ushort const (&)[23])

- ea: `0x18000f040`
- end: `0x18000f084`
- name: `??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[23])`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cfd4`
- `0x18000d280`

## callees

- `0x18000f040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f075`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f075`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f05c`

## string_xrefs

- `0x18000f055`: `Windows.Foundation.Uri`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[23])
{
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18000f040  push    rbx
0x18000f042  sub     rsp, 20h
0x18000f046  mov     rbx, rcx
0x18000f049  lea     r8, [rcx+8]; hstringHeader
0x18000f04d  mov     r9, rcx; string
0x18000f050  mov     edx, 16h; length
0x18000f055  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18000f05c  call    cs:__imp_WindowsCreateStringReference
0x18000f062  test    eax, eax
0x18000f064  jns     short loc_18000F07B
0x18000f066  xor     r9d, r9d; lpArguments
0x18000f069  xor     r8d, r8d; nNumberOfArguments
0x18000f06c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000f071  lea     edx, [r9+1]; dwExceptionFlags
0x18000f075  call    cs:__imp_RaiseException
0x18000f07b  mov     rax, rbx
0x18000f07e  add     rsp, 20h
0x18000f082  pop     rbx
0x18000f083  retn
```
