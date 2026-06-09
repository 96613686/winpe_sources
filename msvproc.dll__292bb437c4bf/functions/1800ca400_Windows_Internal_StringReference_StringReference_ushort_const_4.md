# Windows::Internal::StringReference::StringReference(ushort const (&)[4])

- ea: `0x1800ca400`
- end: `0x1800ca443`
- name: `??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ca498`

## callees

- `0x1800ca400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca434`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca434`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ca41b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ca41b`

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
0x1800ca400  push    rbx
0x1800ca402  sub     rsp, 20h
0x1800ca406  mov     rax, rdx
0x1800ca409  lea     r8, [rcx+8]; hstringHeader
0x1800ca40d  mov     rbx, rcx
0x1800ca410  mov     r9, rcx; string
0x1800ca413  mov     rcx, rax; sourceString
0x1800ca416  mov     edx, 3; length
0x1800ca41b  call    cs:__imp_WindowsCreateStringReference
0x1800ca421  test    eax, eax
0x1800ca423  jns     short loc_1800CA43A
0x1800ca425  xor     r9d, r9d; lpArguments
0x1800ca428  xor     r8d, r8d; nNumberOfArguments
0x1800ca42b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ca430  lea     edx, [r9+1]; dwExceptionFlags
0x1800ca434  call    cs:__imp_RaiseException
0x1800ca43a  mov     rax, rbx
0x1800ca43d  add     rsp, 20h
0x1800ca441  pop     rbx
0x1800ca442  retn
```
