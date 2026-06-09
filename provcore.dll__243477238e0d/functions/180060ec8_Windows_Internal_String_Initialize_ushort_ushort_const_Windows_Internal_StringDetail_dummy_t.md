# Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x180060ec8`
- end: `0x180060f5e`
- name: `??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z`
- size: `150`
- prototype: `__int64 __fastcall(Windows::Internal::String *this, const wchar_t **str, Windows::Internal::_StringDetail::dummy_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006230c`

## callees

- `0x180002790`
- `0x180060ec8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180060f14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180060f14`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize<unsigned short *>(
        Windows::Internal::String *this,
        const wchar_t **str,
        Windows::Internal::_StringDetail::dummy_t a3)
{
  const wchar_t *v4; // rcx
  unsigned __int64 v5; // rdx
  HRESULT v6; // ebx
  HSTRING__ *hstring; // rcx
  HSTRING string; // [rsp+20h] [rbp-18h] BYREF

  v4 = *str;
  if ( *str )
  {
    string = 0;
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    if ( v5 > 0xFFFFFFFF )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v6 = WindowsCreateString(v4, v5, &string);
      if ( v6 >= 0 )
      {
        hstring = this->_hstring;
        this->_hstring = string;
        WindowsDeleteString(hstring);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180060ec8  mov     [rsp+arg_10], rbx
0x180060ecd  mov     [rsp+arg_18], rsi
0x180060ed2  push    rdi
0x180060ed3  sub     rsp, 30h
0x180060ed7  mov     rax, cs:__security_cookie
0x180060ede  xor     rax, rsp
0x180060ee1  mov     [rsp+38h+var_10], rax
0x180060ee6  mov     rdi, this
0x180060ee9  xor     esi, esi
0x180060eeb  mov     this, [str]; sourceString
0x180060eee  test    this, this
0x180060ef1  jz      short loc_180060F3A
0x180060ef3  mov     [rsp+38h+string], rsi
0x180060ef8  or      str, 0FFFFFFFFFFFFFFFFh
0x180060efc  inc     str; length
0x180060eff  cmp     [this+str*2], si
0x180060f03  jnz     short loc_180060EFC
0x180060f05  mov     eax, 0FFFFFFFFh
0x180060f0a  cmp     str, rax
0x180060f0d  ja      short loc_180060F33
0x180060f0f  lea     r8, [rsp+38h+string]; string
0x180060f14  call    cs:__imp_WindowsCreateString
0x180060f1a  mov     ebx, eax
0x180060f1c  test    eax, eax
0x180060f1e  js      short loc_180060F3F
0x180060f20  mov     str, [rsp+38h+string]
0x180060f25  mov     this, [rdi]; string
0x180060f28  mov     [rdi], str
0x180060f2b  call    cs:__imp_WindowsDeleteString
0x180060f31  jmp     short loc_180060F3F
0x180060f33  mov     ebx, 80070216h
0x180060f38  jmp     short loc_180060F3F
0x180060f3a  mov     ebx, 80004003h
0x180060f3f  mov     eax, ebx
0x180060f41  mov     this, [rsp+38h+var_10]
0x180060f46  xor     this, rsp; StackCookie
0x180060f49  call    __security_check_cookie
0x180060f4e  mov     rbx, [rsp+38h+arg_10]
0x180060f53  mov     rsi, [rsp+38h+arg_18]
0x180060f58  add     rsp, 30h
0x180060f5c  pop     rdi
0x180060f5d  retn
```
