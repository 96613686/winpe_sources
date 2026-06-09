# DsrCmdAsyncHelper::DeviceUpdate(void)

- ea: `0x18009f520`
- end: `0x18009fb67`
- name: `?DeviceUpdate@DsrCmdAsyncHelper@@SAJXZ`
- size: `1607`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18009b940`

## callees

- `0x1800084f4`
- `0x18000ab70`
- `0x18000bd20`
- `0x180012948`
- `0x180012c7c`
- `0x180038e44`
- `0x180046ae8`
- `0x180046b3c`
- `0x180065c5c`
- `0x18009f520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f902`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f743`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f743`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009f86f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009f86f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fb41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fb41`

## string_xrefs

- `0x18009f56c`: `DsrCmdAsyncHelper::DeviceUpdate`
- `0x18009f5f4`: `DsrCmdAsyncHelper::DeviceUpdate`
- `0x18009f770`: `%s: CreateEventW failed with error code 0x%08x.\n`
- `0x18009f6ba`: `Failed to determine if the process has administrator privileges: 0x%08x.\n`
- `0x18009f6d0`: `Failed to determine if the process has administrator privileges: 0x%08x.\n`
- `0x18009f5cd`: `The device is enterprise joined, not joined to AAD. Nothing to update. Exiting...\n`
- `0x18009f5e3`: `The device is enterprise joined, not joined to AAD. Nothing to update. Exiting...\n`
- `0x18009f70d`: `To update AAD joined device, you need to run the process as administrator.\n`
- `0x18009f723`: `To update AAD joined device, you need to run the process as administrator.\n`
- `0x18009fb16`: `The device is not joined to AAD. Nothing to update. Exiting...\n`
- `0x18009fb2c`: `The device is not joined to AAD. Nothing to update. Exiting...\n`
- `0x18009fa42`: `%s: DeviceUpdateCallback failed with error code 0x%08x.\n`
- `0x18009f9d2`: `%s: WaitForSingleObject timed out for DsrBeginDeviceUpdate.\n`
- `0x18009f814`: `%s: DsrBeginDeviceUpdate failed with error code 0x%08x.\n`
- `0x18009fad0`: `Device update failed with error code 0x%08x.\n`
- `0x18009fae6`: `Device update failed with error code 0x%08x.\n`
- `0x18009f9a6`: `Device update succeeded.\n`
- `0x18009f9bc`: `Device update succeeded.\n`
- `0x18009f91c`: `%s: WaitForSingleObject failed for DsrBeginDeviceUpdate.\n`
- `0x18009f8a4`: `%s: WaitForSingleObject returned unexpected wait status 0x%08x for DsrBeginDeviceUpdate.\n`
- `0x18009f8da`: `%s: WaitForSingleObject returned unexpected wait status 0x%08x for DsrBeginDeviceUpdate.\n`
- `0x18009f8f6`: `%s: WaitForSingleObject returned unexpected wait status 0x%08x for DsrBeginDeviceUpdate.\n`

## pseudocode

