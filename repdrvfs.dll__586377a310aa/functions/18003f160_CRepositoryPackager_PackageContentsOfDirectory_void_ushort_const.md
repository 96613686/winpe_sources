# CRepositoryPackager::PackageContentsOfDirectory(void *,ushort const *)

- ea: `0x18003f160`
- end: `0x18003f300`
- name: `?PackageContentsOfDirectory@CRepositoryPackager@@AEAAJPEAXPEBG@Z`
- size: `416`
- prototype: `int(CRepositoryPackager *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003f308`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023bf0`
- `0x18003f160`
- `0x18003f624`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f2ce`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f2ce`
- `wbemcomn!GetMemLogObject` at `0x18003f280`
- `wbemcomn!GetMemLogObject` at `0x18003f280`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f28b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f28b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003f1f1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003f1f1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003f269`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003f269`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003f276`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003f276`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRepositoryPackager::PackageContentsOfDirectory(
        CRepositoryPackager *this,
        void *a2,
        const unsigned __int16 *a3)
{
  int v5; // ebx
  unsigned int v6; // r10d
  CRepositoryPackager *v7; // rcx
  HANDLE FirstFileW; // rsi
  int v9; // edx
  int v10; // edx
  CMemoryLog *MemLogObject; // rax
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-288h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-278h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  CFileName::CFileName((CFileName *)lpFileName);
  if ( !lpFileName[0] )
  {
    v5 = -2147217402;
LABEL_16:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v5);
    goto LABEL_17;
  }
  StringCchCopyW((unsigned __int16 *)lpFileName[0], 0x173u, a3);
  StringCchCatW((unsigned __int16 *)lpFileName[0], v6, L"\\*");
  FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v5 = -2147217407;
    goto LABEL_16;
  }
  v5 = 0;
  do
  {
    v9 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
    {
      v7 = 0;
      v9 = FindFileData.cFileName[1];
    }
    if ( v9 )
    {
      v10 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
      {
        v10 = FindFileData.cFileName[1] - 46;
        if ( FindFileData.cFileName[1] == 46 )
        {
          v7 = 0;
          v10 = FindFileData.cFileName[2];
        }
      }
      if ( v10 )
      {
        v5 = CRepositoryPackager::PackageFile(v7, a2, a3, FindFileData.cFileName);
        if ( v5 < 0 )
          break;
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  FindClose(FirstFileW);
  if ( v5 < 0 )
    goto LABEL_16;
LABEL_17:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, (unsigned int)v5);
  }
  CWin32DefaultArena::WbemMemFree((void *)lpFileName[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003f160  mov     [rsp+arg_0], rbx
0x18003f165  mov     [rsp+arg_18], rbp
0x18003f16a  push    rsi
0x18003f16b  push    r14
0x18003f16d  push    r15
0x18003f16f  sub     rsp, 290h
0x18003f176  mov     rax, cs:__security_cookie
0x18003f17d  xor     rax, rsp
0x18003f180  mov     [rsp+2A8h+var_28], rax
0x18003f188  mov     rbp, r8
0x18003f18b  mov     r14, rdx
0x18003f18e  xor     edx, edx; Val
0x18003f190  mov     r8d, 250h; Size
0x18003f196  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x18003f19b  call    memset_0
0x18003f1a0  lea     rcx, [rsp+2A8h+lpFileName]; this
0x18003f1a5  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003f1aa  nop
0x18003f1ab  cmp     [rsp+2A8h+lpFileName], 0
0x18003f1b1  jnz     short loc_18003F1BD
0x18003f1b3  mov     ebx, 80041006h
0x18003f1b8  jmp     loc_18003F280
0x18003f1bd  mov     r8, rbp; unsigned __int16 *
0x18003f1c0  mov     r10d, 173h
0x18003f1c6  mov     edx, r10d; unsigned __int64
0x18003f1c9  mov     rcx, [rsp+2A8h+lpFileName]; unsigned __int16 *
0x18003f1ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f1d3  lea     r8, asc_18004D08C; "\\*"
0x18003f1da  mov     edx, r10d; unsigned __int64
0x18003f1dd  mov     rcx, [rsp+2A8h+lpFileName]; unsigned __int16 *
0x18003f1e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f1e7  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18003f1ec  mov     rcx, [rsp+2A8h+lpFileName]; lpFileName
0x18003f1f1  call    cs:__imp_FindFirstFileW
0x18003f1f7  mov     rsi, rax
0x18003f1fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f1fe  jnz     short loc_18003F207
0x18003f200  mov     ebx, 80041001h
0x18003f205  jmp     short loc_18003F280
0x18003f207  xor     ebx, ebx
0x18003f209  lea     r15d, [rbx+2Eh]
0x18003f20d  movzx   edx, [rsp+2A8h+FindFileData.cFileName]
0x18003f212  sub     edx, r15d
0x18003f215  jnz     short loc_18003F223
0x18003f217  movzx   edx, [rsp+2A8h+FindFileData.cFileName+2]
0x18003f21c  xor     eax, eax
0x18003f21e  movzx   ecx, ax
0x18003f221  sub     edx, ecx
0x18003f223  test    edx, edx
0x18003f225  jz      short loc_18003F261
0x18003f227  movzx   edx, [rsp+2A8h+FindFileData.cFileName]
0x18003f22c  sub     edx, r15d
0x18003f22f  jnz     short loc_18003F247
0x18003f231  movzx   edx, [rsp+2A8h+FindFileData.cFileName+2]
0x18003f236  sub     edx, r15d
0x18003f239  jnz     short loc_18003F247
0x18003f23b  movzx   edx, [rsp+2A8h+FindFileData.cFileName+4]
0x18003f240  xor     eax, eax
0x18003f242  movzx   ecx, ax; this
0x18003f245  sub     edx, ecx
0x18003f247  test    edx, edx
0x18003f249  jz      short loc_18003F261
0x18003f24b  lea     r9, [rsp+2A8h+FindFileData.cFileName]; unsigned __int16 *
0x18003f250  mov     r8, rbp; unsigned __int16 *
0x18003f253  mov     rdx, r14; void *
0x18003f256  call    ?PackageFile@CRepositoryPackager@@AEAAJPEAXPEBGPEAG@Z; CRepositoryPackager::PackageFile(void *,ushort const *,ushort *)
0x18003f25b  mov     ebx, eax
0x18003f25d  test    eax, eax
0x18003f25f  js      short loc_18003F273
0x18003f261  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18003f266  mov     rcx, rsi; hFindFile
0x18003f269  call    cs:__imp_FindNextFileW
0x18003f26f  test    eax, eax
0x18003f271  jnz     short loc_18003F20D
0x18003f273  mov     rcx, rsi; hFindFile
0x18003f276  call    cs:__imp_FindClose
0x18003f27c  test    ebx, ebx
0x18003f27e  jns     short loc_18003F291
0x18003f280  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003f286  mov     edx, ebx
0x18003f288  mov     rcx, rax
0x18003f28b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f291  lea     rax, WPP_GLOBAL_Control
0x18003f298  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f29f  cmp     rcx, rax
0x18003f2a2  jz      short loc_18003F2C9
0x18003f2a4  test    byte ptr [rcx+1Ch], 1
0x18003f2a8  jz      short loc_18003F2C9
0x18003f2aa  cmp     byte ptr [rcx+19h], 2
0x18003f2ae  jb      short loc_18003F2C9
0x18003f2b0  mov     edx, 10h
0x18003f2b5  mov     r9d, ebx
0x18003f2b8  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003f2bf  mov     rcx, [rcx+10h]
0x18003f2c3  call    WPP_SF_d
0x18003f2c8  nop
0x18003f2c9  mov     rcx, [rsp+2A8h+lpFileName]
0x18003f2ce  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003f2d4  nop
0x18003f2d5  mov     eax, ebx
0x18003f2d7  mov     rcx, [rsp+2A8h+var_28]
0x18003f2df  xor     rcx, rsp; StackCookie
0x18003f2e2  call    __security_check_cookie
0x18003f2e7  lea     r11, [rsp+2A8h+var_18]
0x18003f2ef  mov     rbx, [r11+20h]
0x18003f2f3  mov     rbp, [r11+38h]
0x18003f2f7  mov     rsp, r11
0x18003f2fa  pop     r15
0x18003f2fc  pop     r14
0x18003f2fe  pop     rsi
0x18003f2ff  retn
```
