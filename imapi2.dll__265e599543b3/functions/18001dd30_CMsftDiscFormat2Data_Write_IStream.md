# CMsftDiscFormat2Data::Write(IStream *)

- ea: `0x18001dd30`
- end: `0x180021353`
- name: `?Write@CMsftDiscFormat2Data@@UEAAJPEAUIStream@@@Z`
- size: `13859`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Data *this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `55`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180009120`
- `0x180009b80`
- `0x18000a5f0`
- `0x18000a804`
- `0x18000fd58`
- `0x18000fdd4`
- `0x180011b4c`
- `0x180012700`
- `0x1800140f4`
- `0x180014134`
- `0x180014250`
- `0x180016778`
- `0x1800170ec`
- `0x18001724c`
- `0x180017838`
- `0x180017a88`
- `0x180018908`
- `0x180018aec`
- `0x180018cd0`
- `0x180018e80`
- `0x1800190f8`
- `0x180019490`
- `0x180019728`
- `0x180019a00`
- `0x180019dc8`
- `0x18001c518`
- `0x18001cb0c`
- `0x18001cb38`
- `0x18001cc9c`
- `0x18001cdf4`
- `0x18001d338`
- `0x18001d420`
- `0x18001d70c`
- `0x18001d9bc`
- `0x18001dd30`
- `0x1800236b4`
- `0x180023790`
- `0x1800238ec`
- `0x180023a78`
- `0x180023ac8`
- `0x180023b14`
- `0x180023f8c`
- `0x180042708`
- `0x1800454cc`
- `0x1800464ec`
- `0x180046708`
- `0x180046a94`
- `0x180046bf4`
- `0x180047408`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001e02a`
- `ole32!CoTaskMemFree` at `0x18001ed9f`
- `ole32!CoTaskMemFree` at `0x180020201`
- `ole32!CoTaskMemFree` at `0x1800210c6`
- `ole32!CoTaskMemFree` at `0x1800210d3`
- `ole32!CoTaskMemFree` at `0x18001e02a`
- `ole32!CoTaskMemFree` at `0x18001ed9f`
- `ole32!CoTaskMemFree` at `0x180020201`
- `ole32!CoTaskMemFree` at `0x1800210c6`
- `ole32!CoTaskMemFree` at `0x1800210d3`
- `ole32!CoCreateInstance` at `0x18001eb80`
- `ole32!CoCreateInstance` at `0x18001ec4d`
- `ole32!CoCreateInstance` at `0x18001f86c`
- `ole32!CoCreateInstance` at `0x18001f958`
- `ole32!CoCreateInstance` at `0x18001eb80`
- `ole32!CoCreateInstance` at `0x18001ec4d`
- `ole32!CoCreateInstance` at `0x18001f86c`
- `ole32!CoCreateInstance` at `0x18001f958`
- `ole32!CoTaskMemAlloc` at `0x18001fda7`
- `ole32!CoTaskMemAlloc` at `0x18001fda7`
- `OLEAUT32!__imp_VariantClear` at `0x18001e87d`
- `OLEAUT32!__imp_VariantClear` at `0x180020639`
- `OLEAUT32!__imp_VariantClear` at `0x18001e87d`
- `OLEAUT32!__imp_VariantClear` at `0x180020639`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001e7e8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001e7e8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001e7cf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001e7cf`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001e83a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800205fa`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001e83a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800205fa`
- `KERNEL32!Sleep` at `0x18002107d`
- `KERNEL32!Sleep` at `0x180021147`
- `KERNEL32!Sleep` at `0x1800211fa`
- `KERNEL32!Sleep` at `0x18002107d`
- `KERNEL32!Sleep` at `0x180021147`
- `KERNEL32!Sleep` at `0x1800211fa`
- `KERNEL32!GetTickCount` at `0x18001de3f`
- `KERNEL32!GetTickCount` at `0x18001f73c`
- `KERNEL32!GetTickCount` at `0x18002127b`
- `KERNEL32!GetTickCount` at `0x18001de3f`
- `KERNEL32!GetTickCount` at `0x18001f73c`
- `KERNEL32!GetTickCount` at `0x18002127b`
- `KERNEL32!PowerClearRequest` at `0x1800212e5`
- `KERNEL32!PowerClearRequest` at `0x1800212e5`
- `KERNEL32!CloseHandle` at `0x18001de34`
- `KERNEL32!CloseHandle` at `0x1800212f8`
- `KERNEL32!CloseHandle` at `0x18001de34`
- `KERNEL32!CloseHandle` at `0x1800212f8`
- `KERNEL32!PowerSetRequest` at `0x18001de27`
- `KERNEL32!PowerSetRequest` at `0x18001de27`
- `KERNEL32!PowerCreateRequest` at `0x18001ddf5`
- `KERNEL32!PowerCreateRequest` at `0x18001ddf5`
- `KERNEL32!GetLastError` at `0x18001de08`
- `KERNEL32!GetLastError` at `0x1800212ef`
- `KERNEL32!GetLastError` at `0x18001de08`
- `KERNEL32!GetLastError` at `0x1800212ef`

## string_xrefs

- `0x18001dd96`: `Imapi data write is in progress...`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::Write(CMsftDiscFormat2Data *this, struct IUnknown *a2)
{
  Imapi2Utility *v2; // r15
  __int64 v5; // rbx
  HANDLE v6; // rax
  void *v7; // rdi
  signed int LastError; // eax
  enum _IMAPI_MEDIA_PHYSICAL_TYPE CurrentPhysicalMediaType; // edi
  __int64 v10; // rdx
  __int64 lpVtbl_low; // r9
  PVOID *v12; // rcx
  char v13; // si
  CMsftDiscInformation *v14; // rbx
  unsigned __int8 v15; // r8
  __int64 v16; // rcx
  void *v17; // rax
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  enum _IMAPI_MEDIA_PHYSICAL_TYPE *v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r9
  HRESULT v27; // eax
  int v28; // r14d
  unsigned int v29; // r10d
  __int64 v30; // rdx
  LONG v31; // eax
  int v32; // esi
  int v33; // eax
  int v34; // r8d
  int v35; // eax
  int v36; // eax
  int v37; // ebx
  unsigned __int64 v38; // rbx
  int v39; // eax
  HRESULT v40; // eax
  __int64 v41; // rdx
  int v42; // eax
  void *v43; // rax
  void *v44; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  int SessionInfo; // eax
  unsigned int v47; // r8d
  HRESULT Instance; // eax
  __int64 v49; // rdx
  int v50; // eax
  int v51; // r10d
  int v52; // ebx
  __int64 v53; // rdx
  unsigned int v54; // r8d
  unsigned int v55; // r8d
  Imapi2Utility *v56; // rbx
  __int64 v57; // rax
  unsigned int v58; // r14d
  unsigned int v59; // eax
  unsigned int v60; // r9d
  int v61; // eax
  unsigned int v62; // esi
  unsigned int v63; // eax
  const struct _GUID *v64; // r8
  __int64 v65; // r14
  HRESULT v66; // eax
  __int64 v67; // rdx
  int v68; // eax
  __int64 v69; // rdx
  unsigned int v70; // r8d
  __int128 v71; // xmm0
  __int64 v72; // rcx
  Imapi2Utility *v73; // rax
  __int64 v74; // rdx
  int v75; // eax
  __int64 v76; // rcx
  int v77; // eax
  unsigned int v78; // r8d
  __int128 v79; // xmm0
  __int64 v80; // rcx
  int v81; // eax
  _QWORD *v82; // rdi
  __int64 v83; // rbx
  int started; // eax
  int v85; // eax
  int v86; // eax
  int v87; // eax
  LONG v88; // ecx
  LONG v89; // r14d
  __int64 v90; // r8
  LONG v91; // esi
  __int64 v92; // rdx
  struct IUnknown *v93; // rsi
  PVOID *v94; // rcx
  struct IUnknown *v95; // rdx
  LONG v96; // ecx
  __int64 v97; // rax
  int v98; // r14d
  _QWORD *v99; // rcx
  __int64 v100; // rdx
  PVOID *v101; // rcx
  __int64 v102; // rax
  unsigned int v103; // ebx
  unsigned int v104; // r14d
  unsigned int *v105; // r9
  Imapi2Utility *v106; // rcx
  unsigned int v107; // ecx
  int v108; // eax
  __int64 v109; // rax
  unsigned int v110; // ebx
  int v111; // eax
  __int64 v112; // rcx
  int v113; // eax
  unsigned __int8 v114; // r8
  unsigned __int8 v115; // r9
  unsigned int i; // ebx
  unsigned int j; // ebx
  int v118; // ecx
  DWORD v119; // eax
  __int64 v120; // rcx
  HANDLE v121; // rbx
  HANDLE v122; // rcx
  const struct _GUID *v123; // r8
  int ppv; // [rsp+20h] [rbp-E0h]
  int v126; // [rsp+28h] [rbp-D8h]
  int v127; // [rsp+30h] [rbp-D0h]
  int v128; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v129; // [rsp+70h] [rbp-90h]
  LONG rgIndices; // [rsp+74h] [rbp-8Ch] BYREF
  char v131; // [rsp+78h] [rbp-88h]
  char v132; // [rsp+79h] [rbp-87h]
  struct IDiscRecorder2Ex v133; // [rsp+7Ch] [rbp-84h] BYREF
  int v134; // [rsp+84h] [rbp-7Ch] BYREF
  int v135; // [rsp+88h] [rbp-78h] BYREF
  __int64 v136; // [rsp+90h] [rbp-70h]
  LONG v137; // [rsp+98h] [rbp-68h] BYREF
  SIZE_T cb; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v139; // [rsp+A4h] [rbp-5Ch] BYREF
  struct IDiscRecorder2Ex v140; // [rsp+A8h] [rbp-58h] BYREF
  struct IUnknown *v141; // [rsp+B0h] [rbp-50h]
  SAFEARRAY *psa; // [rsp+B8h] [rbp-48h] BYREF
  LONG plLbound; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v144; // [rsp+C4h] [rbp-3Ch] BYREF
  LONG plUbound; // [rsp+C8h] [rbp-38h] BYREF
  Imapi2Utility *v146[2]; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v147; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v148; // [rsp+E8h] [rbp-18h] BYREF
  void *Src; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v150; // [rsp+100h] [rbp+0h] BYREF
  __int64 v151; // [rsp+110h] [rbp+10h] BYREF
  LPVOID v152; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG pvarg; // [rsp+120h] [rbp+20h] BYREF
  DWORD TickCount; // [rsp+138h] [rbp+38h]
  LPVOID v155; // [rsp+140h] [rbp+40h] BYREF
  HANDLE PowerRequest; // [rsp+148h] [rbp+48h]
  _REASON_CONTEXT Context; // [rsp+150h] [rbp+50h] BYREF
  LPVOID pv[2]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v159; // [rsp+180h] [rbp+80h]

  v2 = 0;
  v131 = 0;
  v132 = 0;
  BYTE4(v133.lpVtbl) = 0;
  LODWORD(v133.lpVtbl) = 0;
  memset_0(pv, 0, 0x50u);
  LODWORD(v146[0]) = 0;
  v137 = 0;
  LOBYTE(v5) = -1;
  Context.Reason.Detailed.LocalizedReasonModule = (HMODULE)L"Imapi data write is in progress...";
  v136 = 0xFFFFFFFFLL;
  *(_OWORD *)(&Context.Reason.SimpleReasonString + 1) = 0;
  v139 = 0;
  LODWORD(v140.lpVtbl) = 0;
  v144 = 0;
  v129 = 0;
  v152 = 0;
  Src = 0;
  cb = 0;
  v141 = 0;
  v148 = 0;
  v151 = 0;
  psa = 0;
  plLbound = 0;
  plUbound = 0;
  Context.Version = 0;
  Context.Flags = 1;
  v6 = PowerCreateRequest(&Context);
  PowerRequest = v6;
  v7 = v6;
  if ( v6 != (HANDLE)-1LL )
  {
    if ( PowerSetRequest(v6, PowerRequestExecutionRequired) )
    {
      CurrentPhysicalMediaType = IMAPI_MEDIA_TYPE_UNKNOWN;
      goto LABEL_7;
    }
    CloseHandle(v7);
  }
  LastError = GetLastError();
  CurrentPhysicalMediaType = LastError;
  if ( LastError > 0 )
    CurrentPhysicalMediaType = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
  TickCount = GetTickCount();
  if ( !a2 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 11, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    CurrentPhysicalMediaType = -2147467261;
    rgIndices = 0;
    v13 = 0;
    v14 = 0;
    goto LABEL_734;
  }
  LODWORD(v150) = 0;
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_273;
  CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::ValidateRecorderSet(this);
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_273;
  if ( *((_WORD *)this + 84) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 12, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    CurrentPhysicalMediaType = -1062599680;
    goto LABEL_21;
  }
  v16 = *((_QWORD *)this + 23);
  *((_DWORD *)this + 42) = 0xFFFF;
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)this + 23) = 0;
  }
  if ( *((_WORD *)this + 85) == 0xFFFF )
    goto LABEL_65;
  CurrentPhysicalMediaType = ((unsigned int (__fastcall *)(struct IUnknown *, LPVOID *, __int64))a2->lpVtbl[4].QueryInterface)(
                               a2,
                               pv,
                               1);
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        13,
        &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
        (unsigned int)CurrentPhysicalMediaType);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    CurrentPhysicalMediaType = -1062599677;
    goto LABEL_21;
  }
  v17 = pv[0];
  if ( pv[0] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 14, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
      v17 = pv[0];
    }
    CoTaskMemFree(v17);
    pv[0] = 0;
  }
  if ( *((_WORD *)this + 85) == 0xFFFF )
    goto LABEL_65;
  v10 = 2047;
  if ( (v159 & 0x7FF) != 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
    {
      goto LABEL_44;
    }
    WPP_SF_iidD(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      15,
      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
      v159,
      v159,
      v159 & 0x7FF,
      v159 & 0x7FF);
LABEL_43:
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_44:
    CurrentPhysicalMediaType = -1062599677;
LABEL_21:
    rgIndices = 0;
    v13 = 0;
    v2 = 0;
    v14 = 0;
    goto LABEL_734;
  }
  v18 = v159 >> 11;
  if ( v159 >> 11 > 0x7FFFFFFF )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
    {
      goto LABEL_44;
    }
    WPP_SF_ii(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      16,
      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
      v159 >> 11,
      v159 >> 11);
    goto LABEL_43;
  }
  v14 = 0;
  if ( !v159 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 17, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
LABEL_55:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    goto LABEL_56;
  }
  v19 = *((_QWORD *)this + 26);
  v5 = (unsigned int)v18;
  v20 = *((_QWORD *)this + 30);
  v136 = (unsigned int)v18;
  CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v19 + 72LL))(
                               v19,
                               1,
                               v20);
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
  {
    if ( CurrentPhysicalMediaType == -1062600175 )
      CurrentPhysicalMediaType = -1062599672;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
    {
LABEL_66:
      if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
        goto LABEL_521;
      goto LABEL_67;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      18,
      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
      (unsigned int)CurrentPhysicalMediaType);
LABEL_65:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  v132 = 1;
  v136 = v5;
LABEL_67:
  v21 = -1;
  if ( *((_WORD *)this + 85) != 0xFFFF )
  {
    LOBYTE(v21) = 1;
    CurrentPhysicalMediaType = (unsigned int)Imapi2Utility::PreventAllowMediumRemoval(
                                               *((Imapi2Utility **)this + 27),
                                               (struct IDiscRecorder2Ex *)v21,
                                               v15,
                                               lpVtbl_low);
    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_21;
      }
      v22 = 19;
      goto LABEL_159;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v131 = 1;
    if ( *((_WORD *)this + 85) != 0xFFFF )
    {
      v23 = *((_QWORD *)this + 26);
      LOWORD(rgIndices) = 0;
      CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(CMsftDiscFormat2Data *, __int64, LONG *))(*(_QWORD *)this + 64LL))(
                                   this,
                                   v23,
                                   &rgIndices);
      if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
        goto LABEL_273;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( !(_WORD)rgIndices )
      {
        CurrentPhysicalMediaType = -1062599674;
        goto LABEL_21;
      }
      if ( *((_WORD *)this + 85) != 0xFFFF )
      {
        CurrentPhysicalMediaType = (unsigned int)Imapi2Utility::GetCurrentPhysicalMediaType(
                                                   *((Imapi2Utility **)this + 27),
                                                   &v133,
                                                   v24);
        if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
          {
            goto LABEL_169;
          }
          v25 = 20;
LABEL_84:
          v26 = (unsigned int)CurrentPhysicalMediaType;
LABEL_85:
          WPP_SF_d(v12[37], v25, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v26);
          goto LABEL_86;
        }
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( *((_WORD *)this + 85) != 0xFFFF )
        {
          CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(CMsftDiscFormat2Data *, char *))(*(_QWORD *)this + 144LL))(
                                       this,
                                       (char *)&cb + 4);
          if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
            {
              goto LABEL_21;
            }
            v22 = 21;
            goto LABEL_159;
          }
          lpVtbl_low = HIDWORD(cb);
          if ( HIDWORD(cb) )
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
          else
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
            {
              WPP_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                (unsigned int)(HIDWORD(cb) + 22),
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              lpVtbl_low = HIDWORD(cb);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
          }
          if ( (lpVtbl_low & 0x400) != 0 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
            {
              WPP_SF_(v12[37], 23, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              lpVtbl_low = HIDWORD(cb);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
          }
          if ( (lpVtbl_low & 0x800) != 0 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
            {
              WPP_SF_(v12[37], 24, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              lpVtbl_low = HIDWORD(cb);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
          }
          if ( (lpVtbl_low & 0x1000) != 0 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
            {
              WPP_SF_(v12[37], 25, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              lpVtbl_low = HIDWORD(cb);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
          }
          if ( (lpVtbl_low & 0x2000) != 0 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
            {
              WPP_SF_(v12[37], 26, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              lpVtbl_low = HIDWORD(cb);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
          }
          if ( (lpVtbl_low & 0x4000) != 0 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
            {
              WPP_SF_(v12[37], 27, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              lpVtbl_low = HIDWORD(cb);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
          }
          if ( (lpVtbl_low & 0x8000) != 0 )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
            {
              WPP_SF_(v12[37], 28, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
            goto LABEL_21;
          }
          if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
            goto LABEL_521;
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 4u )
          {
            WPP_SF_d(v12[37], 29, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, lpVtbl_low);
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
      }
    }
  }
  LODWORD(v10) = 529568;
  if ( *((_WORD *)this + 85) == 0xFFFF )
    goto LABEL_222;
  rgIndices = 0;
  CurrentPhysicalMediaType = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                               a2,
                               &GUID_b507ca26_2204_11dd_966a_001aa01bbc58,
                               &v151);
  if ( CurrentPhysicalMediaType == -2147467262 )
  {
    v151 = 0;
    CurrentPhysicalMediaType = IMAPI_MEDIA_TYPE_UNKNOWN;
  }
  else
  {
    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_21;
      }
      v22 = 30;
LABEL_159:
      WPP_SF_d(v12[37], v22, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, (unsigned int)CurrentPhysicalMediaType);
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    if ( v151 )
    {
      CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(__int64, SAFEARRAY **))(*(_QWORD *)v151 + 56LL))(
                                   v151,
                                   &psa);
      if ( CurrentPhysicalMediaType == -2147467263 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        psa = 0;
        CurrentPhysicalMediaType = IMAPI_MEDIA_TYPE_UNKNOWN;
        goto LABEL_163;
      }
      if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
        {
          goto LABEL_169;
        }
        v25 = 31;
        goto LABEL_84;
      }
    }
  }
  if ( psa )
  {
    LOBYTE(lpVtbl_low) = v133.lpVtbl;
    if ( LODWORD(v133.lpVtbl) > 0x13 || (v10 = 529568, !_bittest((const int *)&v10, (unsigned int)v133.lpVtbl)) )
    {
      v27 = -1062599677;
      CurrentPhysicalMediaType = -1062599677;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_169;
      }
      v25 = 32;
LABEL_153:
      v26 = (unsigned int)v27;
      goto LABEL_85;
    }
  }
  else
  {
    LODWORD(v10) = 529568;
  }
  if ( !psa )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_222;
  }
  LODWORD(v14) = 0;
  CurrentPhysicalMediaType = SafeArrayGetLBound(psa, 1u, &plLbound);
  if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
    CurrentPhysicalMediaType = SafeArrayGetUBound(psa, 1u, &plUbound);
  v31 = plLbound;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  rgIndices = plLbound;
  LODWORD(v150) = 0;
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_521;
  while ( v31 <= plUbound )
  {
    v147 = 0;
    v135 = 0;
    v134 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    v32 = 0;
    if ( SafeArrayGetElement(psa, &rgIndices, &pvarg) < 0 )
    {
      CurrentPhysicalMediaType = -2147467262;
LABEL_202:
      v34 = v134;
      goto LABEL_203;
    }
    if ( pvarg.vt == 9 && pvarg.llVal )
      CurrentPhysicalMediaType = (**(unsigned int (__fastcall ***)(LONGLONG, GUID *, LPVOID *))pvarg.llVal)(
                                   pvarg.llVal,
                                   &GUID_b507ca25_2204_11dd_966a_001aa01bbc58,
                                   &v147);
    else
      CurrentPhysicalMediaType = -2147467262;
    VariantClear(&pvarg);
    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
      goto LABEL_202;
    v33 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v147 + 56LL))(v147, &v134);
    v34 = v134;
    v32 = v134;
    CurrentPhysicalMediaType = v33;
    if ( v33 >= 0 )
    {
      v35 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v147 + 64LL))(v147, &v135);
      LODWORD(v14) = v135;
      CurrentPhysicalMediaType = v35;
      v34 = v134;
      if ( v35 >= 0 && (v134 < 0 || v135 < v134) )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          v127 = v135;
          v126 = v135;
          ppv = v32;
          WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 37), 33, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
          v12 = (PVOID *)WPP_GLOBAL_Control;
          v34 = v134;
        }
        CurrentPhysicalMediaType = -2147024809;
        goto LABEL_204;
      }
    }
LABEL_203:
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_204:
    v36 = ++v135;
    if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
    {
      if ( LODWORD(v133.lpVtbl) == 10 )
      {
        v34 -= v34 % 16;
        v134 = v34;
        if ( v36 % 16 )
        {
          if ( (unsigned int)v36 <= 0xFFFFFFEF )
          {
            v36 = v36 - (v36 + 16) % 16 + 16;
            v135 = v36;
          }
        }
      }
      LOBYTE(lpVtbl_low) = v150;
      if ( (int)v150 + v36 - v34 + 1 >= (unsigned int)v150 )
      {
        LOBYTE(lpVtbl_low) = v135 - v34 + v150;
        LODWORD(v150) = v135 - v34 + v150;
      }
      else
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
        {
          WPP_SF_dDdDdD(
            v12[37],
            34,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v150,
            v150,
            v32,
            v32,
            (_DWORD)v14,
            (_DWORD)v14);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        CurrentPhysicalMediaType = -2147024809;
      }
    }
    v10 = (__int64)v147;
    v14 = 0;
    if ( v147 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v147 + 16LL))(v147);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v31 = ++rgIndices;
    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
      goto LABEL_57;
  }
  LOBYTE(v5) = v136;
LABEL_163:
  LODWORD(v10) = 529568;
LABEL_222:
  if ( *((_WORD *)this + 85) == 0xFFFF
    || *((_WORD *)this + 116)
    || psa
    || (LOBYTE(lpVtbl_low) = v133.lpVtbl, LOWORD(rgIndices) = 0, LODWORD(v133.lpVtbl) > 0x13)
    || !_bittest((const int *)&v10, (unsigned int)v133.lpVtbl) )
  {
LABEL_234:
    v10 = -1;
    if ( *((_WORD *)this + 85) != 0xFFFF && LODWORD(v133.lpVtbl) == 10 && (v155 = 0, v147 = 0, (v37 = v5 & 0xF) != 0) )
    {
      v27 = CoCreateInstance(&CLSID_MsftStreamZero, 0, 0x17u, &GUID_0000000c_0000_0000_c000_000000000046, &v155);
      CurrentPhysicalMediaType = v27;
      if ( v27 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
        {
          goto LABEL_169;
        }
        v25 = 36;
        goto LABEL_153;
      }
      v38 = (unsigned __int64)(unsigned int)(16 - v37) << 11;
      v39 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64))(*(_QWORD *)v155 + 48LL))(v155, v38);
      CurrentPhysicalMediaType = v39;
      if ( v39 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
        {
          goto LABEL_169;
        }
        WPP_SF_id(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          37,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          v38,
          v39,
          v126,
          v127);
LABEL_86:
        rgIndices = 0;
LABEL_87:
        v13 = 0;
        v2 = 0;
        goto LABEL_88;
      }
      v40 = CoCreateInstance(&CLSID_MsftStreamConcatenate, 0, 0x17u, &GUID_27354146_7f64_5b0f_8f00_5d77afbe261e, &v147);
      v14 = 0;
      CurrentPhysicalMediaType = v40;
      if ( v40 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
        {
          goto LABEL_170;
        }
        v41 = 38;
LABEL_252:
        WPP_SF_d(v12[37], v41, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, (unsigned int)v40);
        rgIndices = 0;
LABEL_253:
        v13 = 0;
        v2 = 0;
        goto LABEL_733;
      }
      v40 = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, LPVOID))(*(_QWORD *)v147 + 112LL))(v147, a2, v155);
      CurrentPhysicalMediaType = v40;
      if ( v40 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
        {
          goto LABEL_170;
        }
        v41 = 39;
        goto LABEL_252;
      }
      v42 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *, __int64))(*(_QWORD *)v147 + 96LL))(v147, pv, 1);
      CurrentPhysicalMediaType = v42;
      if ( v42 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            40,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v42);
          goto LABEL_55;
        }
LABEL_56:
        CurrentPhysicalMediaType = -1062599677;
LABEL_57:
        rgIndices = 0;
        goto LABEL_518;
      }
      v43 = pv[0];
      if ( pv[0] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 41, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
          v43 = pv[0];
        }
        CoTaskMemFree(v43);
        pv[0] = 0;
      }
      else
      {
        v136 = v159 >> 11;
      }
      v44 = v147;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      v141 = (struct IUnknown *)v147;
    }
    else
    {
      v14 = 0;
      v44 = v141;
    }
    if ( *((_WORD *)this + 85) == 0xFFFF || v44 )
      goto LABEL_170;
    lpVtbl = a2->lpVtbl;
    v141 = a2;
    ((void (__fastcall *)(struct IUnknown *))lpVtbl->AddRef)(a2);
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_171:
    v10 = -1;
    rgIndices = 0;
    v28 = 0;
    if ( *((_WORD *)this + 85) == 0xFFFF )
      goto LABEL_317;
    LOBYTE(lpVtbl_low) = v133.lpVtbl;
    if ( LODWORD(v133.lpVtbl) != 2 )
    {
      rgIndices = 0;
      if ( LODWORD(v133.lpVtbl) != 3 )
      {
LABEL_303:
        if ( *((_WORD *)this + 85) != 0xFFFF )
        {
          v135 = -1;
          v134 = -1;
          SessionInfo = CMsftDiscFormat2Data::GetSessionInfo(
                          this,
                          (int *)v146,
                          &v137,
                          (int *)&v139,
                          &v135,
                          &v134,
                          (int *)&v140,
                          (int *)&v144);
          if ( SessionInfo < 0 )
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                47,
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                (unsigned int)SessionInfo);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599678;
            goto LABEL_518;
          }
          v47 = v137;
          if ( !v137 )
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
            {
              WPP_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                (unsigned int)(v137 + 48),
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -1062599676;
            goto LABEL_518;
          }
          v12 = (PVOID *)WPP_GLOBAL_Control;
          v10 = -1;
          goto LABEL_318;
        }
LABEL_317:
        v47 = v137;
LABEL_318:
        if ( *((_WORD *)this + 85) == 0xFFFF )
          goto LABEL_432;
        if ( v47 < v28 + (int)v136 )
        {
          CurrentPhysicalMediaType = -1062599676;
          if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 308) & 4) == 0 || *((_BYTE *)v12 + 305) < 3u )
            goto LABEL_522;
          WPP_SF_dDdDdD(
            v12[37],
            49,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v136,
            v136,
            v28,
            v28,
            v47,
            v47);
          goto LABEL_253;
        }
        if ( *((_WORD *)this + 85) == 0xFFFF )
          goto LABEL_432;
        Instance = (*(__int64 (__fastcall **)(CMsftDiscFormat2Data *, _QWORD, _QWORD))(*(_QWORD *)this + 344LL))(
                     this,
                     *((unsigned int *)this + 63),
                     *((unsigned __int16 *)this + 128));
        CurrentPhysicalMediaType = Instance;
        if ( Instance < 0 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
          {
            goto LABEL_522;
          }
          v49 = 50;
LABEL_330:
          WPP_SF_d(v12[37], v49, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, (unsigned int)Instance);
          goto LABEL_253;
        }
        v12 = (PVOID *)WPP_GLOBAL_Control;
        v10 = -1;
        if ( *((_WORD *)this + 85) == 0xFFFF )
        {
LABEL_432:
          v146[0] = 0;
          CurrentPhysicalMediaType = (unsigned int)ATL::CComObject<CDiscFormat2DataEventArgs>::CreateInstance(v146, v10);
          if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
            goto LABEL_520;
          v56 = v146[0];
          (*(void (__fastcall **)(Imapi2Utility *))(*(_QWORD *)v146[0] + 8LL))(v146[0]);
          v57 = *(_QWORD *)this;
          v137 = -1;
          CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(CMsftDiscFormat2Data *, LONG *))(v57 + 272))(
                                       this,
                                       &v137);
          if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN && v137 )
          {
            v58 = v136 + v28;
            if ( psa )
              v59 = (plUbound - plLbound) / 5 + (unsigned int)v150 / v137;
            else
              v59 = v58 / v137;
          }
          else
          {
            v59 = 1080;
            v58 = v136 + v28;
          }
          v60 = v59 + 30;
          if ( !v129 )
            v60 = v59;
          v61 = *((_DWORD *)this + 62);
          if ( v61 == 2 )
          {
            v62 = psa ? v60 + (unsigned int)v150 / v137 + (plUbound - plLbound) / 5 : v60 + v58 / v137;
          }
          else
          {
            v62 = v60 + 3;
            if ( v61 != 1 )
              v62 = v60;
          }
          v63 = v139;
          *((_DWORD *)v56 + 17) = v139;
          *((_DWORD *)v56 + 19) = v63;
          *((_DWORD *)v56 + 20) = v63;
          *((_DWORD *)v56 + 18) = v58;
          *(_QWORD *)((char *)v56 + 84) = 0x80000;
          *(_QWORD *)((char *)v56 + 92) = 1310720;
          *((_DWORD *)v56 + 26) = GetTickCount();
          *((_DWORD *)v56 + 28) = 0;
          *((_DWORD *)v56 + 27) = v62;
          *((_DWORD *)v56 + 16) = 0;
          *((_QWORD *)this + 23) = v56;
          v14 = 0;
          if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
          {
LABEL_520:
            v12 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_522;
          }
          if ( *((_WORD *)this + 85) != 0xFFFF )
          {
            LOBYTE(lpVtbl_low) = v133.lpVtbl;
            if ( LODWORD(v133.lpVtbl) != 8 )
            {
              v12 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                  67,
                  &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                  LODWORD(v133.lpVtbl));
                v12 = (PVOID *)WPP_GLOBAL_Control;
              }
LABEL_462:
              if ( *((_WORD *)this + 85) == 0xFFFF )
              {
                LODWORD(v65) = rgIndices;
              }
              else
              {
                v65 = (unsigned int)rgIndices;
                if ( rgIndices )
                {
                  v66 = CoCreateInstance(
                          &CLSID_MsftStreamZero,
                          0,
                          0x17u,
                          &GUID_0000000c_0000_0000_c000_000000000046,
                          &v152);
                  CurrentPhysicalMediaType = v66;
                  if ( v66 < 0 )
                  {
                    v12 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                    {
                      goto LABEL_518;
                    }
                    v67 = 68;
                    goto LABEL_517;
                  }
                  v68 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v152 + 48LL))(v152, v65 << 11);
                  CurrentPhysicalMediaType = v68;
                  if ( v68 < 0 )
                  {
                    v12 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                    {
                      goto LABEL_522;
                    }
                    WPP_SF_id(
                      *((_QWORD *)WPP_GLOBAL_Control + 37),
                      69,
                      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                      v65 << 11,
                      v68,
                      v126,
                      v127);
                    goto LABEL_87;
                  }
                  v14 = 0;
                }
                else if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                {
                  goto LABEL_522;
                }
              }
              if ( *((_WORD *)this + 85) == 0xFFFF )
              {
                rgIndices = v65;
              }
              else
              {
                Instance = CoCreateInstance(
                             &CLSID_MsftWriteEngine2,
                             0,
                             0x17u,
                             &GUID_27354135_7f64_5b0f_8f00_5d77afbe261e,
                             (LPVOID *)this + 24);
                CurrentPhysicalMediaType = Instance;
                if ( Instance < 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                  {
                    goto LABEL_522;
                  }
                  v49 = 70;
                  goto LABEL_330;
                }
              }
              if ( *((_WORD *)this + 85) != 0xFFFF )
              {
                v66 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 24) + 72LL))(
                        *((_QWORD *)this + 24),
                        *((_QWORD *)this + 27));
                CurrentPhysicalMediaType = v66;
                if ( v66 < 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                  {
                    goto LABEL_518;
                  }
                  v67 = 71;
                  goto LABEL_517;
                }
                v66 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 24) + 88LL))(
                        *((_QWORD *)this + 24),
                        0);
                CurrentPhysicalMediaType = v66;
                if ( v66 < 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                  {
                    goto LABEL_518;
                  }
                  v67 = 72;
                  goto LABEL_517;
                }
                v66 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 24) + 104LL))(
                        *((_QWORD *)this + 24),
                        3000);
                CurrentPhysicalMediaType = v66;
                if ( v66 < 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                  {
                    goto LABEL_518;
                  }
                  v67 = 73;
                  goto LABEL_517;
                }
                v66 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 24) + 120LL))(
                        *((_QWORD *)this + 24),
                        3000);
                CurrentPhysicalMediaType = v66;
                if ( v66 < 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                  {
                    goto LABEL_518;
                  }
                  v67 = 74;
                  goto LABEL_517;
                }
                Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 24) + 136LL))(
                             *((_QWORD *)this + 24),
                             2048);
                CurrentPhysicalMediaType = Instance;
                if ( Instance < 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                  {
                    goto LABEL_522;
                  }
                  v49 = 75;
                  goto LABEL_330;
                }
              }
              if ( *((_DWORD *)this + 23) != -16843010 )
                ATL::AtlThrowImpl(-2147467259);
              v66 = ATL::AtlAdvise(
                      *((struct IUnknown **)this + 24),
                      (struct IUnknown *)this + 6,
                      v64,
                      (unsigned int *)this + 23);
              CurrentPhysicalMediaType = v66;
              if ( v66 >= 0 )
              {
                v12 = (PVOID *)WPP_GLOBAL_Control;
                v13 = 0;
                BYTE4(v133.lpVtbl) = 1;
                v2 = 0;
                goto LABEL_523;
              }
              v12 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
              {
                goto LABEL_518;
              }
              v67 = 76;
LABEL_517:
              WPP_SF_d(v12[37], v67, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, (unsigned int)v66);
              v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_518:
              v13 = 0;
              v2 = 0;
              goto LABEL_734;
            }
            if ( !v139 )
            {
              if ( v129 )
              {
                Instance = CMsftDiscFormat2Data::SetDvdPlusRLayerChange(this, v58);
                CurrentPhysicalMediaType = Instance;
                if ( Instance < 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                  {
                    goto LABEL_522;
                  }
                  v49 = 66;
                  goto LABEL_330;
                }
              }
            }
          }
          v12 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_462;
        }
        if ( *((_WORD *)this + 114) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 51, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
          v129 = 1;
          goto LABEL_345;
        }
        LOBYTE(lpVtbl_low) = v133.lpVtbl;
        if ( LODWORD(v133.lpVtbl) <= 0x13 )
        {
          v50 = 528416;
          if ( _bittest(&v50, (unsigned int)v133.lpVtbl) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                52,
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                LODWORD(v133.lpVtbl));
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            v129 = 0;
LABEL_345:
            if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
              goto LABEL_522;
            goto LABEL_432;
          }
        }
        LOBYTE(lpVtbl_low) = v133.lpVtbl;
        v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 2);
        if ( LODWORD(v133.lpVtbl) == 2 || (v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 3), LODWORD(v133.lpVtbl) == 3) )
        {
          if ( v139 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 55, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            LODWORD(v14) = 6750;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 54, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            LODWORD(v14) = 11250;
          }
          goto LABEL_418;
        }
        v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 6);
        if ( LODWORD(v133.lpVtbl) != 6 )
        {
          v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 7);
          if ( LODWORD(v133.lpVtbl) == 7 )
            goto LABEL_398;
          v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 8);
          if ( LODWORD(v133.lpVtbl) != 8 )
          {
            if ( LODWORD(v133.lpVtbl) == 9 )
              goto LABEL_362;
            v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 10);
            if ( LODWORD(v133.lpVtbl) != 10 )
            {
              v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 11);
              if ( LODWORD(v133.lpVtbl) != 11 )
              {
                if ( LODWORD(v133.lpVtbl) != 18 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 305) )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 37),
                      64,
                      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                      LODWORD(v133.lpVtbl));
                    v12 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  CurrentPhysicalMediaType = -2147467263;
                  goto LABEL_518;
                }
                v51 = v136;
                LODWORD(v14) = (((_BYTE)v28 + (_BYTE)v136) & 0x1F) + 0x10000;
                goto LABEL_419;
              }
LABEL_362:
              v51 = v136;
              v52 = ((_BYTE)v28 + (_BYTE)v136) & 0xF;
              v10 = (unsigned int)v136 + v139 + v28;
              if ( (unsigned int)v10 >= 0xFF00 )
              {
                if ( (unsigned int)v10 >= 0x82600 )
                {
                  if ( (unsigned int)v10 >= 0x135700 )
                  {
                    if ( v139 )
                    {
                      LODWORD(v14) = v52 + 9728;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                      {
                        goto LABEL_419;
                      }
                      v53 = 63;
                    }
                    else
                    {
                      LODWORD(v14) = v52 + 47104;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                      {
                        goto LABEL_419;
                      }
                      v53 = 62;
                    }
                  }
                  else if ( v139 )
                  {
                    LODWORD(v14) = v52 + 7680;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                    {
                      goto LABEL_419;
                    }
                    v53 = 61;
                  }
                  else
                  {
                    LODWORD(v14) = v52 + 37888;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                    {
                      goto LABEL_419;
                    }
                    v53 = 60;
                  }
                }
                else
                {
                  if ( !v139 )
                  {
                    lpVtbl_low = (unsigned int)(v52 + 28672);
                    LODWORD(v14) = v52 + 28672;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                    {
                      goto LABEL_419;
                    }
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 37),
                      58,
                      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                      lpVtbl_low,
                      lpVtbl_low);
                    goto LABEL_368;
                  }
                  LODWORD(v14) = v52 + 6192;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                  {
                    goto LABEL_419;
                  }
                  v53 = 59;
                }
              }
              else
              {
                LODWORD(v14) = v52 - v139 - v28 - v136 + 93952;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
                {
                  goto LABEL_419;
                }
                v53 = 57;
              }
LABEL_367:
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                v53,
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                (unsigned int)v14,
                (_DWORD)v14);
LABEL_368:
              v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_418:
              v51 = v136;
LABEL_419:
              if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                goto LABEL_522;
              if ( v137 >= (unsigned int)(v28 + v51) )
                v54 = v137 - (v28 + v51);
              else
                v54 = 0;
              if ( v54 >= (unsigned int)v14 )
                v55 = v54 - (_DWORD)v14;
              else
                v55 = 0;
              v10 = v137 / 0x32u;
              if ( v55 < (unsigned int)v10 )
              {
                if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
                  WPP_SF_dDdDdDdDdDL(
                    (unsigned int)v12[37],
                    v10,
                    v55,
                    v137,
                    v137,
                    v51,
                    v51,
                    v28,
                    v28,
                    (char)v14,
                    (char)v14,
                    v10,
                    v10,
                    (char)v133.lpVtbl);
                v129 = 1;
              }
              goto LABEL_432;
            }
LABEL_398:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                53,
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                LODWORD(v133.lpVtbl));
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            v129 = 1;
            goto LABEL_418;
          }
        }
        v51 = v136;
        LODWORD(v14) = (((_BYTE)v28 + (_BYTE)v136) & 0xF) + 2048;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
        {
          goto LABEL_419;
        }
        v53 = 56;
        goto LABEL_367;
      }
    }
    v29 = v136;
    if ( !*((_WORD *)this + 113) )
    {
      v28 = 150;
      rgIndices = 150;
      if ( (unsigned int)v136 >= 0x96 )
      {
        if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 308) & 4) == 0 || *((_BYTE *)v12 + 305) < 4u )
          goto LABEL_289;
        WPP_SF_Dd(v12[37], 43, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, (unsigned int)v136, v136);
        goto LABEL_300;
      }
      v28 = 300 - v136;
      rgIndices = 300 - v136;
      if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 308) & 4) == 0 || *((_BYTE *)v12 + 305) < 4u )
        goto LABEL_289;
      v30 = 42;
LABEL_299:
      v127 = v136;
      v126 = v136;
      ppv = v28;
      WPP_SF_DDDd(v12[37], v30, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
LABEL_300:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      v29 = v136;
      goto LABEL_289;
    }
    if ( (unsigned int)v136 >= 0x96 )
    {
      if ( (unsigned int)v136 < 0x12C )
      {
        v28 = 300 - v136;
        rgIndices = 300 - v136;
        if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 308) & 4) == 0 || *((_BYTE *)v12 + 305) < 4u )
          goto LABEL_289;
        v30 = 45;
        goto LABEL_299;
      }
    }
    else
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
      {
        WPP_SF_Dd(v12[37], 44, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, (unsigned int)v136, v136);
        v12 = (PVOID *)WPP_GLOBAL_Control;
        v29 = v136;
      }
      CurrentPhysicalMediaType = -1062599677;
    }
    rgIndices = 0;
    v28 = 0;
LABEL_289:
    if ( v28 + v29 < v29 )
    {
      CurrentPhysicalMediaType = -1062599677;
      if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 308) & 4) == 0 || *((_BYTE *)v12 + 305) < 3u )
        goto LABEL_522;
      WPP_SF_Dd(v12[37], 46, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v29, v29);
      goto LABEL_253;
    }
    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
      goto LABEL_522;
    v10 = -1;
    goto LABEL_303;
  }
  CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(CMsftDiscFormat2Data *, LONG *, __int64))(*(_QWORD *)this + 80LL))(
                               this,
                               &rgIndices,
                               -1);
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
  {
LABEL_273:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_521;
  }
  if ( (_WORD)rgIndices )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_234;
  }
  CurrentPhysicalMediaType = -1062599675;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 35, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
    goto LABEL_86;
  }
LABEL_169:
  v14 = 0;
LABEL_170:
  if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_171;
LABEL_521:
  rgIndices = 0;
LABEL_522:
  v14 = 0;
  v13 = 0;
  v2 = 0;
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_734;
LABEL_523:
  if ( *((_WORD *)this + 85) == 0xFFFF )
    goto LABEL_540;
  *(_DWORD *)(*((_QWORD *)this + 23) + 64LL) = 2;
  CMsftDiscFormat2Data::UpdateProgress(this);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( *((_WORD *)this + 85) == 0xFFFF )
    goto LABEL_540;
  CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, void **, SIZE_T *, int, int))(**((_QWORD **)this + 27) + 104LL))(
                               *((_QWORD *)this + 27),
                               5,
                               0,
                               &Src,
                               &cb,
                               v126,
                               v127);
  if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
  {
    v70 = cb;
    if ( (unsigned int)cb >= 0x34 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
      {
        goto LABEL_541;
      }
      v71 = *(_OWORD *)LOG_BLOB(&v150, (unsigned int)cb, Src);
      v72 = *((_QWORD *)WPP_GLOBAL_Control + 37);
      *(_OWORD *)v146 = v71;
      WPP_SF__HEX_(v72, 79, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v146);
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_541;
      }
      ppv = cb;
      WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 37), 78, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_540:
    v70 = cb;
LABEL_541:
    if ( *((_WORD *)this + 85) == 0xFFFF )
      goto LABEL_590;
    v73 = (Imapi2Utility *)CoTaskMemAlloc(v70);
    v2 = v73;
    if ( !v73 )
    {
      CurrentPhysicalMediaType = -2147024882;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_734;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        80,
        &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
        (unsigned int)cb,
        cb);
      goto LABEL_733;
    }
    memcpy_0(v73, Src, (unsigned int)cb);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( *((_WORD *)this + 85) == 0xFFFF )
      goto LABEL_590;
    lpVtbl_low = LODWORD(v133.lpVtbl);
    if ( SLODWORD(v133.lpVtbl) > 9 )
    {
      LOBYTE(lpVtbl_low) = LOBYTE(v133.lpVtbl) - 10;
      if ( LODWORD(v133.lpVtbl) == 10 )
        goto LABEL_584;
      if ( LODWORD(v133.lpVtbl) != 11 )
      {
        LOBYTE(lpVtbl_low) = LOBYTE(v133.lpVtbl) - 12;
        if ( LODWORD(v133.lpVtbl) != 12 )
        {
          LOBYTE(lpVtbl_low) = LOBYTE(v133.lpVtbl) - 18;
          if ( (unsigned int)(LODWORD(v133.lpVtbl) - 18) >= 2 )
            goto LABEL_573;
        }
        goto LABEL_584;
      }
    }
    else if ( LODWORD(v133.lpVtbl) != 9 )
    {
      if ( LODWORD(v133.lpVtbl) != 2 && LODWORD(v133.lpVtbl) != 3 )
      {
        if ( LODWORD(v133.lpVtbl) != 5 )
        {
          if ( LODWORD(v133.lpVtbl) == 6 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
            {
              goto LABEL_590;
            }
            v74 = 83;
LABEL_588:
            lpVtbl_low = LODWORD(v133.lpVtbl);
            goto LABEL_589;
          }
          v10 = (unsigned int)(LODWORD(v133.lpVtbl) - 7);
          if ( LODWORD(v133.lpVtbl) != 7 )
          {
            if ( LODWORD(v133.lpVtbl) == 8 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
              {
                v74 = 84;
LABEL_589:
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                  v74,
                  &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                  lpVtbl_low);
                v12 = (PVOID *)WPP_GLOBAL_Control;
              }
LABEL_590:
              v10 = -1;
              if ( *((_WORD *)this + 85) == 0xFFFF || *((_WORD *)this + 112) )
                goto LABEL_599;
              *((_BYTE *)v2 + 2) |= 0x40u;
              v75 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, Imapi2Utility *, _QWORD, int))(**((_QWORD **)this + 27)
                                                                                            + 112LL))(
                      *((_QWORD *)this + 27),
                      0,
                      v2,
                      (unsigned int)cb,
                      ppv);
              if ( v75 < 0 )
              {
                v12 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                {
                  goto LABEL_598;
                }
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                  87,
                  &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                  (unsigned int)v75);
              }
              v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_598:
              v10 = -1;
LABEL_599:
              if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                goto LABEL_734;
              if ( *((_WORD *)this + 85) == 0xFFFF )
                goto LABEL_643;
              v76 = *((_QWORD *)this + 27);
              v146[0] = 0;
              v137 = 0;
              v77 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, Imapi2Utility **))(*(_QWORD *)v76 + 104LL))(
                      v76,
                      5,
                      0,
                      v146);
              if ( v77 >= 0 )
              {
                if ( (unsigned int)(LODWORD(v133.lpVtbl) - 2) <= 1 )
                  Imapi2Utility::NormalizeWriteParametersModePageForCDMedia(
                    v146[0],
                    (struct _MODE_CDROM_WRITE_PARAMETERS_PAGE2 *)(unsigned int)v137,
                    v78);
                if ( Imapi2Utility::AreWriteParametersModePagesEqual(
                       v2,
                       (const struct _MODE_CDROM_WRITE_PARAMETERS_PAGE2 *)(unsigned int)cb,
                       (unsigned int)v146[0],
                       (const struct _MODE_CDROM_WRITE_PARAMETERS_PAGE2 *)(unsigned int)v137,
                       (unsigned int)&v137) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
                  {
                    v79 = *(_OWORD *)LOG_BLOB(&pvarg, (unsigned int)v137, v146[0]);
                    v80 = *((_QWORD *)WPP_GLOBAL_Control + 37);
                    v150 = v79;
                    WPP_SF__HEX_(v80, 90, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, &v150);
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 89, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                  88,
                  &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                  (unsigned int)v77);
              }
              CoTaskMemFree(v146[0]);
              v12 = (PVOID *)WPP_GLOBAL_Control;
              v10 = -1;
              if ( *((_WORD *)this + 85) == 0xFFFF )
                goto LABEL_643;
              if ( (unsigned int)(*((_DWORD *)this + 62) - 1) > 1 )
              {
LABEL_632:
                if ( *((_WORD *)this + 85) != 0xFFFF )
                {
                  *(_DWORD *)(*((_QWORD *)this + 23) + 64LL) = 3;
                  CMsftDiscFormat2Data::UpdateProgress(this);
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  v10 = -1;
                  if ( *((_WORD *)this + 85) != 0xFFFF )
                  {
                    started = Imapi2Utility::SendStartStopUnitCommand(*((_QWORD *)this + 27));
                    CurrentPhysicalMediaType = started;
                    if ( started >= 0 )
                    {
                      v12 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    else
                    {
                      v12 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 37),
                          92,
                          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                          (unsigned int)started);
                        v12 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      CurrentPhysicalMediaType = IMAPI_MEDIA_TYPE_UNKNOWN;
                    }
                    v10 = -1;
                  }
                }
LABEL_643:
                if ( *((_WORD *)this + 85) == 0xFFFF )
                  goto LABEL_672;
                v85 = Imapi2Utility::RequestAutomaticOPC(
                        *((Imapi2Utility **)this + 27),
                        (struct IDiscRecorder2Ex *)0xFFFFFFFFFFFFFFFFLL);
                CurrentPhysicalMediaType = v85;
                if ( v85 >= 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                }
                else
                {
                  if ( v85 == -1062600177 )
                    goto LABEL_733;
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 37),
                      93,
                      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                      (unsigned int)v85);
                    v12 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  CurrentPhysicalMediaType = IMAPI_MEDIA_TYPE_UNKNOWN;
                }
                v10 = -1;
                if ( *((_WORD *)this + 85) == 0xFFFF )
                  goto LABEL_672;
                LOBYTE(lpVtbl_low) = v133.lpVtbl;
                if ( LODWORD(v133.lpVtbl) > 0x13 )
                  goto LABEL_671;
                v86 = 787584;
                if ( !_bittest(&v86, (unsigned int)v133.lpVtbl) )
                  goto LABEL_671;
                *(_DWORD *)(*((_QWORD *)this + 23) + 64LL) = 1;
                if ( LODWORD(v133.lpVtbl) == 7 )
                {
                  v87 = CMsftDiscFormat2Data::FormatDvdPlusRWMedia(this);
                }
                else if ( LODWORD(v133.lpVtbl) == 10 )
                {
                  v87 = CMsftDiscFormat2Data::FormatDvdDashRWMedia(this, *((_WORD *)this + 116));
                }
                else
                {
                  LOBYTE(lpVtbl_low) = v133.lpVtbl;
                  if ( (unsigned int)(LODWORD(v133.lpVtbl) - 18) > 1 )
                  {
                    CurrentPhysicalMediaType = -2147467259;
                    v12 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                      goto LABEL_734;
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 305) < 2u )
                      goto LABEL_667;
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 37),
                      94,
                      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                      LODWORD(v133.lpVtbl));
LABEL_666:
                    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_667:
                    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) >= 3u )
                    {
                      WPP_SF_Dd(
                        v12[37],
                        95,
                        &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                        LODWORD(v133.lpVtbl),
                        CurrentPhysicalMediaType);
                      v12 = (PVOID *)WPP_GLOBAL_Control;
                    }
LABEL_671:
                    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                      goto LABEL_734;
LABEL_672:
                    if ( *((_WORD *)this + 85) != 0xFFFF )
                    {
                      *(_DWORD *)(*((_QWORD *)this + 23) + 64LL) = 4;
                      if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                        goto LABEL_733;
                      v12 = (PVOID *)WPP_GLOBAL_Control;
                      if ( *((_WORD *)this + 85) != 0xFFFF )
                      {
                        if ( psa )
                        {
                          v88 = plLbound;
                          v89 = plUbound;
                        }
                        else
                        {
                          v88 = 0;
                          v89 = 0;
                        }
                        v137 = v88;
                        *((_DWORD *)this + 50) = 0;
                        while ( 1 )
                        {
                          if ( v88 > v89 )
                          {
                            v12 = (PVOID *)WPP_GLOBAL_Control;
                            break;
                          }
                          v135 = 0;
                          v134 = 0;
                          memset(&pvarg, 0, sizeof(pvarg));
                          if ( !psa )
                          {
                            v90 = v139;
                            LODWORD(lpVtbl_low) = v139 + v136;
                            v134 = v139;
                            v135 = v139 + v136;
                            goto LABEL_711;
                          }
                          v146[0] = 0;
                          if ( SafeArrayGetElement(psa, &v137, &pvarg) < 0 )
                          {
                            CurrentPhysicalMediaType = -2147467262;
                          }
                          else
                          {
                            if ( pvarg.vt == 9 && pvarg.llVal )
                              CurrentPhysicalMediaType = (**(unsigned int (__fastcall ***)(LONGLONG, GUID *, Imapi2Utility **))pvarg.llVal)(
                                                           pvarg.llVal,
                                                           &GUID_b507ca25_2204_11dd_966a_001aa01bbc58,
                                                           v146);
                            else
                              CurrentPhysicalMediaType = -2147467262;
                            VariantClear(&pvarg);
                            if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
                            {
                              CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(Imapi2Utility *, int *))(*(_QWORD *)v146[0] + 56LL))(
                                                           v146[0],
                                                           &v134);
                              if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
                                CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(Imapi2Utility *, int *))(*(_QWORD *)v146[0] + 64LL))(
                                                             v146[0],
                                                             &v135);
                            }
                          }
                          v90 = (unsigned int)v134;
                          LODWORD(lpVtbl_low) = ++v135;
                          if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
                          {
                            if ( v134 < 0 || (int)lpVtbl_low <= v134 )
                            {
                              v94 = (PVOID *)WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
                              {
                                WPP_SF_DDDd(
                                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                                  96,
                                  &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
                                v94 = (PVOID *)WPP_GLOBAL_Control;
                                v90 = (unsigned int)v134;
                                LODWORD(lpVtbl_low) = v135;
                              }
                              CurrentPhysicalMediaType = -2147024809;
                              goto LABEL_702;
                            }
                            v91 = rgIndices;
                            if ( LODWORD(v133.lpVtbl) == 10 )
                            {
                              LODWORD(v90) = v134 - (v134 & 0x8000000F);
                              v134 = v90;
                              if ( (int)lpVtbl_low % 16 )
                              {
                                if ( (unsigned int)lpVtbl_low <= 0xFFFFFFEF )
                                  v135 = lpVtbl_low + 16 - ((int)lpVtbl_low + 16) % 16;
                              }
                            }
                            v92 = (__int64)(int)v90 << 11;
                            *(_QWORD *)&v150 = 0;
                            if ( v148 )
                            {
                              CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(_QWORD *, __int64, _QWORD, __int128 *))(*v148 + 40LL))(
                                                           v148,
                                                           v92,
                                                           0,
                                                           &v150);
                              rgIndices = v91;
                            }
                            else
                            {
                              v93 = v141;
                              CurrentPhysicalMediaType = ((unsigned int (__fastcall *)(struct IUnknown *, __int64, _QWORD, __int128 *))v141->lpVtbl[1].Release)(
                                                           v141,
                                                           v92,
                                                           0,
                                                           &v150);
                              v141 = v93;
                            }
                            v90 = (unsigned int)v134;
                            LODWORD(lpVtbl_low) = v135;
                          }
                          v94 = (PVOID *)WPP_GLOBAL_Control;
LABEL_702:
                          v10 = (__int64)v146[0];
                          if ( !v146[0] )
                            goto LABEL_712;
                          (*(void (__fastcall **)(Imapi2Utility *))(*(_QWORD *)v146[0] + 16LL))(v146[0]);
                          v90 = (unsigned int)v134;
                          LODWORD(lpVtbl_low) = v135;
LABEL_711:
                          v94 = (PVOID *)WPP_GLOBAL_Control;
LABEL_712:
                          if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                            goto LABEL_718;
                          v95 = (struct IUnknown *)v148;
                          if ( v148 )
                          {
                            v148[4] = 0;
                            LODWORD(lpVtbl_low) = v135;
                            v90 = (unsigned int)v134;
                          }
                          else
                          {
                            v95 = v141;
                          }
                          CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(_QWORD, struct IUnknown *, __int64, _QWORD))(**((_QWORD **)this + 24) + 56LL))(
                                                       *((_QWORD *)this + 24),
                                                       v95,
                                                       v90,
                                                       (unsigned int)(lpVtbl_low - v90));
                          if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                          {
                            v94 = (PVOID *)WPP_GLOBAL_Control;
LABEL_718:
                            if ( v94 != &WPP_GLOBAL_Control
                              && (*((_BYTE *)v94 + 308) & 4) != 0
                              && *((_BYTE *)v94 + 305) >= 3u )
                            {
                              WPP_SF_d(
                                v94[37],
                                97,
                                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                                (unsigned int)CurrentPhysicalMediaType);
                            }
                          }
                          v96 = v137;
                          v13 = 1;
                          ++*((_DWORD *)this + 50);
                          v88 = v96 + 1;
                          v137 = v88;
                          if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                            goto LABEL_733;
                        }
                      }
                    }
                    if ( *((_WORD *)this + 85) == 0xFFFF || !rgIndices )
                      goto LABEL_734;
                    CurrentPhysicalMediaType = (*(unsigned int (__fastcall **)(_QWORD, LPVOID, _QWORD, _QWORD))(**((_QWORD **)this + 24) + 56LL))(
                                                 *((_QWORD *)this + 24),
                                                 v152,
                                                 (unsigned int)v136 + v139,
                                                 (unsigned int)rgIndices);
                    if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
                    {
LABEL_733:
                      v12 = (PVOID *)WPP_GLOBAL_Control;
                      goto LABEL_734;
                    }
                    v12 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
                    {
                      goto LABEL_734;
                    }
                    v69 = 98;
LABEL_732:
                    WPP_SF_d(
                      v12[37],
                      v69,
                      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                      (unsigned int)CurrentPhysicalMediaType);
                    goto LABEL_733;
                  }
                  v87 = CMsftDiscFormat2Data::PrepareBDMedia(this, (enum _IMAPI_MEDIA_PHYSICAL_TYPE)v133.lpVtbl);
                }
                CurrentPhysicalMediaType = v87;
                if ( v87 >= 0 )
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  goto LABEL_672;
                }
                goto LABEL_666;
              }
              v81 = ATL::CComObject<CMsftStreamCRC>::CreateInstance(&v148);
              CurrentPhysicalMediaType = v81;
              if ( v81 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                  91,
                  &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                  (unsigned int)v81);
              }
              (*(void (__fastcall **)(_QWORD *))(*v148 + 8LL))(v148);
              if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                goto LABEL_733;
              v82 = v148;
              v83 = 0x100000;
              if ( *((_DWORD *)this + 62) != 1 )
                v83 = -1;
              if ( (struct IUnknown *)v148[2] != v141 )
                ATL::AtlComPtrAssign((struct IUnknown **)v148 + 2, v141);
              *((_DWORD *)v82 + 6) = -1;
              v82[4] = 0;
              v82[5] = v83;
              v14 = (CMsftDiscInformation *)operator new(0x10u);
              if ( v14 )
              {
                *(_QWORD *)v14 = 0;
                *((_QWORD *)v14 + 1) = 0;
                CurrentPhysicalMediaType = (unsigned int)CMsftDiscInformation::Init(
                                                           v14,
                                                           *((struct IDiscRecorder2Ex **)this + 27));
                if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
                  goto LABEL_733;
                v12 = (PVOID *)WPP_GLOBAL_Control;
                v10 = -1;
                goto LABEL_632;
              }
              CurrentPhysicalMediaType = -2147024882;
LABEL_88:
              v14 = 0;
              goto LABEL_733;
            }
LABEL_573:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 305) )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                86,
                &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                LODWORD(v133.lpVtbl));
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            CurrentPhysicalMediaType = -2147467263;
            goto LABEL_734;
          }
        }
LABEL_584:
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
        {
          goto LABEL_590;
        }
        v74 = 82;
        goto LABEL_588;
      }
      CurrentPhysicalMediaType = CMsftDiscFormat2Data::SetCDRModePageForTrackAtOnceWriting(
                                   this,
                                   (struct _MODE_CDROM_WRITE_PARAMETERS_PAGE2 *)v2,
                                   cb,
                                   v129);
      if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
        {
          goto LABEL_734;
        }
        v69 = 81;
        goto LABEL_732;
      }
LABEL_583:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_590;
    }
    CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::SetDvdDashModePageForIncrementalWriting(
                                               this,
                                               (struct _MODE_CDROM_WRITE_PARAMETERS_PAGE2 *)v2,
                                               cb,
                                               v129);
    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_734;
      }
      v69 = 85;
      goto LABEL_732;
    }
    goto LABEL_583;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
  {
    v69 = 77;
    goto LABEL_732;
  }
LABEL_734:
  v97 = *((_QWORD *)this + 23);
  if ( v97 )
  {
    *(_DWORD *)(v97 + 64) = 5;
    CMsftDiscFormat2Data::UpdateProgress(this);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN || *((_WORD *)this + 85) == 0xFFFF) && !v13 )
    goto LABEL_805;
  v98 = CurrentPhysicalMediaType;
  if ( SLODWORD(v133.lpVtbl) > 9 )
  {
    switch ( LODWORD(v133.lpVtbl) )
    {
      case 0xA:
        CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::FinalizeDvdDashRWMedia(this);
        if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
          goto LABEL_803;
        v99 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
        {
          goto LABEL_803;
        }
        v100 = 107;
        break;
      case 0xB:
LABEL_792:
        CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::FinalizeDvdDashRMedia(
                                                   this,
                                                   (unsigned int)v140.lpVtbl,
                                                   v144,
                                                   (enum _IMAPI_MEDIA_PHYSICAL_TYPE)v133.lpVtbl,
                                                   (int)v136 + rgIndices);
        if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
          goto LABEL_803;
        v99 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
        {
          goto LABEL_803;
        }
        v100 = 106;
        break;
      case 0xC:
LABEL_782:
        CurrentPhysicalMediaType = (unsigned int)Imapi2Utility::SendSynchronizeCacheCommand(
                                                   *((Imapi2Utility **)this + 27),
                                                   (struct IDiscRecorder2Ex *)v10,
                                                   0,
                                                   lpVtbl_low);
        if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
        {
          v101 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_803;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
            goto LABEL_788;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            99,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)CurrentPhysicalMediaType);
        }
        v101 = (PVOID *)WPP_GLOBAL_Control;
LABEL_788:
        if ( v101 != &WPP_GLOBAL_Control && (*((_BYTE *)v101 + 308) & 4) != 0 && *((_BYTE *)v101 + 305) >= 4u )
          WPP_SF_d(v101[37], 100, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, LODWORD(v133.lpVtbl));
        goto LABEL_803;
      case 0x12:
        CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::FinalizeBDRMedia(
                                                   this,
                                                   (unsigned int)v140.lpVtbl,
                                                   v129);
        if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
          goto LABEL_803;
        v99 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
        {
          goto LABEL_803;
        }
        v100 = 102;
        break;
      case 0x13:
        goto LABEL_782;
      default:
LABEL_772:
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 308) & 4) != 0 && *((_BYTE *)v12 + 305) )
          WPP_SF_d(v12[37], 108, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, LODWORD(v133.lpVtbl));
        CurrentPhysicalMediaType = -2147467263;
        goto LABEL_803;
    }
LABEL_802:
    WPP_SF_d(v99[37], v100, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, (unsigned int)CurrentPhysicalMediaType);
    goto LABEL_803;
  }
  switch ( LODWORD(v133.lpVtbl) )
  {
    case 9:
      goto LABEL_792;
    case 2:
    case 3:
      CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::FinalizeCDMedia(
                                                 this,
                                                 (unsigned int)v140.lpVtbl,
                                                 v144);
      if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
        goto LABEL_803;
      v99 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_803;
      }
      v100 = 101;
      goto LABEL_802;
    case 5:
      goto LABEL_782;
    case 6:
      CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::FinalizeDvdPlusRMedia(this, v144, v129);
      if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
        goto LABEL_803;
      v99 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_803;
      }
      v100 = 104;
      goto LABEL_802;
    case 7:
      CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::FinalizeDvdPlusRWMedia(this);
      if ( CurrentPhysicalMediaType >= IMAPI_MEDIA_TYPE_UNKNOWN )
        goto LABEL_803;
      v99 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 3u )
      {
        goto LABEL_803;
      }
      v100 = 105;
      goto LABEL_802;
  }
  if ( LODWORD(v133.lpVtbl) != 8 )
    goto LABEL_772;
  CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::FinalizeDvdPlusRDualLayerMedia(this, v144, v129);
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
  {
    v99 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      v100 = 103;
      goto LABEL_802;
    }
  }
LABEL_803:
  if ( v98 < 0 )
  {
    CurrentPhysicalMediaType = v98;
    goto LABEL_830;
  }
LABEL_805:
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_830;
  if ( *((_WORD *)this + 85) == 0xFFFF )
    goto LABEL_828;
  if ( (unsigned int)(*((_DWORD *)this + 62) - 1) <= 1 )
  {
    v102 = *((_QWORD *)this + 23);
    if ( v102 )
    {
      *(_DWORD *)(v102 + 64) = 7;
      CMsftDiscFormat2Data::UpdateProgress(this);
    }
  }
  if ( *((_WORD *)this + 85) == 0xFFFF || (unsigned int)(*((_DWORD *)this + 62) - 1) > 1 )
    goto LABEL_828;
  CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::VerifyReadDiscInformationData(
                                             this,
                                             (enum _IMAPI_MEDIA_PHYSICAL_TYPE)v133.lpVtbl,
                                             v14,
                                             v129);
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_830;
  v103 = v136;
  v104 = v139;
  CurrentPhysicalMediaType = (unsigned int)CMsftDiscFormat2Data::VerifyLastTrackInformationData(
                                             this,
                                             (enum _IMAPI_MEDIA_PHYSICAL_TYPE)v133.lpVtbl,
                                             v139,
                                             (int)v136 + rgIndices);
  if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_830;
  if ( *((_DWORD *)this + 62) == 1 )
  {
    v106 = (Imapi2Utility *)*((_QWORD *)this + 27);
    LODWORD(v140.lpVtbl) = 0;
    LODWORD(v146[0]) = 0;
    CurrentPhysicalMediaType = (unsigned int)Imapi2Utility::ReadMediaCapacity(v106, &v140, (unsigned int *)v146, v105);
    if ( CurrentPhysicalMediaType < IMAPI_MEDIA_TYPE_UNKNOWN )
      goto LABEL_830;
    v107 = 0x100000u / LODWORD(v140.lpVtbl);
  }
  else
  {
    v107 = -1;
  }
  if ( psa )
  {
    v108 = CMsftDiscFormat2Data::VerifySpecificBlockRanges(
             this,
             psa,
             (enum _IMAPI_MEDIA_PHYSICAL_TYPE)v133.lpVtbl,
             v104,
             v107,
             ~*((_DWORD *)v148 + 6));
  }
  else
  {
    if ( v107 < v103 )
      v103 = v107;
    v108 = CMsftDiscFormat2Data::VerifyDataSection(this, v104, v103, ~*((_DWORD *)v148 + 6));
  }
  CurrentPhysicalMediaType = v108;
  if ( v108 >= 0 )
  {
LABEL_828:
    v109 = *((_QWORD *)this + 23);
    if ( v109 )
    {
      *(_DWORD *)(v109 + 64) = 6;
      CMsftDiscFormat2Data::UpdateProgress(this);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 109, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
  }
LABEL_830:
  v110 = 0;
  if ( BYTE4(v133.lpVtbl) )
  {
    v111 = ATL::AtlUnadvise(*((struct IUnknown **)this + 24), (const struct _GUID *)v10, *((_DWORD *)this + 23));
    *((_DWORD *)this + 23) = -16843010;
    if ( v111 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        110,
        &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
        (unsigned int)v111);
    }
  }
  if ( v151 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v151 + 16LL))(v151);
    v151 = 0;
  }
  Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&psa, (struct tagSAFEARRAY **)v10);
  if ( v152 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v152 + 16LL))(v152);
    v152 = 0;
  }
  v112 = *((_QWORD *)this + 24);
  if ( v112 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
    *((_QWORD *)this + 24) = 0;
  }
  if ( v141 )
    ((void (__fastcall *)(struct IUnknown *))v141->lpVtbl->Release)(v141);
  if ( v148 )
    (*(void (__fastcall **)(_QWORD *))(*v148 + 16LL))(v148);
  if ( Src )
  {
    while ( v110 < 5 )
    {
      v113 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, _QWORD))(**((_QWORD **)this + 27) + 112LL))(
               *((_QWORD *)this + 27),
               0,
               Src,
               (unsigned int)cb);
      if ( v113 >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 112, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v110);
        }
        break;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          111,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v113);
      }
      Sleep(0x3E8u);
      ++v110;
    }
  }
  CoTaskMemFree(Src);
  Src = 0;
  CoTaskMemFree(v2);
  if ( v131 )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( (int)Imapi2Utility::PreventAllowMediumRemoval(*((Imapi2Utility **)this + 27), 0, v114, v115) >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 114, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, i);
        }
        break;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          113,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          i,
          CurrentPhysicalMediaType);
      }
      Sleep(0x3E8u);
    }
  }
  if ( v132 )
  {
    for ( j = 0; j < 5; ++j )
    {
      if ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 80LL))(*((_QWORD *)this + 26)) >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 116, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, j);
        }
        break;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          115,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          j,
          CurrentPhysicalMediaType);
      }
      Sleep(0x3E8u);
    }
  }
  if ( *((_WORD *)this + 85) == 0xFFFF )
    CurrentPhysicalMediaType = -1062600702;
  if ( v13
    || CurrentPhysicalMediaType != -2147467261
    && ((unsigned int)(CurrentPhysicalMediaType + 1062599680) > 6
     || (v118 = 89, !_bittest(&v118, CurrentPhysicalMediaType + 1062599680)))
    && CurrentPhysicalMediaType != -1062600701 )
  {
    v119 = GetTickCount();
    Imapi2Utility::SQMLogImapiSession(
      *((Imapi2Utility **)this + 26),
      0,
      (unsigned int)v133.lpVtbl,
      CurrentPhysicalMediaType,
      v119 - TickCount,
      *((_DWORD *)this + 62),
      0,
      0,
      v128);
  }
  v120 = *((_QWORD *)this + 23);
  if ( v120 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
    *((_QWORD *)this + 23) = 0;
  }
  v121 = PowerRequest;
  v122 = PowerRequest;
  *((_DWORD *)this + 42) = 0;
  if ( !PowerClearRequest(v122, PowerRequestExecutionRequired) )
    GetLastError();
  CloseHandle(v121);
  if ( (CurrentPhysicalMediaType & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(CurrentPhysicalMediaType, (int)&CLSID_MsftDiscFormat2Data, v123);
  return (unsigned int)CurrentPhysicalMediaType;
}

```

