# Windows::Internal::String::Initialize(ushort const *,uint)

- ea: `0x18007304c`
- end: `0x18007309c`
- name: `?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z`
- size: `80`
- prototype: `HRESULT __fastcall(Windows::Internal::String *this, const wchar_t *str, unsigned int length)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180072e38`
- `0x1800a8ad0`

## callees

- `0x18007304c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180073072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180073072`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(
        Windows::Internal::String *this,
        const wchar_t *str,
        UINT32 length)
{
  HRESULT v4; // edi
  HSTRING__ *hstring; // rcx
  HSTRING__ *local; // [rsp+30h] [rbp+8h] BYREF

  local = 0;
  v4 = WindowsCreateString(str, length, &local);
  if ( v4 >= 0 )
  {
    hstring = this->_hstring;
    this->_hstring = local;
    WindowsDeleteString(hstring);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007304c  mov     [rsp+arg_8], rbx
0x180073051  push    rdi
0x180073052  sub     rsp, 20h
0x180073056  mov     eax, length
0x180073059  mov     [rsp+28h+local], 0
0x180073062  mov     r9, str
0x180073065  lea     r8, [rsp+28h+local]; string
0x18007306a  mov     rbx, this
0x18007306d  mov     edx, eax; length
0x18007306f  mov     this, r9; sourceString
0x180073072  call    cs:__imp_WindowsCreateString
0x180073078  mov     edi, eax
0x18007307a  test    eax, eax
0x18007307c  js      short loc_18007308F
0x18007307e  mov     str, [rsp+28h+local]
0x180073083  mov     this, [rbx]; string
0x180073086  mov     [rbx], str
0x180073089  call    cs:__imp_WindowsDeleteString
0x18007308f  mov     rbx, [rsp+28h+arg_8]
0x180073094  mov     eax, edi
0x180073096  add     rsp, 20h
0x18007309a  pop     rdi
0x18007309b  retn
```
