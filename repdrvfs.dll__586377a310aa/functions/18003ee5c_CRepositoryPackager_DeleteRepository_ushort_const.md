# CRepositoryPackager::DeleteRepository(ushort const *)

- ea: `0x18003ee5c`
- end: `0x18003efab`
- name: `?DeleteRepository@CRepositoryPackager@@QEAAJPEBG@Z`
- size: `335`
- prototype: `__int64 __fastcall(CRepositoryPackager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004025c`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023b3c`
- `0x180023bf0`
- `0x18003ee5c`
- `0x18003efb4`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ee75`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ee75`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ef27`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ef3f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ef27`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ef3f`
- `wbemcomn!GetMemLogObject` at `0x18003ef46`
- `wbemcomn!GetMemLogObject` at `0x18003ef46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ef51`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ef51`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ef02`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ef02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef17`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepositoryPackager::DeleteRepository(CRepositoryPackager *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rax
  CRepositoryPackager *v3; // rcx
  const unsigned __int16 *v4; // rsi
  int RepositoryDirectory; // ebx
  int v6; // ebp
  CMemoryLog *MemLogObject; // rax
  void *v9[3]; // [rsp+20h] [rbp-18h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp+10h] BYREF

  lpFileName = a2;
  v2 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v4 = v2;
  v9[0] = v2;
  v9[1] = 0;
  if ( v2 )
    RepositoryDirectory = CRepositoryPackager::GetRepositoryDirectory(v3, v2);
  else
    RepositoryDirectory = -2147217402;
  v6 = 0;
  while ( RepositoryDirectory >= 0 )
  {
    if ( v6 == 6 )
      goto LABEL_15;
    CFileName::CFileName((CFileName *)&lpFileName);
    if ( lpFileName )
    {
      StringCchCopyW((unsigned __int16 *)lpFileName, 0x173u, v4);
      StringCchCatW((unsigned __int16 *)lpFileName, 0x173u, off_18004A000[v6]);
      if ( !DeleteFileW(lpFileName) && GetLastError() != 2 && GetLastError() != 3 )
      {
        RepositoryDirectory = -2147217407;
        CWin32DefaultArena::WbemMemFree((void *)lpFileName);
        break;
      }
    }
    else
    {
      RepositoryDirectory = -2147217402;
    }
    CWin32DefaultArena::WbemMemFree((void *)lpFileName);
    ++v6;
  }
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, RepositoryDirectory);
LABEL_15:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids,
      (unsigned int)RepositoryDirectory);
  }
  CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v9);
  return (unsigned int)RepositoryDirectory;
}

```

## disassembly

```asm
0x18003ee5c  mov     [rsp+arg_0], rbx
0x18003ee61  mov     [rsp+arg_10], rbp
0x18003ee66  mov     [rsp+lpFileName], rdx
0x18003ee6b  push    rsi
0x18003ee6c  sub     rsp, 30h
0x18003ee70  mov     ecx, 20Ah
0x18003ee75  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003ee7b  mov     rsi, rax
0x18003ee7e  mov     [rsp+38h+var_18], rax
0x18003ee83  mov     [rsp+38h+var_10], 0
0x18003ee8c  test    rax, rax
0x18003ee8f  jnz     short loc_18003EE98
0x18003ee91  mov     ebx, 80041006h
0x18003ee96  jmp     short loc_18003EEA2
0x18003ee98  mov     rdx, rsi; unsigned __int16 *
0x18003ee9b  call    ?GetRepositoryDirectory@CRepositoryPackager@@AEAAJQEAG@Z; CRepositoryPackager::GetRepositoryDirectory(ushort * const)
0x18003eea0  mov     ebx, eax
0x18003eea2  xor     ebp, ebp
0x18003eea4  test    ebx, ebx
0x18003eea6  js      loc_18003EF46
0x18003eeac  cmp     ebp, 6
0x18003eeaf  jz      loc_18003EF57
0x18003eeb5  lea     rcx, [rsp+38h+lpFileName]; this
0x18003eeba  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003eebf  cmp     [rsp+38h+lpFileName], 0
0x18003eec5  jnz     short loc_18003EECE
0x18003eec7  mov     ebx, 80041006h
0x18003eecc  jmp     short loc_18003EF22
0x18003eece  mov     r8, rsi; unsigned __int16 *
0x18003eed1  mov     edx, 173h; unsigned __int64
0x18003eed6  mov     rcx, [rsp+38h+lpFileName]; unsigned __int16 *
0x18003eedb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003eee0  movsxd  r8, ebp
0x18003eee3  lea     rax, off_18004A000; "$WinMgmt.CFG"
0x18003eeea  mov     r8, [rax+r8*8]; unsigned __int16 *
0x18003eeee  mov     edx, 173h; unsigned __int64
0x18003eef3  mov     rcx, [rsp+38h+lpFileName]; unsigned __int16 *
0x18003eef8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003eefd  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x18003ef02  call    cs:__imp_DeleteFileW
0x18003ef08  test    eax, eax
0x18003ef0a  jnz     short loc_18003EF22
0x18003ef0c  call    cs:__imp_GetLastError
0x18003ef12  cmp     eax, 2
0x18003ef15  jz      short loc_18003EF22
0x18003ef17  call    cs:__imp_GetLastError
0x18003ef1d  cmp     eax, 3
0x18003ef20  jnz     short loc_18003EF35
0x18003ef22  mov     rcx, [rsp+38h+lpFileName]
0x18003ef27  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003ef2d  nop
0x18003ef2e  inc     ebp
0x18003ef30  jmp     loc_18003EEA4
0x18003ef35  mov     ebx, 80041001h
0x18003ef3a  mov     rcx, [rsp+38h+lpFileName]
0x18003ef3f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003ef45  nop
0x18003ef46  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ef4c  mov     edx, ebx
0x18003ef4e  mov     rcx, rax
0x18003ef51  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ef57  lea     rax, WPP_GLOBAL_Control
0x18003ef5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef65  cmp     rcx, rax
0x18003ef68  jz      short loc_18003EF8F
0x18003ef6a  test    byte ptr [rcx+1Ch], 1
0x18003ef6e  jz      short loc_18003EF8F
0x18003ef70  cmp     byte ptr [rcx+19h], 2
0x18003ef74  jb      short loc_18003EF8F
0x18003ef76  mov     edx, 0Eh
0x18003ef7b  mov     r9d, ebx
0x18003ef7e  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003ef85  mov     rcx, [rcx+10h]
0x18003ef89  call    WPP_SF_d
0x18003ef8e  nop
0x18003ef8f  lea     rcx, [rsp+38h+var_18]
0x18003ef94  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18003ef99  mov     eax, ebx
0x18003ef9b  mov     rbx, [rsp+38h+arg_0]
0x18003efa0  mov     rbp, [rsp+38h+arg_10]
0x18003efa5  add     rsp, 30h
0x18003efa9  pop     rsi
0x18003efaa  retn
```
