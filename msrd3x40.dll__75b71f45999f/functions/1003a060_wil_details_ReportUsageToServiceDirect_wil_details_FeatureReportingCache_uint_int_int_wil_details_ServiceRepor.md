# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,ulong,uchar)

- ea: `0x1003a060`
- end: `0x1003a202`
- name: `?ReportUsageToServiceDirect@details@wil@@YGHPAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@IKE@Z`
- size: `418`
- prototype: `int __stdcall __high(struct wil_details_FeatureReportingCache *, unsigned int, int, int, enum wil_details_ServiceReportingKind, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1003a210`

## callees

- `0x1000e680`
- `0x1000eb60`
- `0x10039b40`
- `0x10039e30`
- `0x1003a060`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1003a13a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1003a13a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1003a182`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1003a182`

## pseudocode

```c
BOOL __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8)
{
  int *v9; // eax
  unsigned int v10; // ecx
  int v11; // eax
  void (__thiscall *v12)(_DWORD, unsigned int, unsigned int, int, _DWORD); // esi
  _DWORD *v13; // eax
  void (__thiscall *v14)(_DWORD, _DWORD *, _DWORD (__stdcall *)(void *), int); // esi
  void (__thiscall *v15)(_DWORD, unsigned int, unsigned int, _DWORD, _DWORD); // esi
  unsigned int v16; // eax
  int v18; // [esp+0h] [ebp-50h]
  int v19; // [esp+4h] [ebp-4Ch]
  _BYTE v20[24]; // [esp+18h] [ebp-38h] BYREF
  int v21; // [esp+30h] [ebp-20h]
  struct wil_details_FeatureReportingCache *v22; // [esp+34h] [ebp-1Ch]
  int v23; // [esp+38h] [ebp-18h]
  unsigned int v24; // [esp+3Ch] [ebp-14h]
  int v25; // [esp+40h] [ebp-10h]
  int v26; // [esp+4Ch] [ebp-4h]

  v22 = a1;
  v9 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v20, v18, v19);
  v23 = *v9;
  v21 = v9[1];
  v10 = v9[2];
  v11 = v9[4];
  v24 = v10;
  v25 = v11;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(g_wil_details_RecordSRUMFeatureUsage, a2, a5, 1);
  if ( v23 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      a2,
      v22);
  if ( v21 )
  {
    v12 = (void (__thiscall *)(_DWORD, unsigned int, unsigned int, int, _DWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v12 = (void (__thiscall *)(_DWORD, unsigned int, unsigned int, int, _DWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v12(v12, a2, v24, v21, 0);
    }
  }
  if ( !v25 )
  {
    v26 = 0;
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_10066544);
      if ( !dword_10066578 )
      {
        v13 = (_DWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (__stdcall *)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned int,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&();
        v14 = (void (__thiscall *)(_DWORD, _DWORD *, _DWORD (__stdcall *)(void *), int))g_wil_details_internalSubscribeFeatureStateChangeNotification;
        if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
          || (v14 = (void (__thiscall *)(_DWORD, _DWORD *, _DWORD (__stdcall *)(void *), int))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
        {
          v14(v14, v13, _lambda_c564bccc905f31bdce86a4ddfea345e8_::_lambda_invoker_stdcall_, -1);
        }
        else
        {
          *v13 = 0;
        }
      }
      ReleaseSRWLockExclusive(&stru_10066544);
    }
    v26 = -1;
  }
  if ( a3 )
  {
    v15 = (void (__thiscall *)(_DWORD, unsigned int, unsigned int, _DWORD, _DWORD))g_wil_details_internalRecordFeatureUsage;
    v16 = a5 | 0x80000000;
    if ( !a4 )
      v16 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v15 = (void (__thiscall *)(_DWORD, unsigned int, unsigned int, _DWORD, _DWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v15(v15, a2, v16, 0, 0);
    }
  }
  if ( !v25 && g_wil_details_realtimeFeatureUsageHook )
    g_wil_details_realtimeFeatureUsageHook(g_wil_details_realtimeFeatureUsageHook, a2, a5, a8);
  return v25 == 0;
}

```

