# MapMUIFile

- ea: `0x180006830`
- end: `0x180006914`
- name: `MapMUIFile`
- size: `228`
- prototype: `HMODULE __fastcall(const WCHAR *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180006a80`
- `0x180006b68`

## callees

- `0x180006830`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1800068a3`
- `KERNEL32!CreateFileMappingW` at `0x1800068a3`
- `KERNEL32!CloseHandle` at `0x1800068af`
- `KERNEL32!CloseHandle` at `0x1800068dc`
- `KERNEL32!CloseHandle` at `0x1800068af`
- `KERNEL32!CloseHandle` at `0x1800068dc`
- `KERNEL32!CreateFileW` at `0x180006873`
- `KERNEL32!CreateFileW` at `0x180006873`
- `KERNEL32!MapViewOfFile` at `0x1800068d0`
- `KERNEL32!MapViewOfFile` at `0x1800068d0`
- `KERNEL32!LoadLibraryExW` at `0x1800068ff`
- `KERNEL32!LoadLibraryExW` at `0x1800068ff`

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
0x180006830  mov     [rsp+arg_0], rbx
0x180006835  push    rdi
0x180006836  sub     rsp, 40h
0x18000683a  mov     eax, r8d
0x18000683d  test    rcx, rcx
0x180006840  jz      loc_180006907
0x180006846  test    edx, edx
0x180006848  jz      loc_1800068F4
0x18000684e  xor     r9d, r9d; lpSecurityAttributes
0x180006851  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000685a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180006862  mov     edx, 80000000h; dwDesiredAccess
0x180006867  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000686f  lea     r8d, [r9+5]; dwShareMode
0x180006873  call    cs:__imp_CreateFileW
0x180006879  mov     rbx, rax
0x18000687c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006880  jz      loc_180006907
0x180006886  xor     r9d, r9d; dwMaximumSizeHigh
0x180006889  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180006892  xor     edx, edx; lpFileMappingAttributes
0x180006894  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000689c  mov     rcx, rax; hFile
0x18000689f  lea     r8d, [r9+8]; flProtect
0x1800068a3  call    cs:__imp_CreateFileMappingW
0x1800068a9  mov     rcx, rbx; hObject
0x1800068ac  mov     rdi, rax
0x1800068af  call    cs:__imp_CloseHandle
0x1800068b5  test    rdi, rdi
0x1800068b8  jz      short loc_180006907
0x1800068ba  xor     r9d, r9d; dwFileOffsetLow
0x1800068bd  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800068c6  xor     r8d, r8d; dwFileOffsetHigh
0x1800068c9  mov     rcx, rdi; hFileMappingObject
0x1800068cc  lea     edx, [r9+1]; dwDesiredAccess
0x1800068d0  call    cs:__imp_MapViewOfFile
0x1800068d6  mov     rcx, rdi; hObject
0x1800068d9  mov     rbx, rax
0x1800068dc  call    cs:__imp_CloseHandle
0x1800068e2  mov     rcx, rbx
0x1800068e5  or      rcx, 1; lpLibFileName
0x1800068e9  neg     rbx
0x1800068ec  sbb     rax, rax
0x1800068ef  and     rax, rcx
0x1800068f2  jmp     short loc_180006909
0x1800068f4  xor     r8d, r8d
0x1800068f7  test    eax, eax
0x1800068f9  setnz   r8b; dwFlags
0x1800068fd  xor     edx, edx; hFile
0x1800068ff  call    cs:__imp_LoadLibraryExW
0x180006905  jmp     short loc_180006909
0x180006907  xor     eax, eax
0x180006909  mov     rbx, [rsp+48h+arg_0]
0x18000690e  add     rsp, 40h
0x180006912  pop     rdi
0x180006913  retn
```
