# CcUpdateDynamicRegistrySettings

- ea: `0x1404b3ae0`
- end: `0x1404b4426`
- name: `CcUpdateDynamicRegistrySettings`
- size: `2374`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1402a2f90`
- `0x1404b3ae0`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd6c0`
- `0x140bb1320`
- `0x140bb19f0`

## string_xrefs

- `0x1404b3ba2`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\Memory Management`
- `0x1404b3b33`: `CcUpdateDynamicRegistrySettings: Updating Dynamic Registry Keys under: "%wZ"\n`
- `0x1404b3c7f`: `LargeWriteSize`
- `0x1404b3ce9`: `SoftThrottleLargeWriteAtPct`
- `0x1404b3c15`: `LazyWriterPercentageOfNumProcs`
- `0x1404b3dbd`: `MaxLazyWritePages`
- `0x1404b3fcf`: `EnableAsyncLazywrite`
- `0x1404b4039`: `EnableAsyncLazywriteMulti`
- `0x1404b3f65`: `DisableCacheTelemetry`
- `0x1404b412d`: `CcUpdateDynamicRegistrySettings(1/2): \n	TopBottom                      : 0x%04lx(%s)\n	LazyWriterPct                  : 0x%04lx(%s) (unsupported)\n	LargeWriteSize                 : 0x%04lx(%s)\n	SoftThrottleAt                 : 0x%04lx(%s)\n	SoftThrottleDelay              : 0x%04lx(%s)\n	MaxLazyWritePages              : 0x%04lx(%s)\n`
- `0x1404b417e`: `CcUpdateDynamicRegistrySettings(2/2): \n	PeriodicTelmetrySampleFrequency: 0x%04lx(%s)\n	PeriodicTelmetryReportFrequency: 0x%04lx(%s)\n	DisableCacheTelemetry          : 0x%04lx(%s)\n	EnableAsyncLazywrite           : 0x%04lx(%s)\n	EnableAsyncLazywriteMulti      : 0x%04lx(%s)\n`
- `0x14071cc96`: `CcUpdateDynamicRegistrySettings: Setting EnableAsyncLazywriteMulti requires per-Volume Lazywriter and (simple) Async Lazywriter to be enabled!\n`
- `0x14071ccb2`: `CcUpdateDynamicRegistrySettings: Ignoring invalid EnableAsyncLazywriteMulti(0x%04lx), no change to current value (0x%04lx)\n`
- `0x1404b43fd`: `CcUpdateDynamicRegistrySettings: Setting EnableAsyncLazywrite requires per-Volume Lazywriter is to be enabled!\n`
- `0x14071cc4c`: `CcUpdateDynamicRegistrySettings: Ignoring invalid EnableAsyncLazywrite(0x%04lx), no change to current value (0x%04lx)\n`

## pseudocode

```c
void __fastcall CcUpdateDynamicRegistrySettings(__int64 a1)
{
  int v1; // ebx
  unsigned int *p_P; // rdi
  char v3; // si
  unsigned int v4; // r12d
  int v5; // r13d
  int v6; // r15d
  const char *v7; // rbx
  const char *v8; // r10
  const char *v9; // r9
  const char *v10; // r8
  const char *v11; // rdx
  const char *v12; // rcx
  const char *v13; // rax
  unsigned int v14; // r14d
  const char *v15; // r8
  const char *v16; // rdx
  const char *v17; // rcx
  const char *v18; // rax
  __int64 v19; // rbx
  ULONG v20; // r14d
  ULONG v21; // r14d
  ULONG v22; // r14d
  ULONG v23; // r14d
  ULONG v24; // r14d
  ULONG v25; // r14d
  ULONG v26; // r14d
  ULONG v27; // r14d
  ULONG v28; // r14d
  ULONG v29; // r14d
  ULONG v30; // r14d
  ULONG i; // r14d
  int v32; // ecx
  NTSTATUS v33; // eax
  int v34; // r15d
  unsigned int *PoolWithTag; // r15
  NTSTATUS v36; // eax
  int v37; // r15d
  unsigned int *v38; // r15
  __int64 v39; // rax
  NTSTATUS v40; // eax
  int v41; // r15d
  unsigned int *v42; // r15
  NTSTATUS v43; // eax
  int v44; // r15d
  unsigned int *v45; // r15
  NTSTATUS v46; // eax
  int v47; // r15d
  unsigned int *v48; // r15
  NTSTATUS v49; // eax
  int v50; // r15d
  unsigned int *v51; // r15
  NTSTATUS v52; // eax
  int v53; // r15d
  unsigned int *v54; // r15
  NTSTATUS v55; // eax
  int v56; // r15d
  unsigned int *v57; // r15
  __int64 v58; // rax
  NTSTATUS v59; // eax
  int v60; // r15d
  unsigned int *v61; // r15
  NTSTATUS v62; // eax
  int v63; // r15d
  unsigned int *v64; // r15
  NTSTATUS v65; // eax
  int v66; // r15d
  unsigned int *v67; // r15
  NTSTATUS v68; // eax
  int v69; // r15d
  unsigned int *v70; // rbx
  ULONG Length[2]; // [rsp+20h] [rbp-E0h]
  PULONG ResultLength; // [rsp+28h] [rbp-D8h]
  __int64 v73; // [rsp+38h] [rbp-C8h]
  __int64 v74; // [rsp+48h] [rbp-B8h]
  __int64 v75; // [rsp+58h] [rbp-A8h]
  char v76; // [rsp+80h] [rbp-80h]
  char v77; // [rsp+81h] [rbp-7Fh]
  char v78; // [rsp+82h] [rbp-7Eh]
  char v79; // [rsp+83h] [rbp-7Dh]
  char v80; // [rsp+84h] [rbp-7Ch]
  char v81; // [rsp+85h] [rbp-7Bh]
  char v82; // [rsp+86h] [rbp-7Ah]
  char v83; // [rsp+87h] [rbp-79h]
  char v84; // [rsp+88h] [rbp-78h]
  char v85; // [rsp+89h] [rbp-77h]
  UNICODE_STRING ValueName; // [rsp+90h] [rbp-70h] BYREF
  char v87; // [rsp+A0h] [rbp-60h]
  char v88; // [rsp+A1h] [rbp-5Fh]
  int v89; // [rsp+A4h] [rbp-5Ch]
  int v90; // [rsp+A8h] [rbp-58h]
  int v91; // [rsp+ACh] [rbp-54h]
  unsigned int v92; // [rsp+B0h] [rbp-50h]
  int v93; // [rsp+B4h] [rbp-4Ch]
  _DWORD v94[2]; // [rsp+B8h] [rbp-48h] BYREF
  const WCHAR *v95; // [rsp+C0h] [rbp-40h]
  ULONG v96; // [rsp+C8h] [rbp-38h] BYREF
  ULONG v97; // [rsp+CCh] [rbp-34h] BYREF
  ULONG v98; // [rsp+D0h] [rbp-30h] BYREF
  ULONG v99; // [rsp+D4h] [rbp-2Ch] BYREF
  ULONG v100; // [rsp+D8h] [rbp-28h] BYREF
  ULONG v101; // [rsp+DCh] [rbp-24h] BYREF
  ULONG v102; // [rsp+E0h] [rbp-20h] BYREF
  ULONG v103; // [rsp+E4h] [rbp-1Ch] BYREF
  ULONG v104; // [rsp+E8h] [rbp-18h] BYREF
  ULONG v105; // [rsp+ECh] [rbp-14h] BYREF
  int v106; // [rsp+F0h] [rbp-10h]
  int v107; // [rsp+F4h] [rbp-Ch]
  unsigned int v108; // [rsp+F8h] [rbp-8h]
  unsigned int v109; // [rsp+FCh] [rbp-4h]
  unsigned int v110; // [rsp+100h] [rbp+0h]
  ULONG v111; // [rsp+104h] [rbp+4h] BYREF
  ULONG v112; // [rsp+108h] [rbp+8h] BYREF
  HANDLE v113; // [rsp+110h] [rbp+10h] BYREF
  HANDLE v114; // [rsp+118h] [rbp+18h] BYREF
  HANDLE v115; // [rsp+120h] [rbp+20h] BYREF
  HANDLE v116; // [rsp+128h] [rbp+28h] BYREF
  HANDLE v117; // [rsp+130h] [rbp+30h] BYREF
  HANDLE v118; // [rsp+138h] [rbp+38h] BYREF
  HANDLE v119; // [rsp+140h] [rbp+40h] BYREF
  HANDLE v120; // [rsp+148h] [rbp+48h] BYREF
  HANDLE v121; // [rsp+150h] [rbp+50h] BYREF
  HANDLE v122; // [rsp+158h] [rbp+58h] BYREF
  HANDLE KeyHandle; // [rsp+160h] [rbp+60h] BYREF
  HANDLE Handle; // [rsp+168h] [rbp+68h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+170h] [rbp+70h] BYREF
  OBJECT_ATTRIBUTES v126; // [rsp+1A0h] [rbp+A0h] BYREF
  OBJECT_ATTRIBUTES v127; // [rsp+1D0h] [rbp+D0h] BYREF
  OBJECT_ATTRIBUTES v128; // [rsp+200h] [rbp+100h] BYREF
  OBJECT_ATTRIBUTES v129; // [rsp+230h] [rbp+130h] BYREF
  OBJECT_ATTRIBUTES v130; // [rsp+260h] [rbp+160h] BYREF
  OBJECT_ATTRIBUTES v131; // [rsp+290h] [rbp+190h] BYREF
  OBJECT_ATTRIBUTES v132; // [rsp+2C0h] [rbp+1C0h] BYREF
  OBJECT_ATTRIBUTES v133; // [rsp+2F0h] [rbp+1F0h] BYREF
  OBJECT_ATTRIBUTES v134; // [rsp+320h] [rbp+220h] BYREF
  OBJECT_ATTRIBUTES v135; // [rsp+350h] [rbp+250h] BYREF
  OBJECT_ATTRIBUTES v136; // [rsp+380h] [rbp+280h] BYREF
  char P; // [rsp+3B0h] [rbp+2B0h] BYREF

  v108 = 0;
  v76 = 0;
  v1 = 156;
  v107 = 0;
  v87 = 0;
  v106 = 0;
  v94[1] = 0;
  v77 = 0;
  *(_DWORD *)(&ValueName.MaximumLength + 1) = 0;
  p_P = (unsigned int *)&P;
  v89 = 0;
  v3 = 0;
  v78 = 0;
  v90 = 0;
  v4 = 0;
  v79 = 0;
  v5 = 0;
  v91 = 0;
  v80 = 0;
  v109 = 0;
  v81 = 0;
  v110 = 0;
  v88 = 0;
  v92 = 0;
  v82 = 0;
  v93 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  DbgPrintEx(0x7Fu, 2u, "CcUpdateDynamicRegistrySettings: Updating Dynamic Registry Keys under: \"%wZ\"\n", a1 + 56);
  v94[0] = 11141288;
  v95 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\Memory Management";
  *(_DWORD *)&ValueName.Length = 2359330;
  ValueName.Buffer = L"TopBottomDPTEqual";
  KeyHandle = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v94;
  v111 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v20 = 156;
    while ( 1 )
    {
      v33 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, p_P, v20, &v111);
      v34 = v33;
      if ( v33 != -1073741789 && v33 != -2147483643 )
        break;
      if ( v20 != v1 )
        break;
      v20 = v111;
      if ( v111 > 0x40000 || (PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v111, 0x78666343u)) == 0 )
      {
        v34 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = PoolWithTag;
      v1 = v20;
      v3 = 1;
    }
    ZwClose(KeyHandle);
    if ( v34 >= 0 )
    {
      if ( p_P[3] )
      {
        v108 = *(unsigned int *)((char *)p_P + p_P[2]);
        if ( v108 < 3 )
          v76 = 1;
      }
    }
  }
  *(_DWORD *)&ValueName.Length = 4063292;
  ValueName.Buffer = L"LazyWriterPercentageOfNumProcs";
  Handle = 0;
  v126.ObjectName = (PUNICODE_STRING)v94;
  v112 = 0;
  *(_QWORD *)&v126.Length = 48;
  *(_QWORD *)&v126.Attributes = 576;
  v126.RootDirectory = 0;
  *(_OWORD *)&v126.SecurityDescriptor = 0;
  if ( ZwOpenKey(&Handle, 0x20019u, &v126) >= 0 )
  {
    v21 = v1;
    while ( 1 )
    {
      v36 = ZwQueryValueKey(Handle, &ValueName, KeyValueFullInformation, p_P, v21, &v112);
      v37 = v36;
      if ( v36 != -1073741789 && v36 != -2147483643 )
        break;
      if ( v21 != v1 )
        break;
      v21 = v112;
      if ( v112 > 0x40000 || (v38 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v112, 0x78666343u)) == 0 )
      {
        v37 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v38;
      v1 = v21;
      v3 = 1;
    }
    ZwClose(Handle);
    if ( v37 >= 0 && p_P[3] )
    {
      v39 = p_P[2];
      v87 = 1;
      v107 = *(unsigned int *)((char *)p_P + v39);
    }
  }
  *(_DWORD *)&ValueName.Length = 1966108;
  ValueName.Buffer = L"LargeWriteSize";
  v113 = 0;
  v127.ObjectName = (PUNICODE_STRING)v94;
  v96 = 0;
  *(_QWORD *)&v127.Length = 48;
  *(_QWORD *)&v127.Attributes = 576;
  v127.RootDirectory = 0;
  *(_OWORD *)&v127.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v113, 0x20019u, &v127) >= 0 )
  {
    v22 = v1;
    while ( 1 )
    {
      v40 = ZwQueryValueKey(v113, &ValueName, KeyValueFullInformation, p_P, v22, &v96);
      v41 = v40;
      if ( v40 != -1073741789 && v40 != -2147483643 )
        break;
      if ( v22 != v1 )
        break;
      v22 = v96;
      if ( v96 > 0x40000 || (v42 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v96, 0x78666343u)) == 0 )
      {
        v41 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v42;
      v1 = v22;
      v3 = 1;
    }
    ZwClose(v113);
    if ( v41 >= 0 && p_P[3] )
    {
      v77 = 1;
      v106 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 3670070;
  ValueName.Buffer = L"SoftThrottleLargeWriteAtPct";
  v114 = 0;
  v128.ObjectName = (PUNICODE_STRING)v94;
  v97 = 0;
  *(_QWORD *)&v128.Length = 48;
  *(_QWORD *)&v128.Attributes = 576;
  v128.RootDirectory = 0;
  *(_OWORD *)&v128.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v114, 0x20019u, &v128) >= 0 )
  {
    v23 = v1;
    while ( 1 )
    {
      v43 = ZwQueryValueKey(v114, &ValueName, KeyValueFullInformation, p_P, v23, &v97);
      v44 = v43;
      if ( v43 != -1073741789 && v43 != -2147483643 )
        break;
      if ( v23 != v1 )
        break;
      v23 = v97;
      if ( v97 > 0x40000 || (v45 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v97, 0x78666343u)) == 0 )
      {
        v44 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v45;
      v1 = v23;
      v3 = 1;
    }
    ZwClose(v114);
    if ( v44 >= 0 && p_P[3] )
    {
      v78 = 1;
      v89 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 2883626;
  ValueName.Buffer = L"SoftThrottleDelayInMs";
  v115 = 0;
  v129.ObjectName = (PUNICODE_STRING)v94;
  v98 = 0;
  *(_QWORD *)&v129.Length = 48;
  *(_QWORD *)&v129.Attributes = 576;
  v129.RootDirectory = 0;
  *(_OWORD *)&v129.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v115, 0x20019u, &v129) >= 0 )
  {
    v24 = v1;
    while ( 1 )
    {
      v46 = ZwQueryValueKey(v115, &ValueName, KeyValueFullInformation, p_P, v24, &v98);
      v47 = v46;
      if ( v46 != -1073741789 && v46 != -2147483643 )
        break;
      if ( v24 != v1 )
        break;
      v24 = v98;
      if ( v98 > 0x40000 || (v48 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v98, 0x78666343u)) == 0 )
      {
        v47 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v48;
      v1 = v24;
      v3 = 1;
    }
    ZwClose(v115);
    if ( v47 >= 0 && p_P[3] )
    {
      v79 = 1;
      v90 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 2359330;
  ValueName.Buffer = L"MaxLazyWritePages";
  v116 = 0;
  v130.ObjectName = (PUNICODE_STRING)v94;
  v99 = 0;
  *(_QWORD *)&v130.Length = 48;
  *(_QWORD *)&v130.Attributes = 576;
  v130.RootDirectory = 0;
  *(_OWORD *)&v130.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v116, 0x20019u, &v130) >= 0 )
  {
    v25 = v1;
    while ( 1 )
    {
      v49 = ZwQueryValueKey(v116, &ValueName, KeyValueFullInformation, p_P, v25, &v99);
      v50 = v49;
      if ( v49 != -1073741789 && v49 != -2147483643 )
        break;
      if ( v25 != v1 )
        break;
      v25 = v99;
      if ( v99 > 0x40000 || (v51 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v99, 0x78666343u)) == 0 )
      {
        v50 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v51;
      v1 = v25;
      v3 = 1;
    }
    ZwClose(v116);
    if ( v50 >= 0 && p_P[3] )
    {
      v80 = 1;
      v91 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 4325440;
  ValueName.Buffer = L"PeriodicTelemetrySampleFrequency";
  v117 = 0;
  v131.ObjectName = (PUNICODE_STRING)v94;
  v100 = 0;
  *(_QWORD *)&v131.Length = 48;
  *(_QWORD *)&v131.Attributes = 576;
  v131.RootDirectory = 0;
  *(_OWORD *)&v131.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v117, 0x20019u, &v131) >= 0 )
  {
    v26 = v1;
    while ( 1 )
    {
      v52 = ZwQueryValueKey(v117, &ValueName, KeyValueFullInformation, p_P, v26, &v100);
      v53 = v52;
      if ( v52 != -1073741789 && v52 != -2147483643 )
        break;
      if ( v26 != v1 )
        break;
      v26 = v100;
      if ( v100 > 0x40000 || (v54 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v100, 0x78666343u)) == 0 )
      {
        v53 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v54;
      v1 = v26;
      v3 = 1;
    }
    ZwClose(v117);
    if ( v53 >= 0 && p_P[3] )
    {
      v81 = 1;
      v109 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 4194366;
  ValueName.Buffer = L"PeriodicTelemetryEventFrequency";
  v118 = 0;
  v132.ObjectName = (PUNICODE_STRING)v94;
  v101 = 0;
  *(_QWORD *)&v132.Length = 48;
  *(_QWORD *)&v132.Attributes = 576;
  v132.RootDirectory = 0;
  *(_OWORD *)&v132.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v118, 0x20019u, &v132) >= 0 )
  {
    v27 = v1;
    while ( 1 )
    {
      v55 = ZwQueryValueKey(v118, &ValueName, KeyValueFullInformation, p_P, v27, &v101);
      v56 = v55;
      if ( v55 != -1073741789 && v55 != -2147483643 )
        break;
      if ( v27 != v1 )
        break;
      v27 = v101;
      if ( v101 > 0x40000 || (v57 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v101, 0x78666343u)) == 0 )
      {
        v56 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v57;
      v1 = v27;
      v3 = 1;
    }
    ZwClose(v118);
    if ( v56 >= 0 && p_P[3] )
    {
      v58 = p_P[2];
      v88 = 1;
      v110 = *(unsigned int *)((char *)p_P + v58);
    }
  }
  *(_DWORD *)&ValueName.Length = 4325440;
  ValueName.Buffer = L"PeriodicTelemetryReportFrequency";
  v119 = 0;
  v133.ObjectName = (PUNICODE_STRING)v94;
  v102 = 0;
  *(_QWORD *)&v133.Length = 48;
  *(_QWORD *)&v133.Attributes = 576;
  v133.RootDirectory = 0;
  *(_OWORD *)&v133.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v119, 0x20019u, &v133) >= 0 )
  {
    v28 = v1;
    while ( 1 )
    {
      v59 = ZwQueryValueKey(v119, &ValueName, KeyValueFullInformation, p_P, v28, &v102);
      v60 = v59;
      if ( v59 != -1073741789 && v59 != -2147483643 )
        break;
      if ( v28 != v1 )
        break;
      v28 = v102;
      if ( v102 > 0x40000 || (v61 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v102, 0x78666343u)) == 0 )
      {
        v60 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v61;
      v1 = v28;
      v3 = 1;
    }
    ZwClose(v119);
    if ( v60 >= 0 && p_P[3] )
    {
      v82 = 1;
      v92 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 2883626;
  ValueName.Buffer = L"DisableCacheTelemetry";
  v120 = 0;
  v134.ObjectName = (PUNICODE_STRING)v94;
  v103 = 0;
  *(_QWORD *)&v134.Length = 48;
  *(_QWORD *)&v134.Attributes = 576;
  v134.RootDirectory = 0;
  *(_OWORD *)&v134.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v120, 0x20019u, &v134) >= 0 )
  {
    v29 = v1;
    while ( 1 )
    {
      v62 = ZwQueryValueKey(v120, &ValueName, KeyValueFullInformation, p_P, v29, &v103);
      v63 = v62;
      if ( v62 != -1073741789 && v62 != -2147483643 )
        break;
      if ( v29 != v1 )
        break;
      v29 = v103;
      if ( v103 > 0x40000 || (v64 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v103, 0x78666343u)) == 0 )
      {
        v63 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v64;
      v1 = v29;
      v3 = 1;
    }
    ZwClose(v120);
    if ( v63 >= 0 && p_P[3] )
    {
      v83 = 1;
      v93 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 2752552;
  ValueName.Buffer = L"EnableAsyncLazywrite";
  v121 = 0;
  v135.ObjectName = (PUNICODE_STRING)v94;
  v104 = 0;
  *(_QWORD *)&v135.Length = 48;
  *(_QWORD *)&v135.Attributes = 576;
  v135.RootDirectory = 0;
  *(_OWORD *)&v135.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v121, 0x20019u, &v135) >= 0 )
  {
    v30 = v1;
    while ( 1 )
    {
      v65 = ZwQueryValueKey(v121, &ValueName, KeyValueFullInformation, p_P, v30, &v104);
      v66 = v65;
      if ( v65 != -1073741789 && v65 != -2147483643 )
        break;
      if ( v30 != v1 )
        break;
      v30 = v104;
      if ( v104 > 0x40000 || (v67 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v104, 0x78666343u)) == 0 )
      {
        v66 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v67;
      v1 = v30;
      v3 = 1;
    }
    ZwClose(v121);
    if ( v66 >= 0 && p_P[3] )
    {
      v84 = 1;
      v4 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  *(_DWORD *)&ValueName.Length = 3407922;
  ValueName.Buffer = L"EnableAsyncLazywriteMulti";
  v122 = 0;
  v136.ObjectName = (PUNICODE_STRING)v94;
  v105 = 0;
  *(_QWORD *)&v136.Length = 48;
  *(_QWORD *)&v136.Attributes = 576;
  v136.RootDirectory = 0;
  *(_OWORD *)&v136.SecurityDescriptor = 0;
  if ( ZwOpenKey(&v122, 0x20019u, &v136) >= 0 )
  {
    for ( i = v1; ; v1 = i )
    {
      v68 = ZwQueryValueKey(v122, &ValueName, KeyValueFullInformation, p_P, i, &v105);
      v69 = v68;
      if ( v68 != -1073741789 && v68 != -2147483643 )
        break;
      if ( i != v1 )
        break;
      i = v105;
      if ( v105 > 0x40000 || (v70 = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v105, 0x78666343u)) == 0 )
      {
        v69 = -1073741670;
        break;
      }
      if ( v3 )
        ExFreePoolWithTag(p_P, 0x78666343u);
      p_P = v70;
      v3 = 1;
    }
    ZwClose(v122);
    if ( v69 >= 0 && p_P[3] )
    {
      v85 = 1;
      v5 = *(unsigned int *)((char *)p_P + p_P[2]);
    }
  }
  v6 = v108;
  v7 = "valid";
  v8 = "valid";
  v9 = "valid";
  if ( !v80 )
    v8 = "not found";
  v10 = "valid";
  v11 = "valid";
  v12 = "valid";
  if ( !v79 )
    v9 = "not found";
  v13 = "valid";
  if ( !v78 )
    v10 = "not found";
  if ( !v77 )
    v11 = "not found";
  if ( !v87 )
    v12 = "not found";
  v14 = v106;
  if ( !v76 )
    v13 = "not found";
  DbgPrintEx(
    0x7Fu,
    2u,
    "CcUpdateDynamicRegistrySettings(1/2): \n"
    "\tTopBottom                      : 0x%04lx(%s)\n"
    "\tLazyWriterPct                  : 0x%04lx(%s) (unsupported)\n"
    "\tLargeWriteSize                 : 0x%04lx(%s)\n"
    "\tSoftThrottleAt                 : 0x%04lx(%s)\n"
    "\tSoftThrottleDelay              : 0x%04lx(%s)\n"
    "\tMaxLazyWritePages              : 0x%04lx(%s)\n",
    v108,
    v13,
    v107,
    v12,
    v106,
    v11,
    v89,
    v10,
    v90,
    v9,
    v91,
    v8);
  v15 = "valid";
  v16 = "valid";
  v17 = "valid";
  if ( !v85 )
    v15 = "not found";
  v18 = "valid";
  if ( !v84 )
    v16 = "not found";
  LODWORD(v75) = v5;
  if ( !v83 )
    v17 = "not found";
  LODWORD(v74) = v4;
  if ( !v82 )
    v18 = "not found";
  LODWORD(v73) = v93;
  if ( !v81 )
    v7 = "not found";
  LODWORD(ResultLength) = v92;
  *(_QWORD *)Length = v7;
  v19 = v109;
  DbgPrintEx(
    0x7Fu,
    2u,
    "CcUpdateDynamicRegistrySettings(2/2): \n"
    "\tPeriodicTelmetrySampleFrequency: 0x%04lx(%s)\n"
    "\tPeriodicTelmetryReportFrequency: 0x%04lx(%s)\n"
    "\tDisableCacheTelemetry          : 0x%04lx(%s)\n"
    "\tEnableAsyncLazywrite           : 0x%04lx(%s)\n"
    "\tEnableAsyncLazywriteMulti      : 0x%04lx(%s)\n",
    v109,
    *(_QWORD *)Length,
    ResultLength,
    v18,
    v73,
    v17,
    v74,
    v16,
    v75,
    v15);
  if ( v3 )
    ExFreePoolWithTag(p_P, 0x78666343u);
  if ( v76 )
    CcAzure_TopBottomDPTEqual = v6;
  if ( v77 )
  {
    if ( !v14 || (CcAzure_LargeWriteSize = v14 << 10, v14 << 10 <= v14) )
      CcAzure_LargeWriteSize = 0;
  }
  if ( v78 )
  {
    v32 = 0;
    if ( (unsigned int)(v89 - 1) <= 0x63 )
      v32 = v89;
    CcAzure_SoftThrottleLargeWriteAtPct = v32;
  }
  if ( v79 && v90 )
    CcSoftThrottleDelay = v90;
  if ( v80 && (unsigned int)(v91 - 1) <= 0x7FFF )
    CcMaxLazyWritePages = v91;
  if ( v81 && (_DWORD)v19 )
    DueTime.QuadPart = -10000000 * v19;
  if ( v88 && v110 )
    qword_140F85B88 = 10000000LL * v110;
  if ( v82 && v92 )
    qword_140F85B90 = 10000000LL * v92;
  if ( v83 )
    byte_140F85BA1 = v93 != 0;
  if ( v84 )
  {
    if ( v4 > 1 )
    {
      DbgPrintEx(
        0x7Fu,
        2u,
        "CcUpdateDynamicRegistrySettings: Ignoring invalid EnableAsyncLazywrite(0x%04lx), no change to current value (0x%04lx)\n",
        v4,
        (unsigned __int8)CcEnableAsyncLazywrite);
    }
    else
    {
      CcEnableAsyncLazywrite = v4 != 0;
      if ( v4 && !CcEnablePerVolumeLazyWriter )
        DbgPrintEx(
          0x7Fu,
          2u,
          "CcUpdateDynamicRegistrySettings: Setting EnableAsyncLazywrite requires per-Volume Lazywriter is to be enabled!\n");
    }
  }
  if ( v85 )
  {
    if ( v5 )
    {
      if ( v5 == 1 )
      {
        if ( CcEnablePerVolumeLazyWriter && CcEnableAsyncLazywrite )
          CcEnableAsyncLazywriteMulti = 1;
        else
          DbgPrintEx(
            0x7Fu,
            2u,
            "CcUpdateDynamicRegistrySettings: Setting EnableAsyncLazywriteMulti requires per-Volume Lazywriter and (simpl"
            "e) Async Lazywriter to be enabled!\n");
      }
      else
      {
        DbgPrintEx(
          0x7Fu,
          2u,
          "CcUpdateDynamicRegistrySettings: Ignoring invalid EnableAsyncLazywriteMulti(0x%04lx), no change to current value (0x%04lx)\n",
          v5,
          (unsigned __int8)CcEnableAsyncLazywriteMulti);
      }
    }
    else
    {
      CcEnableAsyncLazywriteMulti = 0;
    }
  }
}

