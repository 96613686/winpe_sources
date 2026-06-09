# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18006af48`
- end: `0x18006af99`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `81`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18006a9f0`
- `0x18006b190`
- `0x1800d7998`
- `0x1800ed64c`
- `0x1801f9cc8`
- `0x1801f9d48`
- `0x1801fa200`
- `0x1801fb364`
- `0x18020947c`
- `0x18027abe4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006af63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006af63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006af8d`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *this, const unsigned __int16 *a2, UINT32 a3)
{
  WindowsDeleteString(*this);
  *this = 0;
  return WindowsCreateString(a2, a3, this);
}

```

## disassembly

```asm
0x18006af48  mov     [rsp+arg_0], rbx
0x18006af4d  mov     [rsp+arg_8], rsi
0x18006af52  push    rdi
0x18006af53  sub     rsp, 20h
0x18006af57  mov     rbx, rcx
0x18006af5a  mov     edi, r8d
0x18006af5d  mov     rcx, [rcx]; string
0x18006af60  mov     rsi, rdx
0x18006af63  call    cs:__imp_WindowsDeleteString
0x18006af6a  nop     dword ptr [rax+rax+00h]
0x18006af6f  mov     r8, rbx
0x18006af72  mov     qword ptr [rbx], 0
0x18006af79  mov     edx, edi
0x18006af7b  mov     rcx, rsi
0x18006af7e  mov     rbx, [rsp+28h+arg_0]
0x18006af83  mov     rsi, [rsp+28h+arg_8]
0x18006af88  add     rsp, 20h
0x18006af8c  pop     rdi
0x18006af8d  jmp     cs:__imp_WindowsCreateString
```
