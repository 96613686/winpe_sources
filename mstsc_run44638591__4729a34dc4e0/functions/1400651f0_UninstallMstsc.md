# UninstallMstsc

- ea: `0x1400651f0`
- end: `0x1400657b5`
- name: `UninstallMstsc`
- size: `1477`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14006590c`

## callees

- `0x140004703`
- `0x140006aec`
- `0x140006de0`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400626a4`
- `0x1400626c8`
- `0x140062750`
- `0x1400633cc`
- `0x1400651f0`
- `0x140065820`
- `0x14010cb10`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006562a`
- `KERNEL32!GetLastError` at `0x1400656ac`
- `KERNEL32!GetLastError` at `0x140065707`
- `KERNEL32!GetLastError` at `0x14006562a`
- `KERNEL32!GetLastError` at `0x1400656ac`
- `KERNEL32!GetLastError` at `0x140065707`
- `COMCTL32!TaskDialogIndirect` at `0x14006550a`
- `COMCTL32!TaskDialogIndirect` at `0x14006550a`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140065620`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140065620`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1400656a2`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1400656a2`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x1400656fd`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x1400656fd`
- `DismApi!DismOpenSession` at `0x14006537d`
- `DismApi!DismOpenSession` at `0x14006537d`
- `DismApi!DismInitialize` at `0x1400652c9`
- `DismApi!DismInitialize` at `0x1400652c9`
- `DismApi!DismDisableFeature` at `0x140065443`
- `DismApi!DismDisableFeature` at `0x140065443`
- `DismApi!DismCloseSession` at `0x14006534c`
- `DismApi!DismShutdown` at `0x140065786`
- `DismApi!DismShutdown` at `0x140065786`

## string_xrefs

- `0x1400653b2`: `DismOpenSession failed`
- `0x140065406`: `GetOptionalComponentInfoForMstsc failed`
- `0x140065546`: `TaskDialogIndirect failed`
- `0x1400655de`: `open_current_access_token_nothrow failed`
- `0x140065619`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall UninstallMstsc(HINSTANCE a1, char a2)
{
  int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  char v6; // di
  int OptionalComponentInfoForMstsc; // ebx
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned int v11; // edx
  struct TsClientOptionalComponent::OptionalComponentInfo *v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rdx
  bool v17; // sf
  TsClientOptionalComponent *v19; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TokenHandle[2]; // [rsp+48h] [rbp-B8h] BYREF
  int pnButton; // [rsp+58h] [rbp-A8h] BYREF
  _LUID Luid; // [rsp+60h] [rbp-A0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+70h] [rbp-90h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+110h] [rbp+10h] BYREF
  bool v25[522]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v26[534]; // [rsp+32Ah] [rbp+22Ah] BYREF

  LODWORD(v19) = 0;
  memset_0(v25, 0, sizeof(v25));
  memset_0(v26, 0, 0x20Au);
  *(_OWORD *)TokenHandle = 0;
  v4 = ProgressDialogHelper::Initialize((ProgressDialogHelper *)TokenHandle, a1);
  if ( v4 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"Initializing the progress dialog failed",
      v4);
  }
  v6 = 1;
  OptionalComponentInfoForMstsc = DismInitialize(1, 0, 0);
  if ( OptionalComponentInfoForMstsc < 0 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 53;
    v10 = "DismInitialize failed";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
      v8,
      (__int64)v10,
      OptionalComponentInfoForMstsc);
LABEL_12:
    ProgressDialogHelper::~ProgressDialogHelper((ProgressDialogHelper *)TokenHandle);
    goto LABEL_62;
  }
  LODWORD(v19) = 0;
  OptionalComponentInfoForMstsc = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v19);
  if ( OptionalComponentInfoForMstsc < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 54;
    v10 = "DismOpenSession failed";
    goto LABEL_11;
  }
  OptionalComponentInfoForMstsc = TsClientOptionalComponent::GetOptionalComponentInfoForMstsc(
                                    (TsClientOptionalComponent *)(unsigned int)v19,
                                    v11,
                                    (bool)v25,
                                    v12);
  if ( OptionalComponentInfoForMstsc < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 55;
    v10 = "GetOptionalComponentInfoForMstsc failed";
    goto LABEL_11;
  }
  OptionalComponentInfoForMstsc = DismDisableFeature(
                                    (unsigned int)v19,
                                    v26,
                                    v25,
                                    0,
                                    0,
                                    ProgressDialogHelper::ProgressCallback,
                                    TokenHandle);
  if ( OptionalComponentInfoForMstsc < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 56;
    v10 = "DismDisableFeature failed";
    goto LABEL_11;
  }
  ProgressDialogHelper::~ProgressDialogHelper((ProgressDialogHelper *)TokenHandle);
  if ( OptionalComponentInfoForMstsc == 3010 )
  {
    pnButton = 0;
    if ( a2 )
    {
      memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
      pTaskConfig.cbSize = 160;
      pTaskConfig.hInstance = a1;
      pTaskConfig.dwFlags = 0x1000000;
      pTaskConfig.pszWindowTitle = (PCWSTR)1004;
      pTaskConfig.pszContent = (PCWSTR)30002;
      pTaskConfig.dwCommonButtons = 6;
      pTaskConfig.hMainIcon = (HICON)0xFFFF;
      OptionalComponentInfoForMstsc = TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
      if ( OptionalComponentInfoForMstsc < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
            v13,
            (__int64)"TaskDialogIndirect failed",
            OptionalComponentInfoForMstsc);
        }
        goto LABEL_62;
      }
      if ( pnButton != 6 )
        goto LABEL_62;
    }
    Luid = 0;
    TokenHandle[0] = 0;
    NewState = 0;
    OptionalComponentInfoForMstsc = wil::open_current_access_token_nothrow(TokenHandle);
    if ( OptionalComponentInfoForMstsc < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
          v14,
          (__int64)"open_current_access_token_nothrow failed",
          OptionalComponentInfoForMstsc);
      }
      goto LABEL_61;
    }
    if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid) )
    {
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      if ( AdjustTokenPrivileges(TokenHandle[0], 0, &NewState, 0x10u, 0, 0) )
      {
        if ( InitiateSystemShutdownExW(0, 0, 0, 0, 1, 0x80040002) )
        {
LABEL_61:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
          goto LABEL_62;
        }
        OptionalComponentInfoForMstsc = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_57:
          v17 = OptionalComponentInfoForMstsc < 0;
          if ( OptionalComponentInfoForMstsc > 0 )
          {
            OptionalComponentInfoForMstsc = (unsigned __int16)OptionalComponentInfoForMstsc | 0x80070000;
            v17 = OptionalComponentInfoForMstsc < 0;
          }
          if ( !v17 )
            OptionalComponentInfoForMstsc = -2147467259;
          goto LABEL_61;
        }
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 61;
      }
      else
      {
        OptionalComponentInfoForMstsc = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 60;
      }
    }
    else
    {
      OptionalComponentInfoForMstsc = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_57;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 59;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
      v15,
      OptionalComponentInfoForMstsc);
    goto LABEL_57;
  }
LABEL_62:
  wil::details::unique_storage<wil::details::resource_policy<unsigned int,long (unsigned int),&long DismCloseSession(unsigned int),wistd::integral_constant<unsigned __int64,0>,unsigned int,unsigned int,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned int,long (unsigned int),&long DismCloseSession(unsigned int),wistd::integral_constant<unsigned __int64,0>,unsigned int,unsigned int,0,std::nullptr_t>>(&v19);
  if ( v6 )
    DismShutdown();
  return (unsigned int)OptionalComponentInfoForMstsc;
}

```

