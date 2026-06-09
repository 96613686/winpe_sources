# OpenDisk(ushort const *,ulong)

- ea: `0x180028830`
- end: `0x1800288b1`
- name: `?OpenDisk@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGK@Z`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014c20`
- `0x180015670`

## callees

- `0x1800136f8`
- `0x180028830`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002886e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002886e`

## string_xrefs

- `0x18002889f`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall OpenDisk(_QWORD *a1, const WCHAR *a2)
{
  HANDLE FileW; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  FileW = CreateFileW(a2, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
  *a1 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      v4);
  return a1;
}

```

## disassembly

```asm
0x180028830  mov     [rsp+arg_0], rcx
0x180028835  push    rbx
0x180028836  sub     rsp, 50h
0x18002883a  mov     rax, rdx
0x18002883d  mov     rbx, rcx
0x180028840  mov     [rsp+58h+var_18], 0
0x180028848  xor     ecx, ecx
0x18002884a  mov     [rbx], rcx
0x18002884d  mov     [rsp+58h+hTemplateFile], rcx; hTemplateFile
0x180028852  mov     [rsp+58h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18002885a  lea     r8d, [rcx+3]; dwShareMode
0x18002885e  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180028863  xor     r9d, r9d; lpSecurityAttributes
0x180028866  mov     edx, 0C0000000h; dwDesiredAccess
0x18002886b  mov     rcx, rax; lpFileName
0x18002886e  call    cs:__imp_CreateFileW
0x180028875  nop     dword ptr [rax+rax+00h]
0x18002887a  mov     [rbx], rax
0x18002887d  mov     [rsp+58h+var_18], 1
0x180028885  inc     rax
0x180028888  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002888e  jz      short loc_18002889A
0x180028890  mov     rax, rbx
0x180028893  add     rsp, 50h
0x180028897  pop     rbx
0x180028898  retn
0x18002889a  mov     rcx, [rsp+58h]; this
0x18002889f  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800288a6  mov     edx, 1FCh; void *
0x1800288ab  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
