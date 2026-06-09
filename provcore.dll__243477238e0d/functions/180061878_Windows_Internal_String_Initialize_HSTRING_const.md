# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x180061878`
- end: `0x1800618df`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `103`
- prototype: `HRESULT __fastcall(Windows::Internal::String *this, HSTRING__ *const *other)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180062bc0`
- `0x180062d00`

## callees

- `0x180002790`
- `0x180061878`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800618a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800618a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800618bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800618bf`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(Windows::Internal::String *this, HSTRING *other)
{
  HRESULT v3; // edi
  HSTRING__ *hstring; // rcx
  HSTRING__ *local; // [rsp+20h] [rbp-18h] BYREF

  local = 0;
  v3 = WindowsDuplicateString(*other, &local);
  if ( v3 >= 0 )
  {
    hstring = this->_hstring;
    this->_hstring = local;
    WindowsDeleteString(hstring);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180061878  mov     [rsp+arg_10], rbx
0x18006187d  push    rdi
0x18006187e  sub     rsp, 30h
0x180061882  mov     rax, cs:__security_cookie
0x180061889  xor     rax, rsp
0x18006188c  mov     [rsp+38h+var_10], rax
0x180061891  mov     rax, other
0x180061894  mov     [rsp+38h+local], 0
0x18006189d  mov     rbx, this
0x1800618a0  lea     other, [rsp+38h+local]; newString
0x1800618a5  mov     this, [rax]; string
0x1800618a8  call    cs:__imp_WindowsDuplicateString
0x1800618ae  mov     edi, eax
0x1800618b0  test    eax, eax
0x1800618b2  js      short loc_1800618C5
0x1800618b4  mov     other, [rsp+38h+local]
0x1800618b9  mov     this, [rbx]; string
0x1800618bc  mov     [rbx], other
0x1800618bf  call    cs:__imp_WindowsDeleteString
0x1800618c5  mov     eax, edi
0x1800618c7  mov     this, [rsp+38h+var_10]
0x1800618cc  xor     this, rsp; StackCookie
0x1800618cf  call    __security_check_cookie
0x1800618d4  mov     rbx, [rsp+38h+arg_10]
0x1800618d9  add     rsp, 30h
0x1800618dd  pop     rdi
0x1800618de  retn
```
