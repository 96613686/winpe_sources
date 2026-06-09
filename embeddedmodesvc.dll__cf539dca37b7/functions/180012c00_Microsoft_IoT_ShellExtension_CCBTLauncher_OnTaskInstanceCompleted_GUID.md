# Microsoft::IoT::ShellExtension::CCBTLauncher::OnTaskInstanceCompleted(_GUID)

- ea: `0x180012c00`
- end: `0x180012e6f`
- name: `?OnTaskInstanceCompleted@CCBTLauncher@ShellExtension@IoT@Microsoft@@UEAAXU_GUID@@@Z`
- size: `623`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012bd0`

## callees

- `0x180002b10`
- `0x180008358`
- `0x180008378`
- `0x18000854c`
- `0x1800091c4`
- `0x18000acf4`
- `0x18000d410`
- `0x18000ef0c`
- `0x18000ef70`
- `0x18000efd4`
- `0x180010100`
- `0x180010620`
- `0x180011134`
- `0x180012c00`
- `0x180012f10`
- `0x180013818`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012d16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012db6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012d16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012db6`

## string_xrefs

- `0x180012c32`: `BackgroundTaskCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::OnTaskInstanceCompleted(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this,
        struct _GUID *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rcx
  Microsoft::IoT::ShellExtension::CCBTLauncher *v8; // rbx
  _QWORD *v9; // rax
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-228h]
  _QWORD *v12; // [rsp+28h] [rbp-220h] BYREF
  __int128 v13; // [rsp+30h] [rbp-218h] BYREF
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+40h] [rbp-208h] BYREF
  wil::ResultException *v15[2]; // [rsp+48h] [rbp-200h] BYREF
  char v16; // [rsp+58h] [rbp-1F0h]
  void *v17[2]; // [rsp+60h] [rbp-1E8h] BYREF
  __int64 *v18; // [rsp+70h] [rbp-1D8h]
  __int64 v19; // [rsp+88h] [rbp-1C0h]
  int v20[10]; // [rsp+98h] [rbp-1B0h] BYREF
  _QWORD v21[42]; // [rsp+C0h] [rbp-188h] BYREF
  std::bad_alloc *v22; // [rsp+210h] [rbp-38h] BYREF
  std::invalid_argument *v23; // [rsp+218h] [rbp-30h] BYREF
  std::range_error *v24; // [rsp+220h] [rbp-28h] BYREF
  std::runtime_error *v25; // [rsp+228h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v11 = 0;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v21,
    (__int64)"BackgroundTaskCompleted");
  v21[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted::StartActivity((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted *)v21);
  v15[1] = (wil::ResultException *)v21;
  v16 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  v4 = *((_QWORD *)this + 16);
  v13 = (__int128)*a2;
  while ( 1 )
  {
    if ( v4 == *((_QWORD *)this + 17) )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xE0,
        (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)0x8000FFFFLL,
        0);
    v5 = v13 - *(_QWORD *)(v4 + 60);
    if ( (_QWORD)v13 == *(_QWORD *)(v4 + 60) )
      v5 = *((_QWORD *)&v13 + 1) - *(_QWORD *)(v4 + 68);
    if ( !v5 )
      break;
    v4 += 88;
  }
  try
  {
    if ( *(_BYTE *)(v4 + 78) || *(_BYTE *)(v4 + 79) )
    {
      *(_DWORD *)(v4 + 56) = -2147024186;
      *(_QWORD *)(v4 + 8) = GetTickCount64();
      *(_QWORD *)&v13 = *(_QWORD *)(v4 + 40);
      v9 = *(_QWORD **)(v4 + 16);
      if ( v9 )
        v9 = (_QWORD *)*v9;
      v12 = v9;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompletedDone<unsigned short *,unsigned short *>(
        (__int64 *)&v12,
        (__int64 *)&v13);
      v8 = (Microsoft::IoT::ShellExtension::CCBTLauncher *)((char *)this - 32);
    }
    else
    {
      if ( *(_DWORD *)(v4 + 56) == -2147483638 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 40LL))(*((_QWORD *)this + 2));
      *(_DWORD *)(v4 + 56) = -2147467259;
      *(_QWORD *)(v4 + 8) = GetTickCount64();
      v12 = *(_QWORD **)(v4 + 40);
      v6 = *(_QWORD **)(v4 + 16);
      if ( v6 )
        v6 = (_QWORD *)*v6;
      *(_QWORD *)&v13 = v6;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompletedFailed<unsigned short *,unsigned short *>(
        (__int64 *)&v13,
        (__int64 *)&v12);
      Microsoft::IoT::ShellExtension::CCBT::CCBT(
        (Microsoft::IoT::ShellExtension::CCBT *)v17,
        (const struct Microsoft::IoT::ShellExtension::CCBT *)v4);
      *(_QWORD *)&v13 = v19;
      if ( v18 )
        v7 = *v18;
      else
        v7 = 0;
      v12 = (_QWORD *)v7;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskFailed<unsigned short *,unsigned short *,long &>(
        (__int64 *)&v12,
        (__int64 *)&v13,
        v20);
      v8 = (Microsoft::IoT::ShellExtension::CCBTLauncher *)((char *)this - 32);
      Microsoft::IoT::ShellExtension::CCBTLauncher::ReLaunch(
        (Microsoft::IoT::ShellExtension::CCBTLauncher *)((char *)this - 32),
        (struct Microsoft::IoT::ShellExtension::CCBT *)v17);
      Microsoft::IoT::ShellExtension::CCBT::~CCBT(v17);
    }
    Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(v8);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v14);
  }
  catch ( wil::ResultException *v15 )
  {
    v11 = *((_DWORD *)v15[0] + 8);
  }
  catch ( std::bad_alloc *v22 )
  {
    v11 = -2147024882;
  }
  catch ( std::invalid_argument *v23 )
  {
    v11 = -2147024809;
  }
  catch ( std::range_error *v24 )
  {
    v11 = -2147483637;
  }
  catch ( std::runtime_error *v25 )
  {
    v11 = -2147467259;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xFD,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      v10);
  }
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFD,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v11);
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v21);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted::~BackgroundTaskCompleted((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted *)v21);
}

```

