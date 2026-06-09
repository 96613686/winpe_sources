# DAS::DevnodeManagment::DevnodeFactory::Close(void)

- ea: `0x18003b3e8`
- end: `0x18003b639`
- name: `?Close@DevnodeFactory@DevnodeManagment@DAS@@QEAAJXZ`
- size: `593`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027bf0`
- `0x180037628`
- `0x180049260`
- `0x18004ecc0`

## callees

- `0x180005770`
- `0x180015b64`
- `0x1800186ac`
- `0x180023890`
- `0x1800240b4`
- `0x180034c00`
- `0x18003b3e8`
- `0x18005d008`
- `0x18005d1a8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b51b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b51b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b509`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b509`

## string_xrefs

- `0x18003b53a`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18003b599`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18003b5f3`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeFactory::Close(RTL_SRWLOCK *this)
{
  int v2; // edx
  int v3; // r8d
  const char *v4; // rax
  const char *v5; // rdi
  RTL_SRWLOCK *v6; // rcx
  RTL_SRWLOCK *Ptr; // rbx
  RTL_SRWLOCK *v8; // r14
  const char *v9; // r15
  PVOID v10; // rcx
  unsigned int v11; // eax
  PVOID v12; // rcx
  unsigned int v13; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  RTL_SRWLOCK *v16; // [rsp+70h] [rbp+8h] BYREF

  _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
    &this[30],
    0xFFFFFFFFLL);
  wil::AcquireSRWLockExclusive(&v16, this + 28);
  if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
  {
    v5 = (const char *)&this[4];
  }
  else
  {
    if ( this[10].Ptr )
    {
      v4 = (const char *)&this[8];
      if ( this[11].Ptr > (PVOID)7 )
        v4 = *(const char **)v4;
    }
    else
    {
      v4 = L"-none passed-";
    }
    v5 = (const char *)&this[4];
    if ( this[7].Ptr <= (PVOID)7 )
      v6 = this + 4;
    else
      v6 = *(RTL_SRWLOCK **)v5;
    WPP_RECORDER_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v2,
      v3,
      14,
      &WPP_f484a48a2ca63e117155ee67294b2084_Traceguids,
      (__int64)v6,
      (__int64)v4);
  }
  LOBYTE(this[29].Ptr) = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
  if ( *((_DWORD *)this[12].Ptr + 12) )
  {
    DAS::DevnodeManagment::remote_devnode_management::free((DAS::DevnodeManagment::remote_devnode_management *)&this[24]);
  }
  else
  {
    Ptr = (RTL_SRWLOCK *)this[22].Ptr;
    if ( Ptr )
    {
      wil::AcquireSRWLockExclusive(&v16, Ptr + 5);
      LOBYTE(Ptr[6].Ptr) = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&this[22]);
    }
    v8 = (RTL_SRWLOCK *)this[21].Ptr;
    if ( v8 )
    {
      if ( *((_QWORD *)v5 + 3) <= 7u )
        v9 = v5;
      else
        v9 = *(const char **)v5;
      AcquireSRWLockExclusive(v8 + 6);
      LODWORD(v8[7].Ptr) = 0;
      ReleaseSRWLockExclusive(v8 + 6);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        0,
        (__int64)"failed to deactivate %ls devnode factory callback",
        v9);
      Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&this[21]);
    }
    if ( this[10].Ptr )
    {
      v12 = this[20].Ptr;
      if ( v12 )
      {
        if ( *((_QWORD *)v5 + 3) > 7u )
          v5 = *(const char **)v5;
        v13 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v12 + 32LL))(v12);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
          (const char *)v13,
          (__int64)"%ls's provider failed to end per-user devnode management",
          v5);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&this[20]);
      }
    }
    else
    {
      v10 = this[19].Ptr;
      if ( v10 )
      {
        if ( *((_QWORD *)v5 + 3) > 7u )
          v5 = *(const char **)v5;
        v11 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v10 + 32LL))(v10);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x109,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
          (const char *)v11,
          (__int64)"%ls's provider failed to end devnode management",
          v5);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&this[19]);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003b3e8  mov     [rsp+arg_8], rbx
