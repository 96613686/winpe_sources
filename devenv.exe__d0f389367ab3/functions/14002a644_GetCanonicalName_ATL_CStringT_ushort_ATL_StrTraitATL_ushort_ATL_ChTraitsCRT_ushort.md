# GetCanonicalName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x14002a644`
- end: `0x14002a808`
- name: `?GetCanonicalName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `452`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x14001d8a0`
- `0x1400238d0`
- `0x140046030`
- `0x14004b3d0`
- `0x14004b5f0`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002dd0`
- `0x140003160`
- `0x140004950`
- `0x140023b80`
- `0x14002a644`
- `0x14002a810`
- `0x140033ab0`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x14002a6f0`
- `KERNEL32!GetLongPathNameW` at `0x14002a6f0`
- `KERNEL32!GetLastError` at `0x14002a747`
- `KERNEL32!GetLastError` at `0x14002a747`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14002a709`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14002a709`
- `SHLWAPI!PathIsDirectoryW` at `0x14002a783`
- `SHLWAPI!PathIsDirectoryW` at `0x14002a783`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCanonicalName(LPCWSTR *a1)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v4; // rax
  WCHAR *v5; // rdx
  DWORD LongPathNameW; // ebx
  LPWSTR v7; // rcx
  int v8; // eax
  int PreservedFileNameCasing; // ebx
  LPCWSTR v10; // rdx
  LPWSTR v11; // rdx
  LPCWSTR pszPath; // [rsp+20h] [rbp-20h] BYREF
  LPWSTR lpszLongPath; // [rsp+28h] [rbp-18h] BYREF

  if ( !*((_DWORD *)*a1 - 4) )
    return 2147942487LL;
  lpszLongPath = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v4 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
  v5 = (WCHAR *)(v4 + 24);
  lpszLongPath = (LPWSTR)(v4 + 24);
  if ( ((1 - *(_DWORD *)(v4 + 16)) | (*(_DWORD *)(v4 + 12) - 261)) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpszLongPath, 261);
    v5 = lpszLongPath;
  }
  LongPathNameW = GetLongPathNameW(*a1, v5, 0x104u);
  v7 = lpszLongPath;
  if ( lpszLongPath )
  {
    v8 = wcsnlen(lpszLongPath, *((int *)lpszLongPath - 3));
    if ( v8 < 0 )
      goto LABEL_25;
    v7 = lpszLongPath;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 > *((_DWORD *)v7 - 3) )
LABEL_25:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)v7 - 4) = v8;
  lpszLongPath[v8] = 0;
  if ( LongPathNameW <= 0x104 )
  {
    if ( !LongPathNameW )
    {
      GetLastError();
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpszLongPath, a1);
    }
    pszPath = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &pszPath,
      lpszLongPath);
    PreservedFileNameCasing = GetPreservedFileNameCasing(&pszPath);
    if ( PreservedFileNameCasing >= 0 )
    {
      if ( PathIsDirectoryW(pszPath) )
        ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::AddBackslash(&pszPath);
      ATL::CSimpleStringT<unsigned short,0>::operator=(a1, &pszPath);
      PreservedFileNameCasing = 0;
    }
    v10 = pszPath - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
    }
  }
  else
  {
    PreservedFileNameCasing = -2147417803;
  }
  v11 = lpszLongPath - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpszLongPath - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  }
  return (unsigned int)PreservedFileNameCasing;
}

