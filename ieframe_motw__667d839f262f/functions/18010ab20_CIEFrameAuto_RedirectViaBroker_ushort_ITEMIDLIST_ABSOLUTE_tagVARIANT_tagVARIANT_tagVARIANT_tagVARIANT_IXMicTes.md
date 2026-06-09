# CIEFrameAuto::_RedirectViaBroker(ushort *,_ITEMIDLIST_ABSOLUTE *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,IXMicTestMode *)

- ea: `0x18010ab20`
- end: `0x18010b0da`
- name: `?_RedirectViaBroker@CIEFrameAuto@@IEAAJPEAGPEAU_ITEMIDLIST_ABSOLUTE@@PEAUtagVARIANT@@222PEAUIXMicTestMode@@@Z`
- size: `1466`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, unsigned __int16 *, struct _ITEMIDLIST_ABSOLUTE *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct IXMicTestMode *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801098c4`

## callees

- `0x18000b9e0`
- `0x18006ff5c`
- `0x18008f70c`
- `0x180090938`
- `0x180104e3c`
- `0x18010ab20`
- `0x1802464fc`
- `0x180246e10`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18010ad6c`
- `KERNEL32!GetCurrentProcessId` at `0x18010ad6c`
- `KERNEL32!GetCurrentThreadId` at `0x18010ada6`
- `KERNEL32!GetCurrentThreadId` at `0x18010ada6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpCA` at `0x18010abb3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpCA` at `0x18010abb3`
- `USER32!AllowSetForegroundWindow` at `0x18010aea5`
- `USER32!AllowSetForegroundWindow` at `0x18010afaf`
- `USER32!AllowSetForegroundWindow` at `0x18010aea5`
- `USER32!AllowSetForegroundWindow` at `0x18010afaf`
- `OLEAUT32!__imp_VariantClear` at `0x18010b0a5`
- `OLEAUT32!__imp_VariantClear` at `0x18010b0a5`
- `OLEAUT32!__imp_VariantCopy` at `0x18010ad3e`
- `OLEAUT32!__imp_VariantCopy` at `0x18010ad3e`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010ae69`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010af73`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010ae69`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18010af73`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010ad8f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010ad8f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18010ae19`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18010ae19`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18010adba`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18010adba`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18010ad98`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18010af2e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18010b037`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18010ad98`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18010af2e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18010b037`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18010ad7a`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18010ad7a`

## pseudocode

