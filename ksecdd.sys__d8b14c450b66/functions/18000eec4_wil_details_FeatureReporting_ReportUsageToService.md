# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000eec4`
- end: `0x18000ef3a`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000f2e0`

## callees

- `0x18000eec4`
- `0x18000ef40`
- `0x18000f374`
- `0x180010920`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v3 = a2 & 1;
  v4 = wil_details_MapReportingKind((unsigned int)a3, a2 & 1, a3, a2);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     v5,
                                                                                                     v6,
                                                                                                     v4);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(53571081, &Feature_Schannel_SslCopyTlsExtensions_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000eec4  mov     [rsp+arg_10], r8d
0x18000eec9  push    rbx
0x18000eeca  sub     rsp, 50h
0x18000eece  mov     ebx, edx
0x18000eed0  mov     r9, rdx
0x18000eed3  and     ebx, 1
0x18000eed6  mov     ecx, r8d
0x18000eed9  mov     edx, ebx
0x18000eedb  call    wil_details_MapReportingKind
0x18000eee0  mov     r8d, eax
0x18000eee3  mov     rdx, r9
0x18000eee6  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000eeeb  test    eax, eax
0x18000eeed  jz      short loc_18000EF33
0x18000eeef  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000eef6  test    rax, rax
0x18000eef9  jz      short loc_18000EF33
0x18000eefb  mov     rdx, cs:off_180018D90
0x18000ef02  lea     rcx, [rsp+58h+arg_10]
0x18000ef07  mov     [rsp+58h+var_20], 1
0x18000ef10  mov     r9d, ebx
0x18000ef13  mov     [rsp+58h+var_28], 0
0x18000ef18  xor     r8d, r8d
0x18000ef1b  mov     [rsp+58h+var_30], 0
0x18000ef24  mov     [rsp+58h+var_38], rcx
0x18000ef29  mov     ecx, 3316E09h
0x18000ef2e  call    _guard_dispatch_icall
0x18000ef33  add     rsp, 50h
0x18000ef37  pop     rbx
0x18000ef38  retn
```
