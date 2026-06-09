# MapMUIFile

- ea: `0x180094644`
- end: `0x18009474d`
- name: `MapMUIFile`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800947a0`
- `0x1800948cc`

## callees

- `0x180094644`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180094731`
- `KERNEL32!LoadLibraryExW` at `0x180094731`
- `KERNEL32!CreateFileW` at `0x180094687`
- `KERNEL32!CreateFileW` at `0x180094687`
- `KERNEL32!CreateFileMappingW` at `0x1800946bd`
- `KERNEL32!CreateFileMappingW` at `0x1800946bd`
- `KERNEL32!MapViewOfFile` at `0x1800946f6`
- `KERNEL32!MapViewOfFile` at `0x1800946f6`
- `KERNEL32!CloseHandle` at `0x1800946cf`
- `KERNEL32!CloseHandle` at `0x180094708`
- `KERNEL32!CloseHandle` at `0x1800946cf`
- `KERNEL32!CloseHandle` at `0x180094708`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180094644  mov     [rsp+arg_0], rbx
0x180094649  push    rdi
0x18009464a  sub     rsp, 40h
0x18009464e  mov     eax, r8d
0x180094651  test    rcx, rcx
0x180094654  jz      loc_18009473F
0x18009465a  test    edx, edx
0x18009465c  jz      loc_180094726
0x180094662  xor     r9d, r9d; lpSecurityAttributes
0x180094665  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18009466e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180094676  mov     edx, 80000000h; dwDesiredAccess
0x18009467b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180094683  lea     r8d, [r9+5]; dwShareMode
0x180094687  call    cs:__imp_CreateFileW
0x18009468e  nop     dword ptr [rax+rax+00h]
0x180094693  mov     rbx, rax
0x180094696  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009469a  jz      loc_18009473F
0x1800946a0  xor     r9d, r9d; dwMaximumSizeHigh
0x1800946a3  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1800946ac  xor     edx, edx; lpFileMappingAttributes
0x1800946ae  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800946b6  mov     rcx, rax; hFile
0x1800946b9  lea     r8d, [r9+8]; flProtect
0x1800946bd  call    cs:__imp_CreateFileMappingW
0x1800946c4  nop     dword ptr [rax+rax+00h]
0x1800946c9  mov     rcx, rbx; hObject
0x1800946cc  mov     rdi, rax
0x1800946cf  call    cs:__imp_CloseHandle
0x1800946d6  nop     dword ptr [rax+rax+00h]
0x1800946db  test    rdi, rdi
0x1800946de  jz      short loc_18009473F
0x1800946e0  xor     r9d, r9d; dwFileOffsetLow
0x1800946e3  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800946ec  xor     r8d, r8d; dwFileOffsetHigh
0x1800946ef  mov     rcx, rdi; hFileMappingObject
0x1800946f2  lea     edx, [r9+1]; dwDesiredAccess
0x1800946f6  call    cs:__imp_MapViewOfFile
0x1800946fd  nop     dword ptr [rax+rax+00h]
0x180094702  mov     rcx, rdi; hObject
0x180094705  mov     rbx, rax
0x180094708  call    cs:__imp_CloseHandle
0x18009470f  nop     dword ptr [rax+rax+00h]
0x180094714  mov     rcx, rbx
0x180094717  or      rcx, 1; lpLibFileName
0x18009471b  neg     rbx
0x18009471e  sbb     rax, rax
0x180094721  and     rax, rcx
0x180094724  jmp     short loc_180094741
0x180094726  xor     r8d, r8d
0x180094729  test    eax, eax
0x18009472b  setnz   r8b; dwFlags
0x18009472f  xor     edx, edx; hFile
0x180094731  call    cs:__imp_LoadLibraryExW
0x180094738  nop     dword ptr [rax+rax+00h]
0x18009473d  jmp     short loc_180094741
0x18009473f  xor     eax, eax
0x180094741  mov     rbx, [rsp+48h+arg_0]
0x180094746  add     rsp, 40h
0x18009474a  pop     rdi
0x18009474b  retn
```
