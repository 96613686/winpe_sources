# RedirectViaBrokerIfNeeded

- ea: `0x180712f74`
- end: `0x18071390f`
- name: `RedirectViaBrokerIfNeeded`
- size: `2459`
- prototype: `__int64 __fastcall(OLECHAR *, __int64, unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int64, int, unsigned __int16 *, int, struct COmWindowProxy *, bool, char, char, char, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180769e3c`

## callees

- `0x1803e41f0`
- `0x1803e7198`
- `0x1805f2dec`
- `0x1805f7f7c`
- `0x180712f74`
- `0x1807cc3bc`
- `0x1808cf80c`
- `0x1808d2154`
- `0x1808d26c0`
- `0x1808d3b80`
- `0x1808d3fb0`
- `0x1808f9ce0`
- `0x1808faa5c`
- `0x18108c2f4`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180713342`
- `KERNEL32!GetCurrentProcessId` at `0x180713342`
- `KERNEL32!GetCurrentThreadId` at `0x1807133b4`
- `KERNEL32!GetCurrentThreadId` at `0x1807133b4`
- `USER32!AllowSetForegroundWindow` at `0x1807135d9`
- `USER32!AllowSetForegroundWindow` at `0x1807136fd`
- `USER32!AllowSetForegroundWindow` at `0x1807135d9`
- `USER32!AllowSetForegroundWindow` at `0x1807136fd`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180713162`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180713162`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180713594`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1807136b8`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180713594`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1807136b8`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180713377`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180713377`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1807134ce`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1807134ce`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1807133d1`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1807133d1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180713389`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18071366c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180713793`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180713389`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18071366c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180713793`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180713357`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180713357`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x1807130d7`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x1807130d7`
- `OLEAUT32!__imp_SysAllocString` at `0x1807134ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1807134ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180713854`
- `OLEAUT32!__imp_SysFreeString` at `0x18071386c`
- `OLEAUT32!__imp_SysFreeString` at `0x1807138ad`
- `OLEAUT32!__imp_SysFreeString` at `0x180713854`
- `OLEAUT32!__imp_SysFreeString` at `0x18071386c`
- `OLEAUT32!__imp_SysFreeString` at `0x1807138ad`
- `OLEAUT32!__imp_VariantInit` at `0x18071322d`
- `OLEAUT32!__imp_VariantInit` at `0x180713465`
- `OLEAUT32!__imp_VariantInit` at `0x18071322d`
- `OLEAUT32!__imp_VariantInit` at `0x180713465`
- `OLEAUT32!__imp_VariantClear` at `0x1807134c2`
- `OLEAUT32!__imp_VariantClear` at `0x1807134c2`

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
0x180712f74  push    rbp
0x180712f76  push    rbx
0x180712f77  push    rsi
0x180712f78  push    rdi
0x180712f79  push    r12
0x180712f7b  push    r13
0x180712f7d  push    r14
0x180712f7f  push    r15
0x180712f81  lea     rbp, [rsp-128h]
0x180712f89  sub     rsp, 228h
0x180712f90  mov     rax, cs:__security_cookie
0x180712f97  xor     rax, rsp
0x180712f9a  mov     [rbp+160h+var_50], rax
0x180712fa1  mov     rax, [rbp+160h+arg_38]
0x180712fa8  xorps   xmm0, xmm0
0x180712fab  mov     rdi, [rbp+160h+arg_20]
0x180712fb2  mov     rsi, [rbp+160h+arg_48]
0x180712fb9  mov     [rsp+260h+var_1F0], rax
0x180712fbe  mov     rax, [rbp+160h+arg_70]
0x180712fc5  mov     qword ptr [rbp+160h+var_1C0], rax
0x180712fc9  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180712fd0  mov     [rbp+160h+var_1D0], rdx
0x180712fd4  mov     rdx, rcx; struct IUri *
0x180712fd7  mov     [rsp+260h+var_208], r8
0x180712fdc  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180712fdf  mov     [rbp+160h+var_1E0], rcx
0x180712fe3  lea     rcx, [rbp+160h+var_1A0]; this
0x180712fe7  mov     [rbp+160h+var_1A0], rax
0x180712feb  mov     [rsp+260h+var_1F8], r9
0x180712ff0  mov     qword ptr [rsp+260h+dwProcessId], rdi
0x180712ff5  mov     [rbp+160h+var_198], 0
0x180712ffd  mov     [rbp+160h+var_190], 0Bh
0x180713004  movdqu  xmmword ptr [rbp+160h+var_188], xmm0
0x180713009  mov     [rbp+160h+var_178], 0
0x180713010  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180713015  mov     ebx, eax
0x180713017  test    eax, eax
0x180713019  jnz     loc_180713878
0x18071301f  mov     rdx, [rsi+78h]
0x180713023  lea     r8d, [rax+1]
0x180713027  test    rdx, rdx
0x18071302a  jz      short loc_180713043
0x18071302c  mov     rax, [rdx+68h]
0x180713030  mov     ecx, [rax+2F4h]
0x180713036  shr     ecx, 8
0x180713039  test    r8b, cl
0x18071303c  jz      short loc_180713043
0x18071303e  mov     r12b, r8b
0x180713041  jmp     short loc_180713046
0x180713043  xor     r12b, r12b
0x180713046  mov     rcx, [rbp+160h+arg_28]
0x18071304d  mov     r15, rcx
0x180713050  and     r15d, 0C400000h
0x180713057  setz    [rsp+260h+var_20F]
0x18071305c  test    rdx, rdx
0x18071305f  jz      short loc_180713078
0x180713061  test    [rdx+0E2h], r8b
0x180713068  jz      short loc_180713078
0x18071306a  test    byte ptr [rdx+0DFh], 20h
0x180713071  jz      short loc_180713078
0x180713073  mov     al, r8b
0x180713076  jmp     short loc_18071307A
0x180713078  xor     al, al
0x18071307a  test    rcx, 21000h
0x180713081  jnz     short loc_18071308C
0x180713083  test    al, al
0x180713085  jnz     short loc_18071308C
0x180713087  mov     r14b, r8b
0x18071308a  jmp     short loc_18071308F
0x18071308c  xor     r14b, r14b
0x18071308f  cmp     [rbp+160h+arg_58], 0
0x180713096  mov     [rsp+260h+var_210], 0
0x18071309b  jz      short loc_1807130A2
0x18071309d  xor     dil, dil
0x1807130a0  jmp     short loc_1807130AD
0x1807130a2  test    byte ptr [rdi+0B4h], 80h
0x1807130a9  setnz   dil
0x1807130ad  mov     r13b, [rbp+160h+arg_60]
0x1807130b4  xor     eax, eax
0x1807130b6  mov     [rbp+160h+var_1D8], eax
0x1807130b9  mov     [rbp+160h+var_1D4], al
0x1807130bc  mov     al, [rbp+160h+arg_68]
0x1807130c2  mov     byte ptr [rbp+160h+var_1D8+2], al
0x1807130c5  test    dil, dil
0x1807130c8  jz      short loc_1807130CF
0x1807130ca  mov     ebx, r8d
0x1807130cd  jmp     short loc_1807130E9
0x1807130cf  mov     rcx, [rbp+160h+var_188+8]
0x1807130d3  lea     rdx, [rbp+160h+var_1D8]
0x1807130d7  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x1807130de  nop     dword ptr [rax+rax+00h]
0x1807130e3  mov     ebx, eax
0x1807130e5  test    eax, eax
0x1807130e7  jz      short loc_180713152
0x1807130e9  test    r12b, r12b
0x1807130ec  jnz     loc_180713878
0x1807130f2  test    dil, dil
0x1807130f5  jnz     short loc_18071314A
0x1807130f7  test    r13b, r13b
0x1807130fa  jz      short loc_18071314A
0x1807130fc  test    r15, r15
0x1807130ff  jnz     short loc_18071314A
0x180713101  test    r14b, r14b
0x180713104  jz      short loc_18071314A
0x180713106  mov     rdi, [rbp+160h+arg_28]
0x18071310d  bt      rdi, 1Fh
0x180713112  jb      short loc_18071314A
0x180713114  mov     rdx, [rsi+78h]
0x180713118  test    rdx, rdx
0x18071311b  jz      short loc_18071314A
0x18071311d  mov     rcx, rdx; this
0x180713120  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x180713125  test    rax, rax
0x180713128  jz      short loc_18071314A
0x18071312a  mov     rcx, rdx; this
0x18071312d  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x180713132  mov     rcx, rax
0x180713135  mov     edx, 7FB8FFF1h
0x18071313a  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x18071313f  test    eax, eax
0x180713141  jnz     short loc_18071314A
0x180713143  mov     [rsp+260h+var_210], 1
0x180713148  jmp     short loc_180713162
0x18071314a  test    ebx, ebx
0x18071314c  jnz     loc_180713878
0x180713152  test    r12b, r12b
0x180713155  jnz     loc_180713878
0x18071315b  mov     rdi, [rbp+160h+arg_28]
0x180713162  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x180713169  nop     dword ptr [rax+rax+00h]
0x18071316e  mov     r12, [rbp+160h+var_1E0]
0x180713172  test    eax, eax
0x180713174  jnz     short loc_1807131A7
0x180713176  mov     [rsp+260h+var_200], eax
0x18071317a  lea     rdx, [rsp+260h+var_200]
0x18071317f  mov     rax, [r12]
0x180713183  mov     rcx, r12
0x180713186  mov     rax, [rax+0C0h]
0x18071318d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180713192  mov     ebx, eax
0x180713194  test    eax, eax
0x180713196  js      short loc_1807131D2
0x180713198  cmp     [rsp+260h+var_200], 0Ah
0x18071319d  jz      short loc_1807131D2
0x18071319f  test    eax, eax
0x1807131a1  jnz     loc_180713878
0x1807131a7  mov     r14b, [rbp+160h+arg_50]
0x1807131ae  mov     [rbp+160h+var_1E0], 0
0x1807131b6  mov     [rbp+160h+bstrString], 0
0x1807131be  test    r14b, r14b
0x1807131c1  jz      short loc_1807131DC
0x1807131c3  test    r13b, r13b
0x1807131c6  jnz     short loc_1807131DC
0x1807131c8  mov     ebx, 80070005h
0x1807131cd  jmp     loc_180713850
0x1807131d2  mov     ebx, 1
0x1807131d7  jmp     loc_180713878
0x1807131dc  mov     rax, [r12]
0x1807131e0  lea     rdx, [rbp+160h+var_1E0]
0x1807131e4  mov     rcx, r12
0x1807131e7  mov     rax, [rax+38h]
0x1807131eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807131f0  mov     ebx, eax
0x1807131f2  test    eax, eax
0x1807131f4  js      loc_180713850
0x1807131fa  mov     rcx, [rbp+160h+var_1D0]
0x1807131fe  lea     rdx, [rbp+160h+bstrString]
0x180713202  mov     rax, [rcx]
0x180713205  mov     rax, [rax+38h]
0x180713209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18071320e  mov     ebx, eax
0x180713210  test    eax, eax
0x180713212  js      loc_180713850
0x180713218  xor     edx, edx; Val
0x18071321a  lea     rcx, [rbp+160h+var_170]; void *
0x18071321e  mov     r8d, 90h; Size
0x180713224  call    memset_0
0x180713229  lea     rcx, [rbp+160h+pvarg]; pvarg
0x18071322d  call    cs:__imp_VariantInit
0x180713234  nop     dword ptr [rax+rax+00h]
0x180713239  mov     r13, [rsp+260h+var_1F0]
0x18071323e  lea     rax, [rbp+160h+var_170]
0x180713242  mov     r8, qword ptr [rsp+260h+dwProcessId]; struct CDwnBindInfo *
0x180713247  mov     r9, rsi; struct COmWindowProxy *
0x18071324a  mov     rdx, [rbp+160h+bstrString]; unsigned __int16 *
0x18071324e  mov     rcx, [rbp+160h+var_1E0]; unsigned __int16 *
0x180713252  mov     [rsp+260h+var_220], rax; struct _BROKER_BIND_INFO *
0x180713257  mov     rax, [rsp+260h+var_1F8]
0x18071325c  mov     [rsp+260h+var_228], r13; unsigned __int16 *
0x180713261  mov     [rsp+260h+var_230], rax; unsigned __int16 *
0x180713266  mov     rax, [rsp+260h+var_208]
0x18071326b  mov     [rsp+260h+var_238], rax; unsigned __int16 *
0x180713270  mov     [rsp+260h+var_240], rdi; unsigned __int64
0x180713275  call    ?SetBrokerBindInfoForRedirectToBroker@@YAJPEBG0PEAVCDwnBindInfo@@PEAVCOmWindowProxy@@_K000PEAU_BROKER_BIND_INFO@@@Z; SetBrokerBindInfoForRedirectToBroker(ushort const *,ushort const *,CDwnBindInfo *,COmWindowProxy *,unsigned __int64,ushort const *,ushort const *,ushort const *,_BROKER_BIND_INFO *)
0x18071327a  mov     ebx, eax
0x18071327c  test    eax, eax
0x18071327e  js      loc_180713847
0x180713284  mov     dl, [rsp+260h+var_20F]; bool
0x180713288  mov     rcx, rdi; unsigned __int64
0x18071328b  mov     [rsp+260h+var_200], 0
0x180713293  call    ?Convert_FHL_To_Nav@@YAK_K_N@Z; Convert_FHL_To_Nav(unsigned __int64,bool)
0x180713298  mov     rcx, [rsi+78h]; this
0x18071329c  mov     ebx, eax
0x18071329e  bts     ebx, 1Eh
0x1807132a2  cmp     [rbp+160h+arg_68], 0
0x1807132a9  cmovz   ebx, eax
0x1807132ac  test    rcx, rcx
0x1807132af  jz      short loc_180713305
0x1807132b1  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1807132b6  mov     rdi, rax
0x1807132b9  test    rax, rax
0x1807132bc  jz      short loc_1807132FE
0x1807132be  test    r15, r15
0x1807132c1  jnz     short loc_1807132DB
0x1807132c3  movzx   r12d, [rsp+260h+var_210]
0x1807132c9  lea     r8, [rsp+260h+var_200]; unsigned int *
0x1807132ce  mov     edx, r12d; int
0x1807132d1  mov     rcx, rax; this
0x1807132d4  call    ?PrepTravelLogForVirtualTabSwitch@CDoc@@QEAAJHPEAK@Z; CDoc::PrepTravelLogForVirtualTabSwitch(int,ulong *)
0x1807132d9  jmp     short loc_1807132E0
0x1807132db  mov     r12b, [rsp+260h+var_210]
0x1807132e0  mov     edx, 3038E7F1h
0x1807132e5  mov     rcx, rdi
0x1807132e8  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x1807132ed  mov     rdi, [rbp+160h+arg_28]
0x1807132f4  test    eax, eax
0x1807132f6  jnz     short loc_18071330A
0x1807132f8  bts     ebx, 12h
0x1807132fc  jmp     short loc_18071330A
0x1807132fe  mov     rdi, [rbp+160h+arg_28]
0x180713305  mov     r12b, [rsp+260h+var_210]
0x18071330a  xorps   xmm0, xmm0
0x18071330d  mov     [rbp+160h+var_DC], ebx
0x180713313  xor     ebx, ebx
0x180713315  mov     [rbp+160h+var_E0], 0
0x18071331f  movups  xmmword ptr [rbp+160h+var_B8], xmm0
0x180713326  mov     [rbp+160h+var_D8], rbx
0x18071332d  mov     [rbp+160h+var_D0], rbx
0x180713334  movups  xmmword ptr [rbp+160h+var_B8+0Ch], xmm0
0x18071333b  movups  [rbp+160h+var_C8], xmm0
0x180713342  call    cs:__imp_GetCurrentProcessId
0x180713349  nop     dword ptr [rax+rax+00h]
0x18071334e  lea     ecx, [rbx+1]
0x180713351  mov     dword ptr [rbp+160h+var_C8], eax
0x180713357  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18071335e  nop     dword ptr [rax+rax+00h]
0x180713363  mov     ecx, 20000011h
0x180713368  mov     dword ptr [rbp+160h+var_C8+8], ebx
0x18071336e  and     eax, 7Fh
0x180713371  mov     dword ptr [rbp+160h+var_C8+4], eax
0x180713377  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18071337e  nop     dword ptr [rax+rax+00h]
0x180713383  mov     [rbp+160h+var_B8], eax
0x180713389  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180713390  nop     dword ptr [rax+rax+00h]
0x180713395  movups  xmm0, xmmword ptr [rax]
0x180713398  mov     eax, [rsp+260h+var_200]
0x18071339c  mov     [rbp+160h+var_B8+8], eax
0x1807133a2  mov     eax, [rbp+160h+arg_40]
0x1807133a8  movdqu  xmmword ptr [rbp+160h+var_B8+0Ch], xmm0
0x1807133b0  test    eax, eax
0x1807133b2  jnz     short loc_1807133DF
0x1807133b4  call    cs:__imp_GetCurrentThreadId
0x1807133bb  nop     dword ptr [rax+rax+00h]
0x1807133c0  xor     r9d, r9d
0x1807133c3  lea     r8, [rbp+160h+var_E0]
0x1807133ca  mov     edx, eax
0x1807133cc  mov     ecx, 203h
0x1807133d1  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1807133d8  nop     dword ptr [rax+rax+00h]
0x1807133dd  jmp     short loc_1807133E5
0x1807133df  mov     [rbp+160h+var_E0], eax
0x1807133e5  mov     rcx, qword ptr [rbp+160h+var_1C0]
0x1807133e9  mov     [rbp+160h+var_1D0], rbx
0x1807133ed  test    rcx, rcx
0x1807133f0  jz      short loc_180713408
0x1807133f2  mov     rax, [rcx]
0x1807133f5  lea     r8, [rbp+160h+var_1D0]
0x1807133f9  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00
0x180713400  mov     rax, [rax]
0x180713403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180713408  test    r15, r15
0x18071340b  jnz     short loc_18071343D
0x18071340d  mov     rdx, [rsi+78h]
0x180713411  test    rdx, rdx
0x180713414  jz      short loc_18071343D
0x180713416  mov     rcx, rdx; this
0x180713419  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18071341e  test    rax, rax
0x180713421  jz      short loc_18071343D
0x180713423  mov     rcx, rdx; this
0x180713426  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18071342b  lea     rcx, [rax+6A8h]; this
0x180713432  call    ?RegisterVTabNavigate@CDeferredActionHandler@@QEAAKXZ; CDeferredActionHandler::RegisterVTabNavigate(void)
0x180713437  mov     [rbp+160h+var_B8+4], eax
0x18071343d  mov     rcx, [rsi+78h]; this
0x180713441  test    rcx, rcx
0x180713444  jz      loc_1807134CE
0x18071344a  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18071344f  test    rax, rax
  ... truncated ...
```
