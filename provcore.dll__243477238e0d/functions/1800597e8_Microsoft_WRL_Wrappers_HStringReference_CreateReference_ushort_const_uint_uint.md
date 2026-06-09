# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800597e8`
- end: `0x180059829`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *this, const wchar_t *str, unsigned int bufferLen, unsigned int len)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005b350`
- `0x18005dc18`
- `0x1800678c8`

## callees

- `0x1800597e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005981d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005981d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180059807`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180059807`

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
0x1800597e8  sub     rsp, 28h
0x1800597ec  mov     eax, len
0x1800597ef  mov     r10, str
0x1800597f2  cmp     len, bufferLen
0x1800597f5  jb      short loc_1800597FB
0x1800597f7  lea     eax, [r8-1]
0x1800597fb  lea     r9, [this+18h]; string
0x1800597ff  mov     r8, this; hstringHeader
0x180059802  mov     this, r10; sourceString
0x180059805  mov     edx, eax; length
0x180059807  call    cs:__imp_WindowsCreateStringReference
0x18005980d  test    eax, eax
0x18005980f  jns     short loc_180059824
0x180059811  xor     len, len; lpArguments
0x180059814  xor     bufferLen, bufferLen; nNumberOfArguments
0x180059817  mov     ecx, eax; dwExceptionCode
0x180059819  lea     edx, [r9+1]; dwExceptionFlags
0x18005981d  call    cs:__imp_RaiseException
0x180059823  int     3; Trap to Debugger
0x180059824  add     rsp, 28h
0x180059828  retn
```