```c
__int64 __fastcall CIEFrameAuto::_RedirectViaBroker(
        CIEFrameAuto *this,
        unsigned __int16 *a2,
        struct _ITEMIDLIST_ABSOLUTE *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6,
        struct tagVARIANT *a7,
        struct IXMicTestMode *a8)
{
  DWORD Lo; // ebx
  LONGLONG llVal; // r12
  LONGLONG v11; // r15
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  DWORD v18; // edi
  int SearchString; // eax
  LONGLONG v20; // rcx
  HRESULT UserBroker; // ebx
  DWORD CurrentThreadId; // eax
  __int64 (__fastcall ***v23)(_QWORD, GUID *, VARIANTARG **); // rcx
  DWORD v24; // ecx
  void (__fastcall *v25)(__int64, __int128 *); // rbx
  HRESULT v26; // eax
  DWORD v27; // ecx
  void (__fastcall *v28)(__int64, __int128 *); // rbx
  bool v30; // [rsp+30h] [rbp-D0h]
  DWORD dwProcessId; // [rsp+34h] [rbp-CCh] BYREF
  VARIANTARG *pvargSrc; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  CHAR pszStr1[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v36; // [rsp+60h] [rbp-A0h] BYREF
  struct tagVARIANT v37; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v38[9]; // [rsp+90h] [rbp-70h] BYREF
  LONGLONG v39; // [rsp+D8h] [rbp-28h]
  VARIANTARG pvargDest; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v41; // [rsp+100h] [rbp+0h]
  unsigned int v42; // [rsp+120h] [rbp+20h] BYREF
  DWORD v43; // [rsp+124h] [rbp+24h]
  __int64 v44; // [rsp+128h] [rbp+28h]
  __int64 v45; // [rsp+130h] [rbp+30h]
  __int128 v46; // [rsp+138h] [rbp+38h]
  _DWORD v47[10]; // [rsp+148h] [rbp+48h] BYREF
  _OWORD v48[4]; // [rsp+170h] [rbp+70h] BYREF

  Lo = 0;
  llVal = 0;
  pvargSrc = a6;
  v11 = 0;
  *(_QWORD *)&v36 = a8;
  *(_QWORD *)&v35 = a2;
  dwProcessId = 0;
  v30 = 0;
  if ( a3 && (unsigned int)ILGetHiddenStringA(a3, a2, pszStr1) )
    v30 = StrCmpCA(pszStr1, "1") == 0;
  v13 = 0;
  if ( a4 )
  {
    if ( a4->vt == 3 )
    {
      Lo = a4->cyVal.Lo;
    }
    else
    {
      if ( a4->vt != 2 )
        goto LABEL_10;
      Lo = a4->iVal;
    }
    v13 = Lo;
    dwProcessId = Lo;
  }
LABEL_10:
  if ( (Lo & 0x11801) == 0 )
  {
    LOWORD(Lo) = v13 | 0x4000;
    dwProcessId = v13 | 0x4000;
  }
  if ( a5 && (v13 & 1) == 0 )
  {
    if ( a5->vt == 16392 )
    {
      llVal = *a5->pllVal;
    }
    else if ( a5->vt == 8 )
    {
      llVal = a5->llVal;
    }
  }
  if ( a7 )
  {
    if ( a7->vt == 16392 )
    {
      v11 = *a7->pllVal;
    }
    else if ( a7->vt == 8 )
    {
      v11 = a7->llVal;
    }
  }
  memset(&v37, 0, sizeof(v37));
  memset_0(v38, 0, 0x90u);
  v38[0] = v35;
  v38[4] = v11;
  v38[7] = llVal;
  if ( (Lo & 0x4000) != 0 )
  {
    v14 = 138412032;
  }
  else if ( (Lo & 1) != 0 )
  {
    v14 = 71303168;
  }
  else
  {
    v15 = 0;
    if ( (Lo & 0x800) != 0 )
      v15 = 138412032;
    v14 = v15;
  }
  *(_DWORD *)pszStr1 = 0;
  v16 = v14 | 0x200000000LL;
  if ( (Lo & 0x8000) == 0 )
    v16 = v14;
  v17 = *((_QWORD *)this + 71);
  v41 = v16;
  HandleBFCache(v17, 0x200000000LL, &dwProcessId, pszStr1);
  if ( v30 )
    v41 |= 0x400000000uLL;
  v18 = dwProcessId;
  if ( (dwProcessId & 0x10) != 0 )
  {
    SearchString = _GetSearchString(
                     (struct IServiceProvider *)(((unsigned __int64)this + 72) & -(__int64)(this != 0)),
                     &v37);
    v20 = v39;
    if ( SearchString >= 0 )
      v20 = v37.llVal;
    v39 = v20;
  }
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( !pvargSrc || (UserBroker = VariantCopy(&pvargDest, pvargSrc), UserBroker >= 0) )
  {
    v42 = 0;
    memset(v47, 0, 28);
    v43 = v18;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    LODWORD(v46) = GetCurrentProcessId();
    *(_QWORD *)((char *)&v46 + 4) = IsoGetIntegrity(1) & 0x7F;
    v47[0] = IEConfiguration_GetDWORD(536870929);
    *(_OWORD *)&v47[3] = *(_OWORD *)GlobalThreadState();
    CurrentThreadId = GetCurrentThreadId();
    LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v42, 0);
    if ( (v18 & 0x4000) == 0 )
      goto LABEL_65;
    v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, VARIANTARG **))*((_QWORD *)this + 66);
    pvargSrc = 0;
    UserBroker = (**v23)(v23, &GUID_acabe16f_8a7f_4b32_82cb_313c3288e78c, &pvargSrc);
    if ( UserBroker >= 0 )
      UserBroker = (*(__int64 (__fastcall **)(VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)&pvargSrc->vt + 56LL))(
                     pvargSrc,
                     0,
                     0);
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pvargSrc);
    if ( UserBroker >= 0 )
    {
LABEL_65:
      if ( IsDualEngineProcess() )
      {
        memset(v48, 0, 60);
        LODWORD(v48[0]) = DualEngine::GetOpenerCookie();
        v33 = 0;
        pvargSrc = 0;
        DWORD2(v48[0]) = (v43 & 1) != 0 ? 3 : 0;
        UserBroker = CoCreateUserBroker((struct IEUserBroker **)&pvargSrc);
        if ( UserBroker >= 0 )
        {
          dwProcessId = 0;
          (*(void (__fastcall **)(VARIANTARG *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)&pvargSrc->vt + 24LL))(
            pvargSrc,
            0,
            0,
            &dwProcessId);
          v24 = -1;
          if ( dwProcessId )
            v24 = dwProcessId;
          AllowSetForegroundWindow(v24);
          *(_QWORD *)&v35 = 0;
          UserBroker = (*(__int64 (__fastcall **)(VARIANTARG *, GUID *, GUID *, __int128 *))(*(_QWORD *)&pvargSrc->vt
                                                                                           + 48LL))(
                         pvargSrc,
                         &CLSID_CShdocvwBroker,
                         &IID_IUnknown,
                         &v35);
          if ( UserBroker >= 0 )
          {
            UserBroker = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v35)(
                           v35,
                           &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                           &v33);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35 + 16LL))(v35);
          }
          (*(void (__fastcall **)(VARIANTARG *))(*(_QWORD *)&pvargSrc->vt + 16LL))(pvargSrc);
          if ( UserBroker >= 0 )
          {
            v25 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v33 + 56LL);
            v36 = *(_OWORD *)GlobalThreadState();
            v25(v33, &v36);
            v26 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *, _OWORD *))(*(_QWORD *)v33 + 48LL))(
                    v33,
                    v38,
                    &v42,
                    v48);
LABEL_59:
            UserBroker = v26;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
            if ( UserBroker >= 0 && *(_DWORD *)pszStr1 )
              LogBFCacheFailureDWORD(*((_QWORD *)this + 71));
          }
        }
      }
      else
      {
        v33 = 0;
        pvargSrc = 0;
        UserBroker = CoCreateUserBroker((struct IEUserBroker **)&pvargSrc);
        if ( UserBroker >= 0 )
        {
          dwProcessId = 0;
          (*(void (__fastcall **)(VARIANTARG *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)&pvargSrc->vt + 24LL))(
            pvargSrc,
            0,
            0,
            &dwProcessId);
          v27 = -1;
          if ( dwProcessId )
            v27 = dwProcessId;
          AllowSetForegroundWindow(v27);
          *(_QWORD *)&v35 = 0;
          UserBroker = (*(__int64 (__fastcall **)(VARIANTARG *, GUID *, GUID *, __int128 *))(*(_QWORD *)&pvargSrc->vt
                                                                                           + 48LL))(
                         pvargSrc,
                         &CLSID_CShdocvwBroker,
                         &IID_IUnknown,
                         &v35);
          if ( UserBroker >= 0 )
          {
            UserBroker = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v35)(
                           v35,
                           &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                           &v33);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35 + 16LL))(v35);
          }
          (*(void (__fastcall **)(VARIANTARG *))(*(_QWORD *)&pvargSrc->vt + 16LL))(pvargSrc);
          if ( UserBroker >= 0 )
          {
            v28 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v33 + 1256LL);
            v35 = *(_OWORD *)GlobalThreadState();
            v28(v33, &v35);
            v26 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *, _QWORD))(*(_QWORD *)v33 + 40LL))(
                    v33,
                    v38,
                    &v42,
                    v36);
            goto LABEL_59;
          }
        }
      }
    }
  }
  VariantClear(&pvargDest);
  ATL::CComVariant::Clear((ATL::CComVariant *)&v37);
  return (unsigned int)UserBroker;
}

```

