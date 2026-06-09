# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18008af34`
- end: `0x18008af7a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18008a400`
- `0x18008a908`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008af4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008af4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008af73`

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
0x18008af34  mov     [rsp+arg_0], rbx
0x18008af39  mov     [rsp+arg_8], rsi
0x18008af3e  push    rdi
0x18008af3f  sub     rsp, 20h
0x18008af43  mov     rbx, rcx
0x18008af46  mov     edi, r8d
0x18008af49  mov     rcx, [rcx]; string
0x18008af4c  mov     rsi, rdx
0x18008af4f  call    cs:__imp_WindowsDeleteString
0x18008af55  mov     r8, rbx
0x18008af58  mov     qword ptr [rbx], 0
0x18008af5f  mov     edx, edi
0x18008af61  mov     rcx, rsi
0x18008af64  mov     rbx, [rsp+28h+arg_0]
0x18008af69  mov     rsi, [rsp+28h+arg_8]
0x18008af6e  add     rsp, 20h
0x18008af72  pop     rdi
0x18008af73  jmp     cs:__imp_WindowsCreateString
```
