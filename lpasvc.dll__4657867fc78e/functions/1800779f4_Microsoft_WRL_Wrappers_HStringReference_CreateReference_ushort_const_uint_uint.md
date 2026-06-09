# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800779f4`
- end: `0x180077a35`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180074140`
- `0x18007cc64`

## callees

- `0x1800779f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077a29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077a29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077a13`

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
0x1800779f4  sub     rsp, 28h
0x1800779f8  mov     eax, r9d
0x1800779fb  mov     r10, rdx
0x1800779fe  cmp     r9d, r8d
0x180077a01  jb      short loc_180077A07
0x180077a03  lea     eax, [r8-1]
0x180077a07  lea     r9, [rcx+18h]; string
0x180077a0b  mov     r8, rcx; hstringHeader
0x180077a0e  mov     rcx, r10; sourceString
0x180077a11  mov     edx, eax; length
0x180077a13  call    cs:__imp_WindowsCreateStringReference
0x180077a19  test    eax, eax
0x180077a1b  jns     short loc_180077A30
0x180077a1d  xor     r9d, r9d; lpArguments
0x180077a20  xor     r8d, r8d; nNumberOfArguments
0x180077a23  mov     ecx, eax; dwExceptionCode
0x180077a25  lea     edx, [r9+1]; dwExceptionFlags
0x180077a29  call    cs:__imp_RaiseException
0x180077a2f  int     3; Trap to Debugger
0x180077a30  add     rsp, 28h
0x180077a34  retn
```
