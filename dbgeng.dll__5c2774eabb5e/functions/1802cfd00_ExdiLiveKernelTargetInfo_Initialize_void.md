# ExdiLiveKernelTargetInfo::Initialize(void)

- ea: `0x1802cfd00`
- end: `0x1802d0610`
- name: `?Initialize@ExdiLiveKernelTargetInfo@@UEAAJXZ`
- size: `2320`
- prototype: `__int64 __fastcall(ExdiLiveKernelTargetInfo *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000191c`
- `0x180071a60`
- `0x180075988`
- `0x180075b88`
- `0x1800793cc`
- `0x18007fc7c`
- `0x18008e130`
- `0x18009497c`
- `0x1800ae5a8`
- `0x1800b94c4`
- `0x1800c1150`
- `0x1800c12b8`
- `0x1800c3810`
- `0x1800f0f40`
- `0x1801e2bbc`
- `0x1802c410c`
- `0x1802c70d8`
- `0x1802caaa8`
- `0x1802cfd00`
- `0x1802d0780`
- `0x1802d42a0`
- `0x1802d5784`
- `0x18036d008`
- `0x18038605c`
- `0x18041688c`
- `0x18041ae64`
- `0x18041af04`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802d052f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802d052f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802d03fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802d03fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d0410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d0427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d0410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d0427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802d04c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802d04c8`

## string_xrefs

- `0x1802cfec8`: `HandleInprocServerTasksFailed`
- `0x1802cfedf`: `EXDI WARNING! The /Inproc option is not compatible with connecting remote clients.\n`
- `0x1802cff22`: `EXDI: CoCreateInstance() returned 0x%08X\n`
- `0x1802cfeeb`: `              Consider removing it if you encounter hangs or strange behavior.\n`
- `0x1802cff35`: `CreateCOMServerFailed`
- `0x1802cffcc`: `EXDI: Cannot create a server using factory. EXDI constructor arguments will be ignored.\n`
- `0x1802d00d3`: `WARNING: An old EXDIv1 server has been detected. Debugger will use the compatibility layer.\n`
- `0x1802d04ff`: `ELFBinComposition.dll`
- `0x1802d0521`: `PrepareServicesForHardwareDebugging`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ExdiLiveKernelTargetInfo::Initialize(ExdiLiveKernelTargetInfo *this)
{
  struct IDebugServiceManager *ServiceManager; // rbx
  unsigned int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const WCHAR *v8; // rdx
  __int64 v9; // rcx
  struct IUnknown *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  struct ExdiLiveKernelTargetInfo::IExdiServerContainer *Exdi1ToExdi3Adapter; // rdi
  __int64 v16; // rcx
  __int64 v17; // rdi
  int v18; // r14d
  int *v19; // rdi
  unsigned int v20; // eax
  GUID *v21; // rdi
  unsigned int v22; // eax
  int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v28; // r14
  struct ExtensionInfo *v29; // rax
  FARPROC ProcAddress; // rax
  __int64 v32; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C8h] BYREF
  struct IUnknown *v34; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B8h] BYREF
  int v36; // [rsp+58h] [rbp-B0h] BYREF
  int v37; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v38; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v39[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v40[2]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v41[16]; // [rsp+88h] [rbp-80h] BYREF
  int v42; // [rsp+98h] [rbp-70h]
  __int64 v43; // [rsp+A0h] [rbp-68h]
  int v44; // [rsp+A8h] [rbp-60h]
  int v45; // [rsp+ACh] [rbp-5Ch]
  int v46; // [rsp+B0h] [rbp-58h]
  __int64 v47; // [rsp+B4h] [rbp-54h]
  int v48; // [rsp+BCh] [rbp-4Ch]
  unsigned int v49; // [rsp+C0h] [rbp-48h]
  const WCHAR *v50; // [rsp+C8h] [rbp-40h]
  __int64 v51; // [rsp+D0h] [rbp-38h]
  __int16 v52; // [rsp+D8h] [rbp-30h]
  int v53; // [rsp+DCh] [rbp-2Ch]
  _BYTE v54[32]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v55[32]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v56[40]; // [rsp+120h] [rbp+18h] BYREF

  v39[1] = -2;
  FeatureUsageTracker::FeatureUsed(L"KernelTransport", L"EXDI", 1u);
  v34 = 0;
  v32 = 0;
  v33 = 0;
  LODWORD(ServiceManager) = LoadDynamicCalls(&g_Ole32CallsDesc);
  if ( !(_DWORD)ServiceManager )
  {
    LODWORD(ServiceManager) = LoadDynamicCalls(&g_OleAut32CallsDesc);
    if ( !(_DWORD)ServiceManager )
    {
      if ( ParameterStringParser::GetParser(
             *((const unsigned __int16 **)this + 527),
             1u,
             (const unsigned __int16 **)&g_ExdiGroupNames) == -1 )
      {
        LODWORD(ServiceManager) = -2147024809;
        goto LABEL_95;
      }
      v40[1] = 0;
      v40[0] = &ExdiParams::`vftable';
      v47 = 0;
      v48 = 0;
      v49 = 4;
      v50 = 0;
      v51 = 0;
      v52 = 256;
      v53 = 64;
      std::wstring::wstring(v54);
      std::wstring::wstring(v55);
      std::wstring::wstring(v56);
      ExdiParams::ResetParameters((ExdiParams *)v40);
      v3 = ParameterStringParser::ParseParameters(
             (ParameterStringParser *)v40,
             *((const unsigned __int16 **)this + 527));
      LODWORD(ServiceManager) = v3;
      if ( v3 )
      {
        VerbOut(L"EXDI: Failed to parse parameters: 0x%08X\n", v3);
LABEL_94:
        ExdiParams::~ExdiParams((ExdiParams *)v40);
        goto LABEL_95;
      }
      *((_DWORD *)this + 1994) = v42;
      *((_QWORD *)this + 998) = v43;
      *((_DWORD *)this + 2012) = v46;
      *(_QWORD *)((char *)this + 8084) = v47;
      *((_DWORD *)this + 2023) = v48;
      ServiceManager = (struct IDebugServiceManager *)(unsigned int)DbgCoInitialize(g_bAllowQiIUnknown);
      VerbOut(L"EXDI: DbgCoInitialize returned 0x%08X\n", ServiceManager);
      if ( (int)ServiceManager < 0 )
        goto LABEL_94;
      *((_DWORD *)this + 2020) = 1;
      if ( v49 == 1 )
      {
        v4 = boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(&v35, v40);
        LODWORD(ServiceManager) = Debugger::DataModel::ConvertException__lambda_761a4dd074768a4dea9dedf020210cee___(v4);
        if ( (_DWORD)ServiceManager )
        {
          FeatureUsageTracker::FeatureUsed(L"EXDI", L"HandleInprocServerTasksFailed", 1u);
          if ( (int)ServiceManager < 0 )
            goto LABEL_94;
        }
        WarnOut(L"EXDI WARNING! The /Inproc option is not compatible with connecting remote clients.\n");
        WarnOut(L"              Consider removing it if you encounter hangs or strange behavior.\n");
      }
      ServiceManager = (struct IDebugServiceManager *)(unsigned int)MEMORY[0](
                                                                      v41,
                                                                      0,
                                                                      v49,
                                                                      &GUID_00000000_0000_0000_c000_000000000046);
      VerbOut(L"EXDI: CoCreateInstance() returned 0x%08X\n", ServiceManager);
      if ( (int)ServiceManager < 0 )
      {
        FeatureUsageTracker::FeatureUsed(L"EXDI", L"CreateCOMServerFailed", 1u);
        goto LABEL_92;
      }
      v35 = 0;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v34->lpVtbl->QueryInterface)(
             v34,
             &GUID_22efa264_6fd7_4992_9427_125b511a477c,
             &v35) >= 0 )
      {
        v39[0] = 0;
        v8 = &strIn;
        if ( v50 )
          v8 = v50;
        if ( (*(int (__fastcall **)(__int64, const WCHAR *, _QWORD *))(*(_QWORD *)v35 + 24LL))(v35, v8, v39) >= 0
          && v39[0] )
        {
          Microsoft::WRL::ComPtr<Debugger::DataModel::Host::HostTypeSymbol>::operator=(&v34, v39);
        }
        else
        {
          ErrOut(L"EXDI: Cannot create a server using factory. EXDI constructor arguments will be ignored.\n");
        }
        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(v39);
      }
      else if ( HIDWORD(v51) )
      {
        ErrOut(L"EXDI: Cannot obtain server factory. EXDI constructor arguments will be ignored.\n");
      }
      v9 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v10 = v34;
      if ( !v34 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(0, v5, v6, v7);
        v10 = v34;
      }
      ServiceManager = (struct IDebugServiceManager *)((unsigned __int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v10->lpVtbl->QueryInterface)(
                                                        v10,
                                                        &GUID_2e501506_9703_4b6f_9d0d_6b42b0e41e6f,
                                                        &v32);
      VerbOut(L"EXDI: QueryInterface(IExdiServer3) returned 0x%08X\n", ServiceManager);
      if ( (int)ServiceManager < 0 )
      {
        if ( (_DWORD)ServiceManager == -2147467262 )
        {
          Exdi1ToExdi3Adapter = CreateExdi1ToExdi3Adapter(v34);
          v16 = *((_QWORD *)this + 1015);
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          *((_QWORD *)this + 1015) = Exdi1ToExdi3Adapter;
          if ( Exdi1ToExdi3Adapter )
          {
            WarnOut(L"WARNING: An old EXDIv1 server has been detected. Debugger will use the compatibility layer.\n");
            WarnOut(L"         It is advised to rebuild your EXDI server using EXDIv3 interfaces.\n");
            FeatureUsageTracker::FeatureUsed(L"EXDI", L"InterfaceV1", 1u);
            v17 = *((_QWORD *)this + 1015);
            ServiceManager = *(struct IDebugServiceManager **)(*(_QWORD *)v17 + 24LL);
            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v32);
            LODWORD(ServiceManager) = ((__int64 (__fastcall *)(__int64, __int64 *))ServiceManager)(v17, &v32);
          }
        }
      }
      else
      {
        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease((char *)this + 8120);
        v35 = v32;
        Microsoft::WRL::ComPtr<Debugger::DataModel::Host::HostTypeSymbol>::InternalAddRef(&v35);
        LODWORD(ServiceManager) = ExdiLiveKernelTargetInfo::Exdi3ServerContainer::Create(&v35, (char *)this + 8120);
        if ( (int)ServiceManager >= 0 && !*((_QWORD *)this + 1015) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
        FeatureUsageTracker::FeatureUsed(L"EXDI", L"InterfaceV3", 1u);
      }
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v34);
      if ( (int)ServiceManager < 0 )
        goto LABEL_92;
      v18 = 2;
      ExdiLiveKernelTargetInfo::ExecuteServerCommand(this, 2, 0, L"ExdiDbgType");
      v19 = (int *)((char *)this + 7912);
      ServiceManager = (struct IDebugServiceManager *)(*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v32 + 24LL))(
                                                        v32,
                                                        (char *)this + 7912);
      VerbOut(L"EXDI: Server::GetTargetInfo() returned 0x%08X\n", ServiceManager);
      if ( (int)ServiceManager < 0 )
        goto LABEL_92;
      if ( *((_QWORD *)this + 1014) && v49 != 1 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 208LL))(v32);
        VerbOut(L"EXDI: Server::SetKeepaliveInterface() returned 0x%08X\n", v20);
      }
      if ( v45 )
      {
        v21 = &GUID_6c4e5523_3ac1_4014_b454_e54e180abd8e;
        v22 = Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(
                &v32,
                &GUID_6c4e5523_3ac1_4014_b454_e54e180abd8e,
                &v33);
        LODWORD(ServiceManager) = v22;
        if ( v22 )
        {
          VerbOut(L"EXDI: Cannot get EBC context: status = 0x%08X\n", v22);
          goto LABEL_92;
        }
        *((_DWORD *)this + 1976) = 4;
        *((_DWORD *)this + 1999) = 3772;
      }
      else
      {
        if ( v44 )
          goto LABEL_64;
        v23 = *v19;
        if ( *v19 )
        {
          switch ( v23 )
          {
            case 8:
              v21 = &GUID_24c6a990_780c_428e_be5b_e27e2caea05a;
              v24 = Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(
                      &v32,
                      &GUID_24c6a990_780c_428e_be5b_e27e2caea05a,
                      &v33);
              LODWORD(ServiceManager) = v24;
              if ( v24 )
              {
                VerbOut(L"EXDI: Cannot get IA64 context: status = 0x%08X\n", v24);
                goto LABEL_92;
              }
              *((_DWORD *)this + 1976) = 3;
              *((_DWORD *)this + 1999) = 512;
              break;
            case 9:
              v21 = &GUID_2146be85_7866_4309_b973_f9650d1aa886;
              LODWORD(ServiceManager) = Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(
                                          &v32,
                                          &GUID_2146be85_7866_4309_b973_f9650d1aa886,
                                          &v33);
              if ( (_DWORD)ServiceManager )
                goto LABEL_92;
              *((_DWORD *)this + 1976) = 6;
              *((_DWORD *)this + 1999) = 43620;
              break;
            case 4:
              v21 = &GUID_25a27a99_c6f7_4a27_8749_fa7ea638adb5;
              v25 = Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(
                      &v32,
                      &GUID_25a27a99_c6f7_4a27_8749_fa7ea638adb5,
                      &v33);
              LODWORD(ServiceManager) = v25;
              if ( v25 )
              {
                VerbOut(L"EXDI: Cannot get ARM context: status = 0x%08X\n", v25);
                goto LABEL_92;
              }
              *((_DWORD *)this + 1976) = 5;
              *((_DWORD *)this + 1999) = 452;
              break;
            default:
              VerbOut(L"EXDI: Unrecognized TargetProcessorFamily: 0x%08X\n");
              LODWORD(ServiceManager) = -2147467262;
              goto LABEL_92;
          }
          goto LABEL_69;
        }
        v21 = &GUID_3a5bf3ff_8cda_4789_8323_be04a970d006;
        if ( (unsigned int)Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(
                             &v32,
                             &GUID_3a5bf3ff_8cda_4789_8323_be04a970d006,
                             &v33) )
        {
LABEL_64:
          v21 = &GUID_3f2a6a8a_d56b_4605_8a93_ac1c9b7e6318;
          if ( (unsigned int)Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(
                               &v32,
                               &GUID_3f2a6a8a_d56b_4605_8a93_ac1c9b7e6318,
                               &v33) )
          {
            v21 = &GUID_ebbbe2d6_9b1e_4f35_b956_28a78c348f0f;
            LODWORD(ServiceManager) = Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(
                                        &v32,
                                        &GUID_ebbbe2d6_9b1e_4f35_b956_28a78c348f0f,
                                        &v33);
            if ( (_DWORD)ServiceManager )
            {
              VerbOut(L"EXDI: Cannot detect x86 context type\n");
              goto LABEL_92;
            }
            *((_DWORD *)this + 1976) = 0;
          }
          else
          {
            *((_DWORD *)this + 1976) = 1;
          }
          *((_DWORD *)this + 1999) = 332;
          goto LABEL_69;
        }
        *((_DWORD *)this + 1976) = 2;
        *((_DWORD *)this + 1999) = 34404;
      }
