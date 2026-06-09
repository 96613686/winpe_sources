# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800094a4`
- end: `0x1800094c3`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000cb9d`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800094b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800094b0`

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
0x1800094a4  push    rbx
0x1800094a6  sub     rsp, 20h
0x1800094aa  mov     rbx, rcx
0x1800094ad  mov     rcx, [rcx]; string
0x1800094b0  call    cs:__imp_WindowsDeleteString
0x1800094b6  mov     qword ptr [rbx], 0
0x1800094bd  add     rsp, 20h
0x1800094c1  pop     rbx
0x1800094c2  retn
```
