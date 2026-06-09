# CLogonTaskFramework::s_HydrateDevHomeStub(void)

- ea: `0x1401a9d80`
- end: `0x1401aa689`
- name: `?s_HydrateDevHomeStub@CLogonTaskFramework@@CAJXZ`
- size: `2313`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1401ac490`

## callees

- `0x140005aa8`
- `0x140082820`
- `0x14009ac68`
- `0x14010e160`
- `0x14010ed6c`
- `0x14013ec58`
- `0x140145854`
- `0x1401a9d80`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1401a9de4`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1401a9de4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401aa198`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401aa198`

## string_xrefs

- `0x1401a9e57`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9ece`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9f56`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9fa4`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa031`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa099`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa10d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa1b5`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa240`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa2d7`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa381`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa43d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa4f2`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa173`: `Windows.Services.Store.StoreContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 CLogonTaskFramework::s_HydrateDevHomeStub(void)
{
  int v0; // ebx
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64); // rbx
  int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, int *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 (__fastcall **v15)(_QWORD *, GUID *, __int64 *); // rax
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  int ActivationFactory; // eax
  unsigned int v21; // ebx
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rdi
  int updated; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  int v34[2]; // [rsp+20h] [rbp-88h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, int *); // [rsp+28h] [rbp-80h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, int *); // [rsp+30h] [rbp-78h] BYREF
  __int64 v37; // [rsp+38h] [rbp-70h] BYREF
  __int64 v38; // [rsp+40h] [rbp-68h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 **); // [rsp+48h] [rbp-60h] BYREF
  __int64 *v40; // [rsp+50h] [rbp-58h] BYREF
  int v41; // [rsp+58h] [rbp-50h] BYREF
  __int64 v42; // [rsp+60h] [rbp-48h] BYREF
  __int64 *v43; // [rsp+68h] [rbp-40h] BYREF
  __int64 v44; // [rsp+70h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-30h] BYREF
  __int64 v46; // [rsp+90h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *(_QWORD *)v34 = 0;
  v46 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.PackageManager",
    0x2Du,
    0x2Cu);
  v35 = 0;
  v36 = 0;
  v0 = RoActivateInstance(v46, &v36);
  if ( v0 >= 0 )
  {
    if ( !memcmp_0(&GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v35 = v36;
    }
    else
    {
      v0 = (**v36)(v36, &GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53, (int *)&v35);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, int *)))(*v36)[2])(v36);
    }
  }
  if ( v0 >= 0 )
  {
    *(_QWORD *)v34 = 0;
    v2 = (**v35)(v35, &GUID_1aa79035_cc71_4b2e_80a6_c7041d8579a7, v34);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v4 = *(_QWORD *)v34;
      v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)v34 + 88LL);
      v46 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Microsoft.Windows.DevHome_8wekyb3d8bbwe",
        0x28u,
        0x27u);
      v6 = v5(v4, v46, 1);
      v8 = v6;
      if ( v6 >= 0 )
      {
        v36 = 0;
        v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
               v7,
               &v36);
        v10 = v9;
        if ( v9 >= 0 )
        {
          v11 = v36;
          v12 = (*v36)[13];
          v46 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"9N8MHTPHNGVV", 0xDu, 0xCu);
          v13 = ((__int64 (__fastcall *)(_QWORD *, __int64))v12)(v11, v46);
          v14 = v13;
          if ( v13 >= 0 )
          {
            v37 = 0;
            v15 = (__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v11;
            v37 = 0;
            v16 = ((__int64 (__fastcall *)(_QWORD *, __int64 *))v15[8])(v11, &v37);
            v17 = v16;
            if ( v16 >= 0 )
            {
              v38 = 0;
              v18 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v11)(
                      v11,
                      &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e,
                      &v38);
              v19 = v18;
              if ( v18 >= 0 )
              {
                v40 = 0;
                v46 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  &hstringHeader,
                  L"Windows.Services.Store.StoreContext",
                  0x24u,
                  0x23u);
                ActivationFactory = RoGetActivationFactory(v46, &GUID_9c06ee5f_15c0_4e72_9330_d6191cebd19c, &v40);
                v21 = ActivationFactory;
                if ( ActivationFactory >= 0 )
                {
                  v39 = 0;
                  v22 = *v40;
                  v39 = 0;
                  v23 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)))(v22 + 48))(
                          v40,
                          &v39);
                  v24 = v23;
                  if ( v23 >= 0 )
                  {
                    v43 = 0;
                    v25 = (**v39)(v39, &GUID_e26226ca_1a01_4730_85a6_ecc896e4ae38, &v43);
                    v26 = v25;
                    if ( v25 >= 0 )
                    {
                      v42 = 0;
                      v27 = *v43;
                      v42 = 0;
                      v28 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v27 + 120))(v43, v38, &v42);
                      v29 = v28;
                      if ( v28 >= 0 )
                      {
                        v44 = 0;
                        v30 = v42;
                        updated = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Services::Store::StorePackageUpdateResult *,Windows::Services::Store::StorePackageUpdateStatus> *>(v42);
                        if ( updated >= 0 )
                          updated = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 80LL))(v30, &v44);
                        if ( updated >= 0 )
                        {
                          v41 = 0;
                          v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 48LL))(v44, &v41);
                          v33 = v32;
                          if ( v32 >= 0 )
                          {
                            if ( v41 == 3 )
                            {
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v44);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v42);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v43);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                              return 0;
                            }
                            else
                            {
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v44);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v42);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v43);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                              return 2150040148LL;
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x1AD2,
                              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                              (const char *)(unsigned int)v32,
                              v34[0]);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v44);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v42);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v43);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                            return v33;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x1ACF,
                            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                            (const char *)(unsigned int)updated,
                            v34[0]);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v44);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v42);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v43);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                          return (unsigned int)updated;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x1ACC,
                          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                          (const char *)(unsigned int)v28,
                          v34[0]);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v42);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v43);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                        return v29;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x1AC9,
                        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                        (const char *)(unsigned int)v25,
                        v34[0]);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v43);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                      return v26;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1AC6,
                      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                      (const char *)(unsigned int)v23,
                      v34[0]);
                    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
                    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                    return v24;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1AC3,
                    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                    (const char *)(unsigned int)ActivationFactory,
                    v34[0]);
                  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
                  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                  return v21;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1ABF,
                  (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                  (const char *)(unsigned int)v18,
                  v34[0]);
                wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v38);
                wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
                wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
                wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
                wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
                return v19;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1ABD,
                (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                (const char *)(unsigned int)v16,
                v34[0]);
              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v37);
              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
              wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
              return v17;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1ABB,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v13,
              v34[0]);
            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
            wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
            return v14;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AB8,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v9,
            v34[0]);
          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v36);
          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
          return v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AB5,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v6,
          v34[0]);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
        return v8;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB3,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v2,
        v34[0]);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
      return v3;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AB2,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v0,
      v34[0]);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v34);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v35);
    return (unsigned int)v0;
  }
}

