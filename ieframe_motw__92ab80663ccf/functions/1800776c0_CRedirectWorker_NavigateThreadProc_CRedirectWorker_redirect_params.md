# CRedirectWorker::NavigateThreadProc(CRedirectWorker::_redirect_params *)

- ea: `0x1800776c0`
- end: `0x180077dc9`
- name: `?NavigateThreadProc@CRedirectWorker@@CAKPEAU_redirect_params@1@@Z`
- size: `1801`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007010`
- `0x18007587c`
- `0x1800776c0`
- `0x18008f1bc`
- `0x18008f5dc`
- `0x18012bfc8`
- `0x18012c380`
- `0x18013bf38`
- `0x180516548`
- `0x180591eea`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180077910`
- `KERNEL32!CloseHandle` at `0x180077910`
- `KERNEL32!WaitForSingleObject` at `0x180077901`
- `KERNEL32!WaitForSingleObject` at `0x180077901`
- `ole32!CoInitialize` at `0x18007772a`
- `ole32!CoInitialize` at `0x18007772a`
- `OLEAUT32!__imp_SysAllocString` at `0x180077972`
- `OLEAUT32!__imp_SysAllocString` at `0x180077972`
- `OLEAUT32!__imp_SysFreeString` at `0x180077ac9`
- `OLEAUT32!__imp_SysFreeString` at `0x180077ac9`
- `SHELL32!__imp_ILFree` at `0x180077c0c`
- `SHELL32!__imp_ILFree` at `0x180077c0c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1800777b7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1800777b7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180077d37`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180077d37`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180077d1d`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180077d1d`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180077922`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180077922`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x1800778e7`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x1800778e7`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180077d03`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180077d03`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x18007778e`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x18007778e`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x180077d2b`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x180077d2b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077747`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077756`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18007776a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18007777a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077d43`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077d53`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077747`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077756`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18007776a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18007777a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077d43`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180077d53`

## pseudocode

