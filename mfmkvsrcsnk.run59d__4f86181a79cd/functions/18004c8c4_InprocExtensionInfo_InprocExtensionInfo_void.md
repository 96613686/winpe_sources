# InprocExtensionInfo::~InprocExtensionInfo(void)

- ea: `0x18004c8c4`
- end: `0x18004c90a`
- name: `??1InprocExtensionInfo@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(InprocExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004c910`

## callees

- `0x18004c850`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8e9`

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
0x18004c8c4  push    rbx
0x18004c8c6  sub     rsp, 20h
0x18004c8ca  mov     rbx, rcx
0x18004c8cd  mov     rcx, [rcx+38h]; string
0x18004c8d1  call    cs:__imp_WindowsDeleteString
0x18004c8d8  nop     dword ptr [rax+rax+00h]
0x18004c8dd  mov     qword ptr [rbx+38h], 0
0x18004c8e5  mov     rcx, [rbx+30h]; string
0x18004c8e9  call    cs:__imp_WindowsDeleteString
0x18004c8f0  nop     dword ptr [rax+rax+00h]
0x18004c8f5  mov     rcx, rbx; this
0x18004c8f8  mov     qword ptr [rbx+30h], 0
0x18004c900  add     rsp, 20h
0x18004c904  pop     rbx
0x18004c905  jmp     ??1ExtensionInfo@@QEAA@XZ; ExtensionInfo::~ExtensionInfo(void)
```
