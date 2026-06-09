# InprocExtensionInfo::~InprocExtensionInfo(void)

- ea: `0x18004a968`
- end: `0x18004a9a2`
- name: `??1InprocExtensionInfo@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(InprocExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004a9a8`

## callees

- `0x18004a90c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a987`

## pseudocode

```c
void __fastcall InprocExtensionInfo::~InprocExtensionInfo(HSTRING *this)
{
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  ExtensionInfo::~ExtensionInfo(this);
}

```

## disassembly

```asm
0x18004a968  push    rbx
0x18004a96a  sub     rsp, 20h
0x18004a96e  mov     rbx, rcx
0x18004a971  mov     rcx, [rcx+38h]; string
0x18004a975  call    cs:__imp_WindowsDeleteString
0x18004a97b  mov     qword ptr [rbx+38h], 0
0x18004a983  mov     rcx, [rbx+30h]; string
0x18004a987  call    cs:__imp_WindowsDeleteString
0x18004a98d  mov     rcx, rbx; this
0x18004a990  mov     qword ptr [rbx+30h], 0
0x18004a998  add     rsp, 20h
0x18004a99c  pop     rbx
0x18004a99d  jmp     ??1ExtensionInfo@@QEAA@XZ; ExtensionInfo::~ExtensionInfo(void)
```
