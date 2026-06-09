# CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser::ActivateoobeCortanaManagerAsUser(Windows::System::IUser *,CloudExperienceHostBroker::Cortana::IOOBECortanaManager * *)

- ea: `0x18006072c`
- end: `0x180060820`
- name: `?ActivateoobeCortanaManagerAsUser@OOBECortanaManagerCoreForUser@Cortana@CloudExperienceHostBroker@@AEAAJPEAUIUser@System@Windows@@PEAPEAUIOOBECortanaManager@23@@Z`
- size: `244`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser *__hidden this, struct Windows::System::IUser *, struct CloudExperienceHostBroker::Cortana::IOOBECortanaManager **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180067150`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18005f3cc`
- `0x18006072c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180060797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180060797`

## string_xrefs

- `0x180060790`: `CloudExperienceHostBroker.Cortana.OOBECortanaManagerCore`
- `0x18006075d`: `shellcommon\shell\oobe\core\components\winrt\oobecortanamanagercore.cpp`
- `0x1800607d6`: `shellcommon\shell\oobe\core\components\winrt\oobecortanamanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser::ActivateoobeCortanaManagerAsUser(
        CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser *this,
        struct Windows::System::IUser *a2,
        struct CloudExperienceHostBroker::Cortana::IOOBECortanaManager **a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  struct CloudExperienceHostBroker::Cortana::IOOBECortanaManager *v7; // rax
  int v9[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    *(_QWORD *)v9 = 0;
    if ( WindowsCreateStringReference(
           L"CloudExperienceHostBroker.Cortana.OOBECortanaManagerCore",
           0x38u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = Windows::Foundation::GetActivationFactoryAsUser<CloudExperienceHostBroker::Cortana::IOOBECortanaManager>(
           string,
           a2,
           v9);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = *(struct CloudExperienceHostBroker::Cortana::IOOBECortanaManager **)v9;
      *(_QWORD *)v9 = 0;
      *a3 = v7;
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobecortanamanagercore.cpp",
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
      (void *)0x7D,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobecortanamanagercore.cpp",
      (const char *)0x80004003LL,
      v9[0]);
  }
  return v5;
}

```

## disassembly

```asm
0x18006072c  mov     [rsp+arg_0], rbx
0x180060731  push    rdi
0x180060732  sub     rsp, 50h
0x180060736  mov     rax, cs:__security_cookie
0x18006073d  xor     rax, rsp
0x180060740  mov     [rsp+58h+var_10], rax
0x180060745  mov     rdi, r8
0x180060748  mov     rbx, rdx
0x18006074b  test    r8, r8
0x18006074e  jnz     short loc_180060771
0x180060750  mov     rcx, [rsp+58h]; this
0x180060755  mov     ebx, 80004003h
0x18006075a  mov     r9d, ebx; char *
0x18006075d  lea     r8, aShellcommonShe_25; "shellcommon\\shell\\oobe\\core\\compone"...
0x180060764  lea     edx, [rdi+7Dh]; void *
0x180060767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006076c  jmp     loc_180060806
0x180060771  mov     qword ptr [r8], 0
0x180060778  mov     qword ptr [rsp+58h+var_38], 0; int
0x180060781  lea     r9, [rsp+58h+string]; string
0x180060786  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18006078b  mov     edx, 38h ; '8'; length
0x180060790  lea     rcx, ?RuntimeClass_CloudExperienceHostBroker_Cortana_OOBECortanaManagerCore@@3QBGB; "CloudExperienceHostBroker.Cortana.OOBEC"...
0x180060797  call    cs:__imp_WindowsCreateStringReference
0x18006079d  test    eax, eax
0x18006079f  jns     short loc_1800607B6
0x1800607a1  xor     r9d, r9d; lpArguments
0x1800607a4  xor     r8d, r8d; nNumberOfArguments
0x1800607a7  lea     edx, [r9+1]; dwExceptionFlags
0x1800607ab  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800607b0  call    cs:__imp_RaiseException
0x1800607b6  lea     r8, [rsp+58h+var_38]
0x1800607bb  mov     rdx, rbx
0x1800607be  mov     rcx, [rsp+58h+string]
0x1800607c3  call    ??$GetActivationFactoryAsUser@UIOOBECortanaManager@Cortana@CloudExperienceHostBroker@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUIOOBECortanaManager@Cortana@CloudExperienceHostBroker@@@Z; Windows::Foundation::GetActivationFactoryAsUser<CloudExperienceHostBroker::Cortana::IOOBECortanaManager>(HSTRING__ *,Windows::System::IUser *,CloudExperienceHostBroker::Cortana::IOOBECortanaManager * *)
0x1800607c8  mov     ebx, eax
0x1800607ca  test    eax, eax
0x1800607cc  jns     short loc_1800607E9
0x1800607ce  mov     rcx, [rsp+58h]; this
0x1800607d3  mov     r9d, eax; char *
0x1800607d6  lea     r8, aShellcommonShe_25; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800607dd  mov     edx, 82h; void *
0x1800607e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800607e7  jmp     short loc_1800607FC
0x1800607e9  mov     rax, qword ptr [rsp+58h+var_38]
0x1800607ee  mov     qword ptr [rsp+58h+var_38], 0
0x1800607f7  mov     [rdi], rax
0x1800607fa  xor     ebx, ebx
0x1800607fc  lea     rcx, [rsp+58h+var_38]
0x180060801  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180060806  mov     eax, ebx
0x180060808  mov     rcx, [rsp+58h+var_10]
0x18006080d  xor     rcx, rsp; StackCookie
0x180060810  call    __security_check_cookie
0x180060815  mov     rbx, [rsp+58h+arg_0]
0x18006081a  add     rsp, 50h
0x18006081e  pop     rdi
0x18006081f  retn
```
