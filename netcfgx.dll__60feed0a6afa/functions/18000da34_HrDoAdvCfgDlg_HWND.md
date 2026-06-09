# HrDoAdvCfgDlg(HWND__ *)

- ea: `0x18000da34`
- end: `0x18000ddca`
- name: `?HrDoAdvCfgDlg@@YAJPEAUHWND__@@@Z`
- size: `918`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b6d0`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x180006a2c`
- `0x180007d38`
- `0x18000c4d8`
- `0x18000da34`
- `0x18000f814`
- `0x18000f9bc`
- `0x180010790`
- `0x180011e58`
- `0x18001218c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000db56`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000db56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd62`
- `COMCTL32!PropertySheetW` at `0x18000dc8d`
- `COMCTL32!PropertySheetW` at `0x18000dc8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrDoAdvCfgDlg(HWND hWnd)
{
  HRESULT v2; // ebx
  __int64 (__fastcall *v3)(__int64, _QWORD, const unsigned __int16 *, LPVOID *); // rbx
  const unsigned __int16 *String; // rax
  HRESULT v5; // eax
  LPVOID v6; // rsi
  __int64 v7; // rdi
  _QWORD *v8; // rax
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v12; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v14; // [rsp+28h] [rbp-D8h]
  HINSTANCE v15; // [rsp+30h] [rbp-D0h]
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v17; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v20; // [rsp+98h] [rbp-68h]
  __int64 v21; // [rsp+A0h] [rbp-60h]
  PROPSHEETHEADERW_V2 v22; // [rsp+B0h] [rbp-50h] BYREF
  void **v23; // [rsp+110h] [rbp+10h] BYREF
  int v24; // [rsp+118h] [rbp+18h] BYREF
  char v25; // [rsp+11Ch] [rbp+1Ch]
  int v26; // [rsp+140h] [rbp+40h] BYREF
  const char *v27; // [rsp+148h] [rbp+48h]
  __int64 v28; // [rsp+150h] [rbp+50h]
  char v29; // [rsp+158h] [rbp+58h]
  int v30; // [rsp+160h] [rbp+60h]
  _BYTE v31[152]; // [rsp+168h] [rbp+68h] BYREF
  __int128 v32; // [rsp+200h] [rbp+100h]
  int v33; // [rsp+210h] [rbp+110h]
  __int64 v34; // [rsp+218h] [rbp+118h]
  int *v35; // [rsp+220h] [rbp+120h]
  __int64 v36; // [rsp+228h] [rbp+128h]
  __int64 v37; // [rsp+230h] [rbp+130h]
  void ***v38; // [rsp+238h] [rbp+138h]
  __int64 v39; // [rsp+240h] [rbp+140h]
  int v40; // [rsp+248h] [rbp+148h]
  int *v41; // [rsp+250h] [rbp+150h]
  char v42; // [rsp+258h] [rbp+158h]
  __int128 v43; // [rsp+260h] [rbp+160h] BYREF
  __int64 v44; // [rsp+270h] [rbp+170h]

  memset_0(&v22, 0, sizeof(v22));
  v43 = 0;
  v44 = 0;
  v24 = 0;
  v25 = 0;
  v29 = 0;
  v26 = 0;
  v27 = "LaunchAdvancedProviderOrderSetting";
  v28 = 0;
  v30 = 0;
  v32 = 0;
  memset_0(v31, 0, sizeof(v31));
  v33 = 1;
  v34 = 0;
  v35 = &v24;
  v36 = 0;
  v37 = 0;
  v38 = &v23;
  v39 = 0;
  v40 = 0;
  v41 = &v26;
  v42 = 0;
  v23 = &NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::`vftable';
  NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::StartActivity((NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *)&v23);
  v17 = 0;
  v16 = 0;
  v2 = CoCreateInstance(&CLSID_CNetCfg, 0, 0x401u, &IID_INetCfg, &v17);
  if ( v2 < 0 )
    goto LABEL_11;
  v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v17)(v17, &IID_INetCfgLock, &v16);
  if ( v2 < 0 )
    goto LABEL_11;
  pv[0] = 0;
  v3 = *(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, LPVOID *))(*(_QWORD *)v16 + 24LL);
  String = SzLoadString(hModule, 0x620Cu);
  v5 = v3(v16, 0, String, pv);
  v2 = v5;
  switch ( v5 )
  {
    case 0:
      v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, 0);
      goto LABEL_5;
    case 1:
      v12 = (const unsigned __int16 *)pv[0];
      if ( !pv[0] )
        v12 = SzLoadString(hModule, 0x6210u);
      NcMsgBox(hWnd, 0x620Eu, 0x620Fu, 0x10u, v12);
      CoTaskMemFree(pv[0]);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v2 = -2147467259;
      break;
    case -2147180507:
      NcMsgBox(hWnd, 0x620Eu, 0x6216u, 0x10u);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      break;
    default:
LABEL_5:
      if ( v2 >= 0 )
      {
        v6 = v17;
        v7 = v16;
        v19[1] = 0;
        v19[0] = &CProviderOrderDlg::`vftable';
        v20 = 0;
        v21 = 0;
        v8 = MemAlloc(0x58u);
        *v8 = v8;
        v8[1] = v8;
        v20 = v8;
        memset(&v19[2], 0, 32);
        *(_QWORD *)&v43 = CPropSheetPage::CreatePage(
                            (CPropSheetPage *)v19,
                            0x61B2u,
                            v9,
                            v10,
                            (const unsigned __int16 *)ppv,
                            v14,
                            v15);
        v22.dwSize = 96;
        v22.dwFlags = 33554560;
        v22.hwndParent = hWnd;
        v22.hInstance = hModule;
        v22.pszCaption = SzLoadString(hModule, 0x6214u);
        v22.nPages = 1;
        v22.ppsp = (LPCPROPSHEETPAGEW)&v43;
        PropertySheetW(&v22);
        v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 32LL))(v6);
        if ( v2 >= 0 )
        {
          if ( !v7
            || (v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7),
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7),
                v2 >= 0) )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
          }
        }
        CProviderOrderDlg::~CProviderOrderDlg((CProviderOrderDlg *)v19);
      }
      break;
  }
