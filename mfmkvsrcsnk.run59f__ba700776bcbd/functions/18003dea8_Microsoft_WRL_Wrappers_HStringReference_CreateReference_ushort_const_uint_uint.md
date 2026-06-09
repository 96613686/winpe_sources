# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18003dea8`
- end: `0x18003def6`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003b90c`
- `0x18003ce90`
- `0x18004cdb4`
- `0x180079a58`
- `0x18007a0e4`

## callees

- `0x18003dea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003dee3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003dee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003dec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003dec7`

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
0x18003dea8  sub     rsp, 28h
0x18003deac  mov     eax, r9d
0x18003deaf  mov     r10, rdx
0x18003deb2  cmp     r9d, r8d
0x18003deb5  jb      short loc_18003DEBB
0x18003deb7  lea     eax, [r8-1]
0x18003debb  lea     r9, [rcx+18h]; string
0x18003debf  mov     r8, rcx; hstringHeader
0x18003dec2  mov     rcx, r10; sourceString
0x18003dec5  mov     edx, eax; length
0x18003dec7  call    cs:__imp_WindowsCreateStringReference
0x18003dece  nop     dword ptr [rax+rax+00h]
0x18003ded3  test    eax, eax
0x18003ded5  jns     short loc_18003DEF0
0x18003ded7  xor     r9d, r9d; lpArguments
0x18003deda  xor     r8d, r8d; nNumberOfArguments
0x18003dedd  mov     ecx, eax; dwExceptionCode
0x18003dedf  lea     edx, [r9+1]; dwExceptionFlags
0x18003dee3  call    cs:__imp_RaiseException
0x18003deea  nop     dword ptr [rax+rax+00h]
0x18003deef  int     3; Trap to Debugger
0x18003def0  add     rsp, 28h
0x18003def4  retn
```
