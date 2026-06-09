# AggregatedTokenRequest::GetAppliesTo(void)

- ea: `0x14000a610`
- end: `0x14000a906`
- name: `?GetAppliesTo@AggregatedTokenRequest@@AEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `758`
- prototype: `void **__fastcall(struct ILogContext *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14000b4f4`

## callees

- `0x140005458`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000a610`
- `0x14000c7d8`
- `0x14000f058`
- `0x14000f0f4`
- `0x14000f170`
- `0x14000f254`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a768`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a780`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a798`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a7ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a768`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a780`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a798`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a816`

## string_xrefs

- `0x14000a75a`: `login.microsoftonline.com`
- `0x14000a84f`: `AggregatedTokenRequest::GetAppliesTo`
- `0x14000a8b5`: `AggregatedTokenRequest::GetAppliesTo`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void **__fastcall AggregatedTokenRequest::GetAppliesTo(struct ILogContext *a1, void **a2)
{
  int v4; // ebx
  _QWORD *v5; // rdx
  char v6; // bl
  _QWORD *v7; // rdx
  __int64 v8; // rbx
  _QWORD *v9; // rdx
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v12; // rbx
  unsigned int v14; // [rsp+20h] [rbp-30h]
  void *v15; // [rsp+38h] [rbp-18h] BYREF
  LPURL_COMPONENTS lpUrlComponents; // [rsp+40h] [rbp-10h]
  __int64 v17; // [rsp+90h] [rbp+40h] BYREF
  __int64 v18; // [rsp+98h] [rbp+48h] BYREF

  *a2 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          a2,
          (__int64)L"urn:federation:MicrosoftOnline") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, L"urn:federation:MicrosoftOnline", 30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v17,
    (__int64 *)(*((_QWORD *)a1 + 1) + 8LL));
  v4 = *(_DWORD *)(v17 - 16);
  v5 = (_QWORD *)(v17 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v17 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  if ( v4 )
  {
    Url::Url((Url *)&v15);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v17,
      (__int64 *)(*((_QWORD *)a1 + 1) + 8LL));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v15,
      &v17);
    v6 = Url::Parse(lpUrlComponents);
    v7 = (_QWORD *)(v17 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v17 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    if ( v6 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v18,
        lpUrlComponents->lpszHostName,
        lpUrlComponents->dwHostNameLength);
      v8 = v18;
      if ( (unsigned int)_o__wcsicmp(v18, L"login.microsoftonline.com") )
      {
        if ( (unsigned int)_o__wcsicmp(v8, L"login.windows.net") )
        {
          if ( (unsigned int)_o__wcsicmp(v8, L"login.windows-ppe.net") )
          {
            if ( (unsigned int)_o__wcsicmp(v8, L"login.windows-int.net") )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v17,
                lpUrlComponents->lpszScheme,
                (&lpUrlComponents->lpszHostName[2 * lpUrlComponents->dwHostNameLength] - lpUrlComponents->lpszScheme) >> 1);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                a2,
                &v17);
              v9 = (_QWORD *)(v17 - 24);
              if ( _InterlockedDecrement((volatile signed __int32 *)(v17 - 24 + 16)) <= 0 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v17,
        (__int64 *)(*((_QWORD *)a1 + 1) + 8LL));
      v14 = v11;
      v8 = v17;
      Log::Verbose(
        a1,
        L"%s: authority \"%s\" is not a valid URL resource ID. Url.Parse failed with error code 0x%08x.",
        L"AggregatedTokenRequest::GetAppliesTo",
        v17,
        v14);
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)(v8 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 - 24) + 8LL))(*(_QWORD *)(v8 - 24));
    Url::~Url(&v15);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v17,
    (__int64 *)(*((_QWORD *)a1 + 1) + 8LL));
  v12 = v17;
  Log::Verbose(
    a1,
    L"%s: using resource ID \"%s\" for authority \"%s\".",
    L"AggregatedTokenRequest::GetAppliesTo",
    *a2,
    v17);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v12 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v12 - 24) + 8LL))(*(_QWORD *)(v12 - 24));
  return a2;
}

```

## disassembly

```asm
0x14000a610  mov     [rsp-28h+arg_0], rbx
0x14000a615  mov     [rsp-28h+arg_8], rdx
0x14000a61a  push    rbp
0x14000a61b  push    rsi
0x14000a61c  push    rdi
0x14000a61d  push    r14
0x14000a61f  push    r15
0x14000a621  mov     rbp, rsp
0x14000a624  sub     rsp, 50h
0x14000a628  mov     rsi, rdx
0x14000a62b  mov     r14, rcx
0x14000a62e  mov     [rbp+var_20], 0
0x14000a635  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000a63c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000a643  mov     rax, [rax+18h]
0x14000a647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a64c  add     rax, 18h
0x14000a650  mov     [rsi], rax
0x14000a653  lea     rdx, aUrnFederationM; "urn:federation:MicrosoftOnline"
0x14000a65a  mov     rcx, rsi
0x14000a65d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000a662  test    al, al
0x14000a664  jnz     short loc_14000A67C
0x14000a666  mov     r8d, 1Eh
0x14000a66c  lea     rdx, aUrnFederationM; "urn:federation:MicrosoftOnline"
0x14000a673  mov     rcx, rsi
0x14000a676  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000a67b  nop
0x14000a67c  mov     [rbp+var_20], 1
0x14000a683  mov     rdx, [r14+8]
0x14000a687  add     rdx, 8
0x14000a68b  lea     rcx, [rbp+arg_10]
0x14000a68f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a694  mov     edi, 3
0x14000a699  mov     [rbp+var_20], edi
0x14000a69c  mov     rax, [rbp+arg_10]
0x14000a6a0  mov     ebx, [rax-10h]
0x14000a6a3  lea     rdx, [rax-18h]
0x14000a6a7  or      r15d, 0FFFFFFFFh
0x14000a6ab  mov     eax, r15d
0x14000a6ae  lock xadd [rdx+10h], eax
0x14000a6b3  add     eax, r15d
0x14000a6b6  test    eax, eax
0x14000a6b8  jg      short loc_14000A6C9
0x14000a6ba  mov     rcx, [rdx]
0x14000a6bd  mov     rax, [rcx]
0x14000a6c0  mov     rax, [rax+8]
0x14000a6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6c9  test    ebx, ebx
0x14000a6cb  jz      loc_14000A892
0x14000a6d1  lea     rcx, [rbp+var_18]; this
0x14000a6d5  call    ??0Url@@QEAA@XZ; Url::Url(void)
0x14000a6da  nop
0x14000a6db  mov     rdx, [r14+8]
0x14000a6df  add     rdx, 8
0x14000a6e3  lea     rcx, [rbp+arg_10]
0x14000a6e7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a6ec  mov     [rbp+var_20], 7
0x14000a6f3  lea     rdx, [rbp+arg_10]
0x14000a6f7  lea     rcx, [rbp+var_18]
0x14000a6fb  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a700  lea     rdx, [rbp+var_18]
0x14000a704  mov     rcx, [rbp+lpUrlComponents]; lpUrlComponents
0x14000a708  call    ?Parse@Url@@CA_NAEAUURLParts@1@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::Parse(Url::URLParts &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a70d  mov     bl, al
0x14000a70f  mov     rdx, [rbp+arg_10]
0x14000a713  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a717  mov     ecx, r15d
0x14000a71a  lock xadd [rdx+10h], ecx
0x14000a71f  add     ecx, r15d
0x14000a722  test    ecx, ecx
0x14000a724  jg      short loc_14000A735
0x14000a726  mov     rcx, [rdx]
0x14000a729  mov     r8, [rcx]
0x14000a72c  mov     rax, [r8+8]
0x14000a730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a735  test    bl, bl
0x14000a737  jz      loc_14000A816
0x14000a73d  mov     rdx, [rbp+lpUrlComponents]
0x14000a741  mov     r8d, [rdx+20h]
0x14000a745  mov     rdx, [rdx+18h]
0x14000a749  lea     rcx, [rbp+arg_18]
0x14000a74d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x14000a752  mov     edi, 0Fh
0x14000a757  mov     [rbp+var_20], edi
0x14000a75a  lea     rdx, aLoginMicrosoft_0; "login.microsoftonline.com"
0x14000a761  mov     rbx, [rbp+arg_18]
0x14000a765  mov     rcx, rbx
0x14000a768  call    cs:__imp__o__wcsicmp
0x14000a76e  test    eax, eax
0x14000a770  jz      loc_14000A814
0x14000a776  lea     rdx, aLoginWindowsNe; "login.windows.net"
0x14000a77d  mov     rcx, rbx
0x14000a780  call    cs:__imp__o__wcsicmp
0x14000a786  test    eax, eax
0x14000a788  jz      loc_14000A814
0x14000a78e  lea     rdx, aLoginWindowsPp; "login.windows-ppe.net"
0x14000a795  mov     rcx, rbx
0x14000a798  call    cs:__imp__o__wcsicmp
0x14000a79e  test    eax, eax
0x14000a7a0  jz      short loc_14000A814
0x14000a7a2  lea     rdx, aLoginWindowsIn; "login.windows-int.net"
0x14000a7a9  mov     rcx, rbx
0x14000a7ac  call    cs:__imp__o__wcsicmp
0x14000a7b2  test    eax, eax
0x14000a7b4  jz      short loc_14000A814
0x14000a7b6  mov     rax, [rbp+lpUrlComponents]
0x14000a7ba  mov     rdx, [rax+8]
0x14000a7be  mov     ecx, [rax+20h]
0x14000a7c1  mov     rax, [rax+18h]
0x14000a7c5  lea     r8, [rax+rcx*2]
0x14000a7c9  sub     r8, rdx
0x14000a7cc  sar     r8, 1
0x14000a7cf  lea     rcx, [rbp+arg_10]
0x14000a7d3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x14000a7d8  mov     edi, 1Fh
0x14000a7dd  mov     [rbp+var_20], edi
0x14000a7e0  lea     rdx, [rbp+arg_10]
0x14000a7e4  mov     rcx, rsi
0x14000a7e7  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a7ec  nop
0x14000a7ed  mov     rdx, [rbp+arg_10]
0x14000a7f1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a7f5  mov     eax, r15d
0x14000a7f8  lock xadd [rdx+10h], eax
0x14000a7fd  add     eax, r15d
0x14000a800  test    eax, eax
0x14000a802  jg      short loc_14000A814
0x14000a804  mov     rcx, [rdx]
0x14000a807  mov     rax, [rcx]
0x14000a80a  mov     rax, [rax+8]
0x14000a80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a813  nop
0x14000a814  jmp     short loc_14000A866
0x14000a816  call    cs:__imp_GetLastError
0x14000a81c  mov     ebx, eax
0x14000a81e  test    eax, eax
0x14000a820  jle     short loc_14000A82B
0x14000a822  movzx   ebx, ax
0x14000a825  or      ebx, 80070000h
0x14000a82b  mov     rdx, [r14+8]
0x14000a82f  add     rdx, 8
0x14000a833  lea     rcx, [rbp+arg_10]
0x14000a837  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a83c  mov     edi, 27h ; '''
0x14000a841  mov     [rbp+var_20], edi
0x14000a844  mov     [rsp+50h+var_30], ebx
0x14000a848  mov     rbx, [rbp+arg_10]
0x14000a84c  mov     r9, rbx
0x14000a84f  lea     r8, aAggregatedtoke_1; "AggregatedTokenRequest::GetAppliesTo"
0x14000a856  lea     rdx, aSAuthoritySIsN; "%s: authority \"%s\" is not a valid URL"...
0x14000a85d  mov     rcx, r14; struct ILogContext *
0x14000a860  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a865  nop
0x14000a866  lea     rdx, [rbx-18h]
0x14000a86a  mov     eax, r15d
0x14000a86d  lock xadd [rdx+10h], eax
0x14000a872  add     eax, r15d
0x14000a875  test    eax, eax
0x14000a877  jg      short loc_14000A889
0x14000a879  mov     rcx, [rdx]
0x14000a87c  mov     rax, [rcx]
0x14000a87f  mov     rax, [rax+8]
0x14000a883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a888  nop
0x14000a889  lea     rcx, [rbp+var_18]; this
0x14000a88d  call    ??1Url@@QEAA@XZ; Url::~Url(void)
0x14000a892  mov     rdx, [r14+8]
0x14000a896  add     rdx, 8
0x14000a89a  lea     rcx, [rbp+arg_10]
0x14000a89e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a8a3  or      edi, 40h
0x14000a8a6  mov     [rbp+var_20], edi
0x14000a8a9  mov     rbx, [rbp+arg_10]
0x14000a8ad  mov     qword ptr [rsp+50h+var_30], rbx
0x14000a8b2  mov     r9, [rsi]
0x14000a8b5  lea     r8, aAggregatedtoke_1; "AggregatedTokenRequest::GetAppliesTo"
0x14000a8bc  lea     rdx, aSUsingResource; "%s: using resource ID \"%s\" for author"...
0x14000a8c3  mov     rcx, r14; struct ILogContext *
0x14000a8c6  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a8cb  nop
0x14000a8cc  lea     rdx, [rbx-18h]
0x14000a8d0  mov     eax, r15d
0x14000a8d3  lock xadd [rdx+10h], eax
0x14000a8d8  add     eax, r15d
0x14000a8db  test    eax, eax
0x14000a8dd  jg      short loc_14000A8EE
0x14000a8df  mov     rcx, [rdx]
0x14000a8e2  mov     rax, [rcx]
0x14000a8e5  mov     rax, [rax+8]
0x14000a8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8ee  mov     rax, rsi
0x14000a8f1  mov     rbx, [rsp+50h+arg_0]
0x14000a8f9  add     rsp, 50h
0x14000a8fd  pop     r15
0x14000a8ff  pop     r14
0x14000a901  pop     rdi
0x14000a902  pop     rsi
0x14000a903  pop     rbp
0x14000a904  retn
```
