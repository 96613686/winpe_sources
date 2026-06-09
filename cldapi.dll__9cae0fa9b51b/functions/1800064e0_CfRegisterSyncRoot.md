# CfRegisterSyncRoot

- ea: `0x1800064e0`
- end: `0x1800078c6`
- name: `CfRegisterSyncRoot`
- size: `5094`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x1800046bc`
- `0x1800064e0`
- `0x18000b65c`
- `0x18000bb90`
- `0x180010294`
- `0x1800112c0`
- `0x180012054`
- `0x180012630`
- `0x180012b08`
- `0x180012c28`
- `0x18001d094`
- `0x18001d0a0`
- `0x18001d0ac`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800068c1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800068eb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800068c1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800068eb`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18000654c`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007897`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18000654c`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007897`
- `ntdll!RtlComputeCrc32` at `0x1800073d5`
- `ntdll!RtlComputeCrc32` at `0x1800073d5`
- `ntdll!RtlNtStatusToDosError` at `0x180006a7d`
- `ntdll!RtlNtStatusToDosError` at `0x180006c50`
- `ntdll!RtlNtStatusToDosError` at `0x180006d32`
- `ntdll!RtlNtStatusToDosError` at `0x180006e10`
- `ntdll!RtlNtStatusToDosError` at `0x180006ed1`
- `ntdll!RtlNtStatusToDosError` at `0x180006f80`
- `ntdll!RtlNtStatusToDosError` at `0x180007034`
- `ntdll!RtlNtStatusToDosError` at `0x1800070e9`
- `ntdll!RtlNtStatusToDosError` at `0x1800071ae`
- `ntdll!RtlNtStatusToDosError` at `0x1800072bb`
- `ntdll!RtlNtStatusToDosError` at `0x180007375`
- `ntdll!RtlNtStatusToDosError` at `0x180006a7d`
- `ntdll!RtlNtStatusToDosError` at `0x180006c50`
- `ntdll!RtlNtStatusToDosError` at `0x180006d32`
- `ntdll!RtlNtStatusToDosError` at `0x180006e10`
- `ntdll!RtlNtStatusToDosError` at `0x180006ed1`
- `ntdll!RtlNtStatusToDosError` at `0x180006f80`
- `ntdll!RtlNtStatusToDosError` at `0x180007034`
- `ntdll!RtlNtStatusToDosError` at `0x1800070e9`
- `ntdll!RtlNtStatusToDosError` at `0x1800071ae`
- `ntdll!RtlNtStatusToDosError` at `0x1800072bb`
- `ntdll!RtlNtStatusToDosError` at `0x180007375`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180006563`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180006563`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000741e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007874`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000741e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007874`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006b53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007432`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006b53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007432`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000784d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000784d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007863`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007863`

## string_xrefs

- `0x1800065aa`: `SyncRootPath is NULL`
- `0x180006ab6`: `CfpCreateFile on SyncRootPath failed`
- `0x180007120`: `SetSyncRootHardLinkPolicy Failed`
- `0x1800077dc`: `CfpRegisterSyncRoot (Update) Failed`

## pseudocode

