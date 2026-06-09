# RegistrationChangeDetection::InitializeForCombaseIfNecessary(void)

- ea: `0x180062084`
- end: `0x180062558`
- name: `?InitializeForCombaseIfNecessary@RegistrationChangeDetection@@YAJXZ`
- size: `1236`
- prototype: `HRESULT __fastcall()`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180062050`
- `0x180084b0c`

## callees

- `0x18000833c`
- `0x180054990`
- `0x18005b0a0`
- `0x18005b454`
- `0x18005cde8`
- `0x18005ce60`
- `0x180062084`
- `0x180082dd4`
- `0x180084480`
- `0x180086714`
- `0x18008db2c`
- `0x180121540`
- `0x180122110`
- `0x18013a4c4`
- `0x180144ac8`
- `0x180147da8`
- `0x18018b024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062540`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062424`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062424`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062468`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062468`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800621d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800621d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800622d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800622d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800623fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800623fd`

## string_xrefs

- `0x180062204`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180062301`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x1800622f5`: `path:%ls`
- `0x1800621af`: `onecore\com\combase\catalog\cache.cxx`
- `0x18006228f`: `onecore\com\combase\catalog\cache.cxx`
- `0x18006239b`: `onecore\com\combase\catalog\cache.cxx`
- `0x1800621e7`: `OpenCurrentUser: %!HRESULT!`
- `0x180062218`: `OpenCurrentUser: %!HRESULT!`
- `0x18006237c`: `OpenCurrentUser: %!HRESULT!`
- `0x180062190`: `SuspendImpersonate: %!HRESULT!`
- `0x1800621a6`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`
- `0x1800622a1`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`
- `0x180062392`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`

## pseudocode

```c
__int64 __fastcall RegistrationChangeDetection::InitializeForCombaseIfNecessary(ProcessToken *a1)
{
  HRESULT v2; // ebx
  char v3; // r12
  bool v4; // r14
  LSTATUS v5; // eax
  HRESULT v6; // esi
  const wchar_t *format; // r8
  int v8; // edx
  LSTATUS v9; // eax
  HRESULT v10; // esi
  int v11; // edx
  RegistrationChangeDetection::NotificationChecker *v12; // rax
  RegistrationChangeDetection::NotificationChecker *v13; // rax
  RegistrationChangeDetection::NotificationChecker *v14; // rsi
  signed int LastError; // eax
  RegistrationChangeDetection::NotificationChecker *ptr; // rbx
  signed __int8 v17; // cl
  unsigned __int8 Value; // tt
  HRESULT v19; // eax
  unsigned int v20; // edx
  signed __int32 v21[8]; // [rsp+0h] [rbp-40h] BYREF
  __int64 v22; // [rsp+28h] [rbp-18h]
  Microsoft::WRL::Wrappers::Event event; // [rsp+30h] [rbp-10h] BYREF
  void *retaddr; // [rsp+78h] [rbp+38h]
  RegistryKey userRoot; // [rsp+80h] [rbp+40h] BYREF
  void *hThreadToken; // [rsp+88h] [rbp+48h] BYREF
  RegistryKey userSoftwareClasses; // [rsp+90h] [rbp+50h] BYREF

  switch ( RegistrationChangeDetection::g_initializationStatus._Storage._Value )
  {
    case 0xAu:
      return 2147500065LL;
    case 0xBu:
      return 0;
    case 0xCu:
      ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(
        RegistrationChangeDetection::g_notificationChecker.ptr_,
        (ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil> >::LockWrapper *)&event);
      v2 = RegistrationChangeDetection::NotificationChecker::RegisterNotification(
             RegistrationChangeDetection::g_notificationChecker.ptr_,
             (const ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil> >::LockWrapper *)&event);
      if ( v2 >= 0 )
        RegistrationChangeDetection::g_initializationStatus._Storage._Value = 11;
      if ( event.handle_ )
        _InterlockedExchange((volatile __int32 *)&event.__vftable[1], 0);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&event.handle_);
      return (unsigned int)v2;
  }
  v2 = 0;
  v3 = 0;
  v4 = (g_GLBOPT_RoFlags & 0x100) == 0 && ProcessToken::IsUserHiveOk(a1);
  userSoftwareClasses._hkey = 0;
  hThreadToken = 0;
  if ( !v4 )
    goto LABEL_75;
  v2 = SuspendImpersonate(&hThreadToken);
  if ( v2 >= 0 )
  {
    if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
      goto LABEL_23;
  }
  else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
  {
    goto LABEL_75;
  }
  LODWORD(v22) = v2;
  ComTraceHr(
    v2,
    "onecore\\com\\combase\\catalog\\cache.cxx",
    "RegistrationChangeDetection::InitializeForCombaseIfNecessary",
    840,
    L"SuspendImpersonate: %!HRESULT!",
    v22);
  if ( v2 < 0 )
    goto LABEL_75;
