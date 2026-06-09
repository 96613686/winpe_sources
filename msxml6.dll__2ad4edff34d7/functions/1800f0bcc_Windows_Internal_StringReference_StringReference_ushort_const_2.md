# Windows::Internal::StringReference::StringReference(ushort const (&)[2])

- ea: `0x1800f0bcc`
- end: `0x1800f0c0f`
- name: `??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z`
- size: `67`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*stringRef)[2])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800f3430`

## callees

- `0x1800f0bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f0c00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f0c00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f0be7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f0be7`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*stringRef)[2])
{
  if ( WindowsCreateStringReference((PCWSTR)stringRef, 1u, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800f0bcc  push    rbx
0x1800f0bce  sub     rsp, 20h
0x1800f0bd2  mov     rax, stringRef
0x1800f0bd5  lea     r8, [this+8]; hstringHeader
0x1800f0bd9  mov     rbx, this
0x1800f0bdc  mov     r9, this; string
0x1800f0bdf  mov     this, rax; sourceString
0x1800f0be2  mov     edx, 1; length
0x1800f0be7  call    cs:__imp_WindowsCreateStringReference
0x1800f0bed  test    eax, eax
0x1800f0bef  jns     short loc_1800F0C06
0x1800f0bf1  xor     r9d, r9d; lpArguments
0x1800f0bf4  xor     r8d, r8d; nNumberOfArguments
0x1800f0bf7  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800f0bfc  lea     edx, [r9+1]; dwExceptionFlags
0x1800f0c00  call    cs:__imp_RaiseException
0x1800f0c06  mov     rax, rbx
0x1800f0c09  add     rsp, 20h
0x1800f0c0d  pop     rbx
0x1800f0c0e  retn
```
