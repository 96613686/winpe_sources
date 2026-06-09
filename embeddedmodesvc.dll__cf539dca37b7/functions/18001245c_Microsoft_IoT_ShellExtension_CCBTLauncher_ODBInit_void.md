# Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(void)

- ea: `0x18001245c`
- end: `0x18001273f`
- name: `?ODBInit@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ`
- size: `739`
- prototype: `__int64 __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800114f0`

## callees

- `0x1800037ec`
- `0x180005590`
- `0x180005fc4`
- `0x180008358`
- `0x18000d410`
- `0x180011e74`
- `0x18001245c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001257b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001257b`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x1800124b0`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x1800124c8`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x1800124de`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x180012514`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x1800124b0`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x1800124c8`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x1800124de`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x180012514`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180012559`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180012559`

## string_xrefs

- `0x1800124a6`: `IoTShellExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 **v3; // rsi
  int v4; // ebx
  unsigned int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int UserSid; // ebx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // ebx
  unsigned int v14; // eax
  int v15; // ebx
  unsigned int v16; // eax
  int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE hObject; // [rsp+50h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+58h] [rbp+10h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v21 = v2;
  if ( !*((_BYTE *)this + 209) )
  {
    *((_BYTE *)this + 209) = 1;
    v3 = (__int64 **)((char *)this + 88);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
    if ( (int)CreateOnDemandBrokerClient(L"IoTShellExtension", (char *)this + 88) < 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
      v4 = CreateOnDemandBrokerClient(L"IoTShellExtension", (char *)this + 88);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
      v5 = CreateOnDemandBrokerClient(L"IoTShellExtension", (char *)this + 88);
      if ( v4 != -2147023781 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x312,
          (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
          (const char *)v5,
          v18);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
      v6 = CreateOnDemandBrokerClient(L"IoTShellExtension", (char *)this + 88);
      v7 = v6;
      if ( v6 >= 0 )
        goto LABEL_23;
      v8 = 786;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)v6,
        v18);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
      return v7;
    }
    hObject = 0;
    UserSid = -2147467259;
    if ( *((_BYTE *)this + 208)
      && (unsigned __int8)IsQueryActiveSessionPresent()
      && (unsigned int)QueryUserToken(*((unsigned int *)this + 46), &hObject) )
    {
      UserSid = Microsoft::IoT::ShellExtension::CCBTLauncher::GetUserSid(hObject);
      CloseHandle(hObject);
    }
    v10 = *v3;
    v11 = **v3;
    v12 = *((_QWORD *)this + 25);
    if ( UserSid < 0 )
    {
      if ( (*(int (__fastcall **)(__int64 *, __int64, __int64, char *))(v11 + 32))(v10, 715, v12, (char *)this + 56) < 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, char *))(**v3 + 32))(
                *v3,
                715,
                *((_QWORD *)this + 25),
                (char *)this + 56);
        v16 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, char *))(**v3 + 32))(
                *v3,
                715,
                *((_QWORD *)this + 25),
                (char *)this + 56);
        if ( v15 != -2147023781 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x325,
            (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
            (const char *)v16,
            v18);
        v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, char *))(**v3 + 32))(
               *v3,
               715,
               *((_QWORD *)this + 25),
               (char *)this + 56);
        v7 = v6;
        if ( v6 >= 0 )
          goto LABEL_23;
        v8 = 805;
        goto LABEL_22;
      }
    }
    else if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64, __int64, char *))(v11 + 24))(
                v10,
                *((_QWORD *)this + 24),
                715,
                v12,
                (char *)this + 56) < 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, char *))(**v3 + 24))(
              *v3,
              *((_QWORD *)this + 24),
              715,
              *((_QWORD *)this + 25),
              (char *)this + 56);
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(**v3 + 24))(
              *v3,
              *((_QWORD *)this + 24),
              715,
              *((_QWORD *)this + 25));
      if ( v13 != -2147023781 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x321,
          (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
          (const char *)v14,
          (_DWORD)this + 56);
      v18 = (_DWORD)this + 56;
      v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(**v3 + 24))(
             *v3,
             *((_QWORD *)this + 24),
             715,
             *((_QWORD *)this + 25));
      v7 = v6;
      if ( v6 >= 0 )
        goto LABEL_23;
      v8 = 801;
      goto LABEL_22;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
  return 0;
}

```

