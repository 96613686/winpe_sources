# CLogonTaskFramework::s_HydrateDevHomeStub(void)

- ea: `0x1401a9b88`
- end: `0x1401aa485`
- name: `?s_HydrateDevHomeStub@CLogonTaskFramework@@CAJXZ`
- size: `2301`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1401ac1b4`

## callees

- `0x14002f838`
- `0x14007ce08`
- `0x1400954e0`
- `0x1401040e0`
- `0x140104cbc`
- `0x140132c88`
- `0x140139618`
- `0x1401a9b88`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1401a9bec`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1401a9bec`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401a9f9a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1401a9f9a`

## string_xrefs

- `0x1401a9c59`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9cd0`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9d58`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9da6`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9e33`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9e9b`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9f0f`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9fb1`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa03c`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa0d3`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa17d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa239`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aa2ee`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401a9f75`: `Windows.Services.Store.StoreContext`

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
                              (void *)0x1AD9,
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
                            (void *)0x1AD6,
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
                          (void *)0x1AD3,
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
                        (void *)0x1AD0,
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
                      (void *)0x1ACD,
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
                    (void *)0x1ACA,
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
                  (void *)0x1AC6,
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
                (void *)0x1AC4,
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
              (void *)0x1AC2,
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
            (void *)0x1ABF,
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
          (void *)0x1ABC,
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
        (void *)0x1ABA,
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
      (void *)0x1AB9,
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
0x1401a9b88  mov     r11, rsp
0x1401a9b8b  mov     [r11+8], rbx
0x1401a9b8f  mov     [r11+10h], rsi
0x1401a9b93  push    rdi
0x1401a9b94  sub     rsp, 0A0h
0x1401a9b9b  mov     rax, cs:__security_cookie
0x1401a9ba2  xor     rax, rsp
0x1401a9ba5  mov     [rsp+0A8h+var_10], rax
0x1401a9bad  xor     esi, esi
0x1401a9baf  mov     qword ptr [rsp+0A8h+var_88], rsi; int
0x1401a9bb4  mov     [r11-80h], rsi
0x1401a9bb8  mov     [r11-18h], rsi
0x1401a9bbc  lea     r9d, [rsi+2Ch]; unsigned int
0x1401a9bc0  lea     r8d, [rsi+2Dh]; unsigned int
0x1401a9bc4  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1401a9bcb  lea     rcx, [r11-30h]; hstringHeader
0x1401a9bcf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401a9bd4  nop
0x1401a9bd5  mov     [rsp+0A8h+var_80], rsi
0x1401a9bda  mov     [rsp+0A8h+var_78], rsi
0x1401a9bdf  lea     rdx, [rsp+0A8h+var_78]
0x1401a9be4  mov     rcx, [rsp+0A8h+var_18]
0x1401a9bec  call    cs:__imp_RoActivateInstance
0x1401a9bf2  mov     ebx, eax
0x1401a9bf4  test    eax, eax
0x1401a9bf6  js      short loc_1401A9C4A
0x1401a9bf8  lea     r8d, [rsi+10h]; Size
0x1401a9bfc  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1401a9c03  lea     rcx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53; Buf1
0x1401a9c0a  call    memcmp_0
0x1401a9c0f  mov     rcx, [rsp+0A8h+var_78]
0x1401a9c14  test    eax, eax
0x1401a9c16  jnz     short loc_1401A9C1F
0x1401a9c18  mov     [rsp+0A8h+var_80], rcx
0x1401a9c1d  jmp     short loc_1401A9C4A
0x1401a9c1f  mov     rax, [rcx]
0x1401a9c22  lea     r8, [rsp+0A8h+var_80]
0x1401a9c27  lea     rdx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53
0x1401a9c2e  mov     rax, [rax]
0x1401a9c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9c36  mov     ebx, eax
0x1401a9c38  mov     rcx, [rsp+0A8h+var_78]
0x1401a9c3d  mov     rax, [rcx]
0x1401a9c40  mov     rax, [rax+10h]
0x1401a9c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9c49  nop
0x1401a9c4a  test    ebx, ebx
0x1401a9c4c  jns     short loc_1401A9C87
0x1401a9c4e  mov     rcx, [rsp+0A8h]; this
0x1401a9c56  mov     r9d, ebx; char *
0x1401a9c59  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9c60  mov     edx, 1AB9h; void *
0x1401a9c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9c6a  nop
0x1401a9c6b  lea     rcx, [rsp+0A8h+var_88]
0x1401a9c70  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9c75  nop
0x1401a9c76  lea     rcx, [rsp+0A8h+var_80]
0x1401a9c7b  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9c80  mov     eax, ebx
0x1401a9c82  jmp     loc_1401AA45F
0x1401a9c87  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x1401a9c8c  mov     qword ptr [rsp+0A8h+var_88], rsi; int
0x1401a9c91  test    rcx, rcx
0x1401a9c94  jz      short loc_1401A9CA3
0x1401a9c96  mov     rax, [rcx]
0x1401a9c99  mov     rax, [rax+10h]
0x1401a9c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9ca2  nop
0x1401a9ca3  mov     rcx, [rsp+0A8h+var_80]
0x1401a9ca8  mov     rax, [rcx]
0x1401a9cab  lea     r8, [rsp+0A8h+var_88]
0x1401a9cb0  lea     rdx, _GUID_1aa79035_cc71_4b2e_80a6_c7041d8579a7
0x1401a9cb7  mov     rax, [rax]
0x1401a9cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9cbf  mov     ebx, eax
0x1401a9cc1  test    eax, eax
0x1401a9cc3  jns     short loc_1401A9CFE
0x1401a9cc5  mov     rcx, [rsp+0A8h]; this
0x1401a9ccd  mov     r9d, eax; char *
0x1401a9cd0  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9cd7  mov     edx, 1ABAh; void *
0x1401a9cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9ce1  nop
0x1401a9ce2  lea     rcx, [rsp+0A8h+var_88]
0x1401a9ce7  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9cec  nop
0x1401a9ced  lea     rcx, [rsp+0A8h+var_80]
0x1401a9cf2  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9cf7  mov     eax, ebx
0x1401a9cf9  jmp     loc_1401AA45F
0x1401a9cfe  mov     rdi, qword ptr [rsp+0A8h+var_88]
0x1401a9d03  mov     rax, [rdi]
0x1401a9d06  mov     rbx, [rax+58h]
0x1401a9d0a  mov     [rsp+0A8h+var_18], rsi
0x1401a9d12  mov     r9d, 27h ; '''; unsigned int
0x1401a9d18  lea     r8d, [r9+1]; unsigned int
0x1401a9d1c  lea     rdx, packageFamilyName; "Microsoft.Windows.DevHome_8wekyb3d8bbwe"
0x1401a9d23  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1401a9d28  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401a9d2d  nop
0x1401a9d2e  mov     r8d, 1
0x1401a9d34  mov     rdx, [rsp+0A8h+var_18]
0x1401a9d3c  mov     rcx, rdi
0x1401a9d3f  mov     rax, rbx
0x1401a9d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9d47  mov     ebx, eax
0x1401a9d49  test    eax, eax
0x1401a9d4b  jns     short loc_1401A9D86
0x1401a9d4d  mov     rcx, [rsp+0A8h]; this
0x1401a9d55  mov     r9d, eax; char *
0x1401a9d58  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9d5f  mov     edx, 1ABCh; void *
0x1401a9d64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9d69  nop
0x1401a9d6a  lea     rcx, [rsp+0A8h+var_88]
0x1401a9d6f  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9d74  nop
0x1401a9d75  lea     rcx, [rsp+0A8h+var_80]
0x1401a9d7a  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9d7f  mov     eax, ebx
0x1401a9d81  jmp     loc_1401AA45F
0x1401a9d86  mov     [rsp+0A8h+var_78], rsi
0x1401a9d8b  lea     rdx, [rsp+0A8h+var_78]
0x1401a9d90  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1401a9d95  mov     ebx, eax
0x1401a9d97  test    eax, eax
0x1401a9d99  jns     short loc_1401A9DDF
0x1401a9d9b  mov     rcx, [rsp+0A8h]; this
0x1401a9da3  mov     r9d, eax; char *
0x1401a9da6  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9dad  mov     edx, 1ABFh; void *
0x1401a9db2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9db7  nop
0x1401a9db8  lea     rcx, [rsp+0A8h+var_78]
0x1401a9dbd  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9dc2  nop
0x1401a9dc3  lea     rcx, [rsp+0A8h+var_88]
0x1401a9dc8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9dcd  nop
0x1401a9dce  lea     rcx, [rsp+0A8h+var_80]
0x1401a9dd3  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9dd8  mov     eax, ebx
0x1401a9dda  jmp     loc_1401AA45F
0x1401a9ddf  mov     rdi, [rsp+0A8h+var_78]
0x1401a9de4  mov     rax, [rdi]
0x1401a9de7  mov     rbx, [rax+68h]
0x1401a9deb  mov     [rsp+0A8h+var_18], rsi
0x1401a9df3  mov     r9d, 0Ch; unsigned int
0x1401a9df9  lea     r8d, [r9+1]; unsigned int
0x1401a9dfd  lea     rdx, a9n8mhtphngvv; "9N8MHTPHNGVV"
0x1401a9e04  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1401a9e09  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401a9e0e  nop
0x1401a9e0f  mov     rdx, [rsp+0A8h+var_18]
0x1401a9e17  mov     rcx, rdi
0x1401a9e1a  mov     rax, rbx
0x1401a9e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9e22  mov     ebx, eax
0x1401a9e24  test    eax, eax
0x1401a9e26  jns     short loc_1401A9E6C
0x1401a9e28  mov     rcx, [rsp+0A8h]; this
0x1401a9e30  mov     r9d, eax; char *
0x1401a9e33  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9e3a  mov     edx, 1AC2h; void *
0x1401a9e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9e44  nop
0x1401a9e45  lea     rcx, [rsp+0A8h+var_78]
0x1401a9e4a  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9e4f  nop
0x1401a9e50  lea     rcx, [rsp+0A8h+var_88]
0x1401a9e55  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9e5a  nop
0x1401a9e5b  lea     rcx, [rsp+0A8h+var_80]
0x1401a9e60  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9e65  mov     eax, ebx
0x1401a9e67  jmp     loc_1401AA45F
0x1401a9e6c  mov     [rsp+0A8h+var_70], rsi
0x1401a9e71  mov     rax, [rdi]
0x1401a9e74  mov     [rsp+0A8h+var_70], rsi
0x1401a9e79  lea     rdx, [rsp+0A8h+var_70]
0x1401a9e7e  mov     rcx, rdi
0x1401a9e81  mov     rax, [rax+40h]
0x1401a9e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9e8a  mov     ebx, eax
0x1401a9e8c  test    eax, eax
0x1401a9e8e  jns     short loc_1401A9EDF
0x1401a9e90  mov     rcx, [rsp+0A8h]; this
0x1401a9e98  mov     r9d, eax; char *
0x1401a9e9b  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9ea2  mov     edx, 1AC4h; void *
0x1401a9ea7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9eac  nop
0x1401a9ead  lea     rcx, [rsp+0A8h+var_70]
0x1401a9eb2  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9eb7  nop
0x1401a9eb8  lea     rcx, [rsp+0A8h+var_78]
0x1401a9ebd  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9ec2  nop
0x1401a9ec3  lea     rcx, [rsp+0A8h+var_88]
0x1401a9ec8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9ecd  nop
0x1401a9ece  lea     rcx, [rsp+0A8h+var_80]
0x1401a9ed3  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9ed8  mov     eax, ebx
0x1401a9eda  jmp     loc_1401AA45F
0x1401a9edf  mov     [rsp+0A8h+var_68], rsi
0x1401a9ee4  mov     rax, [rdi]
0x1401a9ee7  lea     r8, [rsp+0A8h+var_68]
0x1401a9eec  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x1401a9ef3  mov     rcx, rdi
0x1401a9ef6  mov     rax, [rax]
0x1401a9ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a9efe  mov     ebx, eax
0x1401a9f00  test    eax, eax
0x1401a9f02  jns     short loc_1401A9F5E
0x1401a9f04  mov     rcx, [rsp+0A8h]; this
0x1401a9f0c  mov     r9d, eax; char *
0x1401a9f0f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9f16  mov     edx, 1AC6h; void *
0x1401a9f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9f20  nop
0x1401a9f21  lea     rcx, [rsp+0A8h+var_68]
0x1401a9f26  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9f2b  nop
0x1401a9f2c  lea     rcx, [rsp+0A8h+var_70]
0x1401a9f31  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9f36  nop
0x1401a9f37  lea     rcx, [rsp+0A8h+var_78]
0x1401a9f3c  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9f41  nop
0x1401a9f42  lea     rcx, [rsp+0A8h+var_88]
0x1401a9f47  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9f4c  nop
0x1401a9f4d  lea     rcx, [rsp+0A8h+var_80]
0x1401a9f52  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9f57  mov     eax, ebx
0x1401a9f59  jmp     loc_1401AA45F
0x1401a9f5e  mov     [rsp+0A8h+var_58], rsi
0x1401a9f63  mov     [rsp+0A8h+var_18], rsi
0x1401a9f6b  mov     r9d, 23h ; '#'; unsigned int
0x1401a9f71  lea     r8d, [r9+1]; unsigned int
0x1401a9f75  lea     rdx, ?RuntimeClass_Windows_Services_Store_StoreContext@@3QBGB; "Windows.Services.Store.StoreContext"
0x1401a9f7c  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1401a9f81  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401a9f86  lea     r8, [rsp+0A8h+var_58]
0x1401a9f8b  lea     rdx, _GUID_9c06ee5f_15c0_4e72_9330_d6191cebd19c
0x1401a9f92  mov     rcx, [rsp+0A8h+var_18]
0x1401a9f9a  call    cs:__imp_RoGetActivationFactory
0x1401a9fa0  mov     ebx, eax
0x1401a9fa2  test    eax, eax
0x1401a9fa4  jns     short loc_1401AA00B
0x1401a9fa6  mov     rcx, [rsp+0A8h]; this
0x1401a9fae  mov     r9d, eax; char *
0x1401a9fb1  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401a9fb8  mov     edx, 1ACAh; void *
0x1401a9fbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401a9fc2  nop
0x1401a9fc3  lea     rcx, [rsp+0A8h+var_58]
0x1401a9fc8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9fcd  nop
0x1401a9fce  lea     rcx, [rsp+0A8h+var_68]
0x1401a9fd3  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9fd8  nop
0x1401a9fd9  lea     rcx, [rsp+0A8h+var_70]
0x1401a9fde  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9fe3  nop
0x1401a9fe4  lea     rcx, [rsp+0A8h+var_78]
0x1401a9fe9  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9fee  nop
0x1401a9fef  lea     rcx, [rsp+0A8h+var_88]
0x1401a9ff4  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401a9ff9  nop
0x1401a9ffa  lea     rcx, [rsp+0A8h+var_80]
0x1401a9fff  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa004  mov     eax, ebx
0x1401aa006  jmp     loc_1401AA45F
0x1401aa00b  mov     [rsp+0A8h+var_60], rsi
0x1401aa010  mov     rcx, [rsp+0A8h+var_58]
0x1401aa015  mov     rax, [rcx]
0x1401aa018  mov     [rsp+0A8h+var_60], rsi
0x1401aa01d  lea     rdx, [rsp+0A8h+var_60]
0x1401aa022  mov     rax, [rax+30h]
0x1401aa026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401aa02b  mov     ebx, eax
0x1401aa02d  test    eax, eax
0x1401aa02f  jns     short loc_1401AA0A1
0x1401aa031  mov     rcx, [rsp+0A8h]; this
0x1401aa039  mov     r9d, eax; char *
0x1401aa03c  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401aa043  mov     edx, 1ACDh; void *
0x1401aa048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aa04d  nop
0x1401aa04e  lea     rcx, [rsp+0A8h+var_60]
0x1401aa053  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa058  nop
0x1401aa059  lea     rcx, [rsp+0A8h+var_58]
0x1401aa05e  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1401aa063  nop
0x1401aa064  lea     rcx, [rsp+0A8h+var_68]
  ... truncated ...
```
