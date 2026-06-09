# FaxSendThread(_FAX_SEND_ITEM *)

- ea: `0x14002f9f0`
- end: `0x140030515`
- name: `?FaxSendThread@@YAKPEAU_FAX_SEND_ITEM@@@Z`
- size: `2853`
- prototype: `unsigned int __fastcall(struct _FAX_SEND_ITEM *lpMem)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140002c43`
- `0x140003468`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004e68`
- `0x140024850`
- `0x14002efb8`
- `0x14002f9f0`
- `0x1400314a8`
- `0x140031b6c`
- `0x140034564`
- `0x14003465c`
- `0x140034dd0`
- `0x140034ef8`
- `0x1400351b0`
- `0x14004eedc`
- `0x14004f6c0`
- `0x14005584c`
- `0x140065dbc`
- `0x140067168`
- `0x14006ef88`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002fbb7`
- `KERNEL32!GetLastError` at `0x14002fdbf`
- `KERNEL32!GetLastError` at `0x14002fec5`
- `KERNEL32!GetLastError` at `0x1400300f3`
- `KERNEL32!GetLastError` at `0x1400301d0`
- `KERNEL32!GetLastError` at `0x1400302a6`
- `KERNEL32!GetLastError` at `0x140030314`
- `KERNEL32!GetLastError` at `0x140030365`
- `KERNEL32!GetLastError` at `0x1400303f3`
- `KERNEL32!GetLastError` at `0x1400304c4`
- `KERNEL32!GetLastError` at `0x14002fbb7`
- `KERNEL32!GetLastError` at `0x14002fdbf`
- `KERNEL32!GetLastError` at `0x14002fec5`
- `KERNEL32!GetLastError` at `0x1400300f3`
- `KERNEL32!GetLastError` at `0x1400301d0`
- `KERNEL32!GetLastError` at `0x1400302a6`
- `KERNEL32!GetLastError` at `0x140030314`
- `KERNEL32!GetLastError` at `0x140030365`
- `KERNEL32!GetLastError` at `0x1400303f3`
- `KERNEL32!GetLastError` at `0x1400304c4`
- `KERNEL32!EnterCriticalSection` at `0x14002fc6f`
- `KERNEL32!EnterCriticalSection` at `0x14002fd6c`
- `KERNEL32!EnterCriticalSection` at `0x14003005a`
- `KERNEL32!EnterCriticalSection` at `0x1400303a0`
- `KERNEL32!EnterCriticalSection` at `0x14002fc6f`
- `KERNEL32!EnterCriticalSection` at `0x14002fd6c`
- `KERNEL32!EnterCriticalSection` at `0x14003005a`
- `KERNEL32!EnterCriticalSection` at `0x1400303a0`
- `KERNEL32!LeaveCriticalSection` at `0x14002fc86`
- `KERNEL32!LeaveCriticalSection` at `0x14002fdfa`
- `KERNEL32!LeaveCriticalSection` at `0x14003019f`
- `KERNEL32!LeaveCriticalSection` at `0x14003042e`
- `KERNEL32!LeaveCriticalSection` at `0x14002fc86`
- `KERNEL32!LeaveCriticalSection` at `0x14002fdfa`
- `KERNEL32!LeaveCriticalSection` at `0x14003019f`
- `KERNEL32!LeaveCriticalSection` at `0x14003042e`
- `KERNEL32!GetLocalTime` at `0x14002fcf7`
- `KERNEL32!GetLocalTime` at `0x14002fcf7`
- `KERNEL32!SetThreadExecutionState` at `0x14002fa91`
- `KERNEL32!SetThreadExecutionState` at `0x14002fa91`

## pseudocode

