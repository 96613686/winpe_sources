# DAS::DevnodeManagment::DevnodeManager::AddUserDevnodes(unsigned __int64)

- ea: `0x18003997c`
- end: `0x180039ce4`
- name: `?AddUserDevnodes@DevnodeManager@DevnodeManagment@DAS@@AEAAJ_K@Z`
- size: `872`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180039508`
- `0x1800397f4`

## callees

- `0x180005770`
- `0x1800074c0`
- `0x1800190f8`
- `0x18001a350`
- `0x18001a760`
- `0x18001eae0`
- `0x180023890`
- `0x18002394c`
- `0x180024d60`
- `0x180025d10`
- `0x1800290c4`
- `0x180029884`
- `0x18002a948`
- `0x1800346a0`
- `0x180034c00`
- `0x18003961c`
- `0x18003997c`
- `0x18003bc80`
- `0x18004ddb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039b2d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039b2d`

## string_xrefs

- `0x1800399cf`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039a74`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039c0d`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039c78`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039bfb`: `%ls with user context token 0x%016llx was already in the user session map!`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::AddUserDevnodes(RTL_SRWLOCK *this, unsigned __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int PerUserSubKey; // eax
  unsigned int v11; // ebx
  PSRWLOCK v12; // rbx
  int v13; // edx
  int v14; // r8d
  int started; // eax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // ebx
  LPCGUID MessageGuid; // [rsp+20h] [rbp-A8h]
  unsigned __int16 *Src; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-80h] BYREF
  __int64 v22; // [rsp+50h] [rbp-78h] BYREF
  char v23; // [rsp+58h] [rbp-70h]
  RTL_SRWLOCK *v24; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v25; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v26[32]; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  Src = 0;
  v4 = DAS::DevnodeManagment::DevnodeManager::UserContextToSidString(a2, &Src);
  v5 = v4;
  if ( v4 >= 0 )
  {
    wil::AcquireSRWLockExclusive(&v24, this + 7);
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v7,
        v8,
        11,
        &WPP_416e81a390623384018c9851ffc16906_Traceguids,
        (__int64)Src);
    v9 = 0;
    while ( 1 )
    {
      v21 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v21,
        0);
      PerUserSubKey = DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(Src, &v21);
      v11 = PerUserSubKey;
      if ( PerUserSubKey < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x116,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
          (const char *)(unsigned int)PerUserSubKey,
          (int)MessageGuid);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v21);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Src);
        return v11;
      }
      v22 = 0;
      v12 = g_StoreManager;
      Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v22);
      MessageGuid = (LPCGUID)&v22;
      if ( (int)Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(v12, -2147483645, v21, 8) >= 0 )
        break;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v13,
          v14,
          12,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          (__int64)Src,
          v9);
      if ( (unsigned int)++v9 > 3 )
        goto LABEL_16;
      Sleep(500 * v9);
      Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v22);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v21);
    }
    started = DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagementForStore((DAS::DevnodeManagment::DevnodeManager *)this);
    v18 = started;
    if ( started >= 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v16,
          v17,
          13,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          (__int64)Src);
LABEL_16:
      Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v22);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v21);
      v25 = a2;
      std::wstring::wstring(v26, Src);
      std::_Tree<std::_Tmap_traits<unsigned __int64,std::wstring,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::wstring>>,0>>::_Emplace<std::pair<unsigned __int64 const,std::wstring>>(
        &this[8],
        &v22,
        &v25);
      std::wstring::_Tidy_deallocate((__int64)v26);
      if ( !v23 )
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x140,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
          (const char *)0x8000FFFFLL,
          (int)"%ls with user context token 0x%016llx was already in the user session map!",
          (const char *)Src,
          a2);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Src);
      return 0;
    }
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        14,
        &WPP_416e81a390623384018c9851ffc16906_Traceguids,
        (__int64)Src,
        started);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)v18,
      (int)MessageGuid);
    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&v22);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v21);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Src);
    return v18;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)(unsigned int)v4,
      (int)MessageGuid);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Src);
    return v5;
  }
}

```

## disassembly

