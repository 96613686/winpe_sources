# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptinCoreForUser::ActivateOobeOneDriveOptinAsUser(Windows::System::IUser *,CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin * *)

- ea: `0x18005dd3c`
- end: `0x18005de32`
- name: `?ActivateOobeOneDriveOptinAsUser@OOBEOneDriveOptinCoreForUser@SyncEngine@CloudExperienceHostBroker@@AEAAJPEAUIUser@System@Windows@@PEAPEAUIOOBEOneDriveOptin@23@@Z`
- size: `246`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptinCoreForUser *__hidden this, struct Windows::System::IUser *, struct CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin **)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005e540`
- `0x18005eb40`
- `0x18005ece0`
- `0x18005eec0`
- `0x18005f030`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18005d084`
- `0x18005dd3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005ddc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005ddc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005dda9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005dda9`

## string_xrefs

- `0x18005dda2`: `CloudExperienceHostBroker.SyncEngine.OOBEOneDriveOptinCore`
- `0x18005dd6d`: `shellcommon\shell\oobe\core\components\winrt\oobesyncengineapicore.cpp`
- `0x18005dde8`: `shellcommon\shell\oobe\core\components\winrt\oobesyncengineapicore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptinCoreForUser::ActivateOobeOneDriveOptinAsUser(
        CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptinCoreForUser *this,
        struct Windows::System::IUser *a2,
        struct CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin **a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  struct CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin *v7; // rax
  int v9[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    *(_QWORD *)v9 = 0;
    if ( WindowsCreateStringReference(
           L"CloudExperienceHostBroker.SyncEngine.OOBEOneDriveOptinCore",
           0x3Au,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = Windows::Foundation::GetActivationFactoryAsUser<CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin>(
           string,
           a2,
           v9);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = *(struct CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin **)v9;
      *(_QWORD *)v9 = 0;
      *a3 = v7;
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesyncengineapicore.cpp",
        (const char *)(unsigned int)v6,
        v9[0]);
    }
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(v9);
  }
  else
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesyncengineapicore.cpp",
      (const char *)0x80004003LL,
      v9[0]);
  }
  return v5;
}

```

## disassembly

```asm
0x18005dd3c  mov     [rsp+arg_0], rbx
0x18005dd41  push    rdi
0x18005dd42  sub     rsp, 50h
0x18005dd46  mov     rax, cs:__security_cookie
0x18005dd4d  xor     rax, rsp
0x18005dd50  mov     [rsp+58h+var_10], rax
0x18005dd55  mov     rdi, r8
0x18005dd58  mov     rbx, rdx
0x18005dd5b  test    r8, r8
0x18005dd5e  jnz     short loc_18005DD83
0x18005dd60  mov     rcx, [rsp+58h]; this
0x18005dd65  mov     ebx, 80004003h
0x18005dd6a  mov     r9d, ebx; char *
0x18005dd6d  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005dd74  mov     edx, 85h; void *
0x18005dd79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dd7e  jmp     loc_18005DE18
0x18005dd83  mov     qword ptr [r8], 0
0x18005dd8a  mov     qword ptr [rsp+58h+var_38], 0; int
0x18005dd93  lea     r9, [rsp+58h+string]; string
0x18005dd98  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18005dd9d  mov     edx, 3Ah ; ':'; length
0x18005dda2  lea     rcx, ?RuntimeClass_CloudExperienceHostBroker_SyncEngine_OOBEOneDriveOptinCore@@3QBGB; "CloudExperienceHostBroker.SyncEngine.OO"...
0x18005dda9  call    cs:__imp_WindowsCreateStringReference
0x18005ddaf  test    eax, eax
0x18005ddb1  jns     short loc_18005DDC8
0x18005ddb3  xor     r9d, r9d; lpArguments
0x18005ddb6  xor     r8d, r8d; nNumberOfArguments
0x18005ddb9  lea     edx, [r9+1]; dwExceptionFlags
0x18005ddbd  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005ddc2  call    cs:__imp_RaiseException
0x18005ddc8  lea     r8, [rsp+58h+var_38]
0x18005ddcd  mov     rdx, rbx
0x18005ddd0  mov     rcx, [rsp+58h+string]
0x18005ddd5  call    ??$GetActivationFactoryAsUser@UIOOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUIOOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@@Z; Windows::Foundation::GetActivationFactoryAsUser<CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin>(HSTRING__ *,Windows::System::IUser *,CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin * *)
0x18005ddda  mov     ebx, eax
0x18005dddc  test    eax, eax
0x18005ddde  jns     short loc_18005DDFB
0x18005dde0  mov     rcx, [rsp+58h]; this
0x18005dde5  mov     r9d, eax; char *
0x18005dde8  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005ddef  mov     edx, 8Ah; void *
0x18005ddf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ddf9  jmp     short loc_18005DE0E
0x18005ddfb  mov     rax, qword ptr [rsp+58h+var_38]
0x18005de00  mov     qword ptr [rsp+58h+var_38], 0
0x18005de09  mov     [rdi], rax
0x18005de0c  xor     ebx, ebx
0x18005de0e  lea     rcx, [rsp+58h+var_38]
0x18005de13  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005de18  mov     eax, ebx
0x18005de1a  mov     rcx, [rsp+58h+var_10]
0x18005de1f  xor     rcx, rsp; StackCookie
0x18005de22  call    __security_check_cookie
0x18005de27  mov     rbx, [rsp+58h+arg_0]
0x18005de2c  add     rsp, 50h
0x18005de30  pop     rdi
0x18005de31  retn
```