0x18003b3ed  mov     [rsp+arg_10], rbp
0x18003b3f2  push    rsi
0x18003b3f3  push    rdi
0x18003b3f4  push    r12
0x18003b3f6  push    r14
0x18003b3f8  push    r15
0x18003b3fa  sub     rsp, 40h
0x18003b3fe  mov     rsi, rcx
0x18003b401  add     rcx, 0F0h
0x18003b408  or      edx, 0FFFFFFFFh
0x18003b40b  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x18003b410  lea     rdx, [rsi+0E0h]
0x18003b417  lea     rcx, [rsp+68h+arg_0]
0x18003b41c  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18003b421  lea     rax, WPP_RECORDER_INITIALIZED
0x18003b428  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003b42f  jz      short loc_18003B490
0x18003b431  cmp     qword ptr [rsi+50h], 0
0x18003b436  jnz     short loc_18003B441
0x18003b438  lea     rax, aNonePassed; "-none passed-"
0x18003b43f  jmp     short loc_18003B44F
0x18003b441  lea     rax, [rsi+40h]
0x18003b445  cmp     qword ptr [rax+18h], 7
0x18003b44a  jbe     short loc_18003B44F
0x18003b44c  mov     rax, [rax]
0x18003b44f  lea     rdi, [rsi+20h]
0x18003b453  cmp     qword ptr [rdi+18h], 7
0x18003b458  jbe     short loc_18003B45F
0x18003b45a  mov     rcx, [rdi]
0x18003b45d  jmp     short loc_18003B462
0x18003b45f  mov     rcx, rdi
0x18003b462  mov     r9d, 0Eh; int
0x18003b468  mov     [rsp+68h+var_38], rax; __int64
0x18003b46d  mov     [rsp+68h+var_40], rcx; __int64
0x18003b472  lea     rax, WPP_f484a48a2ca63e117155ee67294b2084_Traceguids
0x18003b479  mov     [rsp+68h+MessageGuid], rax; MessageGuid
0x18003b47e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b485  mov     rcx, [rcx+28h]; int
0x18003b489  call    WPP_RECORDER_SF_SS
0x18003b48e  jmp     short loc_18003B494
0x18003b490  lea     rdi, [rsi+20h]
0x18003b494  mov     byte ptr [rsi+0E8h], 0
0x18003b49b  lea     rcx, [rsp+68h+arg_0]
0x18003b4a0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18003b4a5  mov     rax, [rsi+60h]
0x18003b4a9  cmp     dword ptr [rax+30h], 0
0x18003b4ad  jnz     loc_18003B612
0x18003b4b3  lea     r14, [rsi+0B0h]
0x18003b4ba  mov     rbx, [r14]
0x18003b4bd  test    rbx, rbx
0x18003b4c0  jz      short loc_18003B4E6
0x18003b4c2  lea     rdx, [rbx+28h]
0x18003b4c6  lea     rcx, [rsp+68h+arg_0]
0x18003b4cb  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18003b4d0  mov     byte ptr [rbx+30h], 0
0x18003b4d4  lea     rcx, [rsp+68h+arg_0]
0x18003b4d9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18003b4de  mov     rcx, r14
0x18003b4e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b4e6  lea     r12, [rsi+0A8h]
0x18003b4ed  mov     r14, [r12]
0x18003b4f1  test    r14, r14
0x18003b4f4  jz      short loc_18003B553
0x18003b4f6  cmp     qword ptr [rdi+18h], 7
0x18003b4fb  jbe     short loc_18003B502
0x18003b4fd  mov     r15, [rdi]
0x18003b500  jmp     short loc_18003B505
0x18003b502  mov     r15, rdi
0x18003b505  lea     rcx, [r14+30h]; SRWLock
0x18003b509  call    cs:__imp_AcquireSRWLockExclusive
0x18003b50f  mov     dword ptr [r14+38h], 0
0x18003b517  lea     rcx, [r14+30h]; SRWLock
0x18003b51b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b521  mov     rcx, [rsp+68h]; this
0x18003b526  mov     [rsp+68h+var_40], r15; char *
0x18003b52b  lea     rax, aFailedToDeacti; "failed to deactivate %ls devnode factor"...
0x18003b532  mov     [rsp+68h+MessageGuid], rax; __int64
0x18003b537  xor     r9d, r9d; char *
0x18003b53a  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18003b541  mov     edx, 101h; void *
0x18003b546  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003b54b  mov     rcx, r12
0x18003b54e  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x18003b553  cmp     qword ptr [rsi+50h], 0
0x18003b558  jnz     short loc_18003B5B8
0x18003b55a  mov     rcx, [rsi+98h]
0x18003b561  test    rcx, rcx
0x18003b564  jz      loc_18003B61E
0x18003b56a  cmp     qword ptr [rdi+18h], 7
0x18003b56f  jbe     short loc_18003B574
0x18003b571  mov     rdi, [rdi]
0x18003b574  mov     rax, [rcx]
0x18003b577  mov     rax, [rax+20h]
0x18003b57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b580  mov     rcx, [rsp+68h]; this
0x18003b585  mov     [rsp+68h+var_40], rdi; char *
0x18003b58a  lea     rdx, aLsSProviderFai; "%ls's provider failed to end devnode ma"...
0x18003b591  mov     [rsp+68h+MessageGuid], rdx; __int64
0x18003b596  mov     r9d, eax; char *
0x18003b599  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18003b5a0  mov     edx, 109h; void *
0x18003b5a5  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003b5aa  lea     rcx, [rsi+98h]
0x18003b5b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b5b6  jmp     short loc_18003B61E
0x18003b5b8  mov     rcx, [rsi+0A0h]
0x18003b5bf  test    rcx, rcx
0x18003b5c2  jz      short loc_18003B61E
0x18003b5c4  cmp     qword ptr [rdi+18h], 7
0x18003b5c9  jbe     short loc_18003B5CE
0x18003b5cb  mov     rdi, [rdi]
0x18003b5ce  mov     rax, [rcx]
0x18003b5d1  mov     rax, [rax+20h]
0x18003b5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5da  mov     rcx, [rsp+68h]; this
0x18003b5df  mov     [rsp+68h+var_40], rdi; char *
0x18003b5e4  lea     rdx, aLsSProviderFai_0; "%ls's provider failed to end per-user d"...
0x18003b5eb  mov     [rsp+68h+MessageGuid], rdx; __int64
0x18003b5f0  mov     r9d, eax; char *
0x18003b5f3  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18003b5fa  mov     edx, 111h; void *
0x18003b5ff  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003b604  lea     rcx, [rsi+0A0h]
0x18003b60b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b610  jmp     short loc_18003B61E
0x18003b612  lea     rcx, [rsi+0C0h]; this
0x18003b619  call    ?free@remote_devnode_management@DevnodeManagment@DAS@@QEAAXXZ; DAS::DevnodeManagment::remote_devnode_management::free(void)
0x18003b61e  xor     eax, eax
0x18003b620  lea     r11, [rsp+68h+var_28]
0x18003b625  mov     rbx, [r11+38h]
0x18003b629  mov     rbp, [r11+40h]
0x18003b62d  mov     rsp, r11
0x18003b630  pop     r15
0x18003b632  pop     r14
0x18003b634  pop     r12
0x18003b636  pop     rdi
0x18003b637  pop     rsi
0x18003b638  retn
```
