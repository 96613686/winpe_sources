# XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)

- ea: `0x180015cf4`
- end: `0x180015f6b`
- name: `?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z`
- size: `631`
- prototype: `__int64 __fastcall(XPerfCore::CFileMapping *__hidden this, LPCWSTR lpFileName, bool, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800129cc`
- `0x18002469c`

## callees

- `0x18001449c`
- `0x180015cf4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015deb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015deb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ee8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015d3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015daf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015daf`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180015e56`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180015e56`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180015ec4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180015ec4`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180015d70`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180015d70`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180015dcd`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180015dcd`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180015d51`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180015d51`

## string_xrefs

- `0x180015dfa`: `CreateFile failed: %d`
- `0x180015e83`: `CreateFileMapping failed: %d`

## pseudocode

```c
signed int __fastcall XPerfCore::CFileMapping::MapExistingFileReadOnly2(
        XPerfCore::CFileMapping *this,
        LPCWSTR lpFileName,
        char a3,
        struct XPerfCore::IErrorMessage *a4)
{
  HANDLE CurrentProcess; // rax
  void (*v9)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...); // rbx
  DWORD LastError; // eax
  signed int result; // eax
  HANDLE FileMappingW; // rax
  void (__fastcall *v13)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD v14; // eax
  unsigned int *v15; // rcx
  void (__fastcall *v16)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD v17; // eax
  __int64 v18; // rax
  unsigned int v19; // edx
  char *v20; // rcx
  PVOID OldValue; // [rsp+40h] [rbp-38h] BYREF
  WINBOOL Wow64Process; // [rsp+80h] [rbp+8h] BYREF

  if ( *(_OWORD *)this != 0xFFFFFFFFFFFFFFFFuLL || *((_QWORD *)this + 2) )
    return -2147483634;
  Wow64Process = 0;
  OldValue = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process == 1 )
    Wow64Process = Wow64DisableWow64FsRedirection(&OldValue);
  *(_QWORD *)this = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( Wow64Process )
    Wow64RevertWow64FsRedirection(OldValue);
  if ( *(_QWORD *)this == -1 )
  {
    if ( a4 )
    {
      v9 = *(void (**)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...))(*(_QWORD *)a4 + 8LL);
      LastError = GetLastError();
      v9(a4, L"CreateFile failed: %d", LastError);
    }
    goto LABEL_11;
  }
  FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, a3 != 0 ? 285212674 : 2, 0, 0, 0);
  *((_QWORD *)this + 1) = FileMappingW;
  if ( FileMappingW )
  {
    v15 = (unsigned int *)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    *((_QWORD *)this + 2) = v15;
    if ( !v15 )
    {
      if ( a4 )
      {
        v16 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
        v17 = GetLastError();
        v16(a4, L"MapViewOfFileEx failed: %d", v17);
      }
      goto LABEL_16;
    }
    if ( *(_WORD *)v15 == 23117 )
    {
      v18 = v15[15];
      if ( (v18 & 3) == 0 && (_DWORD)v18 != -1 )
      {
        v19 = ~(_DWORD)v18;
        if ( (unsigned int)~(_DWORD)v18 >= 0x1B )
        {
          v20 = (char *)v15 + v18;
          if ( *(_DWORD *)v20 == 17744 )
          {
            if ( *((_WORD *)v20 + 12) == 267 )
            {
              if ( v19 > 0xF8 )
              {
LABEL_31:
                *((_QWORD *)this + 3) = *((unsigned int *)v20 + 20);
                return 0;
              }
            }
            else if ( *((_WORD *)v20 + 12) == 523 && v19 > 0x108 )
            {
              goto LABEL_31;
            }
          }
        }
      }
    }
    v20 = 0;
    goto LABEL_31;
  }
  if ( a4 )
  {
    v13 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
    v14 = GetLastError();
    v13(a4, L"CreateFileMapping failed: %d", v14);
  }
LABEL_16:
  XPerfCore::CFileMapping::Cleanup(this);
