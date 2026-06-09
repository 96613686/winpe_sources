# LanIDsMgr::Initialize(void)

- ea: `0x1800fdfa4`
- end: `0x1800fe1de`
- name: `?Initialize@LanIDsMgr@@AEAAKXZ`
- size: `570`
- prototype: `unsigned int __fastcall(LanIDsMgr *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180031f10`

## callees

- `0x180009990`
- `0x18000f688`
- `0x18000fab0`
- `0x180010340`
- `0x18005b2cc`
- `0x18007448c`
- `0x1800a88a0`
- `0x1800fdfa4`
- `0x1800fe810`
- `0x1800ff864`
- `0x180129510`
- `0x180129550`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe17a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe1b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe17a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe13d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe13d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800fe12b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800fe12b`

## string_xrefs

- `0x1800fe03d`: `NlaSvc-Licensing-LANIds-BSSIDRetrieval-Enabled`
- `0x1800fe015`: `NlaSvc-Licensing-LANIds-Service-Enabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LanIDsMgr::Initialize(LanIDsMgr *this)
{
  unsigned int v2; // edi
  bool v3; // al
  const wchar_t *v4; // rdx
  void *v5; // rcx
  bool v6; // al
  struct WLANApiDllProxy *v7; // rax
  unsigned int v8; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  DWORD LastError; // eax
  DWORD v11; // ebx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-28h] BYREF
  __int128 v14; // [rsp+28h] [rbp-20h] BYREF

  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 8);
  LanIDsMgr::RetrieveRegistryValues(this);
  v3 = !*((_BYTE *)this + 50) && IsLicenseEnabled(L"NlaSvc-Licensing-LANIds-Service-Enabled");
  *((_BYTE *)this + 48) = v3;
  *((_BYTE *)this + 51) = IsLicenseEnabled(L"NlaSvc-Licensing-LANIds-LLDPDriver-Enabled");
  *((_BYTE *)this + 52) = IsLicenseEnabled(L"NlaSvc-Licensing-LANIds-BSSIDRetrieval-Enabled");
  v6 = 0;
  if ( !*((_BYTE *)this + 53) )
  {
    if ( (unsigned __int8)HviIsAnyHypervisorPresent() )
    {
      v14 = 0;
      HviGetHypervisorFeatures(&v14);
      if ( (v14 & 0x100000000000LL) == 0 )
        v6 = 1;
    }
  }
  *((_BYTE *)this + 49) = v6;
  v7 = LanIDsMgr::s_pWLANApiProxyInterceptor;
  if ( !LanIDsMgr::s_pWLANApiProxyInterceptor )
    v7 = (LanIDsMgr *)((char *)this + 176);
  *((_QWORD *)this + 96) = v7;
  if ( !*((_BYTE *)this + 48) )
  {
LABEL_28:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, v2);
    goto LABEL_31;
  }
  v2 = LANIdsRPCHelper::RpcServerStart(v5, v4);
  if ( !v2 )
  {
    *((_QWORD *)this + 7) = qword_180155160;
    (***((void (__fastcall ****)(_QWORD, char *))this + 96))(*((_QWORD *)this + 96), (char *)this + 792);
    v8 = LanIDsMgr::RegisterForNotifications(this);
    v2 = v8;
    if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, v8);
    LanIDsMgr::Update(this);
    ThreadpoolTimer = CreateThreadpoolTimer(LanIDsMgr::StaticTimerCallback, this, 0);
    *((_QWORD *)this + 20) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, LastError);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return v11;
    }
    goto LABEL_28;
  }
