# CLogger::RollOver(void)

- ea: `0x18003533c`
- end: `0x18003546f`
- name: `?RollOver@CLogger@@AEAAHXZ`
- size: `307`
- prototype: `__int64 __fastcall(CLogger *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800354f8`

## callees

- `0x1800031c0`
- `0x180004850`
- `0x1800048c0`
- `0x180004d40`
- `0x1800059ec`
- `0x180019084`
- `0x180034954`
- `0x180034a0c`
- `0x18003505c`
- `0x180035080`
- `0x18003533c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035452`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035452`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035351`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035351`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035430`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035430`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18003543e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18003543e`

## pseudocode

```c
__int64 __fastcall CLogger::RollOver(CLogger *this)
{
  __int64 v2; // rdx
  int *v3; // rdi
  __int64 v4; // rbx
  _QWORD *v5; // rax
  void *v6; // rcx
  unsigned int v7; // ebx
  LPCWSTR lpNewFileName; // [rsp+50h] [rbp+30h] BYREF
  char v10; // [rsp+58h] [rbp+38h] BYREF
  char v11; // [rsp+60h] [rbp+40h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ATL::CTime::GetTickCount(&v10);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&lpNewFileName);
  v2 = *((_QWORD *)this + 3);
  v3 = (int *)(lpNewFileName - 12);
  if ( (LPCWSTR)(v2 - 24) != lpNewFileName - 12 )
  {
    if ( v3[4] >= 0 && *(_QWORD *)(v2 - 24) == *(_QWORD *)v3 )
    {
      v4 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v3);
      lpNewFileName = (LPCWSTR)(v4 + 24);
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(&lpNewFileName, v2, *(unsigned int *)(v2 - 16));
    }
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpNewFileName, "\\");
  ATL::CSimpleStringT<wchar_t,0>::Append(
    &lpNewFileName,
    *((_QWORD *)this + 1),
    *(unsigned int *)(*((_QWORD *)this + 1) - 16LL));
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpNewFileName, ".to-");
  v5 = (_QWORD *)ATL::CTime::Format(&v10, &v11, L"%Y-%m-%d-%H.%M.%S");
  ATL::CSimpleStringT<wchar_t,0>::Append(&lpNewFileName, *v5, *(unsigned int *)(*v5 - 16LL));
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v11);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpNewFileName, ".txt");
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = -1;
  CloseHandle(v6);
  MoveFileW(*((LPCWSTR *)this + 4), lpNewFileName);
  v7 = CLogger::Open(this);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&lpNewFileName);
  return v7;
}

```

## disassembly

```asm
0x18003533c  push    rbp
0x18003533e  push    rbx
0x18003533f  push    rsi
0x180035340  push    rdi
0x180035341  push    r14
0x180035343  mov     rbp, rsp
0x180035346  sub     rsp, 20h
0x18003534a  mov     rsi, rcx
0x18003534d  add     rcx, 48h ; 'H'; lpCriticalSection
0x180035351  call    cs:__imp_EnterCriticalSection
0x180035357  lea     rcx, [rbp+arg_8]
0x18003535b  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180035360  lea     rcx, [rbp+lpNewFileName]
0x180035364  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180035369  nop
0x18003536a  mov     rdx, [rsi+18h]
0x18003536e  lea     rcx, [rdx-18h]
0x180035372  mov     rdi, [rbp+lpNewFileName]
0x180035376  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18003537a  cmp     rcx, rdi
0x18003537d  jz      short loc_1800353B4
0x18003537f  cmp     dword ptr [rdi+10h], 0
0x180035383  jl      short loc_1800353A7
0x180035385  mov     rax, [rdi]
0x180035388  cmp     [rcx], rax
0x18003538b  jnz     short loc_1800353A7
0x18003538d  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180035392  mov     rbx, rax
0x180035395  mov     rcx, rdi; this
0x180035398  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003539d  lea     rax, [rbx+18h]
0x1800353a1  mov     [rbp+lpNewFileName], rax
0x1800353a5  jmp     short loc_1800353B4
0x1800353a7  mov     r8d, [rdx-10h]
0x1800353ab  lea     rcx, [rbp+lpNewFileName]
0x1800353af  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800353b4  lea     rdx, asc_180047FEC; "\\"
0x1800353bb  lea     rcx, [rbp+lpNewFileName]
0x1800353bf  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x1800353c4  mov     rdx, [rsi+8]
0x1800353c8  mov     r8d, [rdx-10h]
0x1800353cc  lea     rcx, [rbp+lpNewFileName]
0x1800353d0  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x1800353d5  lea     rdx, aTo; ".to-"
0x1800353dc  lea     rcx, [rbp+lpNewFileName]
0x1800353e0  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x1800353e5  lea     r8, aYMDHMS; "%Y-%m-%d-%H.%M.%S"
0x1800353ec  lea     rdx, [rbp+arg_10]
0x1800353f0  lea     rcx, [rbp+arg_8]
0x1800353f4  call    ?Format@CTime@ATL@@QEBA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@PEB_W@Z; ATL::CTime::Format(wchar_t const *)
0x1800353f9  nop
0x1800353fa  mov     rdx, [rax]
0x1800353fd  mov     r8d, [rdx-10h]
0x180035401  lea     rcx, [rbp+lpNewFileName]
0x180035405  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x18003540a  nop
0x18003540b  lea     rcx, [rbp+arg_10]
0x18003540f  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180035414  lea     rdx, aTxt_1; ".txt"
0x18003541b  lea     rcx, [rbp+lpNewFileName]
0x18003541f  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180035424  mov     rcx, [rsi+30h]; hObject
0x180035428  mov     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x180035430  call    cs:__imp_CloseHandle
0x180035436  mov     rdx, [rbp+lpNewFileName]; lpNewFileName
0x18003543a  mov     rcx, [rsi+20h]; lpExistingFileName
0x18003543e  call    cs:__imp_MoveFileW
0x180035444  mov     rcx, rsi; this
0x180035447  call    ?Open@CLogger@@QEAAHXZ; CLogger::Open(void)
0x18003544c  mov     ebx, eax
0x18003544e  lea     rcx, [rsi+48h]; lpCriticalSection
0x180035452  call    cs:__imp_LeaveCriticalSection
0x180035458  nop
0x180035459  lea     rcx, [rbp+lpNewFileName]
0x18003545d  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180035462  mov     eax, ebx
0x180035464  add     rsp, 20h
0x180035468  pop     r14
0x18003546a  pop     rdi
0x18003546b  pop     rsi
0x18003546c  pop     rbx
0x18003546d  pop     rbp
0x18003546e  retn
```
