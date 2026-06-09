# CUserDictionary::AddLineToLexFile(ushort const *)

- ea: `0x18008d588`
- end: `0x18008d6cb`
- name: `?AddLineToLexFile@CUserDictionary@@AEAAJPEBG@Z`
- size: `323`
- prototype: `__int64 __fastcall(CUserDictionary *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18008d6d4`

## callees

- `0x1800247c8`
- `0x18008d588`
- `0x18008d76c`
- `0x18008d8a8`
- `0x18008db18`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008d6a7`
- `KERNEL32!CloseHandle` at `0x18008d6a7`
- `KERNEL32!CreateFileW` at `0x18008d5d7`
- `KERNEL32!CreateFileW` at `0x18008d5d7`
- `KERNEL32!GetFileSize` at `0x18008d5ef`
- `KERNEL32!GetFileSize` at `0x18008d65b`
- `KERNEL32!GetFileSize` at `0x18008d5ef`
- `KERNEL32!GetFileSize` at `0x18008d65b`
- `KERNEL32!WriteFile` at `0x18008d62d`
- `KERNEL32!WriteFile` at `0x18008d62d`

## pseudocode

```c
__int64 __fastcall CUserDictionary::AddLineToLexFile(CUserDictionary *this, const unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  HANDLE FileW; // rax
  void *v6; // rdi
  DWORD FileSize; // ebp
  int v8; // eax
  CUserDictionary *v9; // rcx
  int appended; // ebx
  CUserDictionary *v11; // rcx
  CUserDictionary *v12; // rcx
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 6) )
    v4 = (const WCHAR *)*((_QWORD *)this + 4);
  else
    v4 = &cchOriginalDestLength;
  FileW = CreateFileW(v4, 0xC0000000, 4u, 0, 4u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return (unsigned int)HrGetLastError();
  FileSize = GetFileSize(FileW, 0);
  v8 = CUserDictionary::CheckForBOMInFile(this, v6, FileSize);
  appended = v8;
  if ( v8 == 1 )
  {
    NumberOfBytesWritten = 0;
    if ( WriteFile(v6, (char *)this + 88, 2u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 2 )
    {
      if ( !*((_DWORD *)this + 14)
        || (appended = CUserDictionary::AppendTextToFile(v11, v6, *((const unsigned __int16 **)this + 8)), appended >= 0) )
      {
        FileSize = GetFileSize(v6, 0);
LABEL_13:
        appended = CUserDictionary::NeedToAddCRLF(v9, v6, FileSize);
        if ( appended == 1 )
          appended = CUserDictionary::AppendTextToFile(v12, v6, &cchOriginalDestLength);
        if ( appended >= 0 )
          appended = CUserDictionary::AppendTextToFile(v12, v6, a2);
      }
    }
    else
    {
      appended = -2147467259;
    }
  }
  else if ( v8 >= 0 )
  {
    goto LABEL_13;
  }
  CloseHandle(v6);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18008d588  mov     [rsp+arg_8], rbx
0x18008d58d  mov     [rsp+arg_10], rbp
0x18008d592  push    rsi
0x18008d593  push    rdi
0x18008d594  push    r14
0x18008d596  sub     rsp, 40h
0x18008d59a  cmp     dword ptr [rcx+18h], 0
0x18008d59e  mov     r14, rdx
0x18008d5a1  mov     rsi, rcx
0x18008d5a4  jnz     short loc_18008D5AF
0x18008d5a6  lea     rcx, cchOriginalDestLength
0x18008d5ad  jmp     short loc_18008D5B3
0x18008d5af  mov     rcx, [rcx+20h]; lpFileName
0x18008d5b3  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18008d5bc  mov     r8d, 4; dwShareMode
0x18008d5c2  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008d5ca  xor     r9d, r9d; lpSecurityAttributes
0x18008d5cd  mov     edx, 0C0000000h; dwDesiredAccess
0x18008d5d2  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x18008d5d7  call    cs:__imp_CreateFileW
0x18008d5dd  mov     rdi, rax
0x18008d5e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008d5e4  jz      loc_18008D6AF
0x18008d5ea  xor     edx, edx; lpFileSizeHigh
0x18008d5ec  mov     rcx, rax; hFile
0x18008d5ef  call    cs:__imp_GetFileSize
0x18008d5f5  mov     rdx, rdi; void *
0x18008d5f8  mov     rcx, rsi; this
0x18008d5fb  mov     r8d, eax; unsigned int
0x18008d5fe  mov     ebp, eax
0x18008d600  call    ?CheckForBOMInFile@CUserDictionary@@AEAAJPEAXK@Z; CUserDictionary::CheckForBOMInFile(void *,ulong)
0x18008d605  mov     ebx, eax
0x18008d607  cmp     eax, 1
0x18008d60a  jnz     short loc_18008D66C
0x18008d60c  lea     rdx, [rsi+58h]; lpBuffer
0x18008d610  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18008d618  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d61d  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x18008d626  lea     r8d, [rax+1]; nNumberOfBytesToWrite
0x18008d62a  mov     rcx, rdi; hFile
0x18008d62d  call    cs:__imp_WriteFile
0x18008d633  test    eax, eax
0x18008d635  jz      short loc_18008D665
0x18008d637  cmp     [rsp+58h+NumberOfBytesWritten], 2
0x18008d63c  jnz     short loc_18008D665
0x18008d63e  cmp     dword ptr [rsi+38h], 0
0x18008d642  jz      short loc_18008D656
0x18008d644  mov     r8, [rsi+40h]; unsigned __int16 *
0x18008d648  mov     rdx, rdi; void *
0x18008d64b  call    ?AppendTextToFile@CUserDictionary@@AEAAJPEAXPEBG@Z; CUserDictionary::AppendTextToFile(void *,ushort const *)
0x18008d650  mov     ebx, eax
0x18008d652  test    eax, eax
0x18008d654  js      short loc_18008D6A4
0x18008d656  xor     edx, edx; lpFileSizeHigh
0x18008d658  mov     rcx, rdi; hFile
0x18008d65b  call    cs:__imp_GetFileSize
0x18008d661  mov     ebp, eax
0x18008d663  jmp     short loc_18008D670
0x18008d665  mov     ebx, 80004005h
0x18008d66a  jmp     short loc_18008D6A4
0x18008d66c  test    eax, eax
0x18008d66e  js      short loc_18008D6A4
0x18008d670  mov     r8d, ebp; unsigned int
0x18008d673  mov     rdx, rdi; void *
0x18008d676  call    ?NeedToAddCRLF@CUserDictionary@@AEAAJPEAXK@Z; CUserDictionary::NeedToAddCRLF(void *,ulong)
0x18008d67b  mov     ebx, eax
0x18008d67d  cmp     eax, 1
0x18008d680  jnz     short loc_18008D693
0x18008d682  lea     r8, cchOriginalDestLength; unsigned __int16 *
0x18008d689  mov     rdx, rdi; void *
0x18008d68c  call    ?AppendTextToFile@CUserDictionary@@AEAAJPEAXPEBG@Z; CUserDictionary::AppendTextToFile(void *,ushort const *)
0x18008d691  mov     ebx, eax
0x18008d693  test    ebx, ebx
0x18008d695  js      short loc_18008D6A4
0x18008d697  mov     r8, r14; unsigned __int16 *
0x18008d69a  mov     rdx, rdi; void *
0x18008d69d  call    ?AppendTextToFile@CUserDictionary@@AEAAJPEAXPEBG@Z; CUserDictionary::AppendTextToFile(void *,ushort const *)
0x18008d6a2  mov     ebx, eax
0x18008d6a4  mov     rcx, rdi; hObject
0x18008d6a7  call    cs:__imp_CloseHandle
0x18008d6ad  jmp     short loc_18008D6B6
0x18008d6af  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18008d6b4  mov     ebx, eax
0x18008d6b6  mov     rbp, [rsp+58h+arg_10]
0x18008d6bb  mov     eax, ebx
0x18008d6bd  mov     rbx, [rsp+58h+arg_8]
0x18008d6c2  add     rsp, 40h
0x18008d6c6  pop     r14
0x18008d6c8  pop     rdi
0x18008d6c9  pop     rsi
0x18008d6ca  retn
```
