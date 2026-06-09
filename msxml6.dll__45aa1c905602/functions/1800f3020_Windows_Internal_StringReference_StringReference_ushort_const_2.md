# Windows::Internal::StringReference::StringReference(ushort const (&)[2])

- ea: `0x1800f3020`
- end: `0x1800f3070`
- name: `??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z`
- size: `80`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*stringRef)[2])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800f5904`

## callees

- `0x1800f3020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f305a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f305a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f303b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f303b`

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
0x1800f3020  push    rbx
0x1800f3022  sub     rsp, 20h
0x1800f3026  mov     rax, stringRef
0x1800f3029  lea     r8, [this+8]; hstringHeader
0x1800f302d  mov     rbx, this
0x1800f3030  mov     r9, this; string
0x1800f3033  mov     this, rax; sourceString
0x1800f3036  mov     edx, 1; length
0x1800f303b  call    cs:__imp_WindowsCreateStringReference
0x1800f3042  nop     dword ptr [rax+rax+00h]
0x1800f3047  test    eax, eax
0x1800f3049  jns     short loc_1800F3066
0x1800f304b  xor     r9d, r9d; lpArguments
0x1800f304e  xor     r8d, r8d; nNumberOfArguments
0x1800f3051  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800f3056  lea     edx, [r9+1]; dwExceptionFlags
0x1800f305a  call    cs:__imp_RaiseException
0x1800f3061  nop     dword ptr [rax+rax+00h]
0x1800f3066  mov     rax, rbx
0x1800f3069  add     rsp, 20h
0x1800f306d  pop     rbx
0x1800f306e  retn
```
