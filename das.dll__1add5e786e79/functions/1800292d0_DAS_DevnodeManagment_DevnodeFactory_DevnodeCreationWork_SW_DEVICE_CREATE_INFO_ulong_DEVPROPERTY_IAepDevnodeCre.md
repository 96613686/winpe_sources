# DAS::DevnodeManagment::DevnodeFactory::DevnodeCreationWork(_SW_DEVICE_CREATE_INFO,ulong,_DEVPROPERTY *,IAepDevnodeCreationCallback *,IAepDevnode * *)

- ea: `0x1800292d0`
- end: `0x1800295f4`
- name: `?DevnodeCreationWork@DevnodeFactory@DevnodeManagment@DAS@@AEAAJU_SW_DEVICE_CREATE_INFO@@KPEAU_DEVPROPERTY@@PEAUIAepDevnodeCreationCallback@@PEAPEAUIAepDevnode@@@Z`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c3f0`

## callees

- `0x1800074c0`
- `0x180008a50`
- `0x180015b64`
- `0x180018ed4`
- `0x18001dfe0`
- `0x18001eae0`
- `0x180023890`
- `0x180028b0c`
- `0x1800292d0`
- `0x18002a948`
- `0x180034c00`
- `0x18003ab5c`
- `0x18005b8d4`
- `0x18005b988`
- `0x18005d7b0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002932f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800293a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800293e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029577`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800295b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002932f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800293a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800293e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029577`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800295b1`

## string_xrefs

- `0x180029315`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002938d`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002943c`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x1800294f8`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x180029535`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DAS::DevnodeManagment::DevnodeFactory::DevnodeCreationWork(
        __int64 a1,
        const struct _SW_DEVICE_CREATE_INFO *a2,
        unsigned int a3,
        struct _DEVPROPERTY *a4,
        unsigned __int16 *a5,
        __int64 a6)
{
  int RootInstanceId; // ebx
  DAS::DevnodeManagment::DevnodeManager *v12; // rbx
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  struct DAS::DevnodeManagment::Devnode **v16; // rdx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, _QWORD); // rbx
  int v18; // eax
  unsigned int v19; // edi
  int v20; // [rsp+20h] [rbp-38h]
  int v21; // [rsp+20h] [rbp-38h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-28h] BYREF
  PSRWLOCK v23; // [rsp+38h] [rbp-20h] BYREF
  struct DAS::DevnodeManagment::Devnode *v24; // [rsp+40h] [rbp-18h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  struct DAS::DevnodeManagment::Devnode *v27; // [rsp+A0h] [rbp+48h] BYREF

  wil::AcquireSRWLockShared(&SRWLock, (RTL_SRWLOCK *)(a1 + 224));
  if ( !*(_BYTE *)(a1 + 232) )
  {
    RootInstanceId = -2140930029;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C1,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)0x80640013LL,
      v20);
LABEL_3:
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return (unsigned int)RootInstanceId;
  }
  a5 = 0;
  wil::AcquireSRWLockShared(&v23, (RTL_SRWLOCK *)(a1 + 120));
  if ( *(_QWORD *)(a1 + 128) == *(_QWORD *)(a1 + 136) )
  {
    v12 = g_devnodeManager;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &a5,
      0);
    RootInstanceId = DAS::DevnodeManagment::DevnodeManager::GetRootInstanceId(v12, &a5);
    if ( RootInstanceId < 0 )
    {
      v13 = 1485;
      goto LABEL_9;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &a5,
      0);
    RootInstanceId = DafStringCopy(*(_QWORD *)(**(_QWORD **)(a1 + 128) + 16LL), &a5);
    if ( RootInstanceId < 0 )
    {
      v13 = 1489;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)(unsigned int)RootInstanceId,
        v20);
      if ( v23 )
        ReleaseSRWLockShared(v23);
      goto LABEL_11;
    }
  }
  if ( v23 )
    ReleaseSRWLockShared(v23);
  v27 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v14 = (unsigned __int16 *)(a1 + 32);
  if ( *(_QWORD *)(a1 + 56) > 7u )
    v14 = *(unsigned __int16 **)v14;
  RootInstanceId = DAS::DevnodeManagment::Devnode::Create(v14, a5, a2, a3, a4, &v27);
  if ( RootInstanceId < 0 )
  {
    v15 = 1500;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)(unsigned int)RootInstanceId,
      v21);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&a5);
    goto LABEL_3;
  }
  RootInstanceId = DAS::DevnodeManagment::DevnodeFactory::PersistDevnodeCreationInfo(
                     (DAS::DevnodeManagment::DevnodeFactory *)a1,
                     *((const unsigned __int16 **)v27 + 2),
                     a2);
  if ( RootInstanceId < 0 )
  {
    v15 = 1501;
    goto LABEL_20;
  }
  wil::AcquireSRWLockExclusive(&v23, (RTL_SRWLOCK *)(a1 + 120));
  v16 = *(struct DAS::DevnodeManagment::Devnode ***)(a1 + 136);
  if ( v16 == *(struct DAS::DevnodeManagment::Devnode ***)(a1 + 144) )
  {
    std::vector<Microsoft::WRL::ComPtr<IAepDevnodeInterface>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IAepDevnodeInterface> &>(
      (__int64 *)(a1 + 128),
      (__int64)v16,
      (__int64 *)&v27);
  }
  else
  {
    *v16 = v27;
    Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>::InternalAddRef(v16);
    *(_QWORD *)(a1 + 136) += 8LL;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v23);
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 48LL) )
  {
    RootInstanceId = (**(__int64 (__fastcall ***)(struct DAS::DevnodeManagment::Devnode *, GUID *, __int64))v27)(
                       v27,
                       &GUID_a1df39ac_c78d_4e56_97ff_be8ca7e7373f,
                       a6);
    if ( RootInstanceId < 0 )
    {
      v15 = 1516;
      goto LABEL_20;
    }
  }
  else
  {
    v23 = (PSRWLOCK)a1;
    v24 = v27;
    Microsoft::WRL::Details::Make<DAS::DevnodeManagment::DevnodeProxy,DAS::DevnodeManagment::Devnode *,DAS::DevnodeManagment::DevnodeFactory *>(
      &v25,
      (__int64 *)&v24,
      (__int64 *)&v23);
    v17 = v25;
    if ( !v25 )
    {
      RootInstanceId = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E7,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)0x8007000ELL,
        v21);
      goto LABEL_21;
    }
    v18 = (**v25)(v25, &GUID_a1df39ac_c78d_4e56_97ff_be8ca7e7373f, a6);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E8,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)(unsigned int)v18,
        v21);
      if ( v17 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v17)[2])(v17);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&a5);
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
      return v19;
    }
    if ( v17 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v17)[2])(v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&a5);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x1800292d0  push    rbp
0x1800292d2  push    rbx
0x1800292d3  push    rsi
0x1800292d4  push    rdi
0x1800292d5  push    r12
0x1800292d7  push    r13
0x1800292d9  push    r14
0x1800292db  push    r15
0x1800292dd  mov     rbp, rsp
0x1800292e0  sub     rsp, 58h
0x1800292e4  mov     r12, r9
0x1800292e7  mov     r13d, r8d
0x1800292ea  mov     r15, rdx
0x1800292ed  mov     rsi, rcx
0x1800292f0  lea     rdx, [rcx+0E0h]
0x1800292f7  lea     rcx, [rbp+SRWLock]
0x1800292fb  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180029300  cmp     byte ptr [rsi+0E8h], 0
0x180029307  jnz     short loc_18002933C
0x180029309  mov     rcx, [rbp+40h]; this
0x18002930d  mov     ebx, 80640013h
0x180029312  mov     r9d, ebx; char *
0x180029315  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002931c  mov     edx, 5C1h; void *
0x180029321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029326  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002932a  test    rcx, rcx
0x18002932d  jz      short loc_180029335
0x18002932f  call    cs:__imp_ReleaseSRWLockShared
0x180029335  mov     eax, ebx
0x180029337  jmp     loc_1800295B9
0x18002933c  mov     [rbp+arg_20], 0
0x180029344  lea     rdx, [rsi+78h]
0x180029348  lea     rcx, [rbp+var_20]
0x18002934c  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180029351  lea     rdi, [rsi+80h]
0x180029358  mov     rax, [rdi+8]
0x18002935c  xor     edx, edx
0x18002935e  lea     rcx, [rbp+arg_20]
0x180029362  cmp     [rdi], rax
0x180029365  jnz     short loc_1800293BA
0x180029367  mov     rbx, cs:?g_devnodeManager@@3V?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@A; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager> g_devnodeManager
0x18002936e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180029373  lea     rdx, [rbp+arg_20]; unsigned __int16 **
0x180029377  mov     rcx, rbx; this
0x18002937a  call    ?GetRootInstanceId@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::GetRootInstanceId(ushort * *)
0x18002937f  mov     ebx, eax
0x180029381  test    eax, eax
0x180029383  jns     short loc_1800293DF
0x180029385  mov     edx, 5CDh; void *
0x18002938a  mov     r9d, ebx; char *
0x18002938d  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x180029394  mov     rcx, [rbp+40h]; this
0x180029398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002939d  mov     rcx, [rbp+var_20]; SRWLock
0x1800293a1  test    rcx, rcx
0x1800293a4  jz      short loc_1800293AC
0x1800293a6  call    cs:__imp_ReleaseSRWLockShared
0x1800293ac  lea     rcx, [rbp+arg_20]
0x1800293b0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800293b5  jmp     loc_180029326
0x1800293ba  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800293bf  mov     rax, [rdi]
0x1800293c2  mov     rcx, [rax]
0x1800293c5  lea     rdx, [rbp+arg_20]
0x1800293c9  mov     rcx, [rcx+10h]
0x1800293cd  call    DafStringCopy
0x1800293d2  mov     ebx, eax
0x1800293d4  test    eax, eax
0x1800293d6  jns     short loc_1800293DF
0x1800293d8  mov     edx, 5D1h
0x1800293dd  jmp     short loc_18002938A
0x1800293df  mov     rcx, [rbp+var_20]; SRWLock
0x1800293e3  test    rcx, rcx
0x1800293e6  jz      short loc_1800293EE
0x1800293e8  call    cs:__imp_ReleaseSRWLockShared
0x1800293ee  mov     [rbp+arg_0], 0
0x1800293f6  lea     rcx, [rbp+arg_0]
0x1800293fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800293ff  lea     rcx, [rsi+20h]
0x180029403  cmp     qword ptr [rcx+18h], 7
0x180029408  jbe     short loc_18002940D
0x18002940a  mov     rcx, [rcx]; unsigned __int16 *
0x18002940d  lea     rax, [rbp+arg_0]
0x180029411  mov     [rsp+58h+var_30], rax; struct DAS::DevnodeManagment::Devnode **
0x180029416  mov     [rsp+58h+var_38], r12; int
0x18002941b  mov     r9d, r13d; unsigned int
0x18002941e  mov     r8, r15; struct _SW_DEVICE_CREATE_INFO *
0x180029421  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x180029425  call    ?Create@Devnode@DevnodeManagment@DAS@@SAJPEBG0PEBU_SW_DEVICE_CREATE_INFO@@KPEAU_DEVPROPERTY@@PEAPEAV123@@Z; DAS::DevnodeManagment::Devnode::Create(ushort const *,ushort const *,_SW_DEVICE_CREATE_INFO const *,ulong,_DEVPROPERTY *,DAS::DevnodeManagment::Devnode * *)
0x18002942a  mov     ebx, eax
0x18002942c  test    eax, eax
0x18002942e  jns     short loc_180029456
0x180029430  mov     edx, 5DCh; void *
0x180029435  mov     rcx, [rbp+40h]; this
0x180029439  mov     r9d, ebx; char *
0x18002943c  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x180029443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029448  lea     rcx, [rbp+arg_0]
0x18002944c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029451  jmp     loc_1800293AC
0x180029456  mov     r8, r15; struct _SW_DEVICE_CREATE_INFO *
0x180029459  mov     rdx, [rbp+arg_0]
0x18002945d  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180029461  mov     rcx, rsi; this
0x180029464  call    ?PersistDevnodeCreationInfo@DevnodeFactory@DevnodeManagment@DAS@@AEAAJPEBGPEBU_SW_DEVICE_CREATE_INFO@@@Z; DAS::DevnodeManagment::DevnodeFactory::PersistDevnodeCreationInfo(ushort const *,_SW_DEVICE_CREATE_INFO const *)
0x180029469  mov     ebx, eax
0x18002946b  test    eax, eax
0x18002946d  jns     short loc_180029476
0x18002946f  mov     edx, 5DDh
0x180029474  jmp     short loc_180029435
0x180029476  lea     rdx, [rsi+78h]
0x18002947a  lea     rcx, [rbp+var_20]
0x18002947e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180029483  mov     rdx, [rdi+8]
0x180029487  cmp     rdx, [rdi+10h]
0x18002948b  jz      short loc_1800294A3
0x18002948d  mov     rax, [rbp+arg_0]
0x180029491  mov     [rdx], rax
0x180029494  mov     rcx, rdx
0x180029497  call    ?InternalAddRef@?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>::InternalAddRef(void)
0x18002949c  add     qword ptr [rdi+8], 8
0x1800294a1  jmp     short loc_1800294AF
0x1800294a3  lea     r8, [rbp+arg_0]
0x1800294a7  mov     rcx, rdi
0x1800294aa  call    ??$_Emplace_reallocate@AEAV?$ComPtr@UIAepDevnodeInterface@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIAepDevnodeInterface@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIAepDevnodeInterface@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIAepDevnodeInterface@@@WRL@Microsoft@@QEAV234@AEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<IAepDevnodeInterface>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IAepDevnodeInterface> &>(Microsoft::WRL::ComPtr<IAepDevnodeInterface> * const,Microsoft::WRL::ComPtr<IAepDevnodeInterface> &)
0x1800294af  lea     rcx, [rbp+var_20]
0x1800294b3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800294b8  mov     rax, [rsi+60h]
0x1800294bc  cmp     dword ptr [rax+30h], 0
0x1800294c0  jnz     loc_1800295CA
0x1800294c6  mov     [rbp+var_20], rsi
0x1800294ca  mov     rax, [rbp+arg_0]
0x1800294ce  mov     [rbp+var_18], rax
0x1800294d2  lea     r8, [rbp+var_20]
0x1800294d6  lea     rdx, [rbp+var_18]
0x1800294da  lea     rcx, [rbp+var_10]
0x1800294de  call    ??$Make@VDevnodeProxy@DevnodeManagment@DAS@@PEAVDevnode@23@PEAVDevnodeFactory@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VDevnodeProxy@DevnodeManagment@DAS@@@12@$$QEAPEAVDevnode@DevnodeManagment@DAS@@$$QEAPEAVDevnodeFactory@56@@Z; Microsoft::WRL::Details::Make<DAS::DevnodeManagment::DevnodeProxy,DAS::DevnodeManagment::Devnode *,DAS::DevnodeManagment::DevnodeFactory *>(DAS::DevnodeManagment::Devnode * &&,DAS::DevnodeManagment::DevnodeFactory * &&)
0x1800294e3  mov     rbx, [rbp+var_10]
0x1800294e7  test    rbx, rbx
0x1800294ea  jnz     short loc_18002950F
0x1800294ec  mov     rcx, [rbp+40h]; this
0x1800294f0  mov     ebx, 8007000Eh
0x1800294f5  mov     r9d, ebx; char *
0x1800294f8  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x1800294ff  mov     edx, 5E7h; void *
0x180029504  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029509  nop
0x18002950a  jmp     loc_180029448
0x18002950f  mov     rax, [rbx]
0x180029512  mov     r8, [rbp+arg_28]
0x180029516  lea     rdx, _GUID_a1df39ac_c78d_4e56_97ff_be8ca7e7373f
0x18002951d  mov     rcx, rbx
0x180029520  mov     rax, [rax]
0x180029523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029528  mov     edi, eax
0x18002952a  test    eax, eax
0x18002952c  jns     short loc_180029581
0x18002952e  mov     rcx, [rbp+40h]; this
0x180029532  mov     r9d, eax; char *
0x180029535  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002953c  mov     edx, 5E8h; void *
0x180029541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029546  nop
0x180029547  test    rbx, rbx
0x18002954a  jz      short loc_18002955C
0x18002954c  mov     rax, [rbx]
0x18002954f  mov     rcx, rbx
0x180029552  mov     rax, [rax+10h]
0x180029556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002955b  nop
0x18002955c  lea     rcx, [rbp+arg_0]
0x180029560  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029565  lea     rcx, [rbp+arg_20]
0x180029569  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002956e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180029572  test    rcx, rcx
0x180029575  jz      short loc_18002957D
0x180029577  call    cs:__imp_ReleaseSRWLockShared
0x18002957d  mov     eax, edi
0x18002957f  jmp     short loc_1800295B9
0x180029581  test    rbx, rbx
0x180029584  jz      short loc_180029596
0x180029586  mov     rax, [rbx]
0x180029589  mov     rcx, rbx
0x18002958c  mov     rax, [rax+10h]
0x180029590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029595  nop
0x180029596  lea     rcx, [rbp+arg_0]
0x18002959a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002959f  lea     rcx, [rbp+arg_20]
0x1800295a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800295a8  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800295ac  test    rcx, rcx
0x1800295af  jz      short loc_1800295B7
0x1800295b1  call    cs:__imp_ReleaseSRWLockShared
0x1800295b7  xor     eax, eax
0x1800295b9  add     rsp, 58h
0x1800295bd  pop     r15
0x1800295bf  pop     r14
0x1800295c1  pop     r13
0x1800295c3  pop     r12
0x1800295c5  pop     rdi
0x1800295c6  pop     rsi
0x1800295c7  pop     rbx
0x1800295c8  pop     rbp
0x1800295c9  retn
0x1800295ca  mov     rcx, [rbp+arg_0]
0x1800295ce  mov     rax, [rcx]
0x1800295d1  mov     r8, [rbp+arg_28]
0x1800295d5  lea     rdx, _GUID_a1df39ac_c78d_4e56_97ff_be8ca7e7373f
0x1800295dc  mov     rax, [rax]
0x1800295df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295e4  mov     ebx, eax
0x1800295e6  test    eax, eax
0x1800295e8  jns     short loc_180029596
0x1800295ea  mov     edx, 5ECh
0x1800295ef  jmp     loc_180029435
```