## disassembly

```asm
0x18010ab20  push    rbp
0x18010ab22  push    rbx
0x18010ab23  push    rsi
0x18010ab24  push    rdi
0x18010ab25  push    r12
0x18010ab27  push    r13
0x18010ab29  push    r14
0x18010ab2b  push    r15
0x18010ab2d  lea     rbp, [rsp-0C8h]
0x18010ab35  sub     rsp, 1C8h
0x18010ab3c  mov     rax, cs:__security_cookie
0x18010ab43  xor     rax, rsp
0x18010ab46  mov     [rbp+100h+var_50], rax
0x18010ab4d  mov     rsi, [rbp+100h+arg_30]
0x18010ab54  xor     ebx, ebx
0x18010ab56  mov     r14, [rbp+100h+arg_20]
0x18010ab5d  mov     r13, rcx
0x18010ab60  mov     rcx, [rbp+100h+arg_28]
0x18010ab67  xor     r12d, r12d
0x18010ab6a  mov     [rsp+200h+pvargSrc], rcx
0x18010ab6f  xor     r15d, r15d
0x18010ab72  mov     rcx, [rbp+100h+arg_38]
0x18010ab79  mov     rdi, r9
0x18010ab7c  mov     qword ptr [rsp+200h+var_1A0], rcx
0x18010ab81  mov     rax, r8
0x18010ab84  mov     qword ptr [rsp+200h+var_1B0], rdx
0x18010ab89  mov     [rsp+200h+dwProcessId], ebx
0x18010ab8d  mov     [rsp+200h+var_1D0], bl
0x18010ab91  test    r8, r8
0x18010ab94  jz      short loc_18010ABC0
0x18010ab96  lea     r8, [rsp+200h+pszStr1]
0x18010ab9b  mov     rcx, rax
0x18010ab9e  call    ILGetHiddenStringA
0x18010aba3  test    eax, eax
0x18010aba5  jz      short loc_18010ABC0
0x18010aba7  lea     rdx, a1_1; "1"
0x18010abae  lea     rcx, [rsp+200h+pszStr1]; pszStr1
0x18010abb3  call    cs:__imp_StrCmpCA
0x18010abb9  test    eax, eax
0x18010abbb  setz    [rsp+200h+var_1D0]
0x18010abc0  xor     eax, eax
0x18010abc2  lea     ecx, [rax+3]
0x18010abc5  test    rdi, rdi
0x18010abc8  jz      short loc_18010ABE4
0x18010abca  cmp     [rdi], cx
0x18010abcd  jnz     short loc_18010ABD4
0x18010abcf  mov     ebx, [rdi+8]
0x18010abd2  jmp     short loc_18010ABDE
0x18010abd4  cmp     word ptr [rdi], 2
0x18010abd8  jnz     short loc_18010ABE4
0x18010abda  movsx   ebx, word ptr [rdi+8]
0x18010abde  mov     eax, ebx
0x18010abe0  mov     [rsp+200h+dwProcessId], ebx
0x18010abe4  mov     edi, 4000h
0x18010abe9  test    ebx, 11801h
0x18010abef  jnz     short loc_18010ABFB
0x18010abf1  mov     ebx, eax
0x18010abf3  or      ebx, edi
0x18010abf5  mov     [rsp+200h+dwProcessId], ebx
0x18010abf9  mov     eax, ebx
0x18010abfb  mov     ecx, 8
0x18010ac00  mov     edx, 4008h
0x18010ac05  test    r14, r14
0x18010ac08  jz      short loc_18010AC27
0x18010ac0a  test    al, 1
0x18010ac0c  jnz     short loc_18010AC27
0x18010ac0e  cmp     dx, [r14]
0x18010ac12  jnz     short loc_18010AC1D
0x18010ac14  mov     rax, [r14+8]
0x18010ac18  mov     r12, [rax]
0x18010ac1b  jmp     short loc_18010AC27
0x18010ac1d  cmp     cx, [r14]
0x18010ac21  jnz     short loc_18010AC27
0x18010ac23  mov     r12, [r14+8]
0x18010ac27  xor     r14d, r14d
0x18010ac2a  test    rsi, rsi
0x18010ac2d  jz      short loc_18010AC46
0x18010ac2f  cmp     dx, [rsi]
0x18010ac32  jnz     short loc_18010AC3D
0x18010ac34  mov     rax, [rsi+8]
0x18010ac38  mov     r15, [rax]
0x18010ac3b  jmp     short loc_18010AC46
0x18010ac3d  cmp     cx, [rsi]
0x18010ac40  jnz     short loc_18010AC46
0x18010ac42  mov     r15, [rsi+8]
0x18010ac46  xorps   xmm0, xmm0
0x18010ac49  lea     rcx, [rbp+100h+var_170]; void *
0x18010ac4d  xor     eax, eax
0x18010ac4f  xor     edx, edx; Val
0x18010ac51  mov     r8d, 90h; Size
0x18010ac57  mov     qword ptr [rbp+100h+var_190+10h], rax
0x18010ac5b  movups  xmmword ptr [rsp+200h+var_190], xmm0
0x18010ac60  call    memset_0
0x18010ac65  mov     rax, qword ptr [rsp+200h+var_1B0]
0x18010ac6a  mov     [rbp+100h+var_170], rax
0x18010ac6e  mov     [rbp+100h+var_150], r15
0x18010ac72  mov     [rbp+100h+var_138], r12
0x18010ac76  test    edi, ebx
0x18010ac78  jz      short loc_18010AC81
0x18010ac7a  mov     ecx, 8400000h
0x18010ac7f  jmp     short loc_18010ACA0
0x18010ac81  test    bl, 1
0x18010ac84  jz      short loc_18010AC8D
0x18010ac86  mov     ecx, 4400000h
0x18010ac8b  jmp     short loc_18010ACA0
0x18010ac8d  mov     ecx, 8400000h
0x18010ac92  bt      ebx, 0Bh
0x18010ac96  mov     rax, r14
0x18010ac99  cmovb   rax, rcx
0x18010ac9d  mov     rcx, rax
0x18010aca0  mov     rax, rcx
0x18010aca3  mov     dword ptr [rsp+200h+pszStr1], r14d
0x18010aca8  mov     rdx, 200000000h
0x18010acb2  lea     r9, [rsp+200h+pszStr1]
0x18010acb7  or      rax, rdx
0x18010acba  lea     r8, [rsp+200h+dwProcessId]
0x18010acbf  bt      ebx, 0Fh
0x18010acc3  cmovnb  rax, rcx
0x18010acc7  mov     rcx, [r13+238h]
0x18010acce  mov     [rbp+100h+var_100], rax
0x18010acd2  call    ?HandleBFCache@@YAXPEAUIOleCommandTarget@@W4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@PEAKPEAW42@@Z; HandleBFCache(IOleCommandTarget *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS,ulong *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS *)
0x18010acd7  cmp     [rsp+200h+var_1D0], r14b
0x18010acdc  jz      short loc_18010ACEC
0x18010acde  mov     rax, 400000000h
0x18010ace8  or      [rbp+100h+var_100], rax
0x18010acec  mov     edi, [rsp+200h+dwProcessId]
0x18010acf0  test    dil, 10h
0x18010acf4  jz      short loc_18010AD20
0x18010acf6  lea     rdx, [r13+48h]
0x18010acfa  mov     rax, r13
0x18010acfd  neg     rax
0x18010ad00  sbb     rcx, rcx
0x18010ad03  and     rcx, rdx; struct IServiceProvider *
0x18010ad06  lea     rdx, [rsp+200h+var_190]; struct tagVARIANT *
0x18010ad0b  call    ?_GetSearchString@@YAJPEAUIServiceProvider@@PEAUtagVARIANT@@@Z; _GetSearchString(IServiceProvider *,tagVARIANT *)
0x18010ad10  mov     rcx, [rbp+100h+var_128]
0x18010ad14  test    eax, eax
0x18010ad16  cmovns  rcx, qword ptr [rsp+200h+var_190+8]
0x18010ad1c  mov     [rbp+100h+var_128], rcx
0x18010ad20  xor     eax, eax
0x18010ad22  xorps   xmm0, xmm0
0x18010ad25  mov     qword ptr [rbp+100h+pvargDest+10h], rax
0x18010ad29  mov     rax, [rsp+200h+pvargSrc]
0x18010ad2e  movups  xmmword ptr [rbp+100h+pvargDest], xmm0
0x18010ad32  test    rax, rax
0x18010ad35  jz      short loc_18010AD4E
0x18010ad37  mov     rdx, rax; pvargSrc
0x18010ad3a  lea     rcx, [rbp+100h+pvargDest]; pvargDest
0x18010ad3e  call    cs:__imp_VariantCopy
0x18010ad44  mov     ebx, eax
0x18010ad46  test    eax, eax
0x18010ad48  js      loc_18010B0A1
0x18010ad4e  xorps   xmm0, xmm0
0x18010ad51  mov     [rbp+100h+var_E0], r14d
0x18010ad55  movups  xmmword ptr [rbp+100h+var_B8], xmm0
0x18010ad59  mov     [rbp+100h+var_DC], edi
0x18010ad5c  movups  xmmword ptr [rbp+100h+var_B8+0Ch], xmm0
0x18010ad60  mov     [rbp+100h+var_D8], r14
0x18010ad64  mov     [rbp+100h+var_D0], r14
0x18010ad68  movups  [rbp+100h+var_C8], xmm0
0x18010ad6c  call    cs:__imp_GetCurrentProcessId
0x18010ad72  mov     ecx, 1
0x18010ad77  mov     dword ptr [rbp+100h+var_C8], eax
0x18010ad7a  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18010ad80  mov     ecx, 20000011h
0x18010ad85  mov     dword ptr [rbp+100h+var_C8+8], r14d
0x18010ad89  and     eax, 7Fh
0x18010ad8c  mov     dword ptr [rbp+100h+var_C8+4], eax
0x18010ad8f  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18010ad95  mov     [rbp+100h+var_B8], eax
0x18010ad98  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18010ad9e  movups  xmm0, xmmword ptr [rax]
0x18010ada1  movdqu  xmmword ptr [rbp+100h+var_B8+0Ch], xmm0
0x18010ada6  call    cs:__imp_GetCurrentThreadId
0x18010adac  xor     r9d, r9d
0x18010adaf  lea     r8, [rbp+100h+var_E0]
0x18010adb3  mov     edx, eax
0x18010adb5  mov     ecx, 203h
0x18010adba  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x18010adc0  bt      edi, 0Eh
0x18010adc4  jnb     short loc_18010AE19
0x18010adc6  mov     rcx, [r13+210h]
0x18010adcd  lea     r8, [rsp+200h+pvargSrc]
0x18010add2  mov     [rsp+200h+pvargSrc], r14
0x18010add7  lea     rdx, _GUID_acabe16f_8a7f_4b32_82cb_313c3288e78c
0x18010adde  mov     rax, [rcx]
0x18010ade1  mov     rax, [rax]
0x18010ade4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ade9  mov     ebx, eax
0x18010adeb  test    eax, eax
0x18010aded  js      short loc_18010AE07
0x18010adef  mov     rcx, [rsp+200h+pvargSrc]
0x18010adf4  xor     r8d, r8d
0x18010adf7  xor     edx, edx
0x18010adf9  mov     rax, [rcx]
0x18010adfc  mov     rax, [rax+38h]
0x18010ae00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ae05  mov     ebx, eax
0x18010ae07  lea     rcx, [rsp+200h+pvargSrc]; void *
0x18010ae0c  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18010ae11  test    ebx, ebx
0x18010ae13  js      loc_18010B0A1
0x18010ae19  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18010ae1f  test    al, al
0x18010ae21  jz      loc_18010AF64
0x18010ae27  xorps   xmm0, xmm0
0x18010ae2a  movups  xmmword ptr [rbp+100h+var_70], xmm0
0x18010ae31  movups  xmmword ptr [rbp+100h+var_70+0Ch], xmm0
0x18010ae38  movups  [rbp+100h+var_90], xmm0
0x18010ae3c  movups  [rbp+100h+var_80], xmm0
0x18010ae43  call    DualEngine__GetOpenerCookie
0x18010ae48  mov     dword ptr [rbp+100h+var_90], eax
0x18010ae4b  lea     rcx, [rsp+200h+pvargSrc]
0x18010ae50  mov     eax, [rbp+100h+var_DC]
0x18010ae53  and     al, 1
0x18010ae55  mov     [rsp+200h+var_1C0], r14
0x18010ae5a  neg     al
0x18010ae5c  mov     [rsp+200h+pvargSrc], r14
0x18010ae61  sbb     eax, eax
0x18010ae63  and     eax, 3
0x18010ae66  mov     dword ptr [rbp+100h+var_90+8], eax
0x18010ae69  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010ae6f  mov     ebx, eax
0x18010ae71  test    eax, eax
0x18010ae73  js      loc_18010B0A1
0x18010ae79  mov     rcx, [rsp+200h+pvargSrc]
0x18010ae7e  lea     r9, [rsp+200h+dwProcessId]
0x18010ae83  mov     [rsp+200h+dwProcessId], r14d
0x18010ae88  xor     r8d, r8d
0x18010ae8b  xor     edx, edx
0x18010ae8d  mov     rax, [rcx]
0x18010ae90  mov     rax, [rax+18h]
0x18010ae94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ae99  mov     eax, [rsp+200h+dwProcessId]
0x18010ae9d  or      ecx, 0FFFFFFFFh
0x18010aea0  test    eax, eax
0x18010aea2  cmovnz  ecx, eax; dwProcessId
0x18010aea5  call    cs:__imp_AllowSetForegroundWindow
0x18010aeab  mov     rcx, [rsp+200h+pvargSrc]
0x18010aeb0  lea     r9, [rsp+200h+var_1B0]
0x18010aeb5  mov     qword ptr [rsp+200h+var_1B0], r14
0x18010aeba  lea     r8, IID_IUnknown
0x18010aec1  lea     rdx, CLSID_CShdocvwBroker
0x18010aec8  mov     rax, [rcx]
0x18010aecb  mov     rax, [rax+30h]
0x18010aecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aed4  mov     ebx, eax
0x18010aed6  test    eax, eax
0x18010aed8  js      short loc_18010AF09
0x18010aeda  mov     rcx, qword ptr [rsp+200h+var_1B0]
0x18010aedf  lea     r8, [rsp+200h+var_1C0]
0x18010aee4  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x18010aeeb  mov     rax, [rcx]
0x18010aeee  mov     rax, [rax]
0x18010aef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aef6  mov     rcx, qword ptr [rsp+200h+var_1B0]
0x18010aefb  mov     ebx, eax
0x18010aefd  mov     rax, [rcx]
0x18010af00  mov     rax, [rax+10h]
0x18010af04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010af09  mov     rcx, [rsp+200h+pvargSrc]
0x18010af0e  mov     rax, [rcx]
0x18010af11  mov     rax, [rax+10h]
0x18010af15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010af1a  test    ebx, ebx
0x18010af1c  js      loc_18010B0A1
0x18010af22  mov     rax, [rsp+200h+var_1C0]
0x18010af27  mov     rcx, [rax]
0x18010af2a  mov     rbx, [rcx+38h]
0x18010af2e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18010af34  mov     rcx, [rsp+200h+var_1C0]
0x18010af39  lea     rdx, [rsp+200h+var_1A0]
0x18010af3e  movups  xmm0, xmmword ptr [rax]
0x18010af41  mov     rax, rbx
0x18010af44  movdqu  [rsp+200h+var_1A0], xmm0
0x18010af4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010af4f  mov     rcx, [rsp+200h+var_1C0]
0x18010af54  lea     r9, [rbp+100h+var_90]
0x18010af58  mov     rax, [rcx]
0x18010af5b  mov     rax, [rax+30h]
0x18010af5f  jmp     loc_18010B069
0x18010af64  lea     rcx, [rsp+200h+pvargSrc]
0x18010af69  mov     [rsp+200h+var_1C0], r14
0x18010af6e  mov     [rsp+200h+pvargSrc], r14
0x18010af73  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18010af79  mov     ebx, eax
0x18010af7b  test    eax, eax
0x18010af7d  js      loc_18010B0A1
0x18010af83  mov     rcx, [rsp+200h+pvargSrc]
0x18010af88  lea     r9, [rsp+200h+dwProcessId]
0x18010af8d  mov     [rsp+200h+dwProcessId], r14d
0x18010af92  xor     r8d, r8d
0x18010af95  xor     edx, edx
0x18010af97  mov     rax, [rcx]
0x18010af9a  mov     rax, [rax+18h]
0x18010af9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010afa3  mov     eax, [rsp+200h+dwProcessId]
0x18010afa7  or      ecx, 0FFFFFFFFh
0x18010afaa  test    eax, eax
0x18010afac  cmovnz  ecx, eax; dwProcessId
  ... truncated ...
```