```

## disassembly

```asm
0x1401a9d80  mov     r11, rsp
0x1401a9d83  mov     [r11+8], rbx
0x1401a9d87  mov     [r11+10h], rsi
0x1401a9d8b  push    rdi
0x1401a9d8c  sub     rsp, 0A0h
0x1401a9d93  mov     rax, cs:__security_cookie
0x1401a9d9a  xor     rax, rsp
0x1401a9d9d  mov     [rsp+0A8h+var_10], rax
0x1401a9da5  xor     esi, esi
0x1401a9da7  mov     qword ptr [rsp+0A8h+var_88], rsi; int
0x1401a9dac  mov     [r11-80h], rsi
0x1401a9db0  mov     [r11-18h], rsi
0x1401a9db4  lea     r9d, [rsi+2Ch]; unsigned int
0x1401a9db8  lea     r8d, [rsi+2Dh]; unsigned int
0x1401a9dbc  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1401a9dc3  lea     rcx, [r11-30h]; hstringHeader
0x1401a9dc7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401a9dcc  nop
0x1401a9dcd  mov     [rsp+0A8h+var_80], rsi
0x1401a9dd2  mov     [rsp+0A8h+var_78], rsi
0x1401a9dd7  lea     rdx, [rsp+0A8h+var_78]
0x1401a9ddc  mov     rcx, [rsp+0A8h+var_18]
0x1401a9de4  call    cs:__imp_RoActivateInstance
0x1401a9deb  nop     dword ptr [rax+rax+00h]
0x1401a9df0  mov     ebx, eax
0x1401a9df2  test    eax, eax
0x1401a9df4  js      short loc_1401A9E48
0x1401a9df6  lea     r8d, [rsi+10h]; Size
0x1401a9dfa  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1401a9e01  lea     rcx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53; Buf1
0x1401a9e08  call    memcmp_0
0x1401a9e0d  mov     rcx, [rsp+0A8h+var_78]
0x1401a9e12  test    eax, eax
0x1401a9e14  jnz     short loc_1401A9E1D
0x1401a9e16  mov     [rsp+0A8h+var_80], rcx
0x1401a9e1b  jmp     short loc_1401A9E48
0x1401a9e1d  mov     rax, [rcx]
0x1401a9e20  lea     r8, [rsp+0A8h+var_80]
0x1401a9e25  lea     rdx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53
0x1401a9e2c  mov     rax, [rax]
0x1401a9e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9e34  mov     ebx, eax
0x1401a9e36  mov     rcx, [rsp+0A8h+var_78]
0x1401a9e3b  mov     rax, [rcx]
0x1401a9e3e  mov     rax, [rax+10h]
0x1401a9e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9e47  nop
0x1401a9e48  test    ebx, ebx
0x1401a9e4a  jns     short loc_1401A9E85
0x1401a9e4c  mov     rcx, [rsp+0A8h]; this
0x1401a9e54  mov     r9d, ebx; char *
0x1401a9e57  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9e5e  mov     edx, 1AB2h; void *
0x1401a9e63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9e68  nop
0x1401a9e69  lea     rcx, [rsp+0A8h+var_88]
0x1401a9e6e  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9e73  nop
0x1401a9e74  lea     rcx, [rsp+0A8h+var_80]
0x1401a9e79  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9e7e  mov     eax, ebx
0x1401a9e80  jmp     loc_1401AA663
0x1401a9e85  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x1401a9e8a  mov     qword ptr [rsp+0A8h+var_88], rsi; int
0x1401a9e8f  test    rcx, rcx
0x1401a9e92  jz      short loc_1401A9EA1
0x1401a9e94  mov     rax, [rcx]
0x1401a9e97  mov     rax, [rax+10h]
0x1401a9e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9ea0  nop
0x1401a9ea1  mov     rcx, [rsp+0A8h+var_80]
0x1401a9ea6  mov     rax, [rcx]
0x1401a9ea9  lea     r8, [rsp+0A8h+var_88]
0x1401a9eae  lea     rdx, _GUID_1aa79035_cc71_4b2e_80a6_c7041d8579a7
0x1401a9eb5  mov     rax, [rax]
0x1401a9eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9ebd  mov     ebx, eax
0x1401a9ebf  test    eax, eax
0x1401a9ec1  jns     short loc_1401A9EFC
0x1401a9ec3  mov     rcx, [rsp+0A8h]; this
0x1401a9ecb  mov     r9d, eax; char *
0x1401a9ece  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9ed5  mov     edx, 1AB3h; void *
0x1401a9eda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9edf  nop
0x1401a9ee0  lea     rcx, [rsp+0A8h+var_88]
0x1401a9ee5  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9eea  nop
0x1401a9eeb  lea     rcx, [rsp+0A8h+var_80]
0x1401a9ef0  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9ef5  mov     eax, ebx
0x1401a9ef7  jmp     loc_1401AA663
0x1401a9efc  mov     rdi, qword ptr [rsp+0A8h+var_88]
0x1401a9f01  mov     rax, [rdi]
0x1401a9f04  mov     rbx, [rax+58h]
0x1401a9f08  mov     [rsp+0A8h+var_18], rsi
0x1401a9f10  mov     r9d, 27h ; '''; unsigned int
0x1401a9f16  lea     r8d, [r9+1]; unsigned int
0x1401a9f1a  lea     rdx, packageFamilyName; "Microsoft.Windows.DevHome_8wekyb3d8bbwe"
0x1401a9f21  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1401a9f26  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401a9f2b  nop
0x1401a9f2c  mov     r8d, 1
0x1401a9f32  mov     rdx, [rsp+0A8h+var_18]
0x1401a9f3a  mov     rcx, rdi
0x1401a9f3d  mov     rax, rbx
0x1401a9f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9f45  mov     ebx, eax
0x1401a9f47  test    eax, eax
0x1401a9f49  jns     short loc_1401A9F84
0x1401a9f4b  mov     rcx, [rsp+0A8h]; this
0x1401a9f53  mov     r9d, eax; char *
0x1401a9f56  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9f5d  mov     edx, 1AB5h; void *
0x1401a9f62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9f67  nop
0x1401a9f68  lea     rcx, [rsp+0A8h+var_88]
0x1401a9f6d  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9f72  nop
0x1401a9f73  lea     rcx, [rsp+0A8h+var_80]
0x1401a9f78  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9f7d  mov     eax, ebx
0x1401a9f7f  jmp     loc_1401AA663
0x1401a9f84  mov     [rsp+0A8h+var_78], rsi
0x1401a9f89  lea     rdx, [rsp+0A8h+var_78]
0x1401a9f8e  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1401a9f93  mov     ebx, eax
0x1401a9f95  test    eax, eax
0x1401a9f97  jns     short loc_1401A9FDD
0x1401a9f99  mov     rcx, [rsp+0A8h]; this
0x1401a9fa1  mov     r9d, eax; char *
0x1401a9fa4  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9fab  mov     edx, 1AB8h; void *
0x1401a9fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9fb5  nop
0x1401a9fb6  lea     rcx, [rsp+0A8h+var_78]
0x1401a9fbb  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9fc0  nop
0x1401a9fc1  lea     rcx, [rsp+0A8h+var_88]
0x1401a9fc6  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9fcb  nop
0x1401a9fcc  lea     rcx, [rsp+0A8h+var_80]
0x1401a9fd1  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9fd6  mov     eax, ebx
0x1401a9fd8  jmp     loc_1401AA663
0x1401a9fdd  mov     rdi, [rsp+0A8h+var_78]
0x1401a9fe2  mov     rax, [rdi]
0x1401a9fe5  mov     rbx, [rax+68h]
0x1401a9fe9  mov     [rsp+0A8h+var_18], rsi
0x1401a9ff1  mov     r9d, 0Ch; unsigned int
0x1401a9ff7  lea     r8d, [r9+1]; unsigned int
0x1401a9ffb  lea     rdx, a9n8mhtphngvv; "9N8MHTPHNGVV"
0x1401aa002  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1401aa007  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401aa00c  nop
0x1401aa00d  mov     rdx, [rsp+0A8h+var_18]
0x1401aa015  mov     rcx, rdi
0x1401aa018  mov     rax, rbx
0x1401aa01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401aa020  mov     ebx, eax
0x1401aa022  test    eax, eax
0x1401aa024  jns     short loc_1401AA06A
0x1401aa026  mov     rcx, [rsp+0A8h]; this
0x1401aa02e  mov     r9d, eax; char *
0x1401aa031  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401aa038  mov     edx, 1ABBh; void *
0x1401aa03d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aa042  nop
0x1401aa043  lea     rcx, [rsp+0A8h+var_78]
0x1401aa048  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa04d  nop
0x1401aa04e  lea     rcx, [rsp+0A8h+var_88]
0x1401aa053  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa058  nop
0x1401aa059  lea     rcx, [rsp+0A8h+var_80]
0x1401aa05e  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa063  mov     eax, ebx
0x1401aa065  jmp     loc_1401AA663
0x1401aa06a  mov     [rsp+0A8h+var_70], rsi
0x1401aa06f  mov     rax, [rdi]
0x1401aa072  mov     [rsp+0A8h+var_70], rsi
0x1401aa077  lea     rdx, [rsp+0A8h+var_70]
0x1401aa07c  mov     rcx, rdi
0x1401aa07f  mov     rax, [rax+40h]
0x1401aa083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401aa088  mov     ebx, eax
0x1401aa08a  test    eax, eax
0x1401aa08c  jns     short loc_1401AA0DD
0x1401aa08e  mov     rcx, [rsp+0A8h]; this
0x1401aa096  mov     r9d, eax; char *
0x1401aa099  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401aa0a0  mov     edx, 1ABDh; void *
0x1401aa0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aa0aa  nop
0x1401aa0ab  lea     rcx, [rsp+0A8h+var_70]
0x1401aa0b0  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa0b5  nop
0x1401aa0b6  lea     rcx, [rsp+0A8h+var_78]
0x1401aa0bb  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa0c0  nop
0x1401aa0c1  lea     rcx, [rsp+0A8h+var_88]
0x1401aa0c6  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa0cb  nop
0x1401aa0cc  lea     rcx, [rsp+0A8h+var_80]
0x1401aa0d1  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa0d6  mov     eax, ebx
0x1401aa0d8  jmp     loc_1401AA663
0x1401aa0dd  mov     [rsp+0A8h+var_68], rsi
0x1401aa0e2  mov     rax, [rdi]
0x1401aa0e5  lea     r8, [rsp+0A8h+var_68]
0x1401aa0ea  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x1401aa0f1  mov     rcx, rdi
0x1401aa0f4  mov     rax, [rax]
0x1401aa0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401aa0fc  mov     ebx, eax
0x1401aa0fe  test    eax, eax
0x1401aa100  jns     short loc_1401AA15C
0x1401aa102  mov     rcx, [rsp+0A8h]; this
0x1401aa10a  mov     r9d, eax; char *
0x1401aa10d  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401aa114  mov     edx, 1ABFh; void *
0x1401aa119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aa11e  nop
0x1401aa11f  lea     rcx, [rsp+0A8h+var_68]
0x1401aa124  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa129  nop
0x1401aa12a  lea     rcx, [rsp+0A8h+var_70]
0x1401aa12f  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa134  nop
0x1401aa135  lea     rcx, [rsp+0A8h+var_78]
0x1401aa13a  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa13f  nop
0x1401aa140  lea     rcx, [rsp+0A8h+var_88]
0x1401aa145  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa14a  nop
0x1401aa14b  lea     rcx, [rsp+0A8h+var_80]
0x1401aa150  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa155  mov     eax, ebx
0x1401aa157  jmp     loc_1401AA663
0x1401aa15c  mov     [rsp+0A8h+var_58], rsi
0x1401aa161  mov     [rsp+0A8h+var_18], rsi
0x1401aa169  mov     r9d, 23h ; '#'; unsigned int
0x1401aa16f  lea     r8d, [r9+1]; unsigned int
0x1401aa173  lea     rdx, ?RuntimeClass_Windows_Services_Store_StoreContext@@3QBGB; "Windows.Services.Store.StoreContext"
0x1401aa17a  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1401aa17f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401aa184  lea     r8, [rsp+0A8h+var_58]
0x1401aa189  lea     rdx, _GUID_9c06ee5f_15c0_4e72_9330_d6191cebd19c
0x1401aa190  mov     rcx, [rsp+0A8h+var_18]
0x1401aa198  call    cs:__imp_RoGetActivationFactory
0x1401aa19f  nop     dword ptr [rax+rax+00h]
0x1401aa1a4  mov     ebx, eax
0x1401aa1a6  test    eax, eax
0x1401aa1a8  jns     short loc_1401AA20F
0x1401aa1aa  mov     rcx, [rsp+0A8h]; this
0x1401aa1b2  mov     r9d, eax; char *
0x1401aa1b5  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401aa1bc  mov     edx, 1AC3h; void *
0x1401aa1c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aa1c6  nop
0x1401aa1c7  lea     rcx, [rsp+0A8h+var_58]
0x1401aa1cc  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa1d1  nop
0x1401aa1d2  lea     rcx, [rsp+0A8h+var_68]
0x1401aa1d7  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa1dc  nop
0x1401aa1dd  lea     rcx, [rsp+0A8h+var_70]
0x1401aa1e2  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa1e7  nop
0x1401aa1e8  lea     rcx, [rsp+0A8h+var_78]
0x1401aa1ed  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa1f2  nop
0x1401aa1f3  lea     rcx, [rsp+0A8h+var_88]
0x1401aa1f8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa1fd  nop
0x1401aa1fe  lea     rcx, [rsp+0A8h+var_80]
0x1401aa203  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa208  mov     eax, ebx
0x1401aa20a  jmp     loc_1401AA663
0x1401aa20f  mov     [rsp+0A8h+var_60], rsi
0x1401aa214  mov     rcx, [rsp+0A8h+var_58]
0x1401aa219  mov     rax, [rcx]
0x1401aa21c  mov     [rsp+0A8h+var_60], rsi
0x1401aa221  lea     rdx, [rsp+0A8h+var_60]
0x1401aa226  mov     rax, [rax+30h]
0x1401aa22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401aa22f  mov     ebx, eax
0x1401aa231  test    eax, eax
0x1401aa233  jns     short loc_1401AA2A5
0x1401aa235  mov     rcx, [rsp+0A8h]; this
0x1401aa23d  mov     r9d, eax; char *
0x1401aa240  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401aa247  mov     edx, 1AC6h; void *
0x1401aa24c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aa251  nop
0x1401aa252  lea     rcx, [rsp+0A8h+var_60]
0x1401aa257  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa25c  nop
0x1401aa25d  lea     rcx, [rsp+0A8h+var_58]
0x1401aa262  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
  ... truncated ...
```
