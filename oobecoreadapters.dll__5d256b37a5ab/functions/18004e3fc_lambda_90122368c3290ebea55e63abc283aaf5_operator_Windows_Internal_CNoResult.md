# _lambda_90122368c3290ebea55e63abc283aaf5_::operator()(Windows::Internal::CNoResult &)

- ea: `0x18004e3fc`
- end: `0x18004e533`
- name: `??R_lambda_90122368c3290ebea55e63abc283aaf5_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180053230`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x1800266f8`
- `0x180046e48`
- `0x18004e080`
- `0x18004e3fc`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e472`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e472`

## string_xrefs

- `0x18004e483`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`
- `0x18004e4d2`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_90122368c3290ebea55e63abc283aaf5_::operator()(unsigned int *a1, void *a2)
{
  LPVOID v3; // rcx
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  void *v11; // [rsp+40h] [rbp+10h] BYREF
  LPVOID v12; // [rsp+48h] [rbp+18h] BYREF

  v12 = a2;
  v11 = 0;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 96LL) )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeSettingsElevatedManagerCore,wil::err_exception_policy>::operator=(&v11);
  }
  else
  {
    v11 = 0;
    v7 = CloudExperienceHostCreateElevatedObject(
           &GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c,
           &GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b,
           &v11);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28C,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
        (const char *)(unsigned int)v7,
        ppv);
      goto LABEL_13;
    }
  }
  wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(
    &v12,
    *(_QWORD *)a1 + 96LL);
  v3 = v12;
  if ( v12 )
  {
LABEL_10:
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v3 + 64LL))(v3, a1[2]);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 664;
      goto LABEL_6;
    }
LABEL_12:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v12);
    v5 = 0;
    goto LABEL_13;
  }
  v12 = 0;
  v4 = CoCreateInstance(
         &GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c,
         0,
         1u,
         &GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b,
         &v12);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v3 = v12;
    if ( !v12 )
      goto LABEL_12;
    goto LABEL_10;
  }
  v6 = 659;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)v4,
    ppv);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v12);
LABEL_13:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v11);
  return v5;
}

```

## disassembly

```asm
0x18004e3fc  mov     [rsp-8+arg_10], rbx
0x18004e401  mov     [rsp-8+arg_18], rdi
0x18004e406  mov     [rsp-8+arg_8], rdx
0x18004e40b  push    rbp
0x18004e40c  mov     rbp, rsp
0x18004e40f  sub     rsp, 30h
0x18004e413  mov     rdi, rcx
0x18004e416  mov     [rbp+arg_0], 0
0x18004e41e  mov     rax, [rcx]
0x18004e421  mov     rdx, [rax+60h]
0x18004e425  test    rdx, rdx
0x18004e428  jz      short loc_18004E4A2
0x18004e42a  lea     rcx, [rbp+arg_0]
0x18004e42e  call    ??4?$com_ptr_t@UIOobeSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIOobeSettingsElevatedManagerCore@CloudExperienceHostAPI@@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeSettingsElevatedManagerCore,wil::err_exception_policy>::operator=(CloudExperienceHostAPI::IOobeSettingsElevatedManagerCore *)
0x18004e433  mov     rdx, [rdi]
0x18004e436  add     rdx, 60h ; '`'
0x18004e43a  lea     rcx, [rbp+arg_8]
0x18004e43e  call    ??0?$com_ptr_t@UICoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy> const &)
0x18004e443  nop
0x18004e444  mov     rcx, [rbp+arg_8]
0x18004e448  test    rcx, rcx
0x18004e44b  jnz     loc_18004E4EE
0x18004e451  mov     [rbp+arg_8], rcx
0x18004e455  lea     rax, [rbp+arg_8]
0x18004e459  mov     qword ptr [rsp+30h+ppv], rax; int
0x18004e45e  lea     r9, _GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b; riid
0x18004e465  xor     edx, edx; pUnkOuter
0x18004e467  lea     r8d, [rcx+1]; dwClsContext
0x18004e46b  lea     rcx, _GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c; rclsid
0x18004e472  call    cs:__imp_CoCreateInstance
0x18004e478  mov     ebx, eax
0x18004e47a  test    eax, eax
0x18004e47c  jns     short loc_18004E4E5
0x18004e47e  mov     edx, 293h; void *
0x18004e483  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004e48a  mov     r9d, eax; char *
0x18004e48d  mov     rcx, [rbp+8]; this
0x18004e491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e496  nop
0x18004e497  lea     rcx, [rbp+arg_8]
0x18004e49b  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004e4a0  jmp     short loc_18004E518
0x18004e4a2  mov     [rbp+arg_0], 0
0x18004e4aa  lea     r8, [rbp+arg_0]; void **
0x18004e4ae  lea     rdx, _GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b; struct _GUID *
0x18004e4b5  lea     rcx, _GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c; struct _GUID *
0x18004e4bc  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18004e4c1  mov     ebx, eax
0x18004e4c3  test    eax, eax
0x18004e4c5  jns     loc_18004E433
0x18004e4cb  mov     rcx, [rbp+8]; this
0x18004e4cf  mov     r9d, eax; char *
0x18004e4d2  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004e4d9  mov     edx, 28Ch; void *
0x18004e4de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e4e3  jmp     short loc_18004E518
0x18004e4e5  mov     rcx, [rbp+arg_8]
0x18004e4e9  test    rcx, rcx
0x18004e4ec  jz      short loc_18004E50D
0x18004e4ee  mov     rax, [rcx]
0x18004e4f1  mov     edx, [rdi+8]
0x18004e4f4  mov     rax, [rax+40h]
0x18004e4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4fd  mov     ebx, eax
0x18004e4ff  test    eax, eax
0x18004e501  jns     short loc_18004E50D
0x18004e503  mov     edx, 298h
0x18004e508  jmp     loc_18004E483
0x18004e50d  lea     rcx, [rbp+arg_8]
0x18004e511  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004e516  xor     ebx, ebx
0x18004e518  lea     rcx, [rbp+arg_0]
0x18004e51c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004e521  mov     eax, ebx
0x18004e523  mov     rbx, [rsp+30h+arg_10]
0x18004e528  mov     rdi, [rsp+30h+arg_18]
0x18004e52d  add     rsp, 30h
0x18004e531  pop     rbp
0x18004e532  retn
```
