# InternalRefreshCalibration

- ea: `0x18004b680`
- end: `0x18004b9d2`
- name: `InternalRefreshCalibration`
- size: `850`
- prototype: `__int64 __fastcall(LPCWSTR lpString1)`
- caller_count: `6`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180020290`
- `0x18003eb70`
- `0x180042ccc`
- `0x180046450`
- `0x18004b9e0`
- `0x18004ba30`

## callees

- `0x180002984`
- `0x180006a50`
- `0x180008bf0`
- `0x1800098b0`
- `0x18001f194`
- `0x180023a4c`
- `0x180024ba0`
- `0x18002e5f0`
- `0x18002e614`
- `0x180047bd4`
- `0x18004ae7c`
- `0x18004aebc`
- `0x18004aef8`
- `0x18004b5e4`
- `0x18004b680`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004b7a4`
- `ntdll!EtwEventWrite` at `0x18004b7cd`
- `ntdll!EtwEventWrite` at `0x18004b91e`
- `ntdll!EtwEventWrite` at `0x18004b7a4`
- `ntdll!EtwEventWrite` at `0x18004b7cd`
- `ntdll!EtwEventWrite` at `0x18004b91e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004b7ed`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004b7ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b814`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b814`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004b990`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004b990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b999`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b999`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004b855`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004b855`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x18004b8c7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayMonitors` at `0x18004b8c7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004b7af`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004b7af`

## pseudocode

```c
__int64 __fastcall InternalRefreshCalibration(LPCWSTR lpString1, unsigned int a2)
{
  HANDLE MutexW; // rbx
  struct IDxva2Wrapper *v3; // rsi
  signed int LastError; // eax
  DWORD v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v12; // [rsp+40h] [rbp-39h] BYREF
  BOOL pbIsEnabled; // [rsp+44h] [rbp-35h] BYREF
  struct IDxva2Wrapper *v14; // [rsp+48h] [rbp-31h] BYREF
  LPARAM dwData[2]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v16; // [rsp+60h] [rbp-19h]
  __int64 v17; // [rsp+70h] [rbp-9h]
  __int64 v18; // [rsp+78h] [rbp-1h] BYREF
  const OLECHAR *p_pbIsEnabled; // [rsp+80h] [rbp+7h] BYREF
  __int64 v20; // [rsp+88h] [rbp+Fh]
  _QWORD v21[2]; // [rsp+90h] [rbp+17h] BYREF

  v12 = 0;
  MutexW = 0;
  v17 = a2;
  v3 = 0;
  v14 = 0;
  *(_OWORD *)dwData = 0;
  v16 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl'::`2'::impl)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v20) = 0;
    p_pbIsEnabled = (const OLECHAR *)qword_18009EFA0;
    if ( (unsigned __int8)std::unique_lock<std::recursive_mutex>::try_lock(&p_pbIsEnabled) )
      HIDWORD(v17) = (unsigned __int8)byte_18009F4D8;
    std::unique_lock<std::recursive_mutex>::~unique_lock<std::recursive_mutex>(&p_pbIsEnabled);
  }
  if ( ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::GetImpl'::`2'::impl)
     || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl))
    && !HIDWORD(v17) )
  {
    goto LABEL_36;
  }
  if ( !a2 )
  {
    pbIsEnabled = 0;
    if ( !WcsGetCalibrationManagementState(&pbIsEnabled) )
      goto LABEL_11;
    LODWORD(v17) = pbIsEnabled;
    v20 = 4;
    p_pbIsEnabled = (const OLECHAR *)&pbIsEnabled;
    EtwEventWrite(g_etwHandle, CALIBRATION_REFRESH_INVOKED, 1, &p_pbIsEnabled);
  }
  if ( GetSystemMetrics(4096) )
  {
    EtwEventWrite(g_etwHandle, CALIBRATION_REMOTE_SESSION, 0, 0);
LABEL_16:
    v12 = -2147467259;
    goto LABEL_36;
  }
  MutexW = CreateMutexW(0, 1, L"Global\\Microsoft.Windows.WindowsColorSystem.CalibrationLoaderMutex");
  if ( !MutexW )
    goto LABEL_11;
  if ( GetLastError() != 183 )
    goto LABEL_22;
  v7 = WaitForSingleObject(MutexW, 0xBB8u);
  if ( v7 == -1 )
  {
LABEL_11:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_35;
  }
  if ( v7 != 258 && v7 != 128 )
    goto LABEL_16;
