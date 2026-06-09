# TFile::TFile(ushort const *,TOutput &,bool,_SECURITY_ATTRIBUTES *)

- ea: `0x1800259a8`
- end: `0x180025a8f`
- name: `??0TFile@@QEAA@PEBGAEAVTOutput@@_NPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `231`
- prototype: `TFile *(TFile *__hidden this, const unsigned __int16 *, struct TOutput *, bool, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800232f0`

## callees

- `0x180017ad8`
- `0x1800259a8`
- `0x180030010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800259e5`
- `KERNEL32!DeleteFileW` at `0x1800259e5`
- `KERNEL32!GetFileAttributesW` at `0x1800259d7`
- `KERNEL32!GetFileAttributesW` at `0x1800259d7`
- `KERNEL32!CreateFileW` at `0x180025a3f`
- `KERNEL32!CreateFileW` at `0x180025a3f`
- `KERNEL32!GetLastError` at `0x1800259f5`
- `KERNEL32!GetLastError` at `0x1800259f5`

## string_xrefs

- `0x1800259fe`: `Warning! Unable to delete file %s.  Last error returned 0x%08x.\n	Check to see that the file is not Read-Only\n`
- `0x180025a52`: `Error - Failed to create file %s.\n`
- `0x180025a6a`: `CreateFile Failed.`
- `0x180025a71`: `inetsrv\iis\mb\config\src\core\schemagen\tfile.cpp`

## pseudocode

```c
TFile *__fastcall TFile::TFile(
        TFile *this,
        const unsigned __int16 *a2,
        void (***a3)(struct TOutput *, const wchar_t *, ...),
        __int64 a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes)
{
  void (*v8)(struct TOutput *, const wchar_t *, ...); // rbx
  DWORD LastError; // eax
  HANDLE FileW; // rax

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &TFile::`vftable';
  *((_DWORD *)this + 6) = 0;
  if ( GetFileAttributesW(a2) != -1 && !DeleteFileW(a2) )
  {
    v8 = **a3;
    LastError = GetLastError();
    v8(
      (struct TOutput *)a3,
      L"Warning! Unable to delete file %s.  Last error returned 0x%08x.\n"
       "\tCheck to see that the file is not Read-Only\n",
      a2,
      LastError);
  }
  FileW = CreateFileW(a2, 0x40000000u, 0, lpSecurityAttributes, 2u, 0x80u, 0);
  *((_QWORD *)this + 1) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    (**a3)((struct TOutput *)a3, L"Error - Failed to create file %s.\n", a2);
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tfile.cpp", L"CreateFile Failed.", 0x14u, 0);
  }
  return this;
}

```

## disassembly

```asm
0x1800259a8  push    rbx
0x1800259aa  push    rsi
0x1800259ab  push    rdi
0x1800259ac  push    r14
0x1800259ae  sub     rsp, 48h
0x1800259b2  lea     rax, ??_7TFile@@6B@; const TFile::`vftable'
0x1800259b9  mov     qword ptr [rcx+10h], 0
0x1800259c1  mov     [rcx], rax
0x1800259c4  mov     rdi, rcx
0x1800259c7  mov     dword ptr [rcx+18h], 0
0x1800259ce  mov     r14, r8
0x1800259d1  mov     rcx, rdx; lpFileName
0x1800259d4  mov     rsi, rdx
0x1800259d7  call    cs:__imp_GetFileAttributesW
0x1800259dd  cmp     eax, 0FFFFFFFFh
0x1800259e0  jz      short loc_180025A13
0x1800259e2  mov     rcx, rsi; lpFileName
0x1800259e5  call    cs:__imp_DeleteFileW
0x1800259eb  test    eax, eax
0x1800259ed  jnz     short loc_180025A13
0x1800259ef  mov     rax, [r14]
0x1800259f2  mov     rbx, [rax]
0x1800259f5  call    cs:__imp_GetLastError
0x1800259fb  mov     r8, rsi
0x1800259fe  lea     rdx, aWarningUnableT; "Warning! Unable to delete file %s.  Las"...
0x180025a05  mov     r9d, eax
0x180025a08  mov     rcx, r14
0x180025a0b  mov     rax, rbx
0x180025a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a13  mov     r9, [rsp+68h+lpSecurityAttributes]; lpSecurityAttributes
0x180025a1b  xor     r8d, r8d; dwShareMode
0x180025a1e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180025a27  mov     edx, 40000000h; dwDesiredAccess
0x180025a2c  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180025a34  mov     rcx, rsi; lpFileName
0x180025a37  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180025a3f  call    cs:__imp_CreateFileW
0x180025a45  mov     [rdi+8], rax
0x180025a49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025a4d  jnz     short loc_180025A82
0x180025a4f  mov     rax, [r14]
0x180025a52  lea     rdx, aErrorFailedToC; "Error - Failed to create file %s.\n"
0x180025a59  mov     r8, rsi
0x180025a5c  mov     rcx, r14
0x180025a5f  mov     rax, [rax]
0x180025a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a67  xor     r9d, r9d; unsigned int
0x180025a6a  lea     rdx, aCreatefileFail; "CreateFile Failed."
0x180025a71  lea     rcx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180025a78  lea     r8d, [r9+14h]; unsigned int
0x180025a7c  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180025a82  mov     rax, rdi
0x180025a85  add     rsp, 48h
0x180025a89  pop     r14
0x180025a8b  pop     rdi
0x180025a8c  pop     rsi
0x180025a8d  pop     rbx
0x180025a8e  retn
```
