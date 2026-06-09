# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000e120`
- end: `0x14000e198`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000dd78`

## callees

- `0x14000e120`
- `0x14000e1a0`
- `0x14000e2a4`
- `0x140010240`

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
  char v8; // [rsp+30h] [rbp-38h]
  int v9[6]; // [rsp+50h] [rbp-18h] BYREF

  v3 = a2 & 1;
  v9[0] = 3;
  v4 = wil_details_MapReportingKind(3, a2 & 1, a3, a2);
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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(29204454, &Feature_NegoexPassesStructuredExceptions_logged_traits, 0, v3, v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000e120  push    rbx
0x14000e122  sub     rsp, 60h
0x14000e126  mov     ebx, edx
0x14000e128  mov     r9, rdx
0x14000e12b  mov     ecx, 3
0x14000e130  and     ebx, 1
0x14000e133  mov     edx, ebx
0x14000e135  mov     [rsp+68h+var_18], ecx
0x14000e139  call    wil_details_MapReportingKind
0x14000e13e  mov     r8d, eax
0x14000e141  mov     rdx, r9
0x14000e144  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000e149  test    eax, eax
0x14000e14b  jz      short loc_14000E191
0x14000e14d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000e154  test    rax, rax
0x14000e157  jz      short loc_14000E191
0x14000e159  mov     rdx, cs:off_140017898
0x14000e160  lea     rcx, [rsp+68h+var_18]
0x14000e165  mov     [rsp+68h+var_30], 1
0x14000e16e  mov     r9d, ebx
0x14000e171  mov     [rsp+68h+var_38], 0
0x14000e176  xor     r8d, r8d
0x14000e179  mov     [rsp+68h+var_40], 0
0x14000e182  mov     [rsp+68h+var_48], rcx
0x14000e187  mov     ecx, 1BD9FE6h
0x14000e18c  call    _guard_dispatch_icall
0x14000e191  add     rsp, 60h
0x14000e195  pop     rbx
0x14000e196  retn
```
