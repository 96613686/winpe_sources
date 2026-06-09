# InputStateManager::Initialize(void)

- ea: `0x180029258`
- end: `0x1800294ef`
- name: `?Initialize@InputStateManager@@IEAAJXZ`
- size: `663`
- prototype: `__int64 __fastcall(InputStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180029160`

## callees

- `0x180012b74`
- `0x180029258`
- `0x18003afb0`
- `0x18003cc50`
- `0x18008dcac`
- `0x18008e194`
- `0x18008e2f8`
- `0x1800b1b44`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180029480`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180029480`
- `CoreMessaging!CoreUICreate` at `0x1800292c4`
- `CoreMessaging!CoreUICreate` at `0x1800292c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800294ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800294ce`
- `win32u!NtMITUpdateInputGlobals` at `0x180029496`
- `win32u!NtMITUpdateInputGlobals` at `0x180029496`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800294c6`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800294c6`

## string_xrefs

- `0x180029408`: `System\Input\DeviceCommandEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall InputStateManager::Initialize(InputStateManager *this, __int64 a2)
{
  int v3; // eax
  _QWORD *v4; // r15
  int v5; // eax
  const char *v6; // r9
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HLOCAL, char *); // rbx
  int v9; // eax
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, __int64 (__fastcall *)(void *, void *, int), InputStateManager *, _QWORD); // rdi
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  int v16; // eax
  HKEY v17; // rcx
  DWORD TickCount; // eax
  __int64 v19; // rcx
  int v21; // [rsp+20h] [rbp-20h]
  int v22; // [rsp+20h] [rbp-20h]
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  char v24; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v26; // [rsp+78h] [rbp+38h] BYREF

  hMem = 0;
  v24 = 0;
  v26 = 0;
  v3 = InputSecurityDescriptor::QueryDescriptor(&hMem, a2, c_wszMessagePortNames);
  if ( v3 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputstatemanager\\lib\\inputstatemanager.cpp",
      (const char *)(unsigned int)v3,
      v21);
  v4 = (_QWORD *)((char *)this + 48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
  v5 = CoreUICreate((char *)this + 48);
  if ( v5 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputstatemanager\\lib\\inputstatemanager.cpp",
      (const char *)(unsigned int)v5,
      v21);
  if ( !ISMScenarios::s_instance )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\system\\ismscenarios.cpp",
      v6);
  if ( !*(_DWORD *)ISMScenarios::s_instance )
  {
    v7 = *v4;
    v8 = *(__int64 (__fastcall **)(__int64, HLOCAL, char *))(*(_QWORD *)*v4 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 56);
    v9 = v8(v7, hMem, (char *)this + 56);
    if ( v9 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputstatemanager\\lib\\inputstatemanager.cpp",
        (const char *)(unsigned int)v9,
        v21);
    wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
      (char *)this + 64,
      *v4);
    v10 = *v4;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(void *, void *, int), InputStateManager *, _QWORD))(*(_QWORD *)*v4 + 104LL);
    wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
      (char *)this + 64,
      *((_QWORD *)this + 8));
    v22 = (_DWORD)this + 72;
    v12 = v11(v10, InputStateManager::OnDeviceCommandStatic, this, *((_QWORD *)this + 7));
    if ( v12 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputstatemanager\\lib\\inputstatemanager.cpp",
        (const char *)(unsigned int)v12,
        v22);
    v13 = *v4;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v4 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    v15 = v14(v13, &v26);
    if ( v15 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputstatemanager\\lib\\inputstatemanager.cpp",
        (const char *)(unsigned int)v15,
        v22);
    v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64))(*(_QWORD *)v26 + 40LL))(
            v26,
            L"System\\Input\\DeviceCommandEndpoint",
            *((_QWORD *)this + 9),
            1);
    if ( v16 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputstatemanager\\lib\\inputstatemanager.cpp",
        (const char *)(unsigned int)v16,
        v22);
    TestCommandHost::Initialize();
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 184);
  if ( RegistryWatcher::Create(
         v17,
         L"System\\Input",
         this,
         (void (*)(void *, HKEY))InputStateManager::OnInputRegistryKeyChangeStatic,
         (struct RegistryWatcher **)this + 23) < 0 )
  {
    *((_DWORD *)this + 48) = 6;
    *((_DWORD *)this + 49) = -1;
  }
  TickCount = GetTickCount();
  NtMITUpdateInputGlobals(TickCount, 0, 0, 0xFFFFFFFFLL, 0);
  v19 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( hMem )
  {
    if ( v24 )
      FreeTransientObjectSecurityDescriptor();
    else
      LocalFree(hMem);
  }
  return 0;
}

```

