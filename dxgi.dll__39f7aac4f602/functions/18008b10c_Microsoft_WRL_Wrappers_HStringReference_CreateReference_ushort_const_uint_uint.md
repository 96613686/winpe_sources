# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18008b10c`
- end: `0x18008b14d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18008bb78`
- `0x180091254`

## callees

- `0x18008b10c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008b141`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008b141`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008b12b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008b12b`

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
0x18008b10c  sub     rsp, 28h
0x18008b110  mov     eax, r9d
0x18008b113  mov     r10, rdx
0x18008b116  cmp     r9d, r8d
0x18008b119  jb      short loc_18008B11F
0x18008b11b  lea     eax, [r8-1]
0x18008b11f  lea     r9, [rcx+18h]; string
0x18008b123  mov     r8, rcx; hstringHeader
0x18008b126  mov     rcx, r10; sourceString
0x18008b129  mov     edx, eax; length
0x18008b12b  call    cs:__imp_WindowsCreateStringReference
0x18008b131  test    eax, eax
0x18008b133  jns     short loc_18008B148
0x18008b135  xor     r9d, r9d; lpArguments
0x18008b138  xor     r8d, r8d; nNumberOfArguments
0x18008b13b  mov     ecx, eax; dwExceptionCode
0x18008b13d  lea     edx, [r9+1]; dwExceptionFlags
0x18008b141  call    cs:__imp_RaiseException
0x18008b147  int     3; Trap to Debugger
0x18008b148  add     rsp, 28h
0x18008b14c  retn
```
