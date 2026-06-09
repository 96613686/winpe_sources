# Windows::Internal::StringReference::StringReference(ushort const (&)[33])

- ea: `0x180071a8c`
- end: `0x180071add`
- name: `??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z`
- size: `81`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[33])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800718e8`

## callees

- `0x180071a8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071ac7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180071aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180071aa8`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[33])
{
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_Foundation_PropertyValue,
         0x20u,
         &this->_header,
         &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x180071a8c  push    rbx
0x180071a8e  sub     rsp, 20h
0x180071a92  mov     rbx, this
0x180071a95  lea     r8, [this+8]; hstringHeader
0x180071a99  mov     r9, this; string
0x180071a9c  mov     edx, 20h ; ' '; length
0x180071aa1  lea     this, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; sourceString
0x180071aa8  call    cs:__imp_WindowsCreateStringReference
0x180071aaf  nop     dword ptr [rax+rax+00h]
0x180071ab4  test    eax, eax
0x180071ab6  jns     short loc_180071AD3
0x180071ab8  xor     r9d, r9d; lpArguments
0x180071abb  xor     r8d, r8d; nNumberOfArguments
0x180071abe  mov     ecx, 0C000000Dh; dwExceptionCode
0x180071ac3  lea     edx, [r9+1]; dwExceptionFlags
0x180071ac7  call    cs:__imp_RaiseException
0x180071ace  nop     dword ptr [rax+rax+00h]
0x180071ad3  mov     rax, rbx
0x180071ad6  add     rsp, 20h
0x180071ada  pop     rbx
0x180071adb  retn
```