LABEL_22:
  dwData[0] = (LPARAM)lpString1;
  if ( !lpString1 )
    goto LABEL_28;
  dwData[0] = wcsistr(lpString1);
  if ( dwData[0] )
    goto LABEL_28;
  if ( lstrcmpiW(lpString1, gszDisplay) )
  {
    LastError = -2147024809;
    goto LABEL_35;
  }
  v12 = StringCchCopyW(&qword_18009F6F0, 0x104u, gszMonitorGUID);
  if ( v12 >= 0 )
  {
    v12 = StringCchCatW(&qword_18009F6F0, 0x104u, L"\\0000");
    if ( v12 >= 0 )
    {
      dwData[0] = (LPARAM)&qword_18009F6F0;
LABEL_28:
      v12 = CreateDxva2Wrapper(&v14);
      if ( v12 >= 0 )
      {
        v3 = v14;
        *((_QWORD *)&v16 + 1) = v14;
        EnumDisplayMonitors(0, 0, (MONITORENUMPROC)CalibrationMonitorEnumCallback, (LPARAM)dwData);
        if ( lpString1 )
        {
          LastError = -2147024809;
          if ( LODWORD(dwData[1]) )
            LastError = DWORD1(v16);
          goto LABEL_35;
        }
        if ( HIDWORD(dwData[1]) )
        {
          LastError = v16;
LABEL_35:
          v12 = LastError;
        }
      }
    }
  }
LABEL_36:
  v21[0] = &v12;
  v21[1] = 4;
  EtwEventWrite(g_etwHandle, CALIBRATION_REFRESH_FINISHED, 1, v21);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 1) )
  {
    LODWORD(v14) = v12;
    v18 = 0x2000000;
    pbIsEnabled = a2;
    p_pbIsEnabled = lpString1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v8,
      (__int64)byte_180091A3D,
      v9,
      v10,
      (__int64)&v14,
      &p_pbIsEnabled,
      (__int64)&pbIsEnabled,
      (__int64)&v18);
  }
  if ( MutexW )
  {
    ReleaseMutex(MutexW);
    CloseHandle(MutexW);
  }
  operator delete(v3);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004b680  mov     [rsp-8+arg_10], rbx
