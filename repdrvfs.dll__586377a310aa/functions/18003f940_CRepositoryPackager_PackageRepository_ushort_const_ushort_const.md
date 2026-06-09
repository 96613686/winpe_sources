# CRepositoryPackager::PackageRepository(ushort const *,ushort const *)

- ea: `0x18003f940`
- end: `0x18003fc0e`
- name: `?PackageRepository@CRepositoryPackager@@QEAAJPEBG0@Z`
- size: `718`
- prototype: `__int64 __fastcall(CRepositoryPackager *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180038f00`
- `0x18003b9f8`
- `0x18003c580`
- `0x18003c8a0`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023bf0`
- `0x18003efb4`
- `0x18003f308`
- `0x18003f870`
- `0x18003f940`
- `0x18003fc14`

## import_xrefs

- `msvcrt!_itow` at `0x18003fa66`
- `msvcrt!_itow` at `0x18003fa66`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003fbb0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003fbbc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003fbb0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003fbbc`
- `wbemcomn!GetMemLogObject` at `0x18003fae0`
- `wbemcomn!GetMemLogObject` at `0x18003fb64`
- `wbemcomn!GetMemLogObject` at `0x18003fae0`
- `wbemcomn!GetMemLogObject` at `0x18003fb64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003faeb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003fb6f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003faeb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003fb6f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f9e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003faac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f9e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003faac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003fb5a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003fbde`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003fb5a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003fbde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fb3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fb3f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003fa78`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003fc02`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003fa78`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003fc02`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CRepositoryPackager::PackageRepository(
        CRepositoryPackager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  char v5; // r15
  CRepositoryPackager *v6; // rcx
  unsigned __int16 *v7; // rsi
  int RepositoryDirectory; // eax
  int v9; // ebx
  CRepositoryPackager *v10; // rcx
  HANDLE FileW; // rdi
  unsigned int v12; // r10d
  __int64 v13; // rdi
  int i; // ebx
  CRepositoryPackager *v15; // rcx
  const unsigned __int16 *v16; // r9
  CMemoryLog *MemLogObject; // rax
  CRepositoryPackager *v18; // rcx
  CMemoryLog *v19; // rax
  unsigned __int16 *v21; // [rsp+70h] [rbp+8h] BYREF
  LPCWSTR lpNewFileName; // [rsp+88h] [rbp+20h] BYREF

  v21 = (unsigned __int16 *)this;
  CFileName::CFileName((CFileName *)&v21);
  v5 = 0;
  CFileName::CFileName((CFileName *)&lpNewFileName);
  v7 = (unsigned __int16 *)lpNewFileName;
  if ( !lpNewFileName || !v21 )
  {
    v9 = -2147217402;
    goto LABEL_39;
  }
  if ( a3 )
    RepositoryDirectory = StringCchCopyW(v21, 0x105u, a3);
  else
    RepositoryDirectory = CRepositoryPackager::GetRepositoryDirectory(v6, v21);
  v9 = RepositoryDirectory;
  if ( RepositoryDirectory < 0 )
    goto LABEL_39;
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 1u, 0x80000080, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() == 80 || GetLastError() == 183 )
    {
      StringCchCopyW(v7, 0x173u, a2);
      StringCchCatW(v7, v12, L".");
      v13 = -1;
      do
        ++v13;
      while ( v7[v13] );
      for ( i = 0; i != 100; ++i )
      {
        _itow(i, &v7[(int)v13], 10);
        if ( MoveFileExW(a2, v7, 2u) )
        {
          v5 = 1;
          FileW = CreateFileW(a2, 0x40000000u, 0, 0, 1u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
            break;
          goto LABEL_18;
        }
      }
    }
    v9 = -2147217400;
    goto LABEL_39;
  }
LABEL_18:
  v9 = CRepositoryPackager::PackageHeader(v10, FileW);
  if ( v9 >= 0 )
  {
    v9 = CRepositoryPackager::PackageDirectory(v15, FileW, v21, v16);
    if ( v9 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v9);
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids,
        (unsigned int)v9);
    }
    if ( v9 >= 0 )
      v9 = CRepositoryPackager::PackageTrailer(v18, FileW);
  }
  CloseHandle(FileW);
  if ( v9 < 0 )
  {
LABEL_39:
    DeleteFileW(a2);
    if ( v5 && v7 )
      MoveFileExW(v7, a2, 2u);
    goto LABEL_31;
  }
  if ( !v5 )
    goto LABEL_33;
  if ( v7 )
    DeleteFileW(v7);
