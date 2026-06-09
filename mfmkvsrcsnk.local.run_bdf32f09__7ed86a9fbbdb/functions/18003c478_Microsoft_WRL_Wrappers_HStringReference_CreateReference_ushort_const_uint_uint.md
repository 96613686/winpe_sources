# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18003c478`
- end: `0x18003c4b9`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180039f58`
- `0x18003b4b8`
- `0x18004ae44`
- `0x18007656c`
- `0x180076bb0`

## callees

- `0x18003c478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003c4ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003c4ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c497`

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
0x18003c478  sub     rsp, 28h
0x18003c47c  mov     eax, r9d
0x18003c47f  mov     r10, rdx
0x18003c482  cmp     r9d, r8d
0x18003c485  jb      short loc_18003C48B
0x18003c487  lea     eax, [r8-1]
0x18003c48b  lea     r9, [rcx+18h]; string
0x18003c48f  mov     r8, rcx; hstringHeader
0x18003c492  mov     rcx, r10; sourceString
0x18003c495  mov     edx, eax; length
0x18003c497  call    cs:__imp_WindowsCreateStringReference
0x18003c49d  test    eax, eax
0x18003c49f  jns     short loc_18003C4B4
0x18003c4a1  xor     r9d, r9d; lpArguments
0x18003c4a4  xor     r8d, r8d; nNumberOfArguments
0x18003c4a7  mov     ecx, eax; dwExceptionCode
0x18003c4a9  lea     edx, [r9+1]; dwExceptionFlags
0x18003c4ad  call    cs:__imp_RaiseException
0x18003c4b3  int     3; Trap to Debugger
0x18003c4b4  add     rsp, 28h
0x18003c4b8  retn
```
