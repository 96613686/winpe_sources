# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000ef64`
- end: `0x18000efda`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000f348`

## callees

- `0x18000ef64`
- `0x18000efe0`
- `0x18000f3dc`
- `0x180010980`

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
0x18000ef64  mov     [rsp+arg_10], r8d
0x18000ef69  push    rbx
0x18000ef6a  sub     rsp, 50h
0x18000ef6e  mov     ebx, edx
0x18000ef70  mov     r9, rdx
0x18000ef73  and     ebx, 1
0x18000ef76  mov     ecx, r8d
0x18000ef79  mov     edx, ebx
0x18000ef7b  call    wil_details_MapReportingKind
0x18000ef80  mov     r8d, eax
0x18000ef83  mov     rdx, r9
0x18000ef86  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000ef8b  test    eax, eax
0x18000ef8d  jz      short loc_18000EFD3
0x18000ef8f  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000ef96  test    rax, rax
0x18000ef99  jz      short loc_18000EFD3
0x18000ef9b  mov     rdx, cs:off_180018DB0
0x18000efa2  lea     rcx, [rsp+58h+arg_10]
0x18000efa7  mov     [rsp+58h+var_20], 1
0x18000efb0  mov     r9d, ebx
0x18000efb3  mov     [rsp+58h+var_28], 0
0x18000efb8  xor     r8d, r8d
0x18000efbb  mov     [rsp+58h+var_30], 0
0x18000efc4  mov     [rsp+58h+var_38], rcx
0x18000efc9  mov     ecx, 3316E09h
0x18000efce  call    _guard_dispatch_icall
0x18000efd3  add     rsp, 50h
0x18000efd7  pop     rbx
0x18000efd8  retn
```
