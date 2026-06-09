# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180022348`
- end: `0x18002236e`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004c750`
- `0x18004c762`
- `0x18004c774`
- `0x18004c95a`
- `0x18004ca0e`
- `0x18004ca20`
- `0x18004ca32`
- `0x18004ca44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022354`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HString::~HString(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x180022348  push    rbx
0x18002234a  sub     rsp, 20h
0x18002234e  mov     rbx, rcx
0x180022351  mov     rcx, [rcx]; string
0x180022354  call    cs:__imp_WindowsDeleteString
0x18002235b  nop     dword ptr [rax+rax+00h]
0x180022360  mov     qword ptr [rbx], 0
0x180022367  add     rsp, 20h
0x18002236b  pop     rbx
0x18002236c  retn
```