```c
__int64 DsrCmdAsyncHelper::DeviceUpdate(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  unsigned int JoinInfo; // ebx
  _BYTE **CurrentRef; // rax
  const wchar_t *v4; // rsi
  _QWORD *v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  _QWORD *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  signed int LastError; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  _QWORD *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  _QWORD *v44; // rax
  __int64 v45; // rdx
  _QWORD *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rax
  DWORD v49; // eax
  DWORD v50; // esi
  __int64 v51; // rdx
  __int64 v52; // rcx
  _QWORD *v53; // rax
  __int64 v54; // rdx
  _QWORD *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rax
  signed int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rcx
  _QWORD *v63; // rax
  __int64 v64; // rdx
  _QWORD *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  _QWORD *v68; // rax
  __int64 v69; // rdx
  _QWORD *v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rcx
  _QWORD *v75; // rax
  __int64 v76; // rdx
  _QWORD *v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // rdx
  _QWORD *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  _QWORD *v87; // rax
  __int64 v88; // rdx
  _QWORD *v89; // rax
  __int64 v90; // rcx
  __int64 v91; // rax
  _QWORD *v92; // rax
  __int64 v93; // rdx
  _QWORD *v94; // rax
  __int64 v95; // rcx
  __int64 v96; // rax
  HANDLE hHandle[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v99; // [rsp+50h] [rbp-20h] BYREF
  __int128 v100; // [rsp+58h] [rbp-18h]
  WINBOOL IsMember; // [rsp+90h] [rbp+20h] BYREF
  void *Block; // [rsp+98h] [rbp+28h] BYREF

  v99 = 1;
  Block = 0;
  *(_OWORD *)hHandle = 0;
  v100 = 0;
  JoinInfo = DsrGetJoinInfoEx(3, &v99, &Block);
  if ( (JoinInfo & 0x80000000) != 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v1, v0);
    v4 = L"%s: DsrGetJoinInfoEx failed with error code 0x%08x.\n";
    goto LABEL_66;
  }
  if ( Block )
  {
    if ( *((_DWORD *)Block + 4) )
    {
      v1 = *((_QWORD *)Block + 1);
      if ( v1 )
      {
        if ( *(_DWORD *)(v1 + 60) )
        {
          v5 = (_QWORD *)CmdOptions::GetCurrentRef(v1, v0);
          if ( *(_BYTE *)(*v5 + 12LL) )
          {
            v7 = (_QWORD *)CmdOptions::GetCurrentRef(*v5, v6);
            if ( *(_QWORD *)(*v7 + 184LL) )
            {
              v9 = CmdOptions::GetCurrentRef(*v7, v8);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v9 + 184LL),
                L"The device is enterprise joined, not joined to AAD. Nothing to update. Exiting...\n");
            }
          }
          wprintf(L"The device is enterprise joined, not joined to AAD. Nothing to update. Exiting...\n");
          goto LABEL_79;
        }
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v1, v0) )
        {
          wprintf(
            L"%s: Tenant ID: %s\n",
            L"DsrCmdAsyncHelper::DeviceUpdate",
            *(_QWORD *)(*((_QWORD *)Block + 1) + 32LL));
          v12 = (_QWORD *)CmdOptions::GetCurrentRef(v11, v10);
          if ( *(_BYTE *)(*v12 + 12LL) )
          {
            if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v12, v13) + 184LL) )
            {
              v15 = *((_QWORD *)Block + 1);
              v16 = *(_QWORD *)(v15 + 32);
              v17 = CmdOptions::GetCurrentRef(v15, v14);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v17 + 184LL),
                L"%s: Tenant ID: %s\n",
                L"DsrCmdAsyncHelper::DeviceUpdate",
                v16);
            }
          }
        }
        Logger::TraceInformation(
          L"%s: Tenant ID: %s\n",
          L"DsrCmdAsyncHelper::DeviceUpdate",
          *(_QWORD *)(*((_QWORD *)Block + 1) + 32LL));
        IsMember = 0;
        JoinInfo = IsCurrentUserElevated(&IsMember);
        if ( (JoinInfo & 0x80000000) != 0 )
        {
          v20 = (_QWORD *)CmdOptions::GetCurrentRef(v19, v18);
          if ( *(_BYTE *)(*v20 + 12LL) )
          {
            v22 = (_QWORD *)CmdOptions::GetCurrentRef(*v20, v21);
            if ( *(_QWORD *)(*v22 + 184LL) )
            {
              v24 = CmdOptions::GetCurrentRef(*v22, v23);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v24 + 184LL),
                L"Failed to determine if the process has administrator privileges: 0x%08x.\n",
                JoinInfo);
            }
          }
          wprintf(L"Failed to determine if the process has administrator privileges: 0x%08x.\n", JoinInfo);
          goto LABEL_79;
        }
        if ( !IsMember )
        {
          v25 = (_QWORD *)CmdOptions::GetCurrentRef(v19, v18);
          if ( *(_BYTE *)(*v25 + 12LL) )
          {
            v27 = (_QWORD *)CmdOptions::GetCurrentRef(*v25, v26);
            if ( *(_QWORD *)(*v27 + 184LL) )
            {
              v29 = CmdOptions::GetCurrentRef(*v27, v28);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v29 + 184LL),
                L"To update AAD joined device, you need to run the process as administrator.\n");
            }
          }
          wprintf(L"To update AAD joined device, you need to run the process as administrator.\n");
          JoinInfo = -2147024891;
          goto LABEL_79;
        }
        hHandle[1] = CreateEventW(0, 0, 0, 0);
        if ( !hHandle[1] )
        {
          LastError = GetLastError();
          JoinInfo = LastError;
          if ( LastError > 0 )
            JoinInfo = (unsigned __int16)LastError | 0x80070000;
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v32, v31) )
          {
            wprintf(L"%s: CreateEventW failed with error code 0x%08x.\n", L"DsrCmdAsyncHelper::DeviceUpdate", JoinInfo);
            v35 = (_QWORD *)CmdOptions::GetCurrentRef(v34, v33);
            if ( *(_BYTE *)(*v35 + 12LL) )
            {
              v37 = (_QWORD *)CmdOptions::GetCurrentRef(*v35, v36);
              if ( *(_QWORD *)(*v37 + 184LL) )
              {
                v39 = CmdOptions::GetCurrentRef(*v37, v38);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v39 + 184LL),
                  L"%s: CreateEventW failed with error code 0x%08x.\n",
                  L"DsrCmdAsyncHelper::DeviceUpdate",
                  JoinInfo);
              }
            }
          }
          Logger::TraceError(
            L"%s: CreateEventW failed with error code 0x%08x.\n",
            L"DsrCmdAsyncHelper::DeviceUpdate",
            JoinInfo);
          goto LABEL_54;
        }
        JoinInfo = DeviceUpdateController::UpdateDevice(
                     1u,
                     0,
                     0,
                     0,
                     5,
                     (__int64)DsrCmdAsyncHelper::DeviceUpdateCallback,
                     (__int64)hHandle);
        if ( (JoinInfo & 0x80000000) == 0 )
        {
          v44 = (_QWORD *)CmdOptions::GetCurrentRef(v43, v42);
          if ( *(_BYTE *)(*v44 + 12LL) )
          {
            v46 = (_QWORD *)CmdOptions::GetCurrentRef(*v44, v45);
            if ( *(_QWORD *)(*v46 + 184LL) )
            {
              v48 = CmdOptions::GetCurrentRef(v47, *v46);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v48 + 184LL),
                L"Checking and updating device if necessary. Please wait...\n");
            }
          }
          wprintf(L"Checking and updating device if necessary. Please wait...\n");
          v49 = WaitForSingleObject(hHandle[1], 0x57E40u);
          v50 = v49;
          if ( v49 )
          {
            if ( v49 == 258 )
            {
              JoinInfo = -2147023436;
              if ( **(_BYTE **)CmdOptions::GetCurrentRef(v41, v40) )
              {
                wprintf(
                  L"%s: WaitForSingleObject timed out for DsrBeginDeviceUpdate.\n",
                  L"DsrCmdAsyncHelper::DeviceUpdate");
                v75 = (_QWORD *)CmdOptions::GetCurrentRef(v74, v73);
                if ( *(_BYTE *)(*v75 + 12LL) )
                {
                  v77 = (_QWORD *)CmdOptions::GetCurrentRef(*v75, v76);
                  if ( *(_QWORD *)(*v77 + 184LL) )
                  {
                    v79 = CmdOptions::GetCurrentRef(v78, *v77);
                    fwprintf_s(
                      *(FILE *const *)(*(_QWORD *)v79 + 184LL),
                      L"%s: WaitForSingleObject timed out for DsrBeginDeviceUpdate.\n",
                      L"DsrCmdAsyncHelper::DeviceUpdate");
                  }
                }
              }
              Logger::TraceError(
                L"%s: WaitForSingleObject timed out for DsrBeginDeviceUpdate.\n",
                L"DsrCmdAsyncHelper::DeviceUpdate");
              goto LABEL_71;
            }
            if ( v49 != -1 )
            {
              JoinInfo = -2147023436;
              if ( **(_BYTE **)CmdOptions::GetCurrentRef(v41, v40) )
              {
                wprintf(
                  L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for DsrBeginDeviceUpdate.\n",
                  L"DsrCmdAsyncHelper::DeviceUpdate",
                  v50);
                v53 = (_QWORD *)CmdOptions::GetCurrentRef(v52, v51);
                if ( *(_BYTE *)(*v53 + 12LL) )
                {
                  v55 = (_QWORD *)CmdOptions::GetCurrentRef(*v53, v54);
                  if ( *(_QWORD *)(*v55 + 184LL) )
                  {
                    v57 = CmdOptions::GetCurrentRef(*v55, v56);
                    fwprintf_s(
                      *(FILE *const *)(*(_QWORD *)v57 + 184LL),
                      L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for DsrBeginDeviceUpdate.\n",
                      L"DsrCmdAsyncHelper::DeviceUpdate",
                      v50);
                  }
                }
              }
              Logger::TraceError(
                L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for DsrBeginDeviceUpdate.\n",
                L"DsrCmdAsyncHelper::DeviceUpdate",
                v50);
              goto LABEL_71;
            }
            v58 = GetLastError();
            JoinInfo = v58;
            if ( v58 > 0 )
              JoinInfo = (unsigned __int16)v58 | 0x80070000;
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v60, v59) )
            {
              wprintf(L"%s: WaitForSingleObject failed for DsrBeginDeviceUpdate.\n", L"DsrCmdAsyncHelper::DeviceUpdate");
              v63 = (_QWORD *)CmdOptions::GetCurrentRef(v62, v61);
              if ( *(_BYTE *)(*v63 + 12LL) )
              {
                v65 = (_QWORD *)CmdOptions::GetCurrentRef(*v63, v64);
                if ( *(_QWORD *)(*v65 + 184LL) )
                {
                  v67 = CmdOptions::GetCurrentRef(v66, *v65);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v67 + 184LL),
                    L"%s: WaitForSingleObject failed for DsrBeginDeviceUpdate.\n",
                    L"DsrCmdAsyncHelper::DeviceUpdate");
                }
              }
            }
            Logger::TraceError(
              L"%s: WaitForSingleObject failed for DsrBeginDeviceUpdate.\n",
              L"DsrCmdAsyncHelper::DeviceUpdate");
LABEL_54:
            if ( (JoinInfo & 0x80000000) != 0 )
            {
LABEL_71:
              v87 = (_QWORD *)CmdOptions::GetCurrentRef(v41, v40);
              if ( *(_BYTE *)(*v87 + 12LL) )
              {
                v89 = (_QWORD *)CmdOptions::GetCurrentRef(*v87, v88);
                if ( *(_QWORD *)(*v89 + 184LL) )
                {
                  v91 = CmdOptions::GetCurrentRef(v90, *v89);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v91 + 184LL),
                    L"Device update failed with error code 0x%08x.\n",
                    JoinInfo);
                }
              }
              wprintf(L"Device update failed with error code 0x%08x.\n", JoinInfo);
              goto LABEL_79;
            }
            goto LABEL_55;
          }
          JoinInfo = (unsigned int)hHandle[0];
          if ( SLODWORD(hHandle[0]) >= 0 )
          {
LABEL_55:
            v68 = (_QWORD *)CmdOptions::GetCurrentRef(v41, v40);
            if ( *(_BYTE *)(*v68 + 12LL) )
            {
              v70 = (_QWORD *)CmdOptions::GetCurrentRef(*v68, v69);
              if ( *(_QWORD *)(*v70 + 184LL) )
              {
                v72 = CmdOptions::GetCurrentRef(v71, *v70);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v72 + 184LL), L"Device update succeeded.\n");
              }
            }
            wprintf(L"Device update succeeded.\n");
            goto LABEL_79;
          }
          CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v41, v40);
          v4 = L"%s: DeviceUpdateCallback failed with error code 0x%08x.\n";
        }
        else
        {
          CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v43, v42);
          v4 = L"%s: DsrBeginDeviceUpdate failed with error code 0x%08x.\n";
        }
LABEL_66:
        if ( **CurrentRef )
        {
          wprintf(v4, L"DsrCmdAsyncHelper::DeviceUpdate", JoinInfo);
          v82 = (_QWORD *)CmdOptions::GetCurrentRef(v81, v80);
          if ( *(_BYTE *)(*v82 + 12LL) )
          {
            v84 = (_QWORD *)CmdOptions::GetCurrentRef(*v82, v83);
            if ( *(_QWORD *)(*v84 + 184LL) )
            {
              v86 = CmdOptions::GetCurrentRef(*v84, v85);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)v86 + 184LL), v4, L"DsrCmdAsyncHelper::DeviceUpdate", JoinInfo);
            }
          }
        }
        Logger::TraceError(v4, L"DsrCmdAsyncHelper::DeviceUpdate", JoinInfo);
        goto LABEL_71;
      }
    }
  }
  v92 = (_QWORD *)CmdOptions::GetCurrentRef(v1, v0);
  if ( *(_BYTE *)(*v92 + 12LL) )
  {
    v94 = (_QWORD *)CmdOptions::GetCurrentRef(*v92, v93);
    if ( *(_QWORD *)(*v94 + 184LL) )
    {
      v96 = CmdOptions::GetCurrentRef(v95, *v94);
      fwprintf_s(
        *(FILE *const *)(*(_QWORD *)v96 + 184LL),
        L"The device is not joined to AAD. Nothing to update. Exiting...\n");
    }
  }
  wprintf(L"The device is not joined to AAD. Nothing to update. Exiting...\n");
LABEL_79:
  if ( hHandle[1] )
    CloseHandle(hHandle[1]);
  DsrFreeJoinInfoEx(Block);
  return JoinInfo;
}

```

