# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001597c`
- end: `0x1800159cc`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `80`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *this, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c5c4`
- `0x1800440d0`

## callees

- `0x18001597c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800159bf`
- `KERNEL32!RaiseException` at `0x1800159bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015997`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        Microsoft::WRL::Wrappers::HStringReference *this,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  signed int StringReference; // eax

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, &this->header_, &this->hstr_);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
    JUMPOUT(0x1800159CCLL);
  }
}

```

## disassembly

```asm
0x18001597c  sub     rsp, 28h
0x180015980  mov     eax, r9d
0x180015983  mov     r10, rdx
0x180015986  cmp     r9d, r8d
0x180015989  jnb     short loc_1800159AD
0x18001598b  lea     r9, [rcx+18h]; string
0x18001598f  mov     r8, rcx; hstringHeader
0x180015992  mov     rcx, r10; sourceString
0x180015995  mov     edx, eax; length
0x180015997  call    cs:__imp_WindowsCreateStringReference
0x18001599e  nop     dword ptr [rax+rax+00h]
0x1800159a3  test    eax, eax
0x1800159a5  js      short loc_1800159B3
0x1800159a7  add     rsp, 28h
0x1800159ab  retn
0x1800159ad  lea     eax, [r8-1]
0x1800159b1  jmp     short loc_18001598B
0x1800159b3  xor     r9d, r9d; lpArguments
0x1800159b6  xor     r8d, r8d; nNumberOfArguments
0x1800159b9  mov     ecx, eax; dwExceptionCode
0x1800159bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800159bf  call    cs:__imp_RaiseException
0x1800159c6  nop     dword ptr [rax+rax+00h]
0x1800159cb  int     3; Trap to Debugger
```
