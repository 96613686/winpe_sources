# EEDBManager::GetEnrollmentByKey(_GUID,Enrollment * *)

- ea: `0x180004870`
- end: `0x1800056bd`
- name: `?GetEnrollmentByKey@EEDBManager@@QEAAJU_GUID@@PEAPEAVEnrollment@@@Z`
- size: `3661`
- prototype: `int(EEDBManager *__hidden this, struct _GUID *__struct_ptr, struct Enrollment **)`
- caller_count: `17`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004730`
- `0x18001d42c`
- `0x180033a3c`
- `0x180033c3c`
- `0x180033dc8`
- `0x180033fe8`
- `0x1800341e8`
- `0x180034374`
- `0x180034500`
- `0x180034824`
- `0x180034a30`
- `0x180034d68`
- `0x1800350b0`
- `0x1800352bc`
- `0x180037230`
- `0x18003ee54`
- `0x180041c90`

## callees

- `0x180004870`
- `0x1800067a0`
- `0x180006830`
- `0x180006d8c`
- `0x18002e1a0`
- `0x18002e5ac`
- `0x18002ec0a`
- `0x180078040`
- `0x18007b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800051ee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000520b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000533c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005350`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005364`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800053df`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800054a3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800051ee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000520b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000533c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005350`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005364`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800053df`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800054a3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180005624`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180005624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005334`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005334`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ddf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000524e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005326`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ddf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000524e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005326`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ded`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ff3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000525c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ded`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ff3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000525c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005501`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005501`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004ae0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004bf8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004c62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004cdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004d53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004dc1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004e31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004e93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004ee4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004f52`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004fc7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005035`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005114`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000529e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004ae0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004bf8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004c62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004cdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004d53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004dc1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004e31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004e93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004ee4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004f52`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004fc7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005035`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005114`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000529e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000567e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000567e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800048cb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800056a3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800048cb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800056a3`

## string_xrefs

