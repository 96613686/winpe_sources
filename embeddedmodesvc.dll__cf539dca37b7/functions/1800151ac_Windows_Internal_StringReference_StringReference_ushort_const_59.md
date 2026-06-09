# Windows::Internal::StringReference::StringReference(ushort const (&)[59])

- ea: `0x1800151ac`
- end: `0x1800151f0`
- name: `??$?0$0DL@@StringReference@Internal@Windows@@QEAA@AEAY0DL@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[59])`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180015e98`

## callees

- `0x1800151ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800151c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800151c8`

## string_xrefs

- `0x1800151c1`: `Windows.Internal.StateRepository.ApplicationBackgroundTask`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[59])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.ApplicationBackgroundTask",
         0x3Au,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800151ac  push    rbx
0x1800151ae  sub     rsp, 20h
0x1800151b2  mov     rbx, rcx
0x1800151b5  lea     r8, [rcx+8]; hstringHeader
0x1800151b9  mov     r9, rcx; string
0x1800151bc  mov     edx, 3Ah ; ':'; length
0x1800151c1  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationBackgroundTask@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800151c8  call    cs:__imp_WindowsCreateStringReference
0x1800151ce  test    eax, eax
0x1800151d0  jns     short loc_1800151E7
0x1800151d2  xor     r9d, r9d; lpArguments
0x1800151d5  xor     r8d, r8d; nNumberOfArguments
0x1800151d8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800151dd  lea     edx, [r9+1]; dwExceptionFlags
0x1800151e1  call    cs:__imp_RaiseException
0x1800151e7  mov     rax, rbx
0x1800151ea  add     rsp, 20h
0x1800151ee  pop     rbx
0x1800151ef  retn
```
