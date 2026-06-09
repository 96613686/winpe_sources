# _lambda_645992aee5a6b4af0977e82444ecfa7d_::operator()

- ea: `0x180010bfc`
- end: `0x180010c8b`
- name: `_lambda_645992aee5a6b4af0977e82444ecfa7d_::operator()`
- size: `143`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012e80`

## callees

- `0x180002b10`
- `0x180008378`
- `0x1800091c4`
- `0x18000f710`
- `0x180010678`
- `0x180010bfc`
- `0x180013360`

## pseudocode

```c
void __fastcall lambda_645992aee5a6b4af0977e82444ecfa7d_::operator()(Microsoft::IoT::ShellExtension::CCBTLauncher **a1)
{
  int v2; // eax
  int v3[84]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::Start<>((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *)v3);
  v2 = Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(*a1);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v2,
      (int)v3);
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v3);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *)v3);
}

```

## disassembly

```asm
0x180010bfc  push    rbx
0x180010bfe  sub     rsp, 190h
0x180010c05  mov     rax, cs:__security_cookie
0x180010c0c  xor     rax, rsp
0x180010c0f  mov     [rsp+198h+var_18], rax
0x180010c17  mov     rbx, rcx
0x180010c1a  lea     rcx, [rsp+198h+var_168]; this
0x180010c1f  call    ??$Start@$$V@BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SA?AV01234@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::Start<>(void)
0x180010c24  nop
0x180010c25  lea     rax, [rsp+198h+var_168]
0x180010c2a  mov     qword ptr [rsp+198h+var_178], rax; int
0x180010c2f  mov     [rsp+198h+var_170], 1
0x180010c34  mov     rcx, [rbx]; this
0x180010c37  call    ?Reactivate@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(void)
0x180010c3c  mov     rcx, [rsp+198h]; this
0x180010c44  test    eax, eax
0x180010c46  jns     short loc_180010C5D
0x180010c48  mov     r9d, eax; char *
0x180010c4b  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180010c52  mov     edx, 22Ah; void *
0x180010c57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010c5c  nop
0x180010c5d  lea     rcx, [rsp+198h+var_168]
0x180010c62  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010c67  nop
0x180010c68  lea     rcx, [rsp+198h+var_168]; this
0x180010c6d  call    ??1BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch(void)
0x180010c72  mov     rcx, [rsp+198h+var_18]
0x180010c7a  xor     rcx, rsp; StackCookie
0x180010c7d  call    __security_check_cookie
0x180010c82  add     rsp, 190h
0x180010c89  pop     rbx
0x180010c8a  retn
```
