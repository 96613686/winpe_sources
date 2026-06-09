# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x180019194`
- end: `0x180019311`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001964c`

## callees

- `0x180009838`
- `0x180009994`
- `0x1800099b8`
- `0x18000c120`
- `0x180010924`
- `0x180013b90`
- `0x180018ad0`
- `0x180019194`
- `0x180019870`
- `0x18001a684`
- `0x18001a7fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800191c6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019207`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019249`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800191c6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019207`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019249`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800192af`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800192af`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const char *a3,
        const struct _RSDS *a4)
{
  _QWORD *v7; // r14
  const WCHAR *v8; // rbx
  unsigned int v9; // edi
  int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int Error; // eax
  __int64 v15; // rcx
  LPCWSTR lpPathName; // [rsp+70h] [rbp+8h] BYREF

  v7 = (_QWORD *)((char *)this + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 56);
  v8 = lpPathName;
  if ( CreateDirectoryW(lpPathName, 0)
    || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &lpPathName,
      L"\\%hs",
      a3);
    v8 = lpPathName;
    if ( CreateDirectoryW(lpPathName, 0)
      || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
    {
      Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
        v10,
        (unsigned int)&lpPathName,
        *v7,
        (_DWORD)a3,
        (__int64)a4);
      v8 = lpPathName;
      if ( CreateDirectoryW(lpPathName, 0)
        || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
      {
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpPathName, L"\\");
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
          &lpPathName,
          a3);
        v8 = lpPathName;
        if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          McTemplateU0zz_EventWriteTransfer(v12, v11, a2, lpPathName);
        if ( CopyFileW(a2, v8, 0) )
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
            McTemplateU0q_EventWriteTransfer(v13, TraceMerge_NGEN_CopyingPDB_Stop, 0);
          v9 = 0;
        }
        else
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          {
            Error = ATL::AtlHresultFromLastError();
            McTemplateU0q_EventWriteTransfer(v15, TraceMerge_NGEN_CopyingPDB_Stop, Error);
          }
          v9 = ATL::AtlHresultFromLastError();
        }
      }
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  return v9;
}

```

## disassembly

```asm
0x180019194  push    rbx
0x180019196  push    rbp
0x180019197  push    rsi
0x180019198  push    rdi
0x180019199  push    r14
0x18001919b  push    r15
0x18001919d  sub     rsp, 38h
0x1800191a1  mov     r15, r9
0x1800191a4  mov     rsi, r8
0x1800191a7  mov     rbp, rdx
0x1800191aa  lea     r14, [rcx+38h]
0x1800191ae  mov     rdx, r14
0x1800191b1  lea     rcx, [rsp+68h+lpPathName]
0x1800191b6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800191bb  nop
0x1800191bc  xor     edx, edx; lpSecurityAttributes
0x1800191be  mov     rbx, [rsp+68h+lpPathName]
0x1800191c3  mov     rcx, rbx; lpPathName
0x1800191c6  call    cs:__imp_CreateDirectoryW
0x1800191cc  test    eax, eax
0x1800191ce  jnz     short loc_1800191E9
0x1800191d0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800191d5  mov     edi, eax
0x1800191d7  mov     ecx, 0B7h; unsigned int
0x1800191dc  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800191e1  cmp     edi, eax
0x1800191e3  jnz     loc_1800192F9
0x1800191e9  mov     r8, rsi
0x1800191ec  lea     rdx, aHs_0; "\\%hs"
0x1800191f3  lea     rcx, [rsp+68h+lpPathName]
0x1800191f8  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800191fd  xor     edx, edx; lpSecurityAttributes
0x1800191ff  mov     rbx, [rsp+68h+lpPathName]
0x180019204  mov     rcx, rbx; lpPathName
0x180019207  call    cs:__imp_CreateDirectoryW
0x18001920d  test    eax, eax
0x18001920f  jnz     short loc_18001922A
0x180019211  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019216  mov     edi, eax
0x180019218  mov     ecx, 0B7h; unsigned int
0x18001921d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019222  cmp     edi, eax
0x180019224  jnz     loc_1800192F9
0x18001922a  mov     [rsp+68h+var_48], r15
0x18001922f  mov     r9, rsi
0x180019232  mov     r8, [r14]
0x180019235  lea     rdx, [rsp+68h+lpPathName]
0x18001923a  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x18001923f  xor     edx, edx; lpSecurityAttributes
0x180019241  mov     rbx, [rsp+68h+lpPathName]
0x180019246  mov     rcx, rbx; lpPathName
0x180019249  call    cs:__imp_CreateDirectoryW
0x18001924f  test    eax, eax
0x180019251  jnz     short loc_18001926C
0x180019253  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019258  mov     edi, eax
0x18001925a  mov     ecx, 0B7h; unsigned int
0x18001925f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019264  cmp     edi, eax
0x180019266  jnz     loc_1800192F9
0x18001926c  lea     rdx, asc_180029930; "\\"
0x180019273  lea     rcx, [rsp+68h+lpPathName]
0x180019278  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001927d  mov     rdx, rsi
0x180019280  lea     rcx, [rsp+68h+lpPathName]
0x180019285  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18001928a  mov     rbx, [rsp+68h+lpPathName]
0x18001928f  mov     dil, 1
0x180019292  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x180019299  jz      short loc_1800192A6
0x18001929b  mov     r9, rbx
0x18001929e  mov     r8, rbp
0x1800192a1  call    McTemplateU0zz_EventWriteTransfer
0x1800192a6  xor     r8d, r8d; bFailIfExists
0x1800192a9  mov     rdx, rbx; lpNewFileName
0x1800192ac  mov     rcx, rbp; lpExistingFileName
0x1800192af  call    cs:__imp_CopyFileW
0x1800192b5  test    eax, eax
0x1800192b7  jnz     short loc_1800192DF
0x1800192b9  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x1800192c0  jz      short loc_1800192D6
0x1800192c2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800192c7  mov     r8d, eax
0x1800192ca  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x1800192d1  call    McTemplateU0q_EventWriteTransfer
0x1800192d6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800192db  mov     edi, eax
0x1800192dd  jmp     short loc_1800192F9
0x1800192df  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x1800192e6  jz      short loc_1800192F7
0x1800192e8  xor     r8d, r8d
0x1800192eb  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x1800192f2  call    McTemplateU0q_EventWriteTransfer
0x1800192f7  xor     edi, edi
0x1800192f9  lea     rcx, [rbx-18h]; this
0x1800192fd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019302  mov     eax, edi
0x180019304  add     rsp, 38h
0x180019308  pop     r15
0x18001930a  pop     r14
0x18001930c  pop     rdi
0x18001930d  pop     rsi
0x18001930e  pop     rbp
0x18001930f  pop     rbx
0x180019310  retn
```
