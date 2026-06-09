# CRunRetrim::RunOperation(void)

- ea: `0x18002f280`
- end: `0x180030599`
- name: `?RunOperation@CRunRetrim@@UEAAJXZ`
- size: `4889`
- prototype: `__int64 __fastcall(CRunRetrim *__hidden this)`
- caller_count: `0`
- callee_count: `34`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800010dc`
- `0x1800014bc`
- `0x180001bcc`
- `0x180001f18`
- `0x180006400`
- `0x18000ad50`
- `0x18000c644`
- `0x18000c794`
- `0x18000e168`
- `0x180010bc0`
- `0x1800140bc`
- `0x1800193a0`
- `0x18001a630`
- `0x18001c07c`
- `0x18001f22c`
- `0x18002a1d0`
- `0x18002d9a8`
- `0x18002dd8c`
- `0x18002dff0`
- `0x18002e1a4`
- `0x18002f280`
- `0x1800305a0`
- `0x180038064`
- `0x180038c3c`
- `0x1800397a8`
- `0x18004b73c`
- `0x180055874`
- `0x180056618`
- `0x180056704`
- `0x180056768`
- `0x1800567b8`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002f8f3`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002f8f3`
- `api-ms-win-core-file-l1-1-0!SetFileValidData` at `0x18002fa28`
- `api-ms-win-core-file-l1-1-0!SetFileValidData` at `0x18002fa28`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f8a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f936`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f8a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f936`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002faa9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002fb16`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002faa9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002fb16`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002fa8a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002faf9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002fa8a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002faf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002f3b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002f3b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fac5`
- `ntdll!NtFsControlFile` at `0x180030052`
- `ntdll!NtFsControlFile` at `0x180030052`
- `ntdll!NtWaitForSingleObject` at `0x18003006d`
- `ntdll!NtWaitForSingleObject` at `0x18003006d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f7b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f7b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f7ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f7ec`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002f3c0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002fbb5`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002f3c0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002fbb5`

## pseudocode

