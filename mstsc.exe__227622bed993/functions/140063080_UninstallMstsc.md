# UninstallMstsc

- ea: `0x140063080`
- end: `0x140063645`
- name: `UninstallMstsc`
- size: `1477`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14006379c`

## callees

- `0x140004703`
- `0x140006aec`
- `0x140006de0`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x140060534`
- `0x140060558`
- `0x1400605e0`
- `0x14006125c`
- `0x140063080`
- `0x1400636b0`
- `0x14010a9a0`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400634ba`
- `KERNEL32!GetLastError` at `0x14006353c`
- `KERNEL32!GetLastError` at `0x140063597`
- `KERNEL32!GetLastError` at `0x1400634ba`
- `KERNEL32!GetLastError` at `0x14006353c`
- `KERNEL32!GetLastError` at `0x140063597`
- `COMCTL32!TaskDialogIndirect` at `0x14006339a`
- `COMCTL32!TaskDialogIndirect` at `0x14006339a`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1400634b0`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1400634b0`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140063532`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140063532`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x14006358d`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x14006358d`
- `DismApi!DismOpenSession` at `0x14006320d`
- `DismApi!DismOpenSession` at `0x14006320d`
- `DismApi!DismInitialize` at `0x140063159`
- `DismApi!DismInitialize` at `0x140063159`
- `DismApi!DismDisableFeature` at `0x1400632d3`
- `DismApi!DismDisableFeature` at `0x1400632d3`
- `DismApi!DismCloseSession` at `0x1400631dc`
- `DismApi!DismShutdown` at `0x140063616`
- `DismApi!DismShutdown` at `0x140063616`

## string_xrefs

- `0x140063242`: `DismOpenSession failed`
- `0x140063296`: `GetOptionalComponentInfoForMstsc failed`
- `0x1400633d6`: `TaskDialogIndirect failed`
- `0x14006346e`: `open_current_access_token_nothrow failed`
- `0x1400634a9`: `SeShutdownPrivilege`

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
0x140063080  mov     [rsp-8+arg_8], rbx
0x140063085  mov     [rsp-8+arg_10], rsi
0x14006308a  push    rbp
0x14006308b  push    rdi
0x14006308c  push    r14
0x14006308e  lea     rbp, [rsp-450h]
0x140063096  sub     rsp, 550h
0x14006309d  mov     rax, cs:__security_cookie
0x1400630a4  xor     rax, rsp
0x1400630a7  mov     [rbp+460h+var_20], rax
0x1400630ae  mov     sil, dl
0x1400630b1  mov     dword ptr [rsp+560h+var_520], 0
0x1400630b9  mov     r14, rcx
0x1400630bc  mov     ebx, 20Ah
0x1400630c1  mov     r8d, ebx; Size
0x1400630c4  lea     rcx, [rbp+460h+var_440]; void *
0x1400630c8  xor     edx, edx; Val
0x1400630ca  call    memset_0
0x1400630cf  mov     r8d, ebx; Size
0x1400630d2  lea     rcx, [rbp+460h+var_236]; void *
0x1400630d9  xor     edx, edx; Val
0x1400630db  call    memset_0
0x1400630e0  xorps   xmm0, xmm0
0x1400630e3  lea     rcx, [rsp+560h+TokenHandle]; this
0x1400630e8  mov     rdx, r14; HINSTANCE
0x1400630eb  movdqu  xmmword ptr [rsp+560h+TokenHandle], xmm0
0x1400630f1  call    ?Initialize@ProgressDialogHelper@@QEAAJPEAUHINSTANCE__@@@Z; ProgressDialogHelper::Initialize(HINSTANCE__ *)
0x1400630f6  mov     ebx, eax
0x1400630f8  lea     rax, WPP_GLOBAL_Control
0x1400630ff  test    ebx, ebx
0x140063101  jns     short loc_14006314F
0x140063103  mov     rcx, cs:WPP_GLOBAL_Control
0x14006310a  cmp     rcx, rax
0x14006310d  jz      short loc_14006314F
0x14006310f  test    byte ptr [rcx+1Ch], 8
0x140063113  jz      short loc_14006314F
0x140063115  cmp     byte ptr [rcx+19h], 2
0x140063119  jb      short loc_14006314F
0x14006311b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140063120  lea     rcx, aInitializingTh; "Initializing the progress dialog failed"
0x140063127  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x14006312b  mov     [rsp+560h+PreviousState], rcx
0x140063130  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140063137  mov     rcx, cs:WPP_GLOBAL_Control
0x14006313e  mov     edx, 34h ; '4'
0x140063143  mov     r9d, eax
0x140063146  mov     rcx, [rcx+10h]
0x14006314a  call    WPP_SF_DsD
0x14006314f  xor     edx, edx
0x140063151  xor     r8d, r8d
0x140063154  lea     edi, [rdx+1]
0x140063157  mov     ecx, edi
0x140063159  call    cs:__imp_DismInitialize
0x14006315f  mov     ebx, eax
0x140063161  test    eax, eax
0x140063163  jns     short loc_1400631CA
0x140063165  xor     dil, dil
0x140063168  mov     rax, cs:WPP_GLOBAL_Control
0x14006316f  lea     rcx, WPP_GLOBAL_Control
0x140063176  cmp     rax, rcx
0x140063179  jz      short loc_1400631BB
0x14006317b  test    byte ptr [rax+1Ch], 8
0x14006317f  jz      short loc_1400631BB
0x140063181  cmp     byte ptr [rax+19h], 2
0x140063185  jb      short loc_1400631BB
0x140063187  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006318c  mov     edx, 35h ; '5'
0x140063191  lea     rcx, aDisminitialize_0; "DismInitialize failed"
0x140063198  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x14006319c  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400631a3  mov     [rsp+560h+PreviousState], rcx
0x1400631a8  mov     r9d, eax
0x1400631ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400631b2  mov     rcx, [rcx+10h]
0x1400631b6  call    WPP_SF_DsD
0x1400631bb  lea     rcx, [rsp+560h+TokenHandle]; this
0x1400631c0  call    ??1ProgressDialogHelper@@QEAA@XZ; ProgressDialogHelper::~ProgressDialogHelper(void)
0x1400631c5  jmp     loc_140063607
0x1400631ca  mov     ebx, dword ptr [rsp+560h+var_520]
0x1400631ce  test    ebx, ebx
0x1400631d0  jz      short loc_1400631F4
0x1400631d2  lea     rcx, [rsp+560h+Luid]; this
0x1400631d7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400631dc  mov     rax, cs:__imp_DismCloseSession
0x1400631e3  mov     ecx, ebx
0x1400631e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400631ea  lea     rcx, [rsp+560h+Luid]; this
0x1400631ef  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400631f4  lea     r9, [rsp+560h+var_520]
0x1400631f9  mov     dword ptr [rsp+560h+var_520], 0
0x140063201  xor     r8d, r8d
0x140063204  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x14006320b  xor     edx, edx
0x14006320d  call    cs:__imp_DismOpenSession
0x140063213  mov     ebx, eax
0x140063215  test    eax, eax
0x140063217  jns     short loc_14006324E
0x140063219  mov     rax, cs:WPP_GLOBAL_Control
0x140063220  lea     rcx, WPP_GLOBAL_Control
0x140063227  cmp     rax, rcx
0x14006322a  jz      short loc_1400631BB
0x14006322c  test    byte ptr [rax+1Ch], 8
0x140063230  jz      short loc_1400631BB
0x140063232  cmp     byte ptr [rax+19h], 2
0x140063236  jb      short loc_1400631BB
0x140063238  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006323d  mov     edx, 36h ; '6'
0x140063242  lea     rcx, aDismopensessio_0; "DismOpenSession failed"
0x140063249  jmp     loc_140063198
0x14006324e  mov     ecx, dword ptr [rsp+560h+var_520]; this
0x140063252  lea     r8, [rbp+460h+var_440]; bool
0x140063256  call    ?GetOptionalComponentInfoForMstsc@TsClientOptionalComponent@@YAJI_NAEAUOptionalComponentInfo@1@@Z; TsClientOptionalComponent::GetOptionalComponentInfoForMstsc(uint,bool,TsClientOptionalComponent::OptionalComponentInfo &)
0x14006325b  mov     ebx, eax
0x14006325d  test    eax, eax
0x14006325f  jns     short loc_1400632A2
0x140063261  mov     rax, cs:WPP_GLOBAL_Control
0x140063268  lea     rcx, WPP_GLOBAL_Control
0x14006326f  cmp     rax, rcx
0x140063272  jz      loc_1400631BB
0x140063278  test    byte ptr [rax+1Ch], 8
0x14006327c  jz      loc_1400631BB
0x140063282  cmp     byte ptr [rax+19h], 2
0x140063286  jb      loc_1400631BB
0x14006328c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140063291  mov     edx, 37h ; '7'
0x140063296  lea     rcx, aGetoptionalcom; "GetOptionalComponentInfoForMstsc failed"
0x14006329d  jmp     loc_140063198
0x1400632a2  mov     ecx, dword ptr [rsp+560h+var_520]
0x1400632a6  lea     rax, [rsp+560h+TokenHandle]
0x1400632ab  mov     [rsp+560h+var_530], rax
0x1400632b0  lea     r8, [rbp+460h+var_440]
0x1400632b4  lea     rax, ?ProgressCallback@ProgressDialogHelper@@SAXIIPEAX@Z; ProgressDialogHelper::ProgressCallback(uint,uint,void *)
0x1400632bb  xor     r9d, r9d
0x1400632be  mov     [rsp+560h+ReturnLength], rax
0x1400632c3  lea     rdx, [rbp+460h+var_236]
0x1400632ca  mov     [rsp+560h+PreviousState], 0
0x1400632d3  call    cs:__imp_DismDisableFeature
0x1400632d9  mov     ebx, eax
0x1400632db  test    eax, eax
0x1400632dd  jns     short loc_140063320
0x1400632df  mov     rax, cs:WPP_GLOBAL_Control
0x1400632e6  lea     rcx, WPP_GLOBAL_Control
0x1400632ed  cmp     rax, rcx
0x1400632f0  jz      loc_1400631BB
0x1400632f6  test    byte ptr [rax+1Ch], 8
0x1400632fa  jz      loc_1400631BB
0x140063300  cmp     byte ptr [rax+19h], 2
0x140063304  jb      loc_1400631BB
0x14006330a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006330f  mov     edx, 38h ; '8'
0x140063314  lea     rcx, aDismdisablefea_0; "DismDisableFeature failed"
0x14006331b  jmp     loc_140063198
0x140063320  lea     rcx, [rsp+560h+TokenHandle]; this
0x140063325  call    ??1ProgressDialogHelper@@QEAA@XZ; ProgressDialogHelper::~ProgressDialogHelper(void)
0x14006332a  cmp     ebx, 0BC2h
0x140063330  jnz     loc_140063607
0x140063336  mov     [rsp+560h+pnButton], 0
0x14006333e  test    sil, sil
0x140063341  jz      loc_140063415
0x140063347  mov     ebx, 0A0h
0x14006334c  lea     rcx, [rsp+560h+pTaskConfig]; void *
0x140063351  mov     r8d, ebx; Size
0x140063354  xor     edx, edx; Val
0x140063356  call    memset_0
0x14006335b  xor     r9d, r9d; pfVerificationFlagChecked
0x14006335e  mov     [rsp+560h+pTaskConfig.cbSize], ebx
0x140063362  xor     r8d, r8d; pnRadioButton
0x140063365  mov     [rsp+560h+pTaskConfig.hInstance], r14
0x14006336a  lea     rdx, [rsp+560h+pnButton]; pnButton
0x14006336f  mov     [rbp+460h+pTaskConfig.dwFlags], 1000000h
0x140063376  lea     rcx, [rsp+560h+pTaskConfig]; pTaskConfig
0x14006337b  mov     [rbp+460h+pTaskConfig.pszWindowTitle], 3ECh
0x140063383  mov     [rbp+460h+pTaskConfig.pszContent], 7532h
0x14006338b  mov     [rbp+460h+pTaskConfig.dwCommonButtons], 6
0x140063392  mov     qword ptr [rbp+460h+pTaskConfig.24h], 0FFFFh
0x14006339a  call    cs:__imp_TaskDialogIndirect
0x1400633a0  mov     ebx, eax
0x1400633a2  test    eax, eax
0x1400633a4  jns     short loc_14006340A
0x1400633a6  mov     rax, cs:WPP_GLOBAL_Control
0x1400633ad  lea     rcx, WPP_GLOBAL_Control
0x1400633b4  cmp     rax, rcx
0x1400633b7  jz      loc_140063607
0x1400633bd  test    byte ptr [rax+1Ch], 8
0x1400633c1  jz      loc_140063607
0x1400633c7  cmp     byte ptr [rax+19h], 2
0x1400633cb  jb      loc_140063607
0x1400633d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400633d6  lea     rcx, aTaskdialogindi_0; "TaskDialogIndirect failed"
0x1400633dd  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x1400633e1  mov     [rsp+560h+PreviousState], rcx
0x1400633e6  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400633ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400633f4  mov     edx, 39h ; '9'
0x1400633f9  mov     r9d, eax
0x1400633fc  mov     rcx, [rcx+10h]
0x140063400  call    WPP_SF_DsD
0x140063405  jmp     loc_140063607
0x14006340a  cmp     [rsp+560h+pnButton], 6
0x14006340f  jnz     loc_140063607
0x140063415  xorps   xmm0, xmm0
0x140063418  mov     qword ptr [rsp+560h+Luid.LowPart], 0
0x140063421  lea     rcx, [rsp+560h+TokenHandle]
0x140063426  mov     [rsp+560h+TokenHandle], 0
0x14006342f  movups  xmmword ptr [rbp+460h+NewState.PrivilegeCount], xmm0
0x140063433  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x140063438  mov     ebx, eax
0x14006343a  test    eax, eax
0x14006343c  jns     short loc_1400634A2
0x14006343e  mov     rax, cs:WPP_GLOBAL_Control
0x140063445  lea     rcx, WPP_GLOBAL_Control
0x14006344c  cmp     rax, rcx
0x14006344f  jz      loc_1400635FD
0x140063455  test    byte ptr [rax+1Ch], 8
0x140063459  jz      loc_1400635FD
0x14006345f  cmp     byte ptr [rax+19h], 2
0x140063463  jb      loc_1400635FD
0x140063469  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006346e  lea     rcx, aOpenCurrentAcc; "open_current_access_token_nothrow faile"...
0x140063475  mov     dword ptr [rsp+560h+ReturnLength], ebx
0x140063479  mov     [rsp+560h+PreviousState], rcx
0x14006347e  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140063485  mov     rcx, cs:WPP_GLOBAL_Control
0x14006348c  mov     edx, 3Ah ; ':'
0x140063491  mov     r9d, eax
0x140063494  mov     rcx, [rcx+10h]
0x140063498  call    WPP_SF_DsD
0x14006349d  jmp     loc_1400635FD
0x1400634a2  lea     r8, [rsp+560h+Luid]; lpLuid
0x1400634a7  xor     ecx, ecx; lpSystemName
0x1400634a9  lea     rdx, Name; "SeShutdownPrivilege"
0x1400634b0  call    cs:__imp_LookupPrivilegeValueW
0x1400634b6  test    eax, eax
0x1400634b8  jnz     short loc_1400634FC
0x1400634ba  call    cs:__imp_GetLastError
0x1400634c0  mov     ebx, eax
0x1400634c2  mov     rax, cs:WPP_GLOBAL_Control
0x1400634c9  lea     rcx, WPP_GLOBAL_Control
0x1400634d0  cmp     rax, rcx
0x1400634d3  jz      loc_1400635E6
0x1400634d9  test    byte ptr [rax+1Ch], 8
0x1400634dd  jz      loc_1400635E6
0x1400634e3  cmp     byte ptr [rax+19h], 2
0x1400634e7  jb      loc_1400635E6
0x1400634ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400634f2  mov     edx, 3Bh ; ';'
0x1400634f7  jmp     loc_1400635C8
0x1400634fc  mov     rax, qword ptr [rsp+560h+Luid.LowPart]
0x140063501  lea     r8, [rbp+460h+NewState]; NewState
0x140063505  mov     rcx, [rsp+560h+TokenHandle]; TokenHandle
0x14006350a  mov     r9d, 10h; BufferLength
0x140063510  mov     [rsp+560h+ReturnLength], 0; ReturnLength
0x140063519  xor     edx, edx; DisableAllPrivileges
0x14006351b  mov     qword ptr [rbp+460h+NewState.Privileges.Luid.LowPart], rax
0x14006351f  mov     [rbp+460h+NewState.PrivilegeCount], edi
0x140063522  mov     [rbp+460h+NewState.Privileges.Attributes], 2
0x140063529  mov     [rsp+560h+PreviousState], 0; PreviousState
0x140063532  call    cs:__imp_AdjustTokenPrivileges
0x140063538  test    eax, eax
0x14006353a  jnz     short loc_140063577
0x14006353c  call    cs:__imp_GetLastError
0x140063542  mov     ebx, eax
0x140063544  mov     rax, cs:WPP_GLOBAL_Control
0x14006354b  lea     rcx, WPP_GLOBAL_Control
0x140063552  cmp     rax, rcx
0x140063555  jz      loc_1400635E6
0x14006355b  test    byte ptr [rax+1Ch], 8
0x14006355f  jz      loc_1400635E6
0x140063565  cmp     byte ptr [rax+19h], 2
0x140063569  jb      short loc_1400635E6
0x14006356b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140063570  mov     edx, 3Ch ; '<'
0x140063575  jmp     short loc_1400635C8
0x140063577  mov     dword ptr [rsp+560h+ReturnLength], 80040002h; dwReason
0x14006357f  xor     r9d, r9d; bForceAppsClosed
0x140063582  xor     r8d, r8d; dwTimeout
0x140063585  mov     dword ptr [rsp+560h+PreviousState], edi; bRebootAfterShutdown
0x140063589  xor     edx, edx; lpMessage
0x14006358b  xor     ecx, ecx; lpMachineName
0x14006358d  call    cs:__imp_InitiateSystemShutdownExW
0x140063593  test    eax, eax
0x140063595  jnz     short loc_1400635FD
0x140063597  call    cs:__imp_GetLastError
0x14006359d  mov     ebx, eax
0x14006359f  mov     rax, cs:WPP_GLOBAL_Control
0x1400635a6  lea     rcx, WPP_GLOBAL_Control
0x1400635ad  cmp     rax, rcx
0x1400635b0  jz      short loc_1400635E6
0x1400635b2  test    byte ptr [rax+1Ch], 8
0x1400635b6  jz      short loc_1400635E6
0x1400635b8  cmp     byte ptr [rax+19h], 2
0x1400635bc  jb      short loc_1400635E6
0x1400635be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400635c3  mov     edx, 3Dh ; '='
0x1400635c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400635cf  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400635d6  mov     r9d, eax
0x1400635d9  mov     dword ptr [rsp+560h+PreviousState], ebx
0x1400635dd  mov     rcx, [rcx+10h]
0x1400635e1  call    WPP_SF_Dd
  ... truncated ...
```