LABEL_23:
  userRoot._hkey = 0;
  v5 = RegOpenCurrentUser(0x20019u, (PHKEY)&userRoot._hkey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  format = L"OpenCurrentUser: %!HRESULT!";
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024894 )
  {
    wil::details::in1diag3::_Log_Hr(retaddr, 0x178u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v6);
    format = L"OpenCurrentUser: %!HRESULT!";
    v2 = v6;
LABEL_33:
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
    {
LABEL_55:
      if ( v2 != -2147024894 )
        goto LABEL_56;
LABEL_58:
      v4 = 0;
      v2 = 0;
      goto LABEL_59;
    }
    goto LABEL_39;
  }
  v8 = gfEnableTracing;
  v2 = v6;
  if ( v6 != -2147024894 )
    goto LABEL_31;
  if ( !gfEnableTracing )
    goto LABEL_58;
  if ( !IsWppLevelEnabled(VERBOSE) )
  {
LABEL_31:
    if ( v6 >= 0 )
    {
      if ( !v8 || !IsWppLevelEnabled(VERBOSE) )
        goto LABEL_40;
      goto LABEL_39;
    }
    if ( v6 == -2147024894 )
      goto LABEL_55;
    goto LABEL_33;
  }
LABEL_39:
  LODWORD(v22) = v6;
  ComTraceHr(
    v6,
    "onecore\\com\\combase\\catalog\\cache.cxx",
    "RegistrationChangeDetection::InitializeForCombaseIfNecessary",
    846,
    format,
    v22);
  if ( v6 < 0 )
    goto LABEL_55;
LABEL_40:
  v9 = RegOpenKeyExW(userRoot._hkey, L"Software\\Classes", 0, 0x10u, (PHKEY)&userSoftwareClasses._hkey);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 == -2147024894 )
  {
    if ( !gfEnableTracing )
      goto LABEL_58;
    v2 = -2147024894;
    if ( IsWppLevelEnabled(VERBOSE) )
      goto LABEL_54;
  }
  else
  {
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      0x10Eu,
      "onecore\\com\\combase\\inc\\RegistryKey.hpp",
      v10,
      "path:%ls",
      L"Software\\Classes");
    v11 = gfEnableTracing;
    v2 = v10;
  }
  if ( v10 >= 0 )
  {
    if ( !v11 || !IsWppLevelEnabled(VERBOSE) )
      goto LABEL_59;
LABEL_54:
    LODWORD(v22) = v10;
    ComTraceHr(
      v10,
      "onecore\\com\\combase\\catalog\\cache.cxx",
      "RegistrationChangeDetection::InitializeForCombaseIfNecessary",
      851,
      L"OpenCurrentUser: %!HRESULT!",
      v22);
    goto LABEL_55;
  }
  if ( v10 == -2147024894 )
    goto LABEL_55;
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    goto LABEL_54;
LABEL_56:
  if ( v2 == -2147024891 )
    v3 = 1;
LABEL_59:
  RegistryKey::Close(&userRoot);
  if ( v4 && v2 >= 0 )
  {
    if ( RegistrationChangeDetection::g_notificationChecker.ptr_ )
    {
      _InterlockedOr(v21, 0);
    }
    else
    {
      event.handle_ = CreateEventW(0, 0, 0, 0);
      event.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( event.handle_ )
      {
        v12 = (RegistrationChangeDetection::NotificationChecker *)HeapAlloc(g_hHeap, 0, 0x40u);
        if ( v12
          && (RegistrationChangeDetection::NotificationChecker::NotificationChecker(v12, &userSoftwareClasses, &event),
              (v14 = v13) != 0) )
        {
          if ( _InterlockedCompareExchange64(
                 (volatile signed __int64 *)&RegistrationChangeDetection::g_notificationChecker,
                 (signed __int64)v13,
                 0) )
          {
            RegistrationChangeDetection::NotificationChecker::~NotificationChecker(v13);
            HeapFree(g_hHeap, 0, v14);
          }
        }
        else
        {
          v2 = -2147024882;
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
      event.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( event.handle_
        && !Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *)&event) )
      {
        v19 = GetLastError();
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        Microsoft::WRL::Details::RaiseException(v19, v20);
        JUMPOUT(0x180062557LL);
      }
      _InterlockedOr(v21, 0);
      if ( v2 < 0 )
        goto LABEL_75;
    }
    ptr = RegistrationChangeDetection::g_notificationChecker.ptr_;
    ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(
      RegistrationChangeDetection::g_notificationChecker.ptr_,
      (ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil> >::LockWrapper *)&event);
    v2 = RegistrationChangeDetection::NotificationChecker::RegisterNotification(
           ptr,
           (const ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil> >::LockWrapper *)&event);
    ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper((ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil> >::LockWrapper *)&event);
  }
