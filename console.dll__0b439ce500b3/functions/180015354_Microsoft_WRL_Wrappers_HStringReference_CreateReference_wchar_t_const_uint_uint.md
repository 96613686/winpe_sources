# Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)

- ea: `0x180015354`
- end: `0x1800153a2`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015880`

## callees

- `0x180015354`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001538f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001538f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015373`

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
0x180015354  sub     rsp, 28h
0x180015358  mov     eax, r9d
0x18001535b  mov     r10, rdx
0x18001535e  cmp     r9d, r8d
0x180015361  jb      short loc_180015367
0x180015363  lea     eax, [r8-1]
0x180015367  lea     r9, [rcx+18h]; string
0x18001536b  mov     r8, rcx; hstringHeader
0x18001536e  mov     rcx, r10; sourceString
0x180015371  mov     edx, eax; length
0x180015373  call    cs:__imp_WindowsCreateStringReference
0x18001537a  nop     dword ptr [rax+rax+00h]
0x18001537f  test    eax, eax
0x180015381  jns     short loc_18001539C
0x180015383  xor     r9d, r9d; lpArguments
0x180015386  xor     r8d, r8d; nNumberOfArguments
0x180015389  mov     ecx, eax; dwExceptionCode
0x18001538b  lea     edx, [r9+1]; dwExceptionFlags
0x18001538f  call    cs:__imp_RaiseException
0x180015396  nop     dword ptr [rax+rax+00h]
0x18001539b  int     3; Trap to Debugger
0x18001539c  add     rsp, 28h
0x1800153a0  retn
```