```c
__int64 __fastcall CRunRetrim::RunOperation(CRunRetrim *this)
{
  __int64 FileW; // rdi
  __int64 v3; // rbx
  NTSTATUS Status; // r12d
  unsigned int v5; // r15d
  struct IVolume *v6; // r14
  struct IVolume *v7; // rcx
  struct IVolume *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int16 v11; // ax
  int v12; // eax
  CDefragOperation *v13; // rcx
  unsigned __int64 v14; // r15
  __int16 v15; // ax
  __int16 v16; // ax
  unsigned __int16 *v17; // r12
  unsigned int *v18; // r13
  BOOL v19; // r15d
  int v20; // r14d
  struct IFreeSlabManager *v21; // rcx
  __int16 v22; // ax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  CRunRetrim *v31; // rcx
  CRunRetrim *v32; // rcx
  CDefragOperation *v33; // rcx
  LONG v34; // edx
  int lpVtbl; // r12d
  unsigned __int64 v37; // r14
  unsigned __int64 v38; // r15
  int v40; // r12d
  __int64 v41; // rax
  int v42; // eax
  __int16 v43; // cx
  unsigned __int64 v44; // rcx
  __int64 v45; // rcx
  int v46; // r8d
  int v47; // r9d
  unsigned int v48; // ecx
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  unsigned int v52; // r14d
  struct IFreeSlabManager *v53; // rcx
  struct IVolume *v54; // rcx
  __int16 v56; // ax
  unsigned int v57; // r14d
  __int64 v58; // r13
  __int64 v59; // rax
  __int16 v60; // cx
  __int64 v61; // rdx
  __int64 v62; // r8
  CSxGlobalTracer *v63; // r10
  __int64 v64; // rdx
  unsigned __int64 v65; // r9
  __int16 v66; // ax
  __int64 v67; // rax
  __int16 v68; // cx
  __int16 v69; // cx
  __int64 v70; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-100h]
  PHKEY phkResulta; // [rsp+20h] [rbp-100h]
  PHKEY phkResultb; // [rsp+20h] [rbp-100h]
  struct IUnknown *hTemplateFile; // [rsp+30h] [rbp-F0h]
  struct IUnknown *InputBufferLength; // [rsp+38h] [rbp-E8h]
  NTSTATUS v76; // [rsp+A0h] [rbp-80h] BYREF
  unsigned __int64 v77; // [rsp+A8h] [rbp-78h]
  struct IUnknown v78; // [rsp+B0h] [rbp-70h] BYREF
  int RetrimSettings; // [rsp+B8h] [rbp-68h] BYREF
  __int16 v80; // [rsp+BCh] [rbp-64h]
  __int16 v81; // [rsp+BEh] [rbp-62h]
  unsigned int v82; // [rsp+F0h] [rbp-30h] BYREF
  unsigned __int64 v83; // [rsp+F8h] [rbp-28h] BYREF
  struct IFreeSlabManager *v84; // [rsp+100h] [rbp-20h] BYREF
  unsigned int v85; // [rsp+108h] [rbp-18h] BYREF
  unsigned __int64 v86; // [rsp+110h] [rbp-10h] BYREF
  __int64 v87; // [rsp+118h] [rbp-8h] BYREF
  unsigned int v88; // [rsp+120h] [rbp+0h] BYREF
  struct IVolume *v89; // [rsp+128h] [rbp+8h] BYREF
  struct IUnknown v90; // [rsp+130h] [rbp+10h] BYREF
  unsigned int v91; // [rsp+138h] [rbp+18h] BYREF
  LONG DistanceToMoveHigh[2]; // [rsp+140h] [rbp+20h] BYREF
  unsigned __int64 v93; // [rsp+148h] [rbp+28h] BYREF
  __int64 v94; // [rsp+150h] [rbp+30h] BYREF
  unsigned __int64 v95; // [rsp+158h] [rbp+38h] BYREF
  __int64 v96; // [rsp+160h] [rbp+40h] BYREF
  int v97; // [rsp+168h] [rbp+48h] BYREF
  unsigned __int64 v98; // [rsp+170h] [rbp+50h] BYREF
  unsigned __int64 v99; // [rsp+178h] [rbp+58h] BYREF
  __int64 v100; // [rsp+180h] [rbp+60h] BYREF
  HKEY hKey; // [rsp+188h] [rbp+68h] BYREF
  struct _SYSTEMTIME v102; // [rsp+190h] [rbp+70h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+1A0h] [rbp+80h] BYREF
  __int128 InputBuffer; // [rsp+1A8h] [rbp+88h] BYREF
  __int128 v105; // [rsp+1B8h] [rbp+98h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1C8h] [rbp+A8h] BYREF
  struct _GUID v107; // [rsp+1D8h] [rbp+B8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1F0h] [rbp+D0h] BYREF
  _BYTE v109[92]; // [rsp+200h] [rbp+E0h] BYREF
  int v110; // [rsp+25Ch] [rbp+13Ch]
  WCHAR TempFileName[264]; // [rsp+2D0h] [rbp+1B0h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&RetrimSettings, "CRunRetrim::RunOperation", 0x30u, 1u);
  v89 = 0;
  v84 = 0;
  v100 = -1;
  FileW = -1;
  v95 = -1;
  v3 = -1;
  v96 = -1;
  v83 = 0;
  v87 = 0;
  InputBuffer = 0;
  v105 = 0;
  IoStatusBlock = 0;
  Status = 0;
  v76 = 0;
  v5 = 0;
  v77 = 0;
  SystemTime = 0;
  LODWORD(v86) = 0;
  v97 = 0;
  v88 = 0;
  v82 = 0;
  memset_0(v109, 0, 0xD0u);
  v99 = 0;
  v98 = 0;
  *(_QWORD *)DistanceToMoveHigh = 0;
  v93 = 0;
  UnbiasedTime = 0;
  v85 = 0;
  v91 = 0;
  v90.lpVtbl = 0;
  v78.lpVtbl = 0;
  v107 = 0;
  hKey = 0;
  (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 5) + 152LL))(*((_QWORD *)this + 5), &v107);
  GetLocalTime(&SystemTime);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v6 = (struct IVolume *)*((_QWORD *)this + 93);
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*((_QWORD *)this + 93));
    v8 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v89 = v6;
  }
  else
  {
    v7 = v89;
    if ( v89 )
    {
      v89 = (struct IVolume *)*((_QWORD *)this + 93);
      (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    RetrimSettings = CDefragOperation::_CreateVolumeForFileSystem(this, &v89);
    v11 = 110;
    if ( RetrimSettings < 0 )
      goto LABEL_5;
    v80 = 110;
  }
  if ( (unsigned int)dword_1800840E0 > 5 )
  {
    v94 = *((_QWORD *)this + 87);
    *(_QWORD *)&v102.wYear = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v8,
      (unsigned int)&unk_180077DB0,
      v9,
      v10,
      (__int64)&v102,
      (__int64)&v94);
  }
  RetrimSettings = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
                     *((_QWORD *)this + 6),
                     (char *)this + 56);
  v11 = 124;
  if ( RetrimSettings >= 0 )
  {
    v80 = 124;
    if ( *((_QWORD *)this + 18) && *((_DWORD *)this + 66) )
      goto LABEL_17;
    RetrimSettings = (*(__int64 (__fastcall **)(struct IVolume *, char *))(*(_QWORD *)v89 + 48LL))(
                       v89,
                       (char *)this + 56);
    v11 = 130;
    if ( RetrimSettings >= 0 )
    {
      v80 = 130;
LABEL_17:
      v12 = *((_DWORD *)this + 66);
      if ( v12 != 1 )
      {
        if ( v12 == 3 )
        {
          RetrimSettings = CDefragOperation::_CheckCSVState(this);
          v11 = 146;
          if ( RetrimSettings < 0 )
            goto LABEL_5;
          v80 = 146;
        }
        else if ( v12 != 4 )
        {
          RetrimSettings = -1996488672;
          v11 = 139;
          goto LABEL_5;
        }
      }
      RetrimSettings = CDefragOperation::_CheckTrimSupport(this, (int *)&v86);
      v11 = 150;
      if ( RetrimSettings < 0 )
        goto LABEL_5;
      v80 = 150;
      if ( !(_DWORD)v86 )
      {
        RetrimSettings = -1996488662;
        v11 = 154;
        goto LABEL_5;
      }
      RetrimSettings = CDefragOperation::_GetRetrimSettings(
                         v13,
                         &v88,
                         &v82,
                         &v85,
                         &v91,
                         (unsigned int *)&v90.lpVtbl + 1,
                         (unsigned int *)&v90,
                         (unsigned int *)&v78);
      v11 = 164;
      if ( RetrimSettings < 0 )
        goto LABEL_5;
      v80 = 164;
      RetrimSettings = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 5) + 80LL))(
                         *((_QWORD *)this + 5),
                         v109);
      v11 = 178;
      if ( RetrimSettings < 0 )
        goto LABEL_5;
      v80 = 178;
      if ( ((v110 - 5) & 0xFFFFFFFD) != 0 )
      {
        LODWORD(v78.lpVtbl) = 0;
        v14 = ((unsigned __int64)v82 << 10) / *((unsigned int *)this + 38);
        if ( !v14 )
          v14 = 1;
        v86 = v14;
        *((_DWORD *)this + 96) = 0;
      }
      else
      {
        if ( *((_DWORD *)this + 66) == 4 && *((_DWORD *)this + 188) && !LODWORD(v78.lpVtbl) )
        {
          RetrimSettings = -1996488672;
          v11 = 190;
          goto LABEL_5;
        }
        RetrimSettings = CDefragOperation::_GetProvisioningParameters(this, *((_DWORD *)this + 38), &v99, &v98);
        v11 = 195;
        if ( RetrimSettings < 0 )
          goto LABEL_5;
        v80 = 195;
        v14 = v98;
        v86 = v98;
        LODWORD(v78.lpVtbl) = 1;
        *((_DWORD *)this + 96) = 1;
        if ( (unsigned int)CDefragOperation::_CantReclaimEnoughSlabs(
                             this,
                             v89,
                             (CRunRetrim *)((char *)this + 56),
                             v14,
                             v85,
                             v91,
                             HIDWORD(v90.lpVtbl),
                             (unsigned int)v90.lpVtbl,
                             &v107,
                             0x64u,
                             0) )
        {
          RetrimSettings = 150995202;
          v15 = 213;
          goto LABEL_41;
        }
      }
      *((_DWORD *)this + 91) = 0;
      *((_QWORD *)this + 47) = 0;
      *((_DWORD *)this + 82) = 0;
      if ( *((_QWORD *)this + 18) < v14 )
      {
        RetrimSettings = 0;
        v15 = 249;
        goto LABEL_41;
      }
      RetrimSettings = CDefragOperation::_SetPhase(this, 10);
      v16 = 252;
      if ( RetrimSettings < 0
        || (v80 = 252, RetrimSettings = CDefragOperation::_SetPass(this, 1u), v16 = 255, RetrimSettings < 0) )
      {
        v81 = v16;
LABEL_95:
        v5 = v77;
        goto LABEL_96;
      }
      v80 = 255;
      v17 = (unsigned __int16 *)*((_QWORD *)this + 87);
      v18 = (unsigned int *)((char *)this + 152);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl'::`2'::impl) )
      {
        v19 = *v18 == v14 * *v18;
        if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Dfrg", 0, 0x20019u, &hKey) )
        {
          v20 = v19;
        }
        else
        {
          if ( (unsigned int)SxRegReadDWORD(hKey, L"MatchingSlabOptimization", (unsigned int *)&v78.lpVtbl + 1, 1) )
            v20 = v19;
          else
            v20 = HIDWORD(v78.lpVtbl) != 0 && v19;
          RegCloseKey(hKey);
        }
        v14 = v86;
      }
      else
      {
        v20 = 0;
      }
      v21 = v84;
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(struct IFreeSlabManager *))(*(_QWORD *)v21 + 16LL))(v21);
      }
      RetrimSettings = CFreeSlabManager::CreateInstance(
                         v17,
                         *((_QWORD *)this + 18),
                         *v18,
                         v14,
                         v99,
                         &v84,
                         hTemplateFile,
                         InputBufferLength,
                         v20);
      v22 = 281;
      if ( RetrimSettings < 0 )
      {
LABEL_57:
        v81 = v22;
        Status = 0;
        goto LABEL_95;
      }
      v80 = 281;
      v22 = 296;
      if ( !v17 )
      {
        RetrimSettings = -2147024809;
        goto LABEL_57;
      }
      RetrimSettings = 0;
      v80 = 296;
      FileW = (__int64)CreateFileW(v17, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
      v95 = FileW;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        RetrimSettings = GetLastFailureAsHRESULT(v24, v23, v25, v26, phkResult);
        v22 = 307;
        goto LABEL_57;
      }
      RetrimSettings = 0;
      v80 = 307;
      memset_0(TempFileName, 0, 0x208u);
      if ( !GetTempFileNameW(v17, L"rtr", 0, TempFileName) )
      {
        RetrimSettings = -1996488682;
        v22 = 318;
        goto LABEL_57;
      }
      v3 = (__int64)CreateFileW(TempFileName, 0xC0000000, 3u, 0, 2u, 0x4000002u, 0);
      v96 = v3;
      if ( (unsigned __int64)(v3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        RetrimSettings = GetLastFailureAsHRESULT(v28, v27, v29, v30, phkResulta);
        v22 = 330;
        goto LABEL_57;
      }
      RetrimSettings = 0;
      v80 = 330;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_93a218711d32344bab5188808709bc25_Traceguids, TempFileName);
      }
      RetrimSettings = CRunRetrim::_ClearFileCompressionOfMaskFile(v31, (void *)v3);
      v22 = 339;
      if ( RetrimSettings < 0 )
        goto LABEL_57;
      v80 = 339;
      RetrimSettings = CRunRetrim::_ClearFileIntegrityOfMaskFile(v32, (void *)v3);
      v22 = 352;
      if ( RetrimSettings < 0 )
        goto LABEL_57;
      v80 = 352;
      if ( *((_DWORD *)this + 66) == 3 )
      {
        RetrimSettings = (*(__int64 (__fastcall **)(struct IVolume *, int *))(*(_QWORD *)v89 + 304LL))(v89, &v97);
        v22 = 364;
        if ( RetrimSettings < 0 )
          goto LABEL_57;
        v80 = 364;
        if ( !v97 )
        {
          RetrimSettings = CDefragOperation::_DisableCsvCaching(v33, (void *)v3);
          v22 = 370;
          if ( RetrimSettings < 0 )
            goto LABEL_57;
          v80 = 370;
        }
      }
      if ( !SetFileValidData((HANDLE)v3, 0) )
      {
        RetrimSettings = -1996488682;
        v22 = 379;
        goto LABEL_57;
      }
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_93a218711d32344bab5188808709bc25_Traceguids);
      }
      v34 = v14 * *v18;
      *(_QWORD *)DistanceToMoveHigh = v14 * *v18;
      if ( SetFilePointer((HANDLE)v3, v34, &DistanceToMoveHigh[1], 0) == -1 )
      {
        RetrimSettings = -1996488682;
        v22 = 394;
        goto LABEL_57;
      }
      if ( !SetEndOfFile((HANDLE)v3) )
      {
        lpVtbl = (int)v78.lpVtbl;
        while ( *(_QWORD *)DistanceToMoveHigh && GetLastError() == 112 )
        {
          if ( lpVtbl )
          {
            v56 = 406;
            goto LABEL_119;
          }
          v37 = *(_QWORD *)DistanceToMoveHigh >> 1;
          *(_QWORD *)DistanceToMoveHigh = v37;
          v38 = *v18;
          if ( SetFilePointer((HANDLE)v3, v37, &DistanceToMoveHigh[1], 0) == -1 )
          {
            v56 = 419;
            goto LABEL_119;
          }
          v14 = v37 / v38;
          if ( SetEndOfFile((HANDLE)v3) )
            goto LABEL_87;
        }
        v56 = 427;
LABEL_119:
        RetrimSettings = -1996488682;
LABEL_120:
        v81 = v56;
LABEL_94:
        Status = v76;
        goto LABEL_95;
      }
