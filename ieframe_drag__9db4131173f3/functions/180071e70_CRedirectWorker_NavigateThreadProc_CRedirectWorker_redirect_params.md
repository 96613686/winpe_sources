# CRedirectWorker::NavigateThreadProc(CRedirectWorker::_redirect_params *)

- ea: `0x180071e70`
- end: `0x180072500`
- name: `?NavigateThreadProc@CRedirectWorker@@CAKPEAU_redirect_params@1@@Z`
- size: `1680`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18002acc0`
- `0x18006ff5c`
- `0x180071e70`
- `0x180087978`
- `0x180089604`
- `0x18011ef28`
- `0x18011f2d0`
- `0x18012e160`
- `0x1804d8e54`
- `0x18054e27a`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007208a`
- `KERNEL32!CloseHandle` at `0x18007208a`
- `KERNEL32!WaitForSingleObject` at `0x180072081`
- `KERNEL32!WaitForSingleObject` at `0x180072081`
- `ole32!CoInitialize` at `0x180071eda`
- `ole32!CoInitialize` at `0x180071eda`
- `OLEAUT32!__imp_SysAllocString` at `0x1800720e0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800720e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180072231`
- `OLEAUT32!__imp_SysFreeString` at `0x180072231`
- `SHELL32!__imp_ILFree` at `0x18007236e`
- `SHELL32!__imp_ILFree` at `0x18007236e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180071f43`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180071f43`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180072481`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180072481`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180072473`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180072473`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180072096`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x180072096`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x18007206d`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x18007206d`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x18007245f`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x18007245f`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x180071f20`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x180071f20`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18007247b`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18007247b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071ef1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071efa`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071f08`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071f12`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180072487`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180072491`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071ef1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071efa`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071f08`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180071f12`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180072487`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180072491`

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
        bstrString = SysAllocString(&SrcStr);
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
0x180071e70  mov     rax, rsp
0x180071e73  push    rbp
0x180071e74  push    rbx
0x180071e75  push    rsi
0x180071e76  push    rdi
0x180071e77  push    r12
0x180071e79  push    r13
0x180071e7b  push    r14
0x180071e7d  push    r15
0x180071e7f  lea     rbp, [rax-0D8h]
0x180071e86  sub     rsp, 1A8h
0x180071e8d  movaps  xmmword ptr [rax-58h], xmm6
0x180071e91  movaps  xmmword ptr [rax-68h], xmm7
0x180071e95  mov     rax, cs:__security_cookie
0x180071e9c  xor     rax, rsp
0x180071e9f  mov     [rbp+0D0h+var_70], rax
0x180071ea3  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 4
0x180071eaa  mov     rdi, rcx
0x180071ead  mov     [rbp+0D0h+var_120], rcx
0x180071eb1  mov     r12d, 1
0x180071eb7  jz      short loc_180071ED8
0x180071eb9  lea     rax, [rbp+0D0h+var_80]
0x180071ebd  mov     r9d, r12d
0x180071ec0  lea     rdx, Shdocvw_VirtualTab_NavigateThreadProc_Start
0x180071ec7  mov     [rsp+1E0h+var_1C0], rax
0x180071ecc  lea     rcx, BERP_IEFRAME2_Context
0x180071ed3  call    McGenEventWrite_EventWriteTransfer
0x180071ed8  xor     ecx, ecx; pvReserved
0x180071eda  call    cs:__imp_CoInitialize
0x180071ee0  xor     r15d, r15d
0x180071ee3  mov     ebx, eax
0x180071ee5  test    eax, eax
0x180071ee7  js      loc_18007249B
0x180071eed  movups  xmm6, xmmword ptr [rdi+30h]
0x180071ef1  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180071ef7  movups  xmm7, xmmword ptr [rax]
0x180071efa  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180071f00  mov     r14b, [rax+10h]
0x180071f04  mov     [rbp+0D0h+var_150], r14b
0x180071f08  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180071f0e  movdqu  xmmword ptr [rax], xmm6
0x180071f12  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180071f18  xor     edx, edx
0x180071f1a  xor     ecx, ecx
0x180071f1c  mov     [rax+10h], r12b
0x180071f20  call    cs:__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z; IsoReferenceDefaultScope(ulong,IsoScope * *)
0x180071f26  mov     ebx, eax
0x180071f28  test    eax, eax
0x180071f2a  js      loc_180072481
0x180071f30  mov     rcx, [rdi+8]; pStm
0x180071f34  lea     r8, [rbp+0D0h+ppv]; ppv
0x180071f38  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e; iid
0x180071f3f  mov     [rbp+0D0h+ppv], r15
0x180071f43  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180071f49  mov     [rdi+8], r15
0x180071f4d  mov     ebx, eax
0x180071f4f  test    eax, eax
0x180071f51  js      loc_180072456
0x180071f57  mov     rbx, [rbp+0D0h+ppv]
0x180071f5b  mov     r13d, 8007000Eh
0x180071f61  mov     [rbp+0D0h+var_140], r15
0x180071f65  test    rbx, rbx
0x180071f68  jz      short loc_180071F85
0x180071f6a  lea     r8d, [r15+10h]; Size
0x180071f6e  lea     rdx, _GUID_1ac7516e_e6bb_4a69_b63f_e841904dc5a6; Buf2
0x180071f75  lea     rcx, IID_IWebBrowser2; Buf1
0x180071f7c  call    memcmp_0
0x180071f81  test    eax, eax
0x180071f83  jnz     short loc_180071F8F
0x180071f85  mov     ebx, 8000FFFFh
0x180071f8a  jmp     loc_180072042
0x180071f8f  mov     rax, [rbx]
0x180071f92  lea     r8, [rbp+0D0h+pidl]
0x180071f96  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180071f9d  mov     [rbp+0D0h+pidl], r15
0x180071fa1  mov     rcx, rbx
0x180071fa4  mov     rax, [rax]
0x180071fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fac  mov     ebx, eax
0x180071fae  test    eax, eax
0x180071fb0  js      loc_180072042
0x180071fb6  mov     ecx, 80h; dwBytes
0x180071fbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180071fc0  mov     rcx, [rbp+0D0h+pidl]
0x180071fc4  mov     rsi, rax
0x180071fc7  test    rax, rax
0x180071fca  jz      short loc_180072033
0x180071fcc  lea     rax, ??_7CLCIE_IIDProxy_Master@@6BILCIE_IIDProxy_Master@@@; const CLCIE_IIDProxy_Master::`vftable'{for `ILCIE_IIDProxy_Master'}
0x180071fd3  mov     [rsi+20h], rcx
0x180071fd7  mov     [rsi], rax
0x180071fda  lea     rcx, [rsi+30h]; void *
0x180071fde  xor     edx, edx; Val
0x180071fe0  mov     [rsi+18h], r12d
0x180071fe4  lea     rax, ??_7CLCIE_IIDProxy_Master@@6BILCIEProxyControl@@@; const CLCIE_IIDProxy_Master::`vftable'{for `ILCIEProxyControl'}
0x180071feb  mov     [rsi+28h], r15
0x180071fef  mov     [rsi+8], rax
0x180071ff3  lea     rax, ??_7CLCIE_IIDProxy_Master@@6BILCIEProxyControlLocal@@@; const CLCIE_IIDProxy_Master::`vftable'{for `ILCIEProxyControlLocal'}
0x180071ffa  mov     [rsi+10h], rax
0x180071ffe  lea     r8d, [rdx+50h]; Size
0x180072002  call    memset_0
0x180072007  mov     rax, [rsi]
0x18007200a  lea     r8, [rbp+0D0h+var_140]
0x18007200e  lea     rdx, IID_IWebBrowser2
0x180072015  mov     rcx, rsi
0x180072018  mov     rax, [rax]
0x18007201b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072020  mov     ebx, eax
0x180072022  mov     rcx, rsi
0x180072025  mov     rax, [rsi]
0x180072028  mov     rax, [rax+10h]
0x18007202c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072031  jmp     short loc_180072042
0x180072033  mov     rax, [rcx]
0x180072036  mov     rax, [rax+10h]
0x18007203a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007203f  mov     ebx, r13d
0x180072042  mov     rcx, [rbp+0D0h+ppv]
0x180072046  mov     rax, [rcx]
0x180072049  mov     rax, [rax+10h]
0x18007204d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072052  test    ebx, ebx
0x180072054  js      loc_180072456
0x18007205a  test    dword ptr [rdi+24h], 4000h
0x180072061  jz      short loc_1800720A8
0x180072063  mov     ecx, [rdi+28h]
0x180072066  xor     r8d, r8d
0x180072069  lea     edx, [r8+2]
0x18007206d  call    cs:__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z; IsoCreateScopeArtifactEvent(ulong,ulong,IsoScope *)
0x180072073  mov     rbx, rax
0x180072076  test    rax, rax
0x180072079  jz      short loc_180072090
0x18007207b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007207e  mov     rcx, rax; hHandle
0x180072081  call    cs:__imp_WaitForSingleObject
0x180072087  mov     rcx, rbx; hObject
0x18007208a  call    cs:__imp_CloseHandle
0x180072090  mov     ecx, [rdi+2Ch]
0x180072093  mov     edx, r12d
0x180072096  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z; LCIEIsComponentSharedFlagValueSet(ulong,ulong)
0x18007209c  cmp     eax, r12d
0x18007209f  jnz     loc_180072275
0x1800720a5  mov     ebx, r15d
0x1800720a8  mov     [rbp+0D0h+pidl], r15
0x1800720ac  cmp     [rdi], r15b
0x1800720af  jz      loc_1800722A0
0x1800720b5  mov     rcx, [rbp+0D0h+var_140]
0x1800720b9  lea     r8, [rbp+0D0h+pidl]
0x1800720bd  lea     rdx, _GUID_5abdc2ad_7329_4c95_8d32_bb84799fcf88
0x1800720c4  mov     rax, [rcx]
0x1800720c7  mov     rax, [rax]
0x1800720ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720cf  mov     ebx, eax
0x1800720d1  test    eax, eax
0x1800720d3  jnz     loc_180072282
0x1800720d9  lea     rcx, SrcStr; psz
0x1800720e0  call    cs:__imp_SysAllocString
0x1800720e6  mov     [rbp+0D0h+bstrString], rax
0x1800720ea  mov     rdx, rax
0x1800720ed  test    rax, rax
0x1800720f0  jz      loc_18007227F
0x1800720f6  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 4
0x1800720fd  mov     r8, [rdi+10h]
0x180072101  mov     [rbp+0D0h+var_130], r8
0x180072105  jz      short loc_18007212E
0x180072107  lea     rax, [rbp+0D0h+var_80]
0x18007210b  mov     r9d, r12d
0x18007210e  lea     rdx, Shdocvw_VirtualTab_NavigateThreadProc_NavigateEx2Call_Start
0x180072115  mov     [rsp+1E0h+var_1C0], rax
0x18007211a  lea     rcx, BERP_IEFRAME2_Context
0x180072121  call    McGenEventWrite_EventWriteTransfer
0x180072126  mov     rdx, [rbp+0D0h+bstrString]
0x18007212a  mov     r8, [rbp+0D0h+var_130]
0x18007212e  mov     ebx, [r8+88h]
0x180072135  mov     r13, rdx
0x180072138  mov     edi, [r8+84h]
0x18007213f  mov     r11, rdx
0x180072142  mov     esi, [r8+80h]
0x180072149  mov     r10, rdx
0x18007214c  mov     r14d, [r8+7Ch]
0x180072150  mov     rcx, rdx
0x180072153  mov     r15d, [r8+78h]
0x180072157  mov     r9, rdx
0x18007215a  mov     r12, [r8+70h]
0x18007215e  mov     rax, [rbp+0D0h+pidl]
0x180072162  mov     rax, [rax]
0x180072165  mov     rax, [rax+18h]
0x180072169  mov     [rbp+0D0h+var_F0], rax
0x18007216d  xor     eax, eax
0x18007216f  cmp     [r8+30h], rax
0x180072173  cmovnz  r13, [r8+30h]
0x180072178  cmp     [r8+28h], rax
0x18007217c  cmovnz  r11, [r8+28h]
0x180072181  cmp     [r8+20h], rax
0x180072185  cmovnz  r10, [r8+20h]
0x18007218a  cmp     [r8+18h], rax
0x18007218e  cmovnz  rcx, [r8+18h]
0x180072193  cmp     [r8+10h], rax
0x180072197  cmovnz  r9, [r8+10h]
0x18007219c  mov     r8, rdx
0x18007219f  mov     rdx, [rbp+0D0h+var_130]
0x1800721a3  cmp     [rdx+8], rax
0x1800721a7  lea     rax, [rbp+0D0h+var_80]
0x1800721ab  mov     [rsp+1E0h+var_160], rax
0x1800721b3  cmovnz  r8, [rdx+8]
0x1800721b8  mov     rdx, [rbp+0D0h+var_120]
0x1800721bc  movups  xmm0, xmmword ptr [rdx+30h]
0x1800721c0  mov     rdx, [rbp+0D0h+var_130]
0x1800721c4  movdqu  [rbp+0D0h+var_80], xmm0
0x1800721c9  mov     eax, [rdx+8Ch]
0x1800721cf  movups  xmm1, xmmword ptr [rdx+58h]
0x1800721d3  mov     dword ptr [rsp+1E0h+var_168], eax
0x1800721d7  lea     rax, [rbp+0D0h+var_110]
0x1800721db  movsd   xmm0, qword ptr [rdx+68h]
0x1800721e0  mov     rdx, [rdx]
0x1800721e3  mov     [rsp+1E0h+var_170], ebx
0x1800721e7  mov     [rsp+1E0h+var_178], edi
0x1800721eb  mov     [rsp+1E0h+var_180], esi
0x1800721ef  mov     [rsp+1E0h+var_188], r14d
0x1800721f4  mov     [rsp+1E0h+var_190], r15d
0x1800721f9  mov     qword ptr [rsp+1E0h+var_198], r12
0x1800721fe  mov     [rsp+1E0h+var_1A0], rax
0x180072203  mov     rax, [rbp+0D0h+var_F0]
0x180072207  mov     [rsp+1E0h+var_1A8], r13
0x18007220c  mov     [rsp+1E0h+var_1B0], r11
0x180072211  mov     [rsp+1E0h+var_1B8], r10
0x180072216  mov     [rsp+1E0h+var_1C0], rcx
0x18007221b  mov     rcx, [rbp+0D0h+pidl]
0x18007221f  movaps  [rbp+0D0h+var_110], xmm1
0x180072223  movsd   [rbp+0D0h+var_100], xmm0
0x180072228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007222d  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x180072231  call    cs:__imp_SysFreeString
0x180072237  test    byte ptr cs:Microsoft_IEFRAMEEnableBits+1, 4
0x18007223e  mov     r12d, 1
0x180072244  jz      short loc_180072265
0x180072246  lea     rax, [rbp+0D0h+var_80]
0x18007224a  mov     r9d, r12d
0x18007224d  lea     rdx, Shdocvw_VirtualTab_NavigateThreadProc_NavigateEx2Call_Stop
0x180072254  mov     [rsp+1E0h+var_1C0], rax
0x180072259  lea     rcx, BERP_IEFRAME2_Context
0x180072260  call    McGenEventWrite_EventWriteTransfer
0x180072265  mov     rdi, [rbp+0D0h+var_120]
0x180072269  xor     r15d, r15d
0x18007226c  mov     r14b, [rbp+0D0h+var_150]
0x180072270  mov     ebx, r15d
0x180072273  jmp     short loc_180072282
0x180072275  mov     ebx, 80004005h
0x18007227a  jmp     loc_180072442
0x18007227f  mov     ebx, r13d
0x180072282  mov     rcx, [rbp+0D0h+pidl]
0x180072286  test    rcx, rcx
0x180072289  jz      loc_180072442
0x18007228f  mov     rax, [rcx]
0x180072292  mov     rax, [rax+10h]
0x180072296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007229b  jmp     loc_180072442
0x1800722a0  and     dword ptr [rdi+24h], 0FFFEE7FFh
0x1800722a7  lea     rcx, [rbp+0D0h+var_A0]
0x1800722ab  mov     edx, [rdi+24h]
0x1800722ae  xor     eax, eax
0x1800722b0  xorps   xmm0, xmm0
0x1800722b3  mov     [rbp+0D0h+var_90], rax
0x1800722b7  xorps   xmm1, xmm1
0x1800722ba  mov     [rbp+0D0h+var_C0], rax
0x1800722be  movups  [rbp+0D0h+var_A0], xmm0
0x1800722c2  mov     [rbp+0D0h+var_D8], rax
0x1800722c6  movups  [rbp+0D0h+var_D0], xmm1
0x1800722ca  mov     [rbp+0D0h+var_100], rax
0x1800722ce  movups  [rbp+0D0h+var_E8], xmm0
0x1800722d2  mov     [rbp+0D0h+var_A8], rax
0x1800722d6  movups  [rbp+0D0h+var_110], xmm1
0x1800722da  movups  [rbp+0D0h+var_B8], xmm0
0x1800722de  call    ??4CComVariant@ATL@@QEAAAEAV01@J@Z; ATL::CComVariant::operator=(long)
0x1800722e3  mov     rdx, [rdi+10h]
0x1800722e7  test    rdx, rdx
0x1800722ea  jz      short loc_180072338
0x1800722ec  mov     rdx, [rdx+38h]
0x1800722f0  test    rdx, rdx
0x1800722f3  jz      short loc_18007230C
0x1800722f5  lea     rcx, [rbp+0D0h+var_D0]
0x1800722f9  call    ??4CComVariant@ATL@@QEAAAEAV01@PEAG@Z; ATL::CComVariant::operator=(ushort *)
0x1800722fe  mov     rax, qword ptr [rbp+0D0h+var_D0+8]
0x180072302  neg     rax
0x180072305  sbb     ebx, ebx
0x180072307  not     ebx
0x180072309  and     ebx, r13d
0x18007230c  mov     rax, [rdi+10h]
0x180072310  mov     rdx, [rax+20h]
0x180072314  test    rdx, rdx
0x180072317  jz      short loc_180072338
0x180072319  test    ebx, ebx
0x18007231b  js      loc_180072415
0x180072321  lea     rcx, [rbp+0D0h+var_E8]
0x180072325  call    ??4CComVariant@ATL@@QEAAAEAV01@PEAG@Z; ATL::CComVariant::operator=(ushort *)
0x18007232a  cmp     qword ptr [rbp+0D0h+var_E8+8], r15
0x18007232e  jnz     short loc_180072340
0x180072330  mov     ebx, r13d
0x180072333  jmp     loc_180072415
0x180072338  test    ebx, ebx
0x18007233a  js      loc_180072415
  ... truncated ...
```
