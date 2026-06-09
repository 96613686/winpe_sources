# Dfdll::CSubscription::GetApplicationEntryPointFilePath(Dfdll::CString &)

- ea: `0x18000ab8c`
- end: `0x18000c7fe`
- name: `?GetApplicationEntryPointFilePath@CSubscription@Dfdll@@QEAAJAEAVCString@2@@Z`
- size: `7282`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, struct Dfdll::CString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007130`

## callees

- `0x180002604`
- `0x180003530`
- `0x180009e0c`
- `0x18000a040`
- `0x18000ab8c`
- `0x18000d9b8`
- `0x18001efd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000b654`
- `ole32!CoTaskMemFree` at `0x18000b833`
- `ole32!CoTaskMemFree` at `0x18000bbf0`
- `ole32!CoTaskMemFree` at `0x18000bc1a`
- `ole32!CoTaskMemFree` at `0x18000bdf8`
- `ole32!CoTaskMemFree` at `0x18000be22`
- `ole32!CoTaskMemFree` at `0x18000c024`
- `ole32!CoTaskMemFree` at `0x18000c04e`
- `ole32!CoTaskMemFree` at `0x18000c20b`
- `ole32!CoTaskMemFree` at `0x18000c238`
- `ole32!CoTaskMemFree` at `0x18000b654`
- `ole32!CoTaskMemFree` at `0x18000b833`
- `ole32!CoTaskMemFree` at `0x18000bbf0`
- `ole32!CoTaskMemFree` at `0x18000bc1a`
- `ole32!CoTaskMemFree` at `0x18000bdf8`
- `ole32!CoTaskMemFree` at `0x18000be22`
- `ole32!CoTaskMemFree` at `0x18000c024`
- `ole32!CoTaskMemFree` at `0x18000c04e`
- `ole32!CoTaskMemFree` at `0x18000c20b`
- `ole32!CoTaskMemFree` at `0x18000c238`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall Dfdll::CSubscription::GetApplicationEntryPointFilePath(
        Dfdll::CSubscription *this,
        struct Dfdll::CString *a2)
{
  int ApplicationManifest; // esi
  __int64 (__fastcall ***v5)(__int64, __int64, __int64 *); // rcx
  __int64 (__fastcall ***v6)(__int64, __int64, __int64 *); // rsi
  __int64 v7; // r10
  __int64 (__fastcall **v8)(__int64, __int64, __int64 *); // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, __int64, _QWORD *); // rcx
  __int64 (__fastcall ***v12)(_QWORD, __int64, __int64 *); // rsi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 (__fastcall **v15)(_QWORD, __int64, __int64 *); // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // r8
  __int64 (__fastcall ***v19)(_QWORD, __int64, _QWORD *); // rcx
  __int64 (__fastcall ***v20)(_QWORD, __int64, __int64 *); // rsi
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 (__fastcall **v23)(_QWORD, __int64, __int64 *); // rbx
  __int64 v24; // rax
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, __int64, _QWORD *); // rcx
  __int64 (__fastcall ***v27)(_QWORD, __int64, __int64 *); // rsi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 (__fastcall **v30)(_QWORD, __int64, __int64 *); // rbx
  __int64 v31; // rax
  int v32; // eax
  unsigned __int16 *v33; // r14
  unsigned __int16 *v34; // rcx
  void **v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  void **v38; // [rsp+40h] [rbp-C0h]
  __int64 (__fastcall ***v39)(__int64, __int64, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  void **v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  void **v42; // [rsp+60h] [rbp-A0h]
  __int64 (__fastcall ***v43)(_QWORD, __int64, _QWORD *); // [rsp+68h] [rbp-98h] BYREF
  void **v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  void **v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  void **v48; // [rsp+90h] [rbp-70h]
  __int64 (__fastcall ***v49)(_QWORD, __int64, _QWORD *); // [rsp+98h] [rbp-68h] BYREF
  void **v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-58h] BYREF
  void **v52; // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall ***v53)(_QWORD, __int64, _QWORD *); // [rsp+B8h] [rbp-48h] BYREF
  void **v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h] BYREF
  void **v56; // [rsp+D0h] [rbp-30h]
  __int64 v57; // [rsp+D8h] [rbp-28h] BYREF
  void **v58; // [rsp+E0h] [rbp-20h]
  LPVOID pv; // [rsp+E8h] [rbp-18h] BYREF
  int v60; // [rsp+F0h] [rbp-10h]
  char v61; // [rsp+F4h] [rbp-Ch]
  void **v62; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v63; // [rsp+100h] [rbp+0h] BYREF
  int v64; // [rsp+108h] [rbp+8h]
  char v65; // [rsp+10Ch] [rbp+Ch]
  int v66; // [rsp+150h] [rbp+50h] BYREF
  int v67; // [rsp+160h] [rbp+60h] BYREF
  __int64 v68; // [rsp+168h] [rbp+68h] BYREF

  if ( !*((_QWORD *)this + 8) )
    return (unsigned int)-2147023893;
  ApplicationManifest = Dfdll::CSubscription::EnsureInitialization(this);
  if ( ApplicationManifest < 0 )
    return (unsigned int)ApplicationManifest;
  v66 = 1;
  ApplicationManifest = Dfdll::CSubscription::CheckShellVisibility(this, &v66);
  if ( ApplicationManifest < 0 )
    return (unsigned int)ApplicationManifest;
  if ( !v66 )
    return (unsigned int)-2147023893;
  if ( !*((_QWORD *)this + 22) )
  {
    ApplicationManifest = Dfdll::CSubscription::LoadApplicationManifest(this);
    if ( ApplicationManifest < 0 )
      return (unsigned int)ApplicationManifest;
  }
  v55 = 0;
  v54 = &Dfdll::CIUnknownBasedPointer<ISection>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 22) + 96LL))(
                          *((_QWORD *)this + 22),
                          &v55);
  if ( ApplicationManifest < 0 )
  {
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  if ( !v55 )
    return (unsigned int)-2147024883;
  v39 = 0;
  v38 = &Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable';
  v37 = 0;
  v36 = &Dfdll::CIUnknownBasedPointer<IEnumUnknown>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(__int64, __int64, __int64 *)))(*(_QWORD *)v55 + 24LL))(
                          v55,
                          &v39);
  if ( ApplicationManifest < 0 )
  {
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v5 = v39;
  v6 = v39;
  v7 = 0;
  v37 = 0;
  if ( !v39 )
  {
    ApplicationManifest = -2147467261;
    goto LABEL_381;
  }
  v8 = *v39;
  v9 = ((__int64 (__fastcall *)(void ***))v36[5])(&v36);
  v10 = (*v8)((__int64)v6, v9, &v37);
  ApplicationManifest = v10;
  v7 = v37;
  if ( v10 < 0 )
    v7 = 0;
  v37 = v7;
  if ( v10 < 0 )
  {
    v5 = v39;
LABEL_381:
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      v5 = v39;
    }
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v5 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v5)[2])(v5);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v43 = 0;
  v42 = &Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable';
  v41 = 0;
  v40 = &Dfdll::CIUnknownBasedPointer<IEntryPointEntry>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *), int *))(*(_QWORD *)v7 + 24LL))(
                          v7,
                          1,
                          &v43,
                          &v67);
  if ( ApplicationManifest < 0 )
  {
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  if ( !v67 )
  {
    ApplicationManifest = -2147024883;
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v11 = v43;
  v12 = v43;
  v13 = v41;
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v11 = v43;
  }
  v14 = 0;
  v41 = 0;
  if ( !v12 )
  {
    ApplicationManifest = -2147467261;
    goto LABEL_368;
  }
  v15 = *v12;
  v16 = ((__int64 (__fastcall *)(void ***, __int64, _QWORD))v40[5])(&v40, v13, 0);
  v17 = (*v15)(v12, v16, &v41);
  ApplicationManifest = v17;
  v14 = v41;
  if ( v17 < 0 )
    v14 = 0;
  v41 = v14;
  if ( v17 < 0 )
  {
    v11 = v43;
LABEL_368:
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v11 = v43;
    }
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v11 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v11)[2])(v11);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v45 = 0;
  v44 = &Dfdll::CIUnknownBasedPointer<IReferenceIdentity>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 56LL))(v14, &v45);
  if ( ApplicationManifest < 0 )
  {
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  if ( !v45 )
  {
    ApplicationManifest = -2147024883;
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v49 = 0;
  v48 = &Dfdll::CIUnknownBasedPointer<ISection>::`vftable';
  v47 = 0;
  v46 = &Dfdll::CIUnknownBasedPointer<ISectionWithReferenceIdentityKey>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(**((_QWORD **)this + 22) + 72LL))(
                          *((_QWORD *)this + 22),
                          &v49);
  if ( ApplicationManifest < 0 )
  {
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v19 = v49;
  v20 = v49;
  v21 = v47;
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v19 = v49;
  }
  v22 = 0;
  v47 = 0;
  if ( !v20 )
  {
    ApplicationManifest = -2147467261;
    goto LABEL_349;
  }
  v23 = *v20;
  v24 = ((__int64 (__fastcall *)(void ***, __int64, __int64, _QWORD))v46[5])(&v46, v21, v18, 0);
  v25 = (*v23)(v20, v24, &v47);
  ApplicationManifest = v25;
  v22 = v47;
  if ( v25 < 0 )
    v22 = 0;
  v47 = v22;
  if ( v25 < 0 )
  {
    v19 = v49;
LABEL_349:
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v19 = v49;
    }
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v19 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v19)[2])(v19);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v53 = 0;
  v52 = &Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable';
  v51 = 0;
  v50 = &Dfdll::CIUnknownBasedPointer<IAssemblyReferenceEntry>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v22 + 24LL))(v22, v45, &v53);
  if ( ApplicationManifest < 0 )
  {
    v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    v50 = &Dfdll::CObject::`vftable';
    v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v53 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
    v53 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v26 = v53;
  v27 = v53;
  v28 = v51;
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v26 = v53;
  }
  v29 = 0;
  v51 = 0;
  if ( !v27 )
  {
    ApplicationManifest = -2147467261;
    goto LABEL_326;
  }
  v30 = *v27;
  v31 = ((__int64 (__fastcall *)(void ***, __int64, _QWORD))v50[5])(&v50, v28, 0);
  v32 = (*v30)(v27, v31, &v51);
  ApplicationManifest = v32;
  v29 = v51;
  if ( v32 < 0 )
    v29 = 0;
  v51 = v29;
  if ( v32 < 0 )
  {
    v26 = v53;
LABEL_326:
    v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v29 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v26 = v53;
    }
    v51 = 0;
    v50 = &Dfdll::CObject::`vftable';
    v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v26 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v26)[2])(v26);
    v53 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v57 = 0;
  v56 = &Dfdll::CIUnknownBasedPointer<IAssemblyReferenceDependentAssemblyEntry>::`vftable';
  pv = 0;
  v61 = 0;
  v60 = 0;
  v58 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v57);
  if ( ApplicationManifest < 0 )
  {
    v58 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v61 = 0;
    v60 = 0;
    v58 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
    v56 = &Dfdll::CObject::`vftable';
    v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    v50 = &Dfdll::CObject::`vftable';
    v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v53 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
    v53 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  ApplicationManifest = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v57 + 40LL))(v57, &pv);
  if ( ApplicationManifest < 0 )
  {
    v58 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v61 = 0;
    v60 = 0;
    v58 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
    v56 = &Dfdll::CObject::`vftable';
    v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    v50 = &Dfdll::CObject::`vftable';
    v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v53 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
    v53 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  if ( !pv )
  {
    ApplicationManifest = -2147024883;
    pv = 0;
    v61 = 0;
    v60 = 0;
    v58 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
    v56 = &Dfdll::CObject::`vftable';
    v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    v50 = &Dfdll::CObject::`vftable';
    v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v53 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
    v53 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v68 = 0;
  v63 = 0;
  v65 = 0;
  v64 = 0;
  v62 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
  ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *, unsigned __int16 **))(**((_QWORD **)this + 16) + 144LL))(
                          *((_QWORD *)this + 16),
                          0,
                          *((_QWORD *)this + 10),
                          &v68,
                          &v63);
  if ( ApplicationManifest < 0 )
  {
    v62 = &Dfdll::CCOMPointerBase::`vftable';
    if ( v63 )
      CoTaskMemFree(v63);
    v63 = 0;
    v65 = 0;
    v64 = 0;
    v62 = &Dfdll::CObject::`vftable';
    v58 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v61 = 0;
    v60 = 0;
    v58 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
    v56 = &Dfdll::CObject::`vftable';
    v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    v50 = &Dfdll::CObject::`vftable';
    v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v53 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
    v53 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 16) + 152LL))(
                          *((_QWORD *)this + 16),
                          v68);
  if ( ApplicationManifest < 0 )
  {
    v62 = &Dfdll::CCOMPointerBase::`vftable';
    if ( v63 )
      CoTaskMemFree(v63);
    v63 = 0;
    v65 = 0;
    v64 = 0;
    v62 = &Dfdll::CObject::`vftable';
    v58 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v61 = 0;
    v60 = 0;
    v58 = &Dfdll::CObject::`vftable';
    v56 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
    v56 = &Dfdll::CObject::`vftable';
    v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    v50 = &Dfdll::CObject::`vftable';
    v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v53 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
    v53 = 0;
    v52 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v49 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
    v49 = 0;
    v48 = &Dfdll::CObject::`vftable';
    v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
    v44 = &Dfdll::CObject::`vftable';
    v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
    v40 = &Dfdll::CObject::`vftable';
    v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
    v43 = 0;
    v42 = &Dfdll::CObject::`vftable';
    v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
    v36 = &Dfdll::CObject::`vftable';
    v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v39 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
    v39 = 0;
    v38 = &Dfdll::CObject::`vftable';
    v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)ApplicationManifest;
  }
  v33 = (unsigned __int16 *)pv;
  v34 = v63;
  if ( v63 && pv )
  {
    ApplicationManifest = Dfdll::CString::Assign(a2, v63);
    if ( ApplicationManifest >= 0 )
    {
      ApplicationManifest = Dfdll::CPath::PathAddTail(a2, v33);
      if ( ApplicationManifest >= 0 )
      {
        ApplicationManifest = 0;
        v62 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v63 )
          CoTaskMemFree(v63);
        v63 = 0;
        v65 = 0;
        v64 = 0;
        v62 = &Dfdll::CObject::`vftable';
        v58 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v61 = 0;
        v60 = 0;
        v58 = &Dfdll::CObject::`vftable';
        v56 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v57 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        v57 = 0;
        v56 = &Dfdll::CObject::`vftable';
        v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
        v50 = &Dfdll::CObject::`vftable';
        v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v53 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
        v53 = 0;
        v52 = &Dfdll::CObject::`vftable';
        v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        v47 = 0;
        v46 = &Dfdll::CObject::`vftable';
        v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v49 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
        v49 = 0;
        v48 = &Dfdll::CObject::`vftable';
        v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v45 = 0;
        v44 = &Dfdll::CObject::`vftable';
        v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        v41 = 0;
        v40 = &Dfdll::CObject::`vftable';
        v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v43 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
        v43 = 0;
        v42 = &Dfdll::CObject::`vftable';
        v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        v37 = 0;
        v36 = &Dfdll::CObject::`vftable';
        v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v39 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
        v39 = 0;
        v38 = &Dfdll::CObject::`vftable';
        v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v55 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
        return (unsigned int)ApplicationManifest;
      }
    }
    v33 = (unsigned __int16 *)pv;
    v34 = v63;
  }
  else
  {
    ApplicationManifest = -2147024809;
  }
  v62 = &Dfdll::CCOMPointerBase::`vftable';
  if ( v34 )
  {
    CoTaskMemFree(v34);
    v33 = (unsigned __int16 *)pv;
  }
  v63 = 0;
  v65 = 0;
  v64 = 0;
  v62 = &Dfdll::CObject::`vftable';
  v58 = &Dfdll::CCOMPointerBase::`vftable';
  if ( v33 )
    CoTaskMemFree(v33);
  pv = 0;
  v61 = 0;
  v60 = 0;
  v58 = &Dfdll::CObject::`vftable';
  v56 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  v57 = 0;
  v56 = &Dfdll::CObject::`vftable';
  v50 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  v51 = 0;
  v50 = &Dfdll::CObject::`vftable';
  v52 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v53 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v53)[2])(v53);
  v53 = 0;
  v52 = &Dfdll::CObject::`vftable';
  v46 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  v47 = 0;
  v46 = &Dfdll::CObject::`vftable';
  v48 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v49 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v49)[2])(v49);
  v49 = 0;
  v48 = &Dfdll::CObject::`vftable';
  v44 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  v45 = 0;
  v44 = &Dfdll::CObject::`vftable';
  v40 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  v41 = 0;
  v40 = &Dfdll::CObject::`vftable';
  v42 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v43 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v43)[2])(v43);
  v43 = 0;
  v42 = &Dfdll::CObject::`vftable';
  v36 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  v37 = 0;
  v36 = &Dfdll::CObject::`vftable';
  v38 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v39 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v39)[2])(v39);
  v39 = 0;
  v38 = &Dfdll::CObject::`vftable';
  v54 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  return (unsigned int)ApplicationManifest;
}

