# CFileCache::RepositoryExists(ushort const *)

- ea: `0x18003dda4`
- end: `0x18003def5`
- name: `?RepositoryExists@CFileCache@@AEAAJPEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(CFileCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003db10`

## callees

- `0x1800012b8`
- `0x1800216c8`
- `0x180023bf0`
- `0x18003dda4`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003de12`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003de9b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003dee6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003de12`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003de9b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003dee6`
- `wbemcomn!GetMemLogObject` at `0x18003ddc4`
- `wbemcomn!GetMemLogObject` at `0x18003de49`
- `wbemcomn!GetMemLogObject` at `0x18003ddc4`
- `wbemcomn!GetMemLogObject` at `0x18003de49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ddd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003de57`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ddd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003de57`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003de3e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003de3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFileCache::RepositoryExists(const WCHAR *this, const unsigned __int16 *a2)
{
  CMemoryLog *v3; // rax
  CMemoryLog *MemLogObject; // rax
  LPCWSTR lpFileName; // [rsp+30h] [rbp+8h] BYREF

  lpFileName = this;
  CFileName::CFileName((CFileName *)&lpFileName);
  if ( lpFileName )
  {
    StringCchPrintfW((unsigned __int16 *)lpFileName, 0x173u, L"%s\\index.btr", a2);
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, 2);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids, 2);
      }
      CWin32DefaultArena::WbemMemFree((void *)lpFileName);
      return 2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids, 0);
      }
      CWin32DefaultArena::WbemMemFree((void *)lpFileName);
      return 0;
    }
  }
  else
  {
    v3 = GetMemLogObject();
    CMemoryLog::Write(v3, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 14;
  }
}

```

## disassembly

```asm
0x18003dda4  mov     [rsp+lpFileName], rcx
0x18003dda9  push    rdi
0x18003ddaa  sub     rsp, 20h
0x18003ddae  mov     rdi, rdx
0x18003ddb1  lea     rcx, [rsp+28h+lpFileName]; this
0x18003ddb6  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003ddbb  nop
0x18003ddbc  cmp     [rsp+28h+lpFileName], 0
0x18003ddc2  jnz     short loc_18003DE20
0x18003ddc4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ddca  mov     edi, 0Eh
0x18003ddcf  mov     edx, edi
0x18003ddd1  mov     rcx, rax
0x18003ddd4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ddda  lea     rax, WPP_GLOBAL_Control
0x18003dde1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dde8  cmp     rcx, rax
0x18003ddeb  jz      short loc_18003DE10
0x18003dded  test    byte ptr [rcx+1Ch], 1
0x18003ddf1  jz      short loc_18003DE10
0x18003ddf3  cmp     byte ptr [rcx+19h], 2
0x18003ddf7  jb      short loc_18003DE10
0x18003ddf9  lea     edx, [rdi-1]
0x18003ddfc  mov     r9d, edi
0x18003ddff  lea     r8, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids
0x18003de06  mov     rcx, [rcx+10h]
0x18003de0a  call    WPP_SF_d
0x18003de0f  nop
0x18003de10  xor     ecx, ecx
0x18003de12  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003de18  nop
0x18003de19  mov     eax, edi
0x18003de1b  jmp     loc_18003DEEF
0x18003de20  mov     r9, rdi
0x18003de23  lea     r8, aSIndexBtr; "%s\\index.btr"
0x18003de2a  mov     edx, 173h; unsigned __int64
0x18003de2f  mov     rcx, [rsp+28h+lpFileName]; unsigned __int16 *
0x18003de34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003de39  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x18003de3e  call    cs:__imp_GetFileAttributesW
0x18003de44  cmp     eax, 0FFFFFFFFh
0x18003de47  jnz     short loc_18003DEA9
0x18003de49  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003de4f  mov     edx, 2
0x18003de54  mov     rcx, rax
0x18003de57  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003de5d  lea     rax, WPP_GLOBAL_Control
0x18003de64  mov     rcx, cs:WPP_GLOBAL_Control
0x18003de6b  cmp     rcx, rax
0x18003de6e  jz      short loc_18003DE96
0x18003de70  test    byte ptr [rcx+1Ch], 1
0x18003de74  jz      short loc_18003DE96
0x18003de76  cmp     byte ptr [rcx+19h], 2
0x18003de7a  jb      short loc_18003DE96
0x18003de7c  mov     edx, 0Eh
0x18003de81  lea     r9d, [rdx-0Ch]
0x18003de85  lea     r8, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids
0x18003de8c  mov     rcx, [rcx+10h]
0x18003de90  call    WPP_SF_d
0x18003de95  nop
0x18003de96  mov     rcx, [rsp+28h+lpFileName]
0x18003de9b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003dea1  nop
0x18003dea2  mov     eax, 2
0x18003dea7  jmp     short loc_18003DEEF
0x18003dea9  lea     rax, WPP_GLOBAL_Control
0x18003deb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003deb7  cmp     rcx, rax
0x18003deba  jz      short loc_18003DEE1
0x18003debc  test    byte ptr [rcx+1Ch], 1
0x18003dec0  jz      short loc_18003DEE1
0x18003dec2  cmp     byte ptr [rcx+19h], 2
0x18003dec6  jb      short loc_18003DEE1
0x18003dec8  mov     edx, 0Fh
0x18003decd  xor     r9d, r9d
0x18003ded0  lea     r8, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids
0x18003ded7  mov     rcx, [rcx+10h]
0x18003dedb  call    WPP_SF_d
0x18003dee0  nop
0x18003dee1  mov     rcx, [rsp+28h+lpFileName]
0x18003dee6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003deec  nop
0x18003deed  xor     eax, eax
0x18003deef  add     rsp, 20h
0x18003def3  pop     rdi
0x18003def4  retn
```