```c
__int64 __fastcall FaxSendThread(struct _FAX_SEND_ITEM *lpMem)
{
  int v2; // ebx
  int v3; // r9d
  __int64 v4; // rcx
  __int64 v5; // r13
  CMapDeviceId *v6; // rax
  DWORD LastError; // eax
  __int64 v8; // rax
  LPVOID *v9; // rbx
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  int v13; // edx
  DWORD v14; // eax
  LPVOID *v15; // rax
  DWORD v16; // eax
  unsigned int DevStatus; // r8d
  struct _FSPI_JOB_STATUS *v18; // rbx
  unsigned int v19; // r8d
  int v20; // eax
  int v21; // edx
  DWORD v22; // eax
  __int64 v23; // rax
  void *v24; // rcx
  __int64 v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  unsigned int v30; // r13d
  DWORD v31; // eax
  DWORD v32; // eax
  __int64 v33; // r8
  DWORD v34; // eax
  int v35; // edx
  DWORD v36; // eax
  DWORD v37; // eax
  int v39; // [rsp+40h] [rbp-158h]
  int v40; // [rsp+44h] [rbp-154h]
  struct _FSPI_JOB_STATUS *v42; // [rsp+50h] [rbp-148h] BYREF
  unsigned __int16 **v43; // [rsp+58h] [rbp-140h]
  LPVOID lpMema; // [rsp+60h] [rbp-138h]
  LPVOID *v45; // [rsp+68h] [rbp-130h]
  LPVOID *v46; // [rsp+70h] [rbp-128h]
  LPVOID *v47; // [rsp+78h] [rbp-120h]
  LPVOID *v48; // [rsp+80h] [rbp-118h]
  int v49; // [rsp+90h] [rbp-108h] BYREF
  __int64 v50; // [rsp+98h] [rbp-100h]
  __int64 v51; // [rsp+A0h] [rbp-F8h]
  __int64 v52; // [rsp+A8h] [rbp-F0h]
  __int64 v53; // [rsp+B0h] [rbp-E8h]
  __int64 v54; // [rsp+B8h] [rbp-E0h]
  int v55; // [rsp+C0h] [rbp-D8h]
  char v56[8]; // [rsp+C4h] [rbp-D4h]
  __int64 v57; // [rsp+CCh] [rbp-CCh]
  __int128 v58; // [rsp+E0h] [rbp-B8h] BYREF
  __int128 v59; // [rsp+F0h] [rbp-A8h]
  struct _SYSTEMTIME SystemTime; // [rsp+100h] [rbp-98h] BYREF
  __int128 v61; // [rsp+110h] [rbp-88h] BYREF
  __int128 v62; // [rsp+120h] [rbp-78h]
  __int128 v63; // [rsp+130h] [rbp-68h]
  __int128 v64; // [rsp+140h] [rbp-58h]
  __int128 v65; // [rsp+150h] [rbp-48h]
  __int64 v66; // [rsp+160h] [rbp-38h]

  lpMema = lpMem;
  memset_0(&v49, 0, 0x48u);
  memset_0(&v61, 0, 0x58u);
  v42 = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  if ( !SetThreadExecutionState(0x80000001)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  v4 = *(_QWORD *)lpMem;
  v5 = *(_QWORD *)(*(_QWORD *)lpMem + 1104LL);
  v49 = 72;
  v48 = (LPVOID *)((char *)lpMem + 40);
  v51 = *((_QWORD *)lpMem + 5);
  v45 = (LPVOID *)((char *)lpMem + 24);
  v52 = *((_QWORD *)lpMem + 3);
  v47 = (LPVOID *)((char *)lpMem + 32);
  v53 = *((_QWORD *)lpMem + 4);
  v46 = (LPVOID *)((char *)lpMem + 16);
  v54 = *((_QWORD *)lpMem + 2);
  *(_QWORD *)v56 = 0;
  v57 = 0;
  UpdateDeviceJobsCounter(*(struct _LINE_INFO **)(v4 + 16), 1, 1, v3);
  if ( *(_QWORD *)(v5 + 72) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(_DWORD *)(v5 + 32),
      *(_QWORD *)(v5 + 72));
LABEL_25:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v5 + 32));
  }
  if ( (unsigned int)CreateTiffFileForJob((struct _JOB_QUEUE *)v5) )
    goto LABEL_25;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v5 + 32),
      LastError);
    v6 = WPP_GLOBAL_Control;
  }
  v2 = 1;
LABEL_26:
  if ( v2 )
  {
    v9 = (LPVOID *)lpMem;
  }
  else
  {
    v8 = StringDup(*(unsigned __int16 **)(v5 + 72));
    v9 = (LPVOID *)lpMem;
    v43 = (unsigned __int16 **)((char *)lpMem + 8);
    *((_QWORD *)lpMem + 1) = v8;
    if ( v8 )
    {
      v50 = v8;
      v55 = 0;
      EnterCriticalSection(&g_CsConfig);
      v10 = *((_DWORD *)g_pFaxConfig + 6);
      LeaveCriticalSection(&g_CsConfig);
      if ( v10 )
      {
        v58 = 0;
        v59 = 0;
        SystemTime = 0;
        LODWORD(v58) = 48;
        *(_QWORD *)&v59 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 464LL);
        *((_QWORD *)&v59 + 1) = *((_QWORD *)lpMem + 6);
        *((_QWORD *)&v58 + 1) = *v45;
        GetLocalTime(&SystemTime);
        v11 = FaxBrandDocument(*v43, (struct tag_FSPI_BRAND_INFO *)&v58);
        v12 = v11;
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              75,
              &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
              *(unsigned int *)(v5 + 32),
              v11);
          }
          if ( v12 == -2147024713 || v12 == -2147024816 )
          {
            EnterCriticalSection(&g_CsJob);
            FreeFSPIJobStatus((struct _FSPI_JOB_STATUS *)(*(_QWORD *)lpMem + 1120LL), v13);
            *(_DWORD *)(*(_QWORD *)lpMem + 1128LL) = 11;
            *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 12;
            if ( !(unsigned int)HandleFailedSendJob(*(struct _JOB_ENTRY **)lpMem)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = GetLastError();
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                76,
                &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
                *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
                v14);
            }
            LeaveCriticalSection(&g_CsJob);
            v15 = (LPVOID *)v43;
            v9 = (LPVOID *)lpMem;
            goto LABEL_125;
          }
        }
      }
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 16LL) + 72LL) = 536903680;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_lSSDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v50,
          *(_QWORD *)lpMem + 588LL,
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 16LL) + 32LL),
          v56[0]);
      }
      v40 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64 (__fastcall *)(void *, unsigned int, unsigned int, unsigned int)))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 16LL) + 40LL) + 2184LL))(
              *(_QWORD *)(*(_QWORD *)lpMem + 32LL),
              &v49,
              FaxSendCallback);
      if ( !v40
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
          *(unsigned int *)(v5 + 32),
          v16);
      }
      lpMema = 0;
      DevStatus = GetDevStatus(
                    *(void **)(*(_QWORD *)lpMem + 32LL),
                    *(struct _LINE_INFO **)(*(_QWORD *)lpMem + 16LL),
                    &v42);
      if ( DevStatus )
      {
        v39 = 1;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
            DevStatus);
        }
        v18 = v42;
      }
      else
      {
        v39 = 0;
        v18 = v42;
        v19 = *((_DWORD *)v42 + 2);
        if ( v19 == 10 || v19 <= 7 || v19 >= 0xE )
        {
          v39 = 1;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              80,
              &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
              *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
              v19);
          }
          lpMema = v18;
          v61 = *(_OWORD *)v18;
          v62 = *((_OWORD *)v18 + 1);
          v63 = *((_OWORD *)v18 + 2);
          v64 = *((_OWORD *)v18 + 3);
          v65 = *((_OWORD *)v18 + 4);
          v66 = *((_QWORD *)v18 + 10);
          if ( (*((_DWORD *)v18 + 1) & 0x10000000) != 0 )
          {
            HIDWORD(v61) = *((_DWORD *)v18 + 3);
            LODWORD(v62) = *((_DWORD *)v18 + 4);
          }
          v18 = 0;
        }
      }
      EnterCriticalSection(&g_CsJob);
      if ( v39 )
      {
        v18 = (struct _FSPI_JOB_STATUS *)&v61;
        LODWORD(v61) = 88;
        if ( v40 )
        {
          DWORD2(v61) = 9;
          if ( !HIDWORD(v61) )
            HIDWORD(v61) = 18;
        }
        else
        {
          DWORD2(v61) = 11;
          v20 = HIDWORD(v61);
          if ( !HIDWORD(v61) )
            v20 = 12;
          HIDWORD(v61) = v20;
        }
      }
      if ( !UpdateJobStatus(*(struct _JOB_ENTRY **)lpMem, v18) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            81,
            &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
            v22);
        }
        FreeFSPIJobStatus((struct _FSPI_JOB_STATUS *)(*(_QWORD *)lpMem + 1120LL), v21);
        v23 = *(_QWORD *)lpMem;
        if ( v40 )
        {
          *(_DWORD *)(v23 + 1128) = 9;
          *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 18;
        }
        else
        {
          *(_DWORD *)(v23 + 1128) = 11;
          *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 12;
        }
      }
      if ( v39 )
      {
        if ( !lpMema )
        {
LABEL_87:
          *(_DWORD *)(*(_QWORD *)lpMem + 1736LL) = 1;
          LeaveCriticalSection(&g_CsJob);
          v25 = *(_QWORD *)lpMem;
          if ( v40 )
          {
            v42 = 0;
            v27 = *(_QWORD *)(v25 + 1104);
            if ( *(_DWORD *)(v27 + 36) == 2 )
              v27 = *(_QWORD *)(v27 + 584);
            v28 = AllocateAndCopySid(*(PSID *)(v27 + 408), (LPVOID *)&v42);
            v29 = v28;
            if ( v28
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v28);
            }
            v30 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL);
            if ( !(unsigned int)HandleCompletedSendJob(*(struct _JOB_ENTRY **)lpMem)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v31 = GetLastError();
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                84,
                &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
                *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
                v31);
            }
            if ( !v29 )
            {
              if ( !CreateFaxEvent(0, 0x17u, v30, v42)
                && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v32 = GetLastError();
                WPP_SF_Dll(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, v33, 23, v30, v32);
              }
              pMemFree(v42);
            }
          }
          else if ( !(unsigned int)HandleFailedSendJob((struct _JOB_ENTRY *)v25)
                 && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = GetLastError();
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              82,
              &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
              *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
              v26);
          }
          v15 = (LPVOID *)v43;
          v9 = (LPVOID *)lpMem;
          goto LABEL_125;
        }
        v24 = lpMema;
      }
      else
      {
        v24 = v18;
      }
      pMemFree(v24);
      goto LABEL_87;
    }
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    v34 = GetLastError();
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
      v34);
  }
  EnterCriticalSection(&g_CsJob);
  FreeFSPIJobStatus((struct _FSPI_JOB_STATUS *)(*(_QWORD *)lpMem + 1120LL), v35);
  *(_DWORD *)(*(_QWORD *)lpMem + 1128LL) = 11;
  *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 12;
  if ( !(unsigned int)HandleFailedSendJob(*(struct _JOB_ENTRY **)lpMem)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v36 = GetLastError();
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL),
      v36);
  }
  LeaveCriticalSection(&g_CsJob);
  v15 = v9 + 1;
LABEL_125:
  pMemFree(*v15);
  pMemFree(*v46);
  pMemFree(*v45);
  pMemFree(*v47);
  pMemFree(*v48);
  pMemFree(v9[7]);
  pMemFree(v9[6]);
  pMemFree(v9[8]);
  pMemFree(v9[9]);
  pMemFree(v9);
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v37 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v37);
  }
  return 0;
}

```

