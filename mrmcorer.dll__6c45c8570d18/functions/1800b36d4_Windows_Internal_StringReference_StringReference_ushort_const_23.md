# Windows::Internal::StringReference::StringReference(ushort const (&)[23])

- ea: `0x1800b36d4`
- end: `0x1800b3718`
- name: `??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[23])`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800b4530`
- `0x1800b4a88`

## callees

- `0x1800b36d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b3709`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b3709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b36f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b36f0`

## string_xrefs

- `0x1800b36e9`: `Windows.Foundation.Uri`

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
0x1800b36d4  push    rbx
0x1800b36d6  sub     rsp, 20h
0x1800b36da  mov     rbx, rcx
0x1800b36dd  lea     r8, [rcx+8]; hstringHeader
0x1800b36e1  mov     r9, rcx; string
0x1800b36e4  mov     edx, 16h; length
0x1800b36e9  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800b36f0  call    cs:__imp_WindowsCreateStringReference
0x1800b36f6  test    eax, eax
0x1800b36f8  jns     short loc_1800B370F
0x1800b36fa  xor     r9d, r9d; lpArguments
0x1800b36fd  xor     r8d, r8d; nNumberOfArguments
0x1800b3700  lea     edx, [r9+1]; dwExceptionFlags
0x1800b3704  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b3709  call    cs:__imp_RaiseException
0x1800b370f  mov     rax, rbx
0x1800b3712  add     rsp, 20h
0x1800b3716  pop     rbx
0x1800b3717  retn
```
