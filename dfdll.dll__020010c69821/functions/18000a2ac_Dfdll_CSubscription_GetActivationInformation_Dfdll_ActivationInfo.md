# Dfdll::CSubscription::GetActivationInformation(Dfdll::ActivationInfo &)

- ea: `0x18000a2ac`
- end: `0x18000aa13`
- name: `?GetActivationInformation@CSubscription@Dfdll@@QEAAJAEAUActivationInfo@2@@Z`
- size: `1895`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, struct Dfdll::ActivationInfo *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000444c`
- `0x180004580`

## callees

- `0x180002604`
- `0x180009460`
- `0x18000949c`
- `0x180009c44`
- `0x180009e0c`
- `0x18000a040`
- `0x18000a21c`
- `0x18000a2ac`
- `0x18000d9b8`
- `0x180010bf4`
- `0x180010f34`
- `0x180012140`
- `0x180012b30`
- `0x180012bd0`
- `0x18001efd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000a538`
- `ole32!CoTaskMemFree` at `0x18000a587`
- `ole32!CoTaskMemFree` at `0x18000a635`
- `ole32!CoTaskMemFree` at `0x18000a6b8`
- `ole32!CoTaskMemFree` at `0x18000a7e7`
- `ole32!CoTaskMemFree` at `0x18000a890`
- `ole32!CoTaskMemFree` at `0x18000a969`
- `ole32!CoTaskMemFree` at `0x18000a9e2`
- `ole32!CoTaskMemFree` at `0x18000a538`
- `ole32!CoTaskMemFree` at `0x18000a587`
- `ole32!CoTaskMemFree` at `0x18000a635`
- `ole32!CoTaskMemFree` at `0x18000a6b8`
- `ole32!CoTaskMemFree` at `0x18000a7e7`
- `ole32!CoTaskMemFree` at `0x18000a890`
- `ole32!CoTaskMemFree` at `0x18000a969`
- `ole32!CoTaskMemFree` at `0x18000a9e2`

## string_xrefs

- `0x18000a3b4`: `DeploymentProviderUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Dfdll::CSubscription::GetActivationInformation(
        Dfdll::CSubscription *this,
        struct Dfdll::ActivationInfo *a2)
{
  int ApplicationManifest; // ebx
  const struct std::nothrow_t *v5; // rdx
  const struct std::nothrow_t *v6; // rdx
  __int64 (__fastcall ***v7)(_QWORD, __int64, _QWORD *); // rcx
  __int64 (__fastcall ***v8)(_QWORD, __int64, __int64 *); // r14
  __int64 v9; // rdx
  __int64 (__fastcall **v10)(_QWORD, __int64, __int64 *); // rbx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, __int64, _QWORD *); // rcx
  bool v17; // [rsp+40h] [rbp-79h] BYREF
  void **v18; // [rsp+48h] [rbp-71h] BYREF
  __int64 v19; // [rsp+50h] [rbp-69h] BYREF
  void **v20; // [rsp+58h] [rbp-61h]
  __int64 (__fastcall ***v21)(_QWORD, __int64, _QWORD *); // [rsp+60h] [rbp-59h] BYREF
  void **v22; // [rsp+68h] [rbp-51h] BYREF
  __int64 v23; // [rsp+70h] [rbp-49h] BYREF
  void **v24; // [rsp+78h] [rbp-41h]
  LPVOID pv; // [rsp+80h] [rbp-39h] BYREF
  int v26; // [rsp+88h] [rbp-31h]
  char v27; // [rsp+8Ch] [rbp-2Dh]
  int v28; // [rsp+90h] [rbp-29h] BYREF
  void **v29; // [rsp+98h] [rbp-21h] BYREF
  void **v30; // [rsp+A0h] [rbp-19h]
  void *v31; // [rsp+A8h] [rbp-11h]
  int v32; // [rsp+B0h] [rbp-9h]
  int v33; // [rsp+B8h] [rbp-1h]
  struct tagBLOB v34; // [rsp+C0h] [rbp+7h] BYREF
  GUID v35; // [rsp+D0h] [rbp+17h] BYREF