```asm
0x18003997c  mov     [rsp+arg_10], rbx
0x180039981  push    rsi
0x180039982  push    rdi
0x180039983  push    r13
0x180039985  push    r14
0x180039987  push    r15
0x180039989  sub     rsp, 0A0h
0x180039990  mov     rax, cs:__security_cookie
0x180039997  xor     rax, rsp
0x18003999a  mov     [rsp+0C8h+var_38], rax
0x1800399a2  mov     r15, rdx
0x1800399a5  mov     r14, rcx
0x1800399a8  mov     [rsp+0C8h+Src], 0
0x1800399b1  lea     rdx, [rsp+0C8h+Src]; unsigned __int16 **
0x1800399b6  mov     rcx, r15; unsigned __int64
0x1800399b9  call    ?UserContextToSidString@DevnodeManager@DevnodeManagment@DAS@@SAJ_KPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::UserContextToSidString(unsigned __int64,ushort * *)
0x1800399be  mov     ebx, eax
0x1800399c0  test    eax, eax
0x1800399c2  jns     short loc_1800399F2
0x1800399c4  mov     rcx, [rsp+0C8h]; this
0x1800399cc  mov     r9d, eax; char *
0x1800399cf  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x1800399d6  mov     edx, 10Ch; void *
0x1800399db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800399e0  nop
0x1800399e1  lea     rcx, [rsp+0C8h+Src]
0x1800399e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800399eb  mov     eax, ebx
0x1800399ed  jmp     loc_180039CBB
0x1800399f2  lea     rdx, [r14+38h]
0x1800399f6  lea     rcx, [rsp+0C8h+var_68]
0x1800399fb  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180039a00  nop
0x180039a01  lea     r13, WPP_RECORDER_INITIALIZED
0x180039a08  lea     rsi, WPP_416e81a390623384018c9851ffc16906_Traceguids
0x180039a0f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180039a16  jz      short loc_180039A3D
0x180039a18  mov     r9d, 0Bh; int
0x180039a1e  mov     rax, [rsp+0C8h+Src]
0x180039a23  mov     [rsp+0C8h+var_A0], rax; __int64
0x180039a28  mov     [rsp+0C8h+MessageGuid], rsi; int
0x180039a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a34  mov     rcx, [rcx+28h]; int
0x180039a38  call    WPP_RECORDER_SF_S
0x180039a3d  xor     edi, edi
0x180039a3f  mov     [rsp+0C8h+var_80], 0
0x180039a48  xor     edx, edx
0x180039a4a  lea     rcx, [rsp+0C8h+var_80]
0x180039a4f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039a54  lea     rdx, [rsp+0C8h+var_80]; unsigned __int16 **
0x180039a59  mov     rcx, [rsp+0C8h+Src]; Src
0x180039a5e  call    ?MakePerUserSubKey@DevnodeManager@DevnodeManagment@DAS@@SAJPEBGPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(ushort const *,ushort * *)
0x180039a63  mov     ebx, eax
0x180039a65  test    eax, eax
0x180039a67  jns     short loc_180039AAC
0x180039a69  mov     rcx, [rsp+0C8h]; this
0x180039a71  mov     r9d, eax; char *
0x180039a74  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039a7b  mov     edx, 116h; void *
0x180039a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a85  lea     rcx, [rsp+0C8h+var_80]
0x180039a8a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039a8f  nop
0x180039a90  lea     rcx, [rsp+0C8h+var_68]
0x180039a95  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180039a9a  nop
0x180039a9b  lea     rcx, [rsp+0C8h+Src]
0x180039aa0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039aa5  mov     eax, ebx
0x180039aa7  jmp     loc_180039CBB
0x180039aac  mov     [rsp+0C8h+var_78], 0
0x180039ab5  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x180039abc  lea     rcx, [rsp+0C8h+var_78]
0x180039ac1  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180039ac6  lea     rax, [rsp+0C8h+var_78]
0x180039acb  mov     [rsp+0C8h+MessageGuid], rax
0x180039ad0  mov     r9d, 8
0x180039ad6  mov     r8, [rsp+0C8h+var_80]
0x180039adb  mov     rdx, 0FFFFFFFF80000003h
0x180039ae2  mov     rcx, rbx
0x180039ae5  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180039aea  test    eax, eax
0x180039aec  jns     short loc_180039B4C
0x180039aee  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180039af5  jz      short loc_180039B20
0x180039af7  mov     r9d, 0Ch; int
0x180039afd  mov     dword ptr [rsp+0C8h+var_98], edi; char
0x180039b01  mov     rax, [rsp+0C8h+Src]
0x180039b06  mov     [rsp+0C8h+var_A0], rax; __int64
0x180039b0b  mov     [rsp+0C8h+MessageGuid], rsi; MessageGuid
0x180039b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b17  mov     rcx, [rcx+28h]; int
0x180039b1b  call    WPP_RECORDER_SF_Sd
0x180039b20  inc     edi
0x180039b22  cmp     edi, 3
0x180039b25  ja      short loc_180039B96
0x180039b27  imul    ecx, edi, 1F4h; dwMilliseconds
0x180039b2d  call    cs:__imp_Sleep
0x180039b33  lea     rcx, [rsp+0C8h+var_78]
0x180039b38  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180039b3d  lea     rcx, [rsp+0C8h+var_80]
0x180039b42  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039b47  jmp     loc_180039A3F
0x180039b4c  mov     r8, [rsp+0C8h+Src]
0x180039b51  lea     rdx, [rsp+0C8h+var_78]
0x180039b56  mov     rcx, r14; this
0x180039b59  call    ?StartDevnodeManagementForStore@DevnodeManager@DevnodeManagment@DAS@@AEAAJAEAV?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@PEBG@Z; DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagementForStore(Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> &,ushort const *)
0x180039b5e  mov     ebx, eax
0x180039b60  test    eax, eax
0x180039b62  js      loc_180039C3B
0x180039b68  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180039b6f  jz      short loc_180039B96
0x180039b71  mov     r9d, 0Dh; int
0x180039b77  mov     rax, [rsp+0C8h+Src]
0x180039b7c  mov     [rsp+0C8h+var_A0], rax; __int64
0x180039b81  mov     [rsp+0C8h+MessageGuid], rsi; MessageGuid
0x180039b86  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b8d  mov     rcx, [rcx+28h]; int
0x180039b91  call    WPP_RECORDER_SF_S
0x180039b96  lea     rcx, [rsp+0C8h+var_78]
0x180039b9b  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180039ba0  lea     rcx, [rsp+0C8h+var_80]
0x180039ba5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039baa  mov     [rsp+0C8h+var_60], r15
0x180039baf  mov     rdx, [rsp+0C8h+Src]
0x180039bb4  lea     rcx, [rsp+0C8h+var_58]
0x180039bb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180039bbe  nop
0x180039bbf  lea     r8, [rsp+0C8h+var_60]
0x180039bc4  lea     rdx, [rsp+0C8h+var_78]
0x180039bc9  lea     rcx, [r14+40h]
0x180039bcd  call    ??$_Emplace@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CB_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::wstring,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::wstring>>,0>>::_Emplace<std::pair<unsigned __int64 const,std::wstring>>(std::pair<unsigned __int64 const,std::wstring> &&)
0x180039bd2  nop
0x180039bd3  lea     rcx, [rsp+0C8h+var_58]
0x180039bd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039bdd  cmp     [rsp+0C8h+var_70], 0
0x180039be2  jnz     short loc_180039C1F
0x180039be4  mov     rcx, [rsp+0C8h]; this
0x180039bec  mov     qword ptr [rsp+0C8h+var_98], r15
0x180039bf1  mov     rax, [rsp+0C8h+Src]
0x180039bf6  mov     [rsp+0C8h+var_A0], rax; char *
0x180039bfb  lea     rax, aLsWithUserCont; "%ls with user context token 0x%016llx w"...
0x180039c02  mov     [rsp+0C8h+MessageGuid], rax; int
0x180039c07  mov     r9d, 8000FFFFh; char *
0x180039c0d  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039c14  mov     edx, 140h; void *
0x180039c19  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180039c1e  nop
0x180039c1f  lea     rcx, [rsp+0C8h+var_68]
0x180039c24  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180039c29  nop
0x180039c2a  lea     rcx, [rsp+0C8h+Src]
0x180039c2f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039c34  xor     eax, eax
0x180039c36  jmp     loc_180039CBB
0x180039c3b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180039c42  jz      short loc_180039C6D
0x180039c44  mov     r9d, 0Eh; int
0x180039c4a  mov     dword ptr [rsp+0C8h+var_98], ebx; char
0x180039c4e  mov     rax, [rsp+0C8h+Src]
0x180039c53  mov     [rsp+0C8h+var_A0], rax; __int64
0x180039c58  mov     [rsp+0C8h+MessageGuid], rsi; int
0x180039c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c64  mov     rcx, [rcx+28h]; int
0x180039c68  call    WPP_RECORDER_SF_Sd
0x180039c6d  mov     rcx, [rsp+0C8h]; this
0x180039c75  mov     r9d, ebx; char *
0x180039c78  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039c7f  mov     edx, 137h; void *
0x180039c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c89  lea     rcx, [rsp+0C8h+var_78]
0x180039c8e  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180039c93  lea     rcx, [rsp+0C8h+var_80]
0x180039c98  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039c9d  nop
0x180039c9e  lea     rcx, [rsp+0C8h+var_68]
0x180039ca3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180039ca8  nop
0x180039ca9  lea     rcx, [rsp+0C8h+Src]
0x180039cae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039cb3  mov     eax, ebx
0x180039cb5  jmp     short loc_180039CBB
0x180039cb7  mov     eax, dword ptr [rsp+0C8h+Src]
0x180039cbb  mov     rcx, [rsp+0C8h+var_38]
0x180039cc3  xor     rcx, rsp; StackCookie
0x180039cc6  call    __security_check_cookie
0x180039ccb  mov     rbx, [rsp+0C8h+arg_10]
0x180039cd3  add     rsp, 0A0h
0x180039cda  pop     r15
0x180039cdc  pop     r14
0x180039cde  pop     r13
0x180039ce0  pop     rdi
0x180039ce1  pop     rsi
0x180039ce2  retn
```
