# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18007fc40`
- end: `0x18007fc81`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180080520`

## callees

- `0x18007fc40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fc75`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fc75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fc5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fc5f`

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
0x18007fc40  sub     rsp, 28h
0x18007fc44  mov     eax, r9d
0x18007fc47  mov     r10, rdx
0x18007fc4a  cmp     r9d, r8d
0x18007fc4d  jb      short loc_18007FC53
0x18007fc4f  lea     eax, [r8-1]
0x18007fc53  lea     r9, [rcx+18h]; string
0x18007fc57  mov     r8, rcx; hstringHeader
0x18007fc5a  mov     rcx, r10; sourceString
0x18007fc5d  mov     edx, eax; length
0x18007fc5f  call    cs:__imp_WindowsCreateStringReference
0x18007fc65  test    eax, eax
0x18007fc67  jns     short loc_18007FC7C
0x18007fc69  xor     r9d, r9d; lpArguments
0x18007fc6c  xor     r8d, r8d; nNumberOfArguments
0x18007fc6f  mov     ecx, eax; dwExceptionCode
0x18007fc71  lea     edx, [r9+1]; dwExceptionFlags
0x18007fc75  call    cs:__imp_RaiseException
0x18007fc7b  int     3; Trap to Debugger
0x18007fc7c  add     rsp, 28h
0x18007fc80  retn
```