LABEL_69:
      *((_QWORD *)this + 531) = v21;
      v37 = 0;
      v36 = 0;
      ServiceManager = (struct IDebugServiceManager *)(*(unsigned int (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v32 + 72LL))(
                                                        v32,
                                                        &v37,
                                                        &v36);
      VerbOut(L"EXDI: Server::GetNbCodeBpAvail() returned 0x%08X\n", ServiceManager);
      if ( (int)ServiceManager < 0 )
        goto LABEL_92;
      if ( !v36 || v37 == -1 )
        v18 = 0;
      *((_DWORD *)this + 2000) = v18;
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 1002) = EventW;
      if ( EventW )
      {
        LODWORD(ServiceManager) = 0;
      }
      else if ( GetLastError() )
      {
        LastError = GetLastError();
        LODWORD(ServiceManager) = LastError;
        if ( LastError > 0 )
          LODWORD(ServiceManager) = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LODWORD(ServiceManager) = -2147467259;
      }
      VerbOut(L"EXDI: ExdiNotifyRunChange::Initialize() returned 0x%08X\n", (unsigned int)ServiceManager);
      if ( (int)ServiceManager < 0 )
        goto LABEL_92;
      ServiceManager = (struct IDebugServiceManager *)(unsigned int)TargetInfo::Initialize(this);
      VerbOut(L"EXDI: LiveKernelTargetInfo::Initialize() returned 0x%08X\n", ServiceManager);
      if ( (int)ServiceManager >= 0 )
      {
        LODWORD(v38) = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 80LL))(v32, &v38) < 0 || !(_DWORD)v38 )
        {
          WarnOut(L"EXDI data breakpoints not supported\n");
          *((_DWORD *)this + 2012) = 0;
        }
        (*(void (__fastcall **)(ExdiLiveKernelTargetInfo *))(*(_QWORD *)this + 600LL))(this);
        *((_DWORD *)this + 1060) = GetCurrentThreadId();
        if ( !*((_DWORD *)this + 2022) )
          goto LABEL_90;
        ServiceManager = TargetInfo::GetServiceManager(this);
        v28 = *((_QWORD *)Debugger::TargetComposition::Host::TargetCompositionHost::s_pHostSingleton + 2);
        v29 = ExtensionInfo::CheckAdd(0, L"ELFBinComposition.dll", 0, 0, (bool)&v34);
        if ( v29 && (ProcAddress = GetProcAddress(*((HMODULE *)v29 + 206), "PrepareServicesForHardwareDebugging")) != 0 )
        {
          LODWORD(ServiceManager) = ((__int64 (__fastcall *)(struct IDebugServiceManager *, __int64, _QWORD))ProcAddress)(
                                      ServiceManager,
                                      v28,
                                      *((unsigned int *)this + 1999));
          if ( (int)ServiceManager >= 0 )
          {
LABEL_90:
            VerbOut(L"EXDI: Target initialization succeeded\n");
            ExdiParams::~ExdiParams((ExdiParams *)v40);
            LODWORD(ServiceManager) = 0;
            goto LABEL_95;
          }
        }
        else
        {
          LODWORD(ServiceManager) = -2147418113;
        }
      }
      ExdiNotifyRunChange::Uninitialize((ExdiLiveKernelTargetInfo *)((char *)this + 8008));
