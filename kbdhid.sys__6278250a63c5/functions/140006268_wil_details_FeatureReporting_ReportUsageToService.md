# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140006268`
- end: `0x1400062de`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14001187c`

## callees

- `0x140006268`
- `0x1400062e4`
- `0x1400063fc`
- `0x140007170`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(24586078, &Feature_DefaultCrashHotKey_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006268  mov     [rsp+arg_10], r8d
0x14000626d  push    rbx
0x14000626e  sub     rsp, 50h
0x140006272  mov     ebx, edx
0x140006274  mov     r9, rdx
0x140006277  and     ebx, 1
0x14000627a  mov     ecx, r8d
0x14000627d  mov     edx, ebx
0x14000627f  call    wil_details_MapReportingKind
0x140006284  mov     r8d, eax
0x140006287  mov     rdx, r9
0x14000628a  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000628f  test    eax, eax
0x140006291  jz      short loc_1400062D7
0x140006293  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000629a  test    rax, rax
0x14000629d  jz      short loc_1400062D7
0x14000629f  mov     rdx, cs:off_14000A2A8
0x1400062a6  lea     rcx, [rsp+58h+arg_10]
0x1400062ab  mov     [rsp+58h+var_20], 1
0x1400062b4  mov     r9d, ebx
0x1400062b7  mov     [rsp+58h+var_28], 0
0x1400062bc  xor     r8d, r8d
0x1400062bf  mov     [rsp+58h+var_30], 0
0x1400062c8  mov     [rsp+58h+var_38], rcx
0x1400062cd  mov     ecx, 177275Eh
0x1400062d2  call    _guard_dispatch_icall
0x1400062d7  add     rsp, 50h
0x1400062db  pop     rbx
0x1400062dc  retn
```