LABEL_31:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x1800fdfa4  mov     [rsp+arg_8], rbx
0x1800fdfa9  mov     [rsp+arg_10], rbp
0x1800fdfae  push    rdi
0x1800fdfaf  sub     rsp, 40h
0x1800fdfb3  mov     rax, cs:__security_cookie
0x1800fdfba  xor     rax, rsp
0x1800fdfbd  mov     [rsp+48h+var_10], rax
0x1800fdfc2  mov     rbx, rcx
0x1800fdfc5  xor     edi, edi
0x1800fdfc7  lea     rbp, WPP_GLOBAL_Control
0x1800fdfce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fdfd5  cmp     rcx, rbp
0x1800fdfd8  jz      short loc_1800FDFF3
0x1800fdfda  test    byte ptr [rcx+1Ch], 4
0x1800fdfde  jz      short loc_1800FDFF3
0x1800fdfe0  lea     edx, [rdi+19h]
0x1800fdfe3  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fdfea  mov     rcx, [rcx+10h]
0x1800fdfee  call    WPP_SF_
0x1800fdff3  mov     [rsp+48h+lpCriticalSection], rdi
0x1800fdff8  lea     rdx, [rbx+8]
0x1800fdffc  lea     rcx, [rsp+48h+lpCriticalSection]
0x1800fe001  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800fe006  nop
0x1800fe007  mov     rcx, rbx; this
0x1800fe00a  call    ?RetrieveRegistryValues@LanIDsMgr@@AEAAXXZ; LanIDsMgr::RetrieveRegistryValues(void)
0x1800fe00f  cmp     byte ptr [rbx+32h], 0
0x1800fe013  jnz     short loc_1800FE029
0x1800fe015  lea     rcx, aNlasvcLicensin_1; "NlaSvc-Licensing-LANIds-Service-Enabled"
0x1800fe01c  call    ?IsLicenseEnabled@@YA_NPEB_W@Z; IsLicenseEnabled(wchar_t const *)
0x1800fe021  test    al, al
0x1800fe023  jz      short loc_1800FE029
0x1800fe025  mov     al, 1
0x1800fe027  jmp     short loc_1800FE02B
0x1800fe029  xor     al, al
0x1800fe02b  mov     [rbx+30h], al
0x1800fe02e  lea     rcx, aNlasvcLicensin; "NlaSvc-Licensing-LANIds-LLDPDriver-Enab"...
0x1800fe035  call    ?IsLicenseEnabled@@YA_NPEB_W@Z; IsLicenseEnabled(wchar_t const *)
0x1800fe03a  mov     [rbx+33h], al
0x1800fe03d  lea     rcx, aNlasvcLicensin_0; "NlaSvc-Licensing-LANIds-BSSIDRetrieval-"...
0x1800fe044  call    ?IsLicenseEnabled@@YA_NPEB_W@Z; IsLicenseEnabled(wchar_t const *)
0x1800fe049  mov     [rbx+34h], al
0x1800fe04c  cmp     byte ptr [rbx+35h], 0
0x1800fe050  jnz     short loc_1800FE082
0x1800fe052  call    HviIsAnyHypervisorPresent
0x1800fe057  test    al, al
0x1800fe059  jz      short loc_1800FE082
0x1800fe05b  xorps   xmm0, xmm0
0x1800fe05e  movups  [rsp+48h+var_20], xmm0
0x1800fe063  lea     rcx, [rsp+48h+var_20]
0x1800fe068  call    HviGetHypervisorFeatures
0x1800fe06d  mov     rax, 100000000000h
0x1800fe077  test    qword ptr [rsp+48h+var_20], rax
0x1800fe07c  jnz     short loc_1800FE082
0x1800fe07e  mov     al, 1
0x1800fe080  jmp     short loc_1800FE084
0x1800fe082  xor     al, al
0x1800fe084  mov     [rbx+31h], al
0x1800fe087  mov     rax, cs:?s_pWLANApiProxyInterceptor@LanIDsMgr@@0PEAVWLANApiDllProxy@@EA; WLANApiDllProxy * LanIDsMgr::s_pWLANApiProxyInterceptor
0x1800fe08e  test    rax, rax
0x1800fe091  jnz     short loc_1800FE09A
0x1800fe093  lea     rax, [rbx+0B0h]
0x1800fe09a  mov     [rbx+300h], rax
0x1800fe0a1  cmp     byte ptr [rbx+30h], 0
0x1800fe0a5  jz      loc_1800FE184
0x1800fe0ab  call    ?RpcServerStart@LANIdsRPCHelper@@SAKPEAXPEB_W@Z; LANIdsRPCHelper::RpcServerStart(void *,wchar_t const *)
0x1800fe0b0  mov     edi, eax
0x1800fe0b2  test    eax, eax
0x1800fe0b4  jnz     loc_1800FE1AF
0x1800fe0ba  lea     rax, qword_180155160
0x1800fe0c1  mov     [rbx+38h], rax
0x1800fe0c5  mov     rcx, [rbx+300h]
0x1800fe0cc  mov     rax, [rcx]
0x1800fe0cf  lea     rdx, [rbx+318h]
0x1800fe0d6  mov     rax, [rax]
0x1800fe0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe0de  mov     rcx, rbx; CallerContext
0x1800fe0e1  call    ?RegisterForNotifications@LanIDsMgr@@AEAAKXZ; LanIDsMgr::RegisterForNotifications(void)
0x1800fe0e6  mov     edi, eax
0x1800fe0e8  test    eax, eax
0x1800fe0ea  jz      short loc_1800FE116
0x1800fe0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe0f3  cmp     rcx, rbp
0x1800fe0f6  jz      short loc_1800FE116
0x1800fe0f8  test    byte ptr [rcx+1Ch], 1
0x1800fe0fc  jz      short loc_1800FE116
0x1800fe0fe  mov     edx, 1Ah
0x1800fe103  mov     r9d, eax
0x1800fe106  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fe10d  mov     rcx, [rcx+10h]
0x1800fe111  call    WPP_SF_d
0x1800fe116  mov     rcx, rbx; this
0x1800fe119  call    ?Update@LanIDsMgr@@AEAAXXZ; LanIDsMgr::Update(void)
0x1800fe11e  xor     r8d, r8d; pcbe
0x1800fe121  mov     rdx, rbx; pv
0x1800fe124  lea     rcx, ?StaticTimerCallback@LanIDsMgr@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800fe12b  call    cs:__imp_CreateThreadpoolTimer
0x1800fe131  mov     [rbx+0A0h], rax
0x1800fe138  test    rax, rax
0x1800fe13b  jnz     short loc_1800FE184
0x1800fe13d  call    cs:__imp_GetLastError
0x1800fe143  mov     ebx, eax
0x1800fe145  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe14c  cmp     rcx, rbp
0x1800fe14f  jz      short loc_1800FE170
0x1800fe151  test    byte ptr [rcx+1Ch], 1
0x1800fe155  jz      short loc_1800FE170
0x1800fe157  mov     edx, 1Bh
0x1800fe15c  mov     r9d, eax
0x1800fe15f  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fe166  mov     rcx, [rcx+10h]
0x1800fe16a  call    WPP_SF_d
0x1800fe16f  nop
0x1800fe170  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800fe175  test    rcx, rcx
0x1800fe178  jz      short loc_1800FE180
0x1800fe17a  call    cs:__imp_LeaveCriticalSection
0x1800fe180  mov     eax, ebx
0x1800fe182  jmp     short loc_1800FE1C1
0x1800fe184  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe18b  cmp     rcx, rbp
0x1800fe18e  jz      short loc_1800FE1AF
0x1800fe190  test    byte ptr [rcx+1Ch], 4
0x1800fe194  jz      short loc_1800FE1AF
0x1800fe196  mov     edx, 1Ch
0x1800fe19b  mov     r9d, edi
0x1800fe19e  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fe1a5  mov     rcx, [rcx+10h]
0x1800fe1a9  call    WPP_SF_d
0x1800fe1ae  nop
0x1800fe1af  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800fe1b4  test    rcx, rcx
0x1800fe1b7  jz      short loc_1800FE1BF
0x1800fe1b9  call    cs:__imp_LeaveCriticalSection
0x1800fe1bf  mov     eax, edi
0x1800fe1c1  mov     rcx, [rsp+48h+var_10]
0x1800fe1c6  xor     rcx, rsp; StackCookie
0x1800fe1c9  call    __security_check_cookie
0x1800fe1ce  mov     rbx, [rsp+48h+arg_8]
0x1800fe1d3  mov     rbp, [rsp+48h+arg_10]
0x1800fe1d8  add     rsp, 40h
0x1800fe1dc  pop     rdi
0x1800fe1dd  retn
```
