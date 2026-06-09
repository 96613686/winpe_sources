# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180007ee0`
- end: `0x180007f22`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `66`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `27`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010d3c`
- `0x180011fe0`
- `0x180012520`
- `0x180013988`
- `0x180013c08`
- `0x180015ca0`
- `0x180016230`
- `0x180016734`
- `0x180016cf4`
- `0x180016ddc`
- `0x180017768`
- `0x180017cac`
- `0x18001c010`
- `0x18001f53c`
- `0x18001f6fc`
- `0x18001f9d0`
- `0x18001fea0`
- `0x180020048`
- `0x18002037c`
- `0x18002068c`
- `0x180020990`
- `0x1800224b4`
- `0x18003ac30`
- `0x180056e2c`
- `0x180058450`
- `0x18006c030`
- `0x18006c1b0`

## callees

- `0x180007ee0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007eff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f16`

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
0x180007ee0  sub     rsp, 28h
0x180007ee4  mov     eax, r9d
0x180007ee7  mov     r10, rdx
0x180007eea  cmp     r9d, r8d
0x180007eed  jb      short loc_180007EF3
0x180007eef  lea     eax, [r8-1]
0x180007ef3  lea     r9, [rcx+18h]; string
0x180007ef7  mov     r8, rcx; hstringHeader
0x180007efa  mov     rcx, r10; sourceString
0x180007efd  mov     edx, eax; length
0x180007eff  call    cs:__imp_WindowsCreateStringReference
0x180007f05  test    eax, eax
0x180007f07  jns     short loc_180007F1D
0x180007f09  xor     r9d, r9d; lpArguments
0x180007f0c  xor     r8d, r8d; nNumberOfArguments
0x180007f0f  mov     edx, 1; dwExceptionFlags
0x180007f14  mov     ecx, eax; dwExceptionCode
0x180007f16  call    cs:__imp_RaiseException
0x180007f1c  int     3; Trap to Debugger
0x180007f1d  add     rsp, 28h
0x180007f21  retn
```
