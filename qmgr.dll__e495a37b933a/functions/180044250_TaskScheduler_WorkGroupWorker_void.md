# TaskScheduler::WorkGroupWorker(void)

- ea: `0x180044250`
- end: `0x180044dd8`
- name: `?WorkGroupWorker@TaskScheduler@@AEAAKXZ`
- size: `2952`
- prototype: `unsigned int __fastcall(TaskScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c15c0`

## callees

- `0x180016d60`
- `0x18002e5c0`
- `0x180039ef0`
- `0x180044250`
- `0x180044de0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800c158c`
- `0x1800f9948`
- `0x1800f996c`
- `0x18010f010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18004476e`
- `ntdll!NtQueryInformationThread` at `0x18004476e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044ad1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004468d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004468d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044674`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004429e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004431e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004444e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004448b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004429e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004431e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004444e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004448b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800446da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800446da`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180044444`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180044481`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180044444`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180044481`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800444e8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800444e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044736`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044736`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180044414`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180044414`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004463d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044d2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044d95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044dcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004463d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044d2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044d95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044dcb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004427e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044301`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004427e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800443ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800443f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004486c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800443ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800443f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004486c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d48`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800443b5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800443b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044d34`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044d34`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044922`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044935`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044952`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044965`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044922`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044935`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044952`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180044965`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448b6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448c2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448d9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448e5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180044905`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448b6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448c2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448d9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800448e5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180044905`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskScheduler::WorkGroupWorker(TaskScheduler *this)
{
  HANDLE EventW; // rax
  void *v3; // rbx
  unsigned int LastError; // ecx
  HANDLE v5; // rdi
  unsigned int v6; // ecx
  HRESULT v7; // eax
  unsigned int v8; // esi
  __int64 result; // rax
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // eax
  EVENT_LOG *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int64 v16; // r14
  _QWORD *v17; // r8
  _QWORD *i; // rax
  _QWORD *v19; // r10
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // r9
  bool v22; // cf
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // r9
  bool v25; // dl
  unsigned int j; // eax
  char v27; // al
  HANDLE *v28; // rcx
  __int64 v29; // rcx
  __int64 **v30; // r13
  __int64 *v31; // r14
  __int64 *v32; // r12
  void *v33; // r13
  void *v34; // rax
  PUCHAR SidSubAuthorityCount; // r14
  PUCHAR v36; // rax
  PUCHAR v37; // r14
  PUCHAR v38; // rax
  UCHAR k; // r14
  PDWORD SidSubAuthority; // r14
  PDWORD v41; // rax
  PDWORD v42; // r14
  PDWORD v43; // rax
  __int64 v44; // r14
  unsigned int v45; // edx
  unsigned __int64 v46; // r14
  _QWORD *v47; // r12
  _QWORD *v48; // r13
  __int64 v49; // rcx
  __int64 v50; // rax
  unsigned __int64 v51; // r13
  __int64 v52; // rax
  __int64 v53; // rcx
  ComError *v54; // rax
  __int64 *v55; // [rsp+30h] [rbp-428h]
  HANDLE Handles; // [rsp+38h] [rbp-420h] BYREF
  __int64 v57; // [rsp+40h] [rbp-418h]
  ComError *v58; // [rsp+50h] [rbp-408h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-3F8h] BYREF
  __int128 v60; // [rsp+68h] [rbp-3F0h]
  unsigned int v61; // [rsp+78h] [rbp-3E0h]
  int v62; // [rsp+7Ch] [rbp-3DCh]
  int v63; // [rsp+80h] [rbp-3D8h]
  void **v64; // [rsp+C0h] [rbp-398h] BYREF
  __int128 v65; // [rsp+C8h] [rbp-390h]
  unsigned int v66; // [rsp+D8h] [rbp-380h]
  int v67; // [rsp+DCh] [rbp-37Ch]
  int v68; // [rsp+E0h] [rbp-378h]
  void **v69; // [rsp+120h] [rbp-338h] BYREF
  __int128 v70; // [rsp+128h] [rbp-330h]
  int v71; // [rsp+138h] [rbp-320h]
  int v72; // [rsp+13Ch] [rbp-31Ch]
  int v73; // [rsp+140h] [rbp-318h]
  void **v74; // [rsp+180h] [rbp-2D8h] BYREF
  __int128 v75; // [rsp+188h] [rbp-2D0h]
  int v76; // [rsp+198h] [rbp-2C0h]
  int v77; // [rsp+19Ch] [rbp-2BCh]
  int v78; // [rsp+1A0h] [rbp-2B8h]
  void **v79; // [rsp+1E0h] [rbp-278h] BYREF
  __int128 v80; // [rsp+1E8h] [rbp-270h]
  int v81; // [rsp+1F8h] [rbp-260h]
  int v82; // [rsp+1FCh] [rbp-25Ch]
  int v83; // [rsp+200h] [rbp-258h]
  void **v84; // [rsp+240h] [rbp-218h] BYREF
  __int128 v85; // [rsp+248h] [rbp-210h]
  int v86; // [rsp+258h] [rbp-200h]
  int v87; // [rsp+25Ch] [rbp-1FCh]
  int v88; // [rsp+260h] [rbp-1F8h]
  void **v89; // [rsp+2A0h] [rbp-1B8h] BYREF
  __int128 v90; // [rsp+2A8h] [rbp-1B0h]
  int v91; // [rsp+2B8h] [rbp-1A0h]
  int v92; // [rsp+2BCh] [rbp-19Ch]
  int v93; // [rsp+2C0h] [rbp-198h]
  void **v94; // [rsp+300h] [rbp-158h] BYREF
  __int128 v95; // [rsp+308h] [rbp-150h]
  int v96; // [rsp+318h] [rbp-140h]
  int v97; // [rsp+31Ch] [rbp-13Ch]
  int v98; // [rsp+320h] [rbp-138h]
  void **v99; // [rsp+360h] [rbp-F8h] BYREF
  __int128 v100; // [rsp+368h] [rbp-F0h]
  int v101; // [rsp+378h] [rbp-E0h]
  int v102; // [rsp+37Ch] [rbp-DCh]
  int v103; // [rsp+380h] [rbp-D8h]
  __int64 v104; // [rsp+3C0h] [rbp-98h] BYREF
  __int64 ThreadInformation; // [rsp+468h] [rbp+10h] BYREF
  int v106; // [rsp+470h] [rbp+18h] BYREF
  HANDLE nSubAuthority; // [rsp+478h] [rbp+20h]

  v106 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  try
  {
    v3 = EventW;
    nSubAuthority = EventW;
    if ( !EventW )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v60 = 0;
      pExceptionObject = &ComError::`vftable';
      v61 = LastError;
      v62 = 2256;
      v63 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v5 = CreateEventW(0, 1, 0, 0);
    if ( !v5 )
    {
      if ( (int)GetLastError() > 0 )
        v6 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v6 = GetLastError();
      v65 = 0;
      v64 = &ComError::`vftable';
      v66 = v6;
      v67 = 2256;
      v68 = 1;
      throw (ComError *)&v64;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    v7 = CoInitializeEx(0, 0);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids,
          (unsigned int)v7);
      CloseHandle(v5);
      CloseHandle(v3);
      return v8;
    }
    v10 = *((_QWORD *)this + 17);
    SetEvent(*((HANDLE *)this + 16));
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !ResetEvent(v3) )
        {
          v11 = GetLastError();
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v11);
        }
        if ( !ResetEvent(v5) )
        {
          v12 = GetLastError();
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v12);
        }
        Handles = *(HANDLE *)(v10 + 96);
        v57 = *((_QWORD *)this + 2);
        if ( WaitForMultipleObjectsEx(2u, &Handles, 1, 0x7530u, 0) == 258 )
          break;
        if ( *((_BYTE *)this + 8) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v14 = 59;
            goto LABEL_36;
          }
          goto LABEL_128;
        }
        v15 = *(_QWORD *)(v10 + 24);
        v16 = v15 - 8;
        if ( !v15 )
          v16 = 0;
        *(_QWORD *)(v16 + 88) = 0;
        if ( *(_QWORD *)(v16 + 24) == v10 + 16 && *(_QWORD *)(v16 + 24) )
        {
          **(_QWORD **)(v16 + 16) = *(_QWORD *)(v16 + 8);
          *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8LL) = *(_QWORD *)(v16 + 16);
          --*(_QWORD *)(*(_QWORD *)(v16 + 24) + 24LL);
          *(_QWORD *)(v16 + 8) = v16 + 8;
          *(_QWORD *)(v16 + 16) = v16 + 8;
          *(_QWORD *)(v16 + 24) = 0;
        }
        v17 = (_QWORD *)(v10 + 56);
        for ( i = *(_QWORD **)(v10 + 64); i != v17; i = (_QWORD *)i[1] )
        {
          v19 = i - 1;
          if ( !i )
            v19 = 0;
          v20 = v19[5];
          v21 = *(_QWORD *)(v16 + 40);
          v22 = v20 < v21;
          if ( v20 == v21 && (v23 = v19[4], v24 = *(_QWORD *)(v16 + 32), v22 = v23 < v24, v23 == v24) )
          {
            if ( (unsigned __int64)v19 >= v16 )
              break;
          }
          else if ( !v22 )
          {
            break;
          }
        }
        *(_QWORD *)(v16 + 16) = i;
        *(_QWORD *)(v16 + 8) = *i;
        *(_QWORD *)(v16 + 24) = i[2];
        *i = v16 + 8;
        *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8LL) = v16 + 8;
        ++*(_QWORD *)(v10 + 80);
        *(_QWORD *)(v16 + 88) = v17;
        *(_DWORD *)(v16 + 80) = 2;
        *(_QWORD *)(v16 + 56) = v5;
        *(_QWORD *)(v16 + 48) = v3;
        *(_QWORD *)(v16 + 64) = &v106;
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 112));
        ReleaseMutex(*((HANDLE *)this + 2));
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v16);
        TlsSetValue(*((_DWORD *)this + 13), (LPVOID)v16);
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v16 + 8LL))(v16);
        if ( TlsGetValue(*((_DWORD *)this + 13)) )
          TaskScheduler::CompleteWorkItem(this, v25);
        for ( j = v106; v106 > 0; j = v106 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, j);
          Sleep(1u);
        }
        _InterlockedDecrement((volatile signed __int32 *)(v10 + 112));
      }
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
      WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF);
      if ( *(_QWORD *)(v10 + 40) )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
      }
      else
      {
        LODWORD(ThreadInformation) = 0;
        NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIsIoPending, &ThreadInformation, 4u, 0);
        if ( !(_DWORD)ThreadInformation )
        {
          v27 = *((_BYTE *)this + 8);
          if ( *(_DWORD *)(v10 + 104) == 1 )
          {
            if ( v27 )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
              {
                if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
                {
                  WPP_SF_q(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    62,
                    WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids,
                    v10);
                  v13 = WPP_GLOBAL_Control;
                }
                if ( v13 != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)v13 + 28) < 0 )
                {
                  v14 = 63;
                  goto LABEL_36;
                }
              }
              goto LABEL_128;
            }
            if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v10);
            v28 = *(HANDLE **)(v10 + 120);
            if ( !v28 )
            {
              v70 = 0;
              v69 = &ComError::`vftable';
              v71 = -2147023537;
              v72 = 53;
              v73 = 1;
              throw (ComError *)&v69;
            }
            CloseHandle(*v28);
            v30 = (__int64 **)((char *)this + 104);
            v31 = (__int64 *)*((_QWORD *)this + 13);
            v55 = v31;
            v32 = (__int64 *)v31[1];
            HIDWORD(v57) = 0;
            if ( *((_BYTE *)v32 + 25) )
            {
LABEL_94:
              if ( *((_BYTE *)v31 + 25) || (unsigned __int8)CSidSorter::operator()(v29, v10, v31 + 4) )
                v31 = *v30;
              v44 = std::_Tree_val<std::_Tree_simple_types<std::pair<SidHandle const,TaskScheduler::TaskSchedulerWorkGroup *>>>::_Extract(
                      v30,
                      v31);
              SidHandle::~SidHandle((SidHandle *)(v44 + 32));
              operator delete((void *)v44, 0x38u);
              TaskScheduler::TaskSchedulerWorkGroup::`scalar deleting destructor'(
                (TaskScheduler::TaskSchedulerWorkGroup *)v10,
                v45);
              goto LABEL_128;
            }
            while ( 2 )
            {
              v33 = (void *)v32[4];
              v34 = *(void **)v10;
              Handles = *(HANDLE *)v10;
              if ( v33 && v34 )
              {
                SidSubAuthorityCount = GetSidSubAuthorityCount(v34);
                v36 = GetSidSubAuthorityCount(v33);
                v29 = *SidSubAuthorityCount;
                if ( *v36 >= (unsigned __int8)v29 )
                {
                  v37 = GetSidSubAuthorityCount(Handles);
                  v38 = GetSidSubAuthorityCount(v33);
                  v29 = *v37;
                  if ( *v38 <= (unsigned __int8)v29 )
                  {
                    for ( k = 0; ; k = ThreadInformation + 1 )
                    {
                      LOBYTE(ThreadInformation) = k;
                      if ( k >= *GetSidSubAuthorityCount(v33) )
                        break;
                      LODWORD(nSubAuthority) = k;
                      SidSubAuthority = GetSidSubAuthority(Handles, k);
                      v41 = GetSidSubAuthority(v33, (DWORD)nSubAuthority);
                      v29 = *SidSubAuthority;
                      if ( *v41 < (unsigned int)v29 )
                        goto LABEL_98;
                      v42 = GetSidSubAuthority(Handles, (DWORD)nSubAuthority);
                      v43 = GetSidSubAuthority(v33, (DWORD)nSubAuthority);
                      v29 = *v42;
                      if ( *v43 > (unsigned int)v29 )
                        break;
                    }
                  }
LABEL_91:
                  v31 = v32;
                  v55 = v32;
LABEL_92:
                  v32 = (__int64 *)*v32;
                  if ( *((_BYTE *)v32 + 25) )
                  {
                    v30 = (__int64 **)((char *)this + 104);
                    goto LABEL_94;
                  }
                  continue;
                }
LABEL_98:
                v31 = v55;
              }
              else if ( (__int64)v33 >= (__int64)v34 )
              {
                goto LABEL_91;
              }
              break;
            }
            v32 += 2;
            goto LABEL_92;
          }
          if ( v27 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
            {
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v10);
                v13 = WPP_GLOBAL_Control;
              }
              if ( v13 != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)v13 + 28) < 0 )
              {
                v14 = 66;
LABEL_36:
                WPP_SF_(*((_QWORD *)v13 + 2), v14, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
              }
            }
          }
          else
          {
            v46 = 0;
            v47 = (_QWORD *)(v10 + 128);
            v48 = (_QWORD *)(v10 + 128);
            while ( v46 < *(unsigned int *)(v10 + 104) )
            {
              v48 = (_QWORD *)(v10 + 128);
              ThreadInformation = *(_QWORD *)(v10 + 128);
              if ( !ThreadInformation )
              {
                v75 = 0;
                v74 = &ComError::`vftable';
                v76 = -2147023537;
                v77 = 53;
                v78 = 1;
                throw (ComError *)&v74;
              }
              if ( GetCurrentThreadId() == *(_DWORD *)(ThreadInformation + 4 * v46) )
                break;
              ++v46;
            }
            if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control )
            {
              v47 = v48;
            }
            else if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids,
                (unsigned int)v46);
            }
            v49 = *(_QWORD *)(v10 + 120);
            if ( !v49 )
            {
              v80 = 0;
              v79 = &ComError::`vftable';
              v81 = -2147023537;
              v82 = 53;
              v83 = 1;
              throw (ComError *)&v79;
            }
            CloseHandle(*(HANDLE *)(v49 + 8 * v46));
            v50 = *(_QWORD *)(v10 + 120);
            if ( !v50 )
            {
              v85 = 0;
              v84 = &ComError::`vftable';
              v86 = -2147023537;
              v87 = 53;
              v88 = 1;
              throw (ComError *)&v84;
            }
            v51 = *(unsigned int *)(v10 + 104) - v46;
            memmove_0((void *)(v50 + 8 * v46), (const void *)(v50 + 8 * v46 + 8), 8 * v51 - 8);
            if ( !*v47 )
            {
              v90 = 0;
              v89 = &ComError::`vftable';
              v91 = -2147023537;
              v92 = 53;
              v93 = 1;
              throw (ComError *)&v89;
            }
            memmove_0((void *)(*v47 + 4 * v46), (const void *)(*v47 + 4 * v46 + 4), 4 * v51 - 4);
            v52 = (unsigned int)(*(_DWORD *)(v10 + 104) - 1);
            *(_DWORD *)(v10 + 104) = v52;
            v53 = *(_QWORD *)(v10 + 120);
            if ( !v53 )
            {
              v95 = 0;
              v94 = &ComError::`vftable';
              v96 = -2147023537;
              v97 = 53;
              v98 = 1;
              throw (ComError *)&v94;
            }
            *(_QWORD *)(v53 + 8 * v52) = 0;
            if ( !*v47 )
            {
              v100 = 0;
              v99 = &ComError::`vftable';
              v101 = -2147023537;
              v102 = 53;
              v103 = 1;
              throw (ComError *)&v99;
            }
            *(_DWORD *)(*v47 + 4LL * *(unsigned int *)(v10 + 104)) = 0;
          }
LABEL_128:
          ReleaseMutex(*((HANDLE *)this + 2));
          CoUninitialize();
          CloseHandle(v5);
          CloseHandle(v3);
          return 0;
        }
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
      }
      ReleaseMutex(*((HANDLE *)this + 2));
    }
  }
  catch ( ComError *v58 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    v54 = ComError::ComError((ComError *)&v104, v58);
    LogException(v54);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180044250  push    rbx
0x180044252  push    rsi
0x180044253  push    rdi
0x180044254  push    r12
0x180044256  push    r13
0x180044258  push    r14
0x18004425a  push    r15
0x18004425c  sub     rsp, 420h
0x180044263  mov     r15, rcx
0x180044266  xor     r12d, r12d
0x180044269  mov     [rsp+458h+arg_10], r12d
0x180044271  xor     r9d, r9d; lpName
0x180044274  xor     r8d, r8d; bInitialState
0x180044277  mov     edx, 1; bManualReset
0x18004427c  xor     ecx, ecx; lpEventAttributes
0x18004427e  call    cs:__imp_CreateEventW
0x180044284  mov     rbx, rax
0x180044287  mov     [rsp+458h+nSubAuthority], rax
0x18004428f  test    rax, rax
0x180044292  jnz     short loc_1800442F4
0x180044294  call    cs:__imp_GetLastError
0x18004429a  test    eax, eax
0x18004429c  jg      short loc_1800442A8
0x18004429e  call    cs:__imp_GetLastError
0x1800442a4  mov     ecx, eax
0x1800442a6  jmp     short loc_1800442B7
0x1800442a8  call    cs:__imp_GetLastError
0x1800442ae  movzx   ecx, ax
0x1800442b1  or      ecx, 80070000h
0x1800442b7  xorps   xmm0, xmm0
0x1800442ba  movups  [rsp+458h+var_3F0], xmm0
0x1800442bf  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800442c6  mov     [rsp+458h+pExceptionObject], rax
0x1800442cb  mov     [rsp+458h+var_3E0], ecx
0x1800442cf  mov     [rsp+458h+var_3DC], 8D0h
0x1800442d7  mov     [rsp+458h+var_3D8], 1
0x1800442e2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800442e9  lea     rcx, [rsp+458h+pExceptionObject]; pExceptionObject
0x1800442ee  call    _CxxThrowException_0
0x1800442f4  xor     r9d, r9d; lpName
0x1800442f7  xor     r8d, r8d; bInitialState
0x1800442fa  mov     edx, 1; bManualReset
0x1800442ff  xor     ecx, ecx; lpEventAttributes
0x180044301  call    cs:__imp_CreateEventW
0x180044307  mov     rdi, rax
0x18004430a  mov     [rsp+458h+var_428], rax
0x18004430f  test    rax, rax
0x180044312  jnz     short loc_180044383
0x180044314  call    cs:__imp_GetLastError
0x18004431a  test    eax, eax
0x18004431c  jg      short loc_180044328
0x18004431e  call    cs:__imp_GetLastError
0x180044324  mov     ecx, eax
0x180044326  jmp     short loc_180044337
0x180044328  call    cs:__imp_GetLastError
0x18004432e  movzx   ecx, ax
0x180044331  or      ecx, 80070000h
0x180044337  xorps   xmm0, xmm0
0x18004433a  movups  [rsp+458h+var_390], xmm0
0x180044342  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180044349  mov     [rsp+458h+var_398], rax
0x180044351  mov     [rsp+458h+var_380], ecx
0x180044358  mov     [rsp+458h+var_37C], 8D0h
0x180044363  mov     [rsp+458h+var_378], 1
0x18004436e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180044375  lea     rcx, [rsp+458h+var_398]; pExceptionObject
0x18004437d  call    _CxxThrowException_0
0x180044383  lea     r13, WPP_GLOBAL_Control
0x18004438a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044391  cmp     rcx, r13
0x180044394  jz      short loc_1800443B1
0x180044396  test    byte ptr [rcx+1Ch], 80h
0x18004439a  jz      short loc_1800443B1
0x18004439c  mov     edx, 35h ; '5'
0x1800443a1  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x1800443a8  mov     rcx, [rcx+10h]
0x1800443ac  call    WPP_SF_
0x1800443b1  xor     edx, edx; dwCoInit
0x1800443b3  xor     ecx, ecx; pvReserved
0x1800443b5  call    cs:__imp_CoInitializeEx
0x1800443bb  mov     esi, eax
0x1800443bd  test    eax, eax
0x1800443bf  jns     short loc_180044406
0x1800443c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800443c8  cmp     rcx, r13
0x1800443cb  jz      short loc_1800443EC
0x1800443cd  test    byte ptr [rcx+1Ch], 4
0x1800443d1  jz      short loc_1800443EC
0x1800443d3  mov     edx, 36h ; '6'
0x1800443d8  mov     r9d, eax
0x1800443db  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x1800443e2  mov     rcx, [rcx+10h]
0x1800443e6  call    WPP_SF_d
0x1800443eb  nop
0x1800443ec  mov     rcx, rdi; hObject
0x1800443ef  call    cs:__imp_CloseHandle
0x1800443f5  nop
0x1800443f6  mov     rcx, rbx; hObject
0x1800443f9  call    cs:__imp_CloseHandle
0x1800443ff  mov     eax, esi
0x180044401  jmp     loc_180044D57
0x180044406  mov     rsi, [r15+88h]
0x18004440d  mov     rcx, [r15+80h]; hEvent
0x180044414  call    cs:__imp_SetEvent
0x18004441a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044421  cmp     rcx, r13
0x180044424  jz      short loc_180044441
0x180044426  test    byte ptr [rcx+1Ch], 80h
0x18004442a  jz      short loc_180044441
0x18004442c  mov     edx, 37h ; '7'
0x180044431  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180044438  mov     rcx, [rcx+10h]
0x18004443c  call    WPP_SF_
0x180044441  mov     rcx, rbx; hEvent
0x180044444  call    cs:__imp_ResetEvent
0x18004444a  test    eax, eax
0x18004444c  jnz     short loc_18004447E
0x18004444e  call    cs:__imp_GetLastError
0x180044454  mov     rcx, cs:WPP_GLOBAL_Control
0x18004445b  cmp     rcx, r13
0x18004445e  jz      short loc_18004447E
0x180044460  test    byte ptr [rcx+1Ch], 4
0x180044464  jz      short loc_18004447E
0x180044466  mov     edx, 0Bh
0x18004446b  mov     r9d, eax
0x18004446e  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180044475  mov     rcx, [rcx+10h]
0x180044479  call    WPP_SF_d
0x18004447e  mov     rcx, rdi; hEvent
0x180044481  call    cs:__imp_ResetEvent
0x180044487  test    eax, eax
0x180044489  jnz     short loc_1800444BB
0x18004448b  call    cs:__imp_GetLastError
0x180044491  mov     rcx, cs:WPP_GLOBAL_Control
0x180044498  cmp     rcx, r13
0x18004449b  jz      short loc_1800444BB
0x18004449d  test    byte ptr [rcx+1Ch], 4
0x1800444a1  jz      short loc_1800444BB
0x1800444a3  mov     edx, 0Bh
0x1800444a8  mov     r9d, eax
0x1800444ab  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800444b2  mov     rcx, [rcx+10h]
0x1800444b6  call    WPP_SF_d
0x1800444bb  mov     rax, [rsi+60h]
0x1800444bf  mov     [rsp+458h+Handles], rax
0x1800444c4  mov     rax, [r15+10h]
0x1800444c8  mov     [rsp+458h+var_418], rax
0x1800444cd  mov     [rsp+458h+bAlertable], r12d; bAlertable
0x1800444d2  mov     r9d, 7530h; dwMilliseconds
0x1800444d8  mov     r8d, 1; bWaitAll
0x1800444de  lea     rdx, [rsp+458h+Handles]; lpHandles
0x1800444e3  mov     ecx, 2; nCount
0x1800444e8  call    cs:__imp_WaitForMultipleObjectsEx
0x1800444ee  cmp     eax, 102h
0x1800444f3  jz      loc_180044706
0x1800444f9  cmp     byte ptr [r15+8], 0
0x1800444fe  jz      short loc_180044534
0x180044500  mov     rcx, cs:WPP_GLOBAL_Control
0x180044507  cmp     rcx, r13
0x18004450a  jz      loc_180044D2A
0x180044510  test    byte ptr [rcx+1Ch], 80h
0x180044514  jz      loc_180044D2A
0x18004451a  mov     edx, 3Bh ; ';'
0x18004451f  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180044526  mov     rcx, [rcx+10h]
0x18004452a  call    WPP_SF_
0x18004452f  jmp     loc_180044D2A
0x180044534  mov     rcx, [rsi+18h]
0x180044538  lea     r14, [rcx-8]
0x18004453c  test    rcx, rcx
0x18004453f  cmovz   r14, r12
0x180044543  mov     [r14+58h], r12
0x180044547  lea     rax, [rsi+10h]
0x18004454b  cmp     [r14+18h], rax
0x18004454f  jnz     short loc_180044584
0x180044551  lea     rdx, [r14+8]
0x180044555  cmp     qword ptr [rdx+10h], 0
0x18004455a  jz      short loc_180044584
0x18004455c  mov     rcx, [rdx+8]
0x180044560  mov     rax, [rdx]
0x180044563  mov     [rcx], rax
0x180044566  mov     rcx, [rdx]
0x180044569  mov     rax, [rdx+8]
0x18004456d  mov     [rcx+8], rax
0x180044571  mov     rax, [rdx+10h]
0x180044575  dec     qword ptr [rax+18h]
0x180044579  mov     [rdx], rdx
0x18004457c  mov     [rdx+8], rdx
0x180044580  mov     [rdx+10h], r12
0x180044584  lea     r8, [rsi+38h]
0x180044588  mov     rax, [r8+8]
0x18004458c  cmp     rax, r8
0x18004458f  jz      short loc_1800445F1
0x180044591  lea     r10, [rax-8]
0x180044595  test    rax, rax
0x180044598  cmovz   r10, r12
0x18004459c  mov     edx, [r10+2Ch]
0x1800445a0  shl     rdx, 20h
0x1800445a4  mov     ecx, [r10+28h]
0x1800445a8  or      rdx, rcx
0x1800445ab  mov     r9d, [r14+2Ch]
0x1800445af  shl     r9, 20h
0x1800445b3  mov     ecx, [r14+28h]
0x1800445b7  or      r9, rcx
0x1800445ba  cmp     rdx, r9
0x1800445bd  jnz     short loc_1800445E6
0x1800445bf  mov     edx, [r10+24h]
0x1800445c3  shl     rdx, 20h
0x1800445c7  mov     ecx, [r10+20h]
0x1800445cb  or      rdx, rcx
0x1800445ce  mov     r9d, [r14+24h]
0x1800445d2  shl     r9, 20h
0x1800445d6  mov     ecx, [r14+20h]
0x1800445da  or      r9, rcx
0x1800445dd  cmp     rdx, r9
0x1800445e0  jz      loc_1800446F4
0x1800445e6  setb    cl
0x1800445e9  test    cl, cl
0x1800445eb  jnz     loc_1800446FD
0x1800445f1  mov     [r14+10h], rax
0x1800445f5  lea     rdx, [r14+8]
0x1800445f9  mov     rcx, [rax]
0x1800445fc  mov     [rdx], rcx
0x1800445ff  mov     rcx, [rax+10h]
0x180044603  mov     [r14+18h], rcx
0x180044607  mov     [rax], rdx
0x18004460a  mov     rax, [rdx]
0x18004460d  mov     [rax+8], rdx
0x180044611  inc     qword ptr [r8+18h]
0x180044615  mov     [r14+58h], r8
0x180044619  mov     dword ptr [r14+50h], 2
0x180044621  mov     [r14+38h], rdi
0x180044625  mov     [r14+30h], rbx
0x180044629  lea     rax, [rsp+458h+arg_10]
0x180044631  mov     [r14+40h], rax
0x180044635  lock inc dword ptr [rsi+70h]
0x180044639  mov     rcx, [r15+10h]; hMutex
0x18004463d  call    cs:__imp_ReleaseMutex
0x180044643  mov     rcx, cs:WPP_GLOBAL_Control
0x18004464a  cmp     rcx, r13
0x18004464d  jz      short loc_18004466D
0x18004464f  test    byte ptr [rcx+1Ch], 80h
0x180044653  jz      short loc_18004466D
0x180044655  mov     edx, 3Ch ; '<'
0x18004465a  mov     r9, r14
0x18004465d  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180044664  mov     rcx, [rcx+10h]
0x180044668  call    WPP_SF_q
0x18004466d  mov     rdx, r14; lpTlsValue
0x180044670  mov     ecx, [r15+34h]; dwTlsIndex
0x180044674  call    cs:__imp_TlsSetValue
0x18004467a  mov     rax, [r14]
0x18004467d  mov     rcx, r14
0x180044680  mov     rax, [rax+8]
0x180044684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044689  mov     ecx, [r15+34h]; dwTlsIndex
0x18004468d  call    cs:__imp_TlsGetValue
0x180044693  test    rax, rax
0x180044696  jz      short loc_1800446A0
0x180044698  mov     rcx, r15; this
0x18004469b  call    ?CompleteWorkItem@TaskScheduler@@AEAAX_N@Z; TaskScheduler::CompleteWorkItem(bool)
0x1800446a0  mov     eax, [rsp+458h+arg_10]
0x1800446a7  test    eax, eax
0x1800446a9  jle     short loc_1800446EB
0x1800446ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446b2  cmp     rcx, r13
0x1800446b5  jz      short loc_1800446D5
0x1800446b7  test    byte ptr [rcx+1Ch], 1
0x1800446bb  jz      short loc_1800446D5
0x1800446bd  mov     edx, 3Dh ; '='
0x1800446c2  mov     r9d, eax
0x1800446c5  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x1800446cc  mov     rcx, [rcx+10h]
0x1800446d0  call    WPP_SF_d
0x1800446d5  mov     ecx, 1; dwMilliseconds
0x1800446da  call    cs:__imp_Sleep
0x1800446e0  mov     eax, [rsp+458h+arg_10]
0x1800446e7  test    eax, eax
0x1800446e9  jg      short loc_1800446AB
0x1800446eb  lock dec dword ptr [rsi+70h]
0x1800446ef  jmp     loc_180044441
0x1800446f4  cmp     r10, r14
0x1800446f7  jnb     loc_1800445F1
0x1800446fd  mov     rax, [rax+8]
0x180044701  jmp     loc_18004458C
0x180044706  mov     rcx, cs:WPP_GLOBAL_Control
0x18004470d  cmp     rcx, r13
0x180044710  jz      short loc_18004472D
0x180044712  test    byte ptr [rcx+1Ch], 1
0x180044716  jz      short loc_18004472D
0x180044718  mov     edx, 38h ; '8'
0x18004471d  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180044724  mov     rcx, [rcx+10h]
0x180044728  call    WPP_SF_
0x18004472d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180044732  mov     rcx, [r15+10h]; hHandle
0x180044736  call    cs:__imp_WaitForSingleObject
0x18004473c  cmp     qword ptr [rsi+28h], 0
0x180044741  jnz     loc_180044DA0
0x180044747  mov     dword ptr [rsp+458h+ThreadInformation], r12d
  ... truncated ...
```