LABEL_92:
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v33);
      if ( *((_DWORD *)this + 2020) )
      {
        MEMORY[0]();
        *((_DWORD *)this + 2020) = 0;
      }
      goto LABEL_94;
    }
  }
LABEL_95:
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v34);
  return (unsigned int)ServiceManager;
}

```

## disassembly

```asm
0x1802cfd00  mov     rax, rsp
0x1802cfd03  push    rbp
0x1802cfd04  push    rdi
0x1802cfd05  push    r12
0x1802cfd07  push    r14
0x1802cfd09  push    r15
0x1802cfd0b  lea     rbp, [rax-78h]
0x1802cfd0f  sub     rsp, 150h
0x1802cfd16  mov     [rsp+170h+var_108], 0FFFFFFFFFFFFFFFEh
0x1802cfd1f  mov     [rax+10h], rbx
0x1802cfd23  mov     [rax+18h], rsi
0x1802cfd27  mov     rax, cs:__security_cookie
0x1802cfd2e  xor     rax, rsp
0x1802cfd31  mov     [rbp+70h+var_30], rax
0x1802cfd35  mov     rsi, rcx
0x1802cfd38  mov     r12d, 1
0x1802cfd3e  mov     r8d, r12d; unsigned int
0x1802cfd41  lea     r14, aExdi_0; "EXDI"
0x1802cfd48  mov     rdx, r14; unsigned __int16 *
0x1802cfd4b  lea     rcx, aKerneltranspor; "KernelTransport"
0x1802cfd52  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1802cfd57  xor     r15d, r15d
0x1802cfd5a  mov     [rsp+170h+var_130], r15
0x1802cfd5f  mov     [rsp+170h+var_140], r15
0x1802cfd64  mov     [rsp+170h+var_138], r15
0x1802cfd69  lea     rcx, ?g_Ole32CallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_Ole32CallsDesc
0x1802cfd70  call    LoadDynamicCalls
0x1802cfd75  mov     ebx, eax
0x1802cfd77  test    eax, eax
0x1802cfd79  jnz     loc_1802D05C5
0x1802cfd7f  lea     rcx, ?g_OleAut32CallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_OleAut32CallsDesc
0x1802cfd86  call    LoadDynamicCalls
0x1802cfd8b  mov     ebx, eax
0x1802cfd8d  test    eax, eax
0x1802cfd8f  jnz     loc_1802D05C5
0x1802cfd95  lea     r8, ?g_ExdiGroupNames@@3PAPEBGA; unsigned __int16 **
0x1802cfd9c  mov     edx, r12d; unsigned int
0x1802cfd9f  mov     rcx, [rsi+1078h]; Buf2
0x1802cfda6  call    ?GetParser@ParameterStringParser@@SAKPEBGKPEAPEBG@Z; ParameterStringParser::GetParser(ushort const *,ulong,ushort const * *)
0x1802cfdab  cmp     eax, 0FFFFFFFFh
0x1802cfdae  jnz     short loc_1802CFDBA
0x1802cfdb0  mov     ebx, 80070057h
0x1802cfdb5  jmp     loc_1802D05C5
0x1802cfdba  mov     [rsp+170h+var_F8], r15
0x1802cfdbf  lea     rax, ??_7ExdiParams@@6B@; const ExdiParams::`vftable'
0x1802cfdc6  mov     [rsp+170h+var_100], rax
0x1802cfdcb  mov     [rbp+70h+var_C4], r15
0x1802cfdcf  mov     [rbp+70h+var_BC], r15d
0x1802cfdd3  mov     [rbp+70h+var_B8], 4
0x1802cfdda  mov     [rbp+70h+var_B0], r15
0x1802cfdde  mov     [rbp+70h+var_A8], r15
0x1802cfde2  mov     [rbp+70h+var_A0], 100h
0x1802cfde8  mov     [rbp+70h+var_9C], 40h ; '@'
0x1802cfdef  lea     rcx, [rbp+70h+var_98]
0x1802cfdf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1802cfdf8  lea     rcx, [rbp+70h+var_78]
0x1802cfdfc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1802cfe01  lea     rcx, [rbp+70h+var_58]
0x1802cfe05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1802cfe0a  nop
0x1802cfe0b  lea     rcx, [rsp+170h+var_100]; this
0x1802cfe10  call    ?ResetParameters@ExdiParams@@UEAAXXZ; ExdiParams::ResetParameters(void)
0x1802cfe15  mov     rdx, [rsi+1078h]; unsigned __int16 *
0x1802cfe1c  lea     rcx, [rsp+170h+var_100]; this
0x1802cfe21  call    ?ParseParameters@ParameterStringParser@@QEAAJPEBG@Z; ParameterStringParser::ParseParameters(ushort const *)
0x1802cfe26  mov     ebx, eax
0x1802cfe28  test    eax, eax
0x1802cfe2a  jz      short loc_1802CFE3F
0x1802cfe2c  mov     edx, eax
0x1802cfe2e  lea     rcx, aExdiFailedToPa; "EXDI: Failed to parse parameters: 0x%08"...
0x1802cfe35  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1802cfe3a  jmp     loc_1802D05BA
0x1802cfe3f  mov     eax, [rbp+70h+var_E0]
0x1802cfe42  mov     [rsi+1F28h], eax
0x1802cfe48  mov     rax, [rbp+70h+var_D8]
0x1802cfe4c  mov     [rsi+1F30h], rax
0x1802cfe53  mov     eax, [rbp+70h+var_C8]
0x1802cfe56  mov     [rsi+1F70h], eax
0x1802cfe5c  mov     eax, dword ptr [rbp+70h+var_C4]
0x1802cfe5f  mov     [rsi+1F94h], eax
0x1802cfe65  mov     eax, dword ptr [rbp+70h+var_C4+4]
0x1802cfe68  mov     [rsi+1F98h], eax
0x1802cfe6e  mov     eax, [rbp+70h+var_BC]
0x1802cfe71  mov     [rsi+1F9Ch], eax
0x1802cfe77  movzx   ecx, cs:?g_bAllowQiIUnknown@@3EA; int
0x1802cfe7e  call    ?DbgCoInitialize@@YAJH@Z; DbgCoInitialize(int)
0x1802cfe83  mov     ebx, eax
0x1802cfe85  mov     edx, eax
0x1802cfe87  lea     rcx, aExdiDbgcoiniti; "EXDI: DbgCoInitialize returned 0x%08X\n"
0x1802cfe8e  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1802cfe93  test    ebx, ebx
0x1802cfe95  js      loc_1802D05BA
0x1802cfe9b  mov     [rsi+1F90h], r12d
0x1802cfea2  cmp     [rbp+70h+var_B8], r12d
0x1802cfea6  jnz     short loc_1802CFEF7
0x1802cfea8  lea     rdx, [rsp+170h+var_100]
0x1802cfead  lea     rcx, [rsp+170h+var_128]
0x1802cfeb2  call    ??0data_type@?$cpp_int_base@$0IA@$0IA@$0A@$0A@X$0A@@backends@multiprecision@boost@@QEAA@_K@Z; boost::multiprecision::backends::cpp_int_base<128,128,0,0,void,0>::data_type::data_type(unsigned __int64)
0x1802cfeb7  mov     rcx, rax
0x1802cfeba  call    Debugger__DataModel__ConvertException__lambda_761a4dd074768a4dea9dedf020210cee___
0x1802cfebf  mov     ebx, eax
0x1802cfec1  test    eax, eax
0x1802cfec3  jz      short loc_1802CFEDF
0x1802cfec5  mov     r8d, r12d; unsigned int
0x1802cfec8  lea     rdx, aHandleinprocse; "HandleInprocServerTasksFailed"
0x1802cfecf  mov     rcx, r14; unsigned __int16 *
0x1802cfed2  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1802cfed7  test    ebx, ebx
0x1802cfed9  js      loc_1802D05BA
0x1802cfedf  lea     rcx, aExdiWarningThe; "EXDI WARNING! The /Inproc option is not"...
0x1802cfee6  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1802cfeeb  lea     rcx, aConsiderRemovi; "              Consider removing it if y"...
0x1802cfef2  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1802cfef7  mov     rax, cs:qword_18082D0F0
0x1802cfefe  lea     rcx, [rsp+170h+var_130]
0x1802cff03  mov     qword ptr [rsp+170h+var_150], rcx; bool
0x1802cff08  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x1802cff0f  mov     r8d, [rbp+70h+var_B8]
0x1802cff13  xor     edx, edx
0x1802cff15  lea     rcx, [rbp+70h+var_F0]
0x1802cff19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cff1e  mov     ebx, eax
0x1802cff20  mov     edx, eax
0x1802cff22  lea     rcx, aExdiCocreatein; "EXDI: CoCreateInstance() returned 0x%08"...
0x1802cff29  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1802cff2e  test    ebx, ebx
0x1802cff30  jns     short loc_1802CFF49
0x1802cff32  mov     r8d, r12d; unsigned int
0x1802cff35  lea     rdx, aCreatecomserve; "CreateCOMServerFailed"
0x1802cff3c  mov     rcx, r14; unsigned __int16 *
0x1802cff3f  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1802cff44  jmp     loc_1802D0580
0x1802cff49  mov     [rsp+170h+var_128], r15
0x1802cff4e  mov     rcx, [rsp+170h+var_130]
0x1802cff53  mov     rax, [rcx]
0x1802cff56  lea     r8, [rsp+170h+var_128]
0x1802cff5b  lea     rdx, _GUID_22efa264_6fd7_4992_9427_125b511a477c
0x1802cff62  mov     rax, [rax]
0x1802cff65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cff6a  nop
0x1802cff6b  test    eax, eax
0x1802cff6d  jns     short loc_1802CFF83
0x1802cff6f  cmp     dword ptr [rbp+70h+var_A8+4], r15d
0x1802cff73  jz      short loc_1802CFFE4
0x1802cff75  lea     rcx, aExdiCannotObta; "EXDI: Cannot obtain server factory. EXD"...
0x1802cff7c  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802cff81  jmp     short loc_1802CFFE4
0x1802cff83  mov     [rsp+170h+var_110], r15
0x1802cff88  mov     r8, [rbp+70h+var_B0]
0x1802cff8c  mov     rcx, [rsp+170h+var_128]
0x1802cff91  mov     rax, [rcx]
0x1802cff94  lea     rdx, strIn
0x1802cff9b  test    r8, r8
0x1802cff9e  cmovnz  rdx, r8
0x1802cffa2  lea     r8, [rsp+170h+var_110]
0x1802cffa7  mov     rax, [rax+18h]
0x1802cffab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cffb0  test    eax, eax
0x1802cffb2  js      short loc_1802CFFCC
0x1802cffb4  cmp     [rsp+170h+var_110], r15
0x1802cffb9  jz      short loc_1802CFFCC
0x1802cffbb  lea     rdx, [rsp+170h+var_110]
0x1802cffc0  lea     rcx, [rsp+170h+var_130]
0x1802cffc5  call    ??4?$ComPtr@VHostTypeSymbol@Host@DataModel@Debugger@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Debugger::DataModel::Host::HostTypeSymbol>::operator=(Microsoft::WRL::ComPtr<Debugger::DataModel::Host::HostTypeSymbol> const &)
0x1802cffca  jmp     short loc_1802CFFD9
0x1802cffcc  lea     rcx, aExdiCannotCrea; "EXDI: Cannot create a server using fact"...
0x1802cffd3  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802cffd8  nop
0x1802cffd9  lea     rcx, [rsp+170h+var_110]
0x1802cffde  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1802cffe3  nop
0x1802cffe4  mov     rcx, [rsp+170h+var_128]
0x1802cffe9  test    rcx, rcx
0x1802cffec  jz      short loc_1802D0000
0x1802cffee  mov     [rsp+170h+var_128], r15
0x1802cfff3  mov     rax, [rcx]
0x1802cfff6  mov     rax, [rax+10h]
0x1802cfffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cffff  nop
0x1802d0000  mov     rcx, [rsp+170h+var_130]
0x1802d0005  test    rcx, rcx
0x1802d0008  jnz     short loc_1802D0014
0x1802d000a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1802d000f  mov     rcx, [rsp+170h+var_130]
0x1802d0014  mov     rax, [rcx]
0x1802d0017  lea     r8, [rsp+170h+var_140]
0x1802d001c  lea     rdx, _GUID_2e501506_9703_4b6f_9d0d_6b42b0e41e6f
0x1802d0023  mov     rax, [rax]
0x1802d0026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802d002b  mov     ebx, eax
0x1802d002d  mov     edx, eax
0x1802d002f  lea     rcx, aExdiQueryinter; "EXDI: QueryInterface(IExdiServer3) retu"...
0x1802d0036  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1802d003b  test    ebx, ebx
0x1802d003d  js      short loc_1802D0096
0x1802d003f  lea     rdi, [rsi+1FB8h]
0x1802d0046  mov     rcx, rdi
0x1802d0049  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1802d004e  mov     rax, [rsp+170h+var_140]
0x1802d0053  mov     [rsp+170h+var_128], rax
0x1802d0058  lea     rcx, [rsp+170h+var_128]
0x1802d005d  call    ?InternalAddRef@?$ComPtr@VHostTypeSymbol@Host@DataModel@Debugger@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Debugger::DataModel::Host::HostTypeSymbol>::InternalAddRef(void)
0x1802d0062  mov     rdx, rdi
0x1802d0065  lea     rcx, [rsp+170h+var_128]
0x1802d006a  call    ?Create@Exdi3ServerContainer@ExdiLiveKernelTargetInfo@@SAJV?$ComPtr@UIeXdiServer3@@@WRL@Microsoft@@PEAV?$ComPtr@VIExdiServerContainer@ExdiLiveKernelTargetInfo@@@45@@Z; ExdiLiveKernelTargetInfo::Exdi3ServerContainer::Create(Microsoft::WRL::ComPtr<IeXdiServer3>,Microsoft::WRL::ComPtr<ExdiLiveKernelTargetInfo::IExdiServerContainer> *)
0x1802d006f  mov     ebx, eax
0x1802d0071  test    eax, eax
0x1802d0073  js      short loc_1802D007F
0x1802d0075  cmp     [rdi], r15
0x1802d0078  jnz     short loc_1802D007F
0x1802d007a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1802d007f  mov     r8d, r12d; unsigned int
0x1802d0082  lea     rdx, aInterfacev3; "InterfaceV3"
0x1802d0089  mov     rcx, r14; unsigned __int16 *
0x1802d008c  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1802d0091  jmp     loc_1802D0127
0x1802d0096  cmp     ebx, 80004002h
0x1802d009c  jnz     loc_1802D0127
0x1802d00a2  mov     rcx, [rsp+170h+var_130]; struct IUnknown *
0x1802d00a7  call    ?CreateExdi1ToExdi3Adapter@@YAPEAVIExdiServerContainer@ExdiLiveKernelTargetInfo@@PEAUIUnknown@@@Z; CreateExdi1ToExdi3Adapter(IUnknown *)
0x1802d00ac  mov     rdi, rax
0x1802d00af  mov     rcx, [rsi+1FB8h]
0x1802d00b6  test    rcx, rcx
0x1802d00b9  jz      short loc_1802D00C7
0x1802d00bb  mov     rdx, [rcx]
0x1802d00be  mov     rax, [rdx+10h]
0x1802d00c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802d00c7  mov     [rsi+1FB8h], rdi
0x1802d00ce  test    rdi, rdi
0x1802d00d1  jz      short loc_1802D0127
0x1802d00d3  lea     rcx, aWarningAnOldEx; "WARNING: An old EXDIv1 server has been "...
0x1802d00da  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1802d00df  lea     rcx, aItIsAdvisedToR; "         It is advised to rebuild your "...
0x1802d00e6  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1802d00eb  mov     r8d, r12d; unsigned int
0x1802d00ee  lea     rdx, aInterfacev1; "InterfaceV1"
0x1802d00f5  mov     rcx, r14; unsigned __int16 *
0x1802d00f8  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1802d00fd  mov     rdi, [rsi+1FB8h]
0x1802d0104  mov     rax, [rdi]
0x1802d0107  mov     rbx, [rax+18h]
0x1802d010b  lea     rcx, [rsp+170h+var_140]
0x1802d0110  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1802d0115  lea     rdx, [rsp+170h+var_140]
0x1802d011a  mov     rcx, rdi
0x1802d011d  mov     rax, rbx
0x1802d0120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802d0125  mov     ebx, eax
0x1802d0127  lea     rcx, [rsp+170h+var_130]
0x1802d012c  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1802d0131  test    ebx, ebx
0x1802d0133  js      loc_1802D0580
0x1802d0139  lea     r9, aExdidbgtype; "ExdiDbgType"
0x1802d0140  xor     r8d, r8d
0x1802d0143  lea     r14d, [r8+2]
0x1802d0147  mov     edx, r14d
0x1802d014a  mov     rcx, rsi
0x1802d014d  call    ?ExecuteServerCommand@ExdiLiveKernelTargetInfo@@QEAAXW4EXDI_COMMAND_TYPE@1@HPEBG@Z; ExdiLiveKernelTargetInfo::ExecuteServerCommand(ExdiLiveKernelTargetInfo::EXDI_COMMAND_TYPE,int,ushort const *)
0x1802d0152  mov     rcx, [rsp+170h+var_140]
0x1802d0157  lea     rdi, [rsi+1EE8h]
0x1802d015e  mov     rax, [rcx]
0x1802d0161  mov     rdx, rdi
0x1802d0164  mov     rax, [rax+18h]
0x1802d0168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802d016d  mov     ebx, eax
0x1802d016f  mov     edx, eax
0x1802d0171  lea     rcx, aExdiServerGett; "EXDI: Server::GetTargetInfo() returned "...
0x1802d0178  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1802d017d  test    ebx, ebx
0x1802d017f  js      loc_1802D0580
0x1802d0185  mov     rdx, [rsi+1FB0h]
0x1802d018c  test    rdx, rdx
0x1802d018f  jz      short loc_1802D01B9
0x1802d0191  cmp     [rbp+70h+var_B8], r12d
0x1802d0195  jz      short loc_1802D01B9
0x1802d0197  mov     rcx, [rsp+170h+var_140]
0x1802d019c  mov     rax, [rcx]
0x1802d019f  mov     rax, [rax+0D0h]
0x1802d01a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802d01ab  mov     edx, eax
0x1802d01ad  lea     rcx, aExdiServerSetk; "EXDI: Server::SetKeepaliveInterface() r"...
0x1802d01b4  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1802d01b9  cmp     [rbp+70h+var_CC], r15d
0x1802d01bd  jz      short loc_1802D020A
0x1802d01bf  lea     r8, [rsp+170h+var_138]
0x1802d01c4  lea     rdi, _GUID_6c4e5523_3ac1_4014_b454_e54e180abd8e
0x1802d01cb  mov     rdx, rdi
0x1802d01ce  lea     rcx, [rsp+170h+var_140]
0x1802d01d3  call    ?CopyTo@?$ComPtr@UIeXdiServer@eXdiV1@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<eXdiV1::IeXdiServer>::CopyTo(_GUID const &,void * *)
0x1802d01d8  mov     ebx, eax
0x1802d01da  test    eax, eax
0x1802d01dc  jnz     short loc_1802D01F7
0x1802d01de  mov     dword ptr [rsi+1EE0h], 4
0x1802d01e8  mov     dword ptr [rsi+1F3Ch], 0EBCh
0x1802d01f2  jmp     loc_1802D038E
0x1802d01f7  lea     rcx, aExdiCannotGetE; "EXDI: Cannot get EBC context: status = "...
0x1802d01fe  mov     edx, eax
0x1802d0200  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1802d0205  jmp     loc_1802D0580
0x1802d020a  cmp     [rbp+70h+var_D0], r15d
  ... truncated ...
```
