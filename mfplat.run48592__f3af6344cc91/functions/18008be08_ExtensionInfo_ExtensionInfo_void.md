# ExtensionInfo::~ExtensionInfo(void)

- ea: `0x18008be08`
- end: `0x18008be5d`
- name: `??1ExtensionInfo@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(ExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800ac504`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008be4a`

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
0x18008be08  push    rbx
0x18008be0a  sub     rsp, 20h
0x18008be0e  mov     rbx, rcx
0x18008be11  mov     rcx, [rcx+18h]; string
0x18008be15  call    cs:__imp_WindowsDeleteString
0x18008be1b  mov     qword ptr [rbx+18h], 0
0x18008be23  mov     rcx, [rbx+10h]; string
0x18008be27  call    cs:__imp_WindowsDeleteString
0x18008be2d  mov     qword ptr [rbx+10h], 0
0x18008be35  mov     rcx, [rbx+8]; string
0x18008be39  call    cs:__imp_WindowsDeleteString
0x18008be3f  mov     qword ptr [rbx+8], 0
0x18008be47  mov     rcx, [rbx]; string
0x18008be4a  call    cs:__imp_WindowsDeleteString
0x18008be50  mov     qword ptr [rbx], 0
0x18008be57  add     rsp, 20h
0x18008be5b  pop     rbx
0x18008be5c  retn
```
