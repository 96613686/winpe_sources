# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800ec89c`
- end: `0x1800ec8dd`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *this, const wchar_t *str, unsigned int bufferLen, unsigned int len)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800eb5b4`
- `0x1800ed6c0`

## callees

- `0x1800ec89c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ec8d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ec8d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ec8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ec8bb`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        Microsoft::WRL::Wrappers::HStringReference *this,
        const wchar_t *str,
        UINT32 bufferLen,
        UINT32 len)
{
  UINT32 v4; // eax
  signed int StringReference; // eax

  v4 = len;
  if ( len >= bufferLen )
    v4 = bufferLen - 1;
  StringReference = WindowsCreateStringReference(str, v4, &this->header_, &this->hstr_);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x1800ec89c  sub     rsp, 28h
0x1800ec8a0  mov     eax, len
0x1800ec8a3  mov     r10, str
0x1800ec8a6  cmp     len, bufferLen
0x1800ec8a9  jb      short loc_1800EC8AF
0x1800ec8ab  lea     eax, [r8-1]
0x1800ec8af  lea     r9, [this+18h]; string
0x1800ec8b3  mov     r8, this; hstringHeader
0x1800ec8b6  mov     this, r10; sourceString
0x1800ec8b9  mov     edx, eax; length
0x1800ec8bb  call    cs:__imp_WindowsCreateStringReference
0x1800ec8c1  test    eax, eax
0x1800ec8c3  jns     short loc_1800EC8D8
0x1800ec8c5  xor     len, len; lpArguments
0x1800ec8c8  xor     bufferLen, bufferLen; nNumberOfArguments
0x1800ec8cb  mov     ecx, eax; dwExceptionCode
0x1800ec8cd  lea     edx, [r9+1]; dwExceptionFlags
0x1800ec8d1  call    cs:__imp_RaiseException
0x1800ec8d7  int     3; Trap to Debugger
0x1800ec8d8  add     rsp, 28h
0x1800ec8dc  retn
```