```

## disassembly

```asm
0x18000ab8c  mov     [rsp-8+arg_8], rbx
0x18000ab91  push    rbp
0x18000ab92  push    rsi
0x18000ab93  push    rdi
0x18000ab94  push    r12
0x18000ab96  push    r13
0x18000ab98  push    r14
0x18000ab9a  push    r15
0x18000ab9c  lea     rbp, [rsp-10h]
0x18000aba1  sub     rsp, 110h
0x18000aba8  mov     r15, rdx
0x18000abab  mov     rdi, rcx
0x18000abae  xor     r12d, r12d
0x18000abb1  cmp     [rcx+40h], r12
0x18000abb5  jnz     short loc_18000ABC1
0x18000abb7  mov     esi, 800703EBh
0x18000abbc  jmp     loc_18000C7E1
0x18000abc1  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000abc6  mov     esi, eax
0x18000abc8  test    eax, eax
0x18000abca  js      loc_18000C7E1
0x18000abd0  mov     r14d, 1
0x18000abd6  mov     [rbp+40h+arg_0], r14d
0x18000abda  lea     rdx, [rbp+40h+arg_0]; int *
0x18000abde  mov     rcx, rdi; this
0x18000abe1  call    ?CheckShellVisibility@CSubscription@Dfdll@@IEAAJAEAH@Z; Dfdll::CSubscription::CheckShellVisibility(int &)
0x18000abe6  mov     esi, eax
0x18000abe8  test    eax, eax
0x18000abea  js      loc_18000C7E1
0x18000abf0  cmp     [rbp+40h+arg_0], r12d
0x18000abf4  jz      short loc_18000ABB7
0x18000abf6  cmp     [rdi+0B0h], r12
0x18000abfd  jnz     short loc_18000AC11
0x18000abff  mov     rcx, rdi; this
0x18000ac02  call    ?LoadApplicationManifest@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadApplicationManifest(void)
0x18000ac07  mov     esi, eax
0x18000ac09  test    eax, eax
0x18000ac0b  js      loc_18000C7E1
0x18000ac11  mov     [rbp+40h+var_78], r12
0x18000ac15  lea     rax, ??_7?$CIUnknownBasedPointer@UISection@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<ISection>::`vftable'
0x18000ac1c  mov     [rbp+40h+var_80], rax
0x18000ac20  mov     rcx, [rdi+0B0h]
0x18000ac27  mov     rax, [rcx]
0x18000ac2a  lea     rdx, [rbp+40h+var_78]
0x18000ac2e  mov     rax, [rax+60h]
0x18000ac32  call    cs:__guard_dispatch_icall_fptr
0x18000ac38  mov     esi, eax
0x18000ac3a  test    eax, eax
0x18000ac3c  jns     short loc_18000AC65
0x18000ac3e  lea     rbx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000ac45  mov     [rbp+40h+var_80], rbx
0x18000ac49  mov     rcx, [rbp+40h+var_78]
0x18000ac4d  test    rcx, rcx
0x18000ac50  jz      short loc_18000AC60
0x18000ac52  mov     rax, [rcx]
0x18000ac55  mov     rax, [rax+10h]
0x18000ac59  call    cs:__guard_dispatch_icall_fptr
0x18000ac5f  nop
0x18000ac60  jmp     loc_18000C7E1
0x18000ac65  mov     rcx, [rbp+40h+var_78]
0x18000ac69  test    rcx, rcx
0x18000ac6c  jnz     short loc_18000AC78
0x18000ac6e  mov     esi, 8007000Dh
0x18000ac73  jmp     loc_18000C7E1
0x18000ac78  mov     [rsp+140h+var_F8], r12
0x18000ac7d  lea     r13, ??_7?$CIUnknownBasedPointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable'
0x18000ac84  mov     [rsp+140h+var_100], r13
0x18000ac89  mov     [rsp+140h+var_108], r12
0x18000ac8e  lea     rax, ??_7?$CIUnknownBasedPointer@UIEnumUnknown@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IEnumUnknown>::`vftable'
0x18000ac95  mov     [rsp+140h+var_110], rax
0x18000ac9a  mov     rax, [rcx]
0x18000ac9d  lea     rdx, [rsp+140h+var_F8]
0x18000aca2  mov     rax, [rax+18h]
0x18000aca6  call    cs:__guard_dispatch_icall_fptr
0x18000acac  mov     esi, eax
0x18000acae  test    eax, eax
0x18000acb0  jns     short loc_18000AD2C
0x18000acb2  lea     rbx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000acb9  mov     [rsp+140h+var_110], rbx
0x18000acbe  mov     rcx, [rsp+140h+var_108]
0x18000acc3  test    rcx, rcx
0x18000acc6  jz      short loc_18000ACD5
0x18000acc8  mov     rax, [rcx]
0x18000accb  mov     rax, [rax+10h]
0x18000accf  call    cs:__guard_dispatch_icall_fptr
0x18000acd5  mov     [rsp+140h+var_108], r12
0x18000acda  lea     rdi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000ace1  mov     [rsp+140h+var_110], rdi
0x18000ace6  mov     [rsp+140h+var_100], rbx
0x18000aceb  mov     rcx, [rsp+140h+var_F8]
0x18000acf0  test    rcx, rcx
0x18000acf3  jz      short loc_18000AD02
0x18000acf5  mov     rax, [rcx]
0x18000acf8  mov     rax, [rax+10h]
0x18000acfc  call    cs:__guard_dispatch_icall_fptr
0x18000ad02  mov     [rsp+140h+var_F8], r12
0x18000ad07  mov     [rsp+140h+var_100], rdi
0x18000ad0c  mov     [rbp+40h+var_80], rbx
0x18000ad10  mov     rcx, [rbp+40h+var_78]
0x18000ad14  test    rcx, rcx
0x18000ad17  jz      short loc_18000AD27
0x18000ad19  mov     rax, [rcx]
0x18000ad1c  mov     rax, [rax+10h]
0x18000ad20  call    cs:__guard_dispatch_icall_fptr
0x18000ad26  nop
0x18000ad27  jmp     loc_18000C7E1
0x18000ad2c  mov     rcx, [rsp+140h+var_F8]
0x18000ad31  mov     rsi, rcx
0x18000ad34  mov     rdx, [rsp+140h+var_108]
0x18000ad39  test    rdx, rdx
0x18000ad3c  jz      short loc_18000AD53
0x18000ad3e  mov     rax, [rdx]
0x18000ad41  mov     rcx, rdx
0x18000ad44  mov     rax, [rax+10h]
0x18000ad48  call    cs:__guard_dispatch_icall_fptr
0x18000ad4e  mov     rcx, [rsp+140h+var_F8]
0x18000ad53  mov     r10, r12
0x18000ad56  mov     [rsp+140h+var_108], r12
0x18000ad5b  test    rsi, rsi
0x18000ad5e  jz      loc_18000C769
0x18000ad64  mov     rbx, [rsi]
0x18000ad67  mov     rax, [rsp+140h+var_110]
0x18000ad6c  lea     rcx, [rsp+140h+var_110]
0x18000ad71  mov     rax, [rax+28h]
0x18000ad75  call    cs:__guard_dispatch_icall_fptr
0x18000ad7b  mov     rdx, rax
0x18000ad7e  lea     r8, [rsp+140h+var_108]
0x18000ad83  mov     rcx, rsi
0x18000ad86  mov     rax, [rbx]
0x18000ad89  call    cs:__guard_dispatch_icall_fptr
0x18000ad8f  mov     esi, eax
0x18000ad91  mov     r10, [rsp+140h+var_108]
0x18000ad96  test    eax, eax
0x18000ad98  cmovs   r10, r12
0x18000ad9c  mov     [rsp+140h+var_108], r10
0x18000ada1  js      loc_18000C762
0x18000ada7  mov     [rsp+140h+var_D8], r12
0x18000adac  mov     [rsp+140h+var_E0], r13
0x18000adb1  mov     [rsp+140h+var_E8], r12
0x18000adb6  lea     rax, ??_7?$CIUnknownBasedPointer@UIEntryPointEntry@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IEntryPointEntry>::`vftable'
0x18000adbd  mov     [rsp+140h+var_F0], rax
0x18000adc2  mov     rax, [r10]
0x18000adc5  lea     r9, [rbp+40h+arg_10]
0x18000adc9  lea     r8, [rsp+140h+var_D8]
0x18000adce  mov     edx, r14d
0x18000add1  mov     rcx, r10
0x18000add4  mov     rax, [rax+18h]
0x18000add8  call    cs:__guard_dispatch_icall_fptr
0x18000adde  mov     esi, eax
0x18000ade0  test    eax, eax
0x18000ade2  jns     loc_18000AEAE
0x18000ade8  lea     rbx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000adef  mov     [rsp+140h+var_F0], rbx
0x18000adf4  mov     rcx, [rsp+140h+var_E8]
0x18000adf9  test    rcx, rcx
0x18000adfc  jz      short loc_18000AE0B
0x18000adfe  mov     rax, [rcx]
0x18000ae01  mov     rax, [rax+10h]
0x18000ae05  call    cs:__guard_dispatch_icall_fptr
0x18000ae0b  mov     [rsp+140h+var_E8], r12
0x18000ae10  lea     rdi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000ae17  mov     [rsp+140h+var_F0], rdi
0x18000ae1c  mov     [rsp+140h+var_E0], rbx
0x18000ae21  mov     rcx, [rsp+140h+var_D8]
0x18000ae26  test    rcx, rcx
0x18000ae29  jz      short loc_18000AE38
0x18000ae2b  mov     rax, [rcx]
0x18000ae2e  mov     rax, [rax+10h]
0x18000ae32  call    cs:__guard_dispatch_icall_fptr
0x18000ae38  mov     [rsp+140h+var_D8], r12
0x18000ae3d  mov     [rsp+140h+var_E0], rdi
0x18000ae42  mov     [rsp+140h+var_110], rbx
0x18000ae47  mov     rcx, [rsp+140h+var_108]
0x18000ae4c  test    rcx, rcx
0x18000ae4f  jz      short loc_18000AE5E
0x18000ae51  mov     rax, [rcx]
0x18000ae54  mov     rax, [rax+10h]
0x18000ae58  call    cs:__guard_dispatch_icall_fptr
0x18000ae5e  mov     [rsp+140h+var_108], r12
0x18000ae63  mov     [rsp+140h+var_110], rdi
0x18000ae68  mov     [rsp+140h+var_100], rbx
0x18000ae6d  mov     rcx, [rsp+140h+var_F8]
0x18000ae72  test    rcx, rcx
0x18000ae75  jz      short loc_18000AE84
0x18000ae77  mov     rax, [rcx]
0x18000ae7a  mov     rax, [rax+10h]
0x18000ae7e  call    cs:__guard_dispatch_icall_fptr
0x18000ae84  mov     [rsp+140h+var_F8], r12
0x18000ae89  mov     [rsp+140h+var_100], rdi
0x18000ae8e  mov     [rbp+40h+var_80], rbx
0x18000ae92  mov     rcx, [rbp+40h+var_78]
0x18000ae96  test    rcx, rcx
0x18000ae99  jz      short loc_18000AEA9
0x18000ae9b  mov     rax, [rcx]
0x18000ae9e  mov     rax, [rax+10h]
0x18000aea2  call    cs:__guard_dispatch_icall_fptr
0x18000aea8  nop
0x18000aea9  jmp     loc_18000C7E1
0x18000aeae  cmp     [rbp+40h+arg_10], r14d
0x18000aeb2  jnb     loc_18000AF83
0x18000aeb8  mov     esi, 8007000Dh
0x18000aebd  lea     rbx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000aec4  mov     [rsp+140h+var_F0], rbx
0x18000aec9  mov     rcx, [rsp+140h+var_E8]
0x18000aece  test    rcx, rcx
0x18000aed1  jz      short loc_18000AEE0
0x18000aed3  mov     rax, [rcx]
0x18000aed6  mov     rax, [rax+10h]
0x18000aeda  call    cs:__guard_dispatch_icall_fptr
0x18000aee0  mov     [rsp+140h+var_E8], r12
0x18000aee5  lea     rdi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000aeec  mov     [rsp+140h+var_F0], rdi
0x18000aef1  mov     [rsp+140h+var_E0], rbx
0x18000aef6  mov     rcx, [rsp+140h+var_D8]
0x18000aefb  test    rcx, rcx
0x18000aefe  jz      short loc_18000AF0D
0x18000af00  mov     rax, [rcx]
0x18000af03  mov     rax, [rax+10h]
0x18000af07  call    cs:__guard_dispatch_icall_fptr
0x18000af0d  mov     [rsp+140h+var_D8], r12
0x18000af12  mov     [rsp+140h+var_E0], rdi
0x18000af17  mov     [rsp+140h+var_110], rbx
0x18000af1c  mov     rcx, [rsp+140h+var_108]
0x18000af21  test    rcx, rcx
0x18000af24  jz      short loc_18000AF33
0x18000af26  mov     rax, [rcx]
0x18000af29  mov     rax, [rax+10h]
0x18000af2d  call    cs:__guard_dispatch_icall_fptr
0x18000af33  mov     [rsp+140h+var_108], r12
0x18000af38  mov     [rsp+140h+var_110], rdi
0x18000af3d  mov     [rsp+140h+var_100], rbx
0x18000af42  mov     rcx, [rsp+140h+var_F8]
0x18000af47  test    rcx, rcx
0x18000af4a  jz      short loc_18000AF59
0x18000af4c  mov     rax, [rcx]
0x18000af4f  mov     rax, [rax+10h]
0x18000af53  call    cs:__guard_dispatch_icall_fptr
0x18000af59  mov     [rsp+140h+var_F8], r12
0x18000af5e  mov     [rsp+140h+var_100], rdi
0x18000af63  mov     [rbp+40h+var_80], rbx
0x18000af67  mov     rcx, [rbp+40h+var_78]
0x18000af6b  test    rcx, rcx
0x18000af6e  jz      short loc_18000AF7E
0x18000af70  mov     rax, [rcx]
0x18000af73  mov     rax, [rax+10h]
0x18000af77  call    cs:__guard_dispatch_icall_fptr
0x18000af7d  nop
0x18000af7e  jmp     loc_18000C7E1
0x18000af83  mov     rcx, [rsp+140h+var_D8]
0x18000af88  mov     rsi, rcx
0x18000af8b  mov     rdx, [rsp+140h+var_E8]
0x18000af90  test    rdx, rdx
0x18000af93  jz      short loc_18000AFAA
0x18000af95  mov     rax, [rdx]
0x18000af98  mov     rcx, rdx
0x18000af9b  mov     rax, [rax+10h]
0x18000af9f  call    cs:__guard_dispatch_icall_fptr
0x18000afa5  mov     rcx, [rsp+140h+var_D8]
0x18000afaa  mov     r8, r12
0x18000afad  mov     [rsp+140h+var_E8], r12
0x18000afb2  test    rsi, rsi
0x18000afb5  jz      loc_18000C69C
0x18000afbb  mov     rbx, [rsi]
0x18000afbe  mov     rax, [rsp+140h+var_F0]
0x18000afc3  lea     rcx, [rsp+140h+var_F0]
0x18000afc8  mov     rax, [rax+28h]
0x18000afcc  call    cs:__guard_dispatch_icall_fptr
0x18000afd2  mov     rdx, rax
0x18000afd5  lea     r8, [rsp+140h+var_E8]
0x18000afda  mov     rcx, rsi
0x18000afdd  mov     rax, [rbx]
0x18000afe0  call    cs:__guard_dispatch_icall_fptr
0x18000afe6  mov     esi, eax
0x18000afe8  mov     r8, [rsp+140h+var_E8]
0x18000afed  test    eax, eax
0x18000afef  cmovs   r8, r12
0x18000aff3  mov     [rsp+140h+var_E8], r8
0x18000aff8  js      loc_18000C695
0x18000affe  mov     [rsp+140h+var_C8], r12
0x18000b003  lea     rax, ??_7?$CIUnknownBasedPointer@UIReferenceIdentity@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IReferenceIdentity>::`vftable'
0x18000b00a  mov     [rsp+140h+var_D0], rax
0x18000b00f  mov     rax, [r8]
0x18000b012  lea     rdx, [rsp+140h+var_C8]
0x18000b017  mov     rcx, r8
0x18000b01a  mov     rax, [rax+38h]
0x18000b01e  call    cs:__guard_dispatch_icall_fptr
0x18000b024  mov     esi, eax
0x18000b026  test    eax, eax
0x18000b028  jns     loc_18000B11A
0x18000b02e  lea     rbx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000b035  mov     [rsp+140h+var_D0], rbx
0x18000b03a  mov     rcx, [rsp+140h+var_C8]
0x18000b03f  test    rcx, rcx
0x18000b042  jz      short loc_18000B051
0x18000b044  mov     rax, [rcx]
0x18000b047  mov     rax, [rax+10h]
0x18000b04b  call    cs:__guard_dispatch_icall_fptr
0x18000b051  mov     [rsp+140h+var_C8], r12
0x18000b056  lea     rdi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000b05d  mov     [rsp+140h+var_D0], rdi
  ... truncated ...
```