## disassembly

```asm
0x180029258  mov     [rsp-28h+arg_0], rbx
0x18002925d  mov     [rsp-28h+arg_10], rsi
0x180029262  push    rbp
0x180029263  push    rdi
0x180029264  push    r12
0x180029266  push    r14
0x180029268  push    r15
0x18002926a  mov     rbp, rsp
0x18002926d  sub     rsp, 40h
0x180029271  mov     r14, rcx
0x180029274  mov     [rbp+hMem], 0
0x18002927c  mov     [rbp+var_8], 0
0x180029280  mov     [rbp+arg_8], 0
0x180029288  mov     r8, cs:?c_wszMessagePortNames@@3QBQEBGB; ushort const * const near * const c_wszMessagePortNames
0x18002928f  lea     rcx, [rbp+hMem]
0x180029293  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x180029298  mov     rcx, [rbp+28h]; this
0x18002929c  test    eax, eax
0x18002929e  jns     short loc_1800292B5
0x1800292a0  mov     r9d, eax; char *
0x1800292a3  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800292aa  mov     edx, 8Bh; void *
0x1800292af  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800292b5  lea     r15, [r14+30h]
0x1800292b9  mov     rcx, r15
0x1800292bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800292c1  mov     rcx, r15
0x1800292c4  call    cs:__imp_CoreUICreate
0x1800292ca  mov     rcx, [rbp+28h]; this
0x1800292ce  test    eax, eax
0x1800292d0  jns     short loc_1800292E7
0x1800292d2  mov     r9d, eax; char *
0x1800292d5  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800292dc  mov     edx, 8Dh; void *
0x1800292e1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800292e7  mov     rcx, [rbp+28h]; this
0x1800292eb  mov     rax, cs:?s_instance@ISMScenarios@@0PEAV1@EA; ISMScenarios * ISMScenarios::s_instance
0x1800292f2  test    rax, rax
0x1800292f5  jnz     short loc_180029307
0x1800292f7  lea     r8, aOnecoreuapWind_61; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800292fe  lea     edx, [rax+1Ch]; void *
0x180029301  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180029307  cmp     dword ptr [rax], 0
0x18002930a  jnz     loc_18002943A
0x180029310  mov     rdi, [r15]
0x180029313  mov     rax, [rdi]
0x180029316  mov     rbx, [rax+40h]
0x18002931a  lea     r12, [r14+38h]
0x18002931e  mov     rcx, r12
0x180029321  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029326  mov     r8, r12
0x180029329  mov     rdx, [rbp+hMem]
0x18002932d  mov     rcx, rdi
0x180029330  mov     rax, rbx
0x180029333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029338  mov     rcx, [rbp+28h]; this
0x18002933c  test    eax, eax
0x18002933e  jns     short loc_180029355
0x180029340  mov     r9d, eax; char *
0x180029343  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002934a  mov     edx, 95h; void *
0x18002934f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180029355  lea     rbx, [r14+40h]
0x180029359  mov     rdx, [r15]
0x18002935c  mov     rcx, rbx
0x18002935f  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x180029364  mov     rsi, [r15]
0x180029367  mov     rax, [rsi]
0x18002936a  mov     rdi, [rax+68h]
0x18002936e  mov     rdx, [rbx]
0x180029371  mov     rcx, rbx
0x180029374  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x180029379  lea     rdx, [rbx+8]
0x18002937d  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180029382  mov     r9, [r12]
0x180029386  mov     r8, r14
0x180029389  lea     rdx, ?OnDeviceCommandStatic@InputStateManager@@SAJPEAX0H@Z; InputStateManager::OnDeviceCommandStatic(void *,void *,int)
0x180029390  mov     rcx, rsi
0x180029393  mov     rax, rdi
0x180029396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002939b  mov     rcx, [rbp+28h]; this
0x18002939f  test    eax, eax
0x1800293a1  jns     short loc_1800293B8
0x1800293a3  mov     r9d, eax; char *
0x1800293a6  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800293ad  mov     edx, 9Dh; void *
0x1800293b2  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800293b8  mov     rdi, [r15]
0x1800293bb  mov     rax, [rdi]
0x1800293be  mov     rbx, [rax+18h]
0x1800293c2  lea     rcx, [rbp+arg_8]
0x1800293c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800293cb  lea     rdx, [rbp+arg_8]
0x1800293cf  mov     rcx, rdi
0x1800293d2  mov     rax, rbx
0x1800293d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293da  mov     rcx, [rbp+28h]; this
0x1800293de  test    eax, eax
0x1800293e0  jns     short loc_1800293F7
0x1800293e2  mov     r9d, eax; char *
0x1800293e5  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800293ec  mov     edx, 9Fh; void *
0x1800293f1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800293f7  mov     rcx, [rbp+arg_8]
0x1800293fb  mov     rax, [rcx]
0x1800293fe  mov     r9d, 1
0x180029404  mov     r8, [r14+48h]
0x180029408  lea     rdx, aSystemInputDev; "System\\Input\\DeviceCommandEndpoint"
0x18002940f  mov     rax, [rax+28h]
0x180029413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029418  mov     rcx, [rbp+28h]; this
0x18002941c  test    eax, eax
0x18002941e  jns     short loc_180029435
0x180029420  mov     r9d, eax; char *
0x180029423  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002942a  mov     edx, 0A4h; void *
0x18002942f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180029435  call    ?Initialize@TestCommandHost@@SAXXZ; TestCommandHost::Initialize(void)
0x18002943a  lea     rbx, [r14+0B8h]
0x180029441  mov     rcx, rbx
0x180029444  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029449  mov     qword ptr [rsp+40h+var_20], rbx; struct RegistryWatcher **
0x18002944e  lea     r9, ?OnInputRegistryKeyChangeStatic@InputStateManager@@SAXPEAXPEAUHKEY__@@@Z; void (*)(void *, HKEY)
0x180029455  mov     r8, r14; void *
0x180029458  lea     rdx, aSystemInput; "System\\Input"
0x18002945f  call    ?Create@RegistryWatcher@@SAJPEAUHKEY__@@PEBGPEAXP6AX20@ZPEAPEAV1@@Z; RegistryWatcher::Create(HKEY__ *,ushort const *,void *,void (*)(void *,HKEY__ *),RegistryWatcher * *)
0x180029464  test    eax, eax
0x180029466  jns     short loc_18002947E
0x180029468  mov     dword ptr [r14+0C0h], 6
0x180029473  mov     dword ptr [r14+0C4h], 0FFFFFFFFh
0x18002947e  xor     ebx, ebx
0x180029480  call    cs:__imp_GetTickCount
0x180029486  mov     ecx, eax
0x180029488  mov     [rsp+40h+var_20], ebx
0x18002948c  or      r9d, 0FFFFFFFFh
0x180029490  movzx   r8d, bx
0x180029494  xor     edx, edx
0x180029496  call    cs:__imp_NtMITUpdateInputGlobals
0x18002949c  nop
0x18002949d  mov     rcx, [rbp+arg_8]
0x1800294a1  test    rcx, rcx
0x1800294a4  jz      short loc_1800294B7
0x1800294a6  mov     [rbp+arg_8], rbx
0x1800294aa  mov     rax, [rcx]
0x1800294ad  mov     rax, [rax+10h]
0x1800294b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294b6  nop
0x1800294b7  mov     rcx, [rbp+hMem]; hMem
0x1800294bb  test    rcx, rcx
0x1800294be  jz      short loc_1800294D4
0x1800294c0  cmp     [rbp+var_8], 0
0x1800294c4  jz      short loc_1800294CE
0x1800294c6  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800294cc  jmp     short loc_1800294D4
0x1800294ce  call    cs:__imp_LocalFree
0x1800294d4  xor     eax, eax
0x1800294d6  lea     r11, [rsp+40h+var_s0]
0x1800294db  mov     rbx, [r11+30h]
0x1800294df  mov     rsi, [r11+40h]
0x1800294e3  mov     rsp, r11
0x1800294e6  pop     r15
0x1800294e8  pop     r14
0x1800294ea  pop     r12
0x1800294ec  pop     rdi
0x1800294ed  pop     rbp
0x1800294ee  retn
```
