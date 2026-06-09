# _lambda_1bb57df98d7ba98072f104d9e64aece0_::operator()

- ea: `0x18000af90`
- end: `0x18000b098`
- name: `_lambda_1bb57df98d7ba98072f104d9e64aece0_::operator()`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bd40`

## callees

- `0x180002b10`
- `0x180008358`
- `0x180008378`
- `0x18000854c`
- `0x1800091c4`
- `0x18000acc8`
- `0x18000af90`
- `0x18000b6a4`
- `0x18000becc`

## string_xrefs

- `0x18000b002`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`
- `0x18000b02f`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`
- `0x18000b065`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`
- `0x18000afb4`: `BackgroundTaskSettingsChanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall lambda_1bb57df98d7ba98072f104d9e64aece0_::operator()(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost **a1)
{
  int v2; // ebx
  int Launchers; // eax
  const char *v4; // r9
  int v5; // [rsp+20h] [rbp-1A8h]
  wil::ResultException *v7[2]; // [rsp+28h] [rbp-1A0h] BYREF
  char v8; // [rsp+38h] [rbp-190h]
  _QWORD v9[42]; // [rsp+40h] [rbp-188h] BYREF
  std::bad_alloc *v10; // [rsp+190h] [rbp-38h] BYREF
  std::invalid_argument *v11; // [rsp+198h] [rbp-30h] BYREF
  std::range_error *v12; // [rsp+1A0h] [rbp-28h] BYREF
  std::runtime_error *v13; // [rsp+1A8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v2 = 0;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)"BackgroundTaskSettingsChanged");
  v9[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::StartActivity((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged *)v9);
  try
  {
    v7[1] = (wil::ResultException *)v9;
    v8 = 1;
    Launchers = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::EnumerateUsersAndCreateLaunchers(*a1);
    if ( Launchers < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x61,
        (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
        (const char *)(unsigned int)Launchers);
  }
  catch ( wil::ResultException *v7 )
  {
    v5 = *((_DWORD *)v7[0] + 8);
    v2 = v5;
  }
  catch ( std::bad_alloc *v10 )
  {
    v5 = -2147024882;
    v2 = v5;
  }
  catch ( std::invalid_argument *v11 )
  {
    v5 = -2147024809;
    v2 = v5;
  }
  catch ( std::range_error *v12 )
  {
    v5 = -2147483637;
    v2 = v5;
  }
  catch ( std::runtime_error *v13 )
  {
    v5 = -2147467259;
    v2 = v5;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x61,
      (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
      v4);
  }
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x61,
      (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
      (const char *)(unsigned int)v2);
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v9);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::~BackgroundTaskSettingsChanged((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged *)v9);
  if ( v2 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x61,
      (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
      (const char *)(unsigned int)v2,
      v5);
}

```

## disassembly

```asm
0x18000af90  mov     [rsp+arg_8], rbx
0x18000af95  push    rdi
0x18000af96  sub     rsp, 1C0h
0x18000af9d  mov     rax, cs:__security_cookie
0x18000afa4  xor     rax, rsp
0x18000afa7  mov     [rsp+1C8h+var_18], rax
0x18000afaf  mov     rdi, rcx
0x18000afb2  xor     ebx, ebx
0x18000afb4  lea     rdx, aBackgroundtask; "BackgroundTaskSettingsChanged"
0x18000afbb  lea     rcx, [rsp+1C8h+var_188]
0x18000afc0  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000afc5  lea     rax, ??_7BackgroundTaskSettingsChanged@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::`vftable'
0x18000afcc  mov     [rsp+1C8h+var_188], rax
0x18000afd1  lea     rcx, [rsp+1C8h+var_188]; this
0x18000afd6  call    ?StartActivity@BackgroundTaskSettingsChanged@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::StartActivity(void)
0x18000afdb  nop
0x18000afdc  lea     rax, [rsp+1C8h+var_188]
0x18000afe1  mov     [rsp+1C8h+var_198], rax
0x18000afe6  mov     [rsp+1C8h+var_190], 1
0x18000afeb  mov     rcx, [rdi]; this
0x18000afee  call    ?EnumerateUsersAndCreateLaunchers@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::EnumerateUsersAndCreateLaunchers(void)
0x18000aff3  mov     rcx, [rsp+1C8h]; this
0x18000affb  test    eax, eax
0x18000affd  jns     short loc_18000B012
0x18000afff  mov     r9d, eax; char *
0x18000b002  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000b009  lea     edx, [rbx+61h]; void *
0x18000b00c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b011  nop
0x18000b012  jmp     short loc_18000B020
0x18000b014  jmp     short loc_18000B01C
0x18000b016  jmp     short loc_18000B01C
0x18000b018  jmp     short loc_18000B01C
0x18000b01a  jmp     short $+2
0x18000b01c  mov     ebx, [rsp+1C8h+var_1A8]
0x18000b020  mov     rcx, [rsp+1C8h]; this
0x18000b028  test    ebx, ebx
0x18000b02a  jns     short loc_18000B041
0x18000b02c  mov     r9d, ebx; char *
0x18000b02f  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000b036  mov     edx, 61h ; 'a'; void *
0x18000b03b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b040  nop
0x18000b041  lea     rcx, [rsp+1C8h+var_188]
0x18000b046  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000b04b  nop
0x18000b04c  lea     rcx, [rsp+1C8h+var_188]; this
0x18000b051  call    ??1BackgroundTaskSettingsChanged@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::~BackgroundTaskSettingsChanged(void)
0x18000b056  test    ebx, ebx
0x18000b058  jns     short loc_18000B077
0x18000b05a  mov     rcx, [rsp+1C8h]; this
0x18000b062  mov     r9d, ebx; char *
0x18000b065  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000b06c  mov     edx, 61h ; 'a'; void *
0x18000b071  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000b077  mov     rcx, [rsp+1C8h+var_18]
0x18000b07f  xor     rcx, rsp; StackCookie
0x18000b082  call    __security_check_cookie
0x18000b087  mov     rbx, [rsp+1C8h+arg_8]
0x18000b08f  add     rsp, 1C0h
0x18000b096  pop     rdi
0x18000b097  retn
```