## disassembly

```asm
0x14002f9f0  mov     [rsp+arg_8], rbx
0x14002f9f5  mov     [rsp+arg_10], rsi
0x14002f9fa  push    r12
0x14002f9fc  push    r13
0x14002f9fe  push    r14
0x14002fa00  sub     rsp, 180h
0x14002fa07  mov     rax, cs:__security_cookie
0x14002fa0e  xor     rax, rsp
0x14002fa11  mov     [rsp+198h+var_28], rax
0x14002fa19  mov     rsi, rcx
0x14002fa1c  mov     [rsp+198h+lpMem], rcx
0x14002fa21  mov     [rsp+198h+var_150], rcx
0x14002fa26  xor     edx, edx; Val
0x14002fa28  lea     r8d, [rdx+48h]; Size
0x14002fa2c  lea     rcx, [rsp+198h+var_108]; void *
0x14002fa34  call    memset_0
0x14002fa39  xor     edx, edx; Val
0x14002fa3b  lea     r8d, [rdx+58h]; Size
0x14002fa3f  lea     rcx, [rsp+198h+var_88]; void *
0x14002fa47  call    memset_0
0x14002fa4c  mov     [rsp+198h+var_148], 0
0x14002fa55  xor     ebx, ebx
0x14002fa57  lea     r12, WPP_GLOBAL_Control
0x14002fa5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fa65  mov     r14b, 4
0x14002fa68  cmp     rcx, r12
0x14002fa6b  jz      short loc_14002FA8C
0x14002fa6d  test    [rcx+1Ch], r14b
0x14002fa71  jz      short loc_14002FA8C
0x14002fa73  cmp     byte ptr [rcx+19h], 5
0x14002fa77  jb      short loc_14002FA8C
0x14002fa79  lea     edx, [rbx+44h]
0x14002fa7c  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fa83  mov     rcx, [rcx+10h]
0x14002fa87  call    WPP_SF_
0x14002fa8c  mov     ecx, 80000001h; esFlags
0x14002fa91  call    cs:__imp_SetThreadExecutionState
0x14002fa97  test    eax, eax
0x14002fa99  jnz     short loc_14002FAC6
0x14002fa9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002faa2  cmp     rcx, r12
0x14002faa5  jz      short loc_14002FAC6
0x14002faa7  test    [rcx+1Ch], r14b
0x14002faab  jz      short loc_14002FAC6
0x14002faad  cmp     byte ptr [rcx+19h], 2
0x14002fab1  jb      short loc_14002FAC6
0x14002fab3  lea     edx, [rax+45h]
0x14002fab6  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fabd  mov     rcx, [rcx+10h]
0x14002fac1  call    WPP_SF_
0x14002fac6  mov     rcx, [rsi]
0x14002fac9  mov     r13, [rcx+450h]
0x14002fad0  mov     [rsp+198h+var_108], 48h ; 'H'
0x14002fadb  lea     rax, [rsi+28h]
0x14002fadf  mov     [rsp+198h+var_118], rax
0x14002fae7  mov     rax, [rax]
0x14002faea  mov     [rsp+198h+var_F8], rax
0x14002faf2  lea     rax, [rsi+18h]
0x14002faf6  mov     [rsp+198h+var_130], rax
0x14002fafb  mov     rax, [rax]
0x14002fafe  mov     [rsp+198h+var_F0], rax
0x14002fb06  lea     rax, [rsi+20h]
0x14002fb0a  mov     [rsp+198h+var_120], rax
0x14002fb0f  mov     rax, [rax]
0x14002fb12  mov     [rsp+198h+var_E8], rax
0x14002fb1a  lea     rax, [rsi+10h]
0x14002fb1e  mov     [rsp+198h+var_128], rax
0x14002fb23  mov     rax, [rax]
0x14002fb26  mov     [rsp+198h+var_E0], rax
0x14002fb2e  mov     qword ptr [rsp+198h+var_D4], rbx
0x14002fb36  mov     [rsp+198h+var_CC], rbx
0x14002fb3e  mov     eax, 1
0x14002fb43  mov     r8d, eax; int
0x14002fb46  mov     edx, eax; int
0x14002fb48  mov     rcx, [rcx+10h]; struct _LINE_INFO *
0x14002fb4c  call    ?UpdateDeviceJobsCounter@@YAXPEAU_LINE_INFO@@HHH@Z; UpdateDeviceJobsCounter(_LINE_INFO *,int,int,int)
0x14002fb51  mov     rcx, [r13+48h]
0x14002fb55  test    rcx, rcx
0x14002fb58  jnz     loc_14002FBEF
0x14002fb5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fb65  cmp     rcx, r12
0x14002fb68  jz      short loc_14002FB8F
0x14002fb6a  test    [rcx+1Ch], r14b
0x14002fb6e  jz      short loc_14002FB8F
0x14002fb70  cmp     byte ptr [rcx+19h], 5
0x14002fb74  jb      short loc_14002FB8F
0x14002fb76  mov     edx, 46h ; 'F'
0x14002fb7b  mov     r9d, [r13+20h]
0x14002fb7f  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fb86  mov     rcx, [rcx+10h]
0x14002fb8a  call    WPP_SF_d
0x14002fb8f  mov     rcx, r13; struct _JOB_QUEUE *
0x14002fb92  call    ?CreateTiffFileForJob@@YAHPEAU_JOB_QUEUE@@@Z; CreateTiffFileForJob(_JOB_QUEUE *)
0x14002fb97  test    eax, eax
0x14002fb99  jnz     loc_14002FC25
0x14002fb9f  mov     rax, cs:WPP_GLOBAL_Control
0x14002fba6  cmp     rax, r12
0x14002fba9  jz      short loc_14002FBE8
0x14002fbab  test    [rax+1Ch], r14b
0x14002fbaf  jz      short loc_14002FBE8
0x14002fbb1  cmp     byte ptr [rax+19h], 2
0x14002fbb5  jb      short loc_14002FBE8
0x14002fbb7  call    cs:__imp_GetLastError
0x14002fbbd  mov     edx, 47h ; 'G'
0x14002fbc2  mov     dword ptr [rsp+198h+var_178], eax
0x14002fbc6  mov     r9d, [r13+20h]
0x14002fbca  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fbd8  mov     rcx, [rcx+10h]
0x14002fbdc  call    WPP_SF_dd
0x14002fbe1  mov     rax, cs:WPP_GLOBAL_Control
0x14002fbe8  mov     ebx, 1
0x14002fbed  jmp     short loc_14002FC2C
0x14002fbef  mov     rax, cs:WPP_GLOBAL_Control
0x14002fbf6  cmp     rax, r12
0x14002fbf9  jz      short loc_14002FC2C
0x14002fbfb  test    [rax+1Ch], r14b
0x14002fbff  jz      short loc_14002FC2C
0x14002fc01  cmp     byte ptr [rax+19h], 2
0x14002fc05  jb      short loc_14002FC2C
0x14002fc07  mov     edx, 48h ; 'H'
0x14002fc0c  mov     [rsp+198h+var_178], rcx
0x14002fc11  mov     r9d, [r13+20h]
0x14002fc15  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fc1c  mov     rcx, [rax+10h]
0x14002fc20  call    WPP_SF_DS
0x14002fc25  mov     rax, cs:WPP_GLOBAL_Control
0x14002fc2c  test    ebx, ebx
0x14002fc2e  jnz     loc_140030351
0x14002fc34  mov     rcx, [r13+48h]; unsigned __int16 *
0x14002fc38  call    StringDup
0x14002fc3d  mov     rbx, rsi
0x14002fc40  lea     rcx, [rsi+8]
0x14002fc44  mov     [rsp+198h+var_140], rcx
0x14002fc49  mov     [rcx], rax
0x14002fc4c  test    rax, rax
0x14002fc4f  jz      loc_140030348
0x14002fc55  mov     [rsp+198h+var_100], rax
0x14002fc5d  mov     [rsp+198h+var_D8], 0
0x14002fc68  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002fc6f  call    cs:__imp_EnterCriticalSection
0x14002fc75  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002fc7c  mov     ebx, [rax+18h]
0x14002fc7f  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002fc86  call    cs:__imp_LeaveCriticalSection
0x14002fc8c  test    ebx, ebx
0x14002fc8e  jz      loc_14002FE0D
0x14002fc94  xorps   xmm0, xmm0
0x14002fc97  movups  [rsp+198h+var_B8], xmm0
0x14002fc9f  movups  [rsp+198h+var_A8], xmm0
0x14002fca7  movups  xmmword ptr [rsp+198h+SystemTime.wYear], xmm0
0x14002fcaf  mov     dword ptr [rsp+198h+var_B8], 30h ; '0'
0x14002fcba  mov     rax, [rsi]
0x14002fcbd  mov     rcx, [rax+450h]
0x14002fcc4  mov     rax, [rcx+1D0h]
0x14002fccb  mov     qword ptr [rsp+198h+var_A8], rax
0x14002fcd3  mov     rax, [rsi+30h]
0x14002fcd7  mov     qword ptr [rsp+198h+var_A8+8], rax
0x14002fcdf  mov     rax, [rsp+198h+var_130]
0x14002fce4  mov     rax, [rax]
0x14002fce7  mov     qword ptr [rsp+198h+var_B8+8], rax
0x14002fcef  lea     rcx, [rsp+198h+SystemTime]; lpSystemTime
0x14002fcf7  call    cs:__imp_GetLocalTime
0x14002fcfd  lea     rdx, [rsp+198h+var_B8]; struct tag_FSPI_BRAND_INFO *
0x14002fd05  mov     rcx, [rsp+198h+var_140]
0x14002fd0a  mov     rcx, [rcx]; unsigned __int16 *
0x14002fd0d  call    FaxBrandDocument
0x14002fd12  mov     ebx, eax
0x14002fd14  test    eax, eax
0x14002fd16  jns     loc_14002FE0D
0x14002fd1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd23  cmp     rcx, r12
0x14002fd26  jz      short loc_14002FD51
0x14002fd28  test    [rcx+1Ch], r14b
0x14002fd2c  jz      short loc_14002FD51
0x14002fd2e  cmp     byte ptr [rcx+19h], 2
0x14002fd32  jb      short loc_14002FD51
0x14002fd34  mov     edx, 4Bh ; 'K'
0x14002fd39  mov     dword ptr [rsp+198h+var_178], eax
0x14002fd3d  mov     r9d, [r13+20h]
0x14002fd41  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fd48  mov     rcx, [rcx+10h]
0x14002fd4c  call    WPP_SF_dd
0x14002fd51  cmp     ebx, 800700B7h
0x14002fd57  jz      short loc_14002FD65
0x14002fd59  cmp     ebx, 80070050h
0x14002fd5f  jnz     loc_14002FE0D
0x14002fd65  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002fd6c  call    cs:__imp_EnterCriticalSection
0x14002fd72  mov     rcx, [rsi]
0x14002fd75  add     rcx, 460h; struct _FSPI_JOB_STATUS *
0x14002fd7c  call    ?FreeFSPIJobStatus@@YAHPEAU_FSPI_JOB_STATUS@@H@Z; FreeFSPIJobStatus(_FSPI_JOB_STATUS *,int)
0x14002fd81  mov     rax, [rsi]
0x14002fd84  mov     dword ptr [rax+468h], 0Bh
0x14002fd8e  mov     rax, [rsi]
0x14002fd91  mov     dword ptr [rax+46Ch], 0Ch
0x14002fd9b  mov     rcx, [rsi]; lpMem
0x14002fd9e  call    ?HandleFailedSendJob@@YAHPEAU_JOB_ENTRY@@@Z; HandleFailedSendJob(_JOB_ENTRY *)
0x14002fda3  test    eax, eax
0x14002fda5  jnz     short loc_14002FDF3
0x14002fda7  mov     rax, cs:WPP_GLOBAL_Control
0x14002fdae  cmp     rax, r12
0x14002fdb1  jz      short loc_14002FDF3
0x14002fdb3  test    [rax+1Ch], r14b
0x14002fdb7  jz      short loc_14002FDF3
0x14002fdb9  cmp     byte ptr [rax+19h], 2
0x14002fdbd  jb      short loc_14002FDF3
0x14002fdbf  call    cs:__imp_GetLastError
0x14002fdc5  mov     rdx, [rsi]
0x14002fdc8  mov     r9, [rdx+450h]
0x14002fdcf  mov     edx, 4Ch ; 'L'
0x14002fdd4  mov     dword ptr [rsp+198h+var_178], eax
0x14002fdd8  mov     r9d, [r9+20h]
0x14002fddc  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fde3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fdea  mov     rcx, [rcx+10h]
0x14002fdee  call    WPP_SF_dd
0x14002fdf3  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002fdfa  call    cs:__imp_LeaveCriticalSection
0x14002fe00  mov     rax, [rsp+198h+var_140]
0x14002fe05  mov     rbx, rsi
0x14002fe08  jmp     loc_140030438
0x14002fe0d  mov     [rsp+198h+var_154], 0
0x14002fe15  mov     rax, [rsi]
0x14002fe18  mov     rcx, [rax+10h]
0x14002fe1c  mov     dword ptr [rcx+48h], 20008000h
0x14002fe23  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe2a  cmp     rcx, r12
0x14002fe2d  jz      short loc_14002FE7B
0x14002fe2f  test    [rcx+1Ch], r14b
0x14002fe33  jz      short loc_14002FE7B
0x14002fe35  cmp     byte ptr [rcx+19h], 5
0x14002fe39  jb      short loc_14002FE7B
0x14002fe3b  mov     rax, [rsi]
0x14002fe3e  mov     rdx, [rax+10h]
0x14002fe42  lea     r8, [rax+24Ch]
0x14002fe49  mov     eax, dword ptr [rsp+198h+var_D4]
0x14002fe50  mov     dword ptr [rsp+198h+var_160], eax; char
0x14002fe54  mov     eax, [rdx+20h]
0x14002fe57  mov     dword ptr [rsp+198h+var_168], eax; char
0x14002fe5b  mov     [rsp+198h+var_170], r8; __int64
0x14002fe60  mov     rax, [rsp+198h+var_100]
0x14002fe68  mov     [rsp+198h+var_178], rax; __int64
0x14002fe6d  mov     r9d, [r13+20h]
0x14002fe71  mov     rcx, [rcx+10h]; LoggerHandle
0x14002fe75  call    WPP_SF_lSSDD
0x14002fe7a  nop
0x14002fe7b  mov     rcx, [rsi]
0x14002fe7e  mov     rax, [rcx+10h]
0x14002fe82  mov     rdx, [rax+28h]
0x14002fe86  mov     rax, [rdx+888h]
0x14002fe8d  lea     r8, ?FaxSendCallback@@YAHPEAXKKK@Z; FaxSendCallback(void *,ulong,ulong,ulong)
0x14002fe94  lea     rdx, [rsp+198h+var_108]
0x14002fe9c  mov     rcx, [rcx+20h]
0x14002fea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fea5  mov     [rsp+198h+var_154], eax
0x14002fea9  test    eax, eax
0x14002feab  jnz     short loc_14002FEEF
0x14002fead  mov     rcx, cs:WPP_GLOBAL_Control
0x14002feb4  cmp     rcx, r12
0x14002feb7  jz      short loc_14002FEEF
0x14002feb9  test    [rcx+1Ch], r14b
0x14002febd  jz      short loc_14002FEEF
0x14002febf  cmp     byte ptr [rcx+19h], 2
0x14002fec3  jb      short loc_14002FEEF
0x14002fec5  call    cs:__imp_GetLastError
0x14002fecb  mov     edx, 4Eh ; 'N'
0x14002fed0  mov     dword ptr [rsp+198h+var_178], eax
0x14002fed4  mov     r9d, [r13+20h]
0x14002fed8  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fedf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fee6  mov     rcx, [rcx+10h]
0x14002feea  call    WPP_SF_dd
0x14002feef  jmp     short loc_14002FF00
0x14002fef1  lea     r12, WPP_GLOBAL_Control
0x14002fef8  mov     r14b, 4
0x14002fefb  mov     rsi, [rsp+198h+lpMem]
0x14002ff00  mov     [rsp+198h+lpMem], 0
0x14002ff09  mov     rcx, [rsi]
0x14002ff0c  lea     r8, [rsp+198h+var_148]; struct _FSPI_JOB_STATUS **
0x14002ff11  mov     rdx, [rcx+10h]; struct _LINE_INFO *
0x14002ff15  mov     rcx, [rcx+20h]; void *
0x14002ff19  call    ?GetDevStatus@@YAKPEAXPEAU_LINE_INFO@@PEAPEAU_FSPI_JOB_STATUS@@@Z; GetDevStatus(void *,_LINE_INFO *,_FSPI_JOB_STATUS * *)
0x14002ff1e  mov     r8d, eax
0x14002ff21  test    eax, eax
0x14002ff23  jz      short loc_14002FF77
0x14002ff25  mov     [rsp+198h+var_158], 1
0x14002ff2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff34  cmp     rcx, r12
0x14002ff37  jz      short loc_14002FF6D
0x14002ff39  test    [rcx+1Ch], r14b
0x14002ff3d  jz      short loc_14002FF6D
0x14002ff3f  cmp     byte ptr [rcx+19h], 2
0x14002ff43  jb      short loc_14002FF6D
0x14002ff45  mov     rax, [rsi]
0x14002ff48  mov     r9, [rax+450h]
0x14002ff4f  mov     edx, 4Fh ; 'O'
0x14002ff54  mov     dword ptr [rsp+198h+var_178], r8d
0x14002ff59  mov     r9d, [r9+20h]
0x14002ff5d  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
  ... truncated ...
```
