# OobeZdpElevatedManagerCore::RunZDP(void)

- ea: `0x180010160`
- end: `0x180010323`
- name: `?RunZDP@OobeZdpElevatedManagerCore@@AEAAJXZ`
- size: `451`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180010a10`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000b098`
- `0x18000bfc8`
- `0x18000c0d4`
- `0x18000c1e0`
- `0x18000d1a4`
- `0x18000d684`
- `0x18000d6a4`
- `0x18000e2fc`
- `0x18000e4e4`
- `0x18000ebd0`
- `0x18000f044`
- `0x180010160`
- `0x180010640`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800102a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800102a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010197`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010197`

## string_xrefs

- `0x1800101aa`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x1800101df`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x1800102d1`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OobeZdpElevatedManagerCore::RunZDP(RTL_SRWLOCK *this)
{
  HRESULT Instance; // eax
  __int64 v3; // rsi
  int v4; // eax
  OobeZdpElevatedManagerCore *v5; // rcx
  struct IUpdateCollection *v6; // rbx
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-30h]
  RTL_SRWLOCK *v10; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v11[24]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  struct IUpdateSession *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IUpdateCollection *v14; // [rsp+80h] [rbp+30h] BYREF
  struct IUpdateCollection *v15; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  Instance = CoCreateInstance(&CLSID_UpdateSession, 0, 1u, &GUID_816858a4_260d_4260_933a_2585f1abc76b, (LPVOID *)&v13);
  LODWORD(v3) = Instance;
  if ( Instance >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(struct IUpdateSession *, PVOID))v13->lpVtbl->put_ClientApplicationID)(
           v13,
           this[7].Ptr);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v4,
        ppv);
    AutoExecutionPowerHold::AutoExecutionPowerHold((AutoExecutionPowerHold *)v11);
    v15 = 0;
    v3 = (unsigned int)OobeZdpElevatedManagerCore::Search((OobeZdpElevatedManagerCore *)this, v13, &v15);
    OOBE::Health::details::OOBEHealthTracker::HandleEvent<4,long>(v3);
    if ( (int)v3 >= 0 )
      OobeZdpElevatedManagerCore::CancelIfNoUpdates((OobeZdpElevatedManagerCore *)this, v15);
    v14 = 0;
    if ( (int)v3 >= 0 && !LOBYTE(this[6].Ptr) )
    {
      v14 = 0;
      LODWORD(v3) = OobeZdpElevatedManagerCore::FilterUpdates(v5, v15, &v14);
      if ( (int)v3 >= 0 )
      {
        v6 = v14;
        OobeZdpElevatedManagerCore::CancelIfNoUpdates((OobeZdpElevatedManagerCore *)this, v14);
        if ( !LOBYTE(this[6].Ptr) )
        {
          v3 = (unsigned int)OobeZdpElevatedManagerCore::Download((OobeZdpElevatedManagerCore *)this, v13, v6);
          OOBE::Health::details::OOBEHealthTracker::HandleEvent<5,long>(v3);
          if ( (int)v3 >= 0 && !LOBYTE(this[6].Ptr) )
          {
            v3 = (unsigned int)OobeZdpElevatedManagerCore::Install((OobeZdpElevatedManagerCore *)this, v13, v6);
            OOBE::Health::details::OOBEHealthTracker::HandleEvent<6,long>(v3);
          }
        }
      }
    }
    AcquireSRWLockShared(this + 4);
    v10 = this + 4;
    v7 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[5].Ptr + 48LL))(this[5].Ptr, 4);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v14);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v15);
    AutoExecutionPowerHold::~AutoExecutionPowerHold((AutoExecutionPowerHold *)v11);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  }
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180010160  mov     [rsp-18h+arg_0], rbx
0x180010165  push    rbp
0x180010166  push    rsi
0x180010167  push    rdi
0x180010168  mov     rbp, rsp
0x18001016b  sub     rsp, 50h
0x18001016f  mov     rdi, rcx
0x180010172  mov     [rbp+arg_8], 0
0x18001017a  lea     rax, [rbp+arg_8]
0x18001017e  mov     qword ptr [rsp+50h+ppv], rax; int
0x180010183  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x18001018a  xor     edx, edx; pUnkOuter
0x18001018c  lea     r8d, [rdx+1]; dwClsContext
0x180010190  lea     rcx, CLSID_UpdateSession; rclsid
0x180010197  call    cs:__imp_CoCreateInstance
0x18001019d  mov     esi, eax
0x18001019f  test    eax, eax
0x1800101a1  jns     short loc_1800101C0
0x1800101a3  mov     rcx, [rbp+18h]; this
0x1800101a7  mov     r9d, eax; char *
0x1800101aa  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800101b1  mov     edx, 56h ; 'V'; void *
0x1800101b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800101bb  jmp     loc_18001030B
0x1800101c0  mov     rcx, [rbp+arg_8]
0x1800101c4  mov     rax, [rcx]
0x1800101c7  mov     rdx, [rdi+38h]
0x1800101cb  mov     rax, [rax+40h]
0x1800101cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101d4  mov     rcx, [rbp+18h]; this
0x1800101d8  test    eax, eax
0x1800101da  jns     short loc_1800101F0
0x1800101dc  mov     r9d, eax; char *
0x1800101df  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800101e6  mov     edx, 58h ; 'X'; void *
0x1800101eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800101f0  lea     rcx, [rbp+var_18]; this
0x1800101f4  call    ??0AutoExecutionPowerHold@@QEAA@XZ; AutoExecutionPowerHold::AutoExecutionPowerHold(void)
0x1800101f9  nop
0x1800101fa  mov     [rbp+arg_18], 0
0x180010202  lea     r8, [rbp+arg_18]; struct IUpdateCollection **
0x180010206  mov     rdx, [rbp+arg_8]; struct IUpdateSession *
0x18001020a  mov     rcx, rdi; this
0x18001020d  call    ?Search@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSession@@PEAPEAUIUpdateCollection@@@Z; OobeZdpElevatedManagerCore::Search(IUpdateSession *,IUpdateCollection * *)
0x180010212  mov     esi, eax
0x180010214  mov     ecx, eax
0x180010216  call    ??$HandleEvent@$03J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<4,long>(long)
0x18001021b  test    esi, esi
0x18001021d  js      short loc_18001022B
0x18001021f  mov     rdx, [rbp+arg_18]; struct IUpdateCollection *
0x180010223  mov     rcx, rdi; this
0x180010226  call    ?CancelIfNoUpdates@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateCollection@@@Z; OobeZdpElevatedManagerCore::CancelIfNoUpdates(IUpdateCollection *)
0x18001022b  xor     ebx, ebx
0x18001022d  mov     [rbp+arg_10], rbx
0x180010231  test    esi, esi
0x180010233  js      short loc_1800102A0
0x180010235  cmp     [rdi+30h], bl
0x180010238  jnz     short loc_1800102A0
0x18001023a  mov     [rbp+arg_10], rbx
0x18001023e  lea     r8, [rbp+arg_10]; struct IUpdateCollection **
0x180010242  mov     rdx, [rbp+arg_18]; struct IUpdateCollection *
0x180010246  call    ?FilterUpdates@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateCollection@@PEAPEAU2@@Z; OobeZdpElevatedManagerCore::FilterUpdates(IUpdateCollection *,IUpdateCollection * *)
0x18001024b  mov     esi, eax
0x18001024d  test    eax, eax
0x18001024f  js      short loc_1800102A0
0x180010251  mov     rbx, [rbp+arg_10]
0x180010255  mov     rdx, rbx; struct IUpdateCollection *
0x180010258  mov     rcx, rdi; this
0x18001025b  call    ?CancelIfNoUpdates@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateCollection@@@Z; OobeZdpElevatedManagerCore::CancelIfNoUpdates(IUpdateCollection *)
0x180010260  cmp     byte ptr [rdi+30h], 0
0x180010264  jnz     short loc_1800102A0
0x180010266  mov     r8, rbx; struct IUpdateCollection *
0x180010269  mov     rdx, [rbp+arg_8]; struct IUpdateSession *
0x18001026d  mov     rcx, rdi; this
0x180010270  call    ?Download@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z; OobeZdpElevatedManagerCore::Download(IUpdateSession *,IUpdateCollection *)
0x180010275  mov     esi, eax
0x180010277  mov     ecx, eax
0x180010279  call    ??$HandleEvent@$04J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<5,long>(long)
0x18001027e  test    esi, esi
0x180010280  js      short loc_1800102A0
0x180010282  cmp     byte ptr [rdi+30h], 0
0x180010286  jnz     short loc_1800102A0
0x180010288  mov     r8, rbx; struct IUpdateCollection *
0x18001028b  mov     rdx, [rbp+arg_8]; struct IUpdateSession *
0x18001028f  mov     rcx, rdi; this
0x180010292  call    ?Install@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z; OobeZdpElevatedManagerCore::Install(IUpdateSession *,IUpdateCollection *)
0x180010297  mov     esi, eax
0x180010299  mov     ecx, eax
0x18001029b  call    ??$HandleEvent@$05J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<6,long>(long)
0x1800102a0  lea     rbx, [rdi+20h]
0x1800102a4  mov     rcx, rbx; SRWLock
0x1800102a7  call    cs:__imp_AcquireSRWLockShared
0x1800102ad  mov     [rbp+var_20], rbx
0x1800102b1  mov     rcx, [rdi+28h]
0x1800102b5  mov     rax, [rcx]
0x1800102b8  mov     edx, 4
0x1800102bd  mov     rax, [rax+30h]
0x1800102c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102c6  mov     rcx, [rbp+18h]; this
0x1800102ca  test    eax, eax
0x1800102cc  jns     short loc_1800102E3
0x1800102ce  mov     r9d, eax; char *
0x1800102d1  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800102d8  mov     edx, 7Dh ; '}'; void *
0x1800102dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800102e2  nop
0x1800102e3  lea     rcx, [rbp+var_20]
0x1800102e7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800102ec  nop
0x1800102ed  lea     rcx, [rbp+arg_10]
0x1800102f1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800102f6  nop
0x1800102f7  lea     rcx, [rbp+arg_18]
0x1800102fb  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180010300  nop
0x180010301  lea     rcx, [rbp+var_18]; this
0x180010305  call    ??1AutoExecutionPowerHold@@QEAA@XZ; AutoExecutionPowerHold::~AutoExecutionPowerHold(void)
0x18001030a  nop
0x18001030b  lea     rcx, [rbp+arg_8]
0x18001030f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180010314  mov     eax, esi
0x180010316  mov     rbx, [rsp+50h+arg_0]
0x18001031b  add     rsp, 50h
0x18001031f  pop     rdi
0x180010320  pop     rsi
0x180010321  pop     rbp
0x180010322  retn
```
