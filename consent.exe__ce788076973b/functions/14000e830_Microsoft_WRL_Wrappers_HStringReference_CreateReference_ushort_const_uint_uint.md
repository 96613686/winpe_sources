# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x14000e830`
- end: `0x14000e871`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e5e4`

## callees

- `0x14000e830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000e865`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000e865`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e84f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e84f`

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
0x14000e830  sub     rsp, 28h
0x14000e834  mov     eax, r9d
0x14000e837  mov     r10, rdx
0x14000e83a  cmp     r9d, r8d
0x14000e83d  jb      short loc_14000E843
0x14000e83f  lea     eax, [r8-1]
0x14000e843  lea     r9, [rcx+18h]; string
0x14000e847  mov     r8, rcx; hstringHeader
0x14000e84a  mov     rcx, r10; sourceString
0x14000e84d  mov     edx, eax; length
0x14000e84f  call    cs:__imp_WindowsCreateStringReference
0x14000e855  test    eax, eax
0x14000e857  jns     short loc_14000E86C
0x14000e859  xor     r9d, r9d; lpArguments
0x14000e85c  xor     r8d, r8d; nNumberOfArguments
0x14000e85f  mov     ecx, eax; dwExceptionCode
0x14000e861  lea     edx, [r9+1]; dwExceptionFlags
0x14000e865  call    cs:__imp_RaiseException
0x14000e86b  int     3; Trap to Debugger
0x14000e86c  add     rsp, 28h
0x14000e870  retn
```
