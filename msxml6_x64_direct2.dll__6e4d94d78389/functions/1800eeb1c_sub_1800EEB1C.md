# sub_1800EEB1C

- ea: `0x1800eeb1c`
- end: `0x1800eeb6a`
- name: `sub_1800EEB1C`
- size: `78`
- prototype: `__int64 __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ed78c`
- `0x1800ef9f0`

## callees

- `0x1800eeb1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eeb57`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eeb57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eeb3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eeb3b`

## pseudocode

```c
void __fastcall sub_1800EEB1C(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32 a3, UINT32 a4)
{
  UINT32 v4; // eax
  signed int StringReference; // eax

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
0x1800eeb1c  sub     rsp, 28h
0x1800eeb20  mov     eax, r9d
0x1800eeb23  mov     r10, rdx
0x1800eeb26  cmp     r9d, r8d
0x1800eeb29  jb      short loc_1800EEB2F
0x1800eeb2b  lea     eax, [r8-1]
0x1800eeb2f  lea     r9, [rcx+18h]; string
0x1800eeb33  mov     r8, rcx; hstringHeader
0x1800eeb36  mov     rcx, r10; sourceString
0x1800eeb39  mov     edx, eax; length
0x1800eeb3b  call    cs:WindowsCreateStringReference
0x1800eeb42  nop     dword ptr [rax+rax+00h]
0x1800eeb47  test    eax, eax
0x1800eeb49  jns     short loc_1800EEB64
0x1800eeb4b  xor     r9d, r9d; lpArguments
0x1800eeb4e  xor     r8d, r8d; nNumberOfArguments
0x1800eeb51  mov     ecx, eax; dwExceptionCode
0x1800eeb53  lea     edx, [r9+1]; dwExceptionFlags
0x1800eeb57  call    cs:RaiseException
0x1800eeb5e  nop     dword ptr [rax+rax+00h]
0x1800eeb63  int     3; Trap to Debugger
0x1800eeb64  add     rsp, 28h
0x1800eeb68  retn
```