- `0x180004fb5`: `DiscoveryServiceFullURL`
- `0x180005023`: `DiscoveryServiceFullURL`
- `0x180004daf`: `SSPHyperLink`
- `0x180004e1f`: `SSPHyperLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EEDBManager::GetEnrollmentByKey(EEDBManager *this, struct _GUID *a2, struct Enrollment **a3)
{
  Enrollment *v4; // rbx
  __int64 v5; // rcx
  OLECHAR *p_sz; // rax
  DWORD *v7; // r13
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // rcx
  wchar_t *v11; // rdx
  __int64 v12; // r8
  wchar_t *v13; // r9
  wchar_t v14; // ax
  wchar_t *v15; // rcx
  __int64 v16; // rcx
  wchar_t *v17; // rax
  _WORD *v18; // rcx
  HKEY v19; // r14
  __int64 v20; // rdi
  LSTATUS v21; // eax
  WCHAR *v22; // rcx
  WCHAR *v23; // rdx
  WCHAR v24; // ax
  int v25; // r8d
  WCHAR *v26; // rcx
  HKEY v27; // r14
  __int64 v28; // r15
  LSTATUS ValueW; // eax
  bool v30; // cc
  Enrollment *v31; // rax
  LSTATUS v33; // eax
  __int64 v34; // rcx
  int v35; // edi
  int v36; // eax
  LSTATUS v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  LSTATUS v40; // eax
  __int64 v41; // rcx
  _BOOL8 v42; // r15
  LSTATUS v43; // eax
  DWORD v44; // edi
  HANDLE ProcessHeap; // rax
  void *v46; // rax
  _BOOL8 v47; // r15
  LSTATUS v48; // eax
  _BOOL8 v49; // r15
  LSTATUS v50; // eax
  DWORD v51; // edi
  HANDLE v52; // rax
  void *v53; // rdi
  void *v54; // r15
  _BOOL8 v55; // r15
  LSTATUS v56; // eax
  DWORD v57; // edi
  HANDLE v58; // rax
  void *v59; // rdi
  void *v60; // r15
  _BOOL8 v61; // r15
  LSTATUS v62; // eax
  DWORD v63; // edi
  HANDLE v64; // rax
  void *v65; // rdi
  LSTATUS v66; // r15d
  void *v67; // r12
  WCHAR *v68; // rax
  __int64 v69; // rdx
  HANDLE v70; // rax
  DWORD v71; // edi
  HANDLE v72; // rax
  void *v73; // rdi
  void *v74; // r15
  HANDLE v75; // rax
  HANDLE v76; // rax
  HANDLE v77; // rax
  WCHAR *v78; // rax
  __int64 v79; // rdx
  WCHAR *v80; // rax
  Enrollment *v81; // rax
  Enrollment *v82; // rsi
  _OWORD *v83; // rax
  LSTATUS v84; // eax
  DWORD v85; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  int v88; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v90; // [rsp+5Ch] [rbp-A4h] BYREF
  struct Enrollment **v91; // [rsp+60h] [rbp-A0h]
  wchar_t String1[38]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v93[4]; // [rsp+BCh] [rbp-44h] BYREF
  OLECHAR sz; // [rsp+C0h] [rbp-40h] BYREF
  char v95; // [rsp+C2h] [rbp-3Eh] BYREF
  WCHAR v96[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR SubKey[264]; // [rsp+320h] [rbp+220h] BYREF

  v91 = a3;
  hkey = 0;
  String1[0] = 0;
  v4 = 0;
  sz = 0;
  if ( StringFromGUID2(a2, &sz, 39) != 39 )
    goto LABEL_47;
  v5 = 39;
  p_sz = &sz;
  do
  {
    if ( !*p_sz )
      break;
    ++p_sz;
    --v5;
  }
  while ( v5 );
  LODWORD(v7) = -2147024809;
  LODWORD(v8) = -2147024809;
  if ( !v5 )
  {
LABEL_46:
    LODWORD(v7) = v8;
    goto LABEL_41;
  }
  if ( (unsigned __int64)(37 - v5) > 0x24 )
  {
LABEL_47:
    LODWORD(v7) = -2147418113;
    goto LABEL_41;
  }
  v9 = 2147483646;
  v10 = 2147483646;
  v11 = (wchar_t *)&v95;
  v12 = 39;
  v13 = String1;
  do
  {
    if ( !v10 )
      break;
    v14 = *v11;
    if ( !*v11 )
      break;
    ++v11;
    *v13++ = v14;
    --v10;
    --v12;
  }
  while ( v12 );
  v8 = 2147942522LL;
  if ( v12 )
    v8 = 0;
  v15 = v13 - 1;
  if ( v12 )
    v15 = v13;
  *v15 = 0;
  if ( !v12 )
    goto LABEL_46;
  v16 = 39;
  v17 = String1;
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  if ( !v16 )
    goto LABEL_41;
  if ( (unsigned __int64)(37 - v16) > 0x24 )
    goto LABEL_47;
  v18 = &v93[-2 * v16];
  *v18 = 0;
  v19 = (HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL);
  hkey = 0;
  if ( word_1800AFC84 == 0x2000 || !(unsigned __int8)RtlIsStateSeparationEnabled(v18, v8) )
  {
    v20 = 260;
LABEL_23:
    LODWORD(v7) = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Enrollments", String1);
    if ( (int)v7 < 0 )
      goto LABEL_44;
    v21 = RegOpenKeyExW(v19, SubKey, 0, 0x20119u, &hkey);
    LODWORD(v7) = v21;
    if ( v21 > 0 )
      LODWORD(v7) = (unsigned __int16)v21 | 0x80070000;
    goto LABEL_26;
  }
  v20 = 260;
  LODWORD(v7) = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSData\\Software\\Microsoft\\Enrollments", String1);
  if ( (int)v7 < 0 )
    goto LABEL_44;
  v84 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hkey);
  LODWORD(v7) = v84;
  if ( v84 > 0 )
    LODWORD(v7) = (unsigned __int16)v84 | 0x80070000;
  if ( ((int)v7 >= 0 || wcsncmp_0(String1, L"Status", 6u) && wcsncmp_0(String1, L"Context", 7u))
    && (unsigned int)((_DWORD)v7 + 2147024894) <= 1 )
  {
    goto LABEL_23;
  }
LABEL_26:
  v22 = SubKey;
  v23 = v96;
  do
  {
    if ( !v9 )
      break;
    v24 = *v22;
    if ( !*v22 )
      break;
    ++v22;
    *v23++ = v24;
    --v9;
    --v20;
  }
  while ( v20 );
  v25 = -2147024774;
  if ( v20 )
    v25 = 0;
  v26 = v23 - 1;
  if ( v20 )
    v26 = v23;
  *v26 = 0;
  if ( (int)v7 < 0 )
    goto LABEL_165;
  if ( !v20 )
  {
    LODWORD(v7) = v25;
LABEL_165:
    if ( hkey )
    {
      RegCloseKey(hkey);
      hkey = 0;
    }
LABEL_44:
    if ( (int)v7 < 0 )
      goto LABEL_41;
  }
  v27 = hkey;
  pvData = 0;
  v28 = 4;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"EnrollmentType", 0x18u, 0, &pvData, &pcbData);
  LODWORD(v7) = ValueW;
  v30 = ValueW <= 0;
  if ( ValueW )
    goto LABEL_99;
  v31 = (Enrollment *)operator new(0x730u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v31 )
    goto LABEL_38;
  v81 = Enrollment::Enrollment(v31);
  v82 = v81;
  if ( !v81 )
    goto LABEL_38;
  (*(void (__fastcall **)(Enrollment *))(*(_QWORD *)v81 + 8LL))(v81);
  v4 = v82;
  v83 = (_OWORD *)((char *)v82 + 28);
  if ( v82 == (Enrollment *)-28LL )
  {
LABEL_130:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_131;
  }
  if ( !a2 )
  {
    *v83 = 0;
    goto LABEL_130;
  }
  *v83 = *a2;
  if ( StringFromGUID2((const GUID *const)((char *)v82 + 28), (LPOLESTR)v82 + 36, 39) != 39 )
  {
    LODWORD(v7) = -2147418113;
    goto LABEL_39;
  }
  LODWORD(v7) = EEDBTrimGuidBracket((const unsigned __int16 *)v82 + 36, (unsigned __int16 *)v82 + 75);
  if ( (int)v7 < 0 )
    goto LABEL_39;
  *((_DWORD *)v82 + 15) = pvData;
  v88 = 0;
  v90 = 4;
  ValueW = RegGetValueW(hkey, 0, L"EnrollmentState", 0x18u, 0, &v88, &v90);
  LODWORD(v7) = ValueW;
  v30 = ValueW <= 0;
  if ( ValueW )
  {
LABEL_99:
    if ( !v30 )
      LODWORD(v7) = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_39;
  }
  *((_DWORD *)v82 + 6) = v88;
  v85 = 520;
  v33 = RegGetValueW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), v96, L"RootCertThumbPrint", 2u, 0, SubKey, &v85);
  v34 = (__int64)v82 + 228;
  v35 = 22;
  if ( v33 )
  {
    if ( v82 != (Enrollment *)-228LL )
    {
      *(_WORD *)v34 = 0;
LABEL_55:
      v36 = 0;
      goto LABEL_56;
    }
  }
  else if ( v82 != (Enrollment *)-228LL )
  {
    v68 = SubKey;
    v69 = 4;
    do
    {
      *(_OWORD *)v34 = *(_OWORD *)v68;
      *(_OWORD *)(v34 + 16) = *((_OWORD *)v68 + 1);
      *(_OWORD *)(v34 + 32) = *((_OWORD *)v68 + 2);
      *(_OWORD *)(v34 + 48) = *((_OWORD *)v68 + 3);
      *(_OWORD *)(v34 + 64) = *((_OWORD *)v68 + 4);
      *(_OWORD *)(v34 + 80) = *((_OWORD *)v68 + 5);
      *(_OWORD *)(v34 + 96) = *((_OWORD *)v68 + 6);
      *(_OWORD *)(v34 + 112) = *((_OWORD *)v68 + 7);
      v34 += 128;
      v68 += 64;
      --v69;
    }
    while ( v69 );
    *(_QWORD *)v34 = *(_QWORD *)v68;
    goto LABEL_55;
  }
  *(_DWORD *)_o__errno() = 22;
  invalid_parameter_noinfo();
  v36 = 22;
LABEL_56:
  if ( v36 )
  {
LABEL_131:
    LODWORD(v7) = -2147024774;
    goto LABEL_39;
  }
  v85 = 520;
  v37 = RegGetValueW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), v96, L"DMPCertThumbPrint", 2u, 0, SubKey, &v85);
  v38 = (__int64)v82 + 748;
  if ( v37 )
  {
    if ( v82 != (Enrollment *)-748LL )
    {
      *(_WORD *)v38 = 0;
LABEL_60:
      v39 = 0;
      goto LABEL_61;
    }
  }
  else if ( v82 != (Enrollment *)-748LL )
  {
    v78 = SubKey;
    v79 = 4;
    do
    {
      *(_OWORD *)v38 = *(_OWORD *)v78;
      *(_OWORD *)(v38 + 16) = *((_OWORD *)v78 + 1);
      *(_OWORD *)(v38 + 32) = *((_OWORD *)v78 + 2);
      *(_OWORD *)(v38 + 48) = *((_OWORD *)v78 + 3);
      *(_OWORD *)(v38 + 64) = *((_OWORD *)v78 + 4);
      *(_OWORD *)(v38 + 80) = *((_OWORD *)v78 + 5);
      *(_OWORD *)(v38 + 96) = *((_OWORD *)v78 + 6);
      *(_OWORD *)(v38 + 112) = *((_OWORD *)v78 + 7);
      v38 += 128;
      v78 += 64;
      --v79;
    }
    while ( v79 );
    *(_QWORD *)v38 = *(_QWORD *)v78;
    goto LABEL_60;
  }
  *(_DWORD *)_o__errno() = 22;
  invalid_parameter_noinfo();
  v39 = 22;
LABEL_61:
  if ( v39 )
    goto LABEL_131;
  v85 = 520;
  v40 = RegGetValueW(
          (HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL),
          v96,
          L"IntermediateCertThumbPrint",
          2u,
          0,
          SubKey,
          &v85);
  v41 = (__int64)v82 + 1268;
  if ( v40 )
  {
    if ( v82 != (Enrollment *)-1268LL )
    {
      *(_WORD *)v41 = 0;
LABEL_65:
      v35 = 0;
      goto LABEL_66;
    }
  }
  else if ( v82 != (Enrollment *)-1268LL )
  {
    v80 = SubKey;
    do
    {
      *(_OWORD *)v41 = *(_OWORD *)v80;
      *(_OWORD *)(v41 + 16) = *((_OWORD *)v80 + 1);
      *(_OWORD *)(v41 + 32) = *((_OWORD *)v80 + 2);
      *(_OWORD *)(v41 + 48) = *((_OWORD *)v80 + 3);
      *(_OWORD *)(v41 + 64) = *((_OWORD *)v80 + 4);
      *(_OWORD *)(v41 + 80) = *((_OWORD *)v80 + 5);
      *(_OWORD *)(v41 + 96) = *((_OWORD *)v80 + 6);
      *(_OWORD *)(v41 + 112) = *((_OWORD *)v80 + 7);
      v41 += 128;
      v80 += 64;
      --v28;
    }
    while ( v28 );
    *(_QWORD *)v41 = *(_QWORD *)v80;
    goto LABEL_65;
  }
  *(_DWORD *)_o__errno() = 22;
  invalid_parameter_noinfo();
LABEL_66:
  if ( v35 )
    goto LABEL_131;
  v42 = word_1800AFC84 != 0x2000;
  v85 = 0;
  v43 = RegGetValueW((HKEY)(v42 - 0x7FFFFFFF), v96, L"SSPHyperLink", 2u, 0, 0, &v85);
  LODWORD(v7) = v43;
  if ( v43 == 2 )
  {
    *((_QWORD *)v82 + 229) = 0;
    goto LABEL_74;
  }
  if ( v43 )
  {
    if ( v43 <= 0 )
    {
LABEL_73:
      if ( (int)v7 < 0 )
        goto LABEL_39;
      goto LABEL_74;
    }
LABEL_72:
    LODWORD(v7) = (unsigned __int16)v43 | 0x80070000;
    goto LABEL_73;
  }
  v44 = v85;
  ProcessHeap = GetProcessHeap();
  v46 = HeapAlloc(ProcessHeap, 0, v44);
  *((_QWORD *)v82 + 229) = v46;
  if ( !v46 )
    goto LABEL_38;
  v43 = RegGetValueW((HKEY)(v42 - 0x7FFFFFFF), v96, L"SSPHyperLink", 2u, 0, v46, &v85);
  LODWORD(v7) = v43;
  if ( v43 )
  {
    if ( v43 <= 0 )
      goto LABEL_73;
    goto LABEL_72;
  }
LABEL_74:
  v47 = word_1800AFC84 != 0x2000;
  v85 = 0;
  v48 = RegGetValueW((HKEY)(v47 - 0x7FFFFFFF), v96, L"SID", 2u, 0, 0, &v85);
  LODWORD(v7) = v48;
  if ( v48 == 2 )
    goto LABEL_75;
  if ( v48 )
  {
    if ( v48 > 0 )
      LODWORD(v7) = (unsigned __int16)v48 | 0x80070000;
  }
  else
  {
    v71 = v85;
    v72 = GetProcessHeap();
    v73 = HeapAlloc(v72, 0, v71);
    if ( !v73 )
      goto LABEL_38;
    LODWORD(v7) = RegGetValueW((HKEY)(v47 - 0x7FFFFFFF), v96, L"SID", 2u, 0, v73, &v85);
    v74 = (void *)*((_QWORD *)v82 + 225);
    *((_QWORD *)v82 + 225) = 0;
    if ( v74 )
    {
      v77 = GetProcessHeap();
      HeapFree(v77, 0, v74);
    }
    *((_QWORD *)v82 + 225) = v73;
    if ( !(_DWORD)v7 )
      goto LABEL_75;
    if ( (int)v7 > 0 )
      LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
  }
  if ( (int)v7 < 0 )
    goto LABEL_39;
LABEL_75:
  v49 = word_1800AFC84 != 0x2000;
  v85 = 0;
  v50 = RegGetValueW((HKEY)(v49 - 0x7FFFFFFF), v96, L"UPN", 2u, 0, 0, &v85);
  LODWORD(v7) = v50;
  if ( v50 != 2 )
  {
    if ( v50 )
    {
      if ( v50 > 0 )
        LODWORD(v7) = (unsigned __int16)v50 | 0x80070000;
    }
    else
    {
      v51 = v85;
      v52 = GetProcessHeap();
      v53 = HeapAlloc(v52, 0, v51);
      if ( !v53 )
        goto LABEL_38;
      LODWORD(v7) = RegGetValueW((HKEY)(v49 - 0x7FFFFFFF), v96, L"UPN", 2u, 0, v53, &v85);
      v54 = (void *)*((_QWORD *)v82 + 226);
      *((_QWORD *)v82 + 226) = 0;
      if ( v54 )
      {
        v76 = GetProcessHeap();
        HeapFree(v76, 0, v54);
      }
      *((_QWORD *)v82 + 226) = v53;
      if ( !(_DWORD)v7 )
        goto LABEL_81;
      if ( (int)v7 > 0 )
        LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
    }
    if ( (int)v7 < 0 )
      goto LABEL_39;
    goto LABEL_81;
  }
  *((_QWORD *)v82 + 229) = 0;
LABEL_81:
  v55 = word_1800AFC84 != 0x2000;
  v85 = 0;
  v56 = RegGetValueW((HKEY)(v55 - 0x7FFFFFFF), v96, L"DiscoveryServiceFullURL", 2u, 0, 0, &v85);
  LODWORD(v7) = v56;
  if ( v56 == 2 )
    goto LABEL_87;
  if ( v56 )
  {
    if ( v56 > 0 )
      LODWORD(v7) = (unsigned __int16)v56 | 0x80070000;
  }
  else
  {
    v57 = v85;
    v58 = GetProcessHeap();
    v59 = HeapAlloc(v58, 0, v57);
    if ( !v59 )
      goto LABEL_38;
    LODWORD(v7) = RegGetValueW((HKEY)(v55 - 0x7FFFFFFF), v96, L"DiscoveryServiceFullURL", 2u, 0, v59, &v85);
    v60 = (void *)*((_QWORD *)v82 + 227);
    *((_QWORD *)v82 + 227) = 0;
    if ( v60 )
    {
      v70 = GetProcessHeap();
      HeapFree(v70, 0, v60);
    }
    *((_QWORD *)v82 + 227) = v59;
    if ( !(_DWORD)v7 )
      goto LABEL_87;
    if ( (int)v7 > 0 )
      LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
  }
  if ( (int)v7 >= 0 )
  {
LABEL_87:
    v61 = word_1800AFC84 != 0x2000;
    v85 = 0;
    v62 = RegGetValueW((HKEY)(v61 - 0x7FFFFFFF), v96, L"AADTenantID", 2u, 0, 0, &v85);
    v7 = (DWORD *)(unsigned int)v62;
    if ( v62 == 2 )
    {
      LODWORD(v7) = 0;
      v4 = 0;
      *v91 = v82;
      goto LABEL_39;
    }
    if ( v62 )
    {
      if ( v62 > 0 )
        LODWORD(v7) = (unsigned __int16)v62 | 0x80070000;
      goto LABEL_93;
    }
    v63 = v85;
    v64 = GetProcessHeap();
    v65 = HeapAlloc(v64, 0, v63);
    if ( v65 )
    {
      v66 = RegGetValueW((HKEY)(v61 - 0x7FFFFFFF), v96, L"AADTenantID", 2u, v7, v65, &v85);
      v67 = (void *)*((_QWORD *)v82 + 228);
      *((_QWORD *)v82 + 228) = v7;
      if ( v67 )
      {
        v75 = GetProcessHeap();
        HeapFree(v75, 0, v67);
      }
      *((_QWORD *)v82 + 228) = v65;
      if ( v66 )
      {
        if ( v66 > 0 )
          LODWORD(v7) = (unsigned __int16)v66 | 0x80070000;
        else
          LODWORD(v7) = v66;
      }
LABEL_93:
      if ( (int)v7 >= 0 )
      {
        v4 = 0;
        *v91 = v82;
      }
      goto LABEL_39;
    }
LABEL_38:
    LODWORD(v7) = -2147024882;
  }
LABEL_39:
  if ( v27 )
    RegCloseKey(v27);
LABEL_41:
  if ( v4 )
    (*(void (__fastcall **)(Enrollment *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004870  mov     [rsp-8+arg_0], rbx
0x180004875  push    rbp
0x180004876  push    rsi
0x180004877  push    rdi
0x180004878  push    r12
0x18000487a  push    r13
0x18000487c  push    r14
0x18000487e  push    r15
0x180004880  lea     rbp, [rsp-440h]
0x180004888  sub     rsp, 540h
0x18000488f  mov     rax, cs:__security_cookie
0x180004896  xor     rax, rsp
0x180004899  mov     [rbp+470h+var_40], rax
0x1800048a0  mov     [rsp+570h+var_510], r8
0x1800048a5  mov     r12, rdx
0x1800048a8  xor     r15d, r15d
0x1800048ab  mov     [rsp+570h+hkey], r15
0x1800048b0  mov     [rsp+570h+String1], r15w
0x1800048b6  mov     ebx, r15d
0x1800048b9  mov     [rbp+470h+sz], r15w
0x1800048be  mov     r8d, 27h ; '''; cchMax
0x1800048c4  lea     rdx, [rbp+470h+sz]; lpsz
0x1800048c8  mov     rcx, r12; rguid
0x1800048cb  call    cs:__imp_StringFromGUID2
0x1800048d1  cmp     eax, 27h ; '''
0x1800048d4  jnz     loc_180004B71
0x1800048da  mov     ecx, 27h ; '''
0x1800048df  lea     rax, [rbp+470h+sz]
0x1800048e3  cmp     [rax], bx
0x1800048e6  jz      short loc_1800048F2
0x1800048e8  add     rax, 2
0x1800048ec  sub     rcx, 1
0x1800048f0  jnz     short loc_1800048E3
0x1800048f2  mov     r13d, 80070057h
0x1800048f8  mov     edx, r13d
0x1800048fb  test    rcx, rcx
0x1800048fe  cmovnz  edx, r15d
0x180004902  jz      loc_180004B6C
0x180004908  mov     r10d, 25h ; '%'
0x18000490e  mov     eax, r10d
0x180004911  sub     rax, rcx
0x180004914  cmp     rax, 24h ; '$'
0x180004918  ja      loc_180004B71
0x18000491e  mov     esi, 7FFFFFFEh
0x180004923  mov     ecx, esi
0x180004925  lea     rdx, [rbp+470h+var_4AE]
0x180004929  mov     r8d, 27h ; '''
0x18000492f  lea     r9, [rsp+570h+String1]
0x180004934  test    rcx, rcx
0x180004937  jz      short loc_180004956
0x180004939  movzx   eax, word ptr [rdx]
0x18000493c  test    ax, ax
0x18000493f  jz      short loc_180004956
0x180004941  add     rdx, 2
0x180004945  mov     [r9], ax
0x180004949  add     r9, 2
0x18000494d  dec     rcx
0x180004950  sub     r8, 1
0x180004954  jnz     short loc_180004934
0x180004956  mov     edx, 8007007Ah
0x18000495b  test    r8, r8
0x18000495e  cmovnz  edx, r15d
0x180004962  lea     rcx, [r9-2]
0x180004966  cmovnz  rcx, r9
0x18000496a  mov     [rcx], r15w
0x18000496e  jz      loc_180004B6C
0x180004974  mov     ecx, 27h ; '''
0x180004979  lea     rax, [rsp+570h+String1]
0x18000497e  xchg    ax, ax
0x180004980  cmp     [rax], bx
0x180004983  jz      short loc_18000498F
0x180004985  add     rax, 2
0x180004989  sub     rcx, 1
0x18000498d  jnz     short loc_180004980
0x18000498f  test    rcx, rcx
0x180004992  cmovnz  r13d, r15d
0x180004996  jz      loc_180004B20
0x18000499c  sub     r10, rcx
0x18000499f  cmp     r10, 24h ; '$'
0x1800049a3  ja      loc_180004B71
0x1800049a9  lea     rax, [rcx+rcx]
0x1800049ad  lea     rcx, [rbp+470h+var_4B4]
0x1800049b1  sub     rcx, rax
0x1800049b4  mov     [rcx], r15w
0x1800049b8  mov     r14, r15
0x1800049bb  mov     eax, 2000h
0x1800049c0  cmp     cs:word_1800AFC84, ax
0x1800049c7  setnz   r14b
0x1800049cb  add     r14, 0FFFFFFFF80000001h
0x1800049d2  mov     [rsp+570h+hkey], r15
0x1800049d7  cmp     r14, 0FFFFFFFF80000002h
0x1800049de  jz      loc_180005624
0x1800049e4  mov     edi, 104h
0x1800049e9  lea     rax, [rsp+570h+String1]
0x1800049ee  mov     [rsp+570h+phkResult], rax
0x1800049f3  lea     r9, SubKey; "Software\\Microsoft\\Enrollments"
0x1800049fa  lea     r8, aSS_0; "%s\\%s"
0x180004a01  mov     rdx, rdi; unsigned __int64
0x180004a04  lea     rcx, [rbp+470h+SubKey]; unsigned __int16 *
0x180004a0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004a10  mov     r13d, eax
0x180004a13  test    eax, eax
0x180004a15  js      loc_180004B62
0x180004a1b  lea     rax, [rsp+570h+hkey]
0x180004a20  mov     [rsp+570h+phkResult], rax; phkResult
0x180004a25  mov     r9d, 20119h; samDesired
0x180004a2b  xor     r8d, r8d; ulOptions
0x180004a2e  lea     rdx, [rbp+470h+SubKey]; lpSubKey
0x180004a35  mov     rcx, r14; hKey
0x180004a38  call    cs:__imp_RegOpenKeyExW
0x180004a3e  mov     r13d, eax
0x180004a41  test    eax, eax
0x180004a43  jg      loc_180004B79
0x180004a49  lea     rcx, [rbp+470h+SubKey]
0x180004a50  lea     rdx, [rbp+470h+var_460]
0x180004a54  test    rsi, rsi
0x180004a57  jz      short loc_180004A75
0x180004a59  movzx   eax, word ptr [rcx]
0x180004a5c  test    ax, ax
0x180004a5f  jz      short loc_180004A75
0x180004a61  add     rcx, 2
0x180004a65  mov     [rdx], ax
0x180004a68  add     rdx, 2
0x180004a6c  dec     rsi
0x180004a6f  sub     rdi, 1
0x180004a73  jnz     short loc_180004A54
0x180004a75  mov     r8d, 8007007Ah
0x180004a7b  test    rdi, rdi
0x180004a7e  cmovnz  r8d, r15d
0x180004a82  lea     rcx, [rdx-2]
0x180004a86  cmovnz  rcx, rdx
0x180004a8a  mov     [rcx], r15w
0x180004a8e  test    r13d, r13d
0x180004a91  js      loc_180005670
0x180004a97  test    rdi, rdi
0x180004a9a  jz      loc_18000566D
0x180004aa0  mov     r14, [rsp+570h+hkey]
0x180004aa5  mov     [rsp+570h+var_520], r15d
0x180004aaa  mov     r15d, 4
0x180004ab0  mov     [rsp+570h+var_518], r15d
0x180004ab5  lea     rax, [rsp+570h+var_518]
0x180004aba  mov     [rsp+570h+pcbData], rax; pcbData
0x180004abf  lea     rax, [rsp+570h+var_520]
0x180004ac4  mov     [rsp+570h+pvData], rax; pvData
0x180004ac9  mov     [rsp+570h+phkResult], rbx; pdwType
0x180004ace  mov     r9d, 18h; dwFlags
0x180004ad4  lea     r8, aEnrollmenttype; "EnrollmentType"
0x180004adb  xor     edx, edx; lpSubKey
0x180004add  mov     rcx, r14; hkey
0x180004ae0  call    cs:__imp_RegGetValueW
0x180004ae6  mov     r13d, eax
0x180004ae9  test    eax, eax
0x180004aeb  jnz     loc_1800051CF
0x180004af1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004af8  mov     ecx, 730h; unsigned __int64
0x180004afd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004b02  test    rax, rax
0x180004b05  jnz     loc_180005465
0x180004b0b  mov     r13d, 8007000Eh
0x180004b11  test    r14, r14
0x180004b14  jz      short loc_180004B20
0x180004b16  mov     rcx, r14; hKey
0x180004b19  call    cs:__imp_RegCloseKey
0x180004b1f  nop
0x180004b20  test    rbx, rbx
0x180004b23  jz      short loc_180004B35
0x180004b25  mov     rdx, [rbx]
0x180004b28  mov     rcx, rbx
0x180004b2b  mov     rax, [rdx+10h]
0x180004b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b34  nop
0x180004b35  mov     eax, r13d
0x180004b38  mov     rcx, [rbp+470h+var_40]
0x180004b3f  xor     rcx, rsp; StackCookie
0x180004b42  call    __security_check_cookie
0x180004b47  mov     rbx, [rsp+570h+arg_0]
0x180004b4f  add     rsp, 540h
0x180004b56  pop     r15
0x180004b58  pop     r14
0x180004b5a  pop     r13
0x180004b5c  pop     r12
0x180004b5e  pop     rdi
0x180004b5f  pop     rsi
0x180004b60  pop     rbp
0x180004b61  retn
0x180004b62  test    r13d, r13d
0x180004b65  js      short loc_180004B20
0x180004b67  jmp     loc_180004AA0
0x180004b6c  mov     r13d, edx
0x180004b6f  jmp     short loc_180004B20
0x180004b71  mov     r13d, 8000FFFFh
0x180004b77  jmp     short loc_180004B20
0x180004b79  movzx   r13d, ax
0x180004b7d  or      r13d, 80070000h
0x180004b84  jmp     loc_180004A49
0x180004b89  lea     eax, [r13+7FF8FFFEh]
0x180004b90  cmp     eax, 1
0x180004b93  jbe     loc_1800049E9
0x180004b99  jmp     loc_180004A49
0x180004b9e  lea     rdx, [rsi+96h]; unsigned __int16 *
0x180004ba5  lea     rcx, [rsi+48h]; unsigned __int16 *
0x180004ba9  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180004bae  mov     r13d, eax
0x180004bb1  test    eax, eax
0x180004bb3  js      loc_180004B11
0x180004bb9  mov     eax, [rsp+570h+var_520]
0x180004bbd  mov     [rsi+3Ch], eax
0x180004bc0  xor     ecx, ecx
0x180004bc2  mov     [rsp+570h+var_51C], ecx
0x180004bc6  mov     [rsp+570h+var_514], r15d
0x180004bcb  lea     rax, [rsp+570h+var_514]
0x180004bd0  mov     [rsp+570h+pcbData], rax; pcbData
0x180004bd5  lea     rax, [rsp+570h+var_51C]
0x180004bda  mov     [rsp+570h+pvData], rax; pvData
0x180004bdf  mov     [rsp+570h+phkResult], rcx; pdwType
0x180004be4  mov     r9d, 18h; dwFlags
0x180004bea  lea     r8, Value; "EnrollmentState"
0x180004bf1  xor     edx, edx; lpSubKey
0x180004bf3  mov     rcx, [rsp+570h+hkey]; hkey
0x180004bf8  call    cs:__imp_RegGetValueW
0x180004bfe  mov     r13d, eax
0x180004c01  test    eax, eax
0x180004c03  jnz     loc_1800051CF
0x180004c09  mov     eax, [rsp+570h+var_51C]
0x180004c0d  mov     [rsi+18h], eax
0x180004c10  xor     r13d, r13d
0x180004c13  mov     ecx, r13d
0x180004c16  mov     r12d, 2000h
0x180004c1c  cmp     cs:word_1800AFC84, r12w
0x180004c24  setnz   cl
0x180004c27  add     rcx, 0FFFFFFFF80000001h; hkey
0x180004c2e  mov     [rsp+570h+var_530], 208h
0x180004c36  lea     rax, [rsp+570h+var_530]
0x180004c3b  mov     [rsp+570h+pcbData], rax; pcbData
0x180004c40  lea     rax, [rbp+470h+SubKey]
0x180004c47  mov     [rsp+570h+pvData], rax; pvData
0x180004c4c  mov     [rsp+570h+phkResult], r13; pdwType
0x180004c51  mov     r9d, 2; dwFlags
0x180004c57  lea     r8, aRootcertthumbp; "RootCertThumbPrint"
0x180004c5e  lea     rdx, [rbp+470h+var_460]; lpSubKey
0x180004c62  call    cs:__imp_RegGetValueW
0x180004c68  lea     rcx, [rsi+0E4h]
0x180004c6f  mov     edi, 16h
0x180004c74  test    eax, eax
0x180004c76  jz      loc_18000515F
0x180004c7c  test    rcx, rcx
0x180004c7f  jz      loc_18000533C
0x180004c85  mov     [rcx], r13w
0x180004c89  mov     eax, r13d
0x180004c8c  test    eax, eax
0x180004c8e  jnz     loc_1800054B5
0x180004c94  mov     rcx, r13
0x180004c97  cmp     cs:word_1800AFC84, r12w
0x180004c9f  setnz   cl
0x180004ca2  add     rcx, 0FFFFFFFF80000001h; hkey
0x180004ca9  mov     [rsp+570h+var_530], 208h
0x180004cb1  lea     rax, [rsp+570h+var_530]
0x180004cb6  mov     [rsp+570h+pcbData], rax; pcbData
0x180004cbb  lea     rax, [rbp+470h+SubKey]
0x180004cc2  mov     [rsp+570h+pvData], rax; pvData
0x180004cc7  mov     [rsp+570h+phkResult], r13; pdwType
0x180004ccc  mov     r9d, 2; dwFlags
0x180004cd2  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x180004cd9  lea     rdx, [rbp+470h+var_460]; lpSubKey
0x180004cdd  call    cs:__imp_RegGetValueW
0x180004ce3  lea     rcx, [rsi+2ECh]
0x180004cea  test    eax, eax
0x180004cec  jz      loc_1800051E5
0x180004cf2  test    rcx, rcx
0x180004cf5  jz      loc_180005364
0x180004cfb  mov     [rcx], r13w
0x180004cff  mov     eax, r13d
0x180004d02  test    eax, eax
0x180004d04  jnz     loc_1800054B5
0x180004d0a  mov     rcx, r13
0x180004d0d  cmp     cs:word_1800AFC84, r12w
0x180004d15  setnz   cl
0x180004d18  add     rcx, 0FFFFFFFF80000001h; hkey
0x180004d1f  mov     [rsp+570h+var_530], 208h
0x180004d27  lea     rax, [rsp+570h+var_530]
0x180004d2c  mov     [rsp+570h+pcbData], rax; pcbData
0x180004d31  lea     rax, [rbp+470h+SubKey]
0x180004d38  mov     [rsp+570h+pvData], rax; pvData
0x180004d3d  mov     [rsp+570h+phkResult], r13; pdwType
0x180004d42  mov     r9d, 2; dwFlags
0x180004d48  lea     r8, aIntermediatece_0; "IntermediateCertThumbPrint"
0x180004d4f  lea     rdx, [rbp+470h+var_460]; lpSubKey
0x180004d53  call    cs:__imp_RegGetValueW
0x180004d59  lea     rcx, [rsi+4F4h]
0x180004d60  test    eax, eax
0x180004d62  jz      loc_180005202
0x180004d68  test    rcx, rcx
0x180004d6b  jz      loc_1800053DF
0x180004d71  mov     [rcx], r13w
0x180004d75  mov     edi, r13d
0x180004d78  test    edi, edi
0x180004d7a  jnz     loc_1800054B5
0x180004d80  xor     edi, edi
0x180004d82  mov     r15d, edi
0x180004d85  cmp     cs:word_1800AFC84, r12w
  ... truncated ...
```