## disassembly

```asm
0x1400651f0  mov     [rsp-8+arg_8], rbx
0x1400651f5  mov     [rsp-8+arg_10], rsi
0x1400651fa  push    rbp
0x1400651fb  push    rdi
0x1400651fc  push    r14
0x1400651fe  lea     rbp, [rsp-450h]
0x140065206  sub     rsp, 550h
0x14006520d  mov     rax, cs:__security_cookie
0x140065214  xor     rax, rsp
0x140065217  mov     [rbp+460h+var_20], rax
0x14006521e  mov     sil, dl
0x140065221  mov     dword ptr [rsp+560h+var_520], 0
0x140065229  mov     r14, rcx
0x14006522c  mov     ebx, 20Ah
0x140065231  mov     r8d, ebx; Size
0x140065234  lea     rcx, [rbp+460h+var_440]; void *
0x140065238  xor     edx, edx; Val
0x14006523a  call    memset_0
0x14006523f  mov     r8d, ebx; Size
0x140065242  lea     rcx, [rbp+460h+var_236]; void *
0x140065249  xor     edx, edx; Val
0x14006524b  call    memset_0
0x140065250  xorps   xmm0, xmm0
0x140065253  lea     rcx, [rsp+560h+TokenHandle]; this
0x140065258  mov     rdx, r14; HINSTANCE
0x14006525b  movdqu  xmmword ptr [rsp+560h+TokenHandle], xmm0
0x140065261  call    ?Initialize@ProgressDialogHelper@@QEAAJPEAUHINSTANCE__@@@Z; ProgressDialogHelper::Initialize(HINSTANCE__ *)
0x140065266  mov     ebx, eax
0x140065268  lea     rax, WPP_GLOBAL_Control
0x14006526f  test    ebx, ebx
0x140065271  jns     short loc_1400652BF
0x140065273  mov     rcx, cs:WPP_GLOBAL_Control
0x14006527a  cmp     rcx, rax
0x14006527d  jz      short loc_1400652BF
0x14006527f  test    byte ptr [rcx+1Ch], 8
0x140065283  jz      short loc_1400652BF
0x140065285  cmp     byte ptr [rcx+19h], 2
0x140065289  jb      short loc_1400652BF
0x14006528b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140065290  lea     rcx, aInitializingTh; "Initializing the progress dialog failed"
0x140065297  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x14006529b  mov     [rsp+560h+PreviousState], rcx
0x1400652a0  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400652a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400652ae  mov     edx, 34h ; '4'
0x1400652b3  mov     r9d, eax
0x1400652b6  mov     rcx, [rcx+10h]
0x1400652ba  call    WPP_SF_DsD
0x1400652bf  xor     edx, edx
0x1400652c1  xor     r8d, r8d
0x1400652c4  lea     edi, [rdx+1]
0x1400652c7  mov     ecx, edi
0x1400652c9  call    cs:__imp_DismInitialize
0x1400652cf  mov     ebx, eax
0x1400652d1  test    eax, eax
0x1400652d3  jns     short loc_14006533A
0x1400652d5  xor     dil, dil
0x1400652d8  mov     rax, cs:WPP_GLOBAL_Control
0x1400652df  lea     rcx, WPP_GLOBAL_Control
0x1400652e6  cmp     rax, rcx
0x1400652e9  jz      short loc_14006532B
0x1400652eb  test    byte ptr [rax+1Ch], 8
0x1400652ef  jz      short loc_14006532B
0x1400652f1  cmp     byte ptr [rax+19h], 2
0x1400652f5  jb      short loc_14006532B
0x1400652f7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400652fc  mov     edx, 35h ; '5'
0x140065301  lea     rcx, aDisminitialize_0; "DismInitialize failed"
0x140065308  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x14006530c  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140065313  mov     [rsp+560h+PreviousState], rcx
0x140065318  mov     r9d, eax
0x14006531b  mov     rcx, cs:WPP_GLOBAL_Control
0x140065322  mov     rcx, [rcx+10h]
0x140065326  call    WPP_SF_DsD
0x14006532b  lea     rcx, [rsp+560h+TokenHandle]; this
0x140065330  call    ??1ProgressDialogHelper@@QEAA@XZ; ProgressDialogHelper::~ProgressDialogHelper(void)
0x140065335  jmp     loc_140065777
0x14006533a  mov     ebx, dword ptr [rsp+560h+var_520]
0x14006533e  test    ebx, ebx
0x140065340  jz      short loc_140065364
0x140065342  lea     rcx, [rsp+560h+Luid]; this
0x140065347  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14006534c  mov     rax, cs:__imp_DismCloseSession
0x140065353  mov     ecx, ebx
0x140065355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006535a  lea     rcx, [rsp+560h+Luid]; this
0x14006535f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140065364  lea     r9, [rsp+560h+var_520]
0x140065369  mov     dword ptr [rsp+560h+var_520], 0
0x140065371  xor     r8d, r8d
0x140065374  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x14006537b  xor     edx, edx
0x14006537d  call    cs:__imp_DismOpenSession
0x140065383  mov     ebx, eax
0x140065385  test    eax, eax
0x140065387  jns     short loc_1400653BE
0x140065389  mov     rax, cs:WPP_GLOBAL_Control
0x140065390  lea     rcx, WPP_GLOBAL_Control
0x140065397  cmp     rax, rcx
0x14006539a  jz      short loc_14006532B
0x14006539c  test    byte ptr [rax+1Ch], 8
0x1400653a0  jz      short loc_14006532B
0x1400653a2  cmp     byte ptr [rax+19h], 2
0x1400653a6  jb      short loc_14006532B
0x1400653a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400653ad  mov     edx, 36h ; '6'
0x1400653b2  lea     rcx, aDismopensessio_0; "DismOpenSession failed"
0x1400653b9  jmp     loc_140065308
0x1400653be  mov     ecx, dword ptr [rsp+560h+var_520]; this
0x1400653c2  lea     r8, [rbp+460h+var_440]; bool
0x1400653c6  call    ?GetOptionalComponentInfoForMstsc@TsClientOptionalComponent@@YAJI_NAEAUOptionalComponentInfo@1@@Z; TsClientOptionalComponent::GetOptionalComponentInfoForMstsc(uint,bool,TsClientOptionalComponent::OptionalComponentInfo &)
0x1400653cb  mov     ebx, eax
0x1400653cd  test    eax, eax
0x1400653cf  jns     short loc_140065412
0x1400653d1  mov     rax, cs:WPP_GLOBAL_Control
0x1400653d8  lea     rcx, WPP_GLOBAL_Control
0x1400653df  cmp     rax, rcx
0x1400653e2  jz      loc_14006532B
0x1400653e8  test    byte ptr [rax+1Ch], 8
0x1400653ec  jz      loc_14006532B
0x1400653f2  cmp     byte ptr [rax+19h], 2
0x1400653f6  jb      loc_14006532B
0x1400653fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140065401  mov     edx, 37h ; '7'
0x140065406  lea     rcx, aGetoptionalcom; "GetOptionalComponentInfoForMstsc failed"
0x14006540d  jmp     loc_140065308
0x140065412  mov     ecx, dword ptr [rsp+560h+var_520]
0x140065416  lea     rax, [rsp+560h+TokenHandle]
0x14006541b  mov     [rsp+560h+var_530], rax
0x140065420  lea     r8, [rbp+460h+var_440]
0x140065424  lea     rax, ?ProgressCallback@ProgressDialogHelper@@SAXIIPEAX@Z; ProgressDialogHelper::ProgressCallback(uint,uint,void *)
0x14006542b  xor     r9d, r9d
0x14006542e  mov     [rsp+560h+ReturnLength], rax
0x140065433  lea     rdx, [rbp+460h+var_236]
0x14006543a  mov     [rsp+560h+PreviousState], 0
0x140065443  call    cs:__imp_DismDisableFeature
0x140065449  mov     ebx, eax
0x14006544b  test    eax, eax
0x14006544d  jns     short loc_140065490
0x14006544f  mov     rax, cs:WPP_GLOBAL_Control
0x140065456  lea     rcx, WPP_GLOBAL_Control
0x14006545d  cmp     rax, rcx
0x140065460  jz      loc_14006532B
0x140065466  test    byte ptr [rax+1Ch], 8
0x14006546a  jz      loc_14006532B
0x140065470  cmp     byte ptr [rax+19h], 2
0x140065474  jb      loc_14006532B
0x14006547a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006547f  mov     edx, 38h ; '8'
0x140065484  lea     rcx, aDismdisablefea_0; "DismDisableFeature failed"
0x14006548b  jmp     loc_140065308
0x140065490  lea     rcx, [rsp+560h+TokenHandle]; this
0x140065495  call    ??1ProgressDialogHelper@@QEAA@XZ; ProgressDialogHelper::~ProgressDialogHelper(void)
0x14006549a  cmp     ebx, 0BC2h
0x1400654a0  jnz     loc_140065777
0x1400654a6  mov     [rsp+560h+pnButton], 0
0x1400654ae  test    sil, sil
0x1400654b1  jz      loc_140065585
0x1400654b7  mov     ebx, 0A0h
0x1400654bc  lea     rcx, [rsp+560h+pTaskConfig]; void *
0x1400654c1  mov     r8d, ebx; Size
0x1400654c4  xor     edx, edx; Val
0x1400654c6  call    memset_0
0x1400654cb  xor     r9d, r9d; pfVerificationFlagChecked
0x1400654ce  mov     [rsp+560h+pTaskConfig.cbSize], ebx
0x1400654d2  xor     r8d, r8d; pnRadioButton
0x1400654d5  mov     [rsp+560h+pTaskConfig.hInstance], r14
0x1400654da  lea     rdx, [rsp+560h+pnButton]; pnButton
0x1400654df  mov     [rbp+460h+pTaskConfig.dwFlags], 1000000h
0x1400654e6  lea     rcx, [rsp+560h+pTaskConfig]; pTaskConfig
0x1400654eb  mov     [rbp+460h+pTaskConfig.pszWindowTitle], 3ECh
0x1400654f3  mov     [rbp+460h+pTaskConfig.pszContent], 7532h
0x1400654fb  mov     [rbp+460h+pTaskConfig.dwCommonButtons], 6
0x140065502  mov     qword ptr [rbp+460h+pTaskConfig.24h], 0FFFFh
0x14006550a  call    cs:__imp_TaskDialogIndirect
0x140065510  mov     ebx, eax
0x140065512  test    eax, eax
0x140065514  jns     short loc_14006557A
0x140065516  mov     rax, cs:WPP_GLOBAL_Control
0x14006551d  lea     rcx, WPP_GLOBAL_Control
0x140065524  cmp     rax, rcx
0x140065527  jz      loc_140065777
0x14006552d  test    byte ptr [rax+1Ch], 8
0x140065531  jz      loc_140065777
0x140065537  cmp     byte ptr [rax+19h], 2
0x14006553b  jb      loc_140065777
0x140065541  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140065546  lea     rcx, aTaskdialogindi_0; "TaskDialogIndirect failed"
0x14006554d  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x140065551  mov     [rsp+560h+PreviousState], rcx
0x140065556  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x14006555d  mov     rcx, cs:WPP_GLOBAL_Control
0x140065564  mov     edx, 39h ; '9'
0x140065569  mov     r9d, eax
0x14006556c  mov     rcx, [rcx+10h]
0x140065570  call    WPP_SF_DsD
0x140065575  jmp     loc_140065777
0x14006557a  cmp     [rsp+560h+pnButton], 6
0x14006557f  jnz     loc_140065777
0x140065585  xorps   xmm0, xmm0
0x140065588  mov     qword ptr [rsp+560h+Luid.LowPart], 0
0x140065591  lea     rcx, [rsp+560h+TokenHandle]
0x140065596  mov     [rsp+560h+TokenHandle], 0
0x14006559f  movups  xmmword ptr [rbp+460h+NewState.PrivilegeCount], xmm0
0x1400655a3  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x1400655a8  mov     ebx, eax
0x1400655aa  test    eax, eax
0x1400655ac  jns     short loc_140065612
0x1400655ae  mov     rax, cs:WPP_GLOBAL_Control
0x1400655b5  lea     rcx, WPP_GLOBAL_Control
0x1400655bc  cmp     rax, rcx
0x1400655bf  jz      loc_14006576D
0x1400655c5  test    byte ptr [rax+1Ch], 8
0x1400655c9  jz      loc_14006576D
0x1400655cf  cmp     byte ptr [rax+19h], 2
0x1400655d3  jb      loc_14006576D
0x1400655d9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400655de  lea     rcx, aOpenCurrentAcc; "open_current_access_token_nothrow faile"...
0x1400655e5  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x1400655e9  mov     [rsp+560h+PreviousState], rcx
0x1400655ee  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400655f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400655fc  mov     edx, 3Ah ; ':'
0x140065601  mov     r9d, eax
0x140065604  mov     rcx, [rcx+10h]
0x140065608  call    WPP_SF_DsD
0x14006560d  jmp     loc_14006576D
0x140065612  lea     r8, [rsp+560h+Luid]; lpLuid
0x140065617  xor     ecx, ecx; lpSystemName
0x140065619  lea     rdx, Name; "SeShutdownPrivilege"
0x140065620  call    cs:__imp_LookupPrivilegeValueW
0x140065626  test    eax, eax
0x140065628  jnz     short loc_14006566C
0x14006562a  call    cs:__imp_GetLastError
0x140065630  mov     ebx, eax
0x140065632  mov     rax, cs:WPP_GLOBAL_Control
0x140065639  lea     rcx, WPP_GLOBAL_Control
0x140065640  cmp     rax, rcx
0x140065643  jz      loc_140065756
0x140065649  test    byte ptr [rax+1Ch], 8
0x14006564d  jz      loc_140065756
0x140065653  cmp     byte ptr [rax+19h], 2
0x140065657  jb      loc_140065756
0x14006565d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140065662  mov     edx, 3Bh ; ';'
0x140065667  jmp     loc_140065738
0x14006566c  mov     rax, qword ptr [rsp+560h+Luid.LowPart]
0x140065671  lea     r8, [rbp+460h+NewState]; NewState
0x140065675  mov     rcx, [rsp+560h+TokenHandle]; TokenHandle
0x14006567a  mov     r9d, 10h; BufferLength
0x140065680  mov     [rsp+560h+ReturnLength], 0; ReturnLength
0x140065689  xor     edx, edx; DisableAllPrivileges
0x14006568b  mov     qword ptr [rbp+460h+NewState.Privileges.Luid.LowPart], rax
0x14006568f  mov     [rbp+460h+NewState.PrivilegeCount], edi
0x140065692  mov     [rbp+460h+NewState.Privileges.Attributes], 2
0x140065699  mov     [rsp+560h+PreviousState], 0; PreviousState
0x1400656a2  call    cs:__imp_AdjustTokenPrivileges
0x1400656a8  test    eax, eax
0x1400656aa  jnz     short loc_1400656E7
0x1400656ac  call    cs:__imp_GetLastError
0x1400656b2  mov     ebx, eax
0x1400656b4  mov     rax, cs:WPP_GLOBAL_Control
0x1400656bb  lea     rcx, WPP_GLOBAL_Control
0x1400656c2  cmp     rax, rcx
0x1400656c5  jz      loc_140065756
0x1400656cb  test    byte ptr [rax+1Ch], 8
0x1400656cf  jz      loc_140065756
0x1400656d5  cmp     byte ptr [rax+19h], 2
0x1400656d9  jb      short loc_140065756
0x1400656db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400656e0  mov     edx, 3Ch ; '<'
0x1400656e5  jmp     short loc_140065738
0x1400656e7  mov     dword ptr [rsp+560h+ReturnLength], 80040002h; dwReason
0x1400656ef  xor     r9d, r9d; bForceAppsClosed
0x1400656f2  xor     r8d, r8d; dwTimeout
0x1400656f5  mov     dword ptr [rsp+560h+PreviousState], edi; bRebootAfterShutdown
0x1400656f9  xor     edx, edx; lpMessage
0x1400656fb  xor     ecx, ecx; lpMachineName
0x1400656fd  call    cs:__imp_InitiateSystemShutdownExW
0x140065703  test    eax, eax
0x140065705  jnz     short loc_14006576D
0x140065707  call    cs:__imp_GetLastError
0x14006570d  mov     ebx, eax
0x14006570f  mov     rax, cs:WPP_GLOBAL_Control
0x140065716  lea     rcx, WPP_GLOBAL_Control
0x14006571d  cmp     rax, rcx
0x140065720  jz      short loc_140065756
0x140065722  test    byte ptr [rax+1Ch], 8
0x140065726  jz      short loc_140065756
0x140065728  cmp     byte ptr [rax+19h], 2
0x14006572c  jb      short loc_140065756
0x14006572e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140065733  mov     edx, 3Dh ; '='
0x140065738  mov     rcx, cs:WPP_GLOBAL_Control
0x14006573f  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140065746  mov     r9d, eax
0x140065749  mov     dword ptr [rsp+560h+PreviousState], ebx
0x14006574d  mov     rcx, [rcx+10h]
0x140065751  call    WPP_SF_Dd
  ... truncated ...
```