  if ( !*((_QWORD *)this + 8) )
    return (unsigned int)-2147023893;
  ApplicationManifest = Dfdll::CSubscription::EnsureInitialization(this);
  if ( ApplicationManifest >= 0 )
  {
    v28 = 1;
    ApplicationManifest = Dfdll::CSubscription::CheckShellVisibility(this, &v28);
    if ( ApplicationManifest >= 0 )
    {
      if ( !v28 )
        return (unsigned int)-2147023893;
      if ( *((_QWORD *)this + 12) && *((_QWORD *)this + 10)
        || (ApplicationManifest = Dfdll::CSubscription::LoadIdentities(this), ApplicationManifest >= 0) )
      {
        ApplicationManifest = Dfdll::CString::Assign(
                                (struct Dfdll::ActivationInfo *)((char *)a2 + 56),
                                *((const unsigned __int16 **)this + 2));
        if ( ApplicationManifest >= 0 )
        {
          if ( *((_QWORD *)this + 24)
            || (ApplicationManifest = Dfdll::CSubscription::LoadDeploymentManifest(this), ApplicationManifest >= 0) )
          {
            if ( *((_QWORD *)this + 22)
              || (ApplicationManifest = Dfdll::CSubscription::LoadApplicationManifest(this), ApplicationManifest >= 0) )
            {
              v35 = CLSID_STORE_PROPSET;
              ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, struct tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
                                      *((_QWORD *)this + 16),
                                      0,
                                      *((_QWORD *)this + 8),
                                      (char *)this + 200,
                                      &v35,
                                      L"DeploymentProviderUri",
                                      &v34);
              if ( ApplicationManifest >= 0 )
              {
                ApplicationManifest = Dfdll::CConvert::ToString(&v34, (struct Dfdll::ActivationInfo *)((char *)a2 + 96));
                if ( ApplicationManifest >= 0 )
                {
                  *((_DWORD *)a2 + 34) = 0;
                  if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, struct tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
                         *((_QWORD *)this + 16),
                         0,
                         *((_QWORD *)this + 10),
                         (char *)this + 200,
                         &v35,
                         L"IsFullTrust",
                         &v34) < 0 )
                  {
LABEL_24:
                    pv = 0;
                    v27 = 0;
                    v26 = 0;
                    v24 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
                    ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, LPVOID *))(**((_QWORD **)this + 18) + 40LL))(
                                            *((_QWORD *)this + 18),
                                            0,
                                            *((_QWORD *)this + 6),
                                            &pv);
                    if ( ApplicationManifest >= 0 )
                    {
                      ApplicationManifest = Dfdll::CString::Assign(
                                              (struct Dfdll::ActivationInfo *)((char *)a2 + 16),
                                              (const unsigned __int16 *)pv);
                      if ( ApplicationManifest >= 0 )
                      {
                        v21 = 0;
                        v20 = &Dfdll::CIUnknownBasedPointer<ISectionEntry>::`vftable';
                        v19 = 0;
                        v18 = &Dfdll::CIUnknownBasedPointer<IMetadataSectionEntry>::`vftable';
                        ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(**((_QWORD **)this + 24) + 112LL))(
                                                *((_QWORD *)this + 24),
                                                &v21);
                        if ( ApplicationManifest >= 0 )
                        {
                          v7 = v21;
                          if ( v21 )
                          {
                            v8 = v21;
                            v9 = v19;
                            if ( v19 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                            v19 = 0;
                            v10 = *v8;
                            v11 = ((__int64 (__fastcall *)(void ***, __int64, _QWORD))v18[5])(&v18, v9, 0);
                            v12 = (*v10)(v8, v11, &v19);
                            ApplicationManifest = v12;
                            v13 = v19;
                            if ( v12 < 0 )
                              v13 = 0;
                            v19 = v13;
                            if ( v12 < 0 )
                            {
                              v15 = v21;
                              v18 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                              if ( v13 )
                              {
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                                v15 = v21;
                              }
                              v19 = 0;
                              v18 = &Dfdll::CObject::`vftable';
                              v20 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                              if ( v15 )
                                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v15)[2])(v15);
                              v21 = 0;
                              v20 = &Dfdll::CObject::`vftable';
                              v24 = &Dfdll::CCOMPointerBase::`vftable';
                              if ( pv )
                                CoTaskMemFree(pv);
                            }
                            else
                            {
                              v23 = 0;
                              v22 = &Dfdll::CIUnknownBasedPointer<IDeploymentMetadataEntry>::`vftable';
                              ApplicationManifest = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13
                                                                                                  + 120LL))(
                                                      v13,
                                                      &v23);
                              if ( ApplicationManifest >= 0 )
                              {
                                v14 = v19;
                                if ( v19 )
                                {
                                  if ( (int)Dfdll::CSubscription::CheckForBeforeApplicationStartup(this, &v22, a2) < 0 )
                                    *(_DWORD *)a2 = 0;
                                  if ( (int)Dfdll::CSubscription::CheckForUpdateStatus(this) < 0 )
                                    *((_DWORD *)a2 + 1) = 0;
                                  if ( (int)Dfdll::CSubscription::CheckForPendingDeploymentStatus(this, (int *)a2 + 2) < 0 )
                                    *((_DWORD *)a2 + 2) = 0;
                                  ApplicationManifest = 0;
                                  v22 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                  if ( v23 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                                  v23 = 0;
                                  v22 = &Dfdll::CObject::`vftable';
                                  v18 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                  if ( v19 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                                  v19 = 0;
                                  v18 = &Dfdll::CObject::`vftable';
                                  v20 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                  if ( v21 )
                                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v21)[2])(v21);
                                  v21 = 0;
                                  v20 = &Dfdll::CObject::`vftable';
                                  v24 = &Dfdll::CCOMPointerBase::`vftable';
                                  if ( pv )
                                    CoTaskMemFree(pv);
                                }
                                else
                                {
                                  ApplicationManifest = -2147024883;
                                  v22 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                  if ( v23 )
                                  {
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                                    v14 = v19;
                                  }
                                  v23 = 0;
                                  v22 = &Dfdll::CObject::`vftable';
                                  v18 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                  if ( v14 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                                  v19 = 0;
                                  v18 = &Dfdll::CObject::`vftable';
                                  v20 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                  if ( v21 )
                                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v21)[2])(v21);
                                  v21 = 0;
                                  v20 = &Dfdll::CObject::`vftable';
                                  v24 = &Dfdll::CCOMPointerBase::`vftable';
                                  if ( pv )
                                    CoTaskMemFree(pv);
                                }
                              }
                              else
                              {
                                v22 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                if ( v23 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                                v23 = 0;
                                v22 = &Dfdll::CObject::`vftable';
                                v18 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                if ( v19 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                                v19 = 0;
                                v18 = &Dfdll::CObject::`vftable';
                                v20 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                                if ( v21 )
                                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v21)[2])(v21);
                                v21 = 0;
                                v20 = &Dfdll::CObject::`vftable';
                                v24 = &Dfdll::CCOMPointerBase::`vftable';
                                if ( pv )
                                  CoTaskMemFree(pv);
                              }
                            }
                          }
                          else
                          {
                            ApplicationManifest = -2147024883;
                            v18 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                            if ( v19 )
                            {
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                              v7 = v21;
                            }
                            v19 = 0;
                            v18 = &Dfdll::CObject::`vftable';
                            v20 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                            if ( v7 )
                              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v7)[2])(v7);
                            v21 = 0;
                            v20 = &Dfdll::CObject::`vftable';
                            v24 = &Dfdll::CCOMPointerBase::`vftable';
                            if ( pv )
                              CoTaskMemFree(pv);
                          }
                        }
                        else
                        {
                          v18 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                          if ( v19 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                          v19 = 0;
                          v18 = &Dfdll::CObject::`vftable';
                          v20 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                          if ( v21 )
                            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v21)[2])(v21);
                          v21 = 0;
                          v20 = &Dfdll::CObject::`vftable';
                          v24 = &Dfdll::CCOMPointerBase::`vftable';
                          if ( pv )
                            CoTaskMemFree(pv);
                        }
                      }
                      else
                      {
                        v24 = &Dfdll::CCOMPointerBase::`vftable';
                        if ( pv )
                          CoTaskMemFree(pv);
                      }
                    }
                    else
                    {
                      v24 = &Dfdll::CCOMPointerBase::`vftable';
                      if ( pv )
                        CoTaskMemFree(pv);
                    }
                    return (unsigned int)ApplicationManifest;
                  }
                  v29 = &Dfdll::CString::`vftable';
                  v31 = 0;
                  v32 = 0;
                  v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
                  v33 = 0;
                  ApplicationManifest = Dfdll::CConvert::ToString(&v34, (struct Dfdll::CString *)&v29);
                  if ( ApplicationManifest < 0 )
                  {
                    v29 = &Dfdll::CString::`vftable';
                    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
                    if ( v31 )
                      operator delete(v31, v5);
                    return (unsigned int)ApplicationManifest;
                  }
                  v17 = 0;
                  ApplicationManifest = Dfdll::CString::Equals((Dfdll::CString *)&v29, L"True", &v17);
                  if ( ApplicationManifest >= 0 )
                  {
                    *((_DWORD *)a2 + 34) = v17 + 1;
                    v29 = &Dfdll::CString::`vftable';
                    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
                    if ( v31 )
                      operator delete(v31, v6);
                    goto LABEL_24;
                  }
                  v29 = &Dfdll::CString::`vftable';
                  v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
                  if ( v31 )
                    operator delete(v31, v6);
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)ApplicationManifest;
}

