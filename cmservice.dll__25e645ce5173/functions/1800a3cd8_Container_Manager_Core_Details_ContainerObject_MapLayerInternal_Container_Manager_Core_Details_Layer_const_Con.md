# Container::Manager::Core::Details::ContainerObject::MapLayerInternal(Container::Manager::Core::Details::Layer const &,Container::Manager::Core::Details::ContainerObject::MappedLayer &,bool)

- ea: `0x1800a3cd8`
- end: `0x1800a4352`
- name: `?MapLayerInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVLayer@2345@AEAUMappedLayer@12345@_N@Z`
- size: `1658`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this, const struct Container::Manager::Core::Details::Layer *, struct Container::Manager::Core::Details::ContainerObject::MappedLayer *, bool)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800a3b4c`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x180005704`
- `0x18000da88`
- `0x180016774`
- `0x18003943c`
- `0x18003e9f4`
- `0x18004feb4`
- `0x18005bee8`
- `0x1800601f8`
- `0x1800785d4`
- `0x180078778`
- `0x180080880`
- `0x180080980`
- `0x18008ce18`
- `0x18008d36c`
- `0x18008db38`
- `0x18009970c`
- `0x180099858`
- `0x18009acc0`
- `0x18009b018`
- `0x1800a3b4c`
- `0x1800a3cd8`
- `0x1800ac950`
- `0x1800c67c4`
- `0x1800c6c38`
- `0x180101240`
- `0x180123250`
- `0x180123878`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a3dd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a406b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a40cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a3dd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a406b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a40cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a40ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a411e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a4176`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a40ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a411e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a4176`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3ddd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a4077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a40d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3ddd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a4077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a40d9`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::MapLayerInternal(
        Container::Manager::Core::Details::ContainerObject *this,
        const struct Container::Manager::Core::Details::Layer *a2,
        struct Container::Manager::Core::Details::ContainerObject::MappedLayer *a3,
        char a4)
{
  Container::Manager::Core::ResourceHandle *v8; // rax
  Container::Manager::Core::ResourceHandle *v9; // rsi
  int v10; // eax
  int KryptonSiloSettings; // ebx
  __int64 v12; // rdx
  struct Container::Manager::Core::Details::Layer *v13; // rdi
  DWORD CurrentThreadId; // eax
  int ResourcePath; // eax
  int v17; // eax
  DWORD v18; // eax
  RTL_SRWLOCK *v19; // rcx
  int v20; // edi
  char *v21; // rcx
  char v22; // al
  char *v23; // rcx
  __int64 v24; // rdx
  char *v25; // rcx
  __int64 v26; // r11
  int v27; // [rsp+20h] [rbp-E0h]
  void *v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v29[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[40]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[36]; // [rsp+98h] [rbp-68h] BYREF
  int v34; // [rsp+BCh] [rbp-44h]
  char v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+130h] [rbp+30h]
  __int64 v37; // [rsp+138h] [rbp+38h]
  char v38; // [rsp+150h] [rbp+50h]
  _OWORD v39[2]; // [rsp+158h] [rbp+58h] BYREF
  __int128 v40; // [rsp+178h] [rbp+78h]
  _QWORD v41[2]; // [rsp+190h] [rbp+90h] BYREF
  void *v42[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v43; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v44; // [rsp+1C0h] [rbp+C0h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]
  PSRWLOCK SRWLock; // [rsp+230h] [rbp+130h] BYREF

  if ( *((_QWORD *)a3 + 2) )
  {
    v8 = (Container::Manager::Core::ResourceHandle *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      KryptonSiloSettings = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x125F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)0x8007000ELL,
        v27);
      return (unsigned int)KryptonSiloSettings;
    }
    *((_QWORD *)v8 + 5) = 0;
    *(_QWORD *)v8 = (char *)v8 + 16;
    *((_QWORD *)v8 + 1) = (char *)v8 + 16;
    *((_WORD *)v8 + 8) = 0;
    *((_DWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 9) = 0;
    *((_BYTE *)v8 + 80) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 7) = 0;
    SRWLock = (PSRWLOCK)v8;
    v41[0] = L"ContainerObject_MapLayerIfNeeded";
    v41[1] = 32;
    v10 = Container::Manager::Core::ResourceHandle::Initialize(v8, v41);
    KryptonSiloSettings = v10;
    if ( v10 < 0 )
    {
      v12 = 4705;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v10,
        v27);
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v9);
      operator delete(v9, (const struct std::nothrow_t *)0x58);
      return (unsigned int)KryptonSiloSettings;
    }
    v10 = Container::Manager::Core::Details::ResourceBroker::OpenResource(
            *((_QWORD *)this + 179),
            (char *)a2 + 56,
            2,
            &SRWLock);
    KryptonSiloSettings = v10;
    if ( v10 < 0 )
    {
      v12 = 4709;
      goto LABEL_9;
    }
    v13 = (struct Container::Manager::Core::Details::Layer *)Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(v9);
    AcquireSRWLockExclusive((PSRWLOCK)this + 57);
    CurrentThreadId = GetCurrentThreadId();
    SRWLock = (PSRWLOCK)((char *)this + 456);
    *((_DWORD *)this + 116) = CurrentThreadId;
    v10 = Container::Manager::Core::Details::ContainerObject::MapLayerIfNeeded(
            this,
            v13,
            *((struct Container::Manager::Core::Details::ContainerObject::MappedLayer **)a3 + 2),
            0);
    KryptonSiloSettings = v10;
    if ( v10 < 0 )
    {
      v12 = 4723;
      goto LABEL_9;
    }
    Container::Manager::Core::ResourceHandle::~ResourceHandle(v9);
    operator delete(v9, (const struct std::nothrow_t *)0x58);
  }
  if ( *((_BYTE *)a3 + 312) || !a4 )
  {
LABEL_56:
    if ( !*((_BYTE *)a3 + 456) )
    {
      *(_DWORD *)v32 = 0;
      memset(&v32[8], 0, 32);
      v32[8] = 0;
      v32[32] = 0;
      memset_0(v33, 0, 0x60u);
      v33[0] = 0;
      v35 = 0;
      KryptonSiloSettings = Container::Manager::Core::Details::Layer::GetKryptonSiloSettings(
                              a2,
                              (struct Container::Manager::Core::Details::SiloSettings *)v32,
                              1);
      if ( KryptonSiloSettings < 0 )
      {
        v24 = 4794;
LABEL_59:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)KryptonSiloSettings,
          v27);
        if ( v35 )
          Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)v33);
        if ( v32[32] )
          utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(&v32[8]);
        return (unsigned int)KryptonSiloSettings;
      }
      KryptonSiloSettings = Container::Manager::Core::Details::Silo::AddSiloSettings(
                              (Container::Manager::Core::Details::Silo *)(*((_QWORD *)this + 158) + 1528LL),
                              (const struct Container::Manager::Core::Details::SiloSettings *)v32);
      if ( KryptonSiloSettings < 0 )
      {
        v24 = 4796;
        goto LABEL_59;
      }
      v25 = (char *)a3 + 320;
      if ( *((_BYTE *)a3 + 456) )
      {
        Container::Manager::Core::Details::SiloSettings::operator=(v25, v32);
      }
      else
      {
        Container::Manager::Core::Details::SiloSettings::SiloSettings(v25, v32);
        *(_BYTE *)(v26 + 136) = 1;
      }
      if ( v35 )
        Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)v33);
      if ( v32[32] )
        utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(&v32[8]);
    }
    return 0;
  }
  v29[0] = 0;
  v28[0] = v29;
  v28[1] = v29;
  ResourcePath = Container::Manager::Core::Details::Layer::GetResourcePath(a2, 0, v28);
  KryptonSiloSettings = ResourcePath;
  if ( ResourcePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)ResourcePath,
      v27);
    goto LABEL_15;
  }
  memset(v32, 0, sizeof(v32));
  memset_0(v33, 0, 0xC0u);
  v33[0] = 0;
  v38 = 0;
  memset(v39, 0, sizeof(v39));
  LOBYTE(v39[0]) = 0;
  v40 = 0;
  BYTE8(v40) = 0;
  v44 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  KryptonSiloSettings = Container::Manager::Hcs::MappedFolderConfiguration::Initialize(v32, 1, v28, v42);
  if ( (_BYTE)v44 && v42[0] != &v43 )
    operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( KryptonSiloSettings < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1281,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)KryptonSiloSettings,
      v27);
LABEL_24:
    Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v32);
LABEL_15:
    if ( v28[0] != v29 )
      operator delete(v28[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)KryptonSiloSettings;
  }
  if ( v38 )
  {
    v17 = v34 | 0x10;
  }
  else
  {
    LOBYTE(v40) = 1;
    __int2c();
    v17 = v34;
  }
  v34 = v17 | 0x20;
  v30[0] = v31;
  v30[1] = v31;
  v31[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v30,
                           v36,
                           (v37 - v36) >> 1) )
  {
    KryptonSiloSettings = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v27);
    if ( v30[0] != v31 )
      operator delete(v30[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_24;
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  v18 = GetCurrentThreadId();
  SRWLock = (PSRWLOCK)((char *)this + 456);
  *((_DWORD *)this + 116) = v18;
  Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
    this,
    &SRWLock);
  v19 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v19);
  }
  v20 = Container::Manager::Hcs::ComputeSystem::MapSharedFolder(
          *((Container::Manager::Hcs::ComputeSystem **)this + 157),
          (const struct Container::Manager::Hcs::MappedFolderConfiguration *)v32);
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  *((_DWORD *)this + 116) = GetCurrentThreadId();
  Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(this);
  if ( v20 >= 0 )
  {
    if ( this != (Container::Manager::Core::Details::ContainerObject *)-456LL )
    {
      *((_DWORD *)this + 116) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
    }
    v21 = (char *)a3 + 32;
    if ( *((_BYTE *)a3 + 312) )
    {
      utl::optional<Csl::Path>::operator=(v21, v32);
      v22 = *((_BYTE *)a3 + 256);
      if ( v38 )
      {
        v23 = (char *)a3 + 72;
        if ( v22 )
        {
          Container::Manager::Hcs::VsmbShareConfiguration::operator=(v23, v33);
        }
        else
        {
          Container::Manager::Hcs::VsmbShareConfiguration::VsmbShareConfiguration(v23, v33);
          *((_BYTE *)a3 + 256) = 1;
        }
      }
      else if ( v22 )
      {
        Container::Manager::Hcs::VsmbShareConfiguration::~VsmbShareConfiguration((struct Container::Manager::Core::Details::ContainerObject::MappedLayer *)((char *)a3 + 72));
        *((_BYTE *)a3 + 256) = 0;
      }
      utl::optional<Container::Manager::Hcs::MappedFolderConfiguration::ArgonMappedFolderConfiguration>::operator=(
        (char *)a3 + 264,
        v39);
    }
    else
    {
      Container::Manager::Hcs::MappedFolderConfiguration::MappedFolderConfiguration(v21, v32);
      *((_BYTE *)a3 + 312) = 1;
    }
    if ( v30[0] != v31 )
      operator delete(v30[0], (const struct std::nothrow_t *)&std::nothrow);
    Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v32);
    if ( v28[0] != v29 )
      operator delete(v28[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_56;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12A6,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
    (const char *)(unsigned int)v20,
    v27);
  if ( this != (Container::Manager::Core::Details::ContainerObject *)-456LL )
  {
    *((_DWORD *)this + 116) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
  }
  if ( v30[0] != v31 )
    operator delete(v30[0], (const struct std::nothrow_t *)&std::nothrow);
  Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v32);
  if ( v28[0] != v29 )
    operator delete(v28[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1800a3cd8  push    rbp
0x1800a3cda  push    rbx
0x1800a3cdb  push    rsi
0x1800a3cdc  push    rdi
0x1800a3cdd  push    r12
0x1800a3cdf  push    r13
0x1800a3ce1  push    r14
0x1800a3ce3  push    r15
0x1800a3ce5  lea     rbp, [rsp-0D8h]
0x1800a3ced  sub     rsp, 1D8h
0x1800a3cf4  xor     edi, edi
0x1800a3cf6  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800a3cfd  mov     r12b, r9b
0x1800a3d00  mov     r14, r8
0x1800a3d03  mov     r13, rdx
0x1800a3d06  mov     r15, rcx
0x1800a3d09  cmp     [r8+10h], rdi
0x1800a3d0d  jz      loc_1800A3E67
0x1800a3d13  mov     rdx, rsi; struct std::nothrow_t *
0x1800a3d16  lea     ecx, [rdi+58h]; unsigned __int64
0x1800a3d19  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a3d1e  mov     rsi, rax
0x1800a3d21  test    rax, rax
0x1800a3d24  jz      loc_1800A3EDF
0x1800a3d2a  lea     rdx, [rax+10h]
0x1800a3d2e  mov     [rax+28h], rdi
0x1800a3d32  mov     [rax], rdx
0x1800a3d35  mov     rcx, rsi
0x1800a3d38  mov     [rax+8], rdx
0x1800a3d3c  mov     [rdx], di
0x1800a3d3f  lea     rdx, [rbp+110h+var_80]
0x1800a3d46  mov     [rax+20h], edi
0x1800a3d49  mov     [rax+40h], rdi
0x1800a3d4d  mov     [rax+48h], rdi
0x1800a3d51  mov     [rax+50h], dil
0x1800a3d55  mov     [rax+30h], rdi
0x1800a3d59  mov     [rax+38h], rdi
0x1800a3d5d  mov     [rbp+110h+SRWLock], rax
0x1800a3d64  lea     rax, aContainerobjec; "ContainerObject_MapLayerIfNeeded"
0x1800a3d6b  mov     [rbp+110h+var_80], rax
0x1800a3d72  mov     [rbp+110h+var_78], 20h ; ' '
0x1800a3d7d  call    ?Initialize@ResourceHandle@Core@Manager@Container@@QEAAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Core::ResourceHandle::Initialize(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800a3d82  mov     ebx, eax
0x1800a3d84  test    eax, eax
0x1800a3d86  jns     short loc_1800A3D92
0x1800a3d88  mov     edx, 1261h
0x1800a3d8d  jmp     loc_1800A3E1B
0x1800a3d92  mov     rcx, [r15+598h]
0x1800a3d99  lea     rdx, [r13+38h]
0x1800a3d9d  lea     r9, [rbp+110h+SRWLock]
0x1800a3da4  mov     r8d, 2
0x1800a3daa  call    ?OpenResource@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@W4ResourceType@2345@AEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::Details::ResourceBroker::OpenResource(_GUID const &,Container::Manager::Core::Details::ResourceType,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> &)
0x1800a3daf  mov     ebx, eax
0x1800a3db1  test    eax, eax
0x1800a3db3  jns     short loc_1800A3DBC
0x1800a3db5  mov     edx, 1265h
0x1800a3dba  jmp     short loc_1800A3E1B
0x1800a3dbc  mov     rcx, rsi
0x1800a3dbf  call    ??$Get@VLayer@Details@Core@Manager@Container@@@ResourceHandle@Core@Manager@Container@@QEBAPEAVLayer@Details@123@XZ; Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(void)
0x1800a3dc4  lea     rbx, [r15+1C8h]
0x1800a3dcb  mov     rdi, rax
0x1800a3dce  mov     rcx, rbx; SRWLock
0x1800a3dd1  call    cs:__imp_AcquireSRWLockExclusive
0x1800a3dd8  nop     dword ptr [rax+rax+00h]
0x1800a3ddd  call    cs:__imp_GetCurrentThreadId
0x1800a3de4  nop     dword ptr [rax+rax+00h]
0x1800a3de9  lea     r9, [rbp+110h+SRWLock]
0x1800a3df0  mov     [rbp+110h+SRWLock], rbx
0x1800a3df7  mov     [rbx+8], eax
0x1800a3dfa  mov     rdx, rdi
0x1800a3dfd  mov     r8, [r14+10h]
0x1800a3e01  mov     rcx, r15
0x1800a3e04  mov     byte ptr [rsp+210h+var_1F0], 0; int
0x1800a3e09  call    ?MapLayerIfNeeded@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVLayer@2345@AEAUMappedLayer@12345@V?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@_N@Z; Container::Manager::Core::Details::ContainerObject::MapLayerIfNeeded(Container::Manager::Core::Details::Layer const &,Container::Manager::Core::Details::ContainerObject::MappedLayer &,Csl::SrwLock::ReleaseOnScopeExit<0>,bool)
0x1800a3e0e  xor     edi, edi
0x1800a3e10  mov     ebx, eax
0x1800a3e12  test    eax, eax
0x1800a3e14  jns     short loc_1800A3E4B
0x1800a3e16  mov     edx, 1273h; void *
0x1800a3e1b  mov     rcx, [rbp+118h]; this
0x1800a3e22  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a3e29  mov     r9d, eax; char *
0x1800a3e2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3e31  mov     rcx, rsi; this
0x1800a3e34  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a3e39  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800a3e3e  mov     rcx, rsi; void *
0x1800a3e41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a3e46  jmp     loc_1800A3EFF
0x1800a3e4b  mov     rcx, rsi; this
0x1800a3e4e  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a3e53  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800a3e58  mov     rcx, rsi; void *
0x1800a3e5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a3e60  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800a3e67  cmp     [r14+138h], dil
0x1800a3e6e  jnz     loc_1800A4235
0x1800a3e74  test    r12b, r12b
0x1800a3e77  jz      loc_1800A4235
0x1800a3e7d  lea     rax, [rsp+210h+var_1D0]
0x1800a3e82  mov     [rsp+210h+var_1D0], di
0x1800a3e87  mov     [rsp+210h+var_1E0], rax
0x1800a3e8c  lea     r8, [rsp+210h+var_1E0]
0x1800a3e91  lea     rax, [rsp+210h+var_1D0]
0x1800a3e96  xor     edx, edx
0x1800a3e98  mov     rcx, r13
0x1800a3e9b  mov     [rsp+210h+var_1D8], rax
0x1800a3ea0  call    ?GetResourcePath@Layer@Details@Core@Manager@Container@@QEBAJW4LayerResource@2345@AEAVPath@Csl@@@Z; Container::Manager::Core::Details::Layer::GetResourcePath(Container::Manager::Core::Details::LayerResource,Csl::Path &)
0x1800a3ea5  mov     ebx, eax
0x1800a3ea7  test    eax, eax
0x1800a3ea9  jns     short loc_1800A3F06
0x1800a3eab  mov     rcx, [rbp+118h]; this
0x1800a3eb2  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a3eb9  mov     r9d, eax; char *
0x1800a3ebc  mov     edx, 127Ch; void *
0x1800a3ec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3ec6  mov     rcx, [rsp+210h+var_1E0]; void *
0x1800a3ecb  lea     rax, [rsp+210h+var_1D0]
0x1800a3ed0  cmp     rcx, rax
0x1800a3ed3  jz      short loc_1800A3EFF
0x1800a3ed5  mov     rdx, rsi; struct std::nothrow_t *
0x1800a3ed8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a3edd  jmp     short loc_1800A3EFF
0x1800a3edf  mov     rcx, [rbp+118h]; this
0x1800a3ee6  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a3eed  mov     ebx, 8007000Eh
0x1800a3ef2  mov     edx, 125Fh; void *
0x1800a3ef7  mov     r9d, ebx; char *
0x1800a3efa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3eff  mov     eax, ebx
0x1800a3f01  jmp     loc_1800A433D
0x1800a3f06  xorps   xmm0, xmm0
0x1800a3f09  lea     rcx, [rbp+110h+var_178]; void *
0x1800a3f0d  xor     eax, eax
0x1800a3f0f  xor     edx, edx; Val
0x1800a3f11  mov     r8d, 0C0h; Size
0x1800a3f17  mov     [rbp+110h+var_180], rax
0x1800a3f1b  movups  [rsp+210h+var_1A0], xmm0
0x1800a3f20  movups  [rbp+110h+var_190], xmm0
0x1800a3f24  call    memset_0
0x1800a3f29  xorps   xmm0, xmm0
0x1800a3f2c  mov     [rbp+110h+var_178], dil
0x1800a3f30  xor     eax, eax
0x1800a3f32  mov     [rbp+110h+var_C0], dil
0x1800a3f36  movups  [rbp+110h+var_B8], xmm0
0x1800a3f3a  lea     r9, [rbp+110h+var_70]
0x1800a3f41  mov     byte ptr [rbp+110h+var_B8], dil
0x1800a3f45  movups  [rbp+110h+var_98], xmm0
0x1800a3f49  lea     edx, [rax+1]
0x1800a3f4c  mov     byte ptr [rbp+110h+var_98+8], dil
0x1800a3f53  lea     r8, [rsp+210h+var_1E0]
0x1800a3f58  mov     [rbp+110h+var_50], rax
0x1800a3f5f  lea     rcx, [rsp+210h+var_1A0]
0x1800a3f64  movups  [rbp+110h+var_A8], xmm0
0x1800a3f68  movups  xmmword ptr [rbp+110h+var_70], xmm0
0x1800a3f6f  movups  [rbp+110h+var_60], xmm0
0x1800a3f76  call    ?Initialize@MappedFolderConfiguration@Hcs@Manager@Container@@QEAAJW4ComputeSystemType@234@AEBVPath@Csl@@AEBV?$optional@VPath@Csl@@@utl@@@Z; Container::Manager::Hcs::MappedFolderConfiguration::Initialize(Container::Manager::Hcs::ComputeSystemType,Csl::Path const &,utl::optional<Csl::Path> const &)
0x1800a3f7b  mov     ebx, eax
0x1800a3f7d  cmp     byte ptr [rbp+110h+var_50], dil
0x1800a3f84  jz      short loc_1800A3FA1
0x1800a3f86  mov     rcx, [rbp+110h+var_70]; void *
0x1800a3f8d  lea     rax, [rbp+110h+var_60]
0x1800a3f94  cmp     rcx, rax
0x1800a3f97  jz      short loc_1800A3FA1
0x1800a3f99  mov     rdx, rsi; struct std::nothrow_t *
0x1800a3f9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a3fa1  test    ebx, ebx
0x1800a3fa3  jns     short loc_1800A3FCF
0x1800a3fa5  mov     rcx, [rbp+118h]; this
0x1800a3fac  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a3fb3  mov     r9d, ebx; char *
0x1800a3fb6  mov     edx, 1281h; void *
0x1800a3fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3fc0  lea     rcx, [rsp+210h+var_1A0]; this
0x1800a3fc5  call    ??1MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(void)
0x1800a3fca  jmp     loc_1800A3EC6
0x1800a3fcf  cmp     [rbp+110h+var_C0], dil
0x1800a3fd3  jz      short loc_1800A3FDD
0x1800a3fd5  mov     eax, [rbp+110h+var_154]
0x1800a3fd8  or      eax, 10h
0x1800a3fdb  jmp     short loc_1800A3FE6
0x1800a3fdd  mov     byte ptr [rbp+110h+var_98], 1
0x1800a3fe1  int     2Ch; Windows NT - assertion failure
0x1800a3fe3  mov     eax, [rbp+110h+var_154]
0x1800a3fe6  mov     rdx, [rbp+110h+var_E0]
0x1800a3fea  lea     rcx, [rsp+210h+var_1C0]
0x1800a3fef  mov     r8, [rbp+110h+var_D8]
0x1800a3ff3  or      eax, 20h
0x1800a3ff6  mov     [rbp+110h+var_154], eax
0x1800a3ff9  sub     r8, rdx
0x1800a3ffc  lea     rax, [rsp+210h+var_1B0]
0x1800a4001  sar     r8, 1
0x1800a4004  mov     [rsp+210h+var_1C0], rax
0x1800a4009  lea     rax, [rsp+210h+var_1B0]
0x1800a400e  mov     [rsp+210h+var_1B8], rax
0x1800a4013  mov     [rsp+210h+var_1B0], di
0x1800a4018  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a401d  test    al, al
0x1800a401f  jnz     short loc_1800A4061
0x1800a4021  mov     rcx, [rbp+118h]; this
0x1800a4028  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a402f  mov     ebx, 8007000Eh
0x1800a4034  mov     edx, 128Dh; void *
0x1800a4039  mov     r9d, ebx; char *
0x1800a403c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4041  mov     rcx, [rsp+210h+var_1C0]; void *
0x1800a4046  lea     rax, [rsp+210h+var_1B0]
0x1800a404b  cmp     rcx, rax
0x1800a404e  jz      loc_1800A3FC0
0x1800a4054  mov     rdx, rsi; struct std::nothrow_t *
0x1800a4057  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a405c  jmp     loc_1800A3FC0
0x1800a4061  lea     rbx, [r15+1C8h]
0x1800a4068  mov     rcx, rbx; SRWLock
0x1800a406b  call    cs:__imp_AcquireSRWLockExclusive
0x1800a4072  nop     dword ptr [rax+rax+00h]
0x1800a4077  call    cs:__imp_GetCurrentThreadId
0x1800a407e  nop     dword ptr [rax+rax+00h]
0x1800a4083  lea     rdx, [rbp+110h+SRWLock]
0x1800a408a  mov     [rbp+110h+SRWLock], rbx
0x1800a4091  mov     rcx, r15
0x1800a4094  mov     [rbx+8], eax
0x1800a4097  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800a409c  mov     rcx, [rbp+110h+SRWLock]; SRWLock
0x1800a40a3  test    rcx, rcx
0x1800a40a6  jz      short loc_1800A40B7
0x1800a40a8  mov     [rcx+8], edi
0x1800a40ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a40b2  nop     dword ptr [rax+rax+00h]
0x1800a40b7  mov     rcx, [r15+4E8h]; this
0x1800a40be  lea     rdx, [rsp+210h+var_1A0]; struct Container::Manager::Hcs::MappedFolderConfiguration *
0x1800a40c3  call    ?MapSharedFolder@ComputeSystem@Hcs@Manager@Container@@QEAAJAEBVMappedFolderConfiguration@234@@Z; Container::Manager::Hcs::ComputeSystem::MapSharedFolder(Container::Manager::Hcs::MappedFolderConfiguration const &)
0x1800a40c8  mov     rcx, rbx; SRWLock
0x1800a40cb  mov     edi, eax
0x1800a40cd  call    cs:__imp_AcquireSRWLockExclusive
0x1800a40d4  nop     dword ptr [rax+rax+00h]
0x1800a40d9  call    cs:__imp_GetCurrentThreadId
0x1800a40e0  nop     dword ptr [rax+rax+00h]
0x1800a40e5  mov     rcx, r15; this
0x1800a40e8  mov     [rbx+8], eax
0x1800a40eb  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x1800a40f0  test    edi, edi
0x1800a40f2  jns     short loc_1800A4169
0x1800a40f4  mov     rcx, [rbp+118h]; this
0x1800a40fb  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a4102  mov     r9d, edi; char *
0x1800a4105  mov     edx, 12A6h; void *
0x1800a410a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a410f  test    rbx, rbx
0x1800a4112  jz      short loc_1800A412A
0x1800a4114  mov     rcx, rbx; SRWLock
0x1800a4117  mov     dword ptr [rbx+8], 0
0x1800a411e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a4125  nop     dword ptr [rax+rax+00h]
0x1800a412a  mov     rcx, [rsp+210h+var_1C0]; void *
0x1800a412f  lea     rax, [rsp+210h+var_1B0]
0x1800a4134  cmp     rcx, rax
0x1800a4137  jz      short loc_1800A4141
0x1800a4139  mov     rdx, rsi; struct std::nothrow_t *
0x1800a413c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4141  lea     rcx, [rsp+210h+var_1A0]; this
0x1800a4146  call    ??1MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(void)
0x1800a414b  mov     rcx, [rsp+210h+var_1E0]; void *
0x1800a4150  lea     rax, [rsp+210h+var_1D0]
0x1800a4155  cmp     rcx, rax
0x1800a4158  jz      short loc_1800A4162
0x1800a415a  mov     rdx, rsi; struct std::nothrow_t *
0x1800a415d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4162  mov     eax, edi
0x1800a4164  jmp     loc_1800A433D
0x1800a4169  xor     edi, edi
0x1800a416b  test    rbx, rbx
0x1800a416e  jz      short loc_1800A4182
0x1800a4170  mov     rcx, rbx; SRWLock
0x1800a4173  mov     [rbx+8], edi
0x1800a4176  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a417d  nop     dword ptr [rax+rax+00h]
0x1800a4182  lea     rdx, [rsp+210h+var_1A0]
0x1800a4187  lea     rcx, [r14+20h]
0x1800a418b  cmp     [r14+138h], dil
0x1800a4192  jz      short loc_1800A41F0
0x1800a4194  call    ??4?$optional@VPath@Csl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::optional<Csl::Path>::operator=(utl::optional<Csl::Path> &&)
0x1800a4199  cmp     [rbp+110h+var_C0], 0
0x1800a419d  lea     rdi, [r14+48h]
0x1800a41a1  mov     al, [rdi+0B8h]
0x1800a41a7  jz      short loc_1800A41C9
0x1800a41a9  lea     rdx, [rbp+110h+var_178]
0x1800a41ad  mov     rcx, rdi
0x1800a41b0  test    al, al
0x1800a41b2  jz      short loc_1800A41BB
0x1800a41b4  call    ??4VsmbShareConfiguration@Hcs@Manager@Container@@QEAAAEAU0123@$$QEAU0123@@Z; Container::Manager::Hcs::VsmbShareConfiguration::operator=(Container::Manager::Hcs::VsmbShareConfiguration &&)
0x1800a41b9  jmp     short loc_1800A41DC
0x1800a41bb  call    ??0VsmbShareConfiguration@Hcs@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Hcs::VsmbShareConfiguration::VsmbShareConfiguration(Container::Manager::Hcs::VsmbShareConfiguration &&)
0x1800a41c0  mov     byte ptr [rdi+0B8h], 1
0x1800a41c7  jmp     short loc_1800A41DC
0x1800a41c9  test    al, al
0x1800a41cb  jz      short loc_1800A41DC
0x1800a41cd  mov     rcx, rdi; this
0x1800a41d0  call    ??1VsmbShareConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::VsmbShareConfiguration::~VsmbShareConfiguration(void)
0x1800a41d5  mov     byte ptr [rdi+0B8h], 0
  ... truncated ...
```
