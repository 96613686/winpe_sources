# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18004ccc4`
- end: `0x18004cd05`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004c828`
- `0x18004cd0c`
- `0x180060ffc`

## callees

- `0x18004ccc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ccf9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ccf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cce3`

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
0x18004ccc4  sub     rsp, 28h
0x18004ccc8  mov     eax, r9d
0x18004cccb  mov     r10, rdx
0x18004ccce  cmp     r9d, r8d
0x18004ccd1  jb      short loc_18004CCD7
0x18004ccd3  lea     eax, [r8-1]
0x18004ccd7  lea     r9, [rcx+18h]; string
0x18004ccdb  mov     r8, rcx; hstringHeader
0x18004ccde  mov     rcx, r10; sourceString
0x18004cce1  mov     edx, eax; length
0x18004cce3  call    cs:__imp_WindowsCreateStringReference
0x18004cce9  test    eax, eax
0x18004cceb  jns     short loc_18004CD00
0x18004cced  xor     r9d, r9d; lpArguments
0x18004ccf0  xor     r8d, r8d; nNumberOfArguments
0x18004ccf3  mov     ecx, eax; dwExceptionCode
0x18004ccf5  lea     edx, [r9+1]; dwExceptionFlags
0x18004ccf9  call    cs:__imp_RaiseException
0x18004ccff  int     3; Trap to Debugger
0x18004cd00  add     rsp, 28h
0x18004cd04  retn
```
