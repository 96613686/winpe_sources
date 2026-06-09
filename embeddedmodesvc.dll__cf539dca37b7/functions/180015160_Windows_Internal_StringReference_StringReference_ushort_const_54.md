# Windows::Internal::StringReference::StringReference(ushort const (&)[54])

- ea: `0x180015160`
- end: `0x1800151a4`
- name: `??$?0$0DG@@StringReference@Internal@Windows@@QEAA@AEAY0DG@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[54])`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015e98`

## callees

- `0x180015160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015195`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001517c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001517c`

## string_xrefs

- `0x180015175`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[54])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.ApplicationExtension",
         0x35u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180015160  push    rbx
0x180015162  sub     rsp, 20h
0x180015166  mov     rbx, rcx
0x180015169  lea     r8, [rcx+8]; hstringHeader
0x18001516d  mov     r9, rcx; string
0x180015170  mov     edx, 35h ; '5'; length
0x180015175  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18001517c  call    cs:__imp_WindowsCreateStringReference
0x180015182  test    eax, eax
0x180015184  jns     short loc_18001519B
0x180015186  xor     r9d, r9d; lpArguments
0x180015189  xor     r8d, r8d; nNumberOfArguments
0x18001518c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015191  lea     edx, [r9+1]; dwExceptionFlags
0x180015195  call    cs:__imp_RaiseException
0x18001519b  mov     rax, rbx
0x18001519e  add     rsp, 20h
0x1800151a2  pop     rbx
0x1800151a3  retn
```
