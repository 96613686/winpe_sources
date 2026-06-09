# Windows::Internal::StringReference::StringReference(ushort const (&)[18])

- ea: `0x18002c2d8`
- end: `0x18002c31c`
- name: `??$?0$0BC@@StringReference@Internal@Windows@@QEAA@AEAY0BC@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[18])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ef70`

## callees

- `0x18002c2d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c30d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c2f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c2f4`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[18])
{
  if ( WindowsCreateStringReference(L"upnp:programTitle", 0x11u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002c2d8  push    rbx
0x18002c2da  sub     rsp, 20h
0x18002c2de  mov     rbx, rcx
0x18002c2e1  lea     r8, [rcx+8]; hstringHeader
0x18002c2e5  mov     r9, rcx; string
0x18002c2e8  mov     edx, 11h; length
0x18002c2ed  lea     rcx, aUpnpProgramtit; "upnp:programTitle"
0x18002c2f4  call    cs:__imp_WindowsCreateStringReference
0x18002c2fa  test    eax, eax
0x18002c2fc  jns     short loc_18002C313
0x18002c2fe  xor     r9d, r9d; lpArguments
0x18002c301  xor     r8d, r8d; nNumberOfArguments
0x18002c304  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002c309  lea     edx, [r9+1]; dwExceptionFlags
0x18002c30d  call    cs:__imp_RaiseException
0x18002c313  mov     rax, rbx
0x18002c316  add     rsp, 20h
0x18002c31a  pop     rbx
0x18002c31b  retn
```
