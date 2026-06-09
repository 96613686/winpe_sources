# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180025b08`
- end: `0x180025b49`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800180fc`
- `0x1800347d0`
- `0x18003ac98`
- `0x18003ded0`
- `0x18003fe18`
- `0x1800414e0`
- `0x1800425f0`
- `0x1800444ec`
- `0x180046ca0`
- `0x18004b3b8`
- `0x18004c714`
- `0x18004e018`
- `0x180052cf0`
- `0x1800531c8`
- `0x1800b1790`

## callees

- `0x180025b08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025b3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025b3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025b27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025b27`

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
0x180025b08  sub     rsp, 28h
0x180025b0c  mov     eax, r9d
0x180025b0f  mov     r10, rdx
0x180025b12  cmp     r9d, r8d
0x180025b15  jb      short loc_180025B1B
0x180025b17  lea     eax, [r8-1]
0x180025b1b  lea     r9, [rcx+18h]; string
0x180025b1f  mov     r8, rcx; hstringHeader
0x180025b22  mov     rcx, r10; sourceString
0x180025b25  mov     edx, eax; length
0x180025b27  call    cs:__imp_WindowsCreateStringReference
0x180025b2d  test    eax, eax
0x180025b2f  jns     short loc_180025B44
0x180025b31  xor     r9d, r9d; lpArguments
0x180025b34  xor     r8d, r8d; nNumberOfArguments
0x180025b37  mov     ecx, eax; dwExceptionCode
0x180025b39  lea     edx, [r9+1]; dwExceptionFlags
0x180025b3d  call    cs:__imp_RaiseException
0x180025b43  int     3; Trap to Debugger
0x180025b44  add     rsp, 28h
0x180025b48  retn
```
