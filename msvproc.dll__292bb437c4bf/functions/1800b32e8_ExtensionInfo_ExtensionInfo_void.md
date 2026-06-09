# ExtensionInfo::~ExtensionInfo(void)

- ea: `0x1800b32e8`
- end: `0x1800b333d`
- name: `??1ExtensionInfo@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(ExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800b3374`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b32f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b332a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b32f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b332a`

## pseudocode

```c
void __fastcall ExtensionInfo::~ExtensionInfo(HSTRING *this)
{
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x1800b32e8  push    rbx
0x1800b32ea  sub     rsp, 20h
0x1800b32ee  mov     rbx, rcx
0x1800b32f1  mov     rcx, [rcx+18h]; string
0x1800b32f5  call    cs:__imp_WindowsDeleteString
0x1800b32fb  mov     qword ptr [rbx+18h], 0
0x1800b3303  mov     rcx, [rbx+10h]; string
0x1800b3307  call    cs:__imp_WindowsDeleteString
0x1800b330d  mov     qword ptr [rbx+10h], 0
0x1800b3315  mov     rcx, [rbx+8]; string
0x1800b3319  call    cs:__imp_WindowsDeleteString
0x1800b331f  mov     qword ptr [rbx+8], 0
0x1800b3327  mov     rcx, [rbx]; string
0x1800b332a  call    cs:__imp_WindowsDeleteString
0x1800b3330  mov     qword ptr [rbx], 0
0x1800b3337  add     rsp, 20h
0x1800b333b  pop     rbx
0x1800b333c  retn
```
