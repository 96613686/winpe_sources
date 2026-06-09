# RedirectViaBrokerIfNeeded

- ea: `0x18070bc00`
- end: `0x18070c512`
- name: `RedirectViaBrokerIfNeeded`
- size: `2322`
- prototype: `__int64 __usercall@<rax>(struct IUri *@<rcx>, __int64, unsigned __int64, int, __int64, int, struct COmWindowProxy *, char, char, char, char, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18075f090`

## callees

- `0x180373368`
- `0x1804e223c`
- `0x1804fa5e0`
- `0x1805fe298`
- `0x18070bc00`
- `0x1807c0050`
- `0x1808c5f50`
- `0x1808c7cd4`
- `0x1808c8190`
- `0x1808c8f54`
- `0x1808c936c`
- `0x1808ed988`
- `0x1808ee664`
- `0x18105c440`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18070bfbc`
- `KERNEL32!GetCurrentProcessId` at `0x18070bfbc`
- `KERNEL32!GetCurrentThreadId` at `0x18070c016`
- `KERNEL32!GetCurrentThreadId` at `0x18070c016`
- `USER32!AllowSetForegroundWindow` at `0x18070c20d`
- `USER32!AllowSetForegroundWindow` at `0x18070c31f`
- `USER32!AllowSetForegroundWindow` at `0x18070c20d`
- `USER32!AllowSetForegroundWindow` at `0x18070c31f`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18070bde8`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18070bde8`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18070c1ce`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18070c2e0`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18070c1ce`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18070c2e0`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18070bfe5`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18070bfe5`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18070c10e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18070c10e`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18070c02d`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x18070c02d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18070bff1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18070c29a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18070c3af`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18070bff1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18070c29a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18070c3af`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18070bfcb`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18070bfcb`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18070bd63`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18070bd63`
- `OLEAUT32!__imp_SysAllocString` at `0x18070c0fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18070c0fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18070c46a`
- `OLEAUT32!__imp_SysFreeString` at `0x18070c47c`
- `OLEAUT32!__imp_SysFreeString` at `0x18070c4b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18070c46a`
- `OLEAUT32!__imp_SysFreeString` at `0x18070c47c`
- `OLEAUT32!__imp_SysFreeString` at `0x18070c4b7`
- `OLEAUT32!__imp_VariantInit` at `0x18070bead`
- `OLEAUT32!__imp_VariantInit` at `0x18070c0b7`
- `OLEAUT32!__imp_VariantInit` at `0x18070bead`
- `OLEAUT32!__imp_VariantInit` at `0x18070c0b7`
- `OLEAUT32!__imp_VariantClear` at `0x18070c108`
- `OLEAUT32!__imp_VariantClear` at `0x18070c108`

## pseudocode

```c
__int64 __fastcall RedirectViaBrokerIfNeeded(
        OLECHAR *a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int64 a5,
        unsigned __int64 a6,
        int a7,
        unsigned __int16 *a8,
        int a9,
        struct COmWindowProxy *a10,
        bool a11,
        char a12,
        char a13,
        char a14,
        __int64 a15)
{
  int UserBroker; // ebx
  __int64 v16; // rdx
  bool v17; // r12
  bool v18; // al
  bool v19; // r14
  bool v20; // di
  unsigned __int64 v21; // rdi
  CWindow *v22; // rdx
  struct CDoc *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  BSTR v26; // r12
  int v27; // eax
  unsigned __int16 *v28; // r13
  unsigned int v29; // eax
  CWindow *v30; // rcx
  int v31; // ebx
  CDoc *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  CDoc *v35; // rdi
  unsigned __int8 v36; // r12
  int v37; // eax
  __int128 v38; // xmm0
  DWORD CurrentThreadId; // eax
  CWindow *v40; // rdx
  struct CDoc *v41; // rax
  CWindow *v42; // rcx
  struct CDoc *v43; // rax
  CWindow *v44; // r9
  CDoc *v45; // rax
  struct CWindow *v46; // r9
  DWORD v47; // ecx
  void (__fastcall *v48)(unsigned __int16 *, VARIANTARG *); // rbx
  int v49; // eax
  DWORD v50; // ecx
  void (__fastcall *v51)(unsigned __int16 *, VARIANTARG *); // rbx
  struct CDoc *v52; // rax
  __int64 v53; // rcx
  BOOL v54; // edi
  unsigned __int8 v56; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v57; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v58; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v59; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v60; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwProcessId[2]; // [rsp+78h] [rbp-88h] BYREF
  BSTR v62; // [rsp+80h] [rbp-80h] BYREF
  int v63; // [rsp+88h] [rbp-78h] BYREF
  char v64; // [rsp+8Ch] [rbp-74h]
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v67; // [rsp+A0h] [rbp-60h] BYREF
  void **v68; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+D0h] [rbp-30h]
  BSTR v71[2]; // [rsp+D8h] [rbp-28h]
  int v72; // [rsp+E8h] [rbp-18h]
  _BYTE v73[80]; // [rsp+F0h] [rbp-10h] BYREF
  BSTR v74; // [rsp+140h] [rbp+40h]
  VARIANTARG pvarg; // [rsp+148h] [rbp+48h] BYREF
  int v76; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v77; // [rsp+184h] [rbp+84h]
  __int64 v78; // [rsp+188h] [rbp+88h]
  __int64 v79; // [rsp+190h] [rbp+90h]
  __int128 v80; // [rsp+198h] [rbp+98h]
  _DWORD v81[10]; // [rsp+1A8h] [rbp+A8h] BYREF
  _OWORD v82[4]; // [rsp+1D0h] [rbp+D0h] BYREF

  v60 = a8;
  *(_QWORD *)&v67.vt = a15;
  v65 = a2;
  v57 = a3;
  v62 = a1;
  v68 = &CUString::`vftable';
  v59 = a4;
  *(_QWORD *)dwProcessId = a5;
  v69 = 0;
  v70 = 11;
  *(_OWORD *)v71 = 0;
  v72 = 0;
  UserBroker = CUString::Set((CUString *)&v68, (struct IUri *)a1, Uri_PROPERTY_ABSOLUTE_URI);
  if ( UserBroker )
    goto LABEL_105;
  v16 = *((_QWORD *)a10 + 15);
  v17 = v16 && (*(_DWORD *)(*(_QWORD *)(v16 + 104) + 756LL) & 0x100) != 0;
  v18 = v16 && (*(_BYTE *)(v16 + 226) & 1) != 0 && (*(_BYTE *)(v16 + 223) & 0x20) != 0;
  v19 = (a6 & 0x21000) == 0 && !v18;
  v56 = 0;
  if ( a12 )
    v20 = 0;
  else
    v20 = *(char *)(a5 + 180) < 0;
  v63 = 0;
  v64 = 0;
  BYTE2(v63) = a14;
  if ( v20 )
  {
    UserBroker = 1;
    goto LABEL_21;
  }
  UserBroker = IsRedirectToBrokerNeeded(v71[1], (const struct tagRedirectionPolicyFlags *)&v63);
  if ( UserBroker )
  {
LABEL_21:
    if ( v17 )
      goto LABEL_105;
    if ( v20 )
      goto LABEL_105;
    if ( !a13 )
      goto LABEL_105;
    if ( (a6 & 0xC400000) != 0 )
      goto LABEL_105;
    if ( !v19 )
      goto LABEL_105;
    v21 = a6;
    if ( (a6 & 0x80000000) != 0 )
      goto LABEL_105;
    if ( !*((_QWORD *)a10 + 15) )
      goto LABEL_105;
    if ( !CWindow::Doc(*((CWindow **)a10 + 15)) )
      goto LABEL_105;
    v23 = CWindow::Doc(v22);
    if ( (unsigned int)CDoc::CheckBFCacheCandidacy(v23, 2142830577, v24, v25) )
      goto LABEL_105;
    v56 = 1;
    goto LABEL_34;
  }
  if ( v17 )
    goto LABEL_105;
  v21 = a6;
LABEL_34:
  v26 = v62;
  if ( IsProtectedModeProcess() )
  {
LABEL_38:
    v62 = 0;
    bstrString = 0;
    if ( a11 && !a13 )
    {
      UserBroker = -2147024891;
LABEL_104:
      SysFreeString(bstrString);
      bstrString = 0;
      SysFreeString(v62);
      goto LABEL_105;
    }
    UserBroker = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v26 + 56LL))(v26, &v62);
    if ( UserBroker < 0 )
      goto LABEL_104;
    UserBroker = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v65 + 56LL))(v65, &bstrString);
    if ( UserBroker < 0 )
      goto LABEL_104;
    memset_0(v73, 0, 0x90u);
    VariantInit(&pvarg);
    v28 = v60;
    UserBroker = SetBrokerBindInfoForRedirectToBroker(
                   v62,
                   bstrString,
                   *(struct CDwnBindInfo **)dwProcessId,
                   a10,
                   v21,
                   v57,
                   v59,
                   v60,
                   (struct _BROKER_BIND_INFO *)v73);
    if ( UserBroker < 0 )
    {
LABEL_103:
      ClearBrokerBindInfo((struct _BROKER_BIND_INFO *)v73);
      goto LABEL_104;
    }
    v58 = 0;
    v29 = Convert_FHL_To_Nav(v21, (a6 & 0xC400000) == 0);
    v30 = (CWindow *)*((_QWORD *)a10 + 15);
    v31 = v29 | 0x40000000;
    if ( !a14 )
      v31 = v29;
    if ( v30 )
    {
      v32 = CWindow::Doc(v30);
      v35 = v32;
      if ( v32 )
      {
        v36 = v56;
        if ( (a6 & 0xC400000) == 0 )
          CDoc::PrepTravelLogForVirtualTabSwitch(v32, v56, &v58);
        v37 = CDoc::CheckBFCacheCandidacy(v35, 809035761, v33, v34);
        v21 = a6;
        if ( !v37 )
          v31 |= 0x40000u;
LABEL_55:
        v77 = v31;
        v76 = 0;
        memset(v81, 0, 28);
        v78 = 0;
        v79 = 0;
        v80 = 0;
        LODWORD(v80) = GetCurrentProcessId();
        *(_QWORD *)((char *)&v80 + 4) = IsoGetIntegrity(1) & 0x7F;
        v81[0] = IEConfiguration_GetDWORD(536870929);
        v38 = *(_OWORD *)GlobalThreadState();
        v81[2] = v58;
        *(_OWORD *)&v81[3] = v38;
        if ( a9 )
        {
          v76 = a9;
        }
        else
        {
          CurrentThreadId = GetCurrentThreadId();
          LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, (unsigned int *)&v76, 0);
        }
        v65 = 0;
        if ( *(_QWORD *)&v67.vt )
          (***(void (__fastcall ****)(_QWORD, GUID *, __int64 *))&v67.vt)(
            *(_QWORD *)&v67.vt,
            &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00,
            &v65);
        if ( (a6 & 0xC400000) == 0 && *((_QWORD *)a10 + 15) && CWindow::Doc(*((CWindow **)a10 + 15)) )
        {
          v41 = CWindow::Doc(v40);
          v81[1] = CDeferredActionHandler::RegisterVTabNavigate((struct CDoc *)((char *)v41 + 1704));
        }
        v42 = (CWindow *)*((_QWORD *)a10 + 15);
        if ( v42 )
        {
          if ( CWindow::Doc(v42) )
          {
            memset(&v67, 0, sizeof(v67));
            VariantInit(&v67);
            v43 = CWindow::Doc(*((CWindow **)a10 + 15));
            if ( (int)CTExec(*((struct IUnknown **)v43 + 8), &CGID_Explorer, 0x78u, 0, 0, &v67) >= 0 && v67.vt == 8 )
            {
              v74 = SysAllocString(v67.bstrVal);
              VariantClear(&v67);
            }
          }
        }
        if ( IsDualEngineProcess() )
        {
          memset(v82, 0, 60);
          if ( (a6 & 0xC400000) != 0
            && *((_QWORD *)a10 + 15)
            && CWindow::Doc(*((CWindow **)a10 + 15))
            && (v45 = CWindow::Doc(v44),
                (int)CDoc::GetDualEngineBrokerNewWindowParams(
                       v45,
                       v21,
                       v28,
                       v46,
                       (struct __MIDL___MIDL_itf_iebroker_0000_0021_0001 *)v82) >= 0) )
          {
            if ( (v77 & 0x311801) == 0 )
              Abandonment::AssertionFailed();
            v77 = v77 & 0xFFCEE7FE | 1;
          }
          else
          {
            LODWORD(v82[0]) = DualEngine::GetOpenerCookie();
            DWORD2(v82[0]) = (v77 & 1) != 0 ? 3 : 0;
          }
          v57 = 0;
          v59 = 0;
          UserBroker = CoCreateUserBroker((struct IEUserBroker **)&v59);
          if ( UserBroker < 0 )
          {
LABEL_93:
            if ( UserBroker >= 0 )
            {
              if ( v81[1] )
              {
                v52 = CWindow::Doc(*((CWindow **)a10 + 15));
                CDeferredActionHandler::AgreeToVTabNavigate((struct CDoc *)((char *)v52 + 1704), a11);
              }
LABEL_101:
              if ( v65 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
              goto LABEL_103;
            }
LABEL_96:
            if ( UserBroker != -2147467260 && UserBroker != -2147023673 && v36 && !a11 )
              UserBroker = 1;
            goto LABEL_101;
          }
          dwProcessId[0] = 0;
          (*(void (__fastcall **)(unsigned __int16 *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v59 + 24LL))(
            v59,
            0,
            0,
            dwProcessId);
          v47 = -1;
          if ( dwProcessId[0] )
            v47 = dwProcessId[0];
          AllowSetForegroundWindow(v47);
          v60 = 0;
          UserBroker = (*(__int64 (__fastcall **)(unsigned __int16 *, GUID *, GUID *, unsigned __int16 **))(*(_QWORD *)v59 + 48LL))(
                         v59,
                         &CLSID_CShdocvwBroker,
                         &IID_IUnknown,
                         &v60);
          if ( UserBroker >= 0 )
          {
            UserBroker = (**(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, unsigned __int16 **))v60)(
                           v60,
                           &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                           &v57);
            (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v60 + 16LL))(v60);
          }
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v59 + 16LL))(v59);
          if ( UserBroker < 0 )
            goto LABEL_96;
          v48 = *(void (__fastcall **)(unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v57 + 56LL);
          *(_OWORD *)&v67.vt = *(_OWORD *)GlobalThreadState();
          v48(v57, &v67);
          v49 = (*(__int64 (__fastcall **)(unsigned __int16 *, _BYTE *, int *, _OWORD *))(*(_QWORD *)v57 + 48LL))(
                  v57,
                  v73,
                  &v76,
                  v82);
        }
        else
        {
          v57 = 0;
          v59 = 0;
          UserBroker = CoCreateUserBroker((struct IEUserBroker **)&v59);
          if ( UserBroker < 0 )
            goto LABEL_93;
          dwProcessId[0] = 0;
          (*(void (__fastcall **)(unsigned __int16 *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v59 + 24LL))(
            v59,
            0,
            0,
            dwProcessId);
          v50 = -1;
          if ( dwProcessId[0] )
            v50 = dwProcessId[0];
          AllowSetForegroundWindow(v50);
          v60 = 0;
          UserBroker = (*(__int64 (__fastcall **)(unsigned __int16 *, GUID *, GUID *, unsigned __int16 **))(*(_QWORD *)v59 + 48LL))(
                         v59,
                         &CLSID_CShdocvwBroker,
                         &IID_IUnknown,
                         &v60);
          if ( UserBroker >= 0 )
          {
            UserBroker = (**(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, unsigned __int16 **))v60)(
                           v60,
                           &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                           &v57);
            (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v60 + 16LL))(v60);
          }
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v59 + 16LL))(v59);
          if ( UserBroker < 0 )
            goto LABEL_96;
          v51 = *(void (__fastcall **)(unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v57 + 1256LL);
          *(_OWORD *)&v67.vt = *(_OWORD *)GlobalThreadState();
          v51(v57, &v67);
          v49 = (*(__int64 (__fastcall **)(unsigned __int16 *, _BYTE *, int *, __int64))(*(_QWORD *)v57 + 40LL))(
                  v57,
                  v73,
                  &v76,
                  v65);
        }
        UserBroker = v49;
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v57 + 16LL))(v57);
        goto LABEL_93;
      }
      v21 = a6;
    }
    v36 = v56;
    goto LABEL_55;
  }
  v58 = 0;
  v27 = (*(__int64 (__fastcall **)(BSTR, unsigned int *))(*(_QWORD *)v62 + 192LL))(v62, &v58);
  UserBroker = v27;
  if ( v27 < 0 || v58 == 10 )
  {
    UserBroker = 1;
  }
  else if ( !v27 )
  {
    goto LABEL_38;
  }
LABEL_105:
  v53 = v69;
  v68 = &CUString::`vftable';
  v54 = v69 != 0;
  if ( v69 || v70 != 11 )
  {
    if ( v71[0] )
    {
      SysFreeString(v71[0]);
      v53 = v69;
      v71[0] = 0;
    }
    v71[1] = 0;
    v72 = 0;
    if ( v54 && v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  }
  return (unsigned int)UserBroker;
}