LABEL_11:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180015cf4  mov     rax, rsp
0x180015cf7  push    rbx
0x180015cf8  push    rbp
0x180015cf9  push    rsi
0x180015cfa  push    rdi
0x180015cfb  sub     rsp, 58h
0x180015cff  mov     rsi, r9
0x180015d02  mov     bl, r8b
0x180015d05  mov     rbp, rdx
0x180015d08  mov     rdi, rcx
0x180015d0b  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180015d0f  jnz     loc_180015F5C
0x180015d15  cmp     qword ptr [rcx+8], 0
0x180015d1a  jnz     loc_180015F5C
0x180015d20  cmp     qword ptr [rcx+10h], 0
0x180015d25  jnz     loc_180015F5C
0x180015d2b  mov     dword ptr [rax+8], 0
0x180015d32  mov     qword ptr [rax-38h], 0
0x180015d3a  call    cs:__imp_GetCurrentProcess
0x180015d41  nop     dword ptr [rax+rax+00h]
0x180015d46  mov     rcx, rax; hProcess
0x180015d49  lea     rdx, [rsp+78h+Wow64Process]; Wow64Process
0x180015d51  call    cs:__imp_IsWow64Process
0x180015d58  nop     dword ptr [rax+rax+00h]
0x180015d5d  test    eax, eax
0x180015d5f  jz      short loc_180015D87
0x180015d61  cmp     [rsp+78h+Wow64Process], 1
0x180015d69  jnz     short loc_180015D87
0x180015d6b  lea     rcx, [rsp+78h+OldValue]; OldValue
0x180015d70  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180015d77  nop     dword ptr [rax+rax+00h]
0x180015d7c  test    eax, eax
0x180015d7e  jnz     short loc_180015D87
0x180015d80  mov     [rsp+78h+Wow64Process], eax
0x180015d87  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180015d90  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180015d98  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180015da0  xor     r9d, r9d; lpSecurityAttributes
0x180015da3  mov     edx, 80000000h; dwDesiredAccess
0x180015da8  lea     r8d, [r9+1]; dwShareMode
0x180015dac  mov     rcx, rbp; lpFileName
0x180015daf  call    cs:__imp_CreateFileW
0x180015db6  nop     dword ptr [rax+rax+00h]
0x180015dbb  mov     [rdi], rax
0x180015dbe  cmp     [rsp+78h+Wow64Process], 0
0x180015dc6  jz      short loc_180015DD9
0x180015dc8  mov     rcx, [rsp+78h+OldValue]; OlValue
0x180015dcd  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180015dd4  nop     dword ptr [rax+rax+00h]
0x180015dd9  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180015ddd  jnz     short loc_180015E2D
0x180015ddf  test    rsi, rsi
0x180015de2  jz      short loc_180015E0C
0x180015de4  mov     rax, [rsi]
0x180015de7  mov     rbx, [rax+8]
0x180015deb  call    cs:__imp_GetLastError
0x180015df2  nop     dword ptr [rax+rax+00h]
0x180015df7  mov     r8d, eax
0x180015dfa  lea     rdx, aCreatefileFail; "CreateFile failed: %d"
0x180015e01  mov     rcx, rsi
0x180015e04  mov     rax, rbx
0x180015e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e0c  call    cs:__imp_GetLastError
0x180015e13  nop     dword ptr [rax+rax+00h]
0x180015e18  test    eax, eax
0x180015e1a  jle     loc_180015F61
0x180015e20  movzx   eax, ax
0x180015e23  or      eax, 80070000h
0x180015e28  jmp     loc_180015F61
0x180015e2d  neg     bl
0x180015e2f  sbb     r8d, r8d
0x180015e32  and     r8d, 11000000h
0x180015e39  add     r8d, 2; flProtect
0x180015e3d  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x180015e46  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180015e4e  xor     r9d, r9d; dwMaximumSizeHigh
0x180015e51  xor     edx, edx; lpFileMappingAttributes
0x180015e53  mov     rcx, [rdi]; hFile
0x180015e56  call    cs:__imp_CreateFileMappingW
0x180015e5d  nop     dword ptr [rax+rax+00h]
0x180015e62  mov     [rdi+8], rax
0x180015e66  test    rax, rax
0x180015e69  jnz     short loc_180015EA5
0x180015e6b  test    rsi, rsi
0x180015e6e  jz      short loc_180015E98
0x180015e70  mov     rax, [rsi]
0x180015e73  mov     rbx, [rax+8]
0x180015e77  call    cs:__imp_GetLastError
0x180015e7e  nop     dword ptr [rax+rax+00h]
0x180015e83  lea     rdx, aCreatefilemapp; "CreateFileMapping failed: %d"
0x180015e8a  mov     r8d, eax
0x180015e8d  mov     rcx, rsi
0x180015e90  mov     rax, rbx
0x180015e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e98  mov     rcx, rdi; this
0x180015e9b  call    ?Cleanup@CFileMapping@XPerfCore@@AEAAXXZ; XPerfCore::CFileMapping::Cleanup(void)
0x180015ea0  jmp     loc_180015E0C
0x180015ea5  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpBaseAddress
0x180015eae  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180015eb7  xor     r9d, r9d; dwFileOffsetLow
0x180015eba  xor     r8d, r8d; dwFileOffsetHigh
0x180015ebd  lea     edx, [r9+4]; dwDesiredAccess
0x180015ec1  mov     rcx, rax; hFileMappingObject
0x180015ec4  call    cs:__imp_MapViewOfFileEx
0x180015ecb  nop     dword ptr [rax+rax+00h]
0x180015ed0  mov     rcx, rax
0x180015ed3  mov     [rdi+10h], rax
0x180015ed7  test    rax, rax
0x180015eda  jnz     short loc_180015EFD
0x180015edc  test    rsi, rsi
0x180015edf  jz      short loc_180015E98
0x180015ee1  mov     rax, [rsi]
0x180015ee4  mov     rbx, [rax+8]
0x180015ee8  call    cs:__imp_GetLastError
0x180015eef  nop     dword ptr [rax+rax+00h]
0x180015ef4  lea     rdx, aMapviewoffilee; "MapViewOfFileEx failed: %d"
0x180015efb  jmp     short loc_180015E8A
0x180015efd  mov     eax, 5A4Dh
0x180015f02  cmp     [rcx], ax
0x180015f05  jnz     short loc_180015F4F
0x180015f07  mov     eax, [rcx+3Ch]
0x180015f0a  test    al, 3
0x180015f0c  jnz     short loc_180015F4F
0x180015f0e  cmp     eax, 0FFFFFFFFh
0x180015f11  jnb     short loc_180015F4F
0x180015f13  mov     edx, eax
0x180015f15  not     edx
0x180015f17  cmp     edx, 1Bh
0x180015f1a  jb      short loc_180015F4F
0x180015f1c  add     rcx, rax
0x180015f1f  cmp     dword ptr [rcx], 4550h
0x180015f25  jnz     short loc_180015F4F
0x180015f27  mov     eax, 10Bh
0x180015f2c  cmp     [rcx+18h], ax
0x180015f30  jz      short loc_180015F47
0x180015f32  mov     eax, 20Bh
0x180015f37  cmp     [rcx+18h], ax
0x180015f3b  jnz     short loc_180015F4F
0x180015f3d  cmp     edx, 108h
0x180015f43  jbe     short loc_180015F4F
0x180015f45  jmp     short loc_180015F51
0x180015f47  cmp     edx, 0F8h
0x180015f4d  ja      short loc_180015F51
0x180015f4f  xor     ecx, ecx
0x180015f51  mov     eax, [rcx+50h]
0x180015f54  mov     [rdi+18h], rax
0x180015f58  xor     eax, eax
0x180015f5a  jmp     short loc_180015F61
0x180015f5c  mov     eax, 8000000Eh
0x180015f61  add     rsp, 58h
0x180015f65  pop     rdi
0x180015f66  pop     rsi
0x180015f67  pop     rbp
0x180015f68  pop     rbx
0x180015f69  retn
```
