# ProvOperations::CheckFirstRun(void)

- ea: `0x180011884`
- end: `0x180011b80`
- name: `?CheckFirstRun@ProvOperations@@AEAAJXZ`
- size: `764`
- prototype: `__int64 __fastcall(TraceLoggingCorrelationVector **this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x180010b40`

## callees

- `0x180007674`
- `0x18000ca00`
- `0x18000d1e4`
- `0x180011884`
- `0x1800122e4`
- `0x18001434c`
- `0x18001451c`
- `0x180017914`
- `0x180017d8c`
- `0x180017f68`
- `0x180019238`
- `0x18001b3c8`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011921`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011a36`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011921`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011a36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800119f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800119f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800119b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800119b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001196e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011ab4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001196e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011ab4`

## string_xrefs

- `0x180011944`: `FirstRunComplete`
- `0x180011994`: `FirstRunComplete`
- `0x180011a8e`: `InstallType`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvOperations::CheckFirstRun(TraceLoggingCorrelationVector **this)
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int ValueW; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v17[42]; // [rsp+70h] [rbp-90h] BYREF
  char Destination[144]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "CheckFirstRun");
  v17[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::StartActivity((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun *)v17);
  hkey = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\Provisioning\\";
  ValueW = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0x2001Fu, 0, &hkey, 0);
  if ( ValueW )
  {
    v5 = 1228;
LABEL_11:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
           (const char *)ValueW,
           dwOptions);