```

## disassembly

```asm
0x18070bc00  push    rbp
0x18070bc02  push    rbx
0x18070bc03  push    rsi
0x18070bc04  push    rdi
0x18070bc05  push    r12
0x18070bc07  push    r13
0x18070bc09  push    r14
0x18070bc0b  push    r15
0x18070bc0d  lea     rbp, [rsp-128h]
0x18070bc15  sub     rsp, 228h
0x18070bc1c  mov     rax, cs:__security_cookie
0x18070bc23  xor     rax, rsp
0x18070bc26  mov     [rbp+160h+var_50], rax
0x18070bc2d  mov     rax, [rbp+160h+arg_38]
0x18070bc34  xorps   xmm0, xmm0
0x18070bc37  mov     rdi, [rbp+160h+arg_20]
0x18070bc3e  mov     rsi, [rbp+160h+arg_48]
0x18070bc45  mov     [rsp+260h+var_1F0], rax
0x18070bc4a  mov     rax, [rbp+160h+arg_70]
0x18070bc51  mov     qword ptr [rbp+160h+var_1C0], rax
0x18070bc55  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18070bc5c  mov     [rbp+160h+var_1D0], rdx
0x18070bc60  mov     rdx, rcx; struct IUri *
0x18070bc63  mov     [rsp+260h+var_208], r8
0x18070bc68  xor     r8d, r8d; enum __MIDL_IUri_0001
0x18070bc6b  mov     [rbp+160h+var_1E0], rcx
0x18070bc6f  lea     rcx, [rbp+160h+var_1A0]; this
0x18070bc73  mov     [rbp+160h+var_1A0], rax
0x18070bc77  mov     [rsp+260h+var_1F8], r9
0x18070bc7c  mov     qword ptr [rsp+260h+dwProcessId], rdi
0x18070bc81  mov     [rbp+160h+var_198], 0
0x18070bc89  mov     [rbp+160h+var_190], 0Bh
0x18070bc90  movdqu  xmmword ptr [rbp+160h+var_188], xmm0
0x18070bc95  mov     [rbp+160h+var_178], 0
0x18070bc9c  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x18070bca1  mov     ebx, eax
0x18070bca3  test    eax, eax
0x18070bca5  jnz     loc_18070C482
0x18070bcab  mov     rdx, [rsi+78h]
0x18070bcaf  lea     r8d, [rax+1]
0x18070bcb3  test    rdx, rdx
0x18070bcb6  jz      short loc_18070BCCF
0x18070bcb8  mov     rax, [rdx+68h]
0x18070bcbc  mov     ecx, [rax+2F4h]
0x18070bcc2  shr     ecx, 8
0x18070bcc5  test    r8b, cl
0x18070bcc8  jz      short loc_18070BCCF
0x18070bcca  mov     r12b, r8b
0x18070bccd  jmp     short loc_18070BCD2
0x18070bccf  xor     r12b, r12b
0x18070bcd2  mov     rcx, [rbp+160h+arg_28]
0x18070bcd9  mov     r15, rcx
0x18070bcdc  and     r15d, 0C400000h
0x18070bce3  setz    [rsp+260h+var_20F]
0x18070bce8  test    rdx, rdx
0x18070bceb  jz      short loc_18070BD04
0x18070bced  test    [rdx+0E2h], r8b
0x18070bcf4  jz      short loc_18070BD04
0x18070bcf6  test    byte ptr [rdx+0DFh], 20h
0x18070bcfd  jz      short loc_18070BD04
0x18070bcff  mov     al, r8b
0x18070bd02  jmp     short loc_18070BD06
0x18070bd04  xor     al, al
0x18070bd06  test    rcx, 21000h
0x18070bd0d  jnz     short loc_18070BD18
0x18070bd0f  test    al, al
0x18070bd11  jnz     short loc_18070BD18
0x18070bd13  mov     r14b, r8b
0x18070bd16  jmp     short loc_18070BD1B
0x18070bd18  xor     r14b, r14b
0x18070bd1b  cmp     [rbp+160h+arg_58], 0
0x18070bd22  mov     [rsp+260h+var_210], 0
0x18070bd27  jz      short loc_18070BD2E
0x18070bd29  xor     dil, dil
0x18070bd2c  jmp     short loc_18070BD39
0x18070bd2e  test    byte ptr [rdi+0B4h], 80h
0x18070bd35  setnz   dil
0x18070bd39  mov     r13b, [rbp+160h+arg_60]
0x18070bd40  xor     eax, eax
0x18070bd42  mov     [rbp+160h+var_1D8], eax
0x18070bd45  mov     [rbp+160h+var_1D4], al
0x18070bd48  mov     al, [rbp+160h+arg_68]
0x18070bd4e  mov     byte ptr [rbp+160h+var_1D8+2], al
0x18070bd51  test    dil, dil
0x18070bd54  jz      short loc_18070BD5B
0x18070bd56  mov     ebx, r8d
0x18070bd59  jmp     short loc_18070BD6F
0x18070bd5b  mov     rcx, [rbp+160h+var_188+8]
0x18070bd5f  lea     rdx, [rbp+160h+var_1D8]
0x18070bd63  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x18070bd69  mov     ebx, eax
0x18070bd6b  test    eax, eax
0x18070bd6d  jz      short loc_18070BDD8
0x18070bd6f  test    r12b, r12b
0x18070bd72  jnz     loc_18070C482
0x18070bd78  test    dil, dil
0x18070bd7b  jnz     short loc_18070BDD0
0x18070bd7d  test    r13b, r13b
0x18070bd80  jz      short loc_18070BDD0
0x18070bd82  test    r15, r15
0x18070bd85  jnz     short loc_18070BDD0
0x18070bd87  test    r14b, r14b
0x18070bd8a  jz      short loc_18070BDD0
0x18070bd8c  mov     rdi, [rbp+160h+arg_28]
0x18070bd93  bt      rdi, 1Fh
0x18070bd98  jb      short loc_18070BDD0
0x18070bd9a  mov     rdx, [rsi+78h]
0x18070bd9e  test    rdx, rdx
0x18070bda1  jz      short loc_18070BDD0
0x18070bda3  mov     rcx, rdx; this
0x18070bda6  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18070bdab  test    rax, rax
0x18070bdae  jz      short loc_18070BDD0
0x18070bdb0  mov     rcx, rdx; this
0x18070bdb3  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18070bdb8  mov     rcx, rax
0x18070bdbb  mov     edx, 7FB8FFF1h
0x18070bdc0  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x18070bdc5  test    eax, eax
0x18070bdc7  jnz     short loc_18070BDD0
0x18070bdc9  mov     [rsp+260h+var_210], 1
0x18070bdce  jmp     short loc_18070BDE8
0x18070bdd0  test    ebx, ebx
0x18070bdd2  jnz     loc_18070C482
0x18070bdd8  test    r12b, r12b
0x18070bddb  jnz     loc_18070C482
0x18070bde1  mov     rdi, [rbp+160h+arg_28]
0x18070bde8  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x18070bdee  mov     r12, [rbp+160h+var_1E0]
0x18070bdf2  test    eax, eax
0x18070bdf4  jnz     short loc_18070BE27
0x18070bdf6  mov     [rsp+260h+var_200], eax
0x18070bdfa  lea     rdx, [rsp+260h+var_200]
0x18070bdff  mov     rax, [r12]
0x18070be03  mov     rcx, r12
0x18070be06  mov     rax, [rax+0C0h]
0x18070be0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18070be12  mov     ebx, eax
0x18070be14  test    eax, eax
0x18070be16  js      short loc_18070BE52
0x18070be18  cmp     [rsp+260h+var_200], 0Ah
0x18070be1d  jz      short loc_18070BE52
0x18070be1f  test    eax, eax
0x18070be21  jnz     loc_18070C482
0x18070be27  mov     r14b, [rbp+160h+arg_50]
0x18070be2e  mov     [rbp+160h+var_1E0], 0
0x18070be36  mov     [rbp+160h+bstrString], 0
0x18070be3e  test    r14b, r14b
0x18070be41  jz      short loc_18070BE5C
0x18070be43  test    r13b, r13b
0x18070be46  jnz     short loc_18070BE5C
0x18070be48  mov     ebx, 80070005h
0x18070be4d  jmp     loc_18070C466
0x18070be52  mov     ebx, 1
0x18070be57  jmp     loc_18070C482
0x18070be5c  mov     rax, [r12]
0x18070be60  lea     rdx, [rbp+160h+var_1E0]
0x18070be64  mov     rcx, r12
0x18070be67  mov     rax, [rax+38h]
0x18070be6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18070be70  mov     ebx, eax
0x18070be72  test    eax, eax
0x18070be74  js      loc_18070C466
0x18070be7a  mov     rcx, [rbp+160h+var_1D0]
0x18070be7e  lea     rdx, [rbp+160h+bstrString]
0x18070be82  mov     rax, [rcx]
0x18070be85  mov     rax, [rax+38h]
0x18070be89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18070be8e  mov     ebx, eax
0x18070be90  test    eax, eax
0x18070be92  js      loc_18070C466
0x18070be98  xor     edx, edx; Val
0x18070be9a  lea     rcx, [rbp+160h+var_170]; void *
0x18070be9e  mov     r8d, 90h; Size
0x18070bea4  call    memset_0
0x18070bea9  lea     rcx, [rbp+160h+pvarg]; pvarg
0x18070bead  call    cs:__imp_VariantInit
0x18070beb3  mov     r13, [rsp+260h+var_1F0]
0x18070beb8  lea     rax, [rbp+160h+var_170]
0x18070bebc  mov     r8, qword ptr [rsp+260h+dwProcessId]; struct CDwnBindInfo *
0x18070bec1  mov     r9, rsi; struct COmWindowProxy *
0x18070bec4  mov     rdx, [rbp+160h+bstrString]; unsigned __int16 *
0x18070bec8  mov     rcx, [rbp+160h+var_1E0]; unsigned __int16 *
0x18070becc  mov     [rsp+260h+var_220], rax; struct _BROKER_BIND_INFO *
0x18070bed1  mov     rax, [rsp+260h+var_1F8]
0x18070bed6  mov     [rsp+260h+var_228], r13; unsigned __int16 *
0x18070bedb  mov     [rsp+260h+var_230], rax; unsigned __int16 *
0x18070bee0  mov     rax, [rsp+260h+var_208]
0x18070bee5  mov     [rsp+260h+var_238], rax; unsigned __int16 *
0x18070beea  mov     [rsp+260h+var_240], rdi; unsigned __int64
0x18070beef  call    ?SetBrokerBindInfoForRedirectToBroker@@YAJPEBG0PEAVCDwnBindInfo@@PEAVCOmWindowProxy@@_K000PEAU_BROKER_BIND_INFO@@@Z; SetBrokerBindInfoForRedirectToBroker(ushort const *,ushort const *,CDwnBindInfo *,COmWindowProxy *,unsigned __int64,ushort const *,ushort const *,ushort const *,_BROKER_BIND_INFO *)
0x18070bef4  mov     ebx, eax
0x18070bef6  test    eax, eax
0x18070bef8  js      loc_18070C45D
0x18070befe  mov     dl, [rsp+260h+var_20F]; bool
0x18070bf02  mov     rcx, rdi; unsigned __int64
0x18070bf05  mov     [rsp+260h+var_200], 0
0x18070bf0d  call    ?Convert_FHL_To_Nav@@YAK_K_N@Z; Convert_FHL_To_Nav(unsigned __int64,bool)
0x18070bf12  mov     rcx, [rsi+78h]; this
0x18070bf16  mov     ebx, eax
0x18070bf18  bts     ebx, 1Eh
0x18070bf1c  cmp     [rbp+160h+arg_68], 0
0x18070bf23  cmovz   ebx, eax
0x18070bf26  test    rcx, rcx
0x18070bf29  jz      short loc_18070BF7F
0x18070bf2b  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18070bf30  mov     rdi, rax
0x18070bf33  test    rax, rax
0x18070bf36  jz      short loc_18070BF78
0x18070bf38  test    r15, r15
0x18070bf3b  jnz     short loc_18070BF55
0x18070bf3d  movzx   r12d, [rsp+260h+var_210]
0x18070bf43  lea     r8, [rsp+260h+var_200]; unsigned int *
0x18070bf48  mov     edx, r12d; int
0x18070bf4b  mov     rcx, rax; this
0x18070bf4e  call    ?PrepTravelLogForVirtualTabSwitch@CDoc@@QEAAJHPEAK@Z; CDoc::PrepTravelLogForVirtualTabSwitch(int,ulong *)
0x18070bf53  jmp     short loc_18070BF5A
0x18070bf55  mov     r12b, [rsp+260h+var_210]
0x18070bf5a  mov     edx, 3038E7F1h
0x18070bf5f  mov     rcx, rdi
0x18070bf62  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x18070bf67  mov     rdi, [rbp+160h+arg_28]
0x18070bf6e  test    eax, eax
0x18070bf70  jnz     short loc_18070BF84
0x18070bf72  bts     ebx, 12h
0x18070bf76  jmp     short loc_18070BF84
0x18070bf78  mov     rdi, [rbp+160h+arg_28]
0x18070bf7f  mov     r12b, [rsp+260h+var_210]
0x18070bf84  xorps   xmm0, xmm0
0x18070bf87  mov     [rbp+160h+var_DC], ebx
0x18070bf8d  xor     ebx, ebx
0x18070bf8f  mov     [rbp+160h+var_E0], 0
0x18070bf99  movups  xmmword ptr [rbp+160h+var_B8], xmm0
0x18070bfa0  mov     [rbp+160h+var_D8], rbx
0x18070bfa7  mov     [rbp+160h+var_D0], rbx
0x18070bfae  movups  xmmword ptr [rbp+160h+var_B8+0Ch], xmm0
0x18070bfb5  movups  [rbp+160h+var_C8], xmm0
0x18070bfbc  call    cs:__imp_GetCurrentProcessId
0x18070bfc2  lea     ecx, [rbx+1]
0x18070bfc5  mov     dword ptr [rbp+160h+var_C8], eax
0x18070bfcb  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18070bfd1  mov     ecx, 20000011h
0x18070bfd6  mov     dword ptr [rbp+160h+var_C8+8], ebx
0x18070bfdc  and     eax, 7Fh
0x18070bfdf  mov     dword ptr [rbp+160h+var_C8+4], eax
0x18070bfe5  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18070bfeb  mov     [rbp+160h+var_B8], eax
0x18070bff1  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18070bff7  movups  xmm0, xmmword ptr [rax]
0x18070bffa  mov     eax, [rsp+260h+var_200]
0x18070bffe  mov     [rbp+160h+var_B8+8], eax
0x18070c004  mov     eax, [rbp+160h+arg_40]
0x18070c00a  movdqu  xmmword ptr [rbp+160h+var_B8+0Ch], xmm0
0x18070c012  test    eax, eax
0x18070c014  jnz     short loc_18070C035
0x18070c016  call    cs:__imp_GetCurrentThreadId
0x18070c01c  xor     r9d, r9d
0x18070c01f  lea     r8, [rbp+160h+var_E0]
0x18070c026  mov     edx, eax
0x18070c028  mov     ecx, 203h
0x18070c02d  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x18070c033  jmp     short loc_18070C03B
0x18070c035  mov     [rbp+160h+var_E0], eax
0x18070c03b  mov     rcx, qword ptr [rbp+160h+var_1C0]
0x18070c03f  mov     [rbp+160h+var_1D0], rbx
0x18070c043  test    rcx, rcx
0x18070c046  jz      short loc_18070C05E
0x18070c048  mov     rax, [rcx]
0x18070c04b  lea     r8, [rbp+160h+var_1D0]
0x18070c04f  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00
0x18070c056  mov     rax, [rax]
0x18070c059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18070c05e  test    r15, r15
0x18070c061  jnz     short loc_18070C093
0x18070c063  mov     rdx, [rsi+78h]
0x18070c067  test    rdx, rdx
0x18070c06a  jz      short loc_18070C093
0x18070c06c  mov     rcx, rdx; this
0x18070c06f  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18070c074  test    rax, rax
0x18070c077  jz      short loc_18070C093
0x18070c079  mov     rcx, rdx; this
0x18070c07c  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18070c081  lea     rcx, [rax+6A8h]; this
0x18070c088  call    ?RegisterVTabNavigate@CDeferredActionHandler@@QEAAKXZ; CDeferredActionHandler::RegisterVTabNavigate(void)
0x18070c08d  mov     [rbp+160h+var_B8+4], eax
0x18070c093  mov     rcx, [rsi+78h]; this
0x18070c097  test    rcx, rcx
0x18070c09a  jz      short loc_18070C10E
0x18070c09c  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18070c0a1  test    rax, rax
0x18070c0a4  jz      short loc_18070C10E
0x18070c0a6  xorps   xmm0, xmm0
0x18070c0a9  lea     rcx, [rbp+160h+var_1C0]; pvarg
0x18070c0ad  xor     eax, eax
0x18070c0af  movups  xmmword ptr [rbp+160h+var_1C0], xmm0
0x18070c0b3  mov     qword ptr [rbp+160h+var_1C0+10h], rax
0x18070c0b7  call    cs:__imp_VariantInit
0x18070c0bd  mov     rcx, [rsi+78h]; this
0x18070c0c1  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
  ... truncated ...
```
