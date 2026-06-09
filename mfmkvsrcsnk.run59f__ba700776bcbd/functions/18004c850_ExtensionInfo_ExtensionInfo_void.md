# ExtensionInfo::~ExtensionInfo(void)

- ea: `0x18004c850`
- end: `0x18004c8be`
- name: `??1ExtensionInfo@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(ExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18004c8c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c88d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c88d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8a4`

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
0x18004c850  push    rbx
0x18004c852  sub     rsp, 20h
0x18004c856  mov     rbx, rcx
0x18004c859  mov     rcx, [rcx+18h]; string
0x18004c85d  call    cs:__imp_WindowsDeleteString
0x18004c864  nop     dword ptr [rax+rax+00h]
0x18004c869  mov     qword ptr [rbx+18h], 0
0x18004c871  mov     rcx, [rbx+10h]; string
0x18004c875  call    cs:__imp_WindowsDeleteString
0x18004c87c  nop     dword ptr [rax+rax+00h]
0x18004c881  mov     qword ptr [rbx+10h], 0
0x18004c889  mov     rcx, [rbx+8]; string
0x18004c88d  call    cs:__imp_WindowsDeleteString
0x18004c894  nop     dword ptr [rax+rax+00h]
0x18004c899  mov     qword ptr [rbx+8], 0
0x18004c8a1  mov     rcx, [rbx]; string
0x18004c8a4  call    cs:__imp_WindowsDeleteString
0x18004c8ab  nop     dword ptr [rax+rax+00h]
0x18004c8b0  mov     qword ptr [rbx], 0
0x18004c8b7  add     rsp, 20h
0x18004c8bb  pop     rbx
0x18004c8bc  retn
```
