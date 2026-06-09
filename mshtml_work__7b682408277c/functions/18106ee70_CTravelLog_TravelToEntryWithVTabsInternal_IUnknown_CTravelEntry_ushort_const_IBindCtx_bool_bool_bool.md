# CTravelLog::_TravelToEntryWithVTabsInternal(IUnknown *,CTravelEntry *,ushort const *,IBindCtx *,bool,bool,bool)

- ea: `0x18106ee70`
- end: `0x18106f47b`
- name: `?_TravelToEntryWithVTabsInternal@CTravelLog@@IEAAJPEAUIUnknown@@PEAVCTravelEntry@@PEBGPEAUIBindCtx@@_N44@Z`
- size: `1547`
- prototype: `__int64 __fastcall(CTravelLog *__hidden this, struct IUnknown *, struct CTravelEntry *, const unsigned __int16 *, struct IBindCtx *, bool, bool, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18106e854`

## callees

- `0x180013efc`
- `0x1800c5000`
- `0x180402a74`
- `0x1805e77e0`
- `0x18106a6a8`
- `0x18106e654`
- `0x18106ee70`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18106f1b0`
- `KERNEL32!GetCurrentProcessId` at `0x18106f1b0`
- `USER32!AllowSetForegroundWindow` at `0x18106f2c5`
- `USER32!AllowSetForegroundWindow` at `0x18106f2c5`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18106f280`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18106f280`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18106f1e1`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18106f1e1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18106f250`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18106f250`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18106f06e`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18106f06e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18106f1f3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18106f357`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18106f1f3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18106f357`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18106f1c4`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18106f1c4`
- `OLEAUT32!__imp_SysAllocString` at `0x18106f12c`
- `OLEAUT32!__imp_SysAllocString` at `0x18106f261`
- `OLEAUT32!__imp_SysAllocString` at `0x18106f12c`
- `OLEAUT32!__imp_SysAllocString` at `0x18106f261`
- `OLEAUT32!__imp_SysFreeString` at `0x18106f402`
- `OLEAUT32!__imp_SysFreeString` at `0x18106f412`
- `OLEAUT32!__imp_SysFreeString` at `0x18106f402`
- `OLEAUT32!__imp_SysFreeString` at `0x18106f412`
- `OLEAUT32!__imp_VariantInit` at `0x18106efe6`
- `OLEAUT32!__imp_VariantInit` at `0x18106f011`
- `OLEAUT32!__imp_VariantInit` at `0x18106f0e0`
- `OLEAUT32!__imp_VariantInit` at `0x18106efe6`
- `OLEAUT32!__imp_VariantInit` at `0x18106f011`
- `OLEAUT32!__imp_VariantInit` at `0x18106f0e0`
- `OLEAUT32!__imp_VariantClear` at `0x18106f0c3`
- `OLEAUT32!__imp_VariantClear` at `0x18106f140`
- `OLEAUT32!__imp_VariantClear` at `0x18106f0c3`
- `OLEAUT32!__imp_VariantClear` at `0x18106f140`

## pseudocode

```c
__int64 __fastcall CTravelLog::_TravelToEntryWithVTabsInternal(
        struct CTravelEntry **this,
        struct IUnknown *a2,
        struct CTravelEntry *a3,
        const unsigned __int16 *a4,
        struct IBindCtx *a5,
        bool a6,
        bool a7,
        bool a8)
{
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // rcx
  int v14; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  LONG lVal; // r15d
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v18; // rax
  int v19; // eax
  char v20; // bl
  struct CTravelEntry *v21; // rcx
  struct CTravelEntry *v22; // rcx
  OLECHAR *v23; // rax
  int v24; // ebx
  DWORD v25; // ecx
  void (__fastcall *v26)(__int64, _QWORD *); // rbx
  __int64 v28; // [rsp+48h] [rbp-C0h] BYREF
  DWORD dwProcessId[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-B0h] BYREF
  struct IEUserBroker *v31; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD psz[3]; // [rsp+70h] [rbp-98h] BYREF
  void *ppvOut; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v35; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v36; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-48h] BYREF
  BSTR bstrString[10]; // [rsp+D8h] [rbp-30h] BYREF
  BSTR v39; // [rsp+128h] [rbp+20h]
  _DWORD v40[3]; // [rsp+168h] [rbp+60h] BYREF
  __int64 v41; // [rsp+174h] [rbp+6Ch]
  int v42; // [rsp+17Ch] [rbp+74h]
  __int128 v43; // [rsp+180h] [rbp+78h]
  _DWORD v44[10]; // [rsp+190h] [rbp+88h] BYREF

  psz[1] = a4;
  Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
    "CTravelLog::_TravelToEntryWithVTabsInternal - STARTS TravelLog=0x%08lX",
    (_DWORD)this);
  if ( a2 )
  {
    if ( !*((_BYTE *)this + 160) )
      CTravelLog::_PrepTravelLogForVirtualTabSwitch((CTravelLog *)this, a2, a7);
    v11 = *((unsigned int *)this + 37);
    *((_BYTE *)this + 160) = 0;
    v32 = 0;
    if ( (_DWORD)v11 && (unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(v11, 0, 0, 0) )
    {
      v12 = -2147467263;
    }
    else
    {
      v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_d2649e5e_e1a3_4255_b764_d7531a794042,
              &v32);
      if ( v12 >= 0 )
      {
        v13 = v32;
        dwProcessId[0] = 0;
        if ( v32 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v32 + 24LL))(v32, dwProcessId);
          v13 = v32;
          v12 = v14;
        }
        if ( v12 >= 0 )
        {
          memset_0(bstrString, 0, 0x90u);
          lpVtbl = a2->lpVtbl;
          v28 = 0;
          lVal = 0;
          QueryInterface = lpVtbl->QueryInterface;
          v18 = TSmartPointer<ID3D11Device>::operator&(&v28);
          v19 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64))QueryInterface)(
                  a2,
                  &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
                  v18);
          v20 = 0;
          if ( v19 < 0 )
            goto LABEL_25;
          if ( *((_DWORD *)a3 + 20)
            && ((memset(&pvarg, 0, sizeof(pvarg)),
                 VariantInit(&pvarg),
                 pvarg.vt = 19,
                 pvarg.lVal = *((_DWORD *)a3 + 20),
                 memset(&v35, 0, sizeof(v35)),
                 VariantInit(&v35),
                 (*(int (__fastcall **)(__int64, GUID *, __int64, __int64, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v28 + 32LL))(
                   v28,
                   &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                   79,
                   0x4000,
                   &pvarg,
                   &v35) >= 0)
             || v35.vt == 3 && v35.lVal == -2147467260) )
          {
            v20 = 1;
          }
          else if ( LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
          {
            memset(&v35, 0, sizeof(v35));
            if ( (*(int (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v28 + 32LL))(
                   v28,
                   &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                   82) >= 0 )
              lVal = v35.lVal;
            VariantClear(&v35);
          }
          memset(&v36, 0, sizeof(v36));
          VariantInit(&v36);
          if ( (*(int (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v28 + 32LL))(v28, &CGID_Explorer, 120) >= 0
            && v36.vt == 8 )
          {
            v39 = SysAllocString(v36.bstrVal);
            VariantClear(&v36);
          }
          if ( !v20 )
          {
LABEL_25:
            if ( a8 )
            {
              v12 = -2147024809;
            }
            else
            {
              v21 = this[9];
              v40[0] = dwProcessId[0];
              v40[1] = (a6 << 18) + 0x4000;
              v40[2] = FindDistance(v21, a3);
              memset(v44, 0, 28);
              v41 = 0;
              v42 = 0;
              v43 = 0;
              LODWORD(v43) = GetCurrentProcessId();
              *(_QWORD *)((char *)&v43 + 4) = IsoGetIntegrity(1) & 0x7F;
              v44[0] = IEConfiguration_GetDWORD(536870929);
              *(_OWORD *)&v44[3] = *(_OWORD *)GlobalThreadState();
              if ( a7 )
              {
                v22 = this[9];
                if ( v22 )
                  v44[2] = (*(__int64 (__fastcall **)(struct CTravelEntry *))(*(_QWORD *)v22 + 240LL))(v22);
              }
              v44[1] = lVal;
              ppvOut = 0;
              IUnknown_QueryService(a2, &IID_IWebBrowserApp, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &ppvOut);
              v23 = SysAllocString((const OLECHAR *)psz[1]);
              v30 = 0;
              bstrString[0] = v23;
              v31 = 0;
              v24 = CoCreateUserBroker(&v31);
              if ( v24 >= 0 )
              {
                dwProcessId[1] = 0;
                (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v31 + 24LL))(
                  v31,
                  0,
                  0,
                  &dwProcessId[1]);
                v25 = -1;
                if ( dwProcessId[1] )
                  v25 = dwProcessId[1];
                AllowSetForegroundWindow(v25);
                psz[1] = 0;
                v24 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, _QWORD *))(*(_QWORD *)v31 + 48LL))(
                        v31,
                        &CLSID_CShdocvwBroker,
                        &IID_IUnknown,
                        &psz[1]);
                if ( v24 >= 0 )
                {
                  v24 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))psz[1])(
                          psz[1],
                          &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                          &v30);
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)psz[1] + 16LL))(psz[1]);
                }
                (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v31 + 16LL))(v31);
                if ( v24 >= 0 )
                {
                  v26 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v30 + 1256LL);
                  *(_OWORD *)&psz[1] = *(_OWORD *)GlobalThreadState();
                  v26(v30, &psz[1]);
                  v24 = (*(__int64 (__fastcall **)(__int64, BSTR *, _DWORD *, void *))(*(_QWORD *)v30 + 40LL))(
                          v30,
                          bstrString,
                          v40,
                          ppvOut);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                }
              }
              v12 = 0;
              if ( v24 != -2147467260 )
                v12 = v24;
              if ( lVal )
                (*(void (__fastcall **)(__int64, GUID *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v28 + 32LL))(
                  v28,
                  &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                  83,
                  0,
                  0,
                  0);
              if ( ppvOut )
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
            }
          }
          SysFreeString(bstrString[0]);
          SysFreeString(v39);
          TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v28);
          v13 = v32;
        }
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  else
  {
    v12 = -2147418113;
  }
  Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
    "CTravelLog::_TravelToEntryWithVTabsInternal - ENDS TravelLog=0x%08lX hr=0x%08lX",
    (_DWORD)this,
    v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18106ee70  mov     rax, rsp