0x18004b685  push    rbp
0x18004b686  push    rsi
0x18004b687  push    rdi
0x18004b688  push    r12
0x18004b68a  push    r14
0x18004b68c  lea     rbp, [rsp-37h]
0x18004b691  sub     rsp, 0B0h
0x18004b698  mov     rax, cs:__security_cookie
0x18004b69f  xor     rax, rsp
0x18004b6a2  mov     [rbp+57h+var_30], rax
0x18004b6a6  xor     eax, eax
0x18004b6a8  mov     [rbp+57h+var_90], 0
0x18004b6af  xorps   xmm0, xmm0
0x18004b6b2  mov     [rbp+57h+var_60], rax
0x18004b6b6  xor     ebx, ebx
0x18004b6b8  mov     dword ptr [rbp+57h+var_60], edx
0x18004b6bb  xor     esi, esi
0x18004b6bd  mov     r14d, edx
0x18004b6c0  mov     [rbp+57h+var_88], rsi
0x18004b6c4  mov     rdi, rcx
0x18004b6c7  movups  xmmword ptr [rbp+57h+dwData], xmm0
0x18004b6cb  movups  [rbp+57h+var_70], xmm0
0x18004b6cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate> `wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl(void)'::`2'::impl
0x18004b6d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(void)
0x18004b6db  test    al, al
0x18004b6dd  jnz     short loc_18004B6EF
0x18004b6df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x18004b6e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x18004b6eb  test    al, al
0x18004b6ed  jz      short loc_18004B71D
0x18004b6ef  lea     rax, qword_18009EFA0
0x18004b6f6  mov     byte ptr [rbp+57h+var_48], bl
0x18004b6f9  lea     rcx, [rbp+57h+var_50]
0x18004b6fd  mov     [rbp+57h+var_50], rax
0x18004b701  call    ?try_lock@?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA_NXZ; std::unique_lock<std::recursive_mutex>::try_lock(void)
0x18004b706  test    al, al
0x18004b708  jz      short loc_18004B714
0x18004b70a  movzx   eax, cs:byte_18009F4D8
0x18004b711  mov     dword ptr [rbp+57h+var_60+4], eax
0x18004b714  lea     rcx, [rbp+57h+var_50]
0x18004b718  call    ??1?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_mutex>::~unique_lock<std::recursive_mutex>(void)
0x18004b71d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles> `wil::Feature<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::GetImpl(void)'::`2'::impl
0x18004b724  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::__private_IsEnabled(void)
0x18004b729  test    al, al
0x18004b72b  jnz     short loc_18004B73D
0x18004b72d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x18004b734  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x18004b739  test    al, al
0x18004b73b  jz      short loc_18004B746
0x18004b73d  cmp     dword ptr [rbp+57h+var_60+4], ebx
0x18004b740  jz      loc_18004B8F3
0x18004b746  test    r14d, r14d
0x18004b749  jnz     short loc_18004B7AA
0x18004b74b  lea     rcx, [rbp+57h+pbIsEnabled]; pbIsEnabled
0x18004b74f  mov     [rbp+57h+pbIsEnabled], ebx
0x18004b752  call    WcsGetCalibrationManagementState
0x18004b757  test    eax, eax
0x18004b759  jnz     short loc_18004B776
0x18004b75b  call    cs:__imp_GetLastError
0x18004b761  test    eax, eax
0x18004b763  jle     loc_18004B8F0
0x18004b769  movzx   eax, ax
0x18004b76c  or      eax, 80070000h
0x18004b771  jmp     loc_18004B8F0
0x18004b776  mov     eax, [rbp+57h+pbIsEnabled]
0x18004b779  lea     r9, [rbp+57h+var_50]
0x18004b77d  mov     rcx, cs:g_etwHandle
0x18004b784  lea     rdx, CALIBRATION_REFRESH_INVOKED
0x18004b78b  mov     dword ptr [rbp+57h+var_60], eax
0x18004b78e  mov     r8d, 1
0x18004b794  lea     rax, [rbp+57h+pbIsEnabled]
0x18004b798  mov     [rbp+57h+var_48], 4
0x18004b7a0  mov     [rbp+57h+var_50], rax
0x18004b7a4  call    cs:__imp_EtwEventWrite
0x18004b7aa  mov     ecx, 1000h; nIndex
0x18004b7af  call    cs:__imp_GetSystemMetrics
0x18004b7b5  test    eax, eax
0x18004b7b7  jz      short loc_18004B7DF
0x18004b7b9  mov     rcx, cs:g_etwHandle
0x18004b7c0  lea     rdx, CALIBRATION_REMOTE_SESSION
0x18004b7c7  xor     r9d, r9d
0x18004b7ca  xor     r8d, r8d
0x18004b7cd  call    cs:__imp_EtwEventWrite
0x18004b7d3  mov     [rbp+57h+var_90], 80004005h
0x18004b7da  jmp     loc_18004B8F3
0x18004b7df  lea     r8, Name; "Global\\Microsoft.Windows.WindowsColorS"...
0x18004b7e6  mov     edx, 1; bInitialOwner
0x18004b7eb  xor     ecx, ecx; lpMutexAttributes
0x18004b7ed  call    cs:__imp_CreateMutexW
0x18004b7f3  mov     rbx, rax
0x18004b7f6  test    rax, rax
0x18004b7f9  jz      loc_18004B75B
0x18004b7ff  call    cs:__imp_GetLastError
0x18004b805  cmp     eax, 0B7h
0x18004b80a  jnz     short loc_18004B831
0x18004b80c  mov     edx, 0BB8h; dwMilliseconds
0x18004b811  mov     rcx, rbx; hHandle
0x18004b814  call    cs:__imp_WaitForSingleObject
0x18004b81a  cmp     eax, 0FFFFFFFFh
0x18004b81d  jz      loc_18004B75B
0x18004b823  cmp     eax, 102h
0x18004b828  jz      short loc_18004B831
0x18004b82a  cmp     eax, 80h
0x18004b82f  jnz     short loc_18004B7D3
0x18004b831  mov     [rbp+57h+dwData], rdi
0x18004b835  test    rdi, rdi
0x18004b838  jz      short loc_18004B8A0
0x18004b83a  mov     rcx, rdi
0x18004b83d  call    wcsistr
0x18004b842  mov     [rbp+57h+dwData], rax
0x18004b846  test    rax, rax
0x18004b849  jnz     short loc_18004B8A0
0x18004b84b  lea     rdx, gszDisplay; "DISPLAY"
0x18004b852  mov     rcx, rdi; lpString1
0x18004b855  call    cs:__imp_lstrcmpiW
0x18004b85b  test    eax, eax
0x18004b85d  jnz     short loc_18004B8DC
0x18004b85f  lea     r12, qword_18009F6F0
0x18004b866  mov     edx, 104h; unsigned __int64
0x18004b86b  mov     rcx, r12; unsigned __int16 *
0x18004b86e  lea     r8, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x18004b875  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b87a  mov     [rbp+57h+var_90], eax
0x18004b87d  test    eax, eax
0x18004b87f  js      short loc_18004B8F3
0x18004b881  lea     r8, a0000_0; "\\0000"
0x18004b888  mov     edx, 104h; unsigned __int64
0x18004b88d  mov     rcx, r12; unsigned __int16 *
0x18004b890  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004b895  mov     [rbp+57h+var_90], eax
0x18004b898  test    eax, eax
0x18004b89a  js      short loc_18004B8F3
0x18004b89c  mov     [rbp+57h+dwData], r12
0x18004b8a0  lea     rcx, [rbp+57h+var_88]; struct IDxva2Wrapper **
0x18004b8a4  call    ?CreateDxva2Wrapper@@YAJPEAPEAVIDxva2Wrapper@@@Z; CreateDxva2Wrapper(IDxva2Wrapper * *)
0x18004b8a9  mov     [rbp+57h+var_90], eax
0x18004b8ac  test    eax, eax
0x18004b8ae  js      short loc_18004B8F3
0x18004b8b0  mov     rsi, [rbp+57h+var_88]
0x18004b8b4  lea     r9, [rbp+57h+dwData]; dwData
0x18004b8b8  lea     r8, ?CalibrationMonitorEnumCallback@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x18004b8bf  mov     qword ptr [rbp+57h+var_70+8], rsi
0x18004b8c3  xor     edx, edx; lprcClip
0x18004b8c5  xor     ecx, ecx; hdc
0x18004b8c7  call    cs:__imp_EnumDisplayMonitors
0x18004b8cd  test    rdi, rdi
0x18004b8d0  jnz     short loc_18004B8E3
0x18004b8d2  cmp     dword ptr [rbp+57h+dwData+0Ch], edi
0x18004b8d5  jz      short loc_18004B8F3
0x18004b8d7  mov     eax, dword ptr [rbp+57h+var_70]
0x18004b8da  jmp     short loc_18004B8F0
0x18004b8dc  mov     eax, 80070057h
0x18004b8e1  jmp     short loc_18004B8F0
0x18004b8e3  cmp     dword ptr [rbp+57h+dwData+8], 0
0x18004b8e7  mov     eax, 80070057h
0x18004b8ec  cmovnz  eax, dword ptr [rbp+57h+var_70+4]
0x18004b8f0  mov     [rbp+57h+var_90], eax
0x18004b8f3  mov     rcx, cs:g_etwHandle
0x18004b8fa  lea     rax, [rbp+57h+var_90]
0x18004b8fe  mov     r12d, 1
0x18004b904  mov     [rbp+57h+var_40], rax
0x18004b908  mov     r8d, r12d
0x18004b90b  mov     [rbp+57h+var_38], 4
0x18004b913  lea     r9, [rbp+57h+var_40]
0x18004b917  lea     rdx, CALIBRATION_REFRESH_FINISHED
0x18004b91e  call    cs:__imp_EtwEventWrite
0x18004b924  mov     eax, cs:dword_18009E080
0x18004b92a  cmp     eax, 5
0x18004b92d  jbe     short loc_18004B988
0x18004b92f  mov     edx, r12d
0x18004b932  lea     rcx, dword_18009E080
0x18004b939  call    _tlgKeywordOn
0x18004b93e  test    al, al
0x18004b940  jz      short loc_18004B988
0x18004b942  mov     eax, [rbp+57h+var_90]
0x18004b945  lea     rdx, byte_180091A3D
0x18004b94c  mov     dword ptr [rbp+57h+var_88], eax
0x18004b94f  lea     rax, [rbp+57h+var_58]
0x18004b953  mov     [rsp+0D0h+var_98], rax
0x18004b958  lea     rax, [rbp+57h+pbIsEnabled]
0x18004b95c  mov     [rsp+0D0h+var_A0], rax
0x18004b961  lea     rax, [rbp+57h+var_50]
0x18004b965  mov     [rsp+0D0h+var_A8], rax
0x18004b96a  lea     rax, [rbp+57h+var_88]
0x18004b96e  mov     [rsp+0D0h+var_B0], rax
0x18004b973  mov     [rbp+57h+var_58], 2000000h
0x18004b97b  mov     [rbp+57h+pbIsEnabled], r14d
0x18004b97f  mov     [rbp+57h+var_50], rdi
0x18004b983  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18004b988  test    rbx, rbx
0x18004b98b  jz      short loc_18004B99F
0x18004b98d  mov     rcx, rbx; hMutex
0x18004b990  call    cs:__imp_ReleaseMutex
0x18004b996  mov     rcx, rbx; hObject
0x18004b999  call    cs:__imp_CloseHandle
0x18004b99f  mov     edx, 8; unsigned __int64
0x18004b9a4  mov     rcx, rsi; void *
0x18004b9a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004b9ac  mov     eax, [rbp+57h+var_90]
0x18004b9af  mov     rcx, [rbp+57h+var_30]
0x18004b9b3  xor     rcx, rsp; StackCookie
0x18004b9b6  call    __security_check_cookie
0x18004b9bb  mov     rbx, [rsp+0D0h+arg_10]
0x18004b9c3  add     rsp, 0B0h
0x18004b9ca  pop     r14
0x18004b9cc  pop     r12
0x18004b9ce  pop     rdi
0x18004b9cf  pop     rsi
0x18004b9d0  pop     rbp
0x18004b9d1  retn
```