## disassembly

```asm
0x1003a060  mov     edi, edi
0x1003a062  push    ebp
0x1003a063  mov     ebp, esp
0x1003a065  push    0FFFFFFFFh
0x1003a067  push    offset ?ReportUsageToServiceDirect@details@wil@@YGHPAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@IKE@Z_SEH
0x1003a06c  mov     eax, large fs:0
0x1003a072  push    eax
0x1003a073  sub     esp, 2Ch
0x1003a076  push    ebx
0x1003a077  push    esi
0x1003a078  push    edi
0x1003a079  mov     eax, ___security_cookie
0x1003a07e  xor     eax, ebp
0x1003a080  push    eax
0x1003a081  lea     eax, [ebp+var_C]
0x1003a084  mov     large fs:0, eax
0x1003a08a  mov     edi, edx
0x1003a08c  mov     eax, ecx
0x1003a08e  mov     [ebp+var_1C], eax
0x1003a091  mov     ebx, [ebp+arg_8]
0x1003a094  lea     ecx, [ebp+var_38]
0x1003a097  sub     esp, 8
0x1003a09a  mov     edx, ebx
0x1003a09c  push    ecx
0x1003a09d  mov     ecx, eax
0x1003a09f  call    _wil_details_FeatureReporting_RecordUsageInCache@16; wil_details_FeatureReporting_RecordUsageInCache(x,x,x,x)
0x1003a0a4  mov     esi, _g_wil_details_RecordSRUMFeatureUsage
0x1003a0aa  mov     ecx, [eax]
0x1003a0ac  mov     [ebp+var_18], ecx
0x1003a0af  mov     ecx, [eax+4]
0x1003a0b2  mov     [ebp+var_20], ecx
0x1003a0b5  mov     ecx, [eax+8]
0x1003a0b8  mov     eax, [eax+10h]
0x1003a0bb  mov     [ebp+var_14], ecx
0x1003a0be  mov     [ebp+var_10], eax
0x1003a0c1  test    esi, esi
0x1003a0c3  jz      short loc_1003A0DF
0x1003a0c5  test    ebx, ebx
0x1003a0c7  jz      short loc_1003A0D1
0x1003a0c9  lea     eax, [ebx-64h]
0x1003a0cc  cmp     eax, 31h ; '1'
0x1003a0cf  ja      short loc_1003A0DF
0x1003a0d1  push    1
0x1003a0d3  push    ebx; unsigned int
0x1003a0d4  push    edi; void *
0x1003a0d5  mov     ecx, esi
0x1003a0d7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003a0dd  call    esi ; _g_wil_details_RecordSRUMFeatureUsage
0x1003a0df  cmp     [ebp+var_18], 0
0x1003a0e3  jz      short loc_1003A0F3
0x1003a0e5  push    [ebp+var_1C]; struct wil_details_FeatureReportingCache *
0x1003a0e8  mov     ecx, offset ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1003a0ed  push    edi; unsigned int
0x1003a0ee  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QAEXIPAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1003a0f3  mov     eax, [ebp+var_20]
0x1003a0f6  test    eax, eax
0x1003a0f8  jz      short loc_1003A11F
0x1003a0fa  mov     esi, _g_wil_details_internalRecordFeatureUsage
0x1003a100  test    esi, esi
0x1003a102  jnz     short loc_1003A10E
0x1003a104  mov     esi, _g_wil_details_apiRecordFeatureUsage
0x1003a10a  test    esi, esi
0x1003a10c  jz      short loc_1003A11F
0x1003a10e  push    0
0x1003a110  push    eax
0x1003a111  push    [ebp+var_14]; unsigned int
0x1003a114  mov     ecx, esi
0x1003a116  push    edi; void *
0x1003a117  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003a11d  call    esi ; _g_wil_details_internalRecordFeatureUsage
0x1003a11f  cmp     [ebp+var_10], 0
0x1003a123  jnz     short loc_1003A18F
0x1003a125  mov     [ebp+var_4], 0
0x1003a12c  mov     eax, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1003a131  test    eax, eax
0x1003a133  jz      short loc_1003A188
0x1003a135  push    offset stru_10066544; SRWLock
0x1003a13a  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1003a140  cmp     dword_10066578, 0
0x1003a147  jnz     short loc_1003A17D
0x1003a149  mov     ecx, offset dword_10066578
0x1003a14e  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6GXPAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QAEPAPAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<uint,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x1003a153  mov     esi, _g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1003a159  test    esi, esi
0x1003a15b  jz      short loc_1003A171
0x1003a15d  push    0FFFFFFFFh
0x1003a15f  push    offset ?_lambda_invoker_stdcall_@_lambda_c564bccc905f31bdce86a4ddfea345e8_@@CG@PAX@Z; unsigned int
0x1003a164  push    eax; void *
0x1003a165  mov     ecx, esi
0x1003a167  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003a16d  call    esi ; _g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1003a16f  jmp     short loc_1003A17D
0x1003a171  mov     esi, _g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1003a177  test    esi, esi
0x1003a179  jnz     short loc_1003A15D
0x1003a17b  mov     [eax], esi
0x1003a17d  push    offset stru_10066544; SRWLock
0x1003a182  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1003a188  mov     [ebp+var_4], 0FFFFFFFFh
0x1003a18f  cmp     [ebp+arg_0], 0
0x1003a193  jz      short loc_1003A1C7
0x1003a195  mov     esi, _g_wil_details_internalRecordFeatureUsage
0x1003a19b  mov     eax, ebx
0x1003a19d  or      eax, 80000000h
0x1003a1a2  cmp     [ebp+arg_4], 0
0x1003a1a6  cmovz   eax, ebx
0x1003a1a9  test    esi, esi
0x1003a1ab  jnz     short loc_1003A1B7
0x1003a1ad  mov     esi, _g_wil_details_apiRecordFeatureUsage
0x1003a1b3  test    esi, esi
0x1003a1b5  jz      short loc_1003A1C7
0x1003a1b7  push    0
0x1003a1b9  push    0
0x1003a1bb  push    eax; unsigned int
0x1003a1bc  push    edi; void *
0x1003a1bd  mov     ecx, esi
0x1003a1bf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003a1c5  call    esi ; _g_wil_details_internalRecordFeatureUsage
0x1003a1c7  cmp     [ebp+var_10], 0
0x1003a1cb  jnz     short loc_1003A1E6
0x1003a1cd  mov     esi, _g_wil_details_realtimeFeatureUsageHook
0x1003a1d3  test    esi, esi
0x1003a1d5  jz      short loc_1003A1E6
0x1003a1d7  push    [ebp+arg_14]
0x1003a1da  mov     ecx, esi
0x1003a1dc  push    ebx; unsigned int
0x1003a1dd  push    edi; void *
0x1003a1de  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003a1e4  call    esi ; _g_wil_details_realtimeFeatureUsageHook
0x1003a1e6  xor     eax, eax
0x1003a1e8  cmp     [ebp+var_10], eax
0x1003a1eb  setz    al
0x1003a1ee  mov     ecx, [ebp+var_C]
0x1003a1f1  mov     large fs:0, ecx
0x1003a1f8  pop     ecx
0x1003a1f9  pop     edi
0x1003a1fa  pop     esi
0x1003a1fb  pop     ebx
0x1003a1fc  mov     esp, ebp
0x1003a1fe  pop     ebp
0x1003a1ff  retn    18h
0x1005f070  jmp     ds:__imp____std_terminate
0x10060e10  nop
0x10060e11  nop
0x10060e12  mov     edx, [esp-4+arg_4]
0x10060e16  lea     eax, [edx+0Ch]
0x10060e19  mov     ecx, [edx-3Ch]
0x10060e1c  xor     ecx, eax; StackCookie
0x10060e1e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060e23  mov     eax, offset stru_10062B00
0x10060e28  jmp     ___CxxFrameHandler3
```
