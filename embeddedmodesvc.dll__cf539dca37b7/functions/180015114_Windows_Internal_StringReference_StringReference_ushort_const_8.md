# Windows::Internal::StringReference::StringReference(ushort const (&)[8])

- ea: `0x180015114`
- end: `0x180015158`
- name: `??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[8])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015e98`

## callees

- `0x180015114`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015149`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015130`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[8])
{
  if ( WindowsCreateStringReference(L"startup", 7u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180015114  push    rbx
0x180015116  sub     rsp, 20h
0x18001511a  mov     rbx, rcx
0x18001511d  lea     r8, [rcx+8]; hstringHeader
0x180015121  mov     r9, rcx; string
0x180015124  mov     edx, 7; length
0x180015129  lea     rcx, sourceString; "startup"
0x180015130  call    cs:__imp_WindowsCreateStringReference
0x180015136  test    eax, eax
0x180015138  jns     short loc_18001514F
0x18001513a  xor     r9d, r9d; lpArguments
0x18001513d  xor     r8d, r8d; nNumberOfArguments
0x180015140  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015145  lea     edx, [r9+1]; dwExceptionFlags
0x180015149  call    cs:__imp_RaiseException
0x18001514f  mov     rax, rbx
0x180015152  add     rsp, 20h
0x180015156  pop     rbx
0x180015157  retn
```
