# CConfigureApps::InitializePage(void *)

- ea: `0x180019890`
- end: `0x180019996`
- name: `?InitializePage@CConfigureApps@@MEAAJPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(CConfigureApps *__hidden this, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c0f0`
- `0x18000c394`
- `0x18000e5ec`
- `0x18000e7ec`
- `0x1800196d4`
- `0x180019800`
- `0x180019890`
- `0x18001b1d0`
- `0x18001b988`
- `0x180030ea0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800198ce`
- `ntdll!EtwEventWrite` at `0x180019962`
- `ntdll!EtwEventWrite` at `0x1800198ce`
- `ntdll!EtwEventWrite` at `0x180019962`

## string_xrefs

- `0x1800198f1`: `FirewallPageConfigureApps`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConfigureApps::InitializePage(CConfigureApps *this, void *a2)
{
  unsigned int inited; // ebx
  _QWORD v6[42]; // [rsp+20h] [rbp-168h] BYREF

  if ( g_Provider )
    EtwEventWrite(g_Provider, LoadExceptionsInitialize_Start, 0, 0);
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v6,
    "FirewallPageInit");
  v6[0] = &NetworkLegacyUxTelemetry::FirewallPageInit::`vftable';
  NetworkLegacyUxTelemetry::FirewallPageInit::StartActivity(
    (NetworkLegacyUxTelemetry::FirewallPageInit *)v6,
    L"FirewallPageConfigureApps");
  if ( *((_QWORD *)this + 2) && a2 )
  {
    *((_QWORD *)this + 5) = a2;
    CConfigureApps::InitializeHWNDs(this);
    CConfigureApps::InitializeListView(this);
    inited = CConfigureApps::_InitUI(this, 0);
    CConfigureApps::SetSheildIcons(this);
  }
  else
  {
    inited = -2147467259;
  }
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v6, inited);
  if ( g_Provider )
    EtwEventWrite(g_Provider, LoadExceptionsInitialize_End, 0, 0);
  NetworkLegacyUxTelemetry::FirewallPageInit::~FirewallPageInit((NetworkLegacyUxTelemetry::FirewallPageInit *)v6);
  return inited;
}

```

## disassembly

```asm
0x180019890  mov     [rsp+arg_8], rbx
0x180019895  push    rdi
0x180019896  sub     rsp, 180h
0x18001989d  mov     rax, cs:__security_cookie
0x1800198a4  xor     rax, rsp
0x1800198a7  mov     [rsp+188h+var_18], rax
0x1800198af  mov     rbx, rdx
0x1800198b2  mov     rdi, rcx
0x1800198b5  mov     rcx, cs:g_Provider
0x1800198bc  test    rcx, rcx
0x1800198bf  jz      short loc_1800198D4
0x1800198c1  xor     r9d, r9d
0x1800198c4  xor     r8d, r8d
0x1800198c7  lea     rdx, LoadExceptionsInitialize_Start
0x1800198ce  call    cs:__imp_EtwEventWrite
0x1800198d4  lea     rdx, aFirewallpagein; "FirewallPageInit"
0x1800198db  lea     rcx, [rsp+188h+var_168]
0x1800198e0  call    ??0?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800198e5  lea     rax, ??_7FirewallPageInit@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::FirewallPageInit::`vftable'
0x1800198ec  mov     [rsp+188h+var_168], rax
0x1800198f1  lea     rdx, aFirewallpageco; "FirewallPageConfigureApps"
0x1800198f8  lea     rcx, [rsp+188h+var_168]; this
0x1800198fd  call    ?StartActivity@FirewallPageInit@NetworkLegacyUxTelemetry@@QEAAXPEBG@Z; NetworkLegacyUxTelemetry::FirewallPageInit::StartActivity(ushort const *)
0x180019902  cmp     qword ptr [rdi+10h], 0
0x180019907  jz      short loc_180019938
0x180019909  test    rbx, rbx
0x18001990c  jz      short loc_180019938
0x18001990e  mov     [rdi+28h], rbx
0x180019912  mov     rcx, rdi; this
0x180019915  call    ?InitializeHWNDs@CConfigureApps@@AEAAXXZ; CConfigureApps::InitializeHWNDs(void)
0x18001991a  mov     rcx, rdi; this
0x18001991d  call    ?InitializeListView@CConfigureApps@@AEAAXXZ; CConfigureApps::InitializeListView(void)
0x180019922  xor     edx, edx; int
0x180019924  mov     rcx, rdi; this
0x180019927  call    ?_InitUI@CConfigureApps@@AEAAJH@Z; CConfigureApps::_InitUI(int)
0x18001992c  mov     ebx, eax
0x18001992e  mov     rcx, rdi; this
0x180019931  call    ?SetSheildIcons@CConfigureApps@@AEAAXXZ; CConfigureApps::SetSheildIcons(void)
0x180019936  jmp     short loc_18001993D
0x180019938  mov     ebx, 80004005h
0x18001993d  mov     edx, ebx
0x18001993f  lea     rcx, [rsp+188h+var_168]
0x180019944  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180019949  mov     rcx, cs:g_Provider
0x180019950  test    rcx, rcx
0x180019953  jz      short loc_180019969
0x180019955  xor     r9d, r9d
0x180019958  xor     r8d, r8d
0x18001995b  lea     rdx, LoadExceptionsInitialize_End
0x180019962  call    cs:__imp_EtwEventWrite
0x180019968  nop
0x180019969  lea     rcx, [rsp+188h+var_168]; this
0x18001996e  call    ??1FirewallPageInit@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::FirewallPageInit::~FirewallPageInit(void)
0x180019973  mov     eax, ebx
0x180019975  mov     rcx, [rsp+188h+var_18]
0x18001997d  xor     rcx, rsp; StackCookie
0x180019980  call    __security_check_cookie
0x180019985  mov     rbx, [rsp+188h+arg_8]
0x18001998d  add     rsp, 180h
0x180019994  pop     rdi
0x180019995  retn
```