0x18106ee73  mov     [rax+20h], r9
0x18106ee77  mov     [rax+18h], r8
0x18106ee7b  mov     [rax+10h], rdx
0x18106ee7f  mov     [rax+8], rcx
0x18106ee83  push    rbp
0x18106ee84  push    rbx
0x18106ee85  push    rsi
0x18106ee86  push    rdi
0x18106ee87  push    r13
0x18106ee89  push    r14
0x18106ee8b  push    r15
0x18106ee8d  lea     rbp, [rax-0F8h]
0x18106ee94  sub     rsp, 1C0h
0x18106ee9b  mov     rax, cs:__security_cookie
0x18106eea2  xor     rax, rsp
0x18106eea5  mov     [rbp+0F0h+var_40], rax
0x18106eeac  mov     rax, [rbp+0F0h+arg_18]
0x18106eeb3  lea     rcx, aCtravellogTrav_2; "CTravelLog::_TravelToEntryWithVTabsInte"...
0x18106eeba  mov     rsi, [rbp+0F0h+arg_0]
0x18106eec1  mov     r14, [rbp+0F0h+punk]
0x18106eec8  mov     rdx, rsi
0x18106eecb  mov     r13, [rbp+0F0h+arg_10]
0x18106eed2  mov     qword ptr [rsp+1F0h+psz+8], rax
0x18106eed7  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(...)
0x18106eedc  xor     ebx, ebx
0x18106eede  test    r14, r14
0x18106eee1  jz      loc_18106F440
0x18106eee7  cmp     [rsi+0A0h], bl
0x18106eeed  jnz     short loc_18106EF01
0x18106eeef  mov     r8b, [rbp+0F0h+arg_30]; bool
0x18106eef6  mov     rdx, r14; struct IUnknown *
0x18106eef9  mov     rcx, rsi; this
0x18106eefc  call    ?_PrepTravelLogForVirtualTabSwitch@CTravelLog@@IEAAJPEAUIUnknown@@_N@Z; CTravelLog::_PrepTravelLogForVirtualTabSwitch(IUnknown *,bool)
0x18106ef01  mov     ecx, [rsi+94h]
0x18106ef07  mov     [rsi+0A0h], bl
0x18106ef0d  mov     [rsp+1F0h+var_190], rbx
0x18106ef12  test    ecx, ecx
0x18106ef14  jz      short loc_18106EF31
0x18106ef16  xor     r9d, r9d
0x18106ef19  xor     r8d, r8d
0x18106ef1c  xor     edx, edx
0x18106ef1e  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x18106ef23  test    al, al
0x18106ef25  jz      short loc_18106EF31
0x18106ef27  mov     edi, 80004001h
0x18106ef2c  jmp     loc_18106F445
0x18106ef31  mov     rax, [r14]
0x18106ef34  lea     r8, [rsp+1F0h+var_190]
0x18106ef39  lea     rdx, _GUID_d2649e5e_e1a3_4255_b764_d7531a794042
0x18106ef40  mov     rcx, r14
0x18106ef43  mov     rax, [rax]
0x18106ef46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106ef4b  mov     edi, eax
0x18106ef4d  test    eax, eax
0x18106ef4f  js      loc_18106F445
0x18106ef55  mov     rcx, [rsp+1F0h+var_190]
0x18106ef5a  mov     [rsp+1F0h+dwProcessId], ebx
0x18106ef5e  test    rcx, rcx
0x18106ef61  jz      short loc_18106EF7B
0x18106ef63  mov     rax, [rcx]
0x18106ef66  lea     rdx, [rsp+1F0h+dwProcessId]
0x18106ef6b  mov     rax, [rax+18h]
0x18106ef6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106ef74  mov     rcx, [rsp+1F0h+var_190]
0x18106ef79  mov     edi, eax
0x18106ef7b  test    edi, edi
0x18106ef7d  js      loc_18106F42D
0x18106ef83  xor     edx, edx; Val
0x18106ef85  lea     rcx, [rbp+0F0h+bstrString]; void *
0x18106ef89  mov     r8d, 90h; Size
0x18106ef8f  call    memset_0
0x18106ef94  mov     rax, [r14]
0x18106ef97  lea     rcx, [rsp+1F0h+var_1B0]
0x18106ef9c  mov     qword ptr [rsp+1F0h+var_1B0], rbx
0x18106efa1  mov     r15d, ebx
0x18106efa4  mov     rbx, [rax]
0x18106efa7  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x18106efac  mov     r8, rax
0x18106efaf  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x18106efb6  mov     rax, rbx
0x18106efb9  mov     rcx, r14
0x18106efbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106efc1  xor     ebx, ebx
0x18106efc3  test    eax, eax
0x18106efc5  js      loc_18106F156
0x18106efcb  cmp     [r13+50h], ebx
0x18106efcf  jz      loc_18106F069
0x18106efd5  xorps   xmm0, xmm0
0x18106efd8  lea     rcx, [rbp+0F0h+pvarg]; pvarg
0x18106efdc  xor     eax, eax
0x18106efde  movups  xmmword ptr [rbp+0F0h+pvarg], xmm0
0x18106efe2  mov     qword ptr [rbp+0F0h+pvarg+10h], rax
0x18106efe6  call    cs:__imp_VariantInit
0x18106efed  nop     dword ptr [rax+rax+00h]
0x18106eff2  lea     eax, [rbx+13h]
0x18106eff5  xorps   xmm0, xmm0
0x18106eff8  mov     word ptr [rbp+0F0h+pvarg], ax
0x18106effc  lea     rcx, [rbp+0F0h+var_168]; pvarg
0x18106f000  mov     eax, [r13+50h]
0x18106f004  mov     dword ptr [rbp+0F0h+pvarg+8], eax
0x18106f007  xor     eax, eax
0x18106f009  mov     qword ptr [rbp+0F0h+var_168+10h], rax
0x18106f00d  movups  xmmword ptr [rbp+0F0h+var_168], xmm0
0x18106f011  call    cs:__imp_VariantInit
0x18106f018  nop     dword ptr [rax+rax+00h]
0x18106f01d  mov     rcx, qword ptr [rsp+1F0h+var_1B0]
0x18106f022  lea     rdx, [rbp+0F0h+var_168]
0x18106f026  mov     [rsp+28h], rdx
0x18106f02b  lea     r8d, [rbx+4Fh]
0x18106f02f  lea     rdx, [rbp+0F0h+pvarg]
0x18106f033  mov     r9d, 4000h
0x18106f039  mov     [rsp+1F0h+var_1D0], rdx
0x18106f03e  lea     rdx, _GUID_a11452bc_e055_4e56_a151_7b16dbb4544e
0x18106f045  mov     rax, [rcx]
0x18106f048  mov     rax, [rax+20h]
0x18106f04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f051  test    eax, eax
0x18106f053  jns     short loc_18106F065
0x18106f055  cmp     word ptr [rbp+0F0h+var_168], 3
0x18106f05a  jnz     short loc_18106F069
0x18106f05c  cmp     dword ptr [rbp+0F0h+var_168+8], 80004004h
0x18106f063  jnz     short loc_18106F069
0x18106f065  mov     bl, 1
0x18106f067  jmp     short loc_18106F0CF
0x18106f069  mov     ecx, 4
0x18106f06e  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x18106f075  nop     dword ptr [rax+rax+00h]
0x18106f07a  test    eax, eax
0x18106f07c  jz      short loc_18106F0CF
0x18106f07e  mov     rcx, qword ptr [rsp+1F0h+var_1B0]
0x18106f083  lea     rdx, [rbp+0F0h+var_168]
0x18106f087  xor     eax, eax
0x18106f089  mov     [rsp+28h], rdx
0x18106f08e  mov     qword ptr [rbp+0F0h+var_168+10h], rax
0x18106f092  lea     rdx, _GUID_a11452bc_e055_4e56_a151_7b16dbb4544e
0x18106f099  xorps   xmm0, xmm0
0x18106f09c  mov     [rsp+1F0h+var_1D0], rbx
0x18106f0a1  movups  xmmword ptr [rbp+0F0h+var_168], xmm0
0x18106f0a5  mov     rax, [rcx]
0x18106f0a8  xor     r9d, r9d
0x18106f0ab  mov     rax, [rax+20h]
0x18106f0af  lea     r8d, [r9+52h]
0x18106f0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f0b8  test    eax, eax
0x18106f0ba  lea     rcx, [rbp+0F0h+var_168]; pvarg
0x18106f0be  cmovns  r15d, dword ptr [rbp+0F0h+var_168+8]
0x18106f0c3  call    cs:__imp_VariantClear
0x18106f0ca  nop     dword ptr [rax+rax+00h]
0x18106f0cf  xorps   xmm0, xmm0
0x18106f0d2  lea     rcx, [rbp+0F0h+var_150]; pvarg
0x18106f0d6  xor     eax, eax
0x18106f0d8  movups  xmmword ptr [rbp+0F0h+var_150], xmm0
0x18106f0dc  mov     qword ptr [rbp+0F0h+var_150+10h], rax
0x18106f0e0  call    cs:__imp_VariantInit
0x18106f0e7  nop     dword ptr [rax+rax+00h]
0x18106f0ec  mov     rcx, qword ptr [rsp+1F0h+var_1B0]
0x18106f0f1  lea     rdx, [rbp+0F0h+var_150]
0x18106f0f5  mov     [rsp+28h], rdx
0x18106f0fa  xor     r9d, r9d
0x18106f0fd  lea     rdx, CGID_Explorer
0x18106f104  mov     [rsp+1F0h+var_1D0], 0
0x18106f10d  mov     rax, [rcx]
0x18106f110  lea     r8d, [r9+78h]
0x18106f114  mov     rax, [rax+20h]
0x18106f118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f11d  test    eax, eax
0x18106f11f  js      short loc_18106F14C
0x18106f121  cmp     word ptr [rbp+0F0h+var_150], 8
0x18106f126  jnz     short loc_18106F14C
0x18106f128  mov     rcx, qword ptr [rbp+0F0h+var_150+8]; psz
0x18106f12c  call    cs:__imp_SysAllocString
0x18106f133  nop     dword ptr [rax+rax+00h]
0x18106f138  lea     rcx, [rbp+0F0h+var_150]; pvarg
0x18106f13c  mov     [rbp+0F0h+var_D0], rax
0x18106f140  call    cs:__imp_VariantClear
0x18106f147  nop     dword ptr [rax+rax+00h]
0x18106f14c  test    bl, bl
0x18106f14e  jnz     loc_18106F3FE
0x18106f154  xor     ebx, ebx
0x18106f156  cmp     [rbp+0F0h+arg_38], bl
0x18106f15c  jz      short loc_18106F168
0x18106f15e  mov     edi, 80070057h
0x18106f163  jmp     loc_18106F3FE
0x18106f168  mov     eax, [rsp+1F0h+dwProcessId]
0x18106f16c  mov     rdx, r13; struct CTravelEntry *
0x18106f16f  mov     rcx, [rsi+48h]; struct CTravelEntry *
0x18106f173  mov     [rbp+0F0h+var_90], eax
0x18106f176  movzx   eax, [rbp+0F0h+arg_28]
0x18106f17d  shl     eax, 12h
0x18106f180  add     eax, 4000h
0x18106f185  mov     [rbp+0F0h+var_8C], eax
0x18106f188  call    ?FindDistance@@YAHPEAVCTravelEntry@@PEBV1@@Z; FindDistance(CTravelEntry *,CTravelEntry const *)
0x18106f18d  xorps   xmm0, xmm0
0x18106f190  mov     [rbp+0F0h+var_88], eax
0x18106f193  movups  xmmword ptr [rbp+0F0h+var_68], xmm0
0x18106f19a  mov     [rbp+0F0h+var_84], 0
0x18106f1a2  movups  xmmword ptr [rbp+0F0h+var_68+0Ch], xmm0
0x18106f1a9  mov     [rbp+0F0h+var_7C], ebx
0x18106f1ac  movups  [rbp+0F0h+var_78], xmm0
0x18106f1b0  call    cs:__imp_GetCurrentProcessId
0x18106f1b7  nop     dword ptr [rax+rax+00h]
0x18106f1bc  mov     ecx, 1
0x18106f1c1  mov     dword ptr [rbp+0F0h+var_78], eax
0x18106f1c4  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18106f1cb  nop     dword ptr [rax+rax+00h]
0x18106f1d0  mov     ecx, 20000011h
0x18106f1d5  mov     dword ptr [rbp+0F0h+var_78+8], ebx
0x18106f1db  and     eax, 7Fh
0x18106f1de  mov     dword ptr [rbp+0F0h+var_78+4], eax
0x18106f1e1  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18106f1e8  nop     dword ptr [rax+rax+00h]
0x18106f1ed  mov     [rbp+0F0h+var_68], eax
0x18106f1f3  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18106f1fa  nop     dword ptr [rax+rax+00h]
0x18106f1ff  movups  xmm0, xmmword ptr [rax]
0x18106f202  movdqu  xmmword ptr [rbp+0F0h+var_68+0Ch], xmm0
0x18106f20a  cmp     [rbp+0F0h+arg_30], bl
0x18106f210  jz      short loc_18106F230
0x18106f212  mov     rcx, [rsi+48h]
0x18106f216  test    rcx, rcx
0x18106f219  jz      short loc_18106F230
0x18106f21b  mov     rax, [rcx]
0x18106f21e  mov     rax, [rax+0F0h]
0x18106f225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f22a  mov     [rbp+0F0h+var_68+8], eax
0x18106f230  lea     r9, [rbp+0F0h+ppvOut]; ppvOut
0x18106f234  mov     [rbp+0F0h+var_68+4], r15d
0x18106f23b  lea     r8, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; riid
0x18106f242  mov     [rbp+0F0h+ppvOut], rbx
0x18106f246  lea     rdx, IID_IWebBrowserApp; guidService
0x18106f24d  mov     rcx, r14; punk
0x18106f250  call    cs:__imp_IUnknown_QueryService
0x18106f257  nop     dword ptr [rax+rax+00h]
0x18106f25c  mov     rcx, qword ptr [rsp+1F0h+psz+8]; psz
0x18106f261  call    cs:__imp_SysAllocString
0x18106f268  nop     dword ptr [rax+rax+00h]
0x18106f26d  lea     rcx, [rsp+1F0h+var_198]
0x18106f272  mov     [rsp+1F0h+var_1A0], rbx
0x18106f277  mov     [rbp+0F0h+bstrString], rax
0x18106f27b  mov     [rsp+1F0h+var_198], rbx
0x18106f280  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18106f287  nop     dword ptr [rax+rax+00h]
0x18106f28c  mov     ebx, eax
0x18106f28e  test    eax, eax
0x18106f290  js      loc_18106F3AE
0x18106f296  mov     rcx, [rsp+1F0h+var_198]
0x18106f29b  lea     r9, [rsp+1F0h+dwProcessId+4]
0x18106f2a0  mov     [rsp+1F0h+dwProcessId+4], 0
0x18106f2a8  xor     r8d, r8d
0x18106f2ab  xor     edx, edx
0x18106f2ad  mov     rax, [rcx]
0x18106f2b0  mov     rax, [rax+18h]
0x18106f2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f2b9  mov     eax, [rsp+1F0h+dwProcessId+4]
0x18106f2bd  or      ecx, 0FFFFFFFFh
0x18106f2c0  test    eax, eax
0x18106f2c2  cmovnz  ecx, eax; dwProcessId
0x18106f2c5  call    cs:__imp_AllowSetForegroundWindow
0x18106f2cc  nop     dword ptr [rax+rax+00h]
0x18106f2d1  mov     rcx, [rsp+1F0h+var_198]
0x18106f2d6  lea     r9, [rsp+1F0h+psz+8]
0x18106f2db  mov     qword ptr [rsp+1F0h+psz+8], 0
0x18106f2e4  lea     r8, IID_IUnknown
0x18106f2eb  lea     rdx, CLSID_CShdocvwBroker
0x18106f2f2  mov     rax, [rcx]
0x18106f2f5  mov     rax, [rax+30h]
0x18106f2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f2fe  mov     ebx, eax
0x18106f300  test    eax, eax
0x18106f302  js      short loc_18106F333
0x18106f304  mov     rcx, qword ptr [rsp+1F0h+psz+8]
0x18106f309  lea     r8, [rsp+1F0h+var_1A0]
0x18106f30e  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18106f315  mov     rax, [rcx]
0x18106f318  mov     rax, [rax]
0x18106f31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f320  mov     rcx, qword ptr [rsp+1F0h+psz+8]
0x18106f325  mov     ebx, eax
0x18106f327  mov     rax, [rcx]
0x18106f32a  mov     rax, [rax+10h]
0x18106f32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f333  mov     rcx, [rsp+1F0h+var_198]
0x18106f338  mov     rax, [rcx]
0x18106f33b  mov     rax, [rax+10h]
0x18106f33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f344  test    ebx, ebx
0x18106f346  js      short loc_18106F3AE
0x18106f348  mov     rax, [rsp+1F0h+var_1A0]
0x18106f34d  mov     rcx, [rax]
0x18106f350  mov     rbx, [rcx+4E8h]
0x18106f357  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18106f35e  nop     dword ptr [rax+rax+00h]
0x18106f363  mov     rcx, [rsp+1F0h+var_1A0]
0x18106f368  lea     rdx, [rsp+1F0h+psz+8]
0x18106f36d  movups  xmm0, xmmword ptr [rax]
0x18106f370  mov     rax, rbx
0x18106f373  movdqu  xmmword ptr [rsp+1F0h+psz+8], xmm0
0x18106f379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18106f37e  mov     rcx, [rsp+1F0h+var_1A0]
  ... truncated ...
```
