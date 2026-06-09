# sub_1800ED6DC

- ea: `0x1800ed6dc`
- end: `0x1800ed72d`
- name: `sub_1800ED6DC`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800eeb70`
- `0x18015f6a4`
- `0x18015f960`

## callees

- `0x1800ed6dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ed717`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ed717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ed6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ed6f8`

## pseudocode

```c
HSTRING *__fastcall sub_1800ED6DC(HSTRING *string)
{
  if ( WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800ed6dc  push    rbx
0x1800ed6de  sub     rsp, 20h
0x1800ed6e2  mov     rbx, rcx
0x1800ed6e5  lea     r8, [rcx+8]; hstringHeader
0x1800ed6e9  mov     r9, rcx; string
0x1800ed6ec  mov     edx, 1Bh; length
0x1800ed6f1  lea     rcx, aWindowsStorage; "Windows.Storage.StorageFile"
0x1800ed6f8  call    cs:WindowsCreateStringReference
0x1800ed6ff  nop     dword ptr [rax+rax+00h]
0x1800ed704  test    eax, eax
0x1800ed706  jns     short loc_1800ED723
0x1800ed708  xor     r9d, r9d; lpArguments
0x1800ed70b  xor     r8d, r8d; nNumberOfArguments
0x1800ed70e  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ed713  lea     edx, [r9+1]; dwExceptionFlags
0x1800ed717  call    cs:RaiseException
0x1800ed71e  nop     dword ptr [rax+rax+00h]
0x1800ed723  mov     rax, rbx
0x1800ed726  add     rsp, 20h
0x1800ed72a  pop     rbx
0x1800ed72b  retn
```
