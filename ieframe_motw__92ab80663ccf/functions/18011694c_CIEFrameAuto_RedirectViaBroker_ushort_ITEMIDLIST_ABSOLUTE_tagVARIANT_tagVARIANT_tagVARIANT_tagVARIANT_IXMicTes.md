# CIEFrameAuto::_RedirectViaBroker(ushort *,_ITEMIDLIST_ABSOLUTE *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,IXMicTestMode *)

- ea: `0x18011694c`
- end: `0x180116f67`
- name: `?_RedirectViaBroker@CIEFrameAuto@@IEAAJPEAGPEAU_ITEMIDLIST_ABSOLUTE@@PEAUtagVARIANT@@222PEAUIXMicTestMode@@@Z`
- size: `1563`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, unsigned __int16 *, struct _ITEMIDLIST_ABSOLUTE *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct IXMicTestMode *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180115648`

## callees

- `0x180005030`
- `0x18007587c`
- `0x1800964c4`
- `0x1800978cc`
- `0x180110868`
- `0x18011694c`
- `0x1802648c8`
- `0x1802652dc`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180116ba4`
- `KERNEL32!GetCurrentProcessId` at `0x180116ba4`
- `KERNEL32!GetCurrentThreadId` at `0x180116bf6`
- `KERNEL32!GetCurrentThreadId` at `0x180116bf6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpCA` at `0x1801169df`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpCA` at `0x1801169df`
- `USER32!AllowSetForegroundWindow` at `0x180116d0d`
- `USER32!AllowSetForegroundWindow` at `0x180116e29`
- `USER32!AllowSetForegroundWindow` at `0x180116d0d`
- `USER32!AllowSetForegroundWindow` at `0x180116e29`
- `OLEAUT32!__imp_VariantClear` at `0x180116f2b`
- `OLEAUT32!__imp_VariantClear` at `0x180116f2b`
- `OLEAUT32!__imp_VariantCopy` at `0x180116b70`
- `OLEAUT32!__imp_VariantCopy` at `0x180116b70`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180116ccb`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180116de7`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180116ccb`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180116de7`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180116bd3`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180116bd3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180116c75`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180116c75`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180116c10`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180116c10`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180116be2`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180116d9c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180116eb7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180116be2`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180116d9c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180116eb7`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180116bb8`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180116bb8`

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
0x18011694c  push    rbp
0x18011694e  push    rbx
0x18011694f  push    rsi
0x180116950  push    rdi
0x180116951  push    r12
0x180116953  push    r13
0x180116955  push    r14
0x180116957  push    r15
0x180116959  lea     rbp, [rsp-0C8h]
0x180116961  sub     rsp, 1C8h
0x180116968  mov     rax, cs:__security_cookie
0x18011696f  xor     rax, rsp
0x180116972  mov     [rbp+100h+var_50], rax
0x180116979  mov     rsi, [rbp+100h+arg_30]
0x180116980  xor     ebx, ebx
0x180116982  mov     r14, [rbp+100h+arg_20]
0x180116989  mov     r13, rcx
0x18011698c  mov     rcx, [rbp+100h+arg_28]
0x180116993  xor     r12d, r12d
0x180116996  mov     [rsp+200h+pvargSrc], rcx
0x18011699b  xor     r15d, r15d
0x18011699e  mov     rcx, [rbp+100h+arg_38]
0x1801169a5  mov     rdi, r9
0x1801169a8  mov     qword ptr [rsp+200h+var_1A0], rcx
0x1801169ad  mov     rax, r8
0x1801169b0  mov     qword ptr [rsp+200h+var_1B0], rdx
0x1801169b5  mov     [rsp+200h+dwProcessId], ebx
0x1801169b9  mov     [rsp+200h+var_1D0], bl
0x1801169bd  test    r8, r8
0x1801169c0  jz      short loc_1801169F2
0x1801169c2  lea     r8, [rsp+200h+pszStr1]
0x1801169c7  mov     rcx, rax
0x1801169ca  call    ILGetHiddenStringA
0x1801169cf  test    eax, eax
0x1801169d1  jz      short loc_1801169F2
0x1801169d3  lea     rdx, a1_1; "1"
0x1801169da  lea     rcx, [rsp+200h+pszStr1]; pszStr1
0x1801169df  call    cs:__imp_StrCmpCA
0x1801169e6  nop     dword ptr [rax+rax+00h]
0x1801169eb  test    eax, eax
0x1801169ed  setz    [rsp+200h+var_1D0]
0x1801169f2  xor     eax, eax
0x1801169f4  lea     ecx, [rax+3]
0x1801169f7  test    rdi, rdi
0x1801169fa  jz      short loc_180116A16
0x1801169fc  cmp     [rdi], cx
0x1801169ff  jnz     short loc_180116A06
0x180116a01  mov     ebx, [rdi+8]
0x180116a04  jmp     short loc_180116A10
0x180116a06  cmp     word ptr [rdi], 2
0x180116a0a  jnz     short loc_180116A16
0x180116a0c  movsx   ebx, word ptr [rdi+8]
0x180116a10  mov     eax, ebx
0x180116a12  mov     [rsp+200h+dwProcessId], ebx
0x180116a16  mov     edi, 4000h
0x180116a1b  test    ebx, 11801h
0x180116a21  jnz     short loc_180116A2D
0x180116a23  mov     ebx, eax
0x180116a25  or      ebx, edi
0x180116a27  mov     [rsp+200h+dwProcessId], ebx
0x180116a2b  mov     eax, ebx
0x180116a2d  mov     ecx, 8
0x180116a32  mov     edx, 4008h
0x180116a37  test    r14, r14
0x180116a3a  jz      short loc_180116A59
0x180116a3c  test    al, 1
0x180116a3e  jnz     short loc_180116A59
0x180116a40  cmp     dx, [r14]
0x180116a44  jnz     short loc_180116A4F
0x180116a46  mov     rax, [r14+8]
0x180116a4a  mov     r12, [rax]
0x180116a4d  jmp     short loc_180116A59
0x180116a4f  cmp     cx, [r14]
0x180116a53  jnz     short loc_180116A59
0x180116a55  mov     r12, [r14+8]
0x180116a59  xor     r14d, r14d
0x180116a5c  test    rsi, rsi
0x180116a5f  jz      short loc_180116A78
0x180116a61  cmp     dx, [rsi]
0x180116a64  jnz     short loc_180116A6F
0x180116a66  mov     rax, [rsi+8]
0x180116a6a  mov     r15, [rax]
0x180116a6d  jmp     short loc_180116A78
0x180116a6f  cmp     cx, [rsi]
0x180116a72  jnz     short loc_180116A78
0x180116a74  mov     r15, [rsi+8]
0x180116a78  xorps   xmm0, xmm0
0x180116a7b  lea     rcx, [rbp+100h+var_170]; void *
0x180116a7f  xor     eax, eax
0x180116a81  xor     edx, edx; Val
0x180116a83  mov     r8d, 90h; Size
0x180116a89  mov     qword ptr [rbp+100h+var_190+10h], rax
0x180116a8d  movups  xmmword ptr [rsp+200h+var_190], xmm0
0x180116a92  call    memset_0
0x180116a97  mov     rax, qword ptr [rsp+200h+var_1B0]
0x180116a9c  mov     [rbp+100h+var_170], rax
0x180116aa0  mov     [rbp+100h+var_150], r15
0x180116aa4  mov     [rbp+100h+var_138], r12
0x180116aa8  test    edi, ebx
0x180116aaa  jz      short loc_180116AB3
0x180116aac  mov     ecx, 8400000h
0x180116ab1  jmp     short loc_180116AD2
0x180116ab3  test    bl, 1
0x180116ab6  jz      short loc_180116ABF
0x180116ab8  mov     ecx, 4400000h
0x180116abd  jmp     short loc_180116AD2
0x180116abf  mov     ecx, 8400000h
0x180116ac4  bt      ebx, 0Bh
0x180116ac8  mov     rax, r14
0x180116acb  cmovb   rax, rcx
0x180116acf  mov     rcx, rax
0x180116ad2  mov     rax, rcx
0x180116ad5  mov     dword ptr [rsp+200h+pszStr1], r14d
0x180116ada  mov     rdx, 200000000h
0x180116ae4  lea     r9, [rsp+200h+pszStr1]
0x180116ae9  or      rax, rdx
0x180116aec  lea     r8, [rsp+200h+dwProcessId]
0x180116af1  bt      ebx, 0Fh
0x180116af5  cmovnb  rax, rcx
0x180116af9  mov     rcx, [r13+238h]
0x180116b00  mov     [rbp+100h+var_100], rax
0x180116b04  call    ?HandleBFCache@@YAXPEAUIOleCommandTarget@@W4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@PEAKPEAW42@@Z; HandleBFCache(IOleCommandTarget *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS,ulong *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS *)
0x180116b09  cmp     [rsp+200h+var_1D0], r14b
0x180116b0e  jz      short loc_180116B1E
0x180116b10  mov     rax, 400000000h
0x180116b1a  or      [rbp+100h+var_100], rax
0x180116b1e  mov     edi, [rsp+200h+dwProcessId]
0x180116b22  test    dil, 10h
0x180116b26  jz      short loc_180116B52
0x180116b28  lea     rdx, [r13+48h]
0x180116b2c  mov     rax, r13
0x180116b2f  neg     rax
0x180116b32  sbb     rcx, rcx
0x180116b35  and     rcx, rdx; struct IServiceProvider *
0x180116b38  lea     rdx, [rsp+200h+var_190]; struct tagVARIANT *
0x180116b3d  call    ?_GetSearchString@@YAJPEAUIServiceProvider@@PEAUtagVARIANT@@@Z; _GetSearchString(IServiceProvider *,tagVARIANT *)
0x180116b42  mov     rcx, [rbp+100h+var_128]
0x180116b46  test    eax, eax
0x180116b48  cmovns  rcx, qword ptr [rsp+200h+var_190+8]
0x180116b4e  mov     [rbp+100h+var_128], rcx
0x180116b52  xor     eax, eax
0x180116b54  xorps   xmm0, xmm0
0x180116b57  mov     qword ptr [rbp+100h+pvargDest+10h], rax
0x180116b5b  mov     rax, [rsp+200h+pvargSrc]
0x180116b60  movups  xmmword ptr [rbp+100h+pvargDest], xmm0
0x180116b64  test    rax, rax
0x180116b67  jz      short loc_180116B86
0x180116b69  mov     rdx, rax; pvargSrc
0x180116b6c  lea     rcx, [rbp+100h+pvargDest]; pvargDest
0x180116b70  call    cs:__imp_VariantCopy
0x180116b77  nop     dword ptr [rax+rax+00h]
0x180116b7c  mov     ebx, eax
0x180116b7e  test    eax, eax
0x180116b80  js      loc_180116F27
0x180116b86  xorps   xmm0, xmm0
0x180116b89  mov     [rbp+100h+var_E0], r14d
0x180116b8d  movups  xmmword ptr [rbp+100h+var_B8], xmm0
0x180116b91  mov     [rbp+100h+var_DC], edi
0x180116b94  movups  xmmword ptr [rbp+100h+var_B8+0Ch], xmm0
0x180116b98  mov     [rbp+100h+var_D8], r14
0x180116b9c  mov     [rbp+100h+var_D0], r14
0x180116ba0  movups  [rbp+100h+var_C8], xmm0
0x180116ba4  call    cs:__imp_GetCurrentProcessId
0x180116bab  nop     dword ptr [rax+rax+00h]
0x180116bb0  mov     ecx, 1
0x180116bb5  mov     dword ptr [rbp+100h+var_C8], eax
0x180116bb8  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180116bbf  nop     dword ptr [rax+rax+00h]
0x180116bc4  mov     ecx, 20000011h
0x180116bc9  mov     dword ptr [rbp+100h+var_C8+8], r14d
0x180116bcd  and     eax, 7Fh
0x180116bd0  mov     dword ptr [rbp+100h+var_C8+4], eax
0x180116bd3  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180116bda  nop     dword ptr [rax+rax+00h]
0x180116bdf  mov     [rbp+100h+var_B8], eax
0x180116be2  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180116be9  nop     dword ptr [rax+rax+00h]
0x180116bee  movups  xmm0, xmmword ptr [rax]
0x180116bf1  movdqu  xmmword ptr [rbp+100h+var_B8+0Ch], xmm0
0x180116bf6  call    cs:__imp_GetCurrentThreadId
0x180116bfd  nop     dword ptr [rax+rax+00h]
0x180116c02  xor     r9d, r9d
0x180116c05  lea     r8, [rbp+100h+var_E0]
0x180116c09  mov     edx, eax
0x180116c0b  mov     ecx, 203h
0x180116c10  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180116c17  nop     dword ptr [rax+rax+00h]
0x180116c1c  bt      edi, 0Eh
0x180116c20  jnb     short loc_180116C75
0x180116c22  mov     rcx, [r13+210h]
0x180116c29  lea     r8, [rsp+200h+pvargSrc]
0x180116c2e  mov     [rsp+200h+pvargSrc], r14
0x180116c33  lea     rdx, _GUID_acabe16f_8a7f_4b32_82cb_313c3288e78c
0x180116c3a  mov     rax, [rcx]
0x180116c3d  mov     rax, [rax]
0x180116c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116c45  mov     ebx, eax
0x180116c47  test    eax, eax
0x180116c49  js      short loc_180116C63
0x180116c4b  mov     rcx, [rsp+200h+pvargSrc]
0x180116c50  xor     r8d, r8d
0x180116c53  xor     edx, edx
0x180116c55  mov     rax, [rcx]
0x180116c58  mov     rax, [rax+38h]
0x180116c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116c61  mov     ebx, eax
0x180116c63  lea     rcx, [rsp+200h+pvargSrc]; void *
0x180116c68  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180116c6d  test    ebx, ebx
0x180116c6f  js      loc_180116F27
0x180116c75  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180116c7c  nop     dword ptr [rax+rax+00h]
0x180116c81  test    al, al
0x180116c83  jz      loc_180116DD8
0x180116c89  xorps   xmm0, xmm0
0x180116c8c  movups  xmmword ptr [rbp+100h+var_70], xmm0
0x180116c93  movups  xmmword ptr [rbp+100h+var_70+0Ch], xmm0
0x180116c9a  movups  [rbp+100h+var_90], xmm0
0x180116c9e  movups  [rbp+100h+var_80], xmm0
0x180116ca5  call    DualEngine__GetOpenerCookie
0x180116caa  mov     dword ptr [rbp+100h+var_90], eax
0x180116cad  lea     rcx, [rsp+200h+pvargSrc]
0x180116cb2  mov     eax, [rbp+100h+var_DC]
0x180116cb5  and     al, 1
0x180116cb7  mov     [rsp+200h+var_1C0], r14
0x180116cbc  neg     al
0x180116cbe  mov     [rsp+200h+pvargSrc], r14
0x180116cc3  sbb     eax, eax
0x180116cc5  and     eax, 3
0x180116cc8  mov     dword ptr [rbp+100h+var_90+8], eax
0x180116ccb  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180116cd2  nop     dword ptr [rax+rax+00h]
0x180116cd7  mov     ebx, eax
0x180116cd9  test    eax, eax
0x180116cdb  js      loc_180116F27
0x180116ce1  mov     rcx, [rsp+200h+pvargSrc]
0x180116ce6  lea     r9, [rsp+200h+dwProcessId]
0x180116ceb  mov     [rsp+200h+dwProcessId], r14d
0x180116cf0  xor     r8d, r8d
0x180116cf3  xor     edx, edx
0x180116cf5  mov     rax, [rcx]
0x180116cf8  mov     rax, [rax+18h]
0x180116cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116d01  mov     eax, [rsp+200h+dwProcessId]
0x180116d05  or      ecx, 0FFFFFFFFh
0x180116d08  test    eax, eax
0x180116d0a  cmovnz  ecx, eax; dwProcessId
0x180116d0d  call    cs:__imp_AllowSetForegroundWindow
0x180116d14  nop     dword ptr [rax+rax+00h]
0x180116d19  mov     rcx, [rsp+200h+pvargSrc]
0x180116d1e  lea     r9, [rsp+200h+var_1B0]
0x180116d23  mov     qword ptr [rsp+200h+var_1B0], r14
0x180116d28  lea     r8, IID_IUnknown
0x180116d2f  lea     rdx, CLSID_CShdocvwBroker
0x180116d36  mov     rax, [rcx]
0x180116d39  mov     rax, [rax+30h]
0x180116d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116d42  mov     ebx, eax
0x180116d44  test    eax, eax
0x180116d46  js      short loc_180116D77
0x180116d48  mov     rcx, qword ptr [rsp+200h+var_1B0]
0x180116d4d  lea     r8, [rsp+200h+var_1C0]
0x180116d52  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180116d59  mov     rax, [rcx]
0x180116d5c  mov     rax, [rax]
0x180116d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116d64  mov     rcx, qword ptr [rsp+200h+var_1B0]
0x180116d69  mov     ebx, eax
0x180116d6b  mov     rax, [rcx]
0x180116d6e  mov     rax, [rax+10h]
0x180116d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116d77  mov     rcx, [rsp+200h+pvargSrc]
0x180116d7c  mov     rax, [rcx]
0x180116d7f  mov     rax, [rax+10h]
0x180116d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116d88  test    ebx, ebx
0x180116d8a  js      loc_180116F27
0x180116d90  mov     rax, [rsp+200h+var_1C0]
0x180116d95  mov     rcx, [rax]
0x180116d98  mov     rbx, [rcx+38h]
0x180116d9c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180116da3  nop     dword ptr [rax+rax+00h]
0x180116da8  mov     rcx, [rsp+200h+var_1C0]
0x180116dad  lea     rdx, [rsp+200h+var_1A0]
0x180116db2  movups  xmm0, xmmword ptr [rax]
0x180116db5  mov     rax, rbx
0x180116db8  movdqu  [rsp+200h+var_1A0], xmm0
0x180116dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116dc3  mov     rcx, [rsp+200h+var_1C0]
0x180116dc8  lea     r9, [rbp+100h+var_90]
0x180116dcc  mov     rax, [rcx]
0x180116dcf  mov     rax, [rax+30h]
0x180116dd3  jmp     loc_180116EEF
0x180116dd8  lea     rcx, [rsp+200h+pvargSrc]
0x180116ddd  mov     [rsp+200h+var_1C0], r14
0x180116de2  mov     [rsp+200h+pvargSrc], r14
0x180116de7  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180116dee  nop     dword ptr [rax+rax+00h]
0x180116df3  mov     ebx, eax
0x180116df5  test    eax, eax
  ... truncated ...
```
