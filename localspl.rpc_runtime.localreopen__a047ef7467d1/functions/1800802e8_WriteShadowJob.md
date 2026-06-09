# WriteShadowJob

- ea: `0x1800802e8`
- end: `0x180080c85`
- name: `WriteShadowJob`
- size: `2461`
- prototype: `__int64 __fastcall(INIJOB *this)`
- caller_count: `9`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005c9a0`
- `0x18005cf84`
- `0x18005ea34`
- `0x18005ee94`
- `0x18005f220`
- `0x18005fc30`
- `0x1800632bc`
- `0x180067628`
- `0x180088860`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18000d0d8`
- `0x18000eaf0`
- `0x180011ed0`
- `0x1800237d8`
- `0x18002fb3c`
- `0x180046650`
- `0x180047318`
- `0x180047330`
- `0x180054638`
- `0x18005e534`
- `0x180072a40`
- `0x1800802e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c04`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180080bbc`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180080bbc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180080a58`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180080a58`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180080b13`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180080b13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080b8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080b8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080baa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080baa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080b5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080b5b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008045b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008045b`
- `SPOOLSS!DllFreeSplMem` at `0x180080bee`
- `SPOOLSS!DllFreeSplMem` at `0x180080bee`
- `SPOOLSS!DllAllocSplMem` at `0x180080799`
- `SPOOLSS!DllAllocSplMem` at `0x180080799`
- `SPOOLSS!RevertToPrinterSelf` at `0x180080a28`
- `SPOOLSS!RevertToPrinterSelf` at `0x180080a28`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180080a8f`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180080a8f`

## string_xrefs

- `0x180080761`: `WriteShadowJob`
- `0x1800807b7`: `WriteShadowJob`
- `0x180080a7c`: `WriteShadowJob`
- `0x180080aa2`: `WriteShadowJob`
- `0x180080ae9`: `WriteShadowJob`
- `0x180080bd8`: `WriteShadowJob`
- `0x180080c21`: `WriteShadowJob`
- `0x18008077e`: `Overflow in shadow file creation when adding space for security descriptor`
- `0x180080a9b`: `Failed to impersonate client`
- `0x180080bd1`: `WriteFile for shadow file failed.  Error %d`
- `0x180080ae2`: `Failed to open shadow file %ws. Error %d`

## pseudocode

```c
__int64 __fastcall WriteShadowJob(INIJOB *this)
{
  int v1; // r13d
  unsigned __int64 v3; // rbx
  unsigned int v4; // edi
  void *v5; // r9
  __int128 v6; // xmm0
  void *v7; // rcx
  __int64 v8; // r10
  int v9; // edi
  DWORD SecurityDescriptorLength; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned __int64 v42; // r15
  _BYTE *v43; // r14
  DWORD LastError; // eax
  int v45; // edi
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  unsigned __int16 *v59; // rdx
  const void *v60; // rdx
  __int64 v61; // r9
  __int64 v62; // r9
  const unsigned __int16 *v63; // r9
  struct FileListItem *v64; // rbx
  int v65; // edx
  __int64 v66; // rcx
  __int64 v67; // rcx
  struct _SECURITY_ATTRIBUTES *v68; // r9
  HANDLE v69; // rdi
  int WriterFromHandle; // eax
  __int64 SafeFile; // rbx
  DWORD v72; // eax
  DWORD v73; // eax
  DWORD v74; // eax
  DWORD v75; // eax
  unsigned int lpOverlapped; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  int v81; // [rsp+3Ch] [rbp-C4h]
  int v82; // [rsp+40h] [rbp-C0h]
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v87; // [rsp+60h] [rbp-A0h]
  HANDLE hFile; // [rsp+68h] [rbp-98h] BYREF
  __int128 v89; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v90[2]; // [rsp+80h] [rbp-80h]
  unsigned __int64 v91[2]; // [rsp+90h] [rbp-70h]
  unsigned __int64 v92[2]; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v93[2]; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v94[2]; // [rsp+C0h] [rbp-40h]
  __m256i v95; // [rsp+D0h] [rbp-30h]
  size_t v96[2]; // [rsp+F0h] [rbp-10h]
  __int128 v97; // [rsp+100h] [rbp+0h]
  unsigned __int64 v98[2]; // [rsp+110h] [rbp+10h]
  unsigned __int64 v99[2]; // [rsp+120h] [rbp+20h]
  unsigned __int64 v100[2]; // [rsp+130h] [rbp+30h]
  __int128 v101; // [rsp+140h] [rbp+40h]
  unsigned __int16 v102[264]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v103[2048]; // [rsp+360h] [rbp+260h] BYREF

  v1 = 0;
  v3 = 224;
  NumberOfBytesWritten = 0;
  Type = 0;
  hFile = (HANDLE)-1LL;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  Src = 0;
  Size = 0;
  memset_0(&v89, 0, 0xE0u);
  memset_0(v103, 0, sizeof(v103));
  if ( (*((_DWORD *)this + 8) & 0x100) != 0
    || (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 280LL) + 168LL) & 0x1000) != 0
    || (*((_DWORD *)this + 8) & 0x40000000) != 0 )
  {
    v4 = 1;
    goto LABEL_136;
  }
  v4 = 0;
  if ( (unsigned int)INIJOB::GetSerializedBlobOfNamedProperties(this, (unsigned __int8 **)&Src, (unsigned int *)&Size) )
  {
    v5 = Src;
    v6 = *((_OWORD *)this + 9);
    v7 = (void *)*((_QWORD *)this + 33);
    v8 = (__int64)Src;
    v9 = Size;
    DWORD2(v89) = *((_DWORD *)this + 8);
    HIDWORD(v89) = *((_DWORD *)this + 10);
    LODWORD(v90[0]) = *((_DWORD *)this + 11);
    v95.m256i_i64[3] = *(_QWORD *)((char *)this + 164);
    LODWORD(v96[0]) = *((_DWORD *)this + 44);
    LODWORD(v99[0]) = *((_DWORD *)this + 82);
    LODWORD(v100[1]) = *((_DWORD *)this + 45);
    HIDWORD(v100[1]) = *((_DWORD *)this + 83);
    HIDWORD(v96[0]) = *((_DWORD *)this + 69);
    LODWORD(v98[0]) = *((_DWORD *)this + 81);
    *(_QWORD *)&v89 = 0xE000005123LL;
    HIDWORD(v97) = 4;
    LODWORD(v101) = Size;
    *((_QWORD *)&v101 + 1) = Src;
    *(_OWORD *)&v95.m256i_u64[1] = v6;
    if ( v7 )
    {
      SecurityDescriptorLength = GetSecurityDescriptorLength(v7);
      v5 = Src;
      v11 = SecurityDescriptorLength;
      v8 = *((_QWORD *)&v101 + 1);
      LODWORD(v96[1]) = SecurityDescriptorLength;
    }
    else
    {
      v11 = LODWORD(v96[1]);
    }
    LODWORD(v87) = 0;
    if ( v5 )
    {
      *((_QWORD *)&v101 + 1) = 224;
      v8 = 224;
      v87 = (v9 + 7) & 0xFFFFFFF8;
      if ( (unsigned __int64)(v87 + 224) < 0xE0 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "WriteShadowJob",
          L"Overflow in shadow file creation when adding space for named properties",
          v11);
        goto LABEL_82;
      }
      v3 = ((v9 + 7) & 0xFFFFFFF8) + 224LL;
    }
    v12 = *((_QWORD *)this + 13);
    if ( v12 )
    {
      v13 = *(unsigned __int16 *)(v12 + 70);
      v14 = *(unsigned __int16 *)(v12 + 68) + 7LL;
      v93[1] = v3;
      v15 = v3 + ((v13 + v14) & 0xFFFFFFFFFFFFFFF8uLL);
      if ( v15 < v3 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "WriteShadowJob",
          L"Overflow in shadow file creation when adding space for dev mode",
          v11);
        goto LABEL_82;
      }
      v3 = v15;
    }
    if ( *((_QWORD *)this + 33) )
    {
      *(_QWORD *)&v97 = v3;
      if ( v3 + (((unsigned int)v11 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) < v3 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "WriteShadowJob",
          L"Overflow in shadow file creation when adding space for security descriptor",
          v11);
        goto LABEL_82;
      }
      v3 += ((unsigned int)v11 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
    }
    v16 = *((_QWORD *)this + 6);
    DWORD2(v97) = *((_DWORD *)this + 76);
    if ( v16 )
    {
      v90[1] = v3;
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(v16 + 2 * v17) );
      if ( v3 + 2 * (v17 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v17 + 1);
    }
    v18 = *((_QWORD *)this + 7);
    if ( v18 )
    {
      v91[0] = v3;
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v18 + 2 * v19) );
      if ( v3 + 2 * (v19 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v19 + 1);
    }
    v20 = *((_QWORD *)this + 9);
    if ( v20 )
    {
      v91[1] = v3;
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(v20 + 2 * v21) );
      if ( v3 + 2 * (v21 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v21 + 1);
    }
    v22 = *((_QWORD *)this + 10);
    if ( v22 )
    {
      v92[0] = v3;
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(v22 + 2 * v23) );
      if ( v3 + 2 * (v23 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v23 + 1);
    }
    v24 = *(_QWORD *)(*((_QWORD *)this + 11) + 24LL);
    if ( v24 )
    {
      v92[1] = v3;
      v25 = -1;
      do
        ++v25;
      while ( *(_WORD *)(v24 + 2 * v25) );
      if ( v3 + 2 * (v25 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v25 + 1);
    }
    v26 = *((_QWORD *)this + 12);
    if ( v26 )
    {
      v27 = *(_QWORD *)(v26 + 24);
      if ( v27 )
      {
        v93[0] = v3;
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)(v27 + 2 * v28) );
        if ( v3 + 2 * (v28 + 1) < v3 )
          goto LABEL_82;
        v3 += 2 * (v28 + 1);
      }
    }
    v29 = *((_QWORD *)this + 14);
    if ( v29 )
    {
      v30 = *(_QWORD *)(v29 + 24);
      if ( v30 )
      {
        v94[0] = v3;
        v31 = -1;
        do
          ++v31;
        while ( *(_WORD *)(v30 + 2 * v31) );
        if ( v3 + 2 * (v31 + 1) < v3 )
          goto LABEL_82;
        v3 += 2 * (v31 + 1);
      }
    }
    v32 = *((_QWORD *)this + 16);
    if ( v32 )
    {
      v94[1] = v3;
      v33 = -1;
      do
        ++v33;
      while ( *(_WORD *)(v32 + 2 * v33) );
      if ( v3 + 2 * (v33 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v33 + 1);
    }
    v34 = *((_QWORD *)this + 17);
    if ( v34 )
    {
      v95.m256i_i64[0] = v3;
      v35 = -1;
      do
        ++v35;
      while ( *(_WORD *)(v34 + 2 * v35) );
      if ( v3 + 2 * (v35 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v35 + 1);
    }
    v36 = *((_QWORD *)this + 8);
    if ( v36 )
    {
      v98[1] = v3;
      v37 = -1;
      do
        ++v37;
      while ( *(_WORD *)(v36 + 2 * v37) );
      if ( v3 + 2 * (v37 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v37 + 1);
    }
    v38 = *((_QWORD *)this + 51);
    if ( v38 )
    {
      v99[1] = v3;
      v39 = -1;
      do
        ++v39;
      while ( *(_WORD *)(v38 + 2 * v39) );
      if ( v3 + 2 * (v39 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v39 + 1);
    }
    v40 = *((_QWORD *)this + 48);
    if ( v40 )
    {
      v100[0] = v3;
      v41 = -1;
      do
        ++v41;
      while ( *(_WORD *)(v40 + 2 * v41) );
      if ( v3 + 2 * (v41 + 1) < v3 )
        goto LABEL_82;
      v3 += 2 * (v41 + 1);
    }
    v42 = (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v42 < v3 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning("WriteShadowJob", L"ALIGN_UP overflow for cbSize", v11);
LABEL_82:
      v4 = 0;
      goto LABEL_136;
    }
    if ( v42 <= 0x800 )
    {
      v81 = 0;
      v43 = v103;
    }
    else
    {
      v43 = (_BYTE *)DllAllocSplMem((unsigned int)v42);
      if ( !v43 )
      {
        LastError = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "WriteShadowJob",
          L"Failed to allocate memory for shadow buffer.  Error %d",
          LastError);
        goto LABEL_82;
      }
      v5 = Src;
      v8 = *((_QWORD *)&v101 + 1);
      v81 = 1;
    }
    v45 = 1;
    v46 = *(_OWORD *)v90;
    v82 = 1;
    *(_OWORD *)v43 = v89;
    v47 = *(_OWORD *)v91;
    *((_OWORD *)v43 + 1) = v46;
    v48 = *(_OWORD *)v92;
    *((_OWORD *)v43 + 2) = v47;
    v49 = *(_OWORD *)v93;
    *((_OWORD *)v43 + 3) = v48;
    v50 = *(_OWORD *)v94;
    *((_OWORD *)v43 + 4) = v49;
    v51 = *(_OWORD *)v95.m256i_i8;
    *((_OWORD *)v43 + 5) = v50;
    v52 = *(_OWORD *)&v95.m256i_u64[2];
    *((_OWORD *)v43 + 6) = v51;
    v53 = *(_OWORD *)v96;
    *((_OWORD *)v43 + 7) = v52;
    v54 = v97;
    *((_OWORD *)v43 + 8) = v53;
    v55 = *(_OWORD *)v98;
    *((_OWORD *)v43 + 9) = v54;
    v56 = *(_OWORD *)v99;
    *((_OWORD *)v43 + 10) = v55;
    v57 = *(_OWORD *)v100;
    *((_OWORD *)v43 + 11) = v56;
    v58 = v101;
    *((_OWORD *)v43 + 12) = v57;
    *((_OWORD *)v43 + 13) = v58;
    if ( v5 && (unsigned int)Size <= (unsigned int)v87 )
      memcpy_0(&v43[v8], v5, (unsigned int)Size);
    v59 = (unsigned __int16 *)*((_QWORD *)this + 13);
    if ( v59 )
      memcpy_0(&v43[v93[1]], v59, v59[34] + (unsigned __int64)v59[35]);
    v60 = (const void *)*((_QWORD *)this + 33);
    if ( v60 )
      memcpy_0(&v43[v97], v60, LODWORD(v96[1]));
    CopyString(v43, v90[1], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 6));
    CopyString(v43, v91[0], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 7));
    CopyString(v43, v91[1], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 9));
    CopyString(v43, v92[0], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 10));
    CopyString(
      v43,
      v92[1],
      (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL,
      *(const unsigned __int16 **)(*((_QWORD *)this + 11) + 24LL));
    v61 = *((_QWORD *)this + 12);
    if ( v61 )
      CopyString(v43, v93[0], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *(const unsigned __int16 **)(v61 + 24));
    v62 = *((_QWORD *)this + 14);
    if ( v62 )
      CopyString(v43, v94[0], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *(const unsigned __int16 **)(v62 + 24));
    CopyString(v43, v94[1], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 16));
    v63 = (const unsigned __int16 *)*((_QWORD *)this + 17);
    if ( v63 )
      CopyString(v43, v95.m256i_u64[0], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, v63);
    CopyString(v43, v98[1], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 8));
    CopyString(v43, v99[1], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 51));
    CopyString(v43, v100[0], (v3 + 7) & 0xFFFFFFFFFFFFFFF8uLL, *((const unsigned __int16 **)this + 48));
    v64 = (struct FileListItem *)*((_QWORD *)this + 49);
    if ( v64 == (struct FileListItem *)-1LL )
    {
      v65 = *((_DWORD *)this + 10);
      v66 = *((_QWORD *)this + 11);
      v45 = 0;
      v82 = 0;
      GetFullNameFromId(v66, v65, 0, (unsigned int)v102, 260, 0);
    }
    SafeIncrementReference((unsigned int *)this + 6);
    LeaveSplSem(v67);
    if ( !v45 )
    {
      SafeFile = (__int64)InternalCreateSafeFile(v102, 0x40000000u, 1u, v68, lpOverlapped, lpcbData);
      if ( SafeFile != -1 )
        v1 = 1;
      goto LABEL_115;
    }
    v69 = RevertToPrinterSelf();
    WriterFromHandle = GetWriterFromHandle(v64, &hFile, 0);
    if ( WriterFromHandle < 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "WriteShadowJob",
        L"Failed to get file handle from pool item.  Error hr: 0x%x",
        (unsigned int)WriterFromHandle);
    }
    else
    {
      SafeFile = (__int64)hFile;
      v1 = 1;
      if ( SetFilePointer(hFile, 0, 0, 0) != -1 )
        goto LABEL_111;
      v72 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "WriteShadowJob",
        L"Failed to set File pointer for shadow file. Error %d",
        v72);
    }
    SafeFile = -1;
