# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000a4d8`
- end: `0x18000a4fe`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180023165`
- `0x180023177`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a4e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a4e4`

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
0x18000a4d8  push    rbx
0x18000a4da  sub     rsp, 20h
0x18000a4de  mov     rbx, rcx
0x18000a4e1  mov     rcx, [rcx]; string
0x18000a4e4  call    cs:__imp_WindowsDeleteString
0x18000a4eb  nop     dword ptr [rax+rax+00h]
0x18000a4f0  mov     qword ptr [rbx], 0
0x18000a4f7  add     rsp, 20h
0x18000a4fb  pop     rbx
0x18000a4fc  retn
```