LABEL_87:
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) != 0 )
      {
        WPP_SF_i(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_93a218711d32344bab5188808709bc25_Traceguids,
          *(_QWORD *)DistanceToMoveHigh);
      }
      InputBuffer = (unsigned __int64)v3;
      v40 = (int)v78.lpVtbl;
      v41 = *(_QWORD *)v84;
      if ( LODWORD(v78.lpVtbl) )
      {
        v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, unsigned __int64 *, __int64 *))(v41 + 64))(
                v84,
                &v83,
                &v87);
        v43 = 464;
      }
      else
      {
        v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, _QWORD, unsigned __int64, unsigned __int64 *, __int64 *))(v41 + 48))(
                v84,
                v88,
                v14,
                &v83,
                &v87);
        v43 = 466;
      }
      RetrimSettings = v42;
      if ( v42 < 0 )
      {
        v81 = v43;
        goto LABEL_94;
      }
      v80 = v43;
      HIDWORD(v78.lpVtbl) = 0;
      v57 = 0;
      v58 = 0;
      v82 = 0;
      LODWORD(v86) = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v42 == 1 )
          {
            RetrimSettings = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, char *, char *, char *, char *, char *))(*(_QWORD *)v84 + 176LL))(
                               v84,
                               (char *)this + 304,
                               (char *)this + 312,
                               (char *)this + 320,
                               (char *)this + 328,
                               (char *)this + 360);
            v56 = 653;
            if ( RetrimSettings < 0 )
              goto LABEL_120;
            v80 = 653;
            *((_DWORD *)this + 91) = v57;
            *((_QWORD *)this + 47) = v58;
            if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) != 0 )
            {
              WPP_SF_dI(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v70,
                WPP_93a218711d32344bab5188808709bc25_Traceguids,
                v57,
                v58);
            }
            goto LABEL_94;
          }
          if ( v83 != v100 )
            break;
          v59 = *(_QWORD *)v84;
          if ( v40 )
          {
            v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, unsigned __int64 *, __int64 *))(v59 + 72))(
                    v84,
                    &v83,
                    &v87);
            RetrimSettings = v42;
            if ( v42 < 0 )
            {
              v56 = 476;
              goto LABEL_120;
            }
            v60 = 476;
          }
          else
          {
            v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, unsigned __int64, unsigned __int64 *, __int64 *))(v59 + 56))(
                    v84,
                    v14,
                    &v83,
                    &v87);
            RetrimSettings = v42;
            if ( v42 < 0 )
            {
              v56 = 478;
              goto LABEL_120;
            }
            v60 = 478;
          }
          v80 = v60;
        }
        *(_QWORD *)&v105 = v83;
        DWORD2(v105) = v87;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
        {
          WPP_SF_dId(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        Status = NtFsControlFile((HANDLE)FileW, 0, 0, 0, &IoStatusBlock, 0x90074u, &InputBuffer, 0x20u, 0, 0);
        v76 = Status;
        if ( Status == 259 )
        {
          Status = NtWaitForSingleObject((HANDLE)FileW, 0, 0);
          v76 = Status;
          if ( Status < 0 )
            goto LABEL_140;
          Status = IoStatusBlock.Status;
          v76 = IoStatusBlock.Status;
        }
        if ( Status >= 0 )
          goto LABEL_145;
LABEL_140:
        if ( Status == -1073741738 || Status == -1073741791 )
          goto LABEL_145;
        v63 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_IId(*((_QWORD *)WPP_GLOBAL_Control + 2), v61, v62, v83, v87, Status);
LABEL_145:
          v63 = WPP_GLOBAL_Control;
        }
        if ( Status > -1073741697 )
        {
          switch ( Status )
          {
            case -1073741668:
              goto LABEL_209;
            case -1073741662:
LABEL_208:
              RetrimSettings = -1996488687;
              v66 = 556;
              goto LABEL_198;
            case -1073741566:
            case -1073741435:
              goto LABEL_209;
            case -1073741202:
              goto LABEL_208;
            case -1073741052:
              RetrimSettings = -1996488669;
              v66 = 560;
              goto LABEL_198;
            case 0:
              v65 = v83;
              if ( !v82 )
              {
                v100 = v83;
                LODWORD(v86) = 1;
                v82 = 1;
                if ( v63 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v63 + 7) & 0x40000000) != 0 )
                {
                  WPP_SF_(*((_QWORD *)v63 + 2), 15, WPP_93a218711d32344bab5188808709bc25_Traceguids);
                  v65 = v83;
                  v63 = WPP_GLOBAL_Control;
                }
              }
              v58 += v87;
              ++v57;
              if ( v63 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v63 + 7) & 0x40000000) == 0 )
                goto LABEL_175;
              v64 = 16;
              phkResultb = (PHKEY)(v65 + v87 - 1);
              goto LABEL_159;
          }
          if ( Status < 0 )
          {
LABEL_206:
            RetrimSettings = 1;
            v15 = 606;
LABEL_41:
            v80 = v15;
            goto LABEL_95;
          }
        }
        else
        {
          switch ( Status )
          {
            case -1073741697:
              RetrimSettings = -1996488673;
              v66 = 550;
              goto LABEL_198;
            case -1073741811:
              RetrimSettings = 1;
              v15 = 542;
              goto LABEL_41;
            case -1073741810:
              goto LABEL_208;
            case -1073741808:
LABEL_209:
              RetrimSettings = -1996488682;
              v66 = 538;
              goto LABEL_198;
            case -1073741801:
              RetrimSettings = -2147024882;
              v66 = 564;
              goto LABEL_198;
          }
          if ( Status != -1073741791 )
          {
            if ( Status == -1073741790 )
              goto LABEL_209;
            if ( Status == -1073741774 )
            {
              RetrimSettings = -1996488675;
              v66 = 546;
LABEL_198:
              v81 = v66;
              goto LABEL_95;
            }
            if ( Status != -1073741738 )
              goto LABEL_206;
          }
          Status = 0;
          v76 = 0;
          if ( v63 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v63 + 7) & 0x40000000) != 0 )
          {
            v64 = 17;
            phkResultb = (PHKEY)(v83 + v87 - 1);
LABEL_159:
            WPP_SF_II(*((_QWORD *)v63 + 2), v64, WPP_93a218711d32344bab5188808709bc25_Traceguids);
          }
        }
