# CRepositoryPackager::PackageFile(void *,ushort const *,ushort *)

- ea: `0x18003f624`
- end: `0x18003f867`
- name: `?PackageFile@CRepositoryPackager@@AEAAJPEAXPEBGPEAG@Z`
- size: `579`
- prototype: `int(CRepositoryPackager *__hidden this, void *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f160`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023bf0`
- `0x18003ec98`
- `0x18003f624`
- `0x18004037c`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f73c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f838`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f73c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f838`
- `wbemcomn!GetMemLogObject` at `0x18003f7ec`
- `wbemcomn!GetMemLogObject` at `0x18003f7ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f7f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f7f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f7b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f7b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18003f720`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18003f720`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f777`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f72a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7db`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRepositoryPackager::PackageFile(
        CRepositoryPackager *this,
        void *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const unsigned __int16 **v7; // rbx
  unsigned __int16 *v9; // rdi
  int v10; // ebx
  HANDLE FileW; // rax
  void *v12; // rsi
  CMemoryLog *MemLogObject; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD FileInformation[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+70h] [rbp-90h]
  int Buffer; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v19[262]; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v20; // [rsp+290h] [rbp+190h]

  v7 = (const unsigned __int16 **)&CRepositoryPackager::backupFiles_;
  do
  {
    if ( !(unsigned int)_adap_wbem_wcsicmp(a4, *v7) )
      break;
    ++v7;
  }
  while ( v7 != (const unsigned __int16 **)&g_ClassInfoHead );
  if ( v7 == (const unsigned __int16 **)&g_ClassInfoHead )
    return 0;
  memset_0(v19, 0, 0x210u);
  Buffer = 3;
  StringCchCopyW(v19, 0x105u, a4);
  memset(FileInformation, 0, sizeof(FileInformation));
  v17 = 0;
  CFileName::CFileName((CFileName *)&lpFileName);
  v9 = (unsigned __int16 *)lpFileName;
  if ( lpFileName )
  {
    StringCchCopyW((unsigned __int16 *)lpFileName, 0x173u, a3);
    StringCchCatW(v9, 0x173u, L"\\");
    StringCchCatW(v9, 0x173u, a4);
    if ( GetFileAttributesExW(v9, GetFileExInfoStandard, FileInformation) )
    {
      LODWORD(v20) = v17;
      NumberOfBytesWritten = 0;
      if ( WriteFile(a2, &Buffer, 0x214u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 532 )
      {
        v10 = 0;
        if ( !(_DWORD)v20 )
          goto LABEL_19;
        FileW = CreateFileW(v9, 0x80000000, 3u, 0, 3u, 0x8000080u, 0);
        v12 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          v10 = CopyFileW(FileW, a2, (unsigned int)v20);
          CloseHandle(v12);
          if ( v10 >= 0 )
            goto LABEL_19;
          goto LABEL_18;
        }
      }
    }
    else if ( GetLastError() == 2 )
    {
      CWin32DefaultArena::WbemMemFree(v9);
      return 0;
    }
    v10 = -2147217407;
  }
  else
  {
    v10 = -2147217402;
  }
LABEL_18:
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, v10);
LABEL_19:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids,
      (unsigned int)v10);
  }
  CWin32DefaultArena::WbemMemFree(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003f624  mov     [rsp-8+arg_0], rbx
0x18003f629  push    rbp
0x18003f62a  push    rsi
0x18003f62b  push    rdi
0x18003f62c  push    r14
0x18003f62e  push    r15
0x18003f630  lea     rbp, [rsp-1B0h]
0x18003f638  sub     rsp, 2B0h
0x18003f63f  mov     rax, cs:__security_cookie
0x18003f646  xor     rax, rsp
0x18003f649  mov     [rbp+1D0h+var_30], rax
0x18003f650  mov     rsi, r9
0x18003f653  mov     r15, r8
0x18003f656  mov     r14, rdx
0x18003f659  lea     rbx, ?backupFiles_@CRepositoryPackager@@0PAPEAGA; ushort * near * CRepositoryPackager::backupFiles_
0x18003f660  lea     rdi, ?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x18003f667  mov     rdx, [rbx]; unsigned __int16 *
0x18003f66a  mov     rcx, rsi; unsigned __int16 *
0x18003f66d  call    ?_adap_wbem_wcsicmp@@YAHPEBG0@Z; _adap_wbem_wcsicmp(ushort const *,ushort const *)
0x18003f672  test    eax, eax
0x18003f674  jz      short loc_18003F67F
0x18003f676  add     rbx, 8
0x18003f67a  cmp     rbx, rdi
0x18003f67d  jnz     short loc_18003F667
0x18003f67f  cmp     rbx, rdi
0x18003f682  jnz     short loc_18003F68B
0x18003f684  xor     eax, eax
0x18003f686  jmp     loc_18003F841
0x18003f68b  xor     edx, edx; Val
0x18003f68d  mov     r8d, 210h; Size
0x18003f693  lea     rcx, [rbp+1D0h+var_24C]; void *
0x18003f697  call    memset_0
0x18003f69c  mov     [rbp+1D0h+Buffer], 3
0x18003f6a3  mov     r8, rsi; unsigned __int16 *
0x18003f6a6  mov     edx, 105h; unsigned __int64
0x18003f6ab  lea     rcx, [rbp+1D0h+var_24C]; unsigned __int16 *
0x18003f6af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f6b4  xorps   xmm0, xmm0
0x18003f6b7  xor     eax, eax
0x18003f6b9  movups  [rsp+2D0h+FileInformation], xmm0
0x18003f6be  movups  [rsp+2D0h+var_270], xmm0
0x18003f6c3  mov     [rsp+2D0h+var_260], eax
0x18003f6c7  lea     rcx, [rsp+2D0h+lpFileName]; this
0x18003f6cc  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003f6d1  nop
0x18003f6d2  mov     rdi, [rsp+2D0h+lpFileName]
0x18003f6d7  test    rdi, rdi
0x18003f6da  jnz     short loc_18003F6E6
0x18003f6dc  mov     ebx, 80041006h
0x18003f6e1  jmp     loc_18003F7EC
0x18003f6e6  mov     r8, r15; unsigned __int16 *
0x18003f6e9  mov     ebx, 173h
0x18003f6ee  mov     edx, ebx; unsigned __int64
0x18003f6f0  mov     rcx, rdi; unsigned __int16 *
0x18003f6f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f6f8  lea     r8, asc_18004B0E0; "\\"
0x18003f6ff  mov     edx, ebx; unsigned __int64
0x18003f701  mov     rcx, rdi; unsigned __int16 *
0x18003f704  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f709  mov     r8, rsi; unsigned __int16 *
0x18003f70c  mov     edx, ebx; unsigned __int64
0x18003f70e  mov     rcx, rdi; unsigned __int16 *
0x18003f711  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f716  lea     r8, [rsp+2D0h+FileInformation]; lpFileInformation
0x18003f71b  xor     edx, edx; fInfoLevelId
0x18003f71d  mov     rcx, rdi; lpFileName
0x18003f720  call    cs:__imp_GetFileAttributesExW
0x18003f726  test    eax, eax
0x18003f728  jnz     short loc_18003F748
0x18003f72a  call    cs:__imp_GetLastError
0x18003f730  cmp     eax, 2
0x18003f733  jnz     loc_18003F7E7
0x18003f739  mov     rcx, rdi
0x18003f73c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003f742  nop
0x18003f743  jmp     loc_18003F684
0x18003f748  mov     eax, [rsp+2D0h+var_260]
0x18003f74c  mov     dword ptr [rbp+1D0h+var_40], eax
0x18003f752  mov     [rsp+2D0h+NumberOfBytesWritten], 0
0x18003f75a  mov     [rsp+2D0h+lpOverlapped], 0; lpOverlapped
0x18003f763  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003f768  mov     ebx, 214h
0x18003f76d  mov     r8d, ebx; nNumberOfBytesToWrite
0x18003f770  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x18003f774  mov     rcx, r14; hFile
0x18003f777  call    cs:__imp_WriteFile
0x18003f77d  test    eax, eax
0x18003f77f  jz      short loc_18003F7E7
0x18003f781  cmp     [rsp+2D0h+NumberOfBytesWritten], ebx
0x18003f785  jnz     short loc_18003F7E7
0x18003f787  xor     ebx, ebx
0x18003f789  cmp     dword ptr [rbp+1D0h+var_40], ebx
0x18003f78f  jz      short loc_18003F7FD
0x18003f791  mov     [rsp+2D0h+hTemplateFile], rbx; hTemplateFile
0x18003f796  mov     [rsp+2D0h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18003f79e  mov     dword ptr [rsp+2D0h+lpOverlapped], 3; dwCreationDisposition
0x18003f7a6  xor     r9d, r9d; lpSecurityAttributes
0x18003f7a9  mov     edx, 80000000h; dwDesiredAccess
0x18003f7ae  lea     r8d, [rbx+3]; dwShareMode
0x18003f7b2  mov     rcx, rdi; lpFileName
0x18003f7b5  call    cs:__imp_CreateFileW
0x18003f7bb  mov     rsi, rax
0x18003f7be  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f7c2  jz      short loc_18003F7E7
0x18003f7c4  mov     r8d, dword ptr [rbp+1D0h+var_40]; __int64
0x18003f7cb  mov     rdx, r14; HANDLE
0x18003f7ce  mov     rcx, rax; hFile
0x18003f7d1  call    ?CopyFileW@@YAJPEAX0_J@Z; CopyFileW(void *,void *,__int64)
0x18003f7d6  mov     ebx, eax
0x18003f7d8  mov     rcx, rsi; hObject
0x18003f7db  call    cs:__imp_CloseHandle
0x18003f7e1  test    ebx, ebx
0x18003f7e3  jns     short loc_18003F7FD
0x18003f7e5  jmp     short loc_18003F7EC
0x18003f7e7  mov     ebx, 80041001h
0x18003f7ec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003f7f2  mov     edx, ebx
0x18003f7f4  mov     rcx, rax
0x18003f7f7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f7fd  lea     rax, WPP_GLOBAL_Control
0x18003f804  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f80b  cmp     rcx, rax
0x18003f80e  jz      short loc_18003F835
0x18003f810  test    byte ptr [rcx+1Ch], 1
0x18003f814  jz      short loc_18003F835
0x18003f816  cmp     byte ptr [rcx+19h], 2
0x18003f81a  jb      short loc_18003F835
0x18003f81c  mov     edx, 16h
0x18003f821  mov     r9d, ebx
0x18003f824  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003f82b  mov     rcx, [rcx+10h]
0x18003f82f  call    WPP_SF_d
0x18003f834  nop
0x18003f835  mov     rcx, rdi
0x18003f838  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003f83e  nop
0x18003f83f  mov     eax, ebx
0x18003f841  mov     rcx, [rbp+1D0h+var_30]
0x18003f848  xor     rcx, rsp; StackCookie
0x18003f84b  call    __security_check_cookie
0x18003f850  mov     rbx, [rsp+2D0h+arg_0]
0x18003f858  add     rsp, 2B0h
0x18003f85f  pop     r15
0x18003f861  pop     r14
0x18003f863  pop     rdi
0x18003f864  pop     rsi
0x18003f865  pop     rbp
0x18003f866  retn
```