```c
__int64 __fastcall CfRegisterSyncRoot(__int64 a1, __int64 a2, _DWORD *a3, int a4)
{
  __int64 v7; // r12
  _DWORD *v8; // r15
  __int64 v9; // rcx
  char v10; // di
  signed int v11; // esi
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  wchar_t *v14; // rbx
  bool v15; // cf
  const wchar_t *v16; // r8
  void *v17; // rdx
  unsigned int v18; // r13d
  int v19; // edi
  int v20; // eax
  int v21; // ebx
  int v22; // ecx
  int v23; // r14d
  int v24; // eax
  unsigned int v25; // r12d
  __int64 v26; // rcx
  unsigned int v27; // r14d
  __int64 v28; // rcx
  __int64 v29; // rdx
  NTSTATUS File; // eax
  __int64 v31; // rcx
  bool v32; // zf
  unsigned int v33; // r12d
  HANDLE ProcessHeap; // rax
  __int64 v35; // rcx
  unsigned int *v36; // r13
  char *v37; // rdx
  NTSTATUS v38; // r12d
  NTSTATUS v39; // ecx
  __int64 v40; // rcx
  size_t v41; // r8
  __int64 v42; // rcx
  char *v43; // rcx
  signed int v44; // eax
  __int64 v45; // rcx
  NTSTATUS v46; // ecx
  __int64 v47; // rcx
  unsigned int v48; // eax
  wchar_t *v49; // rcx
  signed int v50; // eax
  __int64 v51; // rcx
  NTSTATUS v52; // ecx
  __int64 v53; // rcx
  unsigned int v54; // eax
  wchar_t *v55; // rcx
  signed int v56; // eax
  __int64 v57; // rcx
  NTSTATUS v58; // ecx
  __int64 v59; // rcx
  __int64 v60; // rax
  signed int v61; // eax
  __int64 v62; // rcx
  NTSTATUS v63; // ecx
  __int64 v64; // rcx
  __int64 v65; // rax
  signed int v66; // eax
  __int64 v67; // rcx
  NTSTATUS v68; // ecx
  __int64 v69; // rcx
  __int64 v70; // rax
  int v71; // ecx
  signed int v72; // eax
  __int64 v73; // rcx
  NTSTATUS v74; // ecx
  __int64 v75; // rcx
  __int64 v76; // rax
  signed int v77; // eax
  __int64 v78; // rcx
  __int64 v79; // rbx
  NTSTATUS v80; // ecx
  __int64 v81; // rdx
  __int128 v82; // xmm0
  __int64 v83; // rax
  signed int v84; // eax
  __int64 v85; // rcx
  unsigned int Guid; // eax
  __int64 v87; // rcx
  NTSTATUS v88; // ecx
  __int64 v89; // rdx
  __int128 v90; // xmm0
  __int64 v91; // rax
  signed int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rax
  signed int v96; // eax
  __int64 v97; // rcx
  unsigned int v98; // r8d
  int v99; // eax
  int v100; // r14d
  unsigned int v101; // edi
  HANDLE v102; // rax
  const wchar_t *v103; // rcx
  unsigned int SyncRootInfoByHandle; // eax
  __int64 v105; // rcx
  unsigned int v106; // eax
  __int64 v107; // rcx
  int v108; // eax
  __int64 v109; // rcx
  __int64 v110; // rcx
  const wchar_t *v111; // rcx
  int v112; // eax
  __int64 v113; // rcx
  int v114; // eax
  __int64 v115; // rcx
  __int64 v116; // rcx
  size_t v117; // rdi
  __int64 v118; // rcx
  unsigned int v119; // eax
  __int64 v120; // rcx
  HANDLE v121; // rax
  HANDLE v122; // rcx
  HANDLE v123; // rax
  size_t v125; // [rsp+20h] [rbp-E0h]
  char v126; // [rsp+50h] [rbp-B0h]
  const wchar_t *v127; // [rsp+58h] [rbp-A8h]
  wchar_t *Source; // [rsp+60h] [rbp-A0h]
  unsigned int v129; // [rsp+68h] [rbp-98h]
  int v130; // [rsp+6Ch] [rbp-94h]
  wchar_t *String2; // [rsp+78h] [rbp-88h]
  ULONG cbInput; // [rsp+80h] [rbp-80h]
  int v134; // [rsp+84h] [rbp-7Ch]
  int v135; // [rsp+88h] [rbp-78h] BYREF
  int v136; // [rsp+8Ch] [rbp-74h]
  unsigned int Size; // [rsp+90h] [rbp-70h]
  int Size_4; // [rsp+94h] [rbp-6Ch]
  HANDLE hObject; // [rsp+98h] [rbp-68h]
  __int64 v140; // [rsp+A0h] [rbp-60h]
  int Buf2; // [rsp+A8h] [rbp-58h] BYREF
  int v142; // [rsp+ACh] [rbp-54h] BYREF
  unsigned __int64 v143; // [rsp+B0h] [rbp-50h]
  unsigned __int64 UnbiasedTime; // [rsp+B8h] [rbp-48h] BYREF
  void *Src; // [rsp+C0h] [rbp-40h]
  void *v146; // [rsp+C8h] [rbp-38h]
  char v147[8]; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v148; // [rsp+D8h] [rbp-28h]
  int v149; // [rsp+E0h] [rbp-20h]
  char v150; // [rsp+E4h] [rbp-1Ch]
  UCHAR pbOutput[16]; // [rsp+130h] [rbp+30h] BYREF

  *(_QWORD *)pbOutput = a2;
  v140 = a1;
  hObject = (HANDLE)-1LL;
  LODWORD(String2) = 0;
  v135 = 0;
  UnbiasedTime = 0;
  v7 = 0;
  v8 = 0;
  memset_0(v147, 0, 0x58u);
  LOBYTE(v9) = 2;
  v126 = RtlSetThreadPlaceholderCompatibilityMode(v9);
  v10 = v126;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v11 = a1 == 0 ? 0x57 : 0;
  v12 = v11 | 0x80070000;
  if ( !v140 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1498, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"SyncRootPath is NULL";
LABEL_6:
      v14 = 0;
      goto LABEL_331;
    }
  }
  v11 = a2 == 0 ? 0x57 : 0;
  if ( !a2 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1499, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"Registration is NULL";
      goto LABEL_6;
    }
  }
  v11 = *(_QWORD *)(a2 + 8) == 0 ? 0x57 : 0;
  if ( !*(_QWORD *)(a2 + 8) )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1500, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"ProviderName is NULL";
      goto LABEL_6;
    }
  }
  v11 = *(_QWORD *)(a2 + 16) == 0 ? 0x57 : 0;
  if ( !*(_QWORD *)(a2 + 16) )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1501, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"ProviderVersion is NULL";
      goto LABEL_6;
    }
  }
  if ( !*(_QWORD *)(a2 + 24) || (v11 = 87, *(_DWORD *)(a2 + 32)) )
    v11 = 0;
  if ( v11 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1505, "CfRegisterSyncRoot", (unsigned int)v11);
    v13 = L"Invalid SyncRootIdentity";
    goto LABEL_6;
  }
  if ( !*(_QWORD *)(a2 + 40) || (v11 = 87, *(_DWORD *)(a2 + 48)) )
    v11 = 0;
  if ( v11 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1509, "CfRegisterSyncRoot", (unsigned int)v11);
    v13 = L"Invalid FileIdentity";
    goto LABEL_6;
  }
  v11 = a3 == 0 ? 0x57 : 0;
  if ( !a3 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1511, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"Policies can't be NULL";
      goto LABEL_6;
    }
  }
  v11 = *a3 < 0x14u ? 0x57 : 0;
  if ( *a3 < 0x14u )
    v11 = (*a3 < 0x14u ? 0x57 : 0) | 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1515, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"StructSize lesser than PlaceholderManagement";
      goto LABEL_6;
    }
  }
  v11 = *(_DWORD *)(a2 + 32) > 0x1000u ? 0x57 : 0;
  if ( *(_DWORD *)(a2 + 32) > 0x1000u )
    v11 = (*(_DWORD *)(a2 + 32) > 0x1000u ? 0x57 : 0) | 0x80070000;
  if ( v11 )
  {
    TlmChk(4096, 1519, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"SyncRootIdentityLength invalid";
      goto LABEL_6;
    }
  }
  v15 = *a3 < 0x14u;
  v16 = *(const wchar_t **)(a2 + 8);
  v7 = *(_QWORD *)(a2 + 16);
  v17 = *(void **)(a2 + 24);
  v18 = *(_DWORD *)(a2 + 32);
  v19 = a3[2];
  v146 = *(void **)(a2 + 40);
  v20 = *(_DWORD *)(a2 + 48);
  v21 = a3[1];
  Size_4 = v20;
  v136 = a3[3];
  String2 = (wchar_t *)v16;
  Source = (wchar_t *)v7;
  Src = v17;
  Size = v18;
  Buf2 = v21;
  v142 = v19;
  if ( v15 )
  {
    v23 = 0;
    v130 = 0;
    goto LABEL_56;
  }
  v130 = a3[4];
  if ( *a3 < 0x18u )
  {
    v130 = a3[4];
    v23 = 0;
LABEL_56:
    v134 = 0;
    goto LABEL_57;
  }
  v22 = a3[5];
  v23 = 0;
  v134 = v22;
LABEL_57:
  if ( (v21 & 0x20000) == 0 || (v11 = 87, (v21 & 0x10000) == 0) )
    v11 = 0;
  if ( v11 )
    v11 |= 0x80070000;
  if ( !v11 )
  {
    if ( v16 )
      v24 = wcsnlen(v16, 0xFFu);
    else
      v24 = 0;
    v25 = 2 * v24 + 2;
    cbInput = v25;
    if ( Source )
      v23 = wcsnlen(Source, 0xFFu);
    v11 = 0;
    if ( v25 <= 2 )
      v11 = 87;
    v26 = v11 | 0x80070000;
    if ( v25 <= 2 )
      v11 |= 0x80070000;
    if ( v11 )
    {
      TlmChk(v26, 1556, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"providerNameLength smaller than expected";
LABEL_76:
        v14 = 0;
LABEL_329:
        v7 = (__int64)Source;
        goto LABEL_330;
      }
    }
    v11 = v25 >= 0x1FE ? 0x57 : 0;
    if ( v25 >= 0x1FE )
      v11 = (v25 >= 0x1FE ? 0x57 : 0) | 0x80070000;
    if ( v11 )
    {
      TlmChk(510, 1559, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"providerNameLength larger than allowed";
        goto LABEL_76;
      }
    }
    v27 = 2 * v23 + 2;
    v11 = 0;
    if ( v27 <= 2 )
      v11 = -2147024809;
    if ( v11 )
    {
      TlmChk(2, 1563, "CfRegisterSyncRoot", (unsigned int)v11);
      v13 = L"providerVersionLength smaller than expected";
      goto LABEL_76;
    }
    v28 = 510;
    v11 = v27 >= 0x1FE ? 0x57 : 0;
    if ( v27 >= 0x1FE )
      v11 = (v27 >= 0x1FE ? 0x57 : 0) | 0x80070000;
    if ( v11 )
    {
      TlmChk(510, 1566, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"providerVersionLength larger than expected";
        goto LABEL_76;
      }
    }
    LOBYTE(v28) = 1;
    v11 = GlobalPortInit(v28);
    if ( v11 <= -1 )
    {
      v13 = L"GlobalPortInit Failed";
LABEL_94:
      v14 = 0;
      goto LABEL_329;
    }
    v11 = AttachFilterToVolume(v140);
    if ( v11 <= -1 )
    {
      v13 = L"AttachFilterToVolume Failed";
      goto LABEL_94;
    }
    File = CfpCreateFile(v140, v29, 0, 7);
    v11 = RtlNtStatusToDosError(File);
    v32 = v11 == 0;
    if ( v11 > 0 )
    {
      v11 = (unsigned __int16)v11 | 0x80070000;
      v32 = v11 == 0;
    }
    if ( !v32 )
    {
      TlmChk(v31, 1585, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"CfpCreateFile on SyncRootPath failed";
        goto LABEL_76;
      }
    }
    v33 = ((v27 + ((((v18 + 91) & 0xFFFFFFFC) + 3 + v25) & 0xFFFFFFFC) + 23) & 0xFFFFFFFC) + 16;
    v129 = v33;
    v11 = v33 > 0x10000 ? 0x57 : 0;
    if ( v33 > 0x10000 )
      v11 = (v33 > 0x10000 ? 0x57 : 0) | 0x80070000;
    if ( v11 )
    {
      TlmChk(0x10000, 1600, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"Invalid syncRootInfoLength";
LABEL_107:
        v14 = 0;
        goto LABEL_329;
      }
    }
    v143 = v33;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, v33);
    v11 = v8 == 0 ? 8 : 0;
    if ( !v8 )
      v11 |= 0x80070000;
    if ( v11 )
    {
      TlmChk(v35, 1606, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"syncRootInfo allocation failed";
        goto LABEL_107;
      }
    }
    *(_QWORD *)v8 = 1850307155;
    v36 = v8 + 2;
    v8[3] = 589824;
    v8[2] = 88;
    memset_0(v8 + 4, 0, 0x48u);
    v37 = (char *)Src;
    v38 = -1073741789;
    if ( !Src )
      goto LABEL_128;
    if ( v129 < 0x18 )
      goto LABEL_115;
    if ( *((_WORD *)v8 + 7) )
    {
      v40 = *v36;
      v41 = (unsigned __int16)Size;
      if ( (unsigned __int16)Size + ((v40 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v143 )
      {
LABEL_115:
        v39 = -1073741789;
        goto LABEL_122;
      }
      v42 = ((_DWORD)v40 + 3) & 0xFFFFFFFC;
      *v36 = v42;
      v8[5] = v42;
      v43 = (char *)v8 + v42;
      *((_WORD *)v8 + 8) = 17;
      *((_WORD *)v8 + 9) = v41;
      if ( v43 != v37 )
        memcpy_0(v43, v37, v41);
      v39 = 0;
      *v36 += *((unsigned __int16 *)v8 + 9);
    }
    else
    {
      v39 = -1073741811;
    }
LABEL_122:
    v44 = RtlNtStatusToDosError(v39);
    v11 = v44;
    if ( v44 > 0 )
      v11 = (unsigned __int16)v44 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v45, 1617, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootIdentity Failed";
LABEL_127:
        v14 = 0;
        goto LABEL_329;
      }
    }
LABEL_128:
    if ( v129 < 0x18 )
    {
LABEL_129:
      v46 = -1073741789;
      goto LABEL_140;
    }
    if ( *((_WORD *)v8 + 7) > 1u )
    {
      if ( v129 < 0x20 )
        goto LABEL_129;
      v47 = *v36;
      if ( (unsigned __int16)cbInput + ((v47 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v143 )
        goto LABEL_129;
      if ( *((_WORD *)v8 + 12) )
        *((_WORD *)v8 + 6) |= 1u;
      v48 = (v47 + 3) & 0xFFFFFFFC;
      *v36 = v48;
      *((_WORD *)v8 + 12) = 17;
      *((_WORD *)v8 + 13) = cbInput;
      v8[7] = v48;
      if ( String2 )
      {
        v49 = (wchar_t *)((char *)v8 + v48);
        if ( v49 != String2 )
          memcpy_0(v49, String2, (unsigned __int16)cbInput);
      }
      v46 = 0;
      *v36 += *((unsigned __int16 *)v8 + 13);
    }
    else
    {
      v46 = -1073741811;
    }
LABEL_140:
    v50 = RtlNtStatusToDosError(v46);
    v11 = v50;
    if ( v50 > 0 )
      v11 = (unsigned __int16)v50 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v51, 1625, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootProviderName Failed";
        goto LABEL_127;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_146;
    if ( *((_WORD *)v8 + 7) > 2u )
    {
      if ( v129 < 0x28 || (v53 = *v36, (unsigned __int16)v27 + ((v53 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v143) )
      {
LABEL_146:
        v52 = -1073741789;
        goto LABEL_157;
      }
      if ( *((_WORD *)v8 + 16) )
        *((_WORD *)v8 + 6) |= 1u;
      v54 = (v53 + 3) & 0xFFFFFFFC;
      *v36 = v54;
      *((_WORD *)v8 + 16) = 17;
      *((_WORD *)v8 + 17) = v27;
      v8[9] = v54;
      if ( Source )
      {
        v55 = (wchar_t *)((char *)v8 + v54);
        if ( v55 != Source )
          memcpy_0(v55, Source, (unsigned __int16)v27);
      }
      v52 = 0;
      *v36 += *((unsigned __int16 *)v8 + 17);
    }
    else
    {
      v52 = -1073741811;
    }
LABEL_157:
    v56 = RtlNtStatusToDosError(v52);
    v11 = v56;
    if ( v56 > 0 )
      v11 = (unsigned __int16)v56 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v57, 1632, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootProviderVersion Failed";
LABEL_162:
        v14 = 0;
        goto LABEL_329;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_164;
    if ( *((_WORD *)v8 + 7) > 3u )
    {
      if ( v129 < 0x30 || (v59 = *v36, ((v59 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_164:
        v58 = -1073741789;
        goto LABEL_172;
      }
      v60 = ((_DWORD)v59 + 3) & 0xFFFFFFFC;
      *v36 = v60;
      if ( *((_WORD *)v8 + 20) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[10] = 262154;
      v58 = 0;
      v8[11] = v60;
      *(_DWORD *)((char *)v8 + v60) = v21;
      *v36 += 4;
    }
    else
    {
      v58 = -1073741811;
    }
LABEL_172:
    v61 = RtlNtStatusToDosError(v58);
    v14 = 0;
    v11 = v61;
    if ( v61 > 0 )
      v11 = (unsigned __int16)v61 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v62, 1638, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootHydrationPolicy Failed";
        goto LABEL_329;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_178;
    if ( *((_WORD *)v8 + 7) > 4u )
    {
      if ( v129 < 0x38 || (v64 = *v36, ((v64 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_178:
        v63 = -1073741789;
        goto LABEL_186;
      }
      v65 = ((_DWORD)v64 + 3) & 0xFFFFFFFC;
      *v36 = v65;
      if ( *((_WORD *)v8 + 24) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[12] = 262154;
      v63 = 0;
      v8[13] = v65;
      *(_DWORD *)((char *)v8 + v65) = v19;
      *v36 += 4;
    }
    else
    {
      v63 = -1073741811;
    }
LABEL_186:
    v66 = RtlNtStatusToDosError(v63);
    v11 = v66;
    if ( v66 > 0 )
      v11 = (unsigned __int16)v66 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v67, 1644, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootPopulationPolicy Failed";
        goto LABEL_329;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_192;
    if ( *((_WORD *)v8 + 7) > 5u )
    {
      if ( v129 < 0x40 || (v69 = *v36, ((v69 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_192:
        v68 = -1073741789;
        goto LABEL_200;
      }
      v70 = ((_DWORD)v69 + 3) & 0xFFFFFFFC;
      *v36 = v70;
      if ( *((_WORD *)v8 + 28) )
        *((_WORD *)v8 + 6) |= 1u;
      v71 = v136;
      v8[14] = 262154;
      v8[15] = v70;
      *(_DWORD *)((char *)v8 + v70) = v71;
      v68 = 0;
      *v36 += 4;
    }
    else
    {
      v68 = -1073741811;
    }
LABEL_200:
    v72 = RtlNtStatusToDosError(v68);
    v11 = v72;
    if ( v72 > 0 )
      v11 = (unsigned __int16)v72 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v73, 1648, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootInSyncPolicy Failed";
        goto LABEL_329;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_206;
    if ( *((_WORD *)v8 + 7) > 6u )
    {
      if ( v129 < 0x48 || (v75 = *v36, ((v75 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_206:
        v74 = -1073741789;
        goto LABEL_214;
      }
      v76 = ((_DWORD)v75 + 3) & 0xFFFFFFFC;
      *v36 = v76;
      if ( *((_WORD *)v8 + 32) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[16] = 262154;
      v8[17] = v76;
      *(_DWORD *)((char *)v8 + v76) = v130;
      v74 = 0;
      *v36 += 4;
    }
    else
    {
      v74 = -1073741811;
    }
LABEL_214:
    v77 = RtlNtStatusToDosError(v74);
    v11 = v77;
    if ( v77 > 0 )
      v11 = (unsigned __int16)v77 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v78, 1652, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootHardLinkPolicy Failed";
        goto LABEL_329;
      }
    }
    v79 = *(_QWORD *)pbOutput;
    if ( **(_DWORD **)pbOutput >= 0x44u )
    {
      if ( v129 < 0x18 )
      {
LABEL_221:
        v80 = -1073741789;
        goto LABEL_229;
      }
      if ( *((_WORD *)v8 + 7) > 7u )
      {
        if ( v129 < 0x50 )
          goto LABEL_221;
        v81 = *v36;
        if ( ((v81 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 16 > v129 )
          goto LABEL_221;
        v82 = *(_OWORD *)(*(_QWORD *)pbOutput + 52LL);
        v83 = ((_DWORD)v81 + 3) & 0xFFFFFFFC;
        *v36 = v83;
        if ( *((_WORD *)v8 + 36) )
          *((_WORD *)v8 + 6) |= 1u;
        v8[18] = 1048592;
        v8[19] = v83;
        *(_OWORD *)((char *)v8 + v83) = v82;
        *v36 += 16;
        v80 = 0;
      }
      else
      {
        v80 = -1073741811;
      }
LABEL_229:
      v84 = RtlNtStatusToDosError(v80);
      v11 = v84;
      if ( v84 > 0 )
        v11 = (unsigned __int16)v84 | 0x80070000;
      if ( v11 )
      {
        TlmChk(v85, 1666, "CfRegisterSyncRoot", (unsigned int)v11);
        if ( v11 < 0 )
        {
          v13 = L"SetSyncRootProviderGuid Failed";
          goto LABEL_162;
        }
      }
LABEL_251:
      if ( v129 >= 0x18 )
      {
        if ( *((_WORD *)v8 + 7) > 8u )
        {
          if ( v129 >= 0x58 )
          {
            v94 = *v36;
            if ( ((v94 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v129 )
            {
              v95 = ((_DWORD)v94 + 3) & 0xFFFFFFFC;
              *v36 = v95;
              if ( *((_WORD *)v8 + 40) )
                *((_WORD *)v8 + 6) |= 1u;
              v38 = 0;
              v8[20] = 262154;
              v8[21] = v95;
              *(_DWORD *)((char *)v8 + v95) = v134;
              *v36 += 4;
            }
          }
        }
        else
        {
          v38 = -1073741811;
        }
      }
      v96 = RtlNtStatusToDosError(v38);
      v11 = v96;
      if ( v96 > 0 )
        v11 = (unsigned __int16)v96 | 0x80070000;
      if ( v11 )
      {
        TlmChk(v97, 1689, "CfRegisterSyncRoot", (unsigned int)v11);
        if ( v11 < 0 )
        {
          v13 = L"SetSyncRootPlaceholderManagementPolicy failed.";
          v14 = 0;
          goto LABEL_329;
        }
      }
      v98 = *v36;
      *((_WORD *)v8 + 6) |= 2u;
      v8[1] = RtlComputeCrc32(0, (PUCHAR)v8 + 8, v98 - 8);
      if ( (unsigned __int16)v19 >= 3u || (a4 & 2) != 0 )
      {
        v99 = 65;
        v100 = 320;
      }
      else
      {
        v99 = 33;
        v100 = 288;
      }
      if ( (a4 & 4) != 0 )
        v100 = v99;
      v101 = *(_DWORD *)(v79 + 32) + 1056;
      v102 = GetProcessHeap();
      v103 = (const wchar_t *)HeapAlloc(v102, 0, v101);
      v127 = v103;
      v11 = v103 == 0 ? 8 : 0;
      if ( !v103 )
        v11 |= 0x80070000;
      if ( !v11 || (TlmChk(v103, 1725, "CfRegisterSyncRoot", (unsigned int)v11), v11 >= 0) )
      {
        SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle(hObject, (__int64)&v135);
        v11 = SyncRootInfoByHandle;
        if ( SyncRootInfoByHandle == -2147024506 )
        {
          v7 = (__int64)Source;
          TlmInitializeFirstRunExpStatus(UnbiasedTime, String2, Source);
          LODWORD(v125) = Size_4;
          v106 = CfpRegisterSyncRoot(hObject, (char *)v8, v129, v146, v125, v100, 0);
          v11 = v106;
          if ( v106 && (TlmChk(v107, 1749, "CfRegisterSyncRoot", v106), v11 < 0) )
          {
            v13 = L"CfpRegisterSyncRoot Failed when folder not under syncroot";
          }
          else
          {
            v13 = 0;
            v150 = 1;
          }
          v14 = (wchar_t *)v127;
          goto LABEL_330;
        }
        if ( SyncRootInfoByHandle == -2147024662 )
        {
          v108 = 0;
        }
        else
        {
          if ( SyncRootInfoByHandle )
          {
            TlmChk(v105, 1767, "CfRegisterSyncRoot", SyncRootInfoByHandle);
            if ( v11 < 0 )
            {
              v13 = L"CfpGetSyncRootInfoByHandle Failed";
LABEL_328:
              v14 = (wchar_t *)v127;
              goto LABEL_329;
            }
          }
          v108 = v135;
        }
        if ( (a4 & 1) == 0 )
        {
          v11 = v108 != v101 ? 0x57 : 0;
          if ( v11 )
            v11 |= 0x80070000;
          if ( v11 )
          {
            TlmChk(v105, 1783, "CfRegisterSyncRoot", (unsigned int)v11);
            v13 = L"SyncRootStdInfoLength Mismatch";
            goto LABEL_328;
          }
          v14 = (wchar_t *)v127;
          v11 = memcmp_0(v127 + 4, &Buf2, 4u) != 0 ? 0x57 : 0;
          if ( v11 )
            v11 |= 0x80070000;
          if ( v11 )
          {
            TlmChk(v109, 1788, "CfRegisterSyncRoot", (unsigned int)v11);
            v13 = L"HydrationPolicy Mismatch";
            goto LABEL_329;
          }
          v11 = memcmp_0(v127 + 6, &v142, 4u) != 0 ? 0x57 : 0;
          if ( v11 )
            v11 |= 0x80070000;
          if ( v11 )
          {
            TlmChk(v110, 1793, "CfRegisterSyncRoot", (unsigned int)v11);
LABEL_299:
            v13 = L"PopulationPolicy Mismatch";
            goto LABEL_329;
          }
          v111 = v127;
          v11 = v136 != *((_DWORD *)v127 + 4) ? 0x57 : 0;
          if ( *((_DWORD *)v127 + 4) != v136 )
            v11 = (v136 != *((_DWORD *)v127 + 4) ? 0x57 : 0) | 0x80070000;
          if ( v11 )
          {
            TlmChk(v127, 1796, "CfRegisterSyncRoot", (unsigned int)v11);
            if ( v11 < 0 )
              goto LABEL_299;
            v111 = v127;
          }
          v112 = wcsncmp_0(v111 + 14, String2, 0xFFu);
          v11 = v112 != 0 ? 0x57 : 0;
          v113 = v11 | 0x80070000;
          if ( v112 )
            v11 |= 0x80070000;
          if ( !v11 || (TlmChk(v113, 1801, "CfRegisterSyncRoot", (unsigned int)v11), v11 >= 0) )
          {
            v7 = (__int64)Source;
            v114 = wcsncmp_0(v127 + 270, Source, 0xFFu);
            v11 = v114 != 0 ? 0x57 : 0;
            v115 = v11 | 0x80070000;
            if ( v114 )
              v11 |= 0x80070000;
            if ( v11 && (TlmChk(v115, 1806, "CfRegisterSyncRoot", (unsigned int)v11), v11 < 0) )
            {
              v13 = L"ProviderVersion Mismatch";
            }
            else
            {
              v116 = *((unsigned int *)v127 + 263);
              v117 = Size;
              v11 = Size != *((_DWORD *)v127 + 263) ? 0x57 : 0;
              if ( (_DWORD)v116 != Size )
                v11 = (Size != *((_DWORD *)v127 + 263) ? 0x57 : 0) | 0x80070000;
              if ( v11 && (TlmChk(v116, 1810, "CfRegisterSyncRoot", (unsigned int)v11), v11 < 0) )
              {
                v13 = L"SyncRootIdentityLength Mismatch";
              }
              else
              {
                v11 = memcmp_0(v127 + 528, Src, v117) != 0 ? 0x57 : 0;
                if ( v11 )
                  v11 |= 0x80070000;
                if ( v11 )
                {
                  TlmChk(v118, 1815, "CfRegisterSyncRoot", (unsigned int)v11);
                  v13 = L"SyncRootIdentity Mismatch";
                }
                else
                {
                  v13 = 0;
                }
              }
            }
            goto LABEL_330;
          }
          v13 = L"ProviderName Mismatch";
          goto LABEL_329;
        }
        LODWORD(v125) = Size_4;
        v119 = CfpRegisterSyncRoot(hObject, (char *)v8, v129, v146, v125, v100, 1);
        v11 = v119;
        if ( v119 )
        {
          TlmChk(v120, 1829, "CfRegisterSyncRoot", v119);
          v13 = L"CfpRegisterSyncRoot (Update) Failed";
          if ( v11 < 0 )
            goto LABEL_328;
        }
      }
      v13 = 0;
      goto LABEL_328;
    }
    *(_OWORD *)pbOutput = 0;
    Guid = CfpMakeGuid((PUCHAR)String2, cbInput, pbOutput);
    v11 = Guid;
    if ( Guid )
    {
      TlmChk(v87, 1678, "CfRegisterSyncRoot", Guid);
      if ( v11 < 0 )
      {
        v13 = L"CfpMakeGuid Failed";
        goto LABEL_127;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_238;
    if ( *((_WORD *)v8 + 7) > 7u )
    {
      if ( v129 < 0x50 || (v89 = *v36, ((v89 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 16 > v129) )
      {
LABEL_238:
        v88 = -1073741789;
        goto LABEL_246;
      }
      v90 = *(_OWORD *)pbOutput;
      v91 = ((_DWORD)v89 + 3) & 0xFFFFFFFC;
      *v36 = v91;
      if ( *((_WORD *)v8 + 36) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[18] = 1048592;
      v8[19] = v91;
      *(_OWORD *)((char *)v8 + v91) = v90;
      *v36 += 16;
      v88 = 0;
    }
    else
    {
      v88 = -1073741811;
    }
LABEL_246:
    v92 = RtlNtStatusToDosError(v88);
    v11 = v92;
    if ( v92 > 0 )
      v11 = (unsigned __int16)v92 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v93, 1682, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootProviderGuid after CfpMakeGuid failed";
        goto LABEL_162;
      }
    }
    goto LABEL_251;
  }
  TlmChk(2, 1545, "CfRegisterSyncRoot", (unsigned int)v11);
  v13 = L"hydrationPolicy varification failed";
  v14 = 0;
LABEL_330:
  v10 = v126;
LABEL_331:
  v148 = v13;
  v149 = a4;
  TlmLogApiReliability(9, 0, v140, (_DWORD)String2, v7, UnbiasedTime, (__int64)v147, v11);
  if ( v14 )
  {
    v121 = GetProcessHeap();
    HeapFree(v121, 0, v14);
  }
  v122 = hObject;
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v8 )
  {
    v123 = GetProcessHeap();
    HeapFree(v123, 0, v8);
  }
  LOBYTE(v122) = v10;
  RtlSetThreadPlaceholderCompatibilityMode(v122);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800064e0  push    rbp
0x1800064e2  push    rbx
0x1800064e3  push    rsi
0x1800064e4  push    rdi
0x1800064e5  push    r12
0x1800064e7  push    r13
0x1800064e9  push    r14
0x1800064eb  push    r15
0x1800064ed  lea     rbp, [rsp-58h]
0x1800064f2  sub     rsp, 158h
0x1800064f9  mov     rax, cs:__security_cookie
0x180006500  xor     rax, rsp
0x180006503  mov     [rbp+90h+var_50], rax
0x180006507  xor     r13d, r13d
0x18000650a  mov     qword ptr [rbp+90h+pbOutput], rdx
0x18000650e  mov     r14, r8
0x180006511  mov     [rbp+90h+var_F0], rcx
0x180006515  mov     rbx, rdx
0x180006518  mov     [rsp+190h+var_120], r9d
0x18000651d  mov     rsi, rcx
0x180006520  mov     [rbp+90h+hObject], 0FFFFFFFFFFFFFFFFh
0x180006528  lea     r8d, [r13+58h]; Size
0x18000652c  mov     [rsp+190h+String2], r13
0x180006531  xor     edx, edx; Val
0x180006533  mov     dword ptr [rbp+90h+var_108], r13d
0x180006537  lea     rcx, [rbp+90h+var_C0]; void *
0x18000653b  mov     [rbp+90h+UnbiasedTime], r13
0x18000653f  mov     r12d, r13d
0x180006542  mov     r15d, r13d
0x180006545  call    memset_0
0x18000654a  mov     cl, 2
0x18000654c  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x180006553  nop     dword ptr [rax+rax+00h]
0x180006558  lea     rcx, [rbp+90h+UnbiasedTime]; UnbiasedTime
0x18000655c  mov     [rsp+190h+var_140], al
0x180006560  mov     dil, al
0x180006563  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000656a  nop     dword ptr [rax+rax+00h]
0x18000656f  mov     rcx, rsi
0x180006572  lea     edx, [r13+57h]
0x180006576  neg     rcx
0x180006579  sbb     esi, esi
0x18000657b  not     esi
0x18000657d  and     esi, edx
0x18000657f  mov     ecx, esi
0x180006581  or      ecx, 80070000h
0x180006587  cmp     [rbp+90h+var_F0], r13
0x18000658b  cmovz   esi, ecx
0x18000658e  test    esi, esi
0x180006590  jz      short loc_1800065BE
0x180006592  mov     r9d, esi
0x180006595  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x18000659c  mov     edx, 5DAh
0x1800065a1  call    TlmChk
0x1800065a6  test    esi, esi
0x1800065a8  jns     short loc_1800065B9
0x1800065aa  lea     rax, aSyncrootpathIs; "SyncRootPath is NULL"
0x1800065b1  mov     rbx, r13
0x1800065b4  jmp     loc_1800077F9
0x1800065b9  mov     edx, 57h ; 'W'
0x1800065be  mov     rax, rbx
0x1800065c1  neg     rax
0x1800065c4  sbb     esi, esi
0x1800065c6  not     esi
0x1800065c8  and     esi, edx
0x1800065ca  mov     eax, esi
0x1800065cc  or      eax, 80070000h
0x1800065d1  test    rbx, rbx
0x1800065d4  cmovz   esi, eax
0x1800065d7  test    esi, esi
0x1800065d9  jz      short loc_180006601
0x1800065db  mov     r9d, esi
0x1800065de  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x1800065e5  mov     edx, 5DBh
0x1800065ea  call    TlmChk
0x1800065ef  test    esi, esi
0x1800065f1  jns     short loc_1800065FC
0x1800065f3  lea     rax, aRegistrationIs; "Registration is NULL"
0x1800065fa  jmp     short loc_1800065B1
0x1800065fc  mov     edx, 57h ; 'W'
0x180006601  mov     rax, [rbx+8]
0x180006605  neg     rax
0x180006608  sbb     esi, esi
0x18000660a  not     esi
0x18000660c  and     esi, edx
0x18000660e  mov     eax, esi
0x180006610  or      eax, 80070000h
0x180006615  cmp     [rbx+8], r13
0x180006619  cmovz   esi, eax
0x18000661c  test    esi, esi
0x18000661e  jz      short loc_180006649
0x180006620  mov     r9d, esi
0x180006623  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x18000662a  mov     edx, 5DCh
0x18000662f  call    TlmChk
0x180006634  test    esi, esi
0x180006636  jns     short loc_180006644
0x180006638  lea     rax, aProvidernameIs; "ProviderName is NULL"
0x18000663f  jmp     loc_1800065B1
0x180006644  mov     edx, 57h ; 'W'
0x180006649  mov     rax, [rbx+10h]
0x18000664d  neg     rax
0x180006650  sbb     esi, esi
0x180006652  not     esi
0x180006654  and     esi, edx
0x180006656  mov     eax, esi
0x180006658  or      eax, 80070000h
0x18000665d  cmp     [rbx+10h], r13
0x180006661  cmovz   esi, eax
0x180006664  test    esi, esi
0x180006666  jz      short loc_180006691
0x180006668  mov     r9d, esi
0x18000666b  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006672  mov     edx, 5DDh
0x180006677  call    TlmChk
0x18000667c  test    esi, esi
0x18000667e  jns     short loc_18000668C
0x180006680  lea     rax, aProviderversio; "ProviderVersion is NULL"
0x180006687  jmp     loc_1800065B1
0x18000668c  mov     edx, 57h ; 'W'
0x180006691  cmp     [rbx+18h], r13
0x180006695  jz      short loc_18000669F
0x180006697  mov     esi, edx
0x180006699  cmp     [rbx+20h], r13d
0x18000669d  jz      short loc_1800066A2
0x18000669f  mov     esi, r13d
0x1800066a2  mov     eax, esi
0x1800066a4  or      eax, 80070000h
0x1800066a9  test    esi, esi
0x1800066ab  cmovnz  esi, eax
0x1800066ae  test    esi, esi
0x1800066b0  jz      short loc_1800066D6
0x1800066b2  mov     r9d, esi
0x1800066b5  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x1800066bc  mov     edx, 5E1h
0x1800066c1  call    TlmChk
0x1800066c6  test    esi, esi
0x1800066c8  jns     short loc_1800066D6
0x1800066ca  lea     rax, aInvalidSyncroo; "Invalid SyncRootIdentity"
0x1800066d1  jmp     loc_1800065B1
0x1800066d6  cmp     [rbx+28h], r13
0x1800066da  jz      short loc_1800066E7
0x1800066dc  mov     esi, 57h ; 'W'
0x1800066e1  cmp     [rbx+30h], r13d
0x1800066e5  jz      short loc_1800066EA
0x1800066e7  mov     esi, r13d
0x1800066ea  mov     eax, esi
0x1800066ec  or      eax, 80070000h
0x1800066f1  test    esi, esi
0x1800066f3  cmovnz  esi, eax
0x1800066f6  test    esi, esi
0x1800066f8  jz      short loc_18000671E
0x1800066fa  mov     r9d, esi
0x1800066fd  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006704  mov     edx, 5E5h
0x180006709  call    TlmChk
0x18000670e  test    esi, esi
0x180006710  jns     short loc_18000671E
0x180006712  lea     rax, aInvalidFileide; "Invalid FileIdentity"
0x180006719  jmp     loc_1800065B1
0x18000671e  mov     rax, r14
0x180006721  neg     rax
0x180006724  sbb     esi, esi
0x180006726  not     esi
0x180006728  and     esi, 57h
0x18000672b  mov     eax, esi
0x18000672d  or      eax, 80070000h
0x180006732  test    r14, r14
0x180006735  cmovz   esi, eax
0x180006738  test    esi, esi
0x18000673a  jz      short loc_180006760
0x18000673c  mov     r9d, esi
0x18000673f  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006746  mov     edx, 5E7h
0x18000674b  call    TlmChk
0x180006750  test    esi, esi
0x180006752  jns     short loc_180006760
0x180006754  lea     rax, aPoliciesCanTBe; "Policies can't be NULL"
0x18000675b  jmp     loc_1800065B1
0x180006760  cmp     dword ptr [r14], 14h
0x180006764  sbb     esi, esi
0x180006766  and     esi, 57h
0x180006769  mov     eax, esi
0x18000676b  or      eax, 80070000h
0x180006770  cmp     dword ptr [r14], 14h
0x180006774  cmovb   esi, eax
0x180006777  test    esi, esi
0x180006779  jz      short loc_18000679F
0x18000677b  mov     r9d, esi
0x18000677e  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006785  mov     edx, 5EBh
0x18000678a  call    TlmChk
0x18000678f  test    esi, esi
0x180006791  jns     short loc_18000679F
0x180006793  lea     rax, aStructsizeLess; "StructSize lesser than PlaceholderManag"...
0x18000679a  jmp     loc_1800065B1
0x18000679f  mov     ecx, 1000h
0x1800067a4  cmp     ecx, [rbx+20h]
0x1800067a7  sbb     esi, esi
0x1800067a9  and     esi, 57h
0x1800067ac  mov     eax, esi
0x1800067ae  or      eax, 80070000h
0x1800067b3  cmp     [rbx+20h], ecx
0x1800067b6  cmova   esi, eax
0x1800067b9  test    esi, esi
0x1800067bb  jz      short loc_1800067E1
0x1800067bd  mov     r9d, esi
0x1800067c0  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x1800067c7  mov     edx, 5EFh
0x1800067cc  call    TlmChk
0x1800067d1  test    esi, esi
0x1800067d3  jns     short loc_1800067E1
0x1800067d5  lea     rax, aSyncrootidenti_1; "SyncRootIdentityLength invalid"
0x1800067dc  jmp     loc_1800065B1
0x1800067e1  cmp     dword ptr [r14], 14h
0x1800067e5  mov     rax, [rbx+28h]
0x1800067e9  mov     r8, [rbx+8]
0x1800067ed  mov     r12, [rbx+10h]
0x1800067f1  mov     rdx, [rbx+18h]
0x1800067f5  mov     r13d, [rbx+20h]
0x1800067f9  mov     edi, [r14+8]
0x1800067fd  mov     [rbp+90h+var_C8], rax
0x180006801  mov     eax, [rbx+30h]
0x180006804  mov     ebx, [r14+4]
0x180006808  mov     dword ptr [rbp+90h+Size+4], eax
0x18000680b  mov     eax, [r14+0Ch]
0x18000680f  mov     dword ptr [rbp+90h+var_108+4], eax
0x180006812  mov     [rsp+190h+String2], r8
0x180006817  mov     [rsp+190h+Source], r12
0x18000681c  mov     [rbp+90h+Src], rdx
0x180006820  mov     dword ptr [rbp+90h+Size], r13d
0x180006824  mov     [rbp+90h+Buf2], ebx
0x180006827  mov     [rbp+90h+var_E4], edi
0x18000682a  jb      short loc_18000684F
0x18000682c  cmp     dword ptr [r14], 18h
0x180006830  mov     eax, [r14+10h]
0x180006834  mov     [rsp+190h+var_124], eax
0x180006838  jb      short loc_180006846
0x18000683a  mov     ecx, [r14+14h]
0x18000683e  xor     r14d, r14d
0x180006841  mov     [rbp+90h+var_10C], ecx
0x180006844  jmp     short loc_18000685B
0x180006846  mov     [rsp+190h+var_124], eax
0x18000684a  xor     r14d, r14d
0x18000684d  jmp     short loc_180006857
0x18000684f  xor     r14d, r14d
0x180006852  mov     [rsp+190h+var_124], r14d
0x180006857  mov     [rbp+90h+var_10C], r14d
0x18000685b  mov     eax, ebx
0x18000685d  mov     ecx, 2
0x180006862  shr     eax, 10h
0x180006865  test    cl, al
0x180006867  jz      short loc_180006870
0x180006869  lea     esi, [rcx+55h]
0x18000686c  test    al, 1
0x18000686e  jnz     short loc_180006873
0x180006870  mov     esi, r14d
0x180006873  mov     eax, esi
0x180006875  or      eax, 80070000h
0x18000687a  test    esi, esi
0x18000687c  cmovnz  esi, eax
0x18000687f  test    esi, esi
0x180006881  jz      short loc_1800068AF
0x180006883  mov     r9d, esi
0x180006886  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x18000688d  mov     edx, 609h
0x180006892  call    TlmChk
0x180006897  test    esi, esi
0x180006899  jns     short loc_1800068AA
0x18000689b  lea     rax, aHydrationpolic; "hydrationPolicy varification failed"
0x1800068a2  mov     rbx, r15
0x1800068a5  jmp     loc_1800077F4
0x1800068aa  mov     r8, [rsp+190h+String2]
0x1800068af  test    r8, r8
0x1800068b2  jnz     short loc_1800068B9
0x1800068b4  mov     rax, r14
0x1800068b7  jmp     short loc_1800068CD
0x1800068b9  mov     edx, 0FFh; MaxCount
0x1800068be  mov     rcx, r8; Source
0x1800068c1  call    cs:__imp_wcsnlen
0x1800068c8  nop     dword ptr [rax+rax+00h]
0x1800068cd  lea     r12d, ds:2[rax*2]
0x1800068d5  mov     rax, [rsp+190h+Source]
0x1800068da  mov     [rbp+90h+cbInput], r12d
0x1800068de  test    rax, rax
0x1800068e1  jz      short loc_1800068FA
0x1800068e3  mov     edx, 0FFh; MaxCount
0x1800068e8  mov     rcx, rax; Source
0x1800068eb  call    cs:__imp_wcsnlen
0x1800068f2  nop     dword ptr [rax+rax+00h]
0x1800068f7  mov     r14, rax
0x1800068fa  xor     edx, edx
0x1800068fc  mov     esi, edx
0x1800068fe  lea     r8d, [rdx+2]
0x180006902  cmp     r12d, r8d
0x180006905  lea     eax, [rdx+57h]
0x180006908  cmovbe  esi, eax
0x18000690b  mov     ecx, esi
0x18000690d  or      ecx, 80070000h
0x180006913  cmp     r12d, r8d
  ... truncated ...
```