LABEL_175:
        RetrimSettings = (*(__int64 (__fastcall **)(CRunRetrim *))(*(_QWORD *)this + 32LL))(this);
        v66 = 610;
        if ( RetrimSettings < 0 )
          goto LABEL_198;
        v80 = 610;
        if ( v82 )
        {
          v77 = 100 * (v83 >> 8) / (*((_QWORD *)this + 18) >> 8);
          if ( (unsigned int)v77 >= HIDWORD(v78.lpVtbl) + 1 )
          {
            RetrimSettings = CDefragOperation::_SetPercentComplete(this, v77);
            v66 = 620;
            if ( RetrimSettings < 0 )
              goto LABEL_198;
            HIDWORD(v78.lpVtbl) = v77;
            v80 = 620;
          }
        }
        v67 = *(_QWORD *)v84;
        if ( (_DWORD)v86 )
        {
          if ( LODWORD(v78.lpVtbl) )
          {
            v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, unsigned __int64 *, __int64 *))(v67 + 64))(
                    v84,
                    &v83,
                    &v87);
            RetrimSettings = v42;
            if ( v42 < 0 )
            {
              v66 = 629;
              goto LABEL_198;
            }
            v68 = 629;
          }
          else
          {
            v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, _QWORD, unsigned __int64, unsigned __int64 *, __int64 *))(v67 + 48))(
                    v84,
                    v88,
                    v14,
                    &v83,
                    &v87);
            RetrimSettings = v42;
            if ( v42 < 0 )
            {
              v66 = 631;
              goto LABEL_198;
            }
            v68 = 631;
          }
          v80 = v68;
          LODWORD(v86) = 0;
          v40 = (int)v78.lpVtbl;
          if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_93a218711d32344bab5188808709bc25_Traceguids);
            v42 = RetrimSettings;
          }
        }
        else
        {
          if ( LODWORD(v78.lpVtbl) )
          {
            v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, unsigned __int64 *, __int64 *))(v67 + 72))(
                    v84,
                    &v83,
                    &v87);
            RetrimSettings = v42;
            if ( v42 < 0 )
            {
              v66 = 640;
              goto LABEL_198;
            }
            v69 = 640;
          }
          else
          {
            v42 = (*(__int64 (__fastcall **)(struct IFreeSlabManager *, unsigned __int64, unsigned __int64 *, __int64 *, PHKEY))(v67 + 56))(
                    v84,
                    v14,
                    &v83,
                    &v87,
                    phkResultb);
            RetrimSettings = v42;
            if ( v42 < 0 )
            {
              v66 = 642;
              goto LABEL_198;
            }
            v69 = 642;
          }
          v80 = v69;
          v40 = (int)v78.lpVtbl;
        }
      }
    }
  }