## disassembly

```asm
0x18001dd30  mov     [rsp-8+arg_10], rbx
0x18001dd35  push    rbp
0x18001dd36  push    rsi
0x18001dd37  push    rdi
0x18001dd38  push    r12
0x18001dd3a  push    r13
0x18001dd3c  push    r14
0x18001dd3e  push    r15
0x18001dd40  lea     rbp, [rsp-0D0h]
0x18001dd48  sub     rsp, 1D0h
0x18001dd4f  mov     rax, cs:__security_cookie
0x18001dd56  xor     rax, rsp
0x18001dd59  mov     [rbp+100h+var_40], rax
0x18001dd60  xor     r15d, r15d
0x18001dd63  mov     r14, rdx
0x18001dd66  mov     r13, rcx
0x18001dd69  mov     [rsp+200h+var_188], r15b
0x18001dd6e  xor     edx, edx; Val
0x18001dd70  mov     [rsp+200h+var_187], r15b
0x18001dd75  lea     rcx, [rbp+100h+pv]; void *
0x18001dd79  mov     [rbp+100h+var_180], r15b
0x18001dd7d  lea     r8d, [r15+50h]; Size
0x18001dd81  mov     [rsp+200h+var_184], r15d
0x18001dd86  mov     dword ptr [rbp+100h+cb+4], r15d
0x18001dd8a  call    memset_0
0x18001dd8f  xorps   xmm0, xmm0
0x18001dd92  mov     dword ptr [rbp+100h+var_130], r15d
0x18001dd96  lea     rax, aImapiDataWrite; "Imapi data write is in progress..."
0x18001dd9d  mov     [rbp+100h+var_168], r15d
0x18001dda1  or      ebx, 0FFFFFFFFh
0x18001dda4  mov     qword ptr [rbp+100h+Context.Reason], rax
0x18001dda8  lea     rcx, [rbp+100h+Context]; Context
0x18001ddac  mov     [rbp+100h+var_170], rbx
0x18001ddb0  movdqu  xmmword ptr [rbp+100h+Context.Reason+8], xmm0
0x18001ddb5  mov     [rbp+100h+var_15C], r15d
0x18001ddb9  mov     dword ptr [rbp+100h+var_158.lpVtbl], r15d
0x18001ddbd  mov     [rbp+100h+var_13C], r15d
0x18001ddc1  mov     [rsp+200h+var_190], r15b
0x18001ddc6  mov     [rbp+100h+var_E8], r15
0x18001ddca  mov     [rbp+100h+Src], r15
0x18001ddce  mov     dword ptr [rbp+100h+cb], r15d
0x18001ddd2  mov     [rbp+100h+var_150], r15
0x18001ddd6  mov     [rbp+100h+var_118], r15
0x18001ddda  mov     [rbp+100h+var_F0], r15
0x18001ddde  mov     [rbp+100h+psa], r15
0x18001dde2  mov     [rbp+100h+plLbound], r15d
0x18001dde6  mov     [rbp+100h+plUbound], r15d
0x18001ddea  mov     [rbp+100h+Context.Version], r15d
0x18001ddee  mov     [rbp+100h+Context.Flags], 1
0x18001ddf5  call    cs:__imp_PowerCreateRequest
0x18001ddfb  mov     [rbp+100h+PowerRequest], rax
0x18001ddff  mov     rdi, rax
0x18001de02  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001de06  jnz     short loc_18001DE1F
0x18001de08  call    cs:__imp_GetLastError
0x18001de0e  mov     edi, eax
0x18001de10  test    eax, eax
0x18001de12  jle     short loc_18001DE3F
0x18001de14  movzx   edi, ax
0x18001de17  or      edi, 80070000h
0x18001de1d  jmp     short loc_18001DE3F
0x18001de1f  mov     edx, 3; RequestType
0x18001de24  mov     rcx, rdi; PowerRequest
0x18001de27  call    cs:__imp_PowerSetRequest
0x18001de2d  test    eax, eax
0x18001de2f  jnz     short loc_18001DE3C
0x18001de31  mov     rcx, rdi; hObject
0x18001de34  call    cs:__imp_CloseHandle
0x18001de3a  jmp     short loc_18001DE08
0x18001de3c  mov     edi, r15d
0x18001de3f  call    cs:__imp_GetTickCount
0x18001de45  mov     [rbp+100h+var_C8], eax
0x18001de48  test    r14, r14
0x18001de4b  jnz     short loc_18001DEAB
0x18001de4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de54  lea     r14, WPP_GLOBAL_Control
0x18001de5b  mov     r12d, 4
0x18001de61  cmp     rcx, r14
0x18001de64  jz      short loc_18001DE97
0x18001de66  test    [rcx+134h], r12b
0x18001de6d  jz      short loc_18001DE97
0x18001de6f  cmp     byte ptr [rcx+131h], 3
0x18001de76  jb      short loc_18001DE97
0x18001de78  mov     rcx, [rcx+128h]
0x18001de7f  lea     edx, [r12+7]
0x18001de84  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18001de8b  call    WPP_SF_
0x18001de90  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de97  mov     edi, 80004003h
0x18001de9c  mov     [rsp+200h+rgIndices], r15d
0x18001dea1  mov     sil, r15b
0x18001dea4  xor     ebx, ebx
0x18001dea6  jmp     loc_180020988
0x18001deab  mov     dword ptr [rbp+100h+var_100], r15d
0x18001deaf  lea     r15, WPP_GLOBAL_Control
0x18001deb6  lea     rsi, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18001debd  mov     r12d, 4
0x18001dec3  test    edi, edi
0x18001dec5  js      loc_18001EDCF
0x18001decb  mov     rcx, r13; this
0x18001dece  call    ?ValidateRecorderSet@CMsftDiscFormat2Data@@AEAAJXZ; CMsftDiscFormat2Data::ValidateRecorderSet(void)
0x18001ded3  mov     edi, eax
0x18001ded5  xor     eax, eax
0x18001ded7  test    edi, edi
0x18001ded9  js      loc_18001EDCF
0x18001dedf  cmp     [r13+0A8h], ax
0x18001dee7  jz      short loc_18001DF3D
0x18001dee9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001def0  cmp     rcx, r15
0x18001def3  jz      short loc_18001DF26
0x18001def5  test    [rcx+134h], r12b
0x18001defc  jz      short loc_18001DF26
0x18001defe  cmp     byte ptr [rcx+131h], 3
0x18001df05  jb      short loc_18001DF26
0x18001df07  mov     rcx, [rcx+128h]
0x18001df0e  lea     edx, [rax+0Ch]
0x18001df11  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18001df18  call    WPP_SF_
0x18001df1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df24  xor     eax, eax
0x18001df26  mov     edi, 0C0AA0400h
0x18001df2b  mov     [rsp+200h+rgIndices], eax
0x18001df2f  mov     sil, al
0x18001df32  mov     r15, rax
0x18001df35  mov     rbx, rax
0x18001df38  jmp     loc_180020988
0x18001df3d  mov     rcx, [r13+0B8h]
0x18001df44  mov     dword ptr [r13+0A8h], 0FFFFh
0x18001df4f  test    rcx, rcx
0x18001df52  jz      short loc_18001DF6B
0x18001df54  mov     rax, [rcx]
0x18001df57  mov     rax, [rax+10h]
0x18001df5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df60  mov     qword ptr [r13+0B8h], 0
0x18001df6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001df6f  cmp     [r13+0AAh], ax
0x18001df77  jz      loc_18001E1C0
0x18001df7d  mov     rax, [r14]
0x18001df80  lea     rdx, [rbp+100h+pv]
0x18001df84  mov     r8d, 1
0x18001df8a  mov     rcx, r14
0x18001df8d  mov     rax, [rax+60h]
0x18001df91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df96  mov     edi, eax
0x18001df98  xor     eax, eax
0x18001df9a  test    edi, edi
0x18001df9c  jns     short loc_18001DFE8
0x18001df9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfa5  cmp     rcx, r15
0x18001dfa8  jz      short loc_18001DFDE
0x18001dfaa  test    [rcx+134h], r12b
0x18001dfb1  jz      short loc_18001DFDE
0x18001dfb3  cmp     byte ptr [rcx+131h], 3
0x18001dfba  jb      short loc_18001DFDE
0x18001dfbc  mov     rcx, [rcx+128h]
0x18001dfc3  lea     edx, [rax+0Dh]
0x18001dfc6  mov     r9d, edi
0x18001dfc9  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18001dfd0  call    WPP_SF_d
0x18001dfd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfdc  xor     eax, eax
0x18001dfde  mov     edi, 0C0AA0403h
0x18001dfe3  jmp     loc_18001DF2B
0x18001dfe8  mov     rax, [rbp+100h+pv]
0x18001dfec  test    rax, rax
0x18001dfef  jz      short loc_18001E038
0x18001dff1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dff8  cmp     rcx, r15
0x18001dffb  jz      short loc_18001E027
0x18001dffd  test    [rcx+134h], r12b
0x18001e004  jz      short loc_18001E027
0x18001e006  cmp     byte ptr [rcx+131h], 3
0x18001e00d  jb      short loc_18001E027
0x18001e00f  mov     rcx, [rcx+128h]
0x18001e016  mov     edx, 0Eh
0x18001e01b  mov     r8, rsi
0x18001e01e  call    WPP_SF_
0x18001e023  mov     rax, [rbp+100h+pv]
0x18001e027  mov     rcx, rax; pv
0x18001e02a  call    cs:__imp_CoTaskMemFree
0x18001e030  mov     [rbp+100h+pv], 0
0x18001e038  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e03c  cmp     [r13+0AAh], ax
0x18001e044  jz      loc_18001E1C0
0x18001e04a  mov     r8, [rbp+100h+var_80]
0x18001e051  mov     edx, 7FFh
0x18001e056  test    rdx, r8
0x18001e059  jz      short loc_18001E0B5
0x18001e05b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e062  cmp     rcx, r15
0x18001e065  jz      short loc_18001E0A9
0x18001e067  test    [rcx+134h], r12b
0x18001e06e  jz      short loc_18001E0A9
0x18001e070  cmp     byte ptr [rcx+131h], 3
0x18001e077  jb      short loc_18001E0A9
0x18001e079  mov     rcx, [rcx+128h]
0x18001e080  mov     eax, r8d
0x18001e083  and     eax, edx
0x18001e085  mov     r9, r8
0x18001e088  mov     dword ptr [rsp+200h+var_1D0], eax
0x18001e08c  mov     edx, 0Fh
0x18001e091  mov     dword ptr [rsp+200h+var_1D8], eax
0x18001e095  mov     [rsp+200h+ppv], r8
0x18001e09a  mov     r8, rsi
0x18001e09d  call    WPP_SF_iidD
0x18001e0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0a9  mov     edi, 0C0AA0403h
0x18001e0ae  xor     eax, eax
0x18001e0b0  jmp     loc_18001DF2B
0x18001e0b5  mov     rax, r8
0x18001e0b8  shr     rax, 0Bh
0x18001e0bc  cmp     rax, 7FFFFFFFh
0x18001e0c2  jbe     short loc_18001E100
0x18001e0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0cb  cmp     rcx, r15
0x18001e0ce  jz      short loc_18001E0A9
0x18001e0d0  test    [rcx+134h], r12b
0x18001e0d7  jz      short loc_18001E0A9
0x18001e0d9  cmp     byte ptr [rcx+131h], 3
0x18001e0e0  jb      short loc_18001E0A9
0x18001e0e2  mov     rcx, [rcx+128h]
0x18001e0e9  mov     edx, 10h
0x18001e0ee  mov     r9, rax
0x18001e0f1  mov     [rsp+200h+ppv], rax
0x18001e0f6  mov     r8, rsi
0x18001e0f9  call    WPP_SF_ii
0x18001e0fe  jmp     short loc_18001E0A2
0x18001e100  xor     ebx, ebx
0x18001e102  test    r8, r8
0x18001e105  jnz     short loc_18001E14C
0x18001e107  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e10e  cmp     rcx, r15
0x18001e111  jz      short loc_18001E13E
0x18001e113  test    [rcx+134h], r12b
0x18001e11a  jz      short loc_18001E13E
0x18001e11c  cmp     byte ptr [rcx+131h], 3
0x18001e123  jb      short loc_18001E13E
0x18001e125  mov     rcx, [rcx+128h]
0x18001e12c  lea     edx, [rbx+11h]
0x18001e12f  mov     r8, rsi
0x18001e132  call    WPP_SF_
0x18001e137  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e13e  mov     edi, 0C0AA0403h
0x18001e143  mov     [rsp+200h+rgIndices], ebx
0x18001e147  jmp     loc_18001FBD8
0x18001e14c  mov     rcx, [r13+0D0h]
0x18001e153  mov     ebx, eax
0x18001e155  mov     r8, [r13+0F0h]
0x18001e15c  mov     edx, 1
0x18001e161  mov     [rbp+100h+var_170], rbx
0x18001e165  mov     rax, [rcx]
0x18001e168  mov     rax, [rax+48h]
0x18001e16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e171  mov     edi, eax
0x18001e173  xor     eax, eax
0x18001e175  test    edi, edi
0x18001e177  jns     loc_18001E22B
0x18001e17d  cmp     edi, 0C0AA0211h
0x18001e183  mov     eax, 0C0AA0408h
0x18001e188  cmovz   edi, eax
0x18001e18b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e192  cmp     rcx, r15
0x18001e195  jz      short loc_18001E1C7
0x18001e197  test    [rcx+134h], r12b
0x18001e19e  jz      short loc_18001E1C7
0x18001e1a0  cmp     byte ptr [rcx+131h], 3
0x18001e1a7  jb      short loc_18001E1C7
0x18001e1a9  mov     rcx, [rcx+128h]
0x18001e1b0  mov     edx, 12h
0x18001e1b5  mov     r9d, edi
0x18001e1b8  mov     r8, rsi
0x18001e1bb  call    WPP_SF_d
0x18001e1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1c7  xor     eax, eax
0x18001e1c9  test    edi, edi
0x18001e1cb  js      loc_18001EDD6
0x18001e1d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001e1d5  cmp     [r13+0AAh], dx
0x18001e1dd  jz      loc_18001E5A4
0x18001e1e3  mov     rcx, [r13+0D8h]; this
0x18001e1ea  mov     dl, 1; struct IDiscRecorder2Ex *
0x18001e1ec  call    ?PreventAllowMediumRemoval@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EE@Z; Imapi2Utility::PreventAllowMediumRemoval(IDiscRecorder2Ex *,uchar,uchar)
0x18001e1f1  mov     edi, eax
0x18001e1f3  xor     eax, eax
0x18001e1f5  test    edi, edi
0x18001e1f7  jns     short loc_18001E23D
0x18001e1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e200  cmp     rcx, r15
0x18001e203  jz      loc_18001DF2B
0x18001e209  test    [rcx+134h], r12b
0x18001e210  jz      loc_18001DF2B
0x18001e216  cmp     byte ptr [rcx+131h], 3
0x18001e21d  jb      loc_18001DF2B
0x18001e223  lea     edx, [rax+13h]
0x18001e226  jmp     loc_18001E67E
0x18001e22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e232  mov     [rsp+200h+var_187], 1
0x18001e237  mov     [rbp+100h+var_170], rbx
0x18001e23b  jmp     short loc_18001E1D1
0x18001e23d  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
