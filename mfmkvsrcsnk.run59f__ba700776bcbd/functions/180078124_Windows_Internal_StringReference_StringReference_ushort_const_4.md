# Windows::Internal::StringReference::StringReference(ushort const (&)[4])

- ea: `0x180078124`
- end: `0x180078174`
- name: `??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z`
- size: `80`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007965c`

## callees

- `0x180078124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007815e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007815e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007813f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007813f`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 3u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180078124  push    rbx
0x180078126  sub     rsp, 20h
0x18007812a  mov     rax, rdx
0x18007812d  lea     r8, [rcx+8]; hstringHeader
0x180078131  mov     rbx, rcx
0x180078134  mov     r9, rcx; string
0x180078137  mov     rcx, rax; sourceString
0x18007813a  mov     edx, 3; length
0x18007813f  call    cs:__imp_WindowsCreateStringReference
0x180078146  nop     dword ptr [rax+rax+00h]
0x18007814b  test    eax, eax
0x18007814d  jns     short loc_18007816A
0x18007814f  xor     r9d, r9d; lpArguments
0x180078152  xor     r8d, r8d; nNumberOfArguments
0x180078155  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007815a  lea     edx, [r9+1]; dwExceptionFlags
0x18007815e  call    cs:__imp_RaiseException
0x180078165  nop     dword ptr [rax+rax+00h]
0x18007816a  mov     rax, rbx
0x18007816d  add     rsp, 20h
0x180078171  pop     rbx
0x180078172  retn
```
