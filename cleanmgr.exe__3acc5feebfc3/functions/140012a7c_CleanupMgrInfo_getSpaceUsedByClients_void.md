# CleanupMgrInfo::getSpaceUsedByClients(void)

- ea: `0x140012a7c`
- end: `0x140013529`
- name: `?getSpaceUsedByClients@CleanupMgrInfo@@IEAAHXZ`
- size: `2733`
- prototype: `__int64 __fastcall(CleanupMgrInfo *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000f314`

## callees

- `0x1400019bc`
- `0x140001a88`
- `0x1400020ec`
- `0x1400029a0`
- `0x140005fe4`
- `0x14000e15c`
- `0x14000f254`
- `0x14000f6ac`
- `0x14000f6d8`
- `0x140011e0c`
- `0x140012a7c`
- `0x140016778`
- `0x1400168a4`
- `0x140018010`

## import_xrefs

- `USER32!PostMessageW` at `0x140012cc7`
- `USER32!PostMessageW` at `0x140012cc7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012b6f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012b6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012b98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140012b8b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140012b8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140012b3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140012b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012c7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140012c7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012bf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012ce8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012dd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012e0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012f15`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140013135`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001347a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012bf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012ce8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012dd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012e0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140012f15`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140013135`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001347a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140012bc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140012be1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140012bc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140012be1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400132f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001345c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400132f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001345c`

## string_xrefs

- `0x140012ccd`: `CleanMgrPluginScan`

## pseudocode

