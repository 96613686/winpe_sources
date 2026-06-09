# OpenFileForRead

- ea: `0x180147374`
- end: `0x1801473ec`
- name: `OpenFileForRead`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1801474c0`

## callees

- `0x180147374`
- `0x18015c080`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801473a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801473a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801473b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801473b4`

## pseudocode

```c
__int64 __fastcall OpenFileForRead(const WCHAR *a1, _QWORD *a2)
{
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 v5; // rcx
  unsigned int v6; // r10d
  unsigned int v7; // r10d

  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    LogErrorFxn(v5, v6);
  }
  else
  {
    *a2 = FileW;
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180147374  push    rbx
0x180147376  sub     rsp, 40h
0x18014737a  xor     r9d, r9d; lpSecurityAttributes
0x18014737d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180147386  mov     rbx, rdx
0x180147389  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180147391  mov     edx, 80000000h; dwDesiredAccess
0x180147396  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18014739e  lea     r8d, [r9+7]; dwShareMode
0x1801473a2  call    cs:__imp_CreateFileW
0x1801473a9  nop     dword ptr [rax+rax+00h]
0x1801473ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801473b2  jnz     short loc_1801473DC
0x1801473b4  call    cs:__imp_GetLastError
0x1801473bb  nop     dword ptr [rax+rax+00h]
0x1801473c0  mov     r10d, eax
0x1801473c3  test    eax, eax
0x1801473c5  jle     short loc_1801473D2
0x1801473c7  movzx   r10d, ax
0x1801473cb  or      r10d, 80070000h
0x1801473d2  mov     edx, r10d
0x1801473d5  call    LogErrorFxn
0x1801473da  jmp     short loc_1801473E2
0x1801473dc  mov     [rbx], rax
0x1801473df  xor     r10d, r10d
0x1801473e2  mov     eax, r10d
0x1801473e5  add     rsp, 40h
0x1801473e9  pop     rbx
0x1801473ea  retn
```
