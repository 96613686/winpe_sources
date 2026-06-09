# CLogInfo::_SetLogSize(void)

- ea: `0x180017bc0`
- end: `0x180017c6c`
- name: `?_SetLogSize@CLogInfo@@AEAAXXZ`
- size: `172`
- prototype: `void __fastcall(CLogInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180016ad0`

## callees

- `0x180017bc0`
- `0x18001ea04`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180017c4e`
- `msvcrt!wcscpy_s` at `0x180017c4e`
- `KERNEL32!CreateFileW` at `0x180017bf4`
- `KERNEL32!CreateFileW` at `0x180017bf4`
- `KERNEL32!CloseHandle` at `0x180017c5d`
- `KERNEL32!CloseHandle` at `0x180017c5d`
- `KERNEL32!GetFileSize` at `0x180017c0a`
- `KERNEL32!GetFileSize` at `0x180017c0a`
- `KERNEL32!GetLastError` at `0x180017c17`
- `KERNEL32!GetLastError` at `0x180017c17`

## pseudocode

```c
void __fastcall CLogInfo::_SetLogSize(CLogInfo *this)
{
  HANDLE FileW; // rax
  void *v3; // rbx
  DWORD LastError; // edi
  DWORD FileSize; // ebp

  FileW = CreateFileW((LPCWSTR)this + 538, 0, 3u, 0, 3u, 0, 0);
  v3 = FileW;
  if ( FileW != (HANDLE)-1LL
    && ((LastError = 0, FileSize = GetFileSize(FileW, 0), FileSize != -1) || (LastError = GetLastError()) == 0)
    && (AbbreviateNumber(FileSize, (unsigned __int16 *)this + 2382, 0xAu), !LastError)
    || (wcscpy_s((wchar_t *)this + 2382, 0xAu, L"--"), v3 != (void *)-1LL) )
  {
    CloseHandle(v3);
  }
}

```

## disassembly

```asm
0x180017bc0  push    rbx
0x180017bc2  push    rbp
0x180017bc3  push    rsi
0x180017bc4  push    rdi
0x180017bc5  sub     rsp, 48h
0x180017bc9  mov     rsi, rcx
0x180017bcc  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180017bd5  mov     r8d, 3; dwShareMode
0x180017bdb  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180017be3  add     rcx, 434h; lpFileName
0x180017bea  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x180017bef  xor     r9d, r9d; lpSecurityAttributes
0x180017bf2  xor     edx, edx; dwDesiredAccess
0x180017bf4  call    cs:__imp_CreateFileW
0x180017bfa  mov     rbx, rax
0x180017bfd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017c01  jz      short loc_180017C3B
0x180017c03  xor     edx, edx; lpFileSizeHigh
0x180017c05  mov     rcx, rax; hFile
0x180017c08  xor     edi, edi
0x180017c0a  call    cs:__imp_GetFileSize
0x180017c10  mov     ebp, eax
0x180017c12  cmp     eax, 0FFFFFFFFh
0x180017c15  jnz     short loc_180017C23
0x180017c17  call    cs:__imp_GetLastError
0x180017c1d  mov     edi, eax
0x180017c1f  test    eax, eax
0x180017c21  jnz     short loc_180017C3B
0x180017c23  lea     rdx, [rsi+129Ch]; unsigned __int16 *
0x180017c2a  mov     r8d, 0Ah; unsigned int
0x180017c30  mov     ecx, ebp; unsigned int
0x180017c32  call    ?AbbreviateNumber@@YAXKPEAGK@Z; AbbreviateNumber(ulong,ushort *,ulong)
0x180017c37  test    edi, edi
0x180017c39  jz      short loc_180017C5A
0x180017c3b  lea     rcx, [rsi+129Ch]; Destination
0x180017c42  mov     edx, 0Ah; SizeInWords
0x180017c47  lea     r8, asc_180029514; "--"
0x180017c4e  call    cs:__imp_wcscpy_s
0x180017c54  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180017c58  jz      short loc_180017C63
0x180017c5a  mov     rcx, rbx; hObject
0x180017c5d  call    cs:__imp_CloseHandle
0x180017c63  add     rsp, 48h
0x180017c67  pop     rdi
0x180017c68  pop     rsi
0x180017c69  pop     rbp
0x180017c6a  pop     rbx
0x180017c6b  retn
```
