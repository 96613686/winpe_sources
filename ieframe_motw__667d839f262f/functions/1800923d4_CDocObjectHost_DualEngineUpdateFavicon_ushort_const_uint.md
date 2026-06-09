# CDocObjectHost::_DualEngineUpdateFavicon(ushort const * *,uint)

- ea: `0x1800923d4`
- end: `0x1800927d1`
- name: `?_DualEngineUpdateFavicon@CDocObjectHost@@IEAAXPEAPEBGI@Z`
- size: `1021`
- prototype: `void __fastcall(CDocObjectHost *__hidden this, const unsigned __int16 **, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007eba8`
- `0x18013995c`
- `0x180142328`

## callees

- `0x18000b9e0`
- `0x1800708d8`
- `0x1800923d4`
- `0x180092a2c`
- `0x18009bd88`
- `0x180538024`
- `0x18054e2da`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18009266e`
- `KERNEL32!GetCurrentThreadId` at `0x18009266e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18009260e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180092762`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18009260e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180092762`
- `SHELL32!__imp_ILFree` at `0x1800926c9`
- `SHELL32!__imp_ILFree` at `0x1800926c9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18009252f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18009252f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180092580`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180092622`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18009264c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180092776`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800927a7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180092580`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180092622`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18009264c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180092776`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800927a7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180092552`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800925ba`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180092717`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180092552`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800925ba`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180092717`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180092486`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180092486`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180092687`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180092687`

## pseudocode

```c
void __fastcall CDocObjectHost::_DualEngineUpdateFavicon(
        CDocObjectHost *this,
        const unsigned __int16 **a2,
        unsigned int a3)
{
  __int64 v4; // rcx
  IStream *v6; // rax
  IStream *v7; // rbx
  HRESULT v8; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  unsigned int i; // edi
  HRESULT v12; // eax
  HRESULT v13; // eax
  DWORD CurrentThreadId; // eax
  unsigned int CurrentProcessManager; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  int dwFlagsa; // [rsp+20h] [rbp-E0h]
  int dwFlagsb; // [rsp+20h] [rbp-E0h]
  DWORD pcchCombined; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-C8h] BYREF
  int pv; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v25; // [rsp+44h] [rbp-BCh] BYREF
  IStream *pstm; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[2088]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszCombined[2088]; // [rsp+10C0h] [rbp+FC0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2148h] [rbp+2048h]

  v23 = a3;
  pidl[0] = 0;
  v4 = *((_QWORD *)this + 50);
  if ( v4 && (*(int (__fastcall **)(__int64, LPITEMIDLIST *))(*(_QWORD *)v4 + 176LL))(v4, pidl) >= 0 )
  {
    if ( (*(int (__fastcall **)(_QWORD, LPITEMIDLIST, wchar_t *, __int64))(**((_QWORD **)this + 50) + 80LL))(
           *((_QWORD *)this + 50),
           pidl[0],
           String1,
           0x8000) >= 0
      && (*((_DWORD *)this + 162) & 0x40000) == 0
      && (LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) || wcscmp_0(String1, L"about:blank")) )
    {
      v28 = 0;
      if ( String1[0]
        && (*(int (__fastcall **)(_QWORD, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**((_QWORD **)this + 50)
                                                                                           + 56LL))(
             *((_QWORD *)this + 50),
             &v28) >= 0 )
      {
        v27 = 0;
        if ( (**v28)(v28, &GUID_63416179_2ee8_4973_a86a_5897992097a9, &v27) >= 0 )
        {
          pv = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 40LL))(v27, &pv) >= 0 )
          {
            pstm = 0;
            v6 = SHCreateMemStream(0, 0);
            ATL::CComPtrBase<IProtectionUtil>::Attach(&pstm, v6);
            v7 = pstm;
            v8 = IStream_Write(pstm, &pv, 4u);
            if ( v8 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0x38BA,
                (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                (const char *)(unsigned int)v8,
                dwFlags);
            v9 = IStream_WriteStr(v7, String1);
            if ( v9 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0x38BD,
                (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                (const char *)(unsigned int)v9,
                dwFlags);
            if ( *a2 )
            {
              v10 = IStream_Write(v7, &v23, 4u);
              if ( v10 < 0 )
                wil::details::in1diag3::FailFast_Hr(
                  retaddr,
                  (void *)0x38C3,
                  (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                  (const char *)(unsigned int)v10,
                  dwFlags);
              for ( i = 0; i < v23; ++i )
              {
                pcchCombined = 2084;
                if ( UrlCombineW(String1, a2[i], pszCombined, &pcchCombined, 0) < 0 )
                {
                  v13 = IStream_WriteStr(v7, a2[i]);
                  if ( v13 < 0 )
                    wil::details::in1diag3::FailFast_Hr(
                      retaddr,
                      (void *)0x38D0,
                      (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                      (const char *)(unsigned int)v13,
                      dwFlagsa);
                }
                else
                {
                  v12 = IStream_WriteStr(v7, pszCombined);
                  if ( v12 < 0 )
                    wil::details::in1diag3::FailFast_Hr(
                      retaddr,
                      (void *)0x38CC,
                      (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                      (const char *)(unsigned int)v12,
                      dwFlagsa);
                }
              }
            }
            else
            {
              pcchCombined = 1;
              v16 = IStream_Write(v7, &pcchCombined, 4u);
              if ( v16 < 0 )
                wil::details::in1diag3::FailFast_Hr(
                  retaddr,
                  (void *)0x38D9,
                  (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                  (const char *)(unsigned int)v16,
                  dwFlags);
              v25 = 2084;
              if ( UrlCombineW(String1, L"/favicon.ico", pszCombined, &v25, 0) < 0 )
              {
                v18 = IStream_WriteStr(v7, L"/favicon.ico");
                if ( v18 < 0 )
                  wil::details::in1diag3::FailFast_Hr(
                    retaddr,
                    (void *)0x38E4,
                    (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                    (const char *)(unsigned int)v18,
                    dwFlagsb);
              }
              else
              {
                v17 = IStream_WriteStr(v7, pszCombined);
                if ( v17 < 0 )
                  wil::details::in1diag3::FailFast_Hr(
                    retaddr,
                    (void *)0x38E0,
                    (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                    (const char *)(unsigned int)v17,
                    dwFlagsb);
              }
            }
            pcchCombined = 0;
            CurrentThreadId = GetCurrentThreadId();
            if ( (int)GetFrameTabComponentFromBrowserTabThread(CurrentThreadId, &pcchCombined, 0) >= 0 )
            {
              CurrentProcessManager = IsoGetCurrentProcessManager();
              LCIEPostMessageWithStream(pcchCombined, CurrentProcessManager, 0x1411u, 0, v7);
            }
            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pstm);
          }
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v27);
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v28);
    }
    ILFree(pidl[0]);
  }
}

```

## disassembly

```asm
0x1800923d4  mov     [rsp-8+arg_18], rbx
0x1800923d9  push    rbp
0x1800923da  push    rsi
0x1800923db  push    rdi
0x1800923dc  push    r14
0x1800923de  push    r15
0x1800923e0  lea     rbp, [rsp-2020h]
0x1800923e8  mov     eax, 2120h
0x1800923ed  call    _alloca_probe
0x1800923f2  sub     rsp, rax
0x1800923f5  mov     rax, cs:__security_cookie
0x1800923fc  xor     rax, rsp
0x1800923ff  mov     [rbp+2040h+var_30], rax
0x180092406  xor     r15d, r15d
0x180092409  mov     [rsp+2140h+var_2108], r8d
0x18009240e  mov     rbx, rcx
0x180092411  mov     [rsp+2140h+pidl], r15
0x180092416  mov     rcx, [rcx+190h]
0x18009241d  mov     r14, rdx
0x180092420  test    rcx, rcx
0x180092423  jz      loc_1800926CF
0x180092429  mov     rax, [rcx]
0x18009242c  lea     rdx, [rsp+2140h+pidl]
0x180092431  mov     rax, [rax+0B0h]
0x180092438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009243d  test    eax, eax
0x18009243f  js      loc_1800926CF
0x180092445  mov     rcx, [rbx+190h]
0x18009244c  lea     r8, [rsp+2140h+String1]
0x180092451  mov     rdx, [rsp+2140h+pidl]
0x180092456  mov     r9d, 8000h
0x18009245c  mov     rax, [rcx]
0x18009245f  mov     rax, [rax+50h]
0x180092463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092468  test    eax, eax
0x18009246a  js      loc_1800926C4
0x180092470  test    dword ptr [rbx+288h], 40000h
0x18009247a  jnz     loc_1800926C4
0x180092480  lea     edi, [r15+4]
0x180092484  mov     ecx, edi
0x180092486  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x18009248c  test    eax, eax
0x18009248e  jnz     short loc_1800924A9
0x180092490  lea     rdx, aAboutBlank; "about:blank"
0x180092497  lea     rcx, [rsp+2140h+String1]; String1
0x18009249c  call    wcscmp_0
0x1800924a1  test    eax, eax
0x1800924a3  jz      loc_1800926C4
0x1800924a9  mov     [rsp+2140h+var_20E8], r15
0x1800924ae  cmp     [rsp+2140h+String1], r15w
0x1800924b4  jz      loc_1800926BA
0x1800924ba  mov     rcx, [rbx+190h]
0x1800924c1  lea     rdx, [rsp+2140h+var_20E8]
0x1800924c6  mov     rax, [rcx]
0x1800924c9  mov     rax, [rax+38h]
0x1800924cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800924d2  test    eax, eax
0x1800924d4  js      loc_1800926BA
0x1800924da  mov     rcx, [rsp+2140h+var_20E8]
0x1800924df  lea     r8, [rsp+2140h+var_20F0]
0x1800924e4  mov     [rsp+2140h+var_20F0], r15
0x1800924e9  lea     rdx, _GUID_63416179_2ee8_4973_a86a_5897992097a9
0x1800924f0  mov     rax, [rcx]
0x1800924f3  mov     rax, [rax]
0x1800924f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800924fb  test    eax, eax
0x1800924fd  js      loc_1800926B0
0x180092503  mov     rcx, [rsp+2140h+var_20F0]
0x180092508  lea     rdx, [rsp+2140h+pv]
0x18009250d  mov     [rsp+2140h+pv], r15d
0x180092512  mov     rax, [rcx]
0x180092515  mov     rax, [rax+28h]
0x180092519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009251e  test    eax, eax
0x180092520  js      loc_1800926B0
0x180092526  xor     edx, edx; cbInit
0x180092528  mov     [rsp+2140h+pstm], r15
0x18009252d  xor     ecx, ecx; pInit
0x18009252f  call    cs:__imp_SHCreateMemStream
0x180092535  mov     rdx, rax
0x180092538  lea     rcx, [rsp+2140h+pstm]
0x18009253d  call    ?Attach@?$CComPtrBase@UIProtectionUtil@@@ATL@@QEAAXPEAUIProtectionUtil@@@Z; ATL::CComPtrBase<IProtectionUtil>::Attach(IProtectionUtil *)
0x180092542  mov     rbx, [rsp+2140h+pstm]
0x180092547  lea     rdx, [rsp+2140h+pv]; pv
0x18009254c  mov     rcx, rbx; pstm
0x18009254f  mov     r8d, edi; cb
0x180092552  call    cs:__imp_IStream_Write
0x180092558  test    eax, eax
0x18009255a  jns     short loc_180092578
0x18009255c  mov     rcx, [rbp+2048h]; this
0x180092563  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x18009256a  mov     r9d, eax; char *
0x18009256d  mov     edx, 38BAh; void *
0x180092572  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180092578  lea     rdx, [rsp+2140h+String1]; psz
0x18009257d  mov     rcx, rbx; pstm
0x180092580  call    cs:__imp_IStream_WriteStr
0x180092586  test    eax, eax
0x180092588  jns     short loc_1800925A6
0x18009258a  mov     rcx, [rbp+2048h]; this
0x180092591  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x180092598  mov     r9d, eax; char *
0x18009259b  mov     edx, 38BDh; void *
0x1800925a0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800925a6  mov     r8d, edi; cb
0x1800925a9  mov     rcx, rbx; pstm
0x1800925ac  cmp     [r14], r15
0x1800925af  jz      loc_18009270A
0x1800925b5  lea     rdx, [rsp+2140h+var_2108]; pv
0x1800925ba  call    cs:__imp_IStream_Write
0x1800925c0  test    eax, eax
0x1800925c2  jns     short loc_1800925E0
0x1800925c4  mov     rcx, [rbp+2048h]; this
0x1800925cb  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x1800925d2  mov     r9d, eax; char *
0x1800925d5  mov     edx, 38C3h; void *
0x1800925da  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800925e0  mov     edi, r15d
0x1800925e3  cmp     [rsp+2140h+var_2108], r15d
0x1800925e8  jbe     short loc_180092669
0x1800925ea  mov     esi, edi
0x1800925ec  lea     r9, [rsp+2140h+pcchCombined]; pcchCombined
0x1800925f1  lea     r8, [rbp+2040h+pszCombined]; pszCombined
0x1800925f8  mov     [rsp+2140h+pcchCombined], 824h
0x180092600  lea     rcx, [rsp+2140h+String1]; pszBase
0x180092605  mov     [rsp+2140h+dwFlags], r15d; int
0x18009260a  mov     rdx, [r14+rsi*8]; pszRelative
0x18009260e  call    cs:__imp_UrlCombineW
0x180092614  mov     rcx, rbx; pstm
0x180092617  test    eax, eax
0x180092619  js      short loc_180092648
0x18009261b  lea     rdx, [rbp+2040h+pszCombined]; psz
0x180092622  call    cs:__imp_IStream_WriteStr
0x180092628  mov     rcx, [rbp+2048h]; this
0x18009262f  test    eax, eax
0x180092631  jns     short loc_180092661
0x180092633  mov     r9d, eax; char *
0x180092636  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x18009263d  mov     edx, 38CCh; void *
0x180092642  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180092648  mov     rdx, [r14+rsi*8]; psz
0x18009264c  call    cs:__imp_IStream_WriteStr
0x180092652  mov     rcx, [rbp+2048h]; this
0x180092659  test    eax, eax
0x18009265b  js      loc_1800926F5
0x180092661  inc     edi
0x180092663  cmp     edi, [rsp+2140h+var_2108]
0x180092667  jb      short loc_1800925EA
0x180092669  mov     [rsp+2140h+pcchCombined], r15d
0x18009266e  call    cs:__imp_GetCurrentThreadId
0x180092674  xor     r8d, r8d; struct _IsoComponent **
0x180092677  lea     rdx, [rsp+2140h+pcchCombined]; unsigned int *
0x18009267c  mov     ecx, eax; unsigned int
0x18009267e  call    ?GetFrameTabComponentFromBrowserTabThread@@YAJKPEAKPEAPEAU_IsoComponent@@@Z; GetFrameTabComponentFromBrowserTabThread(ulong,ulong *,_IsoComponent * *)
0x180092683  test    eax, eax
0x180092685  js      short loc_1800926A6
0x180092687  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x18009268d  mov     ecx, [rsp+2140h+pcchCombined]; unsigned int
0x180092691  xor     r9d, r9d; unsigned int
0x180092694  mov     edx, eax; unsigned int
0x180092696  mov     qword ptr [rsp+2140h+dwFlags], rbx; pstm
0x18009269b  mov     r8d, 1411h; unsigned int
0x1800926a1  call    ?LCIEPostMessageWithStream@@YAJKKKKPEAUIStream@@@Z; LCIEPostMessageWithStream(ulong,ulong,ulong,ulong,IStream *)
0x1800926a6  lea     rcx, [rsp+2140h+pstm]; void *
0x1800926ab  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800926b0  lea     rcx, [rsp+2140h+var_20F0]; void *
0x1800926b5  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800926ba  lea     rcx, [rsp+2140h+var_20E8]; void *
0x1800926bf  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800926c4  mov     rcx, [rsp+2140h+pidl]; pidl
0x1800926c9  call    cs:__imp_ILFree
0x1800926cf  mov     rcx, [rbp+2040h+var_30]
0x1800926d6  xor     rcx, rsp; StackCookie
0x1800926d9  call    __security_check_cookie
0x1800926de  mov     rbx, [rsp+2140h+arg_18]
0x1800926e6  add     rsp, 2120h
0x1800926ed  pop     r15
0x1800926ef  pop     r14
0x1800926f1  pop     rdi
0x1800926f2  pop     rsi
0x1800926f3  pop     rbp
0x1800926f4  retn
0x1800926f5  mov     r9d, eax; char *
0x1800926f8  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x1800926ff  mov     edx, 38D0h; void *
0x180092704  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18009270a  lea     rdx, [rsp+2140h+pcchCombined]; pv
0x18009270f  mov     [rsp+2140h+pcchCombined], 1
0x180092717  call    cs:__imp_IStream_Write
0x18009271d  test    eax, eax
0x18009271f  jns     short loc_18009273D
0x180092721  mov     rcx, [rbp+2048h]; this
0x180092728  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x18009272f  mov     r9d, eax; char *
0x180092732  mov     edx, 38D9h; void *
0x180092737  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18009273d  lea     r9, [rsp+2140h+var_20FC]; pcchCombined
0x180092742  mov     [rsp+2140h+var_20FC], 824h
0x18009274a  lea     r8, [rbp+2040h+pszCombined]; pszCombined
0x180092751  mov     [rsp+2140h+dwFlags], r15d; int
0x180092756  lea     rdx, pszRelative; "/favicon.ico"
0x18009275d  lea     rcx, [rsp+2140h+String1]; pszBase
0x180092762  call    cs:__imp_UrlCombineW
0x180092768  mov     rcx, rbx; pstm
0x18009276b  test    eax, eax
0x18009276d  js      short loc_1800927A0
0x18009276f  lea     rdx, [rbp+2040h+pszCombined]; psz
0x180092776  call    cs:__imp_IStream_WriteStr
0x18009277c  test    eax, eax
0x18009277e  jns     loc_180092669
0x180092784  mov     rcx, [rbp+2048h]; this
0x18009278b  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x180092792  mov     r9d, eax; char *
0x180092795  mov     edx, 38E0h; void *
0x18009279a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800927a0  lea     rdx, pszRelative; "/favicon.ico"
0x1800927a7  call    cs:__imp_IStream_WriteStr
0x1800927ad  test    eax, eax
0x1800927af  jns     loc_180092669
0x1800927b5  mov     rcx, [rbp+2048h]; this
0x1800927bc  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x1800927c3  mov     r9d, eax; char *
0x1800927c6  mov     edx, 38E4h; void *
0x1800927cb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
