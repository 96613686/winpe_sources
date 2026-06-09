# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x140012474`
- end: `0x14001249a`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140019a4e`
- `0x140019b2c`
- `0x140019b74`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012480`

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
0x140012474  push    rbx
0x140012476  sub     rsp, 20h
0x14001247a  mov     rbx, rcx
0x14001247d  mov     rcx, [rcx]; string
0x140012480  call    cs:__imp_WindowsDeleteString
0x140012487  nop     dword ptr [rax+rax+00h]
0x14001248c  mov     qword ptr [rbx], 0
0x140012493  add     rsp, 20h
0x140012497  pop     rbx
0x140012498  retn
```