LABEL_111:
    v4 = ImpersonatePrinterClient(v69);
    if ( !v4 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning("WriteShadowJob", L"Failed to impersonate client");
LABEL_127:
      if ( v81 )
        DllFreeSplMem(v43);
      if ( !v82 && SafeFile != -1 && !CloseHandle((HANDLE)SafeFile) )
      {
        v75 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "WriteShadowJob",
          L"Failed to close shadow file handle %p.  Error %d",
          SafeFile,
          v75);
      }
      EnterSplSem(0);
      SafeDecrementReference((unsigned int *)this + 6);
      if ( v1 )
        INIJOB::ClearJobStatusFlags(this, 0x40000000u);
      goto LABEL_136;
    }
LABEL_115:
    if ( SafeFile == -1 )
    {
      v73 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "WriteShadowJob",
        L"Failed to open shadow file %ws. Error %d",
        v102,
        v73);
      v4 = 0;
    }
    else
    {
      v4 = WriteFile((HANDLE)SafeFile, v43, v42, &NumberOfBytesWritten, 0);
      if ( !dwFlushShadowFileBuffers )
      {
        dwFlushShadowFileBuffers = 2;
        HIDWORD(Size) = 4;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print", 0, 0x20019u, &phkResult) )
        {
          if ( !RegQueryValueExW(phkResult, L"FlushShadowFileBuffers", 0, &Type, Data, (LPDWORD)&Size + 1)
            && *(_DWORD *)Data == 1 )
          {
            dwFlushShadowFileBuffers = 1;
          }
          RegCloseKey(phkResult);
        }
      }
      if ( dwFlushShadowFileBuffers == 1 )
        v4 = FlushFileBuffers((HANDLE)SafeFile);
      if ( !v4 )
      {
        v74 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "WriteShadowJob",
          L"WriteFile for shadow file failed.  Error %d",
          v74);
      }
    }
    goto LABEL_127;
  }