LABEL_31:
  if ( v9 < 0 )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, v9);
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, (unsigned int)v9);
  }
  CWin32DefaultArena::WbemMemFree(v7);
  CWin32DefaultArena::WbemMemFree(v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003f940  mov     [rsp+arg_8], rbx
0x18003f945  mov     [rsp+arg_0], rcx
0x18003f94a  push    rbp
0x18003f94b  push    rsi
0x18003f94c  push    rdi
0x18003f94d  push    r12
0x18003f94f  push    r15
0x18003f951  sub     rsp, 40h
0x18003f955  mov     rbx, r8
0x18003f958  mov     rbp, rdx
0x18003f95b  lea     rcx, [rsp+68h+arg_0]; this
0x18003f960  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003f965  nop
0x18003f966  xor     r12d, r12d
0x18003f969  mov     r15b, r12b
0x18003f96c  lea     rcx, [rsp+68h+lpNewFileName]; this
0x18003f974  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003f979  nop
0x18003f97a  mov     rsi, [rsp+68h+lpNewFileName]
0x18003f982  test    rsi, rsi
0x18003f985  jz      loc_18003FBD6
0x18003f98b  cmp     [rsp+68h+arg_0], r12
0x18003f990  jz      loc_18003FBD6
0x18003f996  test    rbx, rbx
0x18003f999  jnz     short loc_18003F9A7
0x18003f99b  mov     rdx, [rsp+68h+arg_0]; unsigned __int16 *
0x18003f9a0  call    ?GetRepositoryDirectory@CRepositoryPackager@@AEAAJQEAG@Z; CRepositoryPackager::GetRepositoryDirectory(ushort * const)
0x18003f9a5  jmp     short loc_18003F9B9
0x18003f9a7  mov     r8, rbx; unsigned __int16 *
0x18003f9aa  mov     edx, 105h; unsigned __int64
0x18003f9af  mov     rcx, [rsp+68h+arg_0]; unsigned __int16 *
0x18003f9b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f9b9  mov     ebx, eax
0x18003f9bb  test    eax, eax
0x18003f9bd  js      loc_18003FBDB
0x18003f9c3  mov     [rsp+68h+hTemplateFile], r12; hTemplateFile
0x18003f9c8  mov     [rsp+68h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x18003f9d0  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x18003f9d8  xor     r9d, r9d; lpSecurityAttributes
0x18003f9db  xor     r8d, r8d; dwShareMode
0x18003f9de  mov     edx, 40000000h; dwDesiredAccess
0x18003f9e3  mov     rcx, rbp; lpFileName
0x18003f9e6  call    cs:__imp_CreateFileW
0x18003f9ec  mov     rdi, rax
0x18003f9ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f9f3  jnz     loc_18003FABF
0x18003f9f9  call    cs:__imp_GetLastError
0x18003f9ff  cmp     eax, 50h ; 'P'
0x18003fa02  jz      short loc_18003FA1B
0x18003fa04  call    cs:__imp_GetLastError
0x18003fa0a  cmp     eax, 0B7h
0x18003fa0f  jz      short loc_18003FA1B
0x18003fa11  mov     ebx, 80041008h
0x18003fa16  jmp     loc_18003FBDB
0x18003fa1b  mov     r8, rbp; unsigned __int16 *
0x18003fa1e  mov     r10d, 173h
0x18003fa24  mov     edx, r10d; unsigned __int64
0x18003fa27  mov     rcx, rsi; unsigned __int16 *
0x18003fa2a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003fa2f  lea     r8, asc_18004D06C; "."
0x18003fa36  mov     edx, r10d; unsigned __int64
0x18003fa39  mov     rcx, rsi; unsigned __int16 *
0x18003fa3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003fa41  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003fa45  inc     rdi
0x18003fa48  cmp     [rsi+rdi*2], r12w
0x18003fa4d  jnz     short loc_18003FA45
0x18003fa4f  mov     ebx, r12d
0x18003fa52  cmp     ebx, 64h ; 'd'
0x18003fa55  jz      short loc_18003FA11
0x18003fa57  movsxd  rax, edi
0x18003fa5a  lea     rdx, [rsi+rax*2]; Buffer
0x18003fa5e  mov     r8d, 0Ah; Radix
0x18003fa64  mov     ecx, ebx; Value
0x18003fa66  call    cs:__imp__itow
0x18003fa6c  mov     r8d, 2; dwFlags
0x18003fa72  mov     rdx, rsi; lpNewFileName
0x18003fa75  mov     rcx, rbp; lpExistingFileName
0x18003fa78  call    cs:__imp_MoveFileExW
0x18003fa7e  test    eax, eax
0x18003fa80  jnz     short loc_18003FA86
0x18003fa82  inc     ebx
0x18003fa84  jmp     short loc_18003FA52
0x18003fa86  mov     r15b, 1
0x18003fa89  mov     [rsp+68h+hTemplateFile], r12; hTemplateFile
0x18003fa8e  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003fa96  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x18003fa9e  xor     r9d, r9d; lpSecurityAttributes
0x18003faa1  xor     r8d, r8d; dwShareMode
0x18003faa4  mov     edx, 40000000h; dwDesiredAccess
0x18003faa9  mov     rcx, rbp; lpFileName
0x18003faac  call    cs:__imp_CreateFileW
0x18003fab2  mov     rdi, rax
0x18003fab5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003fab9  jz      loc_18003FA11
0x18003fabf  mov     rdx, rdi; void *
0x18003fac2  call    ?PackageHeader@CRepositoryPackager@@AEAAJPEAX@Z; CRepositoryPackager::PackageHeader(void *)
0x18003fac7  mov     ebx, eax
0x18003fac9  test    eax, eax
0x18003facb  js      short loc_18003FB3C
0x18003facd  mov     r8, [rsp+68h+arg_0]; unsigned __int16 *
0x18003fad2  mov     rdx, rdi; void *
0x18003fad5  call    ?PackageDirectory@CRepositoryPackager@@AEAAJPEAXPEBG1@Z; CRepositoryPackager::PackageDirectory(void *,ushort const *,ushort const *)
0x18003fada  mov     ebx, eax
0x18003fadc  test    eax, eax
0x18003fade  jns     short loc_18003FAF1
0x18003fae0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003fae6  mov     edx, ebx
0x18003fae8  mov     rcx, rax
0x18003faeb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003faf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003faf8  lea     rax, WPP_GLOBAL_Control
0x18003faff  cmp     rcx, rax
0x18003fb02  jz      short loc_18003FB28
0x18003fb04  test    byte ptr [rcx+1Ch], 1
0x18003fb08  jz      short loc_18003FB28
0x18003fb0a  cmp     byte ptr [rcx+19h], 2
0x18003fb0e  jb      short loc_18003FB28
0x18003fb10  mov     edx, 0Fh
0x18003fb15  mov     r9d, ebx
0x18003fb18  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003fb1f  mov     rcx, [rcx+10h]
0x18003fb23  call    WPP_SF_d
0x18003fb28  test    ebx, ebx
0x18003fb2a  js      short loc_18003FB36
0x18003fb2c  mov     rdx, rdi; void *
0x18003fb2f  call    ?PackageTrailer@CRepositoryPackager@@AEAAJPEAX@Z; CRepositoryPackager::PackageTrailer(void *)
0x18003fb34  mov     ebx, eax
0x18003fb36  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003fb3a  jz      short loc_18003FB45
0x18003fb3c  mov     rcx, rdi; hObject
0x18003fb3f  call    cs:__imp_CloseHandle
0x18003fb45  test    ebx, ebx
0x18003fb47  js      loc_18003FBDB
0x18003fb4d  test    r15b, r15b
0x18003fb50  jz      short loc_18003FB75
0x18003fb52  test    rsi, rsi
0x18003fb55  jz      short loc_18003FB60
0x18003fb57  mov     rcx, rsi; lpFileName
0x18003fb5a  call    cs:__imp_DeleteFileW
0x18003fb60  test    ebx, ebx
0x18003fb62  jns     short loc_18003FB75
0x18003fb64  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003fb6a  mov     edx, ebx
0x18003fb6c  mov     rcx, rax
0x18003fb6f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003fb75  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb7c  lea     rax, WPP_GLOBAL_Control
0x18003fb83  cmp     rcx, rax
0x18003fb86  jz      short loc_18003FBAD
0x18003fb88  test    byte ptr [rcx+1Ch], 1
0x18003fb8c  jz      short loc_18003FBAD
0x18003fb8e  cmp     byte ptr [rcx+19h], 2
0x18003fb92  jb      short loc_18003FBAD
0x18003fb94  mov     edx, 0Ch
0x18003fb99  mov     r9d, ebx
0x18003fb9c  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003fba3  mov     rcx, [rcx+10h]
0x18003fba7  call    WPP_SF_d
0x18003fbac  nop
0x18003fbad  mov     rcx, rsi
0x18003fbb0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003fbb6  nop
0x18003fbb7  mov     rcx, [rsp+68h+arg_0]
0x18003fbbc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003fbc2  nop
0x18003fbc3  mov     eax, ebx
0x18003fbc5  mov     rbx, [rsp+68h+arg_8]
0x18003fbca  add     rsp, 40h
0x18003fbce  pop     r15
0x18003fbd0  pop     r12
0x18003fbd2  pop     rdi
0x18003fbd3  pop     rsi
0x18003fbd4  pop     rbp
0x18003fbd5  retn
0x18003fbd6  mov     ebx, 80041006h
0x18003fbdb  mov     rcx, rbp; lpFileName
0x18003fbde  call    cs:__imp_DeleteFileW
0x18003fbe4  test    r15b, r15b
0x18003fbe7  jz      loc_18003FB60
0x18003fbed  test    rsi, rsi
0x18003fbf0  jz      loc_18003FB60
0x18003fbf6  mov     r8d, 2; dwFlags
0x18003fbfc  mov     rdx, rbp; lpNewFileName
0x18003fbff  mov     rcx, rsi; lpExistingFileName
0x18003fc02  call    cs:__imp_MoveFileExW
0x18003fc08  jmp     loc_18003FB60
```
