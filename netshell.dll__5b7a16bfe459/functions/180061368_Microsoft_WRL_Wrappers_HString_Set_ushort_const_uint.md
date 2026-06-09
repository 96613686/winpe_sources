# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180061368`
- end: `0x1800613ae`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180060ffc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800613a7`

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
0x180061368  mov     [rsp+arg_0], rbx
0x18006136d  mov     [rsp+arg_8], rsi
0x180061372  push    rdi
0x180061373  sub     rsp, 20h
0x180061377  mov     rbx, rcx
0x18006137a  mov     edi, r8d
0x18006137d  mov     rcx, [rcx]; string
0x180061380  mov     rsi, rdx
0x180061383  call    cs:__imp_WindowsDeleteString
0x180061389  mov     r8, rbx
0x18006138c  mov     qword ptr [rbx], 0
0x180061393  mov     edx, edi
0x180061395  mov     rcx, rsi
0x180061398  mov     rbx, [rsp+28h+arg_0]
0x18006139d  mov     rsi, [rsp+28h+arg_8]
0x1800613a2  add     rsp, 20h
0x1800613a6  pop     rdi
0x1800613a7  jmp     cs:__imp_WindowsCreateString
```
