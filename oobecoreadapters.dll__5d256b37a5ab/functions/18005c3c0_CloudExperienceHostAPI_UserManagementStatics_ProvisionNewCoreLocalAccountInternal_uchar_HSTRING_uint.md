# CloudExperienceHostAPI::UserManagementStatics::ProvisionNewCoreLocalAccountInternal(uchar,HSTRING__ *,uint *)

- ea: `0x18005c3c0`
- end: `0x18005c99c`
- name: `?ProvisionNewCoreLocalAccountInternal@UserManagementStatics@CloudExperienceHostAPI@@CAJEPEAUHSTRING__@@PEAI@Z`
- size: `1500`
- prototype: `__int64 __fastcall(char, HSTRING, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005b8cc`
- `0x18005cc70`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18000a4f8`
- `0x1800266f8`
- `0x18004a0cc`
- `0x18005b1fc`
- `0x18005b970`
- `0x18005bd1c`
- `0x18005c3c0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005c427`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005c427`

## string_xrefs

- `0x18005c43a`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c480`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c529`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c585`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c5f4`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c65c`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c6ad`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c70a`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c77d`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c7e0`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c85e`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`
- `0x18005c8d8`: `shellcommon\shell\oobe\core\components\winrt\usermanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostAPI::UserManagementStatics::ProvisionNewCoreLocalAccountInternal(
        char a1,
        HSTRING a2,
        unsigned int *a3)
{
  int ActivationFactory; // eax
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  __int64 (__fastcall **v9)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdi
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 *v23; // [rsp+20h] [rbp-29h] BYREF
  struct Windows::System::Internal::ISignInContext *v24; // [rsp+28h] [rbp-21h] BYREF
  __int64 v25; // [rsp+30h] [rbp-19h] BYREF
  struct Windows::System::Internal::ISignInResult *v26; // [rsp+38h] [rbp-11h] BYREF
  __int64 v27; // [rsp+40h] [rbp-9h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 **); // [rsp+48h] [rbp-1h] BYREF
  char *v29; // [rsp+50h] [rbp+7h] BYREF
  unsigned int *v30; // [rsp+58h] [rbp+Fh] BYREF
  void *v31; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v33; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v30 = a3;
  *a3 = 0;
  v28 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  ActivationFactory = RoGetActivationFactory(v33, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v28);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v23 = 0;
    v7 = (**v28)(v28, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v23);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 132;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
        (const char *)(unsigned int)v7,
        (int)v23);
      goto LABEL_6;
    }
    v9 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v28;
    if ( a2 )
    {
      v7 = ((__int64 (__fastcall **)(_QWORD, HSTRING, unsigned int *))v9)[7](v28, a2, v30);
      v6 = v7;
      if ( v7 < 0 )
      {
        v8 = 141;
        goto LABEL_5;
      }
    }
    else
    {
      v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **), unsigned int *))v9[6])(
             v28,
             v30);
      v6 = v7;
      if ( v7 < 0 )
      {
        v8 = 137;
        goto LABEL_5;
      }
    }
    hstringHeader.Reserved.Reserved1 = &v23;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v30;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v28;
    LOBYTE(v33) = 1;
    v24 = 0;
    v10 = *v23;
    v24 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct Windows::System::Internal::ISignInContext **))(v10 + 64))(
            v23,
            *v30,
            &v24);
    v6 = v11;
    if ( v11 >= 0 )
    {
      v25 = 0;
      v12 = *v23;
      v25 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::System::Internal::ISignInContext *, __int64 *))(v12 + 56))(
              v23,
              v24,
              &v25);
      v6 = v13;
      if ( v13 >= 0 )
      {
        v26 = 0;
        v14 = v25;
        v6 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SignInResult *> *>(v25);
        if ( v6 >= 0 )
          v6 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::Internal::ISignInResult **))(*(_QWORD *)v14 + 64LL))(
                 v14,
                 &v26);
        if ( v6 >= 0 )
        {
          LODWORD(v29) = 0;
          v15 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInResult *, char **))(*(_QWORD *)v26 + 64LL))(
                  v26,
                  &v29);
          v6 = v15;
          if ( v15 >= 0 )
          {
            v6 = (int)v29;
            if ( (int)v29 >= 0 )
            {
              v16 = CloudExperienceHostAPI::UserManagementStatics::AddCredentialsToSignInContext(v26, v24);
              v6 = v16;
              if ( v16 >= 0 )
              {
                v27 = 0;
                v17 = *v23;
                v27 = 0;
                v18 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::System::Internal::ISignInContext *, __int64 *))(v17 + 192))(
                        v23,
                        v24,
                        &v27);
                v6 = v18;
                if ( v18 >= 0 )
                {
                  v19 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v27);
                  v6 = v19;
                  if ( v19 >= 0 )
                  {
                    if ( a1 )
                    {
                      v31 = 0;
                      v20 = CloudExperienceHostCreateElevatedObject(
                              &GUID_06dc6740_fd0d_426a_9bf6_20ddbd7d53ce,
                              &GUID_d378eac7_a5e7_4359_8838_ebc4c5614f77,
                              &v31);
                      v6 = v20;
                      if ( v20 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xB4,
                          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                          (const char *)(unsigned int)v20,
                          (int)v23);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v31);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
                        LOBYTE(v33) = 0;
                        _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
                        goto LABEL_6;
                      }
                      v21 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v31 + 48LL))(v31, *v30);
                      v6 = v21;
                      if ( v21 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xB5,
                          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                          (const char *)(unsigned int)v21,
                          (int)v23);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v31);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
                        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
                        LOBYTE(v33) = 0;
                        _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
                        goto LABEL_6;
                      }
                      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v31);
                    }
                    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
                    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
                    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
                    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
                    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v23);
                    v6 = 0;
                    goto LABEL_37;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xAE,
                    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                    (const char *)(unsigned int)v19,
                    (int)v23);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
                  LOBYTE(v33) = 0;
                  _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xAD,
                    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                    (const char *)(unsigned int)v18,
                    (int)v23);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
                  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
                  LOBYTE(v33) = 0;
                  _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xAA,
                  (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                  (const char *)(unsigned int)v16,
                  (int)v23);
                wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
                wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
                wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
                LOBYTE(v33) = 0;
                _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA7,
                (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
                (const char *)(unsigned int)v29,
                (int)v23);
              wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
              wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
              wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
              LOBYTE(v33) = 0;
              _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA6,
              (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
              (const char *)(unsigned int)v15,
              (int)v23);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
            LOBYTE(v33) = 0;
            _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA2,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
            (const char *)(unsigned int)v6,
            (int)v23);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
          LOBYTE(v33) = 0;
          _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
          (const char *)(unsigned int)v13,
          (int)v23);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v25);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
        LOBYTE(v33) = 0;
        _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
        (const char *)(unsigned int)v11,
        (int)v23);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v24);
      LOBYTE(v33) = 0;
      _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(&hstringHeader);
    }
