# Windows::Internal::StringReference::StringReference(ushort const (&)[41])

- ea: `0x180006540`
- end: `0x180006585`
- name: `??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z`
- size: `69`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[41])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006380`
- `0x18001fad0`

## callees

- `0x180006540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006576`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000655c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000655c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[41])
{
  if ( WindowsCreateStringReference(
         L"Windows.Media.Streaming.DeviceController",
         0x28u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180006540  push    rbx
0x180006542  sub     rsp, 20h
0x180006546  mov     rbx, rcx
0x180006549  lea     r8, [rcx+8]; hstringHeader
0x18000654d  mov     r9, rcx; string
0x180006550  mov     edx, 28h ; '('; length
0x180006555  lea     rcx, ?RuntimeClass_Windows_Media_Streaming_DeviceController@@3QBGB; "Windows.Media.Streaming.DeviceControlle"...
0x18000655c  call    cs:__imp_WindowsCreateStringReference
0x180006562  test    eax, eax
0x180006564  jns     short loc_18000657C
0x180006566  xor     r9d, r9d; lpArguments
0x180006569  xor     r8d, r8d; nNumberOfArguments
0x18000656c  mov     edx, 1; dwExceptionFlags
0x180006571  mov     ecx, 0C000000Dh; dwExceptionCode
0x180006576  call    cs:__imp_RaiseException
0x18000657c  mov     rax, rbx
0x18000657f  add     rsp, 20h
0x180006583  pop     rbx
0x180006584  retn
```