LABEL_136:
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&Src);
  return v4;
}

```

## disassembly

```asm
0x1800802e8  push    rbp
0x1800802ea  push    rbx
0x1800802eb  push    rsi
0x1800802ec  push    rdi
0x1800802ed  push    r12
0x1800802ef  push    r13
0x1800802f1  push    r14
0x1800802f3  push    r15
0x1800802f5  lea     rbp, [rsp-0A78h]
0x1800802fd  sub     rsp, 0B78h
0x180080304  mov     rax, cs:__security_cookie
0x18008030b  xor     rax, rsp
0x18008030e  mov     [rbp+0AB0h+var_50], rax
0x180080315  xor     r13d, r13d
0x180080318  mov     rsi, rcx
0x18008031b  mov     ebx, 0E0h
0x180080320  mov     [rsp+0BB0h+NumberOfBytesWritten], r13d
0x180080325  or      r14, 0FFFFFFFFFFFFFFFFh
0x180080329  mov     [rsp+0BB0h+Type], r13d
0x18008032e  mov     r8d, ebx; Size
0x180080331  mov     [rsp+0BB0h+hFile], r14
0x180080336  xor     edx, edx; Val
0x180080338  mov     dword ptr [rsp+0BB0h+Data], r13d
0x18008033d  lea     rcx, [rsp+0BB0h+var_B40]; void *
0x180080342  mov     dword ptr [rsp+0BB0h+Size+4], r13d
0x180080347  mov     [rsp+0BB0h+phkResult], r13
0x18008034c  mov     [rsp+0BB0h+Src], r13
0x180080351  mov     dword ptr [rsp+0BB0h+Size], r13d
0x180080356  call    memset_0
0x18008035b  xor     edx, edx; Val
0x18008035d  lea     rcx, [rbp+0AB0h+var_850]; void *
0x180080364  mov     r8d, 800h; Size
0x18008036a  call    memset_0
0x18008036f  test    dword ptr [rsi+20h], 100h
0x180080376  jnz     loc_180080C51
0x18008037c  mov     rax, [rsi+58h]
0x180080380  mov     rcx, [rax+118h]
0x180080387  test    dword ptr [rcx+0A8h], 1000h
0x180080391  jnz     loc_180080C51
0x180080397  test    dword ptr [rsi+20h], 40000000h
0x18008039e  jnz     loc_180080C51
0x1800803a4  lea     r8, [rsp+0BB0h+Size]; unsigned int *
0x1800803a9  mov     rcx, rsi; this
0x1800803ac  lea     rdx, [rsp+0BB0h+Src]; unsigned __int8 **
0x1800803b1  mov     edi, r13d
0x1800803b4  call    ?GetSerializedBlobOfNamedProperties@INIJOB@@QEAAHPEAPEAEPEAK@Z; INIJOB::GetSerializedBlobOfNamedProperties(uchar * *,ulong *)
0x1800803b9  test    eax, eax
0x1800803bb  jz      loc_180080C56
0x1800803c1  mov     eax, [rsi+20h]
0x1800803c4  mov     r9, [rsp+0BB0h+Src]
0x1800803c9  movups  xmm0, xmmword ptr [rsi+90h]
0x1800803d0  mov     rcx, [rsi+108h]; pSecurityDescriptor
0x1800803d7  mov     r10, r9
0x1800803da  mov     edi, dword ptr [rsp+0BB0h+Size]
0x1800803de  mov     dword ptr [rsp+0BB0h+var_B40+8], eax
0x1800803e2  mov     eax, [rsi+28h]
0x1800803e5  mov     dword ptr [rsp+0BB0h+var_B40+0Ch], eax
0x1800803e9  mov     eax, [rsi+2Ch]
0x1800803ec  mov     dword ptr [rbp+0AB0h+var_B30], eax
0x1800803ef  mov     eax, [rsi+0A4h]
0x1800803f5  mov     [rbp+0AB0h+var_AC8], eax
0x1800803f8  mov     eax, [rsi+0A8h]
0x1800803fe  mov     [rbp+0AB0h+var_AC4], eax
0x180080401  mov     eax, [rsi+0B0h]
0x180080407  mov     dword ptr [rbp+0AB0h+var_AC0], eax
0x18008040a  mov     eax, [rsi+148h]
0x180080410  mov     dword ptr [rbp+0AB0h+var_A90], eax
0x180080413  mov     eax, [rsi+0B4h]
0x180080419  mov     dword ptr [rbp+0AB0h+var_A80+8], eax
0x18008041c  mov     eax, [rsi+14Ch]
0x180080422  mov     dword ptr [rbp+0AB0h+var_A80+0Ch], eax
0x180080425  mov     eax, [rsi+114h]
0x18008042b  mov     dword ptr [rbp+0AB0h+var_AC0+4], eax
0x18008042e  mov     eax, [rsi+144h]
0x180080434  mov     dword ptr [rbp+0AB0h+var_AA0], eax
0x180080437  mov     dword ptr [rsp+0BB0h+var_B40], 5123h
0x18008043f  mov     dword ptr [rsp+0BB0h+var_B40+4], ebx
0x180080443  mov     dword ptr [rbp+0AB0h+var_AB0+0Ch], 4
0x18008044a  mov     dword ptr [rbp+0AB0h+var_A70], edi
0x18008044d  mov     qword ptr [rbp+0AB0h+var_A70+8], r9
0x180080451  movdqu  xmmword ptr [rbp+0AB0h+var_AE0+8], xmm0
0x180080456  test    rcx, rcx
0x180080459  jz      short loc_180080472
0x18008045b  call    cs:__imp_GetSecurityDescriptorLength
0x180080461  mov     r9, [rsp+0BB0h+Src]
0x180080466  mov     r8d, eax
0x180080469  mov     r10, qword ptr [rbp+0AB0h+var_A70+8]
0x18008046d  mov     dword ptr [rbp+0AB0h+var_AC0+8], eax
0x180080470  jmp     short loc_180080476
0x180080472  mov     r8d, dword ptr [rbp+0AB0h+var_AC0+8]
0x180080476  mov     dword ptr [rsp+0BB0h+var_B50], r13d
0x18008047b  test    r9, r9
0x18008047e  jz      short loc_1800804A3
0x180080480  lea     eax, [rdi+7]
0x180080483  mov     qword ptr [rbp+0AB0h+var_A70+8], rbx
0x180080487  and     eax, 0FFFFFFF8h
0x18008048a  mov     r10, rbx
0x18008048d  mov     ecx, eax
0x18008048f  add     rax, rbx
0x180080492  mov     [rsp+0BB0h+var_B50], rcx
0x180080497  cmp     rax, rbx
0x18008049a  jb      loc_18008075A
0x1800804a0  mov     rbx, rax
0x1800804a3  mov     rax, [rsi+68h]
0x1800804a7  test    rax, rax
0x1800804aa  jz      short loc_1800804D2
0x1800804ac  movzx   ecx, word ptr [rax+46h]
0x1800804b0  movzx   eax, word ptr [rax+44h]
0x1800804b4  add     rax, 7
0x1800804b8  mov     [rbp+0AB0h+var_B00+8], rbx
0x1800804bc  add     rax, rcx
0x1800804bf  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800804c3  add     rax, rbx
0x1800804c6  cmp     rax, rbx
0x1800804c9  jb      loc_180080775
0x1800804cf  mov     rbx, rax
0x1800804d2  cmp     [rsi+108h], r13
0x1800804d9  jz      short loc_1800804F9
0x1800804db  mov     ecx, r8d
0x1800804de  add     rcx, 7
0x1800804e2  mov     qword ptr [rbp+0AB0h+var_AB0], rbx
0x1800804e6  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800804ea  add     rcx, rbx
0x1800804ed  cmp     rcx, rbx
0x1800804f0  jb      loc_18008077E
0x1800804f6  mov     rbx, rcx
0x1800804f9  mov     rcx, [rsi+30h]
0x1800804fd  mov     eax, [rsi+130h]
0x180080503  mov     dword ptr [rbp+0AB0h+var_AB0+8], eax
0x180080506  test    rcx, rcx
0x180080509  jz      short loc_180080530
0x18008050b  mov     [rbp+0AB0h+var_B30+8], rbx
0x18008050f  mov     rax, r14
0x180080512  inc     rax
0x180080515  cmp     [rcx+rax*2], r13w
0x18008051a  jnz     short loc_180080512
0x18008051c  lea     rcx, [rax+1]
0x180080520  lea     rcx, [rbx+rcx*2]
0x180080524  cmp     rcx, rbx
0x180080527  jb      loc_18008076D
0x18008052d  mov     rbx, rcx
0x180080530  mov     rcx, [rsi+38h]
0x180080534  test    rcx, rcx
0x180080537  jz      short loc_18008055E
0x180080539  mov     [rbp+0AB0h+var_B20], rbx
0x18008053d  mov     rax, r14
0x180080540  inc     rax
0x180080543  cmp     [rcx+rax*2], r13w
0x180080548  jnz     short loc_180080540
0x18008054a  lea     rcx, [rax+1]
0x18008054e  lea     rcx, [rbx+rcx*2]
0x180080552  cmp     rcx, rbx
0x180080555  jb      loc_18008076D
0x18008055b  mov     rbx, rcx
0x18008055e  mov     rcx, [rsi+48h]
0x180080562  test    rcx, rcx
0x180080565  jz      short loc_18008058C
0x180080567  mov     [rbp+0AB0h+var_B20+8], rbx
0x18008056b  mov     rax, r14
0x18008056e  inc     rax
0x180080571  cmp     [rcx+rax*2], r13w
0x180080576  jnz     short loc_18008056E
0x180080578  lea     rcx, [rax+1]
0x18008057c  lea     rcx, [rbx+rcx*2]
0x180080580  cmp     rcx, rbx
0x180080583  jb      loc_18008076D
0x180080589  mov     rbx, rcx
0x18008058c  mov     rcx, [rsi+50h]
0x180080590  test    rcx, rcx
0x180080593  jz      short loc_1800805BA
0x180080595  mov     [rbp+0AB0h+var_B10], rbx
0x180080599  mov     rax, r14
0x18008059c  inc     rax
0x18008059f  cmp     [rcx+rax*2], r13w
0x1800805a4  jnz     short loc_18008059C
0x1800805a6  lea     rcx, [rax+1]
0x1800805aa  lea     rcx, [rbx+rcx*2]
0x1800805ae  cmp     rcx, rbx
0x1800805b1  jb      loc_18008076D
0x1800805b7  mov     rbx, rcx
0x1800805ba  mov     rax, [rsi+58h]
0x1800805be  mov     rcx, [rax+18h]
0x1800805c2  test    rcx, rcx
0x1800805c5  jz      short loc_1800805EC
0x1800805c7  mov     [rbp+0AB0h+var_B10+8], rbx
0x1800805cb  mov     rax, r14
0x1800805ce  inc     rax
0x1800805d1  cmp     [rcx+rax*2], r13w
0x1800805d6  jnz     short loc_1800805CE
0x1800805d8  lea     rcx, [rax+1]
0x1800805dc  lea     rcx, [rbx+rcx*2]
0x1800805e0  cmp     rcx, rbx
0x1800805e3  jb      loc_18008076D
0x1800805e9  mov     rbx, rcx
0x1800805ec  mov     rax, [rsi+60h]
0x1800805f0  test    rax, rax
0x1800805f3  jz      short loc_180080623
0x1800805f5  mov     rcx, [rax+18h]
0x1800805f9  test    rcx, rcx
0x1800805fc  jz      short loc_180080623
0x1800805fe  mov     [rbp+0AB0h+var_B00], rbx
0x180080602  mov     rax, r14
0x180080605  inc     rax
0x180080608  cmp     [rcx+rax*2], r13w
0x18008060d  jnz     short loc_180080605
0x18008060f  lea     rcx, [rax+1]
0x180080613  lea     rcx, [rbx+rcx*2]
0x180080617  cmp     rcx, rbx
0x18008061a  jb      loc_18008076D
0x180080620  mov     rbx, rcx
0x180080623  mov     rax, [rsi+70h]
0x180080627  test    rax, rax
0x18008062a  jz      short loc_18008065A
0x18008062c  mov     rcx, [rax+18h]
0x180080630  test    rcx, rcx
0x180080633  jz      short loc_18008065A
0x180080635  mov     [rbp+0AB0h+var_AF0], rbx
0x180080639  mov     rax, r14
0x18008063c  inc     rax
0x18008063f  cmp     [rcx+rax*2], r13w
0x180080644  jnz     short loc_18008063C
0x180080646  lea     rcx, [rax+1]
0x18008064a  lea     rcx, [rbx+rcx*2]
0x18008064e  cmp     rcx, rbx
0x180080651  jb      loc_18008076D
0x180080657  mov     rbx, rcx
0x18008065a  mov     rcx, [rsi+80h]
0x180080661  test    rcx, rcx
0x180080664  jz      short loc_18008068B
0x180080666  mov     [rbp+0AB0h+var_AF0+8], rbx
0x18008066a  mov     rax, r14
0x18008066d  inc     rax
0x180080670  cmp     [rcx+rax*2], r13w
0x180080675  jnz     short loc_18008066D
0x180080677  lea     rcx, [rax+1]
0x18008067b  lea     rcx, [rbx+rcx*2]
0x18008067f  cmp     rcx, rbx
0x180080682  jb      loc_18008076D
0x180080688  mov     rbx, rcx
0x18008068b  mov     rcx, [rsi+88h]
0x180080692  test    rcx, rcx
0x180080695  jz      short loc_1800806BC
0x180080697  mov     [rbp+0AB0h+var_AE0], rbx
0x18008069b  mov     rax, r14
0x18008069e  inc     rax
0x1800806a1  cmp     [rcx+rax*2], r13w
0x1800806a6  jnz     short loc_18008069E
0x1800806a8  lea     rcx, [rax+1]
0x1800806ac  lea     rcx, [rbx+rcx*2]
0x1800806b0  cmp     rcx, rbx
0x1800806b3  jb      loc_18008076D
0x1800806b9  mov     rbx, rcx
0x1800806bc  mov     rcx, [rsi+40h]
0x1800806c0  test    rcx, rcx
0x1800806c3  jz      short loc_1800806EA
0x1800806c5  mov     [rbp+0AB0h+var_AA0+8], rbx
0x1800806c9  mov     rax, r14
0x1800806cc  inc     rax
0x1800806cf  cmp     [rcx+rax*2], r13w
0x1800806d4  jnz     short loc_1800806CC
0x1800806d6  lea     rcx, [rax+1]
0x1800806da  lea     rcx, [rbx+rcx*2]
0x1800806de  cmp     rcx, rbx
0x1800806e1  jb      loc_18008076D
0x1800806e7  mov     rbx, rcx
0x1800806ea  mov     rcx, [rsi+198h]
0x1800806f1  test    rcx, rcx
0x1800806f4  jz      short loc_180080717
0x1800806f6  mov     [rbp+0AB0h+var_A90+8], rbx
0x1800806fa  mov     rax, r14
0x1800806fd  inc     rax
0x180080700  cmp     [rcx+rax*2], r13w
0x180080705  jnz     short loc_1800806FD
0x180080707  lea     rcx, [rax+1]
0x18008070b  lea     rcx, [rbx+rcx*2]
0x18008070f  cmp     rcx, rbx
0x180080712  jb      short loc_18008076D
0x180080714  mov     rbx, rcx
0x180080717  mov     rcx, [rsi+180h]
0x18008071e  test    rcx, rcx
0x180080721  jz      short loc_180080744
0x180080723  mov     [rbp+0AB0h+var_A80], rbx
0x180080727  mov     rax, r14
0x18008072a  inc     rax
0x18008072d  cmp     [rcx+rax*2], r13w
0x180080732  jnz     short loc_18008072A
0x180080734  lea     rcx, [rax+1]
0x180080738  lea     rcx, [rbx+rcx*2]
0x18008073c  cmp     rcx, rbx
0x18008073f  jb      short loc_18008076D
0x180080741  mov     rbx, rcx
0x180080744  lea     r15, [rbx+7]
0x180080748  and     r15, 0FFFFFFFFFFFFFFF8h
0x18008074c  cmp     r15, rbx
0x18008074f  jnb     short loc_180080787
0x180080751  lea     rdx, aAlignUpOverflo; "ALIGN_UP overflow for cbSize"
0x180080758  jmp     short loc_180080761
0x18008075a  lea     rdx, aOverflowInShad; "Overflow in shadow file creation when a"...
0x180080761  lea     rcx, aWriteshadowjob; "WriteShadowJob"
0x180080768  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
  ... truncated ...
```
