# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180010810`
- end: `0x180010851`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010450`
- `0x18003f6d0`
- `0x1800461bc`
- `0x18004a3a0`
- `0x18004a5a0`
- `0x18005e490`
- `0x18005ef00`
- `0x180063030`
- `0x180082860`
- `0x180096bd4`
- `0x18009b0d8`
- `0x1800a8d64`

## callees

- `0x180010810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010845`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001082f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001082f`

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
0x180010810  sub     rsp, 28h
0x180010814  mov     eax, r9d
0x180010817  mov     r10, rdx
0x18001081a  cmp     r9d, r8d
0x18001081d  jb      short loc_180010823
0x18001081f  lea     eax, [r8-1]
0x180010823  lea     r9, [rcx+18h]; string
0x180010827  mov     r8, rcx; hstringHeader
0x18001082a  mov     rcx, r10; sourceString
0x18001082d  mov     edx, eax; length
0x18001082f  call    cs:__imp_WindowsCreateStringReference
0x180010835  test    eax, eax
0x180010837  jns     short loc_18001084C
0x180010839  xor     r9d, r9d; lpArguments
0x18001083c  xor     r8d, r8d; nNumberOfArguments
0x18001083f  mov     ecx, eax; dwExceptionCode
0x180010841  lea     edx, [r9+1]; dwExceptionFlags
0x180010845  call    cs:__imp_RaiseException
0x18001084b  int     3; Trap to Debugger
0x18001084c  add     rsp, 28h
0x180010850  retn
```