LABEL_12:
    if ( hkey )
      RegCloseKey(hkey);
    goto LABEL_31;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"FirstRunComplete", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v5 = 1251;
      goto LABEL_11;
    }
  }
  else if ( pvData )
  {
    goto LABEL_28;
  }
  pvData = 1;
  ValueW = RegSetValueExW(hkey, L"FirstRunComplete", 0, 4u, (const BYTE *)&pvData, 4u);
  if ( ValueW )
  {
    v5 = 1264;
    goto LABEL_11;
  }
  hKey = 0;
  v7 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKey,
         0);
  if ( v7 != 2 )
  {
    if ( v7 )
    {
      v8 = 1283;
LABEL_17:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v8,
             (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
             (const char *)v7,
             dwOptionsa);
      goto LABEL_18;
    }
    pcbData = 4;
    v7 = RegGetValueW(hKey, 0, L"InstallType", 0x10u, 0, &pvData, &pcbData);
    if ( v7 != 2 )
    {
      if ( v7 )
      {
        v8 = 1299;
        goto LABEL_17;
      }
      if ( pvData == 17 )
      {
        TraceLoggingCorrelationVector::ToString(this[7], Destination);
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::ProvOpsPostApr(
          (Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun *)v17,
          Destination);
        v9 = ProvOperations::SetPowerwashSuccessText();
        v6 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x51B,
            (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
            (const char *)(unsigned int)v9,
            dwOptionsa);
LABEL_18:
          if ( hKey )
            RegCloseKey(hKey);
          goto LABEL_12;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_28:
  if ( hkey )
    RegCloseKey(hkey);
  v6 = 0;
LABEL_31:
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
  v17[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
  return v6;
}

```

## disassembly

```asm
0x180011884  push    rbp
0x180011886  push    rbx
0x180011887  push    rdi
0x180011888  push    r12
0x18001188a  lea     rbp, [rsp-168h]
0x180011892  sub     rsp, 268h
0x180011899  mov     rax, cs:__security_cookie
0x1800118a0  xor     rax, rsp
0x1800118a3  mov     [rbp+180h+var_30], rax
0x1800118aa  mov     rbx, rcx
0x1800118ad  lea     rdx, aCheckfirstrun; "CheckFirstRun"
0x1800118b4  lea     rcx, [rsp+280h+var_210]
0x1800118b9  call    ??0?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800118be  lea     r12, ??_7CheckFirstRun@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::`vftable'
0x1800118c5  lea     rcx, [rsp+280h+var_210]; this
0x1800118ca  mov     [rsp+280h+var_210], r12
0x1800118cf  call    ?StartActivity@CheckFirstRun@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::StartActivity(void)
0x1800118d4  xor     edi, edi
0x1800118d6  mov     [rsp+280h+hkey], rdi
0x1800118db  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800118e0  mov     [rsp+280h+lpdwDisposition], rdi; lpdwDisposition
0x1800118e5  lea     rcx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Provisioning\\"
0x1800118ec  test    al, al
0x1800118ee  lea     rdx, aOsdataSoftware_5; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800118f5  lea     rax, [rsp+280h+hkey]
0x1800118fa  mov     [rsp+280h+phkResult], rax; phkResult
0x1800118ff  cmovz   rdx, rcx; lpSubKey
0x180011903  mov     [rsp+280h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180011908  xor     r9d, r9d; lpClass
0x18001190b  mov     [rsp+280h+samDesired], 2001Fh; samDesired
0x180011913  xor     r8d, r8d; Reserved
0x180011916  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001191d  mov     [rsp+280h+dwOptions], edi; dwOptions
0x180011921  call    cs:__imp_RegCreateKeyExW
0x180011927  test    eax, eax
0x180011929  jz      short loc_180011935
0x18001192b  mov     edx, 4CCh
0x180011930  jmp     loc_1800119CC
0x180011935  mov     rcx, [rsp+280h+hkey]; hkey
0x18001193a  lea     rax, [rsp+280h+pcbData]
0x18001193f  mov     [rsp+280h+lpSecurityAttributes], rax; pcbData
0x180011944  lea     r8, Value; "FirstRunComplete"
0x18001194b  lea     rax, [rsp+280h+pvData]
0x180011950  mov     [rsp+280h+pvData], edi
0x180011954  mov     qword ptr [rsp+280h+samDesired], rax; pvData
0x180011959  mov     r9d, 10h; dwFlags
0x18001195f  xor     edx, edx; lpSubKey
0x180011961  mov     qword ptr [rsp+280h+dwOptions], rdi; unsigned int
0x180011966  mov     [rsp+280h+pcbData], 4
0x18001196e  call    cs:__imp_RegGetValueW
0x180011974  test    eax, eax
0x180011976  jnz     short loc_1800119C2
0x180011978  cmp     [rsp+280h+pvData], edi
0x18001197c  ja      loc_180011B2D
0x180011982  mov     rcx, [rsp+280h+hkey]; hKey
0x180011987  lea     rax, [rsp+280h+pvData]
0x18001198c  mov     [rsp+280h+samDesired], 4; cbData
0x180011994  lea     rdx, Value; "FirstRunComplete"
0x18001199b  mov     r9d, 4; dwType
0x1800119a1  mov     qword ptr [rsp+280h+dwOptions], rax; lpData
0x1800119a6  xor     r8d, r8d; Reserved
0x1800119a9  mov     [rsp+280h+pvData], 1
0x1800119b1  call    cs:__imp_RegSetValueExW
0x1800119b7  test    eax, eax
0x1800119b9  jz      short loc_1800119FD
0x1800119bb  mov     edx, 4F0h
0x1800119c0  jmp     short loc_1800119CC
0x1800119c2  cmp     eax, 2
0x1800119c5  jz      short loc_180011982
0x1800119c7  mov     edx, 4E3h; void *
0x1800119cc  mov     rcx, [rbp+188h]; this
0x1800119d3  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x1800119da  mov     r9d, eax; char *
0x1800119dd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800119e2  mov     ebx, eax
0x1800119e4  mov     rcx, [rsp+280h+hkey]; hKey
0x1800119e9  test    rcx, rcx
0x1800119ec  jz      loc_180011B3F
0x1800119f2  call    cs:__imp_RegCloseKey
0x1800119f8  jmp     loc_180011B3F
0x1800119fd  mov     [rsp+280h+lpdwDisposition], rdi; lpdwDisposition
0x180011a02  lea     rax, [rsp+280h+hKey]
0x180011a07  mov     [rsp+280h+phkResult], rax; phkResult
0x180011a0c  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180011a13  mov     [rsp+280h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180011a18  xor     r9d, r9d; lpClass
0x180011a1b  mov     [rsp+280h+samDesired], 20019h; samDesired
0x180011a23  xor     r8d, r8d; Reserved
0x180011a26  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011a2d  mov     [rsp+280h+dwOptions], edi; unsigned int
0x180011a31  mov     [rsp+280h+hKey], rdi
0x180011a36  call    cs:__imp_RegCreateKeyExW
0x180011a3c  cmp     eax, 2
0x180011a3f  jz      loc_180011B1D
0x180011a45  test    eax, eax
0x180011a47  jz      short loc_180011A7F
0x180011a49  mov     edx, 503h; void *
0x180011a4e  mov     rcx, [rbp+188h]; this
0x180011a55  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180011a5c  mov     r9d, eax; char *
0x180011a5f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011a64  mov     ebx, eax
0x180011a66  mov     rcx, [rsp+280h+hKey]; hKey
0x180011a6b  test    rcx, rcx
0x180011a6e  jz      loc_1800119E4
0x180011a74  call    cs:__imp_RegCloseKey
0x180011a7a  jmp     loc_1800119E4
0x180011a7f  mov     rcx, [rsp+280h+hKey]; hkey
0x180011a84  lea     rax, [rsp+280h+pcbData]
0x180011a89  mov     [rsp+280h+lpSecurityAttributes], rax; pcbData
0x180011a8e  lea     r8, aInstalltype; "InstallType"
0x180011a95  lea     rax, [rsp+280h+pvData]
0x180011a9a  mov     [rsp+280h+pcbData], 4
0x180011aa2  mov     qword ptr [rsp+280h+samDesired], rax; pvData
0x180011aa7  mov     r9d, 10h; dwFlags
0x180011aad  xor     edx, edx; lpSubKey
0x180011aaf  mov     qword ptr [rsp+280h+dwOptions], rdi; int
0x180011ab4  call    cs:__imp_RegGetValueW
0x180011aba  cmp     eax, 2
0x180011abd  jz      short loc_180011B1D
0x180011abf  test    eax, eax
0x180011ac1  jz      short loc_180011ACA
0x180011ac3  mov     edx, 513h
0x180011ac8  jmp     short loc_180011A4E
0x180011aca  cmp     [rsp+280h+pvData], 11h
0x180011acf  jnz     short loc_180011B1D
0x180011ad1  mov     rcx, [rbx+38h]; this
0x180011ad5  lea     rdx, [rbp+180h+Destination]; Destination
0x180011adc  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180011ae1  lea     rdx, [rbp+180h+Destination]; char *
0x180011ae8  lea     rcx, [rsp+280h+var_210]; this
0x180011aed  call    ?ProvOpsPostApr@CheckFirstRun@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXPEBD@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CheckFirstRun::ProvOpsPostApr(char const *)
0x180011af2  call    ?SetPowerwashSuccessText@ProvOperations@@CAJXZ; ProvOperations::SetPowerwashSuccessText(void)
0x180011af7  mov     ebx, eax
0x180011af9  test    eax, eax
0x180011afb  jns     short loc_180011B1D
0x180011afd  mov     rcx, [rbp+188h]; this
0x180011b04  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180011b0b  mov     r9d, eax; char *
0x180011b0e  mov     edx, 51Bh; void *
0x180011b13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b18  jmp     loc_180011A66
0x180011b1d  mov     rcx, [rsp+280h+hKey]; hKey
0x180011b22  test    rcx, rcx
0x180011b25  jz      short loc_180011B2D
0x180011b27  call    cs:__imp_RegCloseKey
0x180011b2d  mov     rcx, [rsp+280h+hkey]; hKey
0x180011b32  test    rcx, rcx
0x180011b35  jz      short loc_180011B3D
0x180011b37  call    cs:__imp_RegCloseKey
0x180011b3d  mov     ebx, edi
0x180011b3f  lea     rcx, [rsp+280h+var_210]
0x180011b44  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180011b49  lea     rcx, [rsp+280h+var_210]
0x180011b4e  mov     [rsp+280h+var_210], r12
0x180011b53  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011b58  lea     rcx, [rsp+280h+var_210]
0x180011b5d  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011b62  mov     eax, ebx
0x180011b64  mov     rcx, [rbp+180h+var_30]
0x180011b6b  xor     rcx, rsp; StackCookie
0x180011b6e  call    __security_check_cookie
0x180011b73  add     rsp, 268h
0x180011b7a  pop     r12
0x180011b7c  pop     rdi
0x180011b7d  pop     rbx
0x180011b7e  pop     rbp
0x180011b7f  retn
```