LABEL_5:
  v81 = v11;
LABEL_96:
  QueryUnbiasedInterruptTime(&v93);
  v44 = v93 - UnbiasedTime + 9999;
  v93 = v44 / 0x2710;
  if ( RetrimSettings >= 0 && RetrimSettings != 1 )
  {
    v45 = *((_QWORD *)this + 6);
    v102 = SystemTime;
    (*(void (__fastcall **)(__int64, struct _SYSTEMTIME *))(*(_QWORD *)v45 + 80LL))(v45, &v102);
    if ( dword_1800840E0 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v44, 0x400000000000LL) )
      {
        v96 = (__int64)&v107;
        HIDWORD(v78.lpVtbl) = Status;
        v85 = v5;
        v95 = v93;
        *(_QWORD *)&v102.wYear = *((_QWORD *)this + 47);
        v91 = *((_DWORD *)this + 91);
        HIDWORD(v90.lpVtbl) = *((_DWORD *)this + 82);
        LODWORD(v90.lpVtbl) = *((_DWORD *)this + 76);
        v94 = *((_QWORD *)this + 17);
        v100 = *((_QWORD *)this + 18);
        v48 = *((_DWORD *)this + 38);
        LODWORD(v86) = (*((_QWORD *)this + 40) * (unsigned __int64)v48) >> 10;
        v88 = (*((_QWORD *)this + 39) * (unsigned __int64)v48) >> 10;
        v82 = v48;
        v99 = *((_QWORD *)this + 87);
        v98 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v48,
          (unsigned int)word_180077CAA,
          v46,
          v47,
          (__int64)&v98,
          (__int64)&v99,
          (__int64)&v82,
          (__int64)&v88,
          (__int64)&v86,
          (__int64)&v100,
          (__int64)&v94,
          (__int64)&v90,
          (__int64)&v90.lpVtbl + 4,
          (__int64)&v91,
          (__int64)&v102,
          (__int64)&v95,
          (__int64)&v85,
          (__int64)&v78.lpVtbl + 4,
          (__int64)&v96);
      }
    }
  }
  if ( dword_1800840E0 && (unsigned __int8)tlgKeywordOn(v44, 0x400000000000LL) )
  {
    HIDWORD(v78.lpVtbl) = RetrimSettings;
    LOWORD(v76) = v81;
    v96 = (__int64)&v107;
    v95 = v93;
    *(_QWORD *)&v102.wYear = *((_QWORD *)this + 87);
    v85 = 2;
    v94 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v49,
      (unsigned int)&dword_180077C2C,
      v50,
      v51,
      (__int64)&v94,
      (__int64)&v85,
      (__int64)&v102,
      (__int64)&v95,
      (__int64)&v96,
      (__int64)&v76,
      (__int64)&v78.lpVtbl + 4);
  }
  v52 = RetrimSettings;
  if ( RetrimSettings != 1
    && (!*((_DWORD *)this + 189) || RetrimSettings != -1996488672 && RetrimSettings != -1996488662) )
  {
    Log_DF_OPTIMIZE_RESULT(
      (struct CSxFunctionTracer *)&RetrimSettings,
      0x2C5u,
      *((const unsigned __int16 **)this + 89),
      0x32Au,
      RetrimSettings,
      0);
    v52 = RetrimSettings;
  }
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v3);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  v53 = v84;
  if ( v84 )
  {
    v84 = 0;
    (*(void (__fastcall **)(struct IFreeSlabManager *))(*(_QWORD *)v53 + 16LL))(v53);
  }
  v54 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v54 + 16LL))(v54);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&RetrimSettings);
  return v52;
}

