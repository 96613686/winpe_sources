# Dfdll::CSubscription::LoadDeploymentDataFromManifest(ushort const *,ushort const *,ushort *,ulong *,ushort *,ulong *,ushort *,ulong *,ushort *,ulong *)

- ea: `0x18000dadc`
- end: `0x180010bf2`
- name: `?LoadDeploymentDataFromManifest@CSubscription@Dfdll@@QEAAJPEBG0PEAGPEAK121212@Z`
- size: `12566`
- prototype: `__int64 __usercall@<rax>(Dfdll::CSubscription *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned int *, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007040`

## callees

- `0x180001a64`
- `0x180002604`
- `0x180002af8`
- `0x180007710`
- `0x180008b4c`
- `0x1800093b0`
- `0x18000a040`
- `0x18000dadc`
- `0x180011a8c`
- `0x180012b30`
- `0x18001efd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000de02`
- `ole32!CoTaskMemFree` at `0x18000dfb8`
- `ole32!CoTaskMemFree` at `0x18000e09f`
- `ole32!CoTaskMemFree` at `0x18000e1df`
- `ole32!CoTaskMemFree` at `0x18000e30f`
- `ole32!CoTaskMemFree` at `0x18000e428`
- `ole32!CoTaskMemFree` at `0x18000e5b4`
- `ole32!CoTaskMemFree` at `0x18000e801`
- `ole32!CoTaskMemFree` at `0x18000e9a4`
- `ole32!CoTaskMemFree` at `0x18000ebce`
- `ole32!CoTaskMemFree` at `0x18000ece7`
- `ole32!CoTaskMemFree` at `0x18000ede8`
- `ole32!CoTaskMemFree` at `0x18000eedd`
- `ole32!CoTaskMemFree` at `0x18000efde`
- `ole32!CoTaskMemFree` at `0x18000f101`
- `ole32!CoTaskMemFree` at `0x18000f202`
- `ole32!CoTaskMemFree` at `0x18000f30f`
- `ole32!CoTaskMemFree` at `0x18000f410`
- `ole32!CoTaskMemFree` at `0x18000f53a`
- `ole32!CoTaskMemFree` at `0x18000f63b`
- `ole32!CoTaskMemFree` at `0x18000f70d`
- `ole32!CoTaskMemFree` at `0x18000f782`
- `ole32!CoTaskMemFree` at `0x18000f883`
- `ole32!CoTaskMemFree` at `0x18000f975`
- `ole32!CoTaskMemFree` at `0x18000f9ea`
- `ole32!CoTaskMemFree` at `0x18000faeb`
- `ole32!CoTaskMemFree` at `0x18000fbf0`
- `ole32!CoTaskMemFree` at `0x18001099c`
- `ole32!CoTaskMemFree` at `0x180010af3`
- `ole32!CoTaskMemFree` at `0x18000de02`
- `ole32!CoTaskMemFree` at `0x18000dfb8`
- `ole32!CoTaskMemFree` at `0x18000e09f`
- `ole32!CoTaskMemFree` at `0x18000e1df`
- `ole32!CoTaskMemFree` at `0x18000e30f`
- `ole32!CoTaskMemFree` at `0x18000e428`
- `ole32!CoTaskMemFree` at `0x18000e5b4`
- `ole32!CoTaskMemFree` at `0x18000e801`
- `ole32!CoTaskMemFree` at `0x18000e9a4`
- `ole32!CoTaskMemFree` at `0x18000ebce`
- `ole32!CoTaskMemFree` at `0x18000ece7`
- `ole32!CoTaskMemFree` at `0x18000ede8`
- `ole32!CoTaskMemFree` at `0x18000eedd`
- `ole32!CoTaskMemFree` at `0x18000efde`
- `ole32!CoTaskMemFree` at `0x18000f101`
- `ole32!CoTaskMemFree` at `0x18000f202`
- `ole32!CoTaskMemFree` at `0x18000f30f`
- `ole32!CoTaskMemFree` at `0x18000f410`
- `ole32!CoTaskMemFree` at `0x18000f53a`
- `ole32!CoTaskMemFree` at `0x18000f63b`
- `ole32!CoTaskMemFree` at `0x18000f70d`
- `ole32!CoTaskMemFree` at `0x18000f782`
- `ole32!CoTaskMemFree` at `0x18000f883`
- `ole32!CoTaskMemFree` at `0x18000f975`
- `ole32!CoTaskMemFree` at `0x18000f9ea`
- `ole32!CoTaskMemFree` at `0x18000faeb`
- `ole32!CoTaskMemFree` at `0x18000fbf0`
- `ole32!CoTaskMemFree` at `0x18001099c`
- `ole32!CoTaskMemFree` at `0x180010af3`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
__int64 __fastcall Dfdll::CSubscription::LoadDeploymentDataFromManifest(
        Dfdll::CSubscription *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        unsigned int *a7,
        unsigned __int16 *a8,
        unsigned int *a9,
        unsigned __int16 *a10,
        unsigned int *a11)
{
  unsigned int *v14; // r13
  unsigned int *v15; // r12
  int v16; // esi
  __int64 (__fastcall ***v17)(__int64, __int64, __int64 *); // rcx
  __int64 (__fastcall ***v18)(__int64, __int64, __int64 *); // rdi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 (__fastcall **v21)(__int64, __int64, __int64 *); // rbx
  __int64 v22; // rax
  int v23; // eax
  const struct std::nothrow_t *v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  const struct std::nothrow_t *v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  __int64 (__fastcall ***v28)(_QWORD, __int64, _QWORD *); // rcx
  __int64 (__fastcall ***v29)(_QWORD, __int64, const struct std::nothrow_t **); // rdi
  const struct std::nothrow_t *v30; // rdx
  const struct std::nothrow_t *v31; // r10
  __int64 (__fastcall **v32)(_QWORD, __int64, const struct std::nothrow_t **); // rbx
  __int64 v33; // rax
  int v34; // eax
  const struct std::nothrow_t *v35; // rdx
  __int64 (__fastcall ***v36)(_QWORD, __int64, _QWORD *); // rcx
  __int64 (__fastcall ***v37)(_QWORD, __int64, const struct std::nothrow_t **); // rdi
  const struct std::nothrow_t *v38; // rdx
  const struct std::nothrow_t *v39; // r8
  __int64 (__fastcall **v40)(_QWORD, __int64, const struct std::nothrow_t **); // rbx
  __int64 v41; // rax
  int v42; // eax
  char v43; // bl
  unsigned int *v44; // r8
  unsigned __int16 *v45; // r12
  int v46; // eax
  unsigned __int16 *v47; // r15
  int v48; // eax
  unsigned __int16 *v49; // rdi
  int v50; // eax
  unsigned __int16 *v51; // r14
  void **v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+38h] [rbp-C8h] BYREF
  void **v55; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+48h] [rbp-B8h] BYREF
  void **v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  void **v59; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v61; // [rsp+70h] [rbp-90h]
  char v62; // [rsp+74h] [rbp-8Ch]
  void **v63; // [rsp+78h] [rbp-88h] BYREF
  const struct std::nothrow_t *v64; // [rsp+80h] [rbp-80h] BYREF
  void **v65; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, __int64, _QWORD *); // [rsp+90h] [rbp-70h] BYREF
  void **v67; // [rsp+98h] [rbp-68h] BYREF
  const struct std::nothrow_t *v68; // [rsp+A0h] [rbp-60h] BYREF
  void **v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v70)(_QWORD, __int64, _QWORD *); // [rsp+B0h] [rbp-50h] BYREF
  void **v71; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall ***v72)(__int64, __int64, __int64 *); // [rsp+C0h] [rbp-40h] BYREF
  void **v73; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v74; // [rsp+D0h] [rbp-30h] BYREF
  void **v75; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+E0h] [rbp-20h] BYREF
  void **v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-10h] BYREF
  void **v79; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v80; // [rsp+100h] [rbp+0h] BYREF
  int v81; // [rsp+108h] [rbp+8h]
  char v82; // [rsp+10Ch] [rbp+Ch]
  void **v83; // [rsp+110h] [rbp+10h] BYREF
  void **v84; // [rsp+118h] [rbp+18h]
  void *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+130h] [rbp+30h]
  void **v88; // [rsp+138h] [rbp+38h] BYREF
  __int64 v89; // [rsp+140h] [rbp+40h] BYREF
  void **v90; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 *v91; // [rsp+150h] [rbp+50h] BYREF
  int v92; // [rsp+158h] [rbp+58h]
  char v93; // [rsp+15Ch] [rbp+5Ch]
  void **v94; // [rsp+160h] [rbp+60h] BYREF
  __int64 v95; // [rsp+168h] [rbp+68h] BYREF
  void **v96; // [rsp+170h] [rbp+70h] BYREF
  __int64 v97; // [rsp+178h] [rbp+78h]
  void **v98; // [rsp+180h] [rbp+80h] BYREF
  __int64 v99; // [rsp+188h] [rbp+88h] BYREF
  void **v100; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 *v101; // [rsp+198h] [rbp+98h] BYREF
  int v102; // [rsp+1A0h] [rbp+A0h]
  char v103; // [rsp+1A4h] [rbp+A4h]
  _QWORD v104[3]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v105; // [rsp+1C0h] [rbp+C0h]
  int v106; // [rsp+1C8h] [rbp+C8h]
  void **v107; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 *v108; // [rsp+1D8h] [rbp+D8h] BYREF
  int v109; // [rsp+1E0h] [rbp+E0h]
  char v110; // [rsp+1E4h] [rbp+E4h]
  _QWORD v111[3]; // [rsp+1E8h] [rbp+E8h] BYREF
  int v112; // [rsp+200h] [rbp+100h]
  int v113; // [rsp+208h] [rbp+108h]
  int v114; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v115[3]; // [rsp+218h] [rbp+118h] BYREF
  int v116; // [rsp+230h] [rbp+130h]
  int v117; // [rsp+238h] [rbp+138h]
  _QWORD v118[8]; // [rsp+240h] [rbp+140h] BYREF
  int v119; // [rsp+298h] [rbp+198h] BYREF
  unsigned __int16 *v120; // [rsp+2A8h] [rbp+1A8h]

  v120 = a4;
  if ( !a2
    || !*a2
    || !a3
    || !*a3
    || !a4
    || (v14 = a5) == 0
    || *a5 <= 1
    || !a6
    || (v15 = a7) == 0
    || *a7 <= 1
    || !a8
    || !a9
    || *a9 <= 1
    || !a10
    || !a11
    || *a11 <= 1 )
  {
    return (unsigned int)-2147024809;
  }
  v16 = Dfdll::CSubscription::Reset(this);
  if ( v16 < 0 )
    return (unsigned int)v16;
  v16 = Dfdll::CSubscription::EnsureInitialization(this);
  if ( v16 < 0 )
    return (unsigned int)v16;
  v72 = 0;
  v71 = &Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable';
  v54 = 0;
  v53 = &Dfdll::CIUnknownBasedPointer<ICMS>::`vftable';
  v16 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, GUID *, __int64 (__fastcall ****)(__int64, __int64, __int64 *)))Dfdll::CSubscription::_pfnParseManifest)(
          a3,
          0,
          &GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033,
          &v72);
  if ( v16 < 0 )
  {
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v17 = v72;
  v18 = v72;
  v19 = v54;
  v20 = 0;
  v54 = 0;
  if ( !v72 )
  {
    v16 = -2147467261;
    goto LABEL_607;
  }
  v21 = *v72;
  v22 = ((__int64 (__fastcall *)(void ***, __int64, _QWORD))v53[5])(&v53, v19, 0);
  v23 = (*v21)((__int64)v18, v22, &v54);
  v16 = v23;
  v20 = v54;
  if ( v23 < 0 )
    v20 = 0;
  v54 = v20;
  if ( v23 < 0 )
  {
    v17 = v72;
LABEL_607:
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v17 = v72;
    }
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v17 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v17)[2])(v17);
    return (unsigned int)v16;
  }
  v56 = 0;
  v55 = &Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable';
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 24LL))(v20, &v56);
  if ( v16 < 0 )
  {
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  pv = 0;
  v62 = 0;
  v61 = 0;
  v59 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, LPVOID *))(*(_QWORD *)v56 + 24LL))(
          v56,
          0,
          L"processorArchitecture",
          &pv);
  if ( v16 < 0 )
  {
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  if ( !pv )
  {
    v16 = -2147024883;
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v83 = &Dfdll::CString::`vftable';
  v85 = 0;
  v86 = 0;
  v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v87 = 0;
  v16 = Dfdll::CString::Assign((Dfdll::CString *)&v83, (const unsigned __int16 *)pv);
  if ( v16 < 0 )
  {
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v24);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  if ( !v87 )
  {
    v16 = -2147024883;
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v24);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v58 = 0;
  v57 = &Dfdll::CIUnknownBasedPointer<ISection>::`vftable';
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 72LL))(v54, &v58);
  if ( v16 < 0 )
  {
    v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v25);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v119 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v58 + 32LL))(v58, &v119);
  if ( v16 < 0 )
  {
    v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v26);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  if ( v119 != 1 )
  {
    v16 = -2147024883;
    v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v26);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v66 = 0;
  v65 = &Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable';
  v64 = 0;
  v63 = &Dfdll::CIUnknownBasedPointer<IEnumUnknown>::`vftable';
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(*(_QWORD *)v58 + 24LL))(
          v58,
          &v66);
  if ( v16 < 0 )
  {
    v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v64 )
      (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
    v63 = &Dfdll::CObject::`vftable';
    v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v66 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
    v66 = 0;
    v65 = &Dfdll::CObject::`vftable';
    v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v27);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v28 = v66;
  v29 = (__int64 (__fastcall ***)(_QWORD, __int64, const struct std::nothrow_t **))v66;
  v30 = v64;
  if ( v64 )
  {
    (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
    v28 = v66;
  }
  v31 = 0;
  v64 = 0;
  if ( !v29 )
  {
    v16 = -2147467261;
    goto LABEL_588;
  }
  v32 = *v29;
  v33 = ((__int64 (__fastcall *)(void ***))v63[5])(&v63);
  v34 = (*v32)(v29, v33, &v64);
  v16 = v34;
  v31 = v64;
  if ( v34 < 0 )
    v31 = 0;
  v64 = v31;
  if ( v34 < 0 )
  {
    v28 = v66;
LABEL_588:
    v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v31 )
    {
      (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v31 + 16LL))(v31);
      v28 = v66;
    }
    v64 = 0;
    v63 = &Dfdll::CObject::`vftable';
    v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v28 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v28)[2])(v28);
    v66 = 0;
    v65 = &Dfdll::CObject::`vftable';
    v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v30);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v70 = 0;
  v69 = &Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable';
  v68 = 0;
  v67 = &Dfdll::CIUnknownBasedPointer<IAssemblyReferenceEntry>::`vftable';
  v16 = (*(__int64 (__fastcall **)(const struct std::nothrow_t *, __int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *), int *))(*(_QWORD *)v31 + 24LL))(
          v31,
          1,
          &v70,
          &v114);
  if ( v16 < 0 )
  {
    v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v68 )
      (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
    v68 = 0;
    v67 = &Dfdll::CObject::`vftable';
    v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v70 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
    v70 = 0;
    v69 = &Dfdll::CObject::`vftable';
    v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v64 )
      (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
    v63 = &Dfdll::CObject::`vftable';
    v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v66 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
    v66 = 0;
    v65 = &Dfdll::CObject::`vftable';
    v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v35);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  if ( !v114 )
  {
    v16 = -2147024883;
    v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v68 )
      (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
    v68 = 0;
    v67 = &Dfdll::CObject::`vftable';
    v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v70 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
    v70 = 0;
    v69 = &Dfdll::CObject::`vftable';
    v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v64 )
      (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
    v63 = &Dfdll::CObject::`vftable';
    v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v66 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
    v66 = 0;
    v65 = &Dfdll::CObject::`vftable';
    v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
    v57 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CString::`vftable';
    v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v85 )
      operator delete(v85, v35);
    v85 = 0;
    v86 = 0;
    v84 = &Dfdll::CObject::`vftable';
    v83 = &Dfdll::CObject::`vftable';
    v59 = &Dfdll::CCOMPointerBase::`vftable';
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v62 = 0;
    v61 = 0;
    v59 = &Dfdll::CObject::`vftable';
    v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    v55 = &Dfdll::CObject::`vftable';
    v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
    v53 = &Dfdll::CObject::`vftable';
    v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v72 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
    return (unsigned int)v16;
  }
  v36 = v70;
  v37 = (__int64 (__fastcall ***)(_QWORD, __int64, const struct std::nothrow_t **))v70;
  v38 = v68;
  if ( v68 )
  {
    (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
    v36 = v70;
  }
  v39 = 0;
  v68 = 0;
  if ( v37 )
  {
    v40 = *v37;
    v41 = ((__int64 (__fastcall *)(void ***, const struct std::nothrow_t *, _QWORD))v67[5])(&v67, v38, 0);
    v42 = (*v40)(v37, v41, &v68);
    v16 = v42;
    v39 = v68;
    if ( v42 < 0 )
      v39 = 0;
    v68 = v39;
    if ( v42 >= 0 )
    {
      v74 = 0;
      v73 = &Dfdll::CIUnknownBasedPointer<IReferenceIdentity>::`vftable';
      v16 = (*(__int64 (__fastcall **)(const struct std::nothrow_t *, __int64 *))(*(_QWORD *)v39 + 32LL))(v39, &v74);
      if ( v16 < 0 )
      {
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v80 = 0;
      v82 = 0;
      v81 = 0;
      v79 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
      v76 = 0;
      v75 = &Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable';
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID *))(**((_QWORD **)this + 18) + 56LL))(
              *((_QWORD *)this + 18),
              0,
              v74,
              &v80);
      if ( v16 < 0 )
      {
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        v79 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v80 )
          CoTaskMemFree(v80);
        v80 = 0;
        v82 = 0;
        v81 = 0;
        v79 = &Dfdll::CObject::`vftable';
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, __int64 *))(**((_QWORD **)this + 18) + 24LL))(
              *((_QWORD *)this + 18),
              0,
              v80,
              &v76);
      if ( v16 < 0 )
      {
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        v79 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v80 )
          CoTaskMemFree(v80);
        v80 = 0;
        v82 = 0;
        v81 = 0;
        v79 = &Dfdll::CObject::`vftable';
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v78 = 0;
      v77 = &Dfdll::CIUnknownBasedPointer<IDefinitionAppId>::`vftable';
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 20) + 136LL))(
              *((_QWORD *)this + 20),
              &v78);
      if ( v16 < 0 )
      {
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        v79 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v80 )
          CoTaskMemFree(v80);
        v80 = 0;
        v82 = 0;
        v81 = 0;
        v79 = &Dfdll::CObject::`vftable';
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v78 + 48LL))(v78, a2);
      if ( v16 < 0 )
      {
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        v79 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v80 )
          CoTaskMemFree(v80);
        v80 = 0;
        v82 = 0;
        v81 = 0;
        v79 = &Dfdll::CObject::`vftable';
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v118[0] = v56;
      v118[1] = v76;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v78 + 64LL))(v78, 2, v118);
      if ( v16 < 0 )
      {
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        v79 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v80 )
          CoTaskMemFree(v80);
        v80 = 0;
        v82 = 0;
        v81 = 0;
        v79 = &Dfdll::CObject::`vftable';
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v91 = 0;
      v93 = 0;
      v92 = 0;
      v90 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 20) + 40LL))(
              *((_QWORD *)this + 20),
              0,
              v78,
              &v91);
      if ( v16 < 0 )
      {
        v90 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v91 )
          CoTaskMemFree(v91);
        v91 = 0;
        v93 = 0;
        v92 = 0;
        v90 = &Dfdll::CObject::`vftable';
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        v79 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v80 )
          CoTaskMemFree(v80);
        v80 = 0;
        v82 = 0;
        v81 = 0;
        v79 = &Dfdll::CObject::`vftable';
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v104[0] = &Dfdll::CString::`vftable';
      v104[2] = 0;
      v105 = 0;
      v104[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
      v106 = 0;
      v16 = Dfdll::CString::Assign((Dfdll::CString *)v104, v91);
      if ( v16 < 0 )
      {
        Dfdll::CString::~CString((Dfdll::CString *)v104);
        v90 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v91 )
          CoTaskMemFree(v91);
        v91 = 0;
        v93 = 0;
        v92 = 0;
        v90 = &Dfdll::CObject::`vftable';
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        v79 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v80 )
          CoTaskMemFree(v80);
        v80 = 0;
        v82 = 0;
        v81 = 0;
        v79 = &Dfdll::CObject::`vftable';
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        v59 = &Dfdll::CCOMPointerBase::`vftable';
        if ( pv )
          CoTaskMemFree(pv);
        pv = 0;
        v62 = 0;
        v61 = 0;
        v59 = &Dfdll::CObject::`vftable';
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v89 = 0;
      v88 = &Dfdll::CIUnknownBasedPointer<IAssemblyReferenceDependentAssemblyEntry>::`vftable';
      v16 = (*(__int64 (__fastcall **)(const struct std::nothrow_t *, __int64 *))(*(_QWORD *)v68 + 48LL))(v68, &v89);
      if ( v16 < 0 )
      {
        v88 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v89 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        v89 = 0;
        v88 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)v104);
        v90 = &Dfdll::CCOMPointerBase::`vftable';
        if ( v91 )
          CoTaskMemFree(v91);
        v91 = 0;
        v93 = 0;
        v92 = 0;
        v90 = &Dfdll::CObject::`vftable';
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v79);
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v59);
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      if ( !v89 )
      {
        v16 = -2147024883;
        v89 = 0;
        v88 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)v104);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v90);
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v79);
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v59);
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v101 = 0;
      v103 = 0;
      v102 = 0;
      v100 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
      v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v89 + 40LL))(v89, &v101);
      if ( v16 < 0 )
      {
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v100);
        v88 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v89 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        v89 = 0;
        v88 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)v104);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v90);
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v79);
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v59);
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      if ( !v101 )
      {
        v16 = -2147024883;
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v100);
        v88 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v89 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        v89 = 0;
        v88 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)v104);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v90);
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v79);
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v59);
        v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v56 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
        v55 = &Dfdll::CObject::`vftable';
        v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        v54 = 0;
        v53 = &Dfdll::CObject::`vftable';
        v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v72 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
        return (unsigned int)v16;
      }
      v111[0] = &Dfdll::CString::`vftable';
      v111[2] = 0;
      v112 = 0;
      v111[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
      v113 = 0;
      v16 = Dfdll::CString::Assign((Dfdll::CString *)v111, v101);
      if ( v16 < 0 )
      {
        Dfdll::CString::~CString((Dfdll::CString *)v111);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v100);
        v88 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v89 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        v89 = 0;
        v88 = &Dfdll::CObject::`vftable';
        Dfdll::CString::~CString((Dfdll::CString *)v104);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v90);
        v77 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
        v77 = &Dfdll::CObject::`vftable';
        v75 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v76 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        v76 = 0;
        v75 = &Dfdll::CObject::`vftable';
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v79);
        v73 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
        v73 = &Dfdll::CObject::`vftable';
        v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v68 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v68 + 16LL))(v68);
        v68 = 0;
        v67 = &Dfdll::CObject::`vftable';
        v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v70 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v70)[2])(v70);
        v70 = 0;
        v69 = &Dfdll::CObject::`vftable';
        v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v64 )
          (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
        v64 = 0;
        v63 = &Dfdll::CObject::`vftable';
        v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v66 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
        v66 = 0;
        v65 = &Dfdll::CObject::`vftable';
        v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
        v57 = &Dfdll::CObject::`vftable';
        goto LABEL_535;
      }
      if ( !v113 )
      {
        v16 = -2147024883;
LABEL_538:
        Dfdll::CString::~CString((Dfdll::CString *)v111);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v100);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v88);
        Dfdll::CString::~CString((Dfdll::CString *)v104);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v90);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v77);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v75);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v79);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v73);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v67);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v69);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v63);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v65);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v57);
LABEL_535:
        Dfdll::CString::~CString((Dfdll::CString *)&v83);
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v59);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v55);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v53);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v71);
        return (unsigned int)v16;
      }
      v99 = 0;
      v98 = &Dfdll::CIUnknownBasedPointer<ISectionEntry>::`vftable';
      v97 = 0;
      v96 = &Dfdll::CIUnknownBasedPointer<IMetadataSectionEntry>::`vftable';
      v95 = 0;
      v94 = &Dfdll::CIUnknownBasedPointer<IDeploymentMetadataEntry>::`vftable';
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 112LL))(v54, &v99);
      if ( v16 < 0
        || (v16 = Dfdll::CInterfacePointer<IUnknown>::Attach(&v96, v99, 0), v16 < 0)
        || (v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v97 + 120LL))(v97, &v95), v16 < 0) )
      {
LABEL_540:
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v94);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v96);
        Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(&v98);
        goto LABEL_538;
      }
      if ( !v95 )
      {
        v16 = -2147024883;
        goto LABEL_540;
      }
      v108 = 0;
      v110 = 0;
      v109 = 0;
      v107 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
      v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v95 + 32LL))(v95, &v108);
      if ( v16 < 0 )
      {
LABEL_546:
        Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(&v107);
        goto LABEL_540;
      }
      v115[0] = &Dfdll::CString::`vftable';
      v115[2] = 0;
      v116 = 0;
      v115[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
      v117 = 0;
      v16 = Dfdll::CString::Assign((Dfdll::CString *)v115, v108);
      if ( v16 < 0 )
      {
LABEL_548:
        Dfdll::CString::~CString((Dfdll::CString *)v115);
        goto LABEL_546;
      }
      v43 = 0;
      v44 = v15;
      v45 = a6;
      v46 = Dfdll::CString::CopyTo((Dfdll::CString *)&v83, a6, v44);
      v16 = v46;
      if ( v46 == -2147024774 )
      {
        v43 = 1;
      }
      else if ( v46 < 0 )
      {
        goto LABEL_548;
      }
      v47 = a8;
      v48 = Dfdll::CString::CopyTo((Dfdll::CString *)v111, a8, a9);
      v16 = v48;
      if ( v48 == -2147024774 )
      {
        v43 = 1;
      }
      else if ( v48 < 0 )
      {
        goto LABEL_548;
      }
      v49 = a10;
      v50 = Dfdll::CString::CopyTo((Dfdll::CString *)v115, a10, a11);
      v16 = v50;
      if ( v50 == -2147024774 )
      {
        v43 = 1;
      }
      else if ( v50 < 0 )
      {
        goto LABEL_548;
      }
      v51 = v120;
      v16 = Dfdll::CString::CopyTo((Dfdll::CString *)v104, v120, v14);
      if ( v16 != -2147024774 )
      {
        if ( v16 < 0 )
          goto LABEL_548;
        if ( !v43 )
        {
          v16 = 0;
          goto LABEL_548;
        }
      }
      *v51 = 0;
      *v45 = 0;
      *v47 = 0;
      *v49 = 0;
      v16 = -2147024774;
      goto LABEL_548;
    }
    v36 = v70;
  }
  else
  {
    v16 = -2147467261;
  }
  v67 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v39 )
  {
    (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v39 + 16LL))(v39);
    v36 = v70;
  }
  v68 = 0;
  v67 = &Dfdll::CObject::`vftable';
  v69 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v36 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v36)[2])(v36);
  v70 = 0;
  v69 = &Dfdll::CObject::`vftable';
  v63 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v64 )
    (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v64 + 16LL))(v64);
  v64 = 0;
  v63 = &Dfdll::CObject::`vftable';
  v65 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v66 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *)))(*v66)[2])(v66);
  v66 = 0;
  v65 = &Dfdll::CObject::`vftable';
  v57 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  v58 = 0;
  v57 = &Dfdll::CObject::`vftable';
  v83 = &Dfdll::CString::`vftable';
  v84 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v85 )
    operator delete(v85, v38);
  v85 = 0;
  v86 = 0;
  v84 = &Dfdll::CObject::`vftable';
  v83 = &Dfdll::CObject::`vftable';
  v59 = &Dfdll::CCOMPointerBase::`vftable';
  if ( pv )
    CoTaskMemFree(pv);
  pv = 0;
  v62 = 0;
  v61 = 0;
  v59 = &Dfdll::CObject::`vftable';
  v55 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  v56 = 0;
  v55 = &Dfdll::CObject::`vftable';
  v53 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  v54 = 0;
  v53 = &Dfdll::CObject::`vftable';
  v71 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v72 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v72)[2])(v72);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000dadc  mov     [rsp-8+arg_0], rbx
0x18000dae1  mov     [rsp-8+arg_18], r9
0x18000dae6  push    rbp
0x18000dae7  push    rsi
0x18000dae8  push    rdi
0x18000dae9  push    r12
0x18000daeb  push    r13
0x18000daed  push    r14
0x18000daef  push    r15
0x18000daf1  lea     rbp, [rsp-150h]
0x18000daf9  sub     rsp, 250h
0x18000db00  mov     rax, r9
0x18000db03  mov     rbx, r8
0x18000db06  mov     r15, rdx
0x18000db09  mov     r14, rcx
0x18000db0c  xor     edi, edi
0x18000db0e  test    rdx, rdx
0x18000db11  jz      loc_180010BD0
0x18000db17  cmp     [rdx], di
0x18000db1a  jz      loc_180010BD0
0x18000db20  test    rbx, rbx
0x18000db23  jz      loc_180010BD0
0x18000db29  cmp     [r8], di
0x18000db2d  jz      loc_180010BD0
0x18000db33  test    rax, rax
0x18000db36  jz      loc_180010BD0
0x18000db3c  mov     r13, [rbp+180h+arg_20]
0x18000db43  test    r13, r13
0x18000db46  jz      loc_180010BD0
0x18000db4c  cmp     dword ptr [r13+0], 1
0x18000db51  jbe     loc_180010BD0
0x18000db57  cmp     [rbp+180h+arg_28], rdi
0x18000db5e  jz      loc_180010BD0
0x18000db64  mov     r12, [rbp+180h+arg_30]
0x18000db6b  test    r12, r12
0x18000db6e  jz      loc_180010BD0
0x18000db74  cmp     dword ptr [r12], 1
0x18000db79  jbe     loc_180010BD0
0x18000db7f  cmp     [rbp+180h+arg_38], rdi
0x18000db86  jz      loc_180010BD0
0x18000db8c  mov     rax, [rbp+180h+arg_40]
0x18000db93  test    rax, rax
0x18000db96  jz      loc_180010BD0
0x18000db9c  cmp     dword ptr [rax], 1
0x18000db9f  jbe     loc_180010BD0
0x18000dba5  cmp     [rbp+180h+arg_48], rdi
0x18000dbac  jz      loc_180010BD0
0x18000dbb2  mov     rax, [rbp+180h+arg_50]
0x18000dbb9  test    rax, rax
0x18000dbbc  jz      loc_180010BD0
0x18000dbc2  cmp     dword ptr [rax], 1
0x18000dbc5  jbe     loc_180010BD0
0x18000dbcb  call    ?Reset@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::Reset(void)
0x18000dbd0  mov     esi, eax
0x18000dbd2  test    eax, eax
0x18000dbd4  js      loc_180010BD5
0x18000dbda  mov     rcx, r14; this
0x18000dbdd  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000dbe2  mov     esi, eax
0x18000dbe4  test    eax, eax
0x18000dbe6  js      loc_180010BD5
0x18000dbec  mov     [rbp+180h+var_1C0], rdi
0x18000dbf0  lea     rax, ??_7?$CIUnknownBasedPointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable'
0x18000dbf7  mov     [rbp+180h+var_1C8], rax
0x18000dbfb  mov     [rsp+280h+var_248], rdi
0x18000dc00  lea     rax, ??_7?$CIUnknownBasedPointer@UICMS@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<ICMS>::`vftable'
0x18000dc07  mov     [rsp+280h+var_250], rax
0x18000dc0c  lea     r9, [rbp+180h+var_1C0]
0x18000dc10  lea     r8, _GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033
0x18000dc17  xor     edx, edx
0x18000dc19  mov     rcx, rbx
0x18000dc1c  mov     rax, cs:?_pfnParseManifest@CSubscription@Dfdll@@1P6AJPEBGPEAUIManifestParseErrorCallback@@AEBU_GUID@@PEAPEAUIUnknown@@@ZEA; long (*Dfdll::CSubscription::_pfnParseManifest)(ushort const *,IManifestParseErrorCallback *,_GUID const &,IUnknown * *)
0x18000dc23  call    cs:__guard_dispatch_icall_fptr
0x18000dc29  mov     esi, eax
0x18000dc2b  xor     ebx, ebx
0x18000dc2d  test    eax, eax
0x18000dc2f  jns     short loc_18000DC85
0x18000dc31  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000dc38  mov     [rsp+280h+var_250], rdi
0x18000dc3d  mov     rcx, [rsp+280h+var_248]
0x18000dc42  test    rcx, rcx
0x18000dc45  jz      short loc_18000DC54
0x18000dc47  mov     rax, [rcx]
0x18000dc4a  mov     rax, [rax+10h]
0x18000dc4e  call    cs:__guard_dispatch_icall_fptr
0x18000dc54  mov     [rsp+280h+var_248], rbx
0x18000dc59  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000dc60  mov     [rsp+280h+var_250], rbx
0x18000dc65  mov     [rbp+180h+var_1C8], rdi
0x18000dc69  mov     rcx, [rbp+180h+var_1C0]
0x18000dc6d  test    rcx, rcx
0x18000dc70  jz      short loc_18000DC80
0x18000dc72  mov     rax, [rcx]
0x18000dc75  mov     rax, [rax+10h]
0x18000dc79  call    cs:__guard_dispatch_icall_fptr
0x18000dc7f  nop
0x18000dc80  jmp     loc_180010BD5
0x18000dc85  mov     rcx, [rbp+180h+var_1C0]
0x18000dc89  mov     rdi, rcx
0x18000dc8c  mov     rdx, [rsp+280h+var_248]
0x18000dc91  test    rdx, rdx
0x18000dc94  jz      short loc_18000DCAA
0x18000dc96  mov     rax, [rdx]
0x18000dc99  mov     rcx, rdx
0x18000dc9c  mov     rax, [rax+10h]
0x18000dca0  call    cs:__guard_dispatch_icall_fptr
0x18000dca6  mov     rcx, [rbp+180h+var_1C0]
0x18000dcaa  mov     r8, rbx
0x18000dcad  mov     [rsp+280h+var_248], rbx
0x18000dcb2  test    rdi, rdi
0x18000dcb5  jz      loc_180010B7C
0x18000dcbb  mov     rbx, [rdi]
0x18000dcbe  mov     rax, [rsp+280h+var_250]
0x18000dcc3  lea     rcx, [rsp+280h+var_250]
0x18000dcc8  mov     rax, [rax+28h]
0x18000dccc  call    cs:__guard_dispatch_icall_fptr
0x18000dcd2  mov     rdx, rax
0x18000dcd5  lea     r8, [rsp+280h+var_248]
0x18000dcda  mov     rcx, rdi
0x18000dcdd  mov     rax, [rbx]
0x18000dce0  call    cs:__guard_dispatch_icall_fptr
0x18000dce6  mov     esi, eax
0x18000dce8  mov     r8, [rsp+280h+var_248]
0x18000dced  xor     ebx, ebx
0x18000dcef  test    eax, eax
0x18000dcf1  cmovs   r8, rbx
0x18000dcf5  mov     [rsp+280h+var_248], r8
0x18000dcfa  js      loc_180010B76
0x18000dd00  mov     [rsp+280h+var_238], rbx
0x18000dd05  lea     rax, ??_7?$CIUnknownBasedPointer@UIDefinitionIdentity@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable'
0x18000dd0c  mov     [rsp+280h+var_240], rax
0x18000dd11  mov     rax, [r8]
0x18000dd14  lea     rdx, [rsp+280h+var_238]
0x18000dd19  mov     rcx, r8
0x18000dd1c  mov     rax, [rax+18h]
0x18000dd20  call    cs:__guard_dispatch_icall_fptr
0x18000dd26  mov     esi, eax
0x18000dd28  test    eax, eax
0x18000dd2a  jns     short loc_18000DDA9
0x18000dd2c  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000dd33  mov     [rsp+280h+var_240], rdi
0x18000dd38  mov     rcx, [rsp+280h+var_238]
0x18000dd3d  test    rcx, rcx
0x18000dd40  jz      short loc_18000DD4F
0x18000dd42  mov     rax, [rcx]
0x18000dd45  mov     rax, [rax+10h]
0x18000dd49  call    cs:__guard_dispatch_icall_fptr
0x18000dd4f  mov     [rsp+280h+var_238], rbx
0x18000dd54  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000dd5b  mov     [rsp+280h+var_240], rbx
0x18000dd60  mov     [rsp+280h+var_250], rdi
0x18000dd65  mov     rcx, [rsp+280h+var_248]
0x18000dd6a  xor     r14d, r14d
0x18000dd6d  test    rcx, rcx
0x18000dd70  jz      short loc_18000DD7F
0x18000dd72  mov     rax, [rcx]
0x18000dd75  mov     rax, [rax+10h]
0x18000dd79  call    cs:__guard_dispatch_icall_fptr
0x18000dd7f  mov     [rsp+280h+var_248], r14
0x18000dd84  mov     [rsp+280h+var_250], rbx
0x18000dd89  mov     [rbp+180h+var_1C8], rdi
0x18000dd8d  mov     rcx, [rbp+180h+var_1C0]
0x18000dd91  test    rcx, rcx
0x18000dd94  jz      short loc_18000DDA4
0x18000dd96  mov     rax, [rcx]
0x18000dd99  mov     rax, [rax+10h]
0x18000dd9d  call    cs:__guard_dispatch_icall_fptr
0x18000dda3  nop
0x18000dda4  jmp     loc_180010BD5
0x18000dda9  mov     [rsp+280h+pv], rbx
0x18000ddae  mov     [rsp+280h+var_20C], bl
0x18000ddb2  mov     [rsp+280h+var_210], ebx
0x18000ddb6  lea     rax, ??_7?$CCOMPointer@G@Dfdll@@6B@; const Dfdll::CCOMPointer<ushort>::`vftable'
0x18000ddbd  mov     [rsp+280h+var_220], rax
0x18000ddc2  mov     rcx, [rsp+280h+var_238]
0x18000ddc7  mov     rax, [rcx]
0x18000ddca  lea     r9, [rsp+280h+pv]
0x18000ddcf  lea     r8, aProcessorarchi; "processorArchitecture"
0x18000ddd6  xor     edx, edx
0x18000ddd8  mov     rax, [rax+18h]
0x18000dddc  call    cs:__guard_dispatch_icall_fptr
0x18000dde2  mov     esi, eax
0x18000dde4  test    eax, eax
0x18000dde6  jns     loc_18000DE97
0x18000ddec  lea     r14, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000ddf3  mov     [rsp+280h+var_220], r14
0x18000ddf8  mov     rcx, [rsp+280h+pv]; pv
0x18000ddfd  test    rcx, rcx
0x18000de00  jz      short loc_18000DE08
0x18000de02  call    cs:__imp_CoTaskMemFree
0x18000de08  mov     [rsp+280h+pv], rbx
0x18000de0d  mov     [rsp+280h+var_20C], bl
0x18000de11  mov     [rsp+280h+var_210], ebx
0x18000de15  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000de1c  mov     [rsp+280h+var_220], rbx
0x18000de21  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000de28  mov     [rsp+280h+var_240], rdi
0x18000de2d  mov     rcx, [rsp+280h+var_238]
0x18000de32  xor     r14d, r14d
0x18000de35  test    rcx, rcx
0x18000de38  jz      short loc_18000DE47
0x18000de3a  mov     rax, [rcx]
0x18000de3d  mov     rax, [rax+10h]
0x18000de41  call    cs:__guard_dispatch_icall_fptr
0x18000de47  mov     [rsp+280h+var_238], r14
0x18000de4c  mov     [rsp+280h+var_240], rbx
0x18000de51  mov     [rsp+280h+var_250], rdi
0x18000de56  mov     rcx, [rsp+280h+var_248]
0x18000de5b  test    rcx, rcx
0x18000de5e  jz      short loc_18000DE6D
0x18000de60  mov     rax, [rcx]
0x18000de63  mov     rax, [rax+10h]
0x18000de67  call    cs:__guard_dispatch_icall_fptr
0x18000de6d  mov     [rsp+280h+var_248], r14
0x18000de72  mov     [rsp+280h+var_250], rbx
0x18000de77  mov     [rbp+180h+var_1C8], rdi
0x18000de7b  mov     rcx, [rbp+180h+var_1C0]
0x18000de7f  test    rcx, rcx
0x18000de82  jz      short loc_18000DE92
0x18000de84  mov     rax, [rcx]
0x18000de87  mov     rax, [rax+10h]
0x18000de8b  call    cs:__guard_dispatch_icall_fptr
0x18000de91  nop
0x18000de92  jmp     loc_180010BD5
0x18000de97  mov     rdx, [rsp+280h+pv]; unsigned __int16 *
0x18000de9c  test    rdx, rdx
0x18000de9f  jnz     loc_18000DF39
0x18000dea5  mov     esi, 8007000Dh
0x18000deaa  mov     [rsp+280h+pv], rbx
0x18000deaf  mov     [rsp+280h+var_20C], bl
0x18000deb3  mov     [rsp+280h+var_210], ebx
0x18000deb7  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000debe  mov     [rsp+280h+var_220], rbx
0x18000dec3  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000deca  mov     [rsp+280h+var_240], rdi
0x18000decf  mov     rcx, [rsp+280h+var_238]
0x18000ded4  xor     r14d, r14d
0x18000ded7  test    rcx, rcx
0x18000deda  jz      short loc_18000DEE9
0x18000dedc  mov     rax, [rcx]
0x18000dedf  mov     rax, [rax+10h]
0x18000dee3  call    cs:__guard_dispatch_icall_fptr
0x18000dee9  mov     [rsp+280h+var_238], r14
0x18000deee  mov     [rsp+280h+var_240], rbx
0x18000def3  mov     [rsp+280h+var_250], rdi
0x18000def8  mov     rcx, [rsp+280h+var_248]
0x18000defd  test    rcx, rcx
0x18000df00  jz      short loc_18000DF0F
0x18000df02  mov     rax, [rcx]
0x18000df05  mov     rax, [rax+10h]
0x18000df09  call    cs:__guard_dispatch_icall_fptr
0x18000df0f  mov     [rsp+280h+var_248], r14
0x18000df14  mov     [rsp+280h+var_250], rbx
0x18000df19  mov     [rbp+180h+var_1C8], rdi
0x18000df1d  mov     rcx, [rbp+180h+var_1C0]
0x18000df21  test    rcx, rcx
0x18000df24  jz      short loc_18000DF34
0x18000df26  mov     rax, [rcx]
0x18000df29  mov     rax, [rax+10h]
0x18000df2d  call    cs:__guard_dispatch_icall_fptr
0x18000df33  nop
0x18000df34  jmp     loc_180010BD5
0x18000df39  lea     rdi, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x18000df40  mov     [rbp+180h+var_170], rdi
0x18000df44  mov     [rbp+180h+var_160], rbx
0x18000df48  mov     [rbp+180h+var_158], ebx
0x18000df4b  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000df52  mov     [rbp+180h+var_168], rax
0x18000df56  mov     [rbp+180h+var_150], ebx
0x18000df59  lea     rcx, [rbp+180h+var_170]; this
0x18000df5d  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x18000df62  mov     esi, eax
0x18000df64  test    eax, eax
0x18000df66  jns     loc_18000E045
0x18000df6c  mov     [rbp+180h+var_170], rdi
0x18000df70  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000df77  mov     [rbp+180h+var_168], rax
0x18000df7b  mov     rcx, [rbp+180h+var_160]; void *
0x18000df7f  test    rcx, rcx
0x18000df82  jz      short loc_18000DF89
0x18000df84  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000df89  mov     [rbp+180h+var_160], rbx
0x18000df8d  mov     [rbp+180h+var_158], ebx
0x18000df90  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000df97  mov     [rbp+180h+var_168], rbx
0x18000df9b  mov     [rbp+180h+var_170], rbx
0x18000df9f  lea     r14, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000dfa6  mov     [rsp+280h+var_220], r14
0x18000dfab  mov     rcx, [rsp+280h+pv]; pv
0x18000dfb0  xor     r14d, r14d
0x18000dfb3  test    rcx, rcx
0x18000dfb6  jz      short loc_18000DFBE
0x18000dfb8  call    cs:__imp_CoTaskMemFree
0x18000dfbe  mov     [rsp+280h+pv], r14
0x18000dfc3  mov     [rsp+280h+var_20C], r14b
0x18000dfc8  mov     [rsp+280h+var_210], r14d
0x18000dfcd  mov     [rsp+280h+var_220], rbx
0x18000dfd2  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000dfd9  mov     [rsp+280h+var_240], rdi
0x18000dfde  mov     rcx, [rsp+280h+var_238]
  ... truncated ...
```
