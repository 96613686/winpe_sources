# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18001bc9c`
- end: `0x18001bced`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `81`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180011b00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001bce1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bcb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bcb7`

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
0x18001bc9c  mov     [rsp+arg_0], rbx
0x18001bca1  mov     [rsp+arg_8], rsi
0x18001bca6  push    rdi
0x18001bca7  sub     rsp, 20h
0x18001bcab  mov     rbx, rcx
0x18001bcae  mov     edi, r8d
0x18001bcb1  mov     rcx, [rcx]; string
0x18001bcb4  mov     rsi, rdx
0x18001bcb7  call    cs:__imp_WindowsDeleteString
0x18001bcbe  nop     dword ptr [rax+rax+00h]
0x18001bcc3  mov     r8, rbx
0x18001bcc6  mov     qword ptr [rbx], 0
0x18001bccd  mov     edx, edi
0x18001bccf  mov     rcx, rsi
0x18001bcd2  mov     rbx, [rsp+28h+arg_0]
0x18001bcd7  mov     rsi, [rsp+28h+arg_8]
0x18001bcdc  add     rsp, 20h
0x18001bce0  pop     rdi
0x18001bce1  jmp     cs:__imp_WindowsCreateString
```
