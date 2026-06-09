# CopyOpenFileToCache(_PROCESS_ENTRY *,void *,ushort *,int,ushort const *)

- ea: `0x1801a8c98`
- end: `0x1801a8d66`
- name: `?CopyOpenFileToCache@@YAPEAXPEAU_PROCESS_ENTRY@@PEAXPEAGHPEBG@Z`
- size: `206`
- prototype: `void *(struct _PROCESS_ENTRY *, void *, unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800120f0`
- `0x1801a8ed0`

## callees

- `0x180012e6c`
- `0x1801a16d0`
- `0x1801a8c98`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a8d3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a8d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8cfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8cfc`

## pseudocode

```c
HANDLE __fastcall CopyOpenFileToCache(HANDLE *a1, void *a2, unsigned __int16 *a3, __int64 a4, unsigned __int16 *a5)
{
  DWORD v7; // r8d
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !a1 || !(unsigned int)CopyToCache(a1[6], a3, a5, FileName, 261) )
    return a2;
  wcscpy_s_ex(a3, 0x105u, FileName);
  CloseHandle(a2);
  v7 = 3;
  if ( dword_1802AF874 == 2 )
    v7 = 7;
  return CreateFileW(FileName, 0x80000000, v7, 0, 3u, 0, 0);
}

```

## disassembly

```asm
0x1801a8c98  mov     [rsp+arg_18], rbx
0x1801a8c9d  push    rdi
0x1801a8c9e  sub     rsp, 260h
0x1801a8ca5  mov     rax, cs:__security_cookie
0x1801a8cac  xor     rax, rsp
0x1801a8caf  mov     [rsp+268h+var_18], rax
0x1801a8cb7  mov     rdi, r8
0x1801a8cba  mov     r8, [rsp+268h+arg_20]; unsigned __int16 *
0x1801a8cc2  mov     rbx, rdx
0x1801a8cc5  test    rcx, rcx
0x1801a8cc8  jz      short loc_1801A8D42
0x1801a8cca  mov     rcx, [rcx+30h]; hProcess
0x1801a8cce  lea     r9, [rsp+268h+FileName]; unsigned __int16 *
0x1801a8cd3  mov     rdx, rdi; unsigned __int16 *
0x1801a8cd6  mov     [rsp+268h+dwCreationDisposition], 105h; int
0x1801a8cde  call    ?CopyToCache@@YAHPEAXPEBG1PEAGH@Z; CopyToCache(void *,ushort const *,ushort const *,ushort *,int)
0x1801a8ce3  test    eax, eax
0x1801a8ce5  jz      short loc_1801A8D42
0x1801a8ce7  lea     r8, [rsp+268h+FileName]; unsigned __int16 *
0x1801a8cec  mov     edx, 105h; unsigned __int64
0x1801a8cf1  mov     rcx, rdi; unsigned __int16 *
0x1801a8cf4  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8cf9  mov     rcx, rbx; hObject
0x1801a8cfc  call    cs:__imp_CloseHandle
0x1801a8d02  cmp     cs:dword_1802AF874, 2
0x1801a8d09  mov     ecx, 3
0x1801a8d0e  mov     r8d, ecx
0x1801a8d11  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x1801a8d1a  mov     [rsp+268h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801a8d22  mov     edx, 80000000h; dwDesiredAccess
0x1801a8d27  mov     [rsp+268h+dwCreationDisposition], ecx; dwCreationDisposition
0x1801a8d2b  lea     eax, [rcx+4]
0x1801a8d2e  cmovz   r8d, eax; dwShareMode
0x1801a8d32  lea     rcx, [rsp+268h+FileName]; lpFileName
0x1801a8d37  xor     r9d, r9d; lpSecurityAttributes
0x1801a8d3a  call    cs:__imp_CreateFileW
0x1801a8d40  jmp     short loc_1801A8D45
0x1801a8d42  mov     rax, rbx
0x1801a8d45  mov     rcx, [rsp+268h+var_18]
0x1801a8d4d  xor     rcx, rsp; StackCookie
0x1801a8d50  call    __security_check_cookie
0x1801a8d55  mov     rbx, [rsp+268h+arg_18]
0x1801a8d5d  add     rsp, 260h
0x1801a8d64  pop     rdi
0x1801a8d65  retn
```