## disassembly

```asm
0x180012c00  mov     [rsp+arg_8], rbx
0x180012c05  mov     [rsp+arg_10], rsi
0x180012c0a  push    rdi
0x180012c0b  sub     rsp, 240h
0x180012c12  mov     rax, cs:__security_cookie
0x180012c19  xor     rax, rsp
0x180012c1c  mov     [rsp+248h+var_18], rax
0x180012c24  mov     rsi, rdx
0x180012c27  mov     rdi, rcx
0x180012c2a  mov     dword ptr [rsp+248h+var_228], 0
0x180012c32  lea     rdx, aBackgroundtask_4; "BackgroundTaskCompleted"
0x180012c39  lea     rcx, [rsp+248h+var_188]
0x180012c41  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012c46  lea     rax, ??_7BackgroundTaskCompleted@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted::`vftable'
0x180012c4d  mov     [rsp+248h+var_188], rax
0x180012c55  lea     rcx, [rsp+248h+var_188]; this
0x180012c5d  call    ?StartActivity@BackgroundTaskCompleted@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted::StartActivity(void)
0x180012c62  nop
0x180012c63  lea     rax, [rsp+248h+var_188]
0x180012c6b  mov     [rsp+248h+var_1F8], rax
0x180012c70  mov     [rsp+248h+var_1F0], 1
0x180012c75  lea     rbx, [rdi+40h]
0x180012c79  mov     rcx, rbx; lpCriticalSection
0x180012c7c  call    cs:__imp_EnterCriticalSection
0x180012c82  mov     [rsp+248h+var_208], rbx
0x180012c87  mov     rbx, [rdi+80h]
0x180012c8e  movups  xmm0, xmmword ptr [rsi]
0x180012c91  movdqu  [rsp+248h+var_218], xmm0
0x180012c97  mov     rcx, [rdi+88h]
0x180012c9e  jmp     short loc_180012CBD
0x180012ca0  mov     rax, qword ptr [rsp+248h+var_218]
0x180012ca5  sub     rax, [rbx+3Ch]
0x180012ca9  jnz     short loc_180012CB4
0x180012cab  mov     rax, qword ptr [rsp+248h+var_218+8]
0x180012cb0  sub     rax, [rbx+44h]
0x180012cb4  test    rax, rax
0x180012cb7  jz      short loc_180012CE2
0x180012cb9  add     rbx, 58h ; 'X'
0x180012cbd  cmp     rbx, rcx
0x180012cc0  jnz     short loc_180012CA0
0x180012cc2  mov     rcx, [rsp+248h]; this
0x180012cca  mov     r9d, 8000FFFFh; char *
0x180012cd0  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012cd7  mov     edx, 0E0h; void *
0x180012cdc  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180012ce2  cmp     byte ptr [rbx+4Eh], 0
0x180012ce6  jnz     loc_180012DAF
0x180012cec  cmp     byte ptr [rbx+4Fh], 0
0x180012cf0  jnz     loc_180012DAF
0x180012cf6  cmp     dword ptr [rbx+38h], 8000000Ah
0x180012cfd  jnz     short loc_180012D0F
0x180012cff  mov     rcx, [rdi+10h]
0x180012d03  mov     rax, [rcx]
0x180012d06  mov     rax, [rax+28h]
0x180012d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d0f  mov     dword ptr [rbx+38h], 80004005h
0x180012d16  call    cs:__imp_GetTickCount64
0x180012d1c  mov     [rbx+8], rax
0x180012d20  mov     rax, [rbx+28h]
0x180012d24  mov     [rsp+248h+var_220], rax
0x180012d29  mov     rax, [rbx+10h]
0x180012d2d  test    rax, rax
0x180012d30  jz      short loc_180012D35
0x180012d32  mov     rax, [rax]
0x180012d35  mov     qword ptr [rsp+248h+var_218], rax
0x180012d3a  lea     rdx, [rsp+248h+var_220]
0x180012d3f  lea     rcx, [rsp+248h+var_218]
0x180012d44  call    ??$BackgroundTaskCompletedFailed@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompletedFailed<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180012d49  mov     rdx, rbx; struct Microsoft::IoT::ShellExtension::CCBT *
0x180012d4c  lea     rcx, [rsp+248h+var_1E8]; this
0x180012d51  call    ??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT const &)
0x180012d56  nop
0x180012d57  mov     rax, [rsp+248h+var_1C0]
0x180012d5f  mov     qword ptr [rsp+248h+var_218], rax
0x180012d64  mov     rax, [rsp+248h+var_1D8]
0x180012d69  test    rax, rax
0x180012d6c  jz      short loc_180012D73
0x180012d6e  mov     rcx, [rax]
0x180012d71  jmp     short loc_180012D75
0x180012d73  xor     ecx, ecx
0x180012d75  mov     [rsp+248h+var_220], rcx
0x180012d7a  lea     r8, [rsp+248h+var_1B0]
0x180012d82  lea     rdx, [rsp+248h+var_218]
0x180012d87  lea     rcx, [rsp+248h+var_220]
0x180012d8c  call    ??$BackgroundTaskFailed@PEAGPEAGAEAJ@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0AEAJ@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskFailed<ushort *,ushort *,long &>(ushort * &&,ushort * &&,long &)
0x180012d91  lea     rbx, [rdi-20h]
0x180012d95  lea     rdx, [rsp+248h+var_1E8]; struct Microsoft::IoT::ShellExtension::CCBT *
0x180012d9a  mov     rcx, rbx; this
0x180012d9d  call    ?ReLaunch@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXAEAVCCBT@234@@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::ReLaunch(Microsoft::IoT::ShellExtension::CCBT &)
0x180012da2  nop
0x180012da3  lea     rcx, [rsp+248h+var_1E8]; this
0x180012da8  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x180012dad  jmp     short loc_180012DED
0x180012daf  mov     dword ptr [rbx+38h], 800702C6h
0x180012db6  call    cs:__imp_GetTickCount64
0x180012dbc  mov     [rbx+8], rax
0x180012dc0  mov     rax, [rbx+28h]
0x180012dc4  mov     qword ptr [rsp+248h+var_218], rax
0x180012dc9  mov     rax, [rbx+10h]
0x180012dcd  test    rax, rax
0x180012dd0  jz      short loc_180012DD5
0x180012dd2  mov     rax, [rax]
0x180012dd5  mov     [rsp+248h+var_220], rax
0x180012dda  lea     rdx, [rsp+248h+var_218]
0x180012ddf  lea     rcx, [rsp+248h+var_220]
0x180012de4  call    ??$BackgroundTaskCompletedDone@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompletedDone<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180012de9  lea     rbx, [rdi-20h]
0x180012ded  mov     rcx, rbx; this
0x180012df0  call    ?CheckForPendingTasks@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(void)
0x180012df5  nop
0x180012df6  lea     rcx, [rsp+248h+var_208]
0x180012dfb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180012e00  nop
0x180012e01  jmp     short loc_180012E0B
0x180012e03  jmp     short loc_180012E0B
0x180012e05  jmp     short loc_180012E0B
0x180012e07  jmp     short loc_180012E0B
0x180012e09  jmp     short $+2
0x180012e0b  mov     rcx, [rsp+248h]; this
0x180012e13  mov     r9d, dword ptr [rsp+248h+var_228]; char *
0x180012e18  test    r9d, r9d
0x180012e1b  jns     short loc_180012E2F
0x180012e1d  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012e24  mov     edx, 0FDh; void *
0x180012e29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012e2e  nop
0x180012e2f  lea     rcx, [rsp+248h+var_188]
0x180012e37  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180012e3c  nop
0x180012e3d  lea     rcx, [rsp+248h+var_188]; this
0x180012e45  call    ??1BackgroundTaskCompleted@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCompleted::~BackgroundTaskCompleted(void)
0x180012e4a  mov     rcx, [rsp+248h+var_18]
0x180012e52  xor     rcx, rsp; StackCookie
0x180012e55  call    __security_check_cookie
0x180012e5a  lea     r11, [rsp+248h+var_8]
0x180012e62  mov     rbx, [r11+18h]
0x180012e66  mov     rsi, [r11+20h]
0x180012e6a  mov     rsp, r11
0x180012e6d  pop     rdi
0x180012e6e  retn
```
