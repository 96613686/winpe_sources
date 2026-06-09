# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180081110`
- end: `0x180081151`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016d50`
- `0x180080dc0`
- `0x180080f74`
- `0x180081b7c`
- `0x180081d7c`
- `0x1800825a0`
- `0x180082b50`

## callees

- `0x180081110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180081145`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180081145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008112f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008112f`

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
0x180081110  sub     rsp, 28h
0x180081114  mov     eax, r9d
0x180081117  mov     r10, rdx
0x18008111a  cmp     r9d, r8d
0x18008111d  jb      short loc_180081123
0x18008111f  lea     eax, [r8-1]
0x180081123  lea     r9, [rcx+18h]; string
0x180081127  mov     r8, rcx; hstringHeader
0x18008112a  mov     rcx, r10; sourceString
0x18008112d  mov     edx, eax; length
0x18008112f  call    cs:__imp_WindowsCreateStringReference
0x180081135  test    eax, eax
0x180081137  jns     short loc_18008114C
0x180081139  xor     r9d, r9d; lpArguments
0x18008113c  xor     r8d, r8d; nNumberOfArguments
0x18008113f  mov     ecx, eax; dwExceptionCode
0x180081141  lea     edx, [r9+1]; dwExceptionFlags
0x180081145  call    cs:__imp_RaiseException
0x18008114b  int     3; Trap to Debugger
0x18008114c  add     rsp, 28h
0x180081150  retn
```
