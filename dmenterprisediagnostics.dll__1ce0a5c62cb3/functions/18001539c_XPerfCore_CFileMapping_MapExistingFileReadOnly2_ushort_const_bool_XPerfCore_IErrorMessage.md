# XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)

- ea: `0x18001539c`
- end: `0x1800155d0`
- name: `?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z`
- size: `564`
- prototype: `signed int __fastcall(XPerfCore::CFileMapping *this, LPCWSTR lpFileName, char, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800121e8`
- `0x18002389c`

## callees

- `0x180013ca4`
- `0x18001539c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015554`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800153e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800153e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015445`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015445`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800154d4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800154d4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180015536`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180015536`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18001540c`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18001540c`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001545d`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001545d`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800153f3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800153f3`

## string_xrefs

- `0x18001547e`: `CreateFile failed: %d`
- `0x1800154f5`: `CreateFileMapping failed: %d`

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
0x18001539c  mov     rax, rsp
0x18001539f  push    rbx
0x1800153a0  push    rbp
0x1800153a1  push    rsi
0x1800153a2  push    rdi
0x1800153a3  sub     rsp, 58h
0x1800153a7  mov     rsi, r9
0x1800153aa  mov     bl, r8b
0x1800153ad  mov     rbp, rdx
0x1800153b0  mov     rdi, rcx
0x1800153b3  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800153b7  jnz     loc_1800155C2
0x1800153bd  cmp     qword ptr [rcx+8], 0
0x1800153c2  jnz     loc_1800155C2
0x1800153c8  cmp     qword ptr [rcx+10h], 0
0x1800153cd  jnz     loc_1800155C2
0x1800153d3  mov     dword ptr [rax+8], 0
0x1800153da  mov     qword ptr [rax-38h], 0
0x1800153e2  call    cs:__imp_GetCurrentProcess
0x1800153e8  mov     rcx, rax; hProcess
0x1800153eb  lea     rdx, [rsp+78h+Wow64Process]; Wow64Process
0x1800153f3  call    cs:__imp_IsWow64Process
0x1800153f9  test    eax, eax
0x1800153fb  jz      short loc_18001541D
0x1800153fd  cmp     [rsp+78h+Wow64Process], 1
0x180015405  jnz     short loc_18001541D
0x180015407  lea     rcx, [rsp+78h+OldValue]; OldValue
0x18001540c  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180015412  test    eax, eax
0x180015414  jnz     short loc_18001541D
0x180015416  mov     [rsp+78h+Wow64Process], eax
0x18001541d  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180015426  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001542e  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180015436  xor     r9d, r9d; lpSecurityAttributes
0x180015439  mov     edx, 80000000h; dwDesiredAccess
0x18001543e  lea     r8d, [r9+1]; dwShareMode
0x180015442  mov     rcx, rbp; lpFileName
0x180015445  call    cs:__imp_CreateFileW
0x18001544b  mov     [rdi], rax
0x18001544e  cmp     [rsp+78h+Wow64Process], 0
0x180015456  jz      short loc_180015463
0x180015458  mov     rcx, [rsp+78h+OldValue]; OlValue
0x18001545d  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180015463  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180015467  jnz     short loc_1800154AB
0x180015469  test    rsi, rsi
0x18001546c  jz      short loc_180015490
0x18001546e  mov     rax, [rsi]
0x180015471  mov     rbx, [rax+8]
0x180015475  call    cs:__imp_GetLastError
0x18001547b  mov     r8d, eax
0x18001547e  lea     rdx, aCreatefileFail; "CreateFile failed: %d"
0x180015485  mov     rcx, rsi
0x180015488  mov     rax, rbx
0x18001548b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015490  call    cs:__imp_GetLastError
0x180015496  test    eax, eax
0x180015498  jle     loc_1800155C7
0x18001549e  movzx   eax, ax
0x1800154a1  or      eax, 80070000h
0x1800154a6  jmp     loc_1800155C7
0x1800154ab  neg     bl
0x1800154ad  sbb     r8d, r8d
0x1800154b0  and     r8d, 11000000h
0x1800154b7  add     r8d, 2; flProtect
0x1800154bb  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x1800154c4  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800154cc  xor     r9d, r9d; dwMaximumSizeHigh
0x1800154cf  xor     edx, edx; lpFileMappingAttributes
0x1800154d1  mov     rcx, [rdi]; hFile
0x1800154d4  call    cs:__imp_CreateFileMappingW
0x1800154da  mov     [rdi+8], rax
0x1800154de  test    rax, rax
0x1800154e1  jnz     short loc_180015517
0x1800154e3  test    rsi, rsi
0x1800154e6  jz      short loc_18001550A
0x1800154e8  mov     rax, [rsi]
0x1800154eb  mov     rbx, [rax+8]
0x1800154ef  call    cs:__imp_GetLastError
0x1800154f5  lea     rdx, aCreatefilemapp; "CreateFileMapping failed: %d"
0x1800154fc  mov     r8d, eax
0x1800154ff  mov     rcx, rsi
0x180015502  mov     rax, rbx
0x180015505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001550a  mov     rcx, rdi; this
0x18001550d  call    ?Cleanup@CFileMapping@XPerfCore@@AEAAXXZ; XPerfCore::CFileMapping::Cleanup(void)
0x180015512  jmp     loc_180015490
0x180015517  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpBaseAddress
0x180015520  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180015529  xor     r9d, r9d; dwFileOffsetLow
0x18001552c  xor     r8d, r8d; dwFileOffsetHigh
0x18001552f  lea     edx, [r9+4]; dwDesiredAccess
0x180015533  mov     rcx, rax; hFileMappingObject
0x180015536  call    cs:__imp_MapViewOfFileEx
0x18001553c  mov     rcx, rax
0x18001553f  mov     [rdi+10h], rax
0x180015543  test    rax, rax
0x180015546  jnz     short loc_180015563
0x180015548  test    rsi, rsi
0x18001554b  jz      short loc_18001550A
0x18001554d  mov     rax, [rsi]
0x180015550  mov     rbx, [rax+8]
0x180015554  call    cs:__imp_GetLastError
0x18001555a  lea     rdx, aMapviewoffilee; "MapViewOfFileEx failed: %d"
0x180015561  jmp     short loc_1800154FC
0x180015563  mov     eax, 5A4Dh
0x180015568  cmp     [rcx], ax
0x18001556b  jnz     short loc_1800155B5
0x18001556d  mov     eax, [rcx+3Ch]
0x180015570  test    al, 3
0x180015572  jnz     short loc_1800155B5
0x180015574  cmp     eax, 0FFFFFFFFh
0x180015577  jnb     short loc_1800155B5
0x180015579  mov     edx, eax
0x18001557b  not     edx
0x18001557d  cmp     edx, 1Bh
0x180015580  jb      short loc_1800155B5
0x180015582  add     rcx, rax
0x180015585  cmp     dword ptr [rcx], 4550h
0x18001558b  jnz     short loc_1800155B5
0x18001558d  mov     eax, 10Bh
0x180015592  cmp     [rcx+18h], ax
0x180015596  jz      short loc_1800155AD
0x180015598  mov     eax, 20Bh
0x18001559d  cmp     [rcx+18h], ax
0x1800155a1  jnz     short loc_1800155B5
0x1800155a3  cmp     edx, 108h
0x1800155a9  jbe     short loc_1800155B5
0x1800155ab  jmp     short loc_1800155B7
0x1800155ad  cmp     edx, 0F8h
0x1800155b3  ja      short loc_1800155B7
0x1800155b5  xor     ecx, ecx
0x1800155b7  mov     eax, [rcx+50h]
0x1800155ba  mov     [rdi+18h], rax
0x1800155be  xor     eax, eax
0x1800155c0  jmp     short loc_1800155C7
0x1800155c2  mov     eax, 8000000Eh
0x1800155c7  add     rsp, 58h
0x1800155cb  pop     rdi
0x1800155cc  pop     rsi
0x1800155cd  pop     rbp
0x1800155ce  pop     rbx
0x1800155cf  retn
```
