# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000a4f8`
- end: `0x18000a539`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `45`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009100`
- `0x180009b90`
- `0x180011af8`
- `0x180024da4`
- `0x180029100`
- `0x180029170`
- `0x18002c984`
- `0x18002cc1c`
- `0x180034edc`
- `0x180035334`
- `0x180035458`
- `0x180036740`
- `0x18003920c`
- `0x180039ef8`
- `0x180044d8c`
- `0x180045d88`
- `0x180045f2c`
- `0x1800460d0`
- `0x180046680`
- `0x1800467a0`
- `0x180047464`
- `0x180048d44`
- `0x180049740`
- `0x180049e24`
- `0x18004a8ac`
- `0x18004bd0c`
- `0x18004beb0`
- `0x18004c4dc`
- `0x1800519c0`
- `0x180052190`
- `0x180053670`
- `0x1800546ac`
- `0x1800561b0`
- `0x18005a214`
- `0x18005b8cc`
- `0x18005ba40`
- `0x18005bd1c`
- `0x18005c3c0`
- `0x18005d084`
- `0x18005e0fc`
- `0x18005e9f0`
- `0x18005f3cc`
- `0x1800609e0`
- `0x180060be0`
- `0x1800673ac`

## callees

- `0x18000a4f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a52d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a52d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a517`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a517`

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
0x18000a4f8  sub     rsp, 28h
0x18000a4fc  mov     eax, r9d
0x18000a4ff  mov     r10, rdx
0x18000a502  cmp     r9d, r8d
0x18000a505  jb      short loc_18000A50B
0x18000a507  lea     eax, [r8-1]
0x18000a50b  lea     r9, [rcx+18h]; string
0x18000a50f  mov     r8, rcx; hstringHeader
0x18000a512  mov     rcx, r10; sourceString
0x18000a515  mov     edx, eax; length
0x18000a517  call    cs:__imp_WindowsCreateStringReference
0x18000a51d  test    eax, eax
0x18000a51f  jns     short loc_18000A534
0x18000a521  xor     r9d, r9d; lpArguments
0x18000a524  xor     r8d, r8d; nNumberOfArguments
0x18000a527  mov     ecx, eax; dwExceptionCode
0x18000a529  lea     edx, [r9+1]; dwExceptionFlags
0x18000a52d  call    cs:__imp_RaiseException
0x18000a533  int     3; Trap to Debugger
0x18000a534  add     rsp, 28h
0x18000a538  retn
```
