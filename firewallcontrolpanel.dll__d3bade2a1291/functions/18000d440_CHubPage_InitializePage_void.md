# CHubPage::InitializePage(void *)

- ea: `0x18000d440`
- end: `0x18000d58f`
- name: `?InitializePage@CHubPage@@MEAAJPEAX@Z`
- size: `335`
- prototype: `__int64 __fastcall(CHubPage *__hidden this, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18000994c`
- `0x18000c0f0`
- `0x18000c394`
- `0x18000ccac`
- `0x18000d060`
- `0x18000d440`
- `0x18000e5ec`
- `0x18000e7ec`
- `0x180030ea0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000d47e`
- `ntdll!EtwEventWrite` at `0x18000d55b`
- `ntdll!EtwEventWrite` at `0x18000d47e`
- `ntdll!EtwEventWrite` at `0x18000d55b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHubPage::InitializePage(CHubPage *this, void *a2)
{
  unsigned __int64 v4; // rdx
  int inited; // ebx
  CFwCplLua *v6; // rcx
  __int64 v7; // rdx
  _QWORD v9[42]; // [rsp+20h] [rbp-168h] BYREF

  if ( g_Provider )
    EtwEventWrite(g_Provider, FwCplInitialize_Start, 0, 0);
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "FirewallPageInit");
  v9[0] = &NetworkLegacyUxTelemetry::FirewallPageInit::`vftable';
  NetworkLegacyUxTelemetry::FirewallPageInit::StartActivity(
    (NetworkLegacyUxTelemetry::FirewallPageInit *)v9,
    L"FirewallHubPage");
  if ( *((_QWORD *)this + 2) && a2 )
  {
    *((_QWORD *)this + 5) = a2;
    inited = CHubPage::InitNavPane((CFwProfileMgr **)this, v4);
    if ( inited >= 0 )
    {
      inited = CHubPage::InitUI(this);
      if ( inited < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 13;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 12;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_041ed7bb04083fded16b958364bb1572_Traceguids, (unsigned int)inited);
      }
    }
  }
  else
  {
    inited = -2147467259;
  }
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v9,
    (unsigned int)inited);
  if ( g_Provider )
    EtwEventWrite(g_Provider, FwCplInitialize_End, 0, 0);
  NetworkLegacyUxTelemetry::FirewallPageInit::~FirewallPageInit((NetworkLegacyUxTelemetry::FirewallPageInit *)v9);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000d440  mov     [rsp+arg_8], rbx
0x18000d445  push    rdi
0x18000d446  sub     rsp, 180h
0x18000d44d  mov     rax, cs:__security_cookie
0x18000d454  xor     rax, rsp
0x18000d457  mov     [rsp+188h+var_18], rax
0x18000d45f  mov     rbx, rdx
0x18000d462  mov     rdi, rcx
0x18000d465  mov     rcx, cs:g_Provider
0x18000d46c  test    rcx, rcx
0x18000d46f  jz      short loc_18000D484
0x18000d471  xor     r9d, r9d
0x18000d474  xor     r8d, r8d
0x18000d477  lea     rdx, FwCplInitialize_Start
0x18000d47e  call    cs:__imp_EtwEventWrite
0x18000d484  lea     rdx, aFirewallpagein; "FirewallPageInit"
0x18000d48b  lea     rcx, [rsp+188h+var_168]
0x18000d490  call    ??0?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000d495  lea     rax, ??_7FirewallPageInit@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::FirewallPageInit::`vftable'
0x18000d49c  mov     [rsp+188h+var_168], rax
0x18000d4a1  lea     rdx, aFirewallhubpag; "FirewallHubPage"
0x18000d4a8  lea     rcx, [rsp+188h+var_168]; this
0x18000d4ad  call    ?StartActivity@FirewallPageInit@NetworkLegacyUxTelemetry@@QEAAXPEBG@Z; NetworkLegacyUxTelemetry::FirewallPageInit::StartActivity(ushort const *)
0x18000d4b2  cmp     qword ptr [rdi+10h], 0
0x18000d4b7  jz      short loc_18000D531
0x18000d4b9  test    rbx, rbx
0x18000d4bc  jz      short loc_18000D531
0x18000d4be  mov     [rdi+28h], rbx
0x18000d4c2  mov     rcx, rdi; this
0x18000d4c5  call    ?InitNavPane@CHubPage@@IEAAJXZ; CHubPage::InitNavPane(void)
0x18000d4ca  mov     ebx, eax
0x18000d4cc  test    eax, eax
0x18000d4ce  jns     short loc_18000D503
0x18000d4d0  lea     rax, WPP_GLOBAL_Control
0x18000d4d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4de  cmp     rcx, rax
0x18000d4e1  jz      short loc_18000D536
0x18000d4e3  test    byte ptr [rcx+1Ch], 1
0x18000d4e7  jz      short loc_18000D536
0x18000d4e9  mov     edx, 0Ch
0x18000d4ee  mov     r9d, ebx
0x18000d4f1  lea     r8, WPP_041ed7bb04083fded16b958364bb1572_Traceguids
0x18000d4f8  mov     rcx, [rcx+10h]
0x18000d4fc  call    WPP_SF_d
0x18000d501  jmp     short loc_18000D536
0x18000d503  mov     rcx, rdi; this
0x18000d506  call    ?InitUI@CHubPage@@AEAAJXZ; CHubPage::InitUI(void)
0x18000d50b  mov     ebx, eax
0x18000d50d  test    eax, eax
0x18000d50f  jns     short loc_18000D536
0x18000d511  lea     rax, WPP_GLOBAL_Control
0x18000d518  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d51f  cmp     rcx, rax
0x18000d522  jz      short loc_18000D536
0x18000d524  test    byte ptr [rcx+1Ch], 1
0x18000d528  jz      short loc_18000D536
0x18000d52a  mov     edx, 0Dh
0x18000d52f  jmp     short loc_18000D4EE
0x18000d531  mov     ebx, 80004005h
0x18000d536  mov     edx, ebx
0x18000d538  lea     rcx, [rsp+188h+var_168]
0x18000d53d  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000d542  mov     rcx, cs:g_Provider
0x18000d549  test    rcx, rcx
0x18000d54c  jz      short loc_18000D562
0x18000d54e  xor     r9d, r9d
0x18000d551  xor     r8d, r8d
0x18000d554  lea     rdx, FwCplInitialize_End
0x18000d55b  call    cs:__imp_EtwEventWrite
0x18000d561  nop
0x18000d562  lea     rcx, [rsp+188h+var_168]; this
0x18000d567  call    ??1FirewallPageInit@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::FirewallPageInit::~FirewallPageInit(void)
0x18000d56c  mov     eax, ebx
0x18000d56e  mov     rcx, [rsp+188h+var_18]
0x18000d576  xor     rcx, rsp; StackCookie
0x18000d579  call    __security_check_cookie
0x18000d57e  mov     rbx, [rsp+188h+arg_8]
0x18000d586  add     rsp, 180h
0x18000d58d  pop     rdi
0x18000d58e  retn
```
