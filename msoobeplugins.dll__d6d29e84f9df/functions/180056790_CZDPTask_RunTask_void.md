# CZDPTask::RunTask(void)

- ea: `0x180056790`
- end: `0x180056a98`
- name: `?RunTask@CZDPTask@@UEAAJXZ`
- size: `776`
- prototype: `__int64 __fastcall(CZDPTask *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180056aa0`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x18001aa9c`
- `0x1800553b8`
- `0x1800554e0`
- `0x180055608`
- `0x180055c98`
- `0x180055d24`
- `0x180055db0`
- `0x180055f00`
- `0x18005603c`
- `0x180056790`
- `0x1800573e0`
- `0x180057478`
- `0x180057664`
- `0x180057830`
- `0x180057a14`
- `0x180057f88`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180056826`
- `OLEAUT32!__imp_SysAllocString` at `0x180056826`
- `OLEAUT32!__imp_SysFreeString` at `0x18005684b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005684b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005680b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005680b`

## string_xrefs

- `0x180056a00`: `CZDPTask setting OOBE_GLOBAL_SETTING_ZDPSTATUS ZDP_Finished.`
- `0x1800569f0`: `Resetting HRESULT from E_ABORT before returning from main task method.`
- `0x1800569d7`: `Failed to create IUpdateSession [hr=0x%08X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CZDPTask::RunTask(CZDPTask *this, __int64 a2, __int64 a3)
{
  HRESULT Instance; // eax
  int v5; // ebx
  struct IUpdateSession *v6; // rbx
  OLECHAR *v7; // rsi
  int v8; // ebx
  CZDPTask *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  int v13; // [rsp+30h] [rbp-19h] BYREF
  int v14; // [rsp+34h] [rbp-15h] BYREF
  struct IUpdateCollection *v15; // [rsp+38h] [rbp-11h] BYREF
  struct IUpdateSession *ppv; // [rsp+40h] [rbp-9h] BYREF
  struct IUpdateCollection *v17; // [rsp+48h] [rbp-1h] BYREF
  int v18; // [rsp+50h] [rbp+7h] BYREF
  __int128 v19; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+68h] [rbp+1Fh]

  if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(Microsoft_Windows_OOBE_Machine_Plugins_Context, ZdpTask_Start, a3, 1, &v19);
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  Instance = CoCreateInstance(&CLSID_UpdateSession, 0, 1u, &GUID_816858a4_260d_4260_933a_2585f1abc76b, (LPVOID *)&ppv);
  v5 = Instance;
  if ( Instance >= 0 )
  {
    v6 = ppv;
    v7 = SysAllocString(L"OOBE ZDP");
    if ( v7 )
    {
      v8 = ((__int64 (__fastcall *)(struct IUpdateSession *, OLECHAR *))v6->lpVtbl->put_ClientApplicationID)(v6, v7);
      SysFreeString(v7);
      if ( v8 >= 0 )
        goto LABEL_9;
    }
    else
    {
      v8 = -2147024882;
    }
    UnattendLogW(2, L"Failed to set WU session Client Application ID [hr=0x%08X]", (unsigned int)v8);
LABEL_9:
    AutoExecutionPowerHold::AutoExecutionPowerHold((AutoExecutionPowerHold *)&v19);
    v17 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    v5 = CZDPTask::_Search(this, ppv, &v17);
    v13 = v5;
    OOBE::Health::details::OOBEHealthTracker::HandleEvent<4,long>(v5);
    if ( v5 >= 0 )
    {
      v18 = 0;
      ((void (__fastcall *)(struct IUpdateCollection *, int *))v17->lpVtbl->get_Count)(v17, &v18);
      OobeZdpTelemetry::ZdpSearchStatus<long &,long &>(&v13, &v18);
      CZDPTask::_CancelIfNoUpdates(this, v17);
    }
    v15 = 0;
    if ( v5 >= 0 )
    {
      if ( CZDPTask::_IsCanceled(this) )
        goto LABEL_15;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
      v5 = CZDPTask::_FilterUpdates(v9, v17, &v15);
      if ( v5 >= 0 )
      {
        CZDPTask::_CancelIfNoUpdates(this, v15);
LABEL_15:
        v14 = 0;
        if ( CZDPTask::_IsCanceled(this)
          || (((void (__fastcall *)(struct IUpdateCollection *, int *))v15->lpVtbl->get_Count)(v15, &v14),
              v5 = CZDPTask::_Download(this, ppv, v15),
              v13 = v5,
              OOBE::Health::details::OOBEHealthTracker::HandleEvent<5,long>(v5),
              OobeZdpTelemetry::ZdpDownloadStatus<long &,long &>(&v13, &v14),
              v5 >= 0) )
        {
          if ( !CZDPTask::_IsCanceled(this) )
          {
            v5 = CZDPTask::_Install(this, ppv, v15);
            v13 = v5;
            OOBE::Health::details::OOBEHealthTracker::HandleEvent<6,long>(v5);
            OobeZdpTelemetry::ZdpInstallStatus<long &,long &>(&v13, &v14);
          }
        }
        goto LABEL_20;
      }
    }
    v14 = 0;
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    AutoExecutionPowerHold::~AutoExecutionPowerHold((AutoExecutionPowerHold *)&v19);
    goto LABEL_22;
  }
  UnattendLogW(1, L"Failed to create IUpdateSession [hr=0x%08X]", (unsigned int)Instance);
LABEL_22:
  if ( v5 == -2147467260 )
  {
    UnattendLogW(0, L"Resetting HRESULT from E_ABORT before returning from main task method.");
    v5 = 0;
  }
  UnattendLogW(0, L"CZDPTask setting OOBE_GLOBAL_SETTING_ZDPSTATUS ZDP_Finished.");
  v10 = *((_QWORD *)this + 71);
  v19 = 0;
  v20 = 0;
  LOWORD(v19) = 19;
  DWORD2(v19) = 4;
  (*(void (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v10 + 32LL))(v10, L"ZDPSTATUS", &v19);
  if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(Microsoft_Windows_OOBE_Machine_Plugins_Context, ZdpTask_Stop, v11, 1, &v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180056790  push    rbp
0x180056792  push    rbx
0x180056793  push    rsi
0x180056794  push    rdi
0x180056795  lea     rbp, [rsp-3Fh]
0x18005679a  sub     rsp, 88h
0x1800567a1  mov     rax, cs:__security_cookie
0x1800567a8  xor     rax, rsp
0x1800567ab  mov     [rbp+57h+var_30], rax
0x1800567af  mov     rdi, rcx
0x1800567b2  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x1800567b9  jz      short loc_1800567DD
0x1800567bb  lea     rax, [rbp+57h+var_48]
0x1800567bf  mov     [rsp+0A0h+ppv], rax
0x1800567c4  mov     r9d, 1
0x1800567ca  lea     rdx, ZdpTask_Start
0x1800567d1  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x1800567d8  call    McGenEventWrite_EventWriteTransfer
0x1800567dd  mov     [rbp+57h+var_60], 0
0x1800567e5  lea     rcx, [rbp+57h+var_60]
0x1800567e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800567ee  lea     rax, [rbp+57h+var_60]
0x1800567f2  mov     [rsp+0A0h+ppv], rax; ppv
0x1800567f7  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x1800567fe  xor     edx, edx; pUnkOuter
0x180056800  lea     r8d, [rdx+1]; dwClsContext
0x180056804  lea     rcx, CLSID_UpdateSession; rclsid
0x18005680b  call    cs:__imp_CoCreateInstance
0x180056811  mov     ebx, eax
0x180056813  test    eax, eax
0x180056815  js      loc_1800569D4
0x18005681b  mov     rbx, [rbp+57h+var_60]
0x18005681f  lea     rcx, aOobeZdp; "OOBE ZDP"
0x180056826  call    cs:__imp_SysAllocString
0x18005682c  mov     rsi, rax
0x18005682f  test    rax, rax
0x180056832  jz      short loc_180056857
0x180056834  mov     rdx, [rbx]
0x180056837  mov     rax, [rdx+40h]
0x18005683b  mov     rdx, rsi
0x18005683e  mov     rcx, rbx
0x180056841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056846  mov     ebx, eax
0x180056848  mov     rcx, rsi; bstrString
0x18005684b  call    cs:__imp_SysFreeString
0x180056851  test    ebx, ebx
0x180056853  jns     short loc_180056870
0x180056855  jmp     short loc_18005685C
0x180056857  mov     ebx, 8007000Eh
0x18005685c  mov     r8d, ebx
0x18005685f  lea     rdx, aFailedToSetWuS; "Failed to set WU session Client Applica"...
0x180056866  mov     ecx, 2
0x18005686b  call    UnattendLogW
0x180056870  lea     rcx, [rbp+57h+var_48]; this
0x180056874  call    ??0AutoExecutionPowerHold@@QEAA@XZ; AutoExecutionPowerHold::AutoExecutionPowerHold(void)
0x180056879  nop
0x18005687a  mov     [rbp+57h+var_58], 0
0x180056882  lea     rcx, [rbp+57h+var_58]
0x180056886  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005688b  lea     r8, [rbp+57h+var_58]; struct IUpdateCollection **
0x18005688f  mov     rdx, [rbp+57h+var_60]; struct IUpdateSession *
0x180056893  mov     rcx, rdi; this
0x180056896  call    ?_Search@CZDPTask@@AEAAJPEAUIUpdateSession@@PEAPEAUIUpdateCollection@@@Z; CZDPTask::_Search(IUpdateSession *,IUpdateCollection * *)
0x18005689b  mov     ebx, eax
0x18005689d  mov     [rbp+57h+var_70], eax
0x1800568a0  mov     ecx, eax
0x1800568a2  call    ??$HandleEvent@$03J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<4,long>(long)
0x1800568a7  test    ebx, ebx
0x1800568a9  js      short loc_1800568DF
0x1800568ab  mov     [rbp+57h+var_50], 0
0x1800568b2  mov     rcx, [rbp+57h+var_58]
0x1800568b6  mov     rax, [rcx]
0x1800568b9  lea     rdx, [rbp+57h+var_50]
0x1800568bd  mov     rax, [rax+50h]
0x1800568c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568c6  lea     rdx, [rbp+57h+var_50]
0x1800568ca  lea     rcx, [rbp+57h+var_70]
0x1800568ce  call    ??$ZdpSearchStatus@AEAJAEAJ@OobeZdpTelemetry@@SAXAEAJ0@Z; OobeZdpTelemetry::ZdpSearchStatus<long &,long &>(long &,long &)
0x1800568d3  mov     rdx, [rbp+57h+var_58]; struct IUpdateCollection *
0x1800568d7  mov     rcx, rdi; this
0x1800568da  call    ?_CancelIfNoUpdates@CZDPTask@@AEAAXPEAUIUpdateCollection@@@Z; CZDPTask::_CancelIfNoUpdates(IUpdateCollection *)
0x1800568df  mov     [rbp+57h+var_68], 0
0x1800568e7  test    ebx, ebx
0x1800568e9  js      loc_1800569B0
0x1800568ef  mov     rcx, rdi; this
0x1800568f2  call    ?_IsCanceled@CZDPTask@@AEAA_NXZ; CZDPTask::_IsCanceled(void)
0x1800568f7  test    al, al
0x1800568f9  jnz     short loc_180056927
0x1800568fb  lea     rcx, [rbp+57h+var_68]
0x1800568ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056904  lea     r8, [rbp+57h+var_68]; struct IUpdateCollection **
0x180056908  mov     rdx, [rbp+57h+var_58]; struct IUpdateCollection *
0x18005690c  call    ?_FilterUpdates@CZDPTask@@AEAAJPEAUIUpdateCollection@@PEAPEAU2@@Z; CZDPTask::_FilterUpdates(IUpdateCollection *,IUpdateCollection * *)
0x180056911  mov     ebx, eax
0x180056913  test    eax, eax
0x180056915  js      loc_1800569B0
0x18005691b  mov     rdx, [rbp+57h+var_68]; struct IUpdateCollection *
0x18005691f  mov     rcx, rdi; this
0x180056922  call    ?_CancelIfNoUpdates@CZDPTask@@AEAAXPEAUIUpdateCollection@@@Z; CZDPTask::_CancelIfNoUpdates(IUpdateCollection *)
0x180056927  xor     eax, eax
0x180056929  mov     [rbp+57h+var_6C], eax
0x18005692c  mov     rcx, rdi; this
0x18005692f  call    ?_IsCanceled@CZDPTask@@AEAA_NXZ; CZDPTask::_IsCanceled(void)
0x180056934  test    al, al
0x180056936  jnz     short loc_180056979
0x180056938  mov     rcx, [rbp+57h+var_68]
0x18005693c  mov     rax, [rcx]
0x18005693f  lea     rdx, [rbp+57h+var_6C]
0x180056943  mov     rax, [rax+50h]
0x180056947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005694c  mov     r8, [rbp+57h+var_68]; struct IUpdateCollection *
0x180056950  mov     rdx, [rbp+57h+var_60]; struct IUpdateSession *
0x180056954  mov     rcx, rdi; this
0x180056957  call    ?_Download@CZDPTask@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z; CZDPTask::_Download(IUpdateSession *,IUpdateCollection *)
0x18005695c  mov     ebx, eax
0x18005695e  mov     [rbp+57h+var_70], eax
0x180056961  mov     ecx, eax
0x180056963  call    ??$HandleEvent@$04J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<5,long>(long)
0x180056968  lea     rdx, [rbp+57h+var_6C]
0x18005696c  lea     rcx, [rbp+57h+var_70]
0x180056970  call    ??$ZdpDownloadStatus@AEAJAEAJ@OobeZdpTelemetry@@SAXAEAJ0@Z; OobeZdpTelemetry::ZdpDownloadStatus<long &,long &>(long &,long &)
0x180056975  test    ebx, ebx
0x180056977  js      short loc_1800569B5
0x180056979  mov     rcx, rdi; this
0x18005697c  call    ?_IsCanceled@CZDPTask@@AEAA_NXZ; CZDPTask::_IsCanceled(void)
0x180056981  test    al, al
0x180056983  jnz     short loc_1800569B5
0x180056985  mov     r8, [rbp+57h+var_68]; struct IUpdateCollection *
0x180056989  mov     rdx, [rbp+57h+var_60]; struct IUpdateSession *
0x18005698d  mov     rcx, rdi; this
0x180056990  call    ?_Install@CZDPTask@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z; CZDPTask::_Install(IUpdateSession *,IUpdateCollection *)
0x180056995  mov     ebx, eax
0x180056997  mov     [rbp+57h+var_70], eax
0x18005699a  mov     ecx, eax
0x18005699c  call    ??$HandleEvent@$05J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<6,long>(long)
0x1800569a1  lea     rdx, [rbp+57h+var_6C]
0x1800569a5  lea     rcx, [rbp+57h+var_70]
0x1800569a9  call    ??$ZdpInstallStatus@AEAJAEAJ@OobeZdpTelemetry@@SAXAEAJ0@Z; OobeZdpTelemetry::ZdpInstallStatus<long &,long &>(long &,long &)
0x1800569ae  jmp     short loc_1800569B5
0x1800569b0  xor     eax, eax
0x1800569b2  mov     [rbp+57h+var_6C], eax
0x1800569b5  lea     rcx, [rbp+57h+var_68]
0x1800569b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800569be  nop
0x1800569bf  lea     rcx, [rbp+57h+var_58]
0x1800569c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800569c8  nop
0x1800569c9  lea     rcx, [rbp+57h+var_48]; this
0x1800569cd  call    ??1AutoExecutionPowerHold@@QEAA@XZ; AutoExecutionPowerHold::~AutoExecutionPowerHold(void)
0x1800569d2  jmp     short loc_1800569E8
0x1800569d4  mov     r8d, eax
0x1800569d7  lea     rdx, aFailedToCreate_6; "Failed to create IUpdateSession [hr=0x%"...
0x1800569de  mov     ecx, 1
0x1800569e3  call    UnattendLogW
0x1800569e8  cmp     ebx, 80004004h
0x1800569ee  jnz     short loc_180056A00
0x1800569f0  lea     rdx, aResettingHresu; "Resetting HRESULT from E_ABORT before r"...
0x1800569f7  xor     ecx, ecx
0x1800569f9  call    UnattendLogW
0x1800569fe  xor     ebx, ebx
0x180056a00  lea     rdx, aCzdptaskSettin; "CZDPTask setting OOBE_GLOBAL_SETTING_ZD"...
0x180056a07  xor     ecx, ecx
0x180056a09  call    UnattendLogW
0x180056a0e  mov     rcx, [rdi+238h]
0x180056a15  xorps   xmm0, xmm0
0x180056a18  xor     eax, eax
0x180056a1a  movups  [rbp+57h+var_48], xmm0
0x180056a1e  mov     [rbp+57h+var_38], rax
0x180056a22  mov     eax, 13h
0x180056a27  mov     word ptr [rbp+57h+var_48], ax
0x180056a2b  mov     dword ptr [rbp+57h+var_48+8], 4
0x180056a32  mov     rax, [rcx]
0x180056a35  lea     r8, [rbp+57h+var_48]
0x180056a39  lea     rdx, aZdpstatus; "ZDPSTATUS"
0x180056a40  mov     rax, [rax+20h]
0x180056a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a49  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x180056a50  jz      short loc_180056A75
0x180056a52  lea     rax, [rbp+57h+var_48]
0x180056a56  mov     [rsp+0A0h+ppv], rax
0x180056a5b  mov     r9d, 1
0x180056a61  lea     rdx, ZdpTask_Stop
0x180056a68  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x180056a6f  call    McGenEventWrite_EventWriteTransfer
0x180056a74  nop
0x180056a75  lea     rcx, [rbp+57h+var_60]
0x180056a79  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056a7e  mov     eax, ebx
0x180056a80  mov     rcx, [rbp+57h+var_30]
0x180056a84  xor     rcx, rsp; StackCookie
0x180056a87  call    __security_check_cookie
0x180056a8c  add     rsp, 88h
0x180056a93  pop     rdi
0x180056a94  pop     rsi
0x180056a95  pop     rbx
0x180056a96  pop     rbp
0x180056a97  retn
```