LABEL_75:
  ResumeImpersonate(hThreadToken);
  hThreadToken = 0;
  while ( v2 >= 0 )
  {
    v17 = 11;
LABEL_83:
    Value = RegistrationChangeDetection::g_initializationStatus._Storage._Value;
    if ( Value == _InterlockedCompareExchange8(
                    (volatile signed __int8 *)&RegistrationChangeDetection::g_initializationStatus,
                    v17,
                    RegistrationChangeDetection::g_initializationStatus._Storage._Value) )
      goto LABEL_86;
  }
  if ( RegistrationChangeDetection::g_initializationStatus._Storage._Value == 10 )
    goto LABEL_86;
  if ( RegistrationChangeDetection::g_initializationStatus._Storage._Value < 0xBu )
  {
    if ( v3 )
      v17 = 10;
    else
      v17 = RegistrationChangeDetection::g_initializationStatus._Storage._Value + 1;
    goto LABEL_83;
  }
  v2 = 0;
LABEL_86:
  RegistryKey::Close(&userSoftwareClasses);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180062084  mov     [rsp-38h+arg_18], rbx
0x180062089  push    rbp
0x18006208a  push    rsi
0x18006208b  push    rdi
0x18006208c  push    r12
0x18006208e  push    r13
0x180062090  push    r14
0x180062092  push    r15
0x180062094  mov     rbp, rsp
0x180062097  sub     rsp, 40h
0x18006209b  mov     al, cs:RegistrationChangeDetection__g_initializationStatus._Storage._Value
0x1800620a1  nop
0x1800620a2  cmp     al, 0Ah
0x1800620a4  jnz     short loc_1800620B0
0x1800620a6  mov     eax, 80004021h
0x1800620ab  jmp     loc_180062528
0x1800620b0  mov     r15d, 0Bh
0x1800620b6  cmp     al, r15b
0x1800620b9  jnz     short loc_1800620C2
0x1800620bb  xor     eax, eax
0x1800620bd  jmp     loc_180062528
0x1800620c2  cmp     al, 0Ch
0x1800620c4  jnz     short loc_180062110
0x1800620c6  mov     rcx, cs:RegistrationChangeDetection__g_notificationChecker.ptr_; this
0x1800620cd  lea     rdx, [rbp+event]; result
0x1800620d1  call    ?Lock@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA?AVLockWrapper@123@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(void)
0x1800620d6  mov     rcx, cs:RegistrationChangeDetection__g_notificationChecker.ptr_; this
0x1800620dd  lea     rdx, [rbp+event]; evidenceOfLock
0x1800620e1  call    ?RegisterNotification@NotificationChecker@RegistrationChangeDetection@@QEAAJAEBVLockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@@Z; RegistrationChangeDetection::NotificationChecker::RegisterNotification(ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper const &)
0x1800620e6  xor     edi, edi
0x1800620e8  mov     ebx, eax
0x1800620ea  test    eax, eax
0x1800620ec  js      short loc_1800620F5
0x1800620ee  xchg    r15b, cs:RegistrationChangeDetection__g_initializationStatus._Storage._Value
0x1800620f5  cmp     [rbp+event.handle_], rdi
0x1800620f9  jz      short loc_180062102
0x1800620fb  mov     rcx, [rbp+event.__vftable]
0x1800620ff  xchg    edi, [rcx+8]
0x180062102  lea     rcx, [rbp+event.handle_]; this
0x180062106  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006210b  jmp     loc_180062526
0x180062110  xor     edi, edi
0x180062112  test    cs:?g_GLBOPT_RoFlags@@3KA, 100h; ulong g_GLBOPT_RoFlags
0x18006211c  mov     ebx, edi
0x18006211e  mov     r12b, dil
0x180062121  jz      short loc_180062128
0x180062123  mov     r14b, dil
0x180062126  jmp     short loc_180062130
0x180062128  call    ?IsUserHiveOk@ProcessToken@@QEAA_NXZ; ProcessToken::IsUserHiveOk(void)
0x18006212d  mov     r14b, al
0x180062130  mov     [rbp+userSoftwareClasses._hkey], rdi
0x180062134  mov     [rbp+hThreadToken], rdi
0x180062138  test    r14b, r14b
0x18006213b  jz      loc_1800624DD
0x180062141  lea     rcx, [rbp+hThreadToken]; pHandle
0x180062145  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x18006214a  mov     ebx, eax
0x18006214c  mov     r13d, 80070000h
0x180062152  test    eax, eax
0x180062154  jns     short loc_18006217A
0x180062156  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x18006215c  test    ecx, ecx
0x18006215e  jnz     short loc_180062190
0x180062160  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180062166  jz      loc_1800624DD
0x18006216c  call    IsWppLevelEnabled
0x180062171  test    al, al
0x180062173  jnz     short loc_180062190
0x180062175  jmp     loc_1800624DD
0x18006217a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180062180  jz      short loc_1800621C3
0x180062182  mov     ecx, 3; level
0x180062187  call    IsWppLevelEnabled
0x18006218c  test    al, al
0x18006218e  jz      short loc_1800621C3
0x180062190  lea     rax, aSuspendimperso; "SuspendImpersonate: %!HRESULT!"
0x180062197  mov     dword ptr [rsp+40h+var_18], ebx
0x18006219b  mov     r9d, 348h; line
0x1800621a1  mov     [rsp+40h+format], rax; format
0x1800621a6  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x1800621ad  mov     ecx, ebx; hr
0x1800621af  lea     rdx, aOnecoreComComb_116; "onecore\\com\\combase\\catalog\\cache.c"...
0x1800621b6  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800621bb  test    ebx, ebx
0x1800621bd  js      loc_1800624DD
0x1800621c3  lea     rdx, [rbp+userRoot]; phkResult
0x1800621c7  mov     [rbp+userRoot._hkey], rdi
0x1800621cb  mov     ecx, 20019h; samDesired
0x1800621d0  call    cs:__imp_RegOpenCurrentUser
0x1800621d6  mov     esi, eax
0x1800621d8  test    eax, eax
0x1800621da  jle     short loc_1800621E2
0x1800621dc  movzx   esi, ax
0x1800621df  or      esi, r13d
0x1800621e2  mov     ecx, 80000000h
0x1800621e7  lea     r8, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x1800621ee  mov     r13d, 80070002h
0x1800621f4  lea     eax, [rsi+rcx]
0x1800621f7  test    ecx, eax
0x1800621f9  jnz     short loc_180062223
0x1800621fb  cmp     esi, r13d
0x1800621fe  jz      short loc_180062223
0x180062200  mov     rcx, [rbp+38h]; callerReturnAddress
0x180062204  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18006220b  mov     r9d, esi; hr
0x18006220e  mov     edx, 178h; lineNumber
0x180062213  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062218  lea     r8, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x18006221f  mov     ebx, esi
0x180062221  jmp     short loc_180062253
0x180062223  mov     edx, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x180062229  mov     ebx, esi
0x18006222b  cmp     esi, r13d
0x18006222e  jnz     short loc_180062246
0x180062230  test    edx, edx
0x180062232  jz      loc_1800623B9
0x180062238  mov     ecx, 3; level
0x18006223d  call    IsWppLevelEnabled
0x180062242  test    al, al
0x180062244  jnz     short loc_18006228B
0x180062246  test    esi, esi
0x180062248  jns     short loc_180062279
0x18006224a  cmp     esi, r13d
0x18006224d  jz      loc_1800623A7
0x180062253  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180062259  test    eax, eax
0x18006225b  jnz     short loc_18006228B
0x18006225d  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180062263  jz      loc_1800623A7
0x180062269  xor     ecx, ecx; level
0x18006226b  call    IsWppLevelEnabled
0x180062270  test    al, al
0x180062272  jnz     short loc_18006228B
0x180062274  jmp     loc_1800623A7
0x180062279  test    edx, edx
0x18006227b  jz      short loc_1800622B7
0x18006227d  mov     ecx, 3; level
0x180062282  call    IsWppLevelEnabled
0x180062287  test    al, al
0x180062289  jz      short loc_1800622B7
0x18006228b  mov     dword ptr [rsp+40h+var_18], esi
0x18006228f  lea     rdx, aOnecoreComComb_116; "onecore\\com\\combase\\catalog\\cache.c"...
0x180062296  mov     [rsp+40h+format], r8; format
0x18006229b  mov     r9d, 34Eh; line
0x1800622a1  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x1800622a8  mov     ecx, esi; hr
0x1800622aa  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800622af  test    esi, esi
0x1800622b1  js      loc_1800623A7
0x1800622b7  mov     rcx, [rbp+userRoot._hkey]; hKey
0x1800622bb  lea     rax, [rbp+userSoftwareClasses]
0x1800622bf  lea     rbx, aSoftwareClasse_1; "Software\\Classes"
0x1800622c6  mov     [rsp+40h+format], rax; phkResult
0x1800622cb  mov     rdx, rbx; lpSubKey
0x1800622ce  mov     r9d, 10h; samDesired
0x1800622d4  xor     r8d, r8d; ulOptions
0x1800622d7  call    cs:__imp_RegOpenKeyExW
0x1800622dd  mov     esi, eax
0x1800622df  test    eax, eax
0x1800622e1  jle     short loc_1800622EC
0x1800622e3  movzx   esi, ax
0x1800622e6  or      esi, 80070000h
0x1800622ec  cmp     esi, r13d
0x1800622ef  jz      short loc_180062324
0x1800622f1  mov     rcx, [rbp+38h]; callerReturnAddress
0x1800622f5  lea     rax, aPathLs; "path:%ls"
0x1800622fc  mov     [rsp+40h+var_18], rbx
0x180062301  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x180062308  mov     r9d, esi; hr
0x18006230b  mov     [rsp+40h+format], rax; formatString
0x180062310  mov     edx, 10Eh; lineNumber
0x180062315  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006231a  mov     edx, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x180062320  mov     ebx, esi
0x180062322  jmp     short loc_180062342
0x180062324  mov     edx, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18006232a  test    edx, edx
0x18006232c  jz      loc_1800623B9
0x180062332  mov     ecx, 3; level
0x180062337  mov     ebx, esi
0x180062339  call    IsWppLevelEnabled
0x18006233e  test    al, al
0x180062340  jnz     short loc_18006237C
0x180062342  test    esi, esi
0x180062344  jns     short loc_18006236A
0x180062346  cmp     esi, r13d
0x180062349  jz      short loc_1800623A7
0x18006234b  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180062351  test    eax, eax
0x180062353  jnz     short loc_18006237C
0x180062355  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18006235b  jz      short loc_1800623AC
0x18006235d  xor     ecx, ecx; level
0x18006235f  call    IsWppLevelEnabled
0x180062364  test    al, al
0x180062366  jnz     short loc_18006237C
0x180062368  jmp     short loc_1800623AC
0x18006236a  test    edx, edx
0x18006236c  jz      short loc_1800623BE
0x18006236e  mov     ecx, 3; level
0x180062373  call    IsWppLevelEnabled
0x180062378  test    al, al
0x18006237a  jz      short loc_1800623BE
0x18006237c  lea     rax, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x180062383  mov     dword ptr [rsp+40h+var_18], esi
0x180062387  mov     r9d, 353h; line
0x18006238d  mov     [rsp+40h+format], rax; format
0x180062392  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x180062399  mov     ecx, esi; hr
0x18006239b  lea     rdx, aOnecoreComComb_116; "onecore\\com\\combase\\catalog\\cache.c"...
0x1800623a2  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800623a7  cmp     ebx, r13d
0x1800623aa  jz      short loc_1800623B9
0x1800623ac  cmp     ebx, 80070005h
0x1800623b2  jnz     short loc_1800623BE
0x1800623b4  mov     r12b, 1
0x1800623b7  jmp     short loc_1800623BE
0x1800623b9  mov     r14b, dil
0x1800623bc  mov     ebx, edi
0x1800623be  lea     rcx, [rbp+userRoot]; this
0x1800623c2  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x1800623c7  test    r14b, r14b
0x1800623ca  jz      loc_1800624DD
0x1800623d0  mov     r13d, 80070000h
0x1800623d6  test    ebx, ebx
0x1800623d8  js      loc_1800624DD
0x1800623de  mov     rax, cs:RegistrationChangeDetection__g_notificationChecker.ptr_
0x1800623e5  test    rax, rax
0x1800623e8  jz      short loc_1800623F3
0x1800623ea  lock or [rsp+40h+var_40], edi
0x1800623ee  jmp     loc_1800624B3
0x1800623f3  xor     r9d, r9d; lpName
0x1800623f6  xor     r8d, r8d; bInitialState
0x1800623f9  xor     edx, edx; bManualReset
0x1800623fb  xor     ecx, ecx; lpEventAttributes
0x1800623fd  call    cs:__imp_CreateEventW
0x180062403  mov     [rbp+event.handle_], rax
0x180062407  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18006240e  mov     [rbp+event.__vftable], rcx
0x180062412  test    rax, rax
0x180062415  jz      short loc_180062477
0x180062417  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006241e  xor     edx, edx; dwFlags
0x180062420  lea     r8d, [rdx+40h]; dwBytes
0x180062424  call    cs:__imp_HeapAlloc
0x18006242a  test    rax, rax
0x18006242d  jz      short loc_180062470
0x18006242f  lea     r8, [rbp+event]; event
0x180062433  mov     rcx, rax; this
0x180062436  lea     rdx, [rbp+userSoftwareClasses]; key
0x18006243a  call    ??0NotificationChecker@RegistrationChangeDetection@@QEAA@$$QEAVRegistryKey@@$$QEAVEvent@Wrappers@WRL@Microsoft@@@Z; RegistrationChangeDetection::NotificationChecker::NotificationChecker(RegistryKey &&,Microsoft::WRL::Wrappers::Event &&)
0x18006243f  mov     rsi, rax
0x180062442  test    rax, rax
0x180062445  jz      short loc_180062470
0x180062447  xor     eax, eax
0x180062449  lock cmpxchg cs:RegistrationChangeDetection__g_notificationChecker.ptr_, rsi
0x180062452  jz      short loc_180062489
0x180062454  mov     rcx, rsi; this
0x180062457  call    ??1NotificationChecker@RegistrationChangeDetection@@QEAA@XZ; RegistrationChangeDetection::NotificationChecker::~NotificationChecker(void)
0x18006245c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180062463  mov     r8, rsi; lpMem
0x180062466  xor     edx, edx; dwFlags
0x180062468  call    cs:__imp_HeapFree
0x18006246e  jmp     short loc_180062489
0x180062470  mov     ebx, 8007000Eh
0x180062475  jmp     short loc_180062489
0x180062477  call    cs:__imp_GetLastError
0x18006247d  mov     ebx, eax
0x18006247f  test    eax, eax
0x180062481  jle     short loc_180062489
0x180062483  movzx   ebx, ax
0x180062486  or      ebx, r13d
0x180062489  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180062490  mov     [rbp+event.__vftable], rax
0x180062494  cmp     [rbp+event.handle_], rdi
0x180062498  jz      short loc_1800624AB
0x18006249a  lea     rcx, [rbp+event]; this
0x18006249e  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800624a3  test    al, al
0x1800624a5  jz      loc_180062540
0x1800624ab  lock or [rsp+40h+var_40], edi
0x1800624af  test    ebx, ebx
0x1800624b1  js      short loc_1800624DD
0x1800624b3  mov     rbx, cs:RegistrationChangeDetection__g_notificationChecker.ptr_
0x1800624ba  lea     rdx, [rbp+event]; result
0x1800624be  mov     rcx, rbx; this
0x1800624c1  call    ?Lock@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA?AVLockWrapper@123@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(void)
0x1800624c6  lea     rdx, [rbp+event]; evidenceOfLock
0x1800624ca  mov     rcx, rbx; this
0x1800624cd  call    ?RegisterNotification@NotificationChecker@RegistrationChangeDetection@@QEAAJAEBVLockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@@Z; RegistrationChangeDetection::NotificationChecker::RegisterNotification(ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper const &)
0x1800624d2  lea     rcx, [rbp+event]; this
0x1800624d6  mov     ebx, eax
0x1800624d8  call    ??1LockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper(void)
0x1800624dd  mov     rcx, [rbp+hThreadToken]; hToken
0x1800624e1  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800624e6  mov     [rbp+hThreadToken], rdi
0x1800624ea  mov     al, cs:RegistrationChangeDetection__g_initializationStatus._Storage._Value
0x1800624f0  nop
0x1800624f1  test    ebx, ebx
0x1800624f3  js      short loc_1800624FA
  ... truncated ...
```