LABEL_11:
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v23,
    (unsigned int)v2);
  NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::~LaunchAdvancedProviderOrderSetting((NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *)&v23);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000da34  push    rbp
0x18000da36  push    rbx
0x18000da37  push    rsi
0x18000da38  push    rdi
0x18000da39  push    r14
0x18000da3b  push    r15
0x18000da3d  lea     rbp, [rsp-188h]
0x18000da45  sub     rsp, 288h
0x18000da4c  mov     rax, cs:__security_cookie
0x18000da53  xor     rax, rsp
0x18000da56  mov     [rbp+1B0h+var_38], rax
0x18000da5d  mov     r14, rcx
0x18000da60  xor     edx, edx; Val
0x18000da62  lea     r8d, [rdx+60h]; Size
0x18000da66  lea     rcx, [rbp+1B0h+var_200]; void *
0x18000da6a  call    memset_0
0x18000da6f  xorps   xmm0, xmm0
0x18000da72  xor     eax, eax
0x18000da74  movups  [rbp+1B0h+var_50], xmm0
0x18000da7b  mov     [rbp+1B0h+var_40], rax
0x18000da82  xor     r15d, r15d
0x18000da85  mov     [rbp+1B0h+var_198], r15d
0x18000da89  mov     [rbp+1B0h+var_194], r15b
0x18000da8d  mov     [rbp+1B0h+var_158], r15b
0x18000da91  mov     [rbp+1B0h+var_170], r15d
0x18000da95  lea     rax, aLaunchadvanced; "LaunchAdvancedProviderOrderSetting"
0x18000da9c  mov     [rbp+1B0h+var_168], rax
0x18000daa0  mov     [rbp+1B0h+var_160], r15
0x18000daa4  mov     [rbp+1B0h+var_150], r15d
0x18000daa8  movdqa  [rbp+1B0h+var_B0], xmm0
0x18000dab0  xor     edx, edx; Val
0x18000dab2  mov     r8d, 98h; Size
0x18000dab8  lea     rcx, [rbp+1B0h+var_148]; void *
0x18000dabc  call    memset_0
0x18000dac1  mov     [rbp+1B0h+var_A0], 1
0x18000dacb  xor     eax, eax
0x18000dacd  mov     [rbp+1B0h+var_98], rax
0x18000dad4  lea     rax, [rbp+1B0h+var_198]
0x18000dad8  mov     [rbp+1B0h+var_90], rax
0x18000dadf  mov     [rbp+1B0h+var_88], r15
0x18000dae6  mov     [rbp+1B0h+var_80], r15
0x18000daed  lea     rax, [rbp+1B0h+var_1A0]
0x18000daf1  mov     [rbp+1B0h+var_78], rax
0x18000daf8  mov     [rbp+1B0h+var_70], r15
0x18000daff  mov     [rbp+1B0h+var_68], r15d
0x18000db06  lea     rax, [rbp+1B0h+var_170]
0x18000db0a  mov     [rbp+1B0h+var_60], rax
0x18000db11  mov     [rbp+1B0h+var_58], r15b
0x18000db18  lea     rax, ??_7LaunchAdvancedProviderOrderSetting@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::`vftable'
0x18000db1f  mov     [rbp+1B0h+var_1A0], rax
0x18000db23  lea     rcx, [rbp+1B0h+var_1A0]; this
0x18000db27  call    ?StartActivity@LaunchAdvancedProviderOrderSetting@NetworkLegacyUxTelemetry@@QEAAXXZ; NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::StartActivity(void)
0x18000db2c  mov     [rsp+2B0h+var_268], r15
0x18000db31  mov     [rsp+2B0h+var_270], r15
0x18000db36  lea     rax, [rsp+2B0h+var_268]
0x18000db3b  mov     [rsp+2B0h+ppv], rax; unsigned __int16 *
0x18000db40  lea     r9, IID_INetCfg; riid
0x18000db47  xor     edx, edx; pUnkOuter
0x18000db49  mov     r8d, 401h; dwClsContext
0x18000db4f  lea     rcx, CLSID_CNetCfg; rclsid
0x18000db56  call    cs:__imp_CoCreateInstance
0x18000db5c  mov     ebx, eax
0x18000db5e  test    eax, eax
0x18000db60  js      loc_18000DCEB
0x18000db66  mov     rcx, [rsp+2B0h+var_268]
0x18000db6b  mov     rax, [rcx]
0x18000db6e  lea     r8, [rsp+2B0h+var_270]
0x18000db73  lea     rdx, IID_INetCfgLock
0x18000db7a  mov     rax, [rax]
0x18000db7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db82  mov     ebx, eax
0x18000db84  test    eax, eax
0x18000db86  js      loc_18000DCEB
0x18000db8c  mov     [rsp+2B0h+pv], r15
0x18000db91  mov     rax, [rsp+2B0h+var_270]
0x18000db96  mov     rcx, [rax]
0x18000db99  mov     rbx, [rcx+18h]
0x18000db9d  mov     edx, 620Ch; unsigned int
0x18000dba2  mov     rcx, cs:hModule; hModule
0x18000dba9  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x18000dbae  lea     r9, [rsp+2B0h+pv]
0x18000dbb3  mov     r8, rax
0x18000dbb6  xor     edx, edx
0x18000dbb8  mov     rcx, [rsp+2B0h+var_270]
0x18000dbbd  mov     rax, rbx
0x18000dbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc5  mov     ebx, eax
0x18000dbc7  test    eax, eax
0x18000dbc9  jnz     loc_18000DD21
0x18000dbcf  mov     rcx, [rsp+2B0h+var_268]
0x18000dbd4  mov     rax, [rcx]
0x18000dbd7  xor     edx, edx
0x18000dbd9  mov     rax, [rax+18h]
0x18000dbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbe2  mov     ebx, eax
0x18000dbe4  test    ebx, ebx
0x18000dbe6  js      loc_18000DCEB
0x18000dbec  mov     rsi, [rsp+2B0h+var_268]
0x18000dbf1  mov     rdi, [rsp+2B0h+var_270]
0x18000dbf6  mov     [rsp+2B0h+var_248], r15
0x18000dbfb  lea     rax, ??_7CProviderOrderDlg@@6B@; const CProviderOrderDlg::`vftable'
0x18000dc02  mov     [rsp+2B0h+var_250], rax
0x18000dc07  mov     [rbp+1B0h+var_218], r15
0x18000dc0b  mov     [rbp+1B0h+var_210], r15
0x18000dc0f  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000dc14  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000dc19  mov     [rax], rax
0x18000dc1c  mov     [rax+8], rax
0x18000dc20  mov     [rbp+1B0h+var_218], rax
0x18000dc24  mov     [rsp+2B0h+var_238], r15
0x18000dc29  mov     [rsp+2B0h+var_240], r15
0x18000dc2e  mov     [rbp+1B0h+var_228], r15
0x18000dc32  mov     [rbp+1B0h+var_230], r15
0x18000dc36  mov     edx, 61B2h; unsigned int
0x18000dc3b  lea     rcx, [rsp+2B0h+var_250]; this
0x18000dc40  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *)
0x18000dc45  mov     qword ptr [rbp+1B0h+var_50], rax
0x18000dc4c  mov     [rbp+1B0h+var_200.dwSize], 60h ; '`'
0x18000dc53  mov     [rbp+1B0h+var_200.dwFlags], 2000080h
0x18000dc5a  mov     [rbp+1B0h+var_200.hwndParent], r14
0x18000dc5e  mov     rcx, cs:hModule; hModule
0x18000dc65  mov     [rbp+1B0h+var_200.hInstance], rcx
0x18000dc69  mov     edx, 6214h; unsigned int
0x18000dc6e  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x18000dc73  mov     [rbp+1B0h+var_200.pszCaption], rax
0x18000dc77  mov     [rbp+1B0h+var_200.nPages], 1
0x18000dc7e  lea     rax, [rbp+1B0h+var_50]
0x18000dc85  mov     qword ptr [rbp+1B0h+var_200.38h], rax
0x18000dc89  lea     rcx, [rbp+1B0h+var_200]; LPCPROPSHEETHEADERW
0x18000dc8d  call    cs:__imp_PropertySheetW
0x18000dc93  mov     rax, [rsi]
0x18000dc96  mov     rcx, rsi
0x18000dc99  mov     rax, [rax+20h]
0x18000dc9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dca2  mov     ebx, eax
0x18000dca4  test    eax, eax
0x18000dca6  js      short loc_18000DCE1
0x18000dca8  test    rdi, rdi
0x18000dcab  jz      short loc_18000DCD1
0x18000dcad  mov     rax, [rdi]
0x18000dcb0  mov     rcx, rdi
0x18000dcb3  mov     rax, [rax+20h]
0x18000dcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcbc  mov     ebx, eax
0x18000dcbe  mov     rax, [rdi]
0x18000dcc1  mov     rcx, rdi
0x18000dcc4  mov     rax, [rax+10h]
0x18000dcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dccd  test    ebx, ebx
0x18000dccf  js      short loc_18000DCE1
0x18000dcd1  mov     rax, [rsi]
0x18000dcd4  mov     rcx, rsi
0x18000dcd7  mov     rax, [rax+10h]
0x18000dcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce0  nop
0x18000dce1  lea     rcx, [rsp+2B0h+var_250]; this
0x18000dce6  call    ??1CProviderOrderDlg@@UEAA@XZ; CProviderOrderDlg::~CProviderOrderDlg(void)
0x18000dceb  mov     edx, ebx
0x18000dced  lea     rcx, [rbp+1B0h+var_1A0]
0x18000dcf1  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000dcf6  nop
0x18000dcf7  lea     rcx, [rbp+1B0h+var_1A0]; this
0x18000dcfb  call    ??1LaunchAdvancedProviderOrderSetting@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::~LaunchAdvancedProviderOrderSetting(void)
0x18000dd00  mov     eax, ebx
0x18000dd02  mov     rcx, [rbp+1B0h+var_38]
0x18000dd09  xor     rcx, rsp; StackCookie
0x18000dd0c  call    __security_check_cookie
0x18000dd11  add     rsp, 288h
0x18000dd18  pop     r15
0x18000dd1a  pop     r14
0x18000dd1c  pop     rdi
0x18000dd1d  pop     rsi
0x18000dd1e  pop     rbx
0x18000dd1f  pop     rbp
0x18000dd20  retn
0x18000dd21  cmp     eax, 1
0x18000dd24  jnz     short loc_18000DD88
0x18000dd26  mov     rax, [rsp+2B0h+pv]
0x18000dd2b  test    rax, rax
0x18000dd2e  jnz     short loc_18000DD41
0x18000dd30  mov     edx, 6210h; unsigned int
0x18000dd35  mov     rcx, cs:hModule; hModule
0x18000dd3c  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x18000dd41  mov     [rsp+2B0h+ppv], rax
0x18000dd46  mov     edx, 620Eh; unsigned int
0x18000dd4b  mov     r9d, 10h; unsigned int
0x18000dd51  lea     r8d, [rdx+1]; unsigned int
0x18000dd55  mov     rcx, r14; hWnd
0x18000dd58  call    ?NcMsgBox@@YAHPEAUHWND__@@IIIZZ; NcMsgBox(HWND__ *,uint,uint,uint,...)
0x18000dd5d  mov     rcx, [rsp+2B0h+pv]; pv
0x18000dd62  call    cs:__imp_CoTaskMemFree
0x18000dd68  mov     rcx, [rsp+2B0h+var_270]
0x18000dd6d  test    rcx, rcx
0x18000dd70  jz      short loc_18000DD7E
0x18000dd72  mov     rax, [rcx]
0x18000dd75  mov     rax, [rax+10h]
0x18000dd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd7e  mov     ebx, 80004005h
0x18000dd83  jmp     loc_18000DCEB
0x18000dd88  cmp     eax, 8004A025h
0x18000dd8d  jnz     loc_18000DBE4
0x18000dd93  mov     edx, 620Eh; unsigned int
0x18000dd98  mov     r9d, 10h; unsigned int
0x18000dd9e  lea     r8d, [rdx+8]; unsigned int
0x18000dda2  mov     rcx, r14; hWnd
0x18000dda5  call    ?NcMsgBox@@YAHPEAUHWND__@@IIIZZ; NcMsgBox(HWND__ *,uint,uint,uint,...)
0x18000ddaa  mov     rcx, [rsp+2B0h+var_270]
0x18000ddaf  test    rcx, rcx
0x18000ddb2  jz      loc_18000DCEB
0x18000ddb8  mov     rax, [rcx]
0x18000ddbb  mov     rax, [rax+10h]
0x18000ddbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddc4  jmp     loc_18000DCEB
```