```c
__int64 __fastcall CRedirectWorker::NavigateThreadProc(unsigned int *Parameter, __int64 a2, __int64 a3)
{
  unsigned int *v3; // rdi
  unsigned int v4; // edx
  HRESULT inited; // ebx
  __int64 v6; // r8
  __int128 v7; // xmm6
  __int128 v8; // xmm7
  char v9; // r14
  IStream *v10; // rcx
  HRESULT InterfaceAndReleaseStream; // eax
  __int64 (__fastcall ***v12)(LPVOID, GUID *, LPITEMIDLIST *); // rbx
  __int64 (__fastcall **v13)(LPVOID, GUID *, LPITEMIDLIST *); // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rsi
  void *ScopeArtifactEvent; // rax
  void *v17; // rbx
  BSTR v18; // rdx
  __int64 *v19; // r8
  int v20; // ebx
  BSTR v21; // r13
  int v22; // edi
  BSTR v23; // r11
  int v24; // esi
  BSTR v25; // r10
  int v26; // r14d
  BSTR v27; // rcx
  int v28; // r15d
  BSTR v29; // r9
  __int64 v30; // r12
  BSTR v31; // r8
  __int64 v32; // xmm0_8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  __int128 *v39; // rax
  __int64 v40; // r8
  unsigned int AuthorityManager; // eax
  int v43; // [rsp+80h] [rbp-98h]
  char v44; // [rsp+98h] [rbp-80h]
  LPITEMIDLIST pidl; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-70h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp-68h] BYREF
  __int64 *v48; // [rsp+B8h] [rbp-60h]
  BSTR bstrString; // [rsp+C0h] [rbp-58h]
  unsigned int *v50; // [rsp+C8h] [rbp-50h]
  __int128 v51; // [rsp+D8h] [rbp-40h] BYREF
  __int64 v52; // [rsp+E8h] [rbp-30h]
  void (__fastcall *v53)(LPITEMIDLIST, __int64, BSTR, BSTR, BSTR, BSTR, BSTR, BSTR, __int128 *, __int64, int, int, int, int, int, int, __int128 *); // [rsp+F8h] [rbp-20h]
  __int128 v54; // [rsp+100h] [rbp-18h] BYREF
  __int64 v55; // [rsp+110h] [rbp-8h]
  __int128 v56; // [rsp+118h] [rbp+0h] BYREF
  __int64 v57; // [rsp+128h] [rbp+10h]
  __int128 v58; // [rsp+130h] [rbp+18h] BYREF
  __int64 v59; // [rsp+140h] [rbp+28h]
  __int128 v60; // [rsp+148h] [rbp+30h] BYREF
  __int64 v61; // [rsp+158h] [rbp+40h]
  __int128 v62; // [rsp+168h] [rbp+50h] BYREF

  v3 = Parameter;
  v50 = Parameter;
  if ( (Microsoft_IEFRAMEEnableBits & 0x400) != 0 )
    McGenEventWrite_EventWriteTransfer(BERP_IEFRAME2_Context, Shdocvw_VirtualTab_NavigateThreadProc_Start, a3, 1, &v62);
  inited = CoInitialize(0);
  if ( inited >= 0 )
  {
    v7 = *((_OWORD *)v3 + 3);
    v8 = *(_OWORD *)GlobalThreadState();
    v9 = *((_BYTE *)GlobalThreadState() + 16);
    v44 = v9;
    *(_OWORD *)GlobalThreadState() = v7;
    *((_BYTE *)GlobalThreadState() + 16) = 1;
    inited = IsoReferenceDefaultScope(0, 0);
    if ( inited < 0 )
    {
LABEL_65:
      CoUninitialize();
      *(_OWORD *)GlobalThreadState() = v8;
      *((_BYTE *)GlobalThreadState() + 16) = v9;
      goto LABEL_66;
    }
    v10 = (IStream *)*((_QWORD *)v3 + 1);
    ppv = 0;
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v10, &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e, &ppv);
    *((_QWORD *)v3 + 1) = 0;
    inited = InterfaceAndReleaseStream;
    if ( InterfaceAndReleaseStream < 0 )
      goto LABEL_62;
    v12 = (__int64 (__fastcall ***)(LPVOID, GUID *, LPITEMIDLIST *))ppv;
    v46 = 0;
    if ( ppv && memcmp_0(&IID_IWebBrowser2, &GUID_1ac7516e_e6bb_4a69_b63f_e841904dc5a6, 0x10u) )
    {
      v13 = *v12;
      pidl = 0;
      inited = (*v13)(v12, &GUID_00000000_0000_0000_c000_000000000046, &pidl);
      if ( inited >= 0 )
      {
        v14 = operator new(0x80u);
        v15 = v14;
        if ( v14 )
        {
          v14[4] = pidl;
          *v14 = &CLCIE_IIDProxy_Master::`vftable'{for `ILCIE_IIDProxy_Master'};
          *((_DWORD *)v14 + 6) = 1;
          v14[5] = 0;
          v14[1] = &CLCIE_IIDProxy_Master::`vftable'{for `ILCIEProxyControl'};
          v14[2] = &CLCIE_IIDProxy_Master::`vftable'{for `ILCIEProxyControlLocal'};
          memset_0(v14 + 6, 0, 0x50u);
          inited = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v15)(v15, &IID_IWebBrowser2, &v46);
          (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        }
        else
        {
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
          inited = -2147024882;
        }
      }
    }
    else
    {
      inited = -2147418113;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( inited < 0 )
      goto LABEL_62;
    if ( (v3[9] & 0x4000) != 0 )
    {
      ScopeArtifactEvent = IsoCreateScopeArtifactEvent(v3[10], 2u, 0);
      v17 = ScopeArtifactEvent;
      if ( ScopeArtifactEvent )
      {
        WaitForSingleObject(ScopeArtifactEvent, 0xFFFFFFFF);
        CloseHandle(v17);
      }
      if ( LCIEIsComponentSharedFlagValueSet(v3[11], 1u) != 1 )
      {
        inited = -2147467259;
        goto LABEL_61;
      }
      inited = 0;
    }
    pidl = 0;
    if ( *(_BYTE *)v3 )
    {
      inited = (**(__int64 (__fastcall ***)(__int64, GUID *, LPITEMIDLIST *))v46)(
                 v46,
                 &GUID_5abdc2ad_7329_4c95_8d32_bb84799fcf88,
                 &pidl);
      if ( !inited )
      {
        bstrString = SysAllocString(&Default);
        v18 = bstrString;
        if ( bstrString )
        {
          v19 = (__int64 *)*((_QWORD *)v3 + 2);
          v48 = v19;
          if ( (Microsoft_IEFRAMEEnableBits & 0x400) != 0 )
          {
            McGenEventWrite_EventWriteTransfer(
              BERP_IEFRAME2_Context,
              Shdocvw_VirtualTab_NavigateThreadProc_NavigateEx2Call_Start,
              v19,
              1,
              &v62);
            v18 = bstrString;
            v19 = v48;
          }
          v20 = *((_DWORD *)v19 + 34);
          v21 = v18;
          v22 = *((_DWORD *)v19 + 33);
          v23 = v18;
          v24 = *((_DWORD *)v19 + 32);
          v25 = v18;
          v26 = *((_DWORD *)v19 + 31);
          v27 = v18;
          v28 = *((_DWORD *)v19 + 30);
          v29 = v18;
          v30 = v19[14];
          v53 = *(void (__fastcall **)(LPITEMIDLIST, __int64, BSTR, BSTR, BSTR, BSTR, BSTR, BSTR, __int128 *, __int64, int, int, int, int, int, int, __int128 *))(*(_QWORD *)&pidl->mkid.cb + 24LL);
          if ( v19[6] )
            v21 = (BSTR)v19[6];
          if ( v19[5] )
            v23 = (BSTR)v19[5];
          if ( v19[4] )
            v25 = (BSTR)v19[4];
          if ( v19[3] )
            v27 = (BSTR)v19[3];
          if ( v19[2] )
            v29 = (BSTR)v19[2];
          v31 = v18;
          if ( v48[1] )
            v31 = (BSTR)v48[1];
          v62 = *((_OWORD *)v50 + 3);
          v43 = *((_DWORD *)v48 + 35);
          v32 = v48[13];
          v33 = *v48;
          v51 = *(_OWORD *)(v48 + 11);
          v52 = v32;
          v53(pidl, v33, v31, v29, v27, v25, v23, v21, &v51, v30, v28, v26, v24, v22, v20, v43, &v62);
          SysFreeString(bstrString);
          if ( (Microsoft_IEFRAMEEnableBits & 0x400) != 0 )
            McGenEventWrite_EventWriteTransfer(
              BERP_IEFRAME2_Context,
              Shdocvw_VirtualTab_NavigateThreadProc_NavigateEx2Call_Stop,
              v34,
              1,
              &v62);
          v3 = v50;
          v9 = v44;
          inited = 0;
        }
        else
        {
          inited = -2147024882;
        }
      }
      if ( pidl )
        (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
LABEL_61:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      if ( inited >= 0 )
      {
LABEL_64:
        IsoReleaseDefaultScope(0);
        goto LABEL_65;
      }
LABEL_62:
      if ( (v3[9] & 0x4000) != 0 )
      {
        AuthorityManager = IsoGetAuthorityManager();
        LCIEPostMessageWithoutBuffer(v3[10], AuthorityManager, 0xC42u, 0);
      }
      goto LABEL_64;
    }
    v3[9] &= 0xFFFEE7FF;
    v35 = v3[9];
    v61 = 0;
    v57 = 0;
    v60 = 0;
    v55 = 0;
    v56 = 0;
    v52 = 0;
    v54 = 0;
    v59 = 0;
    v51 = 0;
    v58 = 0;
    ATL::CComVariant::operator=(&v60, v35);
    v36 = *((_QWORD *)v3 + 2);
    if ( !v36 )
      goto LABEL_50;
    if ( *(_QWORD *)(v36 + 56) )
    {
      ATL::CComVariant::operator=(&v56);
      inited = *((_QWORD *)&v56 + 1) == 0 ? 0x8007000E : 0;
    }
    if ( *(_QWORD *)(*((_QWORD *)v3 + 2) + 32LL) )
    {
      if ( inited < 0 )
      {
LABEL_60:
        ATL::CComVariant::Clear((ATL::CComVariant *)&v58);
        ATL::CComVariant::Clear((ATL::CComVariant *)&v51);
        ATL::CComVariant::Clear((ATL::CComVariant *)&v54);
        ATL::CComVariant::Clear((ATL::CComVariant *)&v56);
        ATL::CComVariant::Clear((ATL::CComVariant *)&v60);
        goto LABEL_61;
      }
      ATL::CComVariant::operator=(&v54);
      if ( !*((_QWORD *)&v54 + 1) )
      {
        inited = -2147024882;
        goto LABEL_60;
      }
    }
    else
    {
LABEL_50:
      if ( inited < 0 )
        goto LABEL_60;
    }
    inited = _IECreatePidlFromBrokerBindInfo(
               *((const unsigned __int16 **)v3 + 3),
               *((struct _BROKER_BIND_INFO **)v3 + 2),
               (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
    if ( inited >= 0 )
    {
      inited = InitVariantFromIDList(pidl, &v58);
      ILFree(pidl);
      pidl = 0;
      if ( inited >= 0 )
      {
        if ( (Microsoft_IEFRAMEEnableBits & 0x400) != 0 )
          McGenEventWrite_EventWriteTransfer(
            BERP_IEFRAME2_Context,
            Shdocvw_VirtualTab_NavigateThreadProc_Navigate2Call_Start,
            v37,
            1,
            &v62);
        v38 = *((_QWORD *)v3 + 2);
        if ( v38 )
          v39 = (__int128 *)(v38 + 88);
        else
          v39 = &v51;
        inited = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v46 + 416LL))(
                   v46,
                   &v58,
                   &v60,
                   &v56,
                   v39,
                   &v54);
        if ( (Microsoft_IEFRAMEEnableBits & 0x400) != 0 )
          McGenEventWrite_EventWriteTransfer(
            BERP_IEFRAME2_Context,
            Shdocvw_VirtualTab_NavigateThreadProc_Navigate2Call_Stop,
            v40,
            1,
            &v62);
      }
    }
    goto LABEL_60;
  }
LABEL_66:
  if ( v3 )
    CRedirectWorker::_redirect_params::`scalar deleting destructor'((CRedirectWorker::_redirect_params *)v3, v4);
  if ( (Microsoft_IEFRAMEEnableBits & 0x400) != 0 )
    McGenEventWrite_EventWriteTransfer(BERP_IEFRAME2_Context, Shdocvw_VirtualTab_NavigateThreadProc_Stop, v6, 1, &v62);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800776c0  mov     rax, rsp
0x1800776c3  push    rbp
0x1800776c4  push    rbx
0x1800776c5  push    rsi
0x1800776c6  push    rdi
0x1800776c7  push    r12
0x1800776c9  push    r13
0x1800776cb  push    r14
0x1800776cd  push    r15
0x1800776cf  lea     rbp, [rax-0D8h]
0x1800776d6  sub     rsp, 1A8h
0x1800776dd  movaps  xmmword ptr [rax-58h], xmm6
0x1800776e1  movaps  xmmword ptr [rax-68h], xmm7
0x1800776e5  mov     rax, cs:__security_cookie
0x1800776ec  xor     rax, rsp
0x1800776ef  mov     [rbp+0D0h+var_70], rax
0x1800776f3  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 4
0x1800776fa  mov     rdi, rcx
0x1800776fd  mov     [rbp+0D0h+var_120], rcx
0x180077701  mov     r12d, 1
0x180077707  jz      short loc_180077728
0x180077709  lea     rax, [rbp+0D0h+var_80]
0x18007770d  mov     r9d, r12d
0x180077710  lea     rdx, Shdocvw_VirtualTab_NavigateThreadProc_Start
0x180077717  mov     [rsp+1E0h+var_1C0], rax
0x18007771c  lea     rcx, BERP_IEFRAME2_Context
0x180077723  call    McGenEventWrite_EventWriteTransfer
0x180077728  xor     ecx, ecx; pvReserved
0x18007772a  call    cs:__imp_CoInitialize
0x180077731  nop     dword ptr [rax+rax+00h]
0x180077736  xor     r15d, r15d
0x180077739  mov     ebx, eax
0x18007773b  test    eax, eax
0x18007773d  js      loc_180077D63
0x180077743  movups  xmm6, xmmword ptr [rdi+30h]
0x180077747  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18007774e  nop     dword ptr [rax+rax+00h]
0x180077753  movups  xmm7, xmmword ptr [rax]
0x180077756  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18007775d  nop     dword ptr [rax+rax+00h]
0x180077762  mov     r14b, [rax+10h]
0x180077766  mov     [rbp+0D0h+var_150], r14b
0x18007776a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180077771  nop     dword ptr [rax+rax+00h]
0x180077776  movdqu  xmmword ptr [rax], xmm6
0x18007777a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180077781  nop     dword ptr [rax+rax+00h]
0x180077786  xor     edx, edx
0x180077788  xor     ecx, ecx
0x18007778a  mov     [rax+10h], r12b
0x18007778e  call    cs:__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z; IsoReferenceDefaultScope(ulong,IsoScope * *)
0x180077795  nop     dword ptr [rax+rax+00h]
0x18007779a  mov     ebx, eax
0x18007779c  test    eax, eax
0x18007779e  js      loc_180077D37
0x1800777a4  mov     rcx, [rdi+8]; pStm
0x1800777a8  lea     r8, [rbp+0D0h+ppv]; ppv
0x1800777ac  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e; iid
0x1800777b3  mov     [rbp+0D0h+ppv], r15
0x1800777b7  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1800777be  nop     dword ptr [rax+rax+00h]
0x1800777c3  mov     [rdi+8], r15
0x1800777c7  mov     ebx, eax
0x1800777c9  test    eax, eax
0x1800777cb  js      loc_180077CFA
0x1800777d1  mov     rbx, [rbp+0D0h+ppv]
0x1800777d5  mov     r13d, 8007000Eh
0x1800777db  mov     [rbp+0D0h+var_140], r15
0x1800777df  test    rbx, rbx
0x1800777e2  jz      short loc_1800777FF
0x1800777e4  lea     r8d, [r15+10h]; Size
0x1800777e8  lea     rdx, _GUID_1ac7516e_e6bb_4a69_b63f_e841904dc5a6; Buf2
0x1800777ef  lea     rcx, IID_IWebBrowser2; Buf1
0x1800777f6  call    memcmp_0
0x1800777fb  test    eax, eax
0x1800777fd  jnz     short loc_180077809
0x1800777ff  mov     ebx, 8000FFFFh
0x180077804  jmp     loc_1800778BC
0x180077809  mov     rax, [rbx]
0x18007780c  lea     r8, [rbp+0D0h+pidl]
0x180077810  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180077817  mov     [rbp+0D0h+pidl], r15
0x18007781b  mov     rcx, rbx
0x18007781e  mov     rax, [rax]
0x180077821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077826  mov     ebx, eax
0x180077828  test    eax, eax
0x18007782a  js      loc_1800778BC
0x180077830  mov     ecx, 80h; dwBytes
0x180077835  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007783a  mov     rcx, [rbp+0D0h+pidl]
0x18007783e  mov     rsi, rax
0x180077841  test    rax, rax
0x180077844  jz      short loc_1800778AD
0x180077846  lea     rax, ??_7CLCIE_IIDProxy_Master@@6BILCIE_IIDProxy_Master@@@; const CLCIE_IIDProxy_Master::`vftable'{for `ILCIE_IIDProxy_Master'}
0x18007784d  mov     [rsi+20h], rcx
0x180077851  mov     [rsi], rax
0x180077854  lea     rcx, [rsi+30h]; void *
0x180077858  xor     edx, edx; Val
0x18007785a  mov     [rsi+18h], r12d
0x18007785e  lea     rax, ??_7CLCIE_IIDProxy_Master@@6BILCIEProxyControl@@@; const CLCIE_IIDProxy_Master::`vftable'{for `ILCIEProxyControl'}
0x180077865  mov     [rsi+28h], r15
0x180077869  mov     [rsi+8], rax
0x18007786d  lea     rax, ??_7CLCIE_IIDProxy_Master@@6BILCIEProxyControlLocal@@@; const CLCIE_IIDProxy_Master::`vftable'{for `ILCIEProxyControlLocal'}
0x180077874  mov     [rsi+10h], rax
0x180077878  lea     r8d, [rdx+50h]; Size
0x18007787c  call    memset_0
0x180077881  mov     rax, [rsi]
0x180077884  lea     r8, [rbp+0D0h+var_140]
0x180077888  lea     rdx, IID_IWebBrowser2
0x18007788f  mov     rcx, rsi
0x180077892  mov     rax, [rax]
0x180077895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007789a  mov     ebx, eax
0x18007789c  mov     rcx, rsi
0x18007789f  mov     rax, [rsi]
0x1800778a2  mov     rax, [rax+10h]
0x1800778a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778ab  jmp     short loc_1800778BC
0x1800778ad  mov     rax, [rcx]
0x1800778b0  mov     rax, [rax+10h]
0x1800778b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778b9  mov     ebx, r13d
0x1800778bc  mov     rcx, [rbp+0D0h+ppv]
0x1800778c0  mov     rax, [rcx]
0x1800778c3  mov     rax, [rax+10h]
0x1800778c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778cc  test    ebx, ebx
0x1800778ce  js      loc_180077CFA
0x1800778d4  test    dword ptr [rdi+24h], 4000h
0x1800778db  jz      short loc_18007793A
0x1800778dd  mov     ecx, [rdi+28h]
0x1800778e0  xor     r8d, r8d
0x1800778e3  lea     edx, [r8+2]
0x1800778e7  call    cs:__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z; IsoCreateScopeArtifactEvent(ulong,ulong,IsoScope *)
0x1800778ee  nop     dword ptr [rax+rax+00h]
0x1800778f3  mov     rbx, rax
0x1800778f6  test    rax, rax
0x1800778f9  jz      short loc_18007791C
0x1800778fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800778fe  mov     rcx, rax; hHandle
0x180077901  call    cs:__imp_WaitForSingleObject
0x180077908  nop     dword ptr [rax+rax+00h]
0x18007790d  mov     rcx, rbx; hObject
0x180077910  call    cs:__imp_CloseHandle
0x180077917  nop     dword ptr [rax+rax+00h]
0x18007791c  mov     ecx, [rdi+2Ch]
0x18007791f  mov     edx, r12d
0x180077922  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z; LCIEIsComponentSharedFlagValueSet(ulong,ulong)
0x180077929  nop     dword ptr [rax+rax+00h]
0x18007792e  cmp     eax, r12d
0x180077931  jnz     loc_180077B13
0x180077937  mov     ebx, r15d
0x18007793a  mov     [rbp+0D0h+pidl], r15
0x18007793e  cmp     [rdi], r15b
0x180077941  jz      loc_180077B3E
0x180077947  mov     rcx, [rbp+0D0h+var_140]
0x18007794b  lea     r8, [rbp+0D0h+pidl]
0x18007794f  lea     rdx, _GUID_5abdc2ad_7329_4c95_8d32_bb84799fcf88
0x180077956  mov     rax, [rcx]
0x180077959  mov     rax, [rax]
0x18007795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077961  mov     ebx, eax
0x180077963  test    eax, eax
0x180077965  jnz     loc_180077B20
0x18007796b  lea     rcx, Default; psz
0x180077972  call    cs:__imp_SysAllocString
0x180077979  nop     dword ptr [rax+rax+00h]
0x18007797e  mov     [rbp+0D0h+bstrString], rax
0x180077982  mov     rdx, rax
0x180077985  test    rax, rax
0x180077988  jz      loc_180077B1D
0x18007798e  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 4
0x180077995  mov     r8, [rdi+10h]
0x180077999  mov     [rbp+0D0h+var_130], r8
0x18007799d  jz      short loc_1800779C6
0x18007799f  lea     rax, [rbp+0D0h+var_80]
0x1800779a3  mov     r9d, r12d
0x1800779a6  lea     rdx, Shdocvw_VirtualTab_NavigateThreadProc_NavigateEx2Call_Start
0x1800779ad  mov     [rsp+1E0h+var_1C0], rax
0x1800779b2  lea     rcx, BERP_IEFRAME2_Context
0x1800779b9  call    McGenEventWrite_EventWriteTransfer
0x1800779be  mov     rdx, [rbp+0D0h+bstrString]
0x1800779c2  mov     r8, [rbp+0D0h+var_130]
0x1800779c6  mov     ebx, [r8+88h]
0x1800779cd  mov     r13, rdx
0x1800779d0  mov     edi, [r8+84h]
0x1800779d7  mov     r11, rdx
0x1800779da  mov     esi, [r8+80h]
0x1800779e1  mov     r10, rdx
0x1800779e4  mov     r14d, [r8+7Ch]
0x1800779e8  mov     rcx, rdx
0x1800779eb  mov     r15d, [r8+78h]
0x1800779ef  mov     r9, rdx
0x1800779f2  mov     r12, [r8+70h]
0x1800779f6  mov     rax, [rbp+0D0h+pidl]
0x1800779fa  mov     rax, [rax]
0x1800779fd  mov     rax, [rax+18h]
0x180077a01  mov     [rbp+0D0h+var_F0], rax
0x180077a05  xor     eax, eax
0x180077a07  cmp     [r8+30h], rax
0x180077a0b  cmovnz  r13, [r8+30h]
0x180077a10  cmp     [r8+28h], rax
0x180077a14  cmovnz  r11, [r8+28h]
0x180077a19  cmp     [r8+20h], rax
0x180077a1d  cmovnz  r10, [r8+20h]
0x180077a22  cmp     [r8+18h], rax
0x180077a26  cmovnz  rcx, [r8+18h]
0x180077a2b  cmp     [r8+10h], rax
0x180077a2f  cmovnz  r9, [r8+10h]
0x180077a34  mov     r8, rdx
0x180077a37  mov     rdx, [rbp+0D0h+var_130]
0x180077a3b  cmp     [rdx+8], rax
0x180077a3f  lea     rax, [rbp+0D0h+var_80]
0x180077a43  mov     [rsp+1E0h+var_160], rax
0x180077a4b  cmovnz  r8, [rdx+8]
0x180077a50  mov     rdx, [rbp+0D0h+var_120]
0x180077a54  movups  xmm0, xmmword ptr [rdx+30h]
0x180077a58  mov     rdx, [rbp+0D0h+var_130]
0x180077a5c  movdqu  [rbp+0D0h+var_80], xmm0
0x180077a61  mov     eax, [rdx+8Ch]
0x180077a67  movups  xmm1, xmmword ptr [rdx+58h]
0x180077a6b  mov     dword ptr [rsp+1E0h+var_168], eax
0x180077a6f  lea     rax, [rbp+0D0h+var_110]
0x180077a73  movsd   xmm0, qword ptr [rdx+68h]
0x180077a78  mov     rdx, [rdx]
0x180077a7b  mov     [rsp+1E0h+var_170], ebx
0x180077a7f  mov     [rsp+1E0h+var_178], edi
0x180077a83  mov     [rsp+1E0h+var_180], esi
0x180077a87  mov     [rsp+1E0h+var_188], r14d
0x180077a8c  mov     [rsp+1E0h+var_190], r15d
0x180077a91  mov     qword ptr [rsp+1E0h+var_198], r12
0x180077a96  mov     [rsp+1E0h+var_1A0], rax
0x180077a9b  mov     rax, [rbp+0D0h+var_F0]
0x180077a9f  mov     [rsp+1E0h+var_1A8], r13
0x180077aa4  mov     [rsp+1E0h+var_1B0], r11
0x180077aa9  mov     [rsp+1E0h+var_1B8], r10
0x180077aae  mov     [rsp+1E0h+var_1C0], rcx
0x180077ab3  mov     rcx, [rbp+0D0h+pidl]
0x180077ab7  movaps  [rbp+0D0h+var_110], xmm1
0x180077abb  movsd   [rbp+0D0h+var_100], xmm0
0x180077ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ac5  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x180077ac9  call    cs:__imp_SysFreeString
0x180077ad0  nop     dword ptr [rax+rax+00h]
0x180077ad5  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 4
0x180077adc  mov     r12d, 1
0x180077ae2  jz      short loc_180077B03
0x180077ae4  lea     rax, [rbp+0D0h+var_80]
0x180077ae8  mov     r9d, r12d
0x180077aeb  lea     rdx, Shdocvw_VirtualTab_NavigateThreadProc_NavigateEx2Call_Stop
0x180077af2  mov     [rsp+1E0h+var_1C0], rax
0x180077af7  lea     rcx, BERP_IEFRAME2_Context
0x180077afe  call    McGenEventWrite_EventWriteTransfer
0x180077b03  mov     rdi, [rbp+0D0h+var_120]
0x180077b07  xor     r15d, r15d
0x180077b0a  mov     r14b, [rbp+0D0h+var_150]
0x180077b0e  mov     ebx, r15d
0x180077b11  jmp     short loc_180077B20
0x180077b13  mov     ebx, 80004005h
0x180077b18  jmp     loc_180077CE6
0x180077b1d  mov     ebx, r13d
0x180077b20  mov     rcx, [rbp+0D0h+pidl]
0x180077b24  test    rcx, rcx
0x180077b27  jz      loc_180077CE6
0x180077b2d  mov     rax, [rcx]
0x180077b30  mov     rax, [rax+10h]
0x180077b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b39  jmp     loc_180077CE6
0x180077b3e  and     dword ptr [rdi+24h], 0FFFEE7FFh
0x180077b45  lea     rcx, [rbp+0D0h+var_A0]
0x180077b49  mov     edx, [rdi+24h]
0x180077b4c  xor     eax, eax
0x180077b4e  xorps   xmm0, xmm0
0x180077b51  mov     [rbp+0D0h+var_90], rax
0x180077b55  xorps   xmm1, xmm1
0x180077b58  mov     [rbp+0D0h+var_C0], rax
0x180077b5c  movups  [rbp+0D0h+var_A0], xmm0
0x180077b60  mov     [rbp+0D0h+var_D8], rax
0x180077b64  movups  [rbp+0D0h+var_D0], xmm1
0x180077b68  mov     [rbp+0D0h+var_100], rax
0x180077b6c  movups  [rbp+0D0h+var_E8], xmm0
0x180077b70  mov     [rbp+0D0h+var_A8], rax
0x180077b74  movups  [rbp+0D0h+var_110], xmm1
0x180077b78  movups  [rbp+0D0h+var_B8], xmm0
0x180077b7c  call    ??4CComVariant@ATL@@QEAAAEAV01@J@Z; ATL::CComVariant::operator=(long)
0x180077b81  mov     rdx, [rdi+10h]
0x180077b85  test    rdx, rdx
0x180077b88  jz      short loc_180077BD6
0x180077b8a  mov     rdx, [rdx+38h]
0x180077b8e  test    rdx, rdx
0x180077b91  jz      short loc_180077BAA
0x180077b93  lea     rcx, [rbp+0D0h+var_D0]
0x180077b97  call    ??4CComVariant@ATL@@QEAAAEAV01@PEAG@Z; ATL::CComVariant::operator=(ushort *)
0x180077b9c  mov     rax, qword ptr [rbp+0D0h+var_D0+8]
0x180077ba0  neg     rax
0x180077ba3  sbb     ebx, ebx
0x180077ba5  not     ebx
0x180077ba7  and     ebx, r13d
0x180077baa  mov     rax, [rdi+10h]
  ... truncated ...
```
