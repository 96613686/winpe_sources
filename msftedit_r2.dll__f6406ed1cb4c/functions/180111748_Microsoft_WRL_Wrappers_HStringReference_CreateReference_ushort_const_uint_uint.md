# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180111748`
- end: `0x180111796`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800fa6e0`
- `0x1801e58f4`
- `0x1802773c0`

## callees

- `0x180111748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180111783`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180111783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180111767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180111767`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  HRESULT StringReference; // eax

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180111748  sub     rsp, 28h
0x18011174c  mov     eax, r9d
0x18011174f  mov     r10, rdx
0x180111752  cmp     r9d, r8d
0x180111755  jb      short loc_18011175B
0x180111757  lea     eax, [r8-1]
0x18011175b  lea     r9, [rcx+18h]; string
0x18011175f  mov     r8, rcx; hstringHeader
0x180111762  mov     rcx, r10; sourceString
0x180111765  mov     edx, eax; length
0x180111767  call    cs:__imp_WindowsCreateStringReference
0x18011176e  nop     dword ptr [rax+rax+00h]
0x180111773  test    eax, eax
0x180111775  jns     short loc_180111790
0x180111777  xor     r9d, r9d; lpArguments
0x18011177a  xor     r8d, r8d; nNumberOfArguments
0x18011177d  mov     ecx, eax; dwExceptionCode
0x18011177f  lea     edx, [r9+1]; dwExceptionFlags
0x180111783  call    cs:__imp_RaiseException
0x18011178a  nop     dword ptr [rax+rax+00h]
0x18011178f  int     3; Trap to Debugger
0x180111790  add     rsp, 28h
0x180111794  retn
```
