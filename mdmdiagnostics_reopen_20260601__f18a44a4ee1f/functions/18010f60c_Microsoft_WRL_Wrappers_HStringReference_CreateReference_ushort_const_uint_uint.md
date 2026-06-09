# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18010f60c`
- end: `0x18010f65a`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18010aafc`
- `0x18010afa8`

## callees

- `0x18010f60c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010f647`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010f647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010f62b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18010f62b`

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
0x18010f60c  sub     rsp, 28h
0x18010f610  mov     eax, r9d
0x18010f613  mov     r10, rdx
0x18010f616  cmp     r9d, r8d
0x18010f619  jb      short loc_18010F61F
0x18010f61b  lea     eax, [r8-1]
0x18010f61f  lea     r9, [rcx+18h]; string
0x18010f623  mov     r8, rcx; hstringHeader
0x18010f626  mov     rcx, r10; sourceString
0x18010f629  mov     edx, eax; length
0x18010f62b  call    cs:__imp_WindowsCreateStringReference
0x18010f632  nop     dword ptr [rax+rax+00h]
0x18010f637  test    eax, eax
0x18010f639  jns     short loc_18010F654
0x18010f63b  xor     r9d, r9d; lpArguments
0x18010f63e  xor     r8d, r8d; nNumberOfArguments
0x18010f641  mov     ecx, eax; dwExceptionCode
0x18010f643  lea     edx, [r9+1]; dwExceptionFlags
0x18010f647  call    cs:__imp_RaiseException
0x18010f64e  nop     dword ptr [rax+rax+00h]
0x18010f653  int     3; Trap to Debugger
0x18010f654  add     rsp, 28h
0x18010f658  retn
```