## disassembly

```asm
0x18001245c  mov     [rsp+arg_10], rbx
0x180012461  mov     [rsp+arg_18], rbp
0x180012466  push    rsi
0x180012467  push    rdi
0x180012468  push    r14
0x18001246a  sub     rsp, 30h
0x18001246e  mov     rdi, rcx
0x180012471  lea     rbx, [rcx+60h]
0x180012475  mov     rcx, rbx; lpCriticalSection
0x180012478  call    cs:__imp_EnterCriticalSection
0x18001247e  mov     [rsp+48h+arg_8], rbx
0x180012483  cmp     byte ptr [rdi+0D1h], 0
0x18001248a  jnz     loc_180012720
0x180012490  mov     byte ptr [rdi+0D1h], 1
0x180012497  lea     rsi, [rdi+58h]
0x18001249b  mov     rcx, rsi
0x18001249e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800124a3  mov     rdx, rsi
0x1800124a6  lea     rbp, aIotshellextens; "IoTShellExtension"
0x1800124ad  mov     rcx, rbp
0x1800124b0  call    cs:__imp_CreateOnDemandBrokerClient
0x1800124b6  test    eax, eax
0x1800124b8  jns     short loc_18001252E
0x1800124ba  mov     rcx, rsi
0x1800124bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800124c2  mov     rdx, rsi
0x1800124c5  mov     rcx, rbp
0x1800124c8  call    cs:__imp_CreateOnDemandBrokerClient
0x1800124ce  mov     ebx, eax
0x1800124d0  mov     rcx, rsi
0x1800124d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800124d8  mov     rdx, rsi
0x1800124db  mov     rcx, rbp
0x1800124de  call    cs:__imp_CreateOnDemandBrokerClient
0x1800124e4  mov     rcx, [rsp+48h]; this
0x1800124e9  cmp     ebx, 8007045Bh
0x1800124ef  jz      short loc_180012506
0x1800124f1  mov     r9d, eax; char *
0x1800124f4  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800124fb  mov     edx, 312h; void *
0x180012500  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180012506  mov     rcx, rsi
0x180012509  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001250e  mov     rdx, rsi
0x180012511  mov     rcx, rbp
0x180012514  call    cs:__imp_CreateOnDemandBrokerClient
0x18001251a  mov     ebx, eax
0x18001251c  test    eax, eax
0x18001251e  jns     loc_180012712
0x180012524  mov     edx, 312h
0x180012529  jmp     loc_1800126FD
0x18001252e  mov     [rsp+48h+hObject], 0
0x180012537  mov     ebx, 80004005h
0x18001253c  cmp     byte ptr [rdi+0D0h], 0
0x180012543  jz      short loc_180012581
0x180012545  call    IsQueryActiveSessionPresent
0x18001254a  test    al, al
0x18001254c  jz      short loc_180012581
0x18001254e  lea     rdx, [rsp+48h+hObject]
0x180012553  mov     ecx, [rdi+0B8h]
0x180012559  call    cs:__imp_QueryUserToken
0x18001255f  test    eax, eax
0x180012561  jz      short loc_180012581
0x180012563  lea     rdx, [rdi+0C0h]
0x18001256a  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x18001256f  call    ?GetUserSid@CCBTLauncher@ShellExtension@IoT@Microsoft@@CAJPEAXAEAV?$unique_ptr@U_SID@@U?$default_delete@U_SID@@@std@@@std@@@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::GetUserSid(void *,std::unique_ptr<_SID> &)
0x180012574  mov     ebx, eax
0x180012576  mov     rcx, [rsp+48h+hObject]; hObject
0x18001257b  call    cs:__imp_CloseHandle
0x180012581  lea     r14, [rdi+38h]
0x180012585  mov     rcx, [rsi]
0x180012588  mov     rax, [rcx]
0x18001258b  mov     r8, [rdi+0C8h]
0x180012592  mov     ebp, 2CBh
0x180012597  test    ebx, ebx
0x180012599  js      loc_180012667
0x18001259f  mov     qword ptr [rsp+48h+var_28], r14
0x1800125a4  mov     r9, r8
0x1800125a7  mov     r8d, ebp
0x1800125aa  mov     rdx, [rdi+0C0h]
0x1800125b1  mov     rax, [rax+18h]
0x1800125b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ba  test    eax, eax
0x1800125bc  jns     loc_180012720
0x1800125c2  mov     rcx, [rsi]
0x1800125c5  mov     rax, [rcx]
0x1800125c8  mov     qword ptr [rsp+48h+var_28], r14
0x1800125cd  mov     r9, [rdi+0C8h]
0x1800125d4  mov     r8d, ebp
0x1800125d7  mov     rdx, [rdi+0C0h]
0x1800125de  mov     rax, [rax+18h]
0x1800125e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125e7  mov     ebx, eax
0x1800125e9  mov     rcx, [rsi]
0x1800125ec  mov     rdx, [rcx]
0x1800125ef  mov     rax, [rdx+18h]
0x1800125f3  mov     qword ptr [rsp+48h+var_28], r14; int
0x1800125f8  mov     r9, [rdi+0C8h]
0x1800125ff  mov     r8d, ebp
0x180012602  mov     rdx, [rdi+0C0h]
0x180012609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001260e  mov     rcx, [rsp+48h]; this
0x180012613  cmp     ebx, 8007045Bh
0x180012619  jz      short loc_18001262E
0x18001261b  mov     r9d, eax; char *
0x18001261e  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012625  lea     edx, [rbp+56h]; void *
0x180012628  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18001262e  mov     rcx, [rsi]
0x180012631  mov     rax, [rcx]
0x180012634  mov     qword ptr [rsp+48h+var_28], r14
0x180012639  mov     r9, [rdi+0C8h]
0x180012640  mov     r8d, ebp
0x180012643  mov     rdx, [rdi+0C0h]
0x18001264a  mov     rax, [rax+18h]
0x18001264e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012653  mov     ebx, eax
0x180012655  test    eax, eax
0x180012657  jns     loc_180012712
0x18001265d  mov     edx, 321h
0x180012662  jmp     loc_1800126FD
0x180012667  mov     r9, r14
0x18001266a  mov     edx, ebp
0x18001266c  mov     rax, [rax+20h]
0x180012670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012675  test    eax, eax
0x180012677  jns     loc_180012720
0x18001267d  mov     rcx, [rsi]
0x180012680  mov     rax, [rcx]
0x180012683  mov     r9, r14
0x180012686  mov     r8, [rdi+0C8h]
0x18001268d  mov     edx, ebp
0x18001268f  mov     rax, [rax+20h]
0x180012693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012698  mov     ebx, eax
0x18001269a  mov     rcx, [rsi]
0x18001269d  mov     rdx, [rcx]
0x1800126a0  mov     rax, [rdx+20h]
0x1800126a4  mov     r9, r14
0x1800126a7  mov     r8, [rdi+0C8h]
0x1800126ae  mov     edx, ebp
0x1800126b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126b5  mov     rcx, [rsp+48h]; this
0x1800126ba  cmp     ebx, 8007045Bh
0x1800126c0  jz      short loc_1800126D7
0x1800126c2  mov     r9d, eax; char *
0x1800126c5  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800126cc  mov     edx, 325h; void *
0x1800126d1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800126d7  mov     rcx, [rsi]
0x1800126da  mov     rax, [rcx]
0x1800126dd  mov     r9, r14
0x1800126e0  mov     r8, [rdi+0C8h]
0x1800126e7  mov     edx, ebp
0x1800126e9  mov     rax, [rax+20h]
0x1800126ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126f2  mov     ebx, eax
0x1800126f4  test    eax, eax
0x1800126f6  jns     short loc_180012712
0x1800126f8  mov     edx, 325h; void *
0x1800126fd  mov     r9d, eax; char *
0x180012700  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012707  mov     rcx, [rsp+48h]; this
0x18001270c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012711  nop
0x180012712  lea     rcx, [rsp+48h+arg_8]
0x180012717  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001271c  mov     eax, ebx
0x18001271e  jmp     short loc_18001272C
0x180012720  lea     rcx, [rsp+48h+arg_8]
0x180012725  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001272a  xor     eax, eax
0x18001272c  mov     rbx, [rsp+48h+arg_10]
0x180012731  mov     rbp, [rsp+48h+arg_18]
0x180012736  add     rsp, 30h
0x18001273a  pop     r14
0x18001273c  pop     rdi
0x18001273d  pop     rsi
0x18001273e  retn
```