```

## disassembly

```asm
0x1404b3ae0  push    rbp
0x1404b3ae2  push    rbx
0x1404b3ae3  push    rsi
0x1404b3ae4  push    rdi
0x1404b3ae5  push    r12
0x1404b3ae7  push    r13
0x1404b3ae9  push    r14
0x1404b3aeb  push    r15
0x1404b3aed  lea     rbp, [rsp-368h]
0x1404b3af5  sub     rsp, 468h
0x1404b3afc  mov     rax, cs:__security_cookie
0x1404b3b03  xor     rax, rsp
0x1404b3b06  mov     [rbp+3A0h+var_50], rax
0x1404b3b0d  xor     r14d, r14d
0x1404b3b10  lea     r9, [rcx+38h]
0x1404b3b14  xorps   xmm0, xmm0
0x1404b3b17  mov     [rbp+3A0h+var_3A8], r14d
0x1404b3b1b  xorps   xmm1, xmm1
0x1404b3b1e  mov     [rbp+3A0h+var_420], r14b
0x1404b3b22  mov     ebx, 9Ch
0x1404b3b27  mov     [rbp+3A0h+var_3AC], r14d
0x1404b3b2b  lea     edx, [r14+2]; Level
0x1404b3b2f  mov     [rbp+3A0h+var_400], r14b
0x1404b3b33  lea     r8, aCcupdatedynami_4; "CcUpdateDynamicRegistrySettings: Updati"...
0x1404b3b3a  mov     [rbp+3A0h+var_3B0], r14d
0x1404b3b3e  movups  [rbp+3A0h+var_3E8], xmm0
0x1404b3b42  lea     ecx, [rbx-1Dh]; ComponentId
0x1404b3b45  mov     [rbp+3A0h+var_41F], r14b
0x1404b3b49  movups  xmmword ptr [rbp+3A0h+ValueName.Length], xmm1
0x1404b3b4d  lea     rdi, [rbp+3A0h+P]
0x1404b3b54  mov     [rbp+3A0h+var_3FC], r14d
0x1404b3b58  mov     sil, r14b
0x1404b3b5b  mov     [rbp+3A0h+var_41E], r14b
0x1404b3b5f  mov     [rbp+3A0h+var_3F8], r14d
0x1404b3b63  mov     r12d, r14d
0x1404b3b66  mov     [rbp+3A0h+var_41D], r14b
0x1404b3b6a  mov     r13d, r14d
0x1404b3b6d  mov     [rbp+3A0h+var_3F4], r14d
0x1404b3b71  mov     [rbp+3A0h+var_41C], r14b
0x1404b3b75  mov     [rbp+3A0h+var_3A4], r14d
0x1404b3b79  mov     [rbp+3A0h+var_41B], r14b
0x1404b3b7d  mov     [rbp+3A0h+var_3A0], r14d
0x1404b3b81  mov     [rbp+3A0h+var_3FF], r14b
0x1404b3b85  mov     [rbp+3A0h+var_3F0], r14d
0x1404b3b89  mov     [rbp+3A0h+var_41A], r14b
0x1404b3b8d  mov     [rbp+3A0h+var_3EC], r14d
0x1404b3b91  mov     [rbp+3A0h+var_419], r14b
0x1404b3b95  mov     [rbp+3A0h+var_418], r14b
0x1404b3b99  mov     [rbp+3A0h+var_417], r14b
0x1404b3b9d  call    DbgPrintEx
0x1404b3ba2  lea     rax, aRegistryMachin_74; "\\Registry\\Machine\\System\\CurrentCon"...
0x1404b3ba9  mov     dword ptr [rbp+3A0h+var_3E8], 0AA00A8h
0x1404b3bb0  mov     qword ptr [rbp+3A0h+var_3E8+8], rax
0x1404b3bb4  lea     r8, [rbp+3A0h+ObjectAttributes]; ObjectAttributes
0x1404b3bb8  lea     rax, aTopbottomdpteq; "TopBottomDPTEqual"
0x1404b3bbf  mov     dword ptr [rbp+3A0h+ValueName.Length], 240022h
0x1404b3bc6  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3bca  lea     rcx, [rbp+3A0h+KeyHandle]; KeyHandle
0x1404b3bce  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3bd2  mov     [rbp+3A0h+KeyHandle], r14
0x1404b3bd6  xorps   xmm0, xmm0
0x1404b3bd9  mov     [rbp+3A0h+ObjectAttributes.ObjectName], rax
0x1404b3be0  mov     edx, 20019h; DesiredAccess
0x1404b3be5  mov     [rbp+3A0h+var_39C], r14d
0x1404b3be9  mov     qword ptr [rbp+3A0h+ObjectAttributes.Length], 30h ; '0'
0x1404b3bf1  mov     qword ptr [rbp+3A0h+ObjectAttributes.Attributes], 240h
0x1404b3bfc  mov     [rbp+3A0h+ObjectAttributes.RootDirectory], r14
0x1404b3c00  movdqu  xmmword ptr [rbp+3A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1404b3c08  call    ZwOpenKey
0x1404b3c0d  test    eax, eax
0x1404b3c0f  jns     loc_1404B427C
0x1404b3c15  lea     rax, aLazywriterperc_0; "LazyWriterPercentageOfNumProcs"
0x1404b3c1c  mov     dword ptr [rbp+3A0h+ValueName.Length], 3E003Ch
0x1404b3c23  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3c27  lea     r8, [rbp+3A0h+var_300]; ObjectAttributes
0x1404b3c2e  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3c32  mov     [rbp+3A0h+Handle], r14
0x1404b3c36  xorps   xmm0, xmm0
0x1404b3c39  mov     [rbp+3A0h+var_300.ObjectName], rax
0x1404b3c40  mov     edx, 20019h; DesiredAccess
0x1404b3c45  mov     [rbp+3A0h+var_398], r14d
0x1404b3c49  lea     rcx, [rbp+3A0h+Handle]; KeyHandle
0x1404b3c4d  mov     qword ptr [rbp+3A0h+var_300.Length], 30h ; '0'
0x1404b3c58  mov     qword ptr [rbp+3A0h+var_300.Attributes], 240h
0x1404b3c63  mov     [rbp+3A0h+var_300.RootDirectory], r14
0x1404b3c6a  movdqu  xmmword ptr [rbp+3A0h+var_300.SecurityDescriptor], xmm0
0x1404b3c72  call    ZwOpenKey
0x1404b3c77  test    eax, eax
0x1404b3c79  jns     loc_1404B4284
0x1404b3c7f  lea     rax, aLargewritesize; "LargeWriteSize"
0x1404b3c86  mov     dword ptr [rbp+3A0h+ValueName.Length], 1E001Ch
0x1404b3c8d  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3c91  lea     r8, [rbp+3A0h+var_2D0]; ObjectAttributes
0x1404b3c98  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3c9c  mov     [rbp+3A0h+var_390], r14
0x1404b3ca0  xorps   xmm0, xmm0
0x1404b3ca3  mov     [rbp+3A0h+var_2D0.ObjectName], rax
0x1404b3caa  mov     edx, 20019h; DesiredAccess
0x1404b3caf  mov     [rbp+3A0h+var_3D8], r14d
0x1404b3cb3  lea     rcx, [rbp+3A0h+var_390]; KeyHandle
0x1404b3cb7  mov     qword ptr [rbp+3A0h+var_2D0.Length], 30h ; '0'
0x1404b3cc2  mov     qword ptr [rbp+3A0h+var_2D0.Attributes], 240h
0x1404b3ccd  mov     [rbp+3A0h+var_2D0.RootDirectory], r14
0x1404b3cd4  movdqu  xmmword ptr [rbp+3A0h+var_2D0.SecurityDescriptor], xmm0
0x1404b3cdc  call    ZwOpenKey
0x1404b3ce1  test    eax, eax
0x1404b3ce3  jns     loc_1404B428C
0x1404b3ce9  lea     rax, aSoftthrottlela_0; "SoftThrottleLargeWriteAtPct"
0x1404b3cf0  mov     dword ptr [rbp+3A0h+ValueName.Length], 380036h
0x1404b3cf7  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3cfb  lea     r8, [rbp+3A0h+var_2A0]; ObjectAttributes
0x1404b3d02  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3d06  mov     [rbp+3A0h+var_388], r14
0x1404b3d0a  xorps   xmm0, xmm0
0x1404b3d0d  mov     [rbp+3A0h+var_2A0.ObjectName], rax
0x1404b3d14  mov     edx, 20019h; DesiredAccess
0x1404b3d19  mov     [rbp+3A0h+var_3D4], r14d
0x1404b3d1d  lea     rcx, [rbp+3A0h+var_388]; KeyHandle
0x1404b3d21  mov     qword ptr [rbp+3A0h+var_2A0.Length], 30h ; '0'
0x1404b3d2c  mov     qword ptr [rbp+3A0h+var_2A0.Attributes], 240h
0x1404b3d37  mov     [rbp+3A0h+var_2A0.RootDirectory], r14
0x1404b3d3e  movdqu  xmmword ptr [rbp+3A0h+var_2A0.SecurityDescriptor], xmm0
0x1404b3d46  call    ZwOpenKey
0x1404b3d4b  test    eax, eax
0x1404b3d4d  jns     loc_1404B4294
0x1404b3d53  lea     rax, aSoftthrottlede; "SoftThrottleDelayInMs"
0x1404b3d5a  mov     dword ptr [rbp+3A0h+ValueName.Length], 2C002Ah
0x1404b3d61  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3d65  lea     r8, [rbp+3A0h+var_270]; ObjectAttributes
0x1404b3d6c  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3d70  mov     [rbp+3A0h+var_380], r14
0x1404b3d74  xorps   xmm0, xmm0
0x1404b3d77  mov     [rbp+3A0h+var_270.ObjectName], rax
0x1404b3d7e  mov     edx, 20019h; DesiredAccess
0x1404b3d83  mov     [rbp+3A0h+var_3D0], r14d
0x1404b3d87  lea     rcx, [rbp+3A0h+var_380]; KeyHandle
0x1404b3d8b  mov     qword ptr [rbp+3A0h+var_270.Length], 30h ; '0'
0x1404b3d96  mov     qword ptr [rbp+3A0h+var_270.Attributes], 240h
0x1404b3da1  mov     [rbp+3A0h+var_270.RootDirectory], r14
0x1404b3da8  movdqu  xmmword ptr [rbp+3A0h+var_270.SecurityDescriptor], xmm0
0x1404b3db0  call    ZwOpenKey
0x1404b3db5  test    eax, eax
0x1404b3db7  jns     loc_1404B429C
0x1404b3dbd  lea     rax, aMaxlazywritepa; "MaxLazyWritePages"
0x1404b3dc4  mov     dword ptr [rbp+3A0h+ValueName.Length], 240022h
0x1404b3dcb  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3dcf  lea     r8, [rbp+3A0h+var_240]; ObjectAttributes
0x1404b3dd6  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3dda  mov     [rbp+3A0h+var_378], r14
0x1404b3dde  xorps   xmm0, xmm0
0x1404b3de1  mov     [rbp+3A0h+var_240.ObjectName], rax
0x1404b3de8  mov     edx, 20019h; DesiredAccess
0x1404b3ded  mov     [rbp+3A0h+var_3CC], r14d
0x1404b3df1  lea     rcx, [rbp+3A0h+var_378]; KeyHandle
0x1404b3df5  mov     qword ptr [rbp+3A0h+var_240.Length], 30h ; '0'
0x1404b3e00  mov     qword ptr [rbp+3A0h+var_240.Attributes], 240h
0x1404b3e0b  mov     [rbp+3A0h+var_240.RootDirectory], r14
0x1404b3e12  movdqu  xmmword ptr [rbp+3A0h+var_240.SecurityDescriptor], xmm0
0x1404b3e1a  call    ZwOpenKey
0x1404b3e1f  test    eax, eax
0x1404b3e21  jns     loc_1404B42A4
0x1404b3e27  lea     rax, aPeriodicteleme_1; "PeriodicTelemetrySampleFrequency"
0x1404b3e2e  mov     dword ptr [rbp+3A0h+ValueName.Length], 420040h
0x1404b3e35  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3e39  lea     r8, [rbp+3A0h+var_210]; ObjectAttributes
0x1404b3e40  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3e44  mov     [rbp+3A0h+var_370], r14
0x1404b3e48  xorps   xmm0, xmm0
0x1404b3e4b  mov     [rbp+3A0h+var_210.ObjectName], rax
0x1404b3e52  mov     edx, 20019h; DesiredAccess
0x1404b3e57  mov     [rbp+3A0h+var_3C8], r14d
0x1404b3e5b  lea     rcx, [rbp+3A0h+var_370]; KeyHandle
0x1404b3e5f  mov     qword ptr [rbp+3A0h+var_210.Length], 30h ; '0'
0x1404b3e6a  mov     qword ptr [rbp+3A0h+var_210.Attributes], 240h
0x1404b3e75  mov     [rbp+3A0h+var_210.RootDirectory], r14
0x1404b3e7c  movdqu  xmmword ptr [rbp+3A0h+var_210.SecurityDescriptor], xmm0
0x1404b3e84  call    ZwOpenKey
0x1404b3e89  test    eax, eax
0x1404b3e8b  jns     loc_1404B42AC
0x1404b3e91  lea     rax, aPeriodicteleme_0; "PeriodicTelemetryEventFrequency"
0x1404b3e98  mov     dword ptr [rbp+3A0h+ValueName.Length], 40003Eh
0x1404b3e9f  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3ea3  lea     r8, [rbp+3A0h+var_1E0]; ObjectAttributes
0x1404b3eaa  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3eae  mov     [rbp+3A0h+var_368], r14
0x1404b3eb2  xorps   xmm0, xmm0
0x1404b3eb5  mov     [rbp+3A0h+var_1E0.ObjectName], rax
0x1404b3ebc  mov     edx, 20019h; DesiredAccess
0x1404b3ec1  mov     [rbp+3A0h+var_3C4], r14d
0x1404b3ec5  lea     rcx, [rbp+3A0h+var_368]; KeyHandle
0x1404b3ec9  mov     qword ptr [rbp+3A0h+var_1E0.Length], 30h ; '0'
0x1404b3ed4  mov     qword ptr [rbp+3A0h+var_1E0.Attributes], 240h
0x1404b3edf  mov     [rbp+3A0h+var_1E0.RootDirectory], r14
0x1404b3ee6  movdqu  xmmword ptr [rbp+3A0h+var_1E0.SecurityDescriptor], xmm0
0x1404b3eee  call    ZwOpenKey
0x1404b3ef3  test    eax, eax
0x1404b3ef5  jns     loc_1404B42B4
0x1404b3efb  lea     rax, aPeriodicteleme; "PeriodicTelemetryReportFrequency"
0x1404b3f02  mov     dword ptr [rbp+3A0h+ValueName.Length], 420040h
0x1404b3f09  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3f0d  lea     r8, [rbp+3A0h+var_1B0]; ObjectAttributes
0x1404b3f14  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3f18  mov     [rbp+3A0h+var_360], r14
0x1404b3f1c  xorps   xmm0, xmm0
0x1404b3f1f  mov     [rbp+3A0h+var_1B0.ObjectName], rax
0x1404b3f26  mov     edx, 20019h; DesiredAccess
0x1404b3f2b  mov     [rbp+3A0h+var_3C0], r14d
0x1404b3f2f  lea     rcx, [rbp+3A0h+var_360]; KeyHandle
0x1404b3f33  mov     qword ptr [rbp+3A0h+var_1B0.Length], 30h ; '0'
0x1404b3f3e  mov     qword ptr [rbp+3A0h+var_1B0.Attributes], 240h
0x1404b3f49  mov     [rbp+3A0h+var_1B0.RootDirectory], r14
0x1404b3f50  movdqu  xmmword ptr [rbp+3A0h+var_1B0.SecurityDescriptor], xmm0
0x1404b3f58  call    ZwOpenKey
0x1404b3f5d  test    eax, eax
0x1404b3f5f  jns     loc_1404B42BC
0x1404b3f65  lea     rax, aDisablecachete_0; "DisableCacheTelemetry"
0x1404b3f6c  mov     dword ptr [rbp+3A0h+ValueName.Length], 2C002Ah
0x1404b3f73  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3f77  lea     r8, [rbp+3A0h+var_180]; ObjectAttributes
0x1404b3f7e  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3f82  mov     [rbp+3A0h+var_358], r14
0x1404b3f86  xorps   xmm0, xmm0
0x1404b3f89  mov     [rbp+3A0h+var_180.ObjectName], rax
0x1404b3f90  mov     edx, 20019h; DesiredAccess
0x1404b3f95  mov     [rbp+3A0h+var_3BC], r14d
0x1404b3f99  lea     rcx, [rbp+3A0h+var_358]; KeyHandle
0x1404b3f9d  mov     qword ptr [rbp+3A0h+var_180.Length], 30h ; '0'
0x1404b3fa8  mov     qword ptr [rbp+3A0h+var_180.Attributes], 240h
0x1404b3fb3  mov     [rbp+3A0h+var_180.RootDirectory], r14
0x1404b3fba  movdqu  xmmword ptr [rbp+3A0h+var_180.SecurityDescriptor], xmm0
0x1404b3fc2  call    ZwOpenKey
0x1404b3fc7  test    eax, eax
0x1404b3fc9  jns     loc_1404B42C4
0x1404b3fcf  lea     rax, aEnableasynclaz_1; "EnableAsyncLazywrite"
0x1404b3fd6  mov     dword ptr [rbp+3A0h+ValueName.Length], 2A0028h
0x1404b3fdd  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b3fe1  lea     r8, [rbp+3A0h+var_150]; ObjectAttributes
0x1404b3fe8  lea     rax, [rbp+3A0h+var_3E8]
0x1404b3fec  mov     [rbp+3A0h+var_350], r14
0x1404b3ff0  xorps   xmm0, xmm0
0x1404b3ff3  mov     [rbp+3A0h+var_150.ObjectName], rax
0x1404b3ffa  mov     edx, 20019h; DesiredAccess
0x1404b3fff  mov     [rbp+3A0h+var_3B8], r14d
0x1404b4003  lea     rcx, [rbp+3A0h+var_350]; KeyHandle
0x1404b4007  mov     qword ptr [rbp+3A0h+var_150.Length], 30h ; '0'
0x1404b4012  mov     qword ptr [rbp+3A0h+var_150.Attributes], 240h
0x1404b401d  mov     [rbp+3A0h+var_150.RootDirectory], r14
0x1404b4024  movdqu  xmmword ptr [rbp+3A0h+var_150.SecurityDescriptor], xmm0
0x1404b402c  call    ZwOpenKey
0x1404b4031  test    eax, eax
0x1404b4033  jns     loc_1404B42CC
0x1404b4039  lea     rax, aEnableasynclaz_2; "EnableAsyncLazywriteMulti"
0x1404b4040  mov     dword ptr [rbp+3A0h+ValueName.Length], 340032h
0x1404b4047  mov     [rbp+3A0h+ValueName.Buffer], rax
0x1404b404b  lea     r8, [rbp+3A0h+var_120]; ObjectAttributes
0x1404b4052  lea     rax, [rbp+3A0h+var_3E8]
0x1404b4056  mov     [rbp+3A0h+var_348], r14
0x1404b405a  xorps   xmm0, xmm0
0x1404b405d  mov     [rbp+3A0h+var_120.ObjectName], rax
0x1404b4064  mov     edx, 20019h; DesiredAccess
0x1404b4069  mov     [rbp+3A0h+var_3B4], r14d
0x1404b406d  lea     rcx, [rbp+3A0h+var_348]; KeyHandle
0x1404b4071  mov     qword ptr [rbp+3A0h+var_120.Length], 30h ; '0'
0x1404b407c  mov     qword ptr [rbp+3A0h+var_120.Attributes], 240h
0x1404b4087  mov     [rbp+3A0h+var_120.RootDirectory], r14
0x1404b408e  movdqu  xmmword ptr [rbp+3A0h+var_120.SecurityDescriptor], xmm0
0x1404b4096  call    ZwOpenKey
0x1404b409b  test    eax, eax
0x1404b409d  jns     loc_1404B42D4
0x1404b40a3  cmp     [rbp+3A0h+var_41C], r14b
0x1404b40a7  lea     r11, aNotFound; "not found"
0x1404b40ae  mov     r15d, [rbp+3A0h+var_3A8]
0x1404b40b2  lea     rbx, aValid; "valid"
0x1404b40b9  mov     r10, rbx
0x1404b40bc  mov     r9, rbx
0x1404b40bf  cmovz   r10, r11
0x1404b40c3  mov     r8, rbx
0x1404b40c6  cmp     [rbp+3A0h+var_41D], r14b
0x1404b40ca  mov     rdx, rbx
0x1404b40cd  mov     [rsp+4A0h+var_430], r10
0x1404b40d2  mov     rcx, rbx
0x1404b40d5  mov     r10d, [rbp+3A0h+var_3F4]
0x1404b40d9  cmovz   r9, r11
0x1404b40dd  cmp     [rbp+3A0h+var_41E], r14b
0x1404b40e1  mov     rax, rbx
0x1404b40e4  mov     [rsp+4A0h+var_438], r10d
0x1404b40e9  mov     [rsp+4A0h+var_440], r9
0x1404b40ee  cmovz   r8, r11
0x1404b40f2  cmp     [rbp+3A0h+var_41F], r14b
0x1404b40f6  mov     r9d, [rbp+3A0h+var_3F8]
0x1404b40fa  mov     dword ptr [rsp+4A0h+var_448], r9d
0x1404b40ff  cmovz   rdx, r11
0x1404b4103  cmp     [rbp+3A0h+var_400], r14b
0x1404b4107  mov     r9d, r15d
0x1404b410a  mov     [rsp+4A0h+var_450], r8
0x1404b410f  mov     r8d, [rbp+3A0h+var_3FC]
0x1404b4113  cmovz   rcx, r11
0x1404b4117  cmp     [rbp+3A0h+var_420], r14b
0x1404b411b  mov     r14d, [rbp+3A0h+var_3B0]
0x1404b411f  mov     dword ptr [rsp+4A0h+var_458], r8d
  ... truncated ...
```
