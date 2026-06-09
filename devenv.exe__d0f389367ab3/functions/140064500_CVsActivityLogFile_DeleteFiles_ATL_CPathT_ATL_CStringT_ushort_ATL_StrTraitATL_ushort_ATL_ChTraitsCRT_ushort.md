# CVsActivityLogFile::DeleteFiles(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>)

- ea: `0x140064500`
- end: `0x14006463e`
- name: `?DeleteFiles@CVsActivityLogFile@@AEAAXV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140064640`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140008120`
- `0x140033ab0`
- `0x140064500`
- `0x140064b20`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14006459d`
- `KERNEL32!DeleteFileW` at `0x14006459d`
- `KERNEL32!FindClose` at `0x1400645b8`
- `KERNEL32!FindClose` at `0x1400645b8`
- `KERNEL32!FindNextFileW` at `0x1400645ab`
- `KERNEL32!FindNextFileW` at `0x1400645ab`
- `KERNEL32!FindFirstFileW` at `0x14006453b`
- `KERNEL32!FindFirstFileW` at `0x14006453b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVsActivityLogFile::DeleteFiles(__int64 a1, LPCWSTR *a2)
{
  HANDLE FirstFileW; // rdi
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR **LogFileFolder; // rax
  LPCWSTR v7; // rdx
  volatile signed __int32 *v8; // rdx
  signed __int32 v9; // eax
  bool v10; // cc
  __int64 result; // rax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR *p_lpFileName; // [rsp+28h] [rbp-D8h]
  LPCWSTR *v14; // [rsp+30h] [rbp-D0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  v14 = a2;
  FirstFileW = FindFirstFileW(*a2, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    lpFileName = 0;
    p_lpFileName = &lpFileName;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    lpFileName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                         + 24);
    do
    {
      LogFileFolder = (const WCHAR **)CVsActivityLogFile::GetLogFileFolder(a1);
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
        (LPWSTR *)&lpFileName,
        *LogFileFolder,
        FindFileData.cFileName);
      DeleteFileW(lpFileName);
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    FindClose(FirstFileW);
    p_lpFileName = &lpFileName;
    v7 = lpFileName - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpFileName - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
    }
  }
  p_lpFileName = a2;
  v8 = (volatile signed __int32 *)(*a2 - 12);
  v9 = _InterlockedExchangeAdd(v8 + 4, 0xFFFFFFFF);
  v10 = v9 <= 1;
  result = (unsigned int)(v9 - 1);
  if ( v10 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  }
  return result;
}

```

## disassembly

```asm
0x140064500  mov     [rsp-8+arg_10], rbx
0x140064505  push    rbp
0x140064506  push    rsi
0x140064507  push    rdi
0x140064508  lea     rbp, [rsp-1A0h]
0x140064510  sub     rsp, 2A0h
0x140064517  mov     rax, cs:__security_cookie
0x14006451e  xor     rax, rsp
0x140064521  mov     [rbp+1B0h+var_20], rax
0x140064528  mov     rbx, rdx
0x14006452b  mov     rsi, rcx
0x14006452e  mov     [rsp+2B0h+var_280], rdx
0x140064533  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x140064538  mov     rcx, [rbx]; lpFileName
0x14006453b  call    cs:__imp_FindFirstFileW
0x140064541  mov     rdi, rax
0x140064544  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140064548  jz      loc_1400645EC
0x14006454e  and     [rsp+2B0h+lpFileName], 0
0x140064554  lea     rax, [rsp+2B0h+lpFileName]
0x140064559  mov     [rsp+2B0h+var_288], rax
0x14006455e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140064563  mov     rcx, rax
0x140064566  test    rax, rax
0x140064569  jz      loc_140064633
0x14006456f  mov     rax, [rax]
0x140064572  call    qword ptr [rax+18h]
0x140064575  add     rax, 18h
0x140064579  mov     [rsp+2B0h+lpFileName], rax
0x14006457e  mov     rcx, rsi
0x140064581  call    ?GetLogFileFolder@CVsActivityLogFile@@AEAAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CVsActivityLogFile::GetLogFileFolder(void)
0x140064586  lea     r8, [rsp+2B0h+FindFileData.cFileName]
0x14006458b  mov     rdx, [rax]
0x14006458e  lea     rcx, [rsp+2B0h+lpFileName]
0x140064593  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x140064598  mov     rcx, [rsp+2B0h+lpFileName]; lpFileName
0x14006459d  call    cs:__imp_DeleteFileW
0x1400645a3  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1400645a8  mov     rcx, rdi; hFindFile
0x1400645ab  call    cs:__imp_FindNextFileW
0x1400645b1  test    eax, eax
0x1400645b3  jnz     short loc_14006457E
0x1400645b5  mov     rcx, rdi; hFindFile
0x1400645b8  call    cs:__imp_FindClose
0x1400645be  nop
0x1400645bf  lea     rax, [rsp+2B0h+lpFileName]
0x1400645c4  mov     [rsp+2B0h+var_288], rax
0x1400645c9  mov     rdx, [rsp+2B0h+lpFileName]
0x1400645ce  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400645d2  or      eax, 0FFFFFFFFh
0x1400645d5  lock xadd [rdx+10h], eax
0x1400645da  sub     eax, 1
0x1400645dd  jg      short loc_1400645EC
0x1400645df  lfence
0x1400645e2  mov     rcx, [rdx]
0x1400645e5  mov     rax, [rcx]
0x1400645e8  call    qword ptr [rax+8]
0x1400645eb  nop
0x1400645ec  mov     [rsp+2B0h+var_288], rbx
0x1400645f1  mov     rdx, [rbx]
0x1400645f4  sub     rdx, 18h
0x1400645f8  or      eax, 0FFFFFFFFh
0x1400645fb  lock xadd [rdx+10h], eax
0x140064600  sub     eax, 1
0x140064603  jg      short loc_140064611
0x140064605  lfence
0x140064608  mov     rcx, [rdx]
0x14006460b  mov     rax, [rcx]
0x14006460e  call    qword ptr [rax+8]
0x140064611  mov     rcx, [rbp+1B0h+var_20]
0x140064618  xor     rcx, rsp; StackCookie
0x14006461b  call    __security_check_cookie
0x140064620  mov     rbx, [rsp+2B0h+arg_10]
0x140064628  add     rsp, 2A0h
0x14006462f  pop     rdi
0x140064630  pop     rsi
0x140064631  pop     rbp
0x140064632  retn
0x140064633  mov     ecx, 80004005h; int
0x140064638  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