```

## disassembly

```asm
0x18000a2ac  mov     [rsp-8+arg_10], rbx
0x18000a2b1  mov     [rsp-8+arg_18], rsi
0x18000a2b6  push    rbp
0x18000a2b7  push    rdi
0x18000a2b8  push    r12
0x18000a2ba  push    r14
0x18000a2bc  push    r15
0x18000a2be  lea     rbp, [rsp-37h]
0x18000a2c3  sub     rsp, 0F0h
0x18000a2ca  mov     rax, cs:__security_cookie
0x18000a2d1  xor     rax, rsp
0x18000a2d4  mov     [rbp+57h+var_30], rax
0x18000a2d8  mov     rsi, rdx
0x18000a2db  mov     rdi, rcx
0x18000a2de  xor     r15d, r15d
0x18000a2e1  cmp     [rcx+40h], r15
0x18000a2e5  jnz     short loc_18000A2F1
0x18000a2e7  mov     ebx, 800703EBh
0x18000a2ec  jmp     loc_18000A9E9
0x18000a2f1  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000a2f6  mov     ebx, eax
0x18000a2f8  test    eax, eax
0x18000a2fa  js      loc_18000A9E9
0x18000a300  mov     [rbp+57h+var_80], 1
0x18000a307  lea     rdx, [rbp+57h+var_80]; int *
0x18000a30b  mov     rcx, rdi; this
0x18000a30e  call    ?CheckShellVisibility@CSubscription@Dfdll@@IEAAJAEAH@Z; Dfdll::CSubscription::CheckShellVisibility(int &)
0x18000a313  mov     ebx, eax
0x18000a315  test    eax, eax
0x18000a317  js      loc_18000A9E9
0x18000a31d  cmp     [rbp+57h+var_80], r15d
0x18000a321  jz      short loc_18000A2E7
0x18000a323  cmp     [rdi+60h], r15
0x18000a327  jz      short loc_18000A32F
0x18000a329  cmp     [rdi+50h], r15
0x18000a32d  jnz     short loc_18000A341
0x18000a32f  mov     rcx, rdi; this
0x18000a332  call    ?LoadIdentities@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadIdentities(void)
0x18000a337  mov     ebx, eax
0x18000a339  test    eax, eax
0x18000a33b  js      loc_18000A9E9
0x18000a341  lea     rcx, [rsi+38h]; this
0x18000a345  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18000a349  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x18000a34e  mov     ebx, eax
0x18000a350  test    eax, eax
0x18000a352  js      loc_18000A9E9
0x18000a358  cmp     [rdi+0C0h], r15
0x18000a35f  jnz     short loc_18000A373
0x18000a361  mov     rcx, rdi; this
0x18000a364  call    ?LoadDeploymentManifest@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadDeploymentManifest(void)
0x18000a369  mov     ebx, eax
0x18000a36b  test    eax, eax
0x18000a36d  js      loc_18000A9E9
0x18000a373  cmp     [rdi+0B0h], r15
0x18000a37a  jnz     short loc_18000A38E
0x18000a37c  mov     rcx, rdi; this
0x18000a37f  call    ?LoadApplicationManifest@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadApplicationManifest(void)
0x18000a384  mov     ebx, eax
0x18000a386  test    eax, eax
0x18000a388  js      loc_18000A9E9
0x18000a38e  movups  xmm0, xmmword ptr cs:CLSID_STORE_PROPSET.Data1
0x18000a395  movdqu  [rbp+57h+var_40], xmm0
0x18000a39a  mov     rcx, [rdi+80h]
0x18000a3a1  lea     r14, [rdi+0C8h]
0x18000a3a8  mov     rax, [rcx]
0x18000a3ab  lea     rdx, [rbp+57h+var_50]
0x18000a3af  mov     [rsp+110h+var_E0], rdx
0x18000a3b4  lea     rdx, aDeploymentprov; "DeploymentProviderUri"
0x18000a3bb  mov     [rsp+110h+var_E8], rdx
0x18000a3c0  lea     rdx, [rbp+57h+var_40]
0x18000a3c4  mov     [rsp+110h+var_F0], rdx
0x18000a3c9  mov     r9, r14
0x18000a3cc  mov     r8, [rdi+40h]
0x18000a3d0  xor     edx, edx
0x18000a3d2  mov     rax, [rax+88h]
0x18000a3d9  call    cs:__guard_dispatch_icall_fptr
0x18000a3df  mov     ebx, eax
0x18000a3e1  test    eax, eax
0x18000a3e3  js      loc_18000A9E9
0x18000a3e9  lea     rdx, [rsi+60h]; struct Dfdll::CString *
0x18000a3ed  lea     rcx, [rbp+57h+var_50]; struct tagBLOB *
0x18000a3f1  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x18000a3f6  mov     ebx, eax
0x18000a3f8  test    eax, eax
0x18000a3fa  js      loc_18000A9E9
0x18000a400  mov     [rsi+88h], r15d
0x18000a407  mov     rcx, [rdi+80h]
0x18000a40e  mov     rax, [rcx]
0x18000a411  lea     rdx, [rbp+57h+var_50]
0x18000a415  mov     [rsp+110h+var_E0], rdx
0x18000a41a  lea     rdx, aIsfulltrust; "IsFullTrust"
0x18000a421  mov     [rsp+110h+var_E8], rdx
0x18000a426  lea     rdx, [rbp+57h+var_40]
0x18000a42a  mov     [rsp+110h+var_F0], rdx
0x18000a42f  mov     r9, r14
0x18000a432  mov     r8, [rdi+50h]
0x18000a436  xor     edx, edx
0x18000a438  mov     rax, [rax+88h]
0x18000a43f  call    cs:__guard_dispatch_icall_fptr
0x18000a445  test    eax, eax
0x18000a447  js      loc_18000A4E9
0x18000a44d  lea     r14, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x18000a454  mov     [rbp+57h+var_78], r14
0x18000a458  mov     [rbp+57h+var_68], r15
0x18000a45c  mov     [rbp+57h+var_60], r15d
0x18000a460  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000a467  mov     [rbp+57h+var_70], r12
0x18000a46b  mov     [rbp+57h+var_58], r15d
0x18000a46f  lea     rdx, [rbp+57h+var_78]; struct Dfdll::CString *
0x18000a473  lea     rcx, [rbp+57h+var_50]; struct tagBLOB *
0x18000a477  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x18000a47c  mov     ebx, eax
0x18000a47e  test    eax, eax
0x18000a480  jns     short loc_18000A49E
0x18000a482  mov     [rbp+57h+var_78], r14
0x18000a486  mov     [rbp+57h+var_70], r12
0x18000a48a  mov     rcx, [rbp+57h+var_68]; void *
0x18000a48e  test    rcx, rcx
0x18000a491  jz      short loc_18000A499
0x18000a493  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a498  nop
0x18000a499  jmp     loc_18000A9E9
0x18000a49e  mov     [rbp+57h+var_D0], r15b
0x18000a4a2  lea     r8, [rbp+57h+var_D0]; bool *
0x18000a4a6  lea     rdx, aTrue; "True"
0x18000a4ad  lea     rcx, [rbp+57h+var_78]; this
0x18000a4b1  call    ?Equals@CString@Dfdll@@QEAAJPEBGAEA_N@Z; Dfdll::CString::Equals(ushort const *,bool &)
0x18000a4b6  mov     ebx, eax
0x18000a4b8  test    eax, eax
0x18000a4ba  js      loc_18000A544
0x18000a4c0  mov     eax, r15d
0x18000a4c3  cmp     [rbp+57h+var_D0], r15b
0x18000a4c7  setnz   al
0x18000a4ca  inc     eax
0x18000a4cc  mov     [rsi+88h], eax
0x18000a4d2  mov     [rbp+57h+var_78], r14
0x18000a4d6  mov     [rbp+57h+var_70], r12
0x18000a4da  mov     rcx, [rbp+57h+var_68]; void *
0x18000a4de  test    rcx, rcx
0x18000a4e1  jz      short loc_18000A4E9
0x18000a4e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a4e8  nop
0x18000a4e9  mov     [rbp+57h+pv], r15
0x18000a4ed  mov     [rbp+57h+var_84], r15b
0x18000a4f1  mov     [rbp+57h+var_88], r15d
0x18000a4f5  lea     rax, ??_7?$CCOMPointer@G@Dfdll@@6B@; const Dfdll::CCOMPointer<ushort>::`vftable'
0x18000a4fc  mov     [rbp+57h+var_98], rax
0x18000a500  mov     rcx, [rdi+90h]
0x18000a507  mov     rax, [rcx]
0x18000a50a  lea     r9, [rbp+57h+pv]
0x18000a50e  mov     r8, [rdi+30h]
0x18000a512  xor     edx, edx
0x18000a514  mov     rax, [rax+28h]
0x18000a518  call    cs:__guard_dispatch_icall_fptr
0x18000a51e  mov     ebx, eax
0x18000a520  test    eax, eax
0x18000a522  jns     short loc_18000A560
0x18000a524  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000a52b  mov     [rbp+57h+var_98], rax
0x18000a52f  mov     rcx, [rbp+57h+pv]; pv
0x18000a533  test    rcx, rcx
0x18000a536  jz      short loc_18000A53F
0x18000a538  call    cs:__imp_CoTaskMemFree
0x18000a53e  nop
0x18000a53f  jmp     loc_18000A9E9
0x18000a544  mov     [rbp+57h+var_78], r14
0x18000a548  mov     [rbp+57h+var_70], r12
0x18000a54c  mov     rcx, [rbp+57h+var_68]; void *
0x18000a550  test    rcx, rcx
0x18000a553  jz      short loc_18000A55B
0x18000a555  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a55a  nop
0x18000a55b  jmp     loc_18000A9E9
0x18000a560  lea     rcx, [rsi+10h]; this
0x18000a564  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18000a568  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x18000a56d  mov     ebx, eax
0x18000a56f  test    eax, eax
0x18000a571  jns     short loc_18000A593
0x18000a573  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000a57a  mov     [rbp+57h+var_98], rax
0x18000a57e  mov     rcx, [rbp+57h+pv]; pv
0x18000a582  test    rcx, rcx
0x18000a585  jz      short loc_18000A58E
0x18000a587  call    cs:__imp_CoTaskMemFree
0x18000a58d  nop
0x18000a58e  jmp     loc_18000A9E9
0x18000a593  mov     [rbp+57h+var_B0], r15
0x18000a597  lea     rax, ??_7?$CIUnknownBasedPointer@UISectionEntry@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<ISectionEntry>::`vftable'
0x18000a59e  mov     [rbp+57h+var_B8], rax
0x18000a5a2  mov     [rbp+57h+var_C0], r15
0x18000a5a6  lea     rax, ??_7?$CIUnknownBasedPointer@UIMetadataSectionEntry@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IMetadataSectionEntry>::`vftable'
0x18000a5ad  mov     [rbp+57h+var_C8], rax
0x18000a5b1  mov     rcx, [rdi+0C0h]
0x18000a5b8  mov     rax, [rcx]
0x18000a5bb  lea     rdx, [rbp+57h+var_B0]
0x18000a5bf  mov     rax, [rax+70h]
0x18000a5c3  call    cs:__guard_dispatch_icall_fptr
0x18000a5c9  mov     ebx, eax
0x18000a5cb  test    eax, eax
0x18000a5cd  jns     short loc_18000A641
0x18000a5cf  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000a5d6  mov     [rbp+57h+var_C8], rdi
0x18000a5da  mov     rcx, [rbp+57h+var_C0]
0x18000a5de  test    rcx, rcx
0x18000a5e1  jz      short loc_18000A5F0
0x18000a5e3  mov     rax, [rcx]
0x18000a5e6  mov     rax, [rax+10h]
0x18000a5ea  call    cs:__guard_dispatch_icall_fptr
0x18000a5f0  mov     [rbp+57h+var_C0], r15
0x18000a5f4  lea     rsi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000a5fb  mov     [rbp+57h+var_C8], rsi
0x18000a5ff  mov     [rbp+57h+var_B8], rdi
0x18000a603  mov     rcx, [rbp+57h+var_B0]
0x18000a607  test    rcx, rcx
0x18000a60a  jz      short loc_18000A619
0x18000a60c  mov     rax, [rcx]
0x18000a60f  mov     rax, [rax+10h]
0x18000a613  call    cs:__guard_dispatch_icall_fptr
0x18000a619  mov     [rbp+57h+var_B0], r15
0x18000a61d  mov     [rbp+57h+var_B8], rsi
0x18000a621  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000a628  mov     [rbp+57h+var_98], rax
0x18000a62c  mov     rcx, [rbp+57h+pv]; pv
0x18000a630  test    rcx, rcx
0x18000a633  jz      short loc_18000A63C
0x18000a635  call    cs:__imp_CoTaskMemFree
0x18000a63b  nop
0x18000a63c  jmp     loc_18000A9E9
0x18000a641  mov     rcx, [rbp+57h+var_B0]
0x18000a645  test    rcx, rcx
0x18000a648  jnz     short loc_18000A6C4
0x18000a64a  mov     ebx, 8007000Dh
0x18000a64f  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000a656  mov     [rbp+57h+var_C8], rdi
0x18000a65a  mov     rdx, [rbp+57h+var_C0]
0x18000a65e  test    rdx, rdx
0x18000a661  jz      short loc_18000A677
0x18000a663  mov     rax, [rdx]
0x18000a666  mov     rcx, rdx
0x18000a669  mov     rax, [rax+10h]
0x18000a66d  call    cs:__guard_dispatch_icall_fptr
0x18000a673  mov     rcx, [rbp+57h+var_B0]
0x18000a677  mov     [rbp+57h+var_C0], r15
0x18000a67b  lea     rsi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000a682  mov     [rbp+57h+var_C8], rsi
0x18000a686  mov     [rbp+57h+var_B8], rdi
0x18000a68a  test    rcx, rcx
0x18000a68d  jz      short loc_18000A69C
0x18000a68f  mov     rax, [rcx]
0x18000a692  mov     rax, [rax+10h]
0x18000a696  call    cs:__guard_dispatch_icall_fptr
0x18000a69c  mov     [rbp+57h+var_B0], r15
0x18000a6a0  mov     [rbp+57h+var_B8], rsi
0x18000a6a4  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000a6ab  mov     [rbp+57h+var_98], rax
0x18000a6af  mov     rcx, [rbp+57h+pv]; pv
0x18000a6b3  test    rcx, rcx
0x18000a6b6  jz      short loc_18000A6BF
0x18000a6b8  call    cs:__imp_CoTaskMemFree
0x18000a6be  nop
0x18000a6bf  jmp     loc_18000A9E9
0x18000a6c4  mov     r14, rcx
0x18000a6c7  mov     rdx, [rbp+57h+var_C0]
0x18000a6cb  test    rdx, rdx
0x18000a6ce  jz      short loc_18000A6E4
0x18000a6d0  mov     rax, [rdx]
0x18000a6d3  mov     rcx, rdx
0x18000a6d6  mov     rax, [rax+10h]
0x18000a6da  call    cs:__guard_dispatch_icall_fptr
0x18000a6e0  mov     rcx, [rbp+57h+var_B0]
0x18000a6e4  mov     r8, r15
0x18000a6e7  mov     [rbp+57h+var_C0], r15
0x18000a6eb  test    r14, r14
0x18000a6ee  jz      loc_18000A978
0x18000a6f4  mov     rbx, [r14]
0x18000a6f7  mov     rax, [rbp+57h+var_C8]
0x18000a6fb  lea     rcx, [rbp+57h+var_C8]
0x18000a6ff  mov     rax, [rax+28h]
0x18000a703  call    cs:__guard_dispatch_icall_fptr
0x18000a709  mov     rdx, rax
0x18000a70c  lea     r8, [rbp+57h+var_C0]
0x18000a710  mov     rcx, r14
0x18000a713  mov     rax, [rbx]
0x18000a716  call    cs:__guard_dispatch_icall_fptr
0x18000a71c  mov     ebx, eax
0x18000a71e  mov     r8, [rbp+57h+var_C0]
0x18000a722  test    eax, eax
0x18000a724  cmovs   r8, r15
0x18000a728  mov     [rbp+57h+var_C0], r8
0x18000a72c  js      loc_18000A972
0x18000a732  mov     [rbp+57h+var_A0], r15
0x18000a736  lea     rax, ??_7?$CIUnknownBasedPointer@UIDeploymentMetadataEntry@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDeploymentMetadataEntry>::`vftable'
0x18000a73d  mov     [rbp+57h+var_A8], rax
0x18000a741  mov     rax, [r8]
0x18000a744  lea     rdx, [rbp+57h+var_A0]
0x18000a748  mov     rcx, r8
0x18000a74b  mov     rax, [rax+78h]
0x18000a74f  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
