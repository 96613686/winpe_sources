# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x14000fc68`
- end: `0x14000fc87`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001e470`
- `0x14001e80a`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000fc74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000fc74`

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
0x14000fc68  push    rbx
0x14000fc6a  sub     rsp, 20h
0x14000fc6e  mov     rbx, rcx
0x14000fc71  mov     rcx, [rcx]; string
0x14000fc74  call    cs:__imp_WindowsDeleteString
0x14000fc7a  mov     qword ptr [rbx], 0
0x14000fc81  add     rsp, 20h
0x14000fc85  pop     rbx
0x14000fc86  retn
```
