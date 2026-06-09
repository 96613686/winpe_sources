# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x140012214`
- end: `0x140012255`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400120b0`
- `0x1400122f8`

## callees

- `0x140012214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012249`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012233`

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
0x140012214  sub     rsp, 28h
0x140012218  mov     eax, r9d
0x14001221b  mov     r10, rdx
0x14001221e  cmp     r9d, r8d
0x140012221  jb      short loc_140012227
0x140012223  lea     eax, [r8-1]
0x140012227  lea     r9, [rcx+18h]; string
0x14001222b  mov     r8, rcx; hstringHeader
0x14001222e  mov     rcx, r10; sourceString
0x140012231  mov     edx, eax; length
0x140012233  call    cs:__imp_WindowsCreateStringReference
0x140012239  test    eax, eax
0x14001223b  jns     short loc_140012250
0x14001223d  xor     r9d, r9d; lpArguments
0x140012240  xor     r8d, r8d; nNumberOfArguments
0x140012243  mov     ecx, eax; dwExceptionCode
0x140012245  lea     edx, [r9+1]; dwExceptionFlags
0x140012249  call    cs:__imp_RaiseException
0x14001224f  int     3; Trap to Debugger
0x140012250  add     rsp, 28h
0x140012254  retn
```