```

## disassembly

```asm
0x14002a644  mov     [rsp-8+arg_8], rbx
0x14002a649  mov     [rsp-8+arg_10], rsi
0x14002a64e  mov     [rsp-8+arg_18], rdi
0x14002a653  push    rbp
0x14002a654  mov     rbp, rsp
0x14002a657  sub     rsp, 40h
0x14002a65b  mov     rax, cs:__security_cookie
0x14002a662  xor     rax, rsp
0x14002a665  mov     [rbp+var_10], rax
0x14002a669  mov     rdi, rcx
0x14002a66c  mov     rax, [rcx]
0x14002a66f  xor     esi, esi
0x14002a671  cmp     [rax-10h], esi
0x14002a674  jnz     short loc_14002A69C
0x14002a676  mov     eax, 80070057h
0x14002a67b  mov     rcx, [rbp+var_10]
0x14002a67f  xor     rcx, rsp; StackCookie
0x14002a682  call    __security_check_cookie
0x14002a687  mov     rbx, [rsp+40h+arg_8]
0x14002a68c  mov     rsi, [rsp+40h+arg_10]
0x14002a691  mov     rdi, [rsp+40h+arg_18]
0x14002a696  add     rsp, 40h
0x14002a69a  pop     rbp
0x14002a69b  retn
0x14002a69c  mov     [rbp+lpszLongPath], rsi
0x14002a6a0  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a6a5  mov     rcx, rax
0x14002a6a8  test    rax, rax
0x14002a6ab  jz      loc_14002A7EF
0x14002a6b1  mov     rax, [rax]
0x14002a6b4  call    qword ptr [rax+18h]
0x14002a6b7  lea     rdx, [rax+18h]
0x14002a6bb  mov     [rbp+lpszLongPath], rdx
0x14002a6bf  mov     ecx, 1
0x14002a6c4  sub     ecx, [rdx-8]
0x14002a6c7  mov     eax, [rdx-0Ch]
0x14002a6ca  mov     r8d, 105h
0x14002a6d0  sub     eax, r8d
0x14002a6d3  or      eax, ecx
0x14002a6d5  jge     short loc_14002A6E7
0x14002a6d7  mov     edx, r8d
0x14002a6da  lea     rcx, [rbp+lpszLongPath]
0x14002a6de  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14002a6e3  mov     rdx, [rbp+lpszLongPath]; lpszLongPath
0x14002a6e7  mov     r8d, 104h; cchBuffer
0x14002a6ed  mov     rcx, [rdi]; lpszShortPath
0x14002a6f0  call    cs:__imp_GetLongPathNameW
0x14002a6f6  mov     ebx, eax
0x14002a6f8  mov     rcx, [rbp+lpszLongPath]; Source
0x14002a6fc  test    rcx, rcx
0x14002a6ff  jnz     short loc_14002A705
0x14002a701  mov     eax, esi
0x14002a703  jmp     short loc_14002A71B
0x14002a705  movsxd  rdx, dword ptr [rcx-0Ch]; MaxCount
0x14002a709  call    cs:__imp_wcsnlen
0x14002a70f  test    eax, eax
0x14002a711  js      loc_14002A7FD
0x14002a717  mov     rcx, [rbp+lpszLongPath]
0x14002a71b  cmp     eax, [rcx-0Ch]
0x14002a71e  jg      loc_14002A7FD
0x14002a724  mov     [rcx-10h], eax
0x14002a727  mov     ecx, eax
0x14002a729  mov     rax, [rbp+lpszLongPath]
0x14002a72d  mov     [rax+rcx*2], si
0x14002a731  cmp     ebx, 104h
0x14002a737  jbe     short loc_14002A743
0x14002a739  mov     ebx, 80010135h
0x14002a73e  jmp     loc_14002A7C6
0x14002a743  test    ebx, ebx
0x14002a745  jnz     short loc_14002A759
0x14002a747  call    cs:__imp_GetLastError
0x14002a74d  mov     rdx, rdi
0x14002a750  lea     rcx, [rbp+lpszLongPath]
0x14002a754  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002a759  mov     [rbp+pszPath], rsi
0x14002a75d  mov     rdx, [rbp+lpszLongPath]
0x14002a761  lea     rcx, [rbp+pszPath]
0x14002a765  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002a76a  nop
0x14002a76b  nop     dword ptr [rax+rax+00h]
0x14002a770  lea     rcx, [rbp+pszPath]
0x14002a774  call    ?GetPreservedFileNameCasing@@YAJAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@_N@Z; GetPreservedFileNameCasing(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,bool)
0x14002a779  mov     ebx, eax
0x14002a77b  test    eax, eax
0x14002a77d  js      short loc_14002A7A4
0x14002a77f  mov     rcx, [rbp+pszPath]; pszPath
0x14002a783  call    cs:__imp_PathIsDirectoryW
0x14002a789  test    eax, eax
0x14002a78b  jz      short loc_14002A796
0x14002a78d  lea     rcx, [rbp+pszPath]
0x14002a791  call    ?AddBackslash@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::AddBackslash(void)
0x14002a796  lea     rdx, [rbp+pszPath]
0x14002a79a  mov     rcx, rdi
0x14002a79d  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002a7a2  mov     ebx, esi
0x14002a7a4  mov     rdx, [rbp+pszPath]
0x14002a7a8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002a7ac  or      eax, 0FFFFFFFFh
0x14002a7af  lock xadd [rdx+10h], eax
0x14002a7b4  sub     eax, 1
0x14002a7b7  jg      short loc_14002A7C6
0x14002a7b9  lfence
0x14002a7bc  mov     rcx, [rdx]
0x14002a7bf  mov     rax, [rcx]
0x14002a7c2  call    qword ptr [rax+8]
0x14002a7c5  nop
0x14002a7c6  mov     rdx, [rbp+lpszLongPath]
0x14002a7ca  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002a7ce  or      ecx, 0FFFFFFFFh
0x14002a7d1  lock xadd [rdx+10h], ecx
0x14002a7d6  sub     ecx, 1
0x14002a7d9  jg      short loc_14002A7E8
0x14002a7db  lfence
0x14002a7de  mov     rcx, [rdx]
0x14002a7e1  mov     r8, [rcx]
0x14002a7e4  call    qword ptr [r8+8]
0x14002a7e8  mov     eax, ebx
0x14002a7ea  jmp     loc_14002A67B
0x14002a7ef  mov     ecx, 80004005h; int
0x14002a7f4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a7fa  jmp     short $+2
0x14002a7fc  nop
0x14002a7fd  mov     ecx, 80070057h; int
0x14002a802  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
