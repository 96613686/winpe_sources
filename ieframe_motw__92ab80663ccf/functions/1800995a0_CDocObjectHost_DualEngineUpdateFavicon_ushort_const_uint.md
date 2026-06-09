# CDocObjectHost::_DualEngineUpdateFavicon(ushort const * *,uint)

- ea: `0x1800995a0`
- end: `0x180099a00`
- name: `?_DualEngineUpdateFavicon@CDocObjectHost@@IEAAXPEAPEBGI@Z`
- size: `1120`
- prototype: `void __fastcall(CDocObjectHost *__hidden this, const unsigned __int16 **, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008504c`
- `0x1801485c4`
- `0x180151610`

## callees

- `0x180005030`
- `0x180075ea0`
- `0x1800995a0`
- `0x180099c70`
- `0x1800a2f18`
- `0x18057a6ac`
- `0x180591f4a`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180099872`
- `KERNEL32!GetCurrentThreadId` at `0x180099872`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800997fc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18009997f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800997fc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18009997f`
- `SHELL32!__imp_ILFree` at `0x1800998d9`
- `SHELL32!__imp_ILFree` at `0x1800998d9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180099701`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180099701`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18009975e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180099816`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180099846`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180099999`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800999d0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18009975e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180099816`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180099846`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180099999`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800999d0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18009972a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18009979e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18009992e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18009972a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18009979e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18009992e`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180099652`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x180099652`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180099891`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180099891`

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
                (void *)0x38BC,
                (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                (const char *)(unsigned int)v8,
                dwFlags);
            v9 = IStream_WriteStr(v7, String1);
            if ( v9 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0x38BF,
                (unsigned int)"inetcore\\ieframe\\shdocvw\\dochost.cpp",
                (const char *)(unsigned int)v9,
                dwFlags);
            if ( *a2 )
            {
              v10 = IStream_Write(v7, &v23, 4u);
              if ( v10 < 0 )
                wil::details::in1diag3::FailFast_Hr(
                  retaddr,
                  (void *)0x38C5,
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
                      (void *)0x38D2,
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
                      (void *)0x38CE,
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
                  (void *)0x38DB,
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
                    (void *)0x38E6,
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
                    (void *)0x38E2,
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
0x1800995a0  mov     [rsp-8+arg_18], rbx
0x1800995a5  push    rbp
0x1800995a6  push    rsi
0x1800995a7  push    rdi
0x1800995a8  push    r14
0x1800995aa  push    r15
0x1800995ac  lea     rbp, [rsp-2020h]
0x1800995b4  mov     eax, 2120h
0x1800995b9  call    _alloca_probe
0x1800995be  sub     rsp, rax
0x1800995c1  mov     rax, cs:__security_cookie
0x1800995c8  xor     rax, rsp
0x1800995cb  mov     [rbp+2040h+var_30], rax
0x1800995d2  xor     r15d, r15d
0x1800995d5  mov     [rsp+2140h+var_2108], r8d
0x1800995da  mov     rbx, rcx
0x1800995dd  mov     [rsp+2140h+pidl], r15
0x1800995e2  mov     rcx, [rcx+190h]
0x1800995e9  mov     r14, rdx
0x1800995ec  test    rcx, rcx
0x1800995ef  jz      loc_1800998E5
0x1800995f5  mov     rax, [rcx]
0x1800995f8  lea     rdx, [rsp+2140h+pidl]
0x1800995fd  mov     rax, [rax+0B0h]
0x180099604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099609  test    eax, eax
0x18009960b  js      loc_1800998E5
0x180099611  mov     rcx, [rbx+190h]
0x180099618  lea     r8, [rsp+2140h+String1]
0x18009961d  mov     rdx, [rsp+2140h+pidl]
0x180099622  mov     r9d, 8000h
0x180099628  mov     rax, [rcx]
0x18009962b  mov     rax, [rax+50h]
0x18009962f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099634  test    eax, eax
0x180099636  js      loc_1800998D4
0x18009963c  test    dword ptr [rbx+288h], 40000h
0x180099646  jnz     loc_1800998D4
0x18009964c  lea     edi, [r15+4]
0x180099650  mov     ecx, edi
0x180099652  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x180099659  nop     dword ptr [rax+rax+00h]
0x18009965e  test    eax, eax
0x180099660  jnz     short loc_18009967B
0x180099662  lea     rdx, aAboutBlank; "about:blank"
0x180099669  lea     rcx, [rsp+2140h+String1]; String1
0x18009966e  call    wcscmp_0
0x180099673  test    eax, eax
0x180099675  jz      loc_1800998D4
0x18009967b  mov     [rsp+2140h+var_20E8], r15
0x180099680  cmp     [rsp+2140h+String1], r15w
0x180099686  jz      loc_1800998CA
0x18009968c  mov     rcx, [rbx+190h]
0x180099693  lea     rdx, [rsp+2140h+var_20E8]
0x180099698  mov     rax, [rcx]
0x18009969b  mov     rax, [rax+38h]
0x18009969f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996a4  test    eax, eax
0x1800996a6  js      loc_1800998CA
0x1800996ac  mov     rcx, [rsp+2140h+var_20E8]
0x1800996b1  lea     r8, [rsp+2140h+var_20F0]
0x1800996b6  mov     [rsp+2140h+var_20F0], r15
0x1800996bb  lea     rdx, _GUID_63416179_2ee8_4973_a86a_5897992097a9
0x1800996c2  mov     rax, [rcx]
0x1800996c5  mov     rax, [rax]
0x1800996c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996cd  test    eax, eax
0x1800996cf  js      loc_1800998C0
0x1800996d5  mov     rcx, [rsp+2140h+var_20F0]
0x1800996da  lea     rdx, [rsp+2140h+pv]
0x1800996df  mov     [rsp+2140h+pv], r15d
0x1800996e4  mov     rax, [rcx]
0x1800996e7  mov     rax, [rax+28h]
0x1800996eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996f0  test    eax, eax
0x1800996f2  js      loc_1800998C0
0x1800996f8  xor     edx, edx; cbInit
0x1800996fa  mov     [rsp+2140h+pstm], r15
0x1800996ff  xor     ecx, ecx; pInit
0x180099701  call    cs:__imp_SHCreateMemStream
0x180099708  nop     dword ptr [rax+rax+00h]
0x18009970d  mov     rdx, rax
0x180099710  lea     rcx, [rsp+2140h+pstm]
0x180099715  call    ?Attach@?$CComPtrBase@UIProtectionUtil@@@ATL@@QEAAXPEAUIProtectionUtil@@@Z; ATL::CComPtrBase<IProtectionUtil>::Attach(IProtectionUtil *)
0x18009971a  mov     rbx, [rsp+2140h+pstm]
0x18009971f  lea     rdx, [rsp+2140h+pv]; pv
0x180099724  mov     rcx, rbx; pstm
0x180099727  mov     r8d, edi; cb
0x18009972a  call    cs:__imp_IStream_Write
0x180099731  nop     dword ptr [rax+rax+00h]
0x180099736  test    eax, eax
0x180099738  jns     short loc_180099756
0x18009973a  mov     rcx, [rbp+2048h]; this
0x180099741  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x180099748  mov     r9d, eax; char *
0x18009974b  mov     edx, 38BCh; void *
0x180099750  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180099756  lea     rdx, [rsp+2140h+String1]; psz
0x18009975b  mov     rcx, rbx; pstm
0x18009975e  call    cs:__imp_IStream_WriteStr
0x180099765  nop     dword ptr [rax+rax+00h]
0x18009976a  test    eax, eax
0x18009976c  jns     short loc_18009978A
0x18009976e  mov     rcx, [rbp+2048h]; this
0x180099775  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x18009977c  mov     r9d, eax; char *
0x18009977f  mov     edx, 38BFh; void *
0x180099784  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18009978a  mov     r8d, edi; cb
0x18009978d  mov     rcx, rbx; pstm
0x180099790  cmp     [r14], r15
0x180099793  jz      loc_180099921
0x180099799  lea     rdx, [rsp+2140h+var_2108]; pv
0x18009979e  call    cs:__imp_IStream_Write
0x1800997a5  nop     dword ptr [rax+rax+00h]
0x1800997aa  test    eax, eax
0x1800997ac  jns     short loc_1800997CA
0x1800997ae  mov     rcx, [rbp+2048h]; this
0x1800997b5  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x1800997bc  mov     r9d, eax; char *
0x1800997bf  mov     edx, 38C5h; void *
0x1800997c4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800997ca  mov     edi, r15d
0x1800997cd  cmp     [rsp+2140h+var_2108], r15d
0x1800997d2  jbe     loc_18009986D
0x1800997d8  mov     esi, edi
0x1800997da  lea     r9, [rsp+2140h+pcchCombined]; pcchCombined
0x1800997df  lea     r8, [rbp+2040h+pszCombined]; pszCombined
0x1800997e6  mov     [rsp+2140h+pcchCombined], 824h
0x1800997ee  lea     rcx, [rsp+2140h+String1]; pszBase
0x1800997f3  mov     [rsp+2140h+dwFlags], r15d; int
0x1800997f8  mov     rdx, [r14+rsi*8]; pszRelative
0x1800997fc  call    cs:__imp_UrlCombineW
0x180099803  nop     dword ptr [rax+rax+00h]
0x180099808  mov     rcx, rbx; pstm
0x18009980b  test    eax, eax
0x18009980d  js      short loc_180099842
0x18009980f  lea     rdx, [rbp+2040h+pszCombined]; psz
0x180099816  call    cs:__imp_IStream_WriteStr
0x18009981d  nop     dword ptr [rax+rax+00h]
0x180099822  mov     rcx, [rbp+2048h]; this
0x180099829  test    eax, eax
0x18009982b  jns     short loc_180099861
0x18009982d  mov     r9d, eax; char *
0x180099830  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x180099837  mov     edx, 38CEh; void *
0x18009983c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180099842  mov     rdx, [r14+rsi*8]; psz
0x180099846  call    cs:__imp_IStream_WriteStr
0x18009984d  nop     dword ptr [rax+rax+00h]
0x180099852  mov     rcx, [rbp+2048h]; this
0x180099859  test    eax, eax
0x18009985b  js      loc_18009990C
0x180099861  inc     edi
0x180099863  cmp     edi, [rsp+2140h+var_2108]
0x180099867  jb      loc_1800997D8
0x18009986d  mov     [rsp+2140h+pcchCombined], r15d
0x180099872  call    cs:__imp_GetCurrentThreadId
0x180099879  nop     dword ptr [rax+rax+00h]
0x18009987e  xor     r8d, r8d; struct _IsoComponent **
0x180099881  lea     rdx, [rsp+2140h+pcchCombined]; unsigned int *
0x180099886  mov     ecx, eax; unsigned int
0x180099888  call    ?GetFrameTabComponentFromBrowserTabThread@@YAJKPEAKPEAPEAU_IsoComponent@@@Z; GetFrameTabComponentFromBrowserTabThread(ulong,ulong *,_IsoComponent * *)
0x18009988d  test    eax, eax
0x18009988f  js      short loc_1800998B6
0x180099891  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x180099898  nop     dword ptr [rax+rax+00h]
0x18009989d  mov     ecx, [rsp+2140h+pcchCombined]; unsigned int
0x1800998a1  xor     r9d, r9d; unsigned int
0x1800998a4  mov     edx, eax; unsigned int
0x1800998a6  mov     qword ptr [rsp+2140h+dwFlags], rbx; pstm
0x1800998ab  mov     r8d, 1411h; unsigned int
0x1800998b1  call    ?LCIEPostMessageWithStream@@YAJKKKKPEAUIStream@@@Z; LCIEPostMessageWithStream(ulong,ulong,ulong,ulong,IStream *)
0x1800998b6  lea     rcx, [rsp+2140h+pstm]; void *
0x1800998bb  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800998c0  lea     rcx, [rsp+2140h+var_20F0]; void *
0x1800998c5  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800998ca  lea     rcx, [rsp+2140h+var_20E8]; void *
0x1800998cf  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800998d4  mov     rcx, [rsp+2140h+pidl]; pidl
0x1800998d9  call    cs:__imp_ILFree
0x1800998e0  nop     dword ptr [rax+rax+00h]
0x1800998e5  mov     rcx, [rbp+2040h+var_30]
0x1800998ec  xor     rcx, rsp; StackCookie
0x1800998ef  call    __security_check_cookie
0x1800998f4  mov     rbx, [rsp+2140h+arg_18]
0x1800998fc  add     rsp, 2120h
0x180099903  pop     r15
0x180099905  pop     r14
0x180099907  pop     rdi
0x180099908  pop     rsi
0x180099909  pop     rbp
0x18009990a  retn
0x18009990c  mov     r9d, eax; char *
0x18009990f  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x180099916  mov     edx, 38D2h; void *
0x18009991b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180099921  lea     rdx, [rsp+2140h+pcchCombined]; pv
0x180099926  mov     [rsp+2140h+pcchCombined], 1
0x18009992e  call    cs:__imp_IStream_Write
0x180099935  nop     dword ptr [rax+rax+00h]
0x18009993a  test    eax, eax
0x18009993c  jns     short loc_18009995A
0x18009993e  mov     rcx, [rbp+2048h]; this
0x180099945  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x18009994c  mov     r9d, eax; char *
0x18009994f  mov     edx, 38DBh; void *
0x180099954  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18009995a  lea     r9, [rsp+2140h+var_20FC]; pcchCombined
0x18009995f  mov     [rsp+2140h+var_20FC], 824h
0x180099967  lea     r8, [rbp+2040h+pszCombined]; pszCombined
0x18009996e  mov     [rsp+2140h+dwFlags], r15d; int
0x180099973  lea     rdx, pszRelative; "/favicon.ico"
0x18009997a  lea     rcx, [rsp+2140h+String1]; pszBase
0x18009997f  call    cs:__imp_UrlCombineW
0x180099986  nop     dword ptr [rax+rax+00h]
0x18009998b  mov     rcx, rbx; pstm
0x18009998e  test    eax, eax
0x180099990  js      short loc_1800999C9
0x180099992  lea     rdx, [rbp+2040h+pszCombined]; psz
0x180099999  call    cs:__imp_IStream_WriteStr
0x1800999a0  nop     dword ptr [rax+rax+00h]
0x1800999a5  test    eax, eax
0x1800999a7  jns     loc_18009986D
0x1800999ad  mov     rcx, [rbp+2048h]; this
0x1800999b4  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x1800999bb  mov     r9d, eax; char *
0x1800999be  mov     edx, 38E2h; void *
0x1800999c3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800999c9  lea     rdx, pszRelative; "/favicon.ico"
0x1800999d0  call    cs:__imp_IStream_WriteStr
0x1800999d7  nop     dword ptr [rax+rax+00h]
0x1800999dc  test    eax, eax
0x1800999de  jns     loc_18009986D
0x1800999e4  mov     rcx, [rbp+2048h]; this
0x1800999eb  lea     r8, aInetcoreIefram_45; "inetcore\\ieframe\\shdocvw\\dochost.cpp"
0x1800999f2  mov     r9d, eax; char *
0x1800999f5  mov     edx, 38E6h; void *
0x1800999fa  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