LABEL_6:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v23);
    goto LABEL_37;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x82,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\usermanagement.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)v23);
LABEL_37:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005c3c0  mov     [rsp-8+arg_0], rbx
0x18005c3c5  mov     [rsp-8+arg_18], rsi
0x18005c3ca  push    rbp
0x18005c3cb  push    rdi
0x18005c3cc  push    r14
0x18005c3ce  lea     rbp, [rsp-47h]
0x18005c3d3  sub     rsp, 90h
0x18005c3da  mov     rax, cs:__security_cookie
0x18005c3e1  xor     rax, rsp
0x18005c3e4  mov     [rbp+57h+var_18], rax
0x18005c3e8  mov     rdi, rdx
0x18005c3eb  mov     sil, cl
0x18005c3ee  mov     [rbp+57h+var_48], r8
0x18005c3f2  xor     r14d, r14d
0x18005c3f5  mov     [r8], r14d
0x18005c3f8  mov     [rbp+57h+var_58], r14
0x18005c3fc  mov     [rbp+57h+var_20], r14
0x18005c400  lea     r9d, [r14+23h]; unsigned int
0x18005c404  lea     r8d, [r14+24h]; unsigned int
0x18005c408  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18005c40f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005c413  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005c418  lea     r8, [rbp+57h+var_58]
0x18005c41c  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18005c423  mov     rcx, [rbp+57h+var_20]
0x18005c427  call    cs:__imp_RoGetActivationFactory
0x18005c42d  mov     ebx, eax
0x18005c42f  test    eax, eax
0x18005c431  jns     short loc_18005C450
0x18005c433  mov     rcx, [rbp+5Fh]; this
0x18005c437  mov     r9d, eax; char *
0x18005c43a  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c441  mov     edx, 82h; void *
0x18005c446  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c44b  jmp     loc_18005C96D
0x18005c450  mov     [rbp+57h+var_80], r14
0x18005c454  mov     rcx, [rbp+57h+var_58]
0x18005c458  mov     rax, [rcx]
0x18005c45b  lea     r8, [rbp+57h+var_80]
0x18005c45f  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18005c466  mov     rax, [rax]
0x18005c469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c46e  mov     ebx, eax
0x18005c470  test    eax, eax
0x18005c472  jns     short loc_18005C49B
0x18005c474  mov     edx, 84h; void *
0x18005c479  mov     rcx, [rbp+5Fh]; this
0x18005c47d  mov     r9d, eax; char *
0x18005c480  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c48c  nop
0x18005c48d  lea     rcx, [rbp+57h+var_80]
0x18005c491  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c496  jmp     loc_18005C96D
0x18005c49b  mov     rcx, [rbp+57h+var_58]
0x18005c49f  mov     rax, [rcx]
0x18005c4a2  test    rdi, rdi
0x18005c4a5  jnz     short loc_18005C4C1
0x18005c4a7  mov     rdx, [rbp+57h+var_48]
0x18005c4ab  mov     rax, [rax+30h]
0x18005c4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4b4  mov     ebx, eax
0x18005c4b6  test    eax, eax
0x18005c4b8  jns     short loc_18005C4DE
0x18005c4ba  mov     edx, 89h
0x18005c4bf  jmp     short loc_18005C479
0x18005c4c1  mov     r8, [rbp+57h+var_48]
0x18005c4c5  mov     rdx, rdi
0x18005c4c8  mov     rax, [rax+38h]
0x18005c4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4d1  mov     ebx, eax
0x18005c4d3  test    eax, eax
0x18005c4d5  jns     short loc_18005C4DE
0x18005c4d7  mov     edx, 8Dh
0x18005c4dc  jmp     short loc_18005C479
0x18005c4de  lea     rax, [rbp+57h+var_80]
0x18005c4e2  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18005c4e6  lea     rax, [rbp+57h+var_48]
0x18005c4ea  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x18005c4ee  lea     rax, [rbp+57h+var_58]
0x18005c4f2  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x18005c4f6  mov     byte ptr [rbp+57h+var_20], 1
0x18005c4fa  mov     [rbp+57h+var_78], r14
0x18005c4fe  mov     rcx, [rbp+57h+var_80]
0x18005c502  mov     rax, [rcx]
0x18005c505  mov     [rbp+57h+var_78], r14
0x18005c509  lea     r8, [rbp+57h+var_78]
0x18005c50d  mov     rdx, [rbp+57h+var_48]
0x18005c511  mov     edx, [rdx]
0x18005c513  mov     rax, [rax+40h]
0x18005c517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c51c  mov     ebx, eax
0x18005c51e  test    eax, eax
0x18005c520  jns     short loc_18005C558
0x18005c522  mov     rcx, [rbp+5Fh]; this
0x18005c526  mov     r9d, eax; char *
0x18005c529  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c530  mov     edx, 9Dh; void *
0x18005c535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c53a  nop
0x18005c53b  lea     rcx, [rbp+57h+var_78]
0x18005c53f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c544  nop
0x18005c545  mov     byte ptr [rbp+57h+var_20], r14b
0x18005c549  lea     rcx, [rbp+57h+hstringHeader]
0x18005c54d  call    ??R_lambda_678300044677cb06bfd46f1f1ec5ea84_@@QEBA@XZ; _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(void)
0x18005c552  nop
0x18005c553  jmp     loc_18005C48D
0x18005c558  mov     [rbp+57h+var_70], r14
0x18005c55c  mov     rcx, [rbp+57h+var_80]
0x18005c560  mov     rax, [rcx]
0x18005c563  mov     [rbp+57h+var_70], r14
0x18005c567  lea     r8, [rbp+57h+var_70]
0x18005c56b  mov     rdx, [rbp+57h+var_78]
0x18005c56f  mov     rax, [rax+38h]
0x18005c573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c578  mov     ebx, eax
0x18005c57a  test    eax, eax
0x18005c57c  jns     short loc_18005C5BE
0x18005c57e  mov     rcx, [rbp+5Fh]; this
0x18005c582  mov     r9d, eax; char *
0x18005c585  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c58c  mov     edx, 0A0h; void *
0x18005c591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c596  nop
0x18005c597  lea     rcx, [rbp+57h+var_70]
0x18005c59b  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c5a0  nop
0x18005c5a1  lea     rcx, [rbp+57h+var_78]
0x18005c5a5  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c5aa  nop
0x18005c5ab  mov     byte ptr [rbp+57h+var_20], r14b
0x18005c5af  lea     rcx, [rbp+57h+hstringHeader]
0x18005c5b3  call    ??R_lambda_678300044677cb06bfd46f1f1ec5ea84_@@QEBA@XZ; _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(void)
0x18005c5b8  nop
0x18005c5b9  jmp     loc_18005C48D
0x18005c5be  mov     [rbp+57h+var_68], r14
0x18005c5c2  mov     rdi, [rbp+57h+var_70]
0x18005c5c6  mov     rcx, rdi
0x18005c5c9  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SignInResult *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Internal::SignInResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18005c5ce  mov     ebx, eax
0x18005c5d0  test    eax, eax
0x18005c5d2  js      short loc_18005C5E9
0x18005c5d4  mov     rax, [rdi]
0x18005c5d7  lea     rdx, [rbp+57h+var_68]
0x18005c5db  mov     rcx, rdi
0x18005c5de  mov     rax, [rax+40h]
0x18005c5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5e7  mov     ebx, eax
0x18005c5e9  test    ebx, ebx
0x18005c5eb  jns     short loc_18005C637
0x18005c5ed  mov     rcx, [rbp+5Fh]; this
0x18005c5f1  mov     r9d, ebx; char *
0x18005c5f4  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c5fb  mov     edx, 0A2h; void *
0x18005c600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c605  nop
0x18005c606  lea     rcx, [rbp+57h+var_68]
0x18005c60a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c60f  nop
0x18005c610  lea     rcx, [rbp+57h+var_70]
0x18005c614  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c619  nop
0x18005c61a  lea     rcx, [rbp+57h+var_78]
0x18005c61e  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c623  nop
0x18005c624  mov     byte ptr [rbp+57h+var_20], r14b
0x18005c628  lea     rcx, [rbp+57h+hstringHeader]
0x18005c62c  call    ??R_lambda_678300044677cb06bfd46f1f1ec5ea84_@@QEBA@XZ; _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(void)
0x18005c631  nop
0x18005c632  jmp     loc_18005C48D
0x18005c637  mov     dword ptr [rbp+57h+var_50], r14d
0x18005c63b  mov     rcx, [rbp+57h+var_68]
0x18005c63f  mov     rax, [rcx]
0x18005c642  lea     rdx, [rbp+57h+var_50]
0x18005c646  mov     rax, [rax+40h]
0x18005c64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c64f  mov     ebx, eax
0x18005c651  test    eax, eax
0x18005c653  jns     short loc_18005C69F
0x18005c655  mov     rcx, [rbp+5Fh]; this
0x18005c659  mov     r9d, eax; char *
0x18005c65c  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c663  mov     edx, 0A6h; void *
0x18005c668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c66d  nop
0x18005c66e  lea     rcx, [rbp+57h+var_68]
0x18005c672  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c677  nop
0x18005c678  lea     rcx, [rbp+57h+var_70]
0x18005c67c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c681  nop
0x18005c682  lea     rcx, [rbp+57h+var_78]
0x18005c686  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c68b  nop
0x18005c68c  mov     byte ptr [rbp+57h+var_20], r14b
0x18005c690  lea     rcx, [rbp+57h+hstringHeader]
0x18005c694  call    ??R_lambda_678300044677cb06bfd46f1f1ec5ea84_@@QEBA@XZ; _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(void)
0x18005c699  nop
0x18005c69a  jmp     loc_18005C48D
0x18005c69f  mov     ebx, dword ptr [rbp+57h+var_50]
0x18005c6a2  test    ebx, ebx
0x18005c6a4  jns     short loc_18005C6F0
0x18005c6a6  mov     rcx, [rbp+5Fh]; this
0x18005c6aa  mov     r9d, ebx; char *
0x18005c6ad  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c6b4  mov     edx, 0A7h; void *
0x18005c6b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c6be  nop
0x18005c6bf  lea     rcx, [rbp+57h+var_68]
0x18005c6c3  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c6c8  nop
0x18005c6c9  lea     rcx, [rbp+57h+var_70]
0x18005c6cd  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c6d2  nop
0x18005c6d3  lea     rcx, [rbp+57h+var_78]
0x18005c6d7  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c6dc  nop
0x18005c6dd  mov     byte ptr [rbp+57h+var_20], r14b
0x18005c6e1  lea     rcx, [rbp+57h+hstringHeader]
0x18005c6e5  call    ??R_lambda_678300044677cb06bfd46f1f1ec5ea84_@@QEBA@XZ; _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(void)
0x18005c6ea  nop
0x18005c6eb  jmp     loc_18005C48D
0x18005c6f0  mov     rdx, [rbp+57h+var_78]; struct Windows::System::Internal::ISignInContext *
0x18005c6f4  mov     rcx, [rbp+57h+var_68]; struct Windows::System::Internal::ISignInResult *
0x18005c6f8  call    ?AddCredentialsToSignInContext@UserManagementStatics@CloudExperienceHostAPI@@CAJPEAUISignInResult@Internal@System@Windows@@PEAUISignInContext@456@@Z; CloudExperienceHostAPI::UserManagementStatics::AddCredentialsToSignInContext(Windows::System::Internal::ISignInResult *,Windows::System::Internal::ISignInContext *)
0x18005c6fd  mov     ebx, eax
0x18005c6ff  test    eax, eax
0x18005c701  jns     short loc_18005C74D
0x18005c703  mov     rcx, [rbp+5Fh]; this
0x18005c707  mov     r9d, eax; char *
0x18005c70a  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c711  mov     edx, 0AAh; void *
0x18005c716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c71b  nop
0x18005c71c  lea     rcx, [rbp+57h+var_68]
0x18005c720  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c725  nop
0x18005c726  lea     rcx, [rbp+57h+var_70]
0x18005c72a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c72f  nop
0x18005c730  lea     rcx, [rbp+57h+var_78]
0x18005c734  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c739  nop
0x18005c73a  mov     byte ptr [rbp+57h+var_20], r14b
0x18005c73e  lea     rcx, [rbp+57h+hstringHeader]
0x18005c742  call    ??R_lambda_678300044677cb06bfd46f1f1ec5ea84_@@QEBA@XZ; _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(void)
0x18005c747  nop
0x18005c748  jmp     loc_18005C48D
0x18005c74d  mov     [rbp+57h+var_60], r14
0x18005c751  mov     rcx, [rbp+57h+var_80]
0x18005c755  mov     rax, [rcx]
0x18005c758  mov     [rbp+57h+var_60], r14
0x18005c75c  lea     r8, [rbp+57h+var_60]
0x18005c760  mov     rdx, [rbp+57h+var_78]
0x18005c764  mov     rax, [rax+0C0h]
0x18005c76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c770  mov     ebx, eax
0x18005c772  test    eax, eax
0x18005c774  jns     short loc_18005C7CA
0x18005c776  mov     rcx, [rbp+5Fh]; this
0x18005c77a  mov     r9d, eax; char *
0x18005c77d  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c784  mov     edx, 0ADh; void *
0x18005c789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c78e  nop
0x18005c78f  lea     rcx, [rbp+57h+var_60]
0x18005c793  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c798  nop
0x18005c799  lea     rcx, [rbp+57h+var_68]
0x18005c79d  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c7a2  nop
0x18005c7a3  lea     rcx, [rbp+57h+var_70]
0x18005c7a7  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c7ac  nop
0x18005c7ad  lea     rcx, [rbp+57h+var_78]
0x18005c7b1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c7b6  nop
0x18005c7b7  mov     byte ptr [rbp+57h+var_20], r14b
0x18005c7bb  lea     rcx, [rbp+57h+hstringHeader]
0x18005c7bf  call    ??R_lambda_678300044677cb06bfd46f1f1ec5ea84_@@QEBA@XZ; _lambda_678300044677cb06bfd46f1f1ec5ea84_::operator()(void)
0x18005c7c4  nop
0x18005c7c5  jmp     loc_18005C48D
0x18005c7ca  mov     rcx, [rbp+57h+var_60]
0x18005c7ce  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x18005c7d3  mov     ebx, eax
0x18005c7d5  test    eax, eax
0x18005c7d7  jns     short loc_18005C82D
0x18005c7d9  mov     rcx, [rbp+5Fh]; this
0x18005c7dd  mov     r9d, eax; char *
0x18005c7e0  lea     r8, aShellcommonShe; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005c7e7  mov     edx, 0AEh; void *
0x18005c7ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c7f1  nop
0x18005c7f2  lea     rcx, [rbp+57h+var_60]
0x18005c7f6  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c7fb  nop
0x18005c7fc  lea     rcx, [rbp+57h+var_68]
0x18005c800  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18005c805  nop
  ... truncated ...
```