```c
__int64 __fastcall CleanupMgrInfo::getSpaceUsedByClients(CleanupMgrInfo *this)
{
  int v2; // r15d
  bool v3; // zf
  int v4; // r12d
  int v5; // r13d
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  int *v8; // rsi
  WCHAR *v9; // r14
  __int64 v10; // r13
  LPARAM v11; // rbx
  WPARAM v12; // r14
  __int64 v13; // rsi
  const unsigned __int16 *v14; // r12
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // r15
  unsigned __int16 *v17; // rax
  WPARAM v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  ULONGLONG v21; // rbx
  int v22; // r14d
  __int64 v23; // rcx
  double v24; // xmm0_8
  double v25; // xmm0_8
  unsigned __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rbx
  char v29; // r14
  char v30; // r15
  char v31; // r12
  ULONGLONG v32; // rdx
  unsigned __int64 v33; // rcx
  int v34; // r8d
  double v35; // xmm1_8
  __int64 v36; // rdx
  double v37; // xmm0_8
  unsigned __int64 v38; // rax
  double v39; // xmm0_8
  int v40; // r12d
  WCHAR *v41; // rbx
  int v42; // r15d
  const struct _tlgProvider_t *v43; // rax
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rcx
  double v47; // xmm0_8
  double v48; // xmm0_8
  unsigned __int64 v49; // rax
  const WCHAR *v50; // rbx
  const struct _tlgProvider_t *v51; // rax
  __int64 v52; // r8
  __int64 v53; // r9
  int v54; // r15d
  const struct _tlgProvider_t *v55; // rax
  __int64 v56; // r8
  __int64 v57; // r9
  char v58; // bl
  int v59; // esi
  __int64 v60; // r14
  ULONGLONG v61; // rax
  int v62; // edx
  int v63; // r8d
  ULONGLONG v64; // rcx
  double v65; // xmm0_8
  ULONGLONG v66; // rax
  double v67; // xmm0_8
  unsigned __int16 **dwCreationFlags; // [rsp+28h] [rbp-100h]
  unsigned __int64 *lpThreadId; // [rsp+30h] [rbp-F8h]
  unsigned int v71; // [rsp+38h] [rbp-F0h]
  int v72; // [rsp+A8h] [rbp-80h] BYREF
  int v73; // [rsp+ACh] [rbp-7Ch] BYREF
  int v74; // [rsp+B0h] [rbp-78h] BYREF
  int v75; // [rsp+B4h] [rbp-74h] BYREF
  int v76; // [rsp+B8h] [rbp-70h] BYREF
  int v77; // [rsp+BCh] [rbp-6Ch]
  int v78; // [rsp+C0h] [rbp-68h] BYREF
  int v79; // [rsp+C4h] [rbp-64h] BYREF
  unsigned __int16 **v80; // [rsp+C8h] [rbp-60h] BYREF
  WPARAM v81; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v82; // [rsp+D8h] [rbp-50h] BYREF
  unsigned int v83; // [rsp+E0h] [rbp-48h]
  WCHAR *v84; // [rsp+E8h] [rbp-40h] BYREF
  ULONGLONG TickCount64; // [rsp+F0h] [rbp-38h] BYREF
  ULONGLONG v86; // [rsp+F8h] [rbp-30h]
  __int64 v87; // [rsp+100h] [rbp-28h] BYREF
  const WCHAR *v88; // [rsp+108h] [rbp-20h] BYREF
  int *v89; // [rsp+110h] [rbp-18h] BYREF
  int v90; // [rsp+118h] [rbp-10h]
  WCHAR *v91; // [rsp+120h] [rbp-8h] BYREF
  int v92; // [rsp+128h] [rbp+0h]
  _QWORD v93[42]; // [rsp+138h] [rbp+10h] BYREF
  _QWORD v94[42]; // [rsp+288h] [rbp+160h] BYREF

  v2 = 0;
  v76 = 0;
  v83 = 1;
  v3 = (*((_DWORD *)this + 408) & 0x200) == 0;
  v78 = *((_DWORD *)this + 408) & 0x200;
  v79 = !v3;
  v4 = 0;
  v75 = 0;
  v5 = 0;
  v74 = 0;
  v73 = 0;
  v77 = 0;
  *((_QWORD *)this + 200) = 0;
  *((_DWORD *)this + 442) = 0;
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v94,
    (__int64)"CleanMgrScan");
  v94[0] = &CleanupMgrTelemetry::CleanMgrScan::`vftable';
  cleanmgrBeforeCleanMgrScanTick = GetTickCount64();
  if ( (*((_DWORD *)this + 408) & 0x1220) == 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 209) = EventW;
    if ( EventW )
    {
      Thread = CreateThread(0, 0, ScanAbortThread, this, 0, (LPDWORD)this + 420);
      *((_QWORD *)this + 207) = Thread;
      if ( Thread )
        WaitForSingleObject(*((HANDLE *)this + 209), 0xFFFFFFFF);
      CloseHandle(*((HANDLE *)this + 209));
    }
  }
  if ( *((_QWORD *)this + 219) )
    qword_140021680 = (__int64)this;
  v8 = (int *)LocalAlloc(0x40u, 192LL * *((int *)this + 434));
  v82 = (__int64)v8;
  v9 = (WCHAR *)LocalAlloc(0x40u, 216LL * *((int *)this + 434));
  v84 = v9;
  v86 = 0;
  TickCount64 = GetTickCount64();
  v72 = 0;
  if ( *((int *)this + 434) > 0 )
  {
    while ( 1 )
    {
      v10 = 0;
      v11 = 0;
      v12 = v2;
      v81 = v2;
      v13 = 616LL * v2;
      v14 = *(const unsigned __int16 **)(*((_QWORD *)this + 218) + v13 + 568);
      if ( v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
        v16 = v15 + 1;
        if ( v15 + 1 >= v15 && (v87 = 0, is_mul_ok(v16, 2u)) )
        {
          v17 = (unsigned __int16 *)CoTaskMemAlloc(2 * v16);
          v11 = (LPARAM)v17;
          if ( v17 )
            StringCchCopyNExW(v17, v15 + 1, v14, v15, dwCreationFlags, lpThreadId, v71);
          v12 = v81;
          v2 = v72;
        }
        else
        {
          v11 = 0;
          v12 = v81;
          v2 = v72;
        }
      }
      if ( (*((_DWORD *)this + 408) & 0x1220) == 0 )
        PostMessageW(*((HWND *)this + 208), 0x401u, v12, v11);
      wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        (__int64)v93,
        (__int64)"CleanMgrPluginScan");
      v93[0] = &CleanupMgrTelemetry::CleanMgrPluginScan::`vftable';
      cleanmgrBeforeCleanMgrPluginScanTick = GetTickCount64();
      if ( v82 )
      {
        v18 = v82 + 192 * v12;
        dwCreationFlags = (unsigned __int16 **)(v13 + *((_QWORD *)this + 218) + 40LL);
        StringCchPrintfW((unsigned __int16 *)v18, 0x50u, L"%-*s");
        *(_OWORD *)(v18 + 160) = *(_OWORD *)(v13 + *((_QWORD *)this + 218) + 8);
        *(_DWORD *)(v18 + 176) = *(_DWORD *)(v13 + *((_QWORD *)this + 218) + 608);
        *(_DWORD *)(v18 + 180) = *(_DWORD *)(v13 + *((_QWORD *)this + 218) + 604);
        *(_DWORD *)(v18 + 184) = *(_DWORD *)(v13 + *((_QWORD *)this + 218) + 600);
        *(_DWORD *)(v18 + 188) = v2;
      }
      v19 = *((_QWORD *)this + 218);
      if ( !v78 || v79 == *(_DWORD *)(v13 + v19 + 608) )
      {
        v20 = v13 + v19;
        if ( *(_QWORD *)(v20 + 24) )
        {
          if ( *((_QWORD *)this + 219) )
          {
            if ( v20 )
              qword_140021678 = v20;
            v21 = GetTickCount64();
            v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v13 + *((_QWORD *)this + 218) + 24)
                                                                     + 32LL))(
                    *(_QWORD *)(v13 + *((_QWORD *)this + 218) + 24),
                    v13 + *((_QWORD *)this + 218) + 592LL,
                    *((_QWORD *)this + 220));
            v76 = v22;
            v23 = GetTickCount64() - v21;
            if ( v23 < 0 )
              v24 = (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1))
                  + (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1));
            else
              v24 = (double)(int)v23;
            v25 = v24 / 1000.0;
            v26 = 0;
            if ( v25 >= 9.223372036854776e18 )
            {
              v25 = v25 - 9.223372036854776e18;
              if ( v25 < 9.223372036854776e18 )
                v26 = 0x8000000000000000uLL;
            }
            v10 = v26 + (unsigned int)(int)v25;
            v86 += v10;
            if ( v22 >= 0 )
            {
              ++v74;
            }
            else
            {
              ++v73;
              *((_DWORD *)this + 407) = 2;
            }
          }
        }
      }
      v27 = *((_QWORD *)this + 218);
      if ( !*(_QWORD *)(v13 + v27 + 592) )
      {
        ++v77;
        if ( (*(_BYTE *)(v13 + v27 + 584) & 0x10) != 0 )
          *(_DWORD *)(v13 + v27 + 600) = 0;
      }
      v28 = *((_QWORD *)this + 218);
      *((_QWORD *)this + 200) += *(_QWORD *)(v28 + v13 + 592);
      v29 = *((_DWORD *)this + 442) != 0;
      v81 = *(_QWORD *)(v28 + v13 + 592);
      v30 = *(_DWORD *)(v28 + v13 + 600) != 0;
      v31 = *(_DWORD *)(v28 + v13 + 604) != 0;
      LODWORD(v80) = *(_DWORD *)(v28 + v13 + 608) != 0;
      v32 = GetTickCount64();
      if ( (Microsoft_Windows_CleanmgrEnableBits & 1) != 0 )
      {
        if ( v10 < 0 )
        {
          v33 = v10 & 1 | ((unsigned __int64)v10 >> 1);
          v35 = (double)(int)v33 + (double)(int)v33;
        }
        else
        {
          v35 = (double)(int)v10;
        }
        v36 = v32 - cleanmgrBeforeCleanMgrPluginScanTick;
        if ( v36 < 0 )
        {
          v38 = (unsigned __int64)v36 >> 1;
          LODWORD(v36) = v36 & 1;
          v37 = (double)(int)(v36 | v38) + (double)(int)(v36 | v38);
        }
        else
        {
          v37 = (double)(int)v36;
        }
        v39 = v37 / 1000.0;
        McTemplateU0qztttxtggd_EventWriteTransfer(
          v33,
          v36,
          v34,
          v13 + v28 + 40,
          (char)v80,
          v31,
          v30,
          v81,
          v29,
          SLOBYTE(v39),
          SLOBYTE(v35),
          v76);
      }
      v9 = v84;
      if ( v84 )
      {
        v40 = v75;
        v41 = &v84[108 * v75];
        dwCreationFlags = (unsigned __int16 **)(v13 + *((_QWORD *)this + 218) + 40LL);
        StringCchPrintfW(v41, 0x50u, L"%-*s");
        *((_OWORD *)v41 + 10) = *(_OWORD *)(v13 + *((_QWORD *)this + 218) + 8);
        *((_QWORD *)v41 + 22) = v10;
        *((_QWORD *)v41 + 23) = *(_QWORD *)(v13 + *((_QWORD *)this + 218) + 592);
        *((_DWORD *)v41 + 50) = *((_DWORD *)this + 442);
        *((_DWORD *)v41 + 51) = *(_DWORD *)(v13 + *((_QWORD *)this + 218) + 608);
        *((float *)v41 + 48) = (float)*(int *)(v13 + *((_QWORD *)this + 218) + 604);
        *((float *)v41 + 49) = (float)*(int *)(v13 + *((_QWORD *)this + 218) + 600);
        v42 = v72;
        *((_DWORD *)v41 + 53) = v72;
      }
      else
      {
        v42 = v72;
        v40 = v75;
      }
      v4 = v40 + 1;
      v75 = v4;
      if ( *((_DWORD *)this + 442) == 1 )
        break;
      CleanupMgrTelemetry::CleanMgrPluginScan::~CleanMgrPluginScan((CleanupMgrTelemetry::CleanMgrPluginScan *)v93);
      v2 = v42 + 1;
      v72 = v2;
      if ( v2 >= *((_DWORD *)this + 434) )
        goto LABEL_58;
    }
    v43 = g_hProvider::Provider();
    if ( *(_DWORD *)v43 > 5u && (unsigned __int8)tlgKeywordOn(v43, 0x400000000000LL, v44) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v45,
        (__int64)byte_14001BB83,
        0);
    *((_DWORD *)this + 407) = 3;
    v83 = 0;
    CleanupMgrTelemetry::CleanMgrPluginScan::~CleanMgrPluginScan((CleanupMgrTelemetry::CleanMgrPluginScan *)v93);
LABEL_58:
    v5 = v74;
    v8 = (int *)v82;
  }
  v46 = GetTickCount64() - TickCount64;
  if ( v46 < 0 )
    v47 = (double)(int)(v46 & 1 | ((unsigned __int64)v46 >> 1)) + (double)(int)(v46 & 1 | ((unsigned __int64)v46 >> 1));
  else
    v47 = (double)(int)v46;
  v48 = v47 / 1000.0;
  v49 = 0;
  if ( v48 >= 9.223372036854776e18 )
  {
    v48 = v48 - 9.223372036854776e18;
    if ( v48 < 9.223372036854776e18 )
      v49 = 0x8000000000000000uLL;
  }
  v50 = (const WCHAR *)(v49 + (unsigned int)(int)v48);
  if ( v8 )
  {
    LOWORD(v72) = *((_WORD *)this + 868);
    v51 = g_hProvider::Provider();
    if ( *(_DWORD *)v51 && (unsigned __int8)tlgKeywordOn(v51, 0x400000000000LL, v51) )
    {
      v89 = v8;
      v90 = 192 * (unsigned __int16)v72;
      v91 = (WCHAR *)&v72;
      v92 = 2;
      LODWORD(v80) = *((_DWORD *)this + 442);
      TickCount64 = v86;
      v84 = (WCHAR *)v50;
      v82 = *((_QWORD *)this + 200);
      v79 = *((_DWORD *)this + 412);
      v78 = v77;
      v54 = v73;
      v76 = v73;
      v75 = v5;
      v74 = v4;
      v73 = *((_DWORD *)this + 434);
      LODWORD(v81) = *((_DWORD *)this + 408);
      v88 = (const WCHAR *)((char *)this + 16);
      v87 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v52,
        (__int64)byte_14001BA3B,
        v52,
        v53,
        (__int64)&v87,
        &v88,
        (__int64)&v81,
        (__int64)&v73,
        (__int64)&v74,
        (__int64)&v75,
        (__int64)&v76,
        (__int64)&v78,
        (__int64)&v79,
        (__int64)&v82,
        (__int64)&v84,
        (__int64)&TickCount64,
        (__int64)&v80,
        (__int64 *)&v91,
        (__int64 *)&v89);
    }
    else
    {
      v54 = v73;
    }
    LocalFree(v8);
  }
  else
  {
    v54 = v73;
  }
  if ( v9 )
  {
    LOWORD(v72) = *((_WORD *)this + 868);
    v55 = g_hProvider::Provider();
    if ( *(_DWORD *)v55 && (unsigned __int8)tlgKeywordOn(v55, 0x400000000000LL, v55) )
    {
      v91 = v9;
      v92 = 216 * (unsigned __int16)v72;
      v89 = &v72;
      v90 = 2;
      LODWORD(v81) = *((_DWORD *)this + 442);
      v87 = v86;
      v88 = v50;
      TickCount64 = *((_QWORD *)this + 200);
      LODWORD(v80) = *((_DWORD *)this + 412);
      v79 = v77;
      v78 = v54;
      v76 = v5;
      v75 = v4;
      v74 = *((_DWORD *)this + 434);
      v73 = *((_DWORD *)this + 408);
      v84 = (WCHAR *)((char *)this + 16);
      v82 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v56,
        (__int64)byte_14001B8C1,
        v56,
        v57,
        (__int64)&v82,
        (const WCHAR **)&v84,
        (__int64)&v73,
        (__int64)&v74,
        (__int64)&v75,
        (__int64)&v76,
        (__int64)&v78,
        (__int64)&v79,
        (__int64)&v80,
        (__int64)&TickCount64,
        (__int64)&v88,
        (__int64)&v87,
        (__int64)&v81,
        (__int64 *)&v89,
        (__int64 *)&v91);
    }
    LocalFree(v9);
  }
  v58 = *((_DWORD *)this + 412) != 0;
  v59 = *((_DWORD *)this + 434);
  v60 = *((_QWORD *)this + 200);
  v61 = GetTickCount64();
  if ( (Microsoft_Windows_CleanmgrEnableBits & 1) != 0 )
  {
    v64 = v61 - cleanmgrBeforeCleanMgrScanTick;
    if ( (__int64)(v61 - cleanmgrBeforeCleanMgrScanTick) < 0 )
    {
      v66 = v64 >> 1;
      LODWORD(v64) = v64 & 1;
      v65 = (double)(int)(v64 | v66) + (double)(int)(v64 | v66);
    }
    else
    {
      v65 = (double)(int)v64;
    }
    v67 = v65 / 1000.0;
    McTemplateU0qztxqqqqqg_EventWriteTransfer(
      v64,
      v62,
      v63,
      (_DWORD)this + 16,
      v58,
      v60,
      v59,
      v4,
      v5,
      v54,
      v77,
      SLOBYTE(v67));
  }
  CleanupMgrTelemetry::CleanMgrScan::~CleanMgrScan((CleanupMgrTelemetry::CleanMgrScan *)v94);
  return v83;
}

```

## disassembly

```asm
0x140012a7c  mov     rax, rsp
0x140012a7f  push    rbp
0x140012a80  push    rbx
0x140012a81  push    rsi
0x140012a82  push    rdi
0x140012a83  push    r12
0x140012a85  push    r13
0x140012a87  push    r14
0x140012a89  push    r15
0x140012a8b  lea     rbp, [rax-318h]
0x140012a92  sub     rsp, 3F8h
0x140012a99  movaps  xmmword ptr [rax-58h], xmm6
0x140012a9d  mov     rax, cs:__security_cookie
0x140012aa4  xor     rax, rsp
0x140012aa7  mov     [rbp+310h+var_60], rax
0x140012aae  mov     rdi, rcx
0x140012ab1  xor     r15d, r15d
0x140012ab4  mov     [rbp+310h+var_380], r15d
0x140012ab8  mov     [rbp+310h+var_358], 1
0x140012abf  mov     eax, [rcx+660h]
0x140012ac5  and     eax, 200h
0x140012aca  mov     [rbp+310h+var_378], eax
0x140012acd  mov     eax, r15d
0x140012ad0  setnz   al
0x140012ad3  mov     [rbp+310h+var_374], eax
0x140012ad6  mov     r12d, r15d
0x140012ad9  mov     [rbp+310h+var_384], r15d
0x140012add  mov     r13d, r15d
0x140012ae0  mov     [rbp+310h+var_388], r15d
0x140012ae4  mov     [rbp+310h+var_38C], r15d
0x140012ae8  mov     [rbp+310h+var_37C], r15d
0x140012aec  mov     [rcx+640h], r15
0x140012af3  mov     [rcx+6E8h], r15d
0x140012afa  lea     rdx, aCleanmgrscan; "CleanMgrScan"
0x140012b01  lea     rcx, [rbp+310h+var_1B0]
0x140012b08  call    ??0?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140012b0d  lea     rax, ??_7CleanMgrScan@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::CleanMgrScan::`vftable'
0x140012b14  mov     [rbp+310h+var_1B0], rax
0x140012b1b  call    cs:__imp_GetTickCount64
0x140012b21  mov     cs:?cleanmgrBeforeCleanMgrScanTick@@3_KA, rax; unsigned __int64 cleanmgrBeforeCleanMgrScanTick
0x140012b28  test    dword ptr [rdi+660h], 1220h
0x140012b32  jnz     short loc_140012B9E
0x140012b34  xor     r9d, r9d; lpName
0x140012b37  xor     r8d, r8d; bInitialState
0x140012b3a  xor     edx, edx; bManualReset
0x140012b3c  xor     ecx, ecx; lpEventAttributes
0x140012b3e  call    cs:__imp_CreateEventW
0x140012b44  mov     [rdi+688h], rax
0x140012b4b  test    rax, rax
0x140012b4e  jz      short loc_140012B9E
0x140012b50  lea     rax, [rdi+690h]
0x140012b57  mov     [rsp+430h+lpThreadId], rax; lpThreadId
0x140012b5c  mov     [rsp+430h+dwCreationFlags], r15d; dwCreationFlags
0x140012b61  mov     r9, rdi; lpParameter
0x140012b64  lea     r8, ?ScanAbortThread@@YAKPEAVCleanupMgrInfo@@@Z; lpStartAddress
0x140012b6b  xor     edx, edx; dwStackSize
0x140012b6d  xor     ecx, ecx; lpThreadAttributes
0x140012b6f  call    cs:__imp_CreateThread
0x140012b75  mov     [rdi+678h], rax
0x140012b7c  test    rax, rax
0x140012b7f  jz      short loc_140012B91
0x140012b81  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140012b84  mov     rcx, [rdi+688h]; hHandle
0x140012b8b  call    cs:__imp_WaitForSingleObject
0x140012b91  mov     rcx, [rdi+688h]; hObject
0x140012b98  call    cs:__imp_CloseHandle
0x140012b9e  cmp     [rdi+6D8h], r15
0x140012ba5  jz      short loc_140012BAE
0x140012ba7  mov     cs:qword_140021680, rdi
0x140012bae  movsxd  rax, dword ptr [rdi+6C8h]
0x140012bb5  lea     rdx, [rax+rax*2]
0x140012bb9  shl     rdx, 6; uBytes
0x140012bbd  mov     ebx, 40h ; '@'
0x140012bc2  mov     ecx, ebx; uFlags
0x140012bc4  call    cs:__imp_LocalAlloc
0x140012bca  mov     rsi, rax
0x140012bcd  mov     [rbp+310h+var_360], rax
0x140012bd1  movsxd  rax, dword ptr [rdi+6C8h]
0x140012bd8  imul    rdx, rax, 0D8h; uBytes
0x140012bdf  mov     ecx, ebx; uFlags
0x140012be1  call    cs:__imp_LocalAlloc
0x140012be7  mov     r14, rax
0x140012bea  mov     [rbp+310h+var_350], rax
0x140012bee  mov     [rbp+310h+var_340], r15
0x140012bf2  call    cs:__imp_GetTickCount64
0x140012bf8  mov     [rbp+310h+var_348], rax
0x140012bfc  mov     [rbp+310h+var_390], r15d
0x140012c00  mov     rbx, 8000000000000000h
0x140012c0a  movsd   xmm6, cs:__real@43e0000000000000
0x140012c12  xor     ecx, ecx
0x140012c14  cmp     [rdi+6C8h], ecx
0x140012c1a  jle     loc_140013135
0x140012c20  jmp     short loc_140012C24
0x140012c22  xor     ecx, ecx
0x140012c24  mov     r13, rcx
0x140012c27  mov     rbx, rcx
0x140012c2a  movsxd  r14, r15d
0x140012c2d  mov     [rbp+310h+var_368], r14
0x140012c31  imul    rsi, r14, 268h
0x140012c38  mov     rax, [rdi+6D0h]
0x140012c3f  mov     r12, [rax+rsi+238h]
0x140012c47  test    r12, r12
0x140012c4a  jz      short loc_140012CA6
0x140012c4c  or      r14, 0FFFFFFFFFFFFFFFFh
0x140012c50  inc     r14
0x140012c53  cmp     [r12+r14*2], cx
0x140012c58  jnz     short loc_140012C50
0x140012c5a  lea     r15, [r14+1]
0x140012c5e  cmp     r15, r14
0x140012c61  jb      loc_140012E23
0x140012c67  mov     [rbp+310h+var_338], rcx
0x140012c6b  mov     eax, 2
0x140012c70  mul     r15
0x140012c73  test    rdx, rdx
0x140012c76  jnz     loc_140012E23
0x140012c7c  mov     rcx, rax; cb
0x140012c7f  call    cs:__imp_CoTaskMemAlloc
0x140012c85  mov     rbx, rax
0x140012c88  test    rax, rax
0x140012c8b  jz      short loc_140012C9E
0x140012c8d  mov     r9, r14; unsigned __int64
0x140012c90  mov     r8, r12; unsigned __int16 *
0x140012c93  mov     rdx, r15; unsigned __int64
0x140012c96  mov     rcx, rax; unsigned __int16 *
0x140012c99  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x140012c9e  mov     r14, [rbp+310h+var_368]
0x140012ca2  mov     r15d, [rbp+310h+var_390]
0x140012ca6  xor     r12d, r12d
0x140012ca9  test    dword ptr [rdi+660h], 1220h
0x140012cb3  jnz     short loc_140012CCD
0x140012cb5  mov     r9, rbx; lParam
0x140012cb8  mov     r8, r14; wParam
0x140012cbb  mov     edx, 401h; Msg
0x140012cc0  mov     rcx, [rdi+680h]; hWnd
0x140012cc7  call    cs:__imp_PostMessageW
0x140012ccd  lea     rdx, aCleanmgrplugin_1; "CleanMgrPluginScan"
0x140012cd4  lea     rcx, [rbp+310h+var_300]
0x140012cd8  call    ??0?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140012cdd  lea     rax, ??_7CleanMgrPluginScan@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::CleanMgrPluginScan::`vftable'
0x140012ce4  mov     [rbp+310h+var_300], rax
0x140012ce8  call    cs:__imp_GetTickCount64
0x140012cee  mov     cs:?cleanmgrBeforeCleanMgrPluginScanTick@@3_KA, rax; unsigned __int64 cleanmgrBeforeCleanMgrPluginScanTick
0x140012cf5  mov     rcx, [rbp+310h+var_360]
0x140012cf9  test    rcx, rcx
0x140012cfc  jz      loc_140012D90
0x140012d02  lea     rbx, [r14+r14*2]
0x140012d06  shl     rbx, 6
0x140012d0a  add     rbx, rcx
0x140012d0d  mov     rcx, [rdi+6D0h]
0x140012d14  add     rcx, 28h ; '('
0x140012d18  add     rcx, rsi
0x140012d1b  mov     qword ptr [rsp+430h+dwCreationFlags], rcx
0x140012d20  mov     r9d, 4Fh ; 'O'
0x140012d26  lea     r8, aS; "%-*s"
0x140012d2d  lea     edx, [r9+1]; unsigned __int64
0x140012d31  mov     rcx, rbx; unsigned __int16 *
0x140012d34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012d39  mov     rax, [rdi+6D0h]
0x140012d40  movups  xmm0, xmmword ptr [rsi+rax+8]
0x140012d45  movdqu  xmmword ptr [rbx+0A0h], xmm0
0x140012d4d  mov     rax, [rdi+6D0h]
0x140012d54  mov     ecx, [rsi+rax+260h]
0x140012d5b  mov     [rbx+0B0h], ecx
0x140012d61  mov     rax, [rdi+6D0h]
0x140012d68  mov     ecx, [rsi+rax+25Ch]
0x140012d6f  mov     [rbx+0B4h], ecx
0x140012d75  mov     rax, [rdi+6D0h]
0x140012d7c  mov     ecx, [rsi+rax+258h]
0x140012d83  mov     [rbx+0B8h], ecx
0x140012d89  mov     [rbx+0BCh], r15d
0x140012d90  mov     rax, [rdi+6D0h]
0x140012d97  cmp     [rbp+310h+var_378], r12d
0x140012d9b  jz      short loc_140012DAD
0x140012d9d  mov     ecx, [rbp+310h+var_374]
0x140012da0  cmp     ecx, [rsi+rax+260h]
0x140012da7  jnz     loc_140012E95
0x140012dad  add     rax, rsi
0x140012db0  cmp     [rax+18h], r12
0x140012db4  jz      loc_140012E95
0x140012dba  cmp     [rdi+6D8h], r12
0x140012dc1  jz      loc_140012E95
0x140012dc7  test    rax, rax
0x140012dca  jz      short loc_140012DD3
0x140012dcc  mov     cs:qword_140021678, rax
0x140012dd3  call    cs:__imp_GetTickCount64
0x140012dd9  mov     rbx, rax
0x140012ddc  mov     rdx, [rdi+6D0h]
0x140012de3  mov     rcx, [rsi+rdx+18h]
0x140012de8  mov     rax, [rcx]
0x140012deb  add     rdx, 250h
0x140012df2  add     rdx, rsi
0x140012df5  mov     r8, [rdi+6E0h]
0x140012dfc  mov     rax, [rax+20h]
0x140012e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e05  mov     r14d, eax
0x140012e08  mov     [rbp+310h+var_380], eax
0x140012e0b  call    cs:__imp_GetTickCount64
0x140012e11  mov     rcx, rax
0x140012e14  sub     rcx, rbx
0x140012e17  xorps   xmm0, xmm0
0x140012e1a  js      short loc_140012E36
0x140012e1c  cvtsi2sd xmm0, rcx
0x140012e21  jmp     short loc_140012E4B
0x140012e23  xor     r12d, r12d
0x140012e26  mov     ebx, r12d
0x140012e29  mov     r14, [rbp+310h+var_368]
0x140012e2d  mov     r15d, [rbp+310h+var_390]
0x140012e31  jmp     loc_140012CA9
0x140012e36  mov     rax, rcx
0x140012e39  shr     rax, 1
0x140012e3c  and     ecx, 1
0x140012e3f  or      rax, rcx
0x140012e42  cvtsi2sd xmm0, rax
0x140012e47  addsd   xmm0, xmm0
0x140012e4b  divsd   xmm0, cs:__real@408f400000000000
0x140012e53  xor     eax, eax
0x140012e55  comisd  xmm0, xmm6
0x140012e59  jb      short loc_140012E72
0x140012e5b  subsd   xmm0, xmm6
0x140012e5f  comisd  xmm0, xmm6
0x140012e63  jnb     short loc_140012E72
0x140012e65  mov     rcx, 8000000000000000h
0x140012e6f  mov     rax, rcx
0x140012e72  cvttsd2si r13, xmm0
0x140012e77  add     r13, rax
0x140012e7a  add     [rbp+310h+var_340], r13
0x140012e7e  test    r14d, r14d
0x140012e81  jns     short loc_140012E92
0x140012e83  inc     [rbp+310h+var_38C]
0x140012e86  mov     dword ptr [rdi+65Ch], 2
0x140012e90  jmp     short loc_140012E95
0x140012e92  inc     [rbp+310h+var_388]
0x140012e95  mov     rax, [rdi+6D0h]
0x140012e9c  cmp     [rsi+rax+250h], r12
0x140012ea4  jnz     short loc_140012EBB
0x140012ea6  inc     [rbp+310h+var_37C]
0x140012ea9  test    byte ptr [rsi+rax+248h], 10h
0x140012eb1  jz      short loc_140012EBB
0x140012eb3  mov     [rsi+rax+258h], r12d
0x140012ebb  mov     rbx, [rdi+6D0h]
0x140012ec2  mov     rax, [rbx+rsi+250h]
0x140012eca  add     [rdi+640h], rax
0x140012ed1  mov     r14d, r12d
0x140012ed4  cmp     [rdi+6E8h], r12d
0x140012edb  setnz   r14b
0x140012edf  mov     rax, [rbx+rsi+250h]
0x140012ee7  mov     [rbp+310h+var_368], rax
0x140012eeb  mov     r15d, r12d
0x140012eee  cmp     [rbx+rsi+258h], r12d
0x140012ef6  setnz   r15b
0x140012efa  cmp     dword ptr [rbx+rsi+25Ch], 0
0x140012f02  setnz   r12b
0x140012f06  xor     eax, eax
0x140012f08  cmp     [rbx+rsi+260h], eax
0x140012f0f  setnz   al
0x140012f12  mov     dword ptr [rbp+310h+var_370], eax
0x140012f15  call    cs:__imp_GetTickCount64
0x140012f1b  mov     rdx, rax
0x140012f1e  test    cs:Microsoft_Windows_CleanmgrEnableBits, 1
0x140012f25  jz      loc_140012FC0
0x140012f2b  xorps   xmm1, xmm1
0x140012f2e  test    r13, r13
0x140012f31  js      short loc_140012F3A
0x140012f33  cvtsi2sd xmm1, r13
0x140012f38  jmp     short loc_140012F52
0x140012f3a  mov     rcx, r13
0x140012f3d  shr     rcx, 1
0x140012f40  mov     rax, r13
0x140012f43  and     eax, 1
0x140012f46  or      rcx, rax
0x140012f49  cvtsi2sd xmm1, rcx
0x140012f4e  addsd   xmm1, xmm1
0x140012f52  sub     rdx, cs:?cleanmgrBeforeCleanMgrPluginScanTick@@3_KA; unsigned __int64 cleanmgrBeforeCleanMgrPluginScanTick
0x140012f59  xorps   xmm0, xmm0
0x140012f5c  js      short loc_140012F65
0x140012f5e  cvtsi2sd xmm0, rdx
0x140012f63  jmp     short loc_140012F7A
0x140012f65  mov     rax, rdx
0x140012f68  shr     rax, 1
0x140012f6b  and     edx, 1
0x140012f6e  or      rax, rdx
0x140012f71  cvtsi2sd xmm0, rax
0x140012f76  addsd   xmm0, xmm0
0x140012f7a  divsd   xmm0, cs:__real@408f400000000000
0x140012f82  lea     r9, [rbx+28h]
0x140012f86  add     r9, rsi
0x140012f89  mov     eax, [rbp+310h+var_380]
0x140012f8c  mov     dword ptr [rsp+430h+var_3D8], eax
0x140012f90  movsd   [rsp+430h+var_3E0], xmm1
0x140012f96  movsd   [rsp+430h+var_3E8], xmm0
0x140012f9c  mov     dword ptr [rsp+430h+var_3F0], r14d
0x140012fa1  mov     rax, [rbp+310h+var_368]
0x140012fa5  mov     [rsp+430h+var_3F8], rax
0x140012faa  mov     [rsp+430h+var_400], r15d; unsigned int
0x140012faf  mov     dword ptr [rsp+430h+lpThreadId], r12d; unsigned __int64 *
0x140012fb4  mov     eax, dword ptr [rbp+310h+var_370]
0x140012fb7  mov     [rsp+430h+dwCreationFlags], eax; unsigned __int16 **
0x140012fbb  call    McTemplateU0qztttxtggd_EventWriteTransfer
0x140012fc0  mov     r14, [rbp+310h+var_350]
0x140012fc4  test    r14, r14
  ... truncated ...
```
