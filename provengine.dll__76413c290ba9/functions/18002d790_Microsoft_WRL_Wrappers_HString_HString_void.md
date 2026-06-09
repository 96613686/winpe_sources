# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18002d790`
- end: `0x18002d7af`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180045b34`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d79c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d79c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::WRL::Wrappers::HString::~HString(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18002d790  push    rbx
0x18002d792  sub     rsp, 20h
0x18002d796  mov     rbx, rcx
0x18002d799  mov     rcx, [rcx]; string
0x18002d79c  call    cs:__imp_WindowsDeleteString
0x18002d7a2  mov     qword ptr [rbx], 0
0x18002d7a9  add     rsp, 20h
0x18002d7ad  pop     rbx
0x18002d7ae  retn
```
