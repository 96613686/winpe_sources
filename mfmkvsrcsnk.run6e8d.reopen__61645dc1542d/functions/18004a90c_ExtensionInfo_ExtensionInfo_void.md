# ExtensionInfo::~ExtensionInfo(void)

- ea: `0x18004a90c`
- end: `0x18004a961`
- name: `??1ExtensionInfo@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(ExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18004a968`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a919`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a94e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a919`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a94e`

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
0x18004a90c  push    rbx
0x18004a90e  sub     rsp, 20h
0x18004a912  mov     rbx, rcx
0x18004a915  mov     rcx, [rcx+18h]; string
0x18004a919  call    cs:__imp_WindowsDeleteString
0x18004a91f  mov     qword ptr [rbx+18h], 0
0x18004a927  mov     rcx, [rbx+10h]; string
0x18004a92b  call    cs:__imp_WindowsDeleteString
0x18004a931  mov     qword ptr [rbx+10h], 0
0x18004a939  mov     rcx, [rbx+8]; string
0x18004a93d  call    cs:__imp_WindowsDeleteString
0x18004a943  mov     qword ptr [rbx+8], 0
0x18004a94b  mov     rcx, [rbx]; string
0x18004a94e  call    cs:__imp_WindowsDeleteString
0x18004a954  mov     qword ptr [rbx], 0
0x18004a95b  add     rsp, 20h
0x18004a95f  pop     rbx
0x18004a960  retn
```