## disassembly

```asm
0x18009f520  mov     [rsp-18h+arg_10], rbx
0x18009f525  mov     [rsp-18h+arg_18], rsi
0x18009f52a  push    rbp
0x18009f52b  push    rdi
0x18009f52c  push    r14
0x18009f52e  mov     rbp, rsp
0x18009f531  sub     rsp, 70h
0x18009f535  xorps   xmm0, xmm0
0x18009f538  mov     [rbp+var_20], 1
0x18009f540  xor     r14d, r14d
0x18009f543  lea     r8, [rbp+Block]
0x18009f547  lea     rdx, [rbp+var_20]
0x18009f54b  mov     [rbp+Block], r14
0x18009f54f  movups  xmmword ptr [rbp+hHandle], xmm0
0x18009f553  lea     ecx, [r14+3]
0x18009f557  movdqu  [rbp+var_18], xmm0
0x18009f55c  call    DsrGetJoinInfoEx
0x18009f561  mov     ebx, eax
0x18009f563  test    eax, eax
0x18009f565  jns     short loc_18009F57F
0x18009f567  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f56c  lea     rdi, aDsrcmdasynchel; "DsrCmdAsyncHelper::DeviceUpdate"
0x18009f573  lea     rsi, aSDsrgetjoininf; "%s: DsrGetJoinInfoEx failed with error "...
0x18009f57a  jmp     loc_18009FA49
0x18009f57f  mov     rax, [rbp+Block]
0x18009f583  test    rax, rax
0x18009f586  jz      loc_18009FAF2
0x18009f58c  cmp     [rax+10h], r14d
0x18009f590  jz      loc_18009FAF2
0x18009f596  mov     rcx, [rax+8]
0x18009f59a  test    rcx, rcx
0x18009f59d  jz      loc_18009FAF2
0x18009f5a3  cmp     [rcx+3Ch], r14d
0x18009f5a7  jz      short loc_18009F5EF
0x18009f5a9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f5ae  mov     rcx, [rax]
0x18009f5b1  cmp     [rcx+0Ch], r14b
0x18009f5b5  jz      short loc_18009F5E3
0x18009f5b7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f5bc  mov     rcx, [rax]
0x18009f5bf  cmp     [rcx+0B8h], r14
0x18009f5c6  jz      short loc_18009F5E3
0x18009f5c8  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f5cd  lea     rdx, aTheDeviceIsEnt; "The device is enterprise joined, not jo"...
0x18009f5d4  mov     rcx, [rax]
0x18009f5d7  mov     rcx, [rcx+0B8h]; Stream
0x18009f5de  call    fwprintf_s
0x18009f5e3  lea     rcx, aTheDeviceIsEnt; "The device is enterprise joined, not jo"...
0x18009f5ea  jmp     loc_18009FB33
0x18009f5ef  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f5f4  lea     rdi, aDsrcmdasynchel; "DsrCmdAsyncHelper::DeviceUpdate"
0x18009f5fb  lea     rsi, aSTenantIdS; "%s: Tenant ID: %s\n"
0x18009f602  mov     rcx, [rax]
0x18009f605  cmp     [rcx], r14b
0x18009f608  jz      short loc_18009F669
0x18009f60a  mov     rax, [rbp+Block]
0x18009f60e  mov     rdx, rdi
0x18009f611  mov     rcx, rsi; Format
0x18009f614  mov     r8, [rax+8]
0x18009f618  mov     r8, [r8+20h]
0x18009f61c  call    wprintf
0x18009f621  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f626  mov     rcx, [rax]
0x18009f629  cmp     [rcx+0Ch], r14b
0x18009f62d  jz      short loc_18009F669
0x18009f62f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f634  mov     rcx, [rax]
0x18009f637  cmp     [rcx+0B8h], r14
0x18009f63e  jz      short loc_18009F669
0x18009f640  mov     rax, [rbp+Block]
0x18009f644  mov     rcx, [rax+8]
0x18009f648  mov     rbx, [rcx+20h]
0x18009f64c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f651  mov     r9, rbx
0x18009f654  mov     r8, rdi
0x18009f657  mov     rdx, rsi; Format
0x18009f65a  mov     rcx, [rax]
0x18009f65d  mov     rcx, [rcx+0B8h]; Stream
0x18009f664  call    fwprintf_s
0x18009f669  mov     rax, [rbp+Block]
0x18009f66d  mov     rdx, rdi
0x18009f670  mov     rcx, rsi; unsigned __int16 *
0x18009f673  mov     r8, [rax+8]
0x18009f677  mov     r8, [r8+20h]
0x18009f67b  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009f680  lea     rcx, [rbp+IsMember]; IsMember
0x18009f684  mov     [rbp+IsMember], r14d
0x18009f688  call    ?IsCurrentUserElevated@@YAJAEAH@Z; IsCurrentUserElevated(int &)
0x18009f68d  mov     ebx, eax
0x18009f68f  test    eax, eax
0x18009f691  jns     short loc_18009F6E3
0x18009f693  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f698  mov     rcx, [rax]
0x18009f69b  cmp     [rcx+0Ch], r14b
0x18009f69f  jz      short loc_18009F6D0
0x18009f6a1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f6a6  mov     rcx, [rax]
0x18009f6a9  cmp     [rcx+0B8h], r14
0x18009f6b0  jz      short loc_18009F6D0
0x18009f6b2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f6b7  mov     r8d, ebx
0x18009f6ba  lea     rdx, aFailedToDeterm_1; "Failed to determine if the process has "...
0x18009f6c1  mov     rcx, [rax]
0x18009f6c4  mov     rcx, [rcx+0B8h]; Stream
0x18009f6cb  call    fwprintf_s
0x18009f6d0  lea     rcx, aFailedToDeterm_1; "Failed to determine if the process has "...
0x18009f6d7  mov     edx, ebx
0x18009f6d9  call    wprintf
0x18009f6de  jmp     loc_18009FB38
0x18009f6e3  cmp     [rbp+IsMember], r14d
0x18009f6e7  jnz     short loc_18009F739
0x18009f6e9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f6ee  mov     rcx, [rax]
0x18009f6f1  cmp     [rcx+0Ch], r14b
0x18009f6f5  jz      short loc_18009F723
0x18009f6f7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f6fc  mov     rcx, [rax]
0x18009f6ff  cmp     [rcx+0B8h], r14
0x18009f706  jz      short loc_18009F723
0x18009f708  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f70d  lea     rdx, aToUpdateAadJoi; "To update AAD joined device, you need t"...
0x18009f714  mov     rcx, [rax]
0x18009f717  mov     rcx, [rcx+0B8h]; Stream
0x18009f71e  call    fwprintf_s
0x18009f723  lea     rcx, aToUpdateAadJoi; "To update AAD joined device, you need t"...
0x18009f72a  call    wprintf
0x18009f72f  mov     ebx, 80070005h
0x18009f734  jmp     loc_18009FB38
0x18009f739  xor     r9d, r9d; lpName
0x18009f73c  xor     r8d, r8d; bInitialState
0x18009f73f  xor     edx, edx; bManualReset
0x18009f741  xor     ecx, ecx; lpEventAttributes
0x18009f743  call    cs:__imp_CreateEventW
0x18009f749  mov     [rbp+hHandle+8], rax
0x18009f74d  test    rax, rax
0x18009f750  jnz     loc_18009F7DC
0x18009f756  call    cs:__imp_GetLastError
0x18009f75c  mov     ebx, eax
0x18009f75e  test    eax, eax
0x18009f760  jle     short loc_18009F76B
0x18009f762  movzx   ebx, ax
0x18009f765  or      ebx, 80070000h
0x18009f76b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f770  lea     rsi, aSCreateeventwF; "%s: CreateEventW failed with error code"...
0x18009f777  mov     rcx, [rax]
0x18009f77a  cmp     [rcx], r14b
0x18009f77d  jz      short loc_18009F7C9
0x18009f77f  mov     r8d, ebx
0x18009f782  mov     rdx, rdi
0x18009f785  mov     rcx, rsi; Format
0x18009f788  call    wprintf
0x18009f78d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f792  mov     rcx, [rax]
0x18009f795  cmp     [rcx+0Ch], r14b
0x18009f799  jz      short loc_18009F7C9
0x18009f79b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f7a0  mov     rcx, [rax]
0x18009f7a3  cmp     [rcx+0B8h], r14
0x18009f7aa  jz      short loc_18009F7C9
0x18009f7ac  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f7b1  mov     r9d, ebx
0x18009f7b4  mov     r8, rdi
0x18009f7b7  mov     rdx, rsi; Format
0x18009f7ba  mov     rcx, [rax]
0x18009f7bd  mov     rcx, [rcx+0B8h]; Stream
0x18009f7c4  call    fwprintf_s
0x18009f7c9  mov     r8d, ebx
0x18009f7cc  mov     rdx, rdi
0x18009f7cf  mov     rcx, rsi; unsigned __int16 *
0x18009f7d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009f7d7  jmp     loc_18009F97A
0x18009f7dc  lea     rax, [rbp+hHandle]
0x18009f7e0  xor     edx, edx
0x18009f7e2  mov     [rsp+70h+var_40], rax
0x18009f7e7  xor     r9d, r9d
0x18009f7ea  lea     rax, ?DeviceUpdateCallback@DsrCmdAsyncHelper@@CAX_KJ@Z; DsrCmdAsyncHelper::DeviceUpdateCallback(unsigned __int64,long)
0x18009f7f1  xor     r8d, r8d
0x18009f7f4  mov     [rsp+70h+var_48], rax
0x18009f7f9  lea     ecx, [rdx+1]
0x18009f7fc  mov     [rsp+70h+var_50], 5
0x18009f804  call    ?UpdateDevice@DeviceUpdateController@@SAJW4_DSREG_JOIN_TYPE@@PEBGW4_DSREG_DEVICE_ATTRIBUTES@@1W4_COMPUTER_NAME_FORMAT@@P6AX_KJ@Z4@Z; DeviceUpdateController::UpdateDevice(_DSREG_JOIN_TYPE,ushort const *,_DSREG_DEVICE_ATTRIBUTES,ushort const *,_COMPUTER_NAME_FORMAT,void (*)(unsigned __int64,long),unsigned __int64)
0x18009f809  mov     ebx, eax
0x18009f80b  test    eax, eax
0x18009f80d  jns     short loc_18009F820
0x18009f80f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f814  lea     rsi, aSDsrbegindevic; "%s: DsrBeginDeviceUpdate failed with er"...
0x18009f81b  jmp     loc_18009FA49
0x18009f820  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f825  mov     rcx, [rax]
0x18009f828  cmp     [rcx+0Ch], r14b
0x18009f82c  jz      short loc_18009F85A
0x18009f82e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f833  mov     rdx, [rax]
0x18009f836  cmp     [rdx+0B8h], r14
0x18009f83d  jz      short loc_18009F85A
0x18009f83f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f844  lea     rdx, aCheckingAndUpd; "Checking and updating device if necessa"...
0x18009f84b  mov     rcx, [rax]
0x18009f84e  mov     rcx, [rcx+0B8h]; Stream
0x18009f855  call    fwprintf_s
0x18009f85a  lea     rcx, aCheckingAndUpd; "Checking and updating device if necessa"...
0x18009f861  call    wprintf
0x18009f866  mov     rcx, [rbp+hHandle+8]; hHandle
0x18009f86a  mov     edx, 57E40h; dwMilliseconds
0x18009f86f  call    cs:__imp_WaitForSingleObject
0x18009f875  mov     esi, eax
0x18009f877  test    eax, eax
0x18009f879  jz      loc_18009FA32
0x18009f87f  cmp     eax, 102h
0x18009f884  jz      loc_18009F9C8
0x18009f88a  cmp     eax, 0FFFFFFFFh
0x18009f88d  jz      short loc_18009F902
0x18009f88f  mov     ebx, 800705B4h
0x18009f894  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f899  mov     rcx, [rax]
0x18009f89c  cmp     [rcx], r14b
0x18009f89f  jz      short loc_18009F8F3
0x18009f8a1  mov     r8d, esi
0x18009f8a4  lea     rcx, aSWaitforsingle_7; "%s: WaitForSingleObject returned unexpe"...
0x18009f8ab  mov     rdx, rdi
0x18009f8ae  call    wprintf
0x18009f8b3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f8b8  mov     rcx, [rax]
0x18009f8bb  cmp     [rcx+0Ch], r14b
0x18009f8bf  jz      short loc_18009F8F3
0x18009f8c1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f8c6  mov     rcx, [rax]
0x18009f8c9  cmp     [rcx+0B8h], r14
0x18009f8d0  jz      short loc_18009F8F3
0x18009f8d2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f8d7  mov     r9d, esi
0x18009f8da  lea     rdx, aSWaitforsingle_7; "%s: WaitForSingleObject returned unexpe"...
0x18009f8e1  mov     r8, rdi
0x18009f8e4  mov     rcx, [rax]
0x18009f8e7  mov     rcx, [rcx+0B8h]; Stream
0x18009f8ee  call    fwprintf_s
0x18009f8f3  mov     r8d, esi
0x18009f8f6  lea     rcx, aSWaitforsingle_7; "%s: WaitForSingleObject returned unexpe"...
0x18009f8fd  jmp     loc_18009FAA1
0x18009f902  call    cs:__imp_GetLastError
0x18009f908  mov     ebx, eax
0x18009f90a  test    eax, eax
0x18009f90c  jle     short loc_18009F917
0x18009f90e  movzx   ebx, ax
0x18009f911  or      ebx, 80070000h
0x18009f917  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f91c  lea     rsi, aSWaitforsingle_8; "%s: WaitForSingleObject failed for DsrB"...
0x18009f923  mov     rcx, [rax]
0x18009f926  cmp     [rcx], r14b
0x18009f929  jz      short loc_18009F96F
0x18009f92b  mov     rdx, rdi
0x18009f92e  mov     rcx, rsi; Format
0x18009f931  call    wprintf
0x18009f936  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f93b  mov     rcx, [rax]
0x18009f93e  cmp     [rcx+0Ch], r14b
0x18009f942  jz      short loc_18009F96F
0x18009f944  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f949  mov     rdx, [rax]
0x18009f94c  cmp     [rdx+0B8h], r14
0x18009f953  jz      short loc_18009F96F
0x18009f955  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f95a  mov     r8, rdi
0x18009f95d  mov     rdx, rsi; Format
0x18009f960  mov     rcx, [rax]
0x18009f963  mov     rcx, [rcx+0B8h]; Stream
0x18009f96a  call    fwprintf_s
0x18009f96f  mov     rdx, rdi
0x18009f972  mov     rcx, rsi; unsigned __int16 *
0x18009f975  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009f97a  test    ebx, ebx
0x18009f97c  js      loc_18009FAA9
0x18009f982  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f987  mov     rcx, [rax]
0x18009f98a  cmp     [rcx+0Ch], r14b
0x18009f98e  jz      short loc_18009F9BC
0x18009f990  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f995  mov     rdx, [rax]
0x18009f998  cmp     [rdx+0B8h], r14
0x18009f99f  jz      short loc_18009F9BC
0x18009f9a1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f9a6  lea     rdx, aDeviceUpdateSu; "Device update succeeded.\n"
0x18009f9ad  mov     rcx, [rax]
0x18009f9b0  mov     rcx, [rcx+0B8h]; Stream
0x18009f9b7  call    fwprintf_s
0x18009f9bc  lea     rcx, aDeviceUpdateSu; "Device update succeeded.\n"
0x18009f9c3  jmp     loc_18009FB33
0x18009f9c8  mov     ebx, 800705B4h
0x18009f9cd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f9d2  lea     rsi, aSWaitforsingle_10; "%s: WaitForSingleObject timed out for D"...
0x18009f9d9  mov     rcx, [rax]
0x18009f9dc  cmp     [rcx], r14b
0x18009f9df  jz      short loc_18009FA25
0x18009f9e1  mov     rdx, rdi
0x18009f9e4  mov     rcx, rsi; Format
0x18009f9e7  call    wprintf
0x18009f9ec  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009f9f1  mov     rcx, [rax]
0x18009f9f4  cmp     [rcx+0Ch], r14b
0x18009f9f8  jz      short loc_18009FA25
  ... truncated ...
```
