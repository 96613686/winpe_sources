# InprocExtensionInfo::~InprocExtensionInfo(void)

- ea: `0x1800b3374`
- end: `0x1800b33ae`
- name: `??1InprocExtensionInfo@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(InprocExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b33b4`

## callees

- `0x1800b32e8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3393`

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
0x1800b3374  push    rbx
0x1800b3376  sub     rsp, 20h
0x1800b337a  mov     rbx, rcx
0x1800b337d  mov     rcx, [rcx+38h]; string
0x1800b3381  call    cs:__imp_WindowsDeleteString
0x1800b3387  mov     qword ptr [rbx+38h], 0
0x1800b338f  mov     rcx, [rbx+30h]; string
0x1800b3393  call    cs:__imp_WindowsDeleteString
0x1800b3399  mov     rcx, rbx; this
0x1800b339c  mov     qword ptr [rbx+30h], 0
0x1800b33a4  add     rsp, 20h
0x1800b33a8  pop     rbx
0x1800b33a9  jmp     ??1ExtensionInfo@@QEAA@XZ; ExtensionInfo::~ExtensionInfo(void)
```
