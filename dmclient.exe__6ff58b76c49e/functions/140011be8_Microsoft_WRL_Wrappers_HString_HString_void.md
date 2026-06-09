# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x140011be8`
- end: `0x140011c07`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140018c1d`
- `0x140018cfb`
- `0x140018d43`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140011bf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140011bf4`

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
0x140011be8  push    rbx
0x140011bea  sub     rsp, 20h
0x140011bee  mov     rbx, rcx
0x140011bf1  mov     rcx, [rcx]; string
0x140011bf4  call    cs:__imp_WindowsDeleteString
0x140011bfa  mov     qword ptr [rbx], 0
0x140011c01  add     rsp, 20h
0x140011c05  pop     rbx
0x140011c06  retn
```