```

## disassembly

```asm
0x18002f280  push    rbp
0x18002f282  push    rbx
0x18002f283  push    rsi
0x18002f284  push    rdi
0x18002f285  push    r12
0x18002f287  push    r13
0x18002f289  push    r14
0x18002f28b  push    r15
0x18002f28d  lea     rbp, [rsp-3D8h]
0x18002f295  sub     rsp, 4F8h
0x18002f29c  mov     rax, cs:__security_cookie
0x18002f2a3  xor     rax, rsp
0x18002f2a6  mov     [rbp+410h+var_50], rax
0x18002f2ad  mov     rsi, rcx
0x18002f2b0  mov     r13d, 1
0x18002f2b6  mov     r9d, r13d; unsigned __int16
0x18002f2b9  lea     r8d, [r13+2Fh]; unsigned __int16
0x18002f2bd  lea     rdx, aCrunretrimRuno; "CRunRetrim::RunOperation"
0x18002f2c4  lea     rcx, [rbp+410h+var_478]; this
0x18002f2c8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002f2cd  nop
0x18002f2ce  mov     [rbp+410h+var_408], 0
0x18002f2d6  mov     [rbp+410h+var_430], 0
0x18002f2de  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f2e2  mov     [rbp+410h+var_3B0], rax
0x18002f2e6  mov     rdi, rax
0x18002f2e9  mov     [rbp+410h+var_3D8], rax
0x18002f2ed  mov     rbx, rax
0x18002f2f0  mov     [rbp+410h+var_3D0], rax
0x18002f2f4  mov     [rbp+410h+var_438], 0
0x18002f2fc  mov     [rbp+410h+var_418], 0
0x18002f304  xorps   xmm0, xmm0
0x18002f307  movups  [rbp+410h+InputBuffer], xmm0
0x18002f30e  movups  [rbp+410h+var_378], xmm0
0x18002f315  movups  xmmword ptr [rbp+410h+IoStatusBlock], xmm0
0x18002f31c  xor     r12d, r12d
0x18002f31f  mov     [rbp+410h+var_490], r12d
0x18002f323  xor     r15d, r15d
0x18002f326  mov     [rbp+410h+var_488], r15
0x18002f32a  movups  xmmword ptr [rbp+410h+SystemTime.wYear], xmm0
0x18002f331  mov     dword ptr [rbp+410h+var_420], r12d
0x18002f335  mov     [rbp+410h+var_3C8], r12d
0x18002f339  mov     [rbp+410h+var_410], r12d
0x18002f33d  mov     [rbp+410h+var_440], r12d
0x18002f341  xor     edx, edx; Val
0x18002f343  mov     r8d, 0D0h; Size
0x18002f349  lea     rcx, [rbp+410h+var_330]; void *
0x18002f350  call    memset_0
0x18002f355  mov     [rbp+410h+var_3B8], r12
0x18002f359  mov     [rbp+410h+var_3C0], r12
0x18002f35d  mov     qword ptr [rbp+410h+DistanceToMoveHigh], r12
0x18002f361  mov     [rbp+410h+var_3E8], r12
0x18002f365  mov     [rbp+410h+UnbiasedTime], r12
0x18002f36c  mov     [rbp+410h+var_428], r12d
0x18002f370  mov     [rbp+410h+var_3F8], r12d
0x18002f374  mov     dword ptr [rbp+410h+var_400.lpVtbl+4], r12d
0x18002f378  mov     dword ptr [rbp+410h+var_400.lpVtbl], r12d
0x18002f37c  mov     dword ptr [rbp+410h+var_480.lpVtbl], r12d
0x18002f380  xorps   xmm0, xmm0
0x18002f383  movups  xmmword ptr [rbp+410h+var_358.Data1], xmm0
0x18002f38a  mov     [rbp+410h+hKey], r12
0x18002f38e  mov     dword ptr [rbp+410h+var_480.lpVtbl+4], r12d
0x18002f392  mov     rcx, [rsi+28h]
0x18002f396  mov     rax, [rcx]
0x18002f399  lea     rdx, [rbp+410h+var_358]
0x18002f3a0  mov     rax, [rax+98h]
0x18002f3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3ac  lea     rcx, [rbp+410h+SystemTime]; lpSystemTime
0x18002f3b3  call    cs:__imp_GetLocalTime
0x18002f3b9  lea     rcx, [rbp+410h+UnbiasedTime]; UnbiasedTime
0x18002f3c0  call    cs:__imp_QueryUnbiasedInterruptTime
0x18002f3c6  mov     r14, [rsi+2E8h]
0x18002f3cd  test    r14, r14
0x18002f3d0  jnz     short loc_18002F413
0x18002f3d2  mov     rcx, [rbp+410h+var_408]
0x18002f3d6  test    rcx, rcx
0x18002f3d9  jz      short loc_18002F3EC
0x18002f3db  mov     [rbp+410h+var_408], r14
0x18002f3df  mov     rax, [rcx]
0x18002f3e2  mov     rax, [rax+10h]
0x18002f3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3eb  nop
0x18002f3ec  lea     rdx, [rbp+410h+var_408]; struct IVolume **
0x18002f3f0  mov     rcx, rsi; this
0x18002f3f3  call    ?_CreateVolumeForFileSystem@CDefragOperation@@IEAAJPEAPEAUIVolume@@@Z; CDefragOperation::_CreateVolumeForFileSystem(IVolume * *)
0x18002f3f8  mov     [rbp+410h+var_478], eax
0x18002f3fb  test    eax, eax
0x18002f3fd  mov     eax, 6Eh ; 'n'
0x18002f402  jns     short loc_18002F40D
0x18002f404  mov     [rbp+410h+var_472], ax
0x18002f408  jmp     loc_18002FBB1
0x18002f40d  mov     [rbp+410h+var_474], ax
0x18002f411  jmp     short loc_18002F445
0x18002f413  mov     rax, [r14]
0x18002f416  mov     rcx, r14
0x18002f419  mov     rax, [rax+8]
0x18002f41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f422  nop
0x18002f423  mov     rcx, [rbp+410h+var_408]
0x18002f427  test    rcx, rcx
0x18002f42a  jz      short loc_18002F441
0x18002f42c  mov     [rbp+410h+var_408], 0
0x18002f434  mov     rax, [rcx]
0x18002f437  mov     rax, [rax+10h]
0x18002f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f440  nop
0x18002f441  mov     [rbp+410h+var_408], r14
0x18002f445  mov     eax, cs:dword_1800840E0
0x18002f44b  cmp     eax, 5
0x18002f44e  jbe     short loc_18002F481
0x18002f450  mov     rax, [rsi+2B8h]
0x18002f457  mov     [rbp+410h+var_3E0], rax
0x18002f45b  mov     qword ptr [rbp+410h+var_3A0], 1000000h
0x18002f463  lea     rax, [rbp+410h+var_3E0]
0x18002f467  mov     qword ptr [rsp+530h+dwFlagsAndAttributes], rax
0x18002f46c  lea     rax, [rbp+410h+var_3A0]
0x18002f470  mov     [rsp+530h+phkResult], rax
0x18002f475  lea     rdx, unk_180077DB0
0x18002f47c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18002f481  mov     rcx, [rsi+30h]
0x18002f485  lea     r14, [rsi+38h]
0x18002f489  mov     rax, [rcx]
0x18002f48c  mov     rdx, r14
0x18002f48f  mov     rax, [rax+18h]
0x18002f493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f498  mov     [rbp+410h+var_478], eax
0x18002f49b  test    eax, eax
0x18002f49d  mov     eax, 7Ch ; '|'
0x18002f4a2  js      loc_18002F404
0x18002f4a8  mov     [rbp+410h+var_474], ax
0x18002f4ac  cmp     qword ptr [rsi+90h], 0
0x18002f4b4  jz      short loc_18002F4BF
0x18002f4b6  cmp     dword ptr [rsi+108h], 0
0x18002f4bd  jnz     short loc_18002F4E6
0x18002f4bf  mov     rcx, [rbp+410h+var_408]
0x18002f4c3  mov     rax, [rcx]
0x18002f4c6  mov     rdx, r14
0x18002f4c9  mov     rax, [rax+30h]
0x18002f4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4d2  mov     [rbp+410h+var_478], eax
0x18002f4d5  test    eax, eax
0x18002f4d7  mov     eax, 82h
0x18002f4dc  js      loc_18002F404
0x18002f4e2  mov     [rbp+410h+var_474], ax
0x18002f4e6  mov     eax, [rsi+108h]
0x18002f4ec  cmp     eax, r13d
0x18002f4ef  jz      short loc_18002F528
0x18002f4f1  cmp     eax, 3
0x18002f4f4  jz      short loc_18002F50C
0x18002f4f6  cmp     eax, 4
0x18002f4f9  jz      short loc_18002F528
0x18002f4fb  mov     [rbp+410h+var_478], 89000020h
0x18002f502  mov     eax, 8Bh
0x18002f507  jmp     loc_18002F404
0x18002f50c  mov     rcx, rsi; this
0x18002f50f  call    ?_CheckCSVState@CDefragOperation@@IEAAJXZ; CDefragOperation::_CheckCSVState(void)
0x18002f514  mov     [rbp+410h+var_478], eax
0x18002f517  test    eax, eax
0x18002f519  mov     eax, 92h
0x18002f51e  js      loc_18002F404
0x18002f524  mov     [rbp+410h+var_474], ax
0x18002f528  lea     rdx, [rbp+410h+var_420]; int *
0x18002f52c  mov     rcx, rsi; this
0x18002f52f  call    ?_CheckTrimSupport@CDefragOperation@@IEAAJPEAH@Z; CDefragOperation::_CheckTrimSupport(int *)
0x18002f534  mov     [rbp+410h+var_478], eax
0x18002f537  test    eax, eax
0x18002f539  mov     eax, 96h
0x18002f53e  js      loc_18002F404
0x18002f544  mov     [rbp+410h+var_474], ax
0x18002f548  cmp     dword ptr [rbp+410h+var_420], 0
0x18002f54c  jnz     short loc_18002F55F
0x18002f54e  mov     [rbp+410h+var_478], 8900002Ah
0x18002f555  mov     eax, 9Ah
0x18002f55a  jmp     loc_18002F404
0x18002f55f  lea     rax, [rbp+410h+var_480]
0x18002f563  mov     qword ptr [rsp+530h+InputBufferLength], rax; struct IUnknown *
0x18002f568  lea     rax, [rbp+410h+var_400]
0x18002f56c  mov     [rsp+530h+hTemplateFile], rax; struct IUnknown *
0x18002f571  lea     rax, [rbp+410h+var_400.lpVtbl+4]
0x18002f575  mov     qword ptr [rsp+530h+dwFlagsAndAttributes], rax; unsigned int *
0x18002f57a  lea     rax, [rbp+410h+var_3F8]
0x18002f57e  mov     [rsp+530h+phkResult], rax; unsigned int *
0x18002f583  lea     r9, [rbp+410h+var_428]; unsigned int *
0x18002f587  lea     r8, [rbp+410h+var_440]; unsigned int *
0x18002f58b  lea     rdx, [rbp+410h+var_410]; unsigned int *
0x18002f58f  call    ?_GetRetrimSettings@CDefragOperation@@IEAAJPEAK000000@Z; CDefragOperation::_GetRetrimSettings(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x18002f594  mov     [rbp+410h+var_478], eax
0x18002f597  test    eax, eax
0x18002f599  mov     eax, 0A4h
0x18002f59e  js      loc_18002F404
0x18002f5a4  mov     [rbp+410h+var_474], ax
0x18002f5a8  mov     rcx, [rsi+28h]
0x18002f5ac  mov     rax, [rcx]
0x18002f5af  lea     rdx, [rbp+410h+var_330]
0x18002f5b6  mov     rax, [rax+50h]
0x18002f5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5bf  mov     [rbp+410h+var_478], eax
0x18002f5c2  test    eax, eax
0x18002f5c4  mov     eax, 0B2h
0x18002f5c9  js      loc_18002F404
0x18002f5cf  mov     [rbp+410h+var_474], ax
0x18002f5d3  mov     eax, [rbp+410h+var_2D4]
0x18002f5d9  add     eax, 0FFFFFFFBh
0x18002f5dc  test    eax, 0FFFFFFFDh
0x18002f5e1  jz      short loc_18002F651
0x18002f5e3  mov     dword ptr [rbp+410h+var_480.lpVtbl], 0
0x18002f5ea  mov     ecx, [rsi+98h]
0x18002f5f0  mov     eax, [rbp+410h+var_440]
0x18002f5f3  shl     rax, 0Ah
0x18002f5f7  xor     edx, edx
0x18002f5f9  div     rcx
0x18002f5fc  mov     r15, rax
0x18002f5ff  test    rax, rax
0x18002f602  cmovz   r15, r13
0x18002f606  mov     [rbp+410h+var_420], r15
0x18002f60a  mov     dword ptr [rsi+180h], 0
0x18002f614  mov     dword ptr [rsi+16Ch], 0
0x18002f61e  mov     qword ptr [rsi+178h], 0
0x18002f629  mov     dword ptr [rsi+148h], 0
0x18002f633  cmp     [rsi+90h], r15
0x18002f63a  jnb     loc_18002F71F
0x18002f640  mov     [rbp+410h+var_478], 0
0x18002f647  mov     eax, 0F9h
0x18002f64c  jmp     loc_18002F716
0x18002f651  cmp     dword ptr [rsi+108h], 4
0x18002f658  jnz     short loc_18002F67A
0x18002f65a  cmp     dword ptr [rsi+2F0h], 0
0x18002f661  jz      short loc_18002F67A
0x18002f663  cmp     dword ptr [rbp+410h+var_480.lpVtbl], 0
0x18002f667  jnz     short loc_18002F67A
0x18002f669  mov     [rbp+410h+var_478], 89000020h
0x18002f670  mov     eax, 0BEh
0x18002f675  jmp     loc_18002F404
0x18002f67a  lea     r9, [rbp+410h+var_3C0]; unsigned __int64 *
0x18002f67e  lea     r8, [rbp+410h+var_3B8]; unsigned __int64 *
0x18002f682  mov     edx, [rsi+98h]; unsigned int
0x18002f688  mov     rcx, rsi; this
0x18002f68b  call    ?_GetProvisioningParameters@CDefragOperation@@IEAAJKPEA_K0@Z; CDefragOperation::_GetProvisioningParameters(ulong,unsigned __int64 *,unsigned __int64 *)
0x18002f690  mov     [rbp+410h+var_478], eax
0x18002f693  test    eax, eax
0x18002f695  mov     eax, 0C3h
0x18002f69a  js      loc_18002F404
0x18002f6a0  mov     [rbp+410h+var_474], ax
0x18002f6a4  mov     r15, [rbp+410h+var_3C0]
0x18002f6a8  mov     [rbp+410h+var_420], r15
0x18002f6ac  mov     dword ptr [rbp+410h+var_480.lpVtbl], r13d
0x18002f6b0  mov     [rsi+180h], r13d
0x18002f6b7  mov     [rsp+530h+var_4E0], 0; unsigned __int64 *
0x18002f6c0  mov     [rsp+530h+OutputBufferLength], 64h ; 'd'; unsigned int
0x18002f6c8  lea     rax, [rbp+410h+var_358]
0x18002f6cf  mov     [rsp+530h+OutputBuffer], rax; struct _GUID *
0x18002f6d4  mov     eax, dword ptr [rbp+410h+var_400.lpVtbl]
0x18002f6d7  mov     [rsp+530h+InputBufferLength], eax; unsigned int
0x18002f6db  mov     eax, dword ptr [rbp+410h+var_400.lpVtbl+4]
0x18002f6de  mov     dword ptr [rsp+530h+hTemplateFile], eax; unsigned int
0x18002f6e2  mov     eax, [rbp+410h+var_3F8]
0x18002f6e5  mov     [rsp+530h+dwFlagsAndAttributes], eax; unsigned int
0x18002f6e9  mov     eax, [rbp+410h+var_428]
0x18002f6ec  mov     dword ptr [rsp+530h+phkResult], eax; unsigned int
0x18002f6f0  mov     r9, r15; unsigned __int64
0x18002f6f3  mov     r8, r14; struct __MIDL___MIDL_itf_dfengine_0000_0000_0006 *
0x18002f6f6  mov     rdx, [rbp+410h+var_408]; struct IVolume *
0x18002f6fa  mov     rcx, rsi; this
0x18002f6fd  call    ?_CantReclaimEnoughSlabs@CDefragOperation@@IEAAHPEAUIVolume@@PEAU__MIDL___MIDL_itf_dfengine_0000_0000_0006@@_KKKKKPEAU_GUID@@KPEA_K@Z; CDefragOperation::_CantReclaimEnoughSlabs(IVolume *,__MIDL___MIDL_itf_dfengine_0000_0000_0006 *,unsigned __int64,ulong,ulong,ulong,ulong,_GUID *,ulong,unsigned __int64 *)
0x18002f702  test    eax, eax
0x18002f704  jz      loc_18002F614
0x18002f70a  mov     [rbp+410h+var_478], 9000102h
0x18002f711  mov     eax, 0D5h
0x18002f716  mov     [rbp+410h+var_474], ax
0x18002f71a  jmp     loc_18002FBAD
0x18002f71f  mov     edx, 0Ah
0x18002f724  mov     rcx, rsi
0x18002f727  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18002f72c  mov     [rbp+410h+var_478], eax
0x18002f72f  test    eax, eax
0x18002f731  mov     eax, 0FCh
0x18002f736  jns     short loc_18002F741
0x18002f738  mov     [rbp+410h+var_472], ax
0x18002f73c  jmp     loc_18002FBAD
0x18002f741  mov     [rbp+410h+var_474], ax
0x18002f745  mov     edx, r13d; unsigned int
0x18002f748  mov     rcx, rsi; this
0x18002f74b  call    ?_SetPass@CDefragOperation@@IEAAJK@Z; CDefragOperation::_SetPass(ulong)
0x18002f750  mov     [rbp+410h+var_478], eax
0x18002f753  test    eax, eax
0x18002f755  mov     eax, 0FFh
0x18002f75a  js      short loc_18002F738
0x18002f75c  mov     [rbp+410h+var_474], ax
0x18002f760  mov     r12, [rsi+2B8h]
0x18002f767  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster> `wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl(void)'::`2'::impl
0x18002f76e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(void)
0x18002f773  lea     r13, [rsi+98h]
0x18002f77a  test    al, al
0x18002f77c  jz      short loc_18002F7FD
0x18002f77e  mov     ecx, [r13+0]
0x18002f782  mov     eax, ecx
0x18002f784  imul    rax, r15
0x18002f788  xor     r15d, r15d
0x18002f78b  cmp     rcx, rax
0x18002f78e  setz    r15b
  ... truncated ...
```
